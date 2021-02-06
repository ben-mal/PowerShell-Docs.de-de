---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 04/09/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/set-strictmode?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-StrictMode
ms.openlocfilehash: 58261830ca65da295aeb85cda22d0a78762e2502
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603728"
---
# <span data-ttu-id="93f82-102">Set-StrictMode</span><span class="sxs-lookup"><span data-stu-id="93f82-102">Set-StrictMode</span></span>

## <span data-ttu-id="93f82-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="93f82-103">SYNOPSIS</span></span>
<span data-ttu-id="93f82-104">Erstellt und erzwingt Codierungsregeln in Ausdrücken, Skripts und Skriptblöcken.</span><span class="sxs-lookup"><span data-stu-id="93f82-104">Establishes and enforces coding rules in expressions, scripts, and script blocks.</span></span>

## <span data-ttu-id="93f82-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="93f82-105">SYNTAX</span></span>

### <span data-ttu-id="93f82-106">Version (Standard)</span><span class="sxs-lookup"><span data-stu-id="93f82-106">Version (Default)</span></span>

```
Set-StrictMode -Version <Version> [<CommonParameters>]
```

### <span data-ttu-id="93f82-107">Aus</span><span class="sxs-lookup"><span data-stu-id="93f82-107">Off</span></span>

```
Set-StrictMode [-Off] [<CommonParameters>]
```

## <span data-ttu-id="93f82-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="93f82-108">DESCRIPTION</span></span>

<span data-ttu-id="93f82-109">Das- `Set-StrictMode` Cmdlet konfiguriert den Strict-Modus für den aktuellen Bereich und alle untergeordneten Bereiche und schaltet ihn ein bzw. aus.</span><span class="sxs-lookup"><span data-stu-id="93f82-109">The `Set-StrictMode` cmdlet configures strict mode for the current scope and all child scopes, and turns it on and off.</span></span> <span data-ttu-id="93f82-110">Wenn der Strict-Modus on ist, generiert PowerShell einen Fehler mit Abbruch, wenn der Inhalt eines Ausdrucks, Skripts oder Skript Blocks grundlegende Best Practices-Codierungsregeln verletzt.</span><span class="sxs-lookup"><span data-stu-id="93f82-110">When strict mode is on, PowerShell generates a terminating error when the content of an expression, script, or script block violates basic best-practice coding rules.</span></span>

<span data-ttu-id="93f82-111">Verwenden Sie den **Versions** Parameter, um zu bestimmen, welche Codierungsregeln erzwungen werden.</span><span class="sxs-lookup"><span data-stu-id="93f82-111">Use the **Version** parameter to determine which coding rules are enforced.</span></span>

<span data-ttu-id="93f82-112">`Set-PSDebug -Strict` -Cmdlet schaltet den Strict-Modus für den globalen Gültigkeitsbereich ein.</span><span class="sxs-lookup"><span data-stu-id="93f82-112">`Set-PSDebug -Strict` cmdlet turns on strict mode for the global scope.</span></span> <span data-ttu-id="93f82-113">`Set-StrictMode` wirkt sich nur auf den aktuellen Bereich und dessen untergeordnete Bereiche aus.</span><span class="sxs-lookup"><span data-stu-id="93f82-113">`Set-StrictMode` affects only the current scope and its child scopes.</span></span> <span data-ttu-id="93f82-114">Daher können Sie es in einem Skript oder einer Funktion verwenden, um die Einstellung zu überschreiben, die vom globalen Gültigkeitsbereich geerbt wurde.</span><span class="sxs-lookup"><span data-stu-id="93f82-114">Therefore, you can use it in a script or function to override the setting inherited from the global scope.</span></span>

<span data-ttu-id="93f82-115">Wenn deaktiviert `Set-StrictMode` ist, weist PowerShell folgendes Verhalten auf:</span><span class="sxs-lookup"><span data-stu-id="93f82-115">When `Set-StrictMode` is off, PowerShell has the following behaviors:</span></span>

