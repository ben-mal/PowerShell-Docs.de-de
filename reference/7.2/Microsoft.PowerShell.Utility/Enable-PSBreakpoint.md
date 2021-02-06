---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/09/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/enable-psbreakpoint?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSBreakpoint
ms.openlocfilehash: 28cda7a2fa4435092b647e43a250222a852114b0
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601914"
---
# <span data-ttu-id="51722-102">Enable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="51722-102">Enable-PSBreakpoint</span></span>

## <span data-ttu-id="51722-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="51722-103">SYNOPSIS</span></span>
<span data-ttu-id="51722-104">Aktiviert die Haltepunkte in der aktuellen Konsole.</span><span class="sxs-lookup"><span data-stu-id="51722-104">Enables the breakpoints in the current console.</span></span>

## <span data-ttu-id="51722-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="51722-105">SYNTAX</span></span>

### <span data-ttu-id="51722-106">ID (Standard)</span><span class="sxs-lookup"><span data-stu-id="51722-106">Id (Default)</span></span>

```
Enable-PSBreakpoint [-PassThru] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="51722-107">Haltepunkt</span><span class="sxs-lookup"><span data-stu-id="51722-107">Breakpoint</span></span>

```
Enable-PSBreakpoint [-PassThru] [-Breakpoint] <Breakpoint[]> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="51722-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="51722-108">DESCRIPTION</span></span>

<span data-ttu-id="51722-109">Mit dem `Enable-PSBreakpoint` -Cmdlet werden deaktivierte Haltepunkte erneut aktiviert.</span><span class="sxs-lookup"><span data-stu-id="51722-109">The `Enable-PSBreakpoint` cmdlet re-enables disabled breakpoints.</span></span> <span data-ttu-id="51722-110">Sie können Sie verwenden, um alle Haltepunkte oder bestimmte Haltepunkte durch Bereitstellen von Breakpoint-Objekten oder-IDs zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="51722-110">You can use it to enable all breakpoints, or specific breakpoints by providing breakpoint objects or IDs.</span></span>

<span data-ttu-id="51722-111">Ein Haltepunkt ist ein Punkt in einem Skript, an dem die Ausführung vorübergehend beendet wird, damit Sie den Status des Skripts überprüfen können.</span><span class="sxs-lookup"><span data-stu-id="51722-111">A breakpoint is a point in a script where execution stops temporarily so that you can examine the state of the script.</span></span> <span data-ttu-id="51722-112">Neu erstellte Haltepunkte werden automatisch aktiviert, können aber mithilfe von deaktiviert werden `Disable-PSBreakpoint` .</span><span class="sxs-lookup"><span data-stu-id="51722-112">Newly created breakpoints are automatically enabled, but can be disabled using `Disable-PSBreakpoint`.</span></span>

<span data-ttu-id="51722-113">Aus technischer Sicht ändert dieses Cmdlet den Wert der **aktivierten** Eigenschaft eines breakpointobjekt in " **true**".</span><span class="sxs-lookup"><span data-stu-id="51722-113">Technically, this cmdlet changes the value of the **Enabled** property of a breakpoint object to **True**.</span></span>

<span data-ttu-id="51722-114">`Enable-PSBreakpoint` ist eines von mehreren Cmdlets für das Debuggen von PowerShell-Skripts.</span><span class="sxs-lookup"><span data-stu-id="51722-114">`Enable-PSBreakpoint` is one of several cmdlets designed for debugging PowerShell scripts.</span></span> <span data-ttu-id="51722-115">Weitere Informationen zum PowerShell-Debugger finden Sie unter [about_Debuggers](../Microsoft.PowerShell.Core/About/about_Debuggers.md).</span><span class="sxs-lookup"><span data-stu-id="51722-115">For more information about the PowerShell debugger, see [about_Debuggers](../Microsoft.PowerShell.Core/About/about_Debuggers.md).</span></span>

## <span data-ttu-id="51722-116">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="51722-116">EXAMPLES</span></span>

### <span data-ttu-id="51722-117">Beispiel 1: Aktivieren aller Breakpoints</span><span class="sxs-lookup"><span data-stu-id="51722-117">Example 1: Enable all breakpoints</span></span>

