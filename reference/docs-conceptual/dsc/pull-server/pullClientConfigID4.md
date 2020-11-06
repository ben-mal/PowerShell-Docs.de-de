---
ms.date: 12/12/2018
keywords: DSC,PowerShell,Konfiguration,Setup,Einrichtung
title: Einrichten eines Pullclients mit Konfigurations-IDs in PowerShell 4.0
description: In diesem Artikel wird das Einrichten eines Pullclients mithilfe von Konfigurations-IDs in PowerShell 4.0 erläutert.
ms.openlocfilehash: 2a3d7b79f29030620cddc2b2131cb4432e41e4eb
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92649007"
---
# <a name="set-up-a-pull-client-using-configuration-ids-in-powershell-40"></a><span data-ttu-id="75c30-104">Einrichten eines Pullclients mit Konfigurations-IDs in PowerShell 4.0</span><span class="sxs-lookup"><span data-stu-id="75c30-104">Set up a Pull Client using Configuration IDs in PowerShell 4.0</span></span>

><span data-ttu-id="75c30-105">Gilt für: Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="75c30-105">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

> [!IMPORTANT]
> <span data-ttu-id="75c30-106">Der Pull-Server (Windows-Feature *DSC-Dienst* ) ist eine von Windows Server unterstützte Komponente, jedoch sollen keine neuen Features oder Funktionen angeboten werden.</span><span class="sxs-lookup"><span data-stu-id="75c30-106">The Pull Server (Windows Feature *DSC-Service* ) is a supported component of Windows Server however there are no plans to offer new features or capabilities.</span></span> <span data-ttu-id="75c30-107">Es wird empfohlen, verwaltete Clients auf [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) umzustellen (enthält Features zusätzlich zum Pull-Server unter Windows Server) oder auf eine der [hier](pullserver.md#community-solutions-for-pull-service) aufgeführten Communitylösungen.</span><span class="sxs-lookup"><span data-stu-id="75c30-107">It is recommended to begin transitioning managed clients to [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) (includes features beyond Pull Server on Windows Server) or one of the community solutions listed [here](pullserver.md#community-solutions-for-pull-service).</span></span>

<span data-ttu-id="75c30-108">Bevor Sie einen Pullclient einrichten, sollten Sie einen Pullserver einrichten.</span><span class="sxs-lookup"><span data-stu-id="75c30-108">Before setting up a pull client, you should set up a pull server.</span></span> <span data-ttu-id="75c30-109">Diese Reihenfolge ist zwar nicht erforderlich, jedoch hilft sie bei der Problembehandlung und unterstützt Sie dabei, sicherzustellen, dass die Registrierung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="75c30-109">Though this order is not required, it helps with troubleshooting, and helps you ensure that the registration was successful.</span></span> <span data-ttu-id="75c30-110">Sie können eine der folgenden Führungslinien zum Einrichten eines Pullservers verwenden:</span><span class="sxs-lookup"><span data-stu-id="75c30-110">To set up a pull server, you can use the following guides:</span></span>

- [<span data-ttu-id="75c30-111">Einrichten eines DSC-SMB-Pullservers</span><span class="sxs-lookup"><span data-stu-id="75c30-111">Set up a DSC SMB Pull Server</span></span>](pullServerSmb.md)
- [<span data-ttu-id="75c30-112">Einrichten eines DSC-HTTP-Pullservers</span><span class="sxs-lookup"><span data-stu-id="75c30-112">Set up a DSC HTTP Pull Server</span></span>](pullServer.md)

<span data-ttu-id="75c30-113">Jeder Zielknoten kann zum Herunterladen von Konfigurationen, Ressourcen und sogar zum Berichten seines Status konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="75c30-113">Each target node can be configured to download configurations, resources, and even report its status.</span></span> <span data-ttu-id="75c30-114">In den folgenden Abschnitten wird veranschaulicht, wie Sie einen Pullclient mit einer SMB-Freigabe oder einem HTTP-DSC-Pullserver konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="75c30-114">The sections below show you how to configure a pull client with an SMB share or HTTP DSC Pull Server.</span></span> <span data-ttu-id="75c30-115">Wenn der lokale Konfigurations-Manager des Knotens aktualisiert wird, wendet dieser sich an den konfigurierten Speicherort, um zugewiesene Konfigurationen herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="75c30-115">When the Node's LCM refreshes, it will reach out to the configured location to download any assigned configurations.</span></span> <span data-ttu-id="75c30-116">Wenn erforderliche Ressourcen nicht auf dem Knoten vorhanden sind, werden diese automatisch vom konfigurierten Speicherort heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="75c30-116">If any required resources do not exist on the Node, it will automatically download them from the configured location.</span></span> <span data-ttu-id="75c30-117">Wenn der Knoten mit einem [Berichtsserver](reportServer.md) konfiguriert wurde, wird anschließend der Status des Vorgangs gemeldet.</span><span class="sxs-lookup"><span data-stu-id="75c30-117">If the Node is configured with a [Report Server](reportServer.md), it will then report the status of the operation.</span></span>

## <a name="configure-the-pull-client-lcm"></a><span data-ttu-id="75c30-118">Konfigurieren des lokalen Konfigurations-Managers für den Pullclient</span><span class="sxs-lookup"><span data-stu-id="75c30-118">Configure the pull client LCM</span></span>

<span data-ttu-id="75c30-119">Durch Ausführen der folgenden Beispiele wird ein neuer Ausgabeordner namens **PullClientConfigID** erstellt, und in diesem wird eine MOF-Datei mit der Metakonfiguration platziert.</span><span class="sxs-lookup"><span data-stu-id="75c30-119">Executing any of the examples below creates a new output folder named **PullClientConfigID** and puts a metaconfiguration MOF file there.</span></span> <span data-ttu-id="75c30-120">In diesem Fall heißt die MOF-Datei mit der Metakonfiguration `localhost.meta.mof`.</span><span class="sxs-lookup"><span data-stu-id="75c30-120">In this case, the metaconfiguration MOF file will be named `localhost.meta.mof`.</span></span>

<span data-ttu-id="75c30-121">Rufen Sie zum Anwenden der Konfiguration das Cmdlet **Set-DscLocalConfigurationManager** auf, wobei **Path** auf den Speicherort der MOF-Datei mit der Metakonfiguration festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="75c30-121">To apply the configuration, call the **Set-DscLocalConfigurationManager** cmdlet, with the **Path** set to the location of the metaconfiguration MOF file.</span></span> <span data-ttu-id="75c30-122">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="75c30-122">For example:</span></span>

```powershell
Set-DSCLocalConfigurationManager –ComputerName localhost –Path .\PullClientConfigId –Verbose.
```

## <a name="configuration-id"></a><span data-ttu-id="75c30-123">Konfigurations-ID</span><span class="sxs-lookup"><span data-stu-id="75c30-123">Configuration ID</span></span>

<span data-ttu-id="75c30-124">In den folgenden Beispielen wird die Eigenschaft **ConfigurationID** des lokalen Konfigurations-Managers auf eine **GUID** festgelegt, die zuvor zu diesem Zweck erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="75c30-124">The examples below set the **ConfigurationID** property of the LCM to a **Guid** that had been previously created for this purpose.</span></span> <span data-ttu-id="75c30-125">Der LCM nutzt die **ConfigurationID** zum Auffinden der entsprechenden Konfiguration auf dem Pullserver.</span><span class="sxs-lookup"><span data-stu-id="75c30-125">The **ConfigurationID** is what the LCM uses to find the appropriate configuration on the pull server.</span></span> <span data-ttu-id="75c30-126">Die MOF-Konfigurationsdatei auf dem Pullserver muss den Namen `ConfigurationID.mof` haben, wobei *ConfigurationID* der Wert der Eigenschaft **ConfigurationID** des LCM des Zielknotens ist.</span><span class="sxs-lookup"><span data-stu-id="75c30-126">The configuration MOF file on the pull server must be named `ConfigurationID.mof`, where *ConfigurationID* is the value of the **ConfigurationID** property of the target node's LCM.</span></span> <span data-ttu-id="75c30-127">Weitere Informationen finden Sie unter [Publish Configurations to a Pull Server (v4/v5) (Veröffentlichen von Konfigurationen für einen Pullserver (PowerShell 4.0 und 5.0))](publishConfigs.md).</span><span class="sxs-lookup"><span data-stu-id="75c30-127">For more information, see [Publish Configurations to a Pull Server (v4/v5)](publishConfigs.md).</span></span>

<span data-ttu-id="75c30-128">Sie können eine zufällige **GUID** mithilfe des folgenden Beispiels erstellen.</span><span class="sxs-lookup"><span data-stu-id="75c30-128">You can create a random **Guid** using the example below.</span></span>

```powershell
[System.Guid]::NewGuid()
```

## <a name="set-up-a-pull-client-to-download-configurations"></a><span data-ttu-id="75c30-129">Einrichten eines Pullclients zum Herunterladen von Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="75c30-129">Set up a Pull Client to download Configurations</span></span>

<span data-ttu-id="75c30-130">Jeder Client muss im Modus **Pull** konfiguriert werden und mit der Pullserver-URL zum Speicherort der Konfiguration versehen werden.</span><span class="sxs-lookup"><span data-stu-id="75c30-130">Each client must be configured in **Pull** mode and given the pull server url where its configuration is stored.</span></span> <span data-ttu-id="75c30-131">Hierzu müssen Sie den lokalen Konfigurations-Manager (LCM) mit den benötigten Informationen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="75c30-131">To do this, you have to configure the Local Configuration Manager (LCM) with the necessary information.</span></span> <span data-ttu-id="75c30-132">Zum Konfigurieren des LCM erstellten Sie eine besondere Art von Konfiguration mit einem **DSCLocalConfigurationManager** -Block.</span><span class="sxs-lookup"><span data-stu-id="75c30-132">To configure the LCM, you create a special type of configuration, with a **LocalConfigurationManager** block.</span></span> <span data-ttu-id="75c30-133">Weitere Informationen zum Konfigurieren des LCM finden Sie unter [Konfigurieren des lokalen Konfigurations-Managers](../managing-nodes/metaConfig4.md).</span><span class="sxs-lookup"><span data-stu-id="75c30-133">For more information about configuring the LCM, see [Configuring the Local Configuration Manager](../managing-nodes/metaConfig4.md).</span></span>

## <a name="http-dsc-pull-server"></a><span data-ttu-id="75c30-134">HTTP-DSC-Pullserver</span><span class="sxs-lookup"><span data-stu-id="75c30-134">HTTP DSC Pull Server</span></span>

<span data-ttu-id="75c30-135">Wenn der Pullserver als Webdienst eingerichtet ist, legen Sie **DownloadManagerName** auf **WebDownloadManager** fest.</span><span class="sxs-lookup"><span data-stu-id="75c30-135">If the pull server is set up as a web service, you set the **DownloadManagerName** to **WebDownloadManager**.</span></span> <span data-ttu-id="75c30-136">**WebDownloadManager** erfordert, dass Sie eine **ServerUrl** für den Schlüssel **DownloadManagerCustomData** angeben.</span><span class="sxs-lookup"><span data-stu-id="75c30-136">The **WebDownloadManager** requires that you specify a **ServerUrl** to the **DownloadManagerCustomData** key.</span></span> <span data-ttu-id="75c30-137">Sie können auch einen Wert für **AllowUnsecureConnection** angeben, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="75c30-137">You can also specify a value for **AllowUnsecureConnection** , as in the example below.</span></span> <span data-ttu-id="75c30-138">Das folgende Skript konfiguriert den LCM zum Abrufen von Konfigurationen von einem Pullserver namens „PullServer“.</span><span class="sxs-lookup"><span data-stu-id="75c30-138">The following script configures the LCM to pull configurations from a server named "PullServer".</span></span>

```powershell
Configuration PullClientConfigId
{
    LocalConfigurationManager
    {
        ConfigurationID = "1C707B86-EF8E-4C29-B7C1-34DA2190AE24";
        RefreshMode = "PULL";
        DownloadManagerName = "WebDownloadManager";
        RebootNodeIfNeeded = $true;
        RefreshFrequencyMins = 30;
        ConfigurationModeFrequencyMins = 30;
        ConfigurationMode = "ApplyAndAutoCorrect";
        DownloadManagerCustomData = @{ServerUrl = "http://PullServer:8080/PSDSCPullServer/PSDSCPullServer.svc"; AllowUnsecureConnection = "TRUE"}
    }
}
PullClientConfigId -Output "."
```

## <a name="smb-share"></a><span data-ttu-id="75c30-139">SMB-Freigabe</span><span class="sxs-lookup"><span data-stu-id="75c30-139">SMB Share</span></span>

<span data-ttu-id="75c30-140">Wenn der Pullserver nicht als Webdienst, sondern als SMB-Dateifreigabe konfiguriert wurde, legen Sie **DownloadManagerName** auf **DscFileDownloadManager** anstelle von **WebDownLoadManager** fest.</span><span class="sxs-lookup"><span data-stu-id="75c30-140">If the pull server is set up as an SMB file share, rather than a web service, you set the **DownloadManagerName** to **DscFileDownloadManager** rather than the **WebDownLoadManager**.</span></span> <span data-ttu-id="75c30-141">**DscFileDownloadManager** erfordert, dass Sie eine **SourcePath** -Eigenschaft in **DownloadManagerCustomData** angeben.</span><span class="sxs-lookup"><span data-stu-id="75c30-141">The **DscFileDownloadManager** requires that you specify a **SourcePath** property in the **DownloadManagerCustomData**.</span></span> <span data-ttu-id="75c30-142">Das folgende Skript konfiguriert den LCM zum Abrufen von Konfigurationen von einer SMB-Freigabe namens „SmbDscShare“ auf einem Server namens „CONTOSO-SERVER“.</span><span class="sxs-lookup"><span data-stu-id="75c30-142">The following script configures the LCM to pull configurations from an SMB share named "SmbDscShare" on a server named "CONTOSO-SERVER".</span></span>

```powershell
Configuration PullClientConfigId
{
    LocalConfigurationManager
    {
        ConfigurationID = "1C707B86-EF8E-4C29-B7C1-34DA2190AE24";
        RefreshMode = "PULL";
        DownloadManagerName = "DscFileDownloadManager";
        RebootNodeIfNeeded = $true;
        RefreshFrequencyMins = 30;
        ConfigurationModeFrequencyMins = 30;
        ConfigurationMode = "ApplyAndAutoCorrect";
        DownloadManagerCustomData = @{ServerUrl = "\\CONTOSO-SERVER\SmbDscShare"}
    }
}
PullClientConfigId -Output "."
```

## <a name="next-steps"></a><span data-ttu-id="75c30-143">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="75c30-143">Next Steps</span></span>

<span data-ttu-id="75c30-144">Sobald der Pullclient konfiguriert wurde, können Sie die folgenden Leitfäden zum Durchführen der nächsten Schritte verwenden:</span><span class="sxs-lookup"><span data-stu-id="75c30-144">Once the pull client has been configured, you can use the following guides to perform the next steps:</span></span>

- [<span data-ttu-id="75c30-145">Veröffentlichen von Konfigurationen auf einem Pullserver (v4/v5)</span><span class="sxs-lookup"><span data-stu-id="75c30-145">Publish Configurations to a Pull Server (v4/v5)</span></span>](publishConfigs.md)
- [<span data-ttu-id="75c30-146">Verpacken und Hochladen von Ressourcen auf einen Pullserver (v4)</span><span class="sxs-lookup"><span data-stu-id="75c30-146">Package and Upload Resources to a Pull Server (v4)</span></span>](package-upload-resources.md)

## <a name="see-also"></a><span data-ttu-id="75c30-147">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="75c30-147">See Also</span></span>

- [<span data-ttu-id="75c30-148">Einrichten eines DSC-Webpullservers</span><span class="sxs-lookup"><span data-stu-id="75c30-148">Set up a DSC web pull server</span></span>](pullServer.md)
- [<span data-ttu-id="75c30-149">Einrichten eines DSC-SMB-Pullservers</span><span class="sxs-lookup"><span data-stu-id="75c30-149">Set up a DSC SMB pull server</span></span>](pullServerSMB.md)
