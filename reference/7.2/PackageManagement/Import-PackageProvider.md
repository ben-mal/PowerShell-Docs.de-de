---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
Locale: en-US
Module Name: PackageManagement
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/packagemanagement/import-packageprovider?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-PackageProvider
ms.openlocfilehash: 6c19d1cbc7b7e4dc37e24c466f83efae688f3cec
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "99603701"
---
# <span data-ttu-id="47291-102">Import-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="47291-102">Import-PackageProvider</span></span>

## <span data-ttu-id="47291-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="47291-103">SYNOPSIS</span></span>
<span data-ttu-id="47291-104">Fügt der aktuellen Sitzung Paketverwaltung Paketanbieter hinzu.</span><span class="sxs-lookup"><span data-stu-id="47291-104">Adds Package Management package providers to the current session.</span></span>

## <span data-ttu-id="47291-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="47291-105">SYNTAX</span></span>

```
Import-PackageProvider [-Name] <String[]> [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-Force] [-ForceBootstrap] [<CommonParameters>]
```

## <span data-ttu-id="47291-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="47291-106">DESCRIPTION</span></span>

<span data-ttu-id="47291-107">Mit dem- `Import-PackageProvider` Cmdlet wird der aktuellen Sitzung mindestens ein Paketanbieter hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="47291-107">The `Import-PackageProvider` cmdlet adds one or more package providers to the current session.</span></span>
<span data-ttu-id="47291-108">Der von Ihnen importierte Anbieter muss auf dem lokalen Computer installiert sein.</span><span class="sxs-lookup"><span data-stu-id="47291-108">The provider that you import must be installed on the local computer.</span></span>

<span data-ttu-id="47291-109">Führen Sie aus, um eine Liste der verfügbaren Anbieter zu erhalten `Get-PackageProvider -ListAvailable` .</span><span class="sxs-lookup"><span data-stu-id="47291-109">To get a list of available providers, run `Get-PackageProvider -ListAvailable`.</span></span>
<span data-ttu-id="47291-110">Beachten Sie, dass sich der Name eines Paket Anbieters vom Modulnamen unterscheiden kann.</span><span class="sxs-lookup"><span data-stu-id="47291-110">Note that a package provider name can be different from its module name.</span></span>

<span data-ttu-id="47291-111">Aus Sicherheitsgründen erfordert **packagemanagement** , dass c#-basierte Anbieter einen enthalten `provider.manifest` .</span><span class="sxs-lookup"><span data-stu-id="47291-111">Due to security reasons, **PackageManagement** requires C#-based providers to contain a `provider.manifest`.</span></span> <span data-ttu-id="47291-112">Weitere Informationen zum Erstellen eines Anbieters mit `provider.manifest` injiziertem finden Sie in den `.csproj` Projektdateien unter [https://github.com/oneget/oneget](https://github.com/oneget/oneget) .</span><span class="sxs-lookup"><span data-stu-id="47291-112">For more information on how to build a provider with `provider.manifest` injected, see the `.csproj` project files on [https://github.com/oneget/oneget](https://github.com/oneget/oneget).</span></span>

## <span data-ttu-id="47291-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="47291-113">EXAMPLES</span></span>

### <span data-ttu-id="47291-114">Beispiel 1: Importieren eines Paket Anbieters vom lokalen Computer</span><span class="sxs-lookup"><span data-stu-id="47291-114">Example 1: Import a package provider from the local computer</span></span>

```powershell
PS C:\> Import-PackageProvider -Name "Nuget"
```

<span data-ttu-id="47291-115">Dieser Befehl importiert den nuget-Anbieter, nachdem er auf dem lokalen Computer installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="47291-115">This command imports the Nuget provider after it has been installed on the local computer.</span></span>

### <span data-ttu-id="47291-116">Beispiel 2: Importieren einer bestimmten Version eines Paket Anbieters</span><span class="sxs-lookup"><span data-stu-id="47291-116">Example 2: Import a specific version of a package provider</span></span>

```powershell
PS C:\> Find-PackageProvider -Name "Nuget" -AllVersions
Install-PackageProvider -Name "Nuget" -RequiredVersion "2.8.5.201" -Force
Get-PackageProvider -ListAvailable
Import-PackageProvider -Name "Nuget" -RequiredVersion "2.8.5.201" -Verbose
```

<span data-ttu-id="47291-117">Mit diesem Befehl wird eine bestimmte Version des nuget-Paket Anbieters ermittelt, installiert und importiert.</span><span class="sxs-lookup"><span data-stu-id="47291-117">This command finds, installs, and imports a specific version of the Nuget package provider.</span></span>

## <span data-ttu-id="47291-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="47291-118">PARAMETERS</span></span>

### <span data-ttu-id="47291-119">-Force</span><span class="sxs-lookup"><span data-stu-id="47291-119">-Force</span></span>

<span data-ttu-id="47291-120">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="47291-120">Forces the command to run without asking for user confirmation.</span></span>
<span data-ttu-id="47291-121">Importiert einen Paketanbieter erneut.</span><span class="sxs-lookup"><span data-stu-id="47291-121">Re-imports a package provider.</span></span>

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

### <span data-ttu-id="47291-122">-Forcebootstrap</span><span class="sxs-lookup"><span data-stu-id="47291-122">-ForceBootstrap</span></span>

