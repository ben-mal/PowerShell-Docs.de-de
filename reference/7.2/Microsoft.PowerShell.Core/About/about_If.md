---
description: Beschreibt einen Sprachbefehl, den Sie verwenden können, um Anweisungs Listen basierend auf den Ergebnissen von einem oder mehreren bedingten Tests auszuführen.
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_if?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_If
ms.openlocfilehash: 04c610af36e17c02d2440ab79b7de5330e5063ab
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601123"
---
# <a name="about-if"></a>Informationen zu if

## <a name="short-description"></a>KURZE BESCHREIBUNG
Beschreibt einen Sprachbefehl, den Sie verwenden können, um Anweisungs Listen basierend auf den Ergebnissen von einem oder mehreren bedingten Tests auszuführen.

## <a name="long-description"></a>LANGE BESCHREIBUNG

Sie können die- `If` Anweisung verwenden, um Code Blöcke auszuführen, wenn für einen angegebenen bedingten Test true ausgewertet wird. Sie können auch einen oder mehrere zusätzliche bedingte Tests angeben, die ausgeführt werden sollen, wenn alle vorherigen Tests als false ausgewertet werden. Schließlich können Sie einen zusätzlichen Codeblock angeben, der ausgeführt wird, wenn kein anderer vorheriger bedingter Test zu true ausgewertet wird.

### <a name="syntax"></a>Syntax

Das folgende Beispiel zeigt die `If` Syntax der Anweisung:

```powershell
if (<test1>)
    {<statement list 1>}
[elseif (<test2>)
    {<statement list 2>}]
[else
    {<statement list 3>}]
```

Wenn Sie eine- `If` Anweisung ausführen, wertet PowerShell den `<test1>` bedingten Ausdruck als "true" oder "false" aus. Wenn `<test1>` true ist, wird ausgeführt `<statement list 1>` , und PowerShell beendet die- `If` Anweisung. Wenn `<test1>` den Wert false hat, wertet PowerShell die durch die `<test2>` bedingte Anweisung angegebene Bedingung aus.

Wenn `<test2>` true ist, wird ausgeführt `<statement list 2>` , und PowerShell beendet die- `If` Anweisung. Wenn sowohl `<test1>` als auch als `<test2>` false ausgewertet wird, wird der `<statement list 3`> Codeblock ausgeführt, und PowerShell beendet die if-Anweisung.

Sie können mehrere ElseIf-Anweisungen verwenden, um eine Reihe von bedingten Tests zu verketten. Daher wird jeder Test nur ausgeführt, wenn alle vorherigen Tests false sind.
Wenn Sie eine-Anweisung erstellen müssen, `If` die viele ElseIf-Anweisungen enthält, sollten Sie stattdessen eine Switch-Anweisung verwenden.

Beispiele:

Die einfachste `If` Anweisung enthält einen einzelnen Befehl, der keine ElseIf-Anweisungen oder andere Anweisungen enthält. Das folgende Beispiel zeigt die einfachste Form der- `If` Anweisung:

```powershell
if ($a -gt 2) {
    Write-Host "The value $a is greater than 2."
}
```

Wenn die $a Variable in diesem Beispiel größer als 2 ist, wird die Bedingung als "true" ausgewertet, und die Anweisungs Liste wird ausgeführt. Wenn $a jedoch kleiner oder gleich 2 ist oder keine vorhandene Variable ist, `If` zeigt die Anweisung keine Meldung an.

Wenn eine Else-Anweisung hinzugefügt wird, wird eine Meldung angezeigt, wenn $a kleiner oder gleich 2 ist. Das nächste Beispiel zeigt Folgendes:

```powershell
if ($a -gt 2) {
    Write-Host "The value $a is greater than 2."
}
else {
    Write-Host ("The value $a is less than or equal to 2," +
        " is not created or is not initialized.")
}
```

Zum weiteren verfeinern dieses Beispiels können Sie die ElseIf-Anweisung verwenden, um eine Meldung anzuzeigen, wenn der Wert von $a gleich 2 ist. Das nächste Beispiel zeigt Folgendes:

```powershell
if ($a -gt 2) {
    Write-Host "The value $a is greater than 2."
}
elseif ($a -eq 2) {
    Write-Host "The value $a is equal to 2."
}
else {
    Write-Host ("The value $a is less than 2 or" +
        " was not created or initialized.")
}
```

### <a name="using-the-ternary-operator-syntax"></a>Verwenden der ternären Operator Syntax

PowerShell 7,0 hat mit dem ternären Operator eine neue Syntax eingeführt. Er folgt der c#-Syntax für Ternäre Operatoren:

```Syntax
<condition> ? <if-true> : <if-false>
```

Der ternäre Operator verhält sich wie die vereinfachte- `if-else` Anweisung. Der `<condition>` Ausdruck wird ausgewertet, und das Ergebnis wird in einen booleschen Wert konvertiert, um zu bestimmen, welcher Branch als nächstes ausgewertet werden soll:

- Der Ausdruck `<if-true>` wird ausgeführt, wenn der Ausdruck `<condition>` TRUE ist.
- Der Ausdruck `<if-false>` wird ausgeführt, wenn der Ausdruck `<condition>` FALSE ist.

Beispiel:

```powershell
$message = (Test-Path $path) ? "Path exists" : "Path not found"
```

In diesem Beispiel ist der Wert von `$message` "Path vorhanden", wenn `Test-Path` zurückgibt `$true` . Wenn `Test-Path` zurückgibt `$false` , lautet der Wert von `$message` "Pfad nicht gefunden".

```powershell
$service = Get-Service BITS
$service.Status -eq 'Running' ? (Stop-Service $service) : (Start-Service $service)
```

Wenn der Dienst in diesem Beispiel ausgeführt wird, wird er beendet, und wenn sein Status nicht **ausgeführt** wird, wird er gestartet.

## <a name="see-also"></a>SIEHE AUCH

[about_Comparison_Operators](about_Comparison_Operators.md)

[about_Switch](about_Switch.md)

