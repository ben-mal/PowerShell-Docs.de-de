---
ms.date: 12/12/2018
keywords: DSC,PowerShell,Konfiguration,Setup,Einrichtung
title: Veröffentlichen auf einem Pullserver mithilfe von Konfigurations-IDs (v4/v5)
description: In diesem Artikel wird erläutert, wie Sie Ressourcen hochladen können, damit sie zum Download zur Verfügung stehen. Außerdem erfahren Sie, wie Sie Clients so konfigurieren, dass sie Ressourcen automatisch herunterladen.
ms.openlocfilehash: 20e12e3cac6b6e4a86563576f4a915429b18aadb
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92646837"
---
# <a name="publish-to-a-pull-server-using-configuration-ids-v4v5"></a><span data-ttu-id="302b5-104">Veröffentlichen auf einem Pullserver mithilfe von Konfigurations-IDs (v4/v5)</span><span class="sxs-lookup"><span data-stu-id="302b5-104">Publish to a Pull Server using Configuration IDs (v4/v5)</span></span>

<span data-ttu-id="302b5-105">Die folgenden Abschnitte gehen davon aus, dass Sie bereits einen Pullserver eingerichtet haben.</span><span class="sxs-lookup"><span data-stu-id="302b5-105">The sections below assume that you have already set up a Pull Server.</span></span> <span data-ttu-id="302b5-106">Wenn Sie noch keinen Pullserver eingerichtet haben, können Sie die folgenden Anleitungen verwenden:</span><span class="sxs-lookup"><span data-stu-id="302b5-106">If you haven't set up your Pull Server, you can use the following guides:</span></span>

- [<span data-ttu-id="302b5-107">Einrichten eines DSC-SMB-Pullservers</span><span class="sxs-lookup"><span data-stu-id="302b5-107">Set up a DSC SMB Pull Server</span></span>](pullServerSmb.md)
- [<span data-ttu-id="302b5-108">Einrichten eines DSC-HTTP-Pullservers</span><span class="sxs-lookup"><span data-stu-id="302b5-108">Set up a DSC HTTP Pull Server</span></span>](pullServer.md)

<span data-ttu-id="302b5-109">Jeder Zielknoten kann zum Herunterladen von Konfigurationen, Ressourcen und sogar zum Berichten seines Status konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="302b5-109">Each target node can be configured to download configurations, resources, and even report its status.</span></span> <span data-ttu-id="302b5-110">In diesem Artikel wird erläutert, wie Sie Ressourcen hochladen können, damit sie zum Download zur Verfügung stehen. Außerdem erfahren Sie, wie Sie Clients so konfigurieren, dass sie Ressourcen automatisch herunterladen.</span><span class="sxs-lookup"><span data-stu-id="302b5-110">This article shows you how to upload resources so they're available to be downloaded, and configure clients to automatically download resources.</span></span> <span data-ttu-id="302b5-111">Wenn der Knoten per **Pull** oder **Push** (v5) eine zugewiesene Konfiguration empfängt, lädt er automatisch alle für die Konfiguration erforderlichen Ressourcen aus dem im lokalen Konfigurations-Manager angegebenen Speicherort herunter.</span><span class="sxs-lookup"><span data-stu-id="302b5-111">When the node receives an assigned Configuration, through **Pull** or **Push** (v5), it automatically downloads any resources required by the Configuration from the location specified in the Local Configuration Manager (LCM).</span></span>

## <a name="compile-configurations"></a><span data-ttu-id="302b5-112">Kompilieren von Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="302b5-112">Compile configurations</span></span>

<span data-ttu-id="302b5-113">Der erste Schritt beim Speichern von [Konfigurationen](../configurations/configurations.md) auf einem Pullserver besteht darin, sie in `.mof`-Dateien zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="302b5-113">The first step to storing [Configurations](../configurations/configurations.md) on a Pull Server, is to compile them into `.mof` files.</span></span> <span data-ttu-id="302b5-114">Damit eine Konfiguration generisch und auf mehrere Clients anwendbar wird, verwenden Sie `localhost` in Ihrem Node-Block.</span><span class="sxs-lookup"><span data-stu-id="302b5-114">To make a configuration generic, and applicable to more clients, use `localhost` in your Node block.</span></span> <span data-ttu-id="302b5-115">Das folgende Beispiel zeigt eine Konfigurationsshell, die `localhost` anstelle eines bestimmten Clientnamens verwendet.</span><span class="sxs-lookup"><span data-stu-id="302b5-115">The example below shows a Configuration shell that uses `localhost` instead of a specific client name.</span></span>

