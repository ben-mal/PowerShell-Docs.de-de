---
description: Sowohl ganzzahlige als auch echte numerische Literale können über Typ-und Multiplikator-Suffixe verfügen.
Locale: en-US
ms.date: 04/09/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_numeric_literals?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Informationen zu numerischen Literalen
ms.openlocfilehash: dc1a55dbec1f0de99e06011645e6884b37480233
ms.sourcegitcommit: 39c2a697228276d5dae39e540995fa479c2b5f39
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2020
ms.locfileid: "93354828"
---
# <a name="about-numeric-literals"></a>Informationen zu numerischen Literalen

Es gibt zwei Arten numerischer Literale: Integer und Real. Beide können über Typ-und Multiplikator-Suffixe verfügen.

## <a name="integer-literals"></a>Ganzzahlenliteral

Ganzzahlige Literale können in Dezimal-oder hexadezimal Notation geschrieben werden. Hexadezimal literalen wird das Präfix vorangestellt `0x` , um Sie von Dezimalzahlen zu unterscheiden.

Ganzzahlige Literale können ein Typsuffix und ein Multiplikator-Suffix aufweisen.

| Suffix |            Bedeutung             |          Hinweis           |
| ------ | ------------------------------ | ----------------------- |
| j      | Byte-Datentyp mit Vorzeichen          | In PowerShell 6,2 hinzugefügt |
| uy     | Datentyp ohne Vorzeichen        | In PowerShell 6,2 hinzugefügt |
| s      | short-Datentyp                | In PowerShell 6,2 hinzugefügt |
| USA     | Short-Datentyp ohne Vorzeichen       | In PowerShell 6,2 hinzugefügt |
| l      | Long-Datentyp                 |                         |
| u      | Ganzzahl ohne Vorzeichen int-oder Long-Datentyp | In PowerShell 6,2 hinzugefügt |
| nützlichen     | Long-Datentyp ohne Vorzeichen        | In PowerShell 6,2 hinzugefügt |
| kb     | KB-Multiplikator            |                         |
| mb     | Megabyte-Multiplikator            |                         |
| GB     | Gigabyte-Multiplikator            |                         |
| t     | Terabyte-Multiplikator            |                         |
| PB     | Peer tabyte-Multiplikator            |                         |

Der Typ eines ganzzahligen Literals wird durch seinen Wert, das Typsuffix und das numerische Multiplikator-Suffix bestimmt.

Für ein Ganzzahlliteral ohne Typsuffix:

- Wenn der Wert durch den Typ dargestellt werden kann `[int]` , ist dies der Typ.
- Andernfalls, wenn der Wert durch den Typ dargestellt werden kann `[long]` , ist dies der Typ.
- Andernfalls, wenn der Wert durch den Typ dargestellt werden kann `[decimal]` , ist dies der Typ.
- Andernfalls wird Sie durch den-Typ dargestellt `[double]` .

Für ein Ganzzahlliteral mit einem Typsuffix:

- Wenn das Typsuffix ist `u` und der Wert durch den Typ dargestellt werden kann, `[uint]` ist sein Typ `[uint]` .
- Wenn das Typsuffix ist `u` und der Wert durch den Typ dargestellt werden kann, `[ulong]` ist sein Typ `[ulong]` .
- Wenn der Wert durch den angegebenen Typ dargestellt werden kann, ist dieser Typ.
- Andernfalls ist dieses Literale falsch formatiert.

## <a name="real-literals"></a>Real-Literale

Echte Literale können nur in Dezimal Schreibweise geschrieben werden. Diese Notation kann nach einem Dezimaltrennzeichen und wissenschaftlicher Schreibweise nach Komma Werten mit einem exponentiellen Teil enthalten.

Der exponentielle Teil enthält ein "e", gefolgt von einem optionalen Vorzeichen (+/-) und einer Zahl, die den Exponenten darstellt. Beispielsweise ist der Literalwert mit `1e2` dem numerischen Wert 100.

Echte Literale können ein Typsuffix und ein Multiplikator-Suffix aufweisen.

| Suffix |       Bedeutung       |
| ------ | ------------------- |
| T      | decimal-Datentyp   |
| kb     | KB-Multiplikator |
| mb     | Megabyte-Multiplikator |
| GB     | Gigabyte-Multiplikator |
| t     | Terabyte-Multiplikator |
| PB     | Peer tabyte-Multiplikator |

