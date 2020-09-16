---
ms.date: 08/15/2019
keywords: DSC,PowerShell,Konfiguration,Setup,Einrichtung
title: Erste Schritte mit Desired State Configuration (DSC) für Windows
ms.openlocfilehash: 00e1cf545b19f054b4b1ff468c9f6ad94e5cef55
ms.sourcegitcommit: c4906f4c9fa4ef1a16dcd6dd00ff960d19446d71
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2020
ms.locfileid: "89236321"
---
# <a name="get-started-with-desired-state-configuration-dsc-for-windows"></a><span data-ttu-id="e9a65-103">Erste Schritte mit Desired State Configuration (DSC) für Windows</span><span class="sxs-lookup"><span data-stu-id="e9a65-103">Get started with Desired State Configuration (DSC) for Windows</span></span>

<span data-ttu-id="e9a65-104">In diesem Thema werden die ersten Schritte mit PowerShell Desired State Configuration (DSC) für Windows erläutert.</span><span class="sxs-lookup"><span data-stu-id="e9a65-104">This topic explains how to get started using PowerShell Desired State Configuration (DSC) for Windows.</span></span>
<span data-ttu-id="e9a65-105">Allgemeine Informationen zu DSC finden Sie unter [Erste Schritte mit Windows PowerShell DSC](../overview/overview.md).</span><span class="sxs-lookup"><span data-stu-id="e9a65-105">For general information about DSC, see [Get Started with Windows PowerShell Desired State Configuration](../overview/overview.md).</span></span>

## <a name="supported-windows-operation-system-versions"></a><span data-ttu-id="e9a65-106">Unterstützte Windows-Betriebssystemversionen</span><span class="sxs-lookup"><span data-stu-id="e9a65-106">Supported Windows operation system versions</span></span>

<span data-ttu-id="e9a65-107">Die folgenden Versionen werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="e9a65-107">The following versions are supported:</span></span>

- <span data-ttu-id="e9a65-108">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="e9a65-108">Windows Server 2019</span></span>
- <span data-ttu-id="e9a65-109">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="e9a65-109">Windows Server 2016</span></span>
- <span data-ttu-id="e9a65-110">Windows Server 2012R2</span><span class="sxs-lookup"><span data-stu-id="e9a65-110">Windows Server 2012R2</span></span>
- <span data-ttu-id="e9a65-111">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="e9a65-111">Windows Server 2012</span></span>
- <span data-ttu-id="e9a65-112">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="e9a65-112">Windows Server 2008 R2 SP1</span></span>
- <span data-ttu-id="e9a65-113">Windows 10</span><span class="sxs-lookup"><span data-stu-id="e9a65-113">Windows 10</span></span>
- <span data-ttu-id="e9a65-114">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="e9a65-114">Windows 8.1</span></span>
- <span data-ttu-id="e9a65-115">Windows 7</span><span class="sxs-lookup"><span data-stu-id="e9a65-115">Windows 7</span></span>

<span data-ttu-id="e9a65-116">Die eigenständige Produkt-SKU [Microsoft Hyper-V Server](/windows-server/virtualization/hyper-v/hyper-v-server-2016) umfasst keine Desired State Configuration-Implementierung und kann deshalb nicht mit PowerShell DSC oder Azure Automation State Configuration verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="e9a65-116">The [Microsoft Hyper-V Server](/windows-server/virtualization/hyper-v/hyper-v-server-2016) standalone product sku doesn't contain an implementation of Desired State Configuration so it cannot be managed by PowerShell DSC or Azure Automation State Configuration.</span></span>

## <a name="installing-dsc"></a><span data-ttu-id="e9a65-117">Installieren von DSC</span><span class="sxs-lookup"><span data-stu-id="e9a65-117">Installing DSC</span></span>

<span data-ttu-id="e9a65-118">PowerShell Desired State Configuration ist in Windows enthalten und wird über Windows Management Framework aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="e9a65-118">PowerShell Desired State Configuration is included in Windows and updated through Windows Management Framework.</span></span> <span data-ttu-id="e9a65-119">Die aktuelle Version ist [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616).</span><span class="sxs-lookup"><span data-stu-id="e9a65-119">The latest version is [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616).</span></span>

> [!NOTE]
> <span data-ttu-id="e9a65-120">Es ist nicht erforderlich, das Windows Server-Feature „DSC-Service“ zu aktivieren, um einen Computer mithilfe von DSC zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="e9a65-120">You do not need to enable the Windows Server feature 'DSC-Service' to manage a machine using DSC.</span></span>
> <span data-ttu-id="e9a65-121">Dieses Feature wird nur benötigt, wenn Sie eine Windows Pull Server-Instanz erstellen.</span><span class="sxs-lookup"><span data-stu-id="e9a65-121">That feature is only needed when building a Windows Pull Server instance.</span></span>