- <span data-ttu-id="93f82-116">Für nicht initialisierte Variablen wird angenommen, dass Sie den Wert 0 (null) oder aufweist `$Null` , je nach Typ.</span><span class="sxs-lookup"><span data-stu-id="93f82-116">Uninitialized variables are assumed to have a value of 0 (zero) or `$Null`, depending on type</span></span>
- <span data-ttu-id="93f82-117">Verweise auf nicht vorhandene Eigenschaften geben zurück `$Null`</span><span class="sxs-lookup"><span data-stu-id="93f82-117">References to non-existent properties return `$Null`</span></span>
- <span data-ttu-id="93f82-118">Die Ergebnisse der nicht ordnungsgemäßen Funktions Syntax variieren mit den Fehlerbedingungen.</span><span class="sxs-lookup"><span data-stu-id="93f82-118">Results of improper function syntax vary with the error conditions</span></span>
- <span data-ttu-id="93f82-119">Der Versuch, einen Wert mit einem ungültigen Index in einem Array abzurufen, wird zurückgegeben. `$Null`</span><span class="sxs-lookup"><span data-stu-id="93f82-119">Attempting to retrieve a value using an invalid index in an array returns `$Null`</span></span>

## <span data-ttu-id="93f82-120">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="93f82-120">EXAMPLES</span></span>

### <span data-ttu-id="93f82-121">Beispiel 1: Aktivieren des Strict-Modus als Version 1,0</span><span class="sxs-lookup"><span data-stu-id="93f82-121">Example 1: Turn on strict mode as version 1.0</span></span>

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

<span data-ttu-id="93f82-122">Wenn der Strict-Modus auf Version 1,0 festgelegt ist, schlagen Versuche, auf nicht initialisierte Variablen zu verweisen, fehl.</span><span class="sxs-lookup"><span data-stu-id="93f82-122">With strict mode set to version 1.0, attempts to reference variables that are not initialized fail.</span></span>

### <span data-ttu-id="93f82-123">Beispiel 2: Aktivieren des Strict-Modus als Version 2,0</span><span class="sxs-lookup"><span data-stu-id="93f82-123">Example 2: Turn on strict mode as version 2.0</span></span>

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

<span data-ttu-id="93f82-124">Mit diesem Befehl wird der Strict-Modus eingeschaltet und auf Version 2,0 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="93f82-124">This command turns strict mode on and sets it to version 2.0.</span></span> <span data-ttu-id="93f82-125">Folglich gibt PowerShell einen Fehler zurück, wenn Sie die Methoden Syntax verwenden, die Klammern und Kommas für einen Funktions Aufrufwert verwendet oder auf nicht initialisierte Variablen oder nicht vorhandene Eigenschaften verweist.</span><span class="sxs-lookup"><span data-stu-id="93f82-125">As a result, PowerShell returns an error if you use method syntax, which uses parentheses and commas, for a function call or reference uninitialized variables or non-existent properties.</span></span>

<span data-ttu-id="93f82-126">Die Beispielausgabe zeigt die Auswirkung des Strict-Modus der Version 2,0.</span><span class="sxs-lookup"><span data-stu-id="93f82-126">The sample output shows the effect of version 2.0 strict mode.</span></span>

<span data-ttu-id="93f82-127">Ohne den Strict-Modus der Version 2.0 wird der Wert „(3,4)“ als einzelnes Arrayobjekt interpretiert, dem nichts hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="93f82-127">Without version 2.0 strict mode, the "(3,4)" value is interpreted as a single array object to which nothing is added.</span></span> <span data-ttu-id="93f82-128">Wenn Sie den Strict-Modus der Version 2,0 verwenden, wird er ordnungsgemäß als fehlerhafte Syntax zum Senden von zwei Werten interpretiert.</span><span class="sxs-lookup"><span data-stu-id="93f82-128">By using version 2.0 strict mode, it is correctly interpreted as faulty syntax for submitting two values.</span></span>

<span data-ttu-id="93f82-129">Ohne Version 2,0 gibt der Verweis auf die nicht vorhandene **Month** -Eigenschaft einer Zeichenfolge nur zurück `$Null` .</span><span class="sxs-lookup"><span data-stu-id="93f82-129">Without version 2.0, the reference to the non-existent **Month** property of a string returns only `$Null`.</span></span> <span data-ttu-id="93f82-130">Bei Verwendung von Version 2,0 wird Sie ordnungsgemäß als Verweis Fehler interpretiert.</span><span class="sxs-lookup"><span data-stu-id="93f82-130">By using version 2.0, it is interpreted correctly as a reference error.</span></span>

### <span data-ttu-id="93f82-131">Beispiel 3: Aktivieren des Strict-Modus als Version 3,0</span><span class="sxs-lookup"><span data-stu-id="93f82-131">Example 3: Turn on strict mode as version 3.0</span></span>

