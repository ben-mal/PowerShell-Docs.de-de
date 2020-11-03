---
description: WSMan
keywords: powershell,cmdlet
Locale: en-US
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/about/about_wsman_provider?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: WS-Management-Anbieter
ms.openlocfilehash: 962684fceaa8fdf16985df56fb4fcdb830bb828b
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "93224860"
---
# <a name="wsman-provider"></a><span data-ttu-id="49700-104">WS-Management-Anbieter</span><span class="sxs-lookup"><span data-stu-id="49700-104">WSMan Provider</span></span>

## <a name="provider-name"></a><span data-ttu-id="49700-105">Anbietername</span><span class="sxs-lookup"><span data-stu-id="49700-105">Provider name</span></span>

<span data-ttu-id="49700-106">WSMan</span><span class="sxs-lookup"><span data-stu-id="49700-106">WSMan</span></span>

## <a name="drives"></a><span data-ttu-id="49700-107">Laufwerke</span><span class="sxs-lookup"><span data-stu-id="49700-107">Drives</span></span>

`WSMan:`

## <a name="short-description"></a><span data-ttu-id="49700-108">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="49700-108">Short description</span></span>

<span data-ttu-id="49700-109">Bietet Zugriff auf Web Services for Management (WS-Management)-Konfigurationsinformationen.</span><span class="sxs-lookup"><span data-stu-id="49700-109">Provides access to Web Services for Management (WS-Management) configuration information.</span></span>

## <a name="detailed-description"></a><span data-ttu-id="49700-110">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="49700-110">Detailed description</span></span>

<span data-ttu-id="49700-111">Mit dem **WSMAN** -Anbieter für PowerShell können Sie WS-Management Konfigurationsdaten auf lokalen Computern oder Remote Computern hinzufügen, ändern, löschen und löschen.</span><span class="sxs-lookup"><span data-stu-id="49700-111">The **WSMan** provider for PowerShell lets you add, change, clear, and delete WS-Management configuration data on local or remote computers.</span></span>

<span data-ttu-id="49700-112">Der **WSMAN** -Anbieter macht ein PowerShell-Laufwerk mit einer Verzeichnisstruktur verfügbar, die einer logischen Gruppierung von WS-Management Konfigurationseinstellungen entspricht.</span><span class="sxs-lookup"><span data-stu-id="49700-112">The **WSMan** provider exposes a PowerShell drive with a directory structure that corresponds to a logical grouping of WS-Management configuration settings.</span></span> <span data-ttu-id="49700-113">Diese Gruppierungen werden als Container bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="49700-113">These groupings are known as containers.</span></span>

<span data-ttu-id="49700-114">Ab Windows PowerShell 3,0 wurde der **WSMAN** -Anbieter aktualisiert, um neue Eigenschaften für Sitzungs Konfigurationen zu unterstützen, z. b. **outputbufferingmode**.</span><span class="sxs-lookup"><span data-stu-id="49700-114">Beginning in Windows PowerShell 3.0, the **WSMan** provider has been updated to support new properties for session configurations, such as **OutputBufferingMode**.</span></span> <span data-ttu-id="49700-115">Die Sitzungs Konfigurationen werden als Elemente im Plug-in-Verzeichnis des `WSMan:` Laufwerks angezeigt, und die Eigenschaften werden als Elemente in jeder Sitzungs Konfiguration angezeigt.</span><span class="sxs-lookup"><span data-stu-id="49700-115">The session configurations appear as items in the Plugin directory of the `WSMan:` drive and the properties appear as items in each session configuration.</span></span>

<span data-ttu-id="49700-116">Der **WSMAN** -Anbieter unterstützt die folgenden Cmdlets, die in diesem Artikel behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="49700-116">The **WSMan** provider supports the following cmdlets, which are covered in this article.</span></span>

- [<span data-ttu-id="49700-117">Get-Location</span><span class="sxs-lookup"><span data-stu-id="49700-117">Get-Location</span></span>](xref:Microsoft.PowerShell.Management.Get-Location)
- [<span data-ttu-id="49700-118">Set-Location</span><span class="sxs-lookup"><span data-stu-id="49700-118">Set-Location</span></span>](xref:Microsoft.PowerShell.Management.Set-Location)
- [<span data-ttu-id="49700-119">Get-Item</span><span class="sxs-lookup"><span data-stu-id="49700-119">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)
- [<span data-ttu-id="49700-120">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="49700-120">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)
- [<span data-ttu-id="49700-121">New-Item</span><span class="sxs-lookup"><span data-stu-id="49700-121">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)
- [<span data-ttu-id="49700-122">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="49700-122">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)

> [!NOTE]
> <span data-ttu-id="49700-123">Sie können Befehle im Laufwerk verwenden `WSMan:` , um die Werte der neuen Eigenschaften zu ändern.</span><span class="sxs-lookup"><span data-stu-id="49700-123">You can use commands in the `WSMan:` drive to change the values of the new properties.</span></span> <span data-ttu-id="49700-124">Allerdings können Sie das `WSMan:` Laufwerk in PowerShell 2,0 nicht verwenden, um die in Windows PowerShell 3,0 eingeführten Eigenschaften zu ändern.</span><span class="sxs-lookup"><span data-stu-id="49700-124">However, you cannot use the `WSMan:` drive in PowerShell 2.0 to change properties that are introduced in Windows PowerShell 3.0.</span></span>
> <span data-ttu-id="49700-125">Obwohl kein Fehler generiert wird, sind die Befehle nicht wirksam, um diese Einstellungen zu ändern. verwenden Sie das **WSMAN** -Laufwerk in Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="49700-125">Although no error is generated, the commands are not effective To change these settings, use the **WSMan** drive in Windows PowerShell 3.0.</span></span>

### <a name="organization-of-the-wsman-drive"></a><span data-ttu-id="49700-126">Organisation des WSMAN:-Laufwerks</span><span class="sxs-lookup"><span data-stu-id="49700-126">Organization of the WSMan: Drive</span></span>

- <span data-ttu-id="49700-127">**Client** : Sie können verschiedene Aspekte des WS-Management Clients konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="49700-127">**Client** : You can configure various aspects of the WS-Management client.</span></span> <span data-ttu-id="49700-128">Die Konfigurationsinformationen werden in der Registrierung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="49700-128">The configuration information is stored in the registry.</span></span>

- <span data-ttu-id="49700-129">**Dienst** : Sie können verschiedene Aspekte des WS-Management Dienstanbieter konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="49700-129">**Service** : You can configure various aspects of the WS-Management service.</span></span>
  <span data-ttu-id="49700-130">Die Konfigurationsinformationen werden in der Registrierung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="49700-130">The configuration information is stored in the registry.</span></span>
  > [!NOTE]
  > <span data-ttu-id="49700-131">Die Dienstkonfiguration wird manchmal als Serverkonfiguration bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="49700-131">Service configuration is sometimes referred to as Server configuration.</span></span>

- <span data-ttu-id="49700-132">**Shell** : Sie können verschiedene Aspekte der WS-Management Shell konfigurieren, z. b. die Einstellung zum Zulassen von remoteshellzugriff ( **allowremoteshellaccess** ) und die maximal zulässige Anzahl von gleichzeitigen Benutzern ( **maxconcurrentusers** ).</span><span class="sxs-lookup"><span data-stu-id="49700-132">**Shell** : You can configure various aspects of the WS-Management shell, such as the setting to allow remote shell access ( **AllowRemoteShellAccess** ) and the maximum number of concurrent users allowed ( **MaxConcurrentUsers** ).</span></span>

- <span data-ttu-id="49700-133">**Listener** : Sie können einen Listener erstellen und konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="49700-133">**Listener** : You can create and configure a listener.</span></span> <span data-ttu-id="49700-134">Ein Listener ist ein Verwaltungsdienst, der das WS-Verwaltungsprotokoll zum Senden und Empfangen von Nachrichten implementiert.</span><span class="sxs-lookup"><span data-stu-id="49700-134">A listener is a management service that implements the WS-Management protocol to send and to receive messages.</span></span>

