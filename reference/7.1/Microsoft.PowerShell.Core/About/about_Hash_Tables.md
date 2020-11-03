---
description: Beschreibt das Erstellen, verwenden und Sortieren von Hash Tabellen in PowerShell.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 11/28/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_hash_tables?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Hash_Tables
ms.openlocfilehash: 0c4c54ea0ac017f0238ea5766c3489a1918d8fdd
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93220895"
---
# <a name="about-hash-tables"></a>Informationen zu Hash Tabellen

## <a name="short-description"></a>KURZE BESCHREIBUNG
Beschreibt das Erstellen, verwenden und Sortieren von Hash Tabellen in PowerShell.

## <a name="long-description"></a>LANGE BESCHREIBUNG

Eine Hash Tabelle, die auch als Wörterbuch oder assoziatives Array bezeichnet wird, ist eine kompakte Datenstruktur, die ein oder mehrere Schlüssel/Wert-Paare speichert. Eine Hash Tabelle kann z. b. eine Reihe von IP-Adressen und Computernamen enthalten, wobei es sich bei den IP-Adressen um die Schlüssel handelt und die Computernamen die Werte sind oder umgekehrt.

In PowerShell ist jede Hash Tabelle ein Hashtable-Objekt (System. Collections. Hashtable). Sie können die Eigenschaften und Methoden von Hash fähigen Objekten in PowerShell verwenden.

Ab PowerShell 3,0 können Sie das [geordnete]-Attribut verwenden, um in PowerShell ein geordnetes Wörterbuch (System. Collections. Specialized. OrderedDictionary) zu erstellen.

Geordnete Wörterbücher unterscheiden sich von den Hash Tabellen darin, dass die Schlüssel immer in der Reihenfolge angezeigt werden, in der Sie Sie auflisten. Die Reihenfolge der Schlüssel in einer Hash Tabelle wird nicht ermittelt.

Die Schlüssel und der Wert in den Hash Tabellen sind ebenfalls .NET-Objekte. Sie sind meistens Zeichen folgen oder Ganzzahlen, Sie können jedoch einen beliebigen Objekttyp aufweisen. Sie können auch Tabellen Hash Tabellen erstellen, in denen der Wert eines Schlüssels eine andere Hash Tabelle ist.

Hash Tabellen werden häufig verwendet, da Sie für das Suchen und Abrufen von Daten sehr effizient sind. Sie können Hash Tabellen zum Speichern von Listen und zum Erstellen berechneter Eigenschaften in PowerShell verwenden. Und PowerShell verfügt über das Cmdlet ConvertFrom-StringData, das Zeichen folgen in eine Hash Tabelle konvertiert.

### <a name="syntax"></a>Syntax

Die Syntax einer Hash Tabelle lautet wie folgt:

```powershell
@{ <name> = <value>; [<name> = <value> ] ...}
```

Die Syntax eines geordneten Wörterbuchs lautet wie folgt:

```powershell
[ordered]@{ <name> = <value>; [<name> = <value> ] ...}
```

Das [geordnete]-Attribut wurde in PowerShell 3,0 eingeführt.

### <a name="creating-hash-tables"></a>Erstellen von Hash Tabellen

Befolgen Sie die folgenden Richtlinien, um eine Hash Tabelle zu erstellen:

- Beginnen Sie die Hash Tabelle mit einem @-Zeichen.
- Schließen Sie die Hash Tabelle in geschweifte Klammern ( {} ) ein.
- Geben Sie mindestens ein Schlüssel-Wert-Paar für den Inhalt der Hash Tabelle ein.
- Verwenden Sie ein Gleichheitszeichen (=), um jeden Schlüssel von seinem Wert zu trennen.
- Verwenden Sie ein Semikolon (;) oder ein Zeilenumbruch, um die Schlüssel-Wert-Paare voneinander zu trennen.
- Ein Schlüssel, der Leerzeichen enthält, muss in Anführungszeichen eingeschlossen werden. Werte müssen gültige PowerShell-Ausdrücke sein. Zeichen folgen müssen in Anführungszeichen eingeschlossen werden, auch wenn Sie keine Leerzeichen enthalten.
- Um die Hash Tabelle zu verwalten, speichern Sie Sie in einer Variablen.
- Wenn Sie einer Variablen eine geordnete Hash Tabelle zuweisen, platzieren Sie das Attribut [geordnet] vor dem Symbol "@". Wenn Sie ihn vor dem Variablennamen platzieren, schlägt der Befehl fehl.