<span data-ttu-id="51722-118">In diesem Beispiel werden alle Breakpoints in der aktuellen Sitzung aktiviert.</span><span class="sxs-lookup"><span data-stu-id="51722-118">This example enables all breakpoints in the current session.</span></span>

```powershell
Get-PSBreakpoint | Enable-PSBreakpoint
```

<span data-ttu-id="51722-119">Mithilfe von Aliasen kann dieses Beispiel als abgekürzt werden `gbp | ebp` .</span><span class="sxs-lookup"><span data-stu-id="51722-119">Using aliases, this example can be abbreviated as `gbp | ebp`.</span></span>

### <span data-ttu-id="51722-120">Beispiel 2: Aktivieren von Breakpoints nach ID</span><span class="sxs-lookup"><span data-stu-id="51722-120">Example 2: Enable breakpoints by ID</span></span>

<span data-ttu-id="51722-121">In diesem Beispiel werden mehrere Breakpoints mithilfe ihrer Breakpoint-IDs aktiviert.</span><span class="sxs-lookup"><span data-stu-id="51722-121">This example enables multiple breakpoints using their breakpoint IDs.</span></span>

```powershell
Enable-PSBreakpoint -Id 0, 1, 5
```

### <span data-ttu-id="51722-122">Beispiel 3: Aktivieren eines deaktivierten Breakpoints</span><span class="sxs-lookup"><span data-stu-id="51722-122">Example 3: Enable a disabled breakpoint</span></span>

<span data-ttu-id="51722-123">In diesem Beispiel wird ein Breakpoint wieder aktiviert, der deaktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="51722-123">This example re-enables a breakpoint that has been disabled.</span></span>

```powershell
$B = Set-PSBreakpoint -Script "sample.ps1" -Variable Name -PassThru
$B | Enable-PSBreakpoint -PassThru
```

```Output
AccessMode : Write
Variable   : Name
Action     :
Enabled    : False
HitCount   : 0
Id         : 0
Script     : C:\ps-test\sample.ps1
ScriptName : C:\ps-test\sample.ps1

AccessMode : Write
Variable   : Name
Action     :
Enabled    : True
HitCount   : 0
Id         : 0
Script     : C:\ps-test\sample.ps1
ScriptName : C:\ps-test\sample.ps1
```

<span data-ttu-id="51722-124">`Set-PSBreakpoint` erstellt einen Haltepunkt für die **Name** -Variable im `Sample.ps1` Skript, das das Haltepunkt Objekt in der `$B` Variablen speichert.</span><span class="sxs-lookup"><span data-stu-id="51722-124">`Set-PSBreakpoint` creates a breakpoint on the **Name** variable in the `Sample.ps1` script saving the breakpoint object in the `$B` variable.</span></span> <span data-ttu-id="51722-125">Der **passthru** -Parameter zeigt an, dass der Wert der **aktivierten** Eigenschaft des Breakpoints **false** lautet.</span><span class="sxs-lookup"><span data-stu-id="51722-125">The **PassThru** parameter displays the value of the **Enabled** property of the breakpoint is **False**.</span></span>

<span data-ttu-id="51722-126">`Enable-PSBreakpoint` aktiviert den Breakpoint erneut.</span><span class="sxs-lookup"><span data-stu-id="51722-126">`Enable-PSBreakpoint` re-enables the breakpoint.</span></span> <span data-ttu-id="51722-127">Wenn Sie den **passthru** -Parameter verwenden, sehen wir, dass der Wert der **aktivierten** Eigenschaft " **true**" lautet.</span><span class="sxs-lookup"><span data-stu-id="51722-127">Again, using the **PassThru** parameter we see that the value of the **Enabled** property is **True**.</span></span>

### <span data-ttu-id="51722-128">Beispiel 4: Aktivieren von Breakpoints mithilfe einer Variablen</span><span class="sxs-lookup"><span data-stu-id="51722-128">Example 4: Enable breakpoints using a variable</span></span>

<span data-ttu-id="51722-129">In diesem Beispiel wird eine Reihe von Breakpoints mithilfe der Breakpoint-Objekte aktiviert.</span><span class="sxs-lookup"><span data-stu-id="51722-129">This example enables a set of breakpoints using the breakpoint objects.</span></span>

