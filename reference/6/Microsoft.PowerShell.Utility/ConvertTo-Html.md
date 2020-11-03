---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertto-html?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-Html
ms.openlocfilehash: 92413bae22e7783cd8a444d08df002336da4d0a8
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2020
ms.locfileid: "93219444"
---
# ConvertTo-Html

## ZUSAMMENFASSUNG
Konvertiert .NET-Objekte in HTML, die in einem Webbrowser angezeigt werden kann.

## SYNTAX

### Seite (Standard)

```
ConvertTo-Html [-InputObject <PSObject>] [[-Property] <Object[]>] [[-Body] <String[]>]
 [[-Head] <String[]>] [[-Title] <String>] [-As <String>] [-CssUri <Uri>] [-PostContent <String[]>]
 [-PreContent <String[]>] [-Meta <Hashtable>] [-Charset <String>] [-Transitional]
 [<CommonParameters>]
```

### Fragment

```
ConvertTo-Html [-InputObject <PSObject>] [[-Property] <Object[]>] [-As <String>] [-Fragment]
 [-PostContent <String[]>] [-PreContent <String[]>] [<CommonParameters>]
```

## DESCRIPTION

Das- `ConvertTo-Html` Cmdlet konvertiert .NET-Objekte in HTML, die in einem Webbrowser angezeigt werden können. Sie können dieses Cmdlet verwenden, um die Ausgabe eines Befehls auf einer Webseite anzuzeigen.

Sie können die Parameter von verwenden `ConvertTo-Html` , um Objekteigenschaften auszuwählen, ein Tabellen-oder Listenformat anzugeben, den Titel der HTML-Seite anzugeben, Text vor und nach dem Objekt hinzuzufügen und nur das Tabellen-oder Listen Fragment anstelle einer Strict DTD-Seite zurückzugeben.

Wenn Sie mehrere Objekte an senden `ConvertTo-Html` , erstellt PowerShell die Tabelle (oder Liste) auf Grundlage der Eigenschaften des ersten Objekts, das Sie übermitteln. Wenn die übrigen Objekte nicht über eine der angegebenen Eigenschaften verfügen, ist der Eigenschaftenwert dieses Objekts eine leere Zelle. Wenn die übrigen Objekte zusätzliche Eigenschaften aufweisen, sind diese Eigenschaftenwerte nicht in der Datei enthalten.

## BEISPIELE

### Beispiel 1: Erstellen einer Webseite zum Anzeigen des Datums

```powershell
ConvertTo-Html -InputObject (Get-Date)
```

Dieser Befehl erstellt eine HTML-Seite, die die Eigenschaften des aktuellen Datums anzeigt. Er verwendet den **Inputobject** -Parameter, um die Ergebnisse eines `Get-Date` Befehls an das `ConvertTo-Html` Cmdlet zu übermitteln.

### Beispiel 2: Erstellen einer Webseite zum Anzeigen von PowerShell-Aliasen

```powershell
Get-Alias | ConvertTo-Html | Out-File aliases.htm
Invoke-Item aliases.htm
```

Dieser Befehl erstellt eine HTML-Seite, auf der die PowerShell-Aliase in der aktuellen Konsole aufgeführt sind.

Der Befehl verwendet das `Get-Alias` Cmdlet, um die Aliase zu erhalten. Der Pipeline Operator ( `|` ) wird verwendet, um die Aliase an das `ConvertTo-Html` Cmdlet zu senden, das die HTML-Seite erstellt. Der Befehl verwendet auch das `Out-File` Cmdlet, um den HTML-Code an die Datei zu senden `aliases.htm` .

### Beispiel 3: Erstellen einer Webseite zum Anzeigen von PowerShell-Ereignissen

```powershell
`Get-EventLog` -LogName "Windows PowerShell" | ConvertTo-Html | Out-File pslog.htm
```

Dieser Befehl erstellt eine HTML-Seite mit `pslog.htm` dem Namen, auf der die Ereignisse im Windows PowerShell-Ereignisprotokoll auf dem lokalen Computer angezeigt werden.

Er verwendet das `Get-EventLog` Cmdlet, um die Ereignisse im Windows PowerShell-Protokoll zu erhalten, und verwendet dann den Pipeline Operator ( `|` ), um die Ereignisse an das `ConvertTo-Html` Cmdlet zu senden. Der Befehl verwendet auch das `Out-File` Cmdlet, um den HTML-Code an die Datei zu senden `pslog.htm` .

Der Befehl verwendet auch das `Out-File` Cmdlet, um den HTML-Code an die Datei zu senden `pslog.htm` .

