---
ms.date: 06/12/2017
keywords: DSC,PowerShell,Konfiguration,Setup,Einrichtung
title: Verwenden von DSC auf Nano Server
description: DSC ist ein optionales Paket, das installiert werden kann, wenn Sie eine VHD für Windows Nano Server erstellen.
ms.openlocfilehash: 18585323359abd85515d4db194dae4adbad7c3d8
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92647063"
---
# <a name="using-dsc-on-nano-server"></a><span data-ttu-id="13dce-104">Verwenden von DSC auf Nano Server</span><span class="sxs-lookup"><span data-stu-id="13dce-104">Using DSC on Nano Server</span></span>

> <span data-ttu-id="13dce-105">Gilt für: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="13dce-105">Applies To: Windows PowerShell 5.0</span></span>

<span data-ttu-id="13dce-106">**DSC unter Nano Server** ist ein optionales Paket im Ordner `NanoServer\Packages` des Windows Server 2016-Mediums.</span><span class="sxs-lookup"><span data-stu-id="13dce-106">**DSC on Nano Server** is an optional package in the `NanoServer\Packages` folder of the Windows Server 2016 media.</span></span> <span data-ttu-id="13dce-107">Das Paket kann installiert werden, wenn Sie eine VHD (virtuelle Festplatte) für einen Nano Server erstellen, indem Sie **Microsoft-NanoServer-DSC-Package** als Wert des Parameters **Packages** der Funktion **New-NanoServerImage** angeben.</span><span class="sxs-lookup"><span data-stu-id="13dce-107">The package can be installed when you create a VHD for a Nano Server by specifying **Microsoft-NanoServer-DSC-Package** as the value of the **Packages** parameter of the **New-NanoServerImage** function.</span></span> <span data-ttu-id="13dce-108">Wenn Sie beispielsweise eine virtuelle Festplatte für einen virtuellen Computer erstellen, würde der Befehl wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="13dce-108">For example, if you are creating a VHD for a virtual machine, the command would look like the following:</span></span>

```powershell
New-NanoServerImage -Edition Standard -DeploymentType Guest -MediaPath f:\ -BasePath .\Base -TargetPath .\Nano1\Nano.vhd -ComputerName Nano1 -Packages Microsoft-NanoServer-DSC-Package
```

<span data-ttu-id="13dce-109">Informationen zum Installieren und Verwenden von Nano Server sowie zum Verwalten von Nano Server mit PowerShell-Remoting finden Sie unter [Erste Schritte mit Nano Server](/windows-server/get-started/getting-started-with-nano-server).</span><span class="sxs-lookup"><span data-stu-id="13dce-109">For information about installing and using Nano Server, as well as how to manage Nano Server with PowerShell Remoting, see [Getting Started with Nano Server](/windows-server/get-started/getting-started-with-nano-server).</span></span>

## <a name="dsc-features-available-on-nano-server"></a><span data-ttu-id="13dce-110">Unter Nano Server verfügbare DSC-Funktionen</span><span class="sxs-lookup"><span data-stu-id="13dce-110">DSC features available on Nano Server</span></span>

<span data-ttu-id="13dce-111">Da Nano Server im Vergleich mit einer Vollversion von Windows Server nur einen eingeschränkten Satz von APIs unterstützt, besitzt DSC zurzeit unter Nano Server nicht denselben, vollständigen Funktionsumfang wie DSC, das auf vollständigen SKUs ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="13dce-111">Because Nano Server supports only a limited set of APIs compared to a full version of Windows Server, DSC on Nano Server does not have full functional parity with DSC running on full SKUs for the time being.</span></span> <span data-ttu-id="13dce-112">DSC unter Nano Server befindet sich in der aktiven Entwicklung, und der Funktionsumfang ist noch nicht vollständig.</span><span class="sxs-lookup"><span data-stu-id="13dce-112">DSC on Nano Server is in active development and is not yet feature complete.</span></span>

<span data-ttu-id="13dce-113">Die folgenden DSC-Funktionen sind zurzeit unter Nano Server verfügbar:</span><span class="sxs-lookup"><span data-stu-id="13dce-113">The following DSC features are currently available on Nano Server:</span></span>

