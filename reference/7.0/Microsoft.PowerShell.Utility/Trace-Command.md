---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/09/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/trace-command?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Trace-Command
ms.openlocfilehash: f3f9e47ac6d969dc08518bf97bb87699fb04ade8
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210508"
---
# <span data-ttu-id="21bc2-103">Trace-Command</span><span class="sxs-lookup"><span data-stu-id="21bc2-103">Trace-Command</span></span>

## <span data-ttu-id="21bc2-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="21bc2-104">SYNOPSIS</span></span>
<span data-ttu-id="21bc2-105">Konfiguriert und startet eine Ablaufverfolgung des angegebenen Ausdrucks oder Befehls.</span><span class="sxs-lookup"><span data-stu-id="21bc2-105">Configures and starts a trace of the specified expression or command.</span></span>

## <span data-ttu-id="21bc2-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="21bc2-106">SYNTAX</span></span>

### <span data-ttu-id="21bc2-107">expressionset (Standard)</span><span class="sxs-lookup"><span data-stu-id="21bc2-107">expressionSet (Default)</span></span>

```
Trace-Command [-InputObject <PSObject>] [-Name] <String[]> [[-Option] <PSTraceSourceOptions>]
 [-Expression] <ScriptBlock> [-ListenerOption <TraceOptions>] [-FilePath <String>] [-Force] [-Debugger]
 [-PSHost] [<CommonParameters>]
```

### <span data-ttu-id="21bc2-108">commandSet</span><span class="sxs-lookup"><span data-stu-id="21bc2-108">commandSet</span></span>

```
Trace-Command [-InputObject <PSObject>] [-Name] <String[]> [[-Option] <PSTraceSourceOptions>]
 [-Command] <String> [-ArgumentList <Object[]>] [-ListenerOption <TraceOptions>] [-FilePath <String>] [-Force]
 [-Debugger] [-PSHost] [<CommonParameters>]
```

## <span data-ttu-id="21bc2-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="21bc2-109">DESCRIPTION</span></span>
<span data-ttu-id="21bc2-110">Das `Trace-Command` -Cmdlet konfiguriert und startet eine Ablauf Verfolgung des angegebenen Ausdrucks oder Befehls.</span><span class="sxs-lookup"><span data-stu-id="21bc2-110">The `Trace-Command` cmdlet configures and starts a trace of the specified expression or command.</span></span>
<span data-ttu-id="21bc2-111">Es funktioniert wie Set-TraceSource, mit dem Unterschied, dass es nur für den angegebenen Befehl gilt.</span><span class="sxs-lookup"><span data-stu-id="21bc2-111">It works like Set-TraceSource, except that it applies only to the specified command.</span></span>

## <span data-ttu-id="21bc2-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="21bc2-112">EXAMPLES</span></span>

### <span data-ttu-id="21bc2-113">Beispiel 1: Verarbeitung von Ablauf Verfolgungs Metadaten, Parameter Bindung und ein Ausdruck</span><span class="sxs-lookup"><span data-stu-id="21bc2-113">Example 1: Trace metadata processing, parameter binding, and an expression</span></span>

<span data-ttu-id="21bc2-114">In diesem Beispiel wird eine Ablauf Verfolgung der Metadatenverarbeitung, der Parameter Bindung und der Cmdlet-Erstellung und-Zerstörung des `Get-Process Notepad` Ausdrucks gestartet.</span><span class="sxs-lookup"><span data-stu-id="21bc2-114">This example starts a trace of metadata processing, parameter binding, and cmdlet creation and destruction of the `Get-Process Notepad` expression.</span></span>

```powershell
Trace-Command -Name metadata,parameterbinding,cmdlet -Expression {Get-Process Notepad} -PSHost
```

<span data-ttu-id="21bc2-115">Er verwendet den **Name** -Parameter zum Angeben der Ablauf Verfolgungs Quellen, den **Expression** -Parameter zur Angabe des Befehls und den **pshost** -Parameter, um die Ausgabe an die Konsole zu senden.</span><span class="sxs-lookup"><span data-stu-id="21bc2-115">It uses the **Name** parameter to specify the trace sources, the **Expression** parameter to specify the command, and the **PSHost** parameter to send the output to the console.</span></span> <span data-ttu-id="21bc2-116">Da keine Ablauf Verfolgungs Optionen oder Listeneroptionen angegeben werden, verwendet der Befehl die Standardwerte:</span><span class="sxs-lookup"><span data-stu-id="21bc2-116">Because it does not specify any tracing options or listener options, the command uses the defaults:</span></span>

