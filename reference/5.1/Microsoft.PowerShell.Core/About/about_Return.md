---
description: Beendet den aktuellen Bereich, der eine Funktion, ein Skript oder Skriptblock sein kann.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_return?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Return
ms.openlocfilehash: a2603f24b562ecc1bdafe49f5703a75661b1124d
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222556"
---
# <a name="about-return"></a>Informationen zur Rückgabe

## <a name="short-description"></a>Kurze Beschreibung

Beendet den aktuellen Bereich, der eine Funktion, ein Skript oder Skriptblock sein kann.

## <a name="long-description"></a>Lange Beschreibung

Das- `return` Schlüsselwort beendet eine Funktion, ein Skript oder einen Skriptblock. Sie kann verwendet werden, um einen Bereich an einem bestimmten Punkt zu verlassen, einen Wert zurückzugeben oder um anzugeben, dass das Ende des Bereichs erreicht wurde.

Benutzer, die mit Sprachen wie c oder c vertraut sind, \# können das `return` Schlüsselwort verwenden, um die Logik zum expliziten verlassen eines Bereichs zu vereinfachen.

In PowerShell werden die Ergebnisse jeder Anweisung als Ausgabe zurückgegeben, auch ohne eine-Anweisung, die das Return-Schlüsselwort enthält. Sprachen wie c oder c \# geben nur die Werte zurück, die durch das- `return` Schlüsselwort angegeben werden.

> [!NOTE]
> Ab PowerShell 5,0 hat PowerShell Sprache zum Definieren von Klassen mit formaler Syntax hinzugefügt.  Im Kontext einer PowerShell-Klasse wird von einer-Methode nichts ausgegeben, es sei denn, Sie geben Sie mithilfe einer- `return` Anweisung an. Weitere Informationen zu PowerShell-Klassen finden Sie in [about_Classes](about_Classes.md).

### <a name="syntax"></a>Syntax

Die Syntax für das `return` Schlüsselwort lautet wie folgt:

```
return [<expression>]
```

Das `return` Schlüsselwort kann allein oder ein Wert oder Ausdruck folgendermaßen angezeigt werden:

```powershell
return
return $a
return (2 + $a)
```

### <a name="examples"></a>Beispiele

Im folgenden Beispiel wird das- `return` Schlüsselwort verwendet, um eine Funktion an einem bestimmten Punkt zu beenden, wenn eine bedingte Bedingung erfüllt ist. Ungerade Zahlen werden nicht multipliziert, da die Return-Anweisung beendet wird, bevor die Anweisung ausgeführt werden kann.

```powershell
function MultiplyEven
{
    param($number)

    if ($number % 2) { return "$number is not even" }
    $number * 2
}

1..10 | ForEach-Object {MultiplyEven -Number $_}
```

```output
1 is not even
4
3 is not even
8
5 is not even
12
7 is not even
16
9 is not even
20
```

In PowerShell können Werte auch dann zurückgegeben werden, wenn das- `return` Schlüsselwort nicht verwendet wird.
Die Ergebnisse jeder Anweisung werden zurückgegeben. Die folgenden-Anweisungen geben z. b. den Wert der- `$a` Variablen zurück:

```powershell
$a
return
```

Die folgende Anweisung gibt auch den Wert von zurück `$a` :

```powershell
return $a
```

Das folgende Beispiel enthält eine-Anweisung, mit der der Benutzer informiert werden soll, dass die Funktion eine Berechnung durchführt:

```powershell
function calculation {
    param ($value)

    "Please wait. Working on calculation..."
    $value += 73
    return $value
}

$a = calculation 14
```

"Bitte warten. Arbeiten an der Berechnung... " die Zeichenfolge wird nicht angezeigt. Stattdessen wird Sie der `$a` Variablen zugewiesen, wie im folgenden Beispiel gezeigt:

```
PS> $a
Please wait. Working on calculation...
87
```

Sowohl die Informations Zeichenfolge als auch das Ergebnis der Berechnung werden von der Funktion zurückgegeben und der `$a` Variablen zugewiesen.

Wenn Sie in ihrer Funktion eine Meldung anzeigen möchten, können Sie ab PowerShell 5,0 den Daten `Information` Strom verwenden. Der folgende Code korrigiert das obige Beispiel mithilfe des- `Write-Information` Cmdlets mit dem Wert " `InformationAction` **Continue** ".

```powershell
function calculation {
    param ($value)

    Write-Information "Please wait. Working on calculation..." -InformationAction Continue
    $value += 73
    return $value
}

$a = calculation 14
```

```output
Please wait. Working on calculation...
C:\PS> $a
87
```

### <a name="return-values-and-the-pipeline"></a>Rückgabewerte und Pipeline

Wenn Sie eine Sammlung aus dem Skriptblock oder der Funktion zurückgeben, hebt PowerShell automatisch die Registrierung der Member auf und übergibt sie jeweils einzeln über die Pipeline. Dies ist auf die einmalige Verarbeitung von PowerShell zurückzuführen. Weitere Informationen finden Sie unter [about_pipelines](about_pipelines.md).

Dieses Konzept wird durch die folgende Beispiel Funktion veranschaulicht, die ein Array von Zahlen zurückgibt. Die Ausgabe der Funktion wird an das `Measure-Object` Cmdlet weitergeleitet, das die Anzahl der Objekte in der Pipeline zählt.

```powershell
function Test-Return
{
    $array = 1,2,3
    return $array
}
Test-Return | Measure-Object
```

```Output
Count    : 3
Average  :
Sum      :
Maximum  :
Minimum  :
Property :
```

Um zu erzwingen, dass ein Skriptblock oder eine Funktion eine Auflistung als einzelnes Objekt an die Pipeline zurückgibt, verwenden Sie eine der beiden folgenden Methoden:

- Ausdruck "unäres Array"

  Wenn Sie einen unären Ausdruck verwenden, können Sie den Rückgabewert als einzelnes Objekt an die Pipeline senden, wie im folgenden Beispiel veranschaulicht.

  ```powershell
  function Test-Return
  {
      $array = 1,2,3
      return (, $array)
  }
  Test-Return | Measure-Object
  ```

  ```Output
  Count    : 1
  Average  :
  Sum      :
  Maximum  :
  Minimum  :
  Property :
  ```

- `Write-Output` mit dem **noenumerate** -Parameter.

  Sie können auch das `Write-Output` Cmdlet mit dem **noenumerate** -Parameter verwenden. Im folgenden Beispiel wird das- `Measure-Object` Cmdlet verwendet, um die Objekte zu zählen, die von der Beispiel Funktion durch das-Schlüsselwort an die Pipeline gesendet werden `return` .

  ```powershell
  function Test-Return
  {
      $array = 1, 2, 3
      return Write-Output -NoEnumerate $array
  }

  Test-Return | Measure-Object
  ```

  ```Output
  Count    : 1
  Average  :
  Sum      :
  Maximum  :
  Minimum  :
  Property :
  ```

## <a name="see-also"></a>Weitere Informationen:

[about_Language_Keywords](about_Language_Keywords.md)

[about_Functions](about_Functions.md)

[about_Scopes](about_Scopes.md)

[about_Classes](about_Classes.md)

[Write-Information](xref:Microsoft.PowerShell.Utility.Write-Information)

[about_Script_Blocks](about_Script_Blocks.md)
