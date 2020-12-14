---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 12/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-module?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Module
ms.openlocfilehash: 15a7d7e6488e4b3d11375649fdbc810e1aeb2b2f
ms.sourcegitcommit: 7b376314e7640c39a53aac9f0db8bb935514a960
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2020
ms.locfileid: "96564355"
---
# Get-Module

## ZUSAMMENFASSUNG
Listet die in der aktuellen Sitzung importierten Module auf oder kann aus dem psmodulepath importiert werden.

## SYNTAX

### Geladen (Standard)

```
Get-Module [[-Name] <String[]>] [-FullyQualifiedName <ModuleSpecification[]>] [-All] [<CommonParameters>]
```

### Verfügbar

```
Get-Module [[-Name] <String[]>] [-FullyQualifiedName <ModuleSpecification[]>] [-All] [-ListAvailable]
 [-PSEdition <String>] [-Refresh] [<CommonParameters>]
```

### PsSession

```
Get-Module [[-Name] <String[]>] [-FullyQualifiedName <ModuleSpecification[]>] [-ListAvailable]
 [-PSEdition <String>] [-Refresh] -PSSession <PSSession> [<CommonParameters>]
```

### CimSession

```
Get-Module [[-Name] <String[]>] [-FullyQualifiedName <ModuleSpecification[]>] [-ListAvailable] [-Refresh]
 -CimSession <CimSession> [-CimResourceUri <Uri>] [-CimNamespace <String>] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Get-Module` Cmdlet werden die PowerShell-Module aufgelistet, die importiert oder in eine PowerShell-Sitzung importiert werden können. Ohne Parameter ruft `Get-Module` Module ab, die in die aktuelle Sitzung importiert wurden. Der **listavailable** -Parameter wird verwendet, um die Module aufzulisten, die aus den Pfaden, die in der psmodulepath-Umgebungsvariablen () angegeben sind, importiert werden können `$env:PSModulePath` .

Das Modul Objekt, das `Get-Module` zurückgibt, enthält wertvolle Informationen über das Modul. Sie können die Modul Objekte auch an andere Cmdlets weiterreichen, wie z `Import-Module` . b. die-und- `Remove-Module` Cmdlets.

`Get-Module` Listet Module auf, importiert diese jedoch nicht. Ab Windows PowerShell 3,0 werden Module automatisch importiert, wenn Sie einen Befehl im Modul verwenden, aber ein `Get-Module` Befehl löst keinen automatischen Import aus. Sie können die Module auch mithilfe des Cmdlets in Ihre Sitzung importieren `Import-Module` .

Ab Windows PowerShell 3,0 können Sie Module aus Remote Sitzungen in die lokale Sitzung importieren und dann importieren. Diese Strategie verwendet das implizite Remoting-Feature von PowerShell und entspricht der Verwendung des- `Import-PSSession` Cmdlets. Wenn Sie Befehle in Modulen verwenden, die aus einer anderen Sitzung importiert wurden, werden die Befehle implizit in der Remote Sitzung ausgeführt. Mit dieser Funktion können Sie den Remote Computer über die lokale Sitzung verwalten.

Außerdem können Sie ab Windows PowerShell 3,0 und verwenden, `Get-Module` `Import-Module` um Common Information Model (CIM)-Module zu erhalten und zu importieren. CIM-Module definieren Cmdlets in cdxml-Dateien (Cmdlet Definition XML). Mit dieser Funktion können Sie Cmdlets verwenden, die in nicht verwalteten Codeassemblys implementiert sind, z. b. in C++ geschriebene Assemblys.

Implizites Remoting kann zum Verwalten von Remote Computern verwendet werden, auf denen PowerShell-Remoting aktiviert ist.
Erstellen Sie eine **PSSession** auf dem Remote Computer, und verwenden Sie dann den **PSSession** -Parameter von `Get-Module` , um die PowerShell-Module in der Remote Sitzung abzurufen. Wenn Sie ein Modul aus der Remote Sitzung importieren, werden die importierten Befehle in der Sitzung auf dem Remote Computer ausgeführt.

