---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/import-module?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-Module
ms.openlocfilehash: efb82cb938f7b044b863a8192f4c66673d47a4e0
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93211279"
---
# Import-Module

## ZUSAMMENFASSUNG
Fügt der aktuellen Sitzung Module hinzu.

## SYNTAX

### Name (Standard)

```
Import-Module [-Global] [-Prefix <String>] [-Name] <String[]> [-Function <String[]>]
 [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force] [-SkipEditionCheck]
 [-PassThru] [-AsCustomObject] [-MinimumVersion <Version>] [-MaximumVersion <String>]
 [-RequiredVersion <Version>] [-ArgumentList <Object[]>] [-DisableNameChecking] [-NoClobber]
 [-Scope <String>]  [<CommonParameters>]
```

### PSSession

```
Import-Module [-Global] [-Prefix <String>] [-Name] <String[]> [-Function <String[]>]
 [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force] [-SkipEditionCheck]
 [-PassThru] [-AsCustomObject] [-MinimumVersion <Version>] [-MaximumVersion <String>]
 [-RequiredVersion <Version>] [-ArgumentList <Object[]>] [-DisableNameChecking] [-NoClobber]
 [-Scope <String>] -PSSession <PSSession>  [<CommonParameters>]
```

### CimSession

```
Import-Module [-Global] [-Prefix <String>] [-Name] <String[]> [-Function <String[]>]
 [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force] [-SkipEditionCheck]
 [-PassThru] [-AsCustomObject] [-MinimumVersion <Version>] [-MaximumVersion <String>]
 [-RequiredVersion <Version>] [-ArgumentList <Object[]>] [-DisableNameChecking] [-NoClobber]
 [-Scope <String>] -CimSession <CimSession> [-CimResourceUri <Uri>] [-CimNamespace <String>]
 [<CommonParameters>]
```

### Usewindowspowershell

```
Import-Module [-Name] <string[]> -UseWindowsPowerShell [-Global] [-Prefix <string>]
 [-Function <string[]>] [-Cmdlet <string[]>] [-Variable <string[]>] [-Alias <string[]>]
 [-Force] [-PassThru] [-AsCustomObject] [-MinimumVersion <version>] [-MaximumVersion <string>]
 [-RequiredVersion <version>] [-ArgumentList <Object[]>] [-DisableNameChecking] [-NoClobber]
 [-Scope <string>] [<CommonParameters>]
```

### FullyQualifiedName

```
Import-Module [-Global] [-Prefix <String>] [-FullyQualifiedName] <ModuleSpecification[]>
 [-Function <String[]>] [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force]
 [-SkipEditionCheck] [-PassThru] [-AsCustomObject] [-ArgumentList <Object[]>] [-DisableNameChecking]
 [-NoClobber] [-Scope <String>]  [<CommonParameters>]
```

### Fullyqualifiednameandpssession

```
Import-Module [-Global] [-Prefix <String>] [-FullyQualifiedName] <ModuleSpecification[]>
 [-Function <String[]>] [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force]
 [-SkipEditionCheck] [-PassThru] [-AsCustomObject] [-ArgumentList <Object[]>] [-DisableNameChecking]
 [-NoClobber] [-Scope <String>] -PSSession <PSSession>  [<CommonParameters>]
```

### Fullyqualifiednameanduabwindowspowershell

```
Import-Module [-FullyQualifiedName] <ModuleSpecification[]> -UseWindowsPowerShell [-Global]
 [-Prefix <string>] [-Function <string[]>] [-Cmdlet <string[]>] [-Variable <string[]>]
 [-Alias <string[]>] [-Force] [-PassThru] [-AsCustomObject] [-ArgumentList <Object[]>]
 [-DisableNameChecking] [-NoClobber] [-Scope <string>] [<CommonParameters>]
```

### Assembly

```
Import-Module [-Global] [-Prefix <String>] [-Assembly] <Assembly[]> [-Function <String[]>]
 [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force] [-SkipEditionCheck]
 [-PassThru] [-AsCustomObject] [-ArgumentList <Object[]>] [-DisableNameChecking] [-NoClobber]
 [-Scope <String>]  [<CommonParameters>]
```

### ModuleInfo

```
Import-Module [-Global] [-Prefix <String>] [-Function <String[]>] [-Cmdlet <String[]>]
 [-Variable <String[]>] [-Alias <String[]>] [-Force] [-SkipEditionCheck] [-PassThru]
 [-AsCustomObject] [-ModuleInfo] <PSModuleInfo[]> [-ArgumentList <Object[]>] [-DisableNameChecking]
 [-NoClobber] [-Scope <String>]  [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Import-Module` Cmdlet werden der aktuellen Sitzung ein oder mehrere Module hinzugefügt. Ab PowerShell 3,0 werden installierte Module automatisch in die Sitzung importiert, wenn Sie Befehle oder Anbieter im Modul verwenden. Sie können jedoch weiterhin den-Befehl verwenden, `Import-Module` um ein Modul zu importieren.
Sie können das automatische Importieren von Modulen mithilfe der `$PSModuleAutoloadingPreference` Preference-Variablen deaktivieren. Weitere Informationen zur- `$PSModuleAutoloadingPreference` Variablen finden Sie unter [about_Preference_Variables](About/about_Preference_Variables.md).

Ein Modul ist ein Paket, das Elemente enthält, die in PowerShell verwendet werden können. Zu den Membern gehören Cmdlets, Anbieter, Skripts, Funktionen, Variablen und andere Tools und Dateien. Nachdem ein Modul importiert wurde, können Sie die Modulelemente in der Sitzung verwenden. Weitere Informationen zu Modulen finden Sie unter [about_Modules](About/about_Modules.md).

Standardmäßig importiert alle Member, die `Import-Module` das Modul exportiert, aber Sie können die Parameter **Alias** , **Function** , **Cmdlet** und **Variable** verwenden, um einzuschränken, welche Member importiert werden. Der **noClobber** -Parameter verhindert `Import-Module` , dass Elemente importiert werden, die denselben Namen wie die Member in der aktuellen Sitzung haben.

`Import-Module` importiert ein Modul nur in die aktuelle Sitzung. Um das Modul in jede neue Sitzung zu importieren, fügen Sie `Import-Module` Ihrem PowerShell-Profil einen Befehl hinzu. Weitere Informationen zu Profilen finden Sie unter [about_Profiles](About/about_Profiles.md).

Sie können Windows-Remote Computer verwalten, auf denen PowerShell-Remoting aktiviert ist, indem Sie eine **PSSession** auf dem Remote Computer erstellen. Verwenden Sie dann den **PSSession** -Parameter von `Import-Module` , um die Module zu importieren, die auf dem Remote Computer installiert sind. Sie können jetzt die importierten Befehle in der aktuellen Sitzung verwenden. Die Befehle werden implizit auf dem Remote Computer ausgeführt.

