---
ms.date: 07/23/2020
keywords: DSC,PowerShell,Konfiguration,Setup,Einrichtung
title: DSC-Ressourcen
ms.openlocfilehash: 6ab831c9d423c6189951b43bfab92f800366ceca
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87777930"
---
# <a name="dsc-resources"></a><span data-ttu-id="d359e-103">DSC-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="d359e-103">DSC Resources</span></span>

> <span data-ttu-id="d359e-104">Gilt für Windows PowerShell 4.0 und höher.</span><span class="sxs-lookup"><span data-stu-id="d359e-104">Applies to Windows PowerShell 4.0 and up.</span></span>

## <a name="overview"></a><span data-ttu-id="d359e-105">Übersicht</span><span class="sxs-lookup"><span data-stu-id="d359e-105">Overview</span></span>

<span data-ttu-id="d359e-106">DSC-Ressourcen sind die Bausteine einer DSC-Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="d359e-106">Desired State Configuration (DSC) Resources provide the building blocks for a DSC configuration.</span></span> <span data-ttu-id="d359e-107">Eine Ressource macht Eigenschaften verfügbar, die konfiguriert werden können (Schema), und enthält die PowerShell-Skriptfunktionen, die der lokale Konfigurations-Manager wie gewünscht ausführt.</span><span class="sxs-lookup"><span data-stu-id="d359e-107">A resource exposes properties that can be configured (schema) and contains the PowerShell script functions that the Local Configuration Manager (LCM) calls to "make it so".</span></span>

<span data-ttu-id="d359e-108">Mit einer Ressource kann etwas Allgemeines wie eine Datei oder Spezifisches wie eine IIS-Servereinstellung modelliert werden.</span><span class="sxs-lookup"><span data-stu-id="d359e-108">A resource can model something as generic as a file or as specific as an IIS server setting.</span></span> <span data-ttu-id="d359e-109">Gruppen ähnlicher Ressourcen werden in einem DSC-Modul kombiniert, das alle erforderlichen Dateien in einer Struktur organisiert, die portierbar ist und Metadaten zum Bestimmen des Zwecks der Ressourcen enthält.</span><span class="sxs-lookup"><span data-stu-id="d359e-109">Groups of like resources are combined in to a DSC Module, which organizes all the required files in to a structure that is portable and includes metadata to identify how the resources are intended to be used.</span></span>

<span data-ttu-id="d359e-110">Jede Ressource verfügt über ein \*schema, das die Syntax bestimmt, die für die Verwendung der Ressource in einer [Konfiguration](../configurations/configurations.md) erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="d359e-110">Each resource has a \*schema that determines the syntax needed to use the resource in a [Configuration](../configurations/configurations.md).</span></span>
<span data-ttu-id="d359e-111">Das Schema einer Ressource kann auf folgende Weise definiert werden:</span><span class="sxs-lookup"><span data-stu-id="d359e-111">A resource's schema can be defined in the following ways:</span></span>

