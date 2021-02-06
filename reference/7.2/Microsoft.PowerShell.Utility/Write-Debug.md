---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-debug?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Debug
ms.openlocfilehash: 3d23f76dbf8e1c9a21805a4914038c8c4f319852
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602325"
---
# <span data-ttu-id="511ab-102">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="511ab-102">Write-Debug</span></span>

## <span data-ttu-id="511ab-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="511ab-103">SYNOPSIS</span></span>
<span data-ttu-id="511ab-104">Schreibt eine Debugmeldung in die Konsole.</span><span class="sxs-lookup"><span data-stu-id="511ab-104">Writes a debug message to the console.</span></span>

## <span data-ttu-id="511ab-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="511ab-105">SYNTAX</span></span>

```
Write-Debug [-Message] <String> [<CommonParameters>]
```

## <span data-ttu-id="511ab-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="511ab-106">DESCRIPTION</span></span>

<span data-ttu-id="511ab-107">Das `Write-Debug` Cmdlet schreibt Debugmeldungen aus einem Skript oder Befehl in den Host.</span><span class="sxs-lookup"><span data-stu-id="511ab-107">The `Write-Debug` cmdlet writes debug messages to the host from a script or command.</span></span>

<span data-ttu-id="511ab-108">Standardmäßig werden Debugmeldungen nicht in der-Konsole angezeigt, Sie können Sie jedoch mit dem **Debug** -Parameter oder der- `$DebugPreference` Variablen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="511ab-108">By default, debug messages are not displayed in the console, but you can display them by using the **Debug** parameter or the `$DebugPreference` variable.</span></span>

## <span data-ttu-id="511ab-109">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="511ab-109">EXAMPLES</span></span>

### <span data-ttu-id="511ab-110">Beispiel 1: verstehen $DebugPreference</span><span class="sxs-lookup"><span data-stu-id="511ab-110">Example 1: Understand $DebugPreference</span></span>

<span data-ttu-id="511ab-111">In diesem Beispiel wird eine Debugmeldung geschrieben.</span><span class="sxs-lookup"><span data-stu-id="511ab-111">This example writes a debug message.</span></span>

```powershell
Write-Debug "Cannot open file."
```

<span data-ttu-id="511ab-112">Der Standardwert von `$DebugPreference` ist **SilentlyContinue**.</span><span class="sxs-lookup"><span data-stu-id="511ab-112">The default value of `$DebugPreference` is **SilentlyContinue**.</span></span> <span data-ttu-id="511ab-113">Daher wird die Meldung nicht in der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="511ab-113">Therefore, the message is not displayed in the console.</span></span>

### <span data-ttu-id="511ab-114">Beispiel 2: Ändern des Werts von $DebugPreference</span><span class="sxs-lookup"><span data-stu-id="511ab-114">Example 2: Change the value of $DebugPreference</span></span>

<span data-ttu-id="511ab-115">Dieses Beispiel zeigt die Auswirkung der Änderung des Werts der `$DebugPreference` Variablen.</span><span class="sxs-lookup"><span data-stu-id="511ab-115">This example shows the effect of changing the value of the `$DebugPreference` variable.</span></span> <span data-ttu-id="511ab-116">Zuerst wird der aktuelle Wert von angezeigt, `$DebugPreference` und es wird versucht, eine Debugmeldung zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="511ab-116">First, we display the current value of `$DebugPreference` and attempt to write a debug message.</span></span> <span data-ttu-id="511ab-117">Anschließend ändern wir den Wert von `$DebugPreference` , um **fortzufahren**. Dadurch können Debugmeldungen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="511ab-117">Then we change the value of `$DebugPreference` to **Continue**, which allows debug messages to be displayed.</span></span>

```
PS> $DebugPreference
SilentlyContinue
PS> Write-Debug "Cannot open file."
PS>
PS> $DebugPreference = "Continue"
PS> Write-Debug "Cannot open file."
DEBUG: Cannot open file.
```

<span data-ttu-id="511ab-118">Weitere Informationen zu `$DebugPreference` finden Sie unter [about_Preference_Variables](/powershell/module/Microsoft.PowerShell.Core/About/about_Preference_Variables).</span><span class="sxs-lookup"><span data-stu-id="511ab-118">For more information about `$DebugPreference`, see [about_Preference_Variables](/powershell/module/Microsoft.PowerShell.Core/About/about_Preference_Variables).</span></span>

### <span data-ttu-id="511ab-119">Beispiel 3: Verwenden des Debug-Parameters zum Überschreiben von $DebugPreference</span><span class="sxs-lookup"><span data-stu-id="511ab-119">Example 3: Use the Debug parameter to override $DebugPreference</span></span>

