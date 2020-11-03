---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 6/24/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/clear-recyclebin?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-RecycleBin
ms.openlocfilehash: 9314aaf7c444f9a1159b301135d4130737daa439
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215551"
---
# <span data-ttu-id="a5c91-103">Clear-RecycleBin</span><span class="sxs-lookup"><span data-stu-id="a5c91-103">Clear-RecycleBin</span></span>

## <span data-ttu-id="a5c91-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="a5c91-104">SYNOPSIS</span></span>
<span data-ttu-id="a5c91-105">Löscht den Inhalt eines Papierkorbs.</span><span class="sxs-lookup"><span data-stu-id="a5c91-105">Clears the contents of a recycle bin.</span></span>

## <span data-ttu-id="a5c91-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a5c91-106">SYNTAX</span></span>

### <span data-ttu-id="a5c91-107">Alle</span><span class="sxs-lookup"><span data-stu-id="a5c91-107">All</span></span>

```
Clear-RecycleBin [[-DriveLetter] <String[]>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="a5c91-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a5c91-108">DESCRIPTION</span></span>

<span data-ttu-id="a5c91-109">`Clear-RecycleBin`Mit dem-Cmdlet wird der Inhalt des Papierkorbs eines Computers gelöscht.</span><span class="sxs-lookup"><span data-stu-id="a5c91-109">The `Clear-RecycleBin` cmdlet deletes the content of a computer's recycle bin.</span></span> <span data-ttu-id="a5c91-110">Diese Aktion ähnelt der Verwendung des **leeren** Windows-Papierkorbs.</span><span class="sxs-lookup"><span data-stu-id="a5c91-110">This action is like using Windows **Empty Recycle Bin** .</span></span>

## <span data-ttu-id="a5c91-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="a5c91-111">EXAMPLES</span></span>

### <span data-ttu-id="a5c91-112">1: alle Papierbehälter löschen</span><span class="sxs-lookup"><span data-stu-id="a5c91-112">1: Clear all recycle bins</span></span>

<span data-ttu-id="a5c91-113">In diesem Beispiel werden alle Papierbehälter des lokalen Computers gelöscht.</span><span class="sxs-lookup"><span data-stu-id="a5c91-113">In this example, all the local computer's recycle bins are cleared.</span></span>

```powershell
Clear-RecycleBin
```

```Output
Confirm
Are you sure you want to perform this action?
Performing the operation "Clear-RecycleBin" on target "All of the contents of the Recycle Bin".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="a5c91-114">`Clear-RecycleBin` fordert den Benutzer zur Bestätigung auf, alle Papierkorb auf dem lokalen Computer zu löschen.</span><span class="sxs-lookup"><span data-stu-id="a5c91-114">`Clear-RecycleBin` prompts the user for confirmation to clear all recycle bins on the local computer.</span></span>

### <span data-ttu-id="a5c91-115">2: einen angegebenen Papierkorb löschen</span><span class="sxs-lookup"><span data-stu-id="a5c91-115">2: Clear a specified recycle bin</span></span>

<span data-ttu-id="a5c91-116">In diesem Beispiel wird der Papierkorb für einen angegebenen Laufwerk Buchstaben gelöscht.</span><span class="sxs-lookup"><span data-stu-id="a5c91-116">This example clears the recycle bin for a specified drive letter.</span></span>

```powershell
Clear-RecycleBin -DriveLetter C
```

<span data-ttu-id="a5c91-117">`Clear-RecycleBin` verwendet den **DriveLetter** -Parameter, um den Papierkorb auf dem **C** -Volume anzugeben.</span><span class="sxs-lookup"><span data-stu-id="a5c91-117">`Clear-RecycleBin` uses the **DriveLetter** parameter to specify the recycle bin on the **C** volume.</span></span> <span data-ttu-id="a5c91-118">Der Benutzer wird zur Bestätigung aufgefordert, den Befehl auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a5c91-118">The user is prompted for confirmation to run the command.</span></span>

### <span data-ttu-id="a5c91-119">3: alle Papierkorb ohne Bestätigung löschen</span><span class="sxs-lookup"><span data-stu-id="a5c91-119">3: Clear all recycle bins without confirmation</span></span>

