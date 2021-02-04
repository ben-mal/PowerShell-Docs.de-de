---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 01/29/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/clear-recyclebin?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-RecycleBin
ms.openlocfilehash: f59cc9ff4e6d1b6579292c84f440bbbdd156b65c
ms.sourcegitcommit: 81558c2adb9d109946a027e5b96e4d24b3b13747
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2021
ms.locfileid: "99098562"
---
# <span data-ttu-id="9cca7-102">Clear-RecycleBin</span><span class="sxs-lookup"><span data-stu-id="9cca7-102">Clear-RecycleBin</span></span>

## <span data-ttu-id="9cca7-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="9cca7-103">SYNOPSIS</span></span>
<span data-ttu-id="9cca7-104">Löscht den Inhalt eines Papierkorbs.</span><span class="sxs-lookup"><span data-stu-id="9cca7-104">Clears the contents of a recycle bin.</span></span>

## <span data-ttu-id="9cca7-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9cca7-105">SYNTAX</span></span>

### <span data-ttu-id="9cca7-106">Alle</span><span class="sxs-lookup"><span data-stu-id="9cca7-106">All</span></span>

```
Clear-RecycleBin [[-DriveLetter] <String[]>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="9cca7-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9cca7-107">DESCRIPTION</span></span>

<span data-ttu-id="9cca7-108">`Clear-RecycleBin`Mit dem-Cmdlet wird der Inhalt des Papierkorbs eines Computers gelöscht.</span><span class="sxs-lookup"><span data-stu-id="9cca7-108">The `Clear-RecycleBin` cmdlet deletes the content of a computer's recycle bin.</span></span> <span data-ttu-id="9cca7-109">Diese Aktion ähnelt der Verwendung des **leeren** Windows-Papierkorbs.</span><span class="sxs-lookup"><span data-stu-id="9cca7-109">This action is like using Windows **Empty Recycle Bin**.</span></span>

## <span data-ttu-id="9cca7-110">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="9cca7-110">EXAMPLES</span></span>

### <span data-ttu-id="9cca7-111">1: alle Papierbehälter löschen</span><span class="sxs-lookup"><span data-stu-id="9cca7-111">1: Clear all recycle bins</span></span>

<span data-ttu-id="9cca7-112">In diesem Beispiel werden alle Papierbehälter des lokalen Computers gelöscht.</span><span class="sxs-lookup"><span data-stu-id="9cca7-112">In this example, all the local computer's recycle bins are cleared.</span></span>

```powershell
Clear-RecycleBin
```

```Output
Confirm
Are you sure you want to perform this action?
Performing the operation "Clear-RecycleBin" on target "All of the contents of the Recycle Bin".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="9cca7-113">`Clear-RecycleBin` fordert den Benutzer zur Bestätigung auf, alle Papierkorb auf dem lokalen Computer zu löschen.</span><span class="sxs-lookup"><span data-stu-id="9cca7-113">`Clear-RecycleBin` prompts the user for confirmation to clear all recycle bins on the local computer.</span></span>

### <span data-ttu-id="9cca7-114">2: einen angegebenen Papierkorb löschen</span><span class="sxs-lookup"><span data-stu-id="9cca7-114">2: Clear a specified recycle bin</span></span>

<span data-ttu-id="9cca7-115">In diesem Beispiel wird der Papierkorb für einen angegebenen Laufwerk Buchstaben gelöscht.</span><span class="sxs-lookup"><span data-stu-id="9cca7-115">This example clears the recycle bin for a specified drive letter.</span></span>

```powershell
Clear-RecycleBin -DriveLetter C
```

<span data-ttu-id="9cca7-116">`Clear-RecycleBin` verwendet den **DriveLetter** -Parameter, um den Papierkorb auf dem **C** -Volume anzugeben.</span><span class="sxs-lookup"><span data-stu-id="9cca7-116">`Clear-RecycleBin` uses the **DriveLetter** parameter to specify the recycle bin on the **C** volume.</span></span> <span data-ttu-id="9cca7-117">Der Benutzer wird zur Bestätigung aufgefordert, den Befehl auszuführen.</span><span class="sxs-lookup"><span data-stu-id="9cca7-117">The user is prompted for confirmation to run the command.</span></span>

### <span data-ttu-id="9cca7-118">3: alle Papierkorb ohne Bestätigung löschen</span><span class="sxs-lookup"><span data-stu-id="9cca7-118">3: Clear all recycle bins without confirmation</span></span>

