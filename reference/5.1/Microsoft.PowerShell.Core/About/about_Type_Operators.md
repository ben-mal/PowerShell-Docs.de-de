---
description: Beschreibt die Operatoren, die mit Microsoft .NET Typen arbeiten.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 10/15/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_type_operators?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Type_Operators
ms.openlocfilehash: 6ea2ef2f61636d67a8bacf69ff577f477712a165
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "93224311"
---
# <a name="about-type-operators"></a>Informationen zu Typoperatoren

## <a name="short-description"></a>KURZE BESCHREIBUNG
Beschreibt die Operatoren, die mit Microsoft .NET Typen arbeiten.

## <a name="long-description"></a>LANGE BESCHREIBUNG

Die booleschen Typoperatoren (und) geben an, `-is` `-isNot` ob ein Objekt eine Instanz eines angegebenen .net-Typs ist. Der- `-is` Operator gibt den Wert **true** zurück, wenn der Typ übereinstimmt, andernfalls den Wert **false** . Der- `-isNot` Operator gibt den Wert **false** zurück, wenn der Typ übereinstimmt, andernfalls ist der Wert **true** .

Der- `-as` Operator versucht, das Eingabe Objekt in den angegebenen .NET-Typ zu konvertieren. Wenn Sie erfolgreich ist, wird das konvertierte-Objekt zurückgegeben. Wenn ein Fehler auftritt, wird zurückgegeben `$null` . Es wird kein Fehler zurückgegeben.

In der folgenden Tabelle sind die Typoperatoren in PowerShell aufgelistet.

|Operator|BESCHREIBUNG                |Beispiel                          |
|--------|---------------------------|---------------------------------|
|`-is`   |Gibt true zurück, wenn die Eingabe|`(get-date) -is [DateTime]`      |
|        |ist eine Instanz von      |`True`                           |
|        |der angegebene .NET-Typ.       |                                 |
|`-isNot`|Gibt true zurück, wenn die Eingabe|`(get-date) -isNot [DateTime]`   |
|        |keine Instanz von     |`False`                          |
|        |specified.NET-Typ.        |                                 |
|`-as`   |Konvertiert die Eingabe in die  |`"5/7/07" -as [DateTime]`        |
|        |der angegebene .NET-Typ.       |`Monday, May 7, 2007 12:00:00 AM`|

Die Syntax der Typoperatoren lautet wie folgt:

```powershell
<input> <operator> [.NET type]
```

Sie können auch die folgende Syntax verwenden:

```powershell
<input> <operator> ".NET type"
```

Der .NET-Typ kann als Typname in eckige Klammern oder in einer Zeichenfolge (z `[DateTime]` `"DateTime"` . b. oder für **System. DateTime** ) geschrieben werden. Wenn sich der Typ nicht im Stammverzeichnis des System-Namespace befindet, geben Sie den vollständigen Namen des Objekt Typs an. Sie können "System." weglassen. Wenn Sie z. b. **System. Diagnostics. Process** angeben möchten, geben Sie `[System.Diagnostics.Process]` , `[Diagnostics.Process]` oder ein `"Diagnostics.Process"` .

Die Typoperatoren arbeiten immer für das Eingabe Objekt als Ganzes. Das heißt, _Wenn das Eingabe_ Objekt eine Auflistung ist, ist es der getestete Sammlungstyp, nicht die Typen der _Elemente_ der Auflistung.

### <a name="-isisnot-operators"></a>-is/IsNot-Operatoren

Die **booleschen** Typoperatoren ( `-is` und `-isNot` ) geben immer einen **booleschen** Wert zurück, auch wenn die Eingabe eine Auflistung von-Objekten ist.

Wenn `<input>` ein Typ ist, der mit oder vom .NET-Typ _abgeleitet_ ist, `-is` gibt der Operator zurück `$True` .

Beispielsweise wird der Typ " **directoriyinfo** " vom Typ " **FileSystemInfo** " abgeleitet. Daher geben beide Beispiele **true** zurück.

```powershell
PS> (Get-Item /) -is [System.IO.DirectoryInfo]
True
PS> (Get-Item /) -is [System.IO.FileSystemInfo]
True
```

Der `-is` Operator kann auch Schnittstellen zuordnen, wenn der die- `<input>` Schnittstelle im Vergleich implementiert. In diesem Beispiel ist die Eingabe ein Array. Arrays implementieren die **System. Collections. IList** -Schnittstelle.

```powershell
PS> 1, 2 -is [System.Collections.IList]
True
```

### <a name="-as-operator"></a>-as-Operator

