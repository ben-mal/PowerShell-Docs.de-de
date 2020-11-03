---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/out-gridview?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-GridView
ms.openlocfilehash: 73a2685947ac5980adab99a3f101a0c1f7f809d2
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210332"
---
# Out-GridView

## ZUSAMMENFASSUNG
Sendet die Ausgabe an eine interaktive Tabelle in einem separaten Fenster.

## SYNTAX

### Passthru (Standard)

```
Out-GridView [-InputObject <PSObject>] [-Title <String>] [-PassThru] [<CommonParameters>]
```

### Warten

```
Out-GridView [-InputObject <PSObject>] [-Title <String>] [-Wait] [<CommonParameters>]
```

### OutputMode

```
Out-GridView [-InputObject <PSObject>] [-Title <String>] [-OutputMode <OutputModeOption>]
 [<CommonParameters>]
```

## DESCRIPTION

Das- `Out-GridView` Cmdlet sendet die Ausgabe von einem Befehl an ein Raster Ansichts Fenster, in dem die Ausgabe in einer interaktiven Tabelle angezeigt wird.

Da dieses Cmdlet eine Benutzeroberfläche erfordert, funktioniert es nicht unter Windows Server Core oder Windows Nano Server.

Sie können die folgenden Funktionen der Tabelle verwenden, um Ihre Daten zu überprüfen:

- Ausblenden, anzeigen und Neuanordnen von Spalten
- Zeilen sortieren
- Schnelles Filtern
- Kriterien-Filter hinzufügen
- Kopieren und Einfügen

Vollständige Anweisungen finden Sie im Abschnitt " [Hinweise](#notes) " in diesem Artikel.

