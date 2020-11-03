---
description: Beschreibt, wie Funktionen, die das-Attribut angeben, `CmdletBinding` die für kompilierte Cmdlets verfügbaren Methoden und Eigenschaften verwenden können.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_functions_advanced_methods?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Functions_Advanced_Methods
ms.openlocfilehash: 3dc5118076436ddb7fface16caa01bf4fcdec257
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221620"
---
# <a name="about-functions-advanced-methods"></a><span data-ttu-id="b4a4f-104">Informationen zu erweiterten Funktionen von Functions</span><span class="sxs-lookup"><span data-stu-id="b4a4f-104">About Functions Advanced Methods</span></span>

## <a name="short-description"></a><span data-ttu-id="b4a4f-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b4a4f-105">Short description</span></span>

<span data-ttu-id="b4a4f-106">Beschreibt, wie Funktionen, die das-Attribut angeben, `CmdletBinding` die für kompilierte Cmdlets verfügbaren Methoden und Eigenschaften verwenden können.</span><span class="sxs-lookup"><span data-stu-id="b4a4f-106">Describes how functions that specify the `CmdletBinding` attribute can use the methods and properties that are available to compiled cmdlets.</span></span>

## <a name="long-description"></a><span data-ttu-id="b4a4f-107">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b4a4f-107">Long description</span></span>

<span data-ttu-id="b4a4f-108">Funktionen, die das-Attribut angeben, `CmdletBinding` können über die Variable auf eine Reihe von Methoden und Eigenschaften zugreifen `$PSCmdlet` .</span><span class="sxs-lookup"><span data-stu-id="b4a4f-108">Functions that specify the `CmdletBinding` attribute can access a number of methods and properties through the `$PSCmdlet` variable.</span></span> <span data-ttu-id="b4a4f-109">Diese Methoden umfassen die folgenden Methoden:</span><span class="sxs-lookup"><span data-stu-id="b4a4f-109">These methods include the following methods:</span></span>

- <span data-ttu-id="b4a4f-110">Eingabe Verarbeitungsmethoden, die von den kompilierten Cmdlets verwendet werden, um Ihre Arbeit zu erledigen.</span><span class="sxs-lookup"><span data-stu-id="b4a4f-110">Input-processing methods that compiled cmdlets use to do their work.</span></span>
- <span data-ttu-id="b4a4f-111">Die `ShouldProcess` -und- `ShouldContinue` Methoden, die verwendet werden, um Benutzer Feedback zu erhalten, bevor eine Aktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b4a4f-111">The `ShouldProcess` and `ShouldContinue` methods that are used to get user feedback before an action is performed.</span></span>
- <span data-ttu-id="b4a4f-112">Die `ThrowTerminatingError` Methode zum Erstellen von Fehler Datensätzen.</span><span class="sxs-lookup"><span data-stu-id="b4a4f-112">The `ThrowTerminatingError` method for generating error records.</span></span>
- <span data-ttu-id="b4a4f-113">Mehrere `Write` Methoden, die unterschiedliche Arten der Ausgabe zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="b4a4f-113">Several `Write` methods that return different types of output.</span></span>

<span data-ttu-id="b4a4f-114">Alle Methoden und Eigenschaften der **PSCmdlet** -Klasse sind für erweiterte Funktionen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b4a4f-114">All the methods and properties of the **PSCmdlet** class are available to advanced functions.</span></span> <span data-ttu-id="b4a4f-115">Weitere Informationen finden Sie unter [System. Management. Automation. PSCmdlet](/dotnet/api/system.management.automation.pscmdlet).</span><span class="sxs-lookup"><span data-stu-id="b4a4f-115">For more information, see [System.Management.Automation.PSCmdlet](/dotnet/api/system.management.automation.pscmdlet).</span></span>

