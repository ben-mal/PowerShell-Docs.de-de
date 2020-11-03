---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-psdrive?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PSDrive
ms.openlocfilehash: 6f34e670a29ee65e4a37314472f89c463f0a49ab
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216943"
---
# <span data-ttu-id="e45c1-103">Remove-PSDrive</span><span class="sxs-lookup"><span data-stu-id="e45c1-103">Remove-PSDrive</span></span>

## <span data-ttu-id="e45c1-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="e45c1-104">SYNOPSIS</span></span>
<span data-ttu-id="e45c1-105">Löscht temporäre PowerShell-Laufwerke und trennt die Verbindung mit zugeordneten Netzlaufwerken.</span><span class="sxs-lookup"><span data-stu-id="e45c1-105">Deletes temporary PowerShell drives and disconnects mapped network drives.</span></span>

## <span data-ttu-id="e45c1-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e45c1-106">SYNTAX</span></span>

### <span data-ttu-id="e45c1-107">Name (Standard)</span><span class="sxs-lookup"><span data-stu-id="e45c1-107">Name (Default)</span></span>

```
Remove-PSDrive [-Name] <String[]> [-PSProvider <String[]>] [-Scope <String>] [-Force]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="e45c1-108">LiteralName</span><span class="sxs-lookup"><span data-stu-id="e45c1-108">LiteralName</span></span>

```
Remove-PSDrive [-LiteralName] <String[]> [-PSProvider <String[]>] [-Scope <String>] [-Force]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="e45c1-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e45c1-109">DESCRIPTION</span></span>

<span data-ttu-id="e45c1-110">Mit dem- `Remove-PSDrive` Cmdlet werden temporäre PowerShell-Laufwerke gelöscht, die mithilfe des- `New-PSDrive` Cmdlets erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="e45c1-110">The `Remove-PSDrive` cmdlet deletes temporary PowerShell drives that were created by using the `New-PSDrive` cmdlet.</span></span>

<span data-ttu-id="e45c1-111">Ab Windows PowerShell 3,0 werden `Remove-PSDrive` von auch zugeordnete Netzwerklaufwerke getrennt, einschließlich, aber nicht beschränkt auf Laufwerke, die mit dem- `Persist` Parameter von erstellt wurden `New-PSDrive` .</span><span class="sxs-lookup"><span data-stu-id="e45c1-111">Beginning in Windows PowerShell 3.0, `Remove-PSDrive` also disconnects mapped network drives, including, but not limited to, drives created by using the `Persist` parameter of `New-PSDrive`.</span></span>

<span data-ttu-id="e45c1-112">`Remove-PSDrive` physische oder logische Windows-Laufwerke können nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="e45c1-112">`Remove-PSDrive` cannot delete Windows physical or logical drives.</span></span>

<span data-ttu-id="e45c1-113">Ab Windows PowerShell 3,0 wird von PowerShell automatisch ein PSDrive zum Dateisystem hinzugefügt, das das neue Laufwerk darstellt, wenn ein externes Laufwerk mit dem Computer verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="e45c1-113">Beginning in Windows PowerShell 3.0, when an external drive is connected to the computer, PowerShell automatically adds a PSDrive to the file system that represents the new drive.</span></span>
<span data-ttu-id="e45c1-114">PowerShell muss nicht neu gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="e45c1-114">You do not need to restart PowerShell.</span></span>
<span data-ttu-id="e45c1-115">Ebenso wird beim Trennen eines externen Laufwerks mit dem Computer das PSDrive, das das entfernte Laufwerk darstellt, von PowerShell automatisch gelöscht.</span><span class="sxs-lookup"><span data-stu-id="e45c1-115">Similarly, when an external drive is disconnected from the computer, PowerShell automatically deletes the PSDrive that represents the removed drive.</span></span>

## <span data-ttu-id="e45c1-116">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="e45c1-116">EXAMPLES</span></span>

### <span data-ttu-id="e45c1-117">Beispiel 1: Entfernen eines Dateisystem Laufwerks</span><span class="sxs-lookup"><span data-stu-id="e45c1-117">Example 1: Remove a file system drive</span></span>