<span data-ttu-id="511ab-120">Die `Test-Debug` -Funktion schreibt den Wert der `$DebugPreference` Variablen in den PowerShell-Host und den debugdatenstrom.</span><span class="sxs-lookup"><span data-stu-id="511ab-120">The `Test-Debug` function writes the value of the `$DebugPreference` variable to the PowerShell host and to the Debug stream.</span></span> <span data-ttu-id="511ab-121">In diesem Beispiel verwenden wir den **Debug** -Parameter, um den Wert zu überschreiben `$DebugPreference` .</span><span class="sxs-lookup"><span data-stu-id="511ab-121">In this example, we use the **Debug** parameter to override the `$DebugPreference` value.</span></span>

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
DEBUG: $DebugPreference is Continue
$DebugPreference is Continue
PS> $DebugPreference
SilentlyContinue
```

<span data-ttu-id="511ab-122">Beachten Sie, dass sich der Wert von `$DebugPreference` ändert, wenn Sie den **Debug** -Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="511ab-122">Notice that the value of `$DebugPreference` changes when you use the **Debug** parameter.</span></span> <span data-ttu-id="511ab-123">Diese Änderung wirkt sich nur auf den Gültigkeitsbereich der Funktion aus.</span><span class="sxs-lookup"><span data-stu-id="511ab-123">This change only affects the scope of the function.</span></span> <span data-ttu-id="511ab-124">Der Wert ist außerhalb der Funktion nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="511ab-124">The value is not affected outside the function.</span></span>

<span data-ttu-id="511ab-125">Weitere Informationen zum allgemeinen **Debug** -Parameter finden Sie unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="511ab-125">For more information about the **Debug** common parameter, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="511ab-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="511ab-126">PARAMETERS</span></span>

### <span data-ttu-id="511ab-127">-Meldung</span><span class="sxs-lookup"><span data-stu-id="511ab-127">-Message</span></span>

<span data-ttu-id="511ab-128">Gibt die Debugmeldung an, die an die Konsole gesendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="511ab-128">Specifies the debug message to send to the console.</span></span>

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

### <span data-ttu-id="511ab-129">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="511ab-129">CommonParameters</span></span>

<span data-ttu-id="511ab-130">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="511ab-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="511ab-131">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="511ab-131">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="511ab-132">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="511ab-132">INPUTS</span></span>

### <span data-ttu-id="511ab-133">System.String</span><span class="sxs-lookup"><span data-stu-id="511ab-133">System.String</span></span>

<span data-ttu-id="511ab-134">Sie können eine Zeichenfolge, die eine Debugmeldung enthält, an die Pipeline übergeben `Write-Debug` .</span><span class="sxs-lookup"><span data-stu-id="511ab-134">You can pipe a string that contains a debug message to `Write-Debug`.</span></span>

## <span data-ttu-id="511ab-135">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="511ab-135">OUTPUTS</span></span>

### <span data-ttu-id="511ab-136">Keine</span><span class="sxs-lookup"><span data-stu-id="511ab-136">None</span></span>

<span data-ttu-id="511ab-137">`Write-Debug` schreibt nur in den debugdatenstrom.</span><span class="sxs-lookup"><span data-stu-id="511ab-137">`Write-Debug` only writes to the debug stream.</span></span> <span data-ttu-id="511ab-138">Es werden keine Objekte in die Pipeline geschrieben.</span><span class="sxs-lookup"><span data-stu-id="511ab-138">It does not write any objects to the pipeline.</span></span>

## <span data-ttu-id="511ab-139">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="511ab-139">NOTES</span></span>

## <span data-ttu-id="511ab-140">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="511ab-140">RELATED LINKS</span></span>

[<span data-ttu-id="511ab-141">about_Output_Streams</span><span class="sxs-lookup"><span data-stu-id="511ab-141">about_Output_Streams</span></span>](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[<span data-ttu-id="511ab-142">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="511ab-142">about_Redirection</span></span>](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[<span data-ttu-id="511ab-143">Write-Error</span><span class="sxs-lookup"><span data-stu-id="511ab-143">Write-Error</span></span>](Write-Error.md)

[<span data-ttu-id="511ab-144">Write-Host</span><span class="sxs-lookup"><span data-stu-id="511ab-144">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="511ab-145">Write-Output</span><span class="sxs-lookup"><span data-stu-id="511ab-145">Write-Output</span></span>](Write-Output.md)

[<span data-ttu-id="511ab-146">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="511ab-146">Write-Progress</span></span>](Write-Progress.md)

[<span data-ttu-id="511ab-147">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="511ab-147">Write-Verbose</span></span>](Write-Verbose.md)

[<span data-ttu-id="511ab-148">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="511ab-148">Write-Warning</span></span>](Write-Warning.md)
