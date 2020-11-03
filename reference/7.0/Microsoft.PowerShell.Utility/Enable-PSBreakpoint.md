---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/09/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/enable-psbreakpoint?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSBreakpoint
ms.openlocfilehash: 606ac3205dae254c7f1290f51f80b61e472fbece
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93211495"
---
# <span data-ttu-id="7ef6b-103">Enable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="7ef6b-103">Enable-PSBreakpoint</span></span>

## <span data-ttu-id="7ef6b-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="7ef6b-104">SYNOPSIS</span></span>
<span data-ttu-id="7ef6b-105">Aktiviert die Haltepunkte in der aktuellen Konsole.</span><span class="sxs-lookup"><span data-stu-id="7ef6b-105">Enables the breakpoints in the current console.</span></span>

## <span data-ttu-id="7ef6b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7ef6b-106">SYNTAX</span></span>

### <span data-ttu-id="7ef6b-107">ID (Standard)</span><span class="sxs-lookup"><span data-stu-id="7ef6b-107">Id (Default)</span></span>

```
Enable-PSBreakpoint [-PassThru] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="7ef6b-108">Haltepunkt</span><span class="sxs-lookup"><span data-stu-id="7ef6b-108">Breakpoint</span></span>

```
Enable-PSBreakpoint [-PassThru] [-Breakpoint] <Breakpoint[]> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="7ef6b-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7ef6b-109">DESCRIPTION</span></span>

<span data-ttu-id="7ef6b-110">Mit dem `Enable-PSBreakpoint` -Cmdlet werden deaktivierte Haltepunkte erneut aktiviert.</span><span class="sxs-lookup"><span data-stu-id="7ef6b-110">The `Enable-PSBreakpoint` cmdlet re-enables disabled breakpoints.</span></span> <span data-ttu-id="7ef6b-111">Sie können Sie verwenden, um alle Haltepunkte oder bestimmte Haltepunkte durch Bereitstellen von Breakpoint-Objekten oder-IDs zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="7ef6b-111">You can use it to enable all breakpoints, or specific breakpoints by providing breakpoint objects or IDs.</span></span>

<span data-ttu-id="7ef6b-112">Ein Haltepunkt ist ein Punkt in einem Skript, an dem die Ausführung vorübergehend beendet wird, damit Sie den Status des Skripts überprüfen können.</span><span class="sxs-lookup"><span data-stu-id="7ef6b-112">A breakpoint is a point in a script where execution stops temporarily so that you can examine the state of the script.</span></span> <span data-ttu-id="7ef6b-113">Neu erstellte Haltepunkte werden automatisch aktiviert, können aber mithilfe von deaktiviert werden `Disable-PSBreakpoint` .</span><span class="sxs-lookup"><span data-stu-id="7ef6b-113">Newly created breakpoints are automatically enabled, but can be disabled using `Disable-PSBreakpoint`.</span></span>

<span data-ttu-id="7ef6b-114">Aus technischer Sicht ändert dieses Cmdlet den Wert der **aktivierten** Eigenschaft eines breakpointobjekt in " **true** ".</span><span class="sxs-lookup"><span data-stu-id="7ef6b-114">Technically, this cmdlet changes the value of the **Enabled** property of a breakpoint object to **True** .</span></span>

<span data-ttu-id="7ef6b-115">`Enable-PSBreakpoint` ist eines von mehreren Cmdlets für das Debuggen von PowerShell-Skripts.</span><span class="sxs-lookup"><span data-stu-id="7ef6b-115">`Enable-PSBreakpoint` is one of several cmdlets designed for debugging PowerShell scripts.</span></span> <span data-ttu-id="7ef6b-116">Weitere Informationen zum PowerShell-Debugger finden Sie unter [about_Debuggers](../Microsoft.PowerShell.Core/About/about_Debuggers.md).</span><span class="sxs-lookup"><span data-stu-id="7ef6b-116">For more information about the PowerShell debugger, see [about_Debuggers](../Microsoft.PowerShell.Core/About/about_Debuggers.md).</span></span>

## <span data-ttu-id="7ef6b-117">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="7ef6b-117">EXAMPLES</span></span>

### <span data-ttu-id="7ef6b-118">Beispiel 1: Aktivieren aller Breakpoints</span><span class="sxs-lookup"><span data-stu-id="7ef6b-118">Example 1: Enable all breakpoints</span></span>