- <span data-ttu-id="49700-135">**Plug-in: Plug** -ins werden geladen und vom WS-Management-Dienst verwendet, um verschiedene Funktionen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="49700-135">**Plugin** : Plug-ins are loaded and used by the WS-Management service to provide various functions.</span></span> <span data-ttu-id="49700-136">PowerShell bietet standardmäßig drei Plug-ins:</span><span class="sxs-lookup"><span data-stu-id="49700-136">By default, PowerShell provides three plug-ins:</span></span>
  - <span data-ttu-id="49700-137">Das Ereignis Weiterleitungs-Plug-in.</span><span class="sxs-lookup"><span data-stu-id="49700-137">The Event Forwarding plug-in.</span></span>
  - <span data-ttu-id="49700-138">Das Microsoft. PowerShell-Plug-in.</span><span class="sxs-lookup"><span data-stu-id="49700-138">The Microsoft.PowerShell plug-in.</span></span>
  - <span data-ttu-id="49700-139">Das Plug-in für den Windows-Verwaltungsinstrumentation (WMI)-Anbieter.</span><span class="sxs-lookup"><span data-stu-id="49700-139">The Windows Management Instrumentation (WMI) Provider plug-in.</span></span>
  <span data-ttu-id="49700-140">Diese drei Plug-Ins unterstützen Ereignis Weiterleitung, Konfiguration und WMI-Zugriff.</span><span class="sxs-lookup"><span data-stu-id="49700-140">These three plug-ins support event forwarding, configuration, and WMI access.</span></span>

- <span data-ttu-id="49700-141">**ClientCertificate** : Sie können ein Client Zertifikat erstellen und konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="49700-141">**ClientCertificate** : You can create and configure a client certificate.</span></span>
  <span data-ttu-id="49700-142">Ein Clientzertifikat wird verwendet, wenn der WS-Verwaltungsclient zur Verwendung der Zertifikatsauthentifizierung konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="49700-142">A client certificate is used when the WS-Management client is configured to use certificate authentication.</span></span>

### <a name="directory-hierarchy-of-the-wsman-provider"></a><span data-ttu-id="49700-143">Verzeichnishierarchie des WSMan-Anbieters</span><span class="sxs-lookup"><span data-stu-id="49700-143">Directory Hierarchy of the WSMan Provider</span></span>

<span data-ttu-id="49700-144">Die Verzeichnishierarchie des WSMAN-Anbieters für den lokalen Computer lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="49700-144">The directory hierarchy of the WSMan provider for the local computer is as follows.</span></span>

```
WSMan:\localhost
--- Client
--- Service
--- Shell
--- Listener
------ <Specific_Listener>
--- Plugin
------ Event Forwarding Plugin
--------- InitializationParameters
--------- Resources
------------ Security
------ Microsoft.Powershell
--------- InitializationParameters
--------- Resources
------------ Security
------ WMI Provider
--------- InitializationParameters
--------- Resources
------------ Security
--- ClientCertificate
```

<span data-ttu-id="49700-145">Die Verzeichnishierarchie des WSMan-Anbieters für einen Remotecomputer ist identisch mit der für einen lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="49700-145">The directory hierarchy of the WSMan provider for a remote computer is the same as a local computer.</span></span> <span data-ttu-id="49700-146">Wenn Sie jedoch auf die Konfigurationseinstellungen eines Remote Computers zugreifen möchten, müssen Sie mithilfe von [Connect-WSMAN](xref:Microsoft.WSMan.Management.Connect-WSMan)eine Verbindung mit dem Remote Computer herstellen.</span><span class="sxs-lookup"><span data-stu-id="49700-146">However, in order to access the configuration settings of a remote computer, you need to make a connection to the remote computer using [Connect-WSMan](xref:Microsoft.WSMan.Management.Connect-WSMan).</span></span> <span data-ttu-id="49700-147">Sobald eine Verbindung mit einem Remotecomputer hergestellt wurde, wird der Name des Remotecomputers beim Anbieter angezeigt.</span><span class="sxs-lookup"><span data-stu-id="49700-147">Once a connection is made to a remote computer, the name of the remote computer shows up in the provider.</span></span>

```
WSMan:\<Remote_Computer_Name>
```

## <a name="navigating-the-wsman-drive"></a><span data-ttu-id="49700-148">Navigieren im WSMAN:-Laufwerk</span><span class="sxs-lookup"><span data-stu-id="49700-148">Navigating the WSMan: Drive</span></span>

<span data-ttu-id="49700-149">Dieser Befehl verwendet das `Set-Location` Cmdlet, um den aktuellen Speicherort auf das Laufwerk zu ändern `WSMan:` .</span><span class="sxs-lookup"><span data-stu-id="49700-149">This command uses the `Set-Location` cmdlet to change the current location to the `WSMan:` drive.</span></span>

```powershell
Set-Location WSMan:
```

<span data-ttu-id="49700-150">Um zu einem Dateisystemlaufwerk zurückzukehren, geben Sie den Namen des Laufwerks ein.</span><span class="sxs-lookup"><span data-stu-id="49700-150">To return to a file system drive, type the drive name.</span></span> <span data-ttu-id="49700-151">Geben Sie z. b. ein.</span><span class="sxs-lookup"><span data-stu-id="49700-151">For example, type.</span></span>

```powershell
Set-Location C:
```

### <a name="navigating-to-a-remote-system-store-location"></a><span data-ttu-id="49700-152">Navigieren zu einem Remote System-Speicherort</span><span class="sxs-lookup"><span data-stu-id="49700-152">Navigating to a remote system store location</span></span>

