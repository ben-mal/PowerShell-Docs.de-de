---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/disable-psbreakpoint?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSBreakpoint
ms.openlocfilehash: 2bd1a48d2075950cdb337063a100bf31534ac6fe
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601307"
---
# <span data-ttu-id="1f089-102">Disable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="1f089-102">Disable-PSBreakpoint</span></span>

## <span data-ttu-id="1f089-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="1f089-103">SYNOPSIS</span></span>
<span data-ttu-id="1f089-104">Deaktiviert die Haltepunkte in der aktuellen Konsole.</span><span class="sxs-lookup"><span data-stu-id="1f089-104">Disables the breakpoints in the current console.</span></span>

## <span data-ttu-id="1f089-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1f089-105">SYNTAX</span></span>

### <span data-ttu-id="1f089-106">Breakpoint (Standard)</span><span class="sxs-lookup"><span data-stu-id="1f089-106">Breakpoint (Default)</span></span>

```
Disable-PSBreakpoint [-PassThru] [-Breakpoint] <Breakpoint[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="1f089-107">Id</span><span class="sxs-lookup"><span data-stu-id="1f089-107">Id</span></span>

```
Disable-PSBreakpoint [-PassThru] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="1f089-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1f089-108">DESCRIPTION</span></span>

<span data-ttu-id="1f089-109">Das " **Disab-psbreakpoint"-** Cmdlet deaktiviert Breakpoints, wodurch sichergestellt wird, dass Sie beim Ausführen des Skripts nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1f089-109">The **Disable-PSBreakpoint** cmdlet disables breakpoints, which assures that they are not hit when the script runs.</span></span>
<span data-ttu-id="1f089-110">Sie können es verwenden, um alle Haltepunkte zu deaktivieren, oder Sie können Haltepunkte durch Senden der Haltepunktobjekte oder Haltepunkt-IDs angeben.</span><span class="sxs-lookup"><span data-stu-id="1f089-110">You can use it to disable all breakpoints, or you can specify breakpoints by submitting breakpoint objects or breakpoint IDs.</span></span>

<span data-ttu-id="1f089-111">Aus technischer Sicht ändert dieses Cmdlet den Wert der Enabled-Eigenschaft eines Haltepunktobjekts zu „False“.</span><span class="sxs-lookup"><span data-stu-id="1f089-111">Technically, this cmdlet changes the value of the Enabled property of a breakpoint object to False.</span></span>
<span data-ttu-id="1f089-112">Um einen Haltepunkt wieder zu aktivieren, verwenden Sie das Enable-PSBreakpoint-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1f089-112">To re-enable a breakpoint, use the Enable-PSBreakpoint cmdlet.</span></span>
<span data-ttu-id="1f089-113">Haltepunkte sind standardmäßig aktiviert, wenn Sie sie mithilfe des Set-PSBreakpoint-Cmdlets erstellen.</span><span class="sxs-lookup"><span data-stu-id="1f089-113">Breakpoints are enabled by default when you create them by using the Set-PSBreakpoint cmdlet.</span></span>

<span data-ttu-id="1f089-114">Ein Haltepunkt ist ein Punkt in einem Skript, an dem die Ausführung vorübergehend beendet wird, damit die Anweisungen im Skript überprüft werden können.</span><span class="sxs-lookup"><span data-stu-id="1f089-114">A breakpoint is a point in a script where execution stops temporarily so that you can examine the instructions in the script.</span></span>
<span data-ttu-id="1f089-115">**Deaktivieren-psbreakpoint** ist eines von mehreren Cmdlets, die zum Debuggen von PowerShell-Skripts entworfen wurden.</span><span class="sxs-lookup"><span data-stu-id="1f089-115">**Disable-PSBreakpoint** is one of several cmdlets designed for debugging PowerShell scripts.</span></span>
<span data-ttu-id="1f089-116">Weitere Informationen zum PowerShell-Debugger finden Sie unter about_Debuggers.</span><span class="sxs-lookup"><span data-stu-id="1f089-116">For more information about the PowerShell debugger, see about_Debuggers.</span></span>