- <span data-ttu-id="21bc2-117">Alle für die Ablauf Verfolgungs Optionen</span><span class="sxs-lookup"><span data-stu-id="21bc2-117">All for the tracing options</span></span>
- <span data-ttu-id="21bc2-118">Keine für die Listeneroptionen</span><span class="sxs-lookup"><span data-stu-id="21bc2-118">None for the listener options</span></span>

### <span data-ttu-id="21bc2-119">Beispiel 2: Verfolgen der Aktionen von ParameterBinding-Vorgängen</span><span class="sxs-lookup"><span data-stu-id="21bc2-119">Example 2: Trace the actions of ParameterBinding operations</span></span>

<span data-ttu-id="21bc2-120">In diesem Beispiel werden die Aktionen der **ParameterBinding** -Vorgänge von PowerShell nachverfolgt, während ein-Ausdruck verarbeitet wird `Get-Alias` , der Eingaben aus der Pipeline annimmt.</span><span class="sxs-lookup"><span data-stu-id="21bc2-120">This example traces the actions of the **ParameterBinding** operations of PowerShell while it processes a `Get-Alias` expression that takes input from the pipeline.</span></span>

```powershell
$A = "i*"
Trace-Command ParameterBinding {Get-Alias $Input} -PSHost -InputObject $A
```

<span data-ttu-id="21bc2-121">In `Trace-Command` übergibt der **Inputobject** -Parameter ein Objekt an den Ausdruck, der während der Ablauf Verfolgung verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="21bc2-121">In `Trace-Command`, the **InputObject** parameter passes an object to the expression that is being processed during the trace.</span></span>

<span data-ttu-id="21bc2-122">Der erste Befehl speichert die Zeichenfolge `i*` in der `$A` Variablen.</span><span class="sxs-lookup"><span data-stu-id="21bc2-122">The first command stores the string `i*` in the `$A` variable.</span></span> <span data-ttu-id="21bc2-123">Der zweite Befehl verwendet das `Trace-Command` Cmdlet mit der ParameterBinding-Ablauf Verfolgungs Quelle.</span><span class="sxs-lookup"><span data-stu-id="21bc2-123">The second command uses the `Trace-Command` cmdlet with the ParameterBinding trace source.</span></span> <span data-ttu-id="21bc2-124">Der **pshost** -Parameter sendet die Ausgabe an die Konsole.</span><span class="sxs-lookup"><span data-stu-id="21bc2-124">The **PSHost** parameter sends the output to the console.</span></span>

<span data-ttu-id="21bc2-125">Der Ausdruck, der verarbeitet wird `Get-Alias $Input` , ist, wobei die `$Input` Variable dem **Inputobject** -Parameter zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="21bc2-125">The expression being processed is `Get-Alias $Input`, where the `$Input` variable is associated with the **InputObject** parameter.</span></span> <span data-ttu-id="21bc2-126">Der **Inputobject** -Parameter übergibt die Variable `$A` an den Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="21bc2-126">The **InputObject** parameter passes the variable `$A` to the expression.</span></span> <span data-ttu-id="21bc2-127">Tatsächlich ist der Befehl, der während der Ablauf Verfolgung verarbeitet wird, `Get-Alias -InputObject $A" or "$A | Get-Alias` .</span><span class="sxs-lookup"><span data-stu-id="21bc2-127">In effect, the command being processed during the trace is `Get-Alias -InputObject $A" or "$A | Get-Alias`.</span></span>

## <span data-ttu-id="21bc2-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="21bc2-128">PARAMETERS</span></span>

### <span data-ttu-id="21bc2-129">-Argumentlist</span><span class="sxs-lookup"><span data-stu-id="21bc2-129">-ArgumentList</span></span>

