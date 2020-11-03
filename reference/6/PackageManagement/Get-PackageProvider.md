---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PackageManagement
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/packagemanagement/get-packageprovider?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PackageProvider
ms.openlocfilehash: 85471e6f884d785ec8a5a253a57b1fb13b3a446b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214839"
---
# <span data-ttu-id="0178d-103">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="0178d-103">Get-PackageProvider</span></span>

## <span data-ttu-id="0178d-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="0178d-104">SYNOPSIS</span></span>
<span data-ttu-id="0178d-105">Gibt eine Liste von Paket Anbietern zurück, die mit Paketverwaltung verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="0178d-105">Returns a list of package providers that are connected to Package Management.</span></span>

## <span data-ttu-id="0178d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0178d-106">SYNTAX</span></span>

```
Get-PackageProvider [[-Name] <String[]>] [-ListAvailable] [-Force] [-ForceBootstrap] [<CommonParameters>]
```

## <span data-ttu-id="0178d-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0178d-107">DESCRIPTION</span></span>

<span data-ttu-id="0178d-108">Das **Get-packageprovider** -Cmdlet gibt eine Liste von Paket Anbietern zurück, die mit Paketverwaltung verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="0178d-108">The **Get-PackageProvider** cmdlet returns a list of package providers that are connected to Package Management.</span></span>
<span data-ttu-id="0178d-109">Beispiele für diese Anbieter sind psmodule, nuget und Chocolatey.</span><span class="sxs-lookup"><span data-stu-id="0178d-109">Examples of these providers include PSModule, NuGet, and Chocolatey.</span></span>
<span data-ttu-id="0178d-110">Sie können die Ergebnisse auf der Grundlage eines oder mehrerer Anbieter Namen filtern.</span><span class="sxs-lookup"><span data-stu-id="0178d-110">You can filter the results based on all or part of one or more provider names.</span></span>

## <span data-ttu-id="0178d-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="0178d-111">EXAMPLES</span></span>

### <span data-ttu-id="0178d-112">Beispiel 1: alle zurzeit geladenen Paketanbieter</span><span class="sxs-lookup"><span data-stu-id="0178d-112">Example 1: Get all currently loaded package providers</span></span>

```
PS C:\> Get-PackageProvider
```

<span data-ttu-id="0178d-113">Mit diesem Befehl wird eine Liste aller Paketanbieter abgerufen, die zurzeit auf dem lokalen Computer geladen sind.</span><span class="sxs-lookup"><span data-stu-id="0178d-113">This command gets a list of all the package providers that are currently loaded on the local computer.</span></span>

### <span data-ttu-id="0178d-114">Beispiel 2: alle verfügbaren Paketanbieter erhalten</span><span class="sxs-lookup"><span data-stu-id="0178d-114">Example 2: Get all available package providers</span></span>

```
PS C:\> Get-PackageProvider -ListAvailable
```

<span data-ttu-id="0178d-115">Mit diesem Befehl wird eine Liste aller Paketanbieter abgerufen, die auf dem lokalen Computer verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="0178d-115">This command gets a list of all package providers that are available on the local computer.</span></span>

### <span data-ttu-id="0178d-116">Beispiel 3: Dynamisches erhalten eines Paket Anbieters</span><span class="sxs-lookup"><span data-stu-id="0178d-116">Example 3: Dynamically get a package provider</span></span>

```
PS C:\> Get-PackageProvider -Name "Chocolatey" -ForceBootstrap
```

<span data-ttu-id="0178d-117">Mit diesem Befehl wird der Chocolatey-Anbieter automatisch installiert, wenn auf dem Computer der Chocolatey-Anbieter nicht installiert ist.</span><span class="sxs-lookup"><span data-stu-id="0178d-117">This command automatically installs the Chocolatey provider if your computer does not have the Chocolatey provider installed.</span></span>

## <span data-ttu-id="0178d-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0178d-118">PARAMETERS</span></span>

### <span data-ttu-id="0178d-119">-Force</span><span class="sxs-lookup"><span data-stu-id="0178d-119">-Force</span></span>

<span data-ttu-id="0178d-120">Gibt an, dass dieses Cmdlet alle anderen Aktionen mit diesem Cmdlet erzwingt, die erzwungen werden können.</span><span class="sxs-lookup"><span data-stu-id="0178d-120">Indicates that this cmdlet forces all other actions with this cmdlet that can be forced.</span></span>
<span data-ttu-id="0178d-121">In **Get-packageprovider** bedeutet dies, dass der *Force* -Parameter mit dem Parameter " *forcebootstrap* " identisch ist.</span><span class="sxs-lookup"><span data-stu-id="0178d-121">In **Get-PackageProvider** , this means the *Force* parameter acts the same as the *ForceBootstrap* parameter.</span></span>

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