<span data-ttu-id="49700-153">Dieser Befehl verwendet den- `Set-Location` Befehl, um den aktuellen Speicherort in den Stammverzeichnis des Remote Systemspeicher-Speicher Orts zu ändern.</span><span class="sxs-lookup"><span data-stu-id="49700-153">This command uses the `Set-Location` command to change the current location to the root location in the remote system store location.</span></span> <span data-ttu-id="49700-154">Verwenden Sie einen umgekehrten Schrägstrich `\` oder einen Schrägstrich `/` , um eine Ebene des `WSMan:` Laufwerks anzugeben.</span><span class="sxs-lookup"><span data-stu-id="49700-154">Use a backslash `\` or forward slash `/` to indicate a level of the `WSMan:` drive.</span></span>

```powershell
Set-Location -Path  WSMan:\SERVER01
```

> [!NOTE]
> <span data-ttu-id="49700-155">Der obige Befehl geht davon aus, dass bereits eine Verbindung mit dem Remotesystem vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="49700-155">The above command assume that a connection to the remote system already exists.</span></span>

## <a name="displaying-the-contents-of-the-wsman-drive"></a><span data-ttu-id="49700-156">Anzeigen des Inhalts des WSMAN:-Laufwerks</span><span class="sxs-lookup"><span data-stu-id="49700-156">Displaying the Contents of the WSMan: Drive</span></span>

<span data-ttu-id="49700-157">Dieser Befehl verwendet das `Get-Childitem` Cmdlet, um die WS-Management Stores am localhost-Speicherort anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="49700-157">This command uses the `Get-Childitem` cmdlet to display the WS-Management stores in the Localhost store location.</span></span>

```powershell
Get-ChildItem -path WSMan:\Localhost
```

<span data-ttu-id="49700-158">Wenn Sie sich auf dem `WSMan:` Laufwerk befinden, können Sie den Namen des Laufwerks weglassen.</span><span class="sxs-lookup"><span data-stu-id="49700-158">If you are in the `WSMan:` drive, you can omit the drive name.</span></span>

<span data-ttu-id="49700-159">Dieser Befehl verwendet das `Get-Childitem` Cmdlet, um die WS-Management Stores im Speicherort des Remote Computers "Server01" anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="49700-159">This command uses the `Get-Childitem` cmdlet to display the WS-Management stores in the remote computer "SERVER01" store location.</span></span>

```powershell
Get-ChildItem -path WSMan:\SERVER01
```

> [!NOTE]
> <span data-ttu-id="49700-160">Der obige Befehl geht davon aus, dass bereits eine Verbindung mit dem Remotesystem vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="49700-160">The above command assume that a connection to the remote system already exists.</span></span>

## <a name="setting-the-value-of-items-in-the--wsman-drive"></a><span data-ttu-id="49700-161">Festlegen des Werts von Elementen im WSMAN:-Laufwerk</span><span class="sxs-lookup"><span data-stu-id="49700-161">Setting the value of items in the  WSMAN: drive</span></span>

<span data-ttu-id="49700-162">Sie können das `Set-Item` Cmdlet verwenden, um die Konfigurationseinstellungen im `WSMAN` Laufwerk zu ändern.</span><span class="sxs-lookup"><span data-stu-id="49700-162">You can use the `Set-Item` cmdlet to change configuration settings in the `WSMAN` drive.</span></span> <span data-ttu-id="49700-163">Im folgenden Beispiel wird der Wert für " **Treuhänder Hosts** " so festgelegt, dass alle Hosts mit dem Suffix "contoso.com" akzeptiert werden.</span><span class="sxs-lookup"><span data-stu-id="49700-163">The following example sets the **TrustedHosts** value to accept all hosts with the suffix "contoso.com".</span></span>

```powershell
# You do not need to specify the -Path parameter name when using Set-Item.
PS WSMAN:\localhost\Client> Set-Item .\TrustedHosts -Value "*.contoso.com"
```

<span data-ttu-id="49700-164">Das `Set-Item` Cmdlet unterstützt einen zusätzlichen Parameter `-Concatenate` , der einen Wert anfügt, anstatt ihn zu ändern.</span><span class="sxs-lookup"><span data-stu-id="49700-164">The `Set-Item` cmdlet supports an additional parameter `-Concatenate` that appends a value instead of changing it.</span></span> <span data-ttu-id="49700-165">Im folgenden Beispiel wird der neue Wert "\*. domain2.com" an den alten Wert angehängt, der in gespeichert ist. `TrustedHost:`</span><span class="sxs-lookup"><span data-stu-id="49700-165">The following example will append a new value "\*.domain2.com" to the old value stored in `TrustedHost:`</span></span>

```powershell
Set-Item WSMAN:\localhost\Client\TrustedHosts *.domain2.com -Concatenate
```

## <a name="creating-items-in-the-wsman-drive"></a><span data-ttu-id="49700-166">Erstellen von Elementen im WSMAN:-Laufwerk</span><span class="sxs-lookup"><span data-stu-id="49700-166">Creating items in the WSMAN: drive</span></span>

### <a name="creating-a-new-listener"></a><span data-ttu-id="49700-167">Erstellen eines neuen Listener</span><span class="sxs-lookup"><span data-stu-id="49700-167">Creating a new listener</span></span>

<span data-ttu-id="49700-168">Das- `New-Item` Cmdlet erstellt Elemente innerhalb eines Anbieter Laufwerks.</span><span class="sxs-lookup"><span data-stu-id="49700-168">The `New-Item` cmdlet creates items within a provider drive.</span></span> <span data-ttu-id="49700-169">Jeder Anbieter verfügt über verschiedene Elementtypen, die Sie erstellen können.</span><span class="sxs-lookup"><span data-stu-id="49700-169">Each provider has different item types that you can create.</span></span> <span data-ttu-id="49700-170">Auf dem `WSMAN:` Laufwerk können Sie Listener erstellen *,* die Sie konfigurieren, um Remote Anforderungen zu empfangen und darauf zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="49700-170">In the `WSMAN:` drive, you can create *Listeners* which you configure to receive and respond to remote requests.</span></span> <span data-ttu-id="49700-171">Mit dem folgenden Befehl wird ein neuer http-Listener mit dem- `New-Item` Cmdlet erstellt.</span><span class="sxs-lookup"><span data-stu-id="49700-171">The following command creates a new HTTP listener using the `New-Item` cmdlet.</span></span>

```powershell
New-Item -Path WSMan:\localhost\Listener -Address * -Transport HTTP -force
```

### <a name="creating-a-new-plug-in"></a><span data-ttu-id="49700-172">Erstellen eines neuen Plug-ins</span><span class="sxs-lookup"><span data-stu-id="49700-172">Creating a new plug-in</span></span>

<span data-ttu-id="49700-173">Dieser Befehl erstellt (registriert) ein Plug-In für den WS-Verwaltungsdienst.</span><span class="sxs-lookup"><span data-stu-id="49700-173">This command creates (registers) a plug-in for the WS-Management service.</span></span>

```powershell
New-Item -Path WSMan:\localhost\Plugin `
         -Plugin TestPlugin `
         -FileName %systemroot%\system32\WsmWmiPl.dll `
         -Resource http://schemas.dmtf.org/wbem/wscim/2/cim-schema `
         -SDKVersion 1 `
         -Capability "Get","Put","Invoke","Enumerate" `
         -XMLRenderingType text
```

### <a name="creating-a-new-resource-entry"></a><span data-ttu-id="49700-174">Erstellen eines neuen Ressourcen Eintrags</span><span class="sxs-lookup"><span data-stu-id="49700-174">Creating a new resource entry</span></span>

<span data-ttu-id="49700-175">Dieser Befehl erstellt einen Ressourcen Eintrag im Ressourcenverzeichnis von testplugin.</span><span class="sxs-lookup"><span data-stu-id="49700-175">This command creates a resource entry in the Resources directory of a TestPlugin.</span></span> <span data-ttu-id="49700-176">Bei diesem Befehl wird davon ausgegangen, dass ein testplugin mithilfe eines separaten Befehls erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="49700-176">This command assumes that a TestPlugin has been created using a separate command.</span></span>

```powershell
New-Item -Path WSMan:\localhost\Plugin\TestPlugin\Resources `
         -ResourceUri http://schemas.dmtf.org/wbem/wscim/3/cim-schema `
         -Capability "Enumerate"

```

### <a name="creating-a-new-security-entry-for-a-resource"></a><span data-ttu-id="49700-177">Erstellen eines neuen Sicherheits Eintrags für eine Ressource</span><span class="sxs-lookup"><span data-stu-id="49700-177">Creating a new security entry for a resource</span></span>

<span data-ttu-id="49700-178">Dieser Befehl erstellt einen Eintrag für die Sicherheit im Verzeichnis "Security" von Resource_5967683 (eine bestimmte Ressource).</span><span class="sxs-lookup"><span data-stu-id="49700-178">This command creates a security entry in the Security directory of Resource_5967683 (a specific resource).</span></span> <span data-ttu-id="49700-179">Bei diesem Befehl wird davon ausgegangen, dass der Ressourcen Eintrag mit einem separaten Befehl erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="49700-179">This command assumes that the resource entry has been created using a separate command.</span></span>

```powershell
$path = "WSMan:\localhost\Plugin\TestPlugin\Resources\Resource_5967683"
New-Item -Path $path\Security `
         -Sddl "O:NSG:BAD:P(A;;GA;;;BA)S:P(AU;FA;GA;;;WD)(AU;SA;GWGX;;;WD)"
```

### <a name="creating-a-new-client-certificate"></a><span data-ttu-id="49700-180">Erstellen eines neuen Client Zertifikats</span><span class="sxs-lookup"><span data-stu-id="49700-180">Creating a new Client Certificate</span></span>

