---
description: Beschreibt, wie Funktionen, die das-Attribut angeben, `CmdletBinding` die für kompilierte Cmdlets verfügbaren Methoden und Eigenschaften verwenden können.
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_functions_advanced_methods?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Functions_Advanced_Methods
ms.openlocfilehash: 13a9d7258f1a52d5fcbb2d8c55b91c8d6454452d
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599648"
---
# <a name="about-functions-advanced-methods"></a><span data-ttu-id="bce8b-103">Informationen zu erweiterten Funktionen von Functions</span><span class="sxs-lookup"><span data-stu-id="bce8b-103">About Functions Advanced Methods</span></span>

## <a name="short-description"></a><span data-ttu-id="bce8b-104">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bce8b-104">Short description</span></span>

<span data-ttu-id="bce8b-105">Beschreibt, wie Funktionen, die das-Attribut angeben, `CmdletBinding` die für kompilierte Cmdlets verfügbaren Methoden und Eigenschaften verwenden können.</span><span class="sxs-lookup"><span data-stu-id="bce8b-105">Describes how functions that specify the `CmdletBinding` attribute can use the methods and properties that are available to compiled cmdlets.</span></span>

## <a name="long-description"></a><span data-ttu-id="bce8b-106">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bce8b-106">Long description</span></span>

<span data-ttu-id="bce8b-107">Funktionen, die das-Attribut angeben, `CmdletBinding` können über die Variable auf eine Reihe von Methoden und Eigenschaften zugreifen `$PSCmdlet` .</span><span class="sxs-lookup"><span data-stu-id="bce8b-107">Functions that specify the `CmdletBinding` attribute can access a number of methods and properties through the `$PSCmdlet` variable.</span></span> <span data-ttu-id="bce8b-108">Diese Methoden umfassen die folgenden Methoden:</span><span class="sxs-lookup"><span data-stu-id="bce8b-108">These methods include the following methods:</span></span>

- <span data-ttu-id="bce8b-109">Eingabe Verarbeitungsmethoden, die von den kompilierten Cmdlets verwendet werden, um Ihre Arbeit zu erledigen.</span><span class="sxs-lookup"><span data-stu-id="bce8b-109">Input-processing methods that compiled cmdlets use to do their work.</span></span>
- <span data-ttu-id="bce8b-110">Die `ShouldProcess` -und- `ShouldContinue` Methoden, die verwendet werden, um Benutzer Feedback zu erhalten, bevor eine Aktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="bce8b-110">The `ShouldProcess` and `ShouldContinue` methods that are used to get user feedback before an action is performed.</span></span>
- <span data-ttu-id="bce8b-111">Die `ThrowTerminatingError` Methode zum Erstellen von Fehler Datensätzen.</span><span class="sxs-lookup"><span data-stu-id="bce8b-111">The `ThrowTerminatingError` method for generating error records.</span></span>
- <span data-ttu-id="bce8b-112">Mehrere `Write` Methoden, die unterschiedliche Arten der Ausgabe zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="bce8b-112">Several `Write` methods that return different types of output.</span></span>

<span data-ttu-id="bce8b-113">Alle Methoden und Eigenschaften der **PSCmdlet** -Klasse sind für erweiterte Funktionen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="bce8b-113">All the methods and properties of the **PSCmdlet** class are available to advanced functions.</span></span> <span data-ttu-id="bce8b-114">Weitere Informationen finden Sie unter [System. Management. Automation. PSCmdlet](/dotnet/api/system.management.automation.pscmdlet).</span><span class="sxs-lookup"><span data-stu-id="bce8b-114">For more information, see [System.Management.Automation.PSCmdlet](/dotnet/api/system.management.automation.pscmdlet).</span></span>

<span data-ttu-id="bce8b-115">Weitere Informationen zum- `CmdletBinding` Attribut finden Sie unter [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md).</span><span class="sxs-lookup"><span data-stu-id="bce8b-115">For more information about the `CmdletBinding` attribute, see [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md).</span></span>
<span data-ttu-id="bce8b-116">Informationen zur **cmdletbindingattribute** -Klasse finden Sie unter [System. Management. Automation. Cmdlet. cmdletbindingattribute](/dotnet/api/system.management.automation.cmdletbindingattribute).</span><span class="sxs-lookup"><span data-stu-id="bce8b-116">For the **CmdletBindingAttribute** class, see [System.Management.Automation.Cmdlet.CmdletBindingAttribute](/dotnet/api/system.management.automation.cmdletbindingattribute).</span></span>