### <span data-ttu-id="0178d-122">-Forcebootstrap</span><span class="sxs-lookup"><span data-stu-id="0178d-122">-ForceBootstrap</span></span>

<span data-ttu-id="0178d-123">Gibt an, dass dieses Cmdlet Paketverwaltung zum automatischen Installieren des Paket Anbieters erzwingt.</span><span class="sxs-lookup"><span data-stu-id="0178d-123">Indicates that this cmdlet forces Package Management to automatically install the package provider.</span></span>

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

### <span data-ttu-id="0178d-124">-Listavailable</span><span class="sxs-lookup"><span data-stu-id="0178d-124">-ListAvailable</span></span>

<span data-ttu-id="0178d-125">Ruft alle installierten Anbieter ab.</span><span class="sxs-lookup"><span data-stu-id="0178d-125">Gets all installed providers.</span></span>
<span data-ttu-id="0178d-126">**Get-packageprovider** Ruft den Anbieter in Pfaden ab, die in der **psmodulepath** -Umgebungsvariablen aufgeführt sind, sowie die Assemblyordner des Paket Anbieters:</span><span class="sxs-lookup"><span data-stu-id="0178d-126">**Get-PackageProvider** gets provider in paths listed in the **PSModulePath** environment variable as well as the package provider assembly folders:</span></span>

<span data-ttu-id="0178d-127">**$ENV:P rogramfiles\packagemanagement\providerassemblys \* \* \* \* $ENV: localappdata\packagemanagement\providerassemblys**</span><span class="sxs-lookup"><span data-stu-id="0178d-127">**$env:ProgramFiles\PackageManagement\ProviderAssemblies\*\*\*\*$env:LOCALAPPDATA\PackageManagement\ProviderAssemblies**</span></span>

<span data-ttu-id="0178d-128">Ohne diesen Parameter ruft **Get-packageprovider** nur die Anbieter ab, die in der aktuellen Sitzung geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="0178d-128">Without this parameter, **Get-PackageProvider** gets only the providers loaded in the current session.</span></span>

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

### <span data-ttu-id="0178d-129">-Name</span><span class="sxs-lookup"><span data-stu-id="0178d-129">-Name</span></span>

<span data-ttu-id="0178d-130">Gibt einen oder mehrere Anbieter Namen oder partielle Anbieter Namen an.</span><span class="sxs-lookup"><span data-stu-id="0178d-130">Specifies one or more provider names, or partial provider names.</span></span>
<span data-ttu-id="0178d-131">Trennen Sie mehrere Anbieter Namen durch Kommas.</span><span class="sxs-lookup"><span data-stu-id="0178d-131">Separate multiple provider names with commas.</span></span>
<span data-ttu-id="0178d-132">Gültige Werte für diesen Parameter sind Namen von Anbietern, die Sie mit Paketen installiert haben. Packagemanagement wird mit einer Reihe von Standard Anbietern ausgeliefert, einschließlich der **psmodule** -und **MSI** -Anbieter.</span><span class="sxs-lookup"><span data-stu-id="0178d-132">Valid values for this parameter include names of providers that you have installed with packages; PackageManagement ships with a set of default providers, including the **PSModule** and **MSI** providers.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0178d-133">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0178d-133">CommonParameters</span></span>

<span data-ttu-id="0178d-134">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0178d-134">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0178d-135">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0178d-135">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0178d-136">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="0178d-136">INPUTS</span></span>

## <span data-ttu-id="0178d-137">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="0178d-137">OUTPUTS</span></span>

### <span data-ttu-id="0178d-138">Packageprovider []</span><span class="sxs-lookup"><span data-stu-id="0178d-138">PackageProvider[]</span></span>

## <span data-ttu-id="0178d-139">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="0178d-139">NOTES</span></span>

## <span data-ttu-id="0178d-140">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="0178d-140">RELATED LINKS</span></span>

[<span data-ttu-id="0178d-141">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="0178d-141">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="0178d-142">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="0178d-142">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="0178d-143">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="0178d-143">Register-PackageSource</span></span>](Register-PackageSource.md)

[<span data-ttu-id="0178d-144">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="0178d-144">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)
