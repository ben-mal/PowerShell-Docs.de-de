---
description: Sowohl ganzzahlige als auch echte numerische Literale können über Typ-und Multiplikator-Suffixe verfügen.
Locale: en-US
ms.date: 04/12/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_numeric_literals?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Informationen zu numerischen Literalen
ms.openlocfilehash: 8e26e8c67b1acadc75a67cd51bd6adb07fb7daf3
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93220983"
---
# <a name="about-numeric-literals"></a>Informationen zu numerischen Literalen

Es gibt zwei Arten numerischer Literale: Integer und Real. Beide können über Typ-und Multiplikator-Suffixe verfügen.

## <a name="integer-literals"></a>Ganzzahlenliteral

Ganzzahlige Literale können in Dezimal-, Hexadezimal-oder Binär Notation geschrieben werden.
Hexadezimal literalen wird das Präfix vorangestellt `0x` , und binäre Literale werden als Präfix vorangestellt `0b` , um Sie von Dezimalzahlen zu unterscheiden.

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
| n      | BigInteger-Datentyp           | In PowerShell 7,0 hinzugefügt |
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

Die Multiplikator-Suffixe können in Kombination mit beliebigen typsuffixen verwendet werden, müssen jedoch nach dem Typsuffix vorhanden sein. Beispielsweise ist das Literale falsch formatiert `100gbL` , aber das Literale `100Lgb` ist gültig.

Wenn ein Multiplikator einen Wert erstellt, der die möglichen Werte für den numerischen Typ überschreitet, den das Suffix angibt, ist das Literale falsch formatiert. Beispielsweise ist das Literale falsch formatiert `1usgb` , da der Wert größer ist als der Wert, der `1gb` für den `[ushort]` durch das Suffix angegebenen Typ zulässig ist `us` .

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

| Accelerator |         Hinweis         |           BESCHREIBUNG            |
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

## <a name="examples"></a>Beispiele

Die folgende Tabelle enthält einige Beispiele für numerische Literale und listet deren Typ und Wert auf:

|   Number     |  type      |    Wert     |
| -----------: | ---------- | -----------: |
|         100  | Int32      |          100 |
|        100 u  | UInt32     |          100 |
|        100 d  | Decimal    |          100 |
|        100 l  | Int64      |          100 |
|       100 UL  | UInt64     |          100 |
|       100 US-  | UInt16     |          100 |
|       100 uy  | Byte       |          100 |
|        100 y  | SByte      |          100 |
|         1E2  | Double     |          100 |
|        1. E2  | Double     |          100 |
|       0x1e2  | Int32      |          482 |
|      0x1e2l  | Int64      |          482 |
|      0x1e2d  | Int32      |         7725 |
|        482d  | Decimal    |          482 |
|       482gb  | Int64      | 517543559168 |
|       482ngb | BigInteger | 517543559168 |
|    0x1e2lgb  | Int64      | 517543559168 |
|   0b1011011  | Int32      |           91 |
|  0xFFFFFFFF  | Int32      |           -1 |
| -0xFFFFFFFF  | Int32      |            1 |
| 0xffffffffu  | UInt32     |   4294967295 |

### <a name="working-with-binary-or-hexadecimal-numbers"></a>Arbeiten mit binären oder hexadezimalen Zahlen

Übermäßig große binäre oder hexadezimale Literale können als zurückgeben `[bigint]` , anstatt die Analyse fehlschlagen zu müssen, und zwar nur dann, wenn das `n` Suffix angegeben wird. Signier Bits werden jedoch weiterhin oberhalb von `[decimal]` Bereichen berücksichtigt:

- Wenn eine binäre Zeichenfolge ein Vielfaches von 8 Bits ist, wird das höchste Bit als Signier Bit behandelt.
- Wenn eine hexadezimale Zeichenfolge, die eine Länge von 8 hat, die erste Ziffer 8 oder höher hat, wird die Zahl als negativ behandelt.

Das Angeben eines nicht signierten Suffixes für binäre und hexadezimale Literale ignoriert Signier Bits. `0xFFFFFFFF`Gibt z. b `-1` . zurück, `0xFFFFFFFFu` gibt jedoch den `[uint]::MaxValue` von 4294967295 zurück.

Wenn Sie das Literale mit einem Präfix versehen, `0` wird dies umgangen und als nicht signiert behandelt.
Ein Beispiel für die Camel-Case-Schreibweise lautet: `0b011111111`. Dies kann bei der Arbeit mit Literalen im Bereich notwendig sein `[bigint]` , da die `u` -und- `n` Suffixe nicht kombiniert werden können.

Sie können binäre und hexadezimale Literale auch mit dem- `-` Präfix negieren. Dies kann zu einer positiven Zahl führen, da Signier Bits zulässig sind.

Signier Bits werden für BigInteger-suffixt-Ziffern akzeptiert:

- BigInteger-suffixt-suffixt behandelt das hohe Bit eines beliebigen Literals mit einem Längen Vielfaches von 8 Zeichen als Signier Bit. Die Länge enthält weder das `0x` Präfix noch beliebige Suffixe.
- Die BigInteger-suffixt-Binärdatei akzeptiert Signier Bits bei 96-und 128-Zeichen und bei jeweils 8 Zeichen nach.

