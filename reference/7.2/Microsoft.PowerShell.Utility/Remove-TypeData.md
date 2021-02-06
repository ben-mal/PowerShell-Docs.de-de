---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/remove-typedata?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-TypeData
ms.openlocfilehash: 8ede1375faa1287b70eeb49689ec7fe1bb800d55
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599848"
---
# Remove-TypeData

## Übersicht
Löscht erweiterte Typen aus der aktuellen Sitzung.

## Syntax

### Removetypeer DataSet (Standard)

```
Remove-TypeData -TypeData <TypeData> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Removetypeset

```
Remove-TypeData [-TypeName] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Removefileset

```
Remove-TypeData -Path <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Remove-TypeData` Cmdlet werden erweiterte Typdaten aus der aktuellen Sitzung gelöscht. Dieses Cmdlet wirkt sich nur auf die aktuelle Sitzung und Sitzungen aus, die in der aktuellen Sitzung erstellt werden.

Sie können Objekten in PowerShell Eigenschaften und Methoden hinzufügen, indem Sie Sie in `Update-TypeData` Befehlen und `Types.ps1xml` Dateien definieren. `Remove-TypeData` löscht diese erweiterten Eigenschaften und Methoden aus der aktuellen Sitzung. `Remove-TypeData` die Dateien werden nicht gelöscht, oder es werden `Types.ps1xml` keine erweiterten Typdefinitionen aus den `Types.ps1xml` Dateien gelöscht. Weitere Informationen zu `Types.ps1xml` Dateien finden Sie unter [about_Types.ps1XML](../Microsoft.PowerShell.Core/about/about_Types.ps1xml.md).

Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.

## Beispiele

### Beispiel 1: Entfernen von Typdaten für einen angegebenen Typ

In diesem Beispiel werden alle Typdaten für den **System. Array** -Typ aus der Sitzung gelöscht, einschließlich der von einer Datei hinzugefügten Typdaten `Types.ps1xml` und dynamischer Typdaten, die der Sitzung mithilfe des `Update-TypeData` Cmdlets hinzugefügt wurden.

```powershell
Remove-TypeData -TypeName System.Array
```

### Beispiel 2: Entfernen eines erweiterten Datentyps aus einer Sitzung

Dieses Beispiel zeigt die Auswirkung des Entfernens von erweiterten Typdaten aus einer Sitzung. Der erste ruft `Get-TypeData` Erweiterte Typdaten für den **System. DateTime** -Typ ab. Die Ausgabe zeigt, dass alle **System. DateTime** -Objekte in PowerShell eine **DateTime** -Eigenschaft hinzugefügt wurde. Das- `Get-Date` Cmdlet gibt ein **System. DateTime** -Objekt zurück. Der Befehl verwendet die Punkt Notation, um den Wert der **DateTime** -Eigenschaft des **System. DateTime** -Objekts, das zurückgibt, zu erhalten `Get-Date` .

```powershell
Get-TypeData System.DateTime
(Get-Date).DateTime
Get-TypeData System.DateTime | Remove-TypeData
(Get-Date).DateTime
```

```Output
TypeName        Members
--------        -------
System.DateTime {[DateTime, System.Management.Automation.Runspaces.ScriptPropertyData]}

Friday, January 20, 2012 9:01:00 PM
```

Das nächste `Get-TypeData` Cmdlet, um alle erweiterten Typdaten für den **System. DateTime** -Typ zu erhalten, und leitet dieses an das `Remove-TypeData` Cmdlet weiter, um die erweiterten Typdaten zu löschen. Das letzte `Get-Date` Cmdlet zeigt die Auswirkungen des Löschens der erweiterten Typdaten für **den System. DateTime** -Typ. Da die **System. DateTime** -Eigenschaft nicht mehr vorhanden ist, gibt ein Befehl zum erhalten des Werts nichts zurück.

### Beispiel 3: Entfernen erweiterter Typen für Module

In diesem Beispiel werden alle erweiterten Typdaten für Modul Objekte entfernt. Wenn Sie ein Objekt an die Pipeline übergeben `Remove-TypeData` , ruft `Remove-TypeData` den Namen des Objekt Typs ab und entfernt alle Typdaten für alle Objekte dieses Typs.

```powershell
Get-Module | Remove-TypeData
```

### Beispiel 4: Entfernen erweiterter Typen aus angegebenen Modulen