> [!NOTE]
> Dieses Cmdlet wurde in PowerShell 7 erneut eingeführt. Dieses Cmdlet ist nur auf Windows-Systemen verfügbar, die den Windows-Desktop unterstützen. Eine plattformübergreifende Version dieses Cmdlets finden Sie unter dem [graphicaltools](https://www.powershellgallery.com/packages/Microsoft.PowerShell.GraphicalTools) -Modul in der PowerShell-Katalog.

## BEISPIELE

### Beispiel 1: Ausgabeprozesse in einer Rasteransicht

Dieses Beispiel ruft die Prozesse ab, die auf dem lokalen Computer ausgeführt werden, und sendet diese an ein Raster Ansichts Fenster.

```powershell
Get-Process | Out-GridView
```

### Beispiel 2: Verwenden einer Variablen, um Prozesse an eine Rasteransicht auszugeben

In diesem Beispiel werden auch die Prozesse abgerufen, die auf dem lokalen Computer ausgeführt werden und an ein Raster Ansichts Fenster gesendet werden.

```powershell
$P = Get-Process
$P | Out-GridView
```

Die Ausgabe des `Get-Process` Cmdlets wird in der Variablen gespeichert `$P` . Anschließend `$P` wird an weitergeleitet `Out-GridView` .

### Beispiel 3: Anzeigen ausgewählter Eigenschaften in einer Rasteransicht

In diesem Beispiel werden die ausgewählten Eigenschaften der ausgelaufenden Prozesse in einer Rasteransicht angezeigt.

```powershell
Get-Process | Select-Object -Property Name, WorkingSet, PeakWorkingSet |
  Sort-Object -Property WorkingSet -Descending | Out-GridView
```

Die Ausgabe von `Get-Process` wird an weitergeleitet, `Select-Object` um die Eigenschaften **Name** , **Workingset** und **Peer Share Workingset** auszuwählen. Ein weiterer Pipeline Operator sendet die gefilterten Objekte an das `Sort-Object` Cmdlet, um Sie in absteigender Reihenfolge nach dem Wert der **Workingset** -Eigenschaft zu sortieren.
Anschließend werden die sortierten Ergebnisse an weitergeleitet `Out-GridView` . Sie können nun die Funktionen der Rasteransicht verwenden, um die Daten zu durchsuchen, zu sortieren und zu filtern.

### Beispiel 4: Speichern der Ausgabe in einer Variablen und anschließende Ausgabe einer Rasteransicht

In diesem Beispiel wird die Ausgabe des Cmdlets in einer Variablen gespeichert und dann an gesendet `Out-GridView` .

```powershell
($A = Get-ChildItem -Path $PSHOME -Recurse) | Out-GridView
```

`Get-ChildItem` Ruft alle Dateien im PowerShell-Installationsverzeichnis und seinen Unterverzeichnissen mithilfe der `$PSHOME` automatischen Variablen ab. Die Klammern im Befehl bestimmen die Reihenfolge der Vorgänge. Folglich wird die Ausgabe des `Get-ChildItem` Befehls in der Variablen gespeichert, `$A` bevor Sie an gesendet wird `Out-GridView` .

### Beispiel 5: Ausgabeprozesse für einen angegebenen Computer in einer Rasteransicht

In diesem Beispiel werden die Prozesse angezeigt, die auf dem Server01-Computer in einem Raster Ansichts Fenster ausgeführt werden.

```powershell
Get-Process -ComputerName "Server01" | ogv -Title "Processes - Server01"
```

Der Prüfer verwendet `ogv` , d. h. den Alias für das `Out-GridView` Cmdlet. Der **Title** -Parameter gibt den Fenstertitel an.

### Beispiel 6: Ausgeben von Daten von Remote Computern an eine Rasteransicht

Dieses Beispiel zeigt, wie Daten, die von Remote Computern gesammelt werden, an gesendet werden `Out-GridView` .

```powershell
Invoke-Command -ComputerName S1, S2, S3 -ScriptBlock {Get-Culture} | Out-GridView
```

`Invoke-Command` wird `Get-Culture` auf drei Remote Computern ausgeführt. Die resultierenden Daten werden an weitergeleitet `Out-GridView` . Beachten Sie, dass der Skriptblock, der auf dem Remote Computer ausgeführt wird, den Befehl nicht enthält `Out-GridView` . Wenn dies der Fall war, würde der Befehl bei dem Versuch fehlschlagen, ein Rasteransichtsfenster auf jedem Remotecomputer zu öffnen.

### Beispiel 7: übergeben von mehreren Elementen durch `Out-GridView`

In diesem Beispiel können Sie mehrere Prozesse aus dem- `Out-GridView` Fenster auswählen. Die Prozesse, die Sie auswählen, werden an den Befehl übermittelt `Export-Csv` und in die `ProcessLog.csv` Datei geschrieben.

```powershell
Get-Process | Out-GridView -PassThru | Export-Csv -Path .\ProcessLog.csv
```

Der **passthru** -Parameter von `Out-GridView` ermöglicht das Senden mehrerer Elemente in der Pipeline. Der **PassThru** -Parameter entspricht der Verwendung des **Multiple** -Werts im **OutputMode** -Parameter.

### Beispiel 8: Erstellen einer Windows-Verknüpfung zu `Out-GridView`

In diesem Beispiel wird gezeigt, wie der **Wait** -Parameter von verwendet wird, `Out-GridView` um eine Windows-Verknüpfung mit dem-Fenster zu erstellen `Out-GridView` .

```powershell
pwsh -Command "Get-Service | Out-GridView -Wait"
```

Diese Befehlszeile kann in einer Windows-Verknüpfung verwendet werden. Ohne den **Wait** -Parameter würde PowerShell beendet werden, sobald das `Out-GridView` Fenster geöffnet ist, wodurch das `Out-GridView` Fenster fast sofort geschlossen wird.

## PARAMETERS

### -InputObject

Gibt das Objekt an, das das Cmdlet als Eingabe akzeptiert `Out-GridView` .

Wenn Sie den **Inputobject** -Parameter verwenden, um eine Auflistung von Objekten an zu senden `Out-GridView` , `Out-GridView` behandelt die Auflistung als ein Auflistungs Objekt und zeigt eine Zeile an, die die Auflistung darstellt. Um jedes Objekt in der Auflistung anzuzeigen, verwenden Sie einen Pipeline Operator (|), um Objekte an zu senden `Out-GridView` .

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

### -Outputmode

Gibt die Elemente an, die das interaktive Fenster die Pipeline als Eingabe an andere Befehle sendet.
Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert. Um Elemente aus dem interaktiven Fenster über die Pipeline zu senden, klicken Sie auf die Elemente und dann auf „OK“.

Die Werte für diesen Parameter bestimmen, wie viele Elemente Sie über die Pipeline senden können.

- Keine  Keine Elemente. Dies ist der Standardwert.
- Einfach. Ein Element oder null Elemente. Verwenden Sie diesen Wert, wenn der nächste Befehl nur jeweils ein Eingabeobjekt akzeptieren kann.
- Mehr. Null, eines oder viele Elemente. Verwenden Sie diesen Wert, wenn der nächste Befehl mehrere Eingabeobjekte akzeptieren kann. Dieser Wert entspricht dem **Passthru** -Parameter.

```yaml
Type: Microsoft.PowerShell.Commands.OutputModeOption
Parameter Sets: OutputMode
Aliases:
Accepted values: None, Single, Multiple

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru

Gibt an, dass das Cmdlet Elemente aus dem interaktiven Fenster über die Pipeline als Eingabe an andere Befehle sendet. Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert. Dieser Parameter entspricht der Verwendung des **Multiple** -Werts im **OutputMode** -Parameter.

Um Elemente aus dem interaktiven Fenster über die Pipeline zu senden, klicken Sie auf die Elemente und dann auf „OK“. Das Klicken bei gedrückter UMSCHALTTASTE und STRG-TASTE wird unterstützt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PassThru
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Title

Gibt den Text an, der in der Titelleiste des `Out-GridView` Fensters angezeigt wird. Standardmäßig wird in der Titelleiste der Befehl angezeigt, der aufruft `Out-GridView` .

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

### -Wait

Gibt an, dass das Cmdlet die Eingabeaufforderung unterdrückt und verhindert, dass Windows PowerShell `Out-GridView` geschlossen wird, bis das Fenster geschlossen wird. Standardmäßig wird die Eingabeaufforderung zurückgegeben, wenn das `Out-GridView` Fenster geöffnet wird.

Mit dieser Funktion können Sie die `Out-GridView` Cmdlets in Windows-Tastenkombinationen verwenden. Wenn `Out-GridView` in einer Verknüpfung ohne den **Wait** -Parameter verwendet wird, wird das `Out-GridView` Fenster nur vorübergehend angezeigt, bevor PowerShell geschlossen wird.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Wait
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

### System. Management. Automation. psobject

Sie können jedes beliebige Objekt an dieses Cmdlet senden.

## AUSGABEN

### Keine

Normalerweise gibt keine- `Out-GridView` Objekte zurück. Wenn Sie den **passthru** -Parameter verwenden, werden die Objekte, die die ausgewählten Zeilen darstellen, an die Pipeline zurückgegeben.

## HINWEISE

Sie können keinen Remotebefehl verwenden, um ein Rasteransichtsfenster auf einem anderen Computer zu öffnen.

Die Befehlsausgabe, die Sie an senden, `Out-GridView` kann nicht mit den- `Format` Cmdlets formatiert werden, z `Format-Table` . b.-oder- `Format-Wide` Cmdlets. Verwenden Sie das-Cmdlet, um Eigenschaften auszuwählen `Select-Object` .

Die deserialisierte Ausgabe von Remotebefehlen ist möglicherweise im Rasteransichtsfenster nicht ordnungsgemäß formatiert.

**Tastenkombinationen für**`Out-GridView`

|              Taste              |                                   Aktion                                    |
| --------------------------------------- | -------------------------------------------------------------------------------------------- |
| <kbd>Registerkarte</kbd>                          | Verschiebt den Cursor aus dem Feld " **Filter** " in das Menü " **Kriterien hinzufügen** " in die Tabelle und wieder zurück. |
| <kbd>Oben</kbd>                      | Verschieben Sie eine Zeile nach oben. Wechselt zu Spaltenüberschriften aus der ersten Daten Zeile.                             |
| <kbd>Nach unten</kbd>                    | Eine Zeile nach unten verschieben.                                                                           |
| <kbd>Links</kbd>                    | Verschieben Sie in der Spalten Kopfzeile eine Spalte nach links.                                                  |
| <kbd>RightArrow</kbd>                   | Verschieben Sie in Spalten Kopfzeile eine Spalte nach rechts.                                                 |
| <kbd>Contextmenukey</kbd>               | In der Spalten Kopfzeile wird die Option Spalten auswählen angezeigt.                                    |
| <kbd>Eingabe</kbd> oder <kbd>LEERTASTE</kbd> | Sortieren Sie in der Spalten Kopfzeile die Spaltendaten (A-Z, z-A umschalten).                                    |

**Verwenden der Funktionen des Raster Ansichts Fensters**

**So blenden Sie eine Spalte aus oder ein:**

1. Klicken Sie mit der rechten Maustaste auf eine beliebige Spaltenüberschrift, **und klicken Sie**
2. Verwenden Sie im Dialogfeld **Spalten auswählen** die Pfeiltasten, um die Spalten zwischen den ausgewählten Spalten in die Felder Verfügbare Spalten zu verschieben. Im Raster Ansichts Fenster werden nur Spalten im Feld **Spalten auswählen** angezeigt.

**So sortieren Sie Spalten neu:**

Sie können Spalten per Drag & amp; Drop an die gewünschte Position verschieben. Oder führen Sie die folgenden Schritte aus:

1. Klicken Sie mit der rechten Maustaste auf eine beliebige Spaltenüberschrift, **und klicken Sie**
2. Verwenden Sie im Dialogfeld **Spalten auswählen** die Schaltflächen nach **oben** und nach **unten** , um die Spalten neu zu sortieren. Spalten am oberen Rand der Liste werden links neben den Spalten am Ende der Liste im Rasteransichtsfenster angezeigt.

**Sortieren von Tabellendaten**

- Um die Daten zu sortieren, klicken Sie auf eine Spaltenüberschrift.
- Um die Sortierreihenfolge zu ändern, klicken Sie erneut auf die Spaltenüberschrift. Bei jedem Klicken auf die gleiche Überschrift, wird die Sortierreihenfolge zwischen aufsteigender in absteigender Reihenfolge umgeschaltet. Die aktuelle Reihenfolge wird durch ein Dreieck in der Spaltenüberschrift angezeigt.

**Auswählen von Tabellendaten**

- Um eine Zeile auszuwählen, wählen Sie die Zeile aus, oder verwenden Sie den Pfeil nach oben oder nach unten, um zur Zeile zu navigieren.
- Drücken Sie <kbd>STRG</kbd>A, um alle Zeilen (außer der Kopfzeile) auszuwählen + <kbd>A</kbd>.
- Wenn Sie aufeinander folgende Zeilen auswählen möchten, halten Sie die <kbd>UMSCHALT</kbd> Taste gedrückt, während Sie auf die Zeilen klicken oder die Pfeiltasten verwenden.
- Zum auswählen nicht aufeinander folgender Zeilen drücken Sie die <kbd>STRG</kbd> -Taste, und klicken Sie auf diese Option, um der Auswahl eine Zeile hinzuzufügen.
- Sie können keine Spalten auswählen, und Sie können nicht die gesamte Spaltenüberschriftszeile auswählen.

**Kopieren von Zeilen**

- Wenn Sie eine oder mehrere Zeilen aus der Tabelle kopieren möchten, wählen Sie die Zeilen aus, und drücken Sie dann STRG + C.

  Sie können die Daten in ein anderes Text- oder Tabellenkalkulationsprogramm einfügen. Sie können keine Spalten oder Teile von Zeilen kopieren, und Sie können nicht die Spaltenüberschriftszeile kopieren.

**Suchen in der Tabelle (schnell Filter)**

Verwenden Sie das Feld Filter, um nach Daten in der Tabelle zu suchen. Wenn Sie den Suchtext in das Feld eingeben, werden nur Elemente, die den eingegebenen Text enthalten, in der Tabelle angezeigt.

- Suchen Sie nach Text. Um in der Tabelle nach Text zu suchen, geben Sie im Filter Feld den Text ein, der gesucht werden soll.
- Suchen Sie nach mehreren Wörtern. Um in der Tabelle nach mehreren Wörtern zu suchen, geben Sie die Wörter durch Leerzeichen voneinander getrennt ein. `Out-GridView` zeigt Zeilen an, die alle Wörter (logisches und) enthalten.
- Suchen Sie nach literalen Ausdrücken. Um Ausdrücke zu suchen, die Leerzeichen oder Sonderzeichen enthalten, schließen Sie den Ausdruck in Anführungszeichen ein. `Out-GridView` zeigt Zeilen an, die eine genaue Entsprechung für den Ausdruck enthalten.
- In Spalten suchen. Um in mindestens einer Spalte nach Text zu suchen, verwenden Sie das folgende Format:

  `<column>:<text> [<column>:<text>] ...`

  Wenn Sie z. b. "NET" in der Spalte " **Display Name** " suchen möchten, geben Sie im Feld **Filter** Folgendes ein:

  `displayname:net`

  Wenn Sie in den Spalten **Display Name** und **Name** nach Zeilen mit "NET" suchen möchten, geben Sie im Feld **Filter** Folgendes ein:

  `displayname:net name:net`

- Deaktivieren Sie die Suche. Um die gesamte Tabelle erneut anzuzeigen, klicken Sie auf die rote X-Schaltfläche in der oberen rechten Ecke des **Filter** Felds, oder löschen Sie den Text aus dem **Filter** Feld.

**Verwenden von Kriterien zum Filtern der Tabelle**

Sie können Regeln oder Kriterien verwenden, um zu bestimmen, welche Elemente in der Tabelle angezeigt werden. Elemente werden nur angezeigt, wenn Sie alle von Ihnen festgelegten Kriterien erfüllen. Die verfügbaren Kriterien werden durch die Eigenschaften der Objekte, die im Rasteransichtsfenster angezeigt werden, und die .NET Framework-Typen der Eigenschaften bestimmt.

Jedes Kriterium weist das folgende Format auf:

`<column> <operator> <value>`

Kriterien für die verschiedenen Eigenschaften sind durch **und** verbunden. Kriterien für die gleiche Eigenschaft sind durch **oder** verbunden. Sie können die logischen Verbindungen nicht ändern.

Die Kriterien wirken sich nur auf die Anzeige aus. Es werden keine Elemente aus der Tabelle gelöscht.

**Hinzufügen von Kriterien**

1. Um die Menü Schaltfläche **Kriterien hinzufügen** anzuzeigen, klicken Sie in der oberen rechten Ecke des Fensters auf den Erweiterungs Pfeil.
2. Klicken Sie auf die Menü Schaltfläche **Kriterien hinzufügen** .
3. Klicken Sie, um Spalten (Eigenschaften) auszuwählen. Sie können mindestens eine Eigenschaft auswählen.
4. Wenn Sie die Eigenschaften ausgewählt haben, klicken Sie auf die Schaltfläche **Hinzufügen** .
5. Klicken Sie auf **Abbrechen** , um die Ergänzungen abzubrechen.
6. Um weitere Kriterien hinzuzufügen, klicken Sie erneut auf die Schaltfläche **Kriterien hinzufügen** .

**Bearbeiten eines Kriteriums**

- Um einen Operator zu ändern, klicken Sie auf den Wert blauer Operator, und wählen Sie dann in der Dropdown Liste einen anderen Operator aus.
- Geben Sie einen Wert in das Feld Wert ein, um einen Wert einzugeben oder zu ändern. Wenn Sie einen ungültigen Wert eingeben, wird ein kreisförmiges X-Symbol angezeigt. Ändern Sie den Wert, um dies zu entfernen.
- Fügen Sie zum Erstellen einer- **oder** -Anweisung ein Kriterium mit derselben Eigenschaft hinzu.

**Löschen von Kriterien**

- Um die ausgewählten Kriterien zu löschen, klicken Sie neben jedem Kriterium auf das rote X.
- Wenn Sie alle Kriterien löschen möchten, klicken Sie auf die Schaltfläche **alle** löschen.

## VERWANDTE LINKS

[Out-File](Out-File.md)

[Out-Printer](Out-Printer.md)

[Out-String](Out-String.md)