Um im Wert $Hash eine leere Hash Tabelle zu erstellen, geben Sie Folgendes ein:

```powershell
$hash = @{}
```

Sie können einer Hash Tabelle auch Schlüssel und Werte hinzufügen, wenn Sie Sie erstellen. Beispielsweise erstellt die folgende Anweisung eine Hash Tabelle mit drei Schlüsseln.

```powershell
$hash = @{ Number = 1; Shape = "Square"; Color = "Blue"}
```

### <a name="creating-ordered-dictionaries"></a>Erstellen geordneter Wörterbücher

Sie können ein geordnetes Wörterbuch erstellen, indem Sie ein Objekt des OrderedDictionary-Typs hinzufügen, aber die einfachste Möglichkeit zum Erstellen eines geordneten Wörterbuchs ist das Verwenden des [geordneten]-Attributs.

Das [geordnete]-Attribut wird in PowerShell 3,0 eingeführt.

Platzieren Sie das Attribut direkt vor dem Symbol "@".

```powershell
$hash = [ordered]@{ Number = 1; Shape = "Square"; Color = "Blue"}
```

Sie können geordnete Wörterbücher genauso wie Hash Tabellen verwenden.
Beide Typen können als Parameterwerte verwendet werden, die eine Hash Tabelle oder ein Wörterbuch (IDictionary) akzeptieren.

Sie können das [geordnete]-Attribut nicht verwenden, um eine Hash Tabelle zu konvertieren oder umzuwandeln. Wenn Sie das geordnete Attribut vor dem Variablennamen platzieren, schlägt der Befehl mit der folgenden Fehlermeldung fehl.

```powershell
PS C:\> [ordered]$hash = @{}
At line:1 char:1
+ [ordered]$hash = @{}
+ [!INCLUDE[]()]
The ordered attribute can be specified only on a hash literal node.
+ CategoryInfo          : ParserError: (:) [], ParentContainsErrorRecordExc
eption
+ FullyQualifiedErrorId : OrderedAttributeOnlyOnHashLiteralNode
```

Um den Ausdruck zu korrigieren, verschieben Sie das [geordnete]-Attribut.

```powershell
PS C:\> $hash = [ordered]@{}
```

Sie können ein geordnetes Wörterbuch in eine Hash Tabelle umwandeln, aber Sie können das geordnete Attribut nicht wiederherstellen, selbst wenn Sie die Variable löschen und neue Werte eingeben. Um die Reihenfolge wiederherzustellen, müssen Sie die Variable entfernen und neu erstellen.

```
PS C:\> [hashtable]$hash = [ordered]@{
>> Number = 1; Shape = "Square"; Color = "Blue"}
PS C:\> $hash

Name                           Value
----                           -----
Color                          Blue
Shape                          Square
Number                         1
```

### <a name="displaying-hash-tables"></a>Anzeigen von Hash Tabellen

Zum Anzeigen einer Hash Tabelle, die in einer Variablen gespeichert ist, geben Sie den Variablennamen ein.
Standardmäßig wird eine Hash Tabelle als Tabelle mit einer Spalte für Schlüssel und einer für Werte angezeigt.

```powershell
C:\PS> $hash

Name                           Value
----                           -----
Shape                          Square
Color                          Blue
Number                         1
```

Hash Tabellen verfügen über Schlüssel-und Werte Eigenschaften. Verwenden Sie die Punkt Notation, um alle Schlüssel oder alle Werte anzuzeigen.

```powershell
C:\PS> $hash.keys
Number
Shape
Color

C:\PS> $hash.values
1
Square
Blue
```

