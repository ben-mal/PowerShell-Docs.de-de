---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/24/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/new-pssessionconfigurationfile?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSSessionConfigurationFile
ms.openlocfilehash: a41c52bf163aa0a73b54e75b5192389a14da82bb
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599433"
---
# New-PSSessionConfigurationFile

## ZUSAMMENFASSUNG
Erstellt eine Datei, die eine Sitzungskonfiguration definiert.

## SYNTAX

```
New-PSSessionConfigurationFile [-Path] <String> [-SchemaVersion <Version>] [-Guid <Guid>]
 [-Author <String>] [-Description <String>] [-CompanyName <String>] [-Copyright <String>]
 [-SessionType <SessionType>] [-TranscriptDirectory <String>] [-RunAsVirtualAccount]
 [-RunAsVirtualAccountGroups <String[]>] [-MountUserDrive] [-UserDriveMaximumSize <Int64>]
 [-GroupManagedServiceAccount <String>] [-ScriptsToProcess <String[]>]
 [-RoleDefinitions <IDictionary>] [-RequiredGroups <IDictionary>] [-LanguageMode <PSLanguageMode>]
 [-ExecutionPolicy <ExecutionPolicy>] [-PowerShellVersion <Version>] [-ModulesToImport <Object[]>]
 [-VisibleAliases <String[]>] [-VisibleCmdlets <Object[]>] [-VisibleFunctions <Object[]>]
 [-VisibleExternalCommands <String[]>] [-VisibleProviders <String[]>]
 [-AliasDefinitions <IDictionary[]>] [-FunctionDefinitions <IDictionary[]>]
 [-VariableDefinitions <Object>] [-EnvironmentVariables <IDictionary>] [-TypesToProcess <String[]>]
 [-FormatsToProcess <String[]>] [-AssembliesToLoad <String[]>] [-Full] [<CommonParameters>]
```

## DESCRIPTION

Mit dem `New-PSSessionConfigurationFile` -Cmdlet wird eine Datei mit Einstellungen erstellt, mit denen eine Sitzungs Konfiguration und die Umgebung der Sitzungen definiert werden, die mit der Sitzungs Konfiguration erstellt werden.
Wenn Sie die Datei in einer Sitzungs Konfiguration verwenden möchten, verwenden Sie den **path** -Parameter der `Register-PSSessionConfiguration` `Set-PSSessionConfiguration` Cmdlets oder.

Die Sitzungs Konfigurationsdatei, die `New-PSSessionConfigurationFile` erstellt, ist eine lesbare Textdatei, die eine Hash Tabelle mit den Eigenschaften und Werten der Sitzungs Konfiguration enthält. Die Datei hat eine Datei `.pssc` Namen Erweiterung.

Alle Parameter von `New-PSSessionConfigurationFile` sind optional, mit Ausnahme des **path** -Parameters.
Wenn Sie einen Parameter weglassen, wird der entsprechende Schlüssel in der Sitzungskonfigurationsdatei auskommentiert, es sei denn, er wurde in der Parameterbeschreibung angegeben.

Eine Sitzungs Konfiguration, auch als Endpunkt bezeichnet, ist eine Sammlung von Einstellungen auf dem lokalen Computer, die die Umgebung für PowerShell-Sitzungen (**pssessions**) definieren, die eine Verbindung mit dem Computer herstellen. Alle **pssessions** verwenden eine Sitzungs Konfiguration. Verwenden Sie zum Angeben einer bestimmten Sitzungs Konfiguration den **ConfigurationName** -Parameter von Cmdlets, die eine Sitzung erstellen, z `New-PSSession` . b. das Cmdlet.

Eine session configuration file erleichtert die Definition einer Sitzungskonfiguration ohne komplexe Skripts oder Codeassemblys. Die Einstellungen in der Datei werden mit dem optionalen Startskript und allen Assemblys in der Sitzungs Konfiguration verwendet.

Weitere Informationen zu Sitzungs Konfigurationen und Sitzungs Konfigurationsdateien finden Sie unter [about_Session_Configurations](About/about_Session_Configurations.md) und [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).

Dieses Cmdlet wurde in PowerShell 3,0 eingeführt.

## BEISPIELE

### Beispiel 1: Erstellen und Verwenden einer nolanguage-Sitzung

In diesem Beispiel wird gezeigt, wie Sie die Verwendung einer Sitzungs basierten Sitzung und die Auswirkungen von erstellen können.

Dazu müssen folgende Schritte ausgeführt werden:

1. Erstellen Sie eine neue Konfigurationsdatei.
1. Registrieren Sie die Konfiguration.
1. Erstellen Sie eine neue Sitzung, in der die-Konfiguration verwendet wird.
1. Führt Befehle in dieser neuen Sitzung aus.

Um die Befehle in diesem Beispiel auszuführen, starten Sie PowerShell mit der Option als Administrator ausführen. Diese Option ist erforderlich, um das `Register-PSSessionConfiguration` Cmdlet auszuführen.