### Beispiel 4: Erstellen einer Webseite zum Anzeigen von Prozessen

```powershell
Get-Process |
  ConvertTo-Html -Property Name, Path, Company -Title "Process Information" |
    Out-File proc.htm
Invoke-Item proc.htm
```

Diese Befehle erstellen und öffnen eine HTML-Seite, die den Namen, Pfad und das Unternehmen der Prozesse auf dem lokalen Computer auflistet.

Der erste Befehl verwendet das `Get-Process` Cmdlet, um Objekte zu erhalten, die die Prozesse darstellen, die auf dem Computer ausgeführt werden. Der Befehl verwendet den Pipeline Operator ( `|` ), um die Prozess Objekte an das `ConvertTo-Html` Cmdlet zu senden.

Der Befehl verwendet den **Property** -Parameter, um drei Eigenschaften der Process-Objekte auszuwählen, die in die Tabelle eingeschlossen werden sollen. Der Befehl verwendet den **Title** -Parameter, um einen Titel für die HTML-Seite anzugeben. Der Befehl verwendet auch das `Out-File` Cmdlet, um das resultierende HTML an eine Datei mit dem Namen Proc.htm zu senden.

Der zweite Befehl verwendet das `Invoke-Item` Cmdlet, um `Proc.htm` im Standardbrowser zu öffnen.

### Beispiel 5: Erstellen einer Webseite zum Anzeigen von Dienst Objekten

```powershell
Get-Service | ConvertTo-Html -CssUri "test.css"
```

```Output
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN"  "https://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">
<html>
<head>
<title>HTML TABLE</title>
<link rel="stylesheet" type="text/css" href="test.css" />
...
```

Dieser Befehl erstellt eine HTML-Seite der Dienst Objekte, die vom `Get-Service` Cmdlet zurückgegeben werden. Der Befehl verwendet den **cssuri** -Parameter, um ein Cascading Stylesheet für die HTML-Seite anzugeben.

Der **cssuri** -Parameter fügt dem resultierenden HTML-Code ein zusätzliches `<link rel="stylesheet" type="text/css" href="test.css">` Tag hinzu. Das HREF-Attribut im Tag enthält den Namen des Stylesheets.

### Beispiel 6: Erstellen einer Webseite zum Anzeigen von Dienst Objekten

```powershell
Get-Service | ConvertTo-Html -As LIST | Out-File services.htm
```

Dieser Befehl erstellt eine HTML-Seite der Dienst Objekte, die vom `Get-Service` Cmdlet zurückgegeben werden. Der Befehl verwendet den **As** -Parameter, um ein Listenformat anzugeben. Das-Cmdlet `Out-File` sendet das resultierende HTML an die `Services.htm` Datei.

### Beispiel 7: Erstellen einer Webtabelle für das aktuelle Datum

```powershell
Get-Date | ConvertTo-Html -Fragment
```

```Output
<table>
<colgroup>...</colgroup>
<tr><th>DisplayHint</th><th>DateTime</th><th>Date</th><th>Day</th><th>DayOfWeek</th><th>DayOfYear</th><th>Hour</th>
<th>Kind</th><th>Millisecond</th><th>Minute</th><th>Month</th><th>Second</th><th>Ticks</th><th>TimeOfDay</th><th>Year</th></tr>
<tr><td>DateTime</td><td>Monday, May 05, 2008 10:40:04 AM</td><td>5/5/2008 12:00:00 AM</td><td>5</td><td>Monday</td>
<td>126</td><td>10</td><td>Local</td><td>123</td><td>40</td><td>5</td><td>4</td><td>633455808041237213</td><td>10:40:04.12
37213</td><td>2008</td></tr>
</table>
```

Dieser Befehl verwendet `ConvertTo-Html` , um eine HTML-Tabelle des aktuellen Datums zu generieren. Der Befehl verwendet das `Get-Date` Cmdlet, um das aktuelle Datum zu erhalten. Er verwendet einen Pipeline Operator (|), um die Ergebnisse an das `ConvertTo-Html` Cmdlet zu senden.

Der- `ConvertTo-Html` Befehl enthält den **Fragment** -Parameter, der die Ausgabe auf eine HTML-Tabelle beschränkt. Daher werden die anderen Elemente einer HTML-Seite wie die `<HEAD>`- und `<BODY>`-Tags ausgelassen.

### Beispiel 8: Erstellen einer Webseite zum Anzeigen von PowerShell-Ereignissen

```powershell
Get-EventLog -Log "Windows PowerShell" | ConvertTo-Html -Property id, level, task
```

Dieser Befehl verwendet das `Get-EventLog` Cmdlet, um Ereignisse aus dem Windows PowerShell-Ereignisprotokoll zu erhalten.

