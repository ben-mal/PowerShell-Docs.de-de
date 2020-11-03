---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/format-table?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Format-Table
ms.openlocfilehash: 1a90bfada7a21da24cd41ae2ceb8920f13c17c5d
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2020
ms.locfileid: "93219463"
---
# Format-Table

## ZUSAMMENFASSUNG
Formatiert die Ausgabe als Tabelle.

## SYNTAX

### Alle

```
Format-Table [-AutoSize] [-RepeatHeader] [-HideTableHeaders] [-Wrap] [[-Property] <Object[]>]
 [-GroupBy <Object>] [-View <String>] [-ShowError] [-DisplayError] [-Force] [-Expand <String>]
 [-InputObject <PSObject>] [<CommonParameters>]
```

## DESCRIPTION

Das- `Format-Table` Cmdlet formatiert die Ausgabe eines Befehls als Tabelle mit den ausgewählten Eigenschaften des Objekts in jeder Spalte. Der-Objekttyp bestimmt das Standardlayout und die Standardeigenschaften, die in den einzelnen Spalten angezeigt werden. Sie können den **Property** -Parameter verwenden, um die Eigenschaften auszuwählen, die Sie anzeigen möchten.

PowerShell verwendet Standardformatierer, um zu definieren, wie Objekttypen angezeigt werden. Sie können `.ps1xml` Dateien verwenden, um benutzerdefinierte Ansichten zu erstellen, die eine Ausgabe Tabelle mit angegebenen Eigenschaften anzeigen. Nachdem eine benutzerdefinierte Ansicht erstellt wurde, verwenden Sie den **View** -Parameter, um die Tabelle mit Ihrer benutzerdefinierten Ansicht anzuzeigen. Weitere Informationen zu Ansichten finden Sie unter [about_Format.ps1XML](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).

Sie können eine Hash Tabelle verwenden, um einem Objekt berechnete Eigenschaften hinzuzufügen, bevor Sie Sie anzeigen und die Spaltenüberschriften in der Tabelle angeben. Um eine berechnete Eigenschaft hinzuzufügen, verwenden Sie die **Eigenschaft** oder den **GroupBy** -Parameter. Weitere Informationen zu Hashtabellen finden Sie unter [about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md) (Informationen zu Hashtabellen).

## BEISPIELE

### Beispiel 1: Formatieren eines PowerShell-Hosts

In diesem Beispiel werden Informationen zum Host Programm für PowerShell in einer Tabelle angezeigt.

```powershell
Get-Host | Format-Table -AutoSize
```

Mit dem- `Get-Host` Cmdlet werden **System. Management. Automation. Internal. Host. internalhost** -Objekte abgerufen, die den Host darstellen. Die Objekte werden an die Pipeline gesendet `Format-Table` und in einer Tabelle angezeigt. Der **AutoSize** -Parameter passt die Spaltenbreite an, um das Abschneiden zu minimieren.

### Beispiel 2: Formatieren von Prozessen nach BasePriority

In diesem Beispiel werden Prozesse in Gruppen angezeigt, die dieselbe **BasePriority** -Eigenschaft aufweisen.

```powershell
Get-Process | Sort-Object -Property BasePriority | Format-Table -GroupBy BasePriority -Wrap
```

Das `Get-Process` -Cmdlet ruft Objekte ab, die jeden Prozess auf dem Computer darstellen, und sendet Sie an die Pipeline `Sort-Object` . Die Objekte werden in der Reihenfolge ihrer **BasePriority** -Eigenschaft sortiert.

Die sortierten Objekte werden über die Pipeline an gesendet `Format-Table` . Der **GroupBy** -Parameter ordnet die Prozessdaten basierend auf dem Wert Ihrer **BasePriority** -Eigenschaft in Gruppen an. Mit dem **Wrap** -Parameter wird sichergestellt, dass keine Daten abgeschnitten werden.

### Beispiel 3: Formatieren von Prozessen nach Startdatum

