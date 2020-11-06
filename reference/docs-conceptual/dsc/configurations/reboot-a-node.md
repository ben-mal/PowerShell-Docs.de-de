---
ms.date: 01/17/2019
keywords: DSC,PowerShell,Konfiguration,Setup,Einrichtung
title: Neustart eines Knotens
description: Viele Konfigurationseinstellungen erfordern, dass der Computer neu gestartet wird, damit die Konfigurationsänderung erfolgen kann. In diesem Artikel wird erläutert, wie Neustarts in einer Konfiguration verwaltet werden.
ms.openlocfilehash: d2b0f77c34ebcb006821da1f4f8d7c4b046f7a95
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92645113"
---
# <a name="reboot-a-node"></a><span data-ttu-id="1abe1-105">Neustart eines Knotens</span><span class="sxs-lookup"><span data-stu-id="1abe1-105">Reboot a Node</span></span>

> [!NOTE]
> <span data-ttu-id="1abe1-106">In diesem Thema wird erläutert, wie ein Knoten neu gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="1abe1-106">This topic talks about how to reboot a Node.</span></span> <span data-ttu-id="1abe1-107">Damit der Neustart erfolgreich verläuft, müssen die LCM-Einstellungen **ActionAfterReboot** und **RebootNodeIfNeeded** ordnungsgemäß konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="1abe1-107">In order for the reboot to be successful the **ActionAfterReboot** and **RebootNodeIfNeeded** LCM settings need to be configured properly.</span></span> <span data-ttu-id="1abe1-108">Weitere Informationen zu Einstellungen des lokalen Konfigurations-Managers finden Sie unter [Configure the Local Configuration Manager (Konfigurieren des lokalen Konfigurations-Managers)](../managing-nodes/metaConfig.md) oder [Configure the Local Configuration Manager (v4) (Konfigurieren des lokalen Konfigurations-Managers (Version 4))](../managing-nodes/metaConfig4.md).</span><span class="sxs-lookup"><span data-stu-id="1abe1-108">To read about Local Configuration Manager settings, see [Configure the Local Configuration Manager](../managing-nodes/metaConfig.md), or [Configure the Local Configuration Manager (v4)](../managing-nodes/metaConfig4.md).</span></span>