Der- `-as` Operator versucht, das Eingabe Objekt in den angegebenen .NET-Typ zu konvertieren. Wenn Sie erfolgreich ist, wird das konvertierte-Objekt zurückgegeben. Wenn fehlschlägt, wird zurückgegeben `$null` . Es wird kein Fehler zurückgegeben.

Wenn `<input>` ein Typ ist, der vom .NET-Typ _abgeleitet_ wird, gibt Pass- `-as` _through_ das Eingabe Objekt unverändert zurück. Beispielsweise wird der Typ " **directoriyinfo** " vom Typ " **FileSystemInfo** " abgeleitet. Daher ist der Objekttyp im folgenden Beispiel unverändert:

```powershell
PS> $fsroot = (Get-Item /) -as [System.IO.FileSystemInfo]
PS> $fsroot.GetType().FullName
System.IO.DirectoryInfo
```

#### <a name="converting-the-datetime-type-is-culture-sensitive"></a>Das Umstellen des DateTime-Typs ist Kultur abhängig.

Anders als bei `[DateTime]` Typumwandlungen funktioniert die Konvertierung in den-Typ mit dem- `-as` Operator nur mit Zeichen folgen, die gemäß den Regeln der aktuellen Kultur formatiert sind.

```powershell
PS> [cultureinfo]::CurrentCulture = 'fr-FR'
PS> '13/5/20' -as [datetime]

mercredi 13 mai 2020 00:00:00

PS> '05/13/20' -as [datetime]
PS> [datetime]'05/13/20'

mercredi 13 mai 2020 00:00:00

PS> [datetime]'13/05/20'
InvalidArgument: Cannot convert value "13/05/20" to type "System.DateTime".
Error: "String '13/05/20' was not recognized as a valid DateTime."
```

Verwenden Sie das-Cmdlet, um den .NET-Typ eines Objekts zu suchen `Get-Member` . Oder verwenden Sie die **GetType** -Methode aller-Objekte in Verbindung mit der **FullName** -Eigenschaft dieser Methode. Mit der folgenden Anweisung wird beispielsweise der Typ des Rückgabewerts eines Befehls abgerufen `Get-Culture` :

```powershell
PS> (Get-Culture).GetType().FullName
System.Globalization.CultureInfo
```

## <a name="examples"></a>BEISPIELE

Die folgenden Beispiele zeigen einige Verwendungsmöglichkeiten der Typoperatoren:

```powershell
PS> 32 -is [Float]
False

PS> 32 -is "int"
True

PS> (get-date) -is [DateTime]
True

PS> "12/31/2007" -is [DateTime]
False

PS> "12/31/2007" -is [String]
True

PS> (get-process PowerShell)[0] -is [System.Diagnostics.Process]
True

PS> (get-command get-member) -is [System.Management.Automation.CmdletInfo]
True
```

Das folgende Beispiel zeigt, dass es sich bei der Eingabe um eine Auflistung von-Objekten um den .NET-Typ der Auflistung handelt, nicht um den Typ der einzelnen Objekte in der Auflistung.

Obwohl sowohl das `Get-Culture` -Cmdlet als auch das- `Get-UICulture` Cmdlet **System. Globalization. CultureInfo** -Objekte zurückgeben, ist eine Auflistung dieser Objekte ein System. Object-Array.

```powershell
PS> (get-culture) -is [System.Globalization.CultureInfo]
True

PS> (get-uiculture) -is [System.Globalization.CultureInfo]
True

PS> (get-culture), (get-uiculture) -is [System.Globalization.CultureInfo]
False

PS> (get-culture), (get-uiculture) -is [Array]
True

PS> (get-culture), (get-uiculture) | foreach {
  $_ -is [System.Globalization.CultureInfo])
}
True
True

PS> (get-culture), (get-uiculture) -is [Object]
True
```

In den folgenden Beispielen wird gezeigt, wie der-Operator verwendet wird `-as` .

```powershell
PS> "12/31/07" -is [DateTime]
False

PS> "12/31/07" -as [DateTime]
Monday, December 31, 2007 12:00:00 AM

PS> $date = "12/31/07" -as [DateTime]

C:\PS>$a -is [DateTime]
True

PS> 1031 -as [System.Globalization.CultureInfo]

LCID      Name      DisplayName
----      ----      -----------
1031      de-DE     German (Germany)
```

Das folgende Beispiel zeigt, dass der `-as` Operator zurückgibt, wenn der Operator das Eingabe Objekt nicht in den .NET-Typ konvertieren kann `$null` .

```powershell
PS> 1031 -as [System.Diagnostics.Process]
PS>
```

## <a name="see-also"></a>SIEHE AUCH

[about_Operators](about_Operators.md)