<span data-ttu-id="93f82-132">Wenn der Strict-Modus auf **Off** festgelegt ist, geben ungültige oder out-of-Limit-Indizes Ergebnisse NULL zurück</span><span class="sxs-lookup"><span data-stu-id="93f82-132">With strict mode set to **Off**, invalid or out of bounds indexes result return null values.</span></span>

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

<span data-ttu-id="93f82-133">Wenn der Strict-Modus auf Version 3 oder höher festgelegt ist, führen ungültige oder out-of-Bounds-Indizes zu Fehlern.</span><span class="sxs-lookup"><span data-stu-id="93f82-133">With strict mode set to version 3 or higher, invalid or out of bounds indexes result in errors.</span></span>

## <span data-ttu-id="93f82-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="93f82-134">PARAMETERS</span></span>

### <span data-ttu-id="93f82-135">-Aus</span><span class="sxs-lookup"><span data-stu-id="93f82-135">-Off</span></span>

<span data-ttu-id="93f82-136">Gibt an, dass dieses Cmdlet den Strict-Modus für den aktuellen Bereich und alle untergeordneten Bereiche deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="93f82-136">Indicates that this cmdlet turns strict mode off for the current scope and all child scopes.</span></span>

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

### <span data-ttu-id="93f82-137">-Version</span><span class="sxs-lookup"><span data-stu-id="93f82-137">-Version</span></span>

<span data-ttu-id="93f82-138">Gibt die Bedingungen an, die im Strict-Modus einen Fehler verursachen.</span><span class="sxs-lookup"><span data-stu-id="93f82-138">Specifies the conditions that cause an error in strict mode.</span></span> <span data-ttu-id="93f82-139">Dieser Parameter akzeptiert eine beliebige gültige PowerShell-Versionsnummer.</span><span class="sxs-lookup"><span data-stu-id="93f82-139">This parameter accepts any valid PowerShell version number.</span></span> <span data-ttu-id="93f82-140">Jede Zahl, die größer als 3 ist, wird als **neuestes** behandelt.</span><span class="sxs-lookup"><span data-stu-id="93f82-140">Any number higher than 3 is treated as **Latest**.</span></span>

<span data-ttu-id="93f82-141">Die effektiven Werte für diesen Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="93f82-141">The effective values for this parameter are:</span></span>

- <span data-ttu-id="93f82-142">1.0</span><span class="sxs-lookup"><span data-stu-id="93f82-142">1.0</span></span>
  - <span data-ttu-id="93f82-143">Verhindert Verweise auf nicht initialisierte Variablen, ausgenommen nicht initialisierte Variablen in Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="93f82-143">Prohibits references to uninitialized variables, except for uninitialized variables in strings.</span></span>
- <span data-ttu-id="93f82-144">2.0</span><span class="sxs-lookup"><span data-stu-id="93f82-144">2.0</span></span>
  - <span data-ttu-id="93f82-145">Verhindert Verweise auf nicht initialisierte Variablen.</span><span class="sxs-lookup"><span data-stu-id="93f82-145">Prohibits references to uninitialized variables.</span></span> <span data-ttu-id="93f82-146">Dies schließt nicht initialisierte Variablen in Zeichen folgen ein.</span><span class="sxs-lookup"><span data-stu-id="93f82-146">This includes uninitialized variables in strings.</span></span>
  - <span data-ttu-id="93f82-147">Verhindert Verweise auf nicht vorhandene Eigenschaften eines Objekts.</span><span class="sxs-lookup"><span data-stu-id="93f82-147">Prohibits references to non-existent properties of an object.</span></span>
  - <span data-ttu-id="93f82-148">Verhindert Funktionsaufrufe, die die Syntax zum Aufrufen von Methoden verwenden.</span><span class="sxs-lookup"><span data-stu-id="93f82-148">Prohibits function calls that use the syntax for calling methods.</span></span>