Sie können eine ähnliche Strategie zum Verwalten von Computern verwenden, auf denen PowerShell-Remoting nicht aktiviert ist.
Dies umfasst Computer, auf denen das Windows-Betriebssystem nicht ausgeführt wird, sowie Computer, auf denen PowerShell, aber nicht PowerShell-Remoting aktiviert ist.

Beginnen Sie, indem Sie eine CIM-Sitzung auf dem Remote Computer erstellen. Eine CIM-Sitzung ist eine Verbindung mit Windows-Verwaltungsinstrumentation (WMI) auf dem Remote Computer. Verwenden Sie dann den **cimsession** -Parameter von `Get-Module` , um CIM-Module aus der CIM-Sitzung zu erhalten. Wenn Sie ein CIM-Modul mit dem `Import-Module` Cmdlet importieren und dann die importierten Befehle ausführen, werden die Befehle implizit auf dem Remote Computer ausgeführt. Mit dieser WMI- und CIM-Strategie können Sie den Remotecomputer verwalten.

## BEISPIELE

### Beispiel 1: Importieren von Modulen, die in die aktuelle Sitzung importiert werden

```powershell
Get-Module
```

Dieser Befehl ruft Module ab, die in die aktuelle Sitzung importiert wurden.

### Beispiel 2: Get installierter Module und verfügbarer Module

```powershell
Get-Module -ListAvailable
```

Dieser Befehl ruft die Module ab, die auf dem Computer installiert sind und in die aktuelle Sitzung importiert werden können.

`Get-Module` sucht nach verfügbaren Modulen in dem Pfad, der in der **$ENV:P smodulepath** -Umgebungsvariablen angegeben ist. Weitere Informationen zu **PSModulePath** finden Sie unter [about_Modules](About/about_Modules.md) und [about_Environment_Variables](About/about_Environment_Variables.md).

### Beispiel 3: alle exportierten Dateien

```powershell
Get-Module -ListAvailable -All
```

Dieser Befehl ruft alle exportierten Dateien für alle verfügbaren Module ab.

### Beispiel 4: Holen Sie ein Modul mit seinem voll qualifizierten Namen.

```powershell
$FullyQualifedName = @{ModuleName="Microsoft.PowerShell.Management";ModuleVersion="3.1.0.0"}
Get-Module -FullyQualifiedName $FullyQualifedName | Format-Table -Property Name,Version
```

```Output
Name                             Version
----                             -------
Microsoft.PowerShell.Management  3.1.0.0
```

Mit diesem Befehl wird das **Microsoft. PowerShell. Management** -Modul abgerufen, indem der voll qualifizierte Name des Moduls mithilfe des **FullyQualifiedName** -Parameters angegeben wird. Der Befehl übergibt die Ergebnisse dann an das `Format-Table` Cmdlet, um die Ergebnisse als Tabelle mit dem **Namen** und der **Version** als Spaltenüberschriften zu formatieren.

### Beispiel 5: erhalten der Eigenschaften eines Moduls

```powershell
Get-Module | Get-Member -MemberType Property | Format-Table Name
```

```Output
Name
----
AccessMode
Author
ClrVersion
CompanyName
Copyright
Definition
Description
DotNetFrameworkVersion
ExportedAliases
ExportedCmdlets
ExportedCommands
ExportedFormatFiles
ExportedFunctions
ExportedTypeFiles
ExportedVariables
ExportedWorkflows
FileList
Guid
HelpInfoUri
LogPipelineExecutionDetails
ModuleBase
ModuleList
ModuleType
Name
NestedModules
OnRemove
Path
PowerShellHostName
PowerShellHostVersion
PowerShellVersion
PrivateData
ProcessorArchitecture
RequiredAssemblies
RequiredModules
RootModule
Scripts
SessionState
Version
```

Mit diesem Befehl werden die Eigenschaften des **psmoduleinfo** -Objekts abgerufen, das `Get-Module` zurückgibt. Für jede Moduldatei ist ein Objekt vorhanden.