### <a name="commands-that-look-like-numeric-literals"></a>Befehle, die wie numerische Literale aussehen

Jeder Befehl, der wie ein gültiges numerisches Literalformat aussieht, muss mit dem-Operator () ausgeführt werden `&` , andernfalls wird es als Zahl interpretiert. Falsch formatierte Literale mit gültiger Syntax wie `1usgb` führen zu folgendem Fehler:

```
PS> 1usgb
At line:1 char:6
+ 1usgb
+      ~
The numeric constant 1usgb is not valid.
+ CategoryInfo          : ParserError: (:) [], ParentContainsErrorRecordException
+ FullyQualifiedErrorId : BadNumericConstant
```

Falsch formatierte Literale mit ungültiger Syntax wie werden jedoch `1gbus` als standardmäßige Bare-Zeichenfolge interpretiert und können als gültiger Befehls Name in Kontexten interpretiert werden, in denen Befehle aufgerufen werden können.

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

## <a name="how-powershell-parses-numeric-literals"></a>So analysiert PowerShell numerische Literale

PowerShell v 7.0 änderte die Art und Weise, wie numerische Literale analysiert werden, um die neuen Funktionen zu aktivieren.

### <a name="parsing-real-numeric-literals"></a>Realisieren von echten numerischen Literalen

Wenn das Literale einen Dezimaltrennzeichen oder eine e-Notation enthält, wird die Literalzeichenfolge mit einer reellen Zahl analysiert.

- , Wenn das Decimal-Suffix direkt in vorhanden ist `[decimal]` .
- Andernfalls analysieren `[Double]` Sie As und wenden einen Multiplikator auf den Wert an. Überprüfen Sie dann die typsuffixe, und versuchen Sie, Sie in den entsprechenden Typ umzuwandeln.
- Wenn die Zeichenfolge kein Typsuffix aufweist, analysieren Sie als `[Double]` .

### <a name="paring-integer-numeric-literals"></a>Numerische ganzzahlige numerische Literale werden verarbeitet.

Ganzzahlige typliterale werden mithilfe der folgenden Schritte analysiert:

1. Festlegen des Basis-Formats
   - Analysieren Sie bei binären Formaten in `[BigInteger]` .
   - Analysieren Sie bei hexadezimalen Formaten die `[BigInteger]` Verwendung spezieller Einschränkungen, um ursprüngliches Verhalten beizubehalten, wenn der Wert im `[int]` Bereich oder liegt `[long]` .
   - Wenn weder Binary noch Hex, wird normal als ausgewertet `[BigInteger]` .
2. Wenden Sie den Multiplikatorwert an, bevor Sie Umwandlungen versuchen, um sicherzustellen, dass typbegrenzungen ohne Überlauf ordnungsgemäß geprüft werden.
3. Überprüfen Sie die typsuffixe.
   - Überprüfen Sie die typbegrenzungen, und versuchen Sie, diesen Typ zu analysieren.
   - Wenn kein Suffix verwendet wird, wird der Wert in der folgenden Reihenfolge durch Begrenzungen überprüft, was zum ersten erfolgreichen Test führt, der den Typ der Zahl bestimmt.
     - `[int]`
     - `[long]`
     - `[decimal]` (nur Basis-10-Literale)
     - `[double]` (nur Basis-10-Literale)
   - Wenn der Wert außerhalb des Bereichs für hexadezimale `[long]` und binäre Zahlen liegt, schlägt die Analyse fehl.
   - Wenn der Wert außerhalb des `[double]` Bereichs für die Basis 10-Zahl liegt, schlägt die Analyse fehl.
   - Höhere Werte müssen explizit mit dem-Suffix geschrieben werden `n` , um das Literale als zu analysieren `BigInteger` .

### <a name="parsing-large-value-literals"></a>Auswerten von großen Wert literalen

Zuvor wurden höhere ganzzahlige Werte als Double analysiert, bevor Sie in einen anderen Typ umgewandelt werden. Dies führt zu einem Genauigkeits Verlust in den höheren Bereichen. Beispiel:

```
PS> [bigint]111111111111111111111111111111111111111111111111111111
111111111111111100905595216014112456735339620444667904
```

Um dieses Problem zu vermeiden, müssen Sie Werte als Zeichen folgen schreiben und diese dann konvertieren:

```
PS> [bigint]'111111111111111111111111111111111111111111111111111111'
111111111111111111111111111111111111111111111111111111
```

In PowerShell 7,0 müssen Sie das- `N` Suffix verwenden.

```
PS> 111111111111111111111111111111111111111111111111111111n
111111111111111111111111111111111111111111111111111111
```

Außerdem sollten Werte zwischen `[ulong]::MaxValue` und `[decimal]::MaxValue` mit dem Decimal-Suffix angegeben werden `D` , um die Genauigkeit beizubehalten. Ohne das-Suffix werden diese Werte `[Double]` mit dem echt Analysemodus analysiert.

<!-- reference links -->
[bigint]: /dotnet/api/system.numerics.biginteger?view=netcore-2.2
