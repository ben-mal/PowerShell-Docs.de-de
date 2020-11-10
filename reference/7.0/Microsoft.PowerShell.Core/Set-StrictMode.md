---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 04/09/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/set-strictmode?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-StrictMode
ms.openlocfilehash: aea54dfa2ade8a9b7b67ca82fb0d6365e6eea3c4
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94391339"
---
# Set-StrictMode

## ZUSAMMENFASSUNG
Erstellt und erzwingt Codierungsregeln in Ausdrücken, Skripts und Skriptblöcken.

## SYNTAX

### Version (Standard)

```
Set-StrictMode -Version <Version> [<CommonParameters>]
```

### Aus

```
Set-StrictMode [-Off] [<CommonParameters>]
```

## DESCRIPTION

Das- `Set-StrictMode` Cmdlet konfiguriert den Strict-Modus für den aktuellen Bereich und alle untergeordneten Bereiche und schaltet ihn ein bzw. aus. Wenn der Strict-Modus on ist, generiert PowerShell einen Fehler mit Abbruch, wenn der Inhalt eines Ausdrucks, Skripts oder Skript Blocks grundlegende Best Practices-Codierungsregeln verletzt.

Verwenden Sie den **Versions** Parameter, um zu bestimmen, welche Codierungsregeln erzwungen werden.

`Set-PSDebug -Strict` -Cmdlet schaltet den Strict-Modus für den globalen Gültigkeitsbereich ein. `Set-StrictMode` wirkt sich nur auf den aktuellen Bereich und dessen untergeordnete Bereiche aus. Daher können Sie es in einem Skript oder einer Funktion verwenden, um die Einstellung zu überschreiben, die vom globalen Gültigkeitsbereich geerbt wurde.

Wenn deaktiviert `Set-StrictMode` ist, weist PowerShell folgendes Verhalten auf:

- Für nicht initialisierte Variablen wird angenommen, dass Sie den Wert 0 (null) oder aufweist `$Null` , je nach Typ.
- Verweise auf nicht vorhandene Eigenschaften geben zurück `$Null`
- Die Ergebnisse der nicht ordnungsgemäßen Funktions Syntax variieren mit den Fehlerbedingungen.
- Der Versuch, einen Wert mit einem ungültigen Index in einem Array abzurufen, wird zurückgegeben. `$Null`

## BEISPIELE

### Beispiel 1: Aktivieren des Strict-Modus als Version 1,0

```powershell
# Strict mode is off by default.
$a -gt 5
```

```Output
False
```

```powershell
Set-StrictMode -Version 1.0
$a -gt 5
```

```Output
InvalidOperation: The variable '$a' cannot be retrieved because it has not been set.
```

Wenn der Strict-Modus auf Version 1,0 festgelegt ist, schlagen Versuche, auf nicht initialisierte Variablen zu verweisen, fehl.

### Beispiel 2: Aktivieren des Strict-Modus als Version 2,0

```powershell
# Strict mode is off by default.
function add ($a, $b) {
    '$a = ' + $a
    '$b = ' + $b
    '$a+$b = ' + ($a + $b)
}
add 3 4
```

```Output
$a = 3
$b = 4
$a+$b = 7
```

```powershell
add(3,4)
```

```Output
$a = 3 4
$b =
$a+$b = 3 4
```

```powershell
Set-StrictMode -Version 2.0
add(3,4)
```

```Output
InvalidOperation: The function or command was called as if it were a method. Parameters should be separated by spaces. For information about parameters, see the about_Parameters Help topic.
```

```powershell
Set-StrictMode -Off
$string = "This is a string."
$null -eq $string.Month
```

```Output
True
```

```powershell
Set-StrictMode -Version 2.0
$string = "This is a string."
$null -eq $string.Month
```

```Output
PropertyNotFoundException: The property 'Month' cannot be found on this object. Verify that the property exists.
```

Mit diesem Befehl wird der Strict-Modus eingeschaltet und auf Version 2,0 festgelegt. Folglich gibt PowerShell einen Fehler zurück, wenn Sie die Methoden Syntax verwenden, die Klammern und Kommas für einen Funktions Aufrufwert verwendet oder auf nicht initialisierte Variablen oder nicht vorhandene Eigenschaften verweist.

Die Beispielausgabe zeigt die Auswirkung des Strict-Modus der Version 2,0.

