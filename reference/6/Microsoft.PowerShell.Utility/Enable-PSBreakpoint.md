---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/09/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/enable-psbreakpoint?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSBreakpoint
ms.openlocfilehash: 20e79fe561862912269e716c40ebe91194ea8b6e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216764"
---
# <span data-ttu-id="9f8e3-103">Enable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="9f8e3-103">Enable-PSBreakpoint</span></span>

## <span data-ttu-id="9f8e3-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="9f8e3-104">SYNOPSIS</span></span>
<span data-ttu-id="9f8e3-105">Aktiviert die Haltepunkte in der aktuellen Konsole.</span><span class="sxs-lookup"><span data-stu-id="9f8e3-105">Enables the breakpoints in the current console.</span></span>

## <span data-ttu-id="9f8e3-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9f8e3-106">SYNTAX</span></span>

### <span data-ttu-id="9f8e3-107">ID (Standard)</span><span class="sxs-lookup"><span data-stu-id="9f8e3-107">Id (Default)</span></span>

```
Enable-PSBreakpoint [-PassThru] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="9f8e3-108">Haltepunkt</span><span class="sxs-lookup"><span data-stu-id="9f8e3-108">Breakpoint</span></span>

```
Enable-PSBreakpoint [-PassThru] [-Breakpoint] <Breakpoint[]> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="9f8e3-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9f8e3-109">DESCRIPTION</span></span>

<span data-ttu-id="9f8e3-110">Mit dem `Enable-PSBreakpoint` -Cmdlet werden deaktivierte Haltepunkte erneut aktiviert.</span><span class="sxs-lookup"><span data-stu-id="9f8e3-110">The `Enable-PSBreakpoint` cmdlet re-enables disabled breakpoints.</span></span> <span data-ttu-id="9f8e3-111">Sie können Sie verwenden, um alle Haltepunkte oder bestimmte Haltepunkte durch Bereitstellen von Breakpoint-Objekten oder-IDs zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="9f8e3-111">You can use it to enable all breakpoints, or specific breakpoints by providing breakpoint objects or IDs.</span></span>

<span data-ttu-id="9f8e3-112">Ein Haltepunkt ist ein Punkt in einem Skript, an dem die Ausführung vorübergehend beendet wird, damit Sie den Status des Skripts überprüfen können.</span><span class="sxs-lookup"><span data-stu-id="9f8e3-112">A breakpoint is a point in a script where execution stops temporarily so that you can examine the state of the script.</span></span> <span data-ttu-id="9f8e3-113">Neu erstellte Haltepunkte werden automatisch aktiviert, können aber mithilfe von deaktiviert werden `Disable-PSBreakpoint` .</span><span class="sxs-lookup"><span data-stu-id="9f8e3-113">Newly created breakpoints are automatically enabled, but can be disabled using `Disable-PSBreakpoint`.</span></span>

<span data-ttu-id="9f8e3-114">Aus technischer Sicht ändert dieses Cmdlet den Wert der **aktivierten** Eigenschaft eines breakpointobjekt in " **true** ".</span><span class="sxs-lookup"><span data-stu-id="9f8e3-114">Technically, this cmdlet changes the value of the **Enabled** property of a breakpoint object to **True** .</span></span>

<span data-ttu-id="9f8e3-115">`Enable-PSBreakpoint` ist eines von mehreren Cmdlets für das Debuggen von PowerShell-Skripts.</span><span class="sxs-lookup"><span data-stu-id="9f8e3-115">`Enable-PSBreakpoint` is one of several cmdlets designed for debugging PowerShell scripts.</span></span> <span data-ttu-id="9f8e3-116">Weitere Informationen zum PowerShell-Debugger finden Sie unter [about_Debuggers](../Microsoft.PowerShell.Core/About/about_Debuggers.md).</span><span class="sxs-lookup"><span data-stu-id="9f8e3-116">For more information about the PowerShell debugger, see [about_Debuggers](../Microsoft.PowerShell.Core/About/about_Debuggers.md).</span></span>

## <span data-ttu-id="9f8e3-117">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="9f8e3-117">EXAMPLES</span></span>

### <span data-ttu-id="9f8e3-118">Beispiel 1: Aktivieren aller Breakpoints</span><span class="sxs-lookup"><span data-stu-id="9f8e3-118">Example 1: Enable all breakpoints</span></span>

