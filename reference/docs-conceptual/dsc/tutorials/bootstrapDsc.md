---
ms.date: 06/12/2017
keywords: DSC,PowerShell,Konfiguration,Setup,Einrichtung
title: Konfigurieren eines virtuellen Computers beim ersten Hochfahren mithilfe von DSC
description: In diesem Artikel wird beschrieben, wie Sie einen virtuellen Computer beim ersten Hochfahren mithilfe von DSC konfigurieren.
ms.openlocfilehash: 9fa8c4a21486aaef87e1c0a3097e5983a378d98d
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92656204"
---
# <a name="configure-a-virtual-machines-at-initial-boot-up-by-using-dsc"></a><span data-ttu-id="4f639-104">Konfigurieren eines virtuellen Computers beim ersten Hochfahren mithilfe von DSC</span><span class="sxs-lookup"><span data-stu-id="4f639-104">Configure a virtual machines at initial boot-up by using DSC</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4f639-105">Gilt für: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="4f639-105">Applies To: Windows PowerShell 5.0</span></span>

## <a name="requirements"></a><span data-ttu-id="4f639-106">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4f639-106">Requirements</span></span>

> [!NOTE]
> <span data-ttu-id="4f639-107">Der in diesem Thema beschriebene Registrierungsschlüssel **DSCAutomationHostEnabled** ist in PowerShell 4.0 nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4f639-107">The **DSCAutomationHostEnabled** registry key described in this topic is not available in PowerShell 4.0.</span></span> <span data-ttu-id="4f639-108">Informationen dazu, wie Sie neue virtuelle Computer beim ersten Hochfahren in PowerShell 4.0 konfigurieren, finden Sie unter [Sie möchten Ihre Computer mithilfe von DSC beim ersten Hochfahren automatisch konfigurieren?](https://blogs.msdn.microsoft.com/powershell/2014/02/28/want-to-automatically-configure-your-machines-using-dsc-at-initial-boot-up/)</span><span class="sxs-lookup"><span data-stu-id="4f639-108">For information on how to configure new virtual machines at initial boot-up in PowerShell 4.0, see [Want to Automatically Configure Your Machines Using DSC at Initial Boot-up?](https://blogs.msdn.microsoft.com/powershell/2014/02/28/want-to-automatically-configure-your-machines-using-dsc-at-initial-boot-up/)</span></span>

<span data-ttu-id="4f639-109">Um diese Beispiele auszuführen, benötigen Sie:</span><span class="sxs-lookup"><span data-stu-id="4f639-109">To run these examples, you will need:</span></span>

