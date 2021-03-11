---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/10/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/set-strictmode?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-StrictMode
ms.openlocfilehash: bada911409d227a56ba53d44b0a64bcdf73c8959
ms.sourcegitcommit: 925819a5ad5799650c14944bd3e50fb309a7e6c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2021
ms.locfileid: "102771442"
---
# <span data-ttu-id="49781-103">Set-StrictMode</span><span class="sxs-lookup"><span data-stu-id="49781-103">Set-StrictMode</span></span>

## <span data-ttu-id="49781-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="49781-104">SYNOPSIS</span></span>
<span data-ttu-id="49781-105">Erstellt und erzwingt Codierungsregeln in Ausdrücken, Skripts und Skriptblöcken.</span><span class="sxs-lookup"><span data-stu-id="49781-105">Establishes and enforces coding rules in expressions, scripts, and script blocks.</span></span>

## <span data-ttu-id="49781-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="49781-106">SYNTAX</span></span>

### <span data-ttu-id="49781-107">Version (Standard)</span><span class="sxs-lookup"><span data-stu-id="49781-107">Version (Default)</span></span>

```
Set-StrictMode -Version <Version> [<CommonParameters>]
```

### <span data-ttu-id="49781-108">Aus</span><span class="sxs-lookup"><span data-stu-id="49781-108">Off</span></span>

```
Set-StrictMode [-Off] [<CommonParameters>]
```

## <span data-ttu-id="49781-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="49781-109">DESCRIPTION</span></span>

<span data-ttu-id="49781-110">Das- `Set-StrictMode` Cmdlet konfiguriert den Strict-Modus für den aktuellen Bereich und alle untergeordneten Bereiche und schaltet ihn ein bzw. aus.</span><span class="sxs-lookup"><span data-stu-id="49781-110">The `Set-StrictMode` cmdlet configures strict mode for the current scope and all child scopes, and turns it on and off.</span></span> <span data-ttu-id="49781-111">Wenn der Strict-Modus on ist, generiert PowerShell einen Fehler mit Abbruch, wenn der Inhalt eines Ausdrucks, Skripts oder Skript Blocks grundlegende Best Practices-Codierungsregeln verletzt.</span><span class="sxs-lookup"><span data-stu-id="49781-111">When strict mode is on, PowerShell generates a terminating error when the content of an expression, script, or script block violates basic best-practice coding rules.</span></span>

<span data-ttu-id="49781-112">Verwenden Sie den **Versions** Parameter, um zu bestimmen, welche Codierungsregeln erzwungen werden.</span><span class="sxs-lookup"><span data-stu-id="49781-112">Use the **Version** parameter to determine which coding rules are enforced.</span></span>

<span data-ttu-id="49781-113">`Set-PSDebug -Strict` -Cmdlet schaltet den Strict-Modus für den globalen Gültigkeitsbereich ein.</span><span class="sxs-lookup"><span data-stu-id="49781-113">`Set-PSDebug -Strict` cmdlet turns on strict mode for the global scope.</span></span> <span data-ttu-id="49781-114">`Set-StrictMode` wirkt sich nur auf den aktuellen Bereich und dessen untergeordnete Bereiche aus.</span><span class="sxs-lookup"><span data-stu-id="49781-114">`Set-StrictMode` affects only the current scope and its child scopes.</span></span> <span data-ttu-id="49781-115">Daher können Sie es in einem Skript oder einer Funktion verwenden, um die Einstellung zu überschreiben, die vom globalen Gültigkeitsbereich geerbt wurde.</span><span class="sxs-lookup"><span data-stu-id="49781-115">Therefore, you can use it in a script or function to override the setting inherited from the global scope.</span></span>

<span data-ttu-id="49781-116">Wenn deaktiviert `Set-StrictMode` ist, weist PowerShell folgendes Verhalten auf:</span><span class="sxs-lookup"><span data-stu-id="49781-116">When `Set-StrictMode` is off, PowerShell has the following behaviors:</span></span>