## <a name="using-dsc-for-windows"></a><span data-ttu-id="e9a65-122">Verwenden von DSC für Windows</span><span class="sxs-lookup"><span data-stu-id="e9a65-122">Using DSC for Windows</span></span>

<span data-ttu-id="e9a65-123">In den folgenden Abschnitten wird erläutert, wie DSC-Konfigurationen erstellt und auf Windows-Computern ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e9a65-123">The following sections explain how to create and run DSC configurations on Windows computers.</span></span>

### <a name="creating-a-configuration-mof-document"></a><span data-ttu-id="e9a65-124">Erstellen eines MOF-Konfigurationsdokuments</span><span class="sxs-lookup"><span data-stu-id="e9a65-124">Creating a configuration MOF document</span></span>

<span data-ttu-id="e9a65-125">Um eine Konfiguration zu erstellen, wird das Windows PowerShell-Schlüsselwort `Configuration` verwendet.</span><span class="sxs-lookup"><span data-stu-id="e9a65-125">The Windows PowerShell `Configuration` keyword is used to create a configuration.</span></span>
<span data-ttu-id="e9a65-126">Die folgenden Schritte beschreiben die Erstellung eines Konfigurationsdokuments mithilfe von Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e9a65-126">The following steps describe the creation of a configuration document using Windows PowerShell.</span></span>

#### <a name="define-a-configuration-and-generate-the-configuration-document"></a><span data-ttu-id="e9a65-127">Definieren Sie eine Konfiguration, und generieren Sie das Konfigurationsdokument:</span><span class="sxs-lookup"><span data-stu-id="e9a65-127">Define a configuration and generate the configuration document:</span></span>

```powershell
Configuration EnvironmentVariable_Path
{
    param ()

    Import-DscResource -ModuleName 'PSDscResources'

    Node localhost
    {
        Environment CreatePathEnvironmentVariable
        {
            Name = 'TestPathEnvironmentVariable'
            Value = 'TestValue'
            Ensure = 'Present'
            Path = $true
            Target = @('Process', 'Machine')
        }
    }
}

EnvironmentVariable_Path -OutputPath:"C:\EnvironmentVariable_Path"
```

#### <a name="install-a-module-containing-dsc-resources"></a><span data-ttu-id="e9a65-128">Installieren eines Moduls mit DSC-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="e9a65-128">Install a module containing DSC resources</span></span>

<span data-ttu-id="e9a65-129">Windows PowerShell Desired State Configuration umfasst integrierte Module, die DSC-Ressourcen enthalten.</span><span class="sxs-lookup"><span data-stu-id="e9a65-129">Windows PowerShell Desired State Configuration includes built-in modules containing DSC resources.</span></span>
<span data-ttu-id="e9a65-130">Mithilfe der PowerShellGet-Cmdlets ist es außerdem möglich, Module aus externen Quellen wie z. B. dem PowerShell-Katalog zu laden.</span><span class="sxs-lookup"><span data-stu-id="e9a65-130">You can also load modules from external sources such as the PowerShell Gallery, using the PowerShellGet cmdlets.</span></span>

```PowerShell
Install-Module 'PSDscResources' -Verbose
```

#### <a name="apply-the-configuration-to-the-machine"></a><span data-ttu-id="e9a65-131">Anwenden der Konfiguration auf den Computer</span><span class="sxs-lookup"><span data-stu-id="e9a65-131">Apply the configuration to the machine</span></span>

> [!NOTE]
> <span data-ttu-id="e9a65-132">Damit DSC ausgeführt werden kann, muss Windows für den Empfang von PowerShell-Remotebefehlen konfiguriert werden – selbst dann, wenn Sie eine `localhost`-Konfiguration ausführen.</span><span class="sxs-lookup"><span data-stu-id="e9a65-132">To allow DSC to run, Windows needs to be configured to receive PowerShell remote commands even when you're running a `localhost` configuration.</span></span> <span data-ttu-id="e9a65-133">Um Ihre Umgebung auf einfache Weise ordnungsgemäß zu konfigurieren, rufen Sie einfach `Set-WsManQuickConfig -Force` in einem PowerShell-Terminal mit erhöhten Rechten aus.</span><span class="sxs-lookup"><span data-stu-id="e9a65-133">To easily configure your environment correctly, just run `Set-WsManQuickConfig -Force` in an elevated PowerShell Terminal.</span></span>

