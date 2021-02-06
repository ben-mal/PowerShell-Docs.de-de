---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/get-psrepository?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSRepository
ms.openlocfilehash: 66f840d99b107da22b6771e6327ab68d33a1b368
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601727"
---
# <span data-ttu-id="7e9cf-102">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="7e9cf-102">Get-PSRepository</span></span>

## <span data-ttu-id="7e9cf-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="7e9cf-103">SYNOPSIS</span></span>
<span data-ttu-id="7e9cf-104">Ruft PowerShell-Repository ab.</span><span class="sxs-lookup"><span data-stu-id="7e9cf-104">Gets PowerShell repositories.</span></span>

## <span data-ttu-id="7e9cf-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7e9cf-105">SYNTAX</span></span>

```
Get-PSRepository [[-Name] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="7e9cf-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7e9cf-106">DESCRIPTION</span></span>

<span data-ttu-id="7e9cf-107">Mit dem Cmdlet " **Get-psrepository** " werden PowerShell-moduldepots abgerufen, die für den aktuellen Benutzer registriert sind.</span><span class="sxs-lookup"><span data-stu-id="7e9cf-107">The **Get-PSRepository** cmdlet gets PowerShell module repositories that are registered for the current user.</span></span>

## <span data-ttu-id="7e9cf-108">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="7e9cf-108">EXAMPLES</span></span>

### <span data-ttu-id="7e9cf-109">Beispiel 1: alle modultrepositorys</span><span class="sxs-lookup"><span data-stu-id="7e9cf-109">Example 1: Get all module repositories</span></span>

```
PS C:\> Get-PSRepository
Name                                     SourceLocation                                     OneGetProvider       InstallationPolicy
----                                     --------------                                     --------------       ------------------
PSGallery                                http://go.micro...                                 NuGet                Untrusted
myNuGetSource                            https://myget.c...                                 NuGet                Trusted
```

<span data-ttu-id="7e9cf-110">Mit diesem Befehl werden alle moduldepots abgerufen, die für den aktuellen Benutzer registriert sind.</span><span class="sxs-lookup"><span data-stu-id="7e9cf-110">This command gets all module repositories registered for the current user.</span></span>

### <span data-ttu-id="7e9cf-111">Beispiel 2: Get Module Repository by Name</span><span class="sxs-lookup"><span data-stu-id="7e9cf-111">Example 2: Get module repositories by name</span></span>

```
PS C:\> Get-PSRepository -Name "*NuGet*"
```

<span data-ttu-id="7e9cf-112">Dieser Befehl ruft alle modultrepositorys ab, deren Namen nuget enthalten.</span><span class="sxs-lookup"><span data-stu-id="7e9cf-112">This command gets all module repositories that include NuGet in their names.</span></span>

### <span data-ttu-id="7e9cf-113">Beispiel 3: erhalten eines modulrepository und Formatieren der Ausgabe</span><span class="sxs-lookup"><span data-stu-id="7e9cf-113">Example 3: Get a module repository and format the output</span></span>

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

<span data-ttu-id="7e9cf-114">Dieser Befehl ruft das Repository mit dem Namen Local01 ab und verwendet den Pipeline-Operator, um dieses Objekt an das Format-List-Cmdlet zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="7e9cf-114">This command gets the repository named Local01 and uses the pipeline operator to pass that object to the Format-List cmdlet.</span></span>

## <span data-ttu-id="7e9cf-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7e9cf-115">PARAMETERS</span></span>

### <span data-ttu-id="7e9cf-116">-Name</span><span class="sxs-lookup"><span data-stu-id="7e9cf-116">-Name</span></span>

<span data-ttu-id="7e9cf-117">Gibt die Namen der zu erzurufenden Depots an.</span><span class="sxs-lookup"><span data-stu-id="7e9cf-117">Specifies the names of the repositories to get.</span></span>

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

### <span data-ttu-id="7e9cf-118">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="7e9cf-118">CommonParameters</span></span>

<span data-ttu-id="7e9cf-119">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="7e9cf-119">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7e9cf-120">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="7e9cf-120">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7e9cf-121">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="7e9cf-121">INPUTS</span></span>

### <span data-ttu-id="7e9cf-122">System.String[]</span><span class="sxs-lookup"><span data-stu-id="7e9cf-122">System.String[]</span></span>

## <span data-ttu-id="7e9cf-123">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="7e9cf-123">OUTPUTS</span></span>

### <span data-ttu-id="7e9cf-124">System.Object</span><span class="sxs-lookup"><span data-stu-id="7e9cf-124">System.Object</span></span>

## <span data-ttu-id="7e9cf-125">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="7e9cf-125">NOTES</span></span>

## <span data-ttu-id="7e9cf-126">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="7e9cf-126">RELATED LINKS</span></span>

[<span data-ttu-id="7e9cf-127">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="7e9cf-127">Register-PSRepository</span></span>](Register-PSRepository.md)

[<span data-ttu-id="7e9cf-128">Set-PSRepository</span><span class="sxs-lookup"><span data-stu-id="7e9cf-128">Set-PSRepository</span></span>](Set-PSRepository.md)

[<span data-ttu-id="7e9cf-129">Unregister-PSRepository</span><span class="sxs-lookup"><span data-stu-id="7e9cf-129">Unregister-PSRepository</span></span>](Unregister-PSRepository.md)