Dieses Beispiel zeigt Informationen zu den Prozessen, die auf dem Computer ausgeführt werden. Die Objekte werden sortiert und `Format-Table` verwenden eine Ansicht, um die Objekte nach Ihrem Startdatum zu gruppieren.

```powershell
Get-Process | Sort-Object StartTime | Format-Table -View StartTime
```

`Get-Process` Ruft die **System. Diagnostics. Process** -Objekte ab, die die Prozesse darstellen, die auf dem Computer ausgeführt werden. Die Objekte werden über die Pipeline an gesendet `Sort-Object` und basierend auf der **StartTime** -Eigenschaft sortiert.

Die sortierten Objekte werden über die Pipeline an gesendet `Format-Table` . Der **View** -Parameter gibt die **StartTime** -Ansicht an, die in der PowerShell- `DotNetTypes.format.ps1xml` Datei für **System. Diagnostics. Process** -Objekte definiert ist. Die **StartTime** -Sicht konvertiert die Startzeit der einzelnen Prozesse in ein kurzes Datum und gruppiert dann die Prozesse nach dem Startdatum.

Die `DotNetTypes.format.ps1xml` Datei enthält eine **Prioritäts** Ansicht für Prozesse. Sie können eigene `format.ps1xml` Dateien mit benutzerdefinierten Ansichten erstellen.

### Beispiel 4: Verwenden einer benutzerdefinierten Ansicht für die Tabellenausgabe

In diesem Beispiel zeigt eine benutzerdefinierte Ansicht den Inhalt eines Verzeichnisses an. Die benutzerdefinierte Ansicht fügt der Tabellenausgabe für **System. IO. directeryinfo** -und **System. IO. FileInfo** -Objekte, die von erstellt werden, die Spalte " **Spalte** " hinzu `Get-ChildItem` .