<span data-ttu-id="1abe1-109">Knoten können mithilfe des `$global:DSCMachineStatus`-Flags innerhalb einer Ressource neu gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="1abe1-109">Nodes can be rebooted from within a resource, by using the `$global:DSCMachineStatus` flag.</span></span> <span data-ttu-id="1abe1-110">Wenn dieses Flag in der Funktion `Set-TargetResource` auf `1` festgelegt wird, wird der LCM direkt nach der **Set** -Methode der aktuellen Ressource zum Neustart des Knotens gezwungen.</span><span class="sxs-lookup"><span data-stu-id="1abe1-110">Setting this flag to `1` in the `Set-TargetResource` function forces the LCM to reboot the Node directly after the **Set** method of the current resource.</span></span> <span data-ttu-id="1abe1-111">Mithilfe dieses Flags erkennt die **PendingReboot** -Ressource im DSC-Ressourcenmodul [ComputerManagementDsc](https://github.com/PowerShell/ComputerManagementDsc), ob ein Neustart außerhalb von DSC aussteht.</span><span class="sxs-lookup"><span data-stu-id="1abe1-111">Using this flag, the **PendingReboot** resource in the [ComputerManagementDsc](https://github.com/PowerShell/ComputerManagementDsc) DSC Resource module detects if a reboot is pending outside of DSC.</span></span>

<span data-ttu-id="1abe1-112">Ihre [Konfigurationen](configurations.md) führen möglicherweise Schritte aus, die für den Neustart des Knotens erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="1abe1-112">Your [configurations](configurations.md) may perform steps that require the Node to reboot.</span></span> <span data-ttu-id="1abe1-113">Dazu kann Folgendes gehören:</span><span class="sxs-lookup"><span data-stu-id="1abe1-113">This could include things such as:</span></span>

- <span data-ttu-id="1abe1-114">Windows-Updates</span><span class="sxs-lookup"><span data-stu-id="1abe1-114">Windows updates</span></span>
- <span data-ttu-id="1abe1-115">Softwareinstallation</span><span class="sxs-lookup"><span data-stu-id="1abe1-115">Software install</span></span>
- <span data-ttu-id="1abe1-116">Umbenennen von Dateien</span><span class="sxs-lookup"><span data-stu-id="1abe1-116">File renames</span></span>
- <span data-ttu-id="1abe1-117">Umbenennen von Computern</span><span class="sxs-lookup"><span data-stu-id="1abe1-117">Computer rename</span></span>

<span data-ttu-id="1abe1-118">Die Ressource **PendingReboot** überprüft bestimmte Computerstandorte, um zu bestimmen, ob ein Neustart aussteht.</span><span class="sxs-lookup"><span data-stu-id="1abe1-118">The **PendingReboot** resource checks specific computer locations to determine if a reboot is pending.</span></span> <span data-ttu-id="1abe1-119">Wenn der Knoten einen Neustart außerhalb der DSC erfordert, legt die Ressource **PendingReboot** das `$global:DSCMachineStatus`-Flag auf `1` fest, wodurch ein Neustart erzwungen und die ausstehende Bedingung aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="1abe1-119">If the Node requires a reboot outside of DSC, the **PendingReboot** resource sets the `$global:DSCMachineStatus` flag to `1` forcing a reboot and resolving the pending condition.</span></span>

> [!NOTE]
> <span data-ttu-id="1abe1-120">Jede DSC-Ressource kann den LCM zum Neustart des Knotens anweisen, indem dieses Flag in der Funktion `Set-TargetResource` festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="1abe1-120">Any DSC resource can instruct the LCM to reboot the node by setting this flag in the `Set-TargetResource` function.</span></span> <span data-ttu-id="1abe1-121">Weitere Informationen finden Sie unter [Writing a custom DSC resource with MOF (Schreiben einer benutzerdefinierten DSC-Ressource mit MOF)](../resources/authoringResourceMOF.md).</span><span class="sxs-lookup"><span data-stu-id="1abe1-121">For more information, see [Writing a custom DSC resource with MOF](../resources/authoringResourceMOF.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="1abe1-122">Syntax</span><span class="sxs-lookup"><span data-stu-id="1abe1-122">Syntax</span></span>

```
PendingReboot [String] #ResourceName
{
    Name = [string]
    [DependsOn = [string[]]]
    [PsDscRunAsCredential = [PSCredential]]
    [SkipCcmClientSDK = [bool]]
    [SkipComponentBasedServicing = [bool]]
    [SkipPendingComputerRename = [bool]]
    [SkipPendingFileRename = [bool]]
    [SkipWindowsUpdate = [bool]]
}
```

## <a name="properties"></a><span data-ttu-id="1abe1-123">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="1abe1-123">Properties</span></span>

| <span data-ttu-id="1abe1-124">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="1abe1-124">Property</span></span> | <span data-ttu-id="1abe1-125">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1abe1-125">Description</span></span> |
| --- | --- |
| <span data-ttu-id="1abe1-126">Name</span><span class="sxs-lookup"><span data-stu-id="1abe1-126">Name</span></span>| <span data-ttu-id="1abe1-127">Erforderlicher Parameter, der innerhalb einer Konfiguration pro Ressourceninstanz eindeutig sein muss.</span><span class="sxs-lookup"><span data-stu-id="1abe1-127">Required parameter that must be unique per instance of the resource within a configuration.</span></span>|
| <span data-ttu-id="1abe1-128">SkipComponentBasedServicing</span><span class="sxs-lookup"><span data-stu-id="1abe1-128">SkipComponentBasedServicing</span></span> | <span data-ttu-id="1abe1-129">Überspringen von Neustarts, die von der komponentenbasierten Wartungskomponente ausgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="1abe1-129">Skip reboots triggered by the Component-Based Servicing component.</span></span> |
| <span data-ttu-id="1abe1-130">SkipWindowsUpdate</span><span class="sxs-lookup"><span data-stu-id="1abe1-130">SkipWindowsUpdate</span></span> | <span data-ttu-id="1abe1-131">Überspringen von Neustarts, die von einem Windows-Update ausgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="1abe1-131">Skip reboots triggered by Windows Update.</span></span>|
| <span data-ttu-id="1abe1-132">SkipPendingFileRename</span><span class="sxs-lookup"><span data-stu-id="1abe1-132">SkipPendingFileRename</span></span> | <span data-ttu-id="1abe1-133">Überspringen von ausstehenden Neustarts aufgrund von Dateiumbenennungen.</span><span class="sxs-lookup"><span data-stu-id="1abe1-133">Skip pending file rename reboots.</span></span> |
| <span data-ttu-id="1abe1-134">SkipCcmClientSDK</span><span class="sxs-lookup"><span data-stu-id="1abe1-134">SkipCcmClientSDK</span></span> | <span data-ttu-id="1abe1-135">Überspringen von Neustarts, die vom ConfigMgr-Client ausgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="1abe1-135">Skip reboots triggered by the ConfigMgr client.</span></span> |
| <span data-ttu-id="1abe1-136">SkipComputerRename</span><span class="sxs-lookup"><span data-stu-id="1abe1-136">SkipComputerRename</span></span> | <span data-ttu-id="1abe1-137">Überspringen von Neustarts, die von Umbenennungen eines Computers ausgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="1abe1-137">Skip reboots triggered by Computer renames.</span></span> |
| <span data-ttu-id="1abe1-138">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="1abe1-138">PSDSCRunAsCredential</span></span> | <span data-ttu-id="1abe1-139">Unterstützt in Version 5.</span><span class="sxs-lookup"><span data-stu-id="1abe1-139">Supported in v5.</span></span> <span data-ttu-id="1abe1-140">Führt die Ressource als angegebener Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="1abe1-140">Executes the resource as the specified user.</span></span> |
| <span data-ttu-id="1abe1-141">DependsOn</span><span class="sxs-lookup"><span data-stu-id="1abe1-141">DependsOn</span></span> | <span data-ttu-id="1abe1-142">Gibt an, dass die Konfiguration einer anderen Ressource ausgeführt werden muss, bevor diese Ressource konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="1abe1-142">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="1abe1-143">Wenn beispielsweise die ID des Skriptblocks mit der Ressourcenkonfiguration, den Sie zuerst ausführen möchten, **ResourceName** und dessen Typ **ResourceType** ist, lautet die Syntax für das Verwenden dieser Eigenschaft `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="1abe1-143">For example, if the ID of the resource configuration script block that you want to run first is **ResourceName** and its type is **ResourceType** , the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> <span data-ttu-id="1abe1-144">Weitere Informationen finden Sie unter [Using DependsOn (Verwenden von „DependsOn“)](resource-depends-on.md).</span><span class="sxs-lookup"><span data-stu-id="1abe1-144">For more information, see [Using DependsOn](resource-depends-on.md)</span></span>|

## <a name="example"></a><span data-ttu-id="1abe1-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1abe1-145">Example</span></span>

<span data-ttu-id="1abe1-146">Das folgende Beispiel installiert Microsoft Exchange mithilfe der [xExchange](https://github.com/PowerShell/xExchange)-Ressource.</span><span class="sxs-lookup"><span data-stu-id="1abe1-146">The following example installs Microsoft Exchange using the [xExchange](https://github.com/PowerShell/xExchange) resource.</span></span> <span data-ttu-id="1abe1-147">Während der kompletten Installation wird die **PendingReboot** -Ressource verwendet, um den Knoten neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="1abe1-147">Throughout the install, the **PendingReboot** resource is used to reboot the Node.</span></span>

> [!NOTE]
> <span data-ttu-id="1abe1-148">Für dieses Beispiel sind die Anmeldeinformationen eines Kontos erforderlich, das berechtigt ist, der Gesamtstruktur einen Exchange-Server hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="1abe1-148">This example requires the credential of an account that has rights to add an Exchange server to the forest.</span></span> <span data-ttu-id="1abe1-149">Weitere Informationen zur Verwendung von Anmeldeinformationen in DSC finden Sie unter [Handling Credentials in DSC (Verwendung von Anmeldeinformationen in DSC)](../configurations/configDataCredentials.md).</span><span class="sxs-lookup"><span data-stu-id="1abe1-149">For more information on using credentials in DSC, see [Handling Credentials in DSC](../configurations/configDataCredentials.md)</span></span>

```powershell
$ConfigurationData = @{
    AllNodes = @(
        @{
            NodeName                    = '*'
            PSDSCAllowPlainTextPassword = $true
        },
        @{
            NodeName = 'DSCPULL-1'
        }
    )
}

Configuration Example
{
    param
    (
        [Parameter(Mandatory = $true)]
        [System.Management.Automation.PSCredential]
        $ExchangeAdminCredential
    )

    Import-DscResource -Module xExchange
    Import-DscResource -Module ComputerManagementDsc

    Node $AllNodes.NodeName
    {
        # Copy the Exchange setup files locally
        File ExchangeBinaries
        {
            Ensure          = 'Present'
            Type            = 'Directory'
            Recurse         = $true
            SourcePath      = '\\rras-1\Binaries\E15CU6'
            DestinationPath = 'C:\Binaries\E15CU6'
        }

        # Check if a reboot is needed before installing Exchange
        PendingReboot BeforeExchangeInstall
        {
            Name       = 'BeforeExchangeInstall'
            DependsOn  = '[File]ExchangeBinaries'
        }

        # Do the Exchange install
        xExchInstall InstallExchange
        {
            Path       = 'C:\Binaries\E15CU6\Setup.exe'
            Arguments  = '/mode:Install /role:Mailbox /Iacceptexchangeserverlicenseterms'
            Credential = $ExchangeAdminCredential
            DependsOn  = '[PendingReboot]BeforeExchangeInstall'
        }

        # See if a reboot is required after installing Exchange
        PendingReboot AfterExchangeInstall
        {
            Name      = 'AfterExchangeInstall'
            DependsOn = '[xExchInstall]InstallExchange'
        }
    }
}
```

> [!NOTE]
> <span data-ttu-id="1abe1-150">In diesem Beispiel wird davon ausgegangen, dass Sie Ihren lokalen Konfigurations-Manager so konfiguriert haben, dass Neustarts erlaubt sind, und die Konfiguration nach einem Neustart fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="1abe1-150">This example assumes that you have configured your Local Configuration Manager to allow reboots and continue the configuration after a reboot.</span></span>

## <a name="where-to-download"></a><span data-ttu-id="1abe1-151">Speicherorte für Downloads</span><span class="sxs-lookup"><span data-stu-id="1abe1-151">Where to Download</span></span>

<span data-ttu-id="1abe1-152">Sie können die in diesem Thema verwendeten Ressourcen an folgenden Speicherorten abspeichern, oder mithilfe des PowerShell-Katalogs.</span><span class="sxs-lookup"><span data-stu-id="1abe1-152">You can download the resources used in this topic at the following locations, or by using the PowerShell gallery.</span></span>

- [<span data-ttu-id="1abe1-153">ComputerManagementDsc</span><span class="sxs-lookup"><span data-stu-id="1abe1-153">ComputerManagementDsc</span></span>](https://github.com/PowerShell/ComputerManagementDsc)
- [<span data-ttu-id="1abe1-154">xExchange</span><span class="sxs-lookup"><span data-stu-id="1abe1-154">xExchange</span></span>](https://github.com/PowerShell/xExchange)