Er verwendet einen Pipeline Operator ( `|` ), um die Ereignisse an das `ConvertTo-Html` Cmdlet zu senden, das die Ereignisse in das HTML-Format konvertiert.

Der `ConvertTo-Html` Befehl verwendet den **Property** -Parameter, um nur die Eigenschaften " **ID** ", " **Level** " und " **Task** " des Ereignisses auszuwählen.

### Beispiel 9: Erstellen einer Webseite zum Anzeigen der angegebenen Dienste

```powershell
$htmlParams = @{
  Title = "Windows Services: Server01"
  Body = Get-Date
  PreContent = "<P>Generated by Corporate IT</P>"
  PostContent = "For details, contact Corporate IT."
}
Get-Service A* |
  ConvertTo-Html @htmlParams |
    Out-File Services.htm
Invoke-Item Services.htm
```

Mit diesem Befehl wird eine Webseite erstellt und geöffnet, auf der die Dienste auf dem Computer angezeigt werden, die mit beginnen. Sie verwendet die Parameter **Title** , **Body** , **precontent** und **postcontent** von, `ConvertTo-Html` um die Ausgabe anzupassen.

Der erste Teil des Befehls verwendet das- `Get-Service` Cmdlet, um die Dienste auf dem Computer zu erhalten, die mit beginnen. Der Befehl verwendet einen Pipeline Operator ( `|` ), um die Ergebnisse an das `ConvertTo-Html` Cmdlet zu senden. Der Befehl verwendet auch das `Out-File` Cmdlet, um die Ausgabe an die Services.htm Datei zu senden.

Ein Semikolon ( `;` ) beendet den ersten Befehl und startet einen zweiten Befehl, der das `Invoke-Item` Cmdlet verwendet, um die `Services.htm` Datei im Standardbrowser zu öffnen.

### Beispiel 10: Festlegen der Meta-Eigenschaften und des Zeichensatzes der HTML

```powershell
Get-Service | ConvertTo-HTML -Meta @{
  refresh=10
  author="Author's Name"
  keywords="PowerShell, HTML, ConvertTo-HTML"
} -Charset "UTF-8"
```

Dieser Befehl erstellt den HTML-Code für eine Webseite mit den Meta-Tags für die Aktualisierung, den Autor und die Schlüsselwörter.
Der Zeichensatz für die Seite ist auf UTF-8 festgelegt.

### Beispiel 11: Festlegen des HTML-Code auf XHTML-Übergangs-DTD

```powershell
Get-Service | ConvertTo-HTML -Transitional
```

Mit diesem Befehl wird der DOCTYPE des zurückgegebenen HTML-Code auf XHTML Transitional DTD festgelegt.

## PARAMETERS

### -AS

Bestimmt, ob das Objekt als Tabelle oder Liste formatiert ist. Gültige Werte sind **Table** und **List**. Der Standardwert ist **Table**.

Der **Tabellen** Wert generiert eine HTML-Tabelle, die dem PowerShell-Tabellenformat ähnelt. Die Kopfzeile zeigt die Eigenschaftennamen an. Jede Tabellenzeile stellt ein Objekt dar und zeigt die Werte des Objekts für jede Eigenschaft.

Der **Listen** Wert generiert eine zweispaltige HTML-Tabelle für jedes Objekt, das dem PowerShell-Listenformat ähnelt. Die erste Spalte zeigt den Namen der Eigenschaft an. In der zweiten Spalte wird der Eigenschafts Wert angezeigt.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Table, List

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Text

Gibt den Text an, der nach dem `<BODY>`-Starttag hinzugefügt wird. Standardmäßig enthält diese Position keinen Text.

```yaml
Type: System.String[]
Parameter Sets: Page
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Charset

Gibt den Text an, der dem öffnenden Tag hinzugefügt wird `<charset>` . Standardmäßig enthält diese Position keinen Text.

Dieser Parameter wurde in PowerShell 6,0 eingeführt.

```yaml
Type: System.String
Parameter Sets: Page
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Cssuri

Gibt den Uniform Resource Identifier (URI) des Cascading Style Sheet (CSS) an, das auf die HTML-Datei angewendet wird. Der URI ist in einem Stylesheet-Link in der Ausgabe enthalten.

```yaml
Type: System.Uri
Parameter Sets: Page
Aliases: cu, uri

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Fragment

Generiert nur eine HTML-Tabelle. Die Tags HTML, HEAD, TITLE und BODY werden ausgelassen.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Fragment
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Head

Gibt den Inhalt des `<HEAD>`-Tags an. Der Standardwert ist `<title\>HTML TABLE</title>`. Wenn Sie den **Head** -Parameter verwenden, wird der **Title** -Parameter ignoriert.

```yaml
Type: System.String[]
Parameter Sets: Page
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Gibt die Objekte an, die im HTML-Format dargestellt werden. Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, durch den die Objekte abgerufen werden.