Mit den Eigenschaften können Sie die Modulobjekte formatieren und filtern. Weitere Informationen zu den Eigenschaften finden Sie unter [psmoduleinfo-Eigenschaften](/dotnet/api/system.management.automation.psmoduleinfo).

Die Ausgabe enthält die neuen Eigenschaften, z. b. " **Author** " und " **CompanyName**", die in Windows PowerShell 3,0 eingeführt wurden.

### Beispiel 6: Gruppieren aller Module nach Name

```powershell
Get-Module -ListAvailable -All | Format-Table -Property Name, Moduletype, Path -Groupby Name
```

```Output
Name: AppLocker

Name      ModuleType Path
----      ---------- ----
AppLocker   Manifest C:\Windows\system32\WindowsPowerShell\v1.0\Modules\AppLocker\AppLocker.psd1


   Name: Appx

Name ModuleType Path
---- ---------- ----
Appx   Manifest C:\Windows\system32\WindowsPowerShell\v1.0\Modules\Appx\en-US\Appx.psd1
Appx   Manifest C:\Windows\system32\WindowsPowerShell\v1.0\Modules\Appx\Appx.psd1
Appx     Script C:\Windows\system32\WindowsPowerShell\v1.0\Modules\Appx\Appx.psm1


   Name: BestPractices

Name          ModuleType Path
----          ---------- ----
BestPractices   Manifest C:\Windows\system32\WindowsPowerShell\v1.0\Modules\BestPractices\BestPractices.psd1


   Name: BitsTransfer

Name         ModuleType Path
----         ---------- ----
BitsTransfer   Manifest C:\Windows\system32\WindowsPowerShell\v1.0\Modules\BitsTransfer\BitsTransfer.psd1
```

Dieser Befehl ruft alle Moduldateien ab, die importiert und verfügbar sind, und gruppiert Sie dann nach Modulname. So können Sie die Moduldateien sehen, die von denen einzelnen Skripts exportiert werden.

### Beispiel 7: Anzeigen des Inhalts eines Modul Manifests

Diese Befehle zeigen den Inhalt des Modul Manifests für das Windows PowerShell- **bitstransfer** -Modul an.

Module müssen keine Manifest-Dateien haben. Wenn Sie über eine Manifest-Datei verfügen, muss die Manifest-Datei nur eine Versionsnummer enthalten. Manifestdateien enthalten jedoch oft nützliche Informationen über ein Modul, seine Anforderungen und seinen Inhalt.

```powershell
# First command
$m = Get-Module -list -Name BitsTransfer

# Second command
Get-Content $m.Path
```

```Output
@ {
    GUID               = "{8FA5064B-8479-4c5c-86EA-0D311FE48875}"
    Author             = "Microsoft Corporation"
    CompanyName        = "Microsoft Corporation"
    Copyright          = "Microsoft Corporation. All rights reserved."
    ModuleVersion      = "1.0.0.0"
    Description        = "Windows PowerShell File Transfer Module"
    PowerShellVersion  = "2.0"
    CLRVersion         = "2.0"
    NestedModules      = "Microsoft.BackgroundIntelligentTransfer.Management"
    FormatsToProcess   = "FileTransfer.Format.ps1xml"
    RequiredAssemblies = Join-Path $psScriptRoot "Microsoft.BackgroundIntelligentTransfer.Management.Interop.dll"
}
```

Mit dem ersten Befehl wird das PSModuleInfo-Objekt abgerufen, das das BitsTransfer-Modul darstellt. Das Objekt wird in der `$m` Variablen gespeichert.

Der zweite Befehl verwendet das `Get-Content` Cmdlet, um den Inhalt der Manifest-Datei im angegebenen Pfad zu erhalten. Mithilfe der Punktnotation wird der Pfad zur Manifestdatei abgerufen, der in der Path-Eigenschaft des Objekts gespeichert ist. Die Ausgabe zeigt den Inhalt des Modulmanifests.

### Beispiel 8: Auflisten von Dateien im Modul Verzeichnis

```powershell
dir (Get-Module -ListAvailable FileTransfer).ModuleBase
```

