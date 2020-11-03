---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/08/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/update-modulemanifest?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-ModuleManifest
ms.openlocfilehash: 81c58a09cb6c4e6cedcc7abfa832af7bb694b0e1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217855"
---
# Update-ModuleManifest

## ZUSAMMENFASSUNG
Aktualisiert eine Modulmanifestdatei

## SYNTAX

### Alle

```
Update-ModuleManifest [-Path] <String> [-NestedModules <Object[]>] [-Guid <Guid>] [-Author <String>]
 [-CompanyName <String>] [-Copyright <String>] [-RootModule <String>] [-ModuleVersion <Version>]
 [-Description <String>] [-ProcessorArchitecture <ProcessorArchitecture>]
 [-CompatiblePSEditions <String[]>] [-PowerShellVersion <Version>] [-ClrVersion <Version>]
 [-DotNetFrameworkVersion <Version>] [-PowerShellHostName <String>]
 [-PowerShellHostVersion <Version>] [-RequiredModules <Object[]>] [-TypesToProcess <String[]>]
 [-FormatsToProcess <String[]>] [-ScriptsToProcess <String[]>] [-RequiredAssemblies <String[]>]
 [-FileList <String[]>] [-ModuleList <Object[]>] [-FunctionsToExport <String[]>]
 [-AliasesToExport <String[]>] [-VariablesToExport <String[]>] [-CmdletsToExport <String[]>]
 [-DscResourcesToExport <String[]>] [-PrivateData <Hashtable>] [-Tags <String[]>]
 [-ProjectUri <Uri>] [-LicenseUri <Uri>] [-IconUri <Uri>] [-ReleaseNotes <String[]>]
 [-Prerelease <String>] [-HelpInfoUri <Uri>] [-PassThru] [-DefaultCommandPrefix <String>]
 [-ExternalModuleDependencies <String[]>] [-PackageManagementProviders <String[]>]
 [-RequireLicenseAcceptance] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Update-ModuleManifest` Cmdlet wird eine Modul Manifest- `.psd1` Datei () aktualisiert.

## BEISPIELE

### Beispiel 1: Aktualisieren eines Modul Manifests

In diesem Beispiel wird eine vorhandene Modul Manifest-Datei aktualisiert. Splatting wird zum Übergeben von Parameterwerten an verwendet `Update-ModuleManifest` . Weitere Informationen finden Sie unter [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).

```powershell
$Parms = @{
  Path = "C:\Test\TestManifest.psd1"
  Author = "TestUser1"
  CompanyName = "Contoso Corporation"
  Copyright = "(c) 2019 Contoso Corporation. All rights reserved."
}

Update-ModuleManifest @Parms
```

`$Parms` ist ein splat, das die Parameterwerte für " **path** ", " **Author** ", " **CompanyName** " und " **Copyright** " speichert. `Update-ModuleManifest` Ruft die Parameterwerte aus ab `@Parms` und aktualisiert das Modul Manifest, **TestManifest.psd1**.

## PARAMETERS

### -Aliasestoexport

Gibt die Aliase an, die das Modul exportiert. Platzhalter sind zulässig.

Verwenden Sie diesen Parameter, um die Aliase einzuschränken, die vom Modul exportiert werden. **Aliasestoexport** kann Aliase aus der Liste der exportierten Aliase entfernen, aber keine Aliase zur Liste hinzufügen.

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

### -Autor

Gibt den Autor des Moduls an.

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

### -ClrVersion

Gibt die für das Modul erforderliche Mindestversion der Common Language Runtime (CLR) von Microsoft .NET Framework an.

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

### -Cmdletstoexport

Gibt die Cmdlets an, die das Modul exportiert. Platzhalter sind zulässig.

Verwenden Sie diesen Parameter, um die Cmdlets einzuschränken, die vom Modul exportiert werden. **Cmdletstoexport** kann Cmdlets aus der Liste der exportierten Cmdlets entfernen, aber keine Cmdlets zur Liste hinzufügen.

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