Es gibt zwei Arten von echtem Literalen: Double und Decimal. Diese werden durch das Fehlen oder vorhanden sein des Suffixes Decimal angegeben. PowerShell unterstützt keine Literale Darstellung eines `[float]` Werts. Ein Double Real-Literale weist den Typ auf `[double]` . Ein tatsächliches Dezimaltrennzeichen weist den Typ auf `[decimal]` .
Nachfolgende Nullen im Bruchteil eines Dezimal-Real-Literals sind signifikant.

Wenn der Wert der Ziffern von Exponent-Part in einem `[double]` echten literalen kleiner als der unterstützte Mindestwert ist, ist der Wert dieses `[double]` echten Literals 0. Wenn der Wert der Ziffern von Exponent-Part in einem `[decimal]` echten literalen kleiner als der unterstützte Mindestwert ist, ist dieses Literalformat falsch formatiert. Wenn der Wert der Ziffern Exponent-Part in einem `[double]` oder einem `[decimal]` realen Literalwert größer als der maximal unterstützte Wert ist, ist dieses Literalformat falsch formatiert.

> [!NOTE]
> Die Syntax ermöglicht einem Double Real-literalen das Suffix long-Type.
> PowerShell behandelt diesen Fall als Ganzzahlliteral, dessen Wert durch den Typ dargestellt wird `[long]` . Diese Funktion wurde aus Gründen der Abwärtskompatibilität mit früheren Versionen von PowerShell beibehalten. Programmierer werden jedoch davon abgeraten, ganzzahlige Literale dieses Formulars zu verwenden, da Sie den tatsächlichen Wert des Literale leicht verdecken können. Hat z. b. den `1.2L` Wert 1, den `1.2345e1L` Wert 12 und `1.2345e-5L` den Wert 0, von denen keiner sofort ersichtlich ist.

## <a name="numeric-multipliers"></a>Numerische Multiplikatoren

Aus praktischen Gründen können ganzzahlige und echte Literale einen numerischen Multiplikator enthalten, der einen der häufig verwendeten Kräfte von 2 angibt. Der numerische Multiplikator kann in einer beliebigen Kombination aus Groß-oder Kleinbuchstaben geschrieben werden.

Die Multiplikator-Suffixe können in Kombination mit den `u` `ul` -,-und- `l` typsuffixen verwendet werden.

### <a name="multiplier-examples"></a>Multiplikator-Beispiele

```
PS> 1kb
1024

PS> 1.30Dmb
1363148.80

PS> 0x10Gb
17179869184

PS> 1.4e23tb
1.5393162788864E+35

PS> 0x12Lpb
20266198323167232
```

## <a name="numeric-type-accelerators"></a>Numerische typacceleratoren

PowerShell unterstützt die folgenden typacceleratoren:

| Accelerator |         Hinweis         |           Beschreibung            |
| ----------- | -------------------- | -------------------------------- |
| `[byte]`    |                      | Byte (ohne Vorzeichen)                  |
| `[sbyte]`   |                      | Byte (signiert)                    |
| `[Int16]`   |                      | 16-Bit-Ganzzahl                   |
| `[short]`   | Alias für `[int16]`  | 16-Bit-Ganzzahl                   |
| `[UInt16]`  |                      | 16-Bit-Ganzzahl (ohne Vorzeichen)        |
| `[ushort]`  | Alias für `[uint16]` | 16-Bit-Ganzzahl (ohne Vorzeichen)        |
| `[Int32]`   |                      | 32-bit integer                   |
| `[int]`     | Alias für `[int32]`  | 32-bit integer                   |
| `[UInt32]`  |                      | 32-Bit-Ganzzahl (ohne Vorzeichen)        |
| `[uint]`    | Alias für `[uint32]` | 32-Bit-Ganzzahl (ohne Vorzeichen)        |
| `[Int64]`   |                      | 64-Bit-Integer                   |
| `[long]`    | Alias für `[int64]`  | 64-Bit-Integer                   |
| `[UInt64]`  |                      | 64-Bit-Ganzzahl (ohne Vorzeichen)        |
| `[ulong]`   | Alias für `[uint64]` | 64-Bit-Ganzzahl (ohne Vorzeichen)        |
| `[bigint]`  |                      | Siehe [BigInteger-Struktur][bigint]  |
| `[single]`  |                      | Gleit Komma mit einfacher Genauigkeit  |
| `[float]`   | Alias für `[single]` | Gleit Komma mit einfacher Genauigkeit  |
| `[double]`  |                      | Gleit Komma Wert mit doppelter Genauigkeit  |
| `[decimal]` |                      | 128-Bit-Gleit Komma Zahl           |