```Output
Directory: C:\Windows\system32\WindowsPowerShell\v1.0\Modules\FileTransfer
Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d----        12/16/2008  12:36 PM            en-US
-a---        11/19/2008  11:30 PM      16184 FileTransfer.Format.ps1xml
-a---        11/20/2008  11:30 PM       1044 FileTransfer.psd1
-a---        12/16/2008  12:20 AM     108544 Microsoft.BackgroundIntelligentTransfer.Management.Interop.dll
```

Dieser Befehl listet die Dateien im Verzeichnis des Moduls auf. Dies ist eine weitere Methode, um den Inhalt eines Modul zu ermitteln, bevor Sie es importieren. Einige Module verfügen möglicherweise über Hilfe- oder Infodateien, die das Modul beschreiben.

### Beispiel 9: Installieren von Modulen, die auf einem Computer installiert sind

```powershell
$s = New-PSSession -ComputerName Server01

Get-Module -PSSession $s -ListAvailable
```

Diese Befehle rufen die Module ab, die auf dem Computer Server01 installiert sind.

Der erste Befehl verwendet das `New-PSSession` Cmdlet, um eine **PSSession** auf dem Server01-Computer zu erstellen. Der Befehl speichert die **PSSession** in der $s Variable.

Der zweite Befehl verwendet den **PSSession** -und den **listavailable** -Parameter von `Get-Module` , um die Module in der **PSSession** in der `$s` Variablen abzurufen.

Wenn Sie Module aus anderen Sitzungen an das `Import-Module` Cmdlet weiterreichen, `Import-Module` importiert das Modul mithilfe des impliziten Remotingfeatures in die aktuelle Sitzung. Dies entspricht der Verwendung des- `Import-PSSession` Cmdlets. Sie können die Cmdlets aus dem Modul in der aktuellen Sitzung verwenden, die Befehle, die diese Cmdlets verwenden, werden jedoch tatsächlich in der Remotesitzung ausgeführt. Weitere Informationen finden Sie unter [`Import-Module`](Import-Module.md) und [`Import-PSSession`](../Microsoft.PowerShell.Utility/Import-PSSession.md).

### Beispiel 10: Verwalten eines Computers, auf dem das Windows-Betriebssystem nicht ausgeführt wird

Die Befehle in diesem Beispiel ermöglichen es Ihnen, die Speichersysteme eines Remote Computers zu verwalten, auf dem das Windows-Betriebssystem nicht ausgeführt wird.
Da der Administrator des Computers in diesem Beispiel den WMI-Anbieter für die Modulerkennung installiert hat, können die CIM-Befehle die Standardwerte verwenden, für den Anbieter konzipiert wurden.

```powershell
$cs = New-CimSession -ComputerName RSDGF03
Get-Module -CimSession $cs -Name Storage | Import-Module
Get-Command Get-Disk
```

```Output
CommandType     Name                  ModuleName
-----------     ----                  ----------
Function        Get-Disk              Storage
```

```powershell
Get-Disk
```

```Output
Number Friendly Name              OperationalStatus          Total Size Partition Style
------ -------------              -----------------          ---------- ---------------
0      Virtual HD ATA Device      Online                          40 GB MBR
```

Der erste Befehl verwendet das `New-CimSession` Cmdlet, um eine Sitzung auf dem Remote Computer RSDGF03 zu erstellen. Die Sitzung stellt auf dem Remotecomputer eine Verbindung mit WMI her. Der Befehl speichert die CIM-Sitzung in der `$cs` Variablen.

Der zweite Befehl verwendet die CIM-Sitzung in der `$cs` Variablen, um `Get-Module` auf dem RSDGF03-Computer einen Befehl auszuführen. Mit dem Name-Parameter wird das Storage-Modul angegeben. Der Befehl verwendet einen Pipeline Operator (|), um das Speichermodul an das `Import-Module` Cmdlet zu senden, das das Modul in die lokale Sitzung importiert.