```powershell
New-PSSessionConfigurationFile -Path .\NoLanguage.pssc -LanguageMode NoLanguage
Register-PSSessionConfiguration -Path .\NoLanguage.pssc -Name NoLanguage -Force
$NoLanguageSession = New-PSSession -ComputerName Srv01 -ConfigurationName NoLanguage
Invoke-Command -Session $NoLanguageSession -ScriptBlock {
  if ((Get-Date) -lt '1January2099') {'Before'} else {'After'}
}
```

```Output
The syntax is not supported by this runspace. This might be because it is in no-language mode.
    + CategoryInfo          : ParserError: (if ((Get-Date) ...') {'Before'}  :String) [], ParseException
    + FullyQualifiedErrorId : ScriptsNotAllowed
    + PSComputerName        : localhost
```

In diesem Beispiel schlägt der `Invoke-Command` fehl, da **languagemode** auf **nolanguage** festgelegt ist.

### Beispiel 2: Erstellen und Verwenden einer restrictedlanguage-Sitzung

In diesem Beispiel wird gezeigt, wie Sie die Verwendung einer Sitzungs basierten Sitzung und die Auswirkungen von erstellen können.

Dazu müssen folgende Schritte ausgeführt werden:

1. Erstellen Sie eine neue Konfigurationsdatei.
1. Registrieren Sie die Konfiguration.
1. Erstellen Sie eine neue Sitzung, in der die-Konfiguration verwendet wird.
1. Führt Befehle in dieser neuen Sitzung aus.

Um die Befehle in diesem Beispiel auszuführen, starten Sie PowerShell mit der Option als Administrator ausführen. Diese Option ist erforderlich, um das `Register-PSSessionConfiguration` Cmdlet auszuführen.

```powershell
New-PSSessionConfigurationFile -Path .\NoLanguage.pssc -LanguageMode RestrictedLanguage
Register-PSSessionConfiguration -Path .\NoLanguage.pssc -Name RestrictedLanguage -Force
$RestrictedSession = New-PSSession -ComputerName Srv01 -ConfigurationName RestrictedLanguage
Invoke-Command -Session $RestrictedSession -ScriptBlock {
  if ((Get-Date) -lt '1January2099') {'Before'} else {'After'}
}
```

```Output
Before
```

In diesem Beispiel `Invoke-Command` ist erfolgreich, da **languagemode** auf **restrictedlanguage** festgelegt ist.

### Beispiel 3: Ändern einer Sitzungs Konfigurationsdatei

Dieses Beispiel zeigt, wie Sie die Sitzungs Konfigurationsdatei ändern können, die in einer vorhandenen Sitzung namens "ittasks" verwendet wird. Bisher verfügten diese Sitzungen nur über die Kernmodule und über ein internes **ittasks** -Modul. Der Administrator möchte das **psscheduledjob** -Modul zu Sitzungen hinzufügen, die mit der ittasks-Sitzungs Konfiguration erstellt wurden.

```powershell
New-PSSessionConfigurationFile -Path .\New-ITTasks.pssc -ModulesToImport Microsoft*, ITTasks, PSScheduledJob
Set-PSSessionConfiguration -Name ITTasks -Path .\New-ITTasks.pssc
```

Mit dem- `New-PSSessionConfigurationFile` Cmdlet können Sie eine Sitzungs Konfigurationsdatei erstellen, mit der die erforderlichen Module importiert werden. Mit dem- `Set-PSSessionConfiguration` Cmdlet wird die aktuelle Konfigurationsdatei durch die neue ersetzt. Diese neue Konfiguration wirkt sich nur auf neue Sitzungen aus, die nach der Änderung erstellt wurden.
Vorhandene ittasks-Sitzungen sind nicht betroffen.

### Beispiel 4: Bearbeiten einer Sitzungs Konfigurationsdatei

In diesem Beispiel wird veranschaulicht, wie Sie eine Sitzungskonfiguration durch Bearbeiten der aktiven Sitzungskonfigurationskopie der Konfigurationsdatei ändern können. Um die Sitzungs Konfigurationskopie der Konfigurationsdatei zu ändern, müssen Sie über Vollzugriff auf die Datei verfügen. Dies erfordert möglicherweise das Ändern der Berechtigungen für die Datei.

In diesem Szenario möchten wir einen neuen Alias für das `Select-String` Cmdlet hinzufügen, indem wir die aktive Konfigurationsdatei bearbeiten.

Der folgende Beispielcode führt die folgenden Schritte aus, um diese Änderung vorzunehmen:

1. Den Pfad der Konfigurationsdatei für die ITconfig-Sitzung erhalten.
1. Der Benutzer bearbeitet die Konfigurationsdatei mit **Notepad.exe** , um den **aliasdefinitions** -Wert wie folgt zu ändern: `AliasDefinitions = @(@{Name='slst';Value='Select-String'})` .
1. Testen Sie die aktualisierte Konfigurationsdatei.

```powershell
$ITConfig = Get-PSSessionConfiguration -Name ITConfig
notepad.exe $ITConfig.ConfigFilePath
Test-PSSessionConfigurationFile -Path $ITConfig.ConfigFilePath
```

```Output
True
```