## <span data-ttu-id="1f089-117">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="1f089-117">EXAMPLES</span></span>

### <span data-ttu-id="1f089-118">Beispiel 1: Festlegen eines halte Punkts und Deaktivieren des halte Punkts</span><span class="sxs-lookup"><span data-stu-id="1f089-118">Example 1: Set a breakpoint and disable it</span></span>

```
PS C:\> $B = Set-PSBreakpoint -Script "sample.ps1" -Variable "name"
PS C:\> $B | Disable-PSBreakpoint
```

<span data-ttu-id="1f089-119">Diese Befehle deaktivieren einen neu erstellten Haltepunkt.</span><span class="sxs-lookup"><span data-stu-id="1f089-119">These commands disable a newly-created breakpoint.</span></span>

<span data-ttu-id="1f089-120">Der erste Befehl verwendet das Cmdlet "Set-PSBreakpoint", um einen Haltepunkt für die *Name* -Variable im Sample.ps1 Skript zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1f089-120">The first command uses the Set-PSBreakpoint cmdlet to create a breakpoint on the *Name* variable in the Sample.ps1 script.</span></span>
<span data-ttu-id="1f089-121">Anschließend wird das Haltepunkt Objekt in der $B Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="1f089-121">Then, it saves the breakpoint object in the $B variable.</span></span>

<span data-ttu-id="1f089-122">Der zweite Befehl verwendet das Cmdlet " **Deaktivieren-psbreakpoint** ", um den neuen Haltepunkt zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="1f089-122">The second command uses the **Disable-PSBreakpoint** cmdlet to disable the new breakpoint.</span></span>
<span data-ttu-id="1f089-123">Er verwendet einen Pipeline Operator (|), um das Haltepunkt Objekt in $B an das **Deaktivierte Cmdlet "-psbreakpoint** " zu senden.</span><span class="sxs-lookup"><span data-stu-id="1f089-123">It uses a pipeline operator (|) to send the breakpoint object in $B to the **Disable-PSBreakpoint** cmdlet.</span></span>

<span data-ttu-id="1f089-124">Als Ergebnis dieses Befehls ist der Wert der aktivierten Eigenschaft des Breakpoint-Objekts in $B false.</span><span class="sxs-lookup"><span data-stu-id="1f089-124">As a result of this command, the value of the Enabled property of the breakpoint object in $B is False.</span></span>

### <span data-ttu-id="1f089-125">Beispiel 2: Deaktivieren eines Breakpoints</span><span class="sxs-lookup"><span data-stu-id="1f089-125">Example 2: Disable a breakpoint</span></span>

```
PS C:\> Disable-PSBreakpoint -Id 0
```

<span data-ttu-id="1f089-126">Dieser Befehl deaktiviert den Haltepunkt mit der Haltepunkt-ID 0.</span><span class="sxs-lookup"><span data-stu-id="1f089-126">This command disables the breakpoint with breakpoint ID 0.</span></span>

### <span data-ttu-id="1f089-127">Beispiel 3: Erstellen eines deaktivierten Breakpoints</span><span class="sxs-lookup"><span data-stu-id="1f089-127">Example 3: Create a disabled breakpoint</span></span>

```
PS C:\> Disable-PSBreakpoint -Breakpoint ($B = Set-PSBreakpoint -Script "sample.ps1" -Line 5)
PS C:\> $B
```

<span data-ttu-id="1f089-128">Dieser Befehl erstellt einen neuen Haltepunkt, der deaktiviert ist, bis Sie ihn aktivieren.</span><span class="sxs-lookup"><span data-stu-id="1f089-128">This command creates a new breakpoint that is disabled until you enable it.</span></span>

