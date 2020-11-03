---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 12/19/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/format-list?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Format-List
ms.openlocfilehash: 7817384f077c58b46aed1dba552f89ac431891f0
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2020
ms.locfileid: "93219303"
---
# Format-List

## ZUSAMMENFASSUNG
Formatiert die Ausgabe als eine Liste der Eigenschaften, in der jede Eigenschaft in einer neuen Zeile angezeigt wird.

## SYNTAX

```
Format-List [[-Property] <Object[]>] [-GroupBy <Object>] [-View <string>] [-ShowError]
[-DisplayError] [-Force] [-Expand <string>] [-InputObject <psobject>] [<CommonParameters>]
```

## DESCRIPTION

Das- `Format-List` Cmdlet formatiert die Ausgabe eines Befehls als eine Liste von Eigenschaften, in der jede Eigenschaft in einer eigenen Zeile angezeigt wird. Sie können `Format-List` zum Formatieren und Anzeigen aller oder ausgewählter Eigenschaften eines Objekts als Liste verwenden (Format-List *).

Da für jedes Element in einer Liste mehr Platz als in einer Tabelle verfügbar ist, zeigt PowerShell mehr Eigenschaften des Objekts in der Liste an, und die Eigenschaftswerte werden weniger wahrscheinlich abgeschnitten.

## BEISPIELE

### Beispiel 1: Formatieren von Computerdiensten

```powershell
Get-Service | Format-List
```

Dieser Befehl formatiert Informationen zu Diensten auf dem Computer als Liste. Standardmäßig sind die Dienste als Tabelle formatiert. Mit dem- `Get-Service` Cmdlet werden die Objekte abgerufen, die die Dienste auf dem Computer darstellen. Der Pipeline Operator (|) übergibt die Ergebnisse über die Pipeline an `Format-List` .
Anschließend `Format-List` formatiert der Befehl die Dienst Informationen in einer Liste und sendet Sie an das Standardausgabe-Cmdlet für die Anzeige.

### Beispiel 2: Formatieren von PS1XML-Dateien

Diese Befehle zeigen Informationen zu den PS1XML-Dateien im PowerShell-Verzeichnis als Liste an.

```powershell
$A = Get-ChildItem $pshome\*.ps1xml
Format-List -InputObject $A
```

Der erste Befehl ruft die Objekte ab, die die Dateien darstellen, und speichert Sie in der `$A` Variablen.

Der zweite Befehl verwendet `Format-List` , um Informationen zu Objekten zu formatieren, die in gespeichert sind `$A` . Dieser Befehl verwendet den **Inputobject** -Parameter, um die Variable an zu übergeben `Format-List` , die dann die formatierte Ausgabe zur Anzeige an das Standardausgabe-Cmdlet sendet.

### Beispiel 3: Formatieren von Prozess Eigenschaften nach Name

Dieser Befehl zeigt Name, Basispriorität und Prioritätsklasse für jeden Prozess auf dem Computer an.

```powershell
Get-Process | Format-List -Property name, basepriority, priorityclass
```

Er verwendet das `Get-Process` Cmdlet, um ein Objekt zu erhalten, das jeden Prozess darstellt. Der Pipeline Operator (|) übergibt die Prozess Objekte über die Pipeline an `Format-List` . `Format-List` formatiert die Prozesse als eine Liste mit den angegebenen Eigenschaften. Der *Eigenschafts* Parameter Name ist optional, daher können Sie ihn weglassen.

### Beispiel 4: Formatieren aller Eigenschaften für einen Prozess

Dieser Befehl zeigt alle Eigenschaften des Winlogon-Prozesses an.

```powershell
Get-Process winlogon | Format-List -Property *
```

Er verwendet das Get-Process-Cmdlet zum Abrufen eines Objekts, das den Winlogon-Prozess darstellt. Der Pipeline Operator (|) übergibt das Winlogon-Prozess Objekt über die Pipeline an `Format-List` . Der Befehl verwendet den *Property* -Parameter, um die Eigenschaften und anzugeben \* , um alle Eigenschaften anzugeben.
Da der Name des *Property* -Parameters optional ist, können Sie ihn weglassen und den Befehl als eingeben `Format-List *` . `Format-List` sendet die Ergebnisse automatisch an das Standardausgabe-Cmdlet für die Anzeige.

### Beispiel 5: Problembehandlung bei Format Fehlern

Die folgenden Beispiele zeigen die Ergebnisse des Hinzufügens der **displayerror** -oder **ShowError** -Parameter mit einem Ausdruck.