Verwenden Sie den **verbose** -Parameter mit `Test-PSSessionConfigurationFile` , um alle erkannten Fehler anzuzeigen. Das-Cmdlet gibt zurück, `$True` Wenn keine Fehler in der Datei erkannt werden.

### Beispiel 5: Erstellen einer Beispielkonfigurationsdatei

Dieses Beispiel zeigt einen `New-PSSessionConfigurationFile` Befehl, der alle Cmdlet-Parameter verwendet.
Er wurde angegeben, um das richtige Eingabeformat für jeden Parameter zu zeigen.

Die resultierende SampleFile.pssc wird in der Ausgabe angezeigt.

```powershell
$configSettings = @{
    Path = '.\SampleFile.pssc'
    SchemaVersion = '1.0.0.0'
    Author = 'User01'
    Copyright = '(c) Fabrikam Corporation. All rights reserved.'
    CompanyName = 'Fabrikam Corporation'
    Description = 'This is a sample file.'
    ExecutionPolicy = 'AllSigned'
    PowerShellVersion = '3.0'
    LanguageMode = 'FullLanguage'
    SessionType = 'Default'
    EnvironmentVariables = @{TESTSHARE='\\Test2\Test'}
    ModulesToImport = @{ModuleName='PSScheduledJob'; ModuleVersion='1.0.0.0'; GUID='50cdb55f-5ab7-489f-9e94-4ec21ff51e59'},'PSDiagnostics'
    AssembliesToLoad = 'System.Web.Services','FSharp.Compiler.CodeDom.dll'
    TypesToProcess = 'Types1.ps1xml','Types2.ps1xml'
    FormatsToProcess = 'CustomFormats.ps1xml'
    ScriptsToProcess = 'Get-Inputs.ps1'
    AliasDefinitions = @{Name='hlp';Value='Get-Help';Description='Gets help.';Options='AllScope'},
        @{Name='Update';Value='Update-Help';Description='Updates help';Options='ReadOnly'}
    FunctionDefinitions = @{Name='Get-Function';ScriptBlock={Get-Command -CommandType Function};Options='ReadOnly'}
    VariableDefinitions = @{Name='WarningPreference';Value='SilentlyContinue'}
    VisibleAliases = 'c*','g*','i*','s*'
    VisibleCmdlets = 'Get*'
    VisibleFunctions = 'Get*'
    VisibleProviders = 'FileSystem','Function','Variable'
    RunAsVirtualAccount = $true
    RunAsVirtualAccountGroups = 'Backup Operators'
}
New-PSSessionConfigurationFile @configSettings
Get-Content SampleFile.pssc
```

```Output
@{

# Version number of the schema used for this document
SchemaVersion = '1.0.0.0'

# ID used to uniquely identify this document
GUID = '1caeff7f-27ca-4360-97cf-37846f594235'

# Author of this document
Author = 'User01'

# Description of the functionality provided by these settings
Description = 'This is a sample file.'

# Company associated with this document
CompanyName = 'Fabrikam Corporation'

# Copyright statement for this document
Copyright = '(c) Fabrikam Corporation. All rights reserved.'

# Session type defaults to apply for this session configuration. Can be 'RestrictedRemoteServer' (recommended), 'Empty', or 'Default'
SessionType = 'Default'

# Directory to place session transcripts for this session configuration
# TranscriptDirectory = 'C:\Transcripts\'

# Whether to run this session configuration as the machine's (virtual) administrator account
RunAsVirtualAccount = $true

# Groups associated with machine's (virtual) administrator account
RunAsVirtualAccountGroups = 'Backup Operators'

# Scripts to run when applied to a session
ScriptsToProcess = 'Get-Inputs.ps1'

# User roles (security groups), and the role capabilities that should be applied to them when applied to a session
# RoleDefinitions = @{ 'CONTOSO\SqlAdmins' = @{ RoleCapabilities = 'SqlAdministration' }; 'CONTOSO\SqlManaged' = @{ RoleCapabilityFiles = 'C:\RoleCapability\SqlManaged.psrc' }; 'CONTOSO\ServerMonitors' = @{ VisibleCmdlets = 'Get-Process' } }

# Language mode to apply when applied to a session. Can be 'NoLanguage' (recommended), 'RestrictedLanguage', 'ConstrainedLanguage', or 'FullLanguage'
LanguageMode = 'FullLanguage'

# Execution policy to apply when applied to a session
ExecutionPolicy = 'AllSigned'

# Version of the PowerShell engine to use when applied to a session
PowerShellVersion = '3.0'

# Modules to import when applied to a session
ModulesToImport = @{
    'GUID' = '50cdb55f-5ab7-489f-9e94-4ec21ff51e59'
    'ModuleName' = 'PSScheduledJob'
    'ModuleVersion' = '1.0.0.0' }, 'PSDiagnostics'

# Aliases to make visible when applied to a session
VisibleAliases = 'c*', 'g*', 'i*', 's*'

# Cmdlets to make visible when applied to a session
VisibleCmdlets = 'Get*'

# Functions to make visible when applied to a session
VisibleFunctions = 'Get*'

# Providers to make visible when applied to a session
VisibleProviders = 'FileSystem', 'Function', 'Variable'

# Aliases to be defined when applied to a session
AliasDefinitions = @{
    'Description' = 'Gets help.'
    'Name' = 'hlp'
    'Options' = 'AllScope'
    'Value' = 'Get-Help' }, @{
    'Description' = 'Updates help'
    'Name' = 'Update'
    'Options' = 'ReadOnly'
    'Value' = 'Update-Help' }

# Functions to define when applied to a session
FunctionDefinitions = @{
    'Name' = 'Get-Function'
    'Options' = 'ReadOnly'
    'ScriptBlock' = {Get-Command -CommandType Function} }

# Variables to define when applied to a session
VariableDefinitions = @{
    'Name' = 'WarningPreference'
    'Value' = 'SilentlyContinue' }

# Environment variables to define when applied to a session
EnvironmentVariables = @{
    'TESTSHARE' = '\\Test2\Test' }

# Type files (.ps1xml) to load when applied to a session
TypesToProcess = 'Types1.ps1xml', 'Types2.ps1xml'

# Format files (.ps1xml) to load when applied to a session
FormatsToProcess = 'CustomFormats.ps1xml'

# Assemblies to load when applied to a session
AssembliesToLoad = 'System.Web.Services', 'FSharp.Compiler.CodeDom.dll'

}
```

