---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/24/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/remove-alias?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Alias
ms.openlocfilehash: 08ef751e0573f896c5f63737b00b55ab77ae73e3
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216063"
---
# <span data-ttu-id="af10c-103">Remove-Alias</span><span class="sxs-lookup"><span data-stu-id="af10c-103">Remove-Alias</span></span>

## <span data-ttu-id="af10c-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="af10c-104">SYNOPSIS</span></span>
<span data-ttu-id="af10c-105">Entfernt einen Alias aus der aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="af10c-105">Remove an alias from the current session.</span></span>

## <span data-ttu-id="af10c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="af10c-106">SYNTAX</span></span>

### <span data-ttu-id="af10c-107">Standard (Standard)</span><span class="sxs-lookup"><span data-stu-id="af10c-107">Default (Default)</span></span>

```
Remove-Alias [-Name] <String[]> [-Scope <String>] [-Force] [<CommonParameters>]
```

## <span data-ttu-id="af10c-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="af10c-108">DESCRIPTION</span></span>

<span data-ttu-id="af10c-109">Mit dem- `Remove-Alias` Cmdlet wird ein Alias aus der aktuellen PowerShell-Sitzung entfernt.</span><span class="sxs-lookup"><span data-stu-id="af10c-109">The `Remove-Alias` cmdlet removes an alias from the current PowerShell session.</span></span> <span data-ttu-id="af10c-110">Verwenden Sie den **Force** -Parameter, um einen Alias **zu entfernen** , bei dem die **Option Option** auf "schreibgeschützt" festgelegt</span><span class="sxs-lookup"><span data-stu-id="af10c-110">To remove an alias with the **Option** property set to **ReadOnly** , use the **Force** parameter.</span></span>

<span data-ttu-id="af10c-111">Das `Remove-Alias` Cmdlet wurde in PowerShell 6,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="af10c-111">The `Remove-Alias` cmdlet was introduced in PowerShell 6.0.</span></span>

## <span data-ttu-id="af10c-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="af10c-112">EXAMPLES</span></span>

### <span data-ttu-id="af10c-113">Beispiel 1: Entfernen eines Alias</span><span class="sxs-lookup"><span data-stu-id="af10c-113">Example 1 - Remove an alias</span></span>

<span data-ttu-id="af10c-114">In diesem Beispiel wird ein Alias mit dem Namen entfernt `del` , der das `Remove-Item` Cmdlet darstellt.</span><span class="sxs-lookup"><span data-stu-id="af10c-114">This example removes an alias named `del` that represents the `Remove-Item` cmdlet.</span></span>

```powershell
Remove-Alias -Name del
```

### <span data-ttu-id="af10c-115">Beispiel 2: Entfernen aller nicht konstanten Aliase</span><span class="sxs-lookup"><span data-stu-id="af10c-115">Example 2 - Remove all non-Constant aliases</span></span>

<span data-ttu-id="af10c-116">In diesem Beispiel werden alle Aliase aus der aktuellen PowerShell-Sitzung entfernt, mit Ausnahme von Aliasen, bei denen die **options** -Eigenschaft auf **Constant** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="af10c-116">This example removes all aliases from the current PowerShell session, except for aliases with the **Options** property set to **Constant**.</span></span> <span data-ttu-id="af10c-117">Nachdem der Befehl ausgeführt wurde, sind die Aliase in anderen PowerShell-Sitzungen oder neuen PowerShell-Sitzungen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="af10c-117">After the command is run, the aliases are available in other PowerShell sessions or new PowerShell sessions.</span></span>

```powershell
Get-Alias | Where-Object { $_.Options -NE "Constant" } | Remove-Alias -Force
```

<span data-ttu-id="af10c-118">`Get-Alias` Ruft alle Aliase in der PowerShell-Sitzung ab und sendet die Objekte in der Pipeline.</span><span class="sxs-lookup"><span data-stu-id="af10c-118">`Get-Alias` gets all the aliases in the PowerShell session and sends the objects down the pipeline.</span></span>
<span data-ttu-id="af10c-119">`Where-Object` verwendet einen Skriptblock, und die automatische Variable ( `$_` ) und die **options** -Eigenschaft stellen das aktuelle Pipeline Objekt dar.</span><span class="sxs-lookup"><span data-stu-id="af10c-119">`Where-Object` uses a script block, and the automatic variable (`$_`) and **Options** property represent the current pipeline object.</span></span> <span data-ttu-id="af10c-120">Der Parameter **ne** (nicht gleich) wählt Objekte aus, für die kein **options** Wert auf **Constant** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="af10c-120">The parameter **NE** (not equal), selects objects that don't have an **Options** value set to **Constant**.</span></span> <span data-ttu-id="af10c-121">`Remove-Alias` verwendet den **Force** -Parameter, um Aliase (einschließlich Schreib geschützter Aliase) aus der PowerShell-Sitzung zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="af10c-121">`Remove-Alias` uses the **Force** parameter to remove aliases, including read-only aliases, from the PowerShell session.</span></span>

## <span data-ttu-id="af10c-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="af10c-122">PARAMETERS</span></span>

### <span data-ttu-id="af10c-123">-Force</span><span class="sxs-lookup"><span data-stu-id="af10c-123">-Force</span></span>

<span data-ttu-id="af10c-124">Gibt an, dass das Cmdlet einen Alias entfernt, einschließlich Aliase, deren **options** - **Eigenschaft auf "** schreibgeschützt" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="af10c-124">Indicates that the cmdlet removes an alias, including aliases with the **Option** property set to **ReadOnly**.</span></span> <span data-ttu-id="af10c-125">Der **Force** -Parameter kann keinen Alias entfernen, bei dem die **options** -Eigenschaft auf **Constant** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="af10c-125">The **Force** parameter can't remove an alias with an **Option** property set to **Constant**.</span></span>

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

