---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/clear-recyclebin?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-RecycleBin
ms.openlocfilehash: 85e4ac857135a6df8215dcfe415057dd8aacde86
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210388"
---
# <span data-ttu-id="b7f76-103">Clear-RecycleBin</span><span class="sxs-lookup"><span data-stu-id="b7f76-103">Clear-RecycleBin</span></span>

## <span data-ttu-id="b7f76-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="b7f76-104">SYNOPSIS</span></span>
<span data-ttu-id="b7f76-105">Löscht den Inhalt eines Papierkorbs.</span><span class="sxs-lookup"><span data-stu-id="b7f76-105">Clears the contents of a recycle bin.</span></span>

## <span data-ttu-id="b7f76-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b7f76-106">SYNTAX</span></span>

### <span data-ttu-id="b7f76-107">Alle</span><span class="sxs-lookup"><span data-stu-id="b7f76-107">All</span></span>

```
Clear-RecycleBin [[-DriveLetter] <String[]>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="b7f76-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b7f76-108">DESCRIPTION</span></span>

<span data-ttu-id="b7f76-109">`Clear-RecycleBin`Mit dem-Cmdlet wird der Inhalt des Papierkorbs eines Computers gelöscht.</span><span class="sxs-lookup"><span data-stu-id="b7f76-109">The `Clear-RecycleBin` cmdlet deletes the content of a computer's recycle bin.</span></span> <span data-ttu-id="b7f76-110">Diese Aktion ähnelt der Verwendung des **leeren** Windows-Papierkorbs.</span><span class="sxs-lookup"><span data-stu-id="b7f76-110">This action is like using Windows **Empty Recycle Bin**.</span></span>

<span data-ttu-id="b7f76-111">Dieses Cmdlet wurde in PowerShell 7 gelesen.</span><span class="sxs-lookup"><span data-stu-id="b7f76-111">This cmdlet was readded in PowerShell 7.</span></span>

## <span data-ttu-id="b7f76-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="b7f76-112">EXAMPLES</span></span>

### <span data-ttu-id="b7f76-113">1: alle Papierbehälter löschen</span><span class="sxs-lookup"><span data-stu-id="b7f76-113">1: Clear all recycle bins</span></span>

<span data-ttu-id="b7f76-114">In diesem Beispiel werden alle Papierbehälter des lokalen Computers gelöscht.</span><span class="sxs-lookup"><span data-stu-id="b7f76-114">In this example, all the local computer's recycle bins are cleared.</span></span>

```powershell
Clear-RecycleBin
```

```Output
Confirm
Are you sure you want to perform this action?
Performing the operation "Clear-RecycleBin" on target "All of the contents of the Recycle Bin".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="b7f76-115">`Clear-RecycleBin` fordert den Benutzer zur Bestätigung auf, alle Papierkorb auf dem lokalen Computer zu löschen.</span><span class="sxs-lookup"><span data-stu-id="b7f76-115">`Clear-RecycleBin` prompts the user for confirmation to clear all recycle bins on the local computer.</span></span>

### <span data-ttu-id="b7f76-116">2: einen angegebenen Papierkorb löschen</span><span class="sxs-lookup"><span data-stu-id="b7f76-116">2: Clear a specified recycle bin</span></span>

<span data-ttu-id="b7f76-117">In diesem Beispiel wird der Papierkorb für einen angegebenen Laufwerk Buchstaben gelöscht.</span><span class="sxs-lookup"><span data-stu-id="b7f76-117">This example clears the recycle bin for a specified drive letter.</span></span>

```powershell
Clear-RecycleBin -DriveLetter C
```

<span data-ttu-id="b7f76-118">`Clear-RecycleBin` verwendet den **DriveLetter** -Parameter, um den Papierkorb auf dem **C** -Volume anzugeben.</span><span class="sxs-lookup"><span data-stu-id="b7f76-118">`Clear-RecycleBin` uses the **DriveLetter** parameter to specify the recycle bin on the **C** volume.</span></span> <span data-ttu-id="b7f76-119">Der Benutzer wird zur Bestätigung aufgefordert, den Befehl auszuführen.</span><span class="sxs-lookup"><span data-stu-id="b7f76-119">The user is prompted for confirmation to run the command.</span></span>