```powershell
Configuration GenericConfig
{
    Node localhost
    {

    }
}
GenericConfig
```

<span data-ttu-id="302b5-116">Sobald Sie Ihre generische Konfiguration kompiliert haben, sollten Sie über eine Datei „`localhost.mof`“ verfügen.</span><span class="sxs-lookup"><span data-stu-id="302b5-116">Once you've compiled your generic configuration, you should have a `localhost.mof` file.</span></span>

## <a name="renaming-the-mof-file"></a><span data-ttu-id="302b5-117">Umbenennen der MOF-Datei</span><span class="sxs-lookup"><span data-stu-id="302b5-117">Renaming the MOF file</span></span>

<span data-ttu-id="302b5-118">Sie können `.mof`-Konfigurationsdateien auf einem Pullserver mithilfe von **ConfigurationName** oder **ConfigurationID** speichern.</span><span class="sxs-lookup"><span data-stu-id="302b5-118">You can store Configuration `.mof` files on a Pull Server by **ConfigurationName** or **ConfigurationID** .</span></span> <span data-ttu-id="302b5-119">Je nachdem, wie Sie die Einrichtung Ihrer Pullclients planen, können Sie einen der folgenden Abschnitte auswählen, um Ihre kompilierten `.mof`-Dateien ordnungsgemäß umzubenennen.</span><span class="sxs-lookup"><span data-stu-id="302b5-119">Depending on how you plan to set up your pull clients, you can choose a section below to properly rename your compiled `.mof` files.</span></span>

### <a name="configuration-ids-guid"></a><span data-ttu-id="302b5-120">Konfigurations-IDs (GUIDs)</span><span class="sxs-lookup"><span data-stu-id="302b5-120">Configuration IDs (GUID)</span></span>

<span data-ttu-id="302b5-121">Sie müssen Ihre Datei „`localhost.mof`“ in „`<GUID>.mof`“ umbenennen.</span><span class="sxs-lookup"><span data-stu-id="302b5-121">You'll need to rename your `localhost.mof` file to `<GUID>.mof` file.</span></span> <span data-ttu-id="302b5-122">Sie können eine zufällige **GUID** mithilfe des folgenden Beispiels oder des Cmdlets [New-Guid](/powershell/module/microsoft.powershell.utility/new-guid) erstellen.</span><span class="sxs-lookup"><span data-stu-id="302b5-122">You can create a random **Guid** using the example below, or by using the [New-Guid](/powershell/module/microsoft.powershell.utility/new-guid) cmdlet.</span></span>

```powershell
[System.Guid]::NewGuid()
```

<span data-ttu-id="302b5-123">Beispielausgabe</span><span class="sxs-lookup"><span data-stu-id="302b5-123">Sample Output</span></span>

```Output
Guid
----
64856475-939e-41fb-aba5-4469f4006059
```

<span data-ttu-id="302b5-124">Sie können Ihre `.mof`-Datei dann mit jeder zulässigen Methode umbenennen.</span><span class="sxs-lookup"><span data-stu-id="302b5-124">You can then rename your `.mof` file using any acceptable method.</span></span> <span data-ttu-id="302b5-125">Im folgenden Beispiel wird das Cmdlet [Rename-Item](/powershell/module/microsoft.powershell.management/rename-item) verwendet.</span><span class="sxs-lookup"><span data-stu-id="302b5-125">The example below, uses the [Rename-Item](/powershell/module/microsoft.powershell.management/rename-item) cmdlet.</span></span>

```powershell
Rename-Item -Path .\localhost.mof -NewName '64856475-939e-41fb-aba5-4469f4006059.mof'
```