<span data-ttu-id="21bc2-130">Gibt die Parameter und Parameterwerte für den verfolgten Befehl an.</span><span class="sxs-lookup"><span data-stu-id="21bc2-130">Specifies the parameters and parameter values for the command being traced.</span></span> <span data-ttu-id="21bc2-131">Der Alias für **ArgumentList** ist **Args** .</span><span class="sxs-lookup"><span data-stu-id="21bc2-131">The alias for **ArgumentList** is **Args** .</span></span> <span data-ttu-id="21bc2-132">Diese Funktion ist besonders nützlich für das Debuggen dynamischer Parameter.</span><span class="sxs-lookup"><span data-stu-id="21bc2-132">This feature is especially useful for debugging dynamic parameters.</span></span>

<span data-ttu-id="21bc2-133">Weitere Informationen zum Verhalten von **argumentlist** finden Sie unter [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md#splatting-with-arrays).</span><span class="sxs-lookup"><span data-stu-id="21bc2-133">For more information about the behavior of **ArgumentList** , see [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md#splatting-with-arrays).</span></span>

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

### <span data-ttu-id="21bc2-134">-Command</span><span class="sxs-lookup"><span data-stu-id="21bc2-134">-Command</span></span>

<span data-ttu-id="21bc2-135">Gibt einen Befehl an, der während der Ablaufverfolgung verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="21bc2-135">Specifies a command that is being processed during the trace.</span></span>

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

### <span data-ttu-id="21bc2-136">-Debugger</span><span class="sxs-lookup"><span data-stu-id="21bc2-136">-Debugger</span></span>

<span data-ttu-id="21bc2-137">Gibt an, dass das Cmdlet die Ablauf Verfolgungs Ausgabe an den Debugger sendet.</span><span class="sxs-lookup"><span data-stu-id="21bc2-137">Indicates that the cmdlet sends the trace output to the debugger.</span></span> <span data-ttu-id="21bc2-138">Sie können die Ausgabe in jeden Benutzermodus- oder Kernelmodus-Debugger oder in Visual Studio anzeigen.</span><span class="sxs-lookup"><span data-stu-id="21bc2-138">You can view the output in any user-mode or kernel mode debugger or in Visual Studio.</span></span> <span data-ttu-id="21bc2-139">Dieser Parameter wählt auch den Standard-Ablaufverfolgungslistener aus.</span><span class="sxs-lookup"><span data-stu-id="21bc2-139">This parameter also selects the default trace listener.</span></span>

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

### <span data-ttu-id="21bc2-140">-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="21bc2-140">-Expression</span></span>

<span data-ttu-id="21bc2-141">Gibt den Ausdruck an, der während der Ablaufverfolgung verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="21bc2-141">Specifies the expression that is being processed during the trace.</span></span> <span data-ttu-id="21bc2-142">Schließen Sie den Ausdruck in geschweifte Klammern ( `{}` ) ein.</span><span class="sxs-lookup"><span data-stu-id="21bc2-142">Enclose the expression in braces (`{}`).</span></span>

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

### <span data-ttu-id="21bc2-143">-FilePath</span><span class="sxs-lookup"><span data-stu-id="21bc2-143">-FilePath</span></span>

<span data-ttu-id="21bc2-144">Gibt eine Datei an, an die das Cmdlet die Ablauf Verfolgungs Ausgabe sendet.</span><span class="sxs-lookup"><span data-stu-id="21bc2-144">Specifies a file that the cmdlet sends the trace output to.</span></span> <span data-ttu-id="21bc2-145">Dieser Parameter wählt auch den Ablaufverfolgungslistener der Datei aus.</span><span class="sxs-lookup"><span data-stu-id="21bc2-145">This parameter also selects the file trace listener.</span></span>

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

### <span data-ttu-id="21bc2-146">-Force</span><span class="sxs-lookup"><span data-stu-id="21bc2-146">-Force</span></span>

<span data-ttu-id="21bc2-147">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="21bc2-147">Forces the command to run without asking for user confirmation.</span></span> <span data-ttu-id="21bc2-148">Wird mit dem **FilePath** -Parameter verwendet.</span><span class="sxs-lookup"><span data-stu-id="21bc2-148">Used with the **FilePath** parameter.</span></span> <span data-ttu-id="21bc2-149">Selbst bei Verwendung des **Force** -Parameters kann das Cmdlet keine Sicherheitseinschränkungen außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="21bc2-149">Even using the **Force** parameter, the cmdlet cannot override security restrictions.</span></span>

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

### <span data-ttu-id="21bc2-150">-InputObject</span><span class="sxs-lookup"><span data-stu-id="21bc2-150">-InputObject</span></span>

<span data-ttu-id="21bc2-151">Gibt die Eingabe für den Ausdruck an, der während der Ablauf Verfolgung verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="21bc2-151">Specifies input to the expression that is being processed during the trace.</span></span> <span data-ttu-id="21bc2-152">Sie können eine Variable eingeben, die die Eingabe darstellt und die vom Ausdruck akzeptiert wird, oder Sie können ein Objekt über die Pipeline übergeben.</span><span class="sxs-lookup"><span data-stu-id="21bc2-152">You can enter a variable that represents the input that the expression accepts, or pass an object through the pipeline.</span></span>

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

### <span data-ttu-id="21bc2-153">-Listeneroption</span><span class="sxs-lookup"><span data-stu-id="21bc2-153">-ListenerOption</span></span>

<span data-ttu-id="21bc2-154">Gibt optionale Daten für das Präfix der einzelnen Ablauf Verfolgungs Meldungen in der Ausgabe an.</span><span class="sxs-lookup"><span data-stu-id="21bc2-154">Specifies optional data to the prefix of each trace message in the output.</span></span> <span data-ttu-id="21bc2-155">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="21bc2-155">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="21bc2-156">Keine</span><span class="sxs-lookup"><span data-stu-id="21bc2-156">None</span></span>
- <span data-ttu-id="21bc2-157">LogicalOperationStack</span><span class="sxs-lookup"><span data-stu-id="21bc2-157">LogicalOperationStack</span></span>
- <span data-ttu-id="21bc2-158">Datetime</span><span class="sxs-lookup"><span data-stu-id="21bc2-158">DateTime</span></span>
- <span data-ttu-id="21bc2-159">Timestamp</span><span class="sxs-lookup"><span data-stu-id="21bc2-159">Timestamp</span></span>
- <span data-ttu-id="21bc2-160">ProcessId</span><span class="sxs-lookup"><span data-stu-id="21bc2-160">ProcessId</span></span>
- <span data-ttu-id="21bc2-161">ThreadID</span><span class="sxs-lookup"><span data-stu-id="21bc2-161">ThreadId</span></span>
- <span data-ttu-id="21bc2-162">Aufruf Liste</span><span class="sxs-lookup"><span data-stu-id="21bc2-162">Callstack</span></span>

<span data-ttu-id="21bc2-163">" **None** " ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="21bc2-163">**None** is the default.</span></span>

<span data-ttu-id="21bc2-164">Um mehrere Optionen anzugeben, trennen Sie diese durch Kommas, aber ohne Leerzeichen, und schließen Sie sie in Anführungszeichen ein, z. B. "ProcessID,ThreadID".</span><span class="sxs-lookup"><span data-stu-id="21bc2-164">To specify multiple options, separate them with commas, but with no spaces, and enclose them in quotation marks, such as "ProcessID,ThreadID".</span></span>

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

### <span data-ttu-id="21bc2-165">-Name</span><span class="sxs-lookup"><span data-stu-id="21bc2-165">-Name</span></span>

<span data-ttu-id="21bc2-166">Gibt ein Array von PowerShell-Komponenten an, die nachverfolgt werden.</span><span class="sxs-lookup"><span data-stu-id="21bc2-166">Specifies an array of PowerShell components that are traced.</span></span> <span data-ttu-id="21bc2-167">Geben Sie den Namen der Ablaufverfolgungsquelle jeder Komponente ein.</span><span class="sxs-lookup"><span data-stu-id="21bc2-167">Enter the name of the trace source of each component.</span></span> <span data-ttu-id="21bc2-168">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="21bc2-168">Wildcards are permitted.</span></span> <span data-ttu-id="21bc2-169">Geben Sie ein, um die Ablauf Verfolgungs Quellen auf Ihrem Computer zu finden `Get-TraceSource` .</span><span class="sxs-lookup"><span data-stu-id="21bc2-169">To find the trace sources on your computer, type `Get-TraceSource`.</span></span>

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

### <span data-ttu-id="21bc2-170">-Option</span><span class="sxs-lookup"><span data-stu-id="21bc2-170">-Option</span></span>

<span data-ttu-id="21bc2-171">Bestimmt den Typ der Ereignisse, die verfolgt werden.</span><span class="sxs-lookup"><span data-stu-id="21bc2-171">Determines the type of events that are traced.</span></span> <span data-ttu-id="21bc2-172">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="21bc2-172">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="21bc2-173">Keine</span><span class="sxs-lookup"><span data-stu-id="21bc2-173">None</span></span>
- <span data-ttu-id="21bc2-174">Konstruktor</span><span class="sxs-lookup"><span data-stu-id="21bc2-174">Constructor</span></span>
- <span data-ttu-id="21bc2-175">Dispose</span><span class="sxs-lookup"><span data-stu-id="21bc2-175">Dispose</span></span>
- <span data-ttu-id="21bc2-176">Finalizer</span><span class="sxs-lookup"><span data-stu-id="21bc2-176">Finalizer</span></span>
- <span data-ttu-id="21bc2-177">Methode</span><span class="sxs-lookup"><span data-stu-id="21bc2-177">Method</span></span>
- <span data-ttu-id="21bc2-178">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="21bc2-178">Property</span></span>
- <span data-ttu-id="21bc2-179">Delegaten</span><span class="sxs-lookup"><span data-stu-id="21bc2-179">Delegates</span></span>
- <span data-ttu-id="21bc2-180">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="21bc2-180">Events</span></span>
- <span data-ttu-id="21bc2-181">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="21bc2-181">Exception</span></span>
- <span data-ttu-id="21bc2-182">Sperre</span><span class="sxs-lookup"><span data-stu-id="21bc2-182">Lock</span></span>
- <span data-ttu-id="21bc2-183">Fehler</span><span class="sxs-lookup"><span data-stu-id="21bc2-183">Error</span></span>
- <span data-ttu-id="21bc2-184">Errors</span><span class="sxs-lookup"><span data-stu-id="21bc2-184">Errors</span></span>
- <span data-ttu-id="21bc2-185">Warnung</span><span class="sxs-lookup"><span data-stu-id="21bc2-185">Warning</span></span>
- <span data-ttu-id="21bc2-186">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="21bc2-186">Verbose</span></span>
- <span data-ttu-id="21bc2-187">WriteLine</span><span class="sxs-lookup"><span data-stu-id="21bc2-187">WriteLine</span></span>
- <span data-ttu-id="21bc2-188">Daten</span><span class="sxs-lookup"><span data-stu-id="21bc2-188">Data</span></span>
- <span data-ttu-id="21bc2-189">`Scope`</span><span class="sxs-lookup"><span data-stu-id="21bc2-189">Scope</span></span>
- <span data-ttu-id="21bc2-190">ExecutionFlow</span><span class="sxs-lookup"><span data-stu-id="21bc2-190">ExecutionFlow</span></span>
- <span data-ttu-id="21bc2-191">Assert</span><span class="sxs-lookup"><span data-stu-id="21bc2-191">Assert</span></span>
- <span data-ttu-id="21bc2-192">Alle</span><span class="sxs-lookup"><span data-stu-id="21bc2-192">All</span></span>

<span data-ttu-id="21bc2-193">„All“ ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="21bc2-193">All is the default.</span></span>

<span data-ttu-id="21bc2-194">Die folgenden Werte sind Kombinationen von anderen Werten:</span><span class="sxs-lookup"><span data-stu-id="21bc2-194">The following values are combinations of other values:</span></span>

- <span data-ttu-id="21bc2-195">Executionflow: (Konstruktor, verwerfen, Finalizer, Methode, Delegaten, Ereignisse und Bereich)</span><span class="sxs-lookup"><span data-stu-id="21bc2-195">ExecutionFlow: (Constructor, Dispose, Finalizer, Method, Delegates, Events, and Scope)</span></span>
- <span data-ttu-id="21bc2-196">Daten: (Konstruktor, verwerfen, Finalizer, Property, verbose und Write teline)</span><span class="sxs-lookup"><span data-stu-id="21bc2-196">Data: (Constructor, Dispose, Finalizer, Property, Verbose, and WriteLine)</span></span>
- <span data-ttu-id="21bc2-197">Fehler: (Fehler und Ausnahme).</span><span class="sxs-lookup"><span data-stu-id="21bc2-197">Errors: (Error and Exception).</span></span>

<span data-ttu-id="21bc2-198">Um mehrere Optionen anzugeben, trennen Sie diese durch Kommas, aber ohne Leerzeichen, und schließen Sie sie in Anführungszeichen ein, z. B. "Constructor,Dispose".</span><span class="sxs-lookup"><span data-stu-id="21bc2-198">To specify multiple options, separate them with commas, but with no spaces, and enclose them in quotation marks, such as "Constructor,Dispose".</span></span>

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

### <span data-ttu-id="21bc2-199">-Pshost</span><span class="sxs-lookup"><span data-stu-id="21bc2-199">-PSHost</span></span>

<span data-ttu-id="21bc2-200">Gibt an, dass das Cmdlet die Ablauf Verfolgungs Ausgabe an den PowerShell-Host sendet.</span><span class="sxs-lookup"><span data-stu-id="21bc2-200">Indicates that the cmdlet sends the trace output to the PowerShell host.</span></span> <span data-ttu-id="21bc2-201">Dieser Parameter wählt auch den PSHost-Ablaufverfolgungslistener aus.</span><span class="sxs-lookup"><span data-stu-id="21bc2-201">This parameter also selects the PSHost trace listener.</span></span>

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

### <span data-ttu-id="21bc2-202">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="21bc2-202">CommonParameters</span></span>

<span data-ttu-id="21bc2-203">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="21bc2-203">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="21bc2-204">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="21bc2-204">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="21bc2-205">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="21bc2-205">INPUTS</span></span>

### <span data-ttu-id="21bc2-206">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="21bc2-206">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="21bc2-207">Sie können Objekte, die Eingaben darstellen, an den Ausdruck übergeben `Trace-Command` .</span><span class="sxs-lookup"><span data-stu-id="21bc2-207">You can pipe objects that represent input to the expression to `Trace-Command`.</span></span>

## <span data-ttu-id="21bc2-208">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="21bc2-208">OUTPUTS</span></span>

### <span data-ttu-id="21bc2-209">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="21bc2-209">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="21bc2-210">Gibt die Befehlsablaufverfolgung im Debug-Stream zurück.</span><span class="sxs-lookup"><span data-stu-id="21bc2-210">Returns the command trace in the debug stream.</span></span>

## <span data-ttu-id="21bc2-211">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="21bc2-211">NOTES</span></span>

- <span data-ttu-id="21bc2-212">Die Ablaufverfolgung ist eine Methode, die Entwickler zum Debuggen und Optimieren von Programmen verwenden.</span><span class="sxs-lookup"><span data-stu-id="21bc2-212">Tracing is a method that developers use to debug and refine programs.</span></span> <span data-ttu-id="21bc2-213">Bei der Ablaufverfolgung erzeugt das Programm ausführliche Meldungen zu den einzelnen Schritten in der internen Verarbeitung.</span><span class="sxs-lookup"><span data-stu-id="21bc2-213">When tracing, the program generates detailed messages about each step in its internal processing.</span></span>

- <span data-ttu-id="21bc2-214">Die PowerShell-Ablaufverfolgungs-Cmdlets sind für die Unterstützung von PowerShell-Entwicklern konzipiert, aber Sie stehen allen Benutzern zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="21bc2-214">The PowerShell tracing cmdlets are designed to help PowerShell developers, but they are available to all users.</span></span> <span data-ttu-id="21bc2-215">Damit können Sie fast jeden Aspekt der Shell-Funktionalität überwachen.</span><span class="sxs-lookup"><span data-stu-id="21bc2-215">They let you monitor nearly every aspect of the functionality of the shell.</span></span>

- <span data-ttu-id="21bc2-216">Zum Ermitteln der PowerShell-Komponenten, die für die Ablauf Verfolgung aktiviert sind, geben Sie ein `Get-Help Get-TraceSource` .</span><span class="sxs-lookup"><span data-stu-id="21bc2-216">To find the PowerShell components that are enabled for tracing, type `Get-Help Get-TraceSource`.</span></span>

  <span data-ttu-id="21bc2-217">Eine Ablauf Verfolgungs Quelle ist der Teil jeder PowerShell-Komponente, die die Ablauf Verfolgung verwaltet und Ablauf Verfolgungs Meldungen für die Komponente generiert.</span><span class="sxs-lookup"><span data-stu-id="21bc2-217">A trace source is the part of each PowerShell component that manages tracing and generates trace messages for the component.</span></span> <span data-ttu-id="21bc2-218">Um eine Komponente zu verfolgen, identifizieren Sie die Ablaufverfolgungsquelle.</span><span class="sxs-lookup"><span data-stu-id="21bc2-218">To trace a component, you identify its trace source.</span></span>

  <span data-ttu-id="21bc2-219">Ein Ablaufverfolgungslistener empfängt die Ausgabe der Ablauf Verfolgung und zeigt Sie dem Benutzer an.</span><span class="sxs-lookup"><span data-stu-id="21bc2-219">A trace listener receives the output of the trace and displays it to the user.</span></span> <span data-ttu-id="21bc2-220">Sie können festlegen, dass die Ablauf Verfolgungs Daten an einen Benutzermodus-oder Kernel Modus-Debugger, an den Host oder die Konsole, an eine Datei oder an einen benutzerdefinierten Listener gesendet werden, der von der **System. Diagnostics. TraceListener** -Klasse abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="21bc2-220">You can elect to send the trace data to a user-mode or kernel-mode debugger, to the host or console, to a file, or to a custom listener derived from the **System.Diagnostics.TraceListener** class.</span></span>

- <span data-ttu-id="21bc2-221">Wenn Sie den CommandSet-Parametersatz verwenden, verarbeitet PowerShell den Befehl genauso wie in einer Pipeline.</span><span class="sxs-lookup"><span data-stu-id="21bc2-221">When you use the commandSet parameter set, PowerShell processes the command just as it would be processed in a pipeline.</span></span> <span data-ttu-id="21bc2-222">Beispielsweise wird die Befehlsermittlung nicht für jedes eingehende Objekt wiederholt.</span><span class="sxs-lookup"><span data-stu-id="21bc2-222">For example, command discovery is not repeated for each incoming object.</span></span>

- <span data-ttu-id="21bc2-223">Die Namen der Parameter " **Name** ", " **Ausdruck** ", " **Option** " und " **Command** " sind optional.</span><span class="sxs-lookup"><span data-stu-id="21bc2-223">The names of the **Name** , **Expression** , **Option** , and **Command** parameters are optional.</span></span> <span data-ttu-id="21bc2-224">Wenn Sie die Parameternamen weglassen, müssen die unbenannten Parameterwerte in dieser Reihenfolge angezeigt werden: **Name** , **Ausdruck** , **Option** oder **Name** , **Befehl** , **Option** .</span><span class="sxs-lookup"><span data-stu-id="21bc2-224">If you omit the parameter names, the unnamed parameter values must appear in this order: **Name** , **Expression** , **Option** or **Name** , **Command** , **Option** .</span></span> <span data-ttu-id="21bc2-225">Wenn Sie die Parameternamen angeben, können die Parameter in beliebiger Reihenfolge angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="21bc2-225">If you include the parameter names, the parameters can appear in any order.</span></span>

## <span data-ttu-id="21bc2-226">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="21bc2-226">RELATED LINKS</span></span>

[<span data-ttu-id="21bc2-227">Get-TraceSource</span><span class="sxs-lookup"><span data-stu-id="21bc2-227">Get-TraceSource</span></span>](Get-TraceSource.md)

[<span data-ttu-id="21bc2-228">Measure-Command</span><span class="sxs-lookup"><span data-stu-id="21bc2-228">Measure-Command</span></span>](Measure-Command.md)

[<span data-ttu-id="21bc2-229">Set-TraceSource</span><span class="sxs-lookup"><span data-stu-id="21bc2-229">Set-TraceSource</span></span>](Set-TraceSource.md)
