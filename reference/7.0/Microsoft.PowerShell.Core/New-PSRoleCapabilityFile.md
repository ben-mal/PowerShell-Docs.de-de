---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 09/11/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/new-psrolecapabilityfile?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSRoleCapabilityFile
ms.openlocfilehash: 61a144ca5bc74d63738e9ccfc65188ddf1e27c02
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210687"
---
# New-PSRoleCapabilityFile

## ZUSAMMENFASSUNG
Erstellt eine Datei, die einen Satz von Funktionen definiert, die durch eine Sitzungs Konfiguration verfügbar gemacht werden sollen.

## SYNTAX

```
New-PSRoleCapabilityFile [-Path] <String> [-Guid <Guid>] [-Author <String>] [-Description <String>]
 [-CompanyName <String>] [-Copyright <String>] [-ModulesToImport <Object[]>] [-VisibleAliases <String[]>]
 [-VisibleCmdlets <Object[]>] [-VisibleFunctions <Object[]>] [-VisibleExternalCommands <String[]>]
 [-VisibleProviders <String[]>] [-ScriptsToProcess <String[]>] [-AliasDefinitions <IDictionary[]>]
 [-FunctionDefinitions <IDictionary[]>] [-VariableDefinitions <Object>] [-EnvironmentVariables <IDictionary>]
 [-TypesToProcess <String[]>] [-FormatsToProcess <String[]>] [-AssembliesToLoad <String[]>]
 [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `New-PSRoleCapabilityFile` Cmdlet wird eine Datei erstellt, die eine Reihe von Benutzer Funktionen definiert, die durch Sitzungs Konfigurationsdateien verfügbar gemacht werden können. Dazu gehört auch die Bestimmung, welche Cmdlets, Funktionen und Skripts für Benutzer verfügbar sind. Die Funktions Datei ist eine lesbare Textdatei, die eine Hash Tabelle mit Sitzungs Konfigurations Eigenschaften und-Werten enthält. Die Datei weist die Dateinamenerweiterung. psrc auf und kann von mehr als einer Sitzungs Konfiguration verwendet werden.

Alle Parameter von `New-PSRoleCapabilityFile` sind mit Ausnahme des **path** -Parameters optional, der den Dateipfad für die Datei angibt. Wenn Sie beim Ausführen des Cmdlets keinen Parameter einschließen, wird der entsprechende Schlüssel in der Sitzungs Konfigurationsdatei auskommentiert, es sei denn, dies ist in der Parameter Beschreibung angegeben. Wenn Sie z. b. keinen **assemblyoload** -Parameter einschließen, wird dieser Abschnitt der Sitzungs Konfigurationsdatei auskommentiert.

Wenn Sie die Rollen Funktions Datei in einer Sitzungs Konfiguration verwenden möchten, platzieren Sie die Datei zunächst in einem Unterordner **rolecapability** eines gültigen PowerShell-Modul Ordners. Verweisen Sie dann im Feld " **roledefinitions** " in einer PowerShell-Sitzungs Konfigurationsdatei (PSSC-Datei) mit dem Namen auf die Datei.

Dieses Cmdlet wurde in Windows PowerShell 5,0 eingeführt.

## BEISPIELE

### Beispiel 1: Erstellen einer leeren Rollen Funktions Datei

In diesem Beispiel wird eine neue Rollen Funktions Datei erstellt, in der die Standardwerte (leer) verwendet werden. Die Datei kann später in einem Text-Editor bearbeitet werden, um diese Konfigurationseinstellungen zu ändern.

```powershell
New-PSRoleCapabilityFile -Path ".\ExampleFile.psrc"
```

### Beispiel 2: Erstellen einer Rollen Funktions Datei, die Benutzern das Neustarten von Diensten und VDI-Computern ermöglicht

In diesem Beispiel wird eine Beispiel Rollen Funktions Datei erstellt, mit der Benutzerdienste und Computer, die einem bestimmten Namensmuster entsprechen, neu starten können. Die namens Filterung wird durch Festlegen des **validatepattern** -Parameters auf den regulären Ausdruck definiert `VDI\d+` .

```powershell
$roleParameters = @{
    Path = ".\Maintenance.psrc"
    Author = "User01"
    CompanyName = "Fabrikam Corporation"
    Description = "This role enables users to restart any service and restart any VDI computer."
    ModulesToImport = "Microsoft.PowerShell.Core"
    VisibleCmdlets = "Restart-Service", @{
                      Name = "Restart-Computer"
                      Parameters = @{ Name = "ComputerName"; ValidatePattern = "VDI\d+" }
    }
}
New-PSRoleCapabilityFile @roleParameters
```

## PARAMETERS

### -Aliasdefinitionen

Fügt die angegebenen Aliase zu Sitzungen hinzu, die die Rollen Funktions Datei verwenden. Geben Sie eine Hashtabelle mit den folgenden Schlüsseln ein:

- Name. Name des Alias. Dieser Schlüssel ist erforderlich.
- Wert. Der Befehl, den der Alias darstellt. Dieser Schlüssel ist erforderlich.
- Beschreibung Eine Textzeichenfolge, die den Alias beschreibt. Dieser Schlüssel ist optional.
- Optionen. Aliasoptionen. Dieser Schlüssel ist optional. Der Standardwert lautet „Keine“. Die zulässigen Werte für diesen Parameter lauten: None, Read Only, Constant, private oder allscope.

Beispiel: `@{Name="hlp";Value="Get-Help";Description="Gets help";Options="ReadOnly"}`

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

Gibt die Assemblys an, die in die Sitzungen geladen werden sollen, die die Rollen Funktions Datei verwenden.

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

Gibt den Benutzer an, der die Rollen Funktions Datei erstellt hat.

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

Identifiziert das Unternehmen, das die Rollen Funktions Datei erstellt hat.
Der Standardwert ist Unknown (Unbekannt).

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

### -Copyright

Gibt ein Copyright für die Rollen Funktions Datei an. Wenn Sie diesen Parameter weglassen, `New-PSRoleCapabilityFile` generiert eine Copyright Anweisung mit dem Wert des **Author** -Parameters.

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

Gibt eine Beschreibung für die Rollen Funktions Datei an.

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

Gibt die Umgebungsvariablen für Sitzungen an, die diese Rollen Funktions Datei verfügbar machen. Geben Sie eine Hashtabelle ein, in der die Schlüssel die Namen der Umgebungsvariablen und die Werte die Werte der Umgebungsvariablen sind.

Beispiel: `EnvironmentVariables=@{TestShare="\\\\Server01\TestShare"}`

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

### -Formatstoprocess

Gibt die Formatierungs Dateien (. ps1xml) an, die in Sitzungen ausgeführt werden, in denen die Rollen Funktions Datei verwendet wird. Der Wert dieses Parameters muss ein vollständiger oder absoluter Pfad der Formatierungs Dateien sein.

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

### -Functiondefinitions

Fügt den Sitzungen, die die Rollen Funktion verfügbar machen, die angegebenen Funktionen hinzu. Geben Sie eine Hashtabelle mit den folgenden Schlüsseln ein:

- Name. Name der Funktion. Dieser Schlüssel ist erforderlich.
- ScriptBlock. Funktionstext. Geben Sie einen Skriptblock ein. Dieser Schlüssel ist erforderlich.
- Optionen. Funktionsoptionen. Dieser Schlüssel ist optional. Der Standardwert lautet „Keine“. Die zulässigen Werte für diesen Parameter sind "None", "Read only", "Constant", "private" oder "allscope".

Beispiel:

`@{Name="Get-PowerShellProcess";ScriptBlock={Get-Process PowerShell};Options="AllScope"}`

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

### -GUID

Gibt einen eindeutigen Bezeichner für die Rollen Funktions Datei an. Wenn Sie diesen Parameter weglassen, `New-PSRoleCapabilityFile` generiert eine GUID für die Datei. Geben Sie ein, um eine neue GUID in PowerShell zu erstellen `[guid]::NewGuid()` .

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

### -Modulestoimport

Gibt die Module an, die automatisch in Sitzungen importiert werden, in denen die Rollen Funktions Datei verwendet wird. Standardmäßig sind alle Befehle in aufgelisteten Modulen sichtbar. Bei Verwendung mit **visiblecmdlets** oder **visiblefunctions** können die von den angegebenen Modulen sichtbaren Befehle eingeschränkt werden.

Jedes Modul, das im Wert dieses Parameters verwendet wird, kann durch eine Zeichenfolge oder eine Hash Tabelle dargestellt werden. Eine Modul Zeichenfolge besteht nur aus dem Namen des Moduls. Eine Modul Hash Tabelle kann die Schlüssel " **ModuleName** ", " **moduleversion** " und " **GUID** " enthalten. Nur der **ModuleName** -Schlüssel ist erforderlich.

Beispielsweise besteht der folgende Wert aus einer Zeichenfolge und einer Hashtabelle. Jede Kombination aus Zeichenfolgen und Hashtabellen, in beliebiger Reihenfolge, ist gültig.

`"TroubleshootingPack", @{ModuleName="PSDiagnostics"; ModuleVersion="1.0.0.0";GUID="c61d6278-02a3-4618-ae37-a524d40a7f44"}`

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

### -Path

Gibt den Pfad und den Dateinamen der Rollen Funktions Datei an. Die Datei muss eine Datei `.psrc` Namen Erweiterung aufweisen.

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

### -Scriptstoprocess

Gibt Skripts an, die Sitzungen hinzugefügt werden, die die Rollen Funktions Datei verwenden. Geben Sie den Pfad und die Dateinamen der Skripts ein. Der Wert dieses Parameters muss ein vollständiger oder absoluter Pfad der Skript Dateinamen sein.

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

### -Typestoprocess

Gibt Typdateien (. ps1xml) an, die zu Sitzungen hinzugefügt werden sollen, die die Rollen Funktions Datei verwenden. Geben Sie die typdateinamen ein. Der Wert dieses Parameters muss ein vollständiger oder absoluter Pfad der typdateinamen sein.

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

### -Variabledefinitionen

Gibt Variablen an, die zu Sitzungen hinzugefügt werden, die die Rollen Funktions Datei verwenden. Geben Sie eine Hashtabelle mit den folgenden Schlüsseln ein:

- Name. Name der Variable. Dieser Schlüssel ist erforderlich.
- Wert. Variablenwert. Dieser Schlüssel ist erforderlich.
- Optionen. Variablenoptionen. Dieser Schlüssel ist optional. Der Standardwert lautet „Keine“. Die zulässigen Werte für diesen Parameter sind "None", "Read only", "Constant", "private" oder "allscope".

Beispiel: `@{Name="WarningPreference";Value="SilentlyContinue";Options="AllScope"}`

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

Schränkt die Aliase in der Sitzung auf die Aliase ein, die im Wert dieses Parameters angegeben sind, sowie auf alle Aliase, die Sie im Parameter **Aliasdefinition** definieren. Platzhalterzeichen werden unterstützt.
Standardmäßig sind alle Aliase, die von der PowerShell-Engine definiert werden, und alle Aliase, die von Modulen exportiert werden, in der Sitzung sichtbar.

Um z. b. die verfügbaren Aliase auf GM und GCM einzuschränken, verwenden Sie die folgende Syntax: `VisibleAliases="gcm", "gp"`

Wenn ein beliebiger **sichtbarer** Parameter in der Rollen Funktions Datei enthalten ist, entfernt PowerShell das `Import-Module` Cmdlet und den zugehörigen `ipmo` Alias aus der Sitzung.

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

Standardmäßig sind alle Cmdlets, die die Module in der Sitzung exportieren, in der Sitzung sichtbar. Verwenden Sie die **SessionType** - und **ModulesToImport** -Parameter, um zu bestimmen, welche Module und Snap-Ins in die Sitzung importiert werden. Wenn das Cmdlet von keinem Modul in **modulestoimport** verfügbar gemacht wird, wird `New-PSRoleCapabilityFile` versucht, das entsprechende Modul zu laden.

Wenn ein beliebiger **sichtbarer** Parameter in der Sitzungs Konfigurationsdatei enthalten ist, entfernt PowerShell das `Import-Module` Cmdlet und den zugehörigen `ipmo` Alias aus der Sitzung.

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

### -Visibleexternalcommands

Schränkt die externen Binärdateien, Skripts und Befehle, die in der Sitzung ausgeführt werden können, auf die Werte ein, die im Wert dieses Parameters angegeben werden.

Standardmäßig sind in dieser Sitzung keine externen Befehle sichtbar.

Wenn ein beliebiger **sichtbarer** Parameter in der Sitzungs Konfigurationsdatei enthalten ist, entfernt PowerShell das `Import-Module` Cmdlet und den zugehörigen `ipmo` Alias aus der Sitzung.

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

### -Visiblefunctions

Schränkt die Funktionen in der Sitzung auf jene ein, die im Wert dieses Parameters angegeben sind, sowie auf alle Funktionen, die Sie im **functiondefinitions** -Parameter definieren. Platzhalterzeichen werden unterstützt.

Standardmäßig sind alle Funktionen, die von Modulen in der Sitzung exportiert werden, in dieser Sitzung sichtbar. Verwenden Sie die Parameter **SessionType** und **modulestoimport** , um zu bestimmen, welche Module in die Sitzung importiert werden.

Wenn ein beliebiger **sichtbarer** Parameter in der Sitzungs Konfigurationsdatei enthalten ist, entfernt PowerShell das `Import-Module` Cmdlet und den zugehörigen `ipmo` Alias aus der Sitzung.

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

Standardmäßig sind alle Anbieter, die von einem Modul in der Sitzung exportiert werden, in der Sitzung sichtbar. Verwenden Sie die Parameter **SessionType** und **modulestoimport** , um zu bestimmen, welche Module in die Sitzung importiert werden.

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

## AUSGABEN

## HINWEISE

## VERWANDTE LINKS

[New-PSSessionConfigurationFile](New-PSSessionConfigurationFile.md)

[Get-PSSessionCapability](Get-PSSessionCapability.md)
