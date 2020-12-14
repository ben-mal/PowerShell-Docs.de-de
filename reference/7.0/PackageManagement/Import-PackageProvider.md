---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PackageManagement
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/packagemanagement/import-packageprovider?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-PackageProvider
ms.openlocfilehash: 570ed2a314c498fe59546d30cba17913bc91b70c
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "94890473"
---
# <span data-ttu-id="d8091-103">Import-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="d8091-103">Import-PackageProvider</span></span>

## <span data-ttu-id="d8091-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="d8091-104">SYNOPSIS</span></span>
<span data-ttu-id="d8091-105">Fügt der aktuellen Sitzung Paketverwaltung Paketanbieter hinzu.</span><span class="sxs-lookup"><span data-stu-id="d8091-105">Adds Package Management package providers to the current session.</span></span>

## <span data-ttu-id="d8091-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d8091-106">SYNTAX</span></span>

```
Import-PackageProvider [-Name] <String[]> [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-Force] [-ForceBootstrap] [<CommonParameters>]
```

## <span data-ttu-id="d8091-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d8091-107">DESCRIPTION</span></span>

<span data-ttu-id="d8091-108">Mit dem- `Import-PackageProvider` Cmdlet wird der aktuellen Sitzung mindestens ein Paketanbieter hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="d8091-108">The `Import-PackageProvider` cmdlet adds one or more package providers to the current session.</span></span>
<span data-ttu-id="d8091-109">Der von Ihnen importierte Anbieter muss auf dem lokalen Computer installiert sein.</span><span class="sxs-lookup"><span data-stu-id="d8091-109">The provider that you import must be installed on the local computer.</span></span>

<span data-ttu-id="d8091-110">Führen Sie aus, um eine Liste der verfügbaren Anbieter zu erhalten `Get-PackageProvider -ListAvailable` .</span><span class="sxs-lookup"><span data-stu-id="d8091-110">To get a list of available providers, run `Get-PackageProvider -ListAvailable`.</span></span>
<span data-ttu-id="d8091-111">Beachten Sie, dass sich der Name eines Paket Anbieters vom Modulnamen unterscheiden kann.</span><span class="sxs-lookup"><span data-stu-id="d8091-111">Note that a package provider name can be different from its module name.</span></span>

<span data-ttu-id="d8091-112">Aus Sicherheitsgründen erfordert **packagemanagement** , dass c#-basierte Anbieter einen enthalten `provider.manifest` .</span><span class="sxs-lookup"><span data-stu-id="d8091-112">Due to security reasons, **PackageManagement** requires C#-based providers to contain a `provider.manifest`.</span></span> <span data-ttu-id="d8091-113">Weitere Informationen zum Erstellen eines Anbieters mit `provider.manifest` injiziertem finden Sie in den `.csproj` Projektdateien unter [https://github.com/oneget/oneget](https://github.com/oneget/oneget) .</span><span class="sxs-lookup"><span data-stu-id="d8091-113">For more information on how to build a provider with `provider.manifest` injected, see the `.csproj` project files on [https://github.com/oneget/oneget](https://github.com/oneget/oneget).</span></span>

## <span data-ttu-id="d8091-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="d8091-114">EXAMPLES</span></span>

### <span data-ttu-id="d8091-115">Beispiel 1: Importieren eines Paket Anbieters vom lokalen Computer</span><span class="sxs-lookup"><span data-stu-id="d8091-115">Example 1: Import a package provider from the local computer</span></span>

```powershell
PS C:\> Import-PackageProvider -Name "Nuget"
```

<span data-ttu-id="d8091-116">Dieser Befehl importiert den nuget-Anbieter, nachdem er auf dem lokalen Computer installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="d8091-116">This command imports the Nuget provider after it has been installed on the local computer.</span></span>

### <span data-ttu-id="d8091-117">Beispiel 2: Importieren einer bestimmten Version eines Paket Anbieters</span><span class="sxs-lookup"><span data-stu-id="d8091-117">Example 2: Import a specific version of a package provider</span></span>

```powershell
PS C:\> Find-PackageProvider -Name "Nuget" -AllVersions
Install-PackageProvider -Name "Nuget" -RequiredVersion "2.8.5.201" -Force
Get-PackageProvider -ListAvailable
Import-PackageProvider -Name "Nuget" -RequiredVersion "2.8.5.201" -Verbose
```

<span data-ttu-id="d8091-118">Mit diesem Befehl wird eine bestimmte Version des nuget-Paket Anbieters ermittelt, installiert und importiert.</span><span class="sxs-lookup"><span data-stu-id="d8091-118">This command finds, installs, and imports a specific version of the Nuget package provider.</span></span>

## <span data-ttu-id="d8091-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d8091-119">PARAMETERS</span></span>

### <span data-ttu-id="d8091-120">-Force</span><span class="sxs-lookup"><span data-stu-id="d8091-120">-Force</span></span>

<span data-ttu-id="d8091-121">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="d8091-121">Forces the command to run without asking for user confirmation.</span></span>
<span data-ttu-id="d8091-122">Importiert einen Paketanbieter erneut.</span><span class="sxs-lookup"><span data-stu-id="d8091-122">Re-imports a package provider.</span></span>

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

### <span data-ttu-id="d8091-123">-Forcebootstrap</span><span class="sxs-lookup"><span data-stu-id="d8091-123">-ForceBootstrap</span></span>

