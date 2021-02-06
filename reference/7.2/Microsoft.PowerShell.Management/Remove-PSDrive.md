---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-psdrive?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PSDrive
ms.openlocfilehash: d20a348f3f5ba193eb85e0f9d0e2cc11ad083b47
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599845"
---
# <span data-ttu-id="0683b-102">Remove-PSDrive</span><span class="sxs-lookup"><span data-stu-id="0683b-102">Remove-PSDrive</span></span>

## <span data-ttu-id="0683b-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="0683b-103">SYNOPSIS</span></span>
<span data-ttu-id="0683b-104">Löscht temporäre PowerShell-Laufwerke und trennt die Verbindung mit zugeordneten Netzlaufwerken.</span><span class="sxs-lookup"><span data-stu-id="0683b-104">Deletes temporary PowerShell drives and disconnects mapped network drives.</span></span>

## <span data-ttu-id="0683b-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0683b-105">SYNTAX</span></span>

### <span data-ttu-id="0683b-106">Name (Standard)</span><span class="sxs-lookup"><span data-stu-id="0683b-106">Name (Default)</span></span>

```
Remove-PSDrive [-Name] <String[]> [-PSProvider <String[]>] [-Scope <String>] [-Force]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0683b-107">LiteralName</span><span class="sxs-lookup"><span data-stu-id="0683b-107">LiteralName</span></span>

```
Remove-PSDrive [-LiteralName] <String[]> [-PSProvider <String[]>] [-Scope <String>] [-Force]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="0683b-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0683b-108">DESCRIPTION</span></span>

<span data-ttu-id="0683b-109">Mit dem- `Remove-PSDrive` Cmdlet werden temporäre PowerShell-Laufwerke gelöscht, die mithilfe des- `New-PSDrive` Cmdlets erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="0683b-109">The `Remove-PSDrive` cmdlet deletes temporary PowerShell drives that were created by using the `New-PSDrive` cmdlet.</span></span>

<span data-ttu-id="0683b-110">Ab Windows PowerShell 3,0 werden `Remove-PSDrive` von auch zugeordnete Netzwerklaufwerke getrennt, einschließlich, aber nicht beschränkt auf Laufwerke, die mit dem- `Persist` Parameter von erstellt wurden `New-PSDrive` .</span><span class="sxs-lookup"><span data-stu-id="0683b-110">Beginning in Windows PowerShell 3.0, `Remove-PSDrive` also disconnects mapped network drives, including, but not limited to, drives created by using the `Persist` parameter of `New-PSDrive`.</span></span>

<span data-ttu-id="0683b-111">`Remove-PSDrive` physische oder logische Windows-Laufwerke können nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="0683b-111">`Remove-PSDrive` cannot delete Windows physical or logical drives.</span></span>

<span data-ttu-id="0683b-112">Ab Windows PowerShell 3,0 wird von PowerShell automatisch ein PSDrive zum Dateisystem hinzugefügt, das das neue Laufwerk darstellt, wenn ein externes Laufwerk mit dem Computer verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="0683b-112">Beginning in Windows PowerShell 3.0, when an external drive is connected to the computer, PowerShell automatically adds a PSDrive to the file system that represents the new drive.</span></span>
<span data-ttu-id="0683b-113">PowerShell muss nicht neu gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="0683b-113">You do not need to restart PowerShell.</span></span>
<span data-ttu-id="0683b-114">Ebenso wird beim Trennen eines externen Laufwerks mit dem Computer das PSDrive, das das entfernte Laufwerk darstellt, von PowerShell automatisch gelöscht.</span><span class="sxs-lookup"><span data-stu-id="0683b-114">Similarly, when an external drive is disconnected from the computer, PowerShell automatically deletes the PSDrive that represents the removed drive.</span></span>

## <span data-ttu-id="0683b-115">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="0683b-115">EXAMPLES</span></span>

### <span data-ttu-id="0683b-116">Beispiel 1: Entfernen eines Dateisystem Laufwerks</span><span class="sxs-lookup"><span data-stu-id="0683b-116">Example 1: Remove a file system drive</span></span>

