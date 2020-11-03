---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Guid
ms.openlocfilehash: 2a289500020f069231023fbabaa5401ee0759697
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "93209291"
---
# <span data-ttu-id="dfbd1-103">New-Guid</span><span class="sxs-lookup"><span data-stu-id="dfbd1-103">New-Guid</span></span>

## <span data-ttu-id="dfbd1-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="dfbd1-104">SYNOPSIS</span></span>
<span data-ttu-id="dfbd1-105">Erstellt eine GUID.</span><span class="sxs-lookup"><span data-stu-id="dfbd1-105">Creates a GUID.</span></span>

## <span data-ttu-id="dfbd1-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="dfbd1-106">SYNTAX</span></span>

```
New-Guid [<CommonParameters>]
```

## <span data-ttu-id="dfbd1-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="dfbd1-107">DESCRIPTION</span></span>

<span data-ttu-id="dfbd1-108">Das **New-GUID-** Cmdlet erstellt eine zufällige Globally Unique Identifier (GUID).</span><span class="sxs-lookup"><span data-stu-id="dfbd1-108">The **New-Guid** cmdlet creates a random globally unique identifier (GUID).</span></span>
<span data-ttu-id="dfbd1-109">Wenn Sie in einem Skript eine eindeutige ID benötigen, können Sie nach Bedarf eine GUID erstellen.</span><span class="sxs-lookup"><span data-stu-id="dfbd1-109">If you need a unique ID in a script, you can create a GUID, as needed.</span></span>

## <span data-ttu-id="dfbd1-110">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="dfbd1-110">EXAMPLES</span></span>

### <span data-ttu-id="dfbd1-111">Beispiel 1: Erstellen einer GUID</span><span class="sxs-lookup"><span data-stu-id="dfbd1-111">Example 1: Create a GUID</span></span>

```
PS C:\> New-Guid
Guid
----
0352cf0f-2e7a-4aee-801d-7f27f8344c77
```

<span data-ttu-id="dfbd1-112">Mit diesem Befehl wird eine zufällige GUID erstellt.</span><span class="sxs-lookup"><span data-stu-id="dfbd1-112">This command creates a random GUID.</span></span>
<span data-ttu-id="dfbd1-113">Alternativ können Sie die Ausgabe dieses Cmdlets in einer Variablen speichern, die an anderer Stelle in einem Skript verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="dfbd1-113">Alternatively, you could store the output of this cmdlet in a variable to use elsewhere in a script.</span></span>

## <span data-ttu-id="dfbd1-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="dfbd1-114">PARAMETERS</span></span>

### <span data-ttu-id="dfbd1-115">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="dfbd1-115">CommonParameters</span></span>

<span data-ttu-id="dfbd1-116">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="dfbd1-116">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="dfbd1-117">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="dfbd1-117">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="dfbd1-118">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="dfbd1-118">INPUTS</span></span>

## <span data-ttu-id="dfbd1-119">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="dfbd1-119">OUTPUTS</span></span>

### <span data-ttu-id="dfbd1-120">System.Guid</span><span class="sxs-lookup"><span data-stu-id="dfbd1-120">System.Guid</span></span>

<span data-ttu-id="dfbd1-121">Dieses Cmdlet gibt eine GUID zurück.</span><span class="sxs-lookup"><span data-stu-id="dfbd1-121">This cmdlet returns a GUID.</span></span>

## <span data-ttu-id="dfbd1-122">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="dfbd1-122">NOTES</span></span>

## <span data-ttu-id="dfbd1-123">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="dfbd1-123">RELATED LINKS</span></span>

