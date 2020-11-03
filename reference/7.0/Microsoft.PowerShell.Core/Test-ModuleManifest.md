---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/test-modulemanifest?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-ModuleManifest
ms.openlocfilehash: 41b5ef4471ec2bef0bf4b30f8996f2e0010eceff
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93209831"
---
# Test-ModuleManifest

## ZUSAMMENFASSUNG
Überprüft, ob eine Modulmanifestdatei den Inhalt eines Moduls genau beschreibt.

## SYNTAX

```
Test-ModuleManifest [-Path] <String> [<CommonParameters>]
```

## DESCRIPTION

Mit dem **Test-modulemanifest** -Cmdlet wird überprüft, ob sich die in der Modul Manifest-Datei (. psd1) aufgeführten Dateien tatsächlich in den angegebenen Pfaden befinden.

Dieses Cmdlet soll Modulautoren beim Testen von Manifestdateien unterstützen.
Modul Benutzer können dieses Cmdlet auch in Skripts und Befehlen verwenden, um Fehler zu erkennen, bevor Skripts ausgeführt werden, die vom Modul abhängen.

**Test-modulemanifest** gibt ein Objekt zurück, das das Modul darstellt.
Dabei handelt es sich um denselben Objekttyp, den Get-Module zurückgibt.
Wenn Dateien nicht an den im Manifest angegebenen Speicherorten vorhanden sind, generiert das Cmdlet einen Fehler für jede fehlende Datei.

## BEISPIELE

### Beispiel 1: Testen eines Manifests

```powershell
test-ModuleManifest -Path "$pshome\Modules\TestModule.psd1"
```

Dieser Befehl testet das Modulmanifest „TestModule.psd1“.

### Beispiel 2: Testen eines Manifests mithilfe der Pipeline

```powershell
"$pshome\Modules\TestModule.psd1" | test-modulemanifest
```

```Output
Test-ModuleManifest : The specified type data file 'C:\Windows\System32\Wi
ndowsPowerShell\v1.0\Modules\TestModule\TestTypes.ps1xml' could not be processed because the file was not found. Please correct the path and try again.
At line:1 char:34
+ "$pshome\Modules\TestModule.psd1" | test-modulemanifest <<<<
+ CategoryInfo          : ResourceUnavailable: (C:\Windows\System32\WindowsPowerShell\v1.0\Modules\TestModule\TestTypes.ps1xml:String) [Test-ModuleManifest], FileNotFoundException
+ FullyQualifiedErrorId : Modules_TypeDataFileNotFound,Microsoft.PowerShell.Commands.TestModuleManifestCommandName

Name              : TestModule
Path              : C:\Windows\system32\WindowsPowerShell\v1.0\Modules\TestModule\TestModule.psd1
Description       :
Guid              : 6f0f1387-cd25-4902-b7b4-22cff6aefa7b
Version           : 1.0
ModuleBase        : C:\Windows\system32\WindowsPowerShell\v1.0\Modules\TestModule
ModuleType        : Manifest
PrivateData       :
AccessMode        : ReadWrite
ExportedAliases   : {}
ExportedCmdlets   : {}
ExportedFunctions : {}
ExportedVariables : {}
NestedModules     : {}
```

Dieser Befehl verwendet einen Pipeline Operator (|), um eine Pfad Zeichenfolge an **Test-modulemanifest** zu senden.

Die Befehlsausgabe zeigt einen Testfehler, da die im Manifest aufgeführte Datei „TestTypes.ps1xml“ nicht gefunden wurde.

### Beispiel 3: Schreiben einer Funktion zum Testen eines Modul Manifests

```powershell
function Test-ManifestBool ($path)
```

```Output
{$a = dir $path | Test-ModuleManifest -ErrorAction SilentlyContinue; $?}
```

Diese Funktion ist wie **Test-modulemanifest** , gibt jedoch einen booleschen Wert zurück.
Die Funktion gibt $true zurück, wenn das Manifest den Test erfolgreich durchlaufen hat, und $false andernfalls.

Die Funktion verwendet das Get-ChildItem Cmdlet Alias = dir, um das von der $PATH Variable angegebene Modul Manifest zu erhalten.
Der Befehl verwendet einen Pipeline Operator (|), um das Datei Objekt an **Test-modulemanifest** zu übergeben.

**Test-modulemanifest** verwendet den allgemeinen *ErrorAction* -Parameter mit dem Wert SilentlyContinue, um die Anzeige von Fehlern zu unterdrücken, die der Befehl generiert.
Außerdem wird das von **Test-modulemanifest** zurückgegebene **psmoduleinfo** -Objekt in der $a Variablen gespeichert.
Daher wird das-Objekt nicht angezeigt.

In einem separaten Befehl zeigt die Funktion den Wert des $?
Automatische Variable.
Wenn der vorherige Befehl keinen Fehler generiert, zeigt der Befehl $true an, und $false andernfalls.

Sie können diese Funktion in bedingten Anweisungen verwenden, z. b. solche, die einem **Import-Module** -Befehl vorangestellt sind, oder einen Befehl, der das Modul verwendet.

## PARAMETERS

### -Path

Gibt einen Pfad und einen Dateinamen für die Manifest-Datei an.
Geben Sie einen optionalen Pfad und Namen der Modul Manifest-Datei mit der Dateinamenerweiterung ". psd1" ein.
Der Standardspeicherort ist das aktuelle Verzeichnis.
Platzhalter Zeichen werden unterstützt, müssen jedoch in eine einzelne Modul Manifest-Datei aufgelöst werden.
Dieser Parameter ist erforderlich.
Sie können einen Pfad auch an **Test-modulemanifest** weiterreichen.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System.String

Sie können den Pfad zu einem Modul Manifest an dieses Cmdlet weiterreichen.

## AUSGABEN

### System. Management. Automation. psmoduleinfo

Dieses Cmdlet gibt ein **psmoduleinfo** -Objekt zurück, das das Modul darstellt.
Dieses Objekt wird auch dann zurückgegeben, wenn das Manifest Fehler aufweist.

## HINWEISE

## VERWANDTE LINKS

[Export-ModuleMember](Export-ModuleMember.md)

[Get-Module](Get-Module.md)

[Import-Module](Import-Module.md)

[New-Module](New-Module.md)

[New-ModuleManifest](New-ModuleManifest.md)

[Remove-Module](Remove-Module.md)

[about_Modules](About/about_Modules.md)