Ab Windows PowerShell 3,0 können Sie verwenden, `Import-Module` um Common Information Model (CIM)-Module zu importieren, in denen die Cmdlets in Cmdlet-Definitions-XML-Dateien (cdxml) definiert sind. Diese Funktion ermöglicht es Ihnen, Cmdlets zu verwenden, die in Assemblys mit nicht verwaltetem Code implementiert werden, z. B. in mit C++ geschriebenen Assemblys.

Bei Remote Computern, auf denen PowerShell-Remoting nicht aktiviert ist, einschließlich Computern, auf denen das Windows-Betriebssystem nicht ausgeführt wird, können Sie den **cimsession** -Parameter von verwenden, `Import-Module` um CIM-Module vom Remote Computer zu importieren. Die importierten Befehle werden implizit auf dem Remote Computer ausgeführt. Eine **cimsession** ist eine Verbindung mit Windows-Verwaltungsinstrumentation (WMI) auf dem Remote Computer.

## BEISPIELE

### Beispiel 1: Importieren der Member eines Moduls in die aktuelle Sitzung

In diesem Beispiel werden die Member des **psdiagnostics** -Moduls in die aktuelle Sitzung importiert.

```powershell
Import-Module -Name PSDiagnostics
```

### Beispiel 2: Importieren aller vom Modulpfad angegebenen Module

In diesem Beispiel werden alle verfügbaren Module in dem von der `$env:PSModulePath` Umgebungsvariablen angegebenen Pfad in die aktuelle Sitzung importiert.

```powershell
Get-Module -ListAvailable | Import-Module
```

### Beispiel 3: Importieren der Mitglieder mehrerer Module in die aktuelle Sitzung

In diesem Beispiel werden die Member der **psdiagnostics** - **und** der-instanzmodule in die aktuelle Sitzung importiert.

```powershell
$m = Get-Module -ListAvailable PSDiagnostics, Dism
Import-Module -ModuleInfo $m
```

Das `Get-Module` **-** Cmdlet ruft die **psdiagnostics** -und die-initiatormodule ab und speichert die Objekte in der `$m` Variablen. Der **listavailable** -Parameter ist erforderlich, wenn Sie Module erhalten, die noch nicht in die Sitzung importiert wurden.

Der **ModuleInfo** -Parameter von `Import-Module` wird verwendet, um die Module in die aktuelle Sitzung zu importieren.

### Beispiel 4: Importieren aller durch einen Pfad angegebenen Module

Dieses Beispiel verwendet einen expliziten Pfad zum Identifizieren des zu importierenden Moduls.

```powershell
Import-Module -Name c:\ps-test\modules\test -Verbose
```

```Output
VERBOSE: Loading module from path 'C:\ps-test\modules\Test\Test.psm1'.
VERBOSE: Exporting function 'my-parm'.
VERBOSE: Exporting function 'Get-Parameter'.
VERBOSE: Exporting function 'Get-Specification'.
VERBOSE: Exporting function 'Get-SpecDetails'.
```

Wenn der **verbose** -Parameter verwendet wird `Import-Module` , meldet der Fortschritt beim Laden des Moduls.
Ohne den **verbose** -, **passthru** -oder **ascustomobject** -Parameter `Import-Module` generiert keine Ausgabe, wenn ein Modul importiert wird.

### Beispiel 5: Einschränken von in eine Sitzung importierten Modulmembern

Dieses Beispiel zeigt, wie Sie einschränken, welche Modulmember in die Sitzung importiert werden und welche Auswirkungen dieser Befehl auf die Sitzung hat. Der **Funktions** Parameter schränkt die Member ein, die aus dem Modul importiert werden. Sie können auch die Parameter **Alias** , **Variable** und **Cmdlet** verwenden, um andere Member einzuschränken, die von einem Modul importiert werden.

Mit dem- `Get-Module` Cmdlet wird das-Objekt abgerufen, das das **psdiagnostics** -Modul darstellt. Mit der **exportedcmdlets** -Eigenschaft werden alle Cmdlets aufgelistet, die vom Modul exportiert werden, auch wenn Sie nicht alle importiert wurden.

```powershell
Import-Module PSDiagnostics -Function Disable-PSTrace, Enable-PSTrace
(Get-Module PSDiagnostics).ExportedCommands
```

```Output
Key                          Value
---                          -----
Disable-PSTrace              Disable-PSTrace
Disable-PSWSManCombinedTrace Disable-PSWSManCombinedTrace
Disable-WSManTrace           Disable-WSManTrace
Enable-PSTrace               Enable-PSTrace
Enable-PSWSManCombinedTrace  Enable-PSWSManCombinedTrace
Enable-WSManTrace            Enable-WSManTrace
Get-LogProperties            Get-LogProperties
Set-LogProperties            Set-LogProperties
Start-Trace                  Start-Trace
Stop-Trace                   Stop-Trace
```

```powershell
Get-Command -Module PSDiagnostics
```

```Output
CommandType     Name                 Version    Source
-----------     ----                 -------    ------
Function        Disable-PSTrace      6.1.0.0    PSDiagnostics
Function        Enable-PSTrace       6.1.0.0    PSDiagnostics
```

Mit dem **Module** -Parameter des `Get-Command` Cmdlets werden die Befehle angezeigt, die aus dem **psdiagnostics** -Modul importiert wurden. Die Ergebnisse bestätigen, dass nur `Disable-PSTrace` die `Enable-PSTrace` Cmdlets und importiert wurden.

### Beispiel 6: Importieren der Member eines Moduls und Hinzufügen eines Präfixes

In diesem Beispiel wird das **psdiagnostics** -Modul in die aktuelle Sitzung importiert, ein Präfix zu den Elementnamen hinzugefügt und dann die Namen des vorangestellten Elements angezeigt. Der **prefix** -Parameter von `Import-Module` fügt allen Membern, die aus dem Modul importiert werden, das **x** -Präfix hinzu. Das Präfix gilt nur für die Elemente in der aktuellen Sitzung. Es ändert nicht das Modul. Der **passthru** -Parameter gibt ein Modul Objekt zurück, das das importierte Modul darstellt.

```powershell
Import-Module PSDiagnostics -Prefix x -PassThru
```

```Output
ModuleType Version    Name               ExportedCommands
---------- -------    ----               ----------------
Script     6.1.0.0    PSDiagnostics      {Disable-xPSTrace, Disable-xPSWSManCombinedTrace, Disable-xW...
```

```powershell
Get-Command -Module PSDiagnostics
```