- <span data-ttu-id="d359e-112">`Schema.Mof`-Datei: Die meisten Ressourcen definieren ihr _Schema_ mithilfe des [Managed Object Format (MOF)](/windows/desktop/wmisdk/managed-object-format--mof-) in der Datei `schema.mof`.</span><span class="sxs-lookup"><span data-stu-id="d359e-112">`Schema.Mof` file: Most resources define their _schema_ in a `schema.mof` file, using [Managed Object Format](/windows/desktop/wmisdk/managed-object-format--mof-).</span></span>
- <span data-ttu-id="d359e-113">`<Resource Name>.schema.psm1`-Datei: [Zusammengesetzte Ressourcen](../configurations/compositeConfigs.md) definieren ihr _Schema_ in einer Datei `<ResourceName>.schema.psm1` unter Verwendung eines [Parameterblocks](/powershell/module/microsoft.powershell.core/about/about_functions?view=powershell-6#functions-with-parameters).</span><span class="sxs-lookup"><span data-stu-id="d359e-113">`<Resource Name>.schema.psm1` file: [Composite Resources](../configurations/compositeConfigs.md) define their _schema_ in a `<ResourceName>.schema.psm1` file using a [Parameter Block](/powershell/module/microsoft.powershell.core/about/about_functions?view=powershell-6#functions-with-parameters).</span></span>
- <span data-ttu-id="d359e-114">`<Resource Name>.psm1`-Datei: Klassenbasierte DSC-Ressourcen definieren ihr _Schema_ in der Klassendefinition.</span><span class="sxs-lookup"><span data-stu-id="d359e-114">`<Resource Name>.psm1` file: Class based DSC resources define their _schema_ in the class definition.</span></span> <span data-ttu-id="d359e-115">Syntaxelemente werden als Eigenschaften der Klasse angegeben.</span><span class="sxs-lookup"><span data-stu-id="d359e-115">Syntax items are denoted as Class properties.</span></span> <span data-ttu-id="d359e-116">Weitere Informationen finden Sie unter [about_Classes](/powershell/module/psdesiredstateconfiguration/about/about_classes_and_dsc).</span><span class="sxs-lookup"><span data-stu-id="d359e-116">For more information, see [about_Classes](/powershell/module/psdesiredstateconfiguration/about/about_classes_and_dsc).</span></span>

<span data-ttu-id="d359e-117">Verwenden Sie zum Abrufen der Syntax für eine DSC-Ressource das Cmdlet [Get-DSCResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) mit dem Parameter **Syntax**.</span><span class="sxs-lookup"><span data-stu-id="d359e-117">To retrieve the syntax for a DSC resource, use the [Get-DSCResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) cmdlet with the **Syntax** parameter.</span></span> <span data-ttu-id="d359e-118">Dieser Vorgang ähnelt der Verwendung von [Get-Command](/powershell/module/microsoft.powershell.core/get-command) mit dem Parameter **Syntax**, um die Cmdlet-Syntax abzurufen.</span><span class="sxs-lookup"><span data-stu-id="d359e-118">This usage is similar to using [Get-Command](/powershell/module/microsoft.powershell.core/get-command) with the **Syntax** parameter to get cmdlet syntax.</span></span> <span data-ttu-id="d359e-119">Die Ausgabe, die Sie sehen, zeigt die Vorlage für einen Ressourcenblock für die Ressource an, die Sie angeben.</span><span class="sxs-lookup"><span data-stu-id="d359e-119">The output you see will show the template used for a resource block for the resource you specify.</span></span>

```powershell
Get-DscResource -Syntax Service
```

<span data-ttu-id="d359e-120">Die Ausgabe, die Sie sehen, sollte der folgenden Ausgabe ähneln, obwohl sich die Syntax dieser Ressource in Zukunft ändern kann.</span><span class="sxs-lookup"><span data-stu-id="d359e-120">The output you see should be similar to the output below, though this resource's syntax could change in the future.</span></span> <span data-ttu-id="d359e-121">Wie bei der Cmdlet-Syntax sind die _Schlüssel_ in eckigen Klammern optional.</span><span class="sxs-lookup"><span data-stu-id="d359e-121">Like cmdlet syntax, the _keys_ seen in square brackets, are optional.</span></span> <span data-ttu-id="d359e-122">Die Typen geben den Typ der Daten an, die jeder Schlüssel erwartet.</span><span class="sxs-lookup"><span data-stu-id="d359e-122">The types specify the type of data each key expects.</span></span>

> [!NOTE]
> <span data-ttu-id="d359e-123">Der Schlüssel **Ensure** ist optional, da er standardmäßig auf „Present“ (Vorhanden) festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="d359e-123">The **Ensure** key is optional because it defaults to "Present".</span></span>

```output
Service [String] #ResourceName
{
    Name = [string]
    [BuiltInAccount = [string]{ LocalService | LocalSystem | NetworkService }]
    [Credential = [PSCredential]]
    [Dependencies = [string[]]]
    [DependsOn = [string[]]]
    [Description = [string]]
    [DisplayName = [string]]
    [Ensure = [string]{ Absent | Present }]
    [Path = [string]]
    [PsDscRunAsCredential = [PSCredential]]
    [StartupType = [string]{ Automatic | Disabled | Manual }]
    [State = [string]{ Running | Stopped }]
}
```

> [!NOTE]
> <span data-ttu-id="d359e-124">In Versionen vor PowerShell 7.0 findet `Get-DscResource` keine klassenbasierten DSC-Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="d359e-124">In PowerShell versions below 7.0, `Get-DscResource` does not find Class based DSC resources.</span></span>

<span data-ttu-id="d359e-125">Innerhalb einer Konfiguration könnte ein **Service**-Ressourcenblock wie folgt aussehen, um sicherzustellen (**Ensure**), dass der Spoolerdienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d359e-125">Inside a Configuration, a **Service** resource block might look like this to **Ensure** that the Spooler service is running.</span></span>

> [!NOTE]
> <span data-ttu-id="d359e-126">Bevor Sie eine Ressource in einer Konfiguration verwenden, müssen Sie sie mit [Import-DSCResource](../configurations/import-dscresource.md) importieren.</span><span class="sxs-lookup"><span data-stu-id="d359e-126">Before using a resource in a Configuration, you must import it using [Import-DSCResource](../configurations/import-dscresource.md).</span></span>

```powershell
Configuration TestConfig
{
    # It is best practice to always directly import resources, even if the resource is a built-in resource.
    Import-DSCResource -Name Service
    Node localhost
    {
        # The name of this resource block, can be anything you choose, as long as it is of type [String] as indicated by the schema.
        Service "Spooler:Running"
        {
            Name = "Spooler"
            State = "Running"
        }
    }
}
```

<span data-ttu-id="d359e-127">Konfigurationen können mehrere Instanzen desselben Ressourcentyps enthalten.</span><span class="sxs-lookup"><span data-stu-id="d359e-127">Configurations can contain multiple instances of the same resource type.</span></span> <span data-ttu-id="d359e-128">Jede Instanz muss eindeutig benannt sein.</span><span class="sxs-lookup"><span data-stu-id="d359e-128">Each instance must be uniquely named.</span></span> <span data-ttu-id="d359e-129">Im folgenden Beispiel wird ein zweiter **Service**-Ressourcenblock zum Konfigurieren des „DHCP“-Diensts hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="d359e-129">In the following example, a second **Service** resource block is added to configure the "DHCP" service.</span></span>

```powershell
Configuration TestConfig
{
    # It is best practice to always directly import resources, even if the resource is a built-in resource.
    Import-DSCResource -Name Service
    Node localhost
    {
        # The name of this resource block, can be anything you choose, as long as it is of type [String] as indicated by the schema.
        Service "Spooler:Running"
        {
            Name = "Spooler"
            State = "Running"
        }

        # To configure a second service resource block, add another Service resource block and use a unique name.
        Service "DHCP:Running"
        {
            Name = "DHCP"
            State = "Running"
        }
    }
}
```

> [!NOTE]
> <span data-ttu-id="d359e-130">Ab PowerShell 5.0 wurde IntelliSense für DSC hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="d359e-130">Beginning in PowerShell 5.0, IntelliSense was added for DSC.</span></span> <span data-ttu-id="d359e-131">Dieses neue Feature ermöglicht Ihnen, <kbd>TAB-TASTE</kbd> und <kbd>STRG</kbd>+<kbd>LEERTASTE</kbd> zum automatischen Vervollständigen von Schlüsselnamen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="d359e-131">This new feature allows you to use <kbd>TAB</kbd> and <kbd>Ctr</kbd>+<kbd>Space</kbd> to auto-complete key names.</span></span>

![IntelliSense für Ressourcen mithilfe der Vervollständigung mit der TAB-TASTE](media/resources/resource-tabcompletion.png)

## <a name="types-of-resources"></a><span data-ttu-id="d359e-133">Ressourcentypen</span><span class="sxs-lookup"><span data-stu-id="d359e-133">Types of resources</span></span>

<span data-ttu-id="d359e-134">Windows bietet integrierte Ressourcen, Linux betriebssystemspezifische Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="d359e-134">Windows comes with built in resources and Linux has OS specific resources.</span></span> <span data-ttu-id="d359e-135">Es gibt Ressourcen für [ knotenübergreifende Abhängigkeiten](../configurations/crossNodeDependencies.md), Ressourcen für die Paketverwaltung sowie [von der Community bereitgestellte und gepflegte Ressourcen](https://github.com/dsccommunity).</span><span class="sxs-lookup"><span data-stu-id="d359e-135">There are resources for [cross-node dependencies](../configurations/crossNodeDependencies.md), package management resources, as well as[community owned and maintained resources](https://github.com/dsccommunity).</span></span> <span data-ttu-id="d359e-136">Mit den oben genannten Schritten können Sie die Syntax dieser Ressourcen und deren Verwendung festlegen.</span><span class="sxs-lookup"><span data-stu-id="d359e-136">You can use the above steps to determine the syntax of these resources and how to use them.</span></span> <span data-ttu-id="d359e-137">Die Seiten, die diese Ressourcen verarbeiten, wurden unter **Reference** archiviert.</span><span class="sxs-lookup"><span data-stu-id="d359e-137">The pages that serve these resources have been archived under **Reference**.</span></span>

### <a name="windows-built-in-resources"></a><span data-ttu-id="d359e-138">Integrierte Windows-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="d359e-138">Windows built-in resources</span></span>

- [<span data-ttu-id="d359e-139">Archive-Ressource</span><span class="sxs-lookup"><span data-stu-id="d359e-139">Archive Resource</span></span>](../reference/resources/windows/archiveResource.md)
- [<span data-ttu-id="d359e-140">Environment-Ressource</span><span class="sxs-lookup"><span data-stu-id="d359e-140">Environment Resource</span></span>](../reference/resources/windows/environmentResource.md)
- [<span data-ttu-id="d359e-141">File-Ressource</span><span class="sxs-lookup"><span data-stu-id="d359e-141">File Resource</span></span>](../reference/resources/windows/fileResource.md)
- [<span data-ttu-id="d359e-142">Group-Ressource</span><span class="sxs-lookup"><span data-stu-id="d359e-142">Group Resource</span></span>](../reference/resources/windows/groupResource.md)
- [<span data-ttu-id="d359e-143">GroupSet-Ressource</span><span class="sxs-lookup"><span data-stu-id="d359e-143">GroupSet Resource</span></span>](../reference/resources/windows/groupSetResource.md)
- [<span data-ttu-id="d359e-144">Log-Ressource</span><span class="sxs-lookup"><span data-stu-id="d359e-144">Log Resource</span></span>](../reference/resources/windows/logResource.md)
- [<span data-ttu-id="d359e-145">Package-Ressource</span><span class="sxs-lookup"><span data-stu-id="d359e-145">Package Resource</span></span>](../reference/resources/windows/packageResource.md)
- [<span data-ttu-id="d359e-146">ProcessSet-Ressource</span><span class="sxs-lookup"><span data-stu-id="d359e-146">ProcessSet Resource</span></span>](../reference/resources/windows/ProcessSetResource.md)
- [<span data-ttu-id="d359e-147">Registry-Ressource</span><span class="sxs-lookup"><span data-stu-id="d359e-147">Registry Resource</span></span>](../reference/resources/windows/registryResource.md)
- [<span data-ttu-id="d359e-148">Script-Ressource</span><span class="sxs-lookup"><span data-stu-id="d359e-148">Script Resource</span></span>](../reference/resources/windows/scriptResource.md)
- [<span data-ttu-id="d359e-149">Service-Ressource</span><span class="sxs-lookup"><span data-stu-id="d359e-149">Service Resource</span></span>](../reference/resources/windows/serviceResource.md)
- [<span data-ttu-id="d359e-150">ServiceSet-Ressource</span><span class="sxs-lookup"><span data-stu-id="d359e-150">ServiceSet Resource</span></span>](../reference/resources/windows/serviceSetResource.md)
- [<span data-ttu-id="d359e-151">User-Ressource</span><span class="sxs-lookup"><span data-stu-id="d359e-151">User Resource</span></span>](../reference/resources/windows/userResource.md)
- [<span data-ttu-id="d359e-152">WindowsFeature-Ressource</span><span class="sxs-lookup"><span data-stu-id="d359e-152">WindowsFeature Resource</span></span>](../reference/resources/windows/windowsFeatureResource.md)
- [<span data-ttu-id="d359e-153">WindowsFeatureSet-Ressource</span><span class="sxs-lookup"><span data-stu-id="d359e-153">WindowsFeatureSet Resource</span></span>](../reference/resources/windows/windowsFeatureSetResource.md)
- [<span data-ttu-id="d359e-154">WindowsOptionalFeature-Ressource</span><span class="sxs-lookup"><span data-stu-id="d359e-154">WindowsOptionalFeature Resource</span></span>](../reference/resources/windows/windowsOptionalFeatureResource.md)
- [<span data-ttu-id="d359e-155">WindowsOptionalFeatureSet-Ressource</span><span class="sxs-lookup"><span data-stu-id="d359e-155">WindowsOptionalFeatureSet Resource</span></span>](../reference/resources/windows/windowsOptionalFeatureSetResource.md)
- [<span data-ttu-id="d359e-156">WindowsPackageCabResource-Ressource</span><span class="sxs-lookup"><span data-stu-id="d359e-156">WindowsPackageCabResource Resource</span></span>](../reference/resources/windows/windowsPackageCabResource.md)
- [<span data-ttu-id="d359e-157">WindowsProcess-Ressource</span><span class="sxs-lookup"><span data-stu-id="d359e-157">WindowsProcess Resource</span></span>](../reference/resources/windows/windowsProcessResource.md)

### <a name="cross-node-dependency-resources"></a><span data-ttu-id="d359e-158">Ressourcen mit knotenübergreifenden Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="d359e-158">Cross-Node dependency resources</span></span>

- [<span data-ttu-id="d359e-159">WaitForAll-Ressource</span><span class="sxs-lookup"><span data-stu-id="d359e-159">WaitForAll Resource</span></span>](../reference/resources/windows/waitForAllResource.md)
- [<span data-ttu-id="d359e-160">WaitForSome-Ressource</span><span class="sxs-lookup"><span data-stu-id="d359e-160">WaitForSome Resource</span></span>](../reference/resources/windows/waitForSomeResource.md)
- [<span data-ttu-id="d359e-161">WaitForAny-Ressource</span><span class="sxs-lookup"><span data-stu-id="d359e-161">WaitForAny Resource</span></span>](../reference/resources/windows/waitForAnyResource.md)

### <a name="package-management-resources"></a><span data-ttu-id="d359e-162">Paketverwaltungsressourcen</span><span class="sxs-lookup"><span data-stu-id="d359e-162">Package Management resources</span></span>

- [<span data-ttu-id="d359e-163">PackageManagement-Ressource</span><span class="sxs-lookup"><span data-stu-id="d359e-163">PackageManagement Resource</span></span>](../reference/resources/packagemanagement/PackageManagementDscResource.md)
- [<span data-ttu-id="d359e-164">PackageManagementSource-Ressource</span><span class="sxs-lookup"><span data-stu-id="d359e-164">PackageManagementSource Resource</span></span>](../reference/resources/packagemanagement/PackageManagementSourceDscResource.md)

#### <a name="linux-resources"></a><span data-ttu-id="d359e-165">Linux-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="d359e-165">Linux resources</span></span>

- [<span data-ttu-id="d359e-166">Linux-Ressource „Archive“</span><span class="sxs-lookup"><span data-stu-id="d359e-166">Linux Archive Resource</span></span>](../reference/resources/linux/lnxArchiveResource.md)
- [<span data-ttu-id="d359e-167">Linux-Resource „Environment“</span><span class="sxs-lookup"><span data-stu-id="d359e-167">Linux Environment Resource</span></span>](../reference/resources/linux/lnxEnvironmentResource.md)
- [<span data-ttu-id="d359e-168">Linux-Ressource „FileLine“</span><span class="sxs-lookup"><span data-stu-id="d359e-168">Linux FileLine Resource</span></span>](../reference/resources/linux/lnxFileLineResource.md)
- [<span data-ttu-id="d359e-169">Linux-Ressource „File“</span><span class="sxs-lookup"><span data-stu-id="d359e-169">Linux File Resource</span></span>](../reference/resources/linux/lnxFileResource.md)
- [<span data-ttu-id="d359e-170">Linux-Ressource „Group“</span><span class="sxs-lookup"><span data-stu-id="d359e-170">Linux Group Resource</span></span>](../reference/resources/linux/lnxGroupResource.md)
- [<span data-ttu-id="d359e-171">Linux-Ressource „Package“</span><span class="sxs-lookup"><span data-stu-id="d359e-171">Linux Package Resource</span></span>](../reference/resources/linux/lnxPackageResource.md)
- [<span data-ttu-id="d359e-172">Linux-Ressource „Script“</span><span class="sxs-lookup"><span data-stu-id="d359e-172">Linux Script Resource</span></span>](../reference/resources/linux/lnxScriptResource.md)
- [<span data-ttu-id="d359e-173">Linux-Ressource „Service“</span><span class="sxs-lookup"><span data-stu-id="d359e-173">Linux Service Resource</span></span>](../reference/resources/linux/lnxServiceResource.md)
- [<span data-ttu-id="d359e-174">Linux-Ressource „SshAuthorizedKeys“</span><span class="sxs-lookup"><span data-stu-id="d359e-174">Linux SshAuthorizedKeys Resource</span></span>](../reference/resources/linux/lnxSshAuthorizedKeysResource.md)
- [<span data-ttu-id="d359e-175">Linux-Ressource „User“</span><span class="sxs-lookup"><span data-stu-id="d359e-175">Linux User Resource</span></span>](../reference/resources/linux/lnxUserResource.md)
