---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 10/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-credential?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Credential
ms.openlocfilehash: 3716e5b8b88f4c07da06c28091d2c7f3202caa28
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2020
ms.locfileid: "93225188"
---
# Get-Credential

## ZUSAMMENFASSUNG
Ruft ein Anmeldeinformationsobjekt basierend auf einem Benutzernamen und Kennwort ab.

## SYNTAX

### "Kredentialset" (Standard)

```
Get-Credential [[-Credential] <PSCredential>] [<CommonParameters>]
```

### Messageset

```
Get-Credential [-Message <String>] [[-UserName] <String>] [-Title <String>] [<CommonParameters>]
```

## DESCRIPTION

Mit dem `Get-Credential` -Cmdlet wird ein Anmelde Informationsobjekt für einen angegebenen Benutzernamen und ein bestimmtes Kennwort erstellt. Sie können das Anmeldeinformationsobjekt für Sicherheitsvorgänge verwenden.

Das `Get-Credential` Cmdlet fordert den Benutzer auf, ein Kennwort oder einen Benutzernamen und ein Kennwort einzugeben. Sie können den **Message** -Parameter verwenden, um in der Eingabeaufforderung eine angepasste Meldung anzugeben.

## BEISPIELE

### Beispiel 1

```powershell
$c = Get-Credential
```

Dieser Befehl ruft ein Anmelde Informationsobjekt ab und speichert es in der `$c` Variablen.

Wenn Sie den Befehl eingeben, werden Sie aufgefordert, einen Benutzernamen und ein Kennwort einzugeben. Wenn Sie die angeforderten Informationen eingeben, erstellt das Cmdlet ein **PSCredential** -Objekt, das die Anmelde Informationen des Benutzers darstellt, und speichert es in der `$c` Variablen.

Sie können das Objekt als Eingabe für Cmdlets verwenden, die eine Benutzerauthentifizierung anfordern, z. b. solche mit einem **Credential** -Parameter. Einige Anbieter, die mit PowerShell installiert werden, unterstützen jedoch nicht den **Credential** -Parameter.

### Beispiel 2

```powershell
$c = Get-Credential
Get-CimInstance Win32_DiskDrive -ComputerName Server01 -Credential $c
```

Diese Befehle verwenden ein Anmelde Informationen-Objekt, das vom `Get-Credential` Cmdlet zurückgegeben wird, um einen Benutzer auf einem Remote Computer zu authentifizieren, sodass der Computer mit Windows-Verwaltungsinstrumentation (WMI) verwaltet werden kann.

Der erste Befehl ruft ein Anmelde Informationsobjekt ab und speichert es in der `$c` Variablen. Der zweite Befehl verwendet das Anmelde Informationen-Objekt in einem `Get-CimInstance` Befehl. Dieser Befehl ruft Informationen zu den Festplattenlaufwerken auf dem Computer „Server01“ ab.

### Beispiel 3

```powershell
Get-CimInstance Win32_BIOS -ComputerName Server01 -Credential (Get-Credential -Credential Domain01\User01)
```

Dieser Befehl zeigt, wie Sie einen `Get-Credential` Befehl in einen  `Get-CimInstance` Befehl einschließen.

Dieser Befehl verwendet das `Get-CimInstance` Cmdlet, um Informationen über das BIOS auf dem Server01-Computer zu erhalten. Er verwendet den **Credential** -Parameter, um den Benutzer, Domain01\User01 und einen `Get-Credential` Befehl als Wert des **Credential** -Parameters zu authentifizieren.

### Beispiel 4

```powershell
$c = Get-Credential -credential User01
$c.Username
User01
```

In diesem Beispiel werden die Anmeldeinformationen erstellt, die einen Benutzernamen ohne Domänennamen enthalten.

Mit dem ersten Befehl werden Anmelde Informationen mit dem Benutzernamen USER01 abgerufen und in der `$c` Variablen gespeichert.
Der zweite Befehl zeigt den Wert der **Username** -Eigenschaft des resultierenden Credential-Objekts an.

### Beispiel 5

```powershell
$Credential = $host.ui.PromptForCredential("Need credentials", "Please enter your user name and password.", "", "NetBiosUserName")
```

Dieser Befehl verwendet die **PromptForCredential** -Methode, um den Benutzer zu Eingabe des Benutzernamens und Kennworts aufzufordern. Der Befehl speichert die resultierenden Anmelde Informationen in der `$Credential` Variablen.

Die **promptforcredential** -Methode ist eine Alternative zur Verwendung des- `Get-Credential` Cmdlets. Wenn Sie **promptforcredential** verwenden, können Sie die Beschriftung, die Meldungen und den Benutzernamen angeben, die in der Eingabeaufforderung angezeigt werden.

Weitere Informationen finden Sie in der Dokumentation zu [promptforcredential](/dotnet/api/system.management.automation.host.pshostuserinterface.promptforcredential) im SDK.

### Beispiel 6

Dieses Beispiel zeigt, wie Sie ein Anmelde Informationsobjekt erstellen, das mit dem Objekt identisch ist, das `Get-Credential` zurückgibt, ohne den Benutzer aufzufordern. Für diese Methode ist nur ein Nur-Text-Kennwort erforderlich, was in manchen Unternehmen gegen die Sicherheitsstandards verstoßen könnte.

```powershell
$User = "Domain01\User01"
$PWord = ConvertTo-SecureString -String "P@sSwOrd" -AsPlainText -Force
$Credential = New-Object -TypeName System.Management.Automation.PSCredential -ArgumentList $User, $PWord
```

