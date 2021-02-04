---
ms.date: 01/07/2021
keywords: DSC,PowerShell,Konfiguration,Setup,Einrichtung
title: Erste Schritte mit DSC für Linux
description: In diesem Thema werden die ersten Schritte mit PowerShell DSC für Linux erläutert.
ms.openlocfilehash: 6f0dea956b16c0828964a10b43abbbc65879ea33
ms.sourcegitcommit: b9826dcf402db8a2b6d3eab37edb82c6af113343
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2021
ms.locfileid: "98040921"
---
# <a name="get-started-with-desired-state-configuration-dsc-for-linux"></a><span data-ttu-id="6a44a-104">Erste Schritte mit DSC für Linux</span><span class="sxs-lookup"><span data-stu-id="6a44a-104">Get started with Desired State Configuration (DSC) for Linux</span></span>

<span data-ttu-id="6a44a-105">In diesem Thema werden die ersten Schritte mit PowerShell DSC für Linux erläutert.</span><span class="sxs-lookup"><span data-stu-id="6a44a-105">This topic explains how to get started using PowerShell Desired State Configuration (DSC) for Linux.</span></span>
<span data-ttu-id="6a44a-106">Allgemeine Informationen zu DSC finden Sie unter [Erste Schritte mit Windows PowerShell DSC](../overview/overview.md).</span><span class="sxs-lookup"><span data-stu-id="6a44a-106">For general information about DSC, see [Get Started with Windows PowerShell Desired State Configuration](../overview/overview.md).</span></span>

## <a name="supported-linux-operation-system-versions"></a><span data-ttu-id="6a44a-107">Unterstützte Linux-Betriebssystemversionen</span><span class="sxs-lookup"><span data-stu-id="6a44a-107">Supported Linux operation system versions</span></span>

<span data-ttu-id="6a44a-108">Die folgenden Linux-Betriebssystemversionen werden von DSC für Linux unterstützt:</span><span class="sxs-lookup"><span data-stu-id="6a44a-108">The following Linux operating system versions are supported by DSC for Linux.</span></span>

- <span data-ttu-id="6a44a-109">CentOS 5, 6 und 7 (x86/x64)</span><span class="sxs-lookup"><span data-stu-id="6a44a-109">CentOS 5, 6, and 7 (x86/x64)</span></span>
- <span data-ttu-id="6a44a-110">Debian GNU/Linux 6, 7 und 8 (x86/x64)</span><span class="sxs-lookup"><span data-stu-id="6a44a-110">Debian GNU/Linux 6, 7 and 8 (x86/x64)</span></span>
- <span data-ttu-id="6a44a-111">Oracle Linux 5, 6 und 7 (x86/x64)</span><span class="sxs-lookup"><span data-stu-id="6a44a-111">Oracle Linux 5, 6 and 7 (x86/x64)</span></span>
- <span data-ttu-id="6a44a-112">Red Hat Enterprise Linux Server 5, 6 und 7 (x86/x64)</span><span class="sxs-lookup"><span data-stu-id="6a44a-112">Red Hat Enterprise Linux Server 5, 6 and 7 (x86/x64)</span></span>
- <span data-ttu-id="6a44a-113">SUSE Linux Enterprise Server 10, 11 und 12 (x86/x64)</span><span class="sxs-lookup"><span data-stu-id="6a44a-113">SUSE Linux Enterprise Server 10, 11 and 12 (x86/x64)</span></span>
- <span data-ttu-id="6a44a-114">Ubuntu Server 12.04 LTS, 14.04 LTS, 16.04 LTS, 18.04 (x86/x64)</span><span class="sxs-lookup"><span data-stu-id="6a44a-114">Ubuntu Server 12.04 LTS, 14.04 LTS, 16.04 LTS, 18.04 (x86/x64)</span></span>

## <a name="installing-dsc-for-linux"></a><span data-ttu-id="6a44a-115">Installieren von DSC für Linux</span><span class="sxs-lookup"><span data-stu-id="6a44a-115">Installing DSC for Linux</span></span>