Jeder Schlüssel Name ist auch eine Eigenschaft der Hash Tabelle, und sein Wert ist der Wert der Key-Name-Eigenschaft. Verwenden Sie das folgende Format, um die Eigenschaftswerte anzuzeigen.

```powershell
$hashtable.<key>
<value>
```

Beispiel:

```powershell
C:\PS> $hash.Number
1

C:\PS> $hash.Color
Blue
```

Wenn der Schlüssel Name mit einem der Eigenschaftsnamen des Hash Tabellentyps in Konflikt steht, können Sie verwenden, `PSBase` um auf diese Eigenschaften zuzugreifen. Wenn beispielsweise der Schlüssel Name lautet `keys` und Sie die Auflistung von Schlüsseln zurückgeben möchten, verwenden Sie die folgende Syntax:

```powershell
$hashtable.PSBase.Keys
```

Hash Tabellen haben eine Count-Eigenschaft, die die Anzahl der Schlüssel-Wert-Paare in der Hash Tabelle angibt.

```powershell
C:\PS> $hash.count
3
```

Hash Tabellen Tabellen sind keine Arrays, daher können Sie keine Ganzzahl als Index in der Hash Tabelle verwenden, aber Sie können einen Schlüsselnamen verwenden, um die Hash Tabelle zu indizieren.
Wenn der Schlüssel ein Zeichen folgen Wert ist, müssen Sie den Schlüsselnamen in Anführungszeichen einschließen.

Beispiel:

```powershell
C:\PS> $hash["Number"]
1
```

### <a name="adding-and-removing-keys-and-values"></a>Hinzufügen und Entfernen von Schlüsseln und Werten

Verwenden Sie das folgende Befehls Format, um einer Hash Tabelle Schlüssel und Werte hinzuzufügen.

```powershell
$hash["<key>"] = "<value>"
```

Wenn Sie z. b. der Hash Tabelle einen "Time"-Schlüssel mit dem Wert "Now" hinzufügen möchten, verwenden Sie das folgende Anweisungs Format.

```powershell
$hash["Time"] = "Now"
```

Mithilfe der Add-Methode des System. Collections. Hashtable-Objekts können Sie auch Schlüssel und Werte zu einer Hash Tabelle hinzufügen. Die Add-Methode weist die folgende Syntax auf:

```powershell
Add(Key, Value)
```

Wenn Sie z. b. der Hash Tabelle einen "Time"-Schlüssel mit dem Wert "Now" hinzufügen möchten, verwenden Sie das folgende Anweisungs Format.

```powershell
$hash.Add("Time", "Now")
```

Außerdem können Sie Schlüssel und Werte zu einer Hash Tabelle hinzufügen, indem Sie den Additions Operator (+) verwenden, um einer vorhandenen Hash Tabelle eine Hash Tabelle hinzuzufügen. Beispielsweise fügt die folgende Anweisung der Hash Tabelle in der $Hash Variable einen Zeit Schlüssel mit dem Wert "Now" hinzu.

```powershell
$hash = $hash + @{Time="Now"}
```

Sie können auch Werte hinzufügen, die in Variablen gespeichert sind.

```powershell
$t = "Today"
$now = (Get-Date)

$hash.Add($t, $now)
```

Sie können keinen Subtraktions Operator verwenden, um ein Schlüssel-Wert-Paar aus einer Hash Tabelle zu entfernen, aber Sie können die Remove-Methode des Hashtable-Objekts verwenden. Die Remove-Methode nimmt den Schlüssel als Wert an.

Die Remove-Methode weist die folgende Syntax auf:

```
Remove(Key)
```

Wenn Sie z. b. das Schlüssel-Wert-Paar time = now aus der Hash Tabelle im Wert der $Hash Variable entfernen möchten, geben Sie Folgendes ein:

```powershell
$hash.Remove("Time")
```

Sie können alle Eigenschaften und Methoden von Hash fähigen Objekten in PowerShell verwenden, einschließlich "enthält", "Clear", "Clone" und "CopyTo". Weitere Informationen zu Hash fähigen Objekten finden Sie unter "System. Collections. Hashtable" auf der MSDN-Website.

### <a name="object-types-in-hashtables"></a>Objekttypen in Hash Tabellen

