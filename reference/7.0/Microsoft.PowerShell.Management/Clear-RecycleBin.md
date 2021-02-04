---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 01/29/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/clear-recyclebin?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-RecycleBin
ms.openlocfilehash: 4fde991ea99b46b96d0058334419ef4782a9adac
ms.sourcegitcommit: 81558c2adb9d109946a027e5b96e4d24b3b13747
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2021
ms.locfileid: "99098644"
---
# <span data-ttu-id="95bad-102">Clear-RecycleBin</span><span class="sxs-lookup"><span data-stu-id="95bad-102">Clear-RecycleBin</span></span>

## <span data-ttu-id="95bad-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="95bad-103">SYNOPSIS</span></span>
<span data-ttu-id="95bad-104">Löscht den Inhalt eines Papierkorbs.</span><span class="sxs-lookup"><span data-stu-id="95bad-104">Clears the contents of a recycle bin.</span></span>

## <span data-ttu-id="95bad-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="95bad-105">SYNTAX</span></span>

### <span data-ttu-id="95bad-106">Alle</span><span class="sxs-lookup"><span data-stu-id="95bad-106">All</span></span>

```
Clear-RecycleBin [[-DriveLetter] <String[]>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="95bad-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="95bad-107">DESCRIPTION</span></span>

<span data-ttu-id="95bad-108">`Clear-RecycleBin`Mit dem-Cmdlet wird der Inhalt des Papierkorbs eines Computers gelöscht.</span><span class="sxs-lookup"><span data-stu-id="95bad-108">The `Clear-RecycleBin` cmdlet deletes the content of a computer's recycle bin.</span></span> <span data-ttu-id="95bad-109">Diese Aktion ähnelt der Verwendung des **leeren** Windows-Papierkorbs.</span><span class="sxs-lookup"><span data-stu-id="95bad-109">This action is like using Windows **Empty Recycle Bin**.</span></span>

<span data-ttu-id="95bad-110">Dieses Cmdlet wurde in PowerShell 7 gelesen.</span><span class="sxs-lookup"><span data-stu-id="95bad-110">This cmdlet was readded in PowerShell 7.</span></span>

## <span data-ttu-id="95bad-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="95bad-111">EXAMPLES</span></span>

### <span data-ttu-id="95bad-112">1: alle Papierbehälter löschen</span><span class="sxs-lookup"><span data-stu-id="95bad-112">1: Clear all recycle bins</span></span>

<span data-ttu-id="95bad-113">In diesem Beispiel werden alle Papierbehälter des lokalen Computers gelöscht.</span><span class="sxs-lookup"><span data-stu-id="95bad-113">In this example, all the local computer's recycle bins are cleared.</span></span>

```powershell
Clear-RecycleBin
```

```Output
Confirm
Are you sure you want to perform this action?
Performing the operation "Clear-RecycleBin" on target "All of the contents of the Recycle Bin".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="95bad-114">`Clear-RecycleBin` fordert den Benutzer zur Bestätigung auf, alle Papierkorb auf dem lokalen Computer zu löschen.</span><span class="sxs-lookup"><span data-stu-id="95bad-114">`Clear-RecycleBin` prompts the user for confirmation to clear all recycle bins on the local computer.</span></span>

### <span data-ttu-id="95bad-115">2: einen angegebenen Papierkorb löschen</span><span class="sxs-lookup"><span data-stu-id="95bad-115">2: Clear a specified recycle bin</span></span>

<span data-ttu-id="95bad-116">In diesem Beispiel wird der Papierkorb für einen angegebenen Laufwerk Buchstaben gelöscht.</span><span class="sxs-lookup"><span data-stu-id="95bad-116">This example clears the recycle bin for a specified drive letter.</span></span>

```powershell
Clear-RecycleBin -DriveLetter C
```

<span data-ttu-id="95bad-117">`Clear-RecycleBin` verwendet den **DriveLetter** -Parameter, um den Papierkorb auf dem **C** -Volume anzugeben.</span><span class="sxs-lookup"><span data-stu-id="95bad-117">`Clear-RecycleBin` uses the **DriveLetter** parameter to specify the recycle bin on the **C** volume.</span></span> <span data-ttu-id="95bad-118">Der Benutzer wird zur Bestätigung aufgefordert, den Befehl auszuführen.</span><span class="sxs-lookup"><span data-stu-id="95bad-118">The user is prompted for confirmation to run the command.</span></span>