<span data-ttu-id="e45c1-118">Mit diesem Befehl wird ein temporäres Dateisystemlaufwerk namens %%amp;quot;smp%%amp;quot; entfernt.</span><span class="sxs-lookup"><span data-stu-id="e45c1-118">This command removes a temporary file system drive named "smp".</span></span>

```powershell
Remove-PSDrive -Name smp
```

### <span data-ttu-id="e45c1-119">Beispiel 2: Entfernen von zugeordneten Netzlaufwerken</span><span class="sxs-lookup"><span data-stu-id="e45c1-119">Example 2: Remove mapped network drives</span></span>

<span data-ttu-id="e45c1-120">Dieser Befehl verwendet `Remove-PSDrive` , um die Verbindung zwischen den X: und S: zugeordneten Netzwerklaufwerken zu trennen.</span><span class="sxs-lookup"><span data-stu-id="e45c1-120">This command uses `Remove-PSDrive` to disconnect the X: and S: mapped network drives.</span></span>

```powershell
Get-PSDrive X, S | Remove-PSDrive
```

## <span data-ttu-id="e45c1-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e45c1-121">PARAMETERS</span></span>

### <span data-ttu-id="e45c1-122">-Force</span><span class="sxs-lookup"><span data-stu-id="e45c1-122">-Force</span></span>

<span data-ttu-id="e45c1-123">Entfernt das aktuelle PowerShell-Laufwerk.</span><span class="sxs-lookup"><span data-stu-id="e45c1-123">Removes the current PowerShell drive.</span></span>

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

### <span data-ttu-id="e45c1-124">-LiteralName</span><span class="sxs-lookup"><span data-stu-id="e45c1-124">-LiteralName</span></span>

<span data-ttu-id="e45c1-125">Gibt den Namen des Laufwerks an.</span><span class="sxs-lookup"><span data-stu-id="e45c1-125">Specifies the name of the drive.</span></span>

<span data-ttu-id="e45c1-126">Der Wert von **LiteralName** wird genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="e45c1-126">The value of **LiteralName** is used exactly as typed.</span></span>
<span data-ttu-id="e45c1-127">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="e45c1-127">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="e45c1-128">Wenn der Name Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen (') einschließen.</span><span class="sxs-lookup"><span data-stu-id="e45c1-128">If the name includes escape characters, enclose it in single quotation marks (').</span></span>
<span data-ttu-id="e45c1-129">Einfache Anführungszeichen weisen PowerShell an, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="e45c1-129">Single quotation marks instruct PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="e45c1-130">-Name</span><span class="sxs-lookup"><span data-stu-id="e45c1-130">-Name</span></span>

<span data-ttu-id="e45c1-131">Gibt die Namen der zu entfernenden Laufwerke an.</span><span class="sxs-lookup"><span data-stu-id="e45c1-131">Specifies the names of the drives to remove.</span></span>
<span data-ttu-id="e45c1-132">Geben Sie keinen Doppelpunkt (:) nach dem Laufwerknamen ein.</span><span class="sxs-lookup"><span data-stu-id="e45c1-132">Do not type a colon (:) after the drive name.</span></span>

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

### <span data-ttu-id="e45c1-133">-Psprovider</span><span class="sxs-lookup"><span data-stu-id="e45c1-133">-PSProvider</span></span>

<span data-ttu-id="e45c1-134">Gibt ein Array von **psprovider** -Objekten an.</span><span class="sxs-lookup"><span data-stu-id="e45c1-134">Specifies an array of **PSProvider** objects.</span></span>
<span data-ttu-id="e45c1-135">Mit diesem Cmdlet werden alle Laufwerke, die dem angegebenen PowerShell-Anbieter zugeordnet sind, entfernt und getrennt.</span><span class="sxs-lookup"><span data-stu-id="e45c1-135">This cmdlet removes and disconnects all of the drives associated with the specified PowerShell provider.</span></span>

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

### <span data-ttu-id="e45c1-136">-Bereich</span><span class="sxs-lookup"><span data-stu-id="e45c1-136">-Scope</span></span>