<span data-ttu-id="49700-181">Mit diesem Befehl wird der **ClientCertificate** -Eintrag erstellt, der vom WS-Management-Client verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="49700-181">This command creates **ClientCertificate** entry that can be used by the WS-Management client.</span></span> <span data-ttu-id="49700-182">Das neue **ClientCertificate** wird unter dem Verzeichnis " **ClientCertificate** " als "ClientCertificate_1234567890" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="49700-182">The new **ClientCertificate** will show up under the **ClientCertificate** directory as "ClientCertificate_1234567890".</span></span> <span data-ttu-id="49700-183">Alle Parameter müssen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="49700-183">All of the parameters are mandatory.</span></span> <span data-ttu-id="49700-184">Der **Aussteller** muss den Fingerabdruck des Aussteller Zertifikats aufweisen.</span><span class="sxs-lookup"><span data-stu-id="49700-184">The **Issuer** needs to be thumbprint of the issuers certificate.</span></span>

```powershell
$cred = Get-Credential
New-Item -Path WSMan:\localhost\ClientCertificate `
         -Issuer 1b3fd224d66c6413fe20d21e38b304226d192dfe `
         -URI wmicimv2/* `
         -Credential $cred;
```

### <a name="creating-a-new-initialization-parameter"></a><span data-ttu-id="49700-185">Erstellen eines neuen Initialisierungs Parameters</span><span class="sxs-lookup"><span data-stu-id="49700-185">Creating a new Initialization Parameter</span></span>

<span data-ttu-id="49700-186">Dieser Befehl erstellt im Verzeichnis "initializationparameters" einen Initialisierungs Parameter mit dem Namen "testparametername".</span><span class="sxs-lookup"><span data-stu-id="49700-186">This command creates an Initialization parameter named "testparametername" in the "InitializationParameters" directory.</span></span> <span data-ttu-id="49700-187">Bei diesem Befehl wird davon ausgegangen, dass "testplugin" mit einem separaten Befehl erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="49700-187">This command assumes that the "TestPlugin" has been created using a separate command.</span></span>

```powershell
New-Item -Path WSMan:\localhost\Plugin\TestPlugin\InitializationParameters `
         -ParamName testparametername `
         -ParamValue testparametervalue