> [!NOTE]
> Die folgenden typacceleratoren wurden in PowerShell 6,2 hinzugefügt: `[short]` , `[ushort]` , `[uint]` , `[ulong]` .

### <a name="working-with-other-numeric-types"></a>Arbeiten mit anderen numerischen Typen

Um mit allen anderen numerischen Typen arbeiten zu können, müssen Sie Type Accelerators verwenden, was nicht ohne Probleme. Beispielsweise werden hohe ganzzahlige Werte immer als Double analysiert, bevor Sie in einen anderen Typ umgewandelt werden.

```
PS> [bigint]111111111111111111111111111111111111111111111111111111
111111111111111100905595216014112456735339620444667904
```

Der Wert wird zuerst als Double analysiert und verliert die Genauigkeit in den höheren Bereichen.
Um dieses Problem zu vermeiden, geben Sie Werte als Zeichen folgen ein, und konvertieren Sie Sie dann:

```
PS> [bigint]'111111111111111111111111111111111111111111111111111111'
111111111111111111111111111111111111111111111111111111
```

## <a name="examples"></a>Beispiele

Die folgende Tabelle enthält einige Beispiele für numerische Literale und listet deren Typ und Wert auf:

|  Number  |  Typ   |    Wert     |
| -------: | ------- | -----------: |
|      100 | Int32   |          100 |
|     100 d | Decimal |          100 |
|     100 l | Int64   |          100 |
|    100 UL | UInt64  |          100 |
|    100 US- | UInt16  |          100 |
|    100 uy | Byte    |          100 |
|     100 y | SByte   |          100 |
|      1E2 | Double  |          100 |
|     1. E2 | Double  |          100 |
|    0x1e2 | Int32   |          482 |
|   0x1e2l | Int64   |          482 |
|   0x1e2d | Int32   |         7725 |
|     482d | Decimal |          482 |
|    482gb | Int64   | 517543559168 |
| 0x1e2lgb | Int64   | 517543559168 |

### <a name="commands-that-look-like-numeric-literals"></a>Befehle, die wie numerische Literale aussehen

Jeder Befehl, der einem numerischen Literalzeichen ähnelt, muss mit dem-Operator aufgerufen werden ( `&` ). andernfalls wird er als eine Zahl des zugeordneten Typs interpretiert.

### <a name="access-properties-and-methods-of-numeric-objects"></a>Zugreifen auf Eigenschaften und Methoden numerischer Objekte

Wenn Sie auf ein Member eines numerischen Literals zugreifen müssen, gibt es Fälle, in denen Sie das Literale in Klammern einschließen müssen.

- Das Literale weist keinen Dezimaltrennzeichen auf.
- Das Literale weist keine Ziffern nach dem Dezimaltrennzeichen auf.
- Das Literale weist kein Suffix auf.

Im folgenden Beispiel tritt beispielsweise ein Fehler auf:

```
PS> 2.GetType().Name
At line:1 char:11
+ 2.GetType().Name
+           ~
An expression was expected after '('.
+ CategoryInfo          : ParserError: (:) [], ParentContainsErrorRecordException
+ FullyQualifiedErrorId : ExpectedExpression
```

Die folgenden Beispiele funktionieren:

```
PS> 2uL.GetType().Name
UInt64
PS> 1.234.GetType().Name
Double
PS> (2).GetType().Name
Int32
```

Die ersten beiden Beispiele funktionieren, ohne dass der Literalwert in Klammern eingeschlossen wird, da der PowerShell-Parser ermitteln kann, wo das numerische Literale endet und die **GetType** -Methode gestartet wird.

<!-- reference links -->
[bigint]: /dotnet/api/system.numerics.biginteger