Mit dem dritten Befehl wird das `Get-Command` Cmdlet für den `Get-Disk` Befehl im Storage-Modul ausgeführt.
Wenn Sie ein CIM-Modul in die lokale Sitzung importieren, konvertiert PowerShell die cdxml-Dateien, die das CIM-Modul darstellen, in PowerShell-Skripts, die als Funktionen in der lokalen Sitzung angezeigt werden.

Der vierte Befehl führt den `Get-Disk` Befehl aus. Obwohl der Befehl in die lokale Sitzung eingegeben wird, wird er implizit auf dem Remotecomputer ausgeführt, von dem er importiert wurde. Der Befehl ruft Objekte vom Remotecomputer ab und gibt sie an die lokale Sitzung zurück.

## PARAMETERS

### -All

Gibt an, dass dieses Cmdlet alle Module in jedem Modul Ordner abruft, einschließlich der in einem Modul eingefügten Module, Manifest-Dateien (. psd1), Skript Moduldateien (. psm1) und binärer Moduldateien (. dll). Ohne diesen Parameter `Get-Module` wird von nur das Standardmodul in jedem Modul Ordner abgerufen.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Loaded, Available
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Cimnamespace

Gibt den Namespace eines alternativen CIM-Anbieters an, der CIM-Module verfügbar macht. Der Standardwert ist der Namespace des WMI-Anbieters für die Modulerkennung.

Verwenden Sie diesen Parameter zum Aufrufen von CIM-Modulen von Computern und Geräten, auf denen das Windows-Betriebssystem nicht ausgeführt wird.

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

Verwenden Sie diesen Parameter zum Aufrufen von CIM-Modulen von Computern und Geräten, auf denen das Windows-Betriebssystem nicht ausgeführt wird.

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

Gibt eine CIM-Sitzung auf dem Remotecomputer an. Geben Sie eine Variable ein, die die CIM-Sitzung oder einen Befehl enthält, der die CIM-Sitzung abruft, z. b. den Befehl [Get-cimsession](/powershell/module/cimcmdlets/get-cimsession) .

`Get-Module` verwendet die CIM-Sitzungs Verbindung, um Module vom Remote Computer zu erhalten. Wenn Sie das Modul mit dem `Import-Module` Cmdlet importieren und die Befehle aus dem importierten Modul in der aktuellen Sitzung verwenden, werden die Befehle tatsächlich auf dem Remote Computer ausgeführt.

Sie können diesen Parameter verwenden, um Module von Computern und Geräten, auf denen das Windows-Betriebssystem ausgeführt wird, sowie für Computer mit PowerShell, für die PowerShell-Remoting nicht aktiviert ist, zu erhalten.

Der **CimSession**-Parameter ruft alle Module in der **CIMSession** ab. Sie können jedoch nur CIM- und CDXML (Cmdlet Definition XML)-basierte Module importieren.

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

### -FullyQualifiedName

Gibt Module an, deren Namen in Form von **modulespecification** -Objekten angegeben sind. Weitere Informationen finden Sie im Abschnitt "Hinweise" des [modulespecification-Konstruktors (Hash Tabelle)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).

Der **fullyqualifiedmodule** -Parameter akzeptiert z. b. einen Modulnamen, der in einem der folgenden Formate angegeben ist:

- `@{ModuleName = "modulename"; ModuleVersion = "version_number"}`
- `@{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}`

**ModuleName** und **ModuleVersion** sind erforderlich, aber **Guid** ist optional. Sie können den **fullyqualifiedmodule** -Parameter nicht im selben Befehl wie einen **Modul** Parameter angeben. die beiden Parameter schließen sich gegenseitig aus.

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Listavailable

Gibt an, dass dieses Cmdlet alle installierten Module abruft. `Get-Module` Ruft Module in Pfaden ab, die in der **psmodulepath** -Umgebungsvariablen aufgelistet sind. Ohne diesen Parameter ruft `Get-Module` nur die Module ab, die in der **psmodulepath** -Umgebungsvariablen aufgelistet sind und in die aktuelle Sitzung geladen werden. **ListAvailable** gibt keine Informationen zu Modulen zurück, die in der **PSModulePath**-Umgebungsvariablen nicht gefunden wurden, selbst wenn diese Module in der aktuellen Sitzung geladen sind.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Available, PsSession, CimSession
Aliases:

Required: True (Available), False (PsSession, CimSession)
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Gibt die Namen oder Namensmuster von Modulen an, die von diesem Cmdlet abgerufen werden. Platzhalterzeichen sind zulässig. Sie können die Namen auch über die Pipeline an senden `Get-Module` . Der **FullyQualifiedName** -Parameter kann nicht im selben Befehl wie ein **namens** Parameter angegeben werden.

Der **Name** darf keine Modul-GUID als Wert annehmen.
Um Module durch Angabe einer GUID zurückzugeben, verwenden Sie stattdessen **FullyQualifiedName** .

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### -P* dition

Ruft die Module ab, die die angegebene Edition von PowerShell unterstützen.

Zulässige Werte für diesen Parameter:

- Desktop
- Core

Das Get-Module-Cmdlet überprüft die **compatiblepseditions** -Eigenschaft des **psmoduleinfo** -Objekts auf den angegebenen Wert und gibt nur die Module zurück, für die es festgelegt wurde.

> [!NOTE]
>
> - **Desktop-Edition:** Diese Edition basiert auf .NET Framework und bietet Kompatibilität mit Skripts und Modulen für Versionen von PowerShell, die unter Vollversionen von Windows wie Server Core und Windows Desktop ausgeführt werden.
> - **Core-Edition:** Diese Edition basiert auf .NET Core und bietet Kompatibilität mit Skripts und Modulen für Versionen von PowerShell, die unter funktionsreduzierten Versionen von Windows wie Nano Server und Windows IoT ausgeführt werden.

