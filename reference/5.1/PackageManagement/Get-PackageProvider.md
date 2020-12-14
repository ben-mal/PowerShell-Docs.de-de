---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PackageManagement
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/packagemanagement/get-packageprovider?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PackageProvider
ms.openlocfilehash: 66a6bfeda557894e224753018ff9087de9887cc7
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "94892848"
---
# <span data-ttu-id="5a7ad-103">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="5a7ad-103">Get-PackageProvider</span></span>

## <span data-ttu-id="5a7ad-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="5a7ad-104">SYNOPSIS</span></span>
<span data-ttu-id="5a7ad-105">Gibt eine Liste von Paket Anbietern zurück, die mit Paketverwaltung verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="5a7ad-105">Returns a list of package providers that are connected to Package Management.</span></span>

## <span data-ttu-id="5a7ad-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5a7ad-106">SYNTAX</span></span>

```
Get-PackageProvider [[-Name] <String[]>] [-ListAvailable] [-Force] [-ForceBootstrap] [<CommonParameters>]
```

## <span data-ttu-id="5a7ad-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5a7ad-107">DESCRIPTION</span></span>
<span data-ttu-id="5a7ad-108">Das **Get-packageprovider** -Cmdlet gibt eine Liste von Paket Anbietern zurück, die mit Paketverwaltung verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="5a7ad-108">The **Get-PackageProvider** cmdlet returns a list of package providers that are connected to Package Management.</span></span>
<span data-ttu-id="5a7ad-109">Beispiele für diese Anbieter sind psmodule, nuget und Chocolatey.</span><span class="sxs-lookup"><span data-stu-id="5a7ad-109">Examples of these providers include PSModule, NuGet, and Chocolatey.</span></span>
<span data-ttu-id="5a7ad-110">Sie können die Ergebnisse auf der Grundlage eines oder mehrerer Anbieter Namen filtern.</span><span class="sxs-lookup"><span data-stu-id="5a7ad-110">You can filter the results based on all or part of one or more provider names.</span></span>

## <span data-ttu-id="5a7ad-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="5a7ad-111">EXAMPLES</span></span>

### <span data-ttu-id="5a7ad-112">Beispiel 1: alle zurzeit geladenen Paketanbieter</span><span class="sxs-lookup"><span data-stu-id="5a7ad-112">Example 1: Get all currently loaded package providers</span></span>

```
PS C:\> Get-PackageProvider
```

<span data-ttu-id="5a7ad-113">Mit diesem Befehl wird eine Liste aller Paketanbieter abgerufen, die zurzeit auf dem lokalen Computer geladen sind.</span><span class="sxs-lookup"><span data-stu-id="5a7ad-113">This command gets a list of all the package providers that are currently loaded on the local computer.</span></span>

### <span data-ttu-id="5a7ad-114">Beispiel 2: alle verfügbaren Paketanbieter erhalten</span><span class="sxs-lookup"><span data-stu-id="5a7ad-114">Example 2: Get all available package providers</span></span>

```
PS C:\> Get-PackageProvider -ListAvailable
```

<span data-ttu-id="5a7ad-115">Mit diesem Befehl wird eine Liste aller Paketanbieter abgerufen, die auf dem lokalen Computer verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="5a7ad-115">This command gets a list of all package providers that are available on the local computer.</span></span>

### <span data-ttu-id="5a7ad-116">Beispiel 3: Dynamisches erhalten eines Paket Anbieters</span><span class="sxs-lookup"><span data-stu-id="5a7ad-116">Example 3: Dynamically get a package provider</span></span>

```
PS C:\> Get-PackageProvider -Name "Chocolatey" -ForceBootstrap
```

<span data-ttu-id="5a7ad-117">Mit diesem Befehl wird der Chocolatey-Anbieter automatisch installiert, wenn auf dem Computer der Chocolatey-Anbieter nicht installiert ist.</span><span class="sxs-lookup"><span data-stu-id="5a7ad-117">This command automatically installs the Chocolatey provider if your computer does not have the Chocolatey provider installed.</span></span>

## <span data-ttu-id="5a7ad-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5a7ad-118">PARAMETERS</span></span>

### <span data-ttu-id="5a7ad-119">-Force</span><span class="sxs-lookup"><span data-stu-id="5a7ad-119">-Force</span></span>
<span data-ttu-id="5a7ad-120">Gibt an, dass dieses Cmdlet alle anderen Aktionen mit diesem Cmdlet erzwingt, die erzwungen werden können.</span><span class="sxs-lookup"><span data-stu-id="5a7ad-120">Indicates that this cmdlet forces all other actions with this cmdlet that can be forced.</span></span>
<span data-ttu-id="5a7ad-121">In **Get-packageprovider** bedeutet dies, dass der *Force* -Parameter mit dem Parameter " *forcebootstrap* " identisch ist.</span><span class="sxs-lookup"><span data-stu-id="5a7ad-121">In **Get-PackageProvider**, this means the *Force* parameter acts the same as the *ForceBootstrap* parameter.</span></span>

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

