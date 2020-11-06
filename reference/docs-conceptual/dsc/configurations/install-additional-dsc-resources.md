---
ms.date: 12/12/2018
keywords: DSC,PowerShell,Ressource,Katalog,Setup
title: Installieren zusätzlicher DSC-Ressourcen
description: In diesem Artikel sind die DSC-Ressourcen im Modul PSDesiredStateConfiguration aufgeführt. Außerdem wird erläutert, wie Sie Ressourcen im PowerShell-Katalog suchen und installieren.
ms.openlocfilehash: e75561ed539e06716c9a103f905b9d1e4f3e71d3
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92645133"
---
# <a name="install-additional-dsc-resources"></a><span data-ttu-id="c8a3a-105">Installieren zusätzlicher DSC-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="c8a3a-105">Install Additional DSC Resources</span></span>

<span data-ttu-id="c8a3a-106">PowerShell umfasst mehrere vorgefertigte Ressourcen für die Desired State Configuration (DSC).</span><span class="sxs-lookup"><span data-stu-id="c8a3a-106">PowerShell includes several Out-of-the-box resources for Desired State Configuration (DSC).</span></span> <span data-ttu-id="c8a3a-107">Das **PSDesiredStateConfiguration** -Modul enthält alle für Ihre spezifische Instanz von PowerShell verfügbaren OOB-DSC-Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="c8a3a-107">The **PSDesiredStateConfiguration** module contains all of the OOB DSC resources available on your specific instance of PowerShell.</span></span>

<span data-ttu-id="c8a3a-108">Hier finden Sie eine Liste der in PowerShell 4.0 enthaltenen OOB-Ressourcen sowie Beschreibungen der Funktionen der Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="c8a3a-108">This is a list of the OOB resources included in PowerShell 4.0 and a description of the resource's capabilities.</span></span>

> [!NOTE]
> <span data-ttu-id="c8a3a-109">Diese Liste ist unvollständig, da die Anzahl der OOB-Ressourcen mit jeder Version von PowerShell gewachsen ist.</span><span class="sxs-lookup"><span data-stu-id="c8a3a-109">This is an incomplete list, as the number of OOB resources has grown with each version of PowerShell.</span></span>