<span data-ttu-id="9f8e3-119">In diesem Beispiel werden alle Breakpoints in der aktuellen Sitzung aktiviert.</span><span class="sxs-lookup"><span data-stu-id="9f8e3-119">This example enables all breakpoints in the current session.</span></span>

```powershell
Get-PSBreakpoint | Enable-PSBreakpoint
```

<span data-ttu-id="9f8e3-120">Mithilfe von Aliasen kann dieses Beispiel als abgekürzt werden `gbp | ebp` .</span><span class="sxs-lookup"><span data-stu-id="9f8e3-120">Using aliases, this example can be abbreviated as `gbp | ebp`.</span></span>

### <span data-ttu-id="9f8e3-121">Beispiel 2: Aktivieren von Breakpoints nach ID</span><span class="sxs-lookup"><span data-stu-id="9f8e3-121">Example 2: Enable breakpoints by ID</span></span>

<span data-ttu-id="9f8e3-122">In diesem Beispiel werden mehrere Breakpoints mithilfe ihrer Breakpoint-IDs aktiviert.</span><span class="sxs-lookup"><span data-stu-id="9f8e3-122">This example enables multiple breakpoints using their breakpoint IDs.</span></span>

```powershell
Enable-PSBreakpoint -Id 0, 1, 5
```

### <span data-ttu-id="9f8e3-123">Beispiel 3: Aktivieren eines deaktivierten Breakpoints</span><span class="sxs-lookup"><span data-stu-id="9f8e3-123">Example 3: Enable a disabled breakpoint</span></span>

<span data-ttu-id="9f8e3-124">In diesem Beispiel wird ein Breakpoint wieder aktiviert, der deaktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="9f8e3-124">This example re-enables a breakpoint that has been disabled.</span></span>

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

<span data-ttu-id="9f8e3-125">`Set-PSBreakpoint` erstellt einen Haltepunkt für die **Name** -Variable im `Sample.ps1` Skript, das das Haltepunkt Objekt in der `$B` Variablen speichert.</span><span class="sxs-lookup"><span data-stu-id="9f8e3-125">`Set-PSBreakpoint` creates a breakpoint on the **Name** variable in the `Sample.ps1` script saving the breakpoint object in the `$B` variable.</span></span> <span data-ttu-id="9f8e3-126">Der **passthru** -Parameter zeigt an, dass der Wert der **aktivierten** Eigenschaft des Breakpoints **false** lautet.</span><span class="sxs-lookup"><span data-stu-id="9f8e3-126">The **PassThru** parameter displays the value of the **Enabled** property of the breakpoint is **False** .</span></span>

<span data-ttu-id="9f8e3-127">`Enable-PSBreakpoint` aktiviert den Breakpoint erneut.</span><span class="sxs-lookup"><span data-stu-id="9f8e3-127">`Enable-PSBreakpoint` re-enables the breakpoint.</span></span> <span data-ttu-id="9f8e3-128">Wenn Sie den **passthru** -Parameter verwenden, sehen wir, dass der Wert der **aktivierten** Eigenschaft " **true** " lautet.</span><span class="sxs-lookup"><span data-stu-id="9f8e3-128">Again, using the **PassThru** parameter we see that the value of the **Enabled** property is **True** .</span></span>

### <span data-ttu-id="9f8e3-129">Beispiel 4: Aktivieren von Breakpoints mithilfe einer Variablen</span><span class="sxs-lookup"><span data-stu-id="9f8e3-129">Example 4: Enable breakpoints using a variable</span></span>

<span data-ttu-id="9f8e3-130">In diesem Beispiel wird eine Reihe von Breakpoints mithilfe der Breakpoint-Objekte aktiviert.</span><span class="sxs-lookup"><span data-stu-id="9f8e3-130">This example enables a set of breakpoints using the breakpoint objects.</span></span>

```powershell
$B = Get-PSBreakpoint -Id 3, 5
Enable-PSBreakpoint -Breakpoint $B
```

