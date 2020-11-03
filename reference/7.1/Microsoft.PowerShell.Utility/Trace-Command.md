---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/09/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/trace-command?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Trace-Command
ms.openlocfilehash: c26e1c46db8f7c6eeeb5c970bc17921622cd023e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211748"
---
# <span data-ttu-id="85536-103">Trace-Command</span><span class="sxs-lookup"><span data-stu-id="85536-103">Trace-Command</span></span>

## <span data-ttu-id="85536-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="85536-104">SYNOPSIS</span></span>
<span data-ttu-id="85536-105">Konfiguriert und startet eine Ablaufverfolgung des angegebenen Ausdrucks oder Befehls.</span><span class="sxs-lookup"><span data-stu-id="85536-105">Configures and starts a trace of the specified expression or command.</span></span>

## <span data-ttu-id="85536-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="85536-106">SYNTAX</span></span>

### <span data-ttu-id="85536-107">expressionset (Standard)</span><span class="sxs-lookup"><span data-stu-id="85536-107">expressionSet (Default)</span></span>

```
Trace-Command [-InputObject <PSObject>] [-Name] <String[]> [[-Option] <PSTraceSourceOptions>]
 [-Expression] <ScriptBlock> [-ListenerOption <TraceOptions>] [-FilePath <String>] [-Force] [-Debugger]
 [-PSHost] [<CommonParameters>]
```

### <span data-ttu-id="85536-108">commandSet</span><span class="sxs-lookup"><span data-stu-id="85536-108">commandSet</span></span>

```
Trace-Command [-InputObject <PSObject>] [-Name] <String[]> [[-Option] <PSTraceSourceOptions>]
 [-Command] <String> [-ArgumentList <Object[]>] [-ListenerOption <TraceOptions>] [-FilePath <String>] [-Force]
 [-Debugger] [-PSHost] [<CommonParameters>]
```

## <span data-ttu-id="85536-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="85536-109">DESCRIPTION</span></span>
<span data-ttu-id="85536-110">Das `Trace-Command` -Cmdlet konfiguriert und startet eine Ablauf Verfolgung des angegebenen Ausdrucks oder Befehls.</span><span class="sxs-lookup"><span data-stu-id="85536-110">The `Trace-Command` cmdlet configures and starts a trace of the specified expression or command.</span></span>
<span data-ttu-id="85536-111">Es funktioniert wie Set-TraceSource, mit dem Unterschied, dass es nur für den angegebenen Befehl gilt.</span><span class="sxs-lookup"><span data-stu-id="85536-111">It works like Set-TraceSource, except that it applies only to the specified command.</span></span>

## <span data-ttu-id="85536-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="85536-112">EXAMPLES</span></span>

### <span data-ttu-id="85536-113">Beispiel 1: Verarbeitung von Ablauf Verfolgungs Metadaten, Parameter Bindung und ein Ausdruck</span><span class="sxs-lookup"><span data-stu-id="85536-113">Example 1: Trace metadata processing, parameter binding, and an expression</span></span>

<span data-ttu-id="85536-114">In diesem Beispiel wird eine Ablauf Verfolgung der Metadatenverarbeitung, der Parameter Bindung und der Cmdlet-Erstellung und-Zerstörung des `Get-Process Notepad` Ausdrucks gestartet.</span><span class="sxs-lookup"><span data-stu-id="85536-114">This example starts a trace of metadata processing, parameter binding, and cmdlet creation and destruction of the `Get-Process Notepad` expression.</span></span>

```powershell
Trace-Command -Name metadata,parameterbinding,cmdlet -Expression {Get-Process Notepad} -PSHost
```

<span data-ttu-id="85536-115">Er verwendet den **Name** -Parameter zum Angeben der Ablauf Verfolgungs Quellen, den **Expression** -Parameter zur Angabe des Befehls und den **pshost** -Parameter, um die Ausgabe an die Konsole zu senden.</span><span class="sxs-lookup"><span data-stu-id="85536-115">It uses the **Name** parameter to specify the trace sources, the **Expression** parameter to specify the command, and the **PSHost** parameter to send the output to the console.</span></span> <span data-ttu-id="85536-116">Da keine Ablauf Verfolgungs Optionen oder Listeneroptionen angegeben werden, verwendet der Befehl die Standardwerte:</span><span class="sxs-lookup"><span data-stu-id="85536-116">Because it does not specify any tracing options or listener options, the command uses the defaults:</span></span>