- <span data-ttu-id="49781-117">Für nicht initialisierte Variablen wird angenommen, dass Sie den Wert 0 (null) oder aufweist `$Null` , je nach Typ.</span><span class="sxs-lookup"><span data-stu-id="49781-117">Uninitialized variables are assumed to have a value of 0 (zero) or `$Null`, depending on type</span></span>
- <span data-ttu-id="49781-118">Verweise auf nicht vorhandene Eigenschaften geben zurück `$Null`</span><span class="sxs-lookup"><span data-stu-id="49781-118">References to non-existent properties return `$Null`</span></span>
- <span data-ttu-id="49781-119">Die Ergebnisse der nicht ordnungsgemäßen Funktions Syntax variieren mit den Fehlerbedingungen.</span><span class="sxs-lookup"><span data-stu-id="49781-119">Results of improper function syntax vary with the error conditions</span></span>
- <span data-ttu-id="49781-120">Der Versuch, einen Wert mit einem ungültigen Index in einem Array abzurufen, wird zurückgegeben. `$Null`</span><span class="sxs-lookup"><span data-stu-id="49781-120">Attempting to retrieve a value using an invalid index in an array returns `$Null`</span></span>

## <span data-ttu-id="49781-121">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="49781-121">EXAMPLES</span></span>

### <span data-ttu-id="49781-122">Beispiel 1: Aktivieren des Strict-Modus als Version 1,0</span><span class="sxs-lookup"><span data-stu-id="49781-122">Example 1: Turn on strict mode as version 1.0</span></span>

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

<span data-ttu-id="49781-123">Wenn der Strict-Modus auf Version 1,0 festgelegt ist, schlagen Versuche, auf nicht initialisierte Variablen zu verweisen, fehl.</span><span class="sxs-lookup"><span data-stu-id="49781-123">With strict mode set to version 1.0, attempts to reference variables that are not initialized fail.</span></span>

### <span data-ttu-id="49781-124">Beispiel 2: Aktivieren des Strict-Modus als Version 2,0</span><span class="sxs-lookup"><span data-stu-id="49781-124">Example 2: Turn on strict mode as version 2.0</span></span>

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

<span data-ttu-id="49781-125">Mit diesem Befehl wird der Strict-Modus eingeschaltet und auf Version 2,0 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="49781-125">This command turns strict mode on and sets it to version 2.0.</span></span> <span data-ttu-id="49781-126">Folglich gibt PowerShell einen Fehler zurück, wenn Sie die Methoden Syntax verwenden, die Klammern und Kommas für einen Funktions Aufrufwert verwendet oder auf nicht initialisierte Variablen oder nicht vorhandene Eigenschaften verweist.</span><span class="sxs-lookup"><span data-stu-id="49781-126">As a result, PowerShell returns an error if you use method syntax, which uses parentheses and commas, for a function call or reference uninitialized variables or non-existent properties.</span></span>

<span data-ttu-id="49781-127">Die Beispielausgabe zeigt die Auswirkung des Strict-Modus der Version 2,0.</span><span class="sxs-lookup"><span data-stu-id="49781-127">The sample output shows the effect of version 2.0 strict mode.</span></span>

<span data-ttu-id="49781-128">Ohne den Strict-Modus der Version 2.0 wird der Wert „(3,4)“ als einzelnes Arrayobjekt interpretiert, dem nichts hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="49781-128">Without version 2.0 strict mode, the "(3,4)" value is interpreted as a single array object to which nothing is added.</span></span> <span data-ttu-id="49781-129">Wenn Sie den Strict-Modus der Version 2,0 verwenden, wird er ordnungsgemäß als fehlerhafte Syntax zum Senden von zwei Werten interpretiert.</span><span class="sxs-lookup"><span data-stu-id="49781-129">By using version 2.0 strict mode, it is correctly interpreted as faulty syntax for submitting two values.</span></span>

<span data-ttu-id="49781-130">Ohne Version 2,0 gibt der Verweis auf die nicht vorhandene **Month** -Eigenschaft einer Zeichenfolge nur zurück `$Null` .</span><span class="sxs-lookup"><span data-stu-id="49781-130">Without version 2.0, the reference to the non-existent **Month** property of a string returns only `$Null`.</span></span> <span data-ttu-id="49781-131">Bei Verwendung von Version 2,0 wird Sie ordnungsgemäß als Verweis Fehler interpretiert.</span><span class="sxs-lookup"><span data-stu-id="49781-131">By using version 2.0, it is interpreted correctly as a reference error.</span></span>

### <span data-ttu-id="49781-132">Beispiel 3: Aktivieren des Strict-Modus als Version 3,0</span><span class="sxs-lookup"><span data-stu-id="49781-132">Example 3: Turn on strict mode as version 3.0</span></span>

<span data-ttu-id="49781-133">Wenn der Strict-Modus auf **Off** festgelegt ist, geben ungültige oder out-of-Limit-Indizes Ergebnisse NULL zurück</span><span class="sxs-lookup"><span data-stu-id="49781-133">With strict mode set to **Off**, invalid or out of bounds indexes result return null values.</span></span>

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

