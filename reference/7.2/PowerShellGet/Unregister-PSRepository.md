---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/unregister-psrepository?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-PSRepository
ms.openlocfilehash: 908a43506bfbff964cfbdd8eea270b1fa42c3e77
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596141"
---
# <span data-ttu-id="a9f96-102">Unregister-PSRepository</span><span class="sxs-lookup"><span data-stu-id="a9f96-102">Unregister-PSRepository</span></span>

## <span data-ttu-id="a9f96-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="a9f96-103">SYNOPSIS</span></span>
<span data-ttu-id="a9f96-104">Hebt die Registrierung eines Repositorys auf</span><span class="sxs-lookup"><span data-stu-id="a9f96-104">Unregisters a repository.</span></span>

## <span data-ttu-id="a9f96-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a9f96-105">SYNTAX</span></span>

```
Unregister-PSRepository [-Name] <String[]> [<CommonParameters>]
```

## <span data-ttu-id="a9f96-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a9f96-106">DESCRIPTION</span></span>

<span data-ttu-id="a9f96-107">Mit dem- `Unregister-PSRepository` Cmdlet wird die Registrierung eines Repository für den aktuellen Benutzer aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="a9f96-107">The `Unregister-PSRepository` cmdlet unregisters a repository for the current user.</span></span>

## <span data-ttu-id="a9f96-108">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="a9f96-108">EXAMPLES</span></span>

### <span data-ttu-id="a9f96-109">Beispiel 1: Aufheben der Registrierung eines Repository</span><span class="sxs-lookup"><span data-stu-id="a9f96-109">Example 1: Unregister a repository</span></span>

<span data-ttu-id="a9f96-110">In diesem Beispiel wird die Registrierung des Repository mynugetsource aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="a9f96-110">This example unregisters the repository named myNuGetSource.</span></span>

```powershell
Unregister-PSRepository -Name "myNuGetSource"
```

### <span data-ttu-id="a9f96-111">Beispiel 2: Aufheben der Registrierung aller Depots</span><span class="sxs-lookup"><span data-stu-id="a9f96-111">Example 2: Unregister all repositories</span></span>

<span data-ttu-id="a9f96-112">In diesem Beispiel `Get-PSRepository` werden alle registrierten Depots mithilfe des Pipeline-Operators an übergeben, um die `Unregister-PSRepository` Registrierung aufzuheben.</span><span class="sxs-lookup"><span data-stu-id="a9f96-112">This example uses `Get-PSRepository` to get all registered repositories, and uses the pipeline operator to pass them to `Unregister-PSRepository` to unregister them.</span></span>

```powershell
Get-PSRepository | Unregister-PSRepository
```

## <span data-ttu-id="a9f96-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a9f96-113">PARAMETERS</span></span>

### <span data-ttu-id="a9f96-114">-Name</span><span class="sxs-lookup"><span data-stu-id="a9f96-114">-Name</span></span>

<span data-ttu-id="a9f96-115">Gibt ein Array von Namen der zu entfernenden Depots an.</span><span class="sxs-lookup"><span data-stu-id="a9f96-115">Specifies an array of names of the repositories to remove.</span></span>

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

### <span data-ttu-id="a9f96-116">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a9f96-116">CommonParameters</span></span>

<span data-ttu-id="a9f96-117">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a9f96-117">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a9f96-118">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a9f96-118">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a9f96-119">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="a9f96-119">INPUTS</span></span>

### <span data-ttu-id="a9f96-120">System.String[]</span><span class="sxs-lookup"><span data-stu-id="a9f96-120">System.String[]</span></span>

## <span data-ttu-id="a9f96-121">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="a9f96-121">OUTPUTS</span></span>

### <span data-ttu-id="a9f96-122">System.Object</span><span class="sxs-lookup"><span data-stu-id="a9f96-122">System.Object</span></span>

## <span data-ttu-id="a9f96-123">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="a9f96-123">NOTES</span></span>

## <span data-ttu-id="a9f96-124">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="a9f96-124">RELATED LINKS</span></span>

[<span data-ttu-id="a9f96-125">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="a9f96-125">Get-PSRepository</span></span>](Get-PSRepository.md)

[<span data-ttu-id="a9f96-126">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="a9f96-126">Register-PSRepository</span></span>](Register-PSRepository.md)

[<span data-ttu-id="a9f96-127">Set-PSRepository</span><span class="sxs-lookup"><span data-stu-id="a9f96-127">Set-PSRepository</span></span>](Set-PSRepository.md)