Die benutzerdefinierte Ansicht in diesem Beispiel wurde aus der Ansicht erstellt, die im PowerShell-Quellcode definiert wurde. Weitere Informationen zu Ansichten und zum Code, der zum Erstellen der Ansicht dieses Beispiels verwendet wird, finden Sie unter [about_Format.ps1XML](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md#sample-xml-for-a-format-table-custom-view).

```powershell
Get-ChildItem  -Path C:\Test | Format-Table -View mygciview
```

```Output
    Directory: C:\Test

Mode                LastWriteTime              CreationTime         Length Name
----                -------------              ------------         ------ ----
d-----        11/4/2019     15:54       9/24/2019     15:54                Archives
d-----        8/27/2019     14:22       8/27/2019     14:22                Drawings
d-----       10/23/2019     09:38       2/25/2019     09:38                Files
-a----        11/7/2019     11:07       11/7/2019     11:07          11345 Alias.txt
-a----        2/27/2019     15:15       2/27/2019     15:15            258 alias_out.txt
-a----        2/27/2019     15:16       2/27/2019     15:16            258 alias_out2.txt
```

`Get-ChildItem` Ruft den Inhalt des aktuellen Verzeichnisses ab `C:\Test` . Die Objekte " **System. IO. Director yinfo** " und " **System. IO. FileInfo** " werden über die Pipeline gesendet.
`Format-Table` verwendet den **View** -Parameter, um die benutzerdefinierte Ansicht **mygciview** anzugeben, die die Spalte " **kreationtime** " enthält.

Die Standard `Format-Table` Ausgabe für `Get-ChildItem` enthält nicht die Spalte "up **time** ".

### Beispiel 5: Verwenden von Eigenschaften für die Tabellenausgabe

In diesem Beispiel wird der **Property** -Parameter verwendet, um alle Computerdienste in einer Tabelle mit zwei Spalten anzuzeigen, in der die Eigenschaften **Name** und **DependentServices** angezeigt werden.

```powershell
Get-Service | Format-Table -Property Name, DependentServices
```

`Get-Service` Ruft alle Dienste auf dem Computer ab und sendet die **System. ServiceProcess. ServiceController** -Objekte über die Pipeline. `Format-Table` verwendet den **Property** -Parameter, um anzugeben, dass die Eigenschaften **Name** und **DependentServices** in der Tabelle angezeigt werden.

**Name** und **DependentServices** sind zwei der Eigenschaften des Objekt Typs. Um alle Eigenschaften anzuzeigen: `Get-Service | Get-Member -MemberType Properties` .

### Beispiel 6: Formatieren eines Prozesses und Berechnen der Lauf Zeit

In diesem Beispiel wird eine Tabelle mit dem Prozessnamen und der Gesamtlaufzeit für die **Editor** -Prozesse des lokalen Computers angezeigt. Die Gesamtausführungszeit wird durch Subtrahieren der Startzeit der einzelnen Prozesses von der aktuellen Zeit berechnet.

```powershell
Get-Process notepad |
  Format-Table ProcessName, @{Label="TotalRunningTime"; Expression={(Get-Date) - $_.StartTime}}
```

```Output
ProcessName TotalRunningTime
----------- ----------------
notepad     03:20:00.2751767
notepad     00:00:16.7710520
```

`Get-Process` Ruft alle **Editor** -Prozesse des lokalen Computers ab und sendet die Objekte in der Pipeline. `Format-Table` zeigt eine Tabelle mit zwei Spalten an: **ProcessName** , eine `Get-Process` Eigenschaft und **totalrunningtime** , eine berechnete Eigenschaft.

Die **totalrunningtime** -Eigenschaft wird durch eine Hash Tabelle mit zwei Schlüsseln, **Bezeichnung** und **Ausdruck** , angegeben. Die **Bezeichnung Key gibt den Namen** der Eigenschaft an. Der **Ausdrucks** Schlüssel gibt die Berechnung an. Der Ausdruck ruft die **StartTime** -Eigenschaft jedes Prozess Objekts ab und subtrahiert Sie vom Ergebnis eines- `Get-Date` Befehls, der das aktuelle Datum und die Uhrzeit abruft.

### Beispiel 7: Formatieren von Notepad-Prozessen

In diesem Beispiel wird verwendet `Get-CimInstance` , um die Lauf Zeit für alle **Editor** -Prozesse auf dem lokalen Computer zu erhalten. Sie können `Get-CimInstance` mit dem **Computername** -Parameter verwenden, um Informationen von Remote Computern zu erhalten.

```powershell
$Processes = Get-CimInstance -Class win32_process -Filter "name='notepad.exe'"
$Processes | Format-Table ProcessName, @{ Label = "Total Running Time"; Expression={(Get-Date) - $_.CreationDate}}
```

```Output
ProcessName Total Running Time
----------- ------------------
notepad.exe 03:39:39.6260693
notepad.exe 00:19:56.1376922
```

`Get-CimInstance` Ruft Instanzen der WMI- **Win32_Process** Klasse ab, die alle Prozesse des lokalen Computers mit dem Namen **notepad.exe** beschreibt. Die Prozess Objekte werden in der `$Processes` Variablen gespeichert.

Die Prozess Objekte in der `$Processes` Variablen werden über die Pipeline an gesendet `Format-Table` , wodurch die **ProcessName** -Eigenschaft und eine neue berechnete Eigenschaft, **Gesamtlaufzeit** , angezeigt werden.

Der Befehl weist den Namen der neuen berechneten Eigenschaft ( **gesamte Lauf Zeit** ) dem Bezeichnungs **Schlüssel zu** . Der Skriptblock des **Ausdrucks** Schlüssels berechnet, wie lange der Prozess ausgeführt wurde, indem er das Erstellungsdatum des Prozesses vom aktuellen Datum subtrahieren konnte. Das- `Get-Date` Cmdlet ruft das aktuelle Datum ab. Das Erstellungsdatum wird vom aktuellen Datum subtrahiert. Das Ergebnis ist der Wert der **gesamten Laufzeit**.

### Beispiel 8: Problembehandlung bei Format Fehlern

Die folgenden Beispiele zeigen die Ergebnisse des Hinzufügens der **displayerror** -oder **ShowError** -Parameter mit einem Ausdruck.

```powershell
Get-Date | Format-Table DayOfWeek,{ $_ / $null } -DisplayError
```

```Output
DayOfWeek  $_ / $null
--------- ------------
Wednesday #ERR
```

```powershell
Get-Date | Format-Table DayOfWeek,{ $_ / $null } -ShowError
```

```Output
DayOfWeek  $_ / $null
--------- ------------
Wednesday

InvalidArgument: Failed to evaluate expression " $_ / $null ".
```

## PARAMETERS

### -AutoSize

Gibt an, dass das Cmdlet die Spaltengröße und die Anzahl der Spalten basierend auf der Breite der Daten anpasst. Standardmäßig werden die Spaltengröße und die Anzahl von der Ansicht bestimmt.

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

### -Display Error

Gibt an, dass das Cmdlet Fehler in der Befehlszeile anzeigt. Dieser Parameter kann als Hilfe beim Debuggen verwendet werden, wenn Sie Ausdrücke in einem Befehl formatieren `Format-Table` und Probleme beheben müssen.

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

### -Erweitern

Gibt das Format des Auflistungs Objekts und die Objekte in der Auflistung an. Dieser Parameter dient zum Formatieren von Objekten, die die [ICollection](/dotnet/api/system.collections.icollection) ([System. Collections](/dotnet/api/system.collections))-Schnittstelle unterstützen. Der Standardwert ist " **enumonly** ".
Die zulässigen Werte für diesen Parameter lauten wie folgt:

- **Enumonly** : zeigt die Eigenschaften der Objekte in der Auflistung an.
- **Coreonly** : zeigt die Eigenschaften des Auflistungs Objekts an.
- **Beides** : zeigt die Eigenschaften des Auflistungs Objekts und die Eigenschaften von Objekten in der Auflistung an.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: CoreOnly, EnumOnly, Both

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Gibt an, dass das Cmdlet das Cmdlet anweist, alle Fehlerinformationen anzuzeigen. Verwenden Sie mit dem **Display Error** -Parameter oder **ShowError** -Parameter. Wenn ein Fehlerobjekt in die Fehler- oder Anzeigedatenströme geschrieben wird, werden standardmäßig nur einige der Fehlerinformationen angezeigt.

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

### -GroupBy

Gibt die sortierte Ausgabe basierend auf einem Eigenschafts Wert in separaten Tabellen an. Sie können z. b. **GroupBy** verwenden, um Dienste basierend auf Ihrem Status in separaten Tabellen aufzulisten.

Geben Sie einen Ausdruck oder eine Eigenschaft ein. Der **GroupBy** -Parameter erwartet, dass die Objekte sortiert werden.
Verwenden Sie das- `Sort-Object` Cmdlet `Format-Table` , bevor Sie zum Gruppieren der Objekte verwenden.

Der Wert des **GroupBy** -Parameters kann eine neue berechnete Eigenschaft sein. Die berechnete Eigenschaft kann ein Skriptblock oder eine Hash Tabelle sein. Gültige Schlüssel-Wert-Paare sind:

- Name (oder Bezeichnung)- `<string>`
- Ausdruck `<string>` oder `<script block>`
- FormatString `<string>`

Weitere Informationen finden Sie unter [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).

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

### -Hidetableheaders

Lässt die Spaltenüberschriften in der Tabelle aus.

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

### -InputObject

Gibt die zu formatierenden Objekte an. Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.

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

### -Eigenschaft

Gibt die in der Anzeige angezeigten Objekteigenschaften und die Reihenfolge an, in der sie angezeigt werden. Geben Sie einen oder mehrere Eigenschaftsnamen ein, die durch Kommas getrennt sind, oder verwenden Sie eine Hash Tabelle, um eine berechnete Eigenschaft anzuzeigen. Platzhalter sind zulässig.

Wenn Sie diesen Parameter weglassen, hängen die Eigenschaften, die in der Anzeige angezeigt werden, von den Eigenschaften des ersten Objekts ab. Wenn das erste Objekt beispielsweise **PropertyA** und **propertyb** aufweist, die nachfolgenden Objekte jedoch **PropertyA** , **propertyb** und **propertyc** aufweisen, werden nur die **PropertyA** -und **propertyb** -Header angezeigt.

Der **Property** -Parameter ist optional. Sie können die Parameter " **Property** " und " **View** " nicht im selben Befehl verwenden.

Der Wert des **Property** -Parameters kann eine neue berechnete Eigenschaft sein. Die berechnete Eigenschaft kann ein Skriptblock oder eine Hash Tabelle sein. Gültige Schlüssel-Wert-Paare sind:

- Name (oder Bezeichnung) `<string>`
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
Accept wildcard characters: True
```

### -Repeatheiader

Wiederholt, wenn der Header einer Tabelle nach jedem Vollbild angezeigt wird. Der wiederholte Header ist nützlich, wenn die Ausgabe an einen Pager wie oder weitergeleitet wird, z `less` `more` . b. oder mit einer Bildschirm Sprachausgabe.

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

### -ShowError

Dieser Parameter sendet Fehler über die Pipeline. Dieser Parameter kann als Hilfe beim Debuggen verwendet werden, wenn Sie Ausdrücke in einem Befehl formatieren `Format-Table` und Probleme beheben müssen.

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

### -Ansicht

Ab PowerShell 6 werden die Standardansichten im PowerShell-Quellcode definiert `C#` . Die `*.format.ps1xml` Dateien aus PowerShell 5,1 und früheren Versionen sind in PowerShell 6 und höheren Versionen nicht vorhanden.

Mit dem **View** -Parameter können Sie ein alternatives Format oder eine benutzerdefinierte Ansicht für die Tabelle angeben. Sie können die PowerShell-Standard Sichten verwenden oder benutzerdefinierte Ansichten erstellen. Weitere Informationen zum Erstellen einer benutzerdefinierten Ansicht finden Sie unter [about_Format.ps1XML](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).

Die Alternative und die benutzerdefinierten Ansichten für den **View** -Parameter müssen das Tabellenformat verwenden, andernfalls `Format-Table` schlägt fehl. Wenn die Alternative Ansicht eine Liste ist, verwenden Sie das- `Format-List` Cmdlet. Wenn die Alternative Ansicht weder eine Liste noch eine Tabelle ist, verwenden Sie das- `Format-Custom` Cmdlet.

Sie können die Parameter " **Property** " und " **View** " nicht im selben Befehl verwenden.

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

### -Wrap

Zeigt Text an, der die Spaltenbreite in der nächsten Zeile überschreitet. Standardmäßig wird Text, der die Spaltenbreite überschreitet, abgeschnitten.

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

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System. Management. Automation. psobject

Sie können jedes beliebige Objekt über die Pipeline an senden `Format-Table` .

## AUSGABEN

### Microsoft. PowerShell. Commands. Internal. Format

`Format-Table` gibt Format Objekte zurück, die die Tabelle darstellen.

## HINWEISE

## VERWANDTE LINKS

[about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[about_Format.ps1xml](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md)

[about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md)

[Export-FormatData](Export-FormatData.md)

[Format-Custom](Format-Custom.md)

[Format-Hex](Format-Hex.md)

[Format-List](Format-List.md)

[Format-Wide](Format-Wide.md)

[Get-FormatData](Get-FormatData.md)

[Get-Member](Get-Member.md)

[Get-CimInstance](../CimCmdlets/Get-CimInstance.md)

[Update-FormatData](Update-FormatData.md)