```yaml
Type: System.String
Parameter Sets: PsSession, Available
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PSSession

Ruft die Module in der angegebenen Benutzer verwalteten PowerShell-Sitzung (**PSSession**) ab. Geben Sie eine Variable ein, die die Sitzung enthält, einen Befehl, der die Sitzung abruft, z. b. einen- `Get-PSSession` Befehl oder einen Befehl, der die Sitzung erstellt, z. b. einen- `New-PSSession` Befehl.

Wenn die Sitzung mit einem Remote Computer verbunden ist, müssen Sie den **listavailable** -Parameter angeben.

Ein `Get-Module` Befehl, der den **PSSession** -Parameter verwendet, entspricht der Verwendung des- `Invoke-Command` Cmdlets zum Ausführen eines `Get-Module -ListAvailable` Befehls in einer **PSSession**.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.Automation.Runspaces.PSSession
Parameter Sets: PsSession
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Aktualisieren

Gibt an, dass dieses Cmdlet den Cache der installierten Befehle aktualisiert. Der Befehlscache wird beim Starten der Sitzung erstellt. Sie ermöglicht es dem `Get-Command` Cmdlet, Befehle aus Modulen zu erhalten, die nicht in die Sitzung importiert werden.

Dieser Parameter ist für Entwicklungs- und Testszenarien vorgesehen, in denen der Inhalt von Modulen sich seit dem Start der Sitzung geändert hat.

Wenn Sie den **Refresh** -Parameter in einem Befehl angeben, müssen Sie **listavailable** angeben.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Available, PsSession, CimSession
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System.String

Sie können Modulnamen an dieses Cmdlet weiterreichen.

## AUSGABEN

### System. Management. Automation. psmoduleinfo

Dieses Cmdlet gibt Objekte zurück, die Module darstellen.
Wenn Sie den **listavailable** -Parameter angeben, `Get-Module` gibt ein **moduleinfogruppierung** -Objekt zurück, bei dem es sich um den Typ des **psmoduleinfo** -Objekts handelt, das über die gleichen Eigenschaften und Methoden verfügt.

## HINWEISE

- Ab Windows PowerShell 3,0 werden die in PowerShell enthaltenen Hauptbefehle in Module gepackt. Die Ausnahme ist " **Microsoft. PowerShell. Core**", bei der es sich um ein Snap-in (**PSSnapIn**) handelt. Standardmäßig wird nur das **Microsoft.PowerShell.Core**-Snap-In der Sitzung hinzugefügt. Module werden bei der ersten Verwendung automatisch importiert, und Sie können das `Import-Module` Cmdlet verwenden, um Sie zu importieren.

- In Windows PowerShell 2,0 und in Host Programmen, die in neueren Versionen von PowerShell ältere Sitzungen erstellen, werden die Hauptbefehle in Snap-Ins (**pssnapins**) gepackt. Die Ausnahme ist **Microsoft. PowerShell. Core**, bei der es sich immer um ein Snap-in handelt. Remote Sitzungen, wie z. b. die vom `New-PSSession` Cmdlet gestarteten, sind auch ältere Sitzungen, die Core-Snap-Ins enthalten.

  Weitere Informationen über die **CreateDefault2** -Methode, die Sitzungen im neueren Stil mit Kernmodulen erstellt, finden Sie unter [CreateDefault2-Methode](/dotnet/api/system.management.automation.runspaces.initialsessionstate.createdefault2).

- `Get-Module` Ruft nur Module an Speicherorten ab, die im Wert der **psmodulepath** -Umgebungsvariablen gespeichert sind ($env:P smodulepath). Das `Import-Module` Cmdlet kann Module an anderen Speicherorten importieren, aber Sie können das `Get-Module` Cmdlet nicht verwenden, um Sie zu erhalten.

- Außerdem wurden ab PowerShell 3,0 neue Eigenschaften zum Objekt hinzugefügt, das zurückgibt, die das `Get-Module` Erlernen von Modulen vor dem Importieren vereinfachen. Alle Eigenschaften werden vor dem Importieren aufgefüllt. Hierzu gehören die **exportedcommands**-, **exportedcmdlets** -und **exportedfunctions** -Eigenschaften, die die Befehle auflisten, die das Modul exportiert.

- Der **listavailable** -Parameter ruft nur wohlgeformte Module ab, d. h. Ordner, die mindestens eine Datei enthalten, deren Basisname mit dem Namen des Modul Ordners identisch ist. Der Basisname ist der Name ohne die Dateinamenerweiterung. Ordner, die Dateien mit unterschiedlichen Namen enthalten, gelten als Container, jedoch nicht als Module.

  Zum erhalten von Modulen, die als DLL-Dateien implementiert sind, aber nicht in einem Modul Ordner enthalten sind, geben Sie sowohl den **listavailable** -Parameter als auch **alle** -Parameter an.

- Um die CIM-Sitzung zu verwenden, müssen auf dem Remotecomputer WS-Management-Remoting und Windows-Verwaltungsinstrumentation (WMI) verfügbar sein, wobei es sich um die Microsoft-Implementierung des Common Information Model (CIM)-Standards handelt. Auf dem Computer muss außerdem der WMI-Anbieter für die Modulerkennung oder ein alternativer WMI-Anbieter vorhanden sein, der die gleichen grundlegenden Funktionen bietet.

  Sie können die CIM-Sitzungs Funktion auf Computern verwenden, auf denen das Windows-Betriebssystem nicht ausgeführt wird, sowie auf Windows-Computern, auf denen PowerShell ausgeführt wird, für die PowerShell-Remoting jedoch nicht aktiviert ist.

  Sie können auch die CIM-Parameter verwenden, um CIM-Module von Computern zu erhalten, auf denen PowerShell-Remoting aktiviert ist. Dies schließt den lokalen Computer ein. Wenn Sie eine CIM-Sitzung auf dem lokalen Computer erstellen, verwendet PowerShell DCOM anstelle von WMI, um die Sitzung zu erstellen.

## VERWANDTE LINKS

[Get-CimSession](../CimCmdlets/Get-CimSession.md)

[New-CimSession](../CimCmdlets/New-CimSession.md)

[about_Modules](About/about_Modules.md)

[Get-PSSession](Get-PSSession.md)

[Import-Module](Import-Module.md)

[Import-PSSession](../Microsoft.PowerShell.Utility/Import-PSSession.md)

[New-PSSession](New-PSSession.md)

[Remove-Module](Remove-Module.md)