Wenn Sie diesen Parameter verwenden, um mehrere Objekte zu senden, z. b. alle Dienste auf einem Computer, `ConvertTo-Html` erstellt eine Tabelle, in der die Eigenschaften einer Sammlung oder eines Arrays von Objekten angezeigt werden. Verwenden Sie zum Erstellen einer Tabelle der einzelnen Objekte den Pipeline-Operator, um die Objekte an zu übergeben `ConvertTo-Html` .

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Meta

Gibt den Text an, der dem öffnenden Tag hinzugefügt wird `<meta>` . Standardmäßig enthält diese Position keinen Text.

Dieser Parameter wurde in PowerShell 6,0 eingeführt.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: Page
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Postcontent

Gibt Text an, der nach dem `</TABLE>`-Endtag hinzugefügt wird. Standardmäßig enthält diese Position keinen Text.

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

### -Vorab Inhalt

Gibt den Text an, der vor dem `<TABLE>`-Starttag hinzugefügt wird. Standardmäßig enthält diese Position keinen Text.

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

### -Eigenschaft

Schließt die angegebenen Eigenschaften der Objekte im HTML-Code ein. Der Wert des **Property** -Parameters kann eine neue berechnete Eigenschaft sein. Die berechnete Eigenschaft kann ein Skriptblock oder eine Hash Tabelle sein. Gültige Schlüssel-Wert-Paare sind:

- Name (oder Bezeichnung): `<string>` (hinzugefügt in PowerShell 6. x)
- Ausdruck `<string>` oder `<script block>`
- FormatString `<string>`
- Width- `<int32>` -muss größer sein als `0`
- Der Ausrichtungs Wert kann `Left` , `Center` oder sein. `Right`

Weitere Informationen finden Sie unter [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Title

Gibt einen Titel für die HTML-Datei an, d. h. den Text zwischen den `<TITLE>`-Tags.

```yaml
Type: System.String
Parameter Sets: Page
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Transitional

Ändert den **DOCTYPE** in **XHTML Transitional DTD** , der Standard **DOCTYPE** ist **XHTML strict DTD**.

Dieser Parameter wurde in PowerShell 6,0 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Page
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System. Management. Automation. psobject

Sie können ein beliebiges .NET-Objekt an übergeben `ConvertTo-Html` .

## AUSGABEN

### System. String-oder System.Xml.Xml-Dokument

`ConvertTo-Html` gibt eine Reihe von Zeichen folgen zurück, die gültige HTML enthalten.

## HINWEISE

Um dieses Cmdlet zu verwenden, übergeben Sie ein oder mehrere Objekte an das Cmdlet, oder verwenden Sie den **Inputobject** -Parameter, um das Objekt anzugeben. Wenn die Eingabe aus mehreren Objekten besteht, ist die Ausgabe dieser beiden Methoden sehr unterschiedlich.

- Wenn Sie mehrere Objekte an ein Cmdlet weiterreichen, sendet PowerShell die Objekte nacheinander an das Cmdlet. Daher wird von `ConvertTo-Html` eine Tabelle erstellt, in der die einzelnen Objekte angezeigt werden. Wenn Sie beispielsweise die Prozesse auf einem Computer an weiterleiten `ConvertTo-Html` , zeigt die resultierende Tabelle alle Prozesse an.

- Wenn Sie den **Inputobject** -Parameter verwenden, um mehrere Objekte zu senden, `ConvertTo-Html` empfängt diese Objekte als Sammlung oder als Array. Daher wird eine Tabelle mit dem Array und seinen Eigenschaften erstellt, nicht mit den Elementen im Array. Wenn Sie z. b. **Inputobject** verwenden, um die Prozesse auf einem Computer an zu übermitteln `ConvertTo-Html` , zeigt die resultierende Tabelle ein Objekt Array und seine Eigenschaften an.

  Um die XHTML strict DTD einzuhalten, wird das DOCTYPE-Tag entsprechend geändert:

   `<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN"   "https://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd"\>`

## VERWANDTE LINKS

[about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[ConvertTo-Csv](ConvertTo-Csv.md)

[ConvertTo-Json](ConvertTo-Json.md)

[ConvertTo-Xml](ConvertTo-Xml.md)

[Export-Clixml](Export-Clixml.md)

[Import-Clixml](Import-Clixml.md)
