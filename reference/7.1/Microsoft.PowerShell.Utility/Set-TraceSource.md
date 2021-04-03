---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/01/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/set-tracesource?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-TraceSource
ms.openlocfilehash: 42fd191f8f4b0bc4060f290cf906c71e9000a97c
ms.sourcegitcommit: 5b48fe7b2593581b7d4f7dd7c22206d8a45bb8af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "106184425"
---
# <span data-ttu-id="9dcfa-103">Set-TraceSource</span><span class="sxs-lookup"><span data-stu-id="9dcfa-103">Set-TraceSource</span></span>

## <span data-ttu-id="9dcfa-104">Übersicht</span><span class="sxs-lookup"><span data-stu-id="9dcfa-104">Synopsis</span></span>
<span data-ttu-id="9dcfa-105">Konfiguriert, startet und beendet eine Ablauf Verfolgung von PowerShell-Komponenten.</span><span class="sxs-lookup"><span data-stu-id="9dcfa-105">Configures, starts, and stops a trace of PowerShell components.</span></span>

## <span data-ttu-id="9dcfa-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="9dcfa-106">Syntax</span></span>

### <span data-ttu-id="9dcfa-107">optionsset (Standard)</span><span class="sxs-lookup"><span data-stu-id="9dcfa-107">optionsSet (Default)</span></span>

```
Set-TraceSource [-Name] <String[]> [[-Option] <PSTraceSourceOptions>] [-ListenerOption <TraceOptions>]
 [-FilePath <String>] [-Force] [-Debugger] [-PSHost] [-PassThru] [<CommonParameters>]
```

### <span data-ttu-id="9dcfa-108">removealllistenersset</span><span class="sxs-lookup"><span data-stu-id="9dcfa-108">removeAllListenersSet</span></span>