### <a name="input-processing-methods"></a><span data-ttu-id="bce8b-117">Eingabe Verarbeitungsmethoden</span><span class="sxs-lookup"><span data-stu-id="bce8b-117">Input processing methods</span></span>

<span data-ttu-id="bce8b-118">Die in diesem Abschnitt beschriebenen Methoden werden als Eingabe Verarbeitungsmethoden bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="bce8b-118">The methods described in this section are referred to as the input processing methods.</span></span> <span data-ttu-id="bce8b-119">Für-Funktionen werden diese drei Methoden durch die `Begin` -, `Process` -und- `End` Blöcke der-Funktion dargestellt.</span><span class="sxs-lookup"><span data-stu-id="bce8b-119">For functions, these three methods are represented by the `Begin`, `Process`, and `End` blocks of the function.</span></span> <span data-ttu-id="bce8b-120">Sie müssen diese Blöcke nicht in ihren Funktionen verwenden.</span><span class="sxs-lookup"><span data-stu-id="bce8b-120">You aren't required to use any of these blocks in your functions.</span></span>

> [!NOTE]
> <span data-ttu-id="bce8b-121">Diese Blöcke sind auch für Funktionen verfügbar, die das- `CmdletBinding` Attribut nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="bce8b-121">These blocks are also available to functions that don't use the `CmdletBinding` attribute.</span></span>

#### <a name="begin"></a><span data-ttu-id="bce8b-122">Starten</span><span class="sxs-lookup"><span data-stu-id="bce8b-122">Begin</span></span>

<span data-ttu-id="bce8b-123">Dieser Block wird verwendet, um eine optionale einmalige Vorverarbeitung für die Funktion bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="bce8b-123">This block is used to provide optional one-time preprocessing for the function.</span></span>
<span data-ttu-id="bce8b-124">Die PowerShell-Laufzeit verwendet den Code in diesem Block einmal für jede Instanz der Funktion in der Pipeline.</span><span class="sxs-lookup"><span data-stu-id="bce8b-124">The PowerShell runtime uses the code in this block once for each instance of the function in the pipeline.</span></span>

#### <a name="process"></a><span data-ttu-id="bce8b-125">Prozess</span><span class="sxs-lookup"><span data-stu-id="bce8b-125">Process</span></span>

<span data-ttu-id="bce8b-126">Dieser Block wird verwendet, um die Verarbeitung von Datensätzen im Datensatz für die Funktion bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="bce8b-126">This block is used to provide record-by-record processing for the function.</span></span> <span data-ttu-id="bce8b-127">Sie können einen- `Process` Block verwenden, ohne die anderen Blöcke zu definieren.</span><span class="sxs-lookup"><span data-stu-id="bce8b-127">You can use a `Process` block without defining the other blocks.</span></span> <span data-ttu-id="bce8b-128">Die Anzahl von `Process` Block Ausführungen hängt davon ab, wie Sie die Funktion verwenden und welche Eingaben die Funktion empfängt.</span><span class="sxs-lookup"><span data-stu-id="bce8b-128">The number of `Process` block executions depends on how you use the function and what input the function receives.</span></span>