<span data-ttu-id="6a44a-116">Sie müssen vor der Installation von DSC für Linux die [Open Management Infrastructure (OMI)](https://github.com/Microsoft/omi) installieren.</span><span class="sxs-lookup"><span data-stu-id="6a44a-116">You must install the [Open Management Infrastructure (OMI)](https://github.com/Microsoft/omi) before installing DSC for Linux.</span></span>

### <a name="installing-omi"></a><span data-ttu-id="6a44a-117">Installieren von OMI</span><span class="sxs-lookup"><span data-stu-id="6a44a-117">Installing OMI</span></span>

<span data-ttu-id="6a44a-118">DSC für Linux erfordert den Open Management Infrastructure (OMI) CIM-Server, Version 1.0.8.1 oder höher.</span><span class="sxs-lookup"><span data-stu-id="6a44a-118">Desired State Configuration for Linux requires the Open Management Infrastructure (OMI) CIM server, version 1.0.8.1 or later.</span></span> <span data-ttu-id="6a44a-119">OMI kann unter The Open Group: [Open Management Infrastructure (OMI)](https://github.com/Microsoft/omi) heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="6a44a-119">OMI can be downloaded from The Open Group: [Open Management Infrastructure (OMI)](https://github.com/Microsoft/omi).</span></span>

<span data-ttu-id="6a44a-120">Zum Installieren von OMI installieren Sie das Ihrem Linux-System entsprechende Paket (RPM oder DEB), die OpenSSL-Version (ssl_098 oder ssl_100) und die Architektur (x64/x86).</span><span class="sxs-lookup"><span data-stu-id="6a44a-120">To install OMI, install the package that is appropriate for your Linux system (.rpm or .deb) and OpenSSL version (ssl_098 or ssl_100), and architecture (x64/x86).</span></span> <span data-ttu-id="6a44a-121">RPM-Pakete eignen sich für CentOS, Red Hat Enterprise Linux, SUSE Linux Enterprise Server und Oracle Linux.</span><span class="sxs-lookup"><span data-stu-id="6a44a-121">RPM packages are appropriate for CentOS, Red Hat Enterprise Linux, SUSE Linux Enterprise Server, and Oracle Linux.</span></span> <span data-ttu-id="6a44a-122">DEB-Pakete sind für Debian GNU/Linux und Ubuntu Server geeignet.</span><span class="sxs-lookup"><span data-stu-id="6a44a-122">DEB packages are appropriate for Debian GNU/Linux and Ubuntu Server.</span></span> <span data-ttu-id="6a44a-123">Die ssl_098-Pakete eignen sich für Computer mit installiertem OpenSSL 0.9.8, während die ssl_100 Pakete für Computer mit installiertem OpenSSL 1.0 geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="6a44a-123">The ssl_098 packages are appropriate for computers with OpenSSL 0.9.8 installed while the ssl_100 packages are appropriate for computers with OpenSSL 1.0 installed.</span></span>

> [!NOTE]
> <span data-ttu-id="6a44a-124">Um die installierte OpenSSL-Version zu bestimmen, führen Sie den Befehl `openssl version` aus.</span><span class="sxs-lookup"><span data-stu-id="6a44a-124">To determine the installed OpenSSL version, run the command `openssl version`.</span></span>

<span data-ttu-id="6a44a-125">Führen Sie den folgenden Befehl aus, um OMI auf einem CentOS 7 x64-System zu installieren.</span><span class="sxs-lookup"><span data-stu-id="6a44a-125">Run the following command to install OMI on a CentOS 7 x64 system.</span></span>

`# sudo rpm -Uvh omiserver-1.0.8.ssl_100.rpm`

### <a name="installing-dsc"></a><span data-ttu-id="6a44a-126">Installieren von DSC</span><span class="sxs-lookup"><span data-stu-id="6a44a-126">Installing DSC</span></span>

<span data-ttu-id="6a44a-127">DSC für Linux kann aus dem Repository [PowerShell-DSC-for-Linux](https://github.com/Microsoft/PowerShell-DSC-for-Linux/releases/tag/v1.1.1-926) in das Repository heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="6a44a-127">DSC for Linux is available for download from the [PowerShell-DSC-for-Linux](https://github.com/Microsoft/PowerShell-DSC-for-Linux/releases/tag/v1.1.1-926) repository in the repository.</span></span>

<span data-ttu-id="6a44a-128">Zum Installieren von DSC installieren Sie das Ihrem Linux-System entsprechende Paket (RPM oder DEB), die OpenSSL-Version (ssl_098 oder ssl_100) und die Architektur (x64/x86).</span><span class="sxs-lookup"><span data-stu-id="6a44a-128">To install DSC, install the package that is appropriate for your Linux system (.rpm or .deb) and OpenSSL version (ssl_098 or ssl_100), and architecture (x64/x86).</span></span> <span data-ttu-id="6a44a-129">RPM-Pakete eignen sich für CentOS, Red Hat Enterprise Linux, SUSE Linux Enterprise Server und Oracle Linux.</span><span class="sxs-lookup"><span data-stu-id="6a44a-129">RPM packages are appropriate for CentOS, Red Hat Enterprise Linux, SUSE Linux Enterprise Server, and Oracle Linux.</span></span> <span data-ttu-id="6a44a-130">DEB-Pakete sind für Debian GNU/Linux und Ubuntu Server geeignet.</span><span class="sxs-lookup"><span data-stu-id="6a44a-130">DEB packages are appropriate for Debian GNU/Linux and Ubuntu Server.</span></span> <span data-ttu-id="6a44a-131">Die ssl_098-Pakete eignen sich für Computer mit installiertem OpenSSL 0.9.8, während die ssl_100 Pakete für Computer mit installiertem OpenSSL 1.0 geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="6a44a-131">The ssl_098 packages are appropriate for computers with OpenSSL 0.9.8 installed while the ssl_100 packages are appropriate for computers with OpenSSL 1.0 installed.</span></span>

> [!NOTE]
> <span data-ttu-id="6a44a-132">Um die installierte OpenSSL-Version zu bestimmen, führen Sie den Befehl „openssl version“ aus.</span><span class="sxs-lookup"><span data-stu-id="6a44a-132">To determine the installed OpenSSL version, run the command openssl version.</span></span>

<span data-ttu-id="6a44a-133">Führen Sie den folgenden Befehl aus, um DSC auf einem CentOS 7 x64-System zu installieren.</span><span class="sxs-lookup"><span data-stu-id="6a44a-133">Run the following command to install DSC on a CentOS 7 x64 system.</span></span>

`# sudo rpm -Uvh dsc-1.0.0-254.ssl_100.x64.rpm`

## <a name="using-dsc-for-linux"></a><span data-ttu-id="6a44a-134">Verwenden von DSC für Linux</span><span class="sxs-lookup"><span data-stu-id="6a44a-134">Using DSC for Linux</span></span>

<span data-ttu-id="6a44a-135">In den folgenden Abschnitten wird erläutert, wie DSC-Konfigurationen erstellt und auf Linux-Computern ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="6a44a-135">The following sections explain how to create and run DSC configurations on Linux computers.</span></span>

### <a name="creating-a-configuration-mof-document"></a><span data-ttu-id="6a44a-136">Erstellen eines MOF-Konfigurationsdokuments</span><span class="sxs-lookup"><span data-stu-id="6a44a-136">Creating a configuration MOF document</span></span>

<span data-ttu-id="6a44a-137">Das Windows PowerShell-Schlüsselwort „Configuration“ wird wie für Windows-Computer verwendet, um eine Konfiguration für Linux-Computer zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="6a44a-137">The Windows PowerShell Configuration keyword is used to create a configuration for Linux computers, just like for Windows computers.</span></span> <span data-ttu-id="6a44a-138">Es folgen die Schritte zum Erstellen eines Konfigurationsdokuments für einen Linux-Computer mithilfe von Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6a44a-138">The following steps describe the creation of a configuration document for a Linux computer using Windows PowerShell.</span></span>

1. <span data-ttu-id="6a44a-139">Importieren Sie das Modul „nx“.</span><span class="sxs-lookup"><span data-stu-id="6a44a-139">Import the nx module.</span></span> <span data-ttu-id="6a44a-140">Das Windows PowerShell-Modul „nx“ enthält das Schema für integrierte Ressourcen für DSC für Linux und muss auf dem lokalen Computer installiert und in die Konfiguration importiert werden.</span><span class="sxs-lookup"><span data-stu-id="6a44a-140">The nx Windows PowerShell module contains the schema for Built-In resources for DSC for Linux, and must be installed to your local computer and imported in the configuration.</span></span>

   - <span data-ttu-id="6a44a-141">Zum Installieren des Moduls „nx“ kopieren Sie das Verzeichnis dieses Moduls entweder in `$env:USERPROFILE\Documents\WindowsPowerShell\Modules\` oder in `$PSHOME\Modules`.</span><span class="sxs-lookup"><span data-stu-id="6a44a-141">To install the nx module, copy the nx module directory to either `$env:USERPROFILE\Documents\WindowsPowerShell\Modules\` or `$PSHOME\Modules`.</span></span> <span data-ttu-id="6a44a-142">Das Modul „nx“ ist im Installationspaket von DSC für Linux enthalten.</span><span class="sxs-lookup"><span data-stu-id="6a44a-142">The nx module is included in the DSC for Linux installation package.</span></span> <span data-ttu-id="6a44a-143">Verwenden Sie zum Importieren des Moduls „nx“ in Ihre Konfiguration den Befehl `Import-DSCResource`:</span><span class="sxs-lookup"><span data-stu-id="6a44a-143">To import the nx module in your configuration, use the `Import-DSCResource` command:</span></span>

   ```powershell
   Configuration ExampleConfiguration{

    Import-DSCResource -Module nx

   }
   ```

2. <span data-ttu-id="6a44a-144">Definieren Sie eine Konfiguration, und generieren Sie das Konfigurationsdokument:</span><span class="sxs-lookup"><span data-stu-id="6a44a-144">Define a configuration and generate the configuration document:</span></span>

   ```powershell
   Configuration ExampleConfiguration
   {
        Import-DscResource -Module nx

        Node  "linuxhost.contoso.com"
        {
            nxFile ExampleFile
            {
                DestinationPath = "/tmp/example"
                Contents = "hello world `n"
                Ensure = "Present"
                Type = "File"
            }
        }
   }

   ExampleConfiguration -OutputPath:"C:\temp"
   ```

### <a name="push-the-configuration-to-the-linux-computer"></a><span data-ttu-id="6a44a-145">Übertragen der Konfiguration per Push auf den Linux-Computer</span><span class="sxs-lookup"><span data-stu-id="6a44a-145">Push the configuration to the Linux computer</span></span>

<span data-ttu-id="6a44a-146">Konfigurationsdokumente (MOF-Dateien) können mit dem Cmdlet [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) per Push auf den Linux-Computer übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="6a44a-146">Configuration documents (MOF files) can be pushed to the Linux computer using the [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) cmdlet.</span></span> <span data-ttu-id="6a44a-147">Verwenden Sie eine CIMSession, um dieses Cmdlet zusammen mit den Cmdlets [Get-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration) und [Test-DscConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration) remote auf einem Linux-Computer zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="6a44a-147">In order to use this cmdlet, along with the [Get-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration), or [Test-DscConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration) cmdlets, remotely to a Linux computer, you must use a CIMSession.</span></span> <span data-ttu-id="6a44a-148">Das Cmdlet [New-CimSession](/powershell/module/CimCmdlets/New-CimSession) dient zum Starten einer **CIMSession** mit dem Linux-Computer.</span><span class="sxs-lookup"><span data-stu-id="6a44a-148">The [New-CimSession](/powershell/module/CimCmdlets/New-CimSession) cmdlet is used to create a **CIMSession** to the Linux computer.</span></span>

<span data-ttu-id="6a44a-149">Der folgende Code zeigt, wie Sie eine CIMSession für DSC für Linux starten.</span><span class="sxs-lookup"><span data-stu-id="6a44a-149">The following code shows how to create a CIMSession for DSC for Linux.</span></span>

```powershell
$Node = "ostc-dsc-01"
$Credential = Get-Credential -UserName "root" -Message "Enter Password:"

#Ignore SSL certificate validation
# $opt = New-CimSessionOption -UseSsl -SkipCACheck -SkipCNCheck -SkipRevocationCheck

#Options for a trusted SSL certificate
$opt = New-CimSessionOption -UseSsl

$sessParams = @{
    Credential = $credential
    ComputerName = $Node
    Port = 5986
    Authentication = 'basic'
    SessionOption = $opt
    OperationTimeoutSec = 90
}

$Sess = New-CimSession @sessParams
```

> [!NOTE]
> <span data-ttu-id="6a44a-150">Im Pushmodus müssen die Anmeldeinformationen des Benutzers denen des Root-Benutzers auf dem Linux-Computer entsprechen.</span><span class="sxs-lookup"><span data-stu-id="6a44a-150">For "Push" mode, the user credential must be the root user on the Linux computer.</span></span> <span data-ttu-id="6a44a-151">Für DSC für Linux werden nur SSL/TLS-Verbindungen unterstützt. Der Befehl `New-CimSession` muss mit auf „$true“ festgelegtem „–UseSSL“-Parameter aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="6a44a-151">Only SSL/TLS connections are supported for DSC for Linux, the `New-CimSession` must be used with the –UseSSL parameter set to $true.</span></span> <span data-ttu-id="6a44a-152">Das von OMI (für DSC) verwendete SSL-Zertifikat wird in der Datei `/etc/opt/omi/conf/omiserver.conf` mit den Eigenschaften „pemfile“ und „keyfile“ angegeben.</span><span class="sxs-lookup"><span data-stu-id="6a44a-152">The SSL certificate used by OMI (for DSC) is specified in the file: `/etc/opt/omi/conf/omiserver.conf` with the properties: pemfile and keyfile.</span></span> <span data-ttu-id="6a44a-153">Wenn diesem Zertifikat vom Windows-Computer nicht vertraut wird, auf dem Sie das Cmdlet [New-CimSession](/powershell/module/CimCmdlets/New-CimSession) ausführen, können Sie in den Optionen für „CIMSession“ die Überprüfung des Zertifikats ignorieren: `-SkipCACheck -SkipCNCheck -SkipRevocationCheck`</span><span class="sxs-lookup"><span data-stu-id="6a44a-153">If this certificate is not trusted by the Windows computer that you are running the [New-CimSession](/powershell/module/CimCmdlets/New-CimSession) cmdlet on, you can choose to ignore certificate validation with the CIMSession Options: `-SkipCACheck -SkipCNCheck -SkipRevocationCheck`</span></span>

<span data-ttu-id="6a44a-154">Führen Sie den folgenden Befehl aus, um die DSC-Konfiguration per Push auf den Linux-Knoten zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="6a44a-154">Run the following command to push the DSC configuration to the Linux node.</span></span>

`Start-DscConfiguration -Path:"C:\temp" -CimSession $Sess -Wait -Verbose`

### <a name="distribute-the-configuration-with-a-pull-server"></a><span data-ttu-id="6a44a-155">Verteilen der Konfiguration mit einem Pullserver</span><span class="sxs-lookup"><span data-stu-id="6a44a-155">Distribute the configuration with a pull server</span></span>

<span data-ttu-id="6a44a-156">Konfigurationen können mithilfe eines Pullservers wie bei Windows-Computern auch an Linux-Computer verteilt werden.</span><span class="sxs-lookup"><span data-stu-id="6a44a-156">Configurations can be distributed to a Linux computer with a pull server, just like for Windows computers.</span></span> <span data-ttu-id="6a44a-157">Eine Anleitung zur Verwendung eines Pullservers finden Sie unter [Windows PowerShell DSC – Pullserver](../pull-server/pullServer.md).</span><span class="sxs-lookup"><span data-stu-id="6a44a-157">For guidance on using a pull server, see [Windows PowerShell Desired State Configuration Pull Servers](../pull-server/pullServer.md).</span></span> <span data-ttu-id="6a44a-158">Weitere Informationen und Einschränkungen im Zusammenhang mit der Verwendung von Linux-Computern mit einem Pullserver finden Sie die Versionshinweisen zu DSC für Linux.</span><span class="sxs-lookup"><span data-stu-id="6a44a-158">For additional information and limitations related to using Linux computers with a pull server, see the Release Notes for Desired State Configuration for Linux.</span></span>

### <a name="working-with-configurations-locally"></a><span data-ttu-id="6a44a-159">Arbeiten mit lokalen Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="6a44a-159">Working with configurations locally</span></span>

<span data-ttu-id="6a44a-160">DSC für Linux bietet Skripts für das Ausführen von Konfigurationsaufgaben auf einem lokalen Linux-Computer.</span><span class="sxs-lookup"><span data-stu-id="6a44a-160">DSC for Linux includes scripts to work with configuration from the local Linux computer.</span></span> <span data-ttu-id="6a44a-161">Diese Skripts befinden sich in `/opt/microsoft/dsc/Scripts` und umfassen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="6a44a-161">These scripts are locate in `/opt/microsoft/dsc/Scripts` and include the following:</span></span>

- <span data-ttu-id="6a44a-162">GetDscConfiguration.py</span><span class="sxs-lookup"><span data-stu-id="6a44a-162">GetDscConfiguration.py</span></span>

  <span data-ttu-id="6a44a-163">Gibt die aktuell auf dem Computer installierte Konfiguration zurück.</span><span class="sxs-lookup"><span data-stu-id="6a44a-163">Returns the current configuration applied to the computer.</span></span> <span data-ttu-id="6a44a-164">Dies ist vergleichbar mit dem Windows PowerShell-Cmdlet `Get-DscConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="6a44a-164">Similar to the Windows PowerShell cmdlet `Get-DscConfiguration` cmdlet.</span></span>

  `# sudo ./GetDscConfiguration.py`

- <span data-ttu-id="6a44a-165">GetDscLocalConfigurationManager.py</span><span class="sxs-lookup"><span data-stu-id="6a44a-165">GetDscLocalConfigurationManager.py</span></span>

  <span data-ttu-id="6a44a-166">Gibt die aktuell auf dem Computer installierte Metakonfiguration zurück.</span><span class="sxs-lookup"><span data-stu-id="6a44a-166">Returns the current meta-configuration applied to the computer.</span></span> <span data-ttu-id="6a44a-167">Vergleichbar mit dem Cmdlet [Get-DSCLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Get-DscLocalConfigurationManager).</span><span class="sxs-lookup"><span data-stu-id="6a44a-167">Similar to the cmdlet [Get-DSCLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Get-DscLocalConfigurationManager) cmdlet.</span></span>

  `# sudo ./GetDscLocalConfigurationManager.py`

- <span data-ttu-id="6a44a-168">InstallModule.py</span><span class="sxs-lookup"><span data-stu-id="6a44a-168">InstallModule.py</span></span>

  <span data-ttu-id="6a44a-169">Installiert ein benutzerdefiniertes DSC-Ressourcenmodul.</span><span class="sxs-lookup"><span data-stu-id="6a44a-169">Installs a custom DSC resource module.</span></span> <span data-ttu-id="6a44a-170">Erfordert den Pfad zu einer ZIP-Datei, die die freigegebene Objektbibliothek des Moduls und die MOF-Dateien mit dem Schema enthält.</span><span class="sxs-lookup"><span data-stu-id="6a44a-170">Requires the path to a .zip file containing the module shared object library and schema MOF files.</span></span>

  `# sudo ./InstallModule.py /tmp/cnx_Resource.zip`

- <span data-ttu-id="6a44a-171">RemoveModule.py</span><span class="sxs-lookup"><span data-stu-id="6a44a-171">RemoveModule.py</span></span>

  <span data-ttu-id="6a44a-172">Entfernt ein benutzerdefiniertes DSC-Ressourcenmodul.</span><span class="sxs-lookup"><span data-stu-id="6a44a-172">Removes a custom DSC resource module.</span></span> <span data-ttu-id="6a44a-173">Erfordert die Angabe des Namens des Moduls, das entfernt werden soll.</span><span class="sxs-lookup"><span data-stu-id="6a44a-173">Requires the name of the module to remove.</span></span>

  `# sudo ./RemoveModule.py cnx_Resource`

- <span data-ttu-id="6a44a-174">StartDscLocalConfigurationManager.py</span><span class="sxs-lookup"><span data-stu-id="6a44a-174">StartDscLocalConfigurationManager.py</span></span>

  <span data-ttu-id="6a44a-175">Wendet eine MOF-Konfigurationsdatei auf den Computer an.</span><span class="sxs-lookup"><span data-stu-id="6a44a-175">Applies a configuration MOF file to the computer.</span></span> <span data-ttu-id="6a44a-176">Vergleichbar mit dem Cmdlet [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration).</span><span class="sxs-lookup"><span data-stu-id="6a44a-176">Similar to the [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) cmdlet.</span></span> <span data-ttu-id="6a44a-177">Erfordert die Angabe des Pfads zur anzuwendenden MOF-Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="6a44a-177">Requires the path to the configuration MOF to apply.</span></span>

  `# sudo ./StartDscLocalConfigurationManager.py –configurationmof /tmp/localhost.mof`

- <span data-ttu-id="6a44a-178">SetDscLocalConfigurationManager.py</span><span class="sxs-lookup"><span data-stu-id="6a44a-178">SetDscLocalConfigurationManager.py</span></span>

  <span data-ttu-id="6a44a-179">Wendet eine MOF-Metakonfigurationsdatei auf den Computer an.</span><span class="sxs-lookup"><span data-stu-id="6a44a-179">Applies a Meta Configuration MOF file to the computer.</span></span> <span data-ttu-id="6a44a-180">Vergleichbar mit dem Cmdlet [Set-DSCLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Set-DscLocalConfigurationManager).</span><span class="sxs-lookup"><span data-stu-id="6a44a-180">Similar to the [Set-DSCLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Set-DscLocalConfigurationManager) cmdlet.</span></span> <span data-ttu-id="6a44a-181">Erfordert die Angabe des Pfads zur anzuwendenden MOF-Metakonfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="6a44a-181">Requires the path to the Meta Configuration MOF to apply.</span></span>

  `# sudo ./SetDscLocalConfigurationManager.py –configurationmof /tmp/localhost.meta.mof`

## <a name="powershell-desired-state-configuration-for-linux-log-files"></a><span data-ttu-id="6a44a-182">PowerShell – DSC für Linux – Protokolldateien</span><span class="sxs-lookup"><span data-stu-id="6a44a-182">PowerShell Desired State Configuration for Linux Log Files</span></span>

<span data-ttu-id="6a44a-183">Die folgenden Protokolldateien werden für DSC-für-Linux-Nachrichten generiert.</span><span class="sxs-lookup"><span data-stu-id="6a44a-183">The following log files are generated for DSC for Linux messages.</span></span>

|     <span data-ttu-id="6a44a-184">Protokolldatei</span><span class="sxs-lookup"><span data-stu-id="6a44a-184">Log file</span></span>      |     <span data-ttu-id="6a44a-185">Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="6a44a-185">Directory</span></span>      |                                               <span data-ttu-id="6a44a-186">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6a44a-186">Description</span></span>                                                |
| ----------------- | ------------------ | -------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="6a44a-187">**omiserver.log**</span><span class="sxs-lookup"><span data-stu-id="6a44a-187">**omiserver.log**</span></span> | `/var/opt/omi/log` | <span data-ttu-id="6a44a-188">Meldungen im Zusammenhang mit dem Betrieb des OMI CIM-Servers.</span><span class="sxs-lookup"><span data-stu-id="6a44a-188">Messages relating to the operation of the OMI CIM server.</span></span>                                                |
| <span data-ttu-id="6a44a-189">**dsc.log**</span><span class="sxs-lookup"><span data-stu-id="6a44a-189">**dsc.log**</span></span>       | `/var/opt/omi/log` | <span data-ttu-id="6a44a-190">Meldungen im Zusammenhang mit dem Betrieb des lokalen Konfigurations-Managers (LCM) und DSC-Ressourcenvorgängen.</span><span class="sxs-lookup"><span data-stu-id="6a44a-190">Messages relating to the operation of the Local Configuration Manager (LCM) and DSC resource operations.</span></span> |
