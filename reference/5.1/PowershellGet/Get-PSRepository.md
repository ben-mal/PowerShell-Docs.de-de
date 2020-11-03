---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/get-psrepository?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSRepository
ms.openlocfilehash: e86f06b5e2ebbf51431e362af87b22ba4bd9c30d
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215247"
---
# <span data-ttu-id="a003d-103">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="a003d-103">Get-PSRepository</span></span>

## <span data-ttu-id="a003d-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="a003d-104">SYNOPSIS</span></span>
<span data-ttu-id="a003d-105">Ruft PowerShell-Repository ab.</span><span class="sxs-lookup"><span data-stu-id="a003d-105">Gets PowerShell repositories.</span></span>

## <span data-ttu-id="a003d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a003d-106">SYNTAX</span></span>

```
Get-PSRepository [[-Name] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="a003d-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a003d-107">DESCRIPTION</span></span>
<span data-ttu-id="a003d-108">Mit dem Cmdlet " **Get-psrepository** " werden PowerShell-moduldepots abgerufen, die für den aktuellen Benutzer registriert sind.</span><span class="sxs-lookup"><span data-stu-id="a003d-108">The **Get-PSRepository** cmdlet gets PowerShell module repositories that are registered for the current user.</span></span>

## <span data-ttu-id="a003d-109">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="a003d-109">EXAMPLES</span></span>

### <span data-ttu-id="a003d-110">Beispiel 1: alle modultrepositorys</span><span class="sxs-lookup"><span data-stu-id="a003d-110">Example 1: Get all module repositories</span></span>

```
PS C:\> Get-PSRepository
Name                                     SourceLocation                                     OneGetProvider       InstallationPolicy
----                                     --------------                                     --------------       ------------------
PSGallery                                http://go.micro...                                 NuGet                Untrusted
myNuGetSource                            https://myget.c...                                 NuGet                Trusted
```

<span data-ttu-id="a003d-111">Mit diesem Befehl werden alle moduldepots abgerufen, die für den aktuellen Benutzer registriert sind.</span><span class="sxs-lookup"><span data-stu-id="a003d-111">This command gets all module repositories registered for the current user.</span></span>

### <span data-ttu-id="a003d-112">Beispiel 2: Get Module Repository by Name</span><span class="sxs-lookup"><span data-stu-id="a003d-112">Example 2: Get module repositories by name</span></span>

```
PS C:\> Get-PSRepository -Name "*NuGet*"
```

<span data-ttu-id="a003d-113">Dieser Befehl ruft alle modultrepositorys ab, deren Namen nuget enthalten.</span><span class="sxs-lookup"><span data-stu-id="a003d-113">This command gets all module repositories that include NuGet in their names.</span></span>

### <span data-ttu-id="a003d-114">Beispiel 3: erhalten eines modulrepository und Formatieren der Ausgabe</span><span class="sxs-lookup"><span data-stu-id="a003d-114">Example 3: Get a module repository and format the output</span></span>

```
PS C:\> Get-PSRepository -Name "Local01" | Format-List * -Force
Name                      : local01
SourceLocation            : http://manikb-dev:8765/api/v2/
Trusted                   : True
Registered                : True
InstallationPolicy        : Trusted
PackageManagementProvider : NuGet
PublishLocation           : http://pattif-dev:8765/api/v2/package/
ScriptSourceLocation      : http://pattif-dev:8765/api/v2/artifacts/psscript
ScriptPublishLocation     : http://pattif-dev:8765/api/v2/package/
ProviderOptions           : {}
```

<span data-ttu-id="a003d-115">Dieser Befehl ruft das Repository mit dem Namen Local01 ab und verwendet den Pipeline-Operator, um dieses Objekt an das Format-List-Cmdlet zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="a003d-115">This command gets the repository named Local01 and uses the pipeline operator to pass that object to the Format-List cmdlet.</span></span>

## <span data-ttu-id="a003d-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a003d-116">PARAMETERS</span></span>

### <span data-ttu-id="a003d-117">-Name</span><span class="sxs-lookup"><span data-stu-id="a003d-117">-Name</span></span>
<span data-ttu-id="a003d-118">Gibt die Namen der zu erzurufenden Depots an.</span><span class="sxs-lookup"><span data-stu-id="a003d-118">Specifies the names of the repositories to get.</span></span>

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

### <span data-ttu-id="a003d-119">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a003d-119">CommonParameters</span></span>
<span data-ttu-id="a003d-120">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a003d-120">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a003d-121">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a003d-121">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a003d-122">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="a003d-122">INPUTS</span></span>

## <span data-ttu-id="a003d-123">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="a003d-123">OUTPUTS</span></span>

## <span data-ttu-id="a003d-124">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="a003d-124">NOTES</span></span>

## <span data-ttu-id="a003d-125">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="a003d-125">RELATED LINKS</span></span>

[<span data-ttu-id="a003d-126">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="a003d-126">Register-PSRepository</span></span>](Register-PSRepository.md)

[<span data-ttu-id="a003d-127">Set-PSRepository</span><span class="sxs-lookup"><span data-stu-id="a003d-127">Set-PSRepository</span></span>](Set-PSRepository.md)

[<span data-ttu-id="a003d-128">Unregister-PSRepository</span><span class="sxs-lookup"><span data-stu-id="a003d-128">Unregister-PSRepository</span></span>](Unregister-PSRepository.md)