<span data-ttu-id="9f8e3-131">`Get-PSBreakpoint` Ruft die Breakpoints ab und speichert Sie in der `$B` Variablen.</span><span class="sxs-lookup"><span data-stu-id="9f8e3-131">`Get-PSBreakpoint` gets the breakpoints and saves them in the `$B` variable.</span></span> <span data-ttu-id="9f8e3-132">Mit dem **Breakpoint** `Enable-PSBreakpoint` breakpointparameter werden die Breakpoints aktiviert.</span><span class="sxs-lookup"><span data-stu-id="9f8e3-132">Using the **Breakpoint** parameter, `Enable-PSBreakpoint` enables the breakpoints.</span></span>

<span data-ttu-id="9f8e3-133">Dieses Beispiel entspricht dem Ausführen von `Enable-PSBreakpoint -Id 3, 5` .</span><span class="sxs-lookup"><span data-stu-id="9f8e3-133">This example is equivalent to running `Enable-PSBreakpoint -Id 3, 5`.</span></span>

## <span data-ttu-id="9f8e3-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9f8e3-134">PARAMETERS</span></span>

### <span data-ttu-id="9f8e3-135">-Breakpoint</span><span class="sxs-lookup"><span data-stu-id="9f8e3-135">-Breakpoint</span></span>

<span data-ttu-id="9f8e3-136">Gibt die zu aktivierenden Haltepunkte an.</span><span class="sxs-lookup"><span data-stu-id="9f8e3-136">Specifies the breakpoints to enable.</span></span> <span data-ttu-id="9f8e3-137">Geben Sie eine Variable an, die Breakpoints enthält, oder einen Befehl, der Haltepunkt Objekte abruft, z.b. `Get-PSBreakpoint` .</span><span class="sxs-lookup"><span data-stu-id="9f8e3-137">Provide a variable containing breakpoints or a command that gets breakpoint objects, such as `Get-PSBreakpoint`.</span></span> <span data-ttu-id="9f8e3-138">Sie können Haltepunkt Objekte auch über die Pipeline an übergeben `Enable-PSBreakpoint` .</span><span class="sxs-lookup"><span data-stu-id="9f8e3-138">You can also pipe breakpoint objects to `Enable-PSBreakpoint`.</span></span>

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

### <span data-ttu-id="9f8e3-139">-Id</span><span class="sxs-lookup"><span data-stu-id="9f8e3-139">-Id</span></span>

<span data-ttu-id="9f8e3-140">Gibt die **ID** -Nummern der zu aktivierenden Breakpoints an.</span><span class="sxs-lookup"><span data-stu-id="9f8e3-140">Specifies the **Id** numbers of the breakpoints to enable.</span></span> <span data-ttu-id="9f8e3-141">Standardmäßig werden alle Haltepunkte aktiviert.</span><span class="sxs-lookup"><span data-stu-id="9f8e3-141">The default value is all breakpoints.</span></span>
<span data-ttu-id="9f8e3-142">Geben Sie die **ID** nach Nummer oder in einer Variablen an.</span><span class="sxs-lookup"><span data-stu-id="9f8e3-142">Provide the **Id** by number or in a variable.</span></span> <span data-ttu-id="9f8e3-143">**ID** -Nummern können nicht an übergeben werden `Enable-PSBreakpoint` .</span><span class="sxs-lookup"><span data-stu-id="9f8e3-143">You can't pipe **Id** numbers to `Enable-PSBreakpoint`.</span></span> <span data-ttu-id="9f8e3-144">Um die **ID** eines halte Punkts zu ermitteln, verwenden Sie das- `Get-PSBreakpoint` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9f8e3-144">To find the **Id** of a breakpoint, use the `Get-PSBreakpoint` cmdlet.</span></span>

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

### <span data-ttu-id="9f8e3-145">-PassThru</span><span class="sxs-lookup"><span data-stu-id="9f8e3-145">-PassThru</span></span>

<span data-ttu-id="9f8e3-146">Gibt ein Objekt zurück, das den aktivierten Haltepunkt darstellt.</span><span class="sxs-lookup"><span data-stu-id="9f8e3-146">Returns an object representing the breakpoint being enabled.</span></span> <span data-ttu-id="9f8e3-147">Standardmäßig generiert dieses Cmdlet keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="9f8e3-147">By default, this cmdlet doesn't generate any output.</span></span>

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

### <span data-ttu-id="9f8e3-148">-Confirm</span><span class="sxs-lookup"><span data-stu-id="9f8e3-148">-Confirm</span></span>