```Output
CommandType     Name                                   Version    Source
-----------     ----                                   -------    ------
Function        Disable-xPSTrace                       6.1.0.0    PSDiagnostics
Function        Disable-xPSWSManCombinedTrace          6.1.0.0    PSDiagnostics
Function        Disable-xWSManTrace                    6.1.0.0    PSDiagnostics
Function        Enable-xPSTrace                        6.1.0.0    PSDiagnostics
Function        Enable-xPSWSManCombinedTrace           6.1.0.0    PSDiagnostics
Function        Enable-xWSManTrace                     6.1.0.0    PSDiagnostics
Function        Get-xLogProperties                     6.1.0.0    PSDiagnostics
Function        Set-xLogProperties                     6.1.0.0    PSDiagnostics
Function        Start-xTrace                           6.1.0.0    PSDiagnostics
Function        Stop-xTrace                            6.1.0.0    PSDiagnostics
```

`Get-Command` Ruft die Member ab, die aus dem Modul importiert wurden. Die Ausgabe zeigt, dass die Modulelemente ordnungsgemäß mit dem Präfix versehen wurden.

### Beispiel 7: erhalten und Verwenden eines benutzerdefinierten Objekts

Dieses Beispiel zeigt, wie Sie das benutzerdefinierte Objekt, das von **Import-Module** zurückgegeben wird, erhalten und verwenden.

Benutzerdefinierte Objekte beinhalten synthetische Elemente, die jedes der importierten Modulelemente darstellen. Beispielsweise werden die Cmdlets und Funktionen in einem Modul in Skriptmethoden des benutzerdefinierten Objekts konvertiert.

Benutzerdefinierte Objekte sind bei der Skripterstellung nützlich. Sie sind außerdem nützlich, wenn mehrere importierte Objekte die gleichen Namen haben. Die Skriptmethode eines Objekts entspricht der Angabe des vollqualifizierten Namens eines importierten Elements, darunter der Modulname.

Der **ascustomobject** -Parameter kann nur beim Importieren eines Skript Moduls verwendet werden. Verwenden `Get-Module` Sie, um zu bestimmen, welches der verfügbaren Module ein Skript Modul ist.

```powershell
Get-Module -List | Format-Table -Property Name, ModuleType -AutoSize
```

```Output
Name          ModuleType
----          ----------
Show-Calendar     Script
BitsTransfer    Manifest
PSDiagnostics   Manifest
TestCmdlets       Script
...
```

```powershell
$a = Import-Module -Name Show-Calendar -AsCustomObject -Passthru
$a | Get-Member
```

```Output
    TypeName: System.Management.Automation.PSCustomObject
Name          MemberType   Definition
----          ----------   ----------
Equals        Method       bool Equals(System.Object obj)
GetHashCode   Method       int GetHashCode()
GetType       Method       type GetType()
ToString      Method       string ToString()
Show-Calendar ScriptMethod System.Object Show-Calendar();
```

```powershell
$a."Show-Calendar"()
```

Das **Show-Calendar-** Skript Modul wird mithilfe des **ascustomobject** -Parameters importiert, um ein benutzerdefiniertes Objekt anzufordern, und der **passthru** -Parameter, um das Objekt zurückzugeben. Das resultierende benutzerdefinierte Objekt wird in der `$a` Variablen gespeichert.

Die- `$a` Variable wird an das `Get-Member` Cmdlet weitergeleitet, um die Eigenschaften und Methoden des gespeicherten Objekts anzuzeigen. Die Ausgabe zeigt eine **Show-Calendar-** Skript Methode.

Der Methodenname muss in Anführungszeichen eingeschlossen werden, um die **Show-Calendar-** Skript Methode aufzurufen, da der Name einen Bindestrich enthält.

### Beispiel 8: erneportieren eines Moduls in dieselbe Sitzung

In diesem Beispiel wird gezeigt, wie der **Force** -Parameter von verwendet wird, `Import-Module` Wenn ein Modul in dieselbe Sitzung importiert wird. Der **Force** -Parameter entfernt das geladene Modul und importiert es dann erneut.

```powershell
Import-Module PSDiagnostics
Import-Module PSDiagnostics -Force -Prefix PS
```

Der erste Befehl importiert das **psdiagnostics** -Modul. Der zweite Befehl importiert das Modul erneut, dieses Mal mit dem **Prefix** -Parameter.

Ohne den **Force** -Parameter würde die Sitzung zwei Kopien jedes **psdiagnostics** -Cmdlets enthalten, eine mit dem Standardnamen und eine mit dem Namen mit dem Präfix.

### Beispiel 9: Ausführen von Befehlen, die von importierten Befehlen ausgeblendet wurden

In diesem Beispiel wird veranschaulicht, wie Befehle ausgeführt werden, die von importierten Befehlen ausgeblendet wurden. Das **Testmodule** -Modul enthält eine Funktion `Get-Date` mit dem Namen, die das Jahr und den Tag des Jahres zurückgibt.

```powershell
Get-Date
```

```Output
Thursday, August 15, 2019 2:26:12 PM
```

```powershell
Import-Module TestModule
Get-Date
```

```Output
19227
```

```powershell
Get-Command Get-Date -All | Format-Table -Property CommandType, Name, ModuleName -AutoSize
```

```Output
CommandType     Name         ModuleName
-----------     ----         ----------
Function        Get-Date     TestModule
Cmdlet          Get-Date     Microsoft.PowerShell.Utility
```

```powershell
Microsoft.PowerShell.Utility\Get-Date
```

```Output
Thursday, August 15, 2019 2:28:31 PM
```

Das erste `Get-Date` Cmdlet gibt ein **DateTime** -Objekt mit dem aktuellen Datum zurück. Nach dem Importieren des **Testmodule** `Get-Date` -Moduls gibt das Jahr und den Tag des Jahres zurück.

Mit dem **all** -Parameter von werden `Get-Command` alle `Get-Date` Befehle in der Sitzung angezeigt. Die Ergebnisse zeigen, dass es zwei `Get-Date` Befehle in der Sitzung gibt, eine Funktion aus dem **Testmodule** -Modul und ein Cmdlet aus dem **Microsoft. PowerShell. Utility** -Modul.

Da Funktionen Vorrang vor Cmdlets haben, wird die- `Get-Date` Funktion aus dem **Testmodule** -Modul anstelle des- `Get-Date` Cmdlets ausgeführt. Um die ursprüngliche Version von auszuführen `Get-Date` , müssen Sie den Befehlsnamen mit dem Modulnamen qualifizieren.

Weitere Informationen zur Befehls Rangfolge in PowerShell finden Sie unter [about_Command_Precedence](about/about_Command_Precedence.md).

### Beispiel 10: Importieren einer Mindestversion eines Moduls

In diesem Beispiel wird das **PowerShellGet** -Modul importiert. Er verwendet den **Minimum Version** -Parameter von `Import-Module` , um nur Version 2.0.0 oder höher des Moduls zu importieren.

```powershell
Import-Module -Name PowerShellGet -MinimumVersion 2.0.0
```