<span data-ttu-id="302b5-126">Weitere Informationen zur Verwendung von **GUIDs** in Ihrer Umgebung finden Sie unter [Plan for Guids (Planen von GUIDs)](secureServer.md#guids).</span><span class="sxs-lookup"><span data-stu-id="302b5-126">For more information about using **Guids** in your environment, see [Plan for Guids](secureServer.md#guids).</span></span>

### <a name="configuration-names"></a><span data-ttu-id="302b5-127">Konfigurationsnamen</span><span class="sxs-lookup"><span data-stu-id="302b5-127">Configuration names</span></span>

<span data-ttu-id="302b5-128">Sie müssen Ihre Datei „`localhost.mof`“ in „`<Configuration Name>.mof`“ umbenennen.</span><span class="sxs-lookup"><span data-stu-id="302b5-128">You'll need to rename your `localhost.mof` file to `<Configuration Name>.mof` file.</span></span> <span data-ttu-id="302b5-129">Im folgenden Beispiel wird der Konfigurationsname aus dem vorherigen Abschnitt verwendet.</span><span class="sxs-lookup"><span data-stu-id="302b5-129">In the following example, the configuration name from the previous section is used.</span></span> <span data-ttu-id="302b5-130">Sie können Ihre `.mof`-Datei dann mit jeder zulässigen Methode umbenennen.</span><span class="sxs-lookup"><span data-stu-id="302b5-130">You can then rename your `.mof` file using any acceptable method.</span></span> <span data-ttu-id="302b5-131">Im folgenden Beispiel wird das Cmdlet [Rename-Item](/powershell/module/microsoft.powershell.management/rename-item) verwendet.</span><span class="sxs-lookup"><span data-stu-id="302b5-131">The example below, uses the [Rename-Item](/powershell/module/microsoft.powershell.management/rename-item) cmdlet.</span></span>

```powershell
Rename-Item -Path .\localhost.mof -NewName 'GenericConfig.mof'
```

## <a name="create-the-checksum"></a><span data-ttu-id="302b5-132">Erstellen der Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="302b5-132">Create the checkSum</span></span>

<span data-ttu-id="302b5-133">Jede `.mof`-Datei, die auf einem Pullserver oder in einer SMB-Freigabe gespeichert ist, muss über eine zugeordnete `.checksum`-Datei verfügen.</span><span class="sxs-lookup"><span data-stu-id="302b5-133">Each `.mof` file stored on a Pull Server, or SMB share needs to have an associated `.checksum` file.</span></span>
<span data-ttu-id="302b5-134">Diese Datei informiert die Clients, wenn sich die zugeordnete `.mof`-Datei geändert hat und erneut heruntergeladen werden muss.</span><span class="sxs-lookup"><span data-stu-id="302b5-134">This file lets clients know when the associated `.mof` file has changed and should be downloaded again.</span></span>

<span data-ttu-id="302b5-135">Sie können mit dem Cmdlet [New-DSCCheckSum](/powershell/module/psdesiredstateconfiguration/new-dscchecksum) eine **CheckSum** erstellen.</span><span class="sxs-lookup"><span data-stu-id="302b5-135">You can create a **CheckSum** with the [New-DSCCheckSum](/powershell/module/psdesiredstateconfiguration/new-dscchecksum) cmdlet.</span></span> <span data-ttu-id="302b5-136">Sie können auch `New-DSCCheckSum` für ein Verzeichnis mit Dateien mit dem Parameter `-Path` ausführen.</span><span class="sxs-lookup"><span data-stu-id="302b5-136">You can also run `New-DSCCheckSum` against a directory of files using the `-Path` parameter.</span></span>
<span data-ttu-id="302b5-137">Wenn bereits eine Prüfsumme vorhanden ist, können Sie mit dem Parameter `-Force` erzwingen, dass sie neu erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="302b5-137">If a checksum already exists, you can force it to be re-created with the `-Force` parameter.</span></span> <span data-ttu-id="302b5-138">Das folgende Beispiel gibt ein Verzeichnis mit der `.mof`-Datei aus dem vorherigen Abschnitt an und verwendet den `-Force`-Parameter.</span><span class="sxs-lookup"><span data-stu-id="302b5-138">The following example specified a directory containing the `.mof` file from the previous section, and uses the `-Force` parameter.</span></span>

```powershell
New-DscChecksum -Path '.\' -Force
```

<span data-ttu-id="302b5-139">Es wird keine Ausgabe angezeigt, aber es sollte nun eine Datei „`<GUID or Configuration Name>.mof.checksum`“ angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="302b5-139">No output will be shown, but you should now see a `<GUID or Configuration Name>.mof.checksum` file.</span></span>

## <a name="where-to-store-mof-files-and-checksums"></a><span data-ttu-id="302b5-140">Speicherort für MOF-Dateien und Prüfsummen</span><span class="sxs-lookup"><span data-stu-id="302b5-140">Where to store MOF files and checkSums</span></span>

### <a name="on-a-dsc-http-pull-server"></a><span data-ttu-id="302b5-141">Auf einem DSC-HTTP-Pullserver</span><span class="sxs-lookup"><span data-stu-id="302b5-141">On a DSC HTTP Pull Server</span></span>

<span data-ttu-id="302b5-142">Wenn Sie Ihren HTTP-Pullserver einrichten (wie unter [Einrichten eines DSC-HTTP-Pullservers](pullServer.md) beschrieben), geben Sie Verzeichnisse für die Schlüssel **ModulePath** und **ConfigurationPath** an.</span><span class="sxs-lookup"><span data-stu-id="302b5-142">When you set up your HTTP Pull Server, as explained in [Set up a DSC HTTP Pull Server](pullServer.md), you specify directories for the **ModulePath** and **ConfigurationPath** keys.</span></span> <span data-ttu-id="302b5-143">Der Schlüssel **ModulePath** gibt an, wo die `.zip`-Paketdateien für ein Modul gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="302b5-143">The **ModulePath** key indicates where a module's packaged `.zip` files should be stored.</span></span> <span data-ttu-id="302b5-144">**ConfigurationPath** gibt an, wo `.mof`- und `.checksum`-Dateien gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="302b5-144">The **ConfigurationPath** indicates where any `.mof` files and `.checksum` files should be stored.</span></span>

```powershell
    xDscWebService PSDSCPullServer
    {
    ...
        ModulePath              = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Modules"
        ConfigurationPath       = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Configuration"
    ...
    }

```

### <a name="on-an-smb-share"></a><span data-ttu-id="302b5-145">In einer SMB-Freigabe</span><span class="sxs-lookup"><span data-stu-id="302b5-145">On an SMB share</span></span>

<span data-ttu-id="302b5-146">Wenn Sie einen Pullclient für die Verwendung einer SMB-Freigabe einrichten, geben Sie eine **ConfigurationRepositoryShare** an.</span><span class="sxs-lookup"><span data-stu-id="302b5-146">When you set up a Pull Client to use an SMB share, you specify a **ConfigurationRepositoryShare** .</span></span>
<span data-ttu-id="302b5-147">Alle `.mof`- und `.checksum`-Dateien müssen im Verzeichnis **SourcePath** aus dem **ConfigurationRepositoryShare** -Block gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="302b5-147">All `.mof` files and `.checksum` files should be stored in the **SourcePath** directory from the **ConfigurationRepositoryShare** block.</span></span>

```powershell
ConfigurationRepositoryShare SMBPullServer
{
    SourcePath = '\\SMBPullServer\Pull'
}
```

## <a name="next-steps"></a><span data-ttu-id="302b5-148">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="302b5-148">Next steps</span></span>

<span data-ttu-id="302b5-149">Als Nächstes müssen Sie die Pullclients so konfigurieren, dass sie die angegebene Konfiguration per Pull abrufen.</span><span class="sxs-lookup"><span data-stu-id="302b5-149">Next, you'll want to configure Pull Clients to pull the specified configuration.</span></span> <span data-ttu-id="302b5-150">Weitere Informationen finden Sie in einem der folgenden Leitfäden:</span><span class="sxs-lookup"><span data-stu-id="302b5-150">For more information, see one of the following guides:</span></span>

- [<span data-ttu-id="302b5-151">Einrichten eines Pullclients mithilfe von Konfigurations-IDs (v4)</span><span class="sxs-lookup"><span data-stu-id="302b5-151">Set up a Pull Client using Configuration IDs (v4)</span></span>](pullClientConfigId4.md)
- [<span data-ttu-id="302b5-152">Einrichten eines Pullclients mithilfe von Konfigurations-IDs (v5)</span><span class="sxs-lookup"><span data-stu-id="302b5-152">Set up a Pull Client using Configuration IDs (v5)</span></span>](pullClientConfigId.md)
- [<span data-ttu-id="302b5-153">Einrichten eines Pullclients mithilfe von Konfigurationsnamen (v5)</span><span class="sxs-lookup"><span data-stu-id="302b5-153">Set up a Pull Client using Configuration Names (v5)</span></span>](pullClientConfigNames.md)

## <a name="see-also"></a><span data-ttu-id="302b5-154">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="302b5-154">See also</span></span>

- [<span data-ttu-id="302b5-155">Einrichten eines DSC-SMB-Pullservers</span><span class="sxs-lookup"><span data-stu-id="302b5-155">Set up a DSC SMB Pull Server</span></span>](pullServerSmb.md)
- [<span data-ttu-id="302b5-156">Einrichten eines DSC-HTTP-Pullservers</span><span class="sxs-lookup"><span data-stu-id="302b5-156">Set up a DSC HTTP Pull Server</span></span>](pullServer.md)
- [<span data-ttu-id="302b5-157">Verpacken und Hochladen von Ressourcen auf einen Pullserver</span><span class="sxs-lookup"><span data-stu-id="302b5-157">Package and Upload Resources to a Pull Server</span></span>](package-upload-resources.md)