```powershell
$B = Get-PSBreakpoint -Id 3, 5
Enable-PSBreakpoint -Breakpoint $B
```

<span data-ttu-id="51722-130">`Get-PSBreakpoint` Ruft die Breakpoints ab und speichert Sie in der `$B` Variablen.</span><span class="sxs-lookup"><span data-stu-id="51722-130">`Get-PSBreakpoint` gets the breakpoints and saves them in the `$B` variable.</span></span> <span data-ttu-id="51722-131">Mit dem  `Enable-PSBreakpoint` breakpointparameter werden die Breakpoints aktiviert.</span><span class="sxs-lookup"><span data-stu-id="51722-131">Using the **Breakpoint** parameter, `Enable-PSBreakpoint` enables the breakpoints.</span></span>

<span data-ttu-id="51722-132">Dieses Beispiel entspricht dem Ausführen von `Enable-PSBreakpoint -Id 3, 5` .</span><span class="sxs-lookup"><span data-stu-id="51722-132">This example is equivalent to running `Enable-PSBreakpoint -Id 3, 5`.</span></span>

## <span data-ttu-id="51722-133">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="51722-133">PARAMETERS</span></span>

### <span data-ttu-id="51722-134">-Breakpoint</span><span class="sxs-lookup"><span data-stu-id="51722-134">-Breakpoint</span></span>

<span data-ttu-id="51722-135">Gibt die zu aktivierenden Haltepunkte an.</span><span class="sxs-lookup"><span data-stu-id="51722-135">Specifies the breakpoints to enable.</span></span> <span data-ttu-id="51722-136">Geben Sie eine Variable an, die Breakpoints enthält, oder einen Befehl, der Haltepunkt Objekte abruft, z.b. `Get-PSBreakpoint` .</span><span class="sxs-lookup"><span data-stu-id="51722-136">Provide a variable containing breakpoints or a command that gets breakpoint objects, such as `Get-PSBreakpoint`.</span></span> <span data-ttu-id="51722-137">Sie können Haltepunkt Objekte auch über die Pipeline an übergeben `Enable-PSBreakpoint` .</span><span class="sxs-lookup"><span data-stu-id="51722-137">You can also pipe breakpoint objects to `Enable-PSBreakpoint`.</span></span>

