---
title: Hinzufügen von Unterstützung für Anmeldeinformationen zu PowerShell-Funktionen
description: Erfahren Sie, wie Sie Ihren PowerShell-Skripts, -Funktionen und -Cmdlets Parameter mit Anmeldeinformationen hinzufügen.
ms.date: 10/29/2020
ms.custom: contributor-JoshDuffney
ms.openlocfilehash: fb85d47121dc106ae04742254f418e2c727f6157
ms.sourcegitcommit: 196c7f8cd24560cac70c88acc89909f17a86aea9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2020
ms.locfileid: "93143157"
---
# <a name="add-credential-support-to-powershell-functions"></a>Hinzufügen von Unterstützung für Anmeldeinformationen zu PowerShell-Funktionen

> [!NOTE]
> Die [Originalversion][] dieses Artikels ist im Blog von [@joshduffney][] erschienen. Dieser Artikel wurde für die Einbindung in diese Website bearbeitet. Das PowerShell-Team dankt Josh Duffney, dass er uns diesen Inhalt zur Verfügung stellt. Weitere Informationen finden Sie in seinem Blog unter [duffney.io][].

In diesem Artikel erfahren Sie, wie Sie PowerShell-Funktionen Parameter mit Anmeldeinformationen hinzufügen und warum dies gewünscht ist. Mit einem Parameter mit Anmeldeinformationen können Sie die Funktion oder das Cmdlet als ein anderer Benutzer ausführen. Der häufigste Zweck ist das Ausführen der Funktion oder des Cmdlets mit einem Benutzerkonto mit erhöhten Rechten.

Beispielsweise verfügt das Cmdlet `New-ADUser` über den Parameter **Credential** , mit dem Sie Anmeldeinformationen eines Domänenadministrators bereitstellen können, um in einer Domäne ein Konto zu erstellen. Es wird angenommen, dass Ihr normales Konto, mit dem die PowerShell-Sitzung ausgeführt wird, nicht bereits über diesen Zugriff verfügt.

## <a name="creating-credential-object"></a>Erstellen des Objekts mit Anmeldeinformationen

Das Objekt [PSCredential][] stellt sicherheitsrelevante Anmeldeinformationen wie einen Benutzernamen und ein Kennwort dar. Das Objekt kann als Parameter an eine Funktion übergeben werden, die in diesem Objekt mit Anmeldeinformationen mit dem entsprechenden Benutzerkonto ausgeführt wird. Es gibt mehrere Möglichkeiten, ein Objekt mit Anmeldeinformationen zu erstellen. Die erste ist das PowerShell-Cmdlet `Get-Credential`. Wenn Sie es ohne Parameter ausführen, werden Sie aufgefordert, einen Benutzernamen und ein Kennwort einzugeben. Oder Sie können das Cmdlet mit optionalen Parametern aufrufen.

Um den Domänennamen und den Benutzernamen im Voraus anzugeben, können Sie entweder den Parameter **Credential** oder den Parameter **UserName** verwenden. Beim Parameter **UserName** müssen Sie auch einen Wert für **Message** angeben. Der folgende Code veranschaulicht die Verwendung des Cmdlets. Sie können das Objekt mit Anmeldeinformationen auch in einer Variablen speichern, damit Sie diese mehrmals verwenden können. Im folgenden Beispiel wird das Objekt mit Anmeldeinformationen in der Variablen `$Cred`gespeichert.

```powershell
$Cred = Get-Credential
$Cred = Get-Credential -Credential domain\user
$Cred = Get-Credential -UserName domain\user -Message 'Enter Password'
```

Mitunter ist es nicht möglich, die im vorherigen Beispiel gezeigte interaktive Methode zum Erstellen von Objekten mit Anmeldeinformationen einzusetzen. Die meisten Automatisierungstools erfordern eine nicht interaktive Methode. Erstellen Sie eine sichere Zeichenfolge mit dem Kennwort, um Anmeldeinformationen ohne Interaktion mit dem Benutzer zu erstellen. Übergeben Sie dann die sichere Zeichenfolge und den Benutzernamen an die `System.Management.Automation.PSCredential()`-Methode.

Erstellen Sie mit dem folgenden Befehl eine sichere Zeichenfolge mit dem Kennwort:

```powershell
ConvertTo-SecureString "MyPlainTextPassword" -AsPlainText -Force
```

**AsPlainText** und **Force** sind Pflichtparameter. Ohne diese Parameter erhalten Sie eine Warnmeldung, dass Sie keinen Klartext in eine sichere Zeichenfolge eingeben dürfen. PowerShell gibt diese Warnung zurück, da das Kennwort im Klartext in verschiedenen Protokollen aufgezeichnet wird. Nachdem Sie eine sichere Zeichenfolge erstellt haben, müssen Sie sie an die `PSCredential()`-Methode übergeben, um das Objekt für Anmeldeinformationen zu erstellen. Im folgenden Beispiel enthält die Variable `$password` die sichere Zeichenfolge `$Cred` mit dem Objekt mit Anmeldeinformationen.

```powershell
$password = ConvertTo-SecureString "MyPlainTextPassword" -AsPlainText -Force
$Cred = New-Object System.Management.Automation.PSCredential ("username", $password)
```

Nachdem Sie nun wissen, wie Objekte mit Anmeldeinformationen erstellt werden, können Sie Ihren PowerShell-Funktionen Parameter mit Anmeldeinformationen hinzufügen.

## <a name="adding-a-credential-parameter"></a>Hinzufügen eines Parameters mit Anmeldeinformationen

Wie bei jedem anderen Parameter beginnen Sie, indem Sie ihn dem Block `param` Ihrer Funktion hinzufügen.
Es wird empfohlen, den Parameter `$Credential` zu nennen, weil dieser von vorhandenen PowerShell-Cmdlets verwendet wird. Der Typ des Parameters muss `[System.Management.Automation.PSCredential]` sein.

Das folgende Beispiel zeigt den Parameterblock für eine Funktion mit dem Namen `Get-Something`. Sie hat zwei Parameter: `$Name` und `$Credential`.

```powershell
function Get-Something {
    param(
        $Name,
        [System.Management.Automation.PSCredential]$Credential
    )
```

Der Code in diesem Beispiel reicht für einen funktionierenden Parameter mit Anmeldeinformationen aus. Es gibt jedoch ein paar Dinge, die Sie hinzufügen können, um ihn stabiler zu machen.

- Fügen Sie das Überprüfungsattribut `[ValidateNotNull()]` hinzu, um zu prüfen, ob der Wert an **Credential** übergeben wird. Wenn der Parameterwert NULL ist, verhindert dieses Attribut die Ausführung der Funktion mit ungültigen Anmeldeinformationen.

- Fügen Sie `[System.Management.Automation.Credential()]` hinzu. Dies ermöglicht Ihnen die Eingabe eines Benutzernamens als Zeichenfolge und eine interaktive Abfrage des Kennworts.

- Legen Sie den Standardwert des Parameters `$Credential` auf `[System.Management.Automation.PSCredential]::Empty` fest. Ihre Funktion übergibt dieses `$Credential`-Objekt möglicherweise an vorhandene PowerShell-Cmdlets. Das Angeben eines NULL-Werts für das Cmdlet, das in Ihrer Funktion aufgerufen wird, verursacht einen Fehler. Durch Angeben eines leeren Objekts mit Anmeldeinformationen wird dieser Fehler vermieden.

