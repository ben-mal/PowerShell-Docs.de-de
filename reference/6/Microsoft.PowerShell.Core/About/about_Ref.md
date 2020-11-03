---
description: Beschreibt, wie eine Verweistyp Variable erstellt und verwendet wird. Sie können Verweistyp Variablen verwenden, um es einer Funktion zu gestatten, den Wert einer Variablen zu ändern, die an Sie übermittelt wird.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 08/24/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_ref?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Ref
ms.openlocfilehash: fefc0f002db0b9591b2d23e148db381f7413871f
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221324"
---
# <a name="about-ref"></a>Informationen zu Ref

## <a name="short-description"></a>Kurze Beschreibung
Beschreibt, wie eine Verweistyp Variable erstellt und verwendet wird. Sie können Verweistyp Variablen verwenden, um es einer Funktion zu gestatten, den Wert einer Variablen zu ändern, die an Sie übermittelt wird.

## <a name="long-description"></a>Lange Beschreibung

Sie können Variablen als *Verweis* oder als *Wert* an Funktionen übergeben.

Wenn Sie eine Variable als *Wert* übergeben, übergeben Sie eine Kopie der Daten.

Im folgenden Beispiel ändert die-Funktion den Wert der an Sie übergebenen-Variablen. In PowerShell sind ganze Zahlen Werttypen, sodass Sie als Wert übermittelt werden.
Daher bleibt der Wert von `$var` außerhalb des Gültigkeits Bereichs der Funktion unverändert.

```powershell
Function Test($data)
{
    $data = 3
}

$var = 10
Test -data $var
$var
```

```output
10
```

Im folgenden Beispiel wird eine Variable, die eine enthält, `Hashtable` an eine Funktion übermittelt. `Hashtable` ist ein Objekttyp, der standardmäßig als *Verweis* an die Funktion übermittelt wird.

Wenn eine Variable als *Verweis* übergeben wird, kann die Funktion die Daten ändern, und diese Änderung bleibt nach der Ausführung der Funktion erhalten.

```powershell
Function Test($data)
{
    $data.Test = "New Text"
}

$var = @{}
Test -data $var
$var
```

```output
Name                           Value
----                           -----
Test                           New Text
```

Die-Funktion fügt ein neues Schlüssel-Wert-Paar hinzu, das außerhalb des Gültigkeits Bereichs der Funktion beibehalten wird.

### <a name="writing-functions-to-accept-reference-parameters"></a>Schreiben von Funktionen zum Akzeptieren von Verweis Parametern

Sie können ihre Funktionen so codieren, dass ein Parameter als Verweis übernommen wird, unabhängig vom Typ der übergebenen Daten. Dies erfordert, dass Sie den Parametertyp als `System.Management.Automation.PSReference` , oder angeben `[ref]` .

Wenn Sie Verweise verwenden, müssen Sie die- `Value` Eigenschaft des- `System.Management.Automation.PSReference` Typs verwenden, um auf Ihre Daten zuzugreifen.

```powershell
Function Test([ref]$data)
{
    $data.Value = 3
}
```

Um eine Variable an einen Parameter zu übergeben, der einen Verweis erwartet, müssen Sie die Variable als Verweis umwandeln.

> [!NOTE]
> Beide Klammern und Klammern sind erforderlich.

```powershell
$var = 10
Test -data ([ref]$var)
$var
```

```output
3
```

### <a name="passing-references-to-net-methods"></a>Übergeben von verweisen an .NET-Methoden

Einige .NET-Methoden erfordern möglicherweise, dass Sie eine Variable als Verweis übergeben. Wenn die Definition der Methode die Schlüsselwörter `in` , `out` oder `ref` für einen Parameter verwendet, wird ein Verweis erwartet.

```powershell
[int] | Get-Member -Static -Name TryParse
```

```output
Name     MemberType Definition
----     ---------- ----------
TryParse Method     static bool TryParse(string s, [ref] int result)
```

Die- `TryParse` Methode versucht, eine Zeichenfolge als ganze Zahl zu analysieren. Wenn die Methode erfolgreich ist, gibt Sie zurück `$true` , und das Ergebnis wird in der Variablen gespeichert, die Sie als **Verweis über** mittelt haben.

```
PS> $number = 0
PS> [int]::TryParse("15", ([ref]$number))
True
PS> $number
15
```

### <a name="references-and-scopes"></a>Verweise und Bereiche

Verweise ermöglichen, dass der Wert einer Variablen im übergeordneten Bereich innerhalb eines untergeordneten Bereichs geändert wird.

```powershell
# Create a value type variable.
$i = 0
# Create a reference type variable.
$iRef = [ref]0
# Invoke a scriptblock to attempt to change both values.
&{$i++;$iRef.Value++}
# Output the results.
"`$i = $i;`$iRef = $($iRef.Value)"
```

```output
$i = 0;$iRef = 1
```

Nur die Variable des Verweis Typs wurde geändert.

## <a name="see-also"></a>Weitere Informationen:

[about_Variables](about_Variables.md)

[about_Environment_Variables](about_Environment_Variables.md)

[about_Functions](about_Functions.md)

[about_Script_Blocks](about_Script_Blocks.md)

[about_Scopes](about_scopes.md)