```

## <a name="dynamic-parameters"></a><span data-ttu-id="49700-188">Dynamische Parameter</span><span class="sxs-lookup"><span data-stu-id="49700-188">Dynamic parameters</span></span>

<span data-ttu-id="49700-189">Dynamische Parameter sind Cmdlet-Parameter, die von einem PowerShell-Anbieter hinzugefügt werden und nur verfügbar sind, wenn das Cmdlet im Anbieter fähigen Laufwerk verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="49700-189">Dynamic parameters are cmdlet parameters that are added by a PowerShell provider and are available only when the cmdlet is being used in the provider-enabled drive.</span></span>

### <a name="address-string"></a><span data-ttu-id="49700-190">Adresse \<String\></span><span class="sxs-lookup"><span data-stu-id="49700-190">Address \<String\></span></span>

<span data-ttu-id="49700-191">Gibt die Adresse an, für die der Listener erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="49700-191">Specifies the address for which this listener was created.</span></span> <span data-ttu-id="49700-192">Der Wert kann in folgenden Formen vorliegen:</span><span class="sxs-lookup"><span data-stu-id="49700-192">The value can be one of the following:</span></span>

- <span data-ttu-id="49700-193">Die Literalzeichenfolge "\*".</span><span class="sxs-lookup"><span data-stu-id="49700-193">The literal string "\*".</span></span> <span data-ttu-id="49700-194">(Mit dem Platzhalter Zeichen ( `*` ) werden alle IP-Adressen auf allen Netzwerkadaptern an den Befehl gebunden.)</span><span class="sxs-lookup"><span data-stu-id="49700-194">(The wildcard character (`*`) makes the command bind all the IP addresses on all the network adapters.)</span></span>
- <span data-ttu-id="49700-195">Die Literalzeichenfolge "IP:", gefolgt von einer gültigen IP-Adresse im IPv4-gepunkteten Dezimal Format oder im IPv6-Format mit geklontem hexadezimal.</span><span class="sxs-lookup"><span data-stu-id="49700-195">The literal string "IP:" followed by a valid IP address in either IPv4 dotted-decimal format or in IPv6 cloned-hexadecimal format.</span></span>
- <span data-ttu-id="49700-196">Die Literalzeichenfolge "Mac:" gefolgt von der Mac-Adresse eines Adapters.</span><span class="sxs-lookup"><span data-stu-id="49700-196">The literal string "MAC:" followed by the MAC address of an adapter.</span></span>
  <span data-ttu-id="49700-197">Beispiel: Mac: 32-a3-58 -90-be-cc.</span><span class="sxs-lookup"><span data-stu-id="49700-197">For example: MAC:32-a3-58-90-be-cc.</span></span>

> [!NOTE]
> <span data-ttu-id="49700-198">Der Wert der Adresse wird beim Erstellen eines Listeners festgelegt.</span><span class="sxs-lookup"><span data-stu-id="49700-198">The Address value is set when creating a Listener.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="49700-199">Unterstützte Cmdlets</span><span class="sxs-lookup"><span data-stu-id="49700-199">Cmdlets supported</span></span>

- [<span data-ttu-id="49700-200">New-Item</span><span class="sxs-lookup"><span data-stu-id="49700-200">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="capability-enumeration"></a><span data-ttu-id="49700-201">Re \<Enumeration\></span><span class="sxs-lookup"><span data-stu-id="49700-201">Capability \<Enumeration\></span></span>

<span data-ttu-id="49700-202">Beim Arbeiten mit *Plug-ins* gibt dieser Parameter einen Vorgang an, der für diesen Uniform Resource Identifier (URI) unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="49700-202">When working with *Plug-ins* this parameter specifies an operation that is supported on this Uniform Resource Identifier (URI).</span></span> <span data-ttu-id="49700-203">Sie müssen einen Eintrag für jede Art von Vorgang erstellen, die der URI unterstützt.</span><span class="sxs-lookup"><span data-stu-id="49700-203">You have to create one entry for each type of operation that the URI supports.</span></span> <span data-ttu-id="49700-204">Sie können beliebige gültige Attribute für einen bestimmten Vorgang angeben, wenn der Vorgang dies unterstützt.</span><span class="sxs-lookup"><span data-stu-id="49700-204">You can specify any valid attributes for a given operation, if the operation supports it.</span></span>

<span data-ttu-id="49700-205">Zu diesen Attributen gehören **SupportsFiltering** und **supportsfragment**.</span><span class="sxs-lookup"><span data-stu-id="49700-205">These attributes include **SupportsFiltering** and **SupportsFragment**.</span></span>

- <span data-ttu-id="49700-206">**Create** : Erstellungs Vorgänge werden für den URI unterstützt.</span><span class="sxs-lookup"><span data-stu-id="49700-206">**Create** : Create operations are supported on the URI.</span></span>
  - <span data-ttu-id="49700-207">Das **supportfragment**  -Attribut wird verwendet, wenn der Create-Vorgang das Konzept unterstützt.</span><span class="sxs-lookup"><span data-stu-id="49700-207">The **SupportFragment**  attribute is used if the Create operation supports the concept.</span></span>
  - <span data-ttu-id="49700-208">Das **supportfiltering** -Attribut ist für Erstellungs Vorgänge ungültig und sollte auf "false" festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="49700-208">The **SupportFiltering** attribute is NOT valid for Create operations and should be set to "False".</span></span>
  > [!NOTE]
  > <span data-ttu-id="49700-209">Dieser Vorgang ist nicht für einen URI gültig, wenn auch Shell-Vorgänge unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="49700-209">This operation is not valid for a URI if Shell operations are also supported.</span></span>
- <span data-ttu-id="49700-210">**Delete** : Löschvorgänge werden für den URI unterstützt.</span><span class="sxs-lookup"><span data-stu-id="49700-210">**Delete** : Delete operations are supported on the URI.</span></span>
  - <span data-ttu-id="49700-211">Das **supportfragment** -Attribut wird verwendet, wenn der DELETE-Vorgang das Konzept unterstützt.</span><span class="sxs-lookup"><span data-stu-id="49700-211">The **SupportFragment** attribute is used if the Delete operation supports the concept.</span></span>
  - <span data-ttu-id="49700-212">Das **supportfiltering** -Attribut ist für Löschvorgänge ungültig und sollte auf "false" festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="49700-212">The **SupportFiltering** attribute is NOT valid for Delete operations and should be set to "False".</span></span>
  > [!NOTE]
  > <span data-ttu-id="49700-213">Dieser Vorgang ist nicht für einen URI gültig, wenn auch Shell-Vorgänge unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="49700-213">This operation is not valid for a URI if Shell operations are also supported.</span></span>
- <span data-ttu-id="49700-214">**Enumerate** : aufzählenden Vorgänge werden für den URI unterstützt.</span><span class="sxs-lookup"><span data-stu-id="49700-214">**Enumerate** : Enumerate operations are supported on the URI.</span></span>
  - <span data-ttu-id="49700-215">Das **supportfragment** -Attribut wird für Enumerate-Vorgänge nicht unterstützt und sollte auf false festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="49700-215">The **SupportFragment** attribute is NOT supported for Enumerate operations and should be set to False.</span></span>
  - <span data-ttu-id="49700-216">Das **supportfiltering** -Attribut ist gültig, und wenn das Plug-in das Filtern unterstützt, sollte dieses Attribut auf "true" festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="49700-216">The **SupportFiltering** attribute is valid, and if the plug-in supports filtering, this attribute should be set to "True".</span></span>
  > [!NOTE]
  > <span data-ttu-id="49700-217">Dieser Vorgang ist nicht für einen URI gültig, wenn auch Shell-Vorgänge unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="49700-217">This operation is not valid for a URI if Shell operations are also supported.</span></span>
- <span data-ttu-id="49700-218">**Get** : Get-Vorgänge werden für den URI unterstützt.</span><span class="sxs-lookup"><span data-stu-id="49700-218">**Get** : Get operations are supported on the URI.</span></span>
  - <span data-ttu-id="49700-219">Das **supportfragment** -Attribut wird verwendet, wenn der Get-Vorgang das Konzept unterstützt.</span><span class="sxs-lookup"><span data-stu-id="49700-219">The **SupportFragment** attribute is used if the Get operation supports the concept.</span></span>
  - <span data-ttu-id="49700-220">Das **supportfiltering** -Attribut ist für Get-Vorgänge ungültig und sollte auf "false" festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="49700-220">The **SupportFiltering** attribute is NOT valid for Get operations and should be set to "False".</span></span>
  > [!NOTE]
  > <span data-ttu-id="49700-221">Dieser Vorgang ist nicht für einen URI gültig, wenn auch Shell-Vorgänge unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="49700-221">This operation is not valid for a URI if Shell operations are also supported.</span></span>
- <span data-ttu-id="49700-222">**Aufrufen** : Aufruf Vorgänge werden für den URI unterstützt.</span><span class="sxs-lookup"><span data-stu-id="49700-222">**Invoke** : Invoke operations are supported on the URI.</span></span>
  - <span data-ttu-id="49700-223">Das **supportfragment** -Attribut wird für Aufruf Vorgänge nicht unterstützt und sollte auf false festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="49700-223">The **SupportFragment** attribute is not supported for Invoke operations and should be set to False.</span></span>
  - <span data-ttu-id="49700-224">Das **supportfiltering** -Attribut ist ungültig und sollte auf "false" festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="49700-224">The **SupportFiltering** attribute is not valid and should be set to "False".</span></span>
  > [!NOTE]
  > <span data-ttu-id="49700-225">Dieser Vorgang ist nicht für einen URI gültig, wenn auch Shell-Vorgänge unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="49700-225">This operation is not valid for a URI if Shell operations are also supported.</span></span>
- <span data-ttu-id="49700-226">**Put** : Put-Vorgänge werden für den URI unterstützt.</span><span class="sxs-lookup"><span data-stu-id="49700-226">**Put** : Put operations are supported on the URI.</span></span>
  - <span data-ttu-id="49700-227">Das **supportfragment** -Attribut wird verwendet, wenn der Put-Vorgang das Konzept unterstützt.</span><span class="sxs-lookup"><span data-stu-id="49700-227">The **SupportFragment** attribute is used if the Put operation supports the concept.</span></span>
  - <span data-ttu-id="49700-228">Das **supportfiltering** -Attribut ist für Put-Vorgänge ungültig und sollte auf "false" festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="49700-228">The **SupportFiltering** attribute is not valid for Put operations and should be set to "False".</span></span>
  > [!NOTE]
  > <span data-ttu-id="49700-229">Dieser Vorgang ist nicht für einen URI gültig, wenn auch Shell-Vorgänge unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="49700-229">This operation is not valid for a URI if Shell operations are also supported.</span></span>
- <span data-ttu-id="49700-230">**Abonnieren** : abonnieren-Vorgänge werden für den URI unterstützt.</span><span class="sxs-lookup"><span data-stu-id="49700-230">**Subscribe** : Subscribe operations are supported on the URI.</span></span>
  - <span data-ttu-id="49700-231">Das **supportfragment** -Attribut wird für abonnieren-Vorgänge nicht unterstützt und sollte auf false festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="49700-231">The **SupportFragment** attribute is not supported for Subscribe operations and should be set to False.</span></span>
  - <span data-ttu-id="49700-232">Das **supportfiltering** -Attribut ist für subscribe-Vorgänge ungültig und sollte auf "false" festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="49700-232">The **SupportFiltering** attribute is not valid for Subscribe operations and should be set to "False".</span></span>
  > [!NOTE]
  > <span data-ttu-id="49700-233">Dieser Vorgang ist nicht für einen URI gültig, wenn auch Shell-Vorgänge unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="49700-233">This operation is not valid for a URI if Shell operations are also supported.</span></span>
- <span data-ttu-id="49700-234">**Shell** : Shellvorgänge werden für den URI unterstützt.</span><span class="sxs-lookup"><span data-stu-id="49700-234">**Shell** : Shell operations are supported on the URI.</span></span>
  - <span data-ttu-id="49700-235">Das **supportfragment** -Attribut wird für Shellvorgänge nicht unterstützt und muss auf "false" festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="49700-235">The **SupportFragment** attribute is not supported for Shell operations and should be set to "False".</span></span>
  - <span data-ttu-id="49700-236">Das **supportfiltering** -Attribut ist für Shellvorgänge nicht gültig und sollte auf "false" festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="49700-236">The **SupportFiltering** attribute is not valid for Shell operations and should be set to "False".</span></span>
  > [!NOTE]
  > <span data-ttu-id="49700-237">Dieser Vorgang ist für einen URI ungültig, wenn ein anderer Vorgang ebenfalls unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="49700-237">This operation is not valid for a URI if ANY other operation is also supported.</span></span>
  > [!NOTE]
  > <span data-ttu-id="49700-238">Wenn ein Shell-Vorgang für eine URI konfiguriert ist, werden Get-, Put-, Create-, Delete-, Invoke- und Enumerate-Vorgänge intern innerhalb des WS-Verwaltungsdiensts (WinRM) zum Verwalten von Shells verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="49700-238">If a Shell operation is configured for a URI, Get, Put, Create, Delete, Invoke, and Enumerate operations are processed internally within the WS-Management (WinRM) service to manage shells.</span></span> <span data-ttu-id="49700-239">Daher kann das Plug-In die Vorgänge nicht verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="49700-239">As a result, the plug-in cannot handle the operations.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="49700-240">Unterstützte Cmdlets</span><span class="sxs-lookup"><span data-stu-id="49700-240">Cmdlets supported</span></span>

- [<span data-ttu-id="49700-241">New-Item</span><span class="sxs-lookup"><span data-stu-id="49700-241">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="certificatethumbprint-string"></a><span data-ttu-id="49700-242">CertificateThumbprint \<String\></span><span class="sxs-lookup"><span data-stu-id="49700-242">CertificateThumbprint \<String\></span></span>

<span data-ttu-id="49700-243">Gibt den Fingerabdruck des Dienstzertifikats an.</span><span class="sxs-lookup"><span data-stu-id="49700-243">Specifies the thumbprint of the service certificate.</span></span>

<span data-ttu-id="49700-244">Dieser Wert repräsentiert die Zeichenfolge von zweistelligen Hexadezimalwerten im Fingerabdruckfeld des Zertifikats.</span><span class="sxs-lookup"><span data-stu-id="49700-244">This value represents the string of two-digit hexadecimal values in the Thumbprint field of the certificate.</span></span> <span data-ttu-id="49700-245">Es gibt das digitale Zertifikat für öffentliche Schlüssel (X509) eines Benutzerkontos an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="49700-245">It specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span> <span data-ttu-id="49700-246">Zertifikate werden bei der clientzertifikatbasierten Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="49700-246">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="49700-247">Sie können nur lokalen Benutzerkonten zugeordnet und nicht mit Domänenkonten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="49700-247">They can be mapped only to local user accounts, and they do not work with domain accounts.</span></span> <span data-ttu-id="49700-248">Um einen Zertifikat Fingerabdruck abzurufen, verwenden Sie das- `Get-Item` `Get-ChildItem` Cmdlet oder das-Cmdlet auf dem PowerShell- `Cert:` Laufwerk.</span><span class="sxs-lookup"><span data-stu-id="49700-248">To get a certificate thumbprint, use the `Get-Item` or `Get-ChildItem` cmdlets in the PowerShell `Cert:` drive.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="49700-249">Unterstützte Cmdlets</span><span class="sxs-lookup"><span data-stu-id="49700-249">Cmdlets supported</span></span>

- [<span data-ttu-id="49700-250">New-Item</span><span class="sxs-lookup"><span data-stu-id="49700-250">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="enabled-boolean"></a><span data-ttu-id="49700-251">Wodurch \<Boolean\></span><span class="sxs-lookup"><span data-stu-id="49700-251">Enabled \<Boolean\></span></span>

<span data-ttu-id="49700-252">Gibt an, ob der Listener aktiviert oder deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="49700-252">Specifies whether the listener is enabled or disabled.</span></span> <span data-ttu-id="49700-253">Der Standardwert ist True.</span><span class="sxs-lookup"><span data-stu-id="49700-253">The default is True.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="49700-254">Unterstützte Cmdlets</span><span class="sxs-lookup"><span data-stu-id="49700-254">Cmdlets Supported</span></span>

- [<span data-ttu-id="49700-255">New-Item</span><span class="sxs-lookup"><span data-stu-id="49700-255">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="filename-plugin-string"></a><span data-ttu-id="49700-256">Dateiname (Plugin) \<String\></span><span class="sxs-lookup"><span data-stu-id="49700-256">FileName (Plugin) \<String\></span></span>

<span data-ttu-id="49700-257">Gibt den Dateinamen des Vorgangs-Plug-ins an.</span><span class="sxs-lookup"><span data-stu-id="49700-257">Specifies the file name of the operations plug-in.</span></span> <span data-ttu-id="49700-258">Alle Umgebungsvariablen, die in diesen Eintrag eingefügt werden, werden im Kontext des Benutzers erweitert, wenn eine Anforderung empfangen wird.</span><span class="sxs-lookup"><span data-stu-id="49700-258">Any environment variables that are put in this entry will be expanded in the users' context when a request is received.</span></span> <span data-ttu-id="49700-259">Da jeder Benutzer eine andere Version der gleichen Umgebungsvariablen aufweisen könnte, kann jeder Benutzer über ein anderes Plug-in verfügen.</span><span class="sxs-lookup"><span data-stu-id="49700-259">Because each user could have a different version of the same environment variable, each user could have a different plug-in.</span></span> <span data-ttu-id="49700-260">Dieser Eintrag darf nicht leer sein und muss auf ein gültiges Plug-in zeigen.</span><span class="sxs-lookup"><span data-stu-id="49700-260">This entry cannot be blank and must point to a valid plug-in.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="49700-261">Unterstützte Cmdlets</span><span class="sxs-lookup"><span data-stu-id="49700-261">Cmdlets Supported</span></span>

- [<span data-ttu-id="49700-262">New-Item</span><span class="sxs-lookup"><span data-stu-id="49700-262">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="hostname-string"></a><span data-ttu-id="49700-263">Hostname \<String\></span><span class="sxs-lookup"><span data-stu-id="49700-263">HostName \<String\></span></span>

<span data-ttu-id="49700-264">Gibt den Hostnamen des Computers an, auf dem der WS-Management-Dienst (WinRM) ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="49700-264">Specifies the host name of the computer on which the WS-Management (WinRM) service is running.</span></span>

<span data-ttu-id="49700-265">Bei diesem Wert muss es sich um einen vollständig qualifizierten Domänennamen, eine IPv4- oder IPv6-Literalzeichenfolge oder ein Platzhalterzeichen handeln.</span><span class="sxs-lookup"><span data-stu-id="49700-265">The value must be a fully qualified domain name, an IPv4 or IPv6 literal string, or a wildcard character.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="49700-266">Unterstützte Cmdlets</span><span class="sxs-lookup"><span data-stu-id="49700-266">Cmdlets Supported</span></span>

- [<span data-ttu-id="49700-267">New-Item</span><span class="sxs-lookup"><span data-stu-id="49700-267">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="issuer-string"></a><span data-ttu-id="49700-268">Stellers \<String\></span><span class="sxs-lookup"><span data-stu-id="49700-268">Issuer \<String\></span></span>

<span data-ttu-id="49700-269">Gibt den Namen der Zertifizierungsstelle an, die das Zertifikat ausgestellt hat.</span><span class="sxs-lookup"><span data-stu-id="49700-269">Specifies the name of the certification authority that issued the certificate.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="49700-270">Unterstützte Cmdlets</span><span class="sxs-lookup"><span data-stu-id="49700-270">Cmdlets Supported</span></span>

- [<span data-ttu-id="49700-271">New-Item</span><span class="sxs-lookup"><span data-stu-id="49700-271">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="plugin--ws-management-plug-ins-are-native-dynamic-link-libraries-dlls"></a><span data-ttu-id="49700-272">\<\>Plug-Ins für Plug-ins WS-Management sind native Dynamic Link Libraries (DLLs)</span><span class="sxs-lookup"><span data-stu-id="49700-272">Plugin \<\> WS-Management plug-ins are native dynamic link libraries (DLLs)</span></span>

<span data-ttu-id="49700-273">das Plug-in und erweitert die Funktionalität von WS-Management.</span><span class="sxs-lookup"><span data-stu-id="49700-273">that plug in to and extend the functionality of WS-Management .</span></span> <span data-ttu-id="49700-274">Die WSW-Management-Plug-in-API stellt Funktionen bereit, mit denen ein Benutzer Plug-ins schreiben kann, indem er bestimmte APIs für unterstützte Ressourcen-URIs und-Vorgänge implementiert.</span><span class="sxs-lookup"><span data-stu-id="49700-274">The WSW-Management Plug-in API provides functionality that enables a user to write plug-ins by implementing certain APIs for supported resource URIs and operations.</span></span> <span data-ttu-id="49700-275">Nachdem die Plug-Ins entweder für den WS-Verwaltungsdienst (WinRM) oder für Internet Information Services (IIS) konfiguriert wurden, werden die Plug-Ins in den WS-Management-Host oder in den IIS-Host geladen.</span><span class="sxs-lookup"><span data-stu-id="49700-275">After the plug-ins are configured for either the WS-Management (WinRM) service or for Internet Information Services (IIS), the plug-ins are loaded in the WS-Management host or in the IIS host, respectively.</span></span> <span data-ttu-id="49700-276">Remoteanforderungen werden an diese Plug-In-Einstiegspunkte für Operationen weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="49700-276">Remote requests are routed to these plug-in entry points to perform operations.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="49700-277">Unterstützte Cmdlets</span><span class="sxs-lookup"><span data-stu-id="49700-277">Cmdlets Supported</span></span>

- [<span data-ttu-id="49700-278">New-Item</span><span class="sxs-lookup"><span data-stu-id="49700-278">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="port-unsigned-short-integer"></a><span data-ttu-id="49700-279">Port \<Unsigned Short Integer\></span><span class="sxs-lookup"><span data-stu-id="49700-279">Port \<Unsigned Short Integer\></span></span>

<span data-ttu-id="49700-280">Gibt den TCP-Port an, für den der Listener erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="49700-280">Specifies the TCP port for which this listener is created.</span></span> <span data-ttu-id="49700-281">Sie können einen beliebigen Wert zwischen 1 und 65535 angeben.</span><span class="sxs-lookup"><span data-stu-id="49700-281">You can specify any value from 1 through 65535.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="49700-282">Unterstützte Cmdlets</span><span class="sxs-lookup"><span data-stu-id="49700-282">Cmdlets Supported</span></span>

- [<span data-ttu-id="49700-283">New-Item</span><span class="sxs-lookup"><span data-stu-id="49700-283">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="resource-string"></a><span data-ttu-id="49700-284">Ressource \<String\></span><span class="sxs-lookup"><span data-stu-id="49700-284">Resource \<String\></span></span>

<span data-ttu-id="49700-285">Gibt einen Endpunkt an, der einen unterschiedlichen Typ von Verwaltungsvorgang oder Wert darstellt.</span><span class="sxs-lookup"><span data-stu-id="49700-285">Specifies an endpoint that represents a distinct type of management operation or value.</span></span> <span data-ttu-id="49700-286">Ein Dienst macht eine oder mehrere Ressourcen verfügbar, und einige Ressourcen können mehr als eine Instanz aufweisen.</span><span class="sxs-lookup"><span data-stu-id="49700-286">A service exposes one or more resources, and some resources can have more than one instance.</span></span> <span data-ttu-id="49700-287">Eine Management-Ressource ist vergleichbar mit einer WMI-Klasse oder einer Datenbanktabelle, und eine Instanz ist vergleichbar mit einer Instanz der Klasse oder einer Zeile in der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="49700-287">A management resource is similar to a WMI class or to a database table, and an instance is similar to an instance of the class or to a row in the table.</span></span> <span data-ttu-id="49700-288">Beispielsweise stellt die **Win32_LogicalDisk** -Klasse eine Ressource dar.</span><span class="sxs-lookup"><span data-stu-id="49700-288">For example, the **Win32_LogicalDisk** class represents a resource.</span></span> <span data-ttu-id="49700-289">`Win32_LogicalDisk="C:\\"` ist eine bestimmte Instanz der Ressource.</span><span class="sxs-lookup"><span data-stu-id="49700-289">`Win32_LogicalDisk="C:\\"` is a specific instance of the resource.</span></span>

<span data-ttu-id="49700-290">Ein Uniform Resource Identifier (URI) enthält ein Präfix und einen Pfad zu einer Ressource.</span><span class="sxs-lookup"><span data-stu-id="49700-290">A Uniform Resource Identifier (URI) contains a prefix and a path to a resource.</span></span>
<span data-ttu-id="49700-291">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="49700-291">For example:</span></span>

`http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`

`http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/CIM_NumericSensor`

#### <a name="cmdlets-supported"></a><span data-ttu-id="49700-292">Unterstützte Cmdlets</span><span class="sxs-lookup"><span data-stu-id="49700-292">Cmdlets Supported</span></span>

- [<span data-ttu-id="49700-293">New-Item</span><span class="sxs-lookup"><span data-stu-id="49700-293">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="resource-string"></a><span data-ttu-id="49700-294">Ressource \<String\></span><span class="sxs-lookup"><span data-stu-id="49700-294">Resource \<String\></span></span>

<span data-ttu-id="49700-295">Gibt den Uniform Resource Identifier (URI) an, der eine bestimmte Art von Ressource identifiziert, z. B. ein Datenträger oder ein Prozess auf einem Computer.</span><span class="sxs-lookup"><span data-stu-id="49700-295">Specifies the Uniform Resource Identifier (URI) that identifies a specific type of resource, such as a disk or a process, on a computer.</span></span>

<span data-ttu-id="49700-296">Ein URI besteht aus einem Präfix und einem Pfad zu einer Ressource.</span><span class="sxs-lookup"><span data-stu-id="49700-296">A URI consists of a prefix and a path to a resource.</span></span> <span data-ttu-id="49700-297">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="49700-297">For example:</span></span>

`http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`

`http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/CIM_NumericSensor`

#### <a name="cmdlets-supported"></a><span data-ttu-id="49700-298">Unterstützte Cmdlets</span><span class="sxs-lookup"><span data-stu-id="49700-298">Cmdlets Supported</span></span>

- [<span data-ttu-id="49700-299">New-Item</span><span class="sxs-lookup"><span data-stu-id="49700-299">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="sdkversion-string"></a><span data-ttu-id="49700-300">SDKVersion \<String\></span><span class="sxs-lookup"><span data-stu-id="49700-300">SDKVersion \<String\></span></span>

<span data-ttu-id="49700-301">Gibt die Version des WS-Management-Plug-In-SDKs an.</span><span class="sxs-lookup"><span data-stu-id="49700-301">Specifies the version of the WS-Management plug-in SDK.</span></span> <span data-ttu-id="49700-302">Der einzige gültige Wert ist .</span><span class="sxs-lookup"><span data-stu-id="49700-302">The only valid value is</span></span>
1.

#### <a name="cmdlets-supported"></a><span data-ttu-id="49700-303">Unterstützte Cmdlets</span><span class="sxs-lookup"><span data-stu-id="49700-303">Cmdlets Supported</span></span>

- [<span data-ttu-id="49700-304">New-Item</span><span class="sxs-lookup"><span data-stu-id="49700-304">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="subject-string"></a><span data-ttu-id="49700-305">Betreff \<String\></span><span class="sxs-lookup"><span data-stu-id="49700-305">Subject \<String\></span></span>

<span data-ttu-id="49700-306">Gibt die Entität an, die durch das Zertifikat identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="49700-306">Specifies the entity that is identified by the certificate.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="49700-307">Unterstützte Cmdlets</span><span class="sxs-lookup"><span data-stu-id="49700-307">Cmdlets Supported</span></span>

- [<span data-ttu-id="49700-308">New-Item</span><span class="sxs-lookup"><span data-stu-id="49700-308">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="transport-string"></a><span data-ttu-id="49700-309">Personen \<String\></span><span class="sxs-lookup"><span data-stu-id="49700-309">Transport \<String\></span></span>

<span data-ttu-id="49700-310">Legt den Transport zum Senden und Empfangen von WS-Management-Protokollanforderungen und -antworten fest.</span><span class="sxs-lookup"><span data-stu-id="49700-310">Specifies the transport to use to send and receive WS-Management protocol requests and responses.</span></span> <span data-ttu-id="49700-311">Der Wert muss entweder HTTP oder HTTPS sein.</span><span class="sxs-lookup"><span data-stu-id="49700-311">The value must be either HTTP or HTTPS.</span></span>

<span data-ttu-id="49700-312">Hinweis: der Transport Wert wird festgelegt, wenn ein Listener erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="49700-312">Note: The Transport value is set when creating a Listener.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="49700-313">Unterstützte Cmdlets</span><span class="sxs-lookup"><span data-stu-id="49700-313">Cmdlets Supported</span></span>

- [<span data-ttu-id="49700-314">New-Item</span><span class="sxs-lookup"><span data-stu-id="49700-314">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="uri-string"></a><span data-ttu-id="49700-315">RT \<String\></span><span class="sxs-lookup"><span data-stu-id="49700-315">URI \<String\></span></span>

<span data-ttu-id="49700-316">Gibt den URI an, für den der Zugriff basierend auf dem Wert des Parameters Sddl gewährt wird.</span><span class="sxs-lookup"><span data-stu-id="49700-316">Identifies the URI for which access is authorized based on the value of the Sddl parameter.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="49700-317">Unterstützte Cmdlets</span><span class="sxs-lookup"><span data-stu-id="49700-317">Cmdlets Supported</span></span>

- [<span data-ttu-id="49700-318">New-Item</span><span class="sxs-lookup"><span data-stu-id="49700-318">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="urlprefix-string"></a><span data-ttu-id="49700-319">URLPrefix \<String\></span><span class="sxs-lookup"><span data-stu-id="49700-319">URLPrefix \<String\></span></span>

<span data-ttu-id="49700-320">Ein URL-Präfix für das Akzeptieren von HTTP- oder HTTPS-Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="49700-320">A URL prefix on which to accept HTTP or HTTPS requests.</span></span> <span data-ttu-id="49700-321">Dabei handelt es sich um eine Zeichenfolge, die nur die Zeichen, `[a-z]` `[A-Z]` , `[9-0]` , Unterstriche ( `_` ) und umgekehrten Schrägstrich ( `/` ) enthält.</span><span class="sxs-lookup"><span data-stu-id="49700-321">This is a string containing only the characters `[a-z]`, `[A-Z]`, `[9-0]`, underscore (`_`) and backslash (`/`).</span></span> <span data-ttu-id="49700-322">Die Zeichenfolge darf nicht mit einem umgekehrten Schrägstrich () beginnen oder mit einem umgekehrten Schrägstrich enden `/` .</span><span class="sxs-lookup"><span data-stu-id="49700-322">The string must not start with or end with a backslash (`/`).</span></span> <span data-ttu-id="49700-323">Wenn der Computername beispielsweise "samplecomputer" ist, würde der WS-Management Client `http://SampleMachine/URLPrefix` in der Zieladresse angeben.</span><span class="sxs-lookup"><span data-stu-id="49700-323">For example, if the computer name is "SampleComputer", the WS-Management client would specify `http://SampleMachine/URLPrefix` in the destination address.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="49700-324">Unterstützte Cmdlets</span><span class="sxs-lookup"><span data-stu-id="49700-324">Cmdlets Supported</span></span>