<span data-ttu-id="7ef6b-119">In diesem Beispiel werden alle Breakpoints in der aktuellen Sitzung aktiviert.</span><span class="sxs-lookup"><span data-stu-id="7ef6b-119">This example enables all breakpoints in the current session.</span></span>

```powershell
Get-PSBreakpoint | Enable-PSBreakpoint
```

<span data-ttu-id="7ef6b-120">Mithilfe von Aliasen kann dieses Beispiel als abgekürzt werden `gbp | ebp` .</span><span class="sxs-lookup"><span data-stu-id="7ef6b-120">Using aliases, this example can be abbreviated as `gbp | ebp`.</span></span>

### <span data-ttu-id="7ef6b-121">Beispiel 2: Aktivieren von Breakpoints nach ID</span><span class="sxs-lookup"><span data-stu-id="7ef6b-121">Example 2: Enable breakpoints by ID</span></span>

<span data-ttu-id="7ef6b-122">In diesem Beispiel werden mehrere Breakpoints mithilfe ihrer Breakpoint-IDs aktiviert.</span><span class="sxs-lookup"><span data-stu-id="7ef6b-122">This example enables multiple breakpoints using their breakpoint IDs.</span></span>

```powershell
Enable-PSBreakpoint -Id 0, 1, 5
```

### <span data-ttu-id="7ef6b-123">Beispiel 3: Aktivieren eines deaktivierten Breakpoints</span><span class="sxs-lookup"><span data-stu-id="7ef6b-123">Example 3: Enable a disabled breakpoint</span></span>

<span data-ttu-id="7ef6b-124">In diesem Beispiel wird ein Breakpoint wieder aktiviert, der deaktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="7ef6b-124">This example re-enables a breakpoint that has been disabled.</span></span>

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

<span data-ttu-id="7ef6b-125">`Set-PSBreakpoint` erstellt einen Haltepunkt für die **Name** -Variable im `Sample.ps1` Skript, das das Haltepunkt Objekt in der `$B` Variablen speichert.</span><span class="sxs-lookup"><span data-stu-id="7ef6b-125">`Set-PSBreakpoint` creates a breakpoint on the **Name** variable in the `Sample.ps1` script saving the breakpoint object in the `$B` variable.</span></span> <span data-ttu-id="7ef6b-126">Der **passthru** -Parameter zeigt an, dass der Wert der **aktivierten** Eigenschaft des Breakpoints **false** lautet.</span><span class="sxs-lookup"><span data-stu-id="7ef6b-126">The **PassThru** parameter displays the value of the **Enabled** property of the breakpoint is **False** .</span></span>

<span data-ttu-id="7ef6b-127">`Enable-PSBreakpoint` aktiviert den Breakpoint erneut.</span><span class="sxs-lookup"><span data-stu-id="7ef6b-127">`Enable-PSBreakpoint` re-enables the breakpoint.</span></span> <span data-ttu-id="7ef6b-128">Wenn Sie den **passthru** -Parameter verwenden, sehen wir, dass der Wert der **aktivierten** Eigenschaft " **true** " lautet.</span><span class="sxs-lookup"><span data-stu-id="7ef6b-128">Again, using the **PassThru** parameter we see that the value of the **Enabled** property is **True** .</span></span>

### <span data-ttu-id="7ef6b-129">Beispiel 4: Aktivieren von Breakpoints mithilfe einer Variablen</span><span class="sxs-lookup"><span data-stu-id="7ef6b-129">Example 4: Enable breakpoints using a variable</span></span>

<span data-ttu-id="7ef6b-130">In diesem Beispiel wird eine Reihe von Breakpoints mithilfe der Breakpoint-Objekte aktiviert.</span><span class="sxs-lookup"><span data-stu-id="7ef6b-130">This example enables a set of breakpoints using the breakpoint objects.</span></span>

```powershell
$B = Get-PSBreakpoint -Id 3, 5
Enable-PSBreakpoint -Breakpoint $B
```