<span data-ttu-id="d8091-124">Gibt an, dass dieses Cmdlet Paketverwaltung zum automatischen Installieren des Paket Anbieters erzwingt.</span><span class="sxs-lookup"><span data-stu-id="d8091-124">Indicates that this cmdlet forces Package Management to automatically install the package provider.</span></span>

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

### <span data-ttu-id="d8091-125">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="d8091-125">-MaximumVersion</span></span>

<span data-ttu-id="d8091-126">Gibt die maximal zulässige Version des Paket Anbieters an, den Sie importieren möchten.</span><span class="sxs-lookup"><span data-stu-id="d8091-126">Specifies the maximum allowed version of the package provider that you want to import.</span></span> <span data-ttu-id="d8091-127">Wenn Sie diesen Parameter nicht hinzufügen, `Import-PackageProvider` importiert die höchste verfügbare Version des Anbieters.</span><span class="sxs-lookup"><span data-stu-id="d8091-127">If you do not add this parameter, `Import-PackageProvider` imports the highest available version of the provider.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d8091-128">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="d8091-128">-MinimumVersion</span></span>

<span data-ttu-id="d8091-129">Gibt die minimale zulässige Version des Paket Anbieters an, den Sie importieren möchten.</span><span class="sxs-lookup"><span data-stu-id="d8091-129">Specifies the minimum allowed version of the package provider that you want to import.</span></span> <span data-ttu-id="d8091-130">Wenn Sie diesen Parameter nicht hinzufügen, `Import-PackageProvider` importiert die höchste verfügbare Version des Pakets, das auch eine beliebige maximale Version erfüllt, die mithilfe des *MaximumVersion* -Parameters angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="d8091-130">If you do not add this parameter, `Import-PackageProvider` imports the highest available version of the package that also satisfies any maximum version that is specified using the *MaximumVersion* parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d8091-131">-Name</span><span class="sxs-lookup"><span data-stu-id="d8091-131">-Name</span></span>

<span data-ttu-id="d8091-132">Gibt einen oder mehrere Paketanbieter Namen an.</span><span class="sxs-lookup"><span data-stu-id="d8091-132">Specifies one or more package provider names.</span></span> <span data-ttu-id="d8091-133">Platzhalter sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="d8091-133">Wildcards are not permitted.</span></span>

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

### <span data-ttu-id="d8091-134">-Requirements dversion</span><span class="sxs-lookup"><span data-stu-id="d8091-134">-RequiredVersion</span></span>

<span data-ttu-id="d8091-135">Gibt die genaue Version des Paket Anbieters an, den Sie importieren möchten.</span><span class="sxs-lookup"><span data-stu-id="d8091-135">Specifies the exact version of the package provider that you want to import.</span></span> <span data-ttu-id="d8091-136">Wenn Sie diesen Parameter nicht hinzufügen, `Import-PackageProvider` importiert die höchste verfügbare Version des Anbieters, der auch jede mit dem **MaximumVersion** -Parameter angegebene maximale Version erfüllt.</span><span class="sxs-lookup"><span data-stu-id="d8091-136">If you do not add this parameter, `Import-PackageProvider` imports the highest available version of the provider that also satisfies any maximum version specified using the **MaximumVersion** parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d8091-137">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d8091-137">CommonParameters</span></span>

<span data-ttu-id="d8091-138">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d8091-138">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d8091-139">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d8091-139">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d8091-140">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="d8091-140">INPUTS</span></span>

### <span data-ttu-id="d8091-141">Microsoft. packagemanagement. Implementation. packageprovider</span><span class="sxs-lookup"><span data-stu-id="d8091-141">Microsoft.PackageManagement.Implementation.PackageProvider</span></span>

<span data-ttu-id="d8091-142">Sie können ein von zurück gegebenes **packageprovider** -Objekt über die Pipeline an übergeben `Get-PackageProvider` `Import-PackageProvider` .</span><span class="sxs-lookup"><span data-stu-id="d8091-142">You can pipe a **PackageProvider** object returned by `Get-PackageProvider` into `Import-PackageProvider`.</span></span>

## <span data-ttu-id="d8091-143">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="d8091-143">OUTPUTS</span></span>

## <span data-ttu-id="d8091-144">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="d8091-144">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d8091-145">Ab dem 2020 unterstützt die PowerShell-Katalog nicht mehr Transport Layer Security (TLS)-Versionen 1,0 und 1,1.</span><span class="sxs-lookup"><span data-stu-id="d8091-145">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="d8091-146">Wenn Sie TLS 1,2 oder höher nicht verwenden, erhalten Sie eine Fehlermeldung, wenn Sie versuchen, auf die PowerShell-Katalog zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="d8091-146">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="d8091-147">Verwenden Sie den folgenden Befehl, um sicherzustellen, dass Sie TLS 1,2 verwenden:</span><span class="sxs-lookup"><span data-stu-id="d8091-147">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="d8091-148">Weitere Informationen finden Sie in der [Ankündigung](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) im PowerShell-Blog.</span><span class="sxs-lookup"><span data-stu-id="d8091-148">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="d8091-149">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="d8091-149">RELATED LINKS</span></span>

[<span data-ttu-id="d8091-150">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="d8091-150">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="d8091-151">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="d8091-151">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)

[<span data-ttu-id="d8091-152">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="d8091-152">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="d8091-153">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="d8091-153">Register-PackageSource</span></span>](Register-PackageSource.md)

[<span data-ttu-id="d8091-154">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="d8091-154">Get-PackageProvider</span></span>](Get-PackageProvider.md)
