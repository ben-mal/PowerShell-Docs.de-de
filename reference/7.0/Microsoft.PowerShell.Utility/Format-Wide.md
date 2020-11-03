---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/format-wide?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Format-Wide
ms.openlocfilehash: f26fc996b7fd029ed5994432080e51a1d83ec20e
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2020
ms.locfileid: "93219364"
---
# Format-Wide

## ZUSAMMENFASSUNG
Formatiert Objekte als eine große Tabelle, in der nur eine Eigenschaft pro Objekt angezeigt wird.

## SYNTAX

```
Format-Wide [[-Property] <Object>] [-AutoSize] [-Column <int>] [-GroupBy <Object>] [-View <string>]
  [-ShowError] [-DisplayError] [-Force] [-Expand <string>] [-InputObject <psobject>]
  [<CommonParameters>]
```

## DESCRIPTION

Das- `Format-Wide` Cmdlet formatiert Objekte als eine breite Tabelle, in der nur eine Eigenschaft jedes Objekts angezeigt wird. Sie können den **Property** -Parameter verwenden, um zu bestimmen, welche Eigenschaft angezeigt wird.

## BEISPIELE

### Beispiel 1: Formatieren von Namen von Dateien im aktuellen Verzeichnis

Dieser Befehl zeigt die Namen der Dateien im aktuellen Verzeichnis in drei Spalten auf dem Bildschirm an.

```powershell
Get-ChildItem | Format-Wide -Column 3
```

Das Cmdlet „Get-ChildItem“ ruft die Objekte ab, die jede Datei im Verzeichnis darstellen. Der Pipeline Operator (|) übergibt die Datei Objekte über die Pipeline an `Format-Wide` , wodurch Sie für die Ausgabe formatiert werden. Der **Column** -Parameter gibt die Anzahl der Spalten an.

### Beispiel 2: Formatieren von Namen von Registrierungs Schlüsseln

Dieser Befehl zeigt die Namen der Registrierungsschlüssel im Schlüssel „HKEY_CURRENT_USER\Software\Microsoft“ an.

```powershell
Get-ChildItem HKCU:\software\microsoft | Format-Wide -Property pschildname -AutoSize
```

Das Cmdlet „Get-ChildItem“ ruft die Objekte ab, die die Schlüssel darstellen. Der Pfad wird als "HKCU:" angegeben, eines der Laufwerke, die vom PowerShell-Registrierungs Anbieter verfügbar gemacht werden, gefolgt vom Schlüssel Pfad. Der Pipeline Operator (|) übergibt die Registrierungsschlüssel Objekte über die Pipeline an `Format-Wide` , wodurch Sie für die Ausgabe formatiert werden. Der **Property** -Parameter gibt den Namen der Eigenschaft an, und der **AutoSize** -Parameter passt die Spalten zur besseren Lesbarkeit an.

### Beispiel 3: Problembehandlung bei Format Fehlern

Die folgenden Beispiele zeigen die Ergebnisse des Hinzufügens der **displayerror** -oder **ShowError** -Parameter mit einem Ausdruck.

```powershell
PS /> Get-Date | Format-Wide { $_ / $null } -DisplayError


#ERR

PS /> Get-Date | Format-Wide { $_ / $null } -ShowError


Failed to evaluate expression " $_ / $null ".
+ CategoryInfo          : InvalidArgument: (12/21/2018 8:18:01 AM:PSObject) [], RuntimeException
+ FullyQualifiedErrorId : PSPropertyExpressionError
```

## PARAMETERS

### -AutoSize

Passt die Spaltengröße und die Anzahl der Spalten basierend auf der Breite der Daten an. Standardmäßig werden die Spaltengröße und die Anzahl von der Ansicht bestimmt. Der **AutoSize** -Parameter und der **Column** -Parameter können nicht im selben Befehl verwendet werden.

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

### -Spalte

Gibt die Anzahl der Spalten in der Anzeige an. Der **AutoSize** -Parameter und der **Column** -Parameter können nicht im selben Befehl verwendet werden.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Display Error

Zeigt Fehler in der Befehlszeile an. Dieser Parameter wird nur selten verwendet, kann jedoch als Hilfe beim Debuggen verwendet werden, wenn Sie Ausdrücke in einem Befehl formatieren `Format-Wide` und die Ausdrücke nicht zu funktionieren scheinen.

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