<span data-ttu-id="b4a4f-116">Weitere Informationen zum- `CmdletBinding` Attribut finden Sie unter [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md).</span><span class="sxs-lookup"><span data-stu-id="b4a4f-116">For more information about the `CmdletBinding` attribute, see [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md).</span></span>
<span data-ttu-id="b4a4f-117">Informationen zur **cmdletbindingattribute** -Klasse finden Sie unter [System. Management. Automation. Cmdlet. cmdletbindingattribute](/dotnet/api/system.management.automation.cmdletbindingattribute).</span><span class="sxs-lookup"><span data-stu-id="b4a4f-117">For the **CmdletBindingAttribute** class, see [System.Management.Automation.Cmdlet.CmdletBindingAttribute](/dotnet/api/system.management.automation.cmdletbindingattribute).</span></span>

### <a name="input-processing-methods"></a><span data-ttu-id="b4a4f-118">Eingabe Verarbeitungsmethoden</span><span class="sxs-lookup"><span data-stu-id="b4a4f-118">Input processing methods</span></span>

<span data-ttu-id="b4a4f-119">Die in diesem Abschnitt beschriebenen Methoden werden als Eingabe Verarbeitungsmethoden bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="b4a4f-119">The methods described in this section are referred to as the input processing methods.</span></span> <span data-ttu-id="b4a4f-120">Für-Funktionen werden diese drei Methoden durch die `Begin` -, `Process` -und- `End` Blöcke der-Funktion dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b4a4f-120">For functions, these three methods are represented by the `Begin`, `Process`, and `End` blocks of the function.</span></span> <span data-ttu-id="b4a4f-121">Sie müssen diese Blöcke nicht in ihren Funktionen verwenden.</span><span class="sxs-lookup"><span data-stu-id="b4a4f-121">You aren't required to use any of these blocks in your functions.</span></span>

> [!NOTE]
> <span data-ttu-id="b4a4f-122">Diese Blöcke sind auch für Funktionen verfügbar, die das- `CmdletBinding` Attribut nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="b4a4f-122">These blocks are also available to functions that don't use the `CmdletBinding` attribute.</span></span>

#### <a name="begin"></a><span data-ttu-id="b4a4f-123">Starten</span><span class="sxs-lookup"><span data-stu-id="b4a4f-123">Begin</span></span>

<span data-ttu-id="b4a4f-124">Dieser Block wird verwendet, um eine optionale einmalige Vorverarbeitung für die Funktion bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="b4a4f-124">This block is used to provide optional one-time preprocessing for the function.</span></span>
<span data-ttu-id="b4a4f-125">Die PowerShell-Laufzeit verwendet den Code in diesem Block einmal für jede Instanz der Funktion in der Pipeline.</span><span class="sxs-lookup"><span data-stu-id="b4a4f-125">The PowerShell runtime uses the code in this block once for each instance of the function in the pipeline.</span></span>

#### <a name="process"></a><span data-ttu-id="b4a4f-126">Prozess</span><span class="sxs-lookup"><span data-stu-id="b4a4f-126">Process</span></span>

<span data-ttu-id="b4a4f-127">Dieser Block wird verwendet, um die Verarbeitung von Datensätzen im Datensatz für die Funktion bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="b4a4f-127">This block is used to provide record-by-record processing for the function.</span></span> <span data-ttu-id="b4a4f-128">Sie können einen- `Process` Block verwenden, ohne die anderen Blöcke zu definieren.</span><span class="sxs-lookup"><span data-stu-id="b4a4f-128">You can use a `Process` block without defining the other blocks.</span></span> <span data-ttu-id="b4a4f-129">Die Anzahl von `Process` Block Ausführungen hängt davon ab, wie Sie die Funktion verwenden und welche Eingaben die Funktion empfängt.</span><span class="sxs-lookup"><span data-stu-id="b4a4f-129">The number of `Process` block executions depends on how you use the function and what input the function receives.</span></span>