<span data-ttu-id="1f089-129">Er verwendet das Cmdlet " **Deaktivieren-psbreakpoint** ", um den Breakpoint zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="1f089-129">It uses the **Disable-PSBreakpoint** cmdlet to disable the breakpoint.</span></span>
<span data-ttu-id="1f089-130">Der Wert des *Breakpoint* -Parameters ist ein Set-PSBreakpoint Befehl, der einen neuen Haltepunkt festlegt, ein Haltepunkt Objekt generiert und das Objekt in der $B Variablen speichert.</span><span class="sxs-lookup"><span data-stu-id="1f089-130">The value of the *Breakpoint* parameter is a Set-PSBreakpoint command that sets a new breakpoint, generates a breakpoint object, and saves the object in the $B variable.</span></span>

<span data-ttu-id="1f089-131">Cmdlet-Parameter, die Objekte als Werte annehmen, können eine Variable akzeptieren, die das Objekt enthält, oder einen Befehl, der das Objekt abruft oder generiert.</span><span class="sxs-lookup"><span data-stu-id="1f089-131">Cmdlet parameters that take objects as their values can accept a variable that contains the object or a command that gets or generates the object.</span></span>
<span data-ttu-id="1f089-132">Da **Set-psbreakpoint** ein Haltepunkt Objekt generiert, kann es in diesem Fall als Wert für den *Breakpoint* -Parameter verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1f089-132">In this case, because **Set-PSBreakpoint** generates a breakpoint object, it can be used as the value of the *Breakpoint* parameter.</span></span>

<span data-ttu-id="1f089-133">Der zweite Befehl zeigt das Haltepunkt Objekt im Wert der $B Variablen an.</span><span class="sxs-lookup"><span data-stu-id="1f089-133">The second command displays the breakpoint object in the value of the $B variable.</span></span>

### <span data-ttu-id="1f089-134">Beispiel 4: Deaktivieren aller Haltepunkte in der aktuellen Konsole</span><span class="sxs-lookup"><span data-stu-id="1f089-134">Example 4: Disable all breakpoints in the current console</span></span>

```
PS C:\> Get-PSBreakpoint | Disable-PSBreakpoint
```

<span data-ttu-id="1f089-135">Dieser Befehl deaktiviert alle Haltepunkte in der aktuellen Konsole.</span><span class="sxs-lookup"><span data-stu-id="1f089-135">This command disables all breakpoints in the current console.</span></span>
<span data-ttu-id="1f089-136">Sie können diesen Befehl wie folgt abkürzen: "GBP | DBP ".</span><span class="sxs-lookup"><span data-stu-id="1f089-136">You can abbreviate this command as: "gbp | dbp".</span></span>

## <span data-ttu-id="1f089-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1f089-137">PARAMETERS</span></span>

### <span data-ttu-id="1f089-138">-Breakpoint</span><span class="sxs-lookup"><span data-stu-id="1f089-138">-Breakpoint</span></span>

<span data-ttu-id="1f089-139">Gibt die zu deaktivierenden Haltepunkte an.</span><span class="sxs-lookup"><span data-stu-id="1f089-139">Specifies the breakpoints to disable.</span></span>
<span data-ttu-id="1f089-140">Geben Sie eine Variable ein, die Haltepunktobjekte enthält, bzw. einen Befehl, der Haltepunktobjekte abruft, wie z. B. einen Get-PSBreakpoint-Befehl.</span><span class="sxs-lookup"><span data-stu-id="1f089-140">Enter a variable that contains breakpoint objects or a command that gets breakpoint objects, such as a Get-PSBreakpoint command.</span></span>
<span data-ttu-id="1f089-141">Sie können Haltepunkt Objekte auch über die Pipeline an das Cmdlet " **Deaktivieren-psbreakpoint** " übergeben.</span><span class="sxs-lookup"><span data-stu-id="1f089-141">You can also pipe breakpoint objects to the **Disable-PSBreakpoint** cmdlet.</span></span>

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

### <span data-ttu-id="1f089-142">-Id</span><span class="sxs-lookup"><span data-stu-id="1f089-142">-Id</span></span>

