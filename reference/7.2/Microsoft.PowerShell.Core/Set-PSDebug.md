---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 08/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/set-psdebug?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSDebug
ms.openlocfilehash: 45764b09bfa1f632fe5c36ca76b32b4a1b54874c
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596156"
---
# <span data-ttu-id="0d157-102">Set-PSDebug</span><span class="sxs-lookup"><span data-stu-id="0d157-102">Set-PSDebug</span></span>

## <span data-ttu-id="0d157-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="0d157-103">SYNOPSIS</span></span>
<span data-ttu-id="0d157-104">Aktiviert bzw. deaktiviert Skriptdebuggingfeatures, legt die Ablaufverfolgungsebene fest und schaltet den Strict-Modus um.</span><span class="sxs-lookup"><span data-stu-id="0d157-104">Turns script debugging features on and off, sets the trace level, and toggles strict mode.</span></span>

## <span data-ttu-id="0d157-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0d157-105">SYNTAX</span></span>

### <span data-ttu-id="0d157-106">on</span><span class="sxs-lookup"><span data-stu-id="0d157-106">on</span></span>

```
Set-PSDebug [-Trace <Int32>] [-Step] [-Strict] [<CommonParameters>]
```

### <span data-ttu-id="0d157-107">aus</span><span class="sxs-lookup"><span data-stu-id="0d157-107">off</span></span>

```
Set-PSDebug [-Off] [<CommonParameters>]
```

## <span data-ttu-id="0d157-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0d157-108">DESCRIPTION</span></span>

<span data-ttu-id="0d157-109">Das `Set-PSDebug` -Cmdlet aktiviert und deaktiviert skriptdebuggingfeatures, legt die Ablauf Verfolgungs Ebene fest und schaltet den Strict-Modus um.</span><span class="sxs-lookup"><span data-stu-id="0d157-109">The `Set-PSDebug` cmdlet turns script debugging features on and off, sets the trace level, and toggles strict mode.</span></span> <span data-ttu-id="0d157-110">Die PowerShell-Debuggingfunktionen sind standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="0d157-110">By default, the PowerShell debug features are off.</span></span>

<span data-ttu-id="0d157-111">Wenn der **Trace** -Parameter den Wert aufweist `1` , wird jede Zeile des Skripts während der Ausführung verfolgt.</span><span class="sxs-lookup"><span data-stu-id="0d157-111">When the **Trace** parameter has a value of `1`, each line of script is traced as it runs.</span></span> <span data-ttu-id="0d157-112">Wenn der-Parameter den Wert aufweist `2` , werden auch Variablen Zuweisungen, Funktionsaufrufe und Skript Aufrufe verfolgt.</span><span class="sxs-lookup"><span data-stu-id="0d157-112">When the parameter has a value of `2`, variable assignments, function calls, and script calls are also traced.</span></span> <span data-ttu-id="0d157-113">Wenn der **Step** -Parameter angegeben wird, werden Sie aufgefordert, bevor die einzelnen Zeilen des Skripts ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="0d157-113">If the **Step** parameter is specified, you're prompted before each line of the script runs.</span></span>

## <span data-ttu-id="0d157-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="0d157-114">EXAMPLES</span></span>

### <span data-ttu-id="0d157-115">Beispiel 1: Festlegen der Ablauf Verfolgungs Ebene</span><span class="sxs-lookup"><span data-stu-id="0d157-115">Example 1: Set the trace level</span></span>

<span data-ttu-id="0d157-116">Dieses Beispiel legt die Ablauf Verfolgungs Ebene auf fest `2` und führt dann ein Skript aus, das die Zahlen 1, 2 und</span><span class="sxs-lookup"><span data-stu-id="0d157-116">This example sets the trace level to `2`, and then runs a script that displays the numbers 1, 2, and</span></span>
3.

```powershell
Set-PSDebug -Trace 2; foreach ($i in 1..3) {$i}
```

```Output
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ($i in  >>>> 1..3) {$i}
DEBUG:     ! SET $foreach = 'IEnumerator'.
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ( >>>> $i in 1..3) {$i}
DEBUG:     ! SET $i = '1'.
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ($i in 1..3) { >>>> $i}
1
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ( >>>> $i in 1..3) {$i}
DEBUG:     ! SET $i = '2'.
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ($i in 1..3) { >>>> $i}
2
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ( >>>> $i in 1..3) {$i}
DEBUG:     ! SET $i = '3'.
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ($i in 1..3) { >>>> $i}
3
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ( >>>> $i in 1..3) {$i}
DEBUG:     ! SET $foreach = ''.
```