<span data-ttu-id="e9a65-134">Konfigurationsdokumente (MOF-Dateien) können mit dem Cmdlet [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) auf den Computer angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="e9a65-134">Configuration documents (MOF files) can be applied to the machineusing the [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) cmdlet.</span></span>

```powershell
Start-DscConfiguration -Path 'C:\EnvironmentVariable_Path' -Wait -Verbose
```

#### <a name="get-the-current-state-of-the-configuration"></a><span data-ttu-id="e9a65-135">Abrufen des aktuellen Status der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="e9a65-135">Get the current state of the configuration</span></span>

<span data-ttu-id="e9a65-136">Mit dem Cmdlet [Get-DscConfiguration](/powershell/module/psdesiredstateconfiguration/get-dscconfiguration) wird der aktuelle Status des Computers abgerufen, und es werden die aktuellen Werte für die Konfiguration zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e9a65-136">The [Get-DscConfiguration](/powershell/module/psdesiredstateconfiguration/get-dscconfiguration) cmdlet queries the current status of the machine and returns the current values for the configuration.</span></span>

```powershell
Get-DscConfiguration
```

<span data-ttu-id="e9a65-137">Das Cmdlet [Get-DscLocalConfigurationManager](/powershell/module/psdesiredstateconfiguration/get-dscLocalConfigurationManager) gibt die aktuelle Metakonfiguration zurück, die auf den Computer angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="e9a65-137">The [Get-DscLocalConfigurationManager](/powershell/module/psdesiredstateconfiguration/get-dscLocalConfigurationManager) cmdlet returns the current meta-configuration applied to the machine.</span></span>

```powershell
Get-DscLocalConfigurationManager
```

#### <a name="remove-the-current-configuration-from-a-machine"></a><span data-ttu-id="e9a65-138">Entfernen der aktuellen Konfiguration von einem Computer</span><span class="sxs-lookup"><span data-stu-id="e9a65-138">Remove the current configuration from a machine</span></span>

<span data-ttu-id="e9a65-139">Cmdlet [Remove-DscConfigurationDocument](/powershell/module/psdesiredstateconfiguration/remove-dscconfigurationdocument):</span><span class="sxs-lookup"><span data-stu-id="e9a65-139">The [Remove-DscConfigurationDocument](/powershell/module/psdesiredstateconfiguration/remove-dscconfigurationdocument)</span></span>

```powershell
Remove-DscConfigurationDocument -Stage Current -Verbose
```

#### <a name="configure-settings-in-local-configuration-manager"></a><span data-ttu-id="e9a65-140">Konfigurieren der Einstellungen im lokalen Konfigurations-Manager</span><span class="sxs-lookup"><span data-stu-id="e9a65-140">Configure settings in Local Configuration Manager</span></span>

<span data-ttu-id="e9a65-141">Wenden Sie mit dem Cmdlet [Set-DSCLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Set-DscLocalConfigurationManager) eine MOF-Metakonfigurationsdatei auf den Computer an.</span><span class="sxs-lookup"><span data-stu-id="e9a65-141">Apply a Meta Configuration MOF file to the machine using the [Set-DSCLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Set-DscLocalConfigurationManager) cmdlet.</span></span>
<span data-ttu-id="e9a65-142">Erfordert die Angabe des Pfads zur MOF-Metakonfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="e9a65-142">Requires the path to the Meta Configuration MOF.</span></span>

```powershell
Set-DSCLocalConfigurationManager -Path 'c:\metaconfig\localhost.meta.mof' -Verbose
```

## <a name="windows-powershell-desired-state-configuration-log-files"></a><span data-ttu-id="e9a65-143">Windows PowerShell DSC-Protokolldateien</span><span class="sxs-lookup"><span data-stu-id="e9a65-143">Windows PowerShell Desired State Configuration log files</span></span>

<span data-ttu-id="e9a65-144">Protokolle für Desired State Configuration werden in das Windows-Ereignisprotokoll im Pfad `Microsoft-Windows-Dsc/Operational` geschrieben.</span><span class="sxs-lookup"><span data-stu-id="e9a65-144">Logs for DSC are written to Windows Event Log in the path `Microsoft-Windows-Dsc/Operational`.</span></span>
<span data-ttu-id="e9a65-145">Zusätzliche Protokolle zu Debuggingzwecken können mithilfe der unter [Wo befinden sich die DSC-Ereignisprotokolle?](/powershell/scripting/dsc/troubleshooting/troubleshooting#where-are-dsc-event-logs) genannten Schritte aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="e9a65-145">Additional logs for debugging purposes can be enabled following the steps in [Where Are DSC Event Logs](/powershell/scripting/dsc/troubleshooting/troubleshooting#where-are-dsc-event-logs).</span></span>