|      <span data-ttu-id="c8a3a-110">Resource</span><span class="sxs-lookup"><span data-stu-id="c8a3a-110">Resource</span></span>      |                                                                                       <span data-ttu-id="c8a3a-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c8a3a-111">Description</span></span>                                                                                        |
| ------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="c8a3a-112">**File**</span><span class="sxs-lookup"><span data-stu-id="c8a3a-112">**File**</span></span>           | <span data-ttu-id="c8a3a-113">Steuert den Status der Dateien und Verzeichnisse.</span><span class="sxs-lookup"><span data-stu-id="c8a3a-113">Controls the state of files and directories.</span></span> <span data-ttu-id="c8a3a-114">Kopiert Dateien aus einer **Quelle** in ein **Ziel** und aktualisiert sie bei Änderung der **Quelle** durch Vergleichen von Datumsangaben, Prüfsummen und Hashes.</span><span class="sxs-lookup"><span data-stu-id="c8a3a-114">Copies files from a **Source** to a **Destination** and updates them when the **Source** changes by comparing dates, checksums, and hashes.</span></span> |
| <span data-ttu-id="c8a3a-115">**Archivieren**</span><span class="sxs-lookup"><span data-stu-id="c8a3a-115">**Archive**</span></span>        | <span data-ttu-id="c8a3a-116">Entpackt Archive an einem angegebenen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="c8a3a-116">Unpacks archives and a specified location.</span></span> <span data-ttu-id="c8a3a-117">Überprüft die Archive mit einer angegebenen **Prüfsumme**.</span><span class="sxs-lookup"><span data-stu-id="c8a3a-117">Validates the archives with a specified **Checksum**.</span></span>                                                                                         |
| <span data-ttu-id="c8a3a-118">**Umgebung**</span><span class="sxs-lookup"><span data-stu-id="c8a3a-118">**Environment**</span></span>    | <span data-ttu-id="c8a3a-119">Verwaltet Umgebungsvariablen.</span><span class="sxs-lookup"><span data-stu-id="c8a3a-119">Manages environment variables.</span></span>                                                                                                                                                           |
| <span data-ttu-id="c8a3a-120">**Gruppieren**</span><span class="sxs-lookup"><span data-stu-id="c8a3a-120">**Group**</span></span>          | <span data-ttu-id="c8a3a-121">Verwaltet lokale Gruppen und steuert die Gruppenmitgliedschaft.</span><span class="sxs-lookup"><span data-stu-id="c8a3a-121">Manages local groups and controls group membership.</span></span>                                                                                                                                      |
| <span data-ttu-id="c8a3a-122">**Log**</span><span class="sxs-lookup"><span data-stu-id="c8a3a-122">**Log**</span></span>            | <span data-ttu-id="c8a3a-123">Schreibt Meldungen in das `Microsoft-Windows-Desired State Configuration/Analytic`-Ereignisprotokoll.</span><span class="sxs-lookup"><span data-stu-id="c8a3a-123">Writes messages to the `Microsoft-Windows-Desired State Configuration/Analytic` event log.</span></span>                                                                                               |
| <span data-ttu-id="c8a3a-124">**Paket**</span><span class="sxs-lookup"><span data-stu-id="c8a3a-124">**Package**</span></span>        | <span data-ttu-id="c8a3a-125">Installiert oder deinstalliert Pakete mit **Arguments** , **LogPath** , **ReturnCode** und anderen Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="c8a3a-125">Installs or uninstalls packages using **Arguments** , **LogPath** , **ReturnCode** , other settings.</span></span>                                                                                        |
| <span data-ttu-id="c8a3a-126">**Registrierung**</span><span class="sxs-lookup"><span data-stu-id="c8a3a-126">**Registry**</span></span>       | <span data-ttu-id="c8a3a-127">Verwaltet Registrierungsschlüssel und -werte.</span><span class="sxs-lookup"><span data-stu-id="c8a3a-127">Manages registry keys and values.</span></span>                                                                                                                                                        |
| <span data-ttu-id="c8a3a-128">**Skript**</span><span class="sxs-lookup"><span data-stu-id="c8a3a-128">**Script**</span></span>         | <span data-ttu-id="c8a3a-129">Ermöglicht Ihnen den Entwurf Ihrer eigenen [get-test-set](../resources/get-test-set.md)-Skriptblöcke.</span><span class="sxs-lookup"><span data-stu-id="c8a3a-129">Allows you to design your own [get-test-set](../resources/get-test-set.md) script blocks.</span></span>                                                                                                |
| <span data-ttu-id="c8a3a-130">**Service**</span><span class="sxs-lookup"><span data-stu-id="c8a3a-130">**Service**</span></span>        | <span data-ttu-id="c8a3a-131">Konfiguriert Windows-Dienste.</span><span class="sxs-lookup"><span data-stu-id="c8a3a-131">Configures Windows services.</span></span>                                                                                                                                                             |
| <span data-ttu-id="c8a3a-132">**Benutzer**</span><span class="sxs-lookup"><span data-stu-id="c8a3a-132">**User**</span></span>           | <span data-ttu-id="c8a3a-133">Verwaltet lokale Benutzer und Attribute.</span><span class="sxs-lookup"><span data-stu-id="c8a3a-133">Manages local users and attributes.</span></span>                                                                                                                                                      |
| <span data-ttu-id="c8a3a-134">**WindowsFeature**</span><span class="sxs-lookup"><span data-stu-id="c8a3a-134">**WindowsFeature**</span></span> | <span data-ttu-id="c8a3a-135">Verwaltet Rollen und Features.</span><span class="sxs-lookup"><span data-stu-id="c8a3a-135">Manages roles and features.</span></span>                                                                                                                                                              |
| <span data-ttu-id="c8a3a-136">**WindowsProcess**</span><span class="sxs-lookup"><span data-stu-id="c8a3a-136">**WindowsProcess**</span></span> | <span data-ttu-id="c8a3a-137">Konfiguriert Windows-Prozesse.</span><span class="sxs-lookup"><span data-stu-id="c8a3a-137">Configures Windows processes.</span></span>                                                                                                                                                            |

<span data-ttu-id="c8a3a-138">Die OOB-Ressourcen bieten einen guten Ausgangspunkt für allgemeine Vorgänge.</span><span class="sxs-lookup"><span data-stu-id="c8a3a-138">The OOB resources allow a good starting point for common operations.</span></span> <span data-ttu-id="c8a3a-139">Wenn die OOB-Ressourcen Ihre Anforderungen nicht erfüllen, können Sie Ihre eigene [benutzerdefinierte Ressource](../resources/authoringResource.md) schreiben.</span><span class="sxs-lookup"><span data-stu-id="c8a3a-139">If the OOB resources do not meet your needs, you can write your own [Custom Resource](../resources/authoringResource.md).</span></span> <span data-ttu-id="c8a3a-140">Bevor Sie eine benutzerdefinierte Ressource zur Behebung Ihres Problems schreiben, sollten Sie die große Anzahl von DSC-Ressourcen durchsehen, die bereits von Microsoft und der PowerShell-Community erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="c8a3a-140">Before you write a custom resource to solve your problem, you should look through the vast number of DSC resources that have already been created by both Microsoft and the PowerShell community.</span></span>