Sie können auch den Parameter "Requirements **dversion** " verwenden, um eine bestimmte Version eines Moduls zu importieren, oder die **Modul** -und **Versions** Parameter des `#Requires` Schlüssel Worts verwenden, um eine bestimmte Version eines Moduls in einem Skript anzufordern.

### Beispiel 11: Importieren mit einem voll qualifizierten Namen

In diesem Beispiel wird eine bestimmte Version eines Moduls mit dem FullyQualifiedName importiert.

```powershell
PS> Get-Module -ListAvailable PowerShellGet | Select-Object Name, Version

Name          Version
----          -------
PowerShellGet 2.2.1
PowerShellGet 2.1.3
PowerShellGet 2.1.2
PowerShellGet 1.0.0.1

PS> Import-Module -FullyQualifiedName @{ModuleName = 'PowerShellGet'; ModuleVersion = '2.1.3' }
```

### Beispiel 12: Importieren mithilfe eines voll qualifizierten Pfads

In diesem Beispiel wird eine bestimmte Version eines Moduls mit dem voll qualifizierten Pfad importiert.

```powershell
PS> Get-Module -ListAvailable PowerShellGet | Select-Object Path

Path
----
C:\Program Files\PowerShell\Modules\PowerShellGet\2.2.1\PowerShellGet.psd1
C:\program files\powershell\6\Modules\PowerShellGet\PowerShellGet.psd1
C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\2.1.2\PowerShellGet.psd1
C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\1.0.0.1\PowerShellGet.psd1

PS> Import-Module -Name 'C:\Program Files\PowerShell\Modules\PowerShellGet\2.2.1\PowerShellGet.psd1'
```

### Beispiel 13: Importieren eines Moduls von einem Remote Computer

In diesem Beispiel wird gezeigt, wie Sie mit dem- `Import-Module` Cmdlet ein Modul von einem Remote Computer importieren.
Dieser Befehl verwendet das implizite Remoting-Feature von PowerShell.

Wenn Sie Module aus einer anderen Sitzung importieren, können Sie die Cmdlets in der aktuellen Sitzung verwenden.
Befehle, die die Cmdlets verwenden, werden jedoch in der Remote Sitzung ausgeführt.

```powershell
$s = New-PSSession -ComputerName Server01
Get-Module -PSSession $s -ListAvailable -Name NetSecurity
```

```Output
ModuleType Name             ExportedCommands
---------- ----             ----------------
Manifest   NetSecurity      {New-NetIPsecAuthProposal, New-NetIPsecMainModeCryptoProposal, New-Ne...
```

```powershell
Import-Module -PSSession $s -Name NetSecurity
Get-Command -Module NetSecurity -Name Get-*Firewall*
```

```Output
CommandType     Name                                               ModuleName
-----------     ----                                               ----------
Function        Get-NetFirewallAddressFilter                       NetSecurity
Function        Get-NetFirewallApplicationFilter                   NetSecurity
Function        Get-NetFirewallInterfaceFilter                     NetSecurity
Function        Get-NetFirewallInterfaceTypeFilter                 NetSecurity
Function        Get-NetFirewallPortFilter                          NetSecurity
Function        Get-NetFirewallProfile                             NetSecurity
Function        Get-NetFirewallRule                                NetSecurity
Function        Get-NetFirewallSecurityFilter                      NetSecurity
Function        Get-NetFirewallServiceFilter                       NetSecurity
Function        Get-NetFirewallSetting                             NetSecurity
```

```powershell
Get-NetFirewallRule -DisplayName "Windows Remote Management*" |
  Format-Table -Property DisplayName, Name -AutoSize
```

```Output
DisplayName                                              Name
-----------                                              ----
Windows Remote Management (HTTP-In)                      WINRM-HTTP-In-TCP
Windows Remote Management (HTTP-In)                      WINRM-HTTP-In-TCP-PUBLIC
Windows Remote Management - Compatibility Mode (HTTP-In) WINRM-HTTP-Compat-In-TCP
```

`New-PSSession` erstellt eine Remote Sitzung ( **PSSession** ) mit dem Server01-Computer. Die **PSSession** wird in der `$s` Variablen gespeichert.

