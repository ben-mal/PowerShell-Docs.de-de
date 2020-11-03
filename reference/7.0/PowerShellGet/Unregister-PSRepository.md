---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/unregister-psrepository?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-PSRepository
ms.openlocfilehash: 0f1173cbfab139438d55ff49272f9625579820dc
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93211348"
---
# <span data-ttu-id="db001-103">Unregister-PSRepository</span><span class="sxs-lookup"><span data-stu-id="db001-103">Unregister-PSRepository</span></span>

## <span data-ttu-id="db001-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="db001-104">SYNOPSIS</span></span>
<span data-ttu-id="db001-105">Hebt die Registrierung eines Repositorys auf</span><span class="sxs-lookup"><span data-stu-id="db001-105">Unregisters a repository.</span></span>

## <span data-ttu-id="db001-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="db001-106">SYNTAX</span></span>

```
Unregister-PSRepository [-Name] <String[]> [<CommonParameters>]
```

## <span data-ttu-id="db001-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="db001-107">DESCRIPTION</span></span>

<span data-ttu-id="db001-108">Mit dem- `Unregister-PSRepository` Cmdlet wird die Registrierung eines Repository für den aktuellen Benutzer aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="db001-108">The `Unregister-PSRepository` cmdlet unregisters a repository for the current user.</span></span>

## <span data-ttu-id="db001-109">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="db001-109">EXAMPLES</span></span>

### <span data-ttu-id="db001-110">Beispiel 1: Aufheben der Registrierung eines Repository</span><span class="sxs-lookup"><span data-stu-id="db001-110">Example 1: Unregister a repository</span></span>

<span data-ttu-id="db001-111">In diesem Beispiel wird die Registrierung des Repository mynugetsource aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="db001-111">This example unregisters the repository named myNuGetSource.</span></span>

```powershell
Unregister-PSRepository -Name "myNuGetSource"
```

### <span data-ttu-id="db001-112">Beispiel 2: Aufheben der Registrierung aller Depots</span><span class="sxs-lookup"><span data-stu-id="db001-112">Example 2: Unregister all repositories</span></span>

<span data-ttu-id="db001-113">In diesem Beispiel `Get-PSRepository` werden alle registrierten Depots mithilfe des Pipeline-Operators an übergeben, um die `Unregister-PSRepository` Registrierung aufzuheben.</span><span class="sxs-lookup"><span data-stu-id="db001-113">This example uses `Get-PSRepository` to get all registered repositories, and uses the pipeline operator to pass them to `Unregister-PSRepository` to unregister them.</span></span>

```powershell
Get-PSRepository | Unregister-PSRepository
```

## <span data-ttu-id="db001-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="db001-114">PARAMETERS</span></span>

### <span data-ttu-id="db001-115">-Name</span><span class="sxs-lookup"><span data-stu-id="db001-115">-Name</span></span>

<span data-ttu-id="db001-116">Gibt ein Array von Namen der zu entfernenden Depots an.</span><span class="sxs-lookup"><span data-stu-id="db001-116">Specifies an array of names of the repositories to remove.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="db001-117">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="db001-117">CommonParameters</span></span>

<span data-ttu-id="db001-118">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="db001-118">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="db001-119">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="db001-119">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="db001-120">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="db001-120">INPUTS</span></span>

### <span data-ttu-id="db001-121">System.String[]</span><span class="sxs-lookup"><span data-stu-id="db001-121">System.String[]</span></span>

## <span data-ttu-id="db001-122">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="db001-122">OUTPUTS</span></span>

### <span data-ttu-id="db001-123">System.Object</span><span class="sxs-lookup"><span data-stu-id="db001-123">System.Object</span></span>

## <span data-ttu-id="db001-124">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="db001-124">NOTES</span></span>

## <span data-ttu-id="db001-125">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="db001-125">RELATED LINKS</span></span>

[<span data-ttu-id="db001-126">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="db001-126">Get-PSRepository</span></span>](Get-PSRepository.md)

[<span data-ttu-id="db001-127">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="db001-127">Register-PSRepository</span></span>](Register-PSRepository.md)

[<span data-ttu-id="db001-128">Set-PSRepository</span><span class="sxs-lookup"><span data-stu-id="db001-128">Set-PSRepository</span></span>](Set-PSRepository.md)