## PARAMETERS

### -Aliasdefinitionen

Fügt die angegebenen Aliase zu Sitzungen hinzu, die die Sitzungskonfiguration verwenden. Geben Sie eine Hashtabelle mit den folgenden Schlüsseln ein:

- Name: Name des Alias. Dieser Schlüssel ist erforderlich.
- Value: der Befehl, den der Alias darstellt. Dieser Schlüssel ist erforderlich.
- Description: eine Text Zeichenfolge, die den Alias beschreibt. Dieser Schlüssel ist optional.
- Optionen: Alias Optionen. Dieser Schlüssel ist optional. Der Standardwert ist " **None**". Die zulässigen Werte für diesen Parameter lauten: None, Read Only, Constant, private oder allscope.

Beispiel: `@{Name='hlp';Value='Get-Help';Description='Gets help';Options='ReadOnly'}`

```yaml
Type: System.Collections.IDictionary[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Assemliestoload

Gibt die Assemblys an, die in die Sitzungen geladen werden sollen und die die Sitzungskonfiguration verwenden.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Autor

Gibt den Autor der Sitzungs Konfiguration oder der Konfigurationsdatei an. Der Standardwert ist der aktuelle Benutzer. Der Wert dieses Parameters wird in der Sitzungskonfigurationsdatei angezeigt, aber es handelt sich nicht um eine Eigenschaft des Sitzungskonfigurationsobjekts.

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

### -CompanyName

Gibt das Unternehmen an, das die Sitzungs Konfiguration oder die Konfigurationsdatei erstellt hat. Der Standardwert ist **Unknown** (Unbekannt). Der Wert dieses Parameters wird in der Sitzungskonfigurationsdatei angezeigt, aber es handelt sich nicht um eine Eigenschaft des Sitzungskonfigurationsobjekts.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Unknown
Accept pipeline input: False
Accept wildcard characters: False
```

### -Copyright

Gibt ein Copyright der Sitzungs Konfigurationsdatei an. Der Wert dieses Parameters wird in der Sitzungskonfigurationsdatei angezeigt, aber es handelt sich nicht um eine Eigenschaft des Sitzungskonfigurationsobjekts.

Wenn Sie diesen Parameter weglassen, `New-PSSessionConfigurationFile` generiert eine Copyright Anweisung mit dem Wert des **Author** -Parameters.

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

### -Description

Gibt eine Beschreibung der Sitzungs Konfiguration oder der Sitzungs Konfigurationsdatei an. Der Wert dieses Parameters wird in der Sitzungskonfigurationsdatei angezeigt, aber es handelt sich nicht um eine Eigenschaft des Sitzungskonfigurationsobjekts.

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

### -Umgebungsvariablen

Fügt der Sitzung Umgebungsvariablen hinzu. Geben Sie eine Hashtabelle ein, in der die Schlüssel die Namen der Umgebungsvariablen und die Werte die Werte der Umgebungsvariablen sind.

Beispiel: `EnvironmentVariables=@{TestShare='\\Server01\TestShare'}`

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExecutionPolicy

Bestimmt die Ausführungsrichtlinie von Sitzungen, die die Sitzungskonfiguration verwenden. Wenn Sie diesen Parameter weglassen, ist der Wert des **ExecutionPolicy** -Schlüssels in der Sitzungs Konfigurationsdatei **eingeschränkt**. Informationen zu Ausführungsrichtlinien in PowerShell finden Sie unter [about_Execution_Policies](about/about_Execution_Policies.md).