Die Schlüssel und Werte in einer Hash Tabelle können einen beliebigen .net-Objekttyp haben, und eine einzelne Hash Tabelle kann über Schlüssel und Werte mehrerer Typen verfügen.

Mit der folgenden Anweisung wird eine Hash Tabelle mit Prozessnamen Zeichenfolgen erstellt und Objektwerte verarbeitet und in der \$ p-Variablen gespeichert.

```powershell
$p = @{"PowerShell" = (Get-Process PowerShell);
"Notepad" = (Get-Process notepad)}
```

Sie können die Hash Tabelle in \$ p anzeigen und die Schlüsselnamen-Eigenschaften verwenden, um die Werte anzuzeigen.

```powershell
C:\PS> $p

Name                           Value
----                           -----
PowerShell                     System.Diagnostics.Process (PowerShell)
Notepad                        System.Diagnostics.Process (notepad)

C:\PS> $p.PowerShell

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    441      24    54196      54012   571     5.10   1788 PowerShell

C:\PS> $p.keys | foreach {$p.$_.handles}
441
251
```

Bei den Schlüsseln in einer Hash Tabelle kann es sich auch um einen beliebigen .NET-Typ handeln. Mit der folgenden Anweisung wird der Hash Tabelle in der p-Variablen ein Schlüssel/Wert-Paar hinzugefügt \$ . Der Schlüssel ist ein Dienst Objekt, das den WinRM-Dienst darstellt, und der Wert entspricht dem aktuellen Status des Dienstanbieter.

```powershell
C:\PS> $p = $p + @{(Get-Service WinRM) = ((Get-Service WinRM).Status)}
```

Sie können das neue Schlüssel-Wert-Paar anzeigen und darauf zugreifen, indem Sie die gleichen Methoden verwenden, die Sie auch für andere Paare in der Hash Tabelle verwenden.

```powershell
C:\PS> $p

Name                           Value
----                           -----
PowerShell                     System.Diagnostics.Process (PowerShell)
Notepad                        System.Diagnostics.Process (notepad)
System.ServiceProcess.Servi... Running

C:\PS> $p.keys
PowerShell
Notepad

Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...

C:\PS> $p.keys | foreach {$_.name}
winrm
```

Die Schlüssel und Werte in einer Hash Tabelle können auch Hashtable-Objekte sein. Mit der folgenden Anweisung wird der Hash Tabelle in der p-Variablen, in der der Schlüssel eine Zeichenfolge ist, ein Schlüssel/Wert-Paar hinzugefügt, \$ und der Wert ist eine Hash Tabelle mit drei Schlüssel-Wert-Paaren.

```powershell
C:\PS> $p = $p + @{"Hash2"= @{a=1; b=2; c=3}}
```

Sie können die neuen Werte mit denselben Methoden anzeigen und darauf zugreifen.

```powershell
C:\PS> $p

Name                           Value
----                           -----
PowerShell                     System.Diagnostics.Process (PowerShell)
Notepad                        System.Diagnostics.Process (notepad)
System.ServiceProcess.Servi... Running
Hash2                          {a, b, c}

C:\PS> $p.Hash2

Name                           Value
----                           -----
a                              1
b                              2
c                              3

C:\PS> $p.Hash2.b
2
```

### <a name="sorting-keys-and-values"></a>Sortieren von Schlüsseln und Werten

Die Elemente in einer Hash Tabelle sind intrinsisch Unsortiert. Die Schlüssel-Wert-Paare können bei jedem Anzeigen in einer anderen Reihenfolge angezeigt werden.

Obwohl eine Hash Tabelle nicht sortiert werden kann, können Sie die GetEnumerator-Methode von Hash Tabellen verwenden, um die Schlüssel und Werte aufzulisten. verwenden Sie dann das Cmdlet "Sort-Object", um die Enumerationswerte für die Anzeige zu sortieren.

Die folgenden Befehle zählen z. b. die Schlüssel und Werte in der Hash Tabelle in der \$ p-Variablen auf und Sortieren dann die Schlüssel in alphabetischer Reihenfolge.

