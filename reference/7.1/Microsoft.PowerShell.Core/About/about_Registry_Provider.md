---
description: Registrierung
keywords: powershell,cmdlet
Locale: en-US
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_registry_provider?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Registrierungsanbieter
ms.openlocfilehash: e97fc607c456909dc0abdb50cb7dd5b5847998a0
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223596"
---
# <a name="registry-provider"></a>Registrierungs Anbieter

## <a name="provider-name"></a>Anbietername

Registrierung

## <a name="drives"></a>Laufwerke

`HKLM:`, `HKCU:`

## <a name="capabilities"></a>Funktionen

Nicht **verarbeiten** , **usetransactions**

## <a name="short-description"></a>Kurze Beschreibung

Ermöglicht den Zugriff auf die Registrierungsschlüssel, Einträge und Werte in PowerShell.

## <a name="detailed-description"></a>Detaillierte Beschreibung

Mit dem PowerShell- **Registrierungs** Anbieter können Sie Registrierungsschlüssel, Einträge und Werte in PowerShell erhalten, hinzufügen, ändern, löschen und löschen.

Die **Registrierungs** Laufwerke sind ein hierarchischer Namespace, der die Registrierungsschlüssel und Unterschlüssel auf dem Computer enthält. Registrierungseinträge und Werte sind keine Komponenten dieser Hierarchie. Stattdessen sind sie Eigenschaften des jeweiligen Schlüssels.

Der **Registrierungs** Anbieter unterstützt die folgenden Cmdlets, die in diesem Artikel behandelt werden.

- [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location)
- [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location)
- [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item)
- [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)
- [Invoke-Item](xref:Microsoft.PowerShell.Management.Invoke-Item)
- [Move-Item](xref:Microsoft.PowerShell.Management.Move-Item)
- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)
- [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item)
- [Get-ItemProperty](xref:Microsoft.PowerShell.Management.Get-ItemProperty)
- [Set-ItemProperty](xref:Microsoft.PowerShell.Management.Set-ItemProperty)
- [Remove-ItemProperty](xref:Microsoft.PowerShell.Management.Remove-ItemProperty)
- [Clear-ItemProperty](xref:Microsoft.PowerShell.Management.Clear-ItemProperty)
- [Get-Acl](xref:Microsoft.PowerShell.Security.Get-Acl)
- [Set-Acl](xref:Microsoft.PowerShell.Security.Set-Acl)

## <a name="types-exposed-by-this-provider"></a>Von diesem Anbieter verfügbar gemachte Typen

Registrierungsschlüssel werden als Instanzen der [Microsoft. Win32. RegistryKey](/dotnet/api/microsoft.win32.registrykey) -Klasse dargestellt. Registrierungseinträge werden als Instanzen der Klasse [pscustomobject](/dotnet/api/system.management.automation.pscustomobject) dargestellt.

## <a name="navigating-the-registry-drives"></a>Navigieren in den Registrierungs Laufwerken

Der **Registrierungs** Anbieter stellt seinen Datenspeicher als zwei Standard Laufwerke zur Verfügung. Der Registrierungs Speicherort HKEY_LOCAL_MACHINE der dem Laufwerk zugeordnet ist `HKLM:` und dem Laufwerk HKEY_CURRENT_USER zugeordnet ist `HKCU:` . Wenn Sie mit der Registrierung arbeiten möchten, können Sie den Speicherort `HKLM:` mit dem folgenden Befehl auf das Laufwerk umstellen.

```powershell
Set-Location HKLM:
```

Um zu einem Dateisystemlaufwerk zurückzukehren, geben Sie den Namen des Laufwerks ein. Beispiel:

```powershell
Set-Location C:
```

Sie können auch mit dem **Registrierungs** Anbieter von einem beliebigen anderen PowerShell-Laufwerk aus arbeiten. Um auf einen Registrierungsschlüssel von einem anderen Speicherort zu verweisen, verwenden Sie den Laufwerk Namen ( `HKLM:` , `HKCU:` ) im Pfad. Verwenden Sie einen umgekehrten Schrägstrich ( \\ ) oder einen Schrägstrich (/), um eine Ebene des **Registrierungs** Laufwerks anzugeben.

```powershell
PS C:\> cd HKLM:\Software
```

