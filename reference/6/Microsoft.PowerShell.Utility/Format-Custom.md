---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/format-custom?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Format-Custom
ms.openlocfilehash: 28914b86c86d5c16f09c81a5dc70ed1e05123b3e
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2020
ms.locfileid: "93219252"
---
# Format-Custom

## ZUSAMMENFASSUNG
Verwendet eine benutzerdefinierte Ansicht zur Formatierung der Ausgabe.

## SYNTAX

```
Format-Custom [[-Property] <Object[]>] [-Depth <Int32>] [-GroupBy <Object>] [-View <String>]
 [-ShowError] [-DisplayError] [-Force] [-Expand <String>] [-InputObject <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION

Das- `Format-Custom` Cmdlet formatiert die Ausgabe eines Befehls, wie in einer alternativen Ansicht definiert.
`Format-Custom` dient zum Anzeigen von Sichten, bei denen es sich nicht nur um Tabellen oder nur Listen handelt. Sie können die in PowerShell definierten Ansichten verwenden, oder Sie können eigene Sichten in einer neuen Datei erstellen `format.ps1xml` und Sie mit dem `Update-FormatData` Cmdlet PowerShell hinzufügen.

## BEISPIELE

### Beispiel 1: Formatieren der Ausgabe mit einer benutzerdefinierten Ansicht

```powershell
Get-Command Start-Transcript | Format-Custom -View MyView
```

Dieser Befehl formatiert Informationen über das `Start-Transcript` Cmdlet in dem Format, das in der MyView-Ansicht definiert ist, einer benutzerdefinierten Ansicht, die vom Benutzer erstellt wurde. Zum erfolgreichen Ausführen dieses Befehls müssen Sie zuerst eine neue PS1XML-Datei erstellen, die Ansicht **MyView** definieren und dann den Befehl verwenden, `Update-FormatData` um die Datei PS1XML zu PowerShell hinzuzufügen.

### Beispiel 2: Formatieren der Ausgabe mit der Standardansicht

```powershell
Get-Process Winlogon | Format-Custom
```

Mit diesem Befehl werden Informationen über den **Winlogon** -Prozess in einer alternativen angepassten Ansicht formatiert.
Da der Befehl den **View** -Parameter nicht verwendet, `Format-Custom` verwendet eine standardmäßige benutzerdefinierte Ansicht, um die Daten zu formatieren.

### Beispiel 3: Problembehandlung bei Format Fehlern

Die folgenden Beispiele zeigen die Ergebnisse des Hinzufügens der **displayerror** -oder **ShowError** -Parameter mit einem Ausdruck.

```powershell
PC /> Get-Date | Format-Custom DayOfWeek,{ $_ / $null } -DisplayError

class DateTime
{
  DayOfWeek = Friday
   $_ / $null  = #ERR
}


PC /> Get-Date | Format-Custom DayOfWeek,{ $_ / $null } -ShowError

class DateTime
{
  DayOfWeek = Friday
   $_ / $null  =
}

Failed to evaluate expression " $_ / $null ".
+ CategoryInfo          : InvalidArgument: (12/21/2018 8:01:04 AM:PSObject) [], RuntimeException
+ FullyQualifiedErrorId : PSPropertyExpressionError
```

## PARAMETERS

### -Tiefe

Gibt die Anzahl der Spalten in der Anzeige an.

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

Zeigt Fehler in der Befehlszeile an. Dieser Parameter wird nur selten verwendet, kann jedoch als Hilfe beim Debuggen verwendet werden, wenn Sie Ausdrücke in einem Befehl formatieren `Format-Custom` und die Ausdrücke nicht zu funktionieren scheinen.

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

Formatiert das Auflistungsobjekt und die Objekte in der Auflistung. Dieser Parameter dient zum Formatieren von Objekten, die die **System. Collections. ICollection** -Schnittstelle unterstützen. Der Standardwert ist " **enumonly** ".

Gültige Werte sind:

- Enumonly: zeigt die Eigenschaften der Objekte in der Auflistung an.
- Coreonly: zeigt die Eigenschaften des Auflistungs Objekts an.
- Beides: zeigt die Eigenschaften des Auflistungs Objekts und die Objekte in der Auflistung an.

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

Weist das Cmdlet an, alle Fehlerinformationen anzuzeigen. Verwenden Sie mit den Parametern **displayerror** oder **ShowError** . Wenn ein Fehlerobjekt in die Fehler- oder Anzeigedatenströme geschrieben wird, werden standardmäßig nur einige der Fehlerinformationen angezeigt.

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

Wenn Sie diesen Parameter weglassen, hängen die in der Anzeige dargestellten Eigenschaften von dem angezeigten Objekt ab. Die Parameter Name- **Eigenschaft** ist optional. Sie können die Parameter " **Property** " und " **View** " nicht im selben Befehl verwenden.

Der Wert des **Property** -Parameters kann eine neue berechnete Eigenschaft sein. Die berechnete Eigenschaft kann ein Skriptblock oder eine Hash Tabelle sein. Gültige Schlüssel-Wert-Paare sind:

- Ausdruck `<string>` oder `<script block>`
- Eingeh `<int32>`

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

Sendet Fehler über die Pipeline. Dieser Parameter wird nur selten verwendet, kann jedoch als Hilfe beim Debuggen verwendet werden, wenn Sie Ausdrücke in einem Befehl formatieren `Format-Custom` und die Ausdrücke nicht zu funktionieren scheinen.

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

Gibt den Namen eines alternativen Formats oder einer alternativen Ansicht an. Wenn Sie diesen Parameter weglassen, wird von `Format-Custom` eine standardmäßige benutzerdefinierte Ansicht verwendet. Sie können die Parameter " **Property** " und " **View** " nicht im selben Befehl verwenden.

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

Sie können jedes beliebige Objekt an die Pipeline übergeben `Format-Custom` .

## AUSGABEN

### Microsoft. PowerShell. Commands. Internal. Format

`Format-Custom` Gibt die Format Objekte zurück, die die Anzeige darstellen.

## HINWEISE

`Format-Custom` dient zum Anzeigen von Sichten, bei denen es sich nicht nur um Tabellen oder nur Listen handelt. Um eine Alternative Tabellenansicht anzuzeigen, verwenden Sie `Format-Table` . Um eine Alternative Listenansicht anzuzeigen, verwenden Sie `Format-List` .

Sie können auch auf den `Format-Custom` integrierten Alias verweisen `fc` . Weitere Informationen finden Sie unter [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).

Beim **GroupBy** -Parameter wird davon ausgegangen, dass die Objekte sortiert sind. Vor `Format-Custom` der Verwendung von zum Gruppieren der Objekte verwenden `Sort-Object` Sie, um diese zu sortieren.

## VERWANDTE LINKS

[about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[Format-Hex](Format-Hex.md)

[Format-List](Format-List.md)

[Format-Table](Format-Table.md)

[Format-Wide](Format-Wide.md)

[Get-Process](../Microsoft.PowerShell.Management/Get-Process.md)