Der erste Befehl speichert den Namen des Benutzerkontos im- `$User` Parameter. Der Wert muss das Format „Domäne\Benutzer“ oder „Computername\Benutzer“ haben.

Der zweite Befehl verwendet das `ConvertTo-SecureString` Cmdlet, um eine sichere Zeichenfolge aus einem nur-Text-Kennwort zu erstellen. Der Befehl verwendet den **AsPlainText** -Parameter, um anzugeben, dass die Zeichenfolge Nur-Text ist, und den **Force** -Parameter, um zu bestätigen, dass Sie die Risiken beim Einsatz von Nur-Text verstanden haben.

Der dritte Befehl verwendet das `New-Object` Cmdlet, um ein **PSCredential** -Objekt aus den Werten in den `$User` Variablen und zu erstellen `$PWord` .

### Beispiel 7

```powershell
Get-Credential -Message "Credential are required for access to the \\Server1\Scripts file share." -User Server01\PowerUser
```

```Output
PowerShell Credential Request
Credential are required for access to the \\Server1\Scripts file share.
Password for user Server01\PowerUser:
```

Dieser Befehl verwendet die Parameter " **Message** " und " **username** " des `Get-Credential` Cmdlets. Dieses Befehlsformat wurde für gemeinsam genutzte Skripts und Funktionen entwickelt. In diesem Fall erfährt der Benutzer in der Meldung, warum Anmeldeinformationen erforderlich sind, und bietet ihm die Sicherheit, dass die Anforderung legitim ist.

### Beispiel 8

```powershell
Invoke-Command -ComputerName Server01 {Get-Credential Domain01\User02}
```

```Output
PowerShell Credential Request : PowerShell Credential Request
Warning: This credential is being requested by a script or application on the SERVER01 remote computer. Enter your credentials only if you
 trust the remote computer and the application or script requesting it.

Enter your credentials.
Password for user Domain01\User02: ***************

PSComputerName     : Server01
RunspaceId         : 422bdf52-9886-4ada-ab2f-130497c6777f
PSShowComputerName : True
UserName           : Domain01\User01
Password           : System.Security.SecureString
```

Dieser Befehl ruft die Anmeldeinformationen vom Remotecomputer „Server01“ ab. Der Befehl verwendet das `Invoke-Command` Cmdlet zum Ausführen eines `Get-Credential` Befehls auf dem Remote Computer. Die Ausgabe zeigt die Remote Sicherheitsnachricht, die `Get-Credential` in der Authentifizierungs Aufforderung enthält.

## PARAMETERS

### -Credential

Gibt einen Benutzernamen für die Anmelde Informationen an, z. b. **USER01** oder **Domain01\User01**. Der Parameter Name, `-Credential` , ist optional.

Wenn Sie den Befehl übermitteln und einen Benutzernamen angeben, werden Sie zur Eingabe eines Kennworts aufgefordert. Wenn Sie diesen Parameter weglassen, werden Sie aufgefordert, einen Benutzernamen und ein Kennwort einzugeben.

Wenn Sie in PowerShell 3,0 einen Benutzernamen ohne Domäne eingeben, wird von kein umgekehrter `Get-Credential` Schrägstrich mehr vor dem Namen eingefügt.

Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.

> [!NOTE]
> Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: CredentialSet
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Meldung

Gibt eine Meldung an, die in der Authentifizierungsaufforderung angezeigt wird. Dieser Parameter dient zur Verwendung in einer Funktion oder in einem Skript. Sie können die Meldung verwenden, um dem Benutzer zu erklären, warum Sie Anmeldeinformationen anfordern und wie sie verwendet werden.

Dieser Parameter wurde in PowerShell 3,0 eingeführt.

```yaml
Type: System.String
Parameter Sets: MessageSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Title

Legt den Text der Titelzeile für die Authentifizierungs Aufforderung in der-Konsole fest.

Dieser Parameter wurde in PowerShell 6,0 eingeführt.

```yaml
Type: System.String
Parameter Sets: MessageSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserName

Gibt einen Benutzernamen an. Die Authentifizierungsaufforderung fordert die Eingabe eines Kennworts für den Benutzernamen an. Standardmäßig ist der Benutzername leer, und die Authentifizierungsaufforderung fordert sowohl einen Benutzernamen als auch ein Kennwort an.

Dieser Parameter wurde in PowerShell 3,0 eingeführt.

```yaml
Type: System.String
Parameter Sets: MessageSet
Aliases:

Required: False
Position: 1
Default value: None (blank)
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine

Eingaben können nicht an dieses Cmdlet weitergereicht werden.

## AUSGABEN

### System. Management. Automation. PSCredential

`Get-Credential` Gibt ein Anmelde Informationen-Objekt zurück.

## HINWEISE

Sie können das **PSCredential** -Objekt verwenden, das `Get-Credential` in Cmdlets erstellt, die eine Benutzerauthentifizierung anfordern, z. b. solche mit einem **Credential** -Parameter.

Der **Credential** -Parameter wird nicht von allen Anbietern unterstützt, die mit PowerShell installiert werden.
Ab PowerShell 3,0 wird es für SELECT-Cmdlets unterstützt, wie z `Get-Content` . b. die-und- `New-PSDrive` Cmdlets.

## VERWANDTE LINKS

[PromptForCredential](/dotnet/api/system.management.automation.host.pshostuserinterface.promptforcredential)