```powershell
C:\PS> $p.GetEnumerator() | Sort-Object -Property key

Name                           Value
----                           -----
Notepad                        System.Diagnostics.Process (notepad)
PowerShell                     System.Diagnostics.Process (PowerShell)
System.ServiceProcess.Servi... Running
```

Der folgende Befehl verwendet die gleiche Prozedur, um die Hashwerte in absteigender Reihenfolge zu sortieren.

```powershell
C:\PS> $p.getenumerator() | Sort-Object -Property Value -Descending

Name                           Value
----                           -----
PowerShell                     System.Diagnostics.Process (PowerShell)
Notepad                        System.Diagnostics.Process (notepad)
System.ServiceProcess.Servi... Running
```

### <a name="creating-objects-from-hash-tables"></a>Erstellen von Objekten aus Hash Tabellen

Ab PowerShell 3,0 können Sie ein Objekt aus einer Hash Tabelle mit Eigenschaften und Eigenschafts Werten erstellen.

Die Syntax ist wie folgt:

```powershell
[<class-name>]@{
  <property-name>=<property-value>
  <property-name>=<property-value>
}
```

Diese Methode funktioniert nur für Klassen, die über einen NULL-Konstruktor verfügen, d. h. einen Konstruktor ohne Parameter. Die Objekteigenschaften müssen öffentlich und feststellbar sein.

Weitere Informationen finden Sie unter [about_Object_Creation](about_Object_Creation.md).

### <a name="convertfrom-stringdata"></a>ConvertFrom-StringData

`ConvertFrom-StringData`Mit dem-Cmdlet wird eine Zeichenfolge oder eine here-Zeichenfolge von Schlüssel-Wert-Paaren in eine Hash Tabelle konvertiert. Sie können das `ConvertFrom-StringData` Cmdlet sicher im Daten Abschnitt eines Skripts verwenden, und Sie können es mit dem `Import-LocalizedData` Cmdlet verwenden, um Benutzer Meldungen in der Benutzeroberflächen Kultur des aktuellen Benutzers anzuzeigen.

Diese Zeichen folgen sind besonders nützlich, wenn die Werte in der Hash Tabelle Anführungszeichen enthalten. Weitere Informationen zu here-Zeichen folgen finden Sie unter [about_Quoting_Rules](about_Quoting_Rules.md).

Im folgenden Beispiel wird gezeigt, wie eine here-Zeichenfolge der Benutzer Meldungen im vorherigen Beispiel erstellt wird und wie Sie mit eine `ConvertFrom-StringData` Zeichenfolge aus einer Zeichenfolge in eine Hash Tabelle konvertieren.

Der folgende Befehl erstellt eine here-Zeichenfolge der Schlüssel-Wert-Paare und speichert Sie dann in der \$ Zeichen folgen Variablen.

```powershell
C:\PS> $string = @"
Msg1 = Type "Windows".
Msg2 = She said, "Hello, World."
Msg3 = Enter an alias (or "nickname").
"@
```

Dieser Befehl verwendet das Cmdlet "ConvertFrom-StringData", um die here-Zeichenfolge in eine Hash Tabelle zu konvertieren.

```powershell
C:\PS> ConvertFrom-StringData $string

Name                           Value
----                           -----
Msg3                           Enter an alias (or "nickname").
Msg2                           She said, "Hello, World."
Msg1                           Type "Windows".
```

Weitere Informationen zu here-Zeichen folgen finden Sie unter [about_Quoting_Rules](about_Quoting_Rules.md).

## <a name="see-also"></a>SIEHE AUCH

[about_Arrays](about_Arrays.md)

[about_Object_Creation](about_Object_Creation.md)

[about_Quoting_Rules](about_Quoting_Rules.md)

[about_Script_Internationalization](about_Script_Internationalization.md)

[ConvertFrom-StringData](xref:Microsoft.PowerShell.Utility.ConvertFrom-StringData)

[Import-LocalizedData](xref:Microsoft.PowerShell.Utility.Import-LocalizedData)

[System.Collections.Hashtable](/dotnet/api/system.collections.hashtable)