### -Erweitern

Formatiert das Auflistungsobjekt und die Objekte in der Auflistung. Dieser Parameter dient zum Formatieren der Objekte, die die ICollection (System.Collections)-Schnittstelle unterstützen. Der Standardwert ist " **enumonly** ".

Gültige Werte sind:

- Enumonly: zeigt die Eigenschaften der Objekte in der Auflistung an.
- Coreonly: zeigt die Eigenschaften des Auflistungs Objekts an.
- Beides: zeigt die Eigenschaften des Auflistungs Objekts und die Eigenschaften von Objekten in der Auflistung an.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: CoreOnly, EnumOnly, Both

Required: False
Position: Named
Default value: EnumOnly
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Gibt an, dass dieses Cmdlet Einschränkungen außer Kraft setzt, die die erfolgreiche Ausführung des Befehls verhindern, sodass die Änderungen nicht die Sicherheit beeinträchtigen. Beispielsweise überschreibt **Force** das Schreibschutzattribut oder erstellt Verzeichnisse zum Vervollständigen eines Dateipfads. Es wird jedoch nicht etwa versucht, Dateiberechtigungen zu ändern.

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

### -GroupBy

Formatiert die Ausgabe basierend auf einer freigegebenen Eigenschaft bzw. einem freigegebenen Wert in Gruppen. Geben Sie einen Ausdruck oder eine Eigenschaft der Ausgabe ein.

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

Gibt die in der Anzeige angezeigten Objekteigenschaften und die Reihenfolge an, in der sie angezeigt werden.
Platzhalter sind zulässig.

Wenn Sie diesen Parameter weglassen, hängen die in der Anzeige dargestellten Eigenschaften von dem angezeigten Objekt ab. Der Parameter Name "Property" ist optional. Sie können die Parameter " **Property** " und " **View** " nicht im selben Befehl verwenden.

Der Wert des **Property** -Parameters kann eine neue berechnete Eigenschaft sein. Die berechnete Eigenschaft kann ein Skriptblock oder eine Hash Tabelle sein. Gültige Schlüssel-Wert-Paare sind:

- Ausdruck `<string>` oder `<script block>`
- FormatString `<string>`

Weitere Informationen finden Sie unter [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -ShowError

Sendet Fehler über die Pipeline. Dieser Parameter wird nur selten verwendet, kann jedoch als Hilfe beim Debuggen verwendet werden, wenn Sie Ausdrücke in einem Befehl formatieren `Format-Wide` und die Ausdrücke nicht zu funktionieren scheinen.

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

### -Ansicht

Gibt den Namen eines alternativen Tabellen Formats oder einer anderen Sicht an. Sie können die Parameter " **Property** " und " **View** " nicht im selben Befehl verwenden.

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

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System. Management. Automation. psobject

Sie können jedes beliebige Objekt an die Pipeline übergeben `Format-Wide` .

## AUSGABEN

### Microsoft. PowerShell. Commands. Internal. Format

`Format-Wide` gibt Format Objekte zurück, die die Tabelle darstellen.

## HINWEISE

Sie können auch auf den `Format-Wide` integrierten Alias verweisen `fw` . Weitere Informationen finden Sie unter [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).

Beim **GroupBy** -Parameter wird davon ausgegangen, dass die Objekte sortiert sind. Verwenden Sie `Sort-Object` `Format-Custom` , um die-Objekte mithilfe von zu gruppieren.

Mit dem **View** -Parameter können Sie ein alternatives Format für die Tabelle angeben. Sie können die in den `*.format.PS1XML` Dateien im PowerShell-Verzeichnis definierten Ansichten verwenden oder Ihre eigenen Ansichten in neuen PS1XML-Dateien erstellen und Sie mit dem `Update-FormatData` Cmdlet in PowerShell einschließen.

Die Alternative Ansicht für den **View** -Parameter muss das Tabellenformat verwenden. Wenn dies nicht der Fall ist, schlägt der Befehl fehl. Wenn die Alternative Ansicht eine Liste ist, verwenden Sie `Format-List` . Wenn die alternative Ansicht weder eine Liste noch eine Tabelle ist, verwenden Sie Format-Custom.

## VERWANDTE LINKS

[about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[Format-Custom](Format-Custom.md)

[Format-Hex](Format-Hex.md)

[Format-List](Format-List.md)

[Format-Table](Format-Table.md)
