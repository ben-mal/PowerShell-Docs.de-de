---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/set-tracesource?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-TraceSource
ms.openlocfilehash: 6e7fd1c6eb3551906b4dd9d947b5e551cd05d30a
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602546"
---
# <span data-ttu-id="3fa33-102">Set-TraceSource</span><span class="sxs-lookup"><span data-stu-id="3fa33-102">Set-TraceSource</span></span>

## <span data-ttu-id="3fa33-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="3fa33-103">SYNOPSIS</span></span>
<span data-ttu-id="3fa33-104">Konfiguriert, startet und beendet eine Ablauf Verfolgung von PowerShell-Komponenten.</span><span class="sxs-lookup"><span data-stu-id="3fa33-104">Configures, starts, and stops a trace of PowerShell components.</span></span>

## <span data-ttu-id="3fa33-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3fa33-105">SYNTAX</span></span>

### <span data-ttu-id="3fa33-106">optionsset (Standard)</span><span class="sxs-lookup"><span data-stu-id="3fa33-106">optionsSet (Default)</span></span>

```
Set-TraceSource [-Name] <String[]> [[-Option] <PSTraceSourceOptions>] [-ListenerOption <TraceOptions>]
 [-FilePath <String>] [-Force] [-Debugger] [-PSHost] [-PassThru] [<CommonParameters>]
```

### <span data-ttu-id="3fa33-107">removealllistenersset</span><span class="sxs-lookup"><span data-stu-id="3fa33-107">removeAllListenersSet</span></span>

