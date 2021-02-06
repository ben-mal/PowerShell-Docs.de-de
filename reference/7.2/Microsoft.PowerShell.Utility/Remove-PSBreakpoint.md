---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/remove-psbreakpoint?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PSBreakpoint
ms.openlocfilehash: a56b9041c0ae70def7df619f2a4d265cb631fe7b
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599181"
---
# <span data-ttu-id="7e579-102">Remove-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="7e579-102">Remove-PSBreakpoint</span></span>

## <span data-ttu-id="7e579-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="7e579-103">SYNOPSIS</span></span>
<span data-ttu-id="7e579-104">Löscht Haltepunkte aus der aktuellen Konsole.</span><span class="sxs-lookup"><span data-stu-id="7e579-104">Deletes breakpoints from the current console.</span></span>

## <span data-ttu-id="7e579-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7e579-105">SYNTAX</span></span>

### <span data-ttu-id="7e579-106">Breakpoint (Standard)</span><span class="sxs-lookup"><span data-stu-id="7e579-106">Breakpoint (Default)</span></span>

```
Remove-PSBreakpoint [-Breakpoint] <Breakpoint[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="7e579-107">Id</span><span class="sxs-lookup"><span data-stu-id="7e579-107">Id</span></span>

```
Remove-PSBreakpoint [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="7e579-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7e579-108">DESCRIPTION</span></span>
<span data-ttu-id="7e579-109">Das **Remove-psbreakpoint-** Cmdlet löscht einen Haltepunkt.</span><span class="sxs-lookup"><span data-stu-id="7e579-109">The **Remove-PSBreakpoint** cmdlet deletes a breakpoint.</span></span>
<span data-ttu-id="7e579-110">Geben Sie ein Haltepunktobjekt oder eine Haltepunkt-ID ein.</span><span class="sxs-lookup"><span data-stu-id="7e579-110">Enter a breakpoint object or a breakpoint ID.</span></span>

<span data-ttu-id="7e579-111">Beim Entfernen eines Haltepunkts ist das Haltepunktobjekt nicht mehr verfügbar oder funktioniert nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="7e579-111">When you remove a breakpoint, the breakpoint object is no longer available or functional.</span></span>
<span data-ttu-id="7e579-112">Wenn Sie ein Haltepunktobjekt in einer Variablen gespeichert haben, ist der Verweis noch vorhanden, der Haltepunkt funktioniert jedoch nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="7e579-112">If you have saved a breakpoint object in a variable, the reference still exists, but the breakpoint does not function.</span></span>

<span data-ttu-id="7e579-113">**Remove-psbreakpoint** ist eines von mehreren Cmdlets, die zum Debuggen von PowerShell-Skripts entworfen wurden.</span><span class="sxs-lookup"><span data-stu-id="7e579-113">**Remove-PSBreakpoint** is one of several cmdlets designed for debugging PowerShell scripts.</span></span>
<span data-ttu-id="7e579-114">Weitere Informationen zum PowerShell-Debugger finden Sie unter about_Debuggers.</span><span class="sxs-lookup"><span data-stu-id="7e579-114">For more information about the PowerShell debugger, see about_Debuggers.</span></span>

## <span data-ttu-id="7e579-115">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="7e579-115">EXAMPLES</span></span>

### <span data-ttu-id="7e579-116">Beispiel 1: Entfernen aller Breakpoints</span><span class="sxs-lookup"><span data-stu-id="7e579-116">Example 1: Remove all breakpoints</span></span>

```
PS C:\> Get-PSBreakpoint | Remove-PSBreakpoint
```

<span data-ttu-id="7e579-117">Dieser Befehl löscht alle Haltepunkte in der aktuellen Konsole.</span><span class="sxs-lookup"><span data-stu-id="7e579-117">This command deletes all of the breakpoints in the current console.</span></span>

### <span data-ttu-id="7e579-118">Beispiel 2: Entfernen eines angegebenen Breakpoints</span><span class="sxs-lookup"><span data-stu-id="7e579-118">Example 2: Remove a specified breakpoint</span></span>

```
PS C:\> $B = Set-PSBreakpoint -Script "sample.ps1" -Variable "Name"
PS C:\> $B | Remove-PSBreakpoint
```

<span data-ttu-id="7e579-119">Dieser Befehl löscht einen Haltepunkt.</span><span class="sxs-lookup"><span data-stu-id="7e579-119">This command deletes a breakpoint.</span></span>

<span data-ttu-id="7e579-120">Der erste Befehl verwendet das Set-PSBreakpoint-Cmdlet, um einen Haltepunkt für die Name-Variable im Skript „Sample.ps1“ zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7e579-120">The first command uses the Set-PSBreakpoint cmdlet to create a breakpoint on the Name variable in the Sample.ps1 script.</span></span>
<span data-ttu-id="7e579-121">Anschließend wird das Haltepunkt Objekt in der $B Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="7e579-121">Then, it saves the breakpoint object in the $B variable.</span></span>

<span data-ttu-id="7e579-122">Der zweite Befehl verwendet das **Remove-psbreakpoint-** Cmdlet, um den neuen Breakpoint zu löschen.</span><span class="sxs-lookup"><span data-stu-id="7e579-122">The second command uses the **Remove-PSBreakpoint** cmdlet to delete the new breakpoint.</span></span>
<span data-ttu-id="7e579-123">Er verwendet einen Pipeline Operator (|), um das Haltepunkt Objekt in der $B-Variablen an das **Remove-psbreakpoint-** Cmdlet zu senden.</span><span class="sxs-lookup"><span data-stu-id="7e579-123">It uses a pipeline operator (|) to send the breakpoint object in the $B variable to the **Remove-PSBreakpoint** cmdlet.</span></span>

<span data-ttu-id="7e579-124">Als Ergebnis dieses Befehls wird das Skript bei der Ausführung nicht angehalten.</span><span class="sxs-lookup"><span data-stu-id="7e579-124">As a result of this command, if you run the script, it runs to completion without stopping.</span></span>
<span data-ttu-id="7e579-125">Außerdem gibt das **Get-psbreakpoint-** Cmdlet diesen Haltepunkt nicht zurück.</span><span class="sxs-lookup"><span data-stu-id="7e579-125">Also, the **Get-PSBreakpoint** cmdlet does not return this breakpoint.</span></span>

### <span data-ttu-id="7e579-126">Beispiel 3: Entfernen eines Breakpoints nach ID</span><span class="sxs-lookup"><span data-stu-id="7e579-126">Example 3: Remove a breakpoint by ID</span></span>

```
PS C:\> Remove-PSBreakpoint -Id 2
```

<span data-ttu-id="7e579-127">Dieser Befehl löscht den Haltepunkt mit der Haltepunkt-ID 2.</span><span class="sxs-lookup"><span data-stu-id="7e579-127">This command deletes the breakpoint with breakpoint ID 2.</span></span>

### <span data-ttu-id="7e579-128">Beispiel 4: Verwenden einer Funktion zum Entfernen aller Breakpoints</span><span class="sxs-lookup"><span data-stu-id="7e579-128">Example 4: Use a function to remove all breakpoints</span></span>

```
PS C:\> function del-psb { get-psbreakpoint | remove-psbreakpoint }
```

<span data-ttu-id="7e579-129">Diese einfache Funktion löscht alle Haltepunkte in der aktuellen Konsole.</span><span class="sxs-lookup"><span data-stu-id="7e579-129">This simple function deletes all of the breakpoints in the current console.</span></span>
<span data-ttu-id="7e579-130">Die Funktion verwendet das Get-PSBreakpoint-Cmdlet, um die Haltepunkte abzurufen.</span><span class="sxs-lookup"><span data-stu-id="7e579-130">It uses the Get-PSBreakpoint cmdlet to get the breakpoints.</span></span>
<span data-ttu-id="7e579-131">Anschließend wird ein Pipeline Operator (|) verwendet, um die Breakpoints an das **Remove-psbreakpoint-** Cmdlet zu senden, das Sie löscht.</span><span class="sxs-lookup"><span data-stu-id="7e579-131">Then, it uses a pipeline operator (|) to send the breakpoints to the **Remove-PSBreakpoint** cmdlet, which deletes them.</span></span>

<span data-ttu-id="7e579-132">Daher können Sie `del-psb` anstelle des längeren Befehls eingeben.</span><span class="sxs-lookup"><span data-stu-id="7e579-132">As a result, you can type `del-psb` instead of the longer command.</span></span>

<span data-ttu-id="7e579-133">Um die Funktion zu speichern, fügen Sie Sie Ihrem PowerShell-Profil hinzu.</span><span class="sxs-lookup"><span data-stu-id="7e579-133">To save the function, add it to your PowerShell profile.</span></span>

## <span data-ttu-id="7e579-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7e579-134">PARAMETERS</span></span>

### <span data-ttu-id="7e579-135">-Breakpoint</span><span class="sxs-lookup"><span data-stu-id="7e579-135">-Breakpoint</span></span>
<span data-ttu-id="7e579-136">Gibt die zu löschenden Haltepunkte an.</span><span class="sxs-lookup"><span data-stu-id="7e579-136">Specifies the breakpoints to delete.</span></span>
<span data-ttu-id="7e579-137">Geben Sie eine Variable ein, die Haltepunkt Objekte enthält, oder einen Befehl, der Haltepunkt Objekte abruft, z. b. einen **Get-psbreakpoint** -Befehl.</span><span class="sxs-lookup"><span data-stu-id="7e579-137">Enter a variable that contains breakpoint objects or a command that gets breakpoint objects, such as a **Get-PSBreakpoint** command.</span></span>
<span data-ttu-id="7e579-138">Sie können Haltepunkt Objekte auch über die Pipeline an **Remove-psbreakpoint** übergeben.</span><span class="sxs-lookup"><span data-stu-id="7e579-138">You can also pipe breakpoint objects to **Remove-PSBreakpoint**.</span></span>

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

### <span data-ttu-id="7e579-139">-Id</span><span class="sxs-lookup"><span data-stu-id="7e579-139">-Id</span></span>
<span data-ttu-id="7e579-140">Gibt Breakpoint-IDs an, für die dieses Cmdlet Breakpoints löscht.</span><span class="sxs-lookup"><span data-stu-id="7e579-140">Specifies breakpoint IDs for which this cmdlet deletes breakpoints.</span></span>

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

### <span data-ttu-id="7e579-141">-Confirm</span><span class="sxs-lookup"><span data-stu-id="7e579-141">-Confirm</span></span>
<span data-ttu-id="7e579-142">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="7e579-142">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="7e579-143">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="7e579-143">-WhatIf</span></span>
<span data-ttu-id="7e579-144">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7e579-144">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="7e579-145">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7e579-145">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="7e579-146">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="7e579-146">CommonParameters</span></span>
<span data-ttu-id="7e579-147">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="7e579-147">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7e579-148">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="7e579-148">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7e579-149">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="7e579-149">INPUTS</span></span>

### <span data-ttu-id="7e579-150">System. Management. Automation. Breakpoint</span><span class="sxs-lookup"><span data-stu-id="7e579-150">System.Management.Automation.Breakpoint</span></span>
<span data-ttu-id="7e579-151">Sie können Haltepunkt Objekte über die Pipeline an **Remove-psbreakpoint** übergeben.</span><span class="sxs-lookup"><span data-stu-id="7e579-151">You can pipe breakpoint objects to **Remove-PSBreakpoint**.</span></span>

## <span data-ttu-id="7e579-152">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="7e579-152">OUTPUTS</span></span>

### <span data-ttu-id="7e579-153">Keine</span><span class="sxs-lookup"><span data-stu-id="7e579-153">None</span></span>
<span data-ttu-id="7e579-154">Das Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="7e579-154">The cmdlet does not generate any output.</span></span>

## <span data-ttu-id="7e579-155">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="7e579-155">NOTES</span></span>

## <span data-ttu-id="7e579-156">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="7e579-156">RELATED LINKS</span></span>

[<span data-ttu-id="7e579-157">Disable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="7e579-157">Disable-PSBreakpoint</span></span>](Disable-PSBreakpoint.md)

[<span data-ttu-id="7e579-158">Enable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="7e579-158">Enable-PSBreakpoint</span></span>](Enable-PSBreakpoint.md)

[<span data-ttu-id="7e579-159">Get-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="7e579-159">Get-PSBreakpoint</span></span>](Get-PSBreakpoint.md)

[<span data-ttu-id="7e579-160">Get-PSCallStack</span><span class="sxs-lookup"><span data-stu-id="7e579-160">Get-PSCallStack</span></span>](Get-PSCallStack.md)

[<span data-ttu-id="7e579-161">Set-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="7e579-161">Set-PSBreakpoint</span></span>](Set-PSBreakpoint.md)

