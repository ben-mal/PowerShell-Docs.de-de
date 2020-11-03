---
external help file: Microsoft.PowerShell.Archive-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Archive
ms.date: 02/20/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.archive/compress-archive?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Compress-Archive
ms.openlocfilehash: 7bf349c82133b275f0539db7b78c3583d00da31c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215116"
---
# Compress-Archive

## ZUSAMMENFASSUNG
Erstellt eine komprimierte oder gezippte Datei aus angegebenen Dateien und Verzeichnissen.

## SYNTAX

### Pfad (Standard)

```
Compress-Archive [-Path] <String[]> [-DestinationPath] <String> [-CompressionLevel <String>]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Pathwithupdate

```
Compress-Archive [-Path] <String[]> [-DestinationPath] <String> [-CompressionLevel <String>] -Update
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Pathwithforce

```
Compress-Archive [-Path] <String[]> [-DestinationPath] <String> [-CompressionLevel <String>] -Force
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Literalpathwithupdate

```
Compress-Archive -LiteralPath <String[]> [-DestinationPath] <String> [-CompressionLevel <String>]
 -Update [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Literalpathwithforce

```
Compress-Archive -LiteralPath <String[]> [-DestinationPath] <String> [-CompressionLevel <String>]
 -Force [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### LiteralPath

```
Compress-Archive -LiteralPath <String[]> [-DestinationPath] <String> [-CompressionLevel <String>]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Compress-Archive` Cmdlet wird eine komprimierte oder komprimierte Archivdatei aus einer oder mehreren angegebenen Dateien oder Verzeichnissen erstellt. Ein Archiv verpackt mehrere Dateien mit optionaler Komprimierung in eine einzelne ZIP-Datei, um die Verteilung und den Speicher zu vereinfachen. Eine Archivdatei kann mithilfe des Komprimierungs Algorithmus komprimiert werden, der durch den **CompressionLevel** -Parameter angegeben wird.

Das `Compress-Archive` Cmdlet verwendet die Microsoft .NET-API [System.IO.Compression.ZipArchive](/dotnet/api/system.io.compression.ziparchive) , um Dateien zu komprimieren.
Die maximale Dateigröße beträgt 2 GB, da die zugrunde liegende API eingeschränkt ist.

Einige Beispiele verwenden Verteilung, um die Zeilenlänge der Codebeispiele zu verringern. Weitere Informationen finden Sie unter [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).

## BEISPIELE

### Beispiel 1: Komprimieren von Dateien zum Erstellen einer Archivdatei

In diesem Beispiel werden Dateien aus unterschiedlichen Verzeichnissen komprimiert, und eine Archivdatei wird erstellt. Ein Platzhalter wird verwendet, um alle Dateien mit einer bestimmten Dateierweiterung zu erhalten. Die Archivdatei enthält keine Verzeichnisstruktur, da der **Pfad** nur Dateinamen angibt.

```powershell
$compress = @{
  Path = "C:\Reference\Draftdoc.docx", "C:\Reference\Images\*.vsd"
  CompressionLevel = "Fastest"
  DestinationPath = "C:\Archives\Draft.Zip"
}
Compress-Archive @compress
```

Der **path** -Parameter akzeptiert bestimmte Dateinamen und Dateinamen mit Platzhaltern `*.vsd` . Der **Pfad** verwendet eine durch Trennzeichen getrennte Liste, um Dateien aus unterschiedlichen Verzeichnissen abzurufen. Der Komprimierungs Grad ist **am schnellsten** , um die Verarbeitungszeit zu verkürzen. Der **DestinationPath** -Parameter gibt den Speicherort für die `Draft.zip` Datei an. Die `Draft.zip` Datei enthält `Draftdoc.docx` und alle Dateien mit einer `.vsd` Erweiterung.

### Beispiel 2: Komprimieren von Dateien mit einem literalpath

Dieses Beispiel komprimiert bestimmte benannte Dateien und erstellt eine neue Archivdatei. Die Archivdatei enthält keine Verzeichnisstruktur, da der **Pfad** nur Dateinamen angibt.

```powershell
$compress = @{
LiteralPath= "C:\Reference\Draft Doc.docx", "C:\Reference\Images\diagram2.vsd"
CompressionLevel = "Fastest"
DestinationPath = "C:\Archives\Draft.Zip"
}
Compress-Archive @compress
```

Absolute Pfad-und Dateinamen werden verwendet, da der **literalpath** -Parameter keine Platzhalter akzeptiert. Der **Pfad** verwendet eine durch Trennzeichen getrennte Liste, um Dateien aus unterschiedlichen Verzeichnissen abzurufen. Der Komprimierungs Grad ist **am schnellsten** , um die Verarbeitungszeit zu verkürzen. Der **DestinationPath** -Parameter gibt den Speicherort für die `Draft.zip` Datei an. Die `Draft.zip` Datei enthält nur `Draftdoc.docx` und `diagram2.vsd` .

### Beispiel 3: Komprimieren eines Verzeichnisses, das das Stammverzeichnis enthält

In diesem Beispiel wird ein Verzeichnis komprimiert und eine Archivdatei erstellt, die das Stammverzeichnis sowie alle zugehörigen Dateien und Unterverzeichnisse **enthält** . Die Archivdatei hat eine Verzeichnisstruktur, da der **Pfad** ein Stammverzeichnis angibt.

```powershell
Compress-Archive -Path C:\Reference -DestinationPath C:\Archives\Draft.zip
```

`Compress-Archive` verwendet den **path** -Parameter, um das Stammverzeichnis anzugeben `C:\Reference` . Der **DestinationPath** -Parameter gibt den Speicherort für die Archivdatei an. Das `Draft.zip` Archiv enthält das Stamm `Reference` Verzeichnis und alle zugehörigen Dateien und Unterverzeichnisse.

### Beispiel 4: Komprimieren eines Verzeichnisses, das das Stammverzeichnis ausschließt

In diesem Beispiel wird ein Verzeichnis komprimiert und eine Archivdatei erstellt, die das Stammverzeichnis **ausschließt** , da der **Pfad** ein Sternchen-Platzhalter ( `*` ) verwendet. Das Archiv enthält eine Verzeichnisstruktur, die die Dateien und Unterverzeichnisse des Stamm Verzeichnisses enthält.

```powershell
Compress-Archive -Path C:\Reference\* -DestinationPath C:\Archives\Draft.zip
```

`Compress-Archive` verwendet den **path** -Parameter, um das Stammverzeichnis `C:\Reference` mit einem Platzhalter Zeichen ( `*` ) anzugeben. Der **DestinationPath** -Parameter gibt den Speicherort für die Archivdatei an. Das `Draft.zip` Archiv enthält die Dateien und Unterverzeichnisse des Stamm Verzeichnisses. Das Stamm `Reference` Verzeichnis wird aus dem Archiv ausgeschlossen.

### Beispiel 5: komprimieren nur der Dateien in einem Stammverzeichnis

In diesem Beispiel werden nur die Dateien in einem Stammverzeichnis komprimiert, und eine Archivdatei wird erstellt. Das Archiv enthält keine Verzeichnisstruktur, da nur Dateien komprimiert werden.

```powershell
Compress-Archive -Path C:\Reference\*.* -DestinationPath C:\Archives\Draft.zip
```

`Compress-Archive` verwendet den **path** -Parameter, um das Stammverzeichnis mit einem Platzhalter vom Typ `C:\Reference` **Star-dot-Star** ( `*.*` ) anzugeben. Der **DestinationPath** -Parameter gibt den Speicherort für die Archivdatei an. Das `Draft.zip` Archiv enthält nur die `Reference` Dateien des Stamm Verzeichnisses, und das Stammverzeichnis wird ausgeschlossen.

### Beispiel 6: Verwenden der Pipeline zum Archivieren von Dateien

In diesem Beispiel werden Dateien über die Pipeline gesendet, um ein Archiv zu erstellen. Die Archivdatei enthält keine Verzeichnisstruktur, da der **Pfad** nur Dateinamen angibt.

```powershell
Get-ChildItem -Path C:\Reference\Afile.txt, C:\Reference\Images\Bfile.txt |
  Compress-Archive -DestinationPath C:\Archives\PipelineFiles.zip
```

`Get-ChildItem` verwendet den **path** -Parameter, um zwei Dateien aus unterschiedlichen Verzeichnissen anzugeben. Jede Datei wird durch ein **FileInfo** -Objekt dargestellt und an die Pipeline gesendet `Compress-Archive` .
Die beiden angegebenen Dateien werden in archiviert `PipelineFiles.zip` .

### Beispiel 7: Verwenden der Pipeline zum Archivieren eines Verzeichnisses

In diesem Beispiel wird ein Verzeichnis nach unten in der Pipeline gesendet, um ein Archiv zu erstellen. Dateien werden als **FileInfo** -Objekte und-Verzeichnisse als **DirectoryInfo** -Objekte gesendet. Die Verzeichnisstruktur des Archivs enthält nicht das Stammverzeichnis, aber seine Dateien und Unterverzeichnisse sind im Archiv enthalten.

```powershell
Get-ChildItem -Path C:\LogFiles | Compress-Archive -DestinationPath C:\Archives\PipelineDir.zip
```

`Get-ChildItem` verwendet den **path** -Parameter, um das Stamm `C:\LogFiles` Verzeichnis anzugeben. Jedes " **FileInfo** "-und " **DirectoryInfo** "-Objekt wird über die Pipeline gesendet.

`Compress-Archive` Fügt dem Archiv jedes Objekt hinzu `PipelineDir.zip` . Der **path** -Parameter ist nicht angegeben, da die Pipeline Objekte in der Parameter Position 0 empfangen werden.

### Beispiel 8: so wirkt sich die Rekursion auf Archive aus

Dieses Beispiel zeigt, wie die Rekursion Dateien im Archiv duplizieren kann. Wenn Sie z `Get-ChildItem` . b. mit dem **recurse** -Parameter verwenden. Bei Rekursions Prozessen werden alle **FileInfo** -und **DirectoryInfo** -Objekte über die Pipeline gesendet und dem Archiv hinzugefügt.

```powershell
Get-ChildItem -Path C:\TestLog -Recurse |
  Compress-Archive -DestinationPath C:\Archives\PipelineRecurse.zip
```

Das `C:\TestLog` Verzeichnis enthält keine Dateien. Sie enthält ein Unterverzeichnis mit `testsub` dem Namen, das die `testlog.txt` Datei enthält.

`Get-ChildItem` verwendet den **path** -Parameter, um das Stammverzeichnis anzugeben `C:\TestLog` . Der **recurse** -Parameter verarbeitet die Dateien und Verzeichnisse. Ein **DirectoryInfo** -Objekt wird für `testsub` und ein **FileInfo** -Objekt erstellt `testlog.txt` .

Jedes Objekt wird über die Pipeline an gesendet `Compress-Archive` . Der **DestinationPath** gibt den Speicherort für die Archivdatei an. Der **path** -Parameter ist nicht angegeben, da die Pipeline Objekte in der Parameter Position 0 empfangen werden.

In der folgenden Zusammenfassung werden die `PipelineRecurse.zip` Inhalte des Archivs beschrieben, die eine doppelte Datei enthalten:

- Das **DirectoryInfo** -Objekt erstellt das `testsub` Verzeichnis und enthält die `testlog.txt` Datei, die die ursprüngliche Verzeichnisstruktur widerspiegelt.
- Das **FileInfo** -Objekt erstellt ein Duplikat `testlog.txt` im Stamm des Archivs. Die doppelte Datei wird erstellt, da die Rekursion ein Datei Objekt an gesendet hat `Compress-Archive` . Dieses Verhalten wird erwartet, da jedes an die Pipeline gesendete Objekt dem Archiv hinzugefügt wird.

### Beispiel 9: Aktualisieren einer vorhandenen Archivdatei

In diesem Beispiel wird eine vorhandene Archivdatei, `Draft.Zip` , im `C:\Archives` Verzeichnis aktualisiert. In diesem Beispiel enthält die vorhandene Archivdatei das Stammverzeichnis und seine Dateien und Unterverzeichnisse.

```powershell
Compress-Archive -Path C:\Reference -Update -DestinationPath C:\Archives\Draft.Zip
```

Der Befehl wird `Draft.Zip` mit neueren Versionen vorhandener Dateien im `C:\Reference` Verzeichnis und seinen Unterverzeichnissen aktualisiert. Außerdem sind neue Dateien, die bzw. den Unterverzeichnissen hinzugefügt wurden, `C:\Reference` im aktualisierten `Draft.Zip` Archiv enthalten.

## PARAMETERS

### -CompressionLevel

Gibt an, wie viel Komprimierung beim Erstellen der Archivdatei angewendet werden soll. Die schnellere Komprimierung erfordert weniger Zeit zum Erstellen der Datei, kann jedoch zu größeren Dateigrößen führen.

Wenn dieser Parameter nicht angegeben wird, verwendet der Befehl den Standardwert, **optimal** .

Im folgenden sind die zulässigen Werte für diesen Parameter aufgeführt:

- **Schnellste** . Verwenden Sie die schnellste Komprimierungs Methode, um die Verarbeitungszeit zu verkürzen. Eine schnellere Komprimierung kann zu größeren Dateigrößen führen.
- **NoCompression** . Die Quelldateien werden nicht komprimiert.
- **Optimal** . Die Verarbeitungszeit hängt von der Dateigröße ab.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Optimal, NoCompression, Fastest

Required: False
Position: Named
Default value: Optimal
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

### -DestinationPath

Dieser Parameter ist erforderlich und gibt den Pfad zur Archiv Ausgabedatei an. Der **DestinationPath** muss den Namen der gezippten Datei und entweder den absoluten oder relativen Pfad zur ZIP-Datei enthalten.

Wenn der Dateiname in **DestinationPath** keine `.zip` Dateinamenerweiterung hat, fügt das Cmdlet die `.zip` Dateinamenerweiterung hinzu.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PathWithForce, LiteralPathWithForce
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Literalpath

Gibt den Pfad oder die Pfade zu den Dateien an, die Sie der gezippten ZIP-Datei hinzufügen möchten. Im Gegensatz zum **path** -Parameter wird der Wert von **literalpath** genau so verwendet, wie er eingegeben wurde. Es werden keine Zeichen als Platzhalter interpretiert. Wenn der Pfad Escapezeichen enthält, schließen Sie jedes Escapezeichen in einfache Anführungszeichen ein, um PowerShell anzuweisen, Zeichen nicht als Escapesequenzen zu interpretieren.
Wenn Sie mehrere Pfade angeben und Dateien an mehreren Speicherorten in der ZIP-Ausgabedatei einschließen möchten, trennen Sie die Pfade durch Kommas.

```yaml
Type: System.String[]
Parameter Sets: LiteralPathWithUpdate, LiteralPathWithForce, LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru

Bewirkt, dass das Cmdlet ein Datei Objekt ausgibt, das die erstellte Archivdatei darstellt.

Dieser Parameter wurde in PowerShell 6,0 eingeführt.

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

### -Path

Gibt den Pfad oder die Pfade zu den Dateien an, die Sie der gezippten ZIP-Datei hinzufügen möchten. Wenn Sie mehrere Pfade angeben und Dateien an mehreren Speicherorten einschließen möchten, verwenden Sie Kommas, um die Pfade voneinander zu trennen.

Dieser Parameter akzeptiert Platzhalter Zeichen. Mit Platzhalter Zeichen können Sie Ihrer Archivdatei alle Dateien in einem Verzeichnis hinzufügen.

Die Verwendung von Platzhaltern mit einem Stammverzeichnis wirkt sich auf den Inhalt des Archivs aus:

- Um ein Archiv zu erstellen, das das Stammverzeichnis und alle zugehörigen Dateien und Unterverzeichnisse **enthält** , geben Sie das Stammverzeichnis im **Pfad** ohne Platzhalter an. Beispiel: `-Path C:\Reference`
- Um ein Archiv zu erstellen, das das Stammverzeichnis **ausschließt** , aber alle Dateien und Unterverzeichnisse zippt, verwenden Sie das Platzhalter Zeichen ( `*` ). Beispiel: `-Path C:\Reference\*`
- Um ein Archiv zu erstellen, das nur die Dateien im Stammverzeichnis zippt, verwenden Sie den Platzhalter **Star-dot-Star** ( `*.*` ). Unterverzeichnisse des Stamms sind nicht im Archiv enthalten. Beispiel: `-Path C:\Reference\*.*`

```yaml
Type: System.String[]
Parameter Sets: Path, PathWithUpdate, PathWithForce
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -Aktualisieren

Aktualisiert das angegebene Archiv, indem ältere Dateiversionen im Archiv durch neuere Dateiversionen ersetzt werden, die die gleichen Namen aufweisen. Sie können diesen Parameter auch hinzufügen, um einem vorhandenen Archivdateien hinzuzufügen.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PathWithUpdate, LiteralPathWithUpdate
Aliases:

Required: True
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

## EINGABEN

### System.String

Sie können eine Zeichenfolge, die einen Pfad enthält, über die Pipeline an eine oder mehrere Dateien übergeben.

## AUSGABEN

### System. IO. fileingefo

Das Cmdlet gibt nur ein **FileInfo** -Objekt zurück, wenn Sie den **passthru** -Parameter verwenden.

## HINWEISE

Durch die Verwendung von Rekursion und das Senden von Objekten in der Pipeline können Dateien im Archiv dupliziert werden. Wenn Sie z. b. `Get-ChildItem` mit dem **recurse** -Parameter verwenden, werden alle **FileInfo** -und **DirectoryInfo** -Objekte, die über die Pipeline gesendet werden, dem Archiv hinzugefügt.

Die [ZIP-Datei Spezifikation](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) gibt keine Standardmethode zum Codieren von Dateinamen an, die nicht-ASCII-Zeichen enthalten. Das `Compress-Archive` Cmdlet verwendet UTF-8-Codierung. Andere ZIP-Archiv Tools verwenden möglicherweise ein anderes Codierungsschema. Beim Extrahieren von Dateien mit Dateinamen, die nicht mit UTF-8-Codierung gespeichert werden, `Expand-Archive` verwendet den im Archiv gefundenen Rohwert. Dies kann zu einem Dateinamen führen, der sich von dem im Archiv gespeicherten Quell Dateinamen unterscheidet.

## VERWANDTE LINKS

[Expand-Archive](Expand-Archive.md)

[Get-ChildItem](../Microsoft.PowerShell.Management/Get-ChildItem.md)