Ohne den Strict-Modus der Version 2.0 wird der Wert „(3,4)“ als einzelnes Arrayobjekt interpretiert, dem nichts hinzugefügt wird. Wenn Sie den Strict-Modus der Version 2,0 verwenden, wird er ordnungsgemäß als fehlerhafte Syntax zum Senden von zwei Werten interpretiert.

Ohne Version 2,0 gibt der Verweis auf die nicht vorhandene **Month** -Eigenschaft einer Zeichenfolge nur zurück `$Null` . Bei Verwendung von Version 2,0 wird Sie ordnungsgemäß als Verweis Fehler interpretiert.

### Beispiel 3: Aktivieren des Strict-Modus als Version 3,0

Wenn der Strict-Modus auf **Off** festgelegt ist, geben ungültige oder out-of-Limit-Indizes Ergebnisse NULL zurück

```powershell
# Strict mode is off by default.
$a = @(1)
$null -eq $a[2]
$null -eq $a['abc']
```

```Output
True
True
```

```powershell
Set-StrictMode -Version 3
$a = @(1)
$null -eq $a[2]
$null -eq $a['abc']
```

```Output
OperationStopped: Index was outside the bounds of the array.

InvalidArgument: Cannot convert value "abc" to type "System.Int32". Error: "Input string was not in a correct format."
```

Wenn der Strict-Modus auf Version 3 oder höher festgelegt ist, führen ungültige oder out-of-Bounds-Indizes zu Fehlern.

## PARAMETERS

### -Aus

Gibt an, dass dieses Cmdlet den Strict-Modus für den aktuellen Bereich und alle untergeordneten Bereiche deaktiviert.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Off
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Version

Gibt die Bedingungen an, die im Strict-Modus einen Fehler verursachen. Dieser Parameter akzeptiert eine beliebige gültige PowerShell-Versionsnummer. Jede Zahl, die größer als 3 ist, wird als **neuestes** behandelt.

Die effektiven Werte für diesen Parameter lauten wie folgt:

- 1,0
  - Verhindert Verweise auf nicht initialisierte Variablen, ausgenommen nicht initialisierte Variablen in Zeichen folgen.
- 2.0
  - Verhindert Verweise auf nicht initialisierte Variablen. Dies schließt nicht initialisierte Variablen in Zeichen folgen ein.
  - Verhindert Verweise auf nicht vorhandene Eigenschaften eines Objekts.
  - Verhindert Funktionsaufrufe, die die Syntax zum Aufrufen von Methoden verwenden.
- 3.0
  - Verhindert Verweise auf nicht initialisierte Variablen. Dies schließt nicht initialisierte Variablen in Zeichen folgen ein.
  - Verhindert Verweise auf nicht vorhandene Eigenschaften eines Objekts.
  - Verhindert Funktionsaufrufe, die die Syntax zum Aufrufen von Methoden verwenden.
  - Nicht genügend Begrenzungen oder nicht auflösbare Array Indizes.
- Neueste Version
  - Wählt die neueste verfügbare Version aus. Die neueste Version ist die strengste Version. Verwenden Sie diesen Wert, um sicherzustellen, dass Skripts die strengste verfügbare Version verwenden, auch wenn neue Versionen zu PowerShell hinzugefügt werden.

> [!CAUTION]
> Verwenden einer **Version** von **Latest** in Skripts. Die Bedeutung von **Latest** kann sich in neuen Versionen von PowerShell ändern. Ein Skript, das für eine ältere PowerShell-Version geschrieben wurde, `Set-StrictMode -Version Latest` unterliegt daher restriktiveren Regeln, wenn es in einer neueren Version von PowerShell ausgeführt wird.

```yaml
Type: System.Version
Parameter Sets: Version
Aliases: v

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine

Eingaben können nicht an dieses Cmdlet weitergereicht werden.

## AUSGABEN

### Keine

Dieses Cmdlet gibt keine Ausgabe zurück.

## HINWEISE

`Set-StrictMode` ist nur in dem Bereich wirksam, in dem Sie festgelegt ist, und in den untergeordneten Bereichen. Weitere Informationen zu Bereichen in PowerShell finden Sie unter [about_Scopes](about/about_Scopes.md).

## VERWANDTE LINKS

[Set-PSDebug](Set-PSDebug.md)