<span data-ttu-id="e45c1-137">Gibt einen Bereich für das Laufwerk an.</span><span class="sxs-lookup"><span data-stu-id="e45c1-137">Specifies a scope for the drive.</span></span>
<span data-ttu-id="e45c1-138">Die zulässigen Werte für diesen Parameter lauten: Global, local und Script oder eine Zahl relativ zum aktuellen Bereich.</span><span class="sxs-lookup"><span data-stu-id="e45c1-138">The acceptable values for this parameter are: Global, Local, and Script, or a number relative to the current scope.</span></span> <span data-ttu-id="e45c1-139">Bereiche mit der Zahl 0 bis zur Anzahl der Bereiche.</span><span class="sxs-lookup"><span data-stu-id="e45c1-139">Scopes number 0 through the number of scopes.</span></span> <span data-ttu-id="e45c1-140">Die aktuelle Bereichs Nummer ist 0 und das übergeordnete Element ist 1.</span><span class="sxs-lookup"><span data-stu-id="e45c1-140">The current scope number is 0 and its parent is 1.</span></span>
<span data-ttu-id="e45c1-141">Weitere Informationen finden Sie unter [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="e45c1-141">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span></span>

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

### <span data-ttu-id="e45c1-142">-Confirm</span><span class="sxs-lookup"><span data-stu-id="e45c1-142">-Confirm</span></span>

<span data-ttu-id="e45c1-143">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="e45c1-143">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="e45c1-144">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="e45c1-144">-WhatIf</span></span>

<span data-ttu-id="e45c1-145">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e45c1-145">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="e45c1-146">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e45c1-146">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="e45c1-147">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e45c1-147">CommonParameters</span></span>

<span data-ttu-id="e45c1-148">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e45c1-148">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e45c1-149">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="e45c1-149">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="e45c1-150">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="e45c1-150">INPUTS</span></span>

### <span data-ttu-id="e45c1-151">System.Management.Automation.PSDrivin FO</span><span class="sxs-lookup"><span data-stu-id="e45c1-151">System.Management.Automation.PSDriveInfo</span></span>

<span data-ttu-id="e45c1-152">Sie können ein Laufwerks Objekt, z. b. ein vom `Get-PSDrive` Cmdlet, an das `Remove-PSDrive` Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="e45c1-152">You can pipe a drive object, such as one from the `Get-PSDrive` cmdlet, to the `Remove-PSDrive` cmdlet.</span></span>

## <span data-ttu-id="e45c1-153">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="e45c1-153">OUTPUTS</span></span>

### <span data-ttu-id="e45c1-154">Keine</span><span class="sxs-lookup"><span data-stu-id="e45c1-154">None</span></span>

<span data-ttu-id="e45c1-155">Dieses Cmdlet gibt keine Ausgabe zurück.</span><span class="sxs-lookup"><span data-stu-id="e45c1-155">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="e45c1-156">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="e45c1-156">NOTES</span></span>

- <span data-ttu-id="e45c1-157">Das `Remove-PSDrive` Cmdlet ist für die Arbeit mit den Daten konzipiert, die von einem beliebigen PowerShell-Anbieter verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="e45c1-157">The `Remove-PSDrive` cmdlet is designed to work with the data exposed by any PowerShell provider.</span></span> <span data-ttu-id="e45c1-158">Führen Sie die Anbieter in Ihrer Sitzung mithilfe des Cmdlets `Get-PSProvider` auf.</span><span class="sxs-lookup"><span data-stu-id="e45c1-158">To list the providers in your session, use the `Get-PSProvider` cmdlet.</span></span> <span data-ttu-id="e45c1-159">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="e45c1-159">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="e45c1-160">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="e45c1-160">RELATED LINKS</span></span>

[<span data-ttu-id="e45c1-161">Get-PSDrive</span><span class="sxs-lookup"><span data-stu-id="e45c1-161">Get-PSDrive</span></span>](Get-PSDrive.md)

[<span data-ttu-id="e45c1-162">New-PSDrive</span><span class="sxs-lookup"><span data-stu-id="e45c1-162">New-PSDrive</span></span>](New-PSDrive.md)

[<span data-ttu-id="e45c1-163">about_Providers</span><span class="sxs-lookup"><span data-stu-id="e45c1-163">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
