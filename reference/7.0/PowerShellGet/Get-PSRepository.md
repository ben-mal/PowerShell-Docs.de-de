---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/get-psrepository?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSRepository
ms.openlocfilehash: cc92188384497b5e7534e3dc7daa4fc73c314a36
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210231"
---
# <span data-ttu-id="cb148-103">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="cb148-103">Get-PSRepository</span></span>

## <span data-ttu-id="cb148-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="cb148-104">SYNOPSIS</span></span>
<span data-ttu-id="cb148-105">Ruft PowerShell-Repository ab.</span><span class="sxs-lookup"><span data-stu-id="cb148-105">Gets PowerShell repositories.</span></span>

## <span data-ttu-id="cb148-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="cb148-106">SYNTAX</span></span>

```
Get-PSRepository [[-Name] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="cb148-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="cb148-107">DESCRIPTION</span></span>

<span data-ttu-id="cb148-108">Mit dem Cmdlet " **Get-psrepository** " werden PowerShell-moduldepots abgerufen, die für den aktuellen Benutzer registriert sind.</span><span class="sxs-lookup"><span data-stu-id="cb148-108">The **Get-PSRepository** cmdlet gets PowerShell module repositories that are registered for the current user.</span></span>

## <span data-ttu-id="cb148-109">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="cb148-109">EXAMPLES</span></span>

### <span data-ttu-id="cb148-110">Beispiel 1: alle modultrepositorys</span><span class="sxs-lookup"><span data-stu-id="cb148-110">Example 1: Get all module repositories</span></span>

```
PS C:\> Get-PSRepository
Name                                     SourceLocation                                     OneGetProvider       InstallationPolicy
----                                     --------------                                     --------------       ------------------
PSGallery                                http://go.micro...                                 NuGet                Untrusted
myNuGetSource                            https://myget.c...                                 NuGet                Trusted
```

<span data-ttu-id="cb148-111">Mit diesem Befehl werden alle moduldepots abgerufen, die für den aktuellen Benutzer registriert sind.</span><span class="sxs-lookup"><span data-stu-id="cb148-111">This command gets all module repositories registered for the current user.</span></span>

### <span data-ttu-id="cb148-112">Beispiel 2: Get Module Repository by Name</span><span class="sxs-lookup"><span data-stu-id="cb148-112">Example 2: Get module repositories by name</span></span>

```
PS C:\> Get-PSRepository -Name "*NuGet*"
```

<span data-ttu-id="cb148-113">Dieser Befehl ruft alle modultrepositorys ab, deren Namen nuget enthalten.</span><span class="sxs-lookup"><span data-stu-id="cb148-113">This command gets all module repositories that include NuGet in their names.</span></span>

### <span data-ttu-id="cb148-114">Beispiel 3: erhalten eines modulrepository und Formatieren der Ausgabe</span><span class="sxs-lookup"><span data-stu-id="cb148-114">Example 3: Get a module repository and format the output</span></span>

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

<span data-ttu-id="cb148-115">Dieser Befehl ruft das Repository mit dem Namen Local01 ab und verwendet den Pipeline-Operator, um dieses Objekt an das Format-List-Cmdlet zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="cb148-115">This command gets the repository named Local01 and uses the pipeline operator to pass that object to the Format-List cmdlet.</span></span>

## <span data-ttu-id="cb148-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="cb148-116">PARAMETERS</span></span>

### <span data-ttu-id="cb148-117">-Name</span><span class="sxs-lookup"><span data-stu-id="cb148-117">-Name</span></span>

<span data-ttu-id="cb148-118">Gibt die Namen der zu erzurufenden Depots an.</span><span class="sxs-lookup"><span data-stu-id="cb148-118">Specifies the names of the repositories to get.</span></span>

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

### <span data-ttu-id="cb148-119">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="cb148-119">CommonParameters</span></span>

<span data-ttu-id="cb148-120">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="cb148-120">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="cb148-121">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="cb148-121">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="cb148-122">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="cb148-122">INPUTS</span></span>

### <span data-ttu-id="cb148-123">System.String[]</span><span class="sxs-lookup"><span data-stu-id="cb148-123">System.String[]</span></span>

## <span data-ttu-id="cb148-124">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="cb148-124">OUTPUTS</span></span>

### <span data-ttu-id="cb148-125">System.Object</span><span class="sxs-lookup"><span data-stu-id="cb148-125">System.Object</span></span>

## <span data-ttu-id="cb148-126">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="cb148-126">NOTES</span></span>

## <span data-ttu-id="cb148-127">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="cb148-127">RELATED LINKS</span></span>

[<span data-ttu-id="cb148-128">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="cb148-128">Register-PSRepository</span></span>](Register-PSRepository.md)

[<span data-ttu-id="cb148-129">Set-PSRepository</span><span class="sxs-lookup"><span data-stu-id="cb148-129">Set-PSRepository</span></span>](Set-PSRepository.md)

[<span data-ttu-id="cb148-130">Unregister-PSRepository</span><span class="sxs-lookup"><span data-stu-id="cb148-130">Unregister-PSRepository</span></span>](Unregister-PSRepository.md)