```
Set-TraceSource [-Name] <String[]> [-RemoveListener <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="9dcfa-109">removefilelistenersset</span><span class="sxs-lookup"><span data-stu-id="9dcfa-109">removeFileListenersSet</span></span>

```
Set-TraceSource [-Name] <String[]> [-RemoveFileListener <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="9dcfa-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9dcfa-110">Description</span></span>

<span data-ttu-id="9dcfa-111">`Set-TraceSource`Mit dem-Cmdlet wird eine Ablauf Verfolgung einer PowerShell-Komponente konfiguriert, gestartet und beendet.</span><span class="sxs-lookup"><span data-stu-id="9dcfa-111">The `Set-TraceSource` cmdlet configures, starts, and stops a trace of a PowerShell component.</span></span> <span data-ttu-id="9dcfa-112">Sie können mit ihm angeben, welche Komponenten verfolgt werden sollen und an welches Element die Ausgabe der Ablaufverfolgung gesendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="9dcfa-112">You can use it to specify which components will be traced and where the tracing output is sent.</span></span>

## <span data-ttu-id="9dcfa-113">Beispiele</span><span class="sxs-lookup"><span data-stu-id="9dcfa-113">Examples</span></span>

### <span data-ttu-id="9dcfa-114">Beispiel 1: Ablauf Verfolgung der ParameterBinding-Komponente</span><span class="sxs-lookup"><span data-stu-id="9dcfa-114">Example 1: Trace the ParameterBinding component</span></span>

```
Set-TraceSource -Name "ParameterBinding" -Option ExecutionFlow -PSHost -ListenerOption "ProcessId,TimeStamp"
```

<span data-ttu-id="9dcfa-115">Dieser Befehl startet die Ablauf Verfolgung für die ParameterBinding-Komponente von PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9dcfa-115">This command starts tracing for the ParameterBinding component of PowerShell.</span></span> <span data-ttu-id="9dcfa-116">Er verwendet den **Name** -Parameter, um die Ablauf Verfolgungs Quelle anzugeben, den **Option** -Parameter, um die Ablauf `ExecutionFlow` Verfolgungs Ereignisse auszuwählen, und den **pshost** -Parameter, um den PowerShell-hostlistener auszuwählen, der die Ausgabe an die Konsole sendet.</span><span class="sxs-lookup"><span data-stu-id="9dcfa-116">It uses the **Name** parameter to specify the trace source, the **Option** parameter to select the `ExecutionFlow` trace events, and the **PSHost** parameter to select the PowerShell host listener, which sends the output to the console.</span></span> <span data-ttu-id="9dcfa-117">Der **listeneroption** -Parameter fügt `ProcessID` die `TimeStamp` Werte und zum Präfix der Ablauf Verfolgungs Meldung hinzu.</span><span class="sxs-lookup"><span data-stu-id="9dcfa-117">The **ListenerOption** parameter adds the `ProcessID` and `TimeStamp` values to the trace message prefix.</span></span>

### <span data-ttu-id="9dcfa-118">Beispiel 2: Abbrechen einer Ablauf Verfolgung</span><span class="sxs-lookup"><span data-stu-id="9dcfa-118">Example 2: Stop a trace</span></span>

```
Set-TraceSource -Name "ParameterBinding" -RemoveListener "Host"
```

<span data-ttu-id="9dcfa-119">Dieser Befehl beendet die Ablauf Verfolgung der **ParameterBinding** -Komponente von PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9dcfa-119">This command stops the trace of the **ParameterBinding** component of PowerShell.</span></span> <span data-ttu-id="9dcfa-120">Er verwendet den **Name** -Parameter, um die Komponente zu identifizieren, die verfolgt wurde, und den **RemoveListener** -Parameter, um den Ablaufverfolgungslistener</span><span class="sxs-lookup"><span data-stu-id="9dcfa-120">It uses the **Name** parameter to identify the component that was being traced and the **RemoveListener** parameter to identify the trace listener.</span></span>

## <span data-ttu-id="9dcfa-121">Parameter</span><span class="sxs-lookup"><span data-stu-id="9dcfa-121">Parameters</span></span>

### <span data-ttu-id="9dcfa-122">-Debugger</span><span class="sxs-lookup"><span data-stu-id="9dcfa-122">-Debugger</span></span>

<span data-ttu-id="9dcfa-123">Gibt an, dass das Cmdlet die Ablauf Verfolgungs Ausgabe an den Debugger sendet.</span><span class="sxs-lookup"><span data-stu-id="9dcfa-123">Indicates that the cmdlet sends the trace output to the debugger.</span></span> <span data-ttu-id="9dcfa-124">Sie können die Ausgabe in jedem Benutzer- oder Kernelmodusdebugger oder in Microsoft Visual Studio anzeigen.</span><span class="sxs-lookup"><span data-stu-id="9dcfa-124">You can view the output in any user-mode or kernel mode debugger or in Microsoft Visual Studio.</span></span> <span data-ttu-id="9dcfa-125">Dieser Parameter wählt auch den Standard-Ablaufverfolgungslistener aus.</span><span class="sxs-lookup"><span data-stu-id="9dcfa-125">This parameter also selects the default trace listener.</span></span>

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

### <span data-ttu-id="9dcfa-126">-FilePath</span><span class="sxs-lookup"><span data-stu-id="9dcfa-126">-FilePath</span></span>

<span data-ttu-id="9dcfa-127">Gibt eine Datei an, an die dieses Cmdlet die Ablauf Verfolgungs Ausgabe sendet.</span><span class="sxs-lookup"><span data-stu-id="9dcfa-127">Specifies a file that this cmdlet sends the trace output to.</span></span> <span data-ttu-id="9dcfa-128">Dieser Parameter wählt auch den Ablaufverfolgungslistener der Datei aus.</span><span class="sxs-lookup"><span data-stu-id="9dcfa-128">This parameter also selects the file trace listener.</span></span> <span data-ttu-id="9dcfa-129">Wenn Sie diesen Parameter verwenden, um die Ablauf Verfolgung zu starten, verwenden Sie den **removefilelistener** -Parameter, um die Ablauf Verfolgung zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="9dcfa-129">If you use this parameter to start the trace, use the **RemoveFileListener** parameter to stop the trace.</span></span>

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

### <span data-ttu-id="9dcfa-130">-Force</span><span class="sxs-lookup"><span data-stu-id="9dcfa-130">-Force</span></span>

<span data-ttu-id="9dcfa-131">Gibt an, dass das Cmdlet eine schreibgeschützte Datei überschreibt.</span><span class="sxs-lookup"><span data-stu-id="9dcfa-131">Indicates that the cmdlet overwrites a read-only file.</span></span> <span data-ttu-id="9dcfa-132">Verwenden Sie mit dem **FilePath** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="9dcfa-132">Use with the **FilePath** parameter.</span></span>

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

### <span data-ttu-id="9dcfa-133">-Listeneroption</span><span class="sxs-lookup"><span data-stu-id="9dcfa-133">-ListenerOption</span></span>

<span data-ttu-id="9dcfa-134">Gibt optionale Daten für das Präfix der einzelnen Ablauf Verfolgungs Meldungen in der Ausgabe an.</span><span class="sxs-lookup"><span data-stu-id="9dcfa-134">Specifies optional data to the prefix of each trace message in the output.</span></span> <span data-ttu-id="9dcfa-135">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="9dcfa-135">The acceptable values for this parameter are:</span></span>

- `None`
- `LogicalOperationStack`
- `DateTime`
- `Timestamp`
- `ProcessId`
- `ThreadId`
- `Callstack`

<span data-ttu-id="9dcfa-136">`None` ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="9dcfa-136">`None` is the default.</span></span>

<span data-ttu-id="9dcfa-137">Diese Werte werden als Flag-basierte Enumeration definiert.</span><span class="sxs-lookup"><span data-stu-id="9dcfa-137">These values are defined as a flag-based enumeration.</span></span> <span data-ttu-id="9dcfa-138">Sie können mehrere Werte kombinieren, um mehrere Flags mithilfe dieses Parameters festzulegen.</span><span class="sxs-lookup"><span data-stu-id="9dcfa-138">You can combine multiple values together to set multiple flags using this parameter.</span></span> <span data-ttu-id="9dcfa-139">Die Werte können als Array von Werten an den **listeneroption** -Parameter oder als durch Trennzeichen getrennte Zeichenfolge dieser Werte übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="9dcfa-139">The values can be passed to the **ListenerOption** parameter as an array of values or as a comma-separated string of those values.</span></span> <span data-ttu-id="9dcfa-140">Mit dem-Cmdlet werden die Werte mithilfe eines binären OR-Vorgangs kombiniert.</span><span class="sxs-lookup"><span data-stu-id="9dcfa-140">The cmdlet will combine the values using a binary-OR operation.</span></span> <span data-ttu-id="9dcfa-141">Das übergeben von Werten als Array ist die einfachste Option und ermöglicht Ihnen außerdem, die Vervollständigung mit der Tab-Taste für die Werte zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="9dcfa-141">Passing values as an array is the simplest option and also allows you to use tab-completion on the values.</span></span>

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

### <span data-ttu-id="9dcfa-142">-Name</span><span class="sxs-lookup"><span data-stu-id="9dcfa-142">-Name</span></span>

<span data-ttu-id="9dcfa-143">Gibt an, welche Komponenten verfolgt werden.</span><span class="sxs-lookup"><span data-stu-id="9dcfa-143">Specifies which components are traced.</span></span> <span data-ttu-id="9dcfa-144">Geben Sie den Namen der Ablaufverfolgungsquelle jeder Komponente ein.</span><span class="sxs-lookup"><span data-stu-id="9dcfa-144">Enter the name of the trace source of each component.</span></span>
<span data-ttu-id="9dcfa-145">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="9dcfa-145">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="9dcfa-146">-Option</span><span class="sxs-lookup"><span data-stu-id="9dcfa-146">-Option</span></span>

<span data-ttu-id="9dcfa-147">Gibt den Typ der Ereignisse an, die nachverfolgt werden.</span><span class="sxs-lookup"><span data-stu-id="9dcfa-147">Specifies the type of events that are traced.</span></span> <span data-ttu-id="9dcfa-148">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="9dcfa-148">The acceptable values for this parameter are:</span></span>

- `None`
- `Constructor`
- `Dispose`
- `Finalizer`
- `Method`
- `Property`
- `Delegates`
- `Events`
- `Exception`
- `Lock`
- `Error`
- `Errors`
- `Warning`
- `Verbose`
- `WriteLine`
- `Data`
- `Scope`
- `ExecutionFlow`
- `Assert`
- `All`

<span data-ttu-id="9dcfa-149">`All` ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="9dcfa-149">`All` is the default.</span></span>

<span data-ttu-id="9dcfa-150">Die folgenden Werte sind Kombinationen von anderen Werten:</span><span class="sxs-lookup"><span data-stu-id="9dcfa-150">The following values are combinations of other values:</span></span>

- <span data-ttu-id="9dcfa-151">`ExecutionFlow`: `Constructor`, `Dispose`, `Finalizer`, `Method`, `Delegates`, `Events`, `Scope`</span><span class="sxs-lookup"><span data-stu-id="9dcfa-151">`ExecutionFlow`: `Constructor`, `Dispose`, `Finalizer`, `Method`, `Delegates`, `Events`, `Scope`</span></span>
- <span data-ttu-id="9dcfa-152">`Data`: `Constructor`, `Dispose`, `Finalizer`, `Property`, `Verbose`, `WriteLine`</span><span class="sxs-lookup"><span data-stu-id="9dcfa-152">`Data`: `Constructor`, `Dispose`, `Finalizer`, `Property`, `Verbose`, `WriteLine`</span></span>
- <span data-ttu-id="9dcfa-153">`Errors`: `Error`, `Exception`</span><span class="sxs-lookup"><span data-stu-id="9dcfa-153">`Errors`: `Error`, `Exception`</span></span>

<span data-ttu-id="9dcfa-154">Diese Werte werden als Flag-basierte Enumeration definiert.</span><span class="sxs-lookup"><span data-stu-id="9dcfa-154">These values are defined as a flag-based enumeration.</span></span> <span data-ttu-id="9dcfa-155">Sie können mehrere Werte kombinieren, um mehrere Flags mithilfe dieses Parameters festzulegen.</span><span class="sxs-lookup"><span data-stu-id="9dcfa-155">You can combine multiple values together to set multiple flags using this parameter.</span></span> <span data-ttu-id="9dcfa-156">Die Werte können als Array von Werten an den **options** Parameter oder als durch Trennzeichen getrennte Zeichenfolge dieser Werte übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="9dcfa-156">The values can be passed to the **Option** parameter as an array of values or as a comma-separated string of those values.</span></span> <span data-ttu-id="9dcfa-157">Mit dem-Cmdlet werden die Werte mithilfe eines binären OR-Vorgangs kombiniert.</span><span class="sxs-lookup"><span data-stu-id="9dcfa-157">The cmdlet will combine the values using a binary-OR operation.</span></span> <span data-ttu-id="9dcfa-158">Das übergeben von Werten als Array ist die einfachste Option und ermöglicht Ihnen außerdem, die Vervollständigung mit der Tab-Taste für die Werte zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="9dcfa-158">Passing values as an array is the simplest option and also allows you to use tab-completion on the values.</span></span>

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

### <span data-ttu-id="9dcfa-159">-PassThru</span><span class="sxs-lookup"><span data-stu-id="9dcfa-159">-PassThru</span></span>

<span data-ttu-id="9dcfa-160">Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="9dcfa-160">Returns an object representing the item with which you are working.</span></span> <span data-ttu-id="9dcfa-161">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="9dcfa-161">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="9dcfa-162">-Pshost</span><span class="sxs-lookup"><span data-stu-id="9dcfa-162">-PSHost</span></span>

<span data-ttu-id="9dcfa-163">Gibt an, dass dieses Cmdlet die Ablauf Verfolgungs Ausgabe an den PowerShell-Host sendet.</span><span class="sxs-lookup"><span data-stu-id="9dcfa-163">Indicates that this cmdlet sends the trace output to the PowerShell host.</span></span> <span data-ttu-id="9dcfa-164">Dieser Parameter wählt auch den PSHost-Ablaufverfolgungslistener aus.</span><span class="sxs-lookup"><span data-stu-id="9dcfa-164">This parameter also selects the PSHost trace listener.</span></span>

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

### <span data-ttu-id="9dcfa-165">-Removefilelistener</span><span class="sxs-lookup"><span data-stu-id="9dcfa-165">-RemoveFileListener</span></span>

<span data-ttu-id="9dcfa-166">Beendet die Ablaufverfolgung durch Entfernen des Datei-Ablaufverfolgungslisteners, der der angegebenen Datei zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="9dcfa-166">Stops the trace by removing the file trace listener associated with the specified file.</span></span> <span data-ttu-id="9dcfa-167">Geben Sie den Pfad und den Dateinamen der Ablaufverfolgungsausgabe-Datei an.</span><span class="sxs-lookup"><span data-stu-id="9dcfa-167">Enter the path and file name of the trace output file.</span></span>

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

### <span data-ttu-id="9dcfa-168">-RemoveListener</span><span class="sxs-lookup"><span data-stu-id="9dcfa-168">-RemoveListener</span></span>

<span data-ttu-id="9dcfa-169">Beendet die Ablaufverfolgung durch Entfernen des Ablaufverfolgungslisteners.</span><span class="sxs-lookup"><span data-stu-id="9dcfa-169">Stops the trace by removing the trace listener.</span></span>

<span data-ttu-id="9dcfa-170">Verwenden Sie für **RemoveListener** die folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="9dcfa-170">Use the following values with **RemoveListener**:</span></span>

- <span data-ttu-id="9dcfa-171">Um pshost (Console) zu entfernen, geben Sie ein `Host` .</span><span class="sxs-lookup"><span data-stu-id="9dcfa-171">To remove PSHost (console), type `Host`.</span></span>
- <span data-ttu-id="9dcfa-172">Um den Debugger zu entfernen, geben Sie ein `Debug` .</span><span class="sxs-lookup"><span data-stu-id="9dcfa-172">To remove Debugger, type `Debug`.</span></span>
- <span data-ttu-id="9dcfa-173">Um alle Ablaufverfolgungslistener zu entfernen, `*`</span><span class="sxs-lookup"><span data-stu-id="9dcfa-173">To remove all trace listeners, type `*`.</span></span>

<span data-ttu-id="9dcfa-174">Zum Entfernen des dateiablaufverfolgungslistener verwenden Sie den **removefilelistener** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="9dcfa-174">To remove the file trace listener, use the **RemoveFileListener** parameter.</span></span>

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

### <span data-ttu-id="9dcfa-175">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="9dcfa-175">CommonParameters</span></span>

<span data-ttu-id="9dcfa-176">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9dcfa-176">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9dcfa-177">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="9dcfa-177">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9dcfa-178">Eingaben</span><span class="sxs-lookup"><span data-stu-id="9dcfa-178">Inputs</span></span>

### <span data-ttu-id="9dcfa-179">System.String</span><span class="sxs-lookup"><span data-stu-id="9dcfa-179">System.String</span></span>

<span data-ttu-id="9dcfa-180">Sie können eine Zeichenfolge, die einen Namen enthält, an die Pipeline übergeben `Set-TraceSource` .</span><span class="sxs-lookup"><span data-stu-id="9dcfa-180">You can pipe a string that contains a name to `Set-TraceSource`.</span></span>

## <span data-ttu-id="9dcfa-181">Ausgaben</span><span class="sxs-lookup"><span data-stu-id="9dcfa-181">Outputs</span></span>

### <span data-ttu-id="9dcfa-182">None oder System. Management. Automation. pstracesource</span><span class="sxs-lookup"><span data-stu-id="9dcfa-182">None or System.Management.Automation.PSTraceSource</span></span>

<span data-ttu-id="9dcfa-183">Wenn Sie den **passthru** -Parameter verwenden, `Set-TraceSource` generiert ein **System. Management. Automation. pstracesource** -Objekt, das die Ablauf Verfolgungs Sitzung darstellt.</span><span class="sxs-lookup"><span data-stu-id="9dcfa-183">When you use the **PassThru** parameter, `Set-TraceSource` generates a **System.Management.Automation.PSTraceSource** object representing the trace session.</span></span> <span data-ttu-id="9dcfa-184">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="9dcfa-184">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="9dcfa-185">Notizen</span><span class="sxs-lookup"><span data-stu-id="9dcfa-185">Notes</span></span>

- <span data-ttu-id="9dcfa-186">Die Ablaufverfolgung ist eine Methode, die Entwickler zum Debuggen und Optimieren von Programmen verwenden.</span><span class="sxs-lookup"><span data-stu-id="9dcfa-186">Tracing is a method that developers use to debug and refine programs.</span></span> <span data-ttu-id="9dcfa-187">Bei der Ablaufverfolgung erzeugt das Programm ausführliche Meldungen zu den einzelnen Schritten in der internen Verarbeitung.</span><span class="sxs-lookup"><span data-stu-id="9dcfa-187">When tracing, the program generates detailed messages about each step in its internal processing.</span></span>

  <span data-ttu-id="9dcfa-188">Die PowerShell-Ablaufverfolgungs-Cmdlets sind für die Unterstützung von PowerShell-Entwicklern konzipiert, aber Sie stehen allen Benutzern zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="9dcfa-188">The PowerShell tracing cmdlets are designed to help PowerShell developers, but they are available to all users.</span></span> <span data-ttu-id="9dcfa-189">Mit Ihnen können Sie fast jeden Aspekt der Funktionalität von PowerShell überwachen.</span><span class="sxs-lookup"><span data-stu-id="9dcfa-189">They let you monitor nearly every aspect of the functionality of PowerShell.</span></span>

  <span data-ttu-id="9dcfa-190">Eine Ablauf Verfolgungs Quelle ist der Teil jeder PowerShell-Komponente, die die Ablauf Verfolgung verwaltet und Ablauf Verfolgungs Meldungen für die Komponente generiert.</span><span class="sxs-lookup"><span data-stu-id="9dcfa-190">A trace source is the part of each PowerShell component that manages tracing and generates trace messages for the component.</span></span> <span data-ttu-id="9dcfa-191">Um eine Komponente zu verfolgen, identifizieren Sie die Ablaufverfolgungsquelle.</span><span class="sxs-lookup"><span data-stu-id="9dcfa-191">To trace a component, you identify its trace source.</span></span>

  <span data-ttu-id="9dcfa-192">Ein Ablaufverfolgungslistener empfängt die Ausgabe der Ablauf Verfolgung und zeigt Sie dem Benutzer an.</span><span class="sxs-lookup"><span data-stu-id="9dcfa-192">A trace listener receives the output of the trace and displays it to the user.</span></span> <span data-ttu-id="9dcfa-193">Sie können festlegen, dass die Ablauf Verfolgungs Daten an einen Benutzermodus-oder Kernel Modus-Debugger, an die Konsole, an eine Datei oder an einen benutzerdefinierten Listener gesendet werden, der von der **System. Diagnostics. TraceListener** -Klasse abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="9dcfa-193">You can elect to send the trace data to a user-mode or kernel-mode debugger, to the console, to a file, or to a custom listener derived from the **System.Diagnostics.TraceListener** class.</span></span>

- <span data-ttu-id="9dcfa-194">Um eine Ablauf Verfolgung zu starten, verwenden Sie den **Name** -Parameter, um eine Ablauf Verfolgungs Quelle und die Parameter **FilePath**, **Debugger** oder **pshost** anzugeben, um einen Listener anzugeben (ein Ziel für die Ausgabe).</span><span class="sxs-lookup"><span data-stu-id="9dcfa-194">To start a trace, use the **Name** parameter to specify a trace source and the **FilePath**, **Debugger**, or **PSHost** parameters to specify a listener (a destination for the output).</span></span> <span data-ttu-id="9dcfa-195">Verwenden Sie den **options** -Parameter, um die Typen der Ablauf Verfolgungs Ereignisse zu bestimmen, und den **listeneroption** -Parameter, um die Ablauf Verfolgungs Ausgabe zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="9dcfa-195">Use the **Options** parameter to determine the types of events that are traced and the **ListenerOption** parameter to configure the trace output.</span></span>
- <span data-ttu-id="9dcfa-196">Um die Konfiguration einer Ablauf Verfolgung zu ändern, geben `Set-TraceSource` Sie einen Befehl ein, wie Sie eine Ablauf Verfolgung starten würden.</span><span class="sxs-lookup"><span data-stu-id="9dcfa-196">To change the configuration of a trace, enter a `Set-TraceSource` command as you would to start a trace.</span></span> <span data-ttu-id="9dcfa-197">PowerShell erkennt, dass die Ablauf Verfolgungs Quelle bereits verfolgt wird.</span><span class="sxs-lookup"><span data-stu-id="9dcfa-197">PowerShell recognizes that the trace source is already being traced.</span></span> <span data-ttu-id="9dcfa-198">Es beendet die Ablaufverfolgung, fügt die neue Konfiguration hinzu und startet die Ablaufverfolgung erneut.</span><span class="sxs-lookup"><span data-stu-id="9dcfa-198">It stops the trace, adds the new configuration, and starts or restarts the trace.</span></span>
- <span data-ttu-id="9dcfa-199">Um eine Ablauf Verfolgung zu verhindern, verwenden Sie den **RemoveListener** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="9dcfa-199">To stop a trace, use the **RemoveListener** parameter.</span></span> <span data-ttu-id="9dcfa-200">Um eine Ablauf Verfolgung zu verhindern, die den dateilistener verwendet (eine Ablauf Verfolgung, die mit dem **FilePath** -Parameter gestartet wurde), verwenden Sie den **removefilelistener** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="9dcfa-200">To stop a trace that uses the file listener (a trace started by using the **FilePath** parameter), use the **RemoveFileListener** parameter.</span></span>
  <span data-ttu-id="9dcfa-201">Wenn Sie den Listener entfernen, wird die Ablaufverfolgung beendet.</span><span class="sxs-lookup"><span data-stu-id="9dcfa-201">When you remove the listener, the trace stops.</span></span>
- <span data-ttu-id="9dcfa-202">Um zu bestimmen, welche Komponenten verfolgt werden können, verwenden Sie Get-TraceSource.</span><span class="sxs-lookup"><span data-stu-id="9dcfa-202">To determine which components can be traced, use Get-TraceSource.</span></span> <span data-ttu-id="9dcfa-203">Die Ablauf Verfolgungs Quellen für jedes Modul werden automatisch geladen, wenn die Komponente verwendet wird, und Sie werden in der Ausgabe von angezeigt `Get-TraceSource` .</span><span class="sxs-lookup"><span data-stu-id="9dcfa-203">The trace sources for each module are loaded automatically when the component is in use, and they appear in the output of `Get-TraceSource`.</span></span>

## <span data-ttu-id="9dcfa-204">Ähnliche Themen</span><span class="sxs-lookup"><span data-stu-id="9dcfa-204">Related Links</span></span>

[<span data-ttu-id="9dcfa-205">Get-TraceSource</span><span class="sxs-lookup"><span data-stu-id="9dcfa-205">Get-TraceSource</span></span>](Get-TraceSource.md)

[<span data-ttu-id="9dcfa-206">Trace-Command</span><span class="sxs-lookup"><span data-stu-id="9dcfa-206">Trace-Command</span></span>](Trace-Command.md)