### -CompanyName

Gibt das Unternehmen oder den Hersteller an, der das Modul erstellt hat.

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

### -Compatiblepseditions

Gibt die kompatiblen **pseditions** des Moduls an. Weitere Informationen zu **ppingdition** finden Sie unter [Module mit kompatiblen PowerShell-Editionen](/powershell/scripting/gallery/concepts/module-psedition-support).

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:
Accepted values: Desktop, Core

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

Sie werden zur Bestätigung aufgefordert, bevor Sie ausgeführt werden `Update-ModuleManifest` .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Copyright

Gibt eine Urheberrechtserklärung für das Modul an.

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

### -Defaultcommandprefix

Gibt das Standard Befehls Präfix an.

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

Gibt eine Beschreibung des Moduls an.

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

### -Dotnetframeworkversion

Gibt die für das Modul erforderliche Mindestversion des Microsoft .NET Framework an.

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

### -Dscresourcestoexport

Gibt die DSC-Ressourcen (DSC) an, die vom Modul exportiert werden. Platzhalter sind zulässig.

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

### -Externalmoduledependen

Gibt ein Array externer Modul Abhängigkeiten an.

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

### -FileList

Gibt alle Elemente an, die im Modul enthalten sind.

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

### -Formatstoprocess

Gibt die Formatierungs Dateien ( `.ps1xml` ) an, die beim Importieren des Moduls ausgeführt werden.

Wenn Sie ein Modul importieren, führt PowerShell das `Update-FormatData` Cmdlet mit den angegebenen Dateien aus.
Da Formatierungs Dateien nicht Bereichs bezogen sind, wirken Sie sich auf alle Sitzungs Zustände in der Sitzung aus.

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

### -Functionstoexport

Gibt die Funktionen an, die das Modul exportiert. Platzhalter sind zulässig.

Verwenden Sie diesen Parameter, um die Funktionen einzuschränken, die vom Modul exportiert werden. **Functionstoexport** kann Funktionen aus der Liste der exportierten Aliase entfernen, aber keine Funktionen zur Liste hinzufügen.

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

### -GUID

Gibt einen eindeutigen Bezeichner für das Modul an. Die GUID kann verwendet werden, um Module mit dem gleichen Namen zu unterscheiden.

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

### -Helpinfouri

Gibt die Internetadresse der **helpinfo-XML** -Datei des Moduls an. Geben Sie einen Uniform Resource Identifier (URI) ein, der mit **http** oder **https** beginnt.

Die **helpinfo-XML** -Datei unterstützt das Feature "aktualisierbare Hilfe", das in PowerShell Version 3,0 eingeführt wurde. Sie enthält Informationen über den Speicherort der herunterladbaren Hilfedateien des Moduls und die Versionsnummern der neuesten Hilfedateien für jedes unterstützte Gebiets Schema.

Weitere Informationen zur aktualisierbaren Hilfe finden Sie unter [about_Updatable_Help](../Microsoft.PowerShell.Core/About/about_Updatable_Help.md).
Informationen zur **helpinfo-XML** -Datei finden Sie [unter unterstützen der aktualisierbaren Hilfe](/powershell/scripting/developer/module/supporting-updatable-help).

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Iconuri

Gibt die URL eines Symbols für das Modul an. Das angegebene Symbol wird auf der Katalog Webseite für das Modul angezeigt.

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Licenaburi

Gibt die URL der Lizenzierungs Bedingungen für das Modul an.

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Modulelist

Gibt ein Array von Modulen an, die im Modul enthalten sind.

Geben Sie jeden Modulnamen als Zeichenfolge oder Hashtabelle mit den Schlüsseln **ModuleName** und **ModuleVersion** ein. Die Hashtabelle kann auch einen optionalen **GUID** -Schlüssel haben. Sie können Zeichenfolgen und Hashtabellen im Parameterwert kombinieren.