### <span data-ttu-id="95bad-119">3: alle Papierkorb ohne Bestätigung löschen</span><span class="sxs-lookup"><span data-stu-id="95bad-119">3: Clear all recycle bins without confirmation</span></span>

<span data-ttu-id="95bad-120">In diesem Beispiel wird nicht zur Bestätigung aufgefordert, die Papierbehälter des lokalen Computers zu löschen.</span><span class="sxs-lookup"><span data-stu-id="95bad-120">This example doesn't prompt for confirmation to clear the local computer's recycle bins.</span></span>

```powershell
Clear-RecycleBin -Force
```

<span data-ttu-id="95bad-121">`Clear-RecycleBin` in wird der **Force** -Parameter verwendet, und der Benutzer wird nicht zur Bestätigung aufgefordert, alle Papierkorb auf dem lokalen Computer zu löschen.</span><span class="sxs-lookup"><span data-stu-id="95bad-121">`Clear-RecycleBin` uses the **Force** parameter and doesn't prompt the user for confirmation to clear all recycle bins on the local computer.</span></span>

<span data-ttu-id="95bad-122">Eine Alternative besteht darin, `-Force` durch zu ersetzen `-Confirm:$false` .</span><span class="sxs-lookup"><span data-stu-id="95bad-122">An alternative is to replace `-Force` with `-Confirm:$false`.</span></span>

## <span data-ttu-id="95bad-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="95bad-123">PARAMETERS</span></span>

### <span data-ttu-id="95bad-124">-DriveLetter</span><span class="sxs-lookup"><span data-stu-id="95bad-124">-DriveLetter</span></span>

<span data-ttu-id="95bad-125">Gibt den Papierkorb zum Löschen eines einzelnen Laufwerk Buchstabens oder eines Arrays von Laufwerk Buchstaben an.</span><span class="sxs-lookup"><span data-stu-id="95bad-125">Specifies the recycle bin to clear for a single drive letter or an array of drive letters.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="95bad-126">-Force</span><span class="sxs-lookup"><span data-stu-id="95bad-126">-Force</span></span>

<span data-ttu-id="95bad-127">Gibt an, dass der Benutzer nicht zur Bestätigung aufgefordert wird, einen Papierkorb zu löschen.</span><span class="sxs-lookup"><span data-stu-id="95bad-127">Specifies that the user isn't prompted for confirmation to clear a recycle bin.</span></span> <span data-ttu-id="95bad-128">Der **Force** -Parameter überschreibt auch die Parameter **WhatIf** und **Confirm** .</span><span class="sxs-lookup"><span data-stu-id="95bad-128">The **Force** parameter also overrides the **WhatIf** and **Confirm** parameters.</span></span>

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

### <span data-ttu-id="95bad-129">-Confirm</span><span class="sxs-lookup"><span data-stu-id="95bad-129">-Confirm</span></span>

<span data-ttu-id="95bad-130">Fordert vor dem Ausführen des Cmdlets zur Bestätigung des Benutzers auf.</span><span class="sxs-lookup"><span data-stu-id="95bad-130">Prompts for user confirmation before running the cmdlet.</span></span> <span data-ttu-id="95bad-131">Der Benutzer wird auch dann zur Bestätigung aufgefordert, wenn der **Confirm** -Parameter nicht angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="95bad-131">The user is prompted for confirmation even if the **Confirm** parameter isn't specified.</span></span>

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

### <span data-ttu-id="95bad-132">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="95bad-132">-WhatIf</span></span>

<span data-ttu-id="95bad-133">Zeigt, was geschieht, wenn ausgeführt wird `Clear-RecycleBin` .</span><span class="sxs-lookup"><span data-stu-id="95bad-133">Shows what would happen if `Clear-RecycleBin` runs.</span></span> <span data-ttu-id="95bad-134">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="95bad-134">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="95bad-135">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="95bad-135">CommonParameters</span></span>

<span data-ttu-id="95bad-136">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="95bad-136">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="95bad-137">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="95bad-137">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="95bad-138">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="95bad-138">INPUTS</span></span>

## <span data-ttu-id="95bad-139">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="95bad-139">OUTPUTS</span></span>

### <span data-ttu-id="95bad-140">Keine</span><span class="sxs-lookup"><span data-stu-id="95bad-140">None</span></span>

## <span data-ttu-id="95bad-141">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="95bad-141">NOTES</span></span>

<span data-ttu-id="95bad-142">Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="95bad-142">This cmdlet is only available on Windows platforms.</span></span>

## <span data-ttu-id="95bad-143">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="95bad-143">RELATED LINKS</span></span>