Dieses Beispiel verwendet den **path** -Parameter des `Remove-TypeData` Cmdlets, um die erweiterten Typen zu entfernen, die in den `Types.ps1xml` von den Modulen **psscheduledjob** und **psworkflow** hinzugefügten Dateien definiert sind. Dieser Befehl wirkt sich nicht auf dynamische Typdaten aus, die mit dem `Update-TypeData` Cmdlet hinzugefügt werden. Der Befehl ist nur erfolgreich, wenn die Module in die aktuelle Sitzung importiert wurden.

```powershell
Remove-TypeData -Path "$PSHOME\Modules\PSScheduledJob", "$PSHOME\Modules\PSWorkflow\PSWorkflow.types.ps1xml"
```

Weitere Informationen zu Modulen finden Sie unter [about_Modules](../Microsoft.PowerShell.Core/About/about_Modules.md).

### Beispiel 5: Entfernen erweiterter Typen aus einer Remote Sitzung

In diesem Beispiel werden erweiterte Typen aus einer Remote Sitzung entfernt. Der Befehl verwendet das `Invoke-Command` Cmdlet, um erweiterte Typdaten für alle CIM-Typen in den Sitzungen in der Variablen zu entfernen `$S` .

```powershell
Invoke-Command -Session $S {Get-TypeData -TypeName *CIM* | Remove-TypeData}
```

## Parameter

### -Path

Gibt ein Array von Dateien an, die von diesem Cmdlet aus den erweiterten Typdaten der Sitzung gelöscht werden. Dieser Parameter ist erforderlich.

Geben Sie die Pfade und Dateinamen von einer oder mehreren `Types.ps1xml` Dateien ein. Platzhalter werden nicht unterstützt. Wenn Sie den Pfad weglassen, wird als Standardspeicherort das aktuelle Verzeichnis verwendet.

```yaml
Type: System.String[]
Parameter Sets: RemoveFileSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Typedata

Gibt die Typdaten an, die von diesem Cmdlet aus der Sitzung gelöscht werden. Dieser Parameter ist erforderlich. Geben Sie eine Variable ein, die **typedata** -Objekte (**System. Management. Automation. Runspaces. typedata**) enthält, oder einen Befehl, der **typedata** -Objekte abruft, z. b. einen- `Get-TypeData` Befehl. Sie können **typedata** -Objekte auch über die Pipeline an senden `Remove-TypeData` .

```yaml
Type: System.Management.Automation.Runspaces.TypeData
Parameter Sets: RemoveTypeDataSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Typname

Gibt die Typen an, für die dieses Cmdlet alle erweiterten Typdaten löscht. Geben Sie für Typen im System-Namespace den kurzen Namen ein. Für andere Typen ist der vollständige Typname erforderlich. Platzhalter werden nicht unterstützt.

Sie können Typnamen an übergeben `Remove-TypeData` . Wenn Sie ein Objekt an übergeben `Remove-TypeData` , ruft `Remove-TypeData` den Typnamen des Objekts ab und entfernt alle Typdaten für den Objekttyp.

```yaml
Type: System.String
Parameter Sets: RemoveTypeSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Confirm

Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.

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

### -WhatIf

Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird. Das Cmdlet wird nicht ausgeführt.

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

## Eingaben

### System. Management. Automation. Runspaces. typedata

Sie können das **typedata** -Objekt, z. b. die vom `Get-TypeData` Cmdlet zurückgegebenen, an übergeben `Remove-TypeData` .

### System.String

Sie können die Typnamen an übergeben `Remove-TypeData` . Wenn Sie ein Objekt an übergeben `Remove-TypeData` , ruft `Remove-TypeData` den Typnamen des Objekts ab und entfernt alle Typdaten für den Objekttyp.

## Ausgaben

### Keine

Dieses Cmdlet generiert keine Ausgabe.

## Notizen

`Remove-TypeData` nur die erweiterten Typdaten in der aktuellen Sitzung können entfernt werden. Es kann nicht erweiterte Typdaten entfernen, die sich auf dem Computer befinden, jedoch nicht der aktuellen Sitzung hinzugefügt wurden, wie erweiterte Typen, die in Modulen definiert sind, die aber nicht in die aktuelle Sitzung importiert wurden.

## Verwandte Links

[Get-TypeData](Get-TypeData.md)

[Update-TypeData](Update-TypeData.md)

