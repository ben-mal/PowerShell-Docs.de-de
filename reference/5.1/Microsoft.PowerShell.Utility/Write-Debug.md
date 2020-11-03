---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-debug?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Debug
ms.openlocfilehash: 7e622367f1753fc15bed26fe083e9f343fd82b85
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "93224348"
---
# <span data-ttu-id="9ac04-103">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="9ac04-103">Write-Debug</span></span>

## <span data-ttu-id="9ac04-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="9ac04-104">SYNOPSIS</span></span>
<span data-ttu-id="9ac04-105">Schreibt eine Debugmeldung in die Konsole.</span><span class="sxs-lookup"><span data-stu-id="9ac04-105">Writes a debug message to the console.</span></span>

## <span data-ttu-id="9ac04-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9ac04-106">SYNTAX</span></span>

```
Write-Debug [-Message] <String> [<CommonParameters>]
```

## <span data-ttu-id="9ac04-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9ac04-107">DESCRIPTION</span></span>

<span data-ttu-id="9ac04-108">Das `Write-Debug` Cmdlet schreibt Debugmeldungen aus einem Skript oder Befehl in den Host.</span><span class="sxs-lookup"><span data-stu-id="9ac04-108">The `Write-Debug` cmdlet writes debug messages to the host from a script or command.</span></span>

<span data-ttu-id="9ac04-109">Standardmäßig werden Debugmeldungen nicht in der-Konsole angezeigt, Sie können Sie jedoch mit dem **Debug** -Parameter oder der- `$DebugPreference` Variablen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="9ac04-109">By default, debug messages are not displayed in the console, but you can display them by using the **Debug** parameter or the `$DebugPreference` variable.</span></span>

## <span data-ttu-id="9ac04-110">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="9ac04-110">EXAMPLES</span></span>

### <span data-ttu-id="9ac04-111">Beispiel 1: verstehen $DebugPreference</span><span class="sxs-lookup"><span data-stu-id="9ac04-111">Example 1: Understand $DebugPreference</span></span>

<span data-ttu-id="9ac04-112">In diesem Beispiel wird eine Debugmeldung geschrieben.</span><span class="sxs-lookup"><span data-stu-id="9ac04-112">This example writes a debug message.</span></span>

```powershell
Write-Debug "Cannot open file."
```

<span data-ttu-id="9ac04-113">Der Standardwert von `$DebugPreference` ist **SilentlyContinue** .</span><span class="sxs-lookup"><span data-stu-id="9ac04-113">The default value of `$DebugPreference` is **SilentlyContinue** .</span></span> <span data-ttu-id="9ac04-114">Daher wird die Meldung nicht in der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9ac04-114">Therefore, the message is not displayed in the console.</span></span>

### <span data-ttu-id="9ac04-115">Beispiel 2: Ändern des Werts von $DebugPreference</span><span class="sxs-lookup"><span data-stu-id="9ac04-115">Example 2: Change the value of $DebugPreference</span></span>

<span data-ttu-id="9ac04-116">Dieses Beispiel zeigt die Auswirkung der Änderung des Werts der `$DebugPreference` Variablen.</span><span class="sxs-lookup"><span data-stu-id="9ac04-116">This example shows the effect of changing the value of the `$DebugPreference` variable.</span></span> <span data-ttu-id="9ac04-117">Zuerst wird der aktuelle Wert von angezeigt, `$DebugPreference` und es wird versucht, eine Debugmeldung zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="9ac04-117">First, we display the current value of `$DebugPreference` and attempt to write a debug message.</span></span> <span data-ttu-id="9ac04-118">Anschließend ändern wir den Wert von `$DebugPreference` , um **fortzufahren** . Dadurch können Debugmeldungen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="9ac04-118">Then we change the value of `$DebugPreference` to **Continue** , which allows debug messages to be displayed.</span></span>

```
PS> $DebugPreference
SilentlyContinue
PS> Write-Debug "Cannot open file."
PS>
PS> $DebugPreference = "Continue"
PS> Write-Debug "Cannot open file."
DEBUG: Cannot open file.
```

<span data-ttu-id="9ac04-119">Weitere Informationen zu `$DebugPreference` finden Sie unter [about_Preference_Variables](/powershell/module/Microsoft.PowerShell.Core/About/about_Preference_Variables).</span><span class="sxs-lookup"><span data-stu-id="9ac04-119">For more information about `$DebugPreference`, see [about_Preference_Variables](/powershell/module/Microsoft.PowerShell.Core/About/about_Preference_Variables).</span></span>

### <span data-ttu-id="9ac04-120">Beispiel 3: Verwenden des Debug-Parameters zum Überschreiben von $DebugPreference</span><span class="sxs-lookup"><span data-stu-id="9ac04-120">Example 3: Use the Debug parameter to override $DebugPreference</span></span>

<span data-ttu-id="9ac04-121">Die `Test-Debug` -Funktion schreibt den Wert der `$DebugPreference` Variablen in den PowerShell-Host und den debugdatenstrom.</span><span class="sxs-lookup"><span data-stu-id="9ac04-121">The `Test-Debug` function writes the value of the `$DebugPreference` variable to the PowerShell host and to the Debug stream.</span></span> <span data-ttu-id="9ac04-122">In diesem Beispiel verwenden wir den **Debug** -Parameter, um den Wert zu überschreiben `$DebugPreference` .</span><span class="sxs-lookup"><span data-stu-id="9ac04-122">In this example, we use the **Debug** parameter to override the `$DebugPreference` value.</span></span>