<span data-ttu-id="9cca7-119">In diesem Beispiel wird nicht zur Bestätigung aufgefordert, die Papierbehälter des lokalen Computers zu löschen.</span><span class="sxs-lookup"><span data-stu-id="9cca7-119">This example doesn't prompt for confirmation to clear the local computer's recycle bins.</span></span>

```powershell
Clear-RecycleBin -Force
```

<span data-ttu-id="9cca7-120">`Clear-RecycleBin` in wird der **Force** -Parameter verwendet, und der Benutzer wird nicht zur Bestätigung aufgefordert, alle Papierkorb auf dem lokalen Computer zu löschen.</span><span class="sxs-lookup"><span data-stu-id="9cca7-120">`Clear-RecycleBin` uses the **Force** parameter and doesn't prompt the user for confirmation to clear all recycle bins on the local computer.</span></span>

<span data-ttu-id="9cca7-121">Eine Alternative besteht darin, `-Force` durch zu ersetzen `-Confirm:$false` .</span><span class="sxs-lookup"><span data-stu-id="9cca7-121">An alternative is to replace `-Force` with `-Confirm:$false`.</span></span>

## <span data-ttu-id="9cca7-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9cca7-122">PARAMETERS</span></span>

### <span data-ttu-id="9cca7-123">-DriveLetter</span><span class="sxs-lookup"><span data-stu-id="9cca7-123">-DriveLetter</span></span>

<span data-ttu-id="9cca7-124">Gibt den Papierkorb zum Löschen eines einzelnen Laufwerk Buchstabens oder eines Arrays von Laufwerk Buchstaben an.</span><span class="sxs-lookup"><span data-stu-id="9cca7-124">Specifies the recycle bin to clear for a single drive letter or an array of drive letters.</span></span>

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

### <span data-ttu-id="9cca7-125">-Force</span><span class="sxs-lookup"><span data-stu-id="9cca7-125">-Force</span></span>

<span data-ttu-id="9cca7-126">Gibt an, dass der Benutzer nicht zur Bestätigung aufgefordert wird, einen Papierkorb zu löschen.</span><span class="sxs-lookup"><span data-stu-id="9cca7-126">Specifies that the user isn't prompted for confirmation to clear a recycle bin.</span></span> <span data-ttu-id="9cca7-127">Der **Force** -Parameter überschreibt auch die Parameter **WhatIf** und **Confirm** .</span><span class="sxs-lookup"><span data-stu-id="9cca7-127">The **Force** parameter also overrides the **WhatIf** and **Confirm** parameters.</span></span>

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

### <span data-ttu-id="9cca7-128">-Confirm</span><span class="sxs-lookup"><span data-stu-id="9cca7-128">-Confirm</span></span>

<span data-ttu-id="9cca7-129">Fordert vor dem Ausführen des Cmdlets zur Bestätigung des Benutzers auf.</span><span class="sxs-lookup"><span data-stu-id="9cca7-129">Prompts for user confirmation before running the cmdlet.</span></span> <span data-ttu-id="9cca7-130">Der Benutzer wird auch dann zur Bestätigung aufgefordert, wenn der **Confirm** -Parameter nicht angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="9cca7-130">The user is prompted for confirmation even if the **Confirm** parameter isn't specified.</span></span>

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

### <span data-ttu-id="9cca7-131">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="9cca7-131">-WhatIf</span></span>

<span data-ttu-id="9cca7-132">Zeigt, was geschieht, wenn ausgeführt wird `Clear-RecycleBin` .</span><span class="sxs-lookup"><span data-stu-id="9cca7-132">Shows what would happen if `Clear-RecycleBin` runs.</span></span> <span data-ttu-id="9cca7-133">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="9cca7-133">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="9cca7-134">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="9cca7-134">CommonParameters</span></span>

<span data-ttu-id="9cca7-135">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9cca7-135">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9cca7-136">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="9cca7-136">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9cca7-137">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="9cca7-137">INPUTS</span></span>

## <span data-ttu-id="9cca7-138">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="9cca7-138">OUTPUTS</span></span>

### <span data-ttu-id="9cca7-139">Keine</span><span class="sxs-lookup"><span data-stu-id="9cca7-139">None</span></span>

## <span data-ttu-id="9cca7-140">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="9cca7-140">NOTES</span></span>

## <span data-ttu-id="9cca7-141">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="9cca7-141">RELATED LINKS</span></span>