<span data-ttu-id="0683b-117">Mit diesem Befehl wird ein temporäres Dateisystemlaufwerk namens %%amp;quot;smp%%amp;quot; entfernt.</span><span class="sxs-lookup"><span data-stu-id="0683b-117">This command removes a temporary file system drive named "smp".</span></span>

```powershell
Remove-PSDrive -Name smp
```

### <span data-ttu-id="0683b-118">Beispiel 2: Entfernen von zugeordneten Netzlaufwerken</span><span class="sxs-lookup"><span data-stu-id="0683b-118">Example 2: Remove mapped network drives</span></span>

<span data-ttu-id="0683b-119">Dieser Befehl verwendet `Remove-PSDrive` , um die Verbindung zwischen den X: und S: zugeordneten Netzwerklaufwerken zu trennen.</span><span class="sxs-lookup"><span data-stu-id="0683b-119">This command uses `Remove-PSDrive` to disconnect the X: and S: mapped network drives.</span></span>

```powershell
Get-PSDrive X, S | Remove-PSDrive
```

## <span data-ttu-id="0683b-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0683b-120">PARAMETERS</span></span>

### <span data-ttu-id="0683b-121">-Force</span><span class="sxs-lookup"><span data-stu-id="0683b-121">-Force</span></span>

<span data-ttu-id="0683b-122">Entfernt das aktuelle PowerShell-Laufwerk.</span><span class="sxs-lookup"><span data-stu-id="0683b-122">Removes the current PowerShell drive.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0683b-123">-LiteralName</span><span class="sxs-lookup"><span data-stu-id="0683b-123">-LiteralName</span></span>

<span data-ttu-id="0683b-124">Gibt den Namen des Laufwerks an.</span><span class="sxs-lookup"><span data-stu-id="0683b-124">Specifies the name of the drive.</span></span>

<span data-ttu-id="0683b-125">Der Wert von **LiteralName** wird genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="0683b-125">The value of **LiteralName** is used exactly as typed.</span></span>
<span data-ttu-id="0683b-126">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="0683b-126">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="0683b-127">Wenn der Name Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen (') einschließen.</span><span class="sxs-lookup"><span data-stu-id="0683b-127">If the name includes escape characters, enclose it in single quotation marks (').</span></span>
<span data-ttu-id="0683b-128">Einfache Anführungszeichen weisen PowerShell an, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="0683b-128">Single quotation marks instruct PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="0683b-129">-Name</span><span class="sxs-lookup"><span data-stu-id="0683b-129">-Name</span></span>

<span data-ttu-id="0683b-130">Gibt die Namen der zu entfernenden Laufwerke an.</span><span class="sxs-lookup"><span data-stu-id="0683b-130">Specifies the names of the drives to remove.</span></span>
<span data-ttu-id="0683b-131">Geben Sie keinen Doppelpunkt (:) nach dem Laufwerknamen ein.</span><span class="sxs-lookup"><span data-stu-id="0683b-131">Do not type a colon (:) after the drive name.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="0683b-132">-Psprovider</span><span class="sxs-lookup"><span data-stu-id="0683b-132">-PSProvider</span></span>

<span data-ttu-id="0683b-133">Gibt ein Array von **psprovider** -Objekten an.</span><span class="sxs-lookup"><span data-stu-id="0683b-133">Specifies an array of **PSProvider** objects.</span></span>
<span data-ttu-id="0683b-134">Mit diesem Cmdlet werden alle Laufwerke, die dem angegebenen PowerShell-Anbieter zugeordnet sind, entfernt und getrennt.</span><span class="sxs-lookup"><span data-stu-id="0683b-134">This cmdlet removes and disconnects all of the drives associated with the specified PowerShell provider.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="0683b-135">-Bereich</span><span class="sxs-lookup"><span data-stu-id="0683b-135">-Scope</span></span>