<span data-ttu-id="47291-123">Gibt an, dass dieses Cmdlet Paketverwaltung zum automatischen Installieren des Paket Anbieters erzwingt.</span><span class="sxs-lookup"><span data-stu-id="47291-123">Indicates that this cmdlet forces Package Management to automatically install the package provider.</span></span>

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

### <span data-ttu-id="47291-124">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="47291-124">-MaximumVersion</span></span>

<span data-ttu-id="47291-125">Gibt die maximal zulässige Version des Paket Anbieters an, den Sie importieren möchten.</span><span class="sxs-lookup"><span data-stu-id="47291-125">Specifies the maximum allowed version of the package provider that you want to import.</span></span> <span data-ttu-id="47291-126">Wenn Sie diesen Parameter nicht hinzufügen, `Import-PackageProvider` importiert die höchste verfügbare Version des Anbieters.</span><span class="sxs-lookup"><span data-stu-id="47291-126">If you do not add this parameter, `Import-PackageProvider` imports the highest available version of the provider.</span></span>

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

### <span data-ttu-id="47291-127">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="47291-127">-MinimumVersion</span></span>

<span data-ttu-id="47291-128">Gibt die minimale zulässige Version des Paket Anbieters an, den Sie importieren möchten.</span><span class="sxs-lookup"><span data-stu-id="47291-128">Specifies the minimum allowed version of the package provider that you want to import.</span></span> <span data-ttu-id="47291-129">Wenn Sie diesen Parameter nicht hinzufügen, `Import-PackageProvider` importiert die höchste verfügbare Version des Pakets, das auch eine beliebige maximale Version erfüllt, die mithilfe des *MaximumVersion* -Parameters angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="47291-129">If you do not add this parameter, `Import-PackageProvider` imports the highest available version of the package that also satisfies any maximum version that is specified using the *MaximumVersion* parameter.</span></span>

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

### <span data-ttu-id="47291-130">-Name</span><span class="sxs-lookup"><span data-stu-id="47291-130">-Name</span></span>

<span data-ttu-id="47291-131">Gibt einen oder mehrere Paketanbieter Namen an.</span><span class="sxs-lookup"><span data-stu-id="47291-131">Specifies one or more package provider names.</span></span> <span data-ttu-id="47291-132">Platzhalter sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="47291-132">Wildcards are not permitted.</span></span>

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

### <span data-ttu-id="47291-133">-Requirements dversion</span><span class="sxs-lookup"><span data-stu-id="47291-133">-RequiredVersion</span></span>

<span data-ttu-id="47291-134">Gibt die genaue Version des Paket Anbieters an, den Sie importieren möchten.</span><span class="sxs-lookup"><span data-stu-id="47291-134">Specifies the exact version of the package provider that you want to import.</span></span> <span data-ttu-id="47291-135">Wenn Sie diesen Parameter nicht hinzufügen, `Import-PackageProvider` importiert die höchste verfügbare Version des Anbieters, der auch jede mit dem **MaximumVersion** -Parameter angegebene maximale Version erfüllt.</span><span class="sxs-lookup"><span data-stu-id="47291-135">If you do not add this parameter, `Import-PackageProvider` imports the highest available version of the provider that also satisfies any maximum version specified using the **MaximumVersion** parameter.</span></span>

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

### <span data-ttu-id="47291-136">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="47291-136">CommonParameters</span></span>

<span data-ttu-id="47291-137">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="47291-137">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="47291-138">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="47291-138">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="47291-139">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="47291-139">INPUTS</span></span>

### <span data-ttu-id="47291-140">Microsoft. packagemanagement. Implementation. packageprovider</span><span class="sxs-lookup"><span data-stu-id="47291-140">Microsoft.PackageManagement.Implementation.PackageProvider</span></span>

<span data-ttu-id="47291-141">Sie können ein von zurück gegebenes **packageprovider** -Objekt über die Pipeline an übergeben `Get-PackageProvider` `Import-PackageProvider` .</span><span class="sxs-lookup"><span data-stu-id="47291-141">You can pipe a **PackageProvider** object returned by `Get-PackageProvider` into `Import-PackageProvider`.</span></span>

## <span data-ttu-id="47291-142">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="47291-142">OUTPUTS</span></span>

## <span data-ttu-id="47291-143">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="47291-143">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="47291-144">Ab April 2020 unterstützt der PowerShell-Katalog die TLS-Versionen (Transport Layer Security) 1.0 und 1.1 nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="47291-144">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="47291-145">Wenn Sie nicht TLS 1.2 oder höher verwenden, erhalten Sie beim Versuch des Zugriffs auf den PowerShell-Katalog eine Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="47291-145">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="47291-146">Mit dem folgenden Befehl können Sie sicherstellen, dass Sie TLS 1.2 verwenden:</span><span class="sxs-lookup"><span data-stu-id="47291-146">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="47291-147">Weitere Informationen finden Sie im PowerShell-Blog in der [Ankündigung](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/).</span><span class="sxs-lookup"><span data-stu-id="47291-147">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="47291-148">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="47291-148">RELATED LINKS</span></span>

[<span data-ttu-id="47291-149">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="47291-149">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="47291-150">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="47291-150">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)

[<span data-ttu-id="47291-151">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="47291-151">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="47291-152">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="47291-152">Register-PackageSource</span></span>](Register-PackageSource.md)

[<span data-ttu-id="47291-153">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="47291-153">Get-PackageProvider</span></span>](Get-PackageProvider.md)