### <span data-ttu-id="0d157-117">Beispiel 2: Aktivieren des durch Schrittes</span><span class="sxs-lookup"><span data-stu-id="0d157-117">Example 2: Turn on stepping</span></span>

<span data-ttu-id="0d157-118">In diesem Beispiel wird die schrittweise Ausführung von ausgeführt, und anschließend wird ein Skript ausgeführt, das die Zahlen 1, 2 und 3 anzeigt.</span><span class="sxs-lookup"><span data-stu-id="0d157-118">This example turns on stepping, and then runs a script that displays the numbers 1, 2, and 3.</span></span>

```powershell
Set-PSDebug -Step; foreach ($i in 1..3) {$i}
```

```Output
Continue with this operation?
   1+ Set-PSDebug -Step; foreach ($i in  >>>> 1..3) {$i}
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): A
DEBUG:    1+ Set-PSDebug -Step; foreach ($i in  >>>> 1..3) {$i}
1
2
3
```

### <span data-ttu-id="0d157-119">Beispiel 3: Verwenden des Strict-Modus</span><span class="sxs-lookup"><span data-stu-id="0d157-119">Example 3: Use strict mode</span></span>

<span data-ttu-id="0d157-120">In diesem Beispiel wird PowerShell in den Strict-Modus versetzt und versucht, auf eine Variable zuzugreifen, die über keinen zugewiesenen Wert verfügt.</span><span class="sxs-lookup"><span data-stu-id="0d157-120">This example puts PowerShell in strict mode and attempts to access a variable that doesn't have an assigned value.</span></span>

```powershell
Set-PSDebug -Strict; $NewVar
```

```Output
The variable '$NewVar' cannot be retrieved because it has not been set.
At line:1 char:22
+ Set-PSDebug -Strict; $NewVar
```

### <span data-ttu-id="0d157-121">Beispiel 4: Deaktivieren der Debuggingfunktionen</span><span class="sxs-lookup"><span data-stu-id="0d157-121">Example 4: Turn off debug features</span></span>

<span data-ttu-id="0d157-122">In diesem Beispiel werden alle Debuggingfunktionen deaktiviert, und anschließend wird ein Skript ausgeführt, das die Zahlen 1, 2 und 3 anzeigt.</span><span class="sxs-lookup"><span data-stu-id="0d157-122">This example turns off all debugging features, and then runs a script that displays the numbers 1, 2, and 3.</span></span>

```powershell
Set-PSDebug -Off; foreach ($i in 1..3) {$i}
```

```Output
1
2
3
```

## <span data-ttu-id="0d157-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0d157-123">PARAMETERS</span></span>

### <span data-ttu-id="0d157-124">-Aus</span><span class="sxs-lookup"><span data-stu-id="0d157-124">-Off</span></span>

<span data-ttu-id="0d157-125">Deaktiviert alle Skriptdebuggingfeatures.</span><span class="sxs-lookup"><span data-stu-id="0d157-125">Turns off all script debugging features.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: off
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0d157-126">-Schritt</span><span class="sxs-lookup"><span data-stu-id="0d157-126">-Step</span></span>

<span data-ttu-id="0d157-127">Aktiviert die Schrittausführung für Skripts.</span><span class="sxs-lookup"><span data-stu-id="0d157-127">Turns on script stepping.</span></span> <span data-ttu-id="0d157-128">Vor der Ausführung der einzelnen Zeilen werden Sie von PowerShell aufgefordert, den Status des Skripts zu überprüfen, fortzusetzen oder eine neue interpreterstufe einzugeben.</span><span class="sxs-lookup"><span data-stu-id="0d157-128">Before each line runs, PowerShell prompts you to stop, continue, or enter a new interpreter level to inspect the state of the script.</span></span>

<span data-ttu-id="0d157-129">Durch die Angabe des **Step** -Parameters wird automatisch die Ablauf Verfolgungs Ebene festgelegt `1`</span><span class="sxs-lookup"><span data-stu-id="0d157-129">Specifying the **Step** parameter automatically sets a trace level of `1`.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: on
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0d157-130">-Strict</span><span class="sxs-lookup"><span data-stu-id="0d157-130">-Strict</span></span>