<span data-ttu-id="1f089-143">Deaktiviert die Haltepunkte mit den angegebenen Haltepunkt-IDs.</span><span class="sxs-lookup"><span data-stu-id="1f089-143">Disables the breakpoints with the specified breakpoint IDs.</span></span>
<span data-ttu-id="1f089-144">Geben Sie die IDs oder eine Variable ein, die die IDs enthält.</span><span class="sxs-lookup"><span data-stu-id="1f089-144">Enter the IDs or a variable that contains the IDs.</span></span>
<span data-ttu-id="1f089-145">Sie können keine IDs an " **Deaktivieren-psbreakpoint**" übergeben.</span><span class="sxs-lookup"><span data-stu-id="1f089-145">You cannot pipe IDs to **Disable-PSBreakpoint**.</span></span>

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

### <span data-ttu-id="1f089-146">-PassThru</span><span class="sxs-lookup"><span data-stu-id="1f089-146">-PassThru</span></span>

<span data-ttu-id="1f089-147">Gibt ein Objekt zurück, das die aktivierten Haltepunkte darstellt.</span><span class="sxs-lookup"><span data-stu-id="1f089-147">Returns an object representing the enabled breakpoints.</span></span>
<span data-ttu-id="1f089-148">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="1f089-148">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="1f089-149">-Confirm</span><span class="sxs-lookup"><span data-stu-id="1f089-149">-Confirm</span></span>

<span data-ttu-id="1f089-150">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="1f089-150">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="1f089-151">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="1f089-151">-WhatIf</span></span>

<span data-ttu-id="1f089-152">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1f089-152">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="1f089-153">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1f089-153">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="1f089-154">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="1f089-154">CommonParameters</span></span>

<span data-ttu-id="1f089-155">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1f089-155">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1f089-156">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1f089-156">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1f089-157">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="1f089-157">INPUTS</span></span>

### <span data-ttu-id="1f089-158">System. Management. Automation. Breakpoint</span><span class="sxs-lookup"><span data-stu-id="1f089-158">System.Management.Automation.Breakpoint</span></span>

<span data-ttu-id="1f089-159">Sie können ein Haltepunkt Objekt über die Pipeline an **Deaktivieren-psbreakpoint** übergeben.</span><span class="sxs-lookup"><span data-stu-id="1f089-159">You can pipe a breakpoint object to **Disable-PSBreakpoint**.</span></span>

## <span data-ttu-id="1f089-160">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="1f089-160">OUTPUTS</span></span>

### <span data-ttu-id="1f089-161">None oder System. Management. Automation. Breakpoint</span><span class="sxs-lookup"><span data-stu-id="1f089-161">None or System.Management.Automation.Breakpoint</span></span>

<span data-ttu-id="1f089-162">Wenn Sie den *passthru* -Parameter verwenden, gibt **Deaktivieren-psbreakpoint** ein Objekt zurück, das den deaktivierten Haltepunkt darstellt.</span><span class="sxs-lookup"><span data-stu-id="1f089-162">When you use the *PassThru* parameter, **Disable-PSBreakpoint** returns an object that represents the disabled breakpoint.</span></span>
<span data-ttu-id="1f089-163">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="1f089-163">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="1f089-164">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="1f089-164">NOTES</span></span>

## <span data-ttu-id="1f089-165">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="1f089-165">RELATED LINKS</span></span>

[<span data-ttu-id="1f089-166">Enable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="1f089-166">Enable-PSBreakpoint</span></span>](Enable-PSBreakpoint.md)

[<span data-ttu-id="1f089-167">Get-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="1f089-167">Get-PSBreakpoint</span></span>](Get-PSBreakpoint.md)

[<span data-ttu-id="1f089-168">Get-PSCallStack</span><span class="sxs-lookup"><span data-stu-id="1f089-168">Get-PSCallStack</span></span>](Get-PSCallStack.md)

[<span data-ttu-id="1f089-169">Remove-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="1f089-169">Remove-PSBreakpoint</span></span>](Remove-PSBreakpoint.md)

[<span data-ttu-id="1f089-170">Set-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="1f089-170">Set-PSBreakpoint</span></span>](Set-PSBreakpoint.md)