```powershell
PC /> Get-Date | Format-List DayOfWeek,{ $_ / $null } -DisplayError

DayOfWeek    : Friday
 $_ / $null  : #ERR

PC /> Get-Date | Format-List DayOfWeek,{ $_ / $null } -ShowError

DayOfWeek    : Friday
 $_ / $null  :

Failed to evaluate expression " $_ / $null ".
+ CategoryInfo          : InvalidArgument: (12/21/2018 7:59:23 AM:PSObject) [], RuntimeException
+ FullyQualifiedErrorId : PSPropertyExpressionError
```

## PARAMETERS

### -Display Error

Gibt an, dass dieses Cmdlet Fehler in der Befehlszeile anzeigt. Dieser Parameter wird nur selten verwendet, kann jedoch als Hilfe beim Debuggen verwendet werden, wenn Sie Ausdrücke in einem Befehl formatieren `Format-List` und die Ausdrücke nicht zu funktionieren scheinen.

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

Gibt das formatierte Auflistungs Objekt sowie die Objekte in der Auflistung an. Dieser Parameter dient zum Formatieren der Objekte, die die ICollection (System.Collections)-Schnittstelle unterstützen. Der Standardwert ist „EnumOnly“. Zulässige Werte für diesen Parameter:

- "Enumonly". Zeigt die Eigenschaften der Objekte in der Auflistung an.
- Nur coreonly. Zeigt die Eigenschaften des Auflistungsobjekts an.
- Both (Beides): Zeigt die Eigenschaften des Auflistungsobjekts und die Eigenschaften von Objekten in der Auflistung an.

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

Gibt an, dass dieses Cmdlet alle Fehlerinformationen anzeigt. Verwenden Sie mit dem **Display Error** -Parameter oder **ShowError** -Parameter. Wenn ein Fehlerobjekt in die Fehler- oder Anzeigedatenströme geschrieben wird, werden standardmäßig nur einige der Fehlerinformationen angezeigt.

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

Gibt die Ausgabe in Gruppen basierend auf einer freigegebenen Eigenschaft oder einem freigegebenen Wert an. Geben Sie einen Ausdruck oder eine Eigenschaft der Ausgabe ein.

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

Gibt die zu formatierenden Objekte an. Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, durch den die Objekte abgerufen werden.

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

- Name (oder Bezeichnung)- `<string>`
- Ausdruck `<string>` oder `<script block>`
- FormatString `<string>`

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

### -ShowError

Gibt an, dass das Cmdlet Fehler über die Pipeline sendet. Dieser Parameter wird nur selten verwendet, kann jedoch als Hilfe beim Debuggen verwendet werden, wenn Sie Ausdrücke in einem Befehl formatieren `Format-List` und die Ausdrücke nicht zu funktionieren scheinen.

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

Gibt den Namen eines alternativen Listen Formats oder einer anderen Ansicht an. Sie können die Parameter " **Property** " und " **View** " nicht im selben Befehl verwenden.

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

Sie können jedes beliebige Objekt an die Pipeline übergeben `Format-List` .

## AUSGABEN

### Microsoft. PowerShell. Commands. Internal. Format

`Format-List` Gibt die Format Objekte zurück, die die Liste darstellen.

## HINWEISE

Sie können auch über den integrierten Alias FL auf Format-List verweisen. Weitere Informationen finden Sie unter [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).

Die Format-Cmdlets, wie z `Format-List` . b., ordnen die anzuzeigenden Daten an, zeigen Sie aber nicht an.
Die Daten werden durch die Ausgabe Features von PowerShell und durch die Cmdlets angezeigt, die das out-Verb (die Out-Cmdlets) enthalten, z `Out-Host` `Out-File` . b. oder.

Wenn Sie kein Format-Cmdlet verwenden, wendet PowerShell dieses Standardformat auf jedes Objekt an, das angezeigt wird.

Beim **GroupBy** -Parameter wird davon ausgegangen, dass die Objekte sortiert sind. Verwenden Sie Sort-Object, bevor Sie `Format-List` zum Gruppieren der Objekte verwenden.

Mit dem **View** -Parameter können Sie ein alternatives Format für die Tabelle angeben. Sie können die in den `*.format.PS1XML` Dateien im PowerShell-Verzeichnis definierten Ansichten verwenden oder Ihre eigenen Ansichten in neuen PS1XML-Dateien erstellen und das Cmdlet "Update-FormatData" verwenden, um Sie in PowerShell einzubinden.

Die Alternative Ansicht für den **View** -Parameter muss das Listenformat verwenden. andernfalls schlägt der Befehl fehl. Wenn die Alternative Ansicht eine Tabelle ist, verwenden Sie `Format-Table` . Wenn die Alternative Ansicht weder eine Liste noch eine Tabelle ist, verwenden Sie `Format-Custom` .

## VERWANDTE LINKS

[about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[Format-Custom](Format-Custom.md)

[Format-Hex](Format-Hex.md)

[Format-Table](Format-Table.md)

[Format-Wide](Format-Wide.md)