- <span data-ttu-id="4f639-110">Eine startbare virtuelle Festplatte (VHD).</span><span class="sxs-lookup"><span data-stu-id="4f639-110">A bootable VHD to work with.</span></span> <span data-ttu-id="4f639-111">Sie können ein ISO-Image mit einer Evaluierungsversion von Windows Server 2016 aus dem [TechNet-Evaluierungscenter](https://www.microsoft.com/evalcenter/evaluate-windows-server-2016) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="4f639-111">You can download an ISO with an evaluation copy of Windows Server 2016 at [TechNet Evaluation Center](https://www.microsoft.com/evalcenter/evaluate-windows-server-2016).</span></span>
  <span data-ttu-id="4f639-112">Anweisungen finden Sie zum Erstellen einer VHD aus einem ISO-Image finden Sie unter [Erstellen startbarer virtueller Festplatten](/previous-versions/windows/it-pro/windows-7/gg318049(v=ws.10)).</span><span class="sxs-lookup"><span data-stu-id="4f639-112">You can find instructions on how to create a VHD from an ISO image at [Creating Bootable Virtual Hard Disks](/previous-versions/windows/it-pro/windows-7/gg318049(v=ws.10)).</span></span>
- <span data-ttu-id="4f639-113">Ein Hostcomputer, auf dem Hyper-V aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="4f639-113">A host computer that has Hyper-V enabled.</span></span> <span data-ttu-id="4f639-114">Informationen hierzu finden Sie unter [Übersicht über Hyper-V](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831531(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="4f639-114">For information, see [Hyper-V overview](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831531(v=ws.11)).</span></span>

  <span data-ttu-id="4f639-115">Mithilfe von DSC können Sie die Installation und Konfiguration von Software beim ersten Hochfahren eines Computers automatisieren.</span><span class="sxs-lookup"><span data-stu-id="4f639-115">By using DSC, you can automate software installation and configuration for a computer at initial boot-up.</span></span> <span data-ttu-id="4f639-116">Sie können dazu entweder ein MOF-Konfigurationsdokument oder eine Metakonfiguration zu startbaren Medien (z. B. einer VHD) hinzufügen, die beim ersten Startvorgang ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="4f639-116">You do this by either injecting a configuration MOF document or a metaconfiguration into bootable media (such as a VHD) so that they are run during the initial boot-up process.</span></span> <span data-ttu-id="4f639-117">Dieses Verhalten wird vom [DSCAutomationHostEnabled-Registrierungsschlüssel](DSCAutomationHostEnabled.md) unter `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System` angegeben.</span><span class="sxs-lookup"><span data-stu-id="4f639-117">This behavior is specified by the [DSCAutomationHostEnabled registry key](DSCAutomationHostEnabled.md) registry key under `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System`.</span></span>
  <span data-ttu-id="4f639-118">Standardmäßig ist der Wert dieses Schlüssels 2, wodurch DSC zur Startzeit ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="4f639-118">By default, the value of this key is 2, which allows DSC to run at boot time.</span></span>

  <span data-ttu-id="4f639-119">Wenn DSC nicht zur Startzeit ausgeführt werden soll, legen Sie den Wert des Registrierungsschlüssels [DSCAutomationHostEnabled](DSCAutomationHostEnabled.md) auf 0 fest.</span><span class="sxs-lookup"><span data-stu-id="4f639-119">If you do not want DSC to run at boot time, set the value of the [DSCAutomationHostEnabled registry key](DSCAutomationHostEnabled.md) registry key to 0.</span></span>

- <span data-ttu-id="4f639-120">Hinzufügen eines MOF-Konfigurationsdokuments zu einer VHD</span><span class="sxs-lookup"><span data-stu-id="4f639-120">Inject a configuration MOF document into a VHD</span></span>
- <span data-ttu-id="4f639-121">Hinzufügen einer Metakonfiguration zu einer VHD</span><span class="sxs-lookup"><span data-stu-id="4f639-121">Inject a DSC metaconfiguration into a VHD</span></span>
- <span data-ttu-id="4f639-122">Deaktivieren von DSC zur Startzeit</span><span class="sxs-lookup"><span data-stu-id="4f639-122">Disable DSC at boot time</span></span>

> [!NOTE]
> <span data-ttu-id="4f639-123">Sie können zu einem Computer gleichzeitig `Pending.mof` und `MetaConfig.mof` hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="4f639-123">You can inject both `Pending.mof` and `MetaConfig.mof` into a computer at the same time.</span></span>
> <span data-ttu-id="4f639-124">Wenn beide Dateien vorhanden sind, haben die Einstellungen von `MetaConfig.mof` Vorrang.</span><span class="sxs-lookup"><span data-stu-id="4f639-124">If both files are present, the settings specified in `MetaConfig.mof` take precedence.</span></span>

## <a name="inject-a-configuration-mof-document-into-a-vhd"></a><span data-ttu-id="4f639-125">Hinzufügen eines MOF-Konfigurationsdokuments zu einer VHD</span><span class="sxs-lookup"><span data-stu-id="4f639-125">Inject a configuration MOF document into a VHD</span></span>

<span data-ttu-id="4f639-126">Um eine Konfiguration beim ersten Hochfahren anzuwenden, können Sie ein kompiliertes MOF-Konfigurationsdokument als `Pending.mof`-Datei zur VHD hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="4f639-126">To enact a configuration at initial boot-up, you can inject a compiled configuration MOF document into the VHD as its `Pending.mof` file.</span></span> <span data-ttu-id="4f639-127">Ist der Registrierungsschlüssel **DSCAutomationHostEnabled** auf 2 (Standardwert) festgelegt, wird die in `Pending.mof` definierte Konfiguration von DSC angewendet, sobald der Computer zum ersten Mal gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="4f639-127">If the **DSCAutomationHostEnabled** registry key is set to 2 (the default value), DSC will apply the configuration defined by `Pending.mof` when the computer boots up for the first time.</span></span>

<span data-ttu-id="4f639-128">In diesem Beispiel wird die folgende Konfiguration verwendet, durch die IIS auf dem neuen Computer installiert wird:</span><span class="sxs-lookup"><span data-stu-id="4f639-128">For this example, we will use the following configuration, which will install IIS on the new computer:</span></span>

```powershell
Configuration SampleIISInstall
{
    Import-DscResource -ModuleName 'PSDesiredStateConfiguration'

    node ('localhost')
    {
        WindowsFeature IIS
        {
            Ensure = 'Present'
            Name   = 'Web-Server'
        }
    }
}
```

### <a name="to-inject-the-configuration-mof-document-on-the-vhd"></a><span data-ttu-id="4f639-129">So fügen Sie ein MOF-Konfigurationsdokument zur VHD hinzu</span><span class="sxs-lookup"><span data-stu-id="4f639-129">To inject the configuration MOF document on the VHD</span></span>

1. <span data-ttu-id="4f639-130">Stellen Sie die VHD, zu der Sie die Konfiguration hinzufügen möchten, mit dem Cmdlet [Mount-VHD](/powershell/module/hyper-v/mount-vhd) bereit.</span><span class="sxs-lookup"><span data-stu-id="4f639-130">Mount the VHD into which you want to inject the configuration by calling the [Mount-VHD](/powershell/module/hyper-v/mount-vhd) cmdlet.</span></span> <span data-ttu-id="4f639-131">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="4f639-131">For example:</span></span>

   ```powershell
   Mount-VHD -Path C:\users\public\documents\vhd\Srv16.vhd
   ```

1. <span data-ttu-id="4f639-132">Auf einem Computer mit PowerShell 5.0 oder höher speichern Sie die oben stehende Konfiguration ( **SampleIISInstall** ) als PowerShell-Skriptdatei (.ps1).</span><span class="sxs-lookup"><span data-stu-id="4f639-132">On a computer running PowerShell 5.0 or later, save the above configuration ( **SampleIISInstall** ) as a PowerShell script (.ps1) file.</span></span>

1. <span data-ttu-id="4f639-133">Navigieren Sie in einer PowerShell-Konsole zu dem Ordner, in dem Sie die PS1-Datei gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="4f639-133">In a PowerShell console, navigate to the folder where you saved the .ps1 file.</span></span>

1. <span data-ttu-id="4f639-134">Führen Sie die folgenden PowerShell-Befehle zum Kompilieren des MOF-Dokuments aus (Informationen zum Kompilieren von DSC-Konfigurationen finden Sie unter [DSC-Konfigurationen](../configurations/configurations.md):</span><span class="sxs-lookup"><span data-stu-id="4f639-134">Run the following PowerShell commands to compile the MOF document (for information about compiling DSC configurations, see [DSC Configurations](../configurations/configurations.md):</span></span>

   ```powershell
   . .\SampleIISInstall.ps1
   SampleIISInstall
   ```

1. <span data-ttu-id="4f639-135">Dadurch wird eine `localhost.mof`-Datei in einen neuen Ordner namens `SampleIISInstall` erstellt.</span><span class="sxs-lookup"><span data-stu-id="4f639-135">This will create a `localhost.mof` file in a new folder named `SampleIISInstall`.</span></span> <span data-ttu-id="4f639-136">Benennen Sie die Datei in `Pending.mof`um, und verschieben Sie sie an den richtigen Speicherort auf der virtuellen Festplatte. Verwenden Sie dazu das Cmdlet [Move-Item](/powershell/module/microsoft.powershell.management/move-item).</span><span class="sxs-lookup"><span data-stu-id="4f639-136">Rename and move that file into the proper location on the VHD as `Pending.mof` by using the [Move-Item](/powershell/module/microsoft.powershell.management/move-item) cmdlet.</span></span> <span data-ttu-id="4f639-137">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="4f639-137">For example:</span></span>

   ```powershell
   Move-Item -Path C:\DSCTest\SampleIISInstall\localhost.mof -Destination E:\Windows\System32\Configuration\Pending.mof
   ```

1. <span data-ttu-id="4f639-138">Heben Sie die VHD-Bereitstellung durch Aufrufen des Cmdlets [Dismount-VHD](/powershell/module/hyper-v/dismount-vhd) auf.</span><span class="sxs-lookup"><span data-stu-id="4f639-138">Dismount the VHD by calling the [Dismount-VHD](/powershell/module/hyper-v/dismount-vhd) cmdlet.</span></span>
   <span data-ttu-id="4f639-139">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="4f639-139">For example:</span></span>

   ```powershell
   Dismount-VHD -Path C:\users\public\documents\vhd\Srv16.vhd
   ```

1. <span data-ttu-id="4f639-140">Erstellen Sie einen virtuellen Computer mithilfe der VHD, auf der Sie das DSC MOF-Dokument installiert haben.</span><span class="sxs-lookup"><span data-stu-id="4f639-140">Create a VM by using the VHD where you installed the DSC MOF document.</span></span>

<span data-ttu-id="4f639-141">IIS wird nach dem ersten Hochfahren und der Installation des Betriebssystems installiert.</span><span class="sxs-lookup"><span data-stu-id="4f639-141">After initial boot-up and operating system installation, IIS will be installed.</span></span> <span data-ttu-id="4f639-142">Sie können dies überprüfen, indem Sie das Cmdlet [Get-WindowsFeature](/powershell/module/servermanager/get-windowsfeature) aufrufen.</span><span class="sxs-lookup"><span data-stu-id="4f639-142">You can verify this by calling the [Get-WindowsFeature](/powershell/module/servermanager/get-windowsfeature) cmdlet.</span></span>

## <a name="inject-a-dsc-metaconfiguration-into-a-vhd"></a><span data-ttu-id="4f639-143">Hinzufügen einer Metakonfiguration zu einer VHD</span><span class="sxs-lookup"><span data-stu-id="4f639-143">Inject a DSC metaconfiguration into a VHD</span></span>

<span data-ttu-id="4f639-144">Sie können einen Computer auch so konfigurieren, dass eine Konfiguration beim ersten Hochfahren abgerufen wird, indem Sie eine Metakonfiguration als `MetaConfig.mof`-Datei zur VHD hinzufügen (siehe [Configuring the Local Configuration Manager (LCM) (Konfigurieren des lokalen Konfigurations-Managers)](../managing-nodes/metaConfig.md)).</span><span class="sxs-lookup"><span data-stu-id="4f639-144">You can also configure a computer to pull a configuration at initial boot-up by injecting a metaconfiguration (see [Configuring the Local Configuration Manager (LCM)](../managing-nodes/metaConfig.md)) into the VHD as its `MetaConfig.mof` file.</span></span> <span data-ttu-id="4f639-145">Wenn der Registrierungsschlüssel **DSCAutomationHostEnabled** auf 2 (Standardwert) festgelegt ist, wird die in `MetaConfig.mof` definierte Metakonfiguration von DSC auf den LCM angewendet, sobald der Computer zum ersten Mal gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="4f639-145">If the **DSCAutomationHostEnabled** registry key is set to 2 (the default value), DSC will apply the metaconfiguration defined by `MetaConfig.mof` to the LCM when the computer boots up for the first time.</span></span> <span data-ttu-id="4f639-146">Wenn in der Metakonfiguration festgelegt ist, dass Konfigurationen durch den lokalen Konfigurations-Manager von einem Pullserver abgerufen werden sollen, versucht der Computer beim ersten Hochfahren, die Konfiguration von diesem Pullserver abzurufen.</span><span class="sxs-lookup"><span data-stu-id="4f639-146">If the metaconfiguration specifies that the LCM should pull configurations from a pull server, the computer will attempt to pull a configuration from that pull server at initial boot-up.</span></span> <span data-ttu-id="4f639-147">Weitere Informationen zum Einrichten von DSC-Pullservern finden Sie unter [Einrichten eines DSC-Webpullservers](../pull-server/pullServer.md).</span><span class="sxs-lookup"><span data-stu-id="4f639-147">For information about setting up a DSC pull server, see [Setting up a DSC web pull server](../pull-server/pullServer.md).</span></span>

<span data-ttu-id="4f639-148">In diesem Beispiel wird sowohl die im vorherigen Abschnitt beschriebene Konfiguration ( **SampleIISInstall** ) als auch die folgenden Metakonfiguration verwendet:</span><span class="sxs-lookup"><span data-stu-id="4f639-148">For this example, we will use both the configuration described in the previous section ( **SampleIISInstall** ), and the following metaconfiguration:</span></span>

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientBootstrap
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded = $true
        }
        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'
            RegistrationKey = '140a952b-b9d6-406b-b416-e0f759c9c0e4'
            ConfigurationNames = @('SampleIISInstall')
        }
    }
}
```

### <a name="to-inject-the-metaconfiguration-mof-document-on-the-vhd"></a><span data-ttu-id="4f639-149">So fügen Sie ein MOF-Metakonfigurationsdokument zur VHD hinzu</span><span class="sxs-lookup"><span data-stu-id="4f639-149">To inject the metaconfiguration MOF document on the VHD</span></span>

1. <span data-ttu-id="4f639-150">Stellen Sie die VHD, zu der Sie die Metakonfiguration hinzufügen möchten, mit dem Cmdlet [Mount-VHD](/powershell/module/hyper-v/mount-vhd) bereit.</span><span class="sxs-lookup"><span data-stu-id="4f639-150">Mount the VHD into which you want to inject the metaconfiguration by calling the [Mount-VHD](/powershell/module/hyper-v/mount-vhd) cmdlet.</span></span> <span data-ttu-id="4f639-151">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="4f639-151">For example:</span></span>

   ```powershell
   Mount-VHD -Path C:\users\public\documents\vhd\Srv16.vhd
   ```

1. <span data-ttu-id="4f639-152">[Richten Sie einen DSC-Webpullserver ein](../pull-server/pullServer.md), und speichern Sie die **SampleIISInstall** -Konfiguration im entsprechenden Ordner.</span><span class="sxs-lookup"><span data-stu-id="4f639-152">[Set up a DSC web pull server](../pull-server/pullServer.md), and save the **SampleIISInstall** configuration to the appropriate folder.</span></span>

1. <span data-ttu-id="4f639-153">Auf einem Computer mit PowerShell 5.0 oder höher speichern Sie die oben stehende Metakonfiguration ( **PullClientBootstrap** ) als PowerShell-Skriptdatei (.ps1).</span><span class="sxs-lookup"><span data-stu-id="4f639-153">On a computer running PowerShell 5.0 or later, save the above metaconfiguration ( **PullClientBootstrap** ) as a PowerShell script (.ps1) file.</span></span>

1. <span data-ttu-id="4f639-154">Navigieren Sie in einer PowerShell-Konsole zu dem Ordner, in dem Sie die PS1-Datei gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="4f639-154">In a PowerShell console, navigate to the folder where you saved the .ps1 file.</span></span>

1. <span data-ttu-id="4f639-155">Führen Sie die folgenden PowerShell-Befehle zum Kompilieren des MOF-Metakonfigurationsdokuments aus (Informationen zum Kompilieren von DSC-Konfigurationen finden Sie unter [DSC-Konfigurationen](../configurations/configurations.md):</span><span class="sxs-lookup"><span data-stu-id="4f639-155">Run the following PowerShell commands to compile the metaconfiguration MOF document (for information about compiling DSC configurations, see [DSC Configurations](../configurations/configurations.md):</span></span>

   ```powershell
   . .\PullClientBootstrap.ps1
   PullClientBootstrap
   ```

1. <span data-ttu-id="4f639-156">Dadurch wird eine `localhost.meta.mof`-Datei in einen neuen Ordner namens `PullClientBootstrap` erstellt.</span><span class="sxs-lookup"><span data-stu-id="4f639-156">This will create a `localhost.meta.mof` file in a new folder named `PullClientBootstrap`.</span></span> <span data-ttu-id="4f639-157">Benennen Sie die Datei in `MetaConfig.mof`um, und verschieben Sie sie an den richtigen Speicherort auf der virtuellen Festplatte. Verwenden Sie dazu das Cmdlet [Move-Item](/powershell/module/microsoft.powershell.management/move-item).</span><span class="sxs-lookup"><span data-stu-id="4f639-157">Rename and move that file into the proper location on the VHD as `MetaConfig.mof` by using the [Move-Item](/powershell/module/microsoft.powershell.management/move-item) cmdlet.</span></span>

   ```powershell
   Move-Item -Path C:\DSCTest\PullClientBootstrap\localhost.meta.mof -Destination E:\Windows\System32\Configuration\MetaConfig.mof
   ```

1. <span data-ttu-id="4f639-158">Heben Sie die VHD-Bereitstellung durch Aufrufen des Cmdlets [Dismount-VHD](/powershell/module/hyper-v/dismount-vhd) auf.</span><span class="sxs-lookup"><span data-stu-id="4f639-158">Dismount the VHD by calling the [Dismount-VHD](/powershell/module/hyper-v/dismount-vhd) cmdlet.</span></span>
   <span data-ttu-id="4f639-159">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="4f639-159">For example:</span></span>

   ```powershell
   Dismount-VHD -Path C:\users\public\documents\vhd\Srv16.vhd
   ```

1. <span data-ttu-id="4f639-160">Erstellen Sie einen virtuellen Computer mithilfe der VHD, auf der Sie das DSC MOF-Dokument installiert haben.</span><span class="sxs-lookup"><span data-stu-id="4f639-160">Create a VM by using the VHD where you installed the DSC MOF document.</span></span>

<span data-ttu-id="4f639-161">Nach dem ersten Hochfahren und der Installation des Betriebssystems wird die Konfiguration durch DSC vom Pullserver abgerufen, und IIS wird installiert.</span><span class="sxs-lookup"><span data-stu-id="4f639-161">After initial boot-up and operating system installation, DSC will pull the configuration from the pull server, and IIS will be installed.</span></span> <span data-ttu-id="4f639-162">Sie können dies überprüfen, indem Sie das Cmdlet [Get-WindowsFeature](/powershell/module/servermanager/get-windowsfeature) aufrufen.</span><span class="sxs-lookup"><span data-stu-id="4f639-162">You can verify this by calling the [Get-WindowsFeature](/powershell/module/servermanager/get-windowsfeature) cmdlet.</span></span>

## <a name="disable-dsc-at-boot-time"></a><span data-ttu-id="4f639-163">Deaktivieren von DSC zur Startzeit</span><span class="sxs-lookup"><span data-stu-id="4f639-163">Disable DSC at boot time</span></span>

<span data-ttu-id="4f639-164">Standardmäßig wird der Wert des Schlüssels `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System\DSCAutomationHostEnabled`</span><span class="sxs-lookup"><span data-stu-id="4f639-164">By default, the value of the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System\DSCAutomationHostEnabled`</span></span>
<span data-ttu-id="4f639-165">auf 2 festgelegt ist, wodurch eine DSC-Konfiguration ausgeführt werden kann, wenn der Computer den Zustand „A“ oder „Aktuell“ aufweist.</span><span class="sxs-lookup"><span data-stu-id="4f639-165">key is set to 2, which allows a DSC configuration to run if the computer is in pending or current state.</span></span> <span data-ttu-id="4f639-166">Wenn beim ersten Hochfahren keine Konfiguration ausgeführt werden soll, müssen Sie den Wert dieses Schlüssels auf 0 festgelegt:</span><span class="sxs-lookup"><span data-stu-id="4f639-166">If you do not want a configuration to run at initial boot-up, you need so set the value of this key to 0:</span></span>

1. <span data-ttu-id="4f639-167">Stellen Sie die VHD bereit, indem Sie das Cmdlet [Mount-VHD](/powershell/module/hyper-v/mount-vhd) aufrufen.</span><span class="sxs-lookup"><span data-stu-id="4f639-167">Mount the VHD by calling the [Mount-VHD](/powershell/module/hyper-v/mount-vhd) cmdlet.</span></span> <span data-ttu-id="4f639-168">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="4f639-168">For example:</span></span>

   ```powershell
   Mount-VHD -Path C:\users\public\documents\vhd\Srv16.vhd
   ```

1. <span data-ttu-id="4f639-169">Laden Sie den Registrierungsunterschlüssel `HKLM\Software` durch Aufrufen von `reg load` aus der VHD.</span><span class="sxs-lookup"><span data-stu-id="4f639-169">Load the registry `HKLM\Software` subkey from the VHD by calling `reg load`.</span></span>

   ```powershell
   reg load HKLM\Vhd E:\Windows\System32\Config\Software`
   ```

1. <span data-ttu-id="4f639-170">Navigieren Sie mithilfe des PowerShell-Registrierungsanbieters zu `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System`.</span><span class="sxs-lookup"><span data-stu-id="4f639-170">Navigate to the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System` by using the PowerShell Registry provider.</span></span>

   ```powershell
   Set-Location HKLM:\Software\Microsoft\Windows\CurrentVersion\Policies\System`
   ```

1. <span data-ttu-id="4f639-171">Ändern Sie den Wert von `DSCAutomationHostEnabled` in 0.</span><span class="sxs-lookup"><span data-stu-id="4f639-171">Change the value of `DSCAutomationHostEnabled` to 0.</span></span>

   ```powershell
   Set-ItemProperty -Path . -Name DSCAutomationHostEnabled -Value 0
   ```

5. <span data-ttu-id="4f639-172">Entladen Sie die Registrierung, indem Sie die folgenden Befehle ausführen:</span><span class="sxs-lookup"><span data-stu-id="4f639-172">Unload the registry by running the following commands:</span></span>

   ```powershell
   [gc]::Collect()
   reg unload HKLM\Vhd
   ```

## <a name="see-also"></a><span data-ttu-id="4f639-173">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4f639-173">See Also</span></span>

[<span data-ttu-id="4f639-174">DSC-Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="4f639-174">DSC Configurations</span></span>](../configurations/configurations.md)

[<span data-ttu-id="4f639-175">DSCAutomationHostEnabled (Registrierungsschlüssel)</span><span class="sxs-lookup"><span data-stu-id="4f639-175">DSCAutomationHostEnabled registry key</span></span>](DSCAutomationHostEnabled.md)

[<span data-ttu-id="4f639-176">Konfigurieren des lokalen Konfigurations-Managers (LCM)</span><span class="sxs-lookup"><span data-stu-id="4f639-176">Configuring the Local Configuration Manager (LCM)</span></span>](../managing-nodes/metaConfig.md)

[<span data-ttu-id="4f639-177">Einrichten eines DSC-Webpullservers</span><span class="sxs-lookup"><span data-stu-id="4f639-177">Setting up a DSC web pull server</span></span>](../pull-server/pullServer.md)
