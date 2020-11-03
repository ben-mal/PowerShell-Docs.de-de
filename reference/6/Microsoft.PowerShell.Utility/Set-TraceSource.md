---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/set-tracesource?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-TraceSource
ms.openlocfilehash: e6acb18799646a2e238237d3879198e3a78e7f9a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216228"
---
# <span data-ttu-id="bf0df-103">Set-TraceSource</span><span class="sxs-lookup"><span data-stu-id="bf0df-103">Set-TraceSource</span></span>

## <span data-ttu-id="bf0df-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="bf0df-104">SYNOPSIS</span></span>
<span data-ttu-id="bf0df-105">Konfiguriert, startet und beendet eine Ablauf Verfolgung von PowerShell-Komponenten.</span><span class="sxs-lookup"><span data-stu-id="bf0df-105">Configures, starts, and stops a trace of PowerShell components.</span></span>

## <span data-ttu-id="bf0df-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="bf0df-106">SYNTAX</span></span>

### <span data-ttu-id="bf0df-107">optionsset (Standard)</span><span class="sxs-lookup"><span data-stu-id="bf0df-107">optionsSet (Default)</span></span>

```
Set-TraceSource [-Name] <String[]> [[-Option] <PSTraceSourceOptions>] [-ListenerOption <TraceOptions>]
 [-FilePath <String>] [-Force] [-Debugger] [-PSHost] [-PassThru] [<CommonParameters>]
```

### <span data-ttu-id="bf0df-108">removealllistenersset</span><span class="sxs-lookup"><span data-stu-id="bf0df-108">removeAllListenersSet</span></span>