Dieser Schlüssel ist als Modulinventar konzipiert. Die Module, die im Wert dieses Schlüssels aufgeführt sind, werden nicht automatisch verarbeitet.

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

### -Moduleversion

Gibt die Version des Moduls an.

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

### -Netstedmodules

Gibt Skript Module ( `.psm1` ) und binäre Module ( `.dll` ) an, die in den Sitzungs Status des Moduls importiert werden. Die Dateien im Schlüssel " **netstedmodules** " werden in der Reihenfolge ausgeführt, in der Sie im Wert aufgelistet sind.

Geben Sie jeden Modulnamen als Zeichenfolge oder Hashtabelle mit den Schlüsseln **ModuleName** und **ModuleVersion** ein. Die Hashtabelle kann auch einen optionalen **GUID** -Schlüssel haben. Sie können Zeichenfolgen und Hashtabellen im Parameterwert kombinieren.

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

### -Packagemanagementproviders

Gibt ein Array von Paket Verwaltungs Anbietern an.

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

### -PassThru

Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten. Standardmäßig `Update-ModuleManifest` generiert keine Ausgabe.

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

Gibt den Pfad und den Dateinamen des Modul Manifests an. Geben Sie einen Pfad und einen Dateinamen mit einer `.psd1` Dateinamenerweiterung ein, z `$PSHOME\Modules\MyModule\MyModule.psd1` . b..

Wenn Sie den Pfad zu einer vorhandenen Datei angeben, wird `Update-ModuleManifest` die Datei von ohne Warnung ersetzt, es sei denn, die Datei verfügt über das Attribut "schreibgeschützt".

Das Manifest sollte sich im Verzeichnis des Moduls befinden, und der Name der Manifest-Datei muss mit dem Namen des Modul Verzeichnisses übereinstimmen, aber mit einer `.psd1` Erweiterung.

Sie können keine Variablen (z. b. oder) als `$PSHOME` `$HOME` Antwort auf eine Eingabeaufforderung für einen **path** -Parameter verwenden. Um eine Variable zu verwenden, schließen Sie den **Path** -Parameter in den Befehl ein.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Powershellhostname

Gibt den Namen des PowerShell-Host Programms an, das für das Modul erforderlich ist. Geben Sie den Namen des Host Programms ein, z. b. PowerShell ISE-Host oder ConsoleHost. Platzhalter sind nicht zulässig.

Um den Namen eines Host Programms zu suchen, geben Sie im Programm ein `$Host.Name` .

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

### -Powershellhostversion

Gibt die Mindestversion des PowerShell-Host Programms an, das mit dem Modul funktioniert. Geben Sie eine Versionsnummer an, z. B. 1.1.

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

### -PowerShellVersion

Gibt die Mindestversion von PowerShell an, die mit diesem Modul funktionieren wird. Sie können z. b. 3,0, 4,0 oder 5,0 als Wert dieses Parameters angeben.

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

### -Vorabversion

Gibt an, dass das Modul eine Vorabversion ist.

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

### -PRIVATEDATA

Gibt Daten an, die beim Importieren an das Modul übermittelt werden.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProcessorArchitecture

Gibt die Prozessorarchitektur an, die das Modul erfordert.

Zulässige Werte für diesen Parameter:

- Amd64
- Arm
- IA64
- MSIL
- None (unbekannt oder nicht angegeben)
- X86