- <span data-ttu-id="93f82-149">3.0</span><span class="sxs-lookup"><span data-stu-id="93f82-149">3.0</span></span>
  - <span data-ttu-id="93f82-150">Verhindert Verweise auf nicht initialisierte Variablen.</span><span class="sxs-lookup"><span data-stu-id="93f82-150">Prohibits references to uninitialized variables.</span></span> <span data-ttu-id="93f82-151">Dies schließt nicht initialisierte Variablen in Zeichen folgen ein.</span><span class="sxs-lookup"><span data-stu-id="93f82-151">This includes uninitialized variables in strings.</span></span>
  - <span data-ttu-id="93f82-152">Verhindert Verweise auf nicht vorhandene Eigenschaften eines Objekts.</span><span class="sxs-lookup"><span data-stu-id="93f82-152">Prohibits references to non-existent properties of an object.</span></span>
  - <span data-ttu-id="93f82-153">Verhindert Funktionsaufrufe, die die Syntax zum Aufrufen von Methoden verwenden.</span><span class="sxs-lookup"><span data-stu-id="93f82-153">Prohibits function calls that use the syntax for calling methods.</span></span>
  - <span data-ttu-id="93f82-154">Nicht genügend Begrenzungen oder nicht auflösbare Array Indizes.</span><span class="sxs-lookup"><span data-stu-id="93f82-154">Prohibit out of bounds or unresolvable array indexes.</span></span>
- <span data-ttu-id="93f82-155">Latest</span><span class="sxs-lookup"><span data-stu-id="93f82-155">Latest</span></span>
  - <span data-ttu-id="93f82-156">Wählt die neueste verfügbare Version aus.</span><span class="sxs-lookup"><span data-stu-id="93f82-156">Selects the latest version available.</span></span> <span data-ttu-id="93f82-157">Die neueste Version ist die strengste Version.</span><span class="sxs-lookup"><span data-stu-id="93f82-157">The latest version is the most strict.</span></span> <span data-ttu-id="93f82-158">Verwenden Sie diesen Wert, um sicherzustellen, dass Skripts die strengste verfügbare Version verwenden, auch wenn neue Versionen zu PowerShell hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="93f82-158">Use this value to make sure that scripts use the strictest available version, even when new versions are added to PowerShell.</span></span>

> [!CAUTION]
> <span data-ttu-id="93f82-159">Verwenden einer **Version** von **Latest** in Skripts.</span><span class="sxs-lookup"><span data-stu-id="93f82-159">Using a **Version** of **Latest** in scripts.</span></span> <span data-ttu-id="93f82-160">Die Bedeutung von **Latest** kann sich in neuen Versionen von PowerShell ändern.</span><span class="sxs-lookup"><span data-stu-id="93f82-160">The meaning of **Latest** can change in new releases of PowerShell.</span></span> <span data-ttu-id="93f82-161">Ein Skript, das für eine ältere PowerShell-Version geschrieben wurde, `Set-StrictMode -Version Latest` unterliegt daher restriktiveren Regeln, wenn es in einer neueren Version von PowerShell ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="93f82-161">Therefore, a script written for an older version of PowerShell that uses `Set-StrictMode -Version Latest` is subject to more restrictive rules when run in a newer version of PowerShell.</span></span>

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

### <span data-ttu-id="93f82-162">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="93f82-162">CommonParameters</span></span>

<span data-ttu-id="93f82-163">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="93f82-163">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="93f82-164">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="93f82-164">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="93f82-165">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="93f82-165">INPUTS</span></span>

### <span data-ttu-id="93f82-166">Keine</span><span class="sxs-lookup"><span data-stu-id="93f82-166">None</span></span>

<span data-ttu-id="93f82-167">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="93f82-167">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="93f82-168">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="93f82-168">OUTPUTS</span></span>

### <span data-ttu-id="93f82-169">Keine</span><span class="sxs-lookup"><span data-stu-id="93f82-169">None</span></span>

<span data-ttu-id="93f82-170">Dieses Cmdlet gibt keine Ausgabe zurück.</span><span class="sxs-lookup"><span data-stu-id="93f82-170">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="93f82-171">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="93f82-171">NOTES</span></span>

<span data-ttu-id="93f82-172">`Set-StrictMode` ist nur in dem Bereich wirksam, in dem Sie festgelegt ist, und in den untergeordneten Bereichen.</span><span class="sxs-lookup"><span data-stu-id="93f82-172">`Set-StrictMode` is effective only in the scope in which it is set and in its child scopes.</span></span> <span data-ttu-id="93f82-173">Weitere Informationen zu Bereichen in PowerShell finden Sie unter [about_Scopes](about/about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="93f82-173">For more information about scopes in PowerShell, see [about_Scopes](about/about_Scopes.md).</span></span>

## <span data-ttu-id="93f82-174">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="93f82-174">RELATED LINKS</span></span>

[<span data-ttu-id="93f82-175">Set-PSDebug</span><span class="sxs-lookup"><span data-stu-id="93f82-175">Set-PSDebug</span></span>](Set-PSDebug.md)