<span data-ttu-id="c8a3a-141">DSC-Ressourcen finden Sie sowohl im [PowerShell-Katalog](https://www.powershellgallery.com/) als auch in [GitHub](https://github.com/).</span><span class="sxs-lookup"><span data-stu-id="c8a3a-141">You can find DSC resources in both the [PowerShell Gallery](https://www.powershellgallery.com/) and [GitHub](https://github.com/).</span></span> <span data-ttu-id="c8a3a-142">Sie können DSC-Ressourcen auch mit [PowerShellGet](/powershell/module/powershellget/) direkt über die PowerShell-Konsole installieren.</span><span class="sxs-lookup"><span data-stu-id="c8a3a-142">You can also install DSC resources directly from the PowerShell console using [PowerShellGet](/powershell/module/powershellget/).</span></span>

## <a name="installing-powershellget"></a><span data-ttu-id="c8a3a-143">Installieren von PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="c8a3a-143">Installing PowerShellGet</span></span>

<span data-ttu-id="c8a3a-144">Um festzustellen, ob Sie **PowerShell** bereits besitzen, oder um Hilfe bei der Installation zu erhalten, nutzen Sie die folgende Anleitung: [Installieren von PowerShellGet](/powershell/scripting/gallery/installing-psget).</span><span class="sxs-lookup"><span data-stu-id="c8a3a-144">To determine if you already have **PowerShell** get, or to get help installing it, see the following guide: [Installing PowerShellGet](/powershell/scripting/gallery/installing-psget).</span></span>

## <a name="finding-dsc-resources-using-powershellget"></a><span data-ttu-id="c8a3a-145">Suchen von DSC-Ressourcen mit PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="c8a3a-145">Finding DSC resources using PowerShellGet</span></span>

<span data-ttu-id="c8a3a-146">Sobald **PowerShellGet** auf Ihrem System installiert ist, können Sie im [PowerShell-Katalog](https://www.powershellgallery.com/) gehostete DSC-Ressourcen ermitteln und installieren.</span><span class="sxs-lookup"><span data-stu-id="c8a3a-146">Once **PowerShellGet** is installed on your system, you can find and install DSC resources hosted in the [PowerShell Gallery](https://www.powershellgallery.com/).</span></span>

<span data-ttu-id="c8a3a-147">Suchen Sie zunächst mit dem [Find-DSCResource](/powershell/module/powershellget/find-dscresource)-Cmdlet DSC-Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="c8a3a-147">First, use the [Find-DSCResource](/powershell/module/powershellget/find-dscresource) cmdlet to find DSC resources.</span></span> <span data-ttu-id="c8a3a-148">Wenn Sie `Find-DSCResource` erstmals ausführen, sehen Sie die folgende Aufforderung zum Installieren des „NuGet-Anbieters“.</span><span class="sxs-lookup"><span data-stu-id="c8a3a-148">When you run `Find-DSCResource` for the first time, you see the following prompt to install the "NuGet provider".</span></span>

```
PS> Find-DSCResource

NuGet provider is required to continue
PowerShellGet requires NuGet provider version '2.8.5.201' or newer to interact with NuGet-based
repositories. The NuGet provider must be available in 'C:\Program Files\PackageManagement\ProviderAssemblies'
or 'C:\Users\xAdministrator\AppData\Local\PackageManagement\ProviderAssemblies'. You can also install
the NuGet provider by running 'Install-PackageProvider -Name NuGet -MinimumVersion 2.8.5.201
-Force'. Do you want PowerShellGet to install and import the NuGet provider now?
[Y] Yes  [N] No  [?] Help (default is "Y"):
```

<span data-ttu-id="c8a3a-149">Nach dem Drücken von „j“ wird der „NuGet“-Anbieter installiert, und Sie sehen eine Liste von DSC-Ressourcen, die Sie aus dem PowerShell-Katalog installieren können.</span><span class="sxs-lookup"><span data-stu-id="c8a3a-149">After pressing 'y', the "NuGet" provider is installed, you see a list of DSC resources that you can install from the PowerShell Gallery.</span></span>

> [!NOTE]
> <span data-ttu-id="c8a3a-150">Die Liste wird hier nicht gezeigt, da sie sehr groß ist.</span><span class="sxs-lookup"><span data-stu-id="c8a3a-150">List is not shown because it is very large.</span></span>

<span data-ttu-id="c8a3a-151">Sie können auch mithilfe von Platzhaltern den `-Name`-Parameter angeben, oder den `-Filter`-Parameter ohne Platzhalter, um Ihre Suche einzugrenzen.</span><span class="sxs-lookup"><span data-stu-id="c8a3a-151">You can also specify the `-Name` parameter using wildcards, or `-Filter` parameter without wildcards to narrow down your search.</span></span> <span data-ttu-id="c8a3a-152">In diesem Beispiel wird versucht, eine DSC-Ressource „TimeZone“ mit Platzhaltern zu finden.</span><span class="sxs-lookup"><span data-stu-id="c8a3a-152">This example attempts to find a "TimeZone" DSC resource using the wildcards.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c8a3a-153">Derzeit enthält das `Find-DSCResource`-Cmdlet jedoch einen Fehler, der sowohl im `-Name`- als auch im `-Filter`-Parameter die Suche mit Platzhaltern verhindert.</span><span class="sxs-lookup"><span data-stu-id="c8a3a-153">Currently there is a bug in the `Find-DSCResource` cmdlet that prevents using wildcards in both the `-Name` and `-Filter` parameters.</span></span> <span data-ttu-id="c8a3a-154">Das zweite Beispiel zeigt eine Problemumgehung mit `Where-Object`.</span><span class="sxs-lookup"><span data-stu-id="c8a3a-154">The second example below shows a workaround using `Where-Object`.</span></span>

```
PS> Find-DSCResource -Name *Time*

Name                                Version    ModuleName                          Repository
----                                -------    ----------                          ----------
Carbon_EnvironmentVariable          2.6.0      Carbon                              PSGallery
Carbon_FirewallRule                 2.6.0      Carbon                              PSGallery
Carbon_Group                        2.6.0      Carbon                              PSGallery
Carbon_IniFile                      2.6.0      Carbon                              PSGallery
Carbon_Permission                   2.6.0      Carbon                              PSGallery
Carbon_Privilege                    2.6.0      Carbon                              PSGallery
Carbon_ScheduledTask                2.6.0      Carbon                              PSGallery
Carbon_Service                      2.6.0      Carbon                              PSGallery
TimeZone                            6.0.0.0    ComputerManagementDsc               PSGallery
xTimeZone                           1.8.0.0    xTimeZone                           PSGallery
xSqlServerDefaultDir                1.0.0      mlSqlServerDSC                      PSGallery
xSqlServerMoveDatabaseFiles         1.0.0      mlSqlServerDSC                      PSGallery
xSqlServerSQLDataRoot               1.0.0      mlSqlServerDSC                      PSGallery
xSqlServerStartupParam              1.0.0      mlSqlServerDSC                      PSGallery
```

<span data-ttu-id="c8a3a-155">Sie können auch mit `Where-Object` DSC-Ressourcen mit einer feiner abgestimmten Filterung suchen.</span><span class="sxs-lookup"><span data-stu-id="c8a3a-155">You can also use `Where-Object` to find DSC resources with more granular filtering.</span></span> <span data-ttu-id="c8a3a-156">Dieser Ansatz ist langsamer als die Verwendung der integrierten Filterparameter.</span><span class="sxs-lookup"><span data-stu-id="c8a3a-156">This approach will be slower than using built in filtering parameters.</span></span>

```
PS> Find-DSCResource | Where-Object {$_.Name -like "Time*"}

Name                                Version    ModuleName                          Repository
----                                -------    ----------                          ----------
TimeZone                            6.0.0.0    ComputerManagementDsc               PSGallery
```

<span data-ttu-id="c8a3a-157">Weitere Informationen zur Filterung finden Sie unter [Where-Object](/powershell/module/microsoft.powershell.core/where-object).</span><span class="sxs-lookup"><span data-stu-id="c8a3a-157">For more information on filtering, see [Where-Object](/powershell/module/microsoft.powershell.core/where-object).</span></span>

## <a name="installing-dsc-resources-using-powershellget"></a><span data-ttu-id="c8a3a-158">Installieren von DSC-Ressourcen mit PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="c8a3a-158">Installing DSC Resources using PowerShellGet</span></span>

<span data-ttu-id="c8a3a-159">Installieren Sie eine DSC-Ressource mit dem [Install-Module](/powershell/module/PowershellGet/Install-Module)-Cmdlet, wobei Sie den in den Suchergebnissen unter **ModuleName** angegebenen Namen des Moduls verwenden.</span><span class="sxs-lookup"><span data-stu-id="c8a3a-159">To install a DSC resource, use the [Install-Module](/powershell/module/PowershellGet/Install-Module) cmdlet, specifying the name of the module shown under **Module** name in your search results.</span></span>

<span data-ttu-id="c8a3a-160">Da die Ressource „TimeZone“ sich im Modul „ComputerManagementDSC“ befindet, wird dieses Modul in diesem Beispiel installiert.</span><span class="sxs-lookup"><span data-stu-id="c8a3a-160">The "TimeZone" resource exists in the "ComputerManagementDSC" module, so that is the module this example installs.</span></span>

> [!NOTE]
> <span data-ttu-id="c8a3a-161">Wenn Sie den PowerShell-Katalog noch nicht als vertrauenswürdig eingestuft haben, sehen Sie die unten stehende Warnung mit der Aufforderung zur Bestätigung und Anleitungen, wie Sie nachfolgende Eingabeaufforderungen bei Installationen vermeiden können.</span><span class="sxs-lookup"><span data-stu-id="c8a3a-161">If you have not trusted the PowerShell gallery, you see the warning below asking for confirmation, and instructing you how to avoid subsequent prompts on installs.</span></span>

```
PS> Install-Module -Name ComputerManagementDSC

Untrusted repository
You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the Set-PSRepository cmdlet. Are you sure you want to
install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="c8a3a-162">Drücken Sie „j“, um mit dem Installieren des Moduls fortzufahren.</span><span class="sxs-lookup"><span data-stu-id="c8a3a-162">Press 'y' to continue installing the module.</span></span> <span data-ttu-id="c8a3a-163">Nach der Installation können Sie mit [Get-DSCResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) überprüfen, ob die neue Ressource installiert ist.</span><span class="sxs-lookup"><span data-stu-id="c8a3a-163">After install, you can verify that your new resource is installed using [Get-DSCResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource).</span></span>

```
PS> Get-DSCResource -Name TimeZone -Syntax

TimeZone [String] #ResourceName
{
    IsSingleInstance = [string]{ Yes }
    TimeZone = [string]
    [DependsOn = [string[]]]
    [PsDscRunAsCredential = [PSCredential]]
}
```

<span data-ttu-id="c8a3a-164">Sie können mit Angabe des `-ModuleName`-Parameters auch andere Ressourcen in Ihrem neu installierten Modul anzeigen.</span><span class="sxs-lookup"><span data-stu-id="c8a3a-164">You can also view other resources in your newly installed module, by specifying the `-ModuleName` parameter.</span></span>

```
PS> Get-DSCResource -Module ComputerManagementDSC

ImplementedAs   Name                      ModuleName                     Version    Properties
-------------   ----                      ----------                     -------    ----------
PowerShell      Computer                  ComputerManagementDsc          6.0.0.0    {Name, Credential, DependsOn, ...
PowerShell      OfflineDomainJoin         ComputerManagementDsc          6.0.0.0    {IsSingleInstance, RequestFile...
PowerShell      PowerPlan                 ComputerManagementDsc          6.0.0.0    {IsSingleInstance, Name, Depen...
PowerShell      PowerShellExecutionPolicy ComputerManagementDsc          6.0.0.0    {ExecutionPolicy, ExecutionPol...
PowerShell      ScheduledTask             ComputerManagementDsc          6.0.0.0    {TaskName, ActionArguments, Ac...
PowerShell      TimeZone                  ComputerManagementDsc          6.0.0.0    {IsSingleInstance, TimeZone, D...
PowerShell      VirtualMemory             ComputerManagementDsc          6.0.0.0    {Drive, Type, DependsOn, Initi...
```

## <a name="see-also"></a><span data-ttu-id="c8a3a-165">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c8a3a-165">See also</span></span>

- [<span data-ttu-id="c8a3a-166">Was sind Ressourcen?</span><span class="sxs-lookup"><span data-stu-id="c8a3a-166">What are Resources?</span></span>](../resources/resources.md)