<span data-ttu-id="7ef6b-131">`Get-PSBreakpoint` Ruft die Breakpoints ab und speichert Sie in der `$B` Variablen.</span><span class="sxs-lookup"><span data-stu-id="7ef6b-131">`Get-PSBreakpoint` gets the breakpoints and saves them in the `$B` variable.</span></span> <span data-ttu-id="7ef6b-132">Mit dem **Breakpoint** `Enable-PSBreakpoint` breakpointparameter werden die Breakpoints aktiviert.</span><span class="sxs-lookup"><span data-stu-id="7ef6b-132">Using the **Breakpoint** parameter, `Enable-PSBreakpoint` enables the breakpoints.</span></span>

<span data-ttu-id="7ef6b-133">Dieses Beispiel entspricht dem Ausführen von `Enable-PSBreakpoint -Id 3, 5` .</span><span class="sxs-lookup"><span data-stu-id="7ef6b-133">This example is equivalent to running `Enable-PSBreakpoint -Id 3, 5`.</span></span>

## <span data-ttu-id="7ef6b-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7ef6b-134">PARAMETERS</span></span>

### <span data-ttu-id="7ef6b-135">-Breakpoint</span><span class="sxs-lookup"><span data-stu-id="7ef6b-135">-Breakpoint</span></span>

<span data-ttu-id="7ef6b-136">Gibt die zu aktivierenden Haltepunkte an.</span><span class="sxs-lookup"><span data-stu-id="7ef6b-136">Specifies the breakpoints to enable.</span></span> <span data-ttu-id="7ef6b-137">Geben Sie eine Variable an, die Breakpoints enthält, oder einen Befehl, der Haltepunkt Objekte abruft, z.b. `Get-PSBreakpoint` .</span><span class="sxs-lookup"><span data-stu-id="7ef6b-137">Provide a variable containing breakpoints or a command that gets breakpoint objects, such as `Get-PSBreakpoint`.</span></span> <span data-ttu-id="7ef6b-138">Sie können Haltepunkt Objekte auch über die Pipeline an übergeben `Enable-PSBreakpoint` .</span><span class="sxs-lookup"><span data-stu-id="7ef6b-138">You can also pipe breakpoint objects to `Enable-PSBreakpoint`.</span></span>

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

### <span data-ttu-id="7ef6b-139">-Id</span><span class="sxs-lookup"><span data-stu-id="7ef6b-139">-Id</span></span>

<span data-ttu-id="7ef6b-140">Gibt die **ID** -Nummern der zu aktivierenden Breakpoints an.</span><span class="sxs-lookup"><span data-stu-id="7ef6b-140">Specifies the **Id** numbers of the breakpoints to enable.</span></span> <span data-ttu-id="7ef6b-141">Standardmäßig werden alle Haltepunkte aktiviert.</span><span class="sxs-lookup"><span data-stu-id="7ef6b-141">The default value is all breakpoints.</span></span>
<span data-ttu-id="7ef6b-142">Geben Sie die **ID** nach Nummer oder in einer Variablen an.</span><span class="sxs-lookup"><span data-stu-id="7ef6b-142">Provide the **Id** by number or in a variable.</span></span> <span data-ttu-id="7ef6b-143">**ID** -Nummern können nicht an übergeben werden `Enable-PSBreakpoint` .</span><span class="sxs-lookup"><span data-stu-id="7ef6b-143">You can't pipe **Id** numbers to `Enable-PSBreakpoint`.</span></span> <span data-ttu-id="7ef6b-144">Um die **ID** eines halte Punkts zu ermitteln, verwenden Sie das- `Get-PSBreakpoint` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7ef6b-144">To find the **Id** of a breakpoint, use the `Get-PSBreakpoint` cmdlet.</span></span>

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

### <span data-ttu-id="7ef6b-145">-PassThru</span><span class="sxs-lookup"><span data-stu-id="7ef6b-145">-PassThru</span></span>

<span data-ttu-id="7ef6b-146">Gibt ein Objekt zurück, das den aktivierten Haltepunkt darstellt.</span><span class="sxs-lookup"><span data-stu-id="7ef6b-146">Returns an object representing the breakpoint being enabled.</span></span> <span data-ttu-id="7ef6b-147">Standardmäßig generiert dieses Cmdlet keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="7ef6b-147">By default, this cmdlet doesn't generate any output.</span></span>

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

### <span data-ttu-id="7ef6b-148">-Confirm</span><span class="sxs-lookup"><span data-stu-id="7ef6b-148">-Confirm</span></span>