> [!TIP]
> Einige Cmdlets, die einen Parameter mit Anmeldeinformationen akzeptieren, unterstützen `[System.Management.Automation.PSCredential]::Empty` nicht. Eine Problemumgehung finden Sie im Abschnitt [Umgang mit Legacy-Cmdlets](#dealing-with-legacy-cmdlets).

## <a name="using-credential-parameters"></a>Verwenden von Parametern mit Anmeldeinformationen

Im folgenden Beispiel wird die Verwendung von Parametern mit Anmeldeinformationen veranschaulicht. Dieses Beispiel zeigt eine Funktion mit dem Namen `Set-RemoteRegistryValue`, die aus [The Pester Book][] stammt. Diese Funktion definiert den Parameter mit Anmeldeinformationen mithilfe der im vorherigen Abschnitt beschriebenen Techniken. Die Funktion ruft `Invoke-Command` mithilfe der Variablen `$Credential` auf, die von der Funktion erstellt wurde. Dies ermöglicht Ihnen das Ändern des Benutzers, der `Invoke-Command` ausführt. Da der Standardwert von `$Credential` leere Anmeldeinformationen sind, kann die Funktion ohne Angabe von Anmeldeinformationen ausgeführt werden.

```powershell
function Set-RemoteRegistryValue {
    param(
        $ComputerName,
        $Path,
        $Name,
        $Value,
        [ValidateNotNull()]
        [System.Management.Automation.PSCredential]
        [System.Management.Automation.Credential()]
        $Credential = [System.Management.Automation.PSCredential]::Empty
    )
        $null = Invoke-Command -ComputerName $ComputerName -ScriptBlock {
            Set-ItemProperty -Path $using:Path -Name $using:Name -Value $using:Value
        } -Credential $Credential
}
```

In den folgenden Abschnitten werden verschiedene Methoden zum Bereitstellen von Anmeldeinformationen für `Set-RemoteRegistryValue` erläutert.

### <a name="prompting-for-credentials"></a>Anfordern von Anmeldeinformationen

Die Verwendung von `Get-Credential` in Klammern `()` zur Laufzeit bewirkt, dass `Get-credential` zuerst ausgeführt wird. Sie werden aufgefordert, einen Benutzernamen und ein Kennwort einzugeben. Sie könnten die Parameter **Credential** oder **UserName** von `Get-credential` verwenden, um den Benutzernamen und die Domäne vorab auszufüllen. Im folgenden Beispiel wird eine Technik namens „Splatting“ verwendet, um Parameter an die `Set-RemoteRegistryValue`-Funktion zu übergeben. Weitere Informationen zu Splatting finden Sie im Artikel [about_Splatting][].

```powershell
$remoteKeyParams = @{
    ComputerName = $env:COMPUTERNAME
    Path = 'HKLM:\SOFTWARE\Microsoft\WebManagement\Server'
    Name = 'EnableRemoteManagement'
    Value = '1'
}

Set-RemoteRegistryValue @remoteKeyParams -Credential (Get-Credential)
```

![Abrufen von Anmeldeinformationen zur Laufzeit](./media/add-credentials-to-powershell-functions/GetCredAtRunTime.gif)

Die Verwendung von `(Get-Credential)` scheint umständlich. Wenn Sie den Parameter **Credential** nur mit einem Benutzernamen verwenden, fordert das Cmdlet normalerweise automatisch zur Eingabe des Kennworts auf. Das Attribut `[System.Management.Automation.Credential()]` ermöglicht dieses Verhalten.

```powershell
$remoteKeyParams = @{
    ComputerName = $env:COMPUTERNAME
    Path = 'HKLM:\SOFTWARE\Microsoft\WebManagement\Server'
    Name = 'EnableRemoteManagement'
    Value = '1'
}

Set-RemoteRegistryValue @remoteKeyParams -Credential duffney
```

![Aufforderung zur Eingabe von Anmeldeinformationen](./media/add-credentials-to-powershell-functions/GetCredsPrompt.gif)

> [!NOTE]
> Um den angezeigten Registrierungswert festzulegen, wird in diesen Beispielen davon ausgegangen, dass die **Webserver** -Features von Windows installiert sind. Führen Sie bei Bedarf `Install-WindowsFeature Web-Server` und `Install-WindowsFeature web-mgmt-tools` aus.

### <a name="provide-credentials-in-a-variable"></a>Angeben von Anmeldeinformationen in einer Variablen

Sie können eine Variable für Anmeldeinformationen auch vorab auffüllen und an den **Credential** -Parameter der `Set-RemoteRegistryValue`-Funktion übergeben. Verwenden Sie diese Methode mit Continuous Integration-/Continuous Deployment-Tools (CI/CD) wie Jenkins, TeamCity und Octopus Deploy. Ein Beispiel für Jenkins finden Sie im Blogbeitrag von Matthew Hodgkins [Automating with Jenkins and PowerShell on Windows - Part 2][].

In diesem Beispiel wird die .NET-Methode verwendet, um das Objekt für Anmeldeinformationen und eine sichere Zeichenfolge für die Übergabe des Kennworts zu erstellen.

```powershell
$password = ConvertTo-SecureString "P@ssw0rd" -AsPlainText -Force
$Cred = New-Object System.Management.Automation.PSCredential ("duffney", $password)

$remoteKeyParams = @{
    ComputerName = $env:COMPUTERNAME
    Path = 'HKLM:\SOFTWARE\Microsoft\WebManagement\Server'
    Name = 'EnableRemoteManagement'
    Value = '1'
}

Set-RemoteRegistryValue @remoteKeyParams -Credential $Cred
```

In diesem Beispiel wird die sichere Zeichenfolge mit einem Kennwort in Klartext erstellt. Alle zuvor erwähnten CI/CD-Tools verfügen über eine sichere Methode zur Bereitstellung dieses Kennworts zur Laufzeit. Ersetzen Sie bei Nutzung dieser Tools das Kennwort im Klartext durch die Variable, die in dem von Ihnen verwendeten CI/CD-Tool definiert ist.

### <a name="run-without-credentials"></a>Ausführung ohne Anmeldeinformationen

Da `$Credential` standardmäßig ein leeres Anmeldeinformationsobjekt ist, können Sie den Befehl, wie in diesem Beispiel gezeigt, ohne Anmeldeinformationen ausführen:

```powershell
$remoteKeyParams = @{
    ComputerName = $env:COMPUTERNAME
    Path = 'HKLM:\SOFTWARE\Microsoft\WebManagement\Server'
    Name = 'EnableRemoteManagement'
    Value = '1'
}

Set-RemoteRegistryValue @remoteKeyParams
```

## <a name="dealing-with-legacy-cmdlets"></a>Umgang mit Legacy-Cmdlets

Nicht alle Cmdlets unterstützen Objekte mit Anmeldeinformationen oder lassen leere Anmeldeinformationen zu. Stattdessen fordert das Cmdlet Parameter für Benutzername und Kennwort als Zeichenfolgen an. Es gibt mehrere Möglichkeiten, diese Einschränkung zu umgehen.

### <a name="using-if-else-to-handle-empty-credentials"></a>Verwenden von IF-ELSE bei leeren Anmeldeinformationen

In diesem Szenario akzeptiert das Cmdlet, das Sie ausführen möchten, kein leeres Objekt für Anmeldeinformationen. Bei diesem Beispiel wird der Parameter **Credential** nur dann `Invoke-Command` hinzugefügt, wenn er nicht leer ist. Andernfalls wird `Invoke-Command` ohne den Parameter **Credential** ausgeführt.

```powershell
function Set-RemoteRegistryValue {
    param(
        $ComputerName,
        $Path,
        $Name,
        $Value,
        [ValidateNotNull()]
        [System.Management.Automation.PSCredential]
        [System.Management.Automation.Credential()]
        $Credential = [System.Management.Automation.PSCredential]::Empty
    )

    if($Credential -ne [System.Management.Automation.PSCredential]::Empty) {
        Invoke-Command -ComputerName:$ComputerName -Credential:$Credential  {
            Set-ItemProperty -Path $using:Path -Name $using:Name -Value $using:Value
        }
    } else {
        Invoke-Command -ComputerName:$ComputerName {
            Set-ItemProperty -Path $using:Path -Name $using:Name -Value $using:Value
        }
    }
}
```

### <a name="using-splatting-to-handle-empty-credentials"></a>Verwenden von Splatting bei leeren Anmeldeinformationen

Bei diesem Beispiel wird der Parameter „Splatting“ verwendet, um das Legacy-Cmdlet aufzurufen. Das Objekt `$Credential` wird der Hashtabelle für Splatting bedingt hinzugefügt und vermeidet, dass der Skriptblock `Invoke-Command` wiederholt werden muss. Weitere Informationen zu Splatting innerhalb von Funktionen finden Sie im Blogbeitrag [Splatting Parameters Inside Advanced Functions][].

```powershell
function Set-RemoteRegistryValue {
    param(
        $ComputerName,
        $Path,
        $Name,
        $Value,
        [ValidateNotNull()]
        [System.Management.Automation.PSCredential]
        [System.Management.Automation.Credential()]
        $Credential = [System.Management.Automation.PSCredential]::Empty
    )

        $Splat = @{
            ComputerName = $ComputerName
        }

        if ($Credential -ne [System.Management.Automation.PSCredential]::Empty) {
            $Splat['Credential'] = $Credential
        }

        $null = Invoke-Command -ScriptBlock {
            Set-ItemProperty -Path $using:Path -Name $using:Name -Value $using:Value
        } @splat
}
```

### <a name="working-with-string-passwords"></a>Arbeiten mit Zeichenfolgen als Kennwörtern

Das Cmdlet `Invoke-Sqlcmd` ist ein Beispiel eines Cmdlets, das eine Zeichenfolge als Kennwort akzeptiert.
`Invoke-Sqlcmd` ermöglicht das Ausführen der einfachen SQL-Anweisungen INSERT, UPDATE und DELETE. `Invoke-Sqlcmd` erfordert einen Benutzernamen in Klartext und ein Kennwort anstelle eines sichereren Objekts mit Anmeldeinformationen. Dieses Beispiel zeigt, wie Benutzername und Kennwort aus einem Objekt mit Anmeldeinformationen extrahiert werden.

Die `Get-AllSQLDatabases`-Funktion in diesem Beispiel ruft das Cmdlet `Invoke-Sqlcmd` auf, um alle in einer SQL Server-Instanz enthaltenen Datenbanken abzufragen. Die Funktion definiert den Parameter **Credential** mit dem gleichen Attribut, das in den vorherigen Beispielen verwendet wurde. Da Benutzername und Kennwort innerhalb der Variablen `$Credential` vorhanden sind, können Sie diese Werte für die Verwendung mit `Invoke-Sqlcmd` extrahieren.

Der Benutzername ist über die Eigenschaft **UserName** der Variablen `$Credential` verfügbar. Zum Abrufen des Kennworts müssen Sie die `GetNetworkCredential()`-Methode des `$Credential`-Objekts verwenden. Die Werte werden in Variablen extrahiert, die einer Hashtabelle hinzugefügt werden, die zum Splatting von Parametern in `Invoke-Sqlcmd` dient.

```powershell
function Get-AllSQLDatabases {
    param(
        $SQLServer,
        [ValidateNotNull()]
        [System.Management.Automation.PSCredential]
        [System.Management.Automation.Credential()]
        $Credential = [System.Management.Automation.PSCredential]::Empty
    )

        $UserName = $Credential.UserName
        $Password = $Credential.GetNetworkCredential().Password

        $splat = @{
            UserName = $UserName
            Password = $Password
            ServerInstance = 'SQLServer'
            Query = "Select * from Sys.Databases"
        }

        Invoke-Sqlcmd @splat
}

$credSplat = @{
    TypeName = 'System.Management.Automation.PSCredential'
    ArgumentList = 'duffney',('P@ssw0rd' | ConvertTo-SecureString -AsPlainText -Force)
}
$Credential= New-Object @credSplat
ConvertTo-SecureString -AsPlainText -Force)

Get-AllSQLDatabases -SQLServer SQL01 -Credential $Credential
```

## <a name="continued-learning-credential-management"></a>Weitere Informationen zur Verwaltung von Anmeldeinformationen

Die sichere Erstellung und Speicherung von Objekten mit Anmeldeinformationen kann schwierig sein. Die folgenden Ressourcen können Ihnen bei der Verwaltung von PowerShell-Anmeldeinformationen helfen.

- [BetterCredentials][]
- [Azure Key Vault][]
- [Das Projekt Vault][]
- [Das Modul SecretManagement][]

<!-- link references -->
[Originalversion]: https://duffney.io/addcredentialstopowershellfunctions/
[@joshduffney]: https://twitter.com/joshduffney
[duffney.io]: https://duffney.io/posts/
[BetterCredentials]: https://www.powershellgallery.com/packages/BetterCredentials/
[Azure Key Vault]: https://azure.microsoft.com/services/key-vault/
[Das Projekt Vault]: https://www.vaultproject.io/
[Splatting Parameters Inside Advanced Functions]: http://duffney.io/Splatting-Parameters-Within-AdvancedFunctions
[Automating with Jenkins and PowerShell on Windows - Part 2]: https://hodgkins.io/automating-with-jenkins-and-powershell-on-windows-part-2
[PSCredential]: /dotnet/api/system.management.automation.pscredential
[The Pester Book]: https://leanpub.com/the-pester-book
[about_Splatting]: /powershell/module/microsoft.powershell.core/about/about_splatting
[Das Modul SecretManagement]: https://devblogs.microsoft.com/powershell/secretmanagement-and-secretstore-updates/