```
Set-TraceSource [-Name] <String[]> [-RemoveListener <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="bf0df-109">removefilelistenersset</span><span class="sxs-lookup"><span data-stu-id="bf0df-109">removeFileListenersSet</span></span>

```
Set-TraceSource [-Name] <String[]> [-RemoveFileListener <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="bf0df-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bf0df-110">DESCRIPTION</span></span>

<span data-ttu-id="bf0df-111">Das Cmdlet " **Set-TraceSource** " konfiguriert, startet und beendet eine Ablauf Verfolgung einer PowerShell-Komponente.</span><span class="sxs-lookup"><span data-stu-id="bf0df-111">The **Set-TraceSource** cmdlet configures, starts, and stops a trace of a PowerShell component.</span></span>
<span data-ttu-id="bf0df-112">Sie können mit ihm angeben, welche Komponenten verfolgt werden sollen und an welches Element die Ausgabe der Ablaufverfolgung gesendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="bf0df-112">You can use it to specify which components will be traced and where the tracing output is sent.</span></span>

## <span data-ttu-id="bf0df-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="bf0df-113">EXAMPLES</span></span>

### <span data-ttu-id="bf0df-114">Beispiel 1: Ablauf Verfolgung der ParameterBinding-Komponente</span><span class="sxs-lookup"><span data-stu-id="bf0df-114">Example 1: Trace the ParameterBinding component</span></span>

```
PS C:\> Set-TraceSource -Name "ParameterBinding" -Option ExecutionFlow -PSHost -ListenerOption "ProcessId,TimeStamp"
```

<span data-ttu-id="bf0df-115">Dieser Befehl startet die Ablauf Verfolgung für die ParameterBinding-Komponente von PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bf0df-115">This command starts tracing for the ParameterBinding component of PowerShell.</span></span>
<span data-ttu-id="bf0df-116">Er verwendet den *Name* -Parameter, um die Ablauf Verfolgungs Quelle anzugeben, den *Option* -Parameter zur Auswahl der executionflow-Ablauf Verfolgungs Ereignisse und den *pshost* -Parameter, um den PowerShell-hostlistener auszuwählen, der die Ausgabe an die Konsole sendet.</span><span class="sxs-lookup"><span data-stu-id="bf0df-116">It uses the *Name* parameter to specify the trace source, the *Option* parameter to select the ExecutionFlow trace events, and the *PSHost* parameter to select the PowerShell host listener, which sends the output to the console.</span></span>
<span data-ttu-id="bf0df-117">Der *listeneroption* -Parameter fügt die ProcessID-und timestamp-Werte zum Präfix der Ablauf Verfolgungs Meldung hinzu.</span><span class="sxs-lookup"><span data-stu-id="bf0df-117">The *ListenerOption* parameter adds the ProcessID and TimeStamp values to the trace message prefix.</span></span>

### <span data-ttu-id="bf0df-118">Beispiel 2: Abbrechen einer Ablauf Verfolgung</span><span class="sxs-lookup"><span data-stu-id="bf0df-118">Example 2: Stop a trace</span></span>

```
PS C:\> Set-TraceSource -Name "ParameterBinding" -RemoveListener "Host"
```

<span data-ttu-id="bf0df-119">Dieser Befehl beendet die Ablauf Verfolgung der ParameterBinding-Komponente von PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bf0df-119">This command stops the trace of the ParameterBinding component of PowerShell.</span></span>
<span data-ttu-id="bf0df-120">Er verwendet den *Name* -Parameter, um die Komponente zu identifizieren, die verfolgt wurde, und den *RemoveListener* -Parameter, um den Ablaufverfolgungslistener</span><span class="sxs-lookup"><span data-stu-id="bf0df-120">It uses the *Name* parameter to identify the component that was being traced and the *RemoveListener* parameter to identify the trace listener.</span></span>

## <span data-ttu-id="bf0df-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bf0df-121">PARAMETERS</span></span>

### <span data-ttu-id="bf0df-122">-Debugger</span><span class="sxs-lookup"><span data-stu-id="bf0df-122">-Debugger</span></span>

<span data-ttu-id="bf0df-123">Gibt an, dass das Cmdlet die Ablauf Verfolgungs Ausgabe an den Debugger sendet.</span><span class="sxs-lookup"><span data-stu-id="bf0df-123">Indicates that the cmdlet sends the trace output to the debugger.</span></span>
<span data-ttu-id="bf0df-124">Sie können die Ausgabe in jedem Benutzer- oder Kernelmodusdebugger oder in Microsoft Visual Studio anzeigen.</span><span class="sxs-lookup"><span data-stu-id="bf0df-124">You can view the output in any user-mode or kernel mode debugger or in Microsoft Visual Studio.</span></span>
<span data-ttu-id="bf0df-125">Dieser Parameter wählt auch den Standard-Ablaufverfolgungslistener aus.</span><span class="sxs-lookup"><span data-stu-id="bf0df-125">This parameter also selects the default trace listener.</span></span>

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

### <span data-ttu-id="bf0df-126">-FilePath</span><span class="sxs-lookup"><span data-stu-id="bf0df-126">-FilePath</span></span>

<span data-ttu-id="bf0df-127">Gibt eine Datei an, an die dieses Cmdlet die Ablauf Verfolgungs Ausgabe sendet.</span><span class="sxs-lookup"><span data-stu-id="bf0df-127">Specifies a file that this cmdlet sends the trace output to.</span></span>
<span data-ttu-id="bf0df-128">Dieser Parameter wählt auch den Ablaufverfolgungslistener der Datei aus.</span><span class="sxs-lookup"><span data-stu-id="bf0df-128">This parameter also selects the file trace listener.</span></span>
<span data-ttu-id="bf0df-129">Wenn Sie diesen Parameter verwenden, um die Ablauf Verfolgung zu starten, verwenden Sie den *removefilelistener* -Parameter, um die Ablauf Verfolgung zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="bf0df-129">If you use this parameter to start the trace, use the *RemoveFileListener* parameter to stop the trace.</span></span>

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

### <span data-ttu-id="bf0df-130">-Force</span><span class="sxs-lookup"><span data-stu-id="bf0df-130">-Force</span></span>

<span data-ttu-id="bf0df-131">Gibt an, dass das Cmdlet eine schreibgeschützte Datei überschreibt.</span><span class="sxs-lookup"><span data-stu-id="bf0df-131">Indicates that the cmdlet overwrites a read-only file.</span></span>
<span data-ttu-id="bf0df-132">Verwenden Sie mit dem *FilePath* -Parameter.</span><span class="sxs-lookup"><span data-stu-id="bf0df-132">Use with the *FilePath* parameter.</span></span>

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

### <span data-ttu-id="bf0df-133">-Listeneroption</span><span class="sxs-lookup"><span data-stu-id="bf0df-133">-ListenerOption</span></span>

<span data-ttu-id="bf0df-134">Gibt optionale Daten für das Präfix der einzelnen Ablauf Verfolgungs Meldungen in der Ausgabe an.</span><span class="sxs-lookup"><span data-stu-id="bf0df-134">Specifies optional data to the prefix of each trace message in the output.</span></span>
<span data-ttu-id="bf0df-135">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="bf0df-135">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="bf0df-136">Keine</span><span class="sxs-lookup"><span data-stu-id="bf0df-136">None</span></span>
- <span data-ttu-id="bf0df-137">LogicalOperationStack</span><span class="sxs-lookup"><span data-stu-id="bf0df-137">LogicalOperationStack</span></span>
- <span data-ttu-id="bf0df-138">Datetime</span><span class="sxs-lookup"><span data-stu-id="bf0df-138">DateTime</span></span>
- <span data-ttu-id="bf0df-139">Timestamp</span><span class="sxs-lookup"><span data-stu-id="bf0df-139">Timestamp</span></span>
- <span data-ttu-id="bf0df-140">ProcessId</span><span class="sxs-lookup"><span data-stu-id="bf0df-140">ProcessId</span></span>
- <span data-ttu-id="bf0df-141">ThreadID</span><span class="sxs-lookup"><span data-stu-id="bf0df-141">ThreadId</span></span>
- <span data-ttu-id="bf0df-142">Aufruf Liste</span><span class="sxs-lookup"><span data-stu-id="bf0df-142">Callstack</span></span>

<span data-ttu-id="bf0df-143">"None" ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="bf0df-143">None is the default.</span></span>

<span data-ttu-id="bf0df-144">Um mehrere Optionen anzugeben, trennen Sie diese durch Kommas, aber ohne Leerzeichen, und schließen Sie sie in Anführungszeichen ein, z. B. "ProcessID,ThreadID".</span><span class="sxs-lookup"><span data-stu-id="bf0df-144">To specify multiple options, separate them with commas, but with no spaces, and enclose them in quotation marks, such as "ProcessID,ThreadID".</span></span>

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

### <span data-ttu-id="bf0df-145">-Name</span><span class="sxs-lookup"><span data-stu-id="bf0df-145">-Name</span></span>

<span data-ttu-id="bf0df-146">Gibt an, welche Komponenten verfolgt werden.</span><span class="sxs-lookup"><span data-stu-id="bf0df-146">Specifies which components are traced.</span></span>
<span data-ttu-id="bf0df-147">Geben Sie den Namen der Ablaufverfolgungsquelle jeder Komponente ein.</span><span class="sxs-lookup"><span data-stu-id="bf0df-147">Enter the name of the trace source of each component.</span></span>
<span data-ttu-id="bf0df-148">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="bf0df-148">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="bf0df-149">-Option</span><span class="sxs-lookup"><span data-stu-id="bf0df-149">-Option</span></span>

<span data-ttu-id="bf0df-150">Gibt den Typ der Ereignisse an, die nachverfolgt werden.</span><span class="sxs-lookup"><span data-stu-id="bf0df-150">Specifies the type of events that are traced.</span></span>
<span data-ttu-id="bf0df-151">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="bf0df-151">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="bf0df-152">Keine</span><span class="sxs-lookup"><span data-stu-id="bf0df-152">None</span></span>
- <span data-ttu-id="bf0df-153">Konstruktor</span><span class="sxs-lookup"><span data-stu-id="bf0df-153">Constructor</span></span>
- <span data-ttu-id="bf0df-154">Dispose</span><span class="sxs-lookup"><span data-stu-id="bf0df-154">Dispose</span></span>
- <span data-ttu-id="bf0df-155">Finalizer</span><span class="sxs-lookup"><span data-stu-id="bf0df-155">Finalizer</span></span>
- <span data-ttu-id="bf0df-156">Methode</span><span class="sxs-lookup"><span data-stu-id="bf0df-156">Method</span></span>
- <span data-ttu-id="bf0df-157">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="bf0df-157">Property</span></span>
- <span data-ttu-id="bf0df-158">Delegaten</span><span class="sxs-lookup"><span data-stu-id="bf0df-158">Delegates</span></span>
- <span data-ttu-id="bf0df-159">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="bf0df-159">Events</span></span>
- <span data-ttu-id="bf0df-160">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="bf0df-160">Exception</span></span>
- <span data-ttu-id="bf0df-161">Sperre</span><span class="sxs-lookup"><span data-stu-id="bf0df-161">Lock</span></span>
- <span data-ttu-id="bf0df-162">Fehler</span><span class="sxs-lookup"><span data-stu-id="bf0df-162">Error</span></span>
- <span data-ttu-id="bf0df-163">Errors</span><span class="sxs-lookup"><span data-stu-id="bf0df-163">Errors</span></span>
- <span data-ttu-id="bf0df-164">Warnung</span><span class="sxs-lookup"><span data-stu-id="bf0df-164">Warning</span></span>
- <span data-ttu-id="bf0df-165">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="bf0df-165">Verbose</span></span>
- <span data-ttu-id="bf0df-166">WriteLine</span><span class="sxs-lookup"><span data-stu-id="bf0df-166">WriteLine</span></span>
- <span data-ttu-id="bf0df-167">Daten</span><span class="sxs-lookup"><span data-stu-id="bf0df-167">Data</span></span>
- <span data-ttu-id="bf0df-168">`Scope`</span><span class="sxs-lookup"><span data-stu-id="bf0df-168">Scope</span></span>
- <span data-ttu-id="bf0df-169">ExecutionFlow</span><span class="sxs-lookup"><span data-stu-id="bf0df-169">ExecutionFlow</span></span>
- <span data-ttu-id="bf0df-170">Assert</span><span class="sxs-lookup"><span data-stu-id="bf0df-170">Assert</span></span>
- <span data-ttu-id="bf0df-171">Alle</span><span class="sxs-lookup"><span data-stu-id="bf0df-171">All</span></span>

<span data-ttu-id="bf0df-172">„All“ ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="bf0df-172">All is the default.</span></span>

<span data-ttu-id="bf0df-173">Die folgenden Werte sind Kombinationen von anderen Werten:</span><span class="sxs-lookup"><span data-stu-id="bf0df-173">The following values are combinations of other values:</span></span>

- <span data-ttu-id="bf0df-174">Executionflow: (Konstruktor, verwerfen, Finalizer, Methode, Delegaten, Ereignisse und Bereich)</span><span class="sxs-lookup"><span data-stu-id="bf0df-174">ExecutionFlow: (Constructor, Dispose, Finalizer, Method, Delegates, Events, and Scope)</span></span>
- <span data-ttu-id="bf0df-175">Daten: (Konstruktor, verwerfen, Finalizer, Property, verbose und Write teline)</span><span class="sxs-lookup"><span data-stu-id="bf0df-175">Data: (Constructor, Dispose, Finalizer, Property, Verbose, and WriteLine)</span></span>
- <span data-ttu-id="bf0df-176">Fehler: (Fehler und Ausnahme).</span><span class="sxs-lookup"><span data-stu-id="bf0df-176">Errors: (Error and Exception).</span></span>

<span data-ttu-id="bf0df-177">Um mehrere Optionen anzugeben, trennen Sie diese durch Kommas, aber ohne Leerzeichen, und schließen Sie sie in Anführungszeichen ein, z. B. "Constructor,Dispose".</span><span class="sxs-lookup"><span data-stu-id="bf0df-177">To specify multiple options, separate them with commas, but with no spaces, and enclose them in quotation marks, such as "Constructor,Dispose".</span></span>

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

### <span data-ttu-id="bf0df-178">-PassThru</span><span class="sxs-lookup"><span data-stu-id="bf0df-178">-PassThru</span></span>

<span data-ttu-id="bf0df-179">Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="bf0df-179">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="bf0df-180">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="bf0df-180">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="bf0df-181">-Pshost</span><span class="sxs-lookup"><span data-stu-id="bf0df-181">-PSHost</span></span>

<span data-ttu-id="bf0df-182">Gibt an, dass dieses Cmdlet die Ablauf Verfolgungs Ausgabe an den PowerShell-Host sendet.</span><span class="sxs-lookup"><span data-stu-id="bf0df-182">ndicates that this cmdlet sends the trace output to the PowerShell host.</span></span>
<span data-ttu-id="bf0df-183">Dieser Parameter wählt auch den PSHost-Ablaufverfolgungslistener aus.</span><span class="sxs-lookup"><span data-stu-id="bf0df-183">This parameter also selects the PSHost trace listener.</span></span>

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

### <span data-ttu-id="bf0df-184">-Removefilelistener</span><span class="sxs-lookup"><span data-stu-id="bf0df-184">-RemoveFileListener</span></span>

<span data-ttu-id="bf0df-185">Beendet die Ablaufverfolgung durch Entfernen des Datei-Ablaufverfolgungslisteners, der der angegebenen Datei zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="bf0df-185">Stops the trace by removing the file trace listener associated with the specified file.</span></span>
<span data-ttu-id="bf0df-186">Geben Sie den Pfad und den Dateinamen der Ablaufverfolgungsausgabe-Datei an.</span><span class="sxs-lookup"><span data-stu-id="bf0df-186">Enter the path and file name of the trace output file.</span></span>

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

### <span data-ttu-id="bf0df-187">-RemoveListener</span><span class="sxs-lookup"><span data-stu-id="bf0df-187">-RemoveListener</span></span>

<span data-ttu-id="bf0df-188">Beendet die Ablaufverfolgung durch Entfernen des Ablaufverfolgungslisteners.</span><span class="sxs-lookup"><span data-stu-id="bf0df-188">Stops the trace by removing the trace listener.</span></span>

<span data-ttu-id="bf0df-189">Verwenden Sie für *RemoveListener* die folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="bf0df-189">Use the following values with *RemoveListener* :</span></span>

- <span data-ttu-id="bf0df-190">Um pshost (Console) zu entfernen, geben Sie ein `Host` .</span><span class="sxs-lookup"><span data-stu-id="bf0df-190">To remove PSHost (console), type `Host`.</span></span>
- <span data-ttu-id="bf0df-191">Um den Debugger zu entfernen, geben Sie ein `Debug` .</span><span class="sxs-lookup"><span data-stu-id="bf0df-191">To remove Debugger, type `Debug`.</span></span>
- <span data-ttu-id="bf0df-192">Um alle Ablaufverfolgungslistener zu entfernen, `*`</span><span class="sxs-lookup"><span data-stu-id="bf0df-192">To remove all trace listeners, type `*`.</span></span>

<span data-ttu-id="bf0df-193">Zum Entfernen des dateiablaufverfolgungslistener verwenden Sie den *removefilelistener* -Parameter.</span><span class="sxs-lookup"><span data-stu-id="bf0df-193">To remove the file trace listener, use the *RemoveFileListener* parameter.</span></span>

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

### <span data-ttu-id="bf0df-194">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="bf0df-194">CommonParameters</span></span>

<span data-ttu-id="bf0df-195">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="bf0df-195">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="bf0df-196">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="bf0df-196">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="bf0df-197">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="bf0df-197">INPUTS</span></span>

### <span data-ttu-id="bf0df-198">System.String</span><span class="sxs-lookup"><span data-stu-id="bf0df-198">System.String</span></span>

<span data-ttu-id="bf0df-199">Sie können eine Zeichenfolge, die einen Namen enthält, über die Pipeline an **Set-TraceSource** übergeben.</span><span class="sxs-lookup"><span data-stu-id="bf0df-199">You can pipe a string that contains a name to **Set-TraceSource** .</span></span>

## <span data-ttu-id="bf0df-200">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="bf0df-200">OUTPUTS</span></span>

### <span data-ttu-id="bf0df-201">None oder System. Management. Automation. pstracesource</span><span class="sxs-lookup"><span data-stu-id="bf0df-201">None or System.Management.Automation.PSTraceSource</span></span>

<span data-ttu-id="bf0df-202">Wenn Sie den *passthru* -Parameter verwenden, generiert **Set-TraceSource** ein **System. Management. Automation. pstracesource** -Objekt, das die Ablauf Verfolgungs Sitzung darstellt.</span><span class="sxs-lookup"><span data-stu-id="bf0df-202">When you use the *PassThru* parameter, **Set-TraceSource** generates a **System.Management.Automation.PSTraceSource** object representing the trace session.</span></span>
<span data-ttu-id="bf0df-203">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="bf0df-203">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="bf0df-204">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="bf0df-204">NOTES</span></span>

* <span data-ttu-id="bf0df-205">Die Ablaufverfolgung ist eine Methode, die Entwickler zum Debuggen und Optimieren von Programmen verwenden.</span><span class="sxs-lookup"><span data-stu-id="bf0df-205">Tracing is a method that developers use to debug and refine programs.</span></span> <span data-ttu-id="bf0df-206">Bei der Ablaufverfolgung erzeugt das Programm ausführliche Meldungen zu den einzelnen Schritten in der internen Verarbeitung.</span><span class="sxs-lookup"><span data-stu-id="bf0df-206">When tracing, the program generates detailed messages about each step in its internal processing.</span></span>

  <span data-ttu-id="bf0df-207">Die PowerShell-Ablaufverfolgungs-Cmdlets sind für die Unterstützung von PowerShell-Entwicklern konzipiert, aber Sie stehen allen Benutzern zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="bf0df-207">The PowerShell tracing cmdlets are designed to help PowerShell developers, but they are available to all users.</span></span>
<span data-ttu-id="bf0df-208">Mit Ihnen können Sie fast jeden Aspekt der Funktionalität von PowerShell überwachen.</span><span class="sxs-lookup"><span data-stu-id="bf0df-208">They let you monitor nearly every aspect of the functionality of PowerShell.</span></span>

  <span data-ttu-id="bf0df-209">Eine Ablauf Verfolgungs Quelle ist der Teil jeder PowerShell-Komponente, die die Ablauf Verfolgung verwaltet und Ablauf Verfolgungs Meldungen für die Komponente generiert.</span><span class="sxs-lookup"><span data-stu-id="bf0df-209">A trace source is the part of each PowerShell component that manages tracing and generates trace messages for the component.</span></span>
<span data-ttu-id="bf0df-210">Um eine Komponente zu verfolgen, identifizieren Sie die Ablaufverfolgungsquelle.</span><span class="sxs-lookup"><span data-stu-id="bf0df-210">To trace a component, you identify its trace source.</span></span>

  <span data-ttu-id="bf0df-211">Ein Ablaufverfolgungslistener empfängt die Ausgabe der Ablauf Verfolgung und zeigt Sie dem Benutzer an.</span><span class="sxs-lookup"><span data-stu-id="bf0df-211">A trace listener receives the output of the trace and displays it to the user.</span></span>
<span data-ttu-id="bf0df-212">Sie können festlegen, dass die Ablauf Verfolgungs Daten an einen Benutzermodus-oder Kernel Modus-Debugger, an die Konsole, an eine Datei oder an einen benutzerdefinierten Listener gesendet werden, der von der **System. Diagnostics. TraceListener** -Klasse abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="bf0df-212">You can elect to send the trace data to a user-mode or kernel-mode debugger, to the console, to a file, or to a custom listener derived from the **System.Diagnostics.TraceListener** class.</span></span>

* <span data-ttu-id="bf0df-213">Um eine Ablauf Verfolgung zu starten, verwenden Sie den *Name* -Parameter, um eine Ablauf Verfolgungs Quelle und die Parameter *FilePath* , *Debugger* oder *pshost* anzugeben, um einen Listener anzugeben (ein Ziel für die Ausgabe).</span><span class="sxs-lookup"><span data-stu-id="bf0df-213">To start a trace, use the *Name* parameter to specify a trace source and the *FilePath* , *Debugger* , or *PSHost* parameters to specify a listener (a destination for the output).</span></span> <span data-ttu-id="bf0df-214">Verwenden Sie den *options* -Parameter, um die Typen der Ablauf Verfolgungs Ereignisse zu bestimmen, und den *listeneroption* -Parameter, um die Ablauf Verfolgungs Ausgabe zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="bf0df-214">Use the *Options* parameter to determine the types of events that are traced and the *ListenerOption* parameter to configure the trace output.</span></span>
* <span data-ttu-id="bf0df-215">Um die Konfiguration einer Ablauf Verfolgung zu ändern, geben Sie einen **Set-TraceSource-** Befehl ein, wie Sie eine Ablauf Verfolgung starten würden.</span><span class="sxs-lookup"><span data-stu-id="bf0df-215">To change the configuration of a trace, enter a **Set-TraceSource** command as you would to start a trace.</span></span> <span data-ttu-id="bf0df-216">PowerShell erkennt, dass die Ablauf Verfolgungs Quelle bereits verfolgt wird.</span><span class="sxs-lookup"><span data-stu-id="bf0df-216">PowerShell recognizes that the trace source is already being traced.</span></span> <span data-ttu-id="bf0df-217">Es beendet die Ablaufverfolgung, fügt die neue Konfiguration hinzu und startet die Ablaufverfolgung erneut.</span><span class="sxs-lookup"><span data-stu-id="bf0df-217">It stops the trace, adds the new configuration, and starts or restarts the trace.</span></span>
* <span data-ttu-id="bf0df-218">Um eine Ablauf Verfolgung zu verhindern, verwenden Sie den *RemoveListener* -Parameter.</span><span class="sxs-lookup"><span data-stu-id="bf0df-218">To stop a trace, use the *RemoveListener* parameter.</span></span> <span data-ttu-id="bf0df-219">Um eine Ablauf Verfolgung zu verhindern, die den dateilistener verwendet (eine Ablauf Verfolgung, die mit dem *FilePath* -Parameter gestartet wurde), verwenden Sie den *removefilelistener* -Parameter.</span><span class="sxs-lookup"><span data-stu-id="bf0df-219">To stop a trace that uses the file listener (a trace started by using the *FilePath* parameter), use the *RemoveFileListener* parameter.</span></span> <span data-ttu-id="bf0df-220">Wenn Sie den Listener entfernen, wird die Ablaufverfolgung beendet.</span><span class="sxs-lookup"><span data-stu-id="bf0df-220">When you remove the listener, the trace stops.</span></span>
* <span data-ttu-id="bf0df-221">Um zu bestimmen, welche Komponenten verfolgt werden können, verwenden Sie Get-TraceSource.</span><span class="sxs-lookup"><span data-stu-id="bf0df-221">To determine which components can be traced, use Get-TraceSource.</span></span> <span data-ttu-id="bf0df-222">Die Ablauf Verfolgungs Quellen für jedes Modul werden automatisch geladen, wenn die Komponente verwendet wird, und Sie werden in der Ausgabe von " **Get-TraceSource** " angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bf0df-222">The trace sources for each module are loaded automatically when the component is in use, and they appear in the output of **Get-TraceSource** .</span></span>

## <span data-ttu-id="bf0df-223">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="bf0df-223">RELATED LINKS</span></span>

[<span data-ttu-id="bf0df-224">Get-TraceSource</span><span class="sxs-lookup"><span data-stu-id="bf0df-224">Get-TraceSource</span></span>](Get-TraceSource.md)

[<span data-ttu-id="bf0df-225">Trace-Command</span><span class="sxs-lookup"><span data-stu-id="bf0df-225">Trace-Command</span></span>](Trace-Command.md)