<span data-ttu-id="49781-134">Wenn der Strict-Modus auf Version 3 oder höher festgelegt ist, führen ungültige oder out-of-Bounds-Indizes zu Fehlern.</span><span class="sxs-lookup"><span data-stu-id="49781-134">With strict mode set to version 3 or higher, invalid or out of bounds indexes result in errors.</span></span>

## <span data-ttu-id="49781-135">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="49781-135">PARAMETERS</span></span>

### <span data-ttu-id="49781-136">-Aus</span><span class="sxs-lookup"><span data-stu-id="49781-136">-Off</span></span>

<span data-ttu-id="49781-137">Gibt an, dass dieses Cmdlet den Strict-Modus für den aktuellen Bereich und alle untergeordneten Bereiche deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="49781-137">Indicates that this cmdlet turns strict mode off for the current scope and all child scopes.</span></span>

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

### <span data-ttu-id="49781-138">-Version</span><span class="sxs-lookup"><span data-stu-id="49781-138">-Version</span></span>

<span data-ttu-id="49781-139">Gibt die Bedingungen an, die im Strict-Modus einen Fehler verursachen.</span><span class="sxs-lookup"><span data-stu-id="49781-139">Specifies the conditions that cause an error in strict mode.</span></span> <span data-ttu-id="49781-140">Dieser Parameter akzeptiert eine beliebige gültige PowerShell-Versionsnummer.</span><span class="sxs-lookup"><span data-stu-id="49781-140">This parameter accepts any valid PowerShell version number.</span></span> <span data-ttu-id="49781-141">Jede Zahl, die größer als 3 ist, wird als **neuestes** behandelt.</span><span class="sxs-lookup"><span data-stu-id="49781-141">Any number higher than 3 is treated as **Latest**.</span></span>

<span data-ttu-id="49781-142">Die effektiven Werte für diesen Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="49781-142">The effective values for this parameter are:</span></span>

- <span data-ttu-id="49781-143">1.0</span><span class="sxs-lookup"><span data-stu-id="49781-143">1.0</span></span>
  - <span data-ttu-id="49781-144">Verhindert Verweise auf nicht initialisierte Variablen, ausgenommen nicht initialisierte Variablen in Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="49781-144">Prohibits references to uninitialized variables, except for uninitialized variables in strings.</span></span>
- <span data-ttu-id="49781-145">2.0</span><span class="sxs-lookup"><span data-stu-id="49781-145">2.0</span></span>
  - <span data-ttu-id="49781-146">Verhindert Verweise auf nicht initialisierte Variablen.</span><span class="sxs-lookup"><span data-stu-id="49781-146">Prohibits references to uninitialized variables.</span></span> <span data-ttu-id="49781-147">Dies schließt nicht initialisierte Variablen in Zeichen folgen ein.</span><span class="sxs-lookup"><span data-stu-id="49781-147">This includes uninitialized variables in strings.</span></span>
  - <span data-ttu-id="49781-148">Verhindert Verweise auf nicht vorhandene Eigenschaften eines Objekts.</span><span class="sxs-lookup"><span data-stu-id="49781-148">Prohibits references to non-existent properties of an object.</span></span>
  - <span data-ttu-id="49781-149">Verhindert Funktionsaufrufe, die die Syntax zum Aufrufen von Methoden verwenden.</span><span class="sxs-lookup"><span data-stu-id="49781-149">Prohibits function calls that use the syntax for calling methods.</span></span>
- <span data-ttu-id="49781-150">3.0</span><span class="sxs-lookup"><span data-stu-id="49781-150">3.0</span></span>
  - <span data-ttu-id="49781-151">Verhindert Verweise auf nicht initialisierte Variablen.</span><span class="sxs-lookup"><span data-stu-id="49781-151">Prohibits references to uninitialized variables.</span></span> <span data-ttu-id="49781-152">Dies schließt nicht initialisierte Variablen in Zeichen folgen ein.</span><span class="sxs-lookup"><span data-stu-id="49781-152">This includes uninitialized variables in strings.</span></span>
  - <span data-ttu-id="49781-153">Verhindert Verweise auf nicht vorhandene Eigenschaften eines Objekts.</span><span class="sxs-lookup"><span data-stu-id="49781-153">Prohibits references to non-existent properties of an object.</span></span>
  - <span data-ttu-id="49781-154">Verhindert Funktionsaufrufe, die die Syntax zum Aufrufen von Methoden verwenden.</span><span class="sxs-lookup"><span data-stu-id="49781-154">Prohibits function calls that use the syntax for calling methods.</span></span>
  - <span data-ttu-id="49781-155">Nicht genügend Begrenzungen oder nicht auflösbare Array Indizes.</span><span class="sxs-lookup"><span data-stu-id="49781-155">Prohibit out of bounds or unresolvable array indexes.</span></span>