<span data-ttu-id="bce8b-129">Die automatische Variable `$_` oder `$PSItem` enthält das aktuelle Objekt in der Pipeline für die Verwendung im- `Process` Block.</span><span class="sxs-lookup"><span data-stu-id="bce8b-129">The automatic variable `$_` or `$PSItem` contains the current object in the pipeline for use in the `Process` block.</span></span> <span data-ttu-id="bce8b-130">Die `$input` Automatische Variable enthält einen Enumerator, der nur für Funktionen und Skriptblöcke verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="bce8b-130">The `$input` automatic variable contains an enumerator that's only available to functions and script blocks.</span></span>
<span data-ttu-id="bce8b-131">Weitere Informationen finden Sie unter [about_Automatic_Variables](about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="bce8b-131">For more information, see [about_Automatic_Variables](about_Automatic_Variables.md).</span></span>

- <span data-ttu-id="bce8b-132">Wenn Sie die Funktion am Anfang oder außerhalb einer Pipeline aufrufen, wird der `Process` Block einmal ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="bce8b-132">Calling the function at the beginning, or outside of a pipeline, executes the `Process` block once.</span></span>
- <span data-ttu-id="bce8b-133">Innerhalb einer Pipeline wird der- `Process` Block einmal für jedes Eingabe Objekt ausgeführt, das die-Funktion erreicht.</span><span class="sxs-lookup"><span data-stu-id="bce8b-133">Within a pipeline, the `Process` block executes once for each input object that reaches the function.</span></span>
- <span data-ttu-id="bce8b-134">Wenn die Pipeline Eingabe, die die Funktion erreicht, leer ist, wird der- `Process` Block **nicht** ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="bce8b-134">If the pipeline input that reaches the function is empty, the `Process` block **does not** execute.</span></span>
  - <span data-ttu-id="bce8b-135">Die `Begin` -und- `End` Blöcke werden weiterhin ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="bce8b-135">The `Begin` and `End` blocks still execute.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bce8b-136">Wenn ein Funktionsparameter so festgelegt ist, dass er Pipeline Eingaben annimmt, und ein- `Process` Block nicht definiert ist, schlägt die Daten Satz Weise Verarbeitung fehl.</span><span class="sxs-lookup"><span data-stu-id="bce8b-136">If a function parameter is set to accept pipeline input, and a `Process` block isn't defined, record-by-record processing will fail.</span></span> <span data-ttu-id="bce8b-137">In diesem Fall wird die Funktion nur einmal ausgeführt, unabhängig von der Eingabe.</span><span class="sxs-lookup"><span data-stu-id="bce8b-137">In this case, your function will only execute once, regardless of the input.</span></span>

#### <a name="end"></a><span data-ttu-id="bce8b-138">Ende</span><span class="sxs-lookup"><span data-stu-id="bce8b-138">End</span></span>

<span data-ttu-id="bce8b-139">Dieser Block wird verwendet, um eine optionale einmalige Nachbearbeitung für die Funktion bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="bce8b-139">This block is used to provide optional one-time post-processing for the function.</span></span>

<span data-ttu-id="bce8b-140">Das folgende Beispiel zeigt die Gliederung einer Funktion, die einen `Begin` -Block für die einmalige Vorverarbeitung, einen `Process` -Block für die Verarbeitung mehrerer Datensätze und einen-Block für die `End` einmalige Nachbearbeitung enthält.</span><span class="sxs-lookup"><span data-stu-id="bce8b-140">The following example shows the outline of a function that contains a `Begin` block for one-time preprocessing, a `Process` block for multiple record processing, and an `End` block for one-time post-processing.</span></span>

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
> <span data-ttu-id="bce8b-141">Die Verwendung eines- `Begin` oder- `End` Blocks erfordert, dass Sie alle drei Blöcke definieren.</span><span class="sxs-lookup"><span data-stu-id="bce8b-141">Using either a `Begin` or `End` block requires that you define all three blocks.</span></span> <span data-ttu-id="bce8b-142">Wenn alle drei Blöcke verwendet werden, muss sich der gesamte PowerShell-Code in einem der-Blöcke befinden.</span><span class="sxs-lookup"><span data-stu-id="bce8b-142">When using all three blocks, all PowerShell code must be inside one of the blocks.</span></span>

### <a name="confirmation-methods"></a><span data-ttu-id="bce8b-143">Bestätigungs Methoden</span><span class="sxs-lookup"><span data-stu-id="bce8b-143">Confirmation methods</span></span>

#### <a name="shouldprocess"></a><span data-ttu-id="bce8b-144">ShouldProcess</span><span class="sxs-lookup"><span data-stu-id="bce8b-144">ShouldProcess</span></span>

<span data-ttu-id="bce8b-145">Diese Methode wird aufgerufen, um eine Bestätigung vom Benutzer anzufordern, bevor die Funktion eine Aktion ausführt, durch die das System geändert wird.</span><span class="sxs-lookup"><span data-stu-id="bce8b-145">This method is called to request confirmation from the user before the function performs an action that would change the system.</span></span> <span data-ttu-id="bce8b-146">Die Funktion kann basierend auf dem booleschen Wert fortgesetzt werden, der von der-Methode zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="bce8b-146">The function can continue based on the Boolean value returned by the method.</span></span> <span data-ttu-id="bce8b-147">Diese Methode kann nur innerhalb des- `Process{}` Blocks der-Funktion aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="bce8b-147">This method can only be called only from within the `Process{}` block of the function.</span></span> <span data-ttu-id="bce8b-148">Das- `CmdletBinding` Attribut muss auch deklarieren, dass die-Funktion unterstützt `ShouldProcess` (wie im vorherigen Beispiel gezeigt).</span><span class="sxs-lookup"><span data-stu-id="bce8b-148">The `CmdletBinding` attribute must also declare that the function supports `ShouldProcess` (as shown in the previous example).</span></span>

<span data-ttu-id="bce8b-149">Weitere Informationen zu dieser Methode finden Sie unter " [System. Management. Automation. Cmdlet. schuldprocess](/dotnet/api/system.management.automation.cmdlet.shouldprocess)".</span><span class="sxs-lookup"><span data-stu-id="bce8b-149">For more information about this method, see [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/system.management.automation.cmdlet.shouldprocess).</span></span>

<span data-ttu-id="bce8b-150">Weitere Informationen zum Anfordern der Bestätigung finden Sie unter [Anfordern einer Bestätigung](/powershell/scripting/developer/cmdlet/requesting-confirmation).</span><span class="sxs-lookup"><span data-stu-id="bce8b-150">For more information about how to request confirmation, see [Requesting Confirmation](/powershell/scripting/developer/cmdlet/requesting-confirmation).</span></span>

#### <a name="shouldcontinue"></a><span data-ttu-id="bce8b-151">ShouldContinue</span><span class="sxs-lookup"><span data-stu-id="bce8b-151">ShouldContinue</span></span>

<span data-ttu-id="bce8b-152">Diese Methode wird aufgerufen, um eine zweite Bestätigungsmeldung anzufordern.</span><span class="sxs-lookup"><span data-stu-id="bce8b-152">This method is called to request a second confirmation message.</span></span> <span data-ttu-id="bce8b-153">Sie sollte aufgerufen werden, wenn die- `ShouldProcess` Methode zurückgibt `$true` .</span><span class="sxs-lookup"><span data-stu-id="bce8b-153">It should be called when the `ShouldProcess` method returns `$true`.</span></span> <span data-ttu-id="bce8b-154">Weitere Informationen zu dieser Methode finden Sie unter " [System. Management. Automation. Cmdlet. daudcontinue](/dotnet/api/system.management.automation.cmdlet.shouldcontinue)".</span><span class="sxs-lookup"><span data-stu-id="bce8b-154">For more information about this method, see [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/system.management.automation.cmdlet.shouldcontinue).</span></span>

### <a name="error-methods"></a><span data-ttu-id="bce8b-155">Fehler Methoden</span><span class="sxs-lookup"><span data-stu-id="bce8b-155">Error methods</span></span>

<span data-ttu-id="bce8b-156">Funktionen können zwei verschiedene Methoden aufzurufen, wenn Fehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="bce8b-156">Functions can call two different methods when errors occur.</span></span> <span data-ttu-id="bce8b-157">Wenn ein Fehler ohne Abbruch auftritt, sollte die Funktion die-Methode aufzurufen `WriteError` , die im `Write` Abschnitt Methoden beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="bce8b-157">When a non-terminating error occurs, the function should call the `WriteError` method, which is described in the `Write` methods section.</span></span> <span data-ttu-id="bce8b-158">Wenn ein Abbruch Fehler auftritt und die Funktion nicht fortgesetzt werden kann, sollte die-Methode aufgerufen werden `ThrowTerminatingError` .</span><span class="sxs-lookup"><span data-stu-id="bce8b-158">When a terminating error occurs and the function can't continue, it should call the `ThrowTerminatingError` method.</span></span> <span data-ttu-id="bce8b-159">Sie können auch die `Throw` -Anweisung verwenden, um Fehler zu beenden, und das [Write-error-](xref:Microsoft.PowerShell.Utility.Write-Error) Cmdlet für Fehler ohne Abbruch.</span><span class="sxs-lookup"><span data-stu-id="bce8b-159">You can also use the `Throw` statement for terminating errors and the [Write-Error](xref:Microsoft.PowerShell.Utility.Write-Error) cmdlet for non-terminating errors.</span></span>

<span data-ttu-id="bce8b-160">Weitere Informationen finden Sie unter [System. Management. Automation. Cmdlet. ThrowTerminatingError](/dotnet/api/system.management.automation.cmdlet.throwterminatingerror).</span><span class="sxs-lookup"><span data-stu-id="bce8b-160">For more information, see [System.Management.Automation.Cmdlet.ThrowTerminatingError](/dotnet/api/system.management.automation.cmdlet.throwterminatingerror).</span></span>

### <a name="write-methods"></a><span data-ttu-id="bce8b-161">Write-Methoden</span><span class="sxs-lookup"><span data-stu-id="bce8b-161">Write methods</span></span>

<span data-ttu-id="bce8b-162">Eine Funktion kann die folgenden Methoden aufzurufen, um unterschiedliche Ausgabetypen zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="bce8b-162">A function can call the following methods to return different types of output.</span></span>
<span data-ttu-id="bce8b-163">Beachten Sie, dass nicht die gesamte Ausgabe an den nächsten Befehl in der Pipeline weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="bce8b-163">Notice that not all the output goes to the next command in the pipeline.</span></span> <span data-ttu-id="bce8b-164">Sie können auch die verschiedenen `Write` Cmdlets verwenden, z `Write-Error` . b..</span><span class="sxs-lookup"><span data-stu-id="bce8b-164">You can also use the various `Write` cmdlets, such as `Write-Error`.</span></span>

#### <a name="writecommanddetail"></a><span data-ttu-id="bce8b-165">"Write-commanddetail"</span><span class="sxs-lookup"><span data-stu-id="bce8b-165">WriteCommandDetail</span></span>

<span data-ttu-id="bce8b-166">Weitere Informationen zur- `WriteCommandDetails` Methode finden Sie unter [System. Management. Automation. Cmdlet. Beschreib tecommanddetail](/dotnet/api/system.management.automation.cmdlet.writecommanddetail).</span><span class="sxs-lookup"><span data-stu-id="bce8b-166">For information about the `WriteCommandDetails` method, see [System.Management.Automation.Cmdlet.WriteCommandDetail](/dotnet/api/system.management.automation.cmdlet.writecommanddetail).</span></span>

#### <a name="writedebug"></a><span data-ttu-id="bce8b-167">Beschreib Debuggen</span><span class="sxs-lookup"><span data-stu-id="bce8b-167">WriteDebug</span></span>

<span data-ttu-id="bce8b-168">Zum Bereitstellen von Informationen, die für die Problembehandlung einer Funktion verwendet werden können, muss die Funktion die- `WriteDebug` Methode aufruft.</span><span class="sxs-lookup"><span data-stu-id="bce8b-168">To provide information that can be used to troubleshoot a function, make the function call the `WriteDebug` method.</span></span> <span data-ttu-id="bce8b-169">Die- `WriteDebug` Methode zeigt Debugmeldungen für den Benutzer an.</span><span class="sxs-lookup"><span data-stu-id="bce8b-169">The `WriteDebug` method displays debug messages to the user.</span></span> <span data-ttu-id="bce8b-170">Weitere Informationen finden Sie unter [System. Management. Automation. Cmdlet. Write-Debug](/dotnet/api/system.management.automation.cmdlet.writedebug).</span><span class="sxs-lookup"><span data-stu-id="bce8b-170">For more information, see [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/system.management.automation.cmdlet.writedebug).</span></span>

#### <a name="writeerror"></a><span data-ttu-id="bce8b-171">WriteError</span><span class="sxs-lookup"><span data-stu-id="bce8b-171">WriteError</span></span>

<span data-ttu-id="bce8b-172">Functions sollte diese Methode aufgerufen werden, wenn Fehler ohne Abbruch auftreten und die Funktion zum Fortsetzen der Verarbeitung von Datensätzen entworfen wurde.</span><span class="sxs-lookup"><span data-stu-id="bce8b-172">Functions should call this method when non-terminating errors occur and the function is designed to continue processing records.</span></span> <span data-ttu-id="bce8b-173">Weitere Informationen finden Sie unter [System. Management. Automation. Cmdlet. Write-error](/dotnet/api/system.management.automation.cmdlet.writeerror).</span><span class="sxs-lookup"><span data-stu-id="bce8b-173">For more information, see [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/system.management.automation.cmdlet.writeerror).</span></span>

> [!NOTE]
> <span data-ttu-id="bce8b-174">Wenn ein Abbruch Fehler auftritt, sollte die Funktion die [ThrowTerminatingError](/dotnet/api/system.management.automation.cmdlet.throwterminatingerror) -Methode aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="bce8b-174">If a terminating error occurs, the function should call the [ThrowTerminatingError](/dotnet/api/system.management.automation.cmdlet.throwterminatingerror) method.</span></span>

#### <a name="writeobject"></a><span data-ttu-id="bce8b-175">WriteObject</span><span class="sxs-lookup"><span data-stu-id="bce8b-175">WriteObject</span></span>

<span data-ttu-id="bce8b-176">Die- `WriteObject` Methode ermöglicht es der-Funktion, ein Objekt an den nächsten Befehl in der Pipeline zu senden.</span><span class="sxs-lookup"><span data-stu-id="bce8b-176">The `WriteObject` method allows the function to send an object to the next command in the pipeline.</span></span> <span data-ttu-id="bce8b-177">In den meisten Fällen `WriteObject` ist die Methode, die verwendet werden soll, wenn die Funktion Daten zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="bce8b-177">In most cases, `WriteObject` is the method to use when the function returns data.</span></span> <span data-ttu-id="bce8b-178">Weitere Informationen finden Sie unter [System. Management. Automation. PSCmdlet. Write Object](/dotnet/api/system.management.automation.cmdlet.writeobject).</span><span class="sxs-lookup"><span data-stu-id="bce8b-178">For more information, see [System.Management.Automation.PSCmdlet.WriteObject](/dotnet/api/system.management.automation.cmdlet.writeobject).</span></span>

#### <a name="writeprogress"></a><span data-ttu-id="bce8b-179">"Write Progress"</span><span class="sxs-lookup"><span data-stu-id="bce8b-179">WriteProgress</span></span>

<span data-ttu-id="bce8b-180">Für Funktionen mit Aktionen, deren Ausführung viel Zeit in Anspruch nimmt, ermöglicht diese Methode der-Funktion, die-Methode aufzurufen, `WriteProgress` damit Fortschrittsinformationen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="bce8b-180">For functions with actions that take a long time to complete, this method allows the function to call the `WriteProgress` method so that progress information is displayed.</span></span> <span data-ttu-id="bce8b-181">Beispielsweise können Sie den abgeschlossenen Prozentsatz anzeigen.</span><span class="sxs-lookup"><span data-stu-id="bce8b-181">For example, you can display the percent completed.</span></span>
<span data-ttu-id="bce8b-182">Weitere Informationen finden Sie unter [System. Management. Automation. PSCmdlet. Write Progress](/dotnet/api/system.management.automation.cmdlet.writeprogress).</span><span class="sxs-lookup"><span data-stu-id="bce8b-182">For more information, see [System.Management.Automation.PSCmdlet.WriteProgress](/dotnet/api/system.management.automation.cmdlet.writeprogress).</span></span>

#### <a name="writeverbose"></a><span data-ttu-id="bce8b-183">WriteVerbose</span><span class="sxs-lookup"><span data-stu-id="bce8b-183">WriteVerbose</span></span>

<span data-ttu-id="bce8b-184">Um ausführliche Informationen zur Funktionsweise der Funktion bereitzustellen, müssen Sie die-Funktion aufrufen, `WriteVerbose` um dem Benutzer ausführliche Meldungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="bce8b-184">To provide detailed information about what the function is doing, make the function call the `WriteVerbose` method to display verbose messages to the user.</span></span> <span data-ttu-id="bce8b-185">Standardmäßig werden ausführliche Meldungen nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bce8b-185">By default, verbose messages aren't displayed.</span></span> <span data-ttu-id="bce8b-186">Weitere Informationen finden Sie unter [System. Management. Automation. PSCmdlet. Write-Verbose](/dotnet/api/system.management.automation.cmdlet.writeverbose).</span><span class="sxs-lookup"><span data-stu-id="bce8b-186">For more information, see [System.Management.Automation.PSCmdlet.WriteVerbose](/dotnet/api/system.management.automation.cmdlet.writeverbose).</span></span>

#### <a name="writewarning"></a><span data-ttu-id="bce8b-187">WriteWarning</span><span class="sxs-lookup"><span data-stu-id="bce8b-187">WriteWarning</span></span>

<span data-ttu-id="bce8b-188">Um Informationen zu Bedingungen bereitzustellen, die möglicherweise zu unerwarteten Ergebnissen führen, rufen Sie die-Funktion auf, um dem Benutzer Warnmeldungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="bce8b-188">To provide information about conditions that may cause unexpected results, make the function call the WriteWarning method to display warning messages to the user.</span></span> <span data-ttu-id="bce8b-189">Standardmäßig werden Warnmeldungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bce8b-189">By default, warning messages are displayed.</span></span> <span data-ttu-id="bce8b-190">Weitere Informationen finden Sie unter [System. Management. Automation. PSCmdlet. Write Warning](/dotnet/api/system.management.automation.cmdlet.writewarning).</span><span class="sxs-lookup"><span data-stu-id="bce8b-190">For more information, see [System.Management.Automation.PSCmdlet.WriteWarning](/dotnet/api/system.management.automation.cmdlet.writewarning).</span></span>

> [!NOTE]
> <span data-ttu-id="bce8b-191">Sie können auch Warnmeldungen anzeigen, indem Sie die `$WarningPreference` -Variable oder die `Verbose` `Debug` Befehlszeilenoptionen und verwenden.</span><span class="sxs-lookup"><span data-stu-id="bce8b-191">You can also display warning messages by configuring the `$WarningPreference` variable or by using the `Verbose` and `Debug` command-line options.</span></span> <span data-ttu-id="bce8b-192">Weitere Informationen zur- `$WarningPreference` Variablen finden Sie unter [about_Preference_Variables](about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="bce8b-192">for more information about the `$WarningPreference` variable, see [about_Preference_Variables](about_Preference_Variables.md).</span></span>

### <a name="other-methods-and-properties"></a><span data-ttu-id="bce8b-193">Andere Methoden und Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="bce8b-193">Other methods and properties</span></span>

<span data-ttu-id="bce8b-194">Informationen zu den anderen Methoden und Eigenschaften, auf die über die Variable zugegriffen werden kann `$PSCmdlet` , finden Sie unter [System. Management. Automation. PSCmdlet](/dotnet/api/system.management.automation.pscmdlet).</span><span class="sxs-lookup"><span data-stu-id="bce8b-194">For information about the other methods and properties that can be accessed through the `$PSCmdlet` variable, see [System.Management.Automation.PSCmdlet](/dotnet/api/system.management.automation.pscmdlet).</span></span>

<span data-ttu-id="bce8b-195">Beispielsweise können Sie mit der [parametersetname](/dotnet/api/system.management.automation.pscmdlet.parametersetname) -Eigenschaft den verwendeten Parametersatz anzeigen.</span><span class="sxs-lookup"><span data-stu-id="bce8b-195">For example, the [ParameterSetName](/dotnet/api/system.management.automation.pscmdlet.parametersetname) property allows you to see the parameter set that is being used.</span></span> <span data-ttu-id="bce8b-196">Mithilfe von Parametersätzen können Sie eine Funktion erstellen, die basierend auf den Parametern, die beim Ausführen der Funktion angegeben werden, verschiedene Aufgaben ausführt.</span><span class="sxs-lookup"><span data-stu-id="bce8b-196">Parameter sets allow you to create a function that performs different tasks based on the parameters that are specified when the function is run.</span></span>

## <a name="see-also"></a><span data-ttu-id="bce8b-197">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bce8b-197">See also</span></span>

[<span data-ttu-id="bce8b-198">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="bce8b-198">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="bce8b-199">about_Functions</span><span class="sxs-lookup"><span data-stu-id="bce8b-199">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="bce8b-200">about_Functions_Advanced</span><span class="sxs-lookup"><span data-stu-id="bce8b-200">about_Functions_Advanced</span></span>](about_Functions_Advanced.md)

[<span data-ttu-id="bce8b-201">about_Functions_Advanced_Parameters</span><span class="sxs-lookup"><span data-stu-id="bce8b-201">about_Functions_Advanced_Parameters</span></span>](about_Functions_Advanced_Parameters.md)

[<span data-ttu-id="bce8b-202">about_Functions_CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="bce8b-202">about_Functions_CmdletBindingAttribute</span></span>](about_Functions_CmdletBindingAttribute.md)

[<span data-ttu-id="bce8b-203">about_Functions_OutputTypeAttribute</span><span class="sxs-lookup"><span data-stu-id="bce8b-203">about_Functions_OutputTypeAttribute</span></span>](about_Functions_OutputTypeAttribute.md)

[<span data-ttu-id="bce8b-204">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="bce8b-204">about_Preference_Variables</span></span>](about_Preference_Variables.md)