- <span data-ttu-id="85536-117">Alle für die Ablauf Verfolgungs Optionen</span><span class="sxs-lookup"><span data-stu-id="85536-117">All for the tracing options</span></span>
- <span data-ttu-id="85536-118">Keine für die Listeneroptionen</span><span class="sxs-lookup"><span data-stu-id="85536-118">None for the listener options</span></span>

### <span data-ttu-id="85536-119">Beispiel 2: Verfolgen der Aktionen von ParameterBinding-Vorgängen</span><span class="sxs-lookup"><span data-stu-id="85536-119">Example 2: Trace the actions of ParameterBinding operations</span></span>

<span data-ttu-id="85536-120">In diesem Beispiel werden die Aktionen der **ParameterBinding** -Vorgänge von PowerShell nachverfolgt, während ein-Ausdruck verarbeitet wird `Get-Alias` , der Eingaben aus der Pipeline annimmt.</span><span class="sxs-lookup"><span data-stu-id="85536-120">This example traces the actions of the **ParameterBinding** operations of PowerShell while it processes a `Get-Alias` expression that takes input from the pipeline.</span></span>

```powershell
$A = "i*"
Trace-Command ParameterBinding {Get-Alias $Input} -PSHost -InputObject $A
```

<span data-ttu-id="85536-121">In `Trace-Command` übergibt der **Inputobject** -Parameter ein Objekt an den Ausdruck, der während der Ablauf Verfolgung verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="85536-121">In `Trace-Command`, the **InputObject** parameter passes an object to the expression that is being processed during the trace.</span></span>

<span data-ttu-id="85536-122">Der erste Befehl speichert die Zeichenfolge `i*` in der `$A` Variablen.</span><span class="sxs-lookup"><span data-stu-id="85536-122">The first command stores the string `i*` in the `$A` variable.</span></span> <span data-ttu-id="85536-123">Der zweite Befehl verwendet das `Trace-Command` Cmdlet mit der ParameterBinding-Ablauf Verfolgungs Quelle.</span><span class="sxs-lookup"><span data-stu-id="85536-123">The second command uses the `Trace-Command` cmdlet with the ParameterBinding trace source.</span></span> <span data-ttu-id="85536-124">Der **pshost** -Parameter sendet die Ausgabe an die Konsole.</span><span class="sxs-lookup"><span data-stu-id="85536-124">The **PSHost** parameter sends the output to the console.</span></span>

<span data-ttu-id="85536-125">Der Ausdruck, der verarbeitet wird `Get-Alias $Input` , ist, wobei die `$Input` Variable dem **Inputobject** -Parameter zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="85536-125">The expression being processed is `Get-Alias $Input`, where the `$Input` variable is associated with the **InputObject** parameter.</span></span> <span data-ttu-id="85536-126">Der **Inputobject** -Parameter übergibt die Variable `$A` an den Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="85536-126">The **InputObject** parameter passes the variable `$A` to the expression.</span></span> <span data-ttu-id="85536-127">Tatsächlich ist der Befehl, der während der Ablauf Verfolgung verarbeitet wird, `Get-Alias -InputObject $A" or "$A | Get-Alias` .</span><span class="sxs-lookup"><span data-stu-id="85536-127">In effect, the command being processed during the trace is `Get-Alias -InputObject $A" or "$A | Get-Alias`.</span></span>

## <span data-ttu-id="85536-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="85536-128">PARAMETERS</span></span>

### <span data-ttu-id="85536-129">-Argumentlist</span><span class="sxs-lookup"><span data-stu-id="85536-129">-ArgumentList</span></span>