<span data-ttu-id="9f8e3-149">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="9f8e3-149">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="9f8e3-150">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="9f8e3-150">-WhatIf</span></span>

<span data-ttu-id="9f8e3-151">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9f8e3-151">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="9f8e3-152">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="9f8e3-152">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="9f8e3-153">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="9f8e3-153">CommonParameters</span></span>

<span data-ttu-id="9f8e3-154">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9f8e3-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9f8e3-155">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="9f8e3-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9f8e3-156">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="9f8e3-156">INPUTS</span></span>

### <span data-ttu-id="9f8e3-157">System. Management. Automation. Breakpoint</span><span class="sxs-lookup"><span data-stu-id="9f8e3-157">System.Management.Automation.Breakpoint</span></span>

<span data-ttu-id="9f8e3-158">Sie können ein Haltepunkt Objekt an übergeben `Enable-PSBreakpoint` .</span><span class="sxs-lookup"><span data-stu-id="9f8e3-158">You can pipe a breakpoint object to `Enable-PSBreakpoint`.</span></span>

## <span data-ttu-id="9f8e3-159">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="9f8e3-159">OUTPUTS</span></span>

### <span data-ttu-id="9f8e3-160">None oder System. Management. Automation. Breakpoint</span><span class="sxs-lookup"><span data-stu-id="9f8e3-160">None or System.Management.Automation.Breakpoint</span></span>

<span data-ttu-id="9f8e3-161">Wenn Sie den **passthru** -Parameter verwenden, `Enable-PSBreakpoint` gibt ein Haltepunkt Objekt zurück, das den aktivierten Haltepunkt darstellt.</span><span class="sxs-lookup"><span data-stu-id="9f8e3-161">When you use the **PassThru** parameter, `Enable-PSBreakpoint` returns a breakpoint object that represents that breakpoint that was enabled.</span></span> <span data-ttu-id="9f8e3-162">Andernfalls generiert dieses Cmdlet keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="9f8e3-162">Otherwise, this cmdlet doesn't generate any output.</span></span>

## <span data-ttu-id="9f8e3-163">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="9f8e3-163">NOTES</span></span>

- <span data-ttu-id="9f8e3-164">Das `Enable-PSBreakpoint` Cmdlet generiert keinen Fehler, wenn Sie versuchen, einen Haltepunkt zu aktivieren, der bereits aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="9f8e3-164">The `Enable-PSBreakpoint` cmdlet doesn't generate an error if you try to enable a breakpoint that is already enabled.</span></span> <span data-ttu-id="9f8e3-165">Auf diese Weise können Sie alle Haltepunkte ohne Fehler aktivieren, auch wenn nur wenige deaktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="9f8e3-165">As such, you can enable all breakpoints without error, even when only a few are disabled.</span></span>

- <span data-ttu-id="9f8e3-166">Haltepunkte werden aktiviert, wenn Sie Sie mithilfe des- `Set-PSBreakpoint` Cmdlets erstellen.</span><span class="sxs-lookup"><span data-stu-id="9f8e3-166">Breakpoints are enabled when you create them by using the `Set-PSBreakpoint` cmdlet.</span></span> <span data-ttu-id="9f8e3-167">Sie müssen neu erstellte Haltepunkte nicht aktivieren.</span><span class="sxs-lookup"><span data-stu-id="9f8e3-167">You don't need to enable newly created breakpoints.</span></span>

## <span data-ttu-id="9f8e3-168">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="9f8e3-168">RELATED LINKS</span></span>

[<span data-ttu-id="9f8e3-169">Disable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="9f8e3-169">Disable-PSBreakpoint</span></span>](Disable-PSBreakpoint.md)

[<span data-ttu-id="9f8e3-170">Get-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="9f8e3-170">Get-PSBreakpoint</span></span>](Get-PSBreakpoint.md)

[<span data-ttu-id="9f8e3-171">Get-PSCallStack</span><span class="sxs-lookup"><span data-stu-id="9f8e3-171">Get-PSCallStack</span></span>](Get-PSCallStack.md)

[<span data-ttu-id="9f8e3-172">Remove-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="9f8e3-172">Remove-PSBreakpoint</span></span>](Remove-PSBreakpoint.md)

[<span data-ttu-id="9f8e3-173">Set-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="9f8e3-173">Set-PSBreakpoint</span></span>](Set-PSBreakpoint.md)