<span data-ttu-id="0d157-131">Gibt an, dass Variablen ein Wert zugewiesen werden muss, bevor in einem Skript darauf verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="0d157-131">Specifies that variables must be assigned a value before being referenced in a script.</span></span> <span data-ttu-id="0d157-132">Wenn auf eine Variable verwiesen wird, bevor ein Wert zugewiesen wird, gibt PowerShell einen Ausnahme Fehler zurück.</span><span class="sxs-lookup"><span data-stu-id="0d157-132">If a variable is referenced before a value is assigned, PowerShell returns an exception error.</span></span> <span data-ttu-id="0d157-133">Dieser entspricht `Set-StrictMode -Version 1`.</span><span class="sxs-lookup"><span data-stu-id="0d157-133">This is equivalent to `Set-StrictMode -Version 1`.</span></span> <span data-ttu-id="0d157-134">Weitere Informationen finden Sie unter [Set-strictmode](Set-StrictMode.md).</span><span class="sxs-lookup"><span data-stu-id="0d157-134">For more information, see [Set-StrictMode](Set-StrictMode.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: on
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0d157-135">-Trace</span><span class="sxs-lookup"><span data-stu-id="0d157-135">-Trace</span></span>

<span data-ttu-id="0d157-136">Gibt die Ablauf Verfolgungs Ebene für jede Zeile in einem Skript an.</span><span class="sxs-lookup"><span data-stu-id="0d157-136">Specifies the trace level for each line in a script.</span></span> <span data-ttu-id="0d157-137">Jede Zeile wird nachverfolgt, während Sie ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0d157-137">Each line is traced as it's run.</span></span>

<span data-ttu-id="0d157-138">Die zulässigen Werte für diesen Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="0d157-138">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="0d157-139">0: Skript Ablauf Verfolgung deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="0d157-139">0: Turn script tracing off.</span></span>
- <span data-ttu-id="0d157-140">1: Ablauf Verfolgung für Skript Zeilen während der Durchführung.</span><span class="sxs-lookup"><span data-stu-id="0d157-140">1: Trace script lines as they run.</span></span>
- <span data-ttu-id="0d157-141">2: Ablauf Verfolgung von Skript Zeilen, Variablen Zuweisungen, Funktionsaufrufen und Skripts.</span><span class="sxs-lookup"><span data-stu-id="0d157-141">2: Trace script lines, variable assignments, function calls, and scripts.</span></span>

```yaml
Type: System.Int32
Parameter Sets: on
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0d157-142">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0d157-142">CommonParameters</span></span>

<span data-ttu-id="0d157-143">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0d157-143">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0d157-144">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0d157-144">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0d157-145">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="0d157-145">INPUTS</span></span>

### <span data-ttu-id="0d157-146">Keine</span><span class="sxs-lookup"><span data-stu-id="0d157-146">None</span></span>

<span data-ttu-id="0d157-147">Sie können keine Eingabe für dieses Cmdlet ausführen.</span><span class="sxs-lookup"><span data-stu-id="0d157-147">You can't pipeline input to this cmdlet.</span></span>

## <span data-ttu-id="0d157-148">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="0d157-148">OUTPUTS</span></span>

### <span data-ttu-id="0d157-149">Keine</span><span class="sxs-lookup"><span data-stu-id="0d157-149">None</span></span>

<span data-ttu-id="0d157-150">Dieses Cmdlet gibt keine Ausgabe zurück.</span><span class="sxs-lookup"><span data-stu-id="0d157-150">This cmdlet doesn't return any output.</span></span>

## <span data-ttu-id="0d157-151">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="0d157-151">NOTES</span></span>

## <span data-ttu-id="0d157-152">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="0d157-152">RELATED LINKS</span></span>

[<span data-ttu-id="0d157-153">about_Debuggers</span><span class="sxs-lookup"><span data-stu-id="0d157-153">about_Debuggers</span></span>](./About/about_Debuggers.md)

[<span data-ttu-id="0d157-154">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="0d157-154">Debug-Process</span></span>](../Microsoft.PowerShell.Management/Debug-Process.md)

[<span data-ttu-id="0d157-155">Set-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="0d157-155">Set-PSBreakpoint</span></span>](../Microsoft.PowerShell.Utility/Set-PSBreakpoint.md)

[<span data-ttu-id="0d157-156">Set-StrictMode</span><span class="sxs-lookup"><span data-stu-id="0d157-156">Set-StrictMode</span></span>](Set-StrictMode.md)

[<span data-ttu-id="0d157-157">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="0d157-157">Write-Debug</span></span>](../Microsoft.PowerShell.Utility/Write-Debug.md)