- [<span data-ttu-id="49700-325">New-Item</span><span class="sxs-lookup"><span data-stu-id="49700-325">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="value-string"></a><span data-ttu-id="49700-326">Wert \<String\></span><span class="sxs-lookup"><span data-stu-id="49700-326">Value \<String\></span></span>

<span data-ttu-id="49700-327">Gibt den Wert eines Initialisierungsparameters an, einem Plug-In-spezifischen Wert, der verwendet wird, um Konfigurationsoptionen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="49700-327">Specifies the value of an initialization parameter, which is a plug-in-specific value that is used to specify configuration options.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="49700-328">Unterstützte Cmdlets</span><span class="sxs-lookup"><span data-stu-id="49700-328">Cmdlets Supported</span></span>

- [<span data-ttu-id="49700-329">New-Item</span><span class="sxs-lookup"><span data-stu-id="49700-329">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="xmlrenderingtype-string"></a><span data-ttu-id="49700-330">Xmlrenderingtype \<String\></span><span class="sxs-lookup"><span data-stu-id="49700-330">XMLRenderingType \<String\></span></span>

<span data-ttu-id="49700-331">Gibt das Format an, in dem XML über das **WSMAN_DATA** Objekt an Plug-ins übermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="49700-331">Specifies the format in which XML is passed to plug-ins through the **WSMAN_DATA** object.</span></span> <span data-ttu-id="49700-332">Die folgenden sind Werte gültig:</span><span class="sxs-lookup"><span data-stu-id="49700-332">The following are valid values:</span></span>

- <span data-ttu-id="49700-333">Text: eingehende XML-Daten sind in einer **WSMAN_DATA_TYPE_TEXT** -Struktur enthalten, die den XML-Code als **pcwstr** -Arbeitsspeicher Puffer darstellt.</span><span class="sxs-lookup"><span data-stu-id="49700-333">Text: Incoming XML data is contained in a **WSMAN_DATA_TYPE_TEXT** structure, which represents the XML as a **PCWSTR** memory buffer.</span></span>
- <span data-ttu-id="49700-334">XmlReader: eingehende XML-Daten sind in einer **WSMAN_DATA_TYPE_WS_XML_READER** -Struktur enthalten, die den XML-Code als **XmlReader** -Objekt darstellt, das in der Header Datei "Webservices. h" definiert ist.</span><span class="sxs-lookup"><span data-stu-id="49700-334">XMLReader: Incoming XML data is contained in a **WSMAN_DATA_TYPE_WS_XML_READER** structure, which represents the XML as an **XmlReader** object, which is defined in the "WebServices.h" header file.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="49700-335">Unterstützte Cmdlets</span><span class="sxs-lookup"><span data-stu-id="49700-335">Cmdlets Supported</span></span>

- [<span data-ttu-id="49700-336">New-Item</span><span class="sxs-lookup"><span data-stu-id="49700-336">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

## <a name="using-the-pipeline"></a><span data-ttu-id="49700-337">Verwenden der Pipeline</span><span class="sxs-lookup"><span data-stu-id="49700-337">Using the pipeline</span></span>

<span data-ttu-id="49700-338">Anbieter-Cmdlets akzeptieren Pipeline Eingaben.</span><span class="sxs-lookup"><span data-stu-id="49700-338">Provider cmdlets accept pipeline input.</span></span> <span data-ttu-id="49700-339">Sie können die Pipeline verwenden, um die Aufgabe zu vereinfachen, indem Sie Anbieter Daten von einem Cmdlet an ein anderes Anbieter-Cmdlet senden.</span><span class="sxs-lookup"><span data-stu-id="49700-339">You can use the pipeline to simplify task by sending provider data from one cmdlet to another provider cmdlet.</span></span>
<span data-ttu-id="49700-340">Weitere Informationen zur Verwendung der Pipeline mit Anbieter-Cmdlets finden Sie in den Cmdlet-Referenzen in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="49700-340">To read more about how to use the pipeline with provider cmdlets, see the cmdlet references provided throughout this article.</span></span>

## <a name="getting-help"></a><span data-ttu-id="49700-341">Hilfe</span><span class="sxs-lookup"><span data-stu-id="49700-341">Getting help</span></span>

<span data-ttu-id="49700-342">Ab Windows PowerShell 3.0 können Sie benutzerdefinierte Hilfethemen für Anbieter-Cmdlets abrufen, die erläutern, wie sich diese Cmdlets in einem Dateisystemlaufwerk verhalten.</span><span class="sxs-lookup"><span data-stu-id="49700-342">Beginning in Windows PowerShell 3.0, you can get customized help topics for provider cmdlets that explain how those cmdlets behave in a file system drive.</span></span>

<span data-ttu-id="49700-343">Zum Aufrufen der Hilfe Themen, die für das Dateisystem Laufwerk angepasst sind, führen Sie einen [Get-Help-](xref:Microsoft.PowerShell.Core.Get-Help) Befehl in einem Dateisystem Laufwerk aus, oder verwenden Sie den `-Path` -Parameter von [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) zum Angeben eines Dateisystem Laufwerks.</span><span class="sxs-lookup"><span data-stu-id="49700-343">To get the help topics that are customized for the file system drive, run a [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) command in a file system drive or use the `-Path` parameter of [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) to specify a file system drive.</span></span>

```powershell
Get-Help Get-ChildItem
```

```powershell
Get-Help Get-ChildItem -Path wsman:
```

## <a name="see-also"></a><span data-ttu-id="49700-344">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="49700-344">See also</span></span>

[<span data-ttu-id="49700-345">about_Providers</span><span class="sxs-lookup"><span data-stu-id="49700-345">about_Providers</span></span>](../../Microsoft.PowerShell.Core/About/about_Providers.md)