> [!NOTE]
> PowerShell verwendet Aliase, um Ihnen eine vertraute Möglichkeit zum Arbeiten mit Anbieter Pfaden zu bieten. Befehle wie `dir` und `ls` sind jetzt Aliase für [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` ist ein Alias für [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location)und `pwd` ist ein Alias für [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).

Das letzte Beispiel zeigt eine weitere Pfad Syntax, die Sie verwenden können, um durch den **Registrierungs** Anbieter zu navigieren. Diese Syntax verwendet den Anbieter Namen, gefolgt von zwei Doppelpunkten `::` . Mit dieser Syntax können Sie anstelle des zugeordneten Laufwerks namens den vollständigen Hive-Namen verwenden `HKLM` .

```powershell
cd "Registry::HKEY_LOCAL_MACHINE\Software"
```

## <a name="displaying-the-contents-of-registry-keys"></a>Anzeigen des Inhalts von Registrierungs Schlüsseln

Die Registrierung ist in Schlüssel, Unterschlüssel und Einträge unterteilt. Weitere Informationen zur Registrierungs Struktur finden Sie unter [Struktur der Registrierung](/windows/desktop/sysinfo/structure-of-the-registry).

In einem **Registrierungs** Laufwerk ist jeder Schlüssel ein Container. Ein Schlüssel kann eine beliebige Anzahl von Schlüsseln enthalten. Ein Registrierungsschlüssel, der über einen übergeordneten Schlüssel verfügt, wird als Unterschlüssel bezeichnet. Sie können verwenden `Get-ChildItem` , um Registrierungsschlüssel anzuzeigen und `Set-Location` zu einem Schlüssel Pfad zu navigieren.

Registrierungs Werte sind Attribute eines Registrierungsschlüssels. Im **Registrierungs** Laufwerk werden Sie als **Element Eigenschaften** bezeichnet. Ein Registrierungsschlüssel kann sowohl untergeordnete Schlüssel als auch Element Eigenschaften haben.

In diesem Beispiel wird der Unterschied zwischen `Get-Item` und `Get-ChildItem` angezeigt. Wenn Sie `Get-Item` den "Spooler"-Registrierungsschlüssel verwenden, können Sie dessen Eigenschaften anzeigen.

```
PS C:\ > Get-Item -Path HKLM:\SYSTEM\CurrentControlSet\Services\Spooler


    Hive: HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services


Name        Property
----        --------
Spooler     DependOnService    : {RPCSS, http}
            Description        : @%systemroot%\system32\spoolsv.exe,-2
            DisplayName        : @%systemroot%\system32\spoolsv.exe,-1
            ErrorControl       : 1
            FailureActions     : {16, 14, 0, 0...}
            Group              : SpoolerGroup
            ImagePath          : C:\WINDOWS\System32\spoolsv.exe
            ObjectName         : LocalSystem
            RequiredPrivileges : {SeTcbPrivilege, SeImpersonatePrivilege, ...
            ServiceSidType     : 1
            Start              : 2
            Type               : 27
```

Jeder Registrierungsschlüssel kann auch Unterschlüssel enthalten. Wenn Sie `Get-Item` für einen Registrierungsschlüssel verwenden, werden die Unterschlüssel nicht angezeigt. `Get-ChildItem`Mit dem-Cmdlet werden die untergeordneten Elemente der "Spooler"-Taste angezeigt, einschließlich der Eigenschaften des unter Schlüssels. Die Eigenschaften der übergeordneten Schlüssel werden bei Verwendung von nicht angezeigt `Get-ChildItem` .

```
PS C:\> Get-ChildItem -Path HKLM:\SYSTEM\CurrentControlSet\Services\Spooler


    Hive: HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\Spooler


Name             Property
----             --------
Performance      Close           : PerfClose
                 Collect         : PerfCollect
                 Collect Timeout : 2000
                 Library         : C:\Windows\System32\winspool.drv
                 Object List     : 1450
                 Open            : PerfOpen
                 Open Timeout    : 4000
Security         Security : {1, 0, 20, 128...}
```

Das- `Get-Item` Cmdlet kann auch am aktuellen Speicherort verwendet werden. Im folgenden Beispiel wird zum "Spooler"-Registrierungsschlüssel navigiert, und die Element Eigenschaften werden abgerufen.
Der Punkt `.` wird verwendet, um den aktuellen Speicherort anzugeben.

```
PS C:\> cd HKLM:\System\CurrentControlSet\Services\Spooler
PS HKLM:\SYSTEM\CurrentControlSet\Services\Spooler> Get-Item .

    Hive: HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services

Name             Property
----             --------
Spooler          DependOnService    : {RPCSS, http}
                 Description        : @%systemroot%\system32\spoolsv.exe,-2
...
```

Weitere Informationen zu den in diesem Abschnitt behandelten Cmdlets finden Sie in den folgenden Artikeln.

-[Get-Item](xref:Microsoft.PowerShell.Management.Get-Item) 
- [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)

## <a name="viewing-registry-key-values"></a>Anzeigen von Registrierungsschlüssel Werten

Registrierungsschlüssel Werte werden als Eigenschaften der einzelnen Registrierungsschlüssel gespeichert. Das `Get-ItemProperty` Cmdlet zeigt die Registrierungsschlüssel Eigenschaften mit dem von Ihnen angegebenen Namen an. Das Ergebnis ist ein **pscustomobject** mit den von Ihnen angegebenen Eigenschaften.

Im folgenden Beispiel wird das- `Get-ItemProperty` Cmdlet verwendet, um alle Eigenschaften anzuzeigen. Wenn Sie das resultierende Objekt in einer Variablen speichern, können Sie auf den gewünschten Eigenschafts Wert zugreifen.

```powershell
$p = Get-ItemProperty -Path HKLM:\SYSTEM\CurrentControlSet\Services\Spooler
$p.DependOnService
```

```output
RPCSS
http
```

Wenn Sie einen Wert für den Parameter angeben, werden `-Name` die von Ihnen angegebenen Eigenschaften ausgewählt und das **pscustomobject-Objekt** zurückgegeben.  Das folgende Beispiel zeigt den Unterschied in der Ausgabe, wenn Sie den- `-Name` Parameter verwenden.

```
PS C:\> Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Wbem

BUILD                      : 17134.1
Installation Directory     : C:\WINDOWS\system32\WBEM
MOF Self-Install Directory : C:\WINDOWS\system32\WBEM\MOF
PSPath                     : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Wbem
PSParentPath               : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft
PSChildName                : Wbem
PSDrive                    : HKLM
PSProvider                 : Microsoft.PowerShell.Core\Registry

PS C:\> Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Wbem -Name BUILD

BUILD        : 17134.1
PSPath       : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Wbem
PSParentPath : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft
PSChildName  : Wbem
PSDrive      : HKLM
PSProvider   : Microsoft.PowerShell.Core\Registry
```

Ab PowerShell 5,0 `Get-ItemPropertyValue` gibt das Cmdlet nur den Wert der angegebenen Eigenschaft zurück.

```powershell
Get-ItemPropertyValue -Path HKLM:\SOFTWARE\Microsoft\Wbem -Name BUILD
```

```output
17134.1
```

Weitere Informationen zu den in diesem Abschnitt verwendeten Cmdlets finden Sie in den folgenden Artikeln.

- [Get-ItemProperty](xref:Microsoft.PowerShell.Management.Get-ItemProperty)
- [Get-ItemPropertyValue](xref:Microsoft.PowerShell.Management.Get-ItemProperty)

## <a name="changing-registry-key-values"></a>Ändern von Registrierungsschlüssel Werten

Mit dem- `Set-ItemProperty` Cmdlet werden die Attribute für Registrierungsschlüssel festgelegt. Im folgenden Beispiel wird verwendet `Set-ItemProperty` , um den Starttyp des Spoolerdiensts in manuell zu ändern. Im Beispiel wird der **StartType** mithilfe des Cmdlets wieder in " *automatisch* " geändert `Set-Service` .

```
PS C:\> Get-Service spooler | Select-Object Name, StartMode

Name    StartType
----    ---------
spooler Automatic

PS C:\> $path = "HKLM:\SYSTEM\CurrentControlSet\Services\Spooler\"
PS C:\> Set-ItemProperty -Path $path -Name Start -Value 3
PS C:\> Get-Service spooler | Select-Object Name, StartMode

Name    StartType
----    ---------
spooler    Manual

PS C:\> Set-Service -Name Spooler -StartupType Automatic
```

Jeder Registrierungsschlüssel hat einen *Standard* Wert. Sie können den *Standard* Wert für einen Registrierungsschlüssel entweder mit `Set-Item` oder ändern `Set-ItemProperty` .

```powershell
Set-ItemProperty -Path HKLM:\SOFTWARE\Contoso -Name "(default)" -Value "one"
Set-Item -Path HKLM:\SOFTWARE\Contoso -Value "two"
```

Weitere Informationen zu den in diesem Abschnitt verwendeten Cmdlets finden Sie in den folgenden Artikeln.

- [Set-Item](xref:Microsoft.PowerShell.Management.Set-Item)
- [Set-ItemProperty](xref:Microsoft.PowerShell.Management.Set-ItemProperty)

## <a name="creating-registry-keys-and-values"></a>Erstellen von Registrierungs Schlüsseln und-Werten

Mit dem- `New-Item` Cmdlet werden Registrierungsschlüssel mit einem von Ihnen bereitgestellten Namen erstellt.
Sie können auch die- `mkdir` Funktion verwenden, die das `New-Item` Cmdlet intern aufruft.

```
PS HKLM:\SOFTWARE\> mkdir ContosoCompany

    Hive: HKEY_LOCAL_MACHINE\SOFTWARE

Name                           Property
----                           --------
ContosoCompany
```

Sie können das `New-ItemProperty` Cmdlet verwenden, um Werte in einem von Ihnen angegebenen Registrierungsschlüssel zu erstellen. Im folgenden Beispiel wird ein neuer DWORD-Wert im Registrierungsschlüssel "contosocompany" erstellt.

```powershell
$path = "HKLM:\SOFTWARE\ContosoCompany"
New-ItemProperty -Path  -Name Test -Type DWORD -Value 1
```

> [!NOTE]
> Weitere zulässige Typwerte finden Sie im Abschnitt "dynamische Parameter" in diesem Artikel.

Ausführliche Informationen zur Verwendung von Cmdlets finden Sie unter [New-ItemProperty](xref:Microsoft.PowerShell.Management.New-ItemProperty).

## <a name="copying-registry-keys-and-values"></a>Kopieren von Registrierungs Schlüsseln und-Werten

Verwenden Sie **Registry** das `Copy-Item` Cmdlet zum Kopieren von Registrierungs Schlüsseln und-Werten im Registrierungs Anbieter. Verwenden Sie das- `Copy-ItemProperty` Cmdlet, um nur Registrierungs Werte zu kopieren.
Mit dem folgenden Befehl werden der Registrierungsschlüssel "%% amp; quot;" und seine Eigenschaften an den angegebenen Speicherort "HKLM: \ software\fabrikam" kopiert.

`Copy-Item` erstellt den Ziel Schlüssel, wenn er nicht vorhanden ist. Wenn der Ziel Schlüssel vorhanden ist, wird von `Copy-Item` ein Duplikat des Quell Schlüssels als untergeordnetes Element (Unterschlüssel) des Ziel Schlüssels erstellt.

```powershell
Copy-Item -Path  HKLM:\Software\Contoso -Destination HKLM:\Software\Fabrikam
```

Der folgende Befehl verwendet das `Copy-ItemProperty` Cmdlet, um den Wert "Server" aus dem Schlüssel "" in den Schlüssel "Fabrikam" zu kopieren.

```powershell
$source = "HKLM:\SOFTWARE\Contoso"
$dest = "HKLM:\SOFTWARE\Fabrikam"
Copy-ItemProperty -Path $source -Destination $dest -Name Server
```

Weitere Informationen zu den in diesem Abschnitt verwendeten Cmdlets finden Sie in den folgenden Artikeln.

- [Copy-Item](xref:Microsoft.PowerShell.Management.Copy-Item)
- [Copy-ItemProperty](xref:Microsoft.PowerShell.Management.Copy-ItemProperty)

## <a name="moving-registry-keys-and-values"></a>Verschieben von Registrierungs Schlüsseln und-Werten

Die `Move-Item` `Move-ItemProperty` Cmdlets und Verhalten sich wie Ihre "Copy"-Entsprechungen. Wenn das Ziel vorhanden ist, `Move-Item` Verschiebt den Quell Schlüssel unterhalb des Ziel Schlüssels. Wenn der Ziel Schlüssel nicht vorhanden ist, wird der Quell Schlüssel in den Zielpfad verschoben.

Mit dem folgenden Befehl wird der Schlüssel "fitoso" in den Pfad "HKLM: \ software\fabrikam" verschoben.

```powershell
Move-Item -Path HKLM:\SOFTWARE\Contoso -Destination HKLM:\SOFTWARE\Fabrikam
```

Mit diesem Befehl werden alle Eigenschaften von "HKLM: \ software\contosocompany" nach "HKLM: \ software\fabrikam" verschoben.

```powershell
$source = "HKLM:\SOFTWARE\Contoso"
$dest = "HKLM:\SOFTWARE\Fabrikam"
Move-ItemProperty -Path $source -Destination $dest -Name *
```

Weitere Informationen zu den in diesem Abschnitt verwendeten Cmdlets finden Sie in den folgenden Artikeln.

- [Move-Item](xref:Microsoft.PowerShell.Management.Move-Item)
- [Move-ItemProperty](xref:Microsoft.PowerShell.Management.Move-ItemProperty)

## <a name="renaming-registry-keys-and-values"></a>Umbenennen von Registrierungs Schlüsseln und-Werten

Sie können Registrierungsschlüssel und-Werte genau wie Dateien und Ordner umbenennen.
`Rename-Item` benennt Registrierungsschlüssel um und benennt `Rename-ItemProperty` Registrierungs Werte um.

```powershell
$path = "HKLM:\SOFTWARE\Contoso"
Rename-ItemProperty -Path $path -Name ContosoTest -NewName FabrikamTest
Rename-Item -Path $path -NewName Fabrikam
```

## <a name="changing-security-descriptors"></a>Ändern von Sicherheits Deskriptoren

Sie können den Zugriff auf Registrierungsschlüssel mithilfe der `Get-Acl` `Set-Acl` Cmdlets und einschränken. Im folgenden Beispiel wird ein neuer Benutzer mit Vollzugriff dem Registrierungsschlüssel "HKLM: \ software\configuration Manager" hinzugefügt.

```powershell
$acl = Get-Acl -Path HKLM:\SOFTWARE\Contoso
$rule = New-Object System.Security.AccessControl.RegistryAccessRule `
("CONTOSO\jsmith", "FullControl", "Allow")
$acl.SetAccessRule($rule)
$acl | Set-Acl -Path HKLM:\SOFTWARE\Contoso
```

Weitere Beispiele und Informationen zur Verwendung von Cmdlets finden Sie in den folgenden Artikeln.

- [Get-Acl](xref:Microsoft.PowerShell.Security.Get-Acl)
- [Set-Acl](xref:Microsoft.PowerShell.Security.Set-Acl)

## <a name="removing-and-clearing-registry-keys-and-values"></a>Entfernen und Löschen von Registrierungs Schlüsseln und-Werten

Mit **Remove-Item** können Sie enthaltene Elemente entfernen. Sie werden jedoch aufgefordert, das Entfernen zu bestätigen, wenn das Element etwas anderes enthält. Im folgenden Beispiel wird versucht, den Schlüssel "HKLM: \ software\configuration Manager" zu löschen.

```
PS C:\> dir HKLM:\SOFTWARE\Contoso\

    Hive: HKEY_LOCAL_MACHINE\SOFTWARE\Contoso

Name                           Property
----                           --------
ChildKey

PS C:\> Remove-Item -Path HKLM:\SOFTWARE\Contoso

Confirm
The item at HKLM:\SOFTWARE\Contoso has children and the -Recurse
parameter was not specified. If you continue, all children will be removed
with the item. Are you sure you want to continue?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help
(default is "Y"):
```

Wenn Sie enthaltene Elemente ohne Aufforderung löschen möchten, geben Sie den- `-Recurse` Parameter an.

```powershell
Remove-Item -Path HKLM:\SOFTWARE\Contoso -Recurse
```

Wenn Sie alle Elemente in "HKLM: \ software\configuration Manager", aber nicht "HKLM: \ software\c" selbst entfernen möchten, verwenden Sie einen nachfolgenden umgekehrten Schrägstrich, `\` gefolgt von einem Platzhalter.

```powershell
Remove-Item -Path HKLM:\SOFTWARE\Contoso\* -Recurse
```

Mit diesem Befehl wird der Registrierungs Wert "ContosoTest" aus dem Registrierungsschlüssel "HKLM: \ software\contoso" gelöscht.

```powershell
Remove-ItemProperty -Path HKLM:\SOFTWARE\Contoso -Name ContosoTest
```

`Clear-Item` Löscht alle Registrierungs Werte für einen Schlüssel. Im folgenden Beispiel werden alle Werte aus dem Registrierungsschlüssel "HKLM: \ software\c" gelöscht. Verwenden Sie, um nur eine bestimmte Eigenschaft zu löschen `Clear-ItemProperty` .

```
PS HKLM:\SOFTWARE\> Get-Item .\Contoso\

    Hive: HKEY_LOCAL_MACHINE\SOFTWARE

Name           Property
----           --------
Contoso        Server     : {a, b, c}
               HereString : {This is text which contains
               newlines. It also contains "quoted" strings}
               (default)  : 1

PS HKLM:\SOFTWARE\> Clear-Item .\Contoso\
PS HKLM:\SOFTWARE\> Get-Item .\Contoso\

    Hive: HKEY_LOCAL_MACHINE\SOFTWARE

Name                           Property
----                           --------
Contoso
```

Weitere Beispiele und Informationen zur Verwendung von Cmdlets finden Sie in den folgenden Artikeln.

- [Clear-Item](xref:Microsoft.PowerShell.Management.Clear-Item)
- [Clear-ItemProperty](xref:Microsoft.PowerShell.Management.Clear-ItemProperty)
- [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item)
- [Remove-ItemProperty](xref:Microsoft.PowerShell.Management.Remove-ItemProperty)

## <a name="dynamic-parameters"></a>Dynamische Parameter

Dynamische Parameter sind Cmdlet-Parameter, die von einem PowerShell-Anbieter hinzugefügt werden und nur verfügbar sind, wenn das Cmdlet im Anbieter fähigen Laufwerk verwendet wird.

### <a name="type-microsoftwin32registryvaluekind"></a>Geben Sie <Microsoft. Win32. RegistryValueKind ein>

Erstellt oder ändert den Datentyp eines Registrierungswerts. Der Standardwert ist `String` (REG_SZ).

Dieser Parameter funktioniert wie vorgesehen im Cmdlet [Set-ItemProperty](xref:Microsoft.PowerShell.Management.Set-ItemProperty). Es steht auch im Cmdlet [Set-Item](xref:Microsoft.PowerShell.Management.Set-Item) in den Registrierungslaufwerken zur Verfügung, aber er hat keine Auswirkungen.

|Wert | BESCHREIBUNG |
| ---- | ----------- |
| `String` | Gibt eine Null-terminierte Zeichenfolge an. Entspricht REG_SZ. |
| `ExpandString` | Gibt eine auf NULL endenden Zeichenfolge an, die nicht erweitert ist. |
|                | Verweise auf Umgebungsvariablen, die erweitert werden, wenn |
|                | der Wert wird abgerufen. Entspricht REG_EXPAND_SZ. |
| `Binary` | Gibt Binärdaten in irgendeiner Form an. Entspricht REG_BINARY. |
| `DWord` | Gibt eine 32-Bit-Binärzahl an. Entspricht REG_DWORD. |
| `MultiString` | Gibt ein Array von null-terminierten Zeichen folgen an, die von |
|               | zwei NULL-Zeichen. Entspricht REG_MULTI_SZ. |
| `QWord` | Gibt eine 64-Bit-Binärzahl an. Entspricht REG_QWORD. |
| `Unknown` | Gibt einen nicht unterstützten Registrierungs Datentyp an, z. b. |
|           | REG_RESOURCE_LIST. |

#### <a name="cmdlets-supported"></a>Unterstützte Cmdlets

- [Set-Item](xref:Microsoft.PowerShell.Management.Set-Item)
- [Set-ItemProperty](xref:Microsoft.PowerShell.Management.Set-ItemProperty)

## <a name="using-the-pipeline"></a>Verwenden der Pipeline

Anbieter-Cmdlets akzeptieren Pipeline Eingaben. Sie können die Pipeline verwenden, um die Aufgabe zu vereinfachen, indem Sie Anbieter Daten von einem Cmdlet an ein anderes Anbieter-Cmdlet senden. Weitere Informationen zur Verwendung der Pipeline mit Anbieter-Cmdlets finden Sie in den Cmdlet-Referenzen in diesem Artikel.

## <a name="getting-help"></a>Hilfe

Ab Windows PowerShell 3.0 können Sie benutzerdefinierte Hilfethemen für Anbieter-Cmdlets abrufen, die erläutern, wie sich diese Cmdlets in einem Dateisystemlaufwerk verhalten.

Zum Aufrufen der Hilfe Themen, die für das Dateisystem Laufwerk angepasst sind, führen Sie einen `Get-Help` Befehl in einem Dateisystem Laufwerk aus, oder verwenden Sie den **path** -Parameter, um ein Dateisystem Laufwerk anzugeben.

```powershell
Get-Help Get-ChildItem
```

```powershell
Get-Help Get-ChildItem -Path HKLM:
```

## <a name="see-also"></a>Weitere Informationen:

 [about_Providers](../About/about_Providers.md)