```yaml
Type: System.Management.Automation.Breakpoint[]
Parameter Sets: Breakpoint
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="51722-138">-Id</span><span class="sxs-lookup"><span data-stu-id="51722-138">-Id</span></span>

<span data-ttu-id="51722-139">Gibt die **ID** -Nummern der zu aktivierenden Breakpoints an.</span><span class="sxs-lookup"><span data-stu-id="51722-139">Specifies the **Id** numbers of the breakpoints to enable.</span></span> <span data-ttu-id="51722-140">Standardmäßig werden alle Haltepunkte aktiviert.</span><span class="sxs-lookup"><span data-stu-id="51722-140">The default value is all breakpoints.</span></span>
<span data-ttu-id="51722-141">Geben Sie die **ID** nach Nummer oder in einer Variablen an.</span><span class="sxs-lookup"><span data-stu-id="51722-141">Provide the **Id** by number or in a variable.</span></span> <span data-ttu-id="51722-142">**ID** -Nummern können nicht an übergeben werden `Enable-PSBreakpoint` .</span><span class="sxs-lookup"><span data-stu-id="51722-142">You can't pipe **Id** numbers to `Enable-PSBreakpoint`.</span></span> <span data-ttu-id="51722-143">Um die **ID** eines halte Punkts zu ermitteln, verwenden Sie das- `Get-PSBreakpoint` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="51722-143">To find the **Id** of a breakpoint, use the `Get-PSBreakpoint` cmdlet.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="51722-144">-PassThru</span><span class="sxs-lookup"><span data-stu-id="51722-144">-PassThru</span></span>

<span data-ttu-id="51722-145">Gibt ein Objekt zurück, das den aktivierten Haltepunkt darstellt.</span><span class="sxs-lookup"><span data-stu-id="51722-145">Returns an object representing the breakpoint being enabled.</span></span> <span data-ttu-id="51722-146">Standardmäßig generiert dieses Cmdlet keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="51722-146">By default, this cmdlet doesn't generate any output.</span></span>

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

### <span data-ttu-id="51722-147">-Confirm</span><span class="sxs-lookup"><span data-stu-id="51722-147">-Confirm</span></span>

<span data-ttu-id="51722-148">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="51722-148">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="51722-149">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="51722-149">-WhatIf</span></span>

<span data-ttu-id="51722-150">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="51722-150">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="51722-151">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="51722-151">The cmdlet isn't run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="51722-152">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="51722-152">CommonParameters</span></span>

<span data-ttu-id="51722-153">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="51722-153">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="51722-154">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="51722-154">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="51722-155">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="51722-155">INPUTS</span></span>

### <span data-ttu-id="51722-156">System. Management. Automation. Breakpoint</span><span class="sxs-lookup"><span data-stu-id="51722-156">System.Management.Automation.Breakpoint</span></span>

<span data-ttu-id="51722-157">Sie können ein Haltepunkt Objekt an übergeben `Enable-PSBreakpoint` .</span><span class="sxs-lookup"><span data-stu-id="51722-157">You can pipe a breakpoint object to `Enable-PSBreakpoint`.</span></span>

## <span data-ttu-id="51722-158">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="51722-158">OUTPUTS</span></span>

### <span data-ttu-id="51722-159">None oder System. Management. Automation. Breakpoint</span><span class="sxs-lookup"><span data-stu-id="51722-159">None or System.Management.Automation.Breakpoint</span></span>

<span data-ttu-id="51722-160">Wenn Sie den **passthru** -Parameter verwenden, `Enable-PSBreakpoint` gibt ein Haltepunkt Objekt zurück, das den aktivierten Haltepunkt darstellt.</span><span class="sxs-lookup"><span data-stu-id="51722-160">When you use the **PassThru** parameter, `Enable-PSBreakpoint` returns a breakpoint object that represents that breakpoint that was enabled.</span></span> <span data-ttu-id="51722-161">Andernfalls generiert dieses Cmdlet keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="51722-161">Otherwise, this cmdlet doesn't generate any output.</span></span>

## <span data-ttu-id="51722-162">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="51722-162">NOTES</span></span>

- <span data-ttu-id="51722-163">Das `Enable-PSBreakpoint` Cmdlet generiert keinen Fehler, wenn Sie versuchen, einen Haltepunkt zu aktivieren, der bereits aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="51722-163">The `Enable-PSBreakpoint` cmdlet doesn't generate an error if you try to enable a breakpoint that is already enabled.</span></span> <span data-ttu-id="51722-164">Auf diese Weise können Sie alle Haltepunkte ohne Fehler aktivieren, auch wenn nur wenige deaktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="51722-164">As such, you can enable all breakpoints without error, even when only a few are disabled.</span></span>

- <span data-ttu-id="51722-165">Haltepunkte werden aktiviert, wenn Sie Sie mithilfe des- `Set-PSBreakpoint` Cmdlets erstellen.</span><span class="sxs-lookup"><span data-stu-id="51722-165">Breakpoints are enabled when you create them by using the `Set-PSBreakpoint` cmdlet.</span></span> <span data-ttu-id="51722-166">Sie müssen neu erstellte Haltepunkte nicht aktivieren.</span><span class="sxs-lookup"><span data-stu-id="51722-166">You don't need to enable newly created breakpoints.</span></span>

## <span data-ttu-id="51722-167">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="51722-167">RELATED LINKS</span></span>

[<span data-ttu-id="51722-168">Disable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="51722-168">Disable-PSBreakpoint</span></span>](Disable-PSBreakpoint.md)

[<span data-ttu-id="51722-169">Get-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="51722-169">Get-PSBreakpoint</span></span>](Get-PSBreakpoint.md)

[<span data-ttu-id="51722-170">Get-PSCallStack</span><span class="sxs-lookup"><span data-stu-id="51722-170">Get-PSCallStack</span></span>](Get-PSCallStack.md)

[<span data-ttu-id="51722-171">Remove-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="51722-171">Remove-PSBreakpoint</span></span>](Remove-PSBreakpoint.md)

[<span data-ttu-id="51722-172">Set-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="51722-172">Set-PSBreakpoint</span></span>](Set-PSBreakpoint.md)