<span data-ttu-id="13dce-114">Sowohl Push- als auch Pull-Modus</span><span class="sxs-lookup"><span data-stu-id="13dce-114">Both push and pull modes</span></span>

- <span data-ttu-id="13dce-115">Alle DSC-Cmdlets, die eine Vollversion von Windows Server beinhaltet, einschließlich der folgenden:</span><span class="sxs-lookup"><span data-stu-id="13dce-115">All DSC cmdlets that exist on a full version of Windows Server, including the following:</span></span>
- [<span data-ttu-id="13dce-116">Get-DscLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="13dce-116">Get-DscLocalConfigurationManager</span></span>](/powershell/module/PSDesiredStateConfiguration/Get-DscLocalConfigurationManager)
- [<span data-ttu-id="13dce-117">Set-DscLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="13dce-117">Set-DscLocalConfigurationManager</span></span>](/powershell/module/PSDesiredStateConfiguration/Set-DscLocalConfigurationManager)
- [<span data-ttu-id="13dce-118">Enable-DscDebug</span><span class="sxs-lookup"><span data-stu-id="13dce-118">Enable-DscDebug</span></span>](/powershell/module/PSDesiredStateConfiguration/Enable-DscDebug)
- [<span data-ttu-id="13dce-119">Disable-DscDebug</span><span class="sxs-lookup"><span data-stu-id="13dce-119">Disable-DscDebug</span></span>](/powershell/module/PSDesiredStateConfiguration/Disable-DscDebug)
- [<span data-ttu-id="13dce-120">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="13dce-120">Start-DscConfiguration</span></span>](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration)
- [<span data-ttu-id="13dce-121">Stop-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="13dce-121">Stop-DscConfiguration</span></span>](/powershell/module/PSDesiredStateConfiguration/Stop-DscConfiguration)
- [<span data-ttu-id="13dce-122">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="13dce-122">Get-DscConfiguration</span></span>](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration)
- [<span data-ttu-id="13dce-123">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="13dce-123">Test-DscConfiguration</span></span>](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration)
- [<span data-ttu-id="13dce-124">Publish-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="13dce-124">Publish-DscConfiguration</span></span>](/powershell/module/PSDesiredStateConfiguration/Publish-DscConfiguration)
- [<span data-ttu-id="13dce-125">Update-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="13dce-125">Update-DscConfiguration</span></span>](/powershell/module/PSDesiredStateConfiguration/Update-DscConfiguration)
- [<span data-ttu-id="13dce-126">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="13dce-126">Restore-DscConfiguration</span></span>](/powershell/module/PSDesiredStateConfiguration/Restore-DscConfiguration)
- [<span data-ttu-id="13dce-127">Remove-DscConfigurationDocument</span><span class="sxs-lookup"><span data-stu-id="13dce-127">Remove-DscConfigurationDocument</span></span>](/powershell/module/PSDesiredStateConfiguration/Remove-DscConfigurationDocument)
- [<span data-ttu-id="13dce-128">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="13dce-128">Get-DscConfigurationStatus</span></span>](/powershell/module/PSDesiredStateConfiguration/Get-DscConfigurationStatus)
- [<span data-ttu-id="13dce-129">Invoke-DscResource</span><span class="sxs-lookup"><span data-stu-id="13dce-129">Invoke-DscResource</span></span>](/powershell/module/PSDesiredStateConfiguration/Invoke-DscResource)
- [<span data-ttu-id="13dce-130">Find-DscResource</span><span class="sxs-lookup"><span data-stu-id="13dce-130">Find-DscResource</span></span>](/powershell/module/powershellget/find-dscresource)
- [<span data-ttu-id="13dce-131">Get-DscResource</span><span class="sxs-lookup"><span data-stu-id="13dce-131">Get-DscResource</span></span>](/powershell/module/PSDesiredStateConfiguration/Get-DscResource)
- [<span data-ttu-id="13dce-132">New-DscChecksum</span><span class="sxs-lookup"><span data-stu-id="13dce-132">New-DscChecksum</span></span>](/powershell/module/PSDesiredStateConfiguration/New-DSCCheckSum)

