---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/update-formatdata?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-FormatData
ms.openlocfilehash: 209e5cf9ab5809767b4135817640ffe7c2d69175
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210500"
---
# Update-FormatData

## ZUSAMMENFASSUNG
Aktualisiert die Formatierungsdaten in der aktuellen Sitzung.

## SYNTAX

```
Update-FormatData [[-AppendPath] <String[]>] [-PrependPath <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Update-FormatData` Cmdlet werden die Formatierungsdaten aus Formatierungs Dateien erneut in die aktuelle Sitzung geladen. Mit diesem Cmdlet können Sie die Formatierungsdaten aktualisieren, ohne PowerShell neu zu starten.

Ohne Parameter `Update-FormatData` lädt die Formatierungs Dateien, die zuvor geladen wurden, erneut.
Mit den Parametern von können Sie `Update-FormatData` der Sitzung neue Formatierungs Dateien hinzufügen.

Formatieren von Dateien sind Textdateien im XML-Format mit der `format.ps1xml` Dateinamenerweiterung. Die Formatierungsdaten in den Dateien definieren die Anzeige von Microsoft .NET Framework-Objekten in der Sitzung.

Beim Starten von PowerShell werden die Format Daten aus dem PowerShell-Quellcode geladen. Sie können jedoch benutzerdefinierte format.ps1XML-Dateien erstellen, um die Formatierung in der aktuellen Sitzung zu aktualisieren. Sie können verwenden `Update-FormatData` , um die Formatierungsdaten in der aktuellen Sitzung neu zu laden, ohne PowerShell neu starten zu müssen. Dies ist nützlich, wenn Sie eine Formatierungsdatei hinzugefügt oder geändert haben, die Sitzung aber nicht unterbrechen möchten.

Weitere Informationen zum Formatieren von Dateien in PowerShell finden Sie unter [about_Format.ps1XML](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).

## BEISPIELE

### Beispiel 1: Erneutes Laden zuvor geladener Formatierungs Dateien

```powershell
Update-FormatData
```

Mit diesem Befehl werden die zuvor geladenen Formatierungsdateien erneut geladen.

### Beispiel 2: Erneutes Laden von Formatierungs Dateien und Dateien zur Ablauf Verfolgung und Protokoll Formatierung

```powershell
Update-FormatData -AppendPath "trace.format.ps1xml, log.format.ps1xml"
```

Mit diesem Befehl werden die Formatierungsdateien erneut in die Sitzung geladen, einschließlich der zwei neuen Dateien „Trace.format.ps1xml“ und „Log.format.ps1xml“.

Da der Befehl den **appendpath** -Parameter verwendet, werden die Formatierungsdaten in den neuen Dateien nach den Formatierungsdaten aus den integrierten Dateien geladen.

Der **appendpath** -Parameter wird verwendet, da die neuen Dateien Formatierungsdaten für Objekte enthalten, auf die in den integrierten Dateien nicht verwiesen wird.

### Beispiel 3: Bearbeiten einer Formatierungs Datei und erneutes Laden

```powershell
Update-FormatData -PrependPath "c:\test\NewFiles.format.ps1xml"

# Edit the NewFiles.format.ps1 file.

Update-FormatData
```

In diesem Beispiel wird veranschaulicht, wie eine Formatierungsdatei nach dem Bearbeiten erneut geladen wird.

Mit dem ersten Befehl wird die Datei „NewFiles.format.ps1xml“ zur Sitzung hinzugefügt. Dabei wird der **prepdpath** -Parameter verwendet, da die Datei Formatierungsdaten für Objekte enthält, auf die in den integrierten Dateien verwiesen wird.

Nachdem Sie die NewFiles.format.ps1XML-Datei hinzugefügt und in diesen Sitzungen getestet haben, bearbeitet der Autor die Datei.

Der zweite Befehl verwendet das `Update-FormatData` Cmdlet, um die Formatierungs Dateien erneut zu laden. Da die NewFiles.format.ps1-XML-Datei zuvor bereits geladen wurde, wird `Update-FormatData` Sie von automatisch erneut geladen, ohne Parameter zu verwenden.

## PARAMETERS

### -Appendpath

Gibt Formatierungs Dateien an, die von diesem Cmdlet der Sitzung hinzugefügt werden. Die Dateien werden geladen, nachdem PowerShell die integrierten Formatierungs Dateien geladen hat.

Beim Formatieren von .NET-Objekten verwendet PowerShell die erste Formatierungs Definition, die für jeden .NET-Typ gefunden wird. Wenn Sie den **appendpath** -Parameter verwenden, durchsucht PowerShell die Daten aus den integrierten Dateien, bevor die Formatierungsdaten gefunden werden, die Sie hinzufügen.

Verwenden Sie diesen Parameter zum Hinzufügen einer Datei, die ein .NET-Objekt formatiert, auf das nicht in den integrierten Formatierungsdateien verwiesen wird.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSPath, Path

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Prepdpath

Gibt Formatierungs Dateien an, die von diesem Cmdlet der Sitzung hinzugefügt werden. Die Dateien werden geladen, bevor PowerShell die integrierten Formatierungs Dateien lädt.

Beim Formatieren von .NET-Objekten verwendet PowerShell die erste Formatierungs Definition, die für jeden .NET-Typ gefunden wird. Wenn Sie den **prepdpath** -Parameter verwenden, durchsucht PowerShell die Daten aus den Dateien, die Sie hinzufügen, bevor die Formatierungsdaten aus den integrierten Dateien gefunden werden.

Verwenden Sie diesen Parameter zum Hinzufügen einer Datei, die ein .NET-Objekt formatiert, auf das auch in den integrierten Formatierungsdateien verwiesen wird.

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

Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.
Das Cmdlet wird nicht ausgeführt.

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

Sie können eine Zeichenfolge, die den Anfüge Pfad enthält, über die Pipeline an übergeben `Update-FormatData` .

## AUSGABEN

### Keine

Das Cmdlet gibt keine Ausgabe zurück.

## HINWEISE

- `Update-FormatData` aktualisiert auch die Formatierungsdaten für Befehle in der Sitzung, die aus Modulen importiert wurden. Wenn die Formatierungs Datei für ein Modul geändert wird, können Sie einen Befehl ausführen, `Update-FormatData` um die Formatierungsdaten für importierte Befehle zu aktualisieren. Sie müssen das Modul nicht erneut importieren.

## VERWANDTE LINKS

[Get-FormatData](Get-FormatData.md)

[Export-FormatData](Export-FormatData.md)