```yaml
Type: System.Reflection.ProcessorArchitecture
Parameter Sets: (All)
Aliases:
Accepted values: None, MSIL, X86, IA64, Amd64, Arm

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Projecturi

Gibt die URL einer Webseite zu diesem Projekt an.

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Releasenotes

Gibt ein Zeichen folgen Array an, das Anmerkungen oder Kommentare enthält, die Sie für diese Version des Skripts zur Verfügung stellen möchten.

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

### -Requirements dassemblys

Gibt die Assemblydateien ( `.dll` ) an, die das Modul erfordert. Geben Sie die Namen der Assemblydateien ein.
PowerShell lädt die angegebenen Assemblys vor dem Aktualisieren von Typen oder Formaten, dem Importieren von geschbten Modulen oder dem Importieren der Modul Datei, die im Wert des **rootmodule** -Schlüssels angegeben ist.

Verwenden Sie diesen Parameter, um alle Assemblys anzugeben, die das Modul benötigt, einschließlich Assemblys, die geladen werden müssen, um Formatierungs-oder Typdateien zu aktualisieren, die in den Schlüsseln **formatstoprocess** oder **typestoprocess** aufgeführt sind, auch wenn diese Assemblys auch als binäre Module im Schlüssel " **netstedmodules** " aufgeführt sind.

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

### -Requirements dmodules

Gibt die Module an, die im globalen Sitzungsstatus enthalten sein müssen. Wenn sich die erforderlichen Module nicht im globalen Sitzungs Status befinden, importiert PowerShell Sie. Wenn die erforderlichen Module nicht verfügbar sind, `Import-Module` schlägt der Befehl fehl.

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

### -Requirelicenabakzeptanz

Gibt an, dass für das Modul eine Zustimmung zur Lizenz erforderlich ist.

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

### -Rootmodule

Gibt die primäre oder Stammdatei des Moduls an. Geben Sie den Dateinamen eines Skripts ( `.ps1` ), eines Skript Moduls ( `.psm1` ), eines Modul Manifests ( `.psd1` ), einer Assembly ( `.dll` ), einer Cmdlet-Definitions-XML-Datei ( `.cdxml` ) oder eines Workflows () ein `.xaml` . Wenn das Modul importiert wird, werden die aus der Stammmodul-Datei exportierten Member in den Sitzungsstatus des Aufrufers importiert.

Wenn ein Modul über eine Manifest-Datei verfügt und im **rootmodule** -Schlüssel keine Stammdatei angegeben wurde, wird das Manifest zur primären Datei für das Modul. Und das Modul wird zu einem Manifest-Modul (ModuleType = Manifest).

Zum Exportieren von Membern aus- `.psm1` oder- `.dll` Dateien in einem Modul mit einem Manifest müssen die Namen dieser Dateien in den Werten der **rootmodule** -oder **netstedmodules** -Schlüssel im Manifest angegeben werden. Andernfalls werden die Member nicht exportiert.

In PowerShell 2,0 hieß dieser Schlüssel " **moduletoprocess** ".

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

### -Scriptstoprocess

Gibt Skript `.ps1` Dateien () an, die im Sitzungszustand des Aufrufers ausgeführt werden, wenn das Modul importiert wird.
Sie können diese Skripte zur Vorbereitung einer Umgebung verwenden, wie Sie ein Anmeldeskript verwenden würden.

Um Skripte anzugeben, die im Sitzungsstatus des Moduls ausgeführt werden, verwenden Sie den **NestedModules** -Schlüssel.

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

### -Tags

Gibt ein Array von-Tags an.

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

Gibt die Typdateien ( `.ps1xml` ) an, die beim Importieren des Moduls ausgeführt werden.

Wenn Sie das Modul importieren, führt PowerShell das `Update-TypeData` Cmdlet mit den angegebenen Dateien aus.
Da Typdateien nicht Bereichs bezogen sind, wirken Sie sich auf alle Sitzungs Zustände in der Sitzung aus.

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

### -Variablestoexport

Gibt die Variablen an, die das Modul exportiert. Platzhalter sind zulässig.

Verwenden Sie diesen Parameter, um die Variablen einzuschränken, die vom Modul exportiert werden. **Variablestoexport** kann Variablen aus der Liste der exportierten Variablen entfernen, aber keine Variablen zur Liste hinzufügen.

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

### -WhatIf

Zeigt, was geschieht, wenn ausgeführt wird `Update-ModuleManifest` . Das Cmdlet wird nicht ausgeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

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

## AUSGABEN

### System.Object

## HINWEISE

## VERWANDTE LINKS