<span data-ttu-id="a5c91-120">In diesem Beispiel wird nicht zur Bestätigung aufgefordert, die Papierbehälter des lokalen Computers zu löschen.</span><span class="sxs-lookup"><span data-stu-id="a5c91-120">This example doesn't prompt for confirmation to clear the local computer's recycle bins.</span></span>

```powershell
Clear-RecycleBin -Force
```

<span data-ttu-id="a5c91-121">`Clear-RecycleBin` in wird der **Force** -Parameter verwendet, und der Benutzer wird nicht zur Bestätigung aufgefordert, alle Papierkorb auf dem lokalen Computer zu löschen.</span><span class="sxs-lookup"><span data-stu-id="a5c91-121">`Clear-RecycleBin` uses the **Force** parameter and doesn't prompt the user for confirmation to clear all recycle bins on the local computer.</span></span>

<span data-ttu-id="a5c91-122">Eine Alternative besteht darin, `-Force` durch zu ersetzen `-Confirm:$false` .</span><span class="sxs-lookup"><span data-stu-id="a5c91-122">An alternative is to replace `-Force` with `-Confirm:$false`.</span></span>

## <span data-ttu-id="a5c91-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a5c91-123">PARAMETERS</span></span>

### <span data-ttu-id="a5c91-124">-DriveLetter</span><span class="sxs-lookup"><span data-stu-id="a5c91-124">-DriveLetter</span></span>

<span data-ttu-id="a5c91-125">Gibt den Papierkorb zum Löschen eines einzelnen Laufwerk Buchstabens oder eines Arrays von Laufwerk Buchstaben an.</span><span class="sxs-lookup"><span data-stu-id="a5c91-125">Specifies the recycle bin to clear for a single drive letter or an array of drive letters.</span></span>

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

### <span data-ttu-id="a5c91-126">-Force</span><span class="sxs-lookup"><span data-stu-id="a5c91-126">-Force</span></span>

<span data-ttu-id="a5c91-127">Gibt an, dass der Benutzer nicht zur Bestätigung aufgefordert wird, einen Papierkorb zu löschen.</span><span class="sxs-lookup"><span data-stu-id="a5c91-127">Specifies that the user isn't prompted for confirmation to clear a recycle bin.</span></span>

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

### <span data-ttu-id="a5c91-128">-Confirm</span><span class="sxs-lookup"><span data-stu-id="a5c91-128">-Confirm</span></span>

<span data-ttu-id="a5c91-129">Fordert vor dem Ausführen des Cmdlets zur Bestätigung des Benutzers auf.</span><span class="sxs-lookup"><span data-stu-id="a5c91-129">Prompts for user confirmation before running the cmdlet.</span></span> <span data-ttu-id="a5c91-130">Der Benutzer wird auch dann zur Bestätigung aufgefordert, wenn der **Confirm** -Parameter nicht angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="a5c91-130">The user is prompted for confirmation even if the **Confirm** parameter isn't specified.</span></span>

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

### <span data-ttu-id="a5c91-131">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="a5c91-131">-WhatIf</span></span>

<span data-ttu-id="a5c91-132">Zeigt, was geschieht, wenn ausgeführt wird `Clear-RecycleBin` .</span><span class="sxs-lookup"><span data-stu-id="a5c91-132">Shows what would happen if `Clear-RecycleBin` runs.</span></span> <span data-ttu-id="a5c91-133">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a5c91-133">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="a5c91-134">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a5c91-134">CommonParameters</span></span>

<span data-ttu-id="a5c91-135">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a5c91-135">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a5c91-136">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a5c91-136">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a5c91-137">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="a5c91-137">INPUTS</span></span>

## <span data-ttu-id="a5c91-138">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="a5c91-138">OUTPUTS</span></span>

### <span data-ttu-id="a5c91-139">Keine</span><span class="sxs-lookup"><span data-stu-id="a5c91-139">None</span></span>

## <span data-ttu-id="a5c91-140">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="a5c91-140">NOTES</span></span>

## <span data-ttu-id="a5c91-141">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="a5c91-141">RELATED LINKS</span></span>