```yaml
Type: Microsoft.PowerShell.ExecutionPolicy
Parameter Sets: (All)
Aliases:
Accepted values: Unrestricted, RemoteSigned, AllSigned, Restricted, Default, Bypass, Undefined

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Formatstoprocess

Gibt die Formatierungsdateien (.ps1xml) an, die in Sitzungen ausgeführt werden, die die Sitzungskonfiguration verwenden.
Der Wert dieses Parameters muss ein vollständiger oder absoluter Pfad der Formatierungs Dateien sein.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Full

Gibt an, dass dieser Vorgang alle möglichen Konfigurations Eigenschaften in der Sitzungs Konfigurationsdatei enthält.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Functiondefinitions

Fügt Sitzungen, die die Sitzungskonfiguration verwenden, die angegebenen Funktionen hinzu. Geben Sie eine Hashtabelle mit den folgenden Schlüsseln ein:

- Name: der Name der Funktion. Dieser Schlüssel ist erforderlich.
- ScriptBlock-Funktions Text. Geben Sie einen Skriptblock ein. Dieser Schlüssel ist erforderlich.
- Optionen: Funktions Optionen. Dieser Schlüssel ist optional. Der Standardwert ist " **None**". Die zulässigen Werte für diesen Parameter lauten: None, Read Only, Constant, private oder allscope.

Beispiel: `@{Name='Get-PowerShellProcess';ScriptBlock={Get-Process PowerShell};Options='AllScope'}`

```yaml
Type: System.Collections.IDictionary[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Groupmanagedserviceaccount

Konfiguriert Sitzungen, die diese Sitzungs Konfiguration verwenden, um im Kontext des angegebenen Gruppen verwalteten Dienst Kontos ausgeführt zu werden. Der Computer, auf dem diese Sitzungs Konfiguration registriert ist, muss über die Berechtigung zum Anfordern des GMSA-Kennworts verfügen, damit Sitzungen erfolgreich erstellt werden können. Dieses Feld kann nicht mit dem Parameter " **runasvirtualaccount** " verwendet werden.

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

### -GUID

Gibt einen eindeutigen Bezeichner für die Sitzungskonfigurationsdatei an. Wenn Sie diesen Parameter weglassen, `New-PSSessionConfigurationFile` generiert eine GUID für die Datei. Geben Sie ein, um eine neue GUID in PowerShell zu erstellen `New-Guid` .

```yaml
Type: System.Guid
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Languagemode

Bestimmt, welche Elemente der PowerShell-Sprache in Sitzungen zulässig sind, die diese Sitzungs Konfiguration verwenden. Sie können diesen Parameter verwenden, um die Befehle einzuschränken, die bestimmte Benutzer auf dem Computer ausführen können.

Zulässige Werte für diesen Parameter:

- Fulllanguage: alle Sprachelemente sind zulässig.
- "Einschräninedlanguage": Befehle, die auszuwertende Skripts enthalten, sind nicht zulässig. Der ConstrainedLanguage-Modus schränkt den Benutzerzugriff auf Microsoft .NET Framework-Typen, -Objekte oder -Methoden ein.
- Nolanguage: Benutzer können Cmdlets und Funktionen ausführen, dürfen jedoch keine Sprachelemente verwenden, wie z. b. Skriptblöcke, Variablen oder Operatoren.
- Restrictedlanguage: Benutzer können Cmdlets und Funktionen ausführen, dürfen jedoch keine Skriptblöcke oder Variablen verwenden, mit Ausnahme der folgenden zulässigen Variablen: `$PSCulture` , `$PSUICulture` , `$True` , `$False` und `$Null` . Benutzer dürfen nur die grundlegenden Vergleichs Operatoren ( `-eq` , `-gt` ,) verwenden `-lt` . Zuweisungsanweisungen, Eigenschaftsverweise und Methodenaufrufe sind nicht zulässig.

Der Standardwert des **LanguageMode**-Parameters hängt vom Wert des **SessionType**-Parameters ab.

- Empty-nolanguage
- Restrictedremuteserver-nolanguage
- Standard-fulllanguage

```yaml
Type: System.Management.Automation.PSLanguageMode
Parameter Sets: (All)
Aliases:
Accepted values: FullLanguage, RestrictedLanguage, NoLanguage, ConstrainedLanguage

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Modulestoimport

Gibt die Module und Snap-ins an, die automatisch in Sitzungen importiert werden, die die Sitzungskonfiguration verwenden.

Standardmäßig wird nur das **Microsoft. PowerShell. Core** -Snap-in in Remote Sitzungen importiert, aber wenn die Cmdlets nicht ausgeschlossen sind, können Benutzer die `Import-Module` -und `Add-PSSnapin` -Cmdlets verwenden, um der Sitzung Module und Snap-Ins hinzuzufügen.

Jedes Modul oder Snap-In im Wert dieses Parameters kann durch eine Zeichenfolge oder als Hashtabelle dargestellt werden. Eine Modul Zeichenfolge besteht nur aus dem Namen des Moduls oder Snap-Ins. Eine Modul Hash Tabelle kann die Schlüssel " **ModuleName**", " **moduleversion**" und " **GUID** " enthalten. Nur der **ModuleName**-Schlüssel ist erforderlich.

Beispielsweise besteht der folgende Wert aus einer Zeichenfolge und einer Hashtabelle. Jede Kombination aus Zeichenfolgen und Hashtabellen, in beliebiger Reihenfolge, ist gültig.

`'TroubleshootingPack', @{ModuleName='PSDiagnostics'; ModuleVersion='1.0.0.0';GUID='c61d6278-02a3-4618-ae37-a524d40a7f44'}`

Der Wert des **modulestoimport** -Parameters des `Register-PSSessionConfiguration` Cmdlets hat Vorrang vor dem Wert des **modulestoimport** -Schlüssels in der Sitzungs Konfigurationsdatei.

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Mountuserdrive

Konfiguriert Sitzungen, die diese Sitzungs Konfiguration verwenden, um das `User:` PSDrive verfügbar zu machen. Benutzer Laufwerke sind für jeden Benutzer, der eine Verbindung herstellt, eindeutig und ermöglichen Benutzern das Kopieren von Daten in und von PowerShell-Endpunkten, auch wenn der Datei System Anbieter nicht verfügbar gemacht wird. Benutzer Laufwerk Stämme werden unter erstellt `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell\DriveRoots\` . Für jeden Benutzer, der eine Verbindung zum Endpunkt herstellt, wird ein Ordner mit dem Namen `$env:USERDOMAIN_$env:USERNAME` erstellt.

Der Inhalt des Benutzer Laufwerks wird über Benutzersitzungen hinweg beibehalten und nicht automatisch entfernt. Standardmäßig können Benutzer nur bis zu 50 MB Daten auf dem Benutzer Laufwerk speichern. Dies kann mit dem **userdrivemaximumsize** -Parameter angepasst werden.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Gibt den Pfad und den Dateinamen der Sitzungs Konfigurationsdatei an. Die Datei muss eine `.pssc` Dateinamenerweiterung aufweisen.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PowerShellVersion

Gibt die Version der PowerShell-Engine in Sitzungen an, die die Sitzungs Konfiguration verwenden. Die zulässigen Werte für diesen Parameter sind: 2,0 und 3,0. Wenn Sie diesen Parameter weglassen, wird der **PowerShellVersion** -Schlüssel auskommentiert, und die neueste Version von PowerShell wird in der Sitzung ausgeführt.

Der Wert des **psversion** -Parameters des `Register-PSSessionConfiguration` Cmdlets hat Vorrang vor dem Wert des **PowerShellVersion** -Schlüssels in der Sitzungs Konfigurationsdatei.

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Requirements dgroups

Gibt bedingte Zugriffsregeln für Benutzer an, die eine Verbindung mit Sitzungen herstellen, die diese Sitzungs Konfiguration verwenden.

Geben Sie eine Hash Tabelle ein, um die Liste der Regeln mithilfe von nur 1 Schlüssel pro Hash Tabelle, ' and ' oder ' or ', zu verfassen, und legen Sie den Wert auf ein Array von Sicherheitsgruppen Namen oder zusätzlichen Hash Tabellen fest.

Beispiel für das Herstellen einer Verbindung von Benutzern mit Mitgliedern einer einzelnen Gruppe: `@{ And = 'MyRequiredGroup' }`

Beispiel für den Zugriff auf den Endpunkt durch Benutzer, die der Gruppe a oder beiden Gruppen B und C angehören müssen: `@{ Or = 'GroupA', @{ And = 'GroupB', 'GroupC' } }`

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Roledefinitions

Gibt die Zuordnung zwischen Sicherheitsgruppen (oder Benutzern) und Rollen Funktionen an. Benutzer erhalten Zugriff auf alle Rollen Funktionen, die für ihre Gruppenmitgliedschaft zum Zeitpunkt der Erstellung der Sitzung gelten.

Geben Sie eine Hash Tabelle ein, in der die Schlüssel der Name der Sicherheitsgruppe sind, und die Werte sind Hash Tabellen, die eine Liste der Rollen Funktionen enthalten, die der Sicherheitsgruppe zur Verfügung gestellt werden sollen.

Beispiel: `@{'Contoso\Level 2 Helpdesk Users' = @{ RoleCapabilities = 'Maintenance', 'ADHelpDesk' }}`

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Runasvirtualaccount

Konfiguriert Sitzungen, die diese Sitzungs Konfiguration verwenden, damit Sie als (virtuelles) Administrator Konto des Computers ausgeführt wird. Dieses Feld kann nicht mit dem **groupmanagedserviceaccount** -Parameter verwendet werden.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Runasvirtualaccountgroups

Gibt die Sicherheitsgruppen an, die dem virtuellen Konto zugeordnet werden sollen, wenn eine Sitzung, die die Sitzungs Konfiguration verwendet, als virtuelles Konto ausgeführt wird. Wenn die Angabe weggelassen wird, gehört das virtuelle Konto Domänen Administratoren auf Domänen Controllern und Administratoren auf allen anderen Computern an.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Schemaversion

Gibt die Version des Sitzungskonfigurationsdateischemas an. Der Standardwert ist „1.0.0.0“.

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scriptstoprocess

Fügt den Sitzungen, die die Sitzungskonfiguration verwenden, die angegebenen Skripts hinzu. Geben Sie den Pfad und die Dateinamen der Skripts ein. Der Wert dieses Parameters muss ein vollständiger oder absoluter Pfad von Skript Dateinamen sein.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SessionType

Gibt den Typ der Sitzung an, die mit der Sitzungskonfiguration erstellt wird. Der Standardwert ist Default. Zulässige Werte für diesen Parameter:

- Leer: der Sitzung werden standardmäßig keine Module hinzugefügt. Verwenden Sie die Parameter dieses Cmdlets, um der Sitzung Module, Funktionen, Skripts und andere Funktionen hinzuzufügen. Mit dieser Option können Sie benutzerdefinierte Sitzungen erstellen, indem Sie ausgewählte Befehle hinzufügen. Wenn Sie einer leeren Sitzung keine Befehle hinzufügen, ist die Sitzung auf Ausdrücke beschränkt und kann womöglich nicht verwendet werden.
- Standard: Fügt der Sitzung das Microsoft. PowerShell. Core-Modul hinzu. Dieses Modul enthält das `Import-Module` Cmdlet, mit dem Benutzer andere Module importieren können, sofern Sie dieses Cmdlet nicht explizit verbieten.
- RestrictedRemoteServer. Schließt nur die folgenden Proxy Funktionen ein: `Exit-PSSession` , `Get-Command` , `Get-FormatData` , `Get-Help` , `Measure-Object` , `Out-Default` und `Select-Object` .
  Verwenden Sie die Parameter dieses Cmdlets, um der Sitzung Module, Funktionen, Skripts und andere Funktionen hinzuzufügen.

```yaml
Type: System.Management.Automation.Remoting.SessionType
Parameter Sets: (All)
Aliases:
Accepted values: Empty, RestrictedRemoteServer, Default

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Transcriptdirectory

Gibt das Verzeichnis an, in dem Sitzungsprotokolle für Sitzungen mit dieser Sitzungs Konfiguration platziert werden.

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

### -Typestoprocess

Fügt den `.ps1xml` Sitzungen, die die Sitzungs Konfiguration verwenden, die angegebenen Typdateien hinzu. Geben Sie die typdateinamen ein. Der Wert dieses Parameters muss ein vollständiger oder absoluter Pfad zu den typdateinamen sein.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Userdrivemaximumsize

Gibt die maximale Größe für Benutzer Laufwerke an, die in Sitzungen verfügbar gemacht werden, die diese Sitzungs Konfiguration verwenden.
Wenn der Wert weggelassen wird, beträgt die Standardgröße der einzelnen `User:` Laufwerk Stamm 50 MB.

Dieser Parameter sollte mit **mountuserdrive** verwendet werden.

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Variabledefinitionen

Fügt den Sitzungen, die die Sitzungskonfiguration verwenden, die angegebenen Variablen hinzu. Geben Sie eine Hashtabelle mit den folgenden Schlüsseln ein:

- Name: der Name der Variablen. Dieser Schlüssel ist erforderlich.
- Wert-Variablen Wert. Dieser Schlüssel ist erforderlich.
- Optionen: Variablen Optionen. Dieser Schlüssel ist optional. Der Standardwert ist " **None**". Die zulässigen Werte für diesen Parameter lauten: None, Read Only, Constant, private oder allscope.

Beispiel: `@{Name='WarningPreference';Value='SilentlyContinue';Options='AllScope'}`

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Visiblealiases

Beschränkt die Aliase in der Sitzung auf jene, die im Wert dieses Parameters angegeben wurden, sowie auf alle Aliase, die Sie im **AliasDefinition**-Parameter definieren. Platzhalterzeichen werden unterstützt. Standardmäßig sind alle Aliase, die von der PowerShell-Engine definiert werden, und alle Aliase, die von Modulen exportiert werden, in der Sitzung sichtbar.

Beispiel: `VisibleAliases='gcm', 'gp'`

Wenn ein beliebiger **sichtbarer** Parameter in der Sitzungs Konfigurationsdatei enthalten ist, entfernt PowerShell das `Import-Module` Cmdlet und den zugehörigen ipmo-Alias aus der Sitzung.

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

### -Visiblecmdlets

Beschränkt die Cmdlets in der Sitzung auf jene, die im Wert dieses Parameters angegeben wurden. Platzhalter Zeichen und qualifizierte Modulnamen werden unterstützt.

Standardmäßig sind alle Cmdlets, die von Modulen in der Sitzung exportiert werden, in der Sitzung sichtbar. Verwenden Sie die **SessionType**- und **ModulesToImport**-Parameter, um zu bestimmen, welche Module und Snap-Ins in die Sitzung importiert werden. Wenn das Cmdlet in **modulestoimport** nicht verfügbar ist, versucht das entsprechende Modul, das Cmdlet zu veröffentlichen.

Wenn ein beliebiger **sichtbarer** Parameter in der Sitzungs Konfigurationsdatei enthalten ist, entfernt PowerShell das `Import-Module` Cmdlet und den zugehörigen ipmo-Alias aus der Sitzung.

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Visibleexternalcommands

Schränkt die externen Binärdateien, Skripts und Befehle, die in der Sitzung ausgeführt werden können, auf die Werte ein, die im Wert dieses Parameters angegeben werden. Platzhalterzeichen werden unterstützt.

Standardmäßig sind keine externen Befehle in der Sitzung sichtbar.

Wenn ein beliebiger **sichtbarer** Parameter in der Sitzungs Konfigurationsdatei enthalten ist, entfernt PowerShell das `Import-Module` Cmdlet und den zugehörigen ipmo-Alias aus der Sitzung.

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

### -Visiblefunctions

Beschränkt die Funktionen in der Sitzung auf jene, die im Wert dieses Parameters angegeben wurden, sowie auf alle Funktionen, die Sie im **FunctionDefinition**-Parameter definieren. Platzhalterzeichen werden unterstützt.

Standardmäßig sind alle Funktionen, die von Modulen in der Sitzung exportiert werden, in der Sitzung sichtbar. Verwenden Sie die **SessionType**- und **ModulesToImport**-Parameter, um zu bestimmen, welche Module und Snap-Ins in die Sitzung importiert werden.

Wenn ein beliebiger **sichtbarer** Parameter in der Sitzungs Konfigurationsdatei enthalten ist, entfernt PowerShell das `Import-Module` Cmdlet und den zugehörigen ipmo-Alias aus der Sitzung.

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Visibleproviders

Schränkt die PowerShell-Anbieter in der Sitzung auf die Werte ein, die im Wert dieses Parameters angegeben sind.
Platzhalterzeichen werden unterstützt.

Standardmäßig sind alle Anbieter, die von Modulen in der Sitzung exportiert werden, in der Sitzung sichtbar. Verwenden Sie die Parameter **SessionType** und **modulestoimport** , um zu bestimmen, welche Module in die Sitzung importiert werden.

Wenn ein beliebiger **sichtbarer** Parameter in der Sitzungs Konfigurationsdatei enthalten ist, entfernt PowerShell das `Import-Module` Cmdlet und den zugehörigen `ipmo` Alias aus der Sitzung.

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

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine

Sie können keine Objekte über die Pipeline an dieses Cmdlet übergeben.

## AUSGABEN

### Keine

Dieses Cmdlet generiert keine Ausgabe.

## HINWEISE

Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.

- Parameter, wie z. **b. visiblecmdlets** und **visibleproviders**, importieren keine Elemente in die Sitzung. Stattdessen treffen sie ihre Auswahl unter den Elementen, die in die Sitzung importiert wurden. Wenn z. b. der Wert des **visibleproviders** -Parameters der Zertifikat Anbieter ist, der **modulestoimport** -Parameter jedoch nicht das **Microsoft. PowerShell. Security** -Modul angibt, das den Zertifikat Anbieter enthält, ist der Zertifikat Anbieter in der Sitzung nicht sichtbar.
- `New-PSSessionConfigurationFile` erstellt eine Sitzungs Konfigurationsdatei mit der Dateinamenerweiterung. PSSC in dem Pfad, den Sie im **path** -Parameter angeben. Wenn Sie die Sitzungs Konfigurationsdatei verwenden, um eine Sitzungs Konfiguration zu erstellen, `Register-PSSessionConfiguration` kopiert das Cmdlet die Konfigurationsdatei und speichert eine aktive Kopie der Datei im Unterverzeichnis **sessionconfig** des `$PSHOME` Verzeichnisses.

  Die **configfilepath** -Eigenschaft der Sitzungs Konfiguration enthält den voll qualifizierten Pfad der aktiven Sitzungs Konfigurationsdatei. Sie können die aktive Konfigurationsdatei im Verzeichnis jederzeit `$PSHOME` mithilfe eines beliebigen Text-Editors ändern. Die Änderungen, die Sie vornehmen, betreffen alle neuen Sitzungen, die diese Sitzungskonfiguration verwenden, aber nicht bereits vorhandene Sitzungen.

  Vor der Verwendung einer bearbeiteten Sitzungs Konfigurationsdatei können `Test-PSSessionConfigurationFile` Sie mit dem Cmdlet überprüfen, ob die Einträge in der Konfigurationsdatei gültig sind.

## VERWANDTE LINKS

[Disable-PSSessionConfiguration](Disable-PSSessionConfiguration.md)

[Enable-PSSessionConfiguration](Enable-PSSessionConfiguration.md)

[Get-PSSessionConfiguration](Get-PSSessionConfiguration.md)

[Register-PSSessionConfiguration](Register-PSSessionConfiguration.md)

[Set-PSSessionConfiguration](Set-PSSessionConfiguration.md)

[Test-PSSessionConfigurationFile](Test-PSSessionConfigurationFile.md)

[Unregister-PSSessionConfiguration](Unregister-PSSessionConfiguration.md)

[WSMan-Anbieter](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[about_Session_Configurations](About/about_Session_Configurations.md)

[about_Session_Configuration_Files](About/about_Session_Configuration_Files.md)