<span data-ttu-id="0683b-136">Gibt einen Bereich für das Laufwerk an.</span><span class="sxs-lookup"><span data-stu-id="0683b-136">Specifies a scope for the drive.</span></span>
<span data-ttu-id="0683b-137">Die zulässigen Werte für diesen Parameter lauten: Global, local und Script oder eine Zahl relativ zum aktuellen Bereich.</span><span class="sxs-lookup"><span data-stu-id="0683b-137">The acceptable values for this parameter are: Global, Local, and Script, or a number relative to the current scope.</span></span> <span data-ttu-id="0683b-138">Bereiche mit der Zahl 0 bis zur Anzahl der Bereiche.</span><span class="sxs-lookup"><span data-stu-id="0683b-138">Scopes number 0 through the number of scopes.</span></span> <span data-ttu-id="0683b-139">Die aktuelle Bereichs Nummer ist 0 und das übergeordnete Element ist 1.</span><span class="sxs-lookup"><span data-stu-id="0683b-139">The current scope number is 0 and its parent is 1.</span></span>
<span data-ttu-id="0683b-140">Weitere Informationen finden Sie unter [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="0683b-140">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Local
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="0683b-141">-Confirm</span><span class="sxs-lookup"><span data-stu-id="0683b-141">-Confirm</span></span>

<span data-ttu-id="0683b-142">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="0683b-142">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="0683b-143">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="0683b-143">-WhatIf</span></span>

<span data-ttu-id="0683b-144">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0683b-144">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="0683b-145">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="0683b-145">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="0683b-146">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0683b-146">CommonParameters</span></span>

<span data-ttu-id="0683b-147">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0683b-147">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0683b-148">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="0683b-148">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="0683b-149">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="0683b-149">INPUTS</span></span>

### <span data-ttu-id="0683b-150">System.Management.Automation.PSDrivin FO</span><span class="sxs-lookup"><span data-stu-id="0683b-150">System.Management.Automation.PSDriveInfo</span></span>

<span data-ttu-id="0683b-151">Sie können ein Laufwerks Objekt, z. b. ein vom `Get-PSDrive` Cmdlet, an das `Remove-PSDrive` Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="0683b-151">You can pipe a drive object, such as one from the `Get-PSDrive` cmdlet, to the `Remove-PSDrive` cmdlet.</span></span>

## <span data-ttu-id="0683b-152">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="0683b-152">OUTPUTS</span></span>

### <span data-ttu-id="0683b-153">Keine</span><span class="sxs-lookup"><span data-stu-id="0683b-153">None</span></span>

<span data-ttu-id="0683b-154">Dieses Cmdlet gibt keine Ausgabe zurück.</span><span class="sxs-lookup"><span data-stu-id="0683b-154">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="0683b-155">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="0683b-155">NOTES</span></span>

- <span data-ttu-id="0683b-156">Das `Remove-PSDrive` Cmdlet ist für die Arbeit mit den Daten konzipiert, die von einem beliebigen PowerShell-Anbieter verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="0683b-156">The `Remove-PSDrive` cmdlet is designed to work with the data exposed by any PowerShell provider.</span></span> <span data-ttu-id="0683b-157">Führen Sie die Anbieter in Ihrer Sitzung mithilfe des Cmdlets `Get-PSProvider` auf.</span><span class="sxs-lookup"><span data-stu-id="0683b-157">To list the providers in your session, use the `Get-PSProvider` cmdlet.</span></span> <span data-ttu-id="0683b-158">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="0683b-158">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="0683b-159">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="0683b-159">RELATED LINKS</span></span>

[<span data-ttu-id="0683b-160">Get-PSDrive</span><span class="sxs-lookup"><span data-stu-id="0683b-160">Get-PSDrive</span></span>](Get-PSDrive.md)

[<span data-ttu-id="0683b-161">New-PSDrive</span><span class="sxs-lookup"><span data-stu-id="0683b-161">New-PSDrive</span></span>](New-PSDrive.md)

[<span data-ttu-id="0683b-162">about_Providers</span><span class="sxs-lookup"><span data-stu-id="0683b-162">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