<span data-ttu-id="85536-130">Gibt die Parameter und Parameterwerte für den verfolgten Befehl an.</span><span class="sxs-lookup"><span data-stu-id="85536-130">Specifies the parameters and parameter values for the command being traced.</span></span> <span data-ttu-id="85536-131">Der Alias für **ArgumentList** ist **Args** .</span><span class="sxs-lookup"><span data-stu-id="85536-131">The alias for **ArgumentList** is **Args** .</span></span> <span data-ttu-id="85536-132">Diese Funktion ist besonders nützlich für das Debuggen dynamischer Parameter.</span><span class="sxs-lookup"><span data-stu-id="85536-132">This feature is especially useful for debugging dynamic parameters.</span></span>

<span data-ttu-id="85536-133">Weitere Informationen zum Verhalten von **argumentlist** finden Sie unter [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md#splatting-with-arrays).</span><span class="sxs-lookup"><span data-stu-id="85536-133">For more information about the behavior of **ArgumentList** , see [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md#splatting-with-arrays).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: commandSet
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="85536-134">-Command</span><span class="sxs-lookup"><span data-stu-id="85536-134">-Command</span></span>

<span data-ttu-id="85536-135">Gibt einen Befehl an, der während der Ablaufverfolgung verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="85536-135">Specifies a command that is being processed during the trace.</span></span>

```yaml
Type: System.String
Parameter Sets: commandSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="85536-136">-Debugger</span><span class="sxs-lookup"><span data-stu-id="85536-136">-Debugger</span></span>

<span data-ttu-id="85536-137">Gibt an, dass das Cmdlet die Ablauf Verfolgungs Ausgabe an den Debugger sendet.</span><span class="sxs-lookup"><span data-stu-id="85536-137">Indicates that the cmdlet sends the trace output to the debugger.</span></span> <span data-ttu-id="85536-138">Sie können die Ausgabe in jeden Benutzermodus- oder Kernelmodus-Debugger oder in Visual Studio anzeigen.</span><span class="sxs-lookup"><span data-stu-id="85536-138">You can view the output in any user-mode or kernel mode debugger or in Visual Studio.</span></span> <span data-ttu-id="85536-139">Dieser Parameter wählt auch den Standard-Ablaufverfolgungslistener aus.</span><span class="sxs-lookup"><span data-stu-id="85536-139">This parameter also selects the default trace listener.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="85536-140">-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="85536-140">-Expression</span></span>

<span data-ttu-id="85536-141">Gibt den Ausdruck an, der während der Ablaufverfolgung verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="85536-141">Specifies the expression that is being processed during the trace.</span></span> <span data-ttu-id="85536-142">Schließen Sie den Ausdruck in geschweifte Klammern ( `{}` ) ein.</span><span class="sxs-lookup"><span data-stu-id="85536-142">Enclose the expression in braces (`{}`).</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: expressionSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="85536-143">-FilePath</span><span class="sxs-lookup"><span data-stu-id="85536-143">-FilePath</span></span>

<span data-ttu-id="85536-144">Gibt eine Datei an, an die das Cmdlet die Ablauf Verfolgungs Ausgabe sendet.</span><span class="sxs-lookup"><span data-stu-id="85536-144">Specifies a file that the cmdlet sends the trace output to.</span></span> <span data-ttu-id="85536-145">Dieser Parameter wählt auch den Ablaufverfolgungslistener der Datei aus.</span><span class="sxs-lookup"><span data-stu-id="85536-145">This parameter also selects the file trace listener.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSPath, Path

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="85536-146">-Force</span><span class="sxs-lookup"><span data-stu-id="85536-146">-Force</span></span>

<span data-ttu-id="85536-147">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="85536-147">Forces the command to run without asking for user confirmation.</span></span> <span data-ttu-id="85536-148">Wird mit dem **FilePath** -Parameter verwendet.</span><span class="sxs-lookup"><span data-stu-id="85536-148">Used with the **FilePath** parameter.</span></span> <span data-ttu-id="85536-149">Selbst bei Verwendung des **Force** -Parameters kann das Cmdlet keine Sicherheitseinschränkungen außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="85536-149">Even using the **Force** parameter, the cmdlet cannot override security restrictions.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="85536-150">-InputObject</span><span class="sxs-lookup"><span data-stu-id="85536-150">-InputObject</span></span>

<span data-ttu-id="85536-151">Gibt die Eingabe für den Ausdruck an, der während der Ablauf Verfolgung verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="85536-151">Specifies input to the expression that is being processed during the trace.</span></span> <span data-ttu-id="85536-152">Sie können eine Variable eingeben, die die Eingabe darstellt und die vom Ausdruck akzeptiert wird, oder Sie können ein Objekt über die Pipeline übergeben.</span><span class="sxs-lookup"><span data-stu-id="85536-152">You can enter a variable that represents the input that the expression accepts, or pass an object through the pipeline.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="85536-153">-Listeneroption</span><span class="sxs-lookup"><span data-stu-id="85536-153">-ListenerOption</span></span>

<span data-ttu-id="85536-154">Gibt optionale Daten für das Präfix der einzelnen Ablauf Verfolgungs Meldungen in der Ausgabe an.</span><span class="sxs-lookup"><span data-stu-id="85536-154">Specifies optional data to the prefix of each trace message in the output.</span></span> <span data-ttu-id="85536-155">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="85536-155">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="85536-156">Keine</span><span class="sxs-lookup"><span data-stu-id="85536-156">None</span></span>
- <span data-ttu-id="85536-157">LogicalOperationStack</span><span class="sxs-lookup"><span data-stu-id="85536-157">LogicalOperationStack</span></span>
- <span data-ttu-id="85536-158">Datetime</span><span class="sxs-lookup"><span data-stu-id="85536-158">DateTime</span></span>
- <span data-ttu-id="85536-159">Timestamp</span><span class="sxs-lookup"><span data-stu-id="85536-159">Timestamp</span></span>
- <span data-ttu-id="85536-160">ProcessId</span><span class="sxs-lookup"><span data-stu-id="85536-160">ProcessId</span></span>
- <span data-ttu-id="85536-161">ThreadID</span><span class="sxs-lookup"><span data-stu-id="85536-161">ThreadId</span></span>
- <span data-ttu-id="85536-162">Aufruf Liste</span><span class="sxs-lookup"><span data-stu-id="85536-162">Callstack</span></span>

<span data-ttu-id="85536-163">" **None** " ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="85536-163">**None** is the default.</span></span>

<span data-ttu-id="85536-164">Um mehrere Optionen anzugeben, trennen Sie diese durch Kommas, aber ohne Leerzeichen, und schließen Sie sie in Anführungszeichen ein, z. B. "ProcessID,ThreadID".</span><span class="sxs-lookup"><span data-stu-id="85536-164">To specify multiple options, separate them with commas, but with no spaces, and enclose them in quotation marks, such as "ProcessID,ThreadID".</span></span>

```yaml
Type: System.Diagnostics.TraceOptions
Parameter Sets: (All)
Aliases:
Accepted values: None, LogicalOperationStack, DateTime, Timestamp, ProcessId, ThreadId, Callstack

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="85536-165">-Name</span><span class="sxs-lookup"><span data-stu-id="85536-165">-Name</span></span>

<span data-ttu-id="85536-166">Gibt ein Array von PowerShell-Komponenten an, die nachverfolgt werden.</span><span class="sxs-lookup"><span data-stu-id="85536-166">Specifies an array of PowerShell components that are traced.</span></span> <span data-ttu-id="85536-167">Geben Sie den Namen der Ablaufverfolgungsquelle jeder Komponente ein.</span><span class="sxs-lookup"><span data-stu-id="85536-167">Enter the name of the trace source of each component.</span></span> <span data-ttu-id="85536-168">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="85536-168">Wildcards are permitted.</span></span> <span data-ttu-id="85536-169">Geben Sie ein, um die Ablauf Verfolgungs Quellen auf Ihrem Computer zu finden `Get-TraceSource` .</span><span class="sxs-lookup"><span data-stu-id="85536-169">To find the trace sources on your computer, type `Get-TraceSource`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="85536-170">-Option</span><span class="sxs-lookup"><span data-stu-id="85536-170">-Option</span></span>

<span data-ttu-id="85536-171">Bestimmt den Typ der Ereignisse, die verfolgt werden.</span><span class="sxs-lookup"><span data-stu-id="85536-171">Determines the type of events that are traced.</span></span> <span data-ttu-id="85536-172">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="85536-172">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="85536-173">Keine</span><span class="sxs-lookup"><span data-stu-id="85536-173">None</span></span>
- <span data-ttu-id="85536-174">Konstruktor</span><span class="sxs-lookup"><span data-stu-id="85536-174">Constructor</span></span>
- <span data-ttu-id="85536-175">Dispose</span><span class="sxs-lookup"><span data-stu-id="85536-175">Dispose</span></span>
- <span data-ttu-id="85536-176">Finalizer</span><span class="sxs-lookup"><span data-stu-id="85536-176">Finalizer</span></span>
- <span data-ttu-id="85536-177">Methode</span><span class="sxs-lookup"><span data-stu-id="85536-177">Method</span></span>
- <span data-ttu-id="85536-178">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="85536-178">Property</span></span>
- <span data-ttu-id="85536-179">Delegaten</span><span class="sxs-lookup"><span data-stu-id="85536-179">Delegates</span></span>
- <span data-ttu-id="85536-180">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="85536-180">Events</span></span>
- <span data-ttu-id="85536-181">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="85536-181">Exception</span></span>
- <span data-ttu-id="85536-182">Sperre</span><span class="sxs-lookup"><span data-stu-id="85536-182">Lock</span></span>
- <span data-ttu-id="85536-183">Fehler</span><span class="sxs-lookup"><span data-stu-id="85536-183">Error</span></span>
- <span data-ttu-id="85536-184">Errors</span><span class="sxs-lookup"><span data-stu-id="85536-184">Errors</span></span>
- <span data-ttu-id="85536-185">Warnung</span><span class="sxs-lookup"><span data-stu-id="85536-185">Warning</span></span>
- <span data-ttu-id="85536-186">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="85536-186">Verbose</span></span>
- <span data-ttu-id="85536-187">WriteLine</span><span class="sxs-lookup"><span data-stu-id="85536-187">WriteLine</span></span>
- <span data-ttu-id="85536-188">Daten</span><span class="sxs-lookup"><span data-stu-id="85536-188">Data</span></span>
- <span data-ttu-id="85536-189">`Scope`</span><span class="sxs-lookup"><span data-stu-id="85536-189">Scope</span></span>
- <span data-ttu-id="85536-190">ExecutionFlow</span><span class="sxs-lookup"><span data-stu-id="85536-190">ExecutionFlow</span></span>
- <span data-ttu-id="85536-191">Assert</span><span class="sxs-lookup"><span data-stu-id="85536-191">Assert</span></span>
- <span data-ttu-id="85536-192">Alle</span><span class="sxs-lookup"><span data-stu-id="85536-192">All</span></span>

<span data-ttu-id="85536-193">„All“ ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="85536-193">All is the default.</span></span>

<span data-ttu-id="85536-194">Die folgenden Werte sind Kombinationen von anderen Werten:</span><span class="sxs-lookup"><span data-stu-id="85536-194">The following values are combinations of other values:</span></span>

- <span data-ttu-id="85536-195">Executionflow: (Konstruktor, verwerfen, Finalizer, Methode, Delegaten, Ereignisse und Bereich)</span><span class="sxs-lookup"><span data-stu-id="85536-195">ExecutionFlow: (Constructor, Dispose, Finalizer, Method, Delegates, Events, and Scope)</span></span>
- <span data-ttu-id="85536-196">Daten: (Konstruktor, verwerfen, Finalizer, Property, verbose und Write teline)</span><span class="sxs-lookup"><span data-stu-id="85536-196">Data: (Constructor, Dispose, Finalizer, Property, Verbose, and WriteLine)</span></span>
- <span data-ttu-id="85536-197">Fehler: (Fehler und Ausnahme).</span><span class="sxs-lookup"><span data-stu-id="85536-197">Errors: (Error and Exception).</span></span>

<span data-ttu-id="85536-198">Um mehrere Optionen anzugeben, trennen Sie diese durch Kommas, aber ohne Leerzeichen, und schließen Sie sie in Anführungszeichen ein, z. B. "Constructor,Dispose".</span><span class="sxs-lookup"><span data-stu-id="85536-198">To specify multiple options, separate them with commas, but with no spaces, and enclose them in quotation marks, such as "Constructor,Dispose".</span></span>

```yaml
Type: System.Management.Automation.PSTraceSourceOptions
Parameter Sets: (All)
Aliases:
Accepted values: None, Constructor, Dispose, Finalizer, Method, Property, Delegates, Events, Exception, Lock, Error, Errors, Warning, Verbose, WriteLine, Data, Scope, ExecutionFlow, Assert, All

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="85536-199">-Pshost</span><span class="sxs-lookup"><span data-stu-id="85536-199">-PSHost</span></span>

<span data-ttu-id="85536-200">Gibt an, dass das Cmdlet die Ablauf Verfolgungs Ausgabe an den PowerShell-Host sendet.</span><span class="sxs-lookup"><span data-stu-id="85536-200">Indicates that the cmdlet sends the trace output to the PowerShell host.</span></span> <span data-ttu-id="85536-201">Dieser Parameter wählt auch den PSHost-Ablaufverfolgungslistener aus.</span><span class="sxs-lookup"><span data-stu-id="85536-201">This parameter also selects the PSHost trace listener.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="85536-202">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="85536-202">CommonParameters</span></span>

<span data-ttu-id="85536-203">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="85536-203">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="85536-204">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="85536-204">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="85536-205">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="85536-205">INPUTS</span></span>

### <span data-ttu-id="85536-206">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="85536-206">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="85536-207">Sie können Objekte, die Eingaben darstellen, an den Ausdruck übergeben `Trace-Command` .</span><span class="sxs-lookup"><span data-stu-id="85536-207">You can pipe objects that represent input to the expression to `Trace-Command`.</span></span>

## <span data-ttu-id="85536-208">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="85536-208">OUTPUTS</span></span>

### <span data-ttu-id="85536-209">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="85536-209">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="85536-210">Gibt die Befehlsablaufverfolgung im Debug-Stream zurück.</span><span class="sxs-lookup"><span data-stu-id="85536-210">Returns the command trace in the debug stream.</span></span>

## <span data-ttu-id="85536-211">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="85536-211">NOTES</span></span>

- <span data-ttu-id="85536-212">Die Ablaufverfolgung ist eine Methode, die Entwickler zum Debuggen und Optimieren von Programmen verwenden.</span><span class="sxs-lookup"><span data-stu-id="85536-212">Tracing is a method that developers use to debug and refine programs.</span></span> <span data-ttu-id="85536-213">Bei der Ablaufverfolgung erzeugt das Programm ausführliche Meldungen zu den einzelnen Schritten in der internen Verarbeitung.</span><span class="sxs-lookup"><span data-stu-id="85536-213">When tracing, the program generates detailed messages about each step in its internal processing.</span></span>

- <span data-ttu-id="85536-214">Die PowerShell-Ablaufverfolgungs-Cmdlets sind für die Unterstützung von PowerShell-Entwicklern konzipiert, aber Sie stehen allen Benutzern zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="85536-214">The PowerShell tracing cmdlets are designed to help PowerShell developers, but they are available to all users.</span></span> <span data-ttu-id="85536-215">Damit können Sie fast jeden Aspekt der Shell-Funktionalität überwachen.</span><span class="sxs-lookup"><span data-stu-id="85536-215">They let you monitor nearly every aspect of the functionality of the shell.</span></span>

- <span data-ttu-id="85536-216">Zum Ermitteln der PowerShell-Komponenten, die für die Ablauf Verfolgung aktiviert sind, geben Sie ein `Get-Help Get-TraceSource` .</span><span class="sxs-lookup"><span data-stu-id="85536-216">To find the PowerShell components that are enabled for tracing, type `Get-Help Get-TraceSource`.</span></span>

  <span data-ttu-id="85536-217">Eine Ablauf Verfolgungs Quelle ist der Teil jeder PowerShell-Komponente, die die Ablauf Verfolgung verwaltet und Ablauf Verfolgungs Meldungen für die Komponente generiert.</span><span class="sxs-lookup"><span data-stu-id="85536-217">A trace source is the part of each PowerShell component that manages tracing and generates trace messages for the component.</span></span> <span data-ttu-id="85536-218">Um eine Komponente zu verfolgen, identifizieren Sie die Ablaufverfolgungsquelle.</span><span class="sxs-lookup"><span data-stu-id="85536-218">To trace a component, you identify its trace source.</span></span>

  <span data-ttu-id="85536-219">Ein Ablaufverfolgungslistener empfängt die Ausgabe der Ablauf Verfolgung und zeigt Sie dem Benutzer an.</span><span class="sxs-lookup"><span data-stu-id="85536-219">A trace listener receives the output of the trace and displays it to the user.</span></span> <span data-ttu-id="85536-220">Sie können festlegen, dass die Ablauf Verfolgungs Daten an einen Benutzermodus-oder Kernel Modus-Debugger, an den Host oder die Konsole, an eine Datei oder an einen benutzerdefinierten Listener gesendet werden, der von der **System. Diagnostics. TraceListener** -Klasse abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="85536-220">You can elect to send the trace data to a user-mode or kernel-mode debugger, to the host or console, to a file, or to a custom listener derived from the **System.Diagnostics.TraceListener** class.</span></span>

- <span data-ttu-id="85536-221">Wenn Sie den CommandSet-Parametersatz verwenden, verarbeitet PowerShell den Befehl genauso wie in einer Pipeline.</span><span class="sxs-lookup"><span data-stu-id="85536-221">When you use the commandSet parameter set, PowerShell processes the command just as it would be processed in a pipeline.</span></span> <span data-ttu-id="85536-222">Beispielsweise wird die Befehlsermittlung nicht für jedes eingehende Objekt wiederholt.</span><span class="sxs-lookup"><span data-stu-id="85536-222">For example, command discovery is not repeated for each incoming object.</span></span>

- <span data-ttu-id="85536-223">Die Namen der Parameter " **Name** ", " **Ausdruck** ", " **Option** " und " **Command** " sind optional.</span><span class="sxs-lookup"><span data-stu-id="85536-223">The names of the **Name** , **Expression** , **Option** , and **Command** parameters are optional.</span></span> <span data-ttu-id="85536-224">Wenn Sie die Parameternamen weglassen, müssen die unbenannten Parameterwerte in dieser Reihenfolge angezeigt werden: **Name** , **Ausdruck** , **Option** oder **Name** , **Befehl** , **Option** .</span><span class="sxs-lookup"><span data-stu-id="85536-224">If you omit the parameter names, the unnamed parameter values must appear in this order: **Name** , **Expression** , **Option** or **Name** , **Command** , **Option** .</span></span> <span data-ttu-id="85536-225">Wenn Sie die Parameternamen angeben, können die Parameter in beliebiger Reihenfolge angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="85536-225">If you include the parameter names, the parameters can appear in any order.</span></span>

## <span data-ttu-id="85536-226">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="85536-226">RELATED LINKS</span></span>

[<span data-ttu-id="85536-227">Get-TraceSource</span><span class="sxs-lookup"><span data-stu-id="85536-227">Get-TraceSource</span></span>](Get-TraceSource.md)

[<span data-ttu-id="85536-228">Measure-Command</span><span class="sxs-lookup"><span data-stu-id="85536-228">Measure-Command</span></span>](Measure-Command.md)

[<span data-ttu-id="85536-229">Set-TraceSource</span><span class="sxs-lookup"><span data-stu-id="85536-229">Set-TraceSource</span></span>](Set-TraceSource.md)