### <span data-ttu-id="b7f76-120">3: alle Papierkorb ohne Bestätigung löschen</span><span class="sxs-lookup"><span data-stu-id="b7f76-120">3: Clear all recycle bins without confirmation</span></span>

<span data-ttu-id="b7f76-121">In diesem Beispiel wird nicht zur Bestätigung aufgefordert, die Papierbehälter des lokalen Computers zu löschen.</span><span class="sxs-lookup"><span data-stu-id="b7f76-121">This example doesn't prompt for confirmation to clear the local computer's recycle bins.</span></span>

```powershell
Clear-RecycleBin -Force
```

<span data-ttu-id="b7f76-122">`Clear-RecycleBin` in wird der **Force** -Parameter verwendet, und der Benutzer wird nicht zur Bestätigung aufgefordert, alle Papierkorb auf dem lokalen Computer zu löschen.</span><span class="sxs-lookup"><span data-stu-id="b7f76-122">`Clear-RecycleBin` uses the **Force** parameter and doesn't prompt the user for confirmation to clear all recycle bins on the local computer.</span></span>

<span data-ttu-id="b7f76-123">Eine Alternative besteht darin, `-Force` durch zu ersetzen `-Confirm:$false` .</span><span class="sxs-lookup"><span data-stu-id="b7f76-123">An alternative is to replace `-Force` with `-Confirm:$false`.</span></span>

## <span data-ttu-id="b7f76-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b7f76-124">PARAMETERS</span></span>

### <span data-ttu-id="b7f76-125">-DriveLetter</span><span class="sxs-lookup"><span data-stu-id="b7f76-125">-DriveLetter</span></span>

<span data-ttu-id="b7f76-126">Gibt den Papierkorb zum Löschen eines einzelnen Laufwerk Buchstabens oder eines Arrays von Laufwerk Buchstaben an.</span><span class="sxs-lookup"><span data-stu-id="b7f76-126">Specifies the recycle bin to clear for a single drive letter or an array of drive letters.</span></span>

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

### <span data-ttu-id="b7f76-127">-Force</span><span class="sxs-lookup"><span data-stu-id="b7f76-127">-Force</span></span>

<span data-ttu-id="b7f76-128">Gibt an, dass der Benutzer nicht zur Bestätigung aufgefordert wird, einen Papierkorb zu löschen.</span><span class="sxs-lookup"><span data-stu-id="b7f76-128">Specifies that the user isn't prompted for confirmation to clear a recycle bin.</span></span>

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

### <span data-ttu-id="b7f76-129">-Confirm</span><span class="sxs-lookup"><span data-stu-id="b7f76-129">-Confirm</span></span>

<span data-ttu-id="b7f76-130">Fordert vor dem Ausführen des Cmdlets zur Bestätigung des Benutzers auf.</span><span class="sxs-lookup"><span data-stu-id="b7f76-130">Prompts for user confirmation before running the cmdlet.</span></span> <span data-ttu-id="b7f76-131">Der Benutzer wird auch dann zur Bestätigung aufgefordert, wenn der **Confirm** -Parameter nicht angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="b7f76-131">The user is prompted for confirmation even if the **Confirm** parameter isn't specified.</span></span>

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

### <span data-ttu-id="b7f76-132">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="b7f76-132">-WhatIf</span></span>

<span data-ttu-id="b7f76-133">Zeigt, was geschieht, wenn ausgeführt wird `Clear-RecycleBin` .</span><span class="sxs-lookup"><span data-stu-id="b7f76-133">Shows what would happen if `Clear-RecycleBin` runs.</span></span> <span data-ttu-id="b7f76-134">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b7f76-134">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="b7f76-135">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b7f76-135">CommonParameters</span></span>

<span data-ttu-id="b7f76-136">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b7f76-136">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b7f76-137">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b7f76-137">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b7f76-138">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="b7f76-138">INPUTS</span></span>

## <span data-ttu-id="b7f76-139">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="b7f76-139">OUTPUTS</span></span>

### <span data-ttu-id="b7f76-140">Keine</span><span class="sxs-lookup"><span data-stu-id="b7f76-140">None</span></span>

## <span data-ttu-id="b7f76-141">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="b7f76-141">NOTES</span></span>

## <span data-ttu-id="b7f76-142">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="b7f76-142">RELATED LINKS</span></span>