```powershell
function Test-Debug {
    [CmdletBinding()]
    param()
    Write-Debug ('$DebugPreference is ' + $DebugPreference)
    Write-Host ('$DebugPreference is ' + $DebugPreference)
}
```

```
PS> Test-Debug
$DebugPreference is SilentlyContinue

PS> Test-Debug -Debug
DEBUG: $DebugPreference is Inquire

Confirm
Continue with this operation?
[Y] Yes  [A] Yes to All  [H] Halt Command  [?] Help (default is "Y"):
$DebugPreference is Inquire
PS> $DebugPreference
SilentlyContinue
```

<span data-ttu-id="9ac04-123">Beachten Sie, dass sich der Wert von `$DebugPreference` ändert, wenn Sie den **Debug** -Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="9ac04-123">Notice that the value of `$DebugPreference` changes when you use the **Debug** parameter.</span></span> <span data-ttu-id="9ac04-124">Diese Änderung wirkt sich nur auf den Gültigkeitsbereich der Funktion aus.</span><span class="sxs-lookup"><span data-stu-id="9ac04-124">This change only affects the scope of the function.</span></span> <span data-ttu-id="9ac04-125">Der Wert ist außerhalb der Funktion nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="9ac04-125">The value is not affected outside the function.</span></span>

> [!NOTE]
> <span data-ttu-id="9ac04-126">Wenn der Wert von `$DebugPreference` **infrage** kommt, stoppt PowerShell die Ausführung, um zu Fragen, ob die Ausführung fortgesetzt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9ac04-126">When the value of `$DebugPreference` is **Inquire** , PowerShell halts execution to ask if execution should continue.</span></span>

<span data-ttu-id="9ac04-127">Weitere Informationen zum allgemeinen **Debug** -Parameter finden Sie unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="9ac04-127">For more information about the **Debug** common parameter, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9ac04-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9ac04-128">PARAMETERS</span></span>

### <span data-ttu-id="9ac04-129">-Meldung</span><span class="sxs-lookup"><span data-stu-id="9ac04-129">-Message</span></span>

<span data-ttu-id="9ac04-130">Gibt die Debugmeldung an, die an die Konsole gesendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="9ac04-130">Specifies the debug message to send to the console.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Msg

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="9ac04-131">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="9ac04-131">CommonParameters</span></span>

<span data-ttu-id="9ac04-132">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9ac04-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9ac04-133">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="9ac04-133">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9ac04-134">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="9ac04-134">INPUTS</span></span>

### <span data-ttu-id="9ac04-135">System.String</span><span class="sxs-lookup"><span data-stu-id="9ac04-135">System.String</span></span>

<span data-ttu-id="9ac04-136">Sie können eine Zeichenfolge, die eine Debugmeldung enthält, an die Pipeline übergeben `Write-Debug` .</span><span class="sxs-lookup"><span data-stu-id="9ac04-136">You can pipe a string that contains a debug message to `Write-Debug`.</span></span>

## <span data-ttu-id="9ac04-137">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="9ac04-137">OUTPUTS</span></span>

### <span data-ttu-id="9ac04-138">Keine</span><span class="sxs-lookup"><span data-stu-id="9ac04-138">None</span></span>

<span data-ttu-id="9ac04-139">`Write-Debug` schreibt nur in den debugdatenstrom.</span><span class="sxs-lookup"><span data-stu-id="9ac04-139">`Write-Debug` only writes to the debug stream.</span></span> <span data-ttu-id="9ac04-140">Es werden keine Objekte in die Pipeline geschrieben.</span><span class="sxs-lookup"><span data-stu-id="9ac04-140">It does not write any objects to the pipeline.</span></span>

## <span data-ttu-id="9ac04-141">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="9ac04-141">NOTES</span></span>

## <span data-ttu-id="9ac04-142">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="9ac04-142">RELATED LINKS</span></span>

[<span data-ttu-id="9ac04-143">about_Output_Streams</span><span class="sxs-lookup"><span data-stu-id="9ac04-143">about_Output_Streams</span></span>](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[<span data-ttu-id="9ac04-144">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="9ac04-144">about_Redirection</span></span>](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[<span data-ttu-id="9ac04-145">Schreibfehler</span><span class="sxs-lookup"><span data-stu-id="9ac04-145">Write-Error</span></span>](Write-Error.md)

[<span data-ttu-id="9ac04-146">Write-Host</span><span class="sxs-lookup"><span data-stu-id="9ac04-146">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="9ac04-147">Write-Output</span><span class="sxs-lookup"><span data-stu-id="9ac04-147">Write-Output</span></span>](Write-Output.md)

[<span data-ttu-id="9ac04-148">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="9ac04-148">Write-Progress</span></span>](Write-Progress.md)

[<span data-ttu-id="9ac04-149">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="9ac04-149">Write-Verbose</span></span>](Write-Verbose.md)

[<span data-ttu-id="9ac04-150">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="9ac04-150">Write-Warning</span></span>](Write-Warning.md)