<span data-ttu-id="7ef6b-149">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="7ef6b-149">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="7ef6b-150">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="7ef6b-150">-WhatIf</span></span>

<span data-ttu-id="7ef6b-151">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7ef6b-151">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="7ef6b-152">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7ef6b-152">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="7ef6b-153">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="7ef6b-153">CommonParameters</span></span>

<span data-ttu-id="7ef6b-154">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="7ef6b-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7ef6b-155">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="7ef6b-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7ef6b-156">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="7ef6b-156">INPUTS</span></span>

### <span data-ttu-id="7ef6b-157">System. Management. Automation. Breakpoint</span><span class="sxs-lookup"><span data-stu-id="7ef6b-157">System.Management.Automation.Breakpoint</span></span>

<span data-ttu-id="7ef6b-158">Sie können ein Haltepunkt Objekt an übergeben `Enable-PSBreakpoint` .</span><span class="sxs-lookup"><span data-stu-id="7ef6b-158">You can pipe a breakpoint object to `Enable-PSBreakpoint`.</span></span>

## <span data-ttu-id="7ef6b-159">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="7ef6b-159">OUTPUTS</span></span>

### <span data-ttu-id="7ef6b-160">None oder System. Management. Automation. Breakpoint</span><span class="sxs-lookup"><span data-stu-id="7ef6b-160">None or System.Management.Automation.Breakpoint</span></span>

<span data-ttu-id="7ef6b-161">Wenn Sie den **passthru** -Parameter verwenden, `Enable-PSBreakpoint` gibt ein Haltepunkt Objekt zurück, das den aktivierten Haltepunkt darstellt.</span><span class="sxs-lookup"><span data-stu-id="7ef6b-161">When you use the **PassThru** parameter, `Enable-PSBreakpoint` returns a breakpoint object that represents that breakpoint that was enabled.</span></span> <span data-ttu-id="7ef6b-162">Andernfalls generiert dieses Cmdlet keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="7ef6b-162">Otherwise, this cmdlet doesn't generate any output.</span></span>

## <span data-ttu-id="7ef6b-163">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="7ef6b-163">NOTES</span></span>

- <span data-ttu-id="7ef6b-164">Das `Enable-PSBreakpoint` Cmdlet generiert keinen Fehler, wenn Sie versuchen, einen Haltepunkt zu aktivieren, der bereits aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="7ef6b-164">The `Enable-PSBreakpoint` cmdlet doesn't generate an error if you try to enable a breakpoint that is already enabled.</span></span> <span data-ttu-id="7ef6b-165">Auf diese Weise können Sie alle Haltepunkte ohne Fehler aktivieren, auch wenn nur wenige deaktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="7ef6b-165">As such, you can enable all breakpoints without error, even when only a few are disabled.</span></span>

- <span data-ttu-id="7ef6b-166">Haltepunkte werden aktiviert, wenn Sie Sie mithilfe des- `Set-PSBreakpoint` Cmdlets erstellen.</span><span class="sxs-lookup"><span data-stu-id="7ef6b-166">Breakpoints are enabled when you create them by using the `Set-PSBreakpoint` cmdlet.</span></span> <span data-ttu-id="7ef6b-167">Sie müssen neu erstellte Haltepunkte nicht aktivieren.</span><span class="sxs-lookup"><span data-stu-id="7ef6b-167">You don't need to enable newly created breakpoints.</span></span>

## <span data-ttu-id="7ef6b-168">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="7ef6b-168">RELATED LINKS</span></span>

[<span data-ttu-id="7ef6b-169">Disable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="7ef6b-169">Disable-PSBreakpoint</span></span>](Disable-PSBreakpoint.md)

[<span data-ttu-id="7ef6b-170">Get-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="7ef6b-170">Get-PSBreakpoint</span></span>](Get-PSBreakpoint.md)

[<span data-ttu-id="7ef6b-171">Get-PSCallStack</span><span class="sxs-lookup"><span data-stu-id="7ef6b-171">Get-PSCallStack</span></span>](Get-PSCallStack.md)

[<span data-ttu-id="7ef6b-172">Remove-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="7ef6b-172">Remove-PSBreakpoint</span></span>](Remove-PSBreakpoint.md)

[<span data-ttu-id="7ef6b-173">Set-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="7ef6b-173">Set-PSBreakpoint</span></span>](Set-PSBreakpoint.md)