<span data-ttu-id="b4a4f-130">Die automatische Variable `$_` oder `$PSItem` enthält das aktuelle Objekt in der Pipeline für die Verwendung im- `Process` Block.</span><span class="sxs-lookup"><span data-stu-id="b4a4f-130">The automatic variable `$_` or `$PSItem` contains the current object in the pipeline for use in the `Process` block.</span></span> <span data-ttu-id="b4a4f-131">Die `$input` Automatische Variable enthält einen Enumerator, der nur für Funktionen und Skriptblöcke verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="b4a4f-131">The `$input` automatic variable contains an enumerator that's only available to functions and script blocks.</span></span>
<span data-ttu-id="b4a4f-132">Weitere Informationen finden Sie unter [about_Automatic_Variables](about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="b4a4f-132">For more information, see [about_Automatic_Variables](about_Automatic_Variables.md).</span></span>

- <span data-ttu-id="b4a4f-133">Wenn Sie die Funktion am Anfang oder außerhalb einer Pipeline aufrufen, wird der `Process` Block einmal ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b4a4f-133">Calling the function at the beginning, or outside of a pipeline, executes the `Process` block once.</span></span>
- <span data-ttu-id="b4a4f-134">Innerhalb einer Pipeline wird der- `Process` Block einmal für jedes Eingabe Objekt ausgeführt, das die-Funktion erreicht.</span><span class="sxs-lookup"><span data-stu-id="b4a4f-134">Within a pipeline, the `Process` block executes once for each input object that reaches the function.</span></span>
- <span data-ttu-id="b4a4f-135">Wenn die Pipeline Eingabe, die die Funktion erreicht, leer ist, wird der- `Process` Block **nicht** ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b4a4f-135">If the pipeline input that reaches the function is empty, the `Process` block **does not** execute.</span></span>
  - <span data-ttu-id="b4a4f-136">Die `Begin` -und- `End` Blöcke werden weiterhin ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b4a4f-136">The `Begin` and `End` blocks still execute.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b4a4f-137">Wenn ein Funktionsparameter so festgelegt ist, dass er Pipeline Eingaben annimmt, und ein- `Process` Block nicht definiert ist, schlägt die Daten Satz Weise Verarbeitung fehl.</span><span class="sxs-lookup"><span data-stu-id="b4a4f-137">If a function parameter is set to accept pipeline input, and a `Process` block isn't defined, record-by-record processing will fail.</span></span> <span data-ttu-id="b4a4f-138">In diesem Fall wird die Funktion nur einmal ausgeführt, unabhängig von der Eingabe.</span><span class="sxs-lookup"><span data-stu-id="b4a4f-138">In this case, your function will only execute once, regardless of the input.</span></span>

#### <a name="end"></a><span data-ttu-id="b4a4f-139">Ende</span><span class="sxs-lookup"><span data-stu-id="b4a4f-139">End</span></span>

<span data-ttu-id="b4a4f-140">Dieser Block wird verwendet, um eine optionale einmalige Nachbearbeitung für die Funktion bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="b4a4f-140">This block is used to provide optional one-time post-processing for the function.</span></span>

<span data-ttu-id="b4a4f-141">Das folgende Beispiel zeigt die Gliederung einer Funktion, die einen `Begin` -Block für die einmalige Vorverarbeitung, einen `Process` -Block für die Verarbeitung mehrerer Datensätze und einen-Block für die `End` einmalige Nachbearbeitung enthält.</span><span class="sxs-lookup"><span data-stu-id="b4a4f-141">The following example shows the outline of a function that contains a `Begin` block for one-time preprocessing, a `Process` block for multiple record processing, and an `End` block for one-time post-processing.</span></span>

```powershell
Function Test-ScriptCmdlet
{
[CmdletBinding(SupportsShouldProcess=$True)]
    Param ($Parameter1)
    Begin{}
    Process{}
    End{}
}
```

> [!NOTE]
> <span data-ttu-id="b4a4f-142">Die Verwendung eines- `Begin` oder- `End` Blocks erfordert, dass Sie alle drei Blöcke definieren.</span><span class="sxs-lookup"><span data-stu-id="b4a4f-142">Using either a `Begin` or `End` block requires that you define all three blocks.</span></span> <span data-ttu-id="b4a4f-143">Wenn alle drei Blöcke verwendet werden, muss sich der gesamte PowerShell-Code in einem der-Blöcke befinden.</span><span class="sxs-lookup"><span data-stu-id="b4a4f-143">When using all three blocks, all PowerShell code must be inside one of the blocks.</span></span>

### <a name="confirmation-methods"></a><span data-ttu-id="b4a4f-144">Bestätigungs Methoden</span><span class="sxs-lookup"><span data-stu-id="b4a4f-144">Confirmation methods</span></span>

#### <a name="shouldprocess"></a><span data-ttu-id="b4a4f-145">ShouldProcess</span><span class="sxs-lookup"><span data-stu-id="b4a4f-145">ShouldProcess</span></span>

<span data-ttu-id="b4a4f-146">Diese Methode wird aufgerufen, um eine Bestätigung vom Benutzer anzufordern, bevor die Funktion eine Aktion ausführt, durch die das System geändert wird.</span><span class="sxs-lookup"><span data-stu-id="b4a4f-146">This method is called to request confirmation from the user before the function performs an action that would change the system.</span></span> <span data-ttu-id="b4a4f-147">Die Funktion kann basierend auf dem booleschen Wert fortgesetzt werden, der von der-Methode zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="b4a4f-147">The function can continue based on the Boolean value returned by the method.</span></span> <span data-ttu-id="b4a4f-148">Diese Methode kann nur innerhalb des- `Process{}` Blocks der-Funktion aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="b4a4f-148">This method can only be called only from within the `Process{}` block of the function.</span></span> <span data-ttu-id="b4a4f-149">Das- `CmdletBinding` Attribut muss auch deklarieren, dass die-Funktion unterstützt `ShouldProcess` (wie im vorherigen Beispiel gezeigt).</span><span class="sxs-lookup"><span data-stu-id="b4a4f-149">The `CmdletBinding` attribute must also declare that the function supports `ShouldProcess` (as shown in the previous example).</span></span>

<span data-ttu-id="b4a4f-150">Weitere Informationen zu dieser Methode finden Sie unter " [System. Management. Automation. Cmdlet. schuldprocess](/dotnet/api/system.management.automation.cmdlet.shouldprocess)".</span><span class="sxs-lookup"><span data-stu-id="b4a4f-150">For more information about this method, see [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/system.management.automation.cmdlet.shouldprocess).</span></span>

<span data-ttu-id="b4a4f-151">Weitere Informationen zum Anfordern der Bestätigung finden Sie unter [Anfordern einer Bestätigung](/powershell/scripting/developer/cmdlet/requesting-confirmation).</span><span class="sxs-lookup"><span data-stu-id="b4a4f-151">For more information about how to request confirmation, see [Requesting Confirmation](/powershell/scripting/developer/cmdlet/requesting-confirmation).</span></span>

#### <a name="shouldcontinue"></a><span data-ttu-id="b4a4f-152">ShouldContinue</span><span class="sxs-lookup"><span data-stu-id="b4a4f-152">ShouldContinue</span></span>

<span data-ttu-id="b4a4f-153">Diese Methode wird aufgerufen, um eine zweite Bestätigungsmeldung anzufordern.</span><span class="sxs-lookup"><span data-stu-id="b4a4f-153">This method is called to request a second confirmation message.</span></span> <span data-ttu-id="b4a4f-154">Sie sollte aufgerufen werden, wenn die- `ShouldProcess` Methode zurückgibt `$true` .</span><span class="sxs-lookup"><span data-stu-id="b4a4f-154">It should be called when the `ShouldProcess` method returns `$true`.</span></span> <span data-ttu-id="b4a4f-155">Weitere Informationen zu dieser Methode finden Sie unter " [System. Management. Automation. Cmdlet. daudcontinue](/dotnet/api/system.management.automation.cmdlet.shouldcontinue)".</span><span class="sxs-lookup"><span data-stu-id="b4a4f-155">For more information about this method, see [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/system.management.automation.cmdlet.shouldcontinue).</span></span>

### <a name="error-methods"></a><span data-ttu-id="b4a4f-156">Fehler Methoden</span><span class="sxs-lookup"><span data-stu-id="b4a4f-156">Error methods</span></span>

<span data-ttu-id="b4a4f-157">Funktionen können zwei verschiedene Methoden aufzurufen, wenn Fehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="b4a4f-157">Functions can call two different methods when errors occur.</span></span> <span data-ttu-id="b4a4f-158">Wenn ein Fehler ohne Abbruch auftritt, sollte die Funktion die-Methode aufzurufen `WriteError` , die im `Write` Abschnitt Methoden beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="b4a4f-158">When a non-terminating error occurs, the function should call the `WriteError` method, which is described in the `Write` methods section.</span></span> <span data-ttu-id="b4a4f-159">Wenn ein Abbruch Fehler auftritt und die Funktion nicht fortgesetzt werden kann, sollte die-Methode aufgerufen werden `ThrowTerminatingError` .</span><span class="sxs-lookup"><span data-stu-id="b4a4f-159">When a terminating error occurs and the function can't continue, it should call the `ThrowTerminatingError` method.</span></span> <span data-ttu-id="b4a4f-160">Sie können auch die `Throw` -Anweisung verwenden, um Fehler zu beenden, und das [Write-error-](xref:Microsoft.PowerShell.Utility.Write-Error) Cmdlet für Fehler ohne Abbruch.</span><span class="sxs-lookup"><span data-stu-id="b4a4f-160">You can also use the `Throw` statement for terminating errors and the [Write-Error](xref:Microsoft.PowerShell.Utility.Write-Error) cmdlet for non-terminating errors.</span></span>

<span data-ttu-id="b4a4f-161">Weitere Informationen finden Sie unter [System. Management. Automation. Cmdlet. ThrowTerminatingError](/dotnet/api/system.management.automation.cmdlet.throwterminatingerror).</span><span class="sxs-lookup"><span data-stu-id="b4a4f-161">For more information, see [System.Management.Automation.Cmdlet.ThrowTerminatingError](/dotnet/api/system.management.automation.cmdlet.throwterminatingerror).</span></span>

### <a name="write-methods"></a><span data-ttu-id="b4a4f-162">Write-Methoden</span><span class="sxs-lookup"><span data-stu-id="b4a4f-162">Write methods</span></span>

<span data-ttu-id="b4a4f-163">Eine Funktion kann die folgenden Methoden aufzurufen, um unterschiedliche Ausgabetypen zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="b4a4f-163">A function can call the following methods to return different types of output.</span></span>
<span data-ttu-id="b4a4f-164">Beachten Sie, dass nicht die gesamte Ausgabe an den nächsten Befehl in der Pipeline weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="b4a4f-164">Notice that not all the output goes to the next command in the pipeline.</span></span> <span data-ttu-id="b4a4f-165">Sie können auch die verschiedenen `Write` Cmdlets verwenden, z `Write-Error` . b..</span><span class="sxs-lookup"><span data-stu-id="b4a4f-165">You can also use the various `Write` cmdlets, such as `Write-Error`.</span></span>

#### <a name="writecommanddetail"></a><span data-ttu-id="b4a4f-166">"Write-commanddetail"</span><span class="sxs-lookup"><span data-stu-id="b4a4f-166">WriteCommandDetail</span></span>

<span data-ttu-id="b4a4f-167">Weitere Informationen zur- `WriteCommandDetails` Methode finden Sie unter [System. Management. Automation. Cmdlet. Beschreib tecommanddetail](/dotnet/api/system.management.automation.cmdlet.writecommanddetail).</span><span class="sxs-lookup"><span data-stu-id="b4a4f-167">For information about the `WriteCommandDetails` method, see [System.Management.Automation.Cmdlet.WriteCommandDetail](/dotnet/api/system.management.automation.cmdlet.writecommanddetail).</span></span>

#### <a name="writedebug"></a><span data-ttu-id="b4a4f-168">Beschreib Debuggen</span><span class="sxs-lookup"><span data-stu-id="b4a4f-168">WriteDebug</span></span>

<span data-ttu-id="b4a4f-169">Zum Bereitstellen von Informationen, die für die Problembehandlung einer Funktion verwendet werden können, muss die Funktion die- `WriteDebug` Methode aufruft.</span><span class="sxs-lookup"><span data-stu-id="b4a4f-169">To provide information that can be used to troubleshoot a function, make the function call the `WriteDebug` method.</span></span> <span data-ttu-id="b4a4f-170">Die- `WriteDebug` Methode zeigt Debugmeldungen für den Benutzer an.</span><span class="sxs-lookup"><span data-stu-id="b4a4f-170">The `WriteDebug` method displays debug messages to the user.</span></span> <span data-ttu-id="b4a4f-171">Weitere Informationen finden Sie unter [System. Management. Automation. Cmdlet. Write-Debug](/dotnet/api/system.management.automation.cmdlet.writedebug).</span><span class="sxs-lookup"><span data-stu-id="b4a4f-171">For more information, see [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/system.management.automation.cmdlet.writedebug).</span></span>

#### <a name="writeerror"></a><span data-ttu-id="b4a4f-172">WriteError</span><span class="sxs-lookup"><span data-stu-id="b4a4f-172">WriteError</span></span>

<span data-ttu-id="b4a4f-173">Functions sollte diese Methode aufgerufen werden, wenn Fehler ohne Abbruch auftreten und die Funktion zum Fortsetzen der Verarbeitung von Datensätzen entworfen wurde.</span><span class="sxs-lookup"><span data-stu-id="b4a4f-173">Functions should call this method when non-terminating errors occur and the function is designed to continue processing records.</span></span> <span data-ttu-id="b4a4f-174">Weitere Informationen finden Sie unter [System. Management. Automation. Cmdlet. Write-error](/dotnet/api/system.management.automation.cmdlet.writeerror).</span><span class="sxs-lookup"><span data-stu-id="b4a4f-174">For more information, see [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/system.management.automation.cmdlet.writeerror).</span></span>

> [!NOTE]
> <span data-ttu-id="b4a4f-175">Wenn ein Abbruch Fehler auftritt, sollte die Funktion die [ThrowTerminatingError](/dotnet/api/system.management.automation.cmdlet.throwterminatingerror) -Methode aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="b4a4f-175">If a terminating error occurs, the function should call the [ThrowTerminatingError](/dotnet/api/system.management.automation.cmdlet.throwterminatingerror) method.</span></span>

#### <a name="writeobject"></a><span data-ttu-id="b4a4f-176">WriteObject</span><span class="sxs-lookup"><span data-stu-id="b4a4f-176">WriteObject</span></span>

<span data-ttu-id="b4a4f-177">Die- `WriteObject` Methode ermöglicht es der-Funktion, ein Objekt an den nächsten Befehl in der Pipeline zu senden.</span><span class="sxs-lookup"><span data-stu-id="b4a4f-177">The `WriteObject` method allows the function to send an object to the next command in the pipeline.</span></span> <span data-ttu-id="b4a4f-178">In den meisten Fällen `WriteObject` ist die Methode, die verwendet werden soll, wenn die Funktion Daten zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="b4a4f-178">In most cases, `WriteObject` is the method to use when the function returns data.</span></span> <span data-ttu-id="b4a4f-179">Weitere Informationen finden Sie unter [System. Management. Automation. PSCmdlet. Write Object](/dotnet/api/system.management.automation.cmdlet.writeobject).</span><span class="sxs-lookup"><span data-stu-id="b4a4f-179">For more information, see [System.Management.Automation.PSCmdlet.WriteObject](/dotnet/api/system.management.automation.cmdlet.writeobject).</span></span>

#### <a name="writeprogress"></a><span data-ttu-id="b4a4f-180">"Write Progress"</span><span class="sxs-lookup"><span data-stu-id="b4a4f-180">WriteProgress</span></span>

<span data-ttu-id="b4a4f-181">Für Funktionen mit Aktionen, deren Ausführung viel Zeit in Anspruch nimmt, ermöglicht diese Methode der-Funktion, die-Methode aufzurufen, `WriteProgress` damit Fortschrittsinformationen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b4a4f-181">For functions with actions that take a long time to complete, this method allows the function to call the `WriteProgress` method so that progress information is displayed.</span></span> <span data-ttu-id="b4a4f-182">Beispielsweise können Sie den abgeschlossenen Prozentsatz anzeigen.</span><span class="sxs-lookup"><span data-stu-id="b4a4f-182">For example, you can display the percent completed.</span></span>
<span data-ttu-id="b4a4f-183">Weitere Informationen finden Sie unter [System. Management. Automation. PSCmdlet. Write Progress](/dotnet/api/system.management.automation.cmdlet.writeprogress).</span><span class="sxs-lookup"><span data-stu-id="b4a4f-183">For more information, see [System.Management.Automation.PSCmdlet.WriteProgress](/dotnet/api/system.management.automation.cmdlet.writeprogress).</span></span>

#### <a name="writeverbose"></a><span data-ttu-id="b4a4f-184">WriteVerbose</span><span class="sxs-lookup"><span data-stu-id="b4a4f-184">WriteVerbose</span></span>

<span data-ttu-id="b4a4f-185">Um ausführliche Informationen zur Funktionsweise der Funktion bereitzustellen, müssen Sie die-Funktion aufrufen, `WriteVerbose` um dem Benutzer ausführliche Meldungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b4a4f-185">To provide detailed information about what the function is doing, make the function call the `WriteVerbose` method to display verbose messages to the user.</span></span> <span data-ttu-id="b4a4f-186">Standardmäßig werden ausführliche Meldungen nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b4a4f-186">By default, verbose messages aren't displayed.</span></span> <span data-ttu-id="b4a4f-187">Weitere Informationen finden Sie unter [System. Management. Automation. PSCmdlet. Write-Verbose](/dotnet/api/system.management.automation.cmdlet.writeverbose).</span><span class="sxs-lookup"><span data-stu-id="b4a4f-187">For more information, see [System.Management.Automation.PSCmdlet.WriteVerbose](/dotnet/api/system.management.automation.cmdlet.writeverbose).</span></span>

#### <a name="writewarning"></a><span data-ttu-id="b4a4f-188">WriteWarning</span><span class="sxs-lookup"><span data-stu-id="b4a4f-188">WriteWarning</span></span>

<span data-ttu-id="b4a4f-189">Um Informationen zu Bedingungen bereitzustellen, die möglicherweise zu unerwarteten Ergebnissen führen, rufen Sie die-Funktion auf, um dem Benutzer Warnmeldungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b4a4f-189">To provide information about conditions that may cause unexpected results, make the function call the WriteWarning method to display warning messages to the user.</span></span> <span data-ttu-id="b4a4f-190">Standardmäßig werden Warnmeldungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b4a4f-190">By default, warning messages are displayed.</span></span> <span data-ttu-id="b4a4f-191">Weitere Informationen finden Sie unter [System. Management. Automation. PSCmdlet. Write Warning](/dotnet/api/system.management.automation.cmdlet.writewarning).</span><span class="sxs-lookup"><span data-stu-id="b4a4f-191">For more information, see [System.Management.Automation.PSCmdlet.WriteWarning](/dotnet/api/system.management.automation.cmdlet.writewarning).</span></span>

> [!NOTE]
> <span data-ttu-id="b4a4f-192">Sie können auch Warnmeldungen anzeigen, indem Sie die `$WarningPreference` -Variable oder die `Verbose` `Debug` Befehlszeilenoptionen und verwenden.</span><span class="sxs-lookup"><span data-stu-id="b4a4f-192">You can also display warning messages by configuring the `$WarningPreference` variable or by using the `Verbose` and `Debug` command-line options.</span></span> <span data-ttu-id="b4a4f-193">Weitere Informationen zur- `$WarningPreference` Variablen finden Sie unter [about_Preference_Variables](about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="b4a4f-193">for more information about the `$WarningPreference` variable, see [about_Preference_Variables](about_Preference_Variables.md).</span></span>

### <a name="other-methods-and-properties"></a><span data-ttu-id="b4a4f-194">Andere Methoden und Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="b4a4f-194">Other methods and properties</span></span>

<span data-ttu-id="b4a4f-195">Informationen zu den anderen Methoden und Eigenschaften, auf die über die Variable zugegriffen werden kann `$PSCmdlet` , finden Sie unter [System. Management. Automation. PSCmdlet](/dotnet/api/system.management.automation.pscmdlet).</span><span class="sxs-lookup"><span data-stu-id="b4a4f-195">For information about the other methods and properties that can be accessed through the `$PSCmdlet` variable, see [System.Management.Automation.PSCmdlet](/dotnet/api/system.management.automation.pscmdlet).</span></span>

<span data-ttu-id="b4a4f-196">Beispielsweise können Sie mit der [parametersetname](/dotnet/api/system.management.automation.pscmdlet.parametersetname) -Eigenschaft den verwendeten Parametersatz anzeigen.</span><span class="sxs-lookup"><span data-stu-id="b4a4f-196">For example, the [ParameterSetName](/dotnet/api/system.management.automation.pscmdlet.parametersetname) property allows you to see the parameter set that is being used.</span></span> <span data-ttu-id="b4a4f-197">Mithilfe von Parametersätzen können Sie eine Funktion erstellen, die basierend auf den Parametern, die beim Ausführen der Funktion angegeben werden, verschiedene Aufgaben ausführt.</span><span class="sxs-lookup"><span data-stu-id="b4a4f-197">Parameter sets allow you to create a function that performs different tasks based on the parameters that are specified when the function is run.</span></span>

## <a name="see-also"></a><span data-ttu-id="b4a4f-198">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="b4a4f-198">See also</span></span>

[<span data-ttu-id="b4a4f-199">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="b4a4f-199">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="b4a4f-200">about_Functions</span><span class="sxs-lookup"><span data-stu-id="b4a4f-200">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="b4a4f-201">about_Functions_Advanced</span><span class="sxs-lookup"><span data-stu-id="b4a4f-201">about_Functions_Advanced</span></span>](about_Functions_Advanced.md)

[<span data-ttu-id="b4a4f-202">about_Functions_Advanced_Parameters</span><span class="sxs-lookup"><span data-stu-id="b4a4f-202">about_Functions_Advanced_Parameters</span></span>](about_Functions_Advanced_Parameters.md)

[<span data-ttu-id="b4a4f-203">about_Functions_CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="b4a4f-203">about_Functions_CmdletBindingAttribute</span></span>](about_Functions_CmdletBindingAttribute.md)

[<span data-ttu-id="b4a4f-204">about_Functions_OutputTypeAttribute</span><span class="sxs-lookup"><span data-stu-id="b4a4f-204">about_Functions_OutputTypeAttribute</span></span>](about_Functions_OutputTypeAttribute.md)

[<span data-ttu-id="b4a4f-205">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="b4a4f-205">about_Preference_Variables</span></span>](about_Preference_Variables.md)