- <span data-ttu-id="13dce-133">Kompilieren von Konfigurationen (siehe [DSC-Konfigurationen](../configurations/configurations.md))</span><span class="sxs-lookup"><span data-stu-id="13dce-133">Compiling configurations (see [DSC configurations](../configurations/configurations.md))</span></span>

  <span data-ttu-id="13dce-134">**Problem:** Die Kennwortverschlüsselung (siehe [Schützen der MOF-Datei](../pull-server/secureMOF.md)) während der Konfigurationskompilierung funktioniert nicht.</span><span class="sxs-lookup"><span data-stu-id="13dce-134">**Issue:** Password encryption (see [Securing the MOF File](../pull-server/secureMOF.md)) during configuration compilation doesn't work.</span></span>

- <span data-ttu-id="13dce-135">Kompilieren von Metakonfigurationen (siehe [Konfigurieren des lokalen Konfigurations-Managers](../managing-nodes/metaConfig.md)</span><span class="sxs-lookup"><span data-stu-id="13dce-135">Compiling metaconfigurations (see [Configuring the Local Configuration Manager](../managing-nodes/metaConfig.md))</span></span>

- <span data-ttu-id="13dce-136">Ausführen einer Ressource unter dem Benutzerkontext (siehe [Ausführen von DSC mit Benutzeranmeldeinformationen („Ausführen als“, RunAs)](../configurations/runAsUser.md))</span><span class="sxs-lookup"><span data-stu-id="13dce-136">Running a resource under user context (see [Running DSC with user credentials (RunAs)](../configurations/runAsUser.md))</span></span>

- <span data-ttu-id="13dce-137">Klassenbasierte Ressourcen (siehe [Schreiben einer benutzerdefinierten DSC-Ressource mit PowerShell-Klassen](/previous-versions//dn948461(v=technet.10)))</span><span class="sxs-lookup"><span data-stu-id="13dce-137">Class-based resources (see [Writing a custom DSC resource with PowerShell classes](/previous-versions//dn948461(v=technet.10)))</span></span>

- <span data-ttu-id="13dce-138">Debuggen von DSC-Ressourcen (siehe [Debuggen von DSC-Ressourcen](../troubleshooting/debugResource.md))</span><span class="sxs-lookup"><span data-stu-id="13dce-138">Debugging of DSC resources (see [Debugging DSC resources](../troubleshooting/debugResource.md))</span></span>

  <span data-ttu-id="13dce-139">**Problem:** Funktioniert nicht, wenn eine Ressource PsDscRunAsCredential verwendet (siehe [Ausführen von DSC mit Benutzeranmeldeinformationen](../configurations/runAsUser.md))</span><span class="sxs-lookup"><span data-stu-id="13dce-139">**Issue:** Doesn't work if a resource is using PsDscRunAsCredential (see [Running DSC with user credentials](../configurations/runAsUser.md))</span></span>

- [<span data-ttu-id="13dce-140">Angeben knotenübergreifender Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="13dce-140">Specifying cross-node dependencies</span></span>](../configurations/crossNodeDependencies.md)

- [<span data-ttu-id="13dce-141">Ressourcenversionsverwaltung</span><span class="sxs-lookup"><span data-stu-id="13dce-141">Resource versioning</span></span>](../configurations/sxsResource.md)

- <span data-ttu-id="13dce-142">Pullclient (Konfigurationen und Ressourcen) (siehe [Einrichten eines Pullclients mithilfe von Konfigurationsnamen](../pull-server/pullClientConfigNames.md))</span><span class="sxs-lookup"><span data-stu-id="13dce-142">Pull client (configurations & resources) (see [Setting up a pull client using configuration names](../pull-server/pullClientConfigNames.md))</span></span>

- [<span data-ttu-id="13dce-143">Teilkonfigurationen (Pull und Push)</span><span class="sxs-lookup"><span data-stu-id="13dce-143">Partial configurations (pull & push)</span></span>](../pull-server/partialConfigs.md)

- [<span data-ttu-id="13dce-144">Berichterstattung an Pullserver</span><span class="sxs-lookup"><span data-stu-id="13dce-144">Reporting to pull server</span></span>](../pull-server/reportServer.md)

- <span data-ttu-id="13dce-145">MOF-Verschlüsselung</span><span class="sxs-lookup"><span data-stu-id="13dce-145">MOF encryption</span></span>

- <span data-ttu-id="13dce-146">Ereignisprotokollierung</span><span class="sxs-lookup"><span data-stu-id="13dce-146">Event logging</span></span>

- <span data-ttu-id="13dce-147">Azure Automation-DSC-Berichte</span><span class="sxs-lookup"><span data-stu-id="13dce-147">Azure Automation DSC reporting</span></span>

- <span data-ttu-id="13dce-148">Ressourcen, die voll funktionsfähig sind</span><span class="sxs-lookup"><span data-stu-id="13dce-148">Resources that are fully functional</span></span>

  - <span data-ttu-id="13dce-149">**Archivieren**</span><span class="sxs-lookup"><span data-stu-id="13dce-149">**Archive**</span></span>
  - <span data-ttu-id="13dce-150">**Umgebung**</span><span class="sxs-lookup"><span data-stu-id="13dce-150">**Environment**</span></span>
  - <span data-ttu-id="13dce-151">**File**</span><span class="sxs-lookup"><span data-stu-id="13dce-151">**File**</span></span>
  - <span data-ttu-id="13dce-152">**Log**</span><span class="sxs-lookup"><span data-stu-id="13dce-152">**Log**</span></span>
  - <span data-ttu-id="13dce-153">**ProcessSet**</span><span class="sxs-lookup"><span data-stu-id="13dce-153">**ProcessSet**</span></span>
  - <span data-ttu-id="13dce-154">**Registrierung**</span><span class="sxs-lookup"><span data-stu-id="13dce-154">**Registry**</span></span>
  - <span data-ttu-id="13dce-155">**Skript**</span><span class="sxs-lookup"><span data-stu-id="13dce-155">**Script**</span></span>
  - <span data-ttu-id="13dce-156">**WindowsPackageCab**</span><span class="sxs-lookup"><span data-stu-id="13dce-156">**WindowsPackageCab**</span></span>
  - <span data-ttu-id="13dce-157">**WindowsProcess**</span><span class="sxs-lookup"><span data-stu-id="13dce-157">**WindowsProcess**</span></span>
  - <span data-ttu-id="13dce-158">**WaitForAll** (siehe [Angeben knotenübergreifender Abhängigkeiten](../configurations/crossNodeDependencies.md))</span><span class="sxs-lookup"><span data-stu-id="13dce-158">**WaitForAll** (see [Specifying cross-node dependencies](../configurations/crossNodeDependencies.md))</span></span>
  - <span data-ttu-id="13dce-159">**WaitForAny** (siehe [Angeben knotenübergreifender Abhängigkeiten](../configurations/crossNodeDependencies.md))</span><span class="sxs-lookup"><span data-stu-id="13dce-159">**WaitForAny** (see [Specifying cross-node dependencies](../configurations/crossNodeDependencies.md))</span></span>
  - <span data-ttu-id="13dce-160">**WaitForSome** (siehe [Angeben knotenübergreifender Abhängigkeiten](../configurations/crossNodeDependencies.md))</span><span class="sxs-lookup"><span data-stu-id="13dce-160">**WaitForSome** (see [Specifying cross-node dependencies](../configurations/crossNodeDependencies.md))</span></span>

- <span data-ttu-id="13dce-161">Ressourcen, die teilweise funktionsfähig sind</span><span class="sxs-lookup"><span data-stu-id="13dce-161">Resources that are partially functional</span></span>

  - <span data-ttu-id="13dce-162">**Gruppieren**</span><span class="sxs-lookup"><span data-stu-id="13dce-162">**Group**</span></span>
  - <span data-ttu-id="13dce-163">**GroupSet**</span><span class="sxs-lookup"><span data-stu-id="13dce-163">**GroupSet**</span></span>

    <span data-ttu-id="13dce-164">**Problem:** Bei den oben genannten Ressourcen tritt ein Fehler auf, wenn eine bestimmte Instanz zweimal aufgerufen wird (bzw. wenn die gleiche Konfiguration zweimal ausgeführt wird)</span><span class="sxs-lookup"><span data-stu-id="13dce-164">**Issue:** Above resources fail if specific instance is called twice (running the same configuration twice)</span></span>

  - <span data-ttu-id="13dce-165">**Service**</span><span class="sxs-lookup"><span data-stu-id="13dce-165">**Service**</span></span>
  - <span data-ttu-id="13dce-166">**ServiceSet**</span><span class="sxs-lookup"><span data-stu-id="13dce-166">**ServiceSet**</span></span>

    <span data-ttu-id="13dce-167">**Problem:** Funktioniert nur beim Starten/Beenden (Status) des Diensts.</span><span class="sxs-lookup"><span data-stu-id="13dce-167">**Issue:** Only works for starting/stopping (status) service.</span></span> <span data-ttu-id="13dce-168">Schlägt fehl, wenn versucht wird, andere Attribute des Diensts zu ändern, z. B. Starttyp, Anmeldeinformationen, Beschreibung usw.</span><span class="sxs-lookup"><span data-stu-id="13dce-168">Fails, if one tries to change other service attributes like startuptype, credentials, description etc..</span></span> <span data-ttu-id="13dce-169">Ein Fehler mit etwa folgendem Wortlaut wird ausgelöst:</span><span class="sxs-lookup"><span data-stu-id="13dce-169">The error thrown is similar to:</span></span>

    ```
    Cannot find type [management.managementobject]: verify that the assembly containing this type is loaded.
    ```

- <span data-ttu-id="13dce-170">Ressourcen, die nicht funktionsfähig sind</span><span class="sxs-lookup"><span data-stu-id="13dce-170">Resources that are not functional</span></span>

  - <span data-ttu-id="13dce-171">**Benutzer**</span><span class="sxs-lookup"><span data-stu-id="13dce-171">**User**</span></span>

## <a name="dsc-features-not-available-on-nano-server"></a><span data-ttu-id="13dce-172">Unter Nano Server nicht verfügbare DSC-Funktionen</span><span class="sxs-lookup"><span data-stu-id="13dce-172">DSC features not available on Nano Server</span></span>

<span data-ttu-id="13dce-173">Die folgenden DSC-Funktionen sind zurzeit unter Nano Server nicht verfügbar:</span><span class="sxs-lookup"><span data-stu-id="13dce-173">The following DSC features are not currently available on Nano Server:</span></span>

- <span data-ttu-id="13dce-174">Entschlüsseln von MOF-Dokumenten mit verschlüsselten Kennwörtern</span><span class="sxs-lookup"><span data-stu-id="13dce-174">Decrypting MOF document with encrypted password(s)</span></span>
- <span data-ttu-id="13dce-175">Pullserver: Sie können zurzeit keinen Pullserver unter Nano Server einrichten.</span><span class="sxs-lookup"><span data-stu-id="13dce-175">Pull Server--you cannot currently set up a pull server on Nano Server</span></span>
- <span data-ttu-id="13dce-176">Alle Funktionen, die nicht in der Liste der Funktionen aufgeführt sind, funktionieren.</span><span class="sxs-lookup"><span data-stu-id="13dce-176">Anything that is not in the list of feature works</span></span>

## <a name="using-custom-dsc-resources-on-nano-server"></a><span data-ttu-id="13dce-177">Verwenden benutzerdefinierter DSC-Ressourcen unter Nano Server</span><span class="sxs-lookup"><span data-stu-id="13dce-177">Using custom DSC resources on Nano Server</span></span>

<span data-ttu-id="13dce-178">Aufgrund eingeschränkter Sätze von Windows-APIs und CLR-Bibliotheken, die unter Nano Server verfügbar sind, funktionieren DSC-Ressourcen, die in der vollständigen CLR-Version von Windows funktionieren, nicht notwendigerweise auch unter Nano Server.</span><span class="sxs-lookup"><span data-stu-id="13dce-178">Due to a limited sets of Windows APIs and CLR libraries available on Nano Server, DSC resources that work on the full CLR version of Windows do not necessarily work on Nano Server.</span></span>
<span data-ttu-id="13dce-179">Führen Sie zuerst End-to-End-Tests durch, bevor Sie benutzerdefinierte DSC-Ressourcen in einer Produktionsumgebung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="13dce-179">Complete end-to-end testing before deploying any DSC custom resources to a production environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="13dce-180">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="13dce-180">See Also</span></span>

- [<span data-ttu-id="13dce-181">Erste Schritte mit Nano Server</span><span class="sxs-lookup"><span data-stu-id="13dce-181">Getting Started with Nano Server</span></span>](/windows-server/get-started/getting-started-with-nano-server)