```
Set-TraceSource [-Name] <String[]> [-RemoveListener <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="3fa33-108">removefilelistenersset</span><span class="sxs-lookup"><span data-stu-id="3fa33-108">removeFileListenersSet</span></span>

```
Set-TraceSource [-Name] <String[]> [-RemoveFileListener <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="3fa33-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3fa33-109">DESCRIPTION</span></span>

<span data-ttu-id="3fa33-110">Das Cmdlet " **Set-TraceSource** " konfiguriert, startet und beendet eine Ablauf Verfolgung einer PowerShell-Komponente.</span><span class="sxs-lookup"><span data-stu-id="3fa33-110">The **Set-TraceSource** cmdlet configures, starts, and stops a trace of a PowerShell component.</span></span>
<span data-ttu-id="3fa33-111">Sie können mit ihm angeben, welche Komponenten verfolgt werden sollen und an welches Element die Ausgabe der Ablaufverfolgung gesendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="3fa33-111">You can use it to specify which components will be traced and where the tracing output is sent.</span></span>

## <span data-ttu-id="3fa33-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="3fa33-112">EXAMPLES</span></span>

### <span data-ttu-id="3fa33-113">Beispiel 1: Ablauf Verfolgung der ParameterBinding-Komponente</span><span class="sxs-lookup"><span data-stu-id="3fa33-113">Example 1: Trace the ParameterBinding component</span></span>

```
PS C:\> Set-TraceSource -Name "ParameterBinding" -Option ExecutionFlow -PSHost -ListenerOption "ProcessId,TimeStamp"
```

<span data-ttu-id="3fa33-114">Dieser Befehl startet die Ablauf Verfolgung für die ParameterBinding-Komponente von PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3fa33-114">This command starts tracing for the ParameterBinding component of PowerShell.</span></span>
<span data-ttu-id="3fa33-115">Er verwendet den *Name* -Parameter, um die Ablauf Verfolgungs Quelle anzugeben, den *Option* -Parameter zur Auswahl der executionflow-Ablauf Verfolgungs Ereignisse und den *pshost* -Parameter, um den PowerShell-hostlistener auszuwählen, der die Ausgabe an die Konsole sendet.</span><span class="sxs-lookup"><span data-stu-id="3fa33-115">It uses the *Name* parameter to specify the trace source, the *Option* parameter to select the ExecutionFlow trace events, and the *PSHost* parameter to select the PowerShell host listener, which sends the output to the console.</span></span>
<span data-ttu-id="3fa33-116">Der *listeneroption* -Parameter fügt die ProcessID-und timestamp-Werte zum Präfix der Ablauf Verfolgungs Meldung hinzu.</span><span class="sxs-lookup"><span data-stu-id="3fa33-116">The *ListenerOption* parameter adds the ProcessID and TimeStamp values to the trace message prefix.</span></span>

### <span data-ttu-id="3fa33-117">Beispiel 2: Abbrechen einer Ablauf Verfolgung</span><span class="sxs-lookup"><span data-stu-id="3fa33-117">Example 2: Stop a trace</span></span>

```
PS C:\> Set-TraceSource -Name "ParameterBinding" -RemoveListener "Host"
```

<span data-ttu-id="3fa33-118">Dieser Befehl beendet die Ablauf Verfolgung der ParameterBinding-Komponente von PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3fa33-118">This command stops the trace of the ParameterBinding component of PowerShell.</span></span>
<span data-ttu-id="3fa33-119">Er verwendet den *Name* -Parameter, um die Komponente zu identifizieren, die verfolgt wurde, und den *RemoveListener* -Parameter, um den Ablaufverfolgungslistener</span><span class="sxs-lookup"><span data-stu-id="3fa33-119">It uses the *Name* parameter to identify the component that was being traced and the *RemoveListener* parameter to identify the trace listener.</span></span>

## <span data-ttu-id="3fa33-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3fa33-120">PARAMETERS</span></span>

### <span data-ttu-id="3fa33-121">-Debugger</span><span class="sxs-lookup"><span data-stu-id="3fa33-121">-Debugger</span></span>

<span data-ttu-id="3fa33-122">Gibt an, dass das Cmdlet die Ablauf Verfolgungs Ausgabe an den Debugger sendet.</span><span class="sxs-lookup"><span data-stu-id="3fa33-122">Indicates that the cmdlet sends the trace output to the debugger.</span></span>
<span data-ttu-id="3fa33-123">Sie können die Ausgabe in jedem Benutzer- oder Kernelmodusdebugger oder in Microsoft Visual Studio anzeigen.</span><span class="sxs-lookup"><span data-stu-id="3fa33-123">You can view the output in any user-mode or kernel mode debugger or in Microsoft Visual Studio.</span></span>
<span data-ttu-id="3fa33-124">Dieser Parameter wählt auch den Standard-Ablaufverfolgungslistener aus.</span><span class="sxs-lookup"><span data-stu-id="3fa33-124">This parameter also selects the default trace listener.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: optionsSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3fa33-125">-FilePath</span><span class="sxs-lookup"><span data-stu-id="3fa33-125">-FilePath</span></span>

<span data-ttu-id="3fa33-126">Gibt eine Datei an, an die dieses Cmdlet die Ablauf Verfolgungs Ausgabe sendet.</span><span class="sxs-lookup"><span data-stu-id="3fa33-126">Specifies a file that this cmdlet sends the trace output to.</span></span>
<span data-ttu-id="3fa33-127">Dieser Parameter wählt auch den Ablaufverfolgungslistener der Datei aus.</span><span class="sxs-lookup"><span data-stu-id="3fa33-127">This parameter also selects the file trace listener.</span></span>
<span data-ttu-id="3fa33-128">Wenn Sie diesen Parameter verwenden, um die Ablauf Verfolgung zu starten, verwenden Sie den *removefilelistener* -Parameter, um die Ablauf Verfolgung zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="3fa33-128">If you use this parameter to start the trace, use the *RemoveFileListener* parameter to stop the trace.</span></span>

```yaml
Type: System.String
Parameter Sets: optionsSet
Aliases: PSPath, Path

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3fa33-129">-Force</span><span class="sxs-lookup"><span data-stu-id="3fa33-129">-Force</span></span>

<span data-ttu-id="3fa33-130">Gibt an, dass das Cmdlet eine schreibgeschützte Datei überschreibt.</span><span class="sxs-lookup"><span data-stu-id="3fa33-130">Indicates that the cmdlet overwrites a read-only file.</span></span>
<span data-ttu-id="3fa33-131">Verwenden Sie mit dem *FilePath* -Parameter.</span><span class="sxs-lookup"><span data-stu-id="3fa33-131">Use with the *FilePath* parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: optionsSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3fa33-132">-Listeneroption</span><span class="sxs-lookup"><span data-stu-id="3fa33-132">-ListenerOption</span></span>

<span data-ttu-id="3fa33-133">Gibt optionale Daten für das Präfix der einzelnen Ablauf Verfolgungs Meldungen in der Ausgabe an.</span><span class="sxs-lookup"><span data-stu-id="3fa33-133">Specifies optional data to the prefix of each trace message in the output.</span></span>
<span data-ttu-id="3fa33-134">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="3fa33-134">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="3fa33-135">Keine</span><span class="sxs-lookup"><span data-stu-id="3fa33-135">None</span></span>
- <span data-ttu-id="3fa33-136">LogicalOperationStack</span><span class="sxs-lookup"><span data-stu-id="3fa33-136">LogicalOperationStack</span></span>
- <span data-ttu-id="3fa33-137">Datetime</span><span class="sxs-lookup"><span data-stu-id="3fa33-137">DateTime</span></span>
- <span data-ttu-id="3fa33-138">Timestamp</span><span class="sxs-lookup"><span data-stu-id="3fa33-138">Timestamp</span></span>
- <span data-ttu-id="3fa33-139">ProcessId</span><span class="sxs-lookup"><span data-stu-id="3fa33-139">ProcessId</span></span>
- <span data-ttu-id="3fa33-140"> ThreadId</span><span class="sxs-lookup"><span data-stu-id="3fa33-140">ThreadId</span></span>
- <span data-ttu-id="3fa33-141">Aufruf Liste</span><span class="sxs-lookup"><span data-stu-id="3fa33-141">Callstack</span></span>

<span data-ttu-id="3fa33-142">Keine ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="3fa33-142">None is the default.</span></span>

<span data-ttu-id="3fa33-143">Um mehrere Optionen anzugeben, trennen Sie diese durch Kommas, aber ohne Leerzeichen, und schließen Sie sie in Anführungszeichen ein, z. B. "ProcessID,ThreadID".</span><span class="sxs-lookup"><span data-stu-id="3fa33-143">To specify multiple options, separate them with commas, but with no spaces, and enclose them in quotation marks, such as "ProcessID,ThreadID".</span></span>

```yaml
Type: System.Diagnostics.TraceOptions
Parameter Sets: optionsSet
Aliases:
Accepted values: None, LogicalOperationStack, DateTime, Timestamp, ProcessId, ThreadId, Callstack

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3fa33-144">-Name</span><span class="sxs-lookup"><span data-stu-id="3fa33-144">-Name</span></span>

<span data-ttu-id="3fa33-145">Gibt an, welche Komponenten verfolgt werden.</span><span class="sxs-lookup"><span data-stu-id="3fa33-145">Specifies which components are traced.</span></span>
<span data-ttu-id="3fa33-146">Geben Sie den Namen der Ablaufverfolgungsquelle jeder Komponente ein.</span><span class="sxs-lookup"><span data-stu-id="3fa33-146">Enter the name of the trace source of each component.</span></span>
<span data-ttu-id="3fa33-147">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="3fa33-147">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="3fa33-148">-Option</span><span class="sxs-lookup"><span data-stu-id="3fa33-148">-Option</span></span>

<span data-ttu-id="3fa33-149">Gibt den Typ der Ereignisse an, die nachverfolgt werden.</span><span class="sxs-lookup"><span data-stu-id="3fa33-149">Specifies the type of events that are traced.</span></span>
<span data-ttu-id="3fa33-150">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="3fa33-150">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="3fa33-151">Keine</span><span class="sxs-lookup"><span data-stu-id="3fa33-151">None</span></span>
- <span data-ttu-id="3fa33-152">Konstruktor</span><span class="sxs-lookup"><span data-stu-id="3fa33-152">Constructor</span></span>
- <span data-ttu-id="3fa33-153">Dispose</span><span class="sxs-lookup"><span data-stu-id="3fa33-153">Dispose</span></span>
- <span data-ttu-id="3fa33-154">Finalizer</span><span class="sxs-lookup"><span data-stu-id="3fa33-154">Finalizer</span></span>
- <span data-ttu-id="3fa33-155">Methode</span><span class="sxs-lookup"><span data-stu-id="3fa33-155">Method</span></span>
- <span data-ttu-id="3fa33-156">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="3fa33-156">Property</span></span>
- <span data-ttu-id="3fa33-157">Delegaten</span><span class="sxs-lookup"><span data-stu-id="3fa33-157">Delegates</span></span>
- <span data-ttu-id="3fa33-158">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="3fa33-158">Events</span></span>
- <span data-ttu-id="3fa33-159">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="3fa33-159">Exception</span></span>
- <span data-ttu-id="3fa33-160">Sperre</span><span class="sxs-lookup"><span data-stu-id="3fa33-160">Lock</span></span>
- <span data-ttu-id="3fa33-161">Fehler</span><span class="sxs-lookup"><span data-stu-id="3fa33-161">Error</span></span>
- <span data-ttu-id="3fa33-162">Errors</span><span class="sxs-lookup"><span data-stu-id="3fa33-162">Errors</span></span>
- <span data-ttu-id="3fa33-163">Warnung</span><span class="sxs-lookup"><span data-stu-id="3fa33-163">Warning</span></span>
- <span data-ttu-id="3fa33-164">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="3fa33-164">Verbose</span></span>
- <span data-ttu-id="3fa33-165">WriteLine</span><span class="sxs-lookup"><span data-stu-id="3fa33-165">WriteLine</span></span>
- <span data-ttu-id="3fa33-166">Daten</span><span class="sxs-lookup"><span data-stu-id="3fa33-166">Data</span></span>
- <span data-ttu-id="3fa33-167">`Scope`</span><span class="sxs-lookup"><span data-stu-id="3fa33-167">Scope</span></span>
- <span data-ttu-id="3fa33-168">ExecutionFlow</span><span class="sxs-lookup"><span data-stu-id="3fa33-168">ExecutionFlow</span></span>
- <span data-ttu-id="3fa33-169">Assert</span><span class="sxs-lookup"><span data-stu-id="3fa33-169">Assert</span></span>
- <span data-ttu-id="3fa33-170">Alle</span><span class="sxs-lookup"><span data-stu-id="3fa33-170">All</span></span>

<span data-ttu-id="3fa33-171">„All“ ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="3fa33-171">All is the default.</span></span>

<span data-ttu-id="3fa33-172">Die folgenden Werte sind Kombinationen von anderen Werten:</span><span class="sxs-lookup"><span data-stu-id="3fa33-172">The following values are combinations of other values:</span></span>

- <span data-ttu-id="3fa33-173">Executionflow: (Konstruktor, verwerfen, Finalizer, Methode, Delegaten, Ereignisse und Bereich)</span><span class="sxs-lookup"><span data-stu-id="3fa33-173">ExecutionFlow: (Constructor, Dispose, Finalizer, Method, Delegates, Events, and Scope)</span></span>
- <span data-ttu-id="3fa33-174">Daten: (Konstruktor, verwerfen, Finalizer, Property, verbose und Write teline)</span><span class="sxs-lookup"><span data-stu-id="3fa33-174">Data: (Constructor, Dispose, Finalizer, Property, Verbose, and WriteLine)</span></span>
- <span data-ttu-id="3fa33-175">Fehler: (Fehler und Ausnahme).</span><span class="sxs-lookup"><span data-stu-id="3fa33-175">Errors: (Error and Exception).</span></span>

<span data-ttu-id="3fa33-176">Um mehrere Optionen anzugeben, trennen Sie diese durch Kommas, aber ohne Leerzeichen, und schließen Sie sie in Anführungszeichen ein, z. B. "Constructor,Dispose".</span><span class="sxs-lookup"><span data-stu-id="3fa33-176">To specify multiple options, separate them with commas, but with no spaces, and enclose them in quotation marks, such as "Constructor,Dispose".</span></span>

```yaml
Type: System.Management.Automation.PSTraceSourceOptions
Parameter Sets: optionsSet
Aliases:
Accepted values: None, Constructor, Dispose, Finalizer, Method, Property, Delegates, Events, Exception, Lock, Error, Errors, Warning, Verbose, WriteLine, Data, Scope, ExecutionFlow, Assert, All

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="3fa33-177">-PassThru</span><span class="sxs-lookup"><span data-stu-id="3fa33-177">-PassThru</span></span>

<span data-ttu-id="3fa33-178">Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="3fa33-178">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="3fa33-179">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="3fa33-179">By default, this cmdlet does not generate any output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: optionsSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3fa33-180">-Pshost</span><span class="sxs-lookup"><span data-stu-id="3fa33-180">-PSHost</span></span>

<span data-ttu-id="3fa33-181">Gibt an, dass dieses Cmdlet die Ablauf Verfolgungs Ausgabe an den PowerShell-Host sendet.</span><span class="sxs-lookup"><span data-stu-id="3fa33-181">ndicates that this cmdlet sends the trace output to the PowerShell host.</span></span>
<span data-ttu-id="3fa33-182">Dieser Parameter wählt auch den PSHost-Ablaufverfolgungslistener aus.</span><span class="sxs-lookup"><span data-stu-id="3fa33-182">This parameter also selects the PSHost trace listener.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: optionsSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3fa33-183">-Removefilelistener</span><span class="sxs-lookup"><span data-stu-id="3fa33-183">-RemoveFileListener</span></span>

<span data-ttu-id="3fa33-184">Beendet die Ablaufverfolgung durch Entfernen des Datei-Ablaufverfolgungslisteners, der der angegebenen Datei zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="3fa33-184">Stops the trace by removing the file trace listener associated with the specified file.</span></span>
<span data-ttu-id="3fa33-185">Geben Sie den Pfad und den Dateinamen der Ablaufverfolgungsausgabe-Datei an.</span><span class="sxs-lookup"><span data-stu-id="3fa33-185">Enter the path and file name of the trace output file.</span></span>

```yaml
Type: System.String[]
Parameter Sets: removeFileListenersSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3fa33-186">-RemoveListener</span><span class="sxs-lookup"><span data-stu-id="3fa33-186">-RemoveListener</span></span>

<span data-ttu-id="3fa33-187">Beendet die Ablaufverfolgung durch Entfernen des Ablaufverfolgungslisteners.</span><span class="sxs-lookup"><span data-stu-id="3fa33-187">Stops the trace by removing the trace listener.</span></span>

<span data-ttu-id="3fa33-188">Verwenden Sie für *RemoveListener* die folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="3fa33-188">Use the following values with *RemoveListener*:</span></span>

- <span data-ttu-id="3fa33-189">Um pshost (Console) zu entfernen, geben Sie ein `Host` .</span><span class="sxs-lookup"><span data-stu-id="3fa33-189">To remove PSHost (console), type `Host`.</span></span>
- <span data-ttu-id="3fa33-190">Um den Debugger zu entfernen, geben Sie ein `Debug` .</span><span class="sxs-lookup"><span data-stu-id="3fa33-190">To remove Debugger, type `Debug`.</span></span>
- <span data-ttu-id="3fa33-191">Um alle Ablaufverfolgungslistener zu entfernen, `*`</span><span class="sxs-lookup"><span data-stu-id="3fa33-191">To remove all trace listeners, type `*`.</span></span>

<span data-ttu-id="3fa33-192">Zum Entfernen des dateiablaufverfolgungslistener verwenden Sie den *removefilelistener* -Parameter.</span><span class="sxs-lookup"><span data-stu-id="3fa33-192">To remove the file trace listener, use the *RemoveFileListener* parameter.</span></span>

```yaml
Type: System.String[]
Parameter Sets: removeAllListenersSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3fa33-193">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="3fa33-193">CommonParameters</span></span>

<span data-ttu-id="3fa33-194">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3fa33-194">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3fa33-195">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="3fa33-195">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3fa33-196">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="3fa33-196">INPUTS</span></span>

### <span data-ttu-id="3fa33-197">System.String</span><span class="sxs-lookup"><span data-stu-id="3fa33-197">System.String</span></span>

<span data-ttu-id="3fa33-198">Sie können eine Zeichenfolge, die einen Namen enthält, über die Pipeline an **Set-TraceSource** übergeben.</span><span class="sxs-lookup"><span data-stu-id="3fa33-198">You can pipe a string that contains a name to **Set-TraceSource**.</span></span>

## <span data-ttu-id="3fa33-199">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="3fa33-199">OUTPUTS</span></span>

### <span data-ttu-id="3fa33-200">None oder System. Management. Automation. pstracesource</span><span class="sxs-lookup"><span data-stu-id="3fa33-200">None or System.Management.Automation.PSTraceSource</span></span>

<span data-ttu-id="3fa33-201">Wenn Sie den *passthru* -Parameter verwenden, generiert **Set-TraceSource** ein **System. Management. Automation. pstracesource** -Objekt, das die Ablauf Verfolgungs Sitzung darstellt.</span><span class="sxs-lookup"><span data-stu-id="3fa33-201">When you use the *PassThru* parameter, **Set-TraceSource** generates a **System.Management.Automation.PSTraceSource** object representing the trace session.</span></span>
<span data-ttu-id="3fa33-202">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="3fa33-202">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="3fa33-203">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="3fa33-203">NOTES</span></span>

* <span data-ttu-id="3fa33-204">Die Ablaufverfolgung ist eine Methode, die Entwickler zum Debuggen und Optimieren von Programmen verwenden.</span><span class="sxs-lookup"><span data-stu-id="3fa33-204">Tracing is a method that developers use to debug and refine programs.</span></span> <span data-ttu-id="3fa33-205">Bei der Ablaufverfolgung erzeugt das Programm ausführliche Meldungen zu den einzelnen Schritten in der internen Verarbeitung.</span><span class="sxs-lookup"><span data-stu-id="3fa33-205">When tracing, the program generates detailed messages about each step in its internal processing.</span></span>

  <span data-ttu-id="3fa33-206">Die PowerShell-Ablaufverfolgungs-Cmdlets sind für die Unterstützung von PowerShell-Entwicklern konzipiert, aber Sie stehen allen Benutzern zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="3fa33-206">The PowerShell tracing cmdlets are designed to help PowerShell developers, but they are available to all users.</span></span>
<span data-ttu-id="3fa33-207">Mit Ihnen können Sie fast jeden Aspekt der Funktionalität von PowerShell überwachen.</span><span class="sxs-lookup"><span data-stu-id="3fa33-207">They let you monitor nearly every aspect of the functionality of PowerShell.</span></span>

  <span data-ttu-id="3fa33-208">Eine Ablauf Verfolgungs Quelle ist der Teil jeder PowerShell-Komponente, die die Ablauf Verfolgung verwaltet und Ablauf Verfolgungs Meldungen für die Komponente generiert.</span><span class="sxs-lookup"><span data-stu-id="3fa33-208">A trace source is the part of each PowerShell component that manages tracing and generates trace messages for the component.</span></span>
<span data-ttu-id="3fa33-209">Um eine Komponente zu verfolgen, identifizieren Sie die Ablaufverfolgungsquelle.</span><span class="sxs-lookup"><span data-stu-id="3fa33-209">To trace a component, you identify its trace source.</span></span>

  <span data-ttu-id="3fa33-210">Ein Ablaufverfolgungslistener empfängt die Ausgabe der Ablauf Verfolgung und zeigt Sie dem Benutzer an.</span><span class="sxs-lookup"><span data-stu-id="3fa33-210">A trace listener receives the output of the trace and displays it to the user.</span></span>
<span data-ttu-id="3fa33-211">Sie können festlegen, dass die Ablauf Verfolgungs Daten an einen Benutzermodus-oder Kernel Modus-Debugger, an die Konsole, an eine Datei oder an einen benutzerdefinierten Listener gesendet werden, der von der **System. Diagnostics. TraceListener** -Klasse abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="3fa33-211">You can elect to send the trace data to a user-mode or kernel-mode debugger, to the console, to a file, or to a custom listener derived from the **System.Diagnostics.TraceListener** class.</span></span>

* <span data-ttu-id="3fa33-212">Um eine Ablauf Verfolgung zu starten, verwenden Sie den *Name* -Parameter, um eine Ablauf Verfolgungs Quelle und die Parameter *FilePath*, *Debugger* oder *pshost* anzugeben, um einen Listener anzugeben (ein Ziel für die Ausgabe).</span><span class="sxs-lookup"><span data-stu-id="3fa33-212">To start a trace, use the *Name* parameter to specify a trace source and the *FilePath*, *Debugger*, or *PSHost* parameters to specify a listener (a destination for the output).</span></span> <span data-ttu-id="3fa33-213">Verwenden Sie den *options* -Parameter, um die Typen der Ablauf Verfolgungs Ereignisse zu bestimmen, und den *listeneroption* -Parameter, um die Ablauf Verfolgungs Ausgabe zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="3fa33-213">Use the *Options* parameter to determine the types of events that are traced and the *ListenerOption* parameter to configure the trace output.</span></span>
* <span data-ttu-id="3fa33-214">Um die Konfiguration einer Ablauf Verfolgung zu ändern, geben Sie einen **Set-TraceSource-** Befehl ein, wie Sie eine Ablauf Verfolgung starten würden.</span><span class="sxs-lookup"><span data-stu-id="3fa33-214">To change the configuration of a trace, enter a **Set-TraceSource** command as you would to start a trace.</span></span> <span data-ttu-id="3fa33-215">PowerShell erkennt, dass die Ablauf Verfolgungs Quelle bereits verfolgt wird.</span><span class="sxs-lookup"><span data-stu-id="3fa33-215">PowerShell recognizes that the trace source is already being traced.</span></span> <span data-ttu-id="3fa33-216">Es beendet die Ablaufverfolgung, fügt die neue Konfiguration hinzu und startet die Ablaufverfolgung erneut.</span><span class="sxs-lookup"><span data-stu-id="3fa33-216">It stops the trace, adds the new configuration, and starts or restarts the trace.</span></span>
* <span data-ttu-id="3fa33-217">Um eine Ablauf Verfolgung zu verhindern, verwenden Sie den *RemoveListener* -Parameter.</span><span class="sxs-lookup"><span data-stu-id="3fa33-217">To stop a trace, use the *RemoveListener* parameter.</span></span> <span data-ttu-id="3fa33-218">Um eine Ablauf Verfolgung zu verhindern, die den dateilistener verwendet (eine Ablauf Verfolgung, die mit dem *FilePath* -Parameter gestartet wurde), verwenden Sie den *removefilelistener* -Parameter.</span><span class="sxs-lookup"><span data-stu-id="3fa33-218">To stop a trace that uses the file listener (a trace started by using the *FilePath* parameter), use the *RemoveFileListener* parameter.</span></span> <span data-ttu-id="3fa33-219">Wenn Sie den Listener entfernen, wird die Ablaufverfolgung beendet.</span><span class="sxs-lookup"><span data-stu-id="3fa33-219">When you remove the listener, the trace stops.</span></span>
* <span data-ttu-id="3fa33-220">Um zu bestimmen, welche Komponenten verfolgt werden können, verwenden Sie Get-TraceSource.</span><span class="sxs-lookup"><span data-stu-id="3fa33-220">To determine which components can be traced, use Get-TraceSource.</span></span> <span data-ttu-id="3fa33-221">Die Ablauf Verfolgungs Quellen für jedes Modul werden automatisch geladen, wenn die Komponente verwendet wird, und Sie werden in der Ausgabe von " **Get-TraceSource**" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3fa33-221">The trace sources for each module are loaded automatically when the component is in use, and they appear in the output of **Get-TraceSource**.</span></span>

## <span data-ttu-id="3fa33-222">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="3fa33-222">RELATED LINKS</span></span>

[<span data-ttu-id="3fa33-223">Get-TraceSource</span><span class="sxs-lookup"><span data-stu-id="3fa33-223">Get-TraceSource</span></span>](Get-TraceSource.md)

[<span data-ttu-id="3fa33-224">Trace-Command</span><span class="sxs-lookup"><span data-stu-id="3fa33-224">Trace-Command</span></span>](Trace-Command.md)