- <span data-ttu-id="49781-156">Neueste</span><span class="sxs-lookup"><span data-stu-id="49781-156">Latest</span></span>
  - <span data-ttu-id="49781-157">Wählt die neueste verfügbare Version aus.</span><span class="sxs-lookup"><span data-stu-id="49781-157">Selects the latest version available.</span></span> <span data-ttu-id="49781-158">Die neueste Version ist die strengste Version.</span><span class="sxs-lookup"><span data-stu-id="49781-158">The latest version is the most strict.</span></span> <span data-ttu-id="49781-159">Verwenden Sie diesen Wert, um sicherzustellen, dass Skripts die strengste verfügbare Version verwenden, auch wenn neue Versionen zu PowerShell hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="49781-159">Use this value to make sure that scripts use the strictest available version, even when new versions are added to PowerShell.</span></span>

> [!CAUTION]
> <span data-ttu-id="49781-160">Verwenden einer **Version** von **Latest** in Skripts.</span><span class="sxs-lookup"><span data-stu-id="49781-160">Using a **Version** of **Latest** in scripts.</span></span> <span data-ttu-id="49781-161">Die Bedeutung von **Latest** kann sich in neuen Versionen von PowerShell ändern.</span><span class="sxs-lookup"><span data-stu-id="49781-161">The meaning of **Latest** can change in new releases of PowerShell.</span></span> <span data-ttu-id="49781-162">Ein Skript, das für eine ältere PowerShell-Version geschrieben wurde, `Set-StrictMode -Version Latest` unterliegt daher restriktiveren Regeln, wenn es in einer neueren Version von PowerShell ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="49781-162">Therefore, a script written for an older version of PowerShell that uses `Set-StrictMode -Version Latest` is subject to more restrictive rules when run in a newer version of PowerShell.</span></span>

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

### <span data-ttu-id="49781-163">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="49781-163">CommonParameters</span></span>

<span data-ttu-id="49781-164">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="49781-164">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="49781-165">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="49781-165">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="49781-166">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="49781-166">INPUTS</span></span>

### <span data-ttu-id="49781-167">Keine</span><span class="sxs-lookup"><span data-stu-id="49781-167">None</span></span>

<span data-ttu-id="49781-168">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="49781-168">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="49781-169">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="49781-169">OUTPUTS</span></span>

### <span data-ttu-id="49781-170">Keine</span><span class="sxs-lookup"><span data-stu-id="49781-170">None</span></span>

<span data-ttu-id="49781-171">Dieses Cmdlet gibt keine Ausgabe zurück.</span><span class="sxs-lookup"><span data-stu-id="49781-171">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="49781-172">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="49781-172">NOTES</span></span>

<span data-ttu-id="49781-173">Obwohl der `Set-StrictMode` **Versions** Parameterwerte überschreitet `3.0` , die größer als sind, sind zurzeit keine weiteren Regeln für etwas höher als definiert `3.0` .</span><span class="sxs-lookup"><span data-stu-id="49781-173">While `Set-StrictMode` **Version** parameter will accept values greater than `3.0`, currently there are no additional rules defined for anything higher than `3.0`.</span></span>

<span data-ttu-id="49781-174">`Set-StrictMode` ist nur in dem Bereich wirksam, in dem Sie festgelegt ist, und in den untergeordneten Bereichen.</span><span class="sxs-lookup"><span data-stu-id="49781-174">`Set-StrictMode` is effective only in the scope in which it is set and in its child scopes.</span></span> <span data-ttu-id="49781-175">Weitere Informationen zu Bereichen in PowerShell finden Sie unter [about_Scopes](about/about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="49781-175">For more information about scopes in PowerShell, see [about_Scopes](about/about_Scopes.md).</span></span>

## <span data-ttu-id="49781-176">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="49781-176">RELATED LINKS</span></span>

[<span data-ttu-id="49781-177">Set-PSDebug</span><span class="sxs-lookup"><span data-stu-id="49781-177">Set-PSDebug</span></span>](Set-PSDebug.md)