Das Ausführen `Get-Module` von mit dem **PSSession** -Parameter zeigt an, dass das **Netsecurity** -Modul auf dem Remote Computer installiert und verfügbar ist. Dieser Befehl entspricht der Verwendung des- `Invoke-Command` Cmdlets zum Ausführen des `Get-Module` Befehls in der Remote Sitzung. Beispiel: (`Invoke-Command $s {Get-Module -ListAvailable -Name NetSecurity`

Beim Ausführen `Import-Module` mit dem **PSSession** -Parameter wird das **Netsecurity** -Modul vom Remote Computer in die aktuelle Sitzung importiert. Das- `Get-Command` Cmdlet wird verwendet, um Befehle zu erhalten, die mit **Get** und include **Firewall** aus dem **Netsecurity** -Modul beginnen. Die Ausgabe bestätigt, dass das Modul und die zugehörigen Cmdlets in die aktuelle Sitzung importiert wurden.

Als nächstes `Get-NetFirewallRule` Ruft das Cmdlet Windows-Remoteverwaltung Firewallregeln auf dem Computer "Server01" ab. Dies entspricht der Verwendung des- `Invoke-Command` Cmdlets, um `Get-NetFirewallRule` in der Remote Sitzung auszuführen.

### Beispiel 14: Verwalten von Speicher auf einem Remote Computer ohne das Windows-Betriebssystem

In diesem Beispiel hat der Administrator des Computers den WMI-Anbieter für die Modul Ermittlung installiert, mit dem Sie CIM-Befehle verwenden können, die für den Anbieter entwickelt wurden.

Mit dem- `New-CimSession` Cmdlet wird eine Sitzung auf dem Remote Computer mit dem Namen RSDGF03 erstellt. Die Sitzung stellt eine Verbindung mit dem WMI-Dienst auf dem Remote Computer her. Die CIM-Sitzung wird in der `$cs` Variablen gespeichert.
`Import-Module` verwendet **cimsession** in `$cs` , um das **Storage** -CIM-Modul vom RSDGF03-Computer zu importieren.

Das- `Get-Command` Cmdlet zeigt den `Get-Disk` Befehl im **Storage** -Modul an. Wenn Sie ein CIM-Modul in die lokale Sitzung importieren, konvertiert PowerShell die cdxml-Dateien für jeden Befehl in PowerShell-Skripts, die als Funktionen in der lokalen Sitzung angezeigt werden.

Obwohl `Get-Disk` in der lokalen Sitzung typisiert ist, wird das Cmdlet implizit auf dem Remote Computer ausgeführt, von dem er importiert wurde. Der Befehl gibt Objekte vom Remote Computer an die lokale Sitzung zurück.

```powershell
$cs = New-CimSession -ComputerName RSDGF03
Import-Module -CimSession $cs -Name Storage
# Importing a CIM module, converts the CDXML files for each command into PowerShell scripts.
# These appear as functions in the local session.
Get-Command Get-Disk
```

```Output
CommandType     Name                  ModuleName
-----------     ----                  ----------
Function        Get-Disk              Storage
```

```powershell
# Use implicit remoting to query disks on the remote computer from which the module was imported.
Get-Disk
```

```Output
Number Friendly Name           OperationalStatus  Total Size Partition Style
------ -------------           -----------------  ---------- ---------------
0      Virtual HD ATA Device   Online                  40 GB MBR
```

## PARAMETERS

### -Alias

Gibt die Aliase an, die dieses Cmdlet aus dem Modul in die aktuelle Sitzung importiert. Geben Sie eine durch Kommas getrennte Liste der Aliase ein. Platzhalterzeichen sind zulässig.

Einige Module exportieren automatisch ausgewählte Aliase in Ihre Sitzung, wenn Sie das Modul importieren.
Mit diesem Parameter können Sie eine Auswahl aus den exportierten Aliasen treffen.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Argumentlist

Gibt ein Array von Argumenten oder Parameterwerten an, die während des Befehls an ein Skript Modul übergeben werden `Import-Module` . Dieser Parameter ist nur gültig, wenn Sie ein Skript Modul importieren.

Sie können auch über den Alias " **args** " auf den Argument **List** -Parameter verweisen. Weitere Informationen zum Verhalten von **argumentlist** finden Sie unter [about_Splatting](about/about_Splatting.md#splatting-with-arrays).

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Ascustomobject

Gibt an, dass dieses Cmdlet ein benutzerdefiniertes Objekt mit Membern zurückgibt, die die importierten Modul Elemente darstellen. Dieser Parameter gilt nur für Skriptmodule.

Wenn Sie den **ascustomobject** -Parameter verwenden, `Import-Module` importiert die Modul Elemente in die Sitzung und gibt dann ein **pscustomobject** -Objekt anstelle eines **psmoduleinfo** -Objekts zurück. Sie können das benutzerdefinierte Objekt in einer Variablen speichern und die punktierte Schreibweise verwenden, um die Elemente aufzurufen.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Assembly

Gibt ein Array von assemblyobjekten an. Mit diesem Cmdlet werden die in den angegebenen assemblyobjekten implementierten Cmdlets und Anbieter importiert. Geben Sie eine Variable ein, die Assemblyobjekte enthält, oder geben Sie einen Befehl ein, mit dem die Assemblyobjekte erstellt werden. Sie können ein Assemblyobjekt auch über die Pipeline an senden `Import-Module` .

Wenn Sie diesen Parameter verwenden, werden nur die Cmdlets und Anbieter importiert, die durch die angegebenen Assemblys implementiert wurden. Wenn das Modul andere Dateien enthält, werden Sie nicht importiert, und möglicherweise fehlen wichtige Member des Moduls. Verwenden Sie diesen Parameter zum Debuggen und Testen des Moduls, oder wenn Sie angewiesen werden, es vom Modul Autor zu verwenden.

```yaml
Type: System.Reflection.Assembly[]
Parameter Sets: Assembly
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Cimnamespace

Gibt den Namespace eines alternativen CIM-Anbieters an, der CIM-Module verfügbar macht. Der Standardwert ist der Namespace des WMI-Anbieters für die Modulerkennung.

Verwenden Sie diesen Parameter, um CIM-Module von Computern und Geräten zu importieren, auf denen kein Windows-Betriebssystem ausgeführt wird.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.String
Parameter Sets: CimSession
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Cimresourceuri

Gibt einen alternativen Speicherort für die CIM-Module an. Der Standardwert ist der Ressourcen-URI des WMI-Anbieters für die Modul Ermittlung auf dem Remote Computer.

Verwenden Sie diesen Parameter, um CIM-Module von Computern und Geräten zu importieren, auf denen kein Windows-Betriebssystem ausgeführt wird.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Uri
Parameter Sets: CimSession
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession

Gibt eine CIM-Sitzung auf dem Remotecomputer an. Geben Sie eine Variable ein, die die CIM-Sitzung oder einen Befehl enthält, der die CIM-Sitzung abruft, z. b. den Befehl [Get-cimsession](../CimCmdlets/Get-CimSession.md) .

`Import-Module` verwendet die CIM-Sitzungs Verbindung, um Module vom Remote Computer in die aktuelle Sitzung zu importieren. Wenn Sie die Befehle aus dem importierten Modul in der aktuellen Sitzung verwenden, werden die Befehle auf dem Remote Computer ausgeführt.

Sie können diesen Parameter verwenden, um Module von Computern und Geräten zu importieren, auf denen das Windows-Betriebssystem nicht ausgeführt wird, sowie von Windows-Computern mit PowerShell, für die PowerShell-Remoting nicht aktiviert ist.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: Microsoft.Management.Infrastructure.CimSession
Parameter Sets: CimSession
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Cmdlet

Gibt ein Array von Cmdlets an, die von diesem Cmdlet aus dem Modul in die aktuelle Sitzung importiert werden.
Platzhalterzeichen sind zulässig.

Einige Module exportieren automatisch ausgewählte Cmdlets in Ihre Sitzung, wenn Sie das Modul importieren.
Mit diesem Parameter können Sie eine Auswahl aus den exportierten Cmdlets treffen.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Disablenamecheck

Gibt an, dass dieses Cmdlet die Meldung unterdrückt, die Sie warnt, wenn Sie ein Cmdlet oder eine Funktion importieren, deren Name ein nicht genehmigtes Verb oder ein unzulässiges Zeichen enthält.

Wenn ein Modul, das Sie importieren, Cmdlets oder Funktionen exportiert, die nicht genehmigte Verben in ihren Namen haben, zeigt PowerShell standardmäßig die folgende Warnmeldung an:

> Warnung: einige importierte Befehlsnamen enthalten nicht genehmigte Verben, die Sie möglicherweise weniger auffallen machen. Verwenden Sie den Verbose-Parameter für weitere Details, oder geben Sie „Get-Verb“ ein, um die Liste der zulässigen Verben anzuzeigen.

Diese Meldung ist nur eine Warnung. Es wird trotzdem das gesamte Modul einschließlich nicht konformer Befehle importiert. Obwohl die Meldung für Modulbenutzer angezeigt wird, sollte das Namensproblem vom Modulautor behoben werden.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Dieser Parameter bewirkt, dass ein Modul über den aktuellen Anfang geladen oder neu geladen wird.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -FullyQualifiedName

Gibt den voll qualifizierten Namen des Moduls als Hash Tabelle an. Der Wert kann eine Kombination aus Zeichen folgen und Hash Tabellen sein. Die Hash Tabelle verfügt über die folgenden Schlüssel.

- `ModuleName` - **Erforderlich** Gibt den Namen des Moduls an.
- `GUID` - **Optional** Gibt die GUID des Moduls an.
- Es ist auch **erforderlich** , einen der drei folgenden Schlüssel anzugeben. Diese Schlüssel können nicht gleichzeitig verwendet werden.
  - `ModuleVersion` : Gibt eine zulässige Mindestversion des Moduls an.
  - `RequiredVersion` : Gibt eine exakte, erforderliche Version des Moduls an.
  - `MaximumVersion` : Gibt die maximal zulässige Version des Moduls an.

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification[]
Parameter Sets: FullyQualifiedNameAndPSSession, FullyQualifiedName, FullyQualifiedNameAndWinCompat
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Funktion

Gibt ein Array von Funktionen an, die dieses Cmdlet aus dem Modul in die aktuelle Sitzung importiert.
Platzhalterzeichen sind zulässig. Einige Module exportieren automatisch ausgewählte Funktionen in Ihre Sitzung, wenn Sie das Modul importieren. Mit diesem Parameter können Sie eine Auswahl aus den exportierten Funktionen treffen.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Global

Gibt an, dass dieses Cmdlet Module in den globalen Sitzungszustand importiert, sodass Sie für alle Befehle in der Sitzung verfügbar sind.

Wenn `Import-Module` das Cmdlet von der Eingabeaufforderung, von der Skriptdatei oder von ScriptBlock aufgerufen wird, werden standardmäßig alle Befehle in den globalen Sitzungszustand importiert.

Wenn Sie von einem anderen Modul aufgerufen wird, `Import-Module` importiert das Cmdlet die Befehle in einem Modul, einschließlich der Befehle aus den in einem Modul eingefügten Modulen, in den Sitzungszustand des aufrufenden Moduls

> [!TIP]
> Vermeiden Sie das Aufrufen `Import-Module` von innerhalb eines Moduls. Deklarieren Sie das Zielmodul stattdessen als ein gestreamtes Modul im Manifest des übergeordneten Moduls. Das Deklarieren von geschsted Modulen verbessert die Auffindbarkeit von Abhängigkeiten.

Der **Global** -Parameter entspricht dem **Scope** -Parameter mit dem Wert **Global** .

Um die Befehle einzuschränken, die ein Modul exportiert, verwenden Sie einen `Export-ModuleMember` Befehl im Skript Modul.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaximumVersion

Gibt eine maximale Version an. Dieses Cmdlet importiert nur eine Version des Moduls, die kleiner oder gleich dem angegebenen Wert ist. Wenn keine Version qualifiziert ist, wird `Import-Module` ein Fehler zurückgegeben.

```yaml
Type: System.String
Parameter Sets: Name, PSSession, CimSession, WinCompat
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinimumVersion

Gibt eine Mindestversion an. Dieses Cmdlet importiert nur eine Version des Moduls, das größer als der angegebene Wert oder gleich dem angegebenen Wert ist. Verwenden Sie den **MinimumVersion** -Parameternamen oder dessen Alias **Version** . Wenn keine Version qualifiziert ist, wird von `Import-Module` ein Fehler generiert.

Verwenden Sie zum Angeben einer genauen Version den **RequiredVersion** -Parameter. Sie können auch die **Module** -und **Versions** Parameter des **#requires** -Schlüssel Worts verwenden, um eine bestimmte Version eines Moduls in einem Skript anzufordern.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Version
Parameter Sets: Name, PSSession, CimSession, WinCompat
Aliases: Version

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ModuleInfo

Gibt ein Array der zu importierenden Modul Objekte an. Geben Sie eine Variable ein, die die Modul Objekte enthält, oder einen Befehl, mit dem die Modul Objekte abgerufen werden, z. b. den folgenden Befehl: `Get-Module -ListAvailable` . Sie können Modul Objekte auch über die Pipeline an übergeben `Import-Module` .

```yaml
Type: System.Management.Automation.PSModuleInfo[]
Parameter Sets: ModuleInfo
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name

Gibt die Namen der zu importierenden Module an. Geben Sie den Namen des Moduls oder den Namen einer Datei im Modul ein, z. b. eine-,-,- `.psd1` `.psm1` oder- `.dll` `.ps1` Datei. Dateipfade sind optional. Platzhalter Zeichen sind nicht zulässig. Sie können Modulnamen und Dateinamen auch über die Pipeline an übergeben `Import-Module` .

Wenn Sie einen Pfad weglassen, `Import-Module` sucht das Modul in den Pfaden, die in der `$env:PSModulePath` Umgebungsvariablen gespeichert sind.

Geben Sie nach Möglichkeit nur den Namen des Moduls an. Wenn Sie einen Dateinamen angeben, werden nur die in dieser Datei implementierten Elemente importiert. Wenn das Modul andere Dateien enthält, werden Sie nicht importiert, und möglicherweise fehlen wichtige Member des Moduls.

```yaml
Type: System.String[]
Parameter Sets: Name, PSSession, CimSession, WinCompat
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### -NoClobber

Verhindert das Importieren von Befehlen, die denselben Namen wie vorhandene Befehle in der aktuellen Sitzung haben. Standardmäßig werden `Import-Module` alle exportierten Modul Befehle importiert.

Befehle mit den gleichen Namen können Befehle in der Sitzung ausblenden oder ersetzen. Um Konflikte bei Befehlsnamen in einer Sitzung zu vermeiden, verwenden Sie die Parameter **Prefix** oder **NoClobber** . Weitere Informationen (womöglich nur in englischer Sprache) zu Namenskonflikten und zur Befehlsrangfolge finden Sie unter „Module und Namenskonflikte“ in [about_Modules](about/about_Modules.md) und [about_Command_Precedence](about/about_Command_Precedence.md).

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NoOverwrite

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru

Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten. Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Präfix

Gibt ein Präfix an, das dieses Cmdlet den Substantiven in den Namen importierter Modul Elemente hinzufügt.

Verwenden Sie diesen Parameter, um Namenskonflikte zu vermeiden, die auftreten können, wenn verschiedene Elemente in der Sitzung den gleichen Namen haben. Dieser Parameter ändert nicht das Modul und wirkt sich nicht auf Dateien aus, die das Modul zur eigenen Verwendung importiert. Diese werden als "geduckte Module" bezeichnet. Dieses Cmdlet wirkt sich nur auf die Namen von Membern in der aktuellen Sitzung aus.

Wenn Sie z. b. das Präfix UTC angeben und dann ein `Get-Date` Cmdlet importieren, ist das Cmdlet in der Sitzung als bekannt `Get-UTCDate` und nicht mit dem ursprünglichen `Get-Date` Cmdlet verwechselt.

Der Wert dieses Parameters hat Vorrang vor der **DefaultCommandPrefix** -Eigenschaft des Moduls, die das Standardpräfix angibt.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PSSession

Gibt eine vom Benutzer verwaltete PowerShell-Sitzung ( **PSSession** ) an, aus der dieses Cmdlet Module in die aktuelle Sitzung importiert. Geben Sie eine Variable ein, die eine **PSSession** oder einen Befehl enthält, mit dem eine **PSSession** abgerufen wird, z. b. ein- `Get-PSSession` Befehl.

Beim Importieren eines Moduls aus einer anderen Sitzung in die aktuelle Sitzung können Sie die Cmdlets aus dem Modul in der aktuellen Sitzung verwenden, so wie Sie Cmdlets aus einem lokalen Modul verwenden würden. Befehle, die die Remote-Cmdlets verwenden, werden in der Remote Sitzung ausgeführt, aber die remotingdetails werden von PowerShell im Hintergrund verwaltet.

Dieser Parameter verwendet das implizite Remoting-Feature von PowerShell. Dies entspricht der Verwendung des- `Import-PSSession` Cmdlets, um bestimmte Module aus einer Sitzung zu importieren.

`Import-Module` PowerShell-Kernmodule können nicht aus einer anderen Sitzung importiert werden. Die PowerShell-Kernmodule verfügen über Namen, die mit Microsoft. PowerShell beginnen.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.Automation.Runspaces.PSSession
Parameter Sets: PSSession, FullyQualifiedNameAndPSSession
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Requirements dversion

Gibt eine Version des Moduls an, das von diesem Cmdlet importiert wird. Wenn die Version nicht installiert ist, wird von `Import-Module` ein Fehler generiert.

Standardmäßig `Import-Module` importiert das Modul, ohne die Versionsnummer zu überprüfen.

Verwenden Sie zum Angeben einer Mindestversion den **MinimumVersion** -Parameter. Sie können auch die **Module** -und **Versions** Parameter des **#requires** -Schlüssel Worts verwenden, um eine bestimmte Version eines Moduls in einem Skript anzufordern.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

Skripts, die "Requirements **dversion** " zum Importieren von Modulen verwenden, die in vorhandenen Versionen des Windows-Betriebssystems enthalten sind, werden nicht automatisch in zukünftigen Versionen des Windows-Betriebssystems ausgeführt. Dies liegt daran, dass die Versionsnummern von PowerShell-Modulen in zukünftigen Versionen des Windows-Betriebssystems höher sind als die Modul Versionsnummern in vorhandenen Versionen des Windows-Betriebssystems.

```yaml
Type: System.Version
Parameter Sets: Name, PSSession, CimSession, WinCompat
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Bereich

Gibt einen Bereich an, in den dieses Cmdlet das Modul importiert.

Zulässige Werte für diesen Parameter:

- **Global** . Für alle Befehle in der Sitzung verfügbar. Entspricht dem **Global** -Parameter.
- **Lokal** . Nur im aktuellen Bereich verfügbar.

Wenn `Import-Module` das Cmdlet von der Eingabeaufforderung, von der Skriptdatei oder von ScriptBlock aufgerufen wird, werden standardmäßig alle Befehle in den globalen Sitzungszustand importiert. Sie können den Parameter " **-Scope** " mit dem Wert " **local** " verwenden, um Modul Inhalt in das Skript oder den ScriptBlock-Bereich zu importieren.

Wenn Sie von einem anderen Modul aufgerufen wird, `Import-Module` importiert das Cmdlet die Befehle in einem Modul, einschließlich der Befehle aus den in einem Modul vorgerufenen Modulen, in den Sitzungszustand des Aufrufers Durch `-Scope Global` angeben `-Global` von oder wird angegeben, dass dieses Cmdlet Module in den globalen Sitzungszustand importiert, sodass Sie für alle Befehle in der Sitzung verfügbar sind.

Der **globale** Parameter entspricht dem **Scope** -Parameter mit dem Wert Global.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Local, Global

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Variable

Gibt ein Array von Variablen an, die von diesem Cmdlet aus dem Modul in die aktuelle Sitzung importiert werden.
Geben Sie eine Liste der Variablen ein. Platzhalterzeichen sind zulässig.

Einige Module exportieren automatisch ausgewählte Variablen in Ihre Sitzung, wenn Sie das Modul importieren.
Mit diesem Parameter können Sie eine Auswahl aus den exportierten Variablen treffen.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Skipeditioncheck

Überspringt die Überprüfung des `CompatiblePSEditions` Felds.

Ermöglicht das Laden eines Moduls aus dem `"$($env:windir)\System32\WindowsPowerShell\v1.0\Modules"` Modul Verzeichnis in PowerShell Core, wenn dieses Modul nicht `Core` im `CompatiblePSEditions` Feld Manifest angegeben ist.

Wenn Sie ein Modul aus einem anderen Pfad importieren, bewirkt dieser Switch nichts, da die Überprüfung nicht ausgeführt wird. Unter Linux und macOS führt dieser Switch keine Aktion aus.

Weitere Informationen finden Sie unter [about_PowerShell_Editions](About/about_PowerShell_Editions.md).

> [!WARNING]
> `Import-Module -SkipEditionCheck` Es ist jedoch wahrscheinlich, dass ein Modul nicht importiert werden kann. Auch wenn der Vorgang erfolgreich ist, kann der Aufruf eines Befehls aus dem Modul zu einem späteren Zeitpunkt fehlschlagen, wenn versucht wird, eine nicht kompatible API zu verwenden.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Name, PSSession, CimSession, FullyQualifiedNameAndPSSession, FullyQualifiedName, Assembly, ModuleInfo
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Usewindowspowershell

Lädt das Modul mithilfe der Windows PowerShell-Kompatibilitäts Funktionalität. Weitere Informationen finden Sie unter [about_Windows_PowerShell_Compatibility](About/about_Windows_PowerShell_Compatibility.md) .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: WinCompat, FullyQualifiedNameAndWinCompat
Aliases: UseWinPS

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System. String, System. Management. Automation. psmoduleinfo, System. Reflection. Assembly

Sie können einen Modulnamen, ein Modul Objekt oder ein Assemblyobjekt über die Pipeline an dieses Cmdlet übergeben.

## AUSGABEN

### "None", "System. Management. Automation. psmoduleinfo" oder "System. Management. Automation. pscustomobject"

Standardmäßig `Import-Module` generiert keine Ausgabe. Wenn Sie den **passthru** -Parameter angeben, generiert das Cmdlet ein **System. Management. Automation. psmoduleinfo** -Objekt, das das Modul darstellt. Wenn Sie den **ascustomobject** -Parameter angeben, generiert er ein **pscustomobject** -Objekt.

## HINWEISE

- Bevor Sie ein Modul importieren können, muss das Modul auf dem lokalen Computer installiert sein. Das heißt, das Modul Verzeichnis muss in ein Verzeichnis kopiert werden, auf das der lokale Computer zugreifen kann. Weitere Informationen finden Sie unter [about_Modules](About/about_Modules.md).

  Sie können auch die Parameter **PSSession** und **CIMSession** verwenden, um Module zu importieren, die auf Remotecomputern installiert sind. Befehle, die die Cmdlets in diesen Modulen verwenden, werden jedoch in der Remote Sitzung auf dem Remote Computer ausgeführt.

- Wenn Sie Member mit demselben Namen und demselben Typ in die Sitzung importieren, verwendet PowerShell den zuletzt importierten Member standardmäßig. Variablen und Aliase werden ersetzt, und die Originale sind nicht zugänglich. Funktionen, Cmdlets und Anbieter werden lediglich von den neuen Membern schattiert. Sie können darauf zugreifen, indem Sie den Befehlsnamen mit dem Namen seines Snap-Ins, Moduls oder Funktions Pfads qualifizieren.

- Verwenden Sie das-Cmdlet, um die Formatierungsdaten für Befehle zu aktualisieren, die aus einem Modul importiert wurden `Update-FormatData` . `Update-FormatData` aktualisiert auch die Formatierungsdaten für Befehle in der Sitzung, die aus Modulen importiert wurden. Wenn die Formatierungs Datei für ein Modul geändert wird, können Sie einen Befehl ausführen, `Update-FormatData` um die Formatierungsdaten für importierte Befehle zu aktualisieren. Sie müssen das Modul nicht erneut importieren.

- Ab Windows PowerShell 3,0 werden die mit PowerShell installierten Hauptbefehle in Module gepackt. In Windows PowerShell 2,0 und in Host Programmen, die in neueren Versionen von PowerShell ältere Sitzungen erstellen, werden die Hauptbefehle in Snap-Ins ( **pssnapins** ) gepackt. Die Ausnahme ist **Microsoft. PowerShell. Core** , bei der es sich immer um ein Snap-in handelt. Remote Sitzungen, wie z. b. die vom `New-PSSession` Cmdlet gestarteten, sind auch ältere Sitzungen, die Core-Snap-Ins enthalten.

  Weitere Informationen über die **CreateDefault2** -Methode, die Sitzungen im neueren Stil mit Kernmodulen erstellt, finden Sie unter der [CreateDefault2-Methode](/dotnet/api/system.management.automation.runspaces.initialsessionstate.createdefault2).

- `Import-Module` PowerShell-Kernmodule können nicht aus einer anderen Sitzung importiert werden. Die PowerShell-Kernmodule verfügen über Namen, die mit beginnen `Microsoft.PowerShell` .

- In Windows PowerShell 2,0 wurden einige der Eigenschaftswerte des Modul Objekts, z. b. die Eigenschaften Werte " **exportedcmdlets** " und " **netstedmodules** ", erst aufgefüllt, wenn das Modul importiert wurde, und waren nicht für das Modul Objekt verfügbar, das der **passthru** -Parameter zurückgibt. In Windows PowerShell 3,0 werden alle Modul Eigenschaftswerte aufgefüllt.

- Wenn Sie versuchen, ein Modul zu importieren, das Assemblys im gemischten Modus enthält, die nicht mit Windows PowerShell 3,0 kompatibel sind, `Import-Module` gibt eine Fehlermeldung wie die folgende zurück.

  > Import-Module: die Assembly im gemischten Modus wird für die Version "v 2.0.50727" der Laufzeit erstellt und kann nicht ohne zusätzliche Konfigurationsinformationen in der Laufzeitumgebung von 4,0 geladen werden.

  Dieser Fehler tritt auf, wenn ein Modul, das für Windows PowerShell 2,0 entworfen wurde, mindestens eine Assembly mit gemischtem Modul enthält, d. h. eine Assembly, die sowohl verwalteten als auch nicht verwalteten Code, z. b. C++ und c#, enthält.

  Zum Importieren eines Moduls, das Assemblys im gemischten Modus enthält, starten Sie Windows PowerShell 2,0 mit dem folgenden Befehl, und `Import-Module` Wiederholen Sie dann den Befehl.

  `PowerShell.exe -Version 2.0`

- Um die CIM-Sitzung zu verwenden, müssen auf dem Remotecomputer WS-Management-Remoting und Windows-Verwaltungsinstrumentation (WMI) verfügbar sein, wobei es sich um die Microsoft-Implementierung des Common Information Model (CIM)-Standards handelt. Der Computer muss auch den WMI-Anbieter für die Modulerkennung oder einen anderen CIM-Anbieter haben, der die gleichen grundlegenden Funktionen hat.

  Sie können die CIM-Sitzungs Funktion auf Computern verwenden, auf denen kein Windows-Betriebssystem ausgeführt wird, sowie auf Windows-Computern mit PowerShell, auf denen PowerShell-Remoting nicht aktiviert ist.

  Sie können auch die CIM-Parameter verwenden, um CIM-Module von Computern zu erhalten, auf denen PowerShell-Remoting aktiviert ist, einschließlich des lokalen Computers. Wenn Sie eine CIM-Sitzung auf dem lokalen Computer erstellen, verwendet PowerShell DCOM anstelle von WMI, um die Sitzung zu erstellen.

- Standardmäßig `Import-Module` importiert Module in den globalen Gültigkeitsbereich, auch wenn Sie von einem Nachfolger Bereich aufgerufen werden. Der Bereich der obersten Ebene und alle untergeordneten Bereiche haben Zugriff auf die exportierten Elemente des Moduls.

  In einem Nachfolger Bereich `-Scope Local` beschränkt den Import auf diesen Bereich und alle untergeordneten Bereiche. Übergeordnete Bereiche werden dann die importierten Member nicht angezeigt.

  > [!NOTE]
  > `Get-Module` zeigt alle in der aktuellen Sitzung geladenen Module an. Dies schließt Module ein, die lokal in einem Nachfolger Bereich geladen werden. Verwenden `Get-Command -Module modulename` Sie, um anzuzeigen, welche Member im aktuellen Bereich geladen werden.

  Wenn das Modul Klassen-und Enumerationsdefinitionen enthält, verwenden `using module` Sie am Anfang des Skripts. Dadurch werden die Skripts importiert, einschließlich der-Klasse und der Enumeration-Definitionen. Weitere Informationen finden Sie unter [about_Using](About/about_Using.md).

## VERWANDTE LINKS

[Export-ModuleMember](Export-ModuleMember.md)

[Get-Module](Get-Module.md)

[New-Module](New-Module.md)

[Remove-Module](Remove-Module.md)

[about_PowerShell_Editions](About/about_PowerShell_Editions.md)