### <span data-ttu-id="af10c-126">-Name</span><span class="sxs-lookup"><span data-stu-id="af10c-126">-Name</span></span>

<span data-ttu-id="af10c-127">Gibt den Namen des zu entfernenden Alias an.</span><span class="sxs-lookup"><span data-stu-id="af10c-127">Specifies the name of the alias to remove.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="af10c-128">-Bereich</span><span class="sxs-lookup"><span data-stu-id="af10c-128">-Scope</span></span>

<span data-ttu-id="af10c-129">Wirkt sich nur auf die Aliase im angegebenen Bereich aus.</span><span class="sxs-lookup"><span data-stu-id="af10c-129">Affects only the aliases in the specified scope.</span></span> <span data-ttu-id="af10c-130">Der Standardbereich ist **local**.</span><span class="sxs-lookup"><span data-stu-id="af10c-130">The default scope is **Local**.</span></span> <span data-ttu-id="af10c-131">Weitere Informationen finden Sie unter [about_Scopes](../microsoft.powershell.core/about/about_scopes.md).</span><span class="sxs-lookup"><span data-stu-id="af10c-131">For more information, see [about_Scopes](../microsoft.powershell.core/about/about_scopes.md).</span></span>

<span data-ttu-id="af10c-132">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="af10c-132">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="af10c-133">Global</span><span class="sxs-lookup"><span data-stu-id="af10c-133">Global</span></span>
- <span data-ttu-id="af10c-134">Lokal</span><span class="sxs-lookup"><span data-stu-id="af10c-134">Local</span></span>
- <span data-ttu-id="af10c-135">Skript</span><span class="sxs-lookup"><span data-stu-id="af10c-135">Script</span></span>
- <span data-ttu-id="af10c-136">Eine Zahl relativ zum aktuellen Bereich (0 bis zur Anzahl der Bereiche, wobei 0 der aktuelle Bereich und 1 der übergeordnete Bereich ist)</span><span class="sxs-lookup"><span data-stu-id="af10c-136">A number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent)</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Local
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="af10c-137">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="af10c-137">CommonParameters</span></span>

<span data-ttu-id="af10c-138">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="af10c-138">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="af10c-139">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="af10c-139">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="af10c-140">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="af10c-140">INPUTS</span></span>

### <span data-ttu-id="af10c-141">System.String[]</span><span class="sxs-lookup"><span data-stu-id="af10c-141">System.String[]</span></span>

<span data-ttu-id="af10c-142">Sie können ein Alias Objekt an **Remove-Alias** übergeben.</span><span class="sxs-lookup"><span data-stu-id="af10c-142">You can pipe an alias object to **Remove-Alias**.</span></span>

## <span data-ttu-id="af10c-143">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="af10c-143">OUTPUTS</span></span>

### <span data-ttu-id="af10c-144">Keine</span><span class="sxs-lookup"><span data-stu-id="af10c-144">None</span></span>

<span data-ttu-id="af10c-145">Dieses Cmdlet gibt keine Ausgabe zurück.</span><span class="sxs-lookup"><span data-stu-id="af10c-145">This cmdlet doesn't return any output.</span></span>

## <span data-ttu-id="af10c-146">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="af10c-146">NOTES</span></span>

<span data-ttu-id="af10c-147">Änderungen wirken sich nur auf den aktuellen Bereich aus.</span><span class="sxs-lookup"><span data-stu-id="af10c-147">Changes only affect the current scope.</span></span> <span data-ttu-id="af10c-148">Fügen Sie Ihrem PowerShell-Profil einen **Remove-Alias-** Befehl hinzu, um einen Alias aus allen Sitzungen zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="af10c-148">To remove an alias from all sessions, add a **Remove-Alias** command to your PowerShell profile.</span></span>

<span data-ttu-id="af10c-149">Weitere Informationen finden Sie unter [about_Aliases](../microsoft.powershell.core/about/about_aliases.md).</span><span class="sxs-lookup"><span data-stu-id="af10c-149">For more information, see [about_Aliases](../microsoft.powershell.core/about/about_aliases.md).</span></span>

## <span data-ttu-id="af10c-150">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="af10c-150">RELATED LINKS</span></span>

[<span data-ttu-id="af10c-151">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="af10c-151">about_Automatic_Variables</span></span>](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)

[<span data-ttu-id="af10c-152">Export-Alias</span><span class="sxs-lookup"><span data-stu-id="af10c-152">Export-Alias</span></span>](Export-Alias.md)

[<span data-ttu-id="af10c-153">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="af10c-153">Get-Alias</span></span>](Get-Alias.md)

[<span data-ttu-id="af10c-154">Import-Alias</span><span class="sxs-lookup"><span data-stu-id="af10c-154">Import-Alias</span></span>](Import-Alias.md)

[<span data-ttu-id="af10c-155">New-Alias</span><span class="sxs-lookup"><span data-stu-id="af10c-155">New-Alias</span></span>](New-Alias.md)

[<span data-ttu-id="af10c-156">Set-Alias</span><span class="sxs-lookup"><span data-stu-id="af10c-156">Set-Alias</span></span>](Set-Alias.md)

[<span data-ttu-id="af10c-157">Where-Object</span><span class="sxs-lookup"><span data-stu-id="af10c-157">Where-Object</span></span>](../Microsoft.PowerShell.Core/Where-Object.md)