### <span data-ttu-id="5a7ad-122">-Forcebootstrap</span><span class="sxs-lookup"><span data-stu-id="5a7ad-122">-ForceBootstrap</span></span>
<span data-ttu-id="5a7ad-123">Gibt an, dass dieses Cmdlet Paketverwaltung zum automatischen Installieren des Paket Anbieters erzwingt.</span><span class="sxs-lookup"><span data-stu-id="5a7ad-123">Indicates that this cmdlet forces Package Management to automatically install the package provider.</span></span>

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

### <span data-ttu-id="5a7ad-124">-Listavailable</span><span class="sxs-lookup"><span data-stu-id="5a7ad-124">-ListAvailable</span></span>
<span data-ttu-id="5a7ad-125">Ruft alle installierten Anbieter ab.</span><span class="sxs-lookup"><span data-stu-id="5a7ad-125">Gets all installed providers.</span></span>
<span data-ttu-id="5a7ad-126">**Get-packageprovider** Ruft den Anbieter in Pfaden ab, die in der **psmodulepath** -Umgebungsvariablen aufgeführt sind, sowie die Assemblyordner des Paket Anbieters:</span><span class="sxs-lookup"><span data-stu-id="5a7ad-126">**Get-PackageProvider** gets provider in paths listed in the **PSModulePath** environment variable as well as the package provider assembly folders:</span></span>

<span data-ttu-id="5a7ad-127">**$ENV:P rogramfiles\packagemanagement\providerassemblys \* \* \* \* $ENV: localappdata\packagemanagement\providerassemblys**</span><span class="sxs-lookup"><span data-stu-id="5a7ad-127">**$env:ProgramFiles\PackageManagement\ProviderAssemblies\*\*\*\*$env:LOCALAPPDATA\PackageManagement\ProviderAssemblies**</span></span>

<span data-ttu-id="5a7ad-128">Ohne diesen Parameter ruft **Get-packageprovider** nur die Anbieter ab, die in der aktuellen Sitzung geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="5a7ad-128">Without this parameter, **Get-PackageProvider** gets only the providers loaded in the current session.</span></span>

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

### <span data-ttu-id="5a7ad-129">-Name</span><span class="sxs-lookup"><span data-stu-id="5a7ad-129">-Name</span></span>
<span data-ttu-id="5a7ad-130">Gibt einen oder mehrere Anbieter Namen oder partielle Anbieter Namen an.</span><span class="sxs-lookup"><span data-stu-id="5a7ad-130">Specifies one or more provider names, or partial provider names.</span></span>
<span data-ttu-id="5a7ad-131">Trennen Sie mehrere Anbieter Namen durch Kommas.</span><span class="sxs-lookup"><span data-stu-id="5a7ad-131">Separate multiple provider names with commas.</span></span>
<span data-ttu-id="5a7ad-132">Gültige Werte für diesen Parameter sind Namen von Anbietern, die Sie mit Paketen installiert haben. Packagemanagement wird mit einer Reihe von Standard Anbietern ausgeliefert, einschließlich der **psmodule** -und **MSI** -Anbieter.</span><span class="sxs-lookup"><span data-stu-id="5a7ad-132">Valid values for this parameter include names of providers that you have installed with packages; PackageManagement ships with a set of default providers, including the **PSModule** and **MSI** providers.</span></span>

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

### <span data-ttu-id="5a7ad-133">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="5a7ad-133">CommonParameters</span></span>
<span data-ttu-id="5a7ad-134">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5a7ad-134">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5a7ad-135">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="5a7ad-135">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5a7ad-136">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="5a7ad-136">INPUTS</span></span>

## <span data-ttu-id="5a7ad-137">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="5a7ad-137">OUTPUTS</span></span>

### <span data-ttu-id="5a7ad-138">Packageprovider []</span><span class="sxs-lookup"><span data-stu-id="5a7ad-138">PackageProvider[]</span></span>

## <span data-ttu-id="5a7ad-139">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="5a7ad-139">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5a7ad-140">Ab dem 2020 unterstützt die PowerShell-Katalog nicht mehr Transport Layer Security (TLS)-Versionen 1,0 und 1,1.</span><span class="sxs-lookup"><span data-stu-id="5a7ad-140">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="5a7ad-141">Wenn Sie TLS 1,2 oder höher nicht verwenden, erhalten Sie eine Fehlermeldung, wenn Sie versuchen, auf die PowerShell-Katalog zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="5a7ad-141">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="5a7ad-142">Verwenden Sie den folgenden Befehl, um sicherzustellen, dass Sie TLS 1,2 verwenden:</span><span class="sxs-lookup"><span data-stu-id="5a7ad-142">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="5a7ad-143">Weitere Informationen finden Sie in der [Ankündigung](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) im PowerShell-Blog.</span><span class="sxs-lookup"><span data-stu-id="5a7ad-143">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="5a7ad-144">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="5a7ad-144">RELATED LINKS</span></span>

[<span data-ttu-id="5a7ad-145">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="5a7ad-145">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="5a7ad-146">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="5a7ad-146">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="5a7ad-147">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="5a7ad-147">Register-PackageSource</span></span>](Register-PackageSource.md)

[<span data-ttu-id="5a7ad-148">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="5a7ad-148">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)
