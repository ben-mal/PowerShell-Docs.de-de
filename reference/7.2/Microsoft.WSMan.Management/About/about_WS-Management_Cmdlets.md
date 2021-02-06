---
description: Bietet einen Überblick über die Web Services for Management (WS-Management) als Hintergrund für die Verwendung der WS-Management-Cmdlets in Windows PowerShell.
Locale: en-US
ms.date: 01/04/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/about/about_ws-management_cmdlets?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_WS Management_Cmdlets
ms.openlocfilehash: faf0f0b08d604f7568ac316557788eea21feea8d
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600711"
---
# <a name="about-ws-management-cmdlets"></a><span data-ttu-id="e26b8-103">Informationen zu WS-Management Cmdlets</span><span class="sxs-lookup"><span data-stu-id="e26b8-103">About WS-Management Cmdlets</span></span>

## <a name="short-description"></a><span data-ttu-id="e26b8-104">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e26b8-104">SHORT DESCRIPTION</span></span>

<span data-ttu-id="e26b8-105">Bietet einen Überblick über die Web Services for Management (WS-Management) als Hintergrund für die Verwendung der WS-Management-Cmdlets in Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e26b8-105">Provides an overview of Web Services for Management (WS-Management) as background for using the WS-Management cmdlets in Windows PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="e26b8-106">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e26b8-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="e26b8-107">Dieses Thema bietet einen Überblick über die Web Services for Management (WS-Management) als Hintergrund für die Verwendung der WS-Management-Cmdlets in Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e26b8-107">This topic provides an overview of Web Services for Management (WS-Management) as background for using the WS-Management cmdlets in Windows PowerShell.</span></span> <span data-ttu-id="e26b8-108">Dieses Thema enthält auch Links zu weiteren Informationen zur WS-Verwaltung.</span><span class="sxs-lookup"><span data-stu-id="e26b8-108">This topic also provides links to more information about WS-Management.</span></span> <span data-ttu-id="e26b8-109">Die Microsoft-Implementierung von WS-Management wird auch als Windows-Remoteverwaltung (WinRM) bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="e26b8-109">The Microsoft implementation of WS-Management is also known as Windows Remote Management (WinRM).</span></span>

## <a name="about-ws-management"></a><span data-ttu-id="e26b8-110">Informationen zu WS-Management</span><span class="sxs-lookup"><span data-stu-id="e26b8-110">About WS-Management</span></span>

<span data-ttu-id="e26b8-111">Windows-Remoteverwaltung ist die Microsoft-Implementierung des WS-Management-Protokolls, ein Standardmäßiges SOAP-basiertes, firewallfreundliches Protokoll, mit dem Hardware und Betriebssysteme verschiedener Anbieter zusammenarbeiten können.</span><span class="sxs-lookup"><span data-stu-id="e26b8-111">Windows Remote Management is the Microsoft implementation of the WS-Management protocol, a standard SOAP-based, firewall-friendly protocol that allows hardware and operating systems from different vendors to interoperate.</span></span> <span data-ttu-id="e26b8-112">Die WS-Management-Protokollspezifikation ist eine gängige Methode für Systeme, um auf Verwaltungsinformationen in einer IT-Infrastruktur zuzugreifen und diese auszutauschen.</span><span class="sxs-lookup"><span data-stu-id="e26b8-112">The WS-Management protocol specification provides a common way for systems to access and exchange management information across an information technology (IT) infrastructure.</span></span> <span data-ttu-id="e26b8-113">WS-Management und Intelligent Platform Management Interface (IPMI) sind zusammen mit dem Ereignis Sammler Komponenten der Windows-Hardware Verwaltungsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="e26b8-113">WS-Management and Intelligent Platform Management Interface (IPMI), along with the Event Collector, are components of the Windows Hardware Management features.</span></span>

<span data-ttu-id="e26b8-114">Das WS-Management Protokoll basiert auf den folgenden Standardweb Dienst Spezifikationen: https, SOAP über HTTP (WS-I Profile), SOAP 1,2, WS-Adressierung, WS-Transfer, WS-Enumeration und WS-Event.</span><span class="sxs-lookup"><span data-stu-id="e26b8-114">The WS-Management protocol is based on the following standard Web service specifications: HTTPS, SOAP over HTTP (WS-I profile), SOAP 1.2, WS-Addressing, WS-Transfer, WS-Enumeration, and WS-Eventing.</span></span>

## <a name="ws-management-and-wmi"></a><span data-ttu-id="e26b8-115">WS-Management und WMI</span><span class="sxs-lookup"><span data-stu-id="e26b8-115">WS-Management and WMI</span></span>

<span data-ttu-id="e26b8-116">WS-Management können zum Abrufen von Daten verwendet werden, die von Windows-Verwaltungsinstrumentation (WMI) verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="e26b8-116">WS-Management can be used to retrieve data exposed by Windows Management Instrumentation (WMI).</span></span> <span data-ttu-id="e26b8-117">Sie können WMI-Daten mit Skripts oder Anwendungen abrufen, die die WS-Management-Skript-API oder über das WinRM-Befehlszeilen Tool verwenden.</span><span class="sxs-lookup"><span data-stu-id="e26b8-117">You can obtain WMI data with scripts or applications that use the WS-Management Scripting API or through the WinRM command-line tool.</span></span> <span data-ttu-id="e26b8-118">WS-Management unterstützt den größten Teil der vertrauten WMI-Klassen und-Vorgänge, einschließlich eingebetteter Objekte.</span><span class="sxs-lookup"><span data-stu-id="e26b8-118">WS-Management supports most of the familiar WMI classes and operations, including embedded objects.</span></span> <span data-ttu-id="e26b8-119">WS-Management können WMI zum Sammeln von Daten zu Ressourcen oder zum Verwalten von Ressourcen auf Windows-basierten Computern nutzen.</span><span class="sxs-lookup"><span data-stu-id="e26b8-119">WS-Management can leverage WMI to collect data about resources or to manage resources on a Windows-based computers.</span></span> <span data-ttu-id="e26b8-120">Dies bedeutet, dass Sie Daten über Objekte wie Datenträger, Netzwerkadapter, Dienste oder Prozesse in Ihrem Unternehmen über den vorhandenen Satz von WMI-Klassen abrufen können.</span><span class="sxs-lookup"><span data-stu-id="e26b8-120">That means that you can obtain data about objects such as disks, network adapters, services, or processes in your enterprise through the existing set of WMI classes.</span></span> <span data-ttu-id="e26b8-121">Sie können auch auf die Hardware Daten zugreifen, die über den standardmäßigen WMI-IPMI-Anbieter verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="e26b8-121">You can also access the hardware data that is available from the standard WMI IPMI provider.</span></span>

## <a name="ws-management-windows-powershell-provider-wsman"></a><span data-ttu-id="e26b8-122">WS-Management Windows PowerShell-Anbieter (WSMAN)</span><span class="sxs-lookup"><span data-stu-id="e26b8-122">WS-Management Windows PowerShell Provider (WSMan)</span></span>

<span data-ttu-id="e26b8-123">Der WSMAN-Anbieter bietet eine hierarchische Ansicht der verfügbaren WS-Management Konfigurationseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="e26b8-123">The WSMan provider provides a hierarchical view into the available WS-Management configuration settings.</span></span> <span data-ttu-id="e26b8-124">Mit dem Anbieter können Sie die verschiedenen Optionen für die WS-Management Konfiguration untersuchen und festlegen.</span><span class="sxs-lookup"><span data-stu-id="e26b8-124">The provider allows you to explore and set the various WS-Management configuration options.</span></span>

## <a name="ws-management-configuration"></a><span data-ttu-id="e26b8-125">WS-Management Konfiguration</span><span class="sxs-lookup"><span data-stu-id="e26b8-125">WS-Management Configuration</span></span>

<span data-ttu-id="e26b8-126">Wenn WS-Management nicht installiert und konfiguriert ist, ist Windows PowerShell-Remoting nicht verfügbar, die WS-Management-Cmdlets werden nicht ausgeführt, WS-Management Skripts werden nicht ausgeführt, und der WSMAN-Anbieter kann keine Daten Vorgänge ausführen.</span><span class="sxs-lookup"><span data-stu-id="e26b8-126">If WS-Management is not installed and configured, Windows PowerShell remoting is not available, the WS-Management cmdlets do not run, WS-Management scripts do not run, and the WSMan provider cannot perform data operations.</span></span> <span data-ttu-id="e26b8-127">Das WS-Management Befehlszeilen Tool, WinRM und die Ereignis Weiterleitung sind auch von der WS-Management Konfiguration abhängig.</span><span class="sxs-lookup"><span data-stu-id="e26b8-127">The WS-Management command-line tool, WinRM, and event forwarding also depend on the WS-Management configuration.</span></span>

## <a name="ws-management-cmdlets"></a><span data-ttu-id="e26b8-128">WS-Management-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="e26b8-128">WS-Management Cmdlets</span></span>

<span data-ttu-id="e26b8-129">WS-Management Funktionalität wird in Windows PowerShell durch ein Modul implementiert, das einen Satz von Cmdlets und den WSMAN-Anbieter enthält.</span><span class="sxs-lookup"><span data-stu-id="e26b8-129">WS-Management functionality is implemented in Windows PowerShell through a module that contains a set of cmdlets and the WSMan provider.</span></span> <span data-ttu-id="e26b8-130">Sie können diese Cmdlets verwenden, um die End-to-End-Aufgaben abzuschließen, die zum Verwalten von WS-Management Einstellungen auf lokalen Computern und Remote Computern erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="e26b8-130">You can use these cmdlets to complete the end-to-end tasks necessary to manage WS-Management settings on local and remote computers.</span></span>

<span data-ttu-id="e26b8-131">Die folgenden WS-Management-Cmdlets sind verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e26b8-131">The following WS-Management cmdlets are available.</span></span>

## <a name="connection-cmdlets"></a><span data-ttu-id="e26b8-132">Cmdlets für die Verbindung</span><span class="sxs-lookup"><span data-stu-id="e26b8-132">Connection Cmdlets</span></span>

- <span data-ttu-id="e26b8-133">Connect-WSMAN: verbindet den lokalen Computer mit dem WS-Management-Dienst (WinRM) auf einem Remote Computer.</span><span class="sxs-lookup"><span data-stu-id="e26b8-133">Connect-WSMan: Connects the local computer to the WS-Management (WinRM) service on a remote computer.</span></span>

- <span data-ttu-id="e26b8-134">Disconnect-WSMAN: trennt die Verbindung zwischen dem lokalen Computer und dem WS-Management-Dienst (WinRM) auf einem Remote Computer.</span><span class="sxs-lookup"><span data-stu-id="e26b8-134">Disconnect-WSMan: Disconnects the local computer from the WS-Management (WinRM) service on a remote computer.</span></span>

## <a name="management-data-cmdlets"></a><span data-ttu-id="e26b8-135">Management-Data-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="e26b8-135">Management-Data Cmdlets</span></span>

- <span data-ttu-id="e26b8-136">Get-wsmaninstance: zeigt Verwaltungsinformationen für eine Ressourcen Instanz an, die durch einen Ressourcen-URI angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="e26b8-136">Get-WSManInstance: Displays management information for a resource instance that is specified by a resource URI.</span></span>

- <span data-ttu-id="e26b8-137">Aufruf-wsmanaction: Ruft eine Aktion für das Zielobjekt auf, das durch den Ressourcen-URI und die Selektoren angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="e26b8-137">Invoke-WSManAction: Invokes an action on the target object that is specified by the resource URI and by the selectors.</span></span>

- <span data-ttu-id="e26b8-138">New-wsmaninstance: erstellt eine neue Instanz der Verwaltungs Ressource.</span><span class="sxs-lookup"><span data-stu-id="e26b8-138">New-WSManInstance: Creates a new management resource instance.</span></span>

- <span data-ttu-id="e26b8-139">Remove-wsmaninstance: Löscht eine Verwaltungsressourcen Instanz.</span><span class="sxs-lookup"><span data-stu-id="e26b8-139">Remove-WSManInstance: Deletes a management resource instance.</span></span>

- <span data-ttu-id="e26b8-140">Set-wsmaninstance: ändert die Verwaltungsinformationen, die mit einer Ressource verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="e26b8-140">Set-WSManInstance: Modifies the management information that is related to a resource.</span></span>

## <a name="setup-and-configuration-cmdlets"></a><span data-ttu-id="e26b8-141">Setup-und Konfigurations-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="e26b8-141">Setup and Configuration Cmdlets</span></span>

- <span data-ttu-id="e26b8-142">Set-wsmanquickconfig: konfiguriert den lokalen Computer für die Remote Verwaltung.</span><span class="sxs-lookup"><span data-stu-id="e26b8-142">Set-WSManQuickConfig: Configures the local computer for remote management.</span></span>
  <span data-ttu-id="e26b8-143">Sie können das Cmdlet "Set-WSManQuickConfig" verwenden, um WS-Management so zu konfigurieren, dass Remote Verbindungen mit dem WS-Management (WinRM)-Dienst zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="e26b8-143">You can use the Set-WSManQuickConfig cmdlet to configure WS-Management to allow remote connections to the WS-Management (WinRM) service.</span></span> <span data-ttu-id="e26b8-144">Das Set-WSManQuickConfig-Cmdlet führt die folgenden Vorgänge aus:</span><span class="sxs-lookup"><span data-stu-id="e26b8-144">The Set-WSManQuickConfig cmdlet performs the following operations:</span></span>
  - <span data-ttu-id="e26b8-145">Es bestimmt, ob der WS-Management (WinRM)-Dienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e26b8-145">It determines whether the WS-Management (WinRM) service is running.</span></span> <span data-ttu-id="e26b8-146">Wenn der WinRM-Dienst nicht ausgeführt wird, startet das Cmdlet "Set-WSManQuickConfig" den Dienst.</span><span class="sxs-lookup"><span data-stu-id="e26b8-146">If the WinRM service is not running, the Set-WSManQuickConfig cmdlet starts the service.</span></span>
  - <span data-ttu-id="e26b8-147">Der WS-Management (WinRM)-Dienst Starttyp wird auf automatisch festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e26b8-147">It sets the WS-Management (WinRM) service startup type to automatic.</span></span>
  - <span data-ttu-id="e26b8-148">Er erstellt einen Listener, der Anforderungen von einer beliebigen IP-Adresse annimmt.</span><span class="sxs-lookup"><span data-stu-id="e26b8-148">It creates a listener that accepts requests from any IP address.</span></span> <span data-ttu-id="e26b8-149">Das Standard Transportprotokoll ist "http".</span><span class="sxs-lookup"><span data-stu-id="e26b8-149">The default transport protocol is HTTP.</span></span>
  - <span data-ttu-id="e26b8-150">Dies ermöglicht eine Firewallausnahme für WS-Management-Datenverkehr.</span><span class="sxs-lookup"><span data-stu-id="e26b8-150">It enables a firewall exception for WS-Management traffic.</span></span>

  <span data-ttu-id="e26b8-151">Hinweis: Wenn Sie dieses Cmdlet unter Windows Vista, Windows Server 2008 und neueren Versionen von Windows ausführen möchten, müssen Sie Windows PowerShell mit der Option "als Administrator ausführen" starten.</span><span class="sxs-lookup"><span data-stu-id="e26b8-151">Note: To run this cmdlet in Windows Vista, Windows Server 2008, and later versions of Windows, you must start Windows PowerShell with the "Run as administrator" option.</span></span>

- <span data-ttu-id="e26b8-152">Test-WSMAN: überprüft, ob WS-Management installiert und konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="e26b8-152">Test-WSMan: Verifies that WS-Management is installed and configured.</span></span> <span data-ttu-id="e26b8-153">Das Test-WSMan-Cmdlet testet, ob der WS-Management (WinRM)-Dienst auf einem lokalen oder Remote Computer ausgeführt wird und konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="e26b8-153">The Test-WSMan cmdlet tests whether the WS-Management (WinRM) service is running and configured on a local or remote computer.</span></span>

- <span data-ttu-id="e26b8-154">Deaktivieren-wsmankredssp: deaktiviert die dedssp-Authentifizierung auf einem Client Computer.</span><span class="sxs-lookup"><span data-stu-id="e26b8-154">Disable-WSManCredSSP: Disables CredSSP authentication on a client computer.</span></span>

- <span data-ttu-id="e26b8-155">Enable-wsmankredssp: aktiviert die fordssp-Authentifizierung auf einem Client Computer.</span><span class="sxs-lookup"><span data-stu-id="e26b8-155">Enable-WSManCredSSP: Enables CredSSP authentication on a client computer.</span></span>

- <span data-ttu-id="e26b8-156">Get-wsmankredssp: Ruft die auf dem Client computerbezogene Konfiguration für den Client Computer ab.</span><span class="sxs-lookup"><span data-stu-id="e26b8-156">Get-WSManCredSSP: Gets the CredSSP-related configuration for a client computer.</span></span>

## <a name="ws-management-specific-cmdlets"></a><span data-ttu-id="e26b8-157">WS-Management-spezifische Cmdlets</span><span class="sxs-lookup"><span data-stu-id="e26b8-157">WS-Management-Specific Cmdlets</span></span>

- <span data-ttu-id="e26b8-158">New-wsmansessionoption: erstellt ein wsmansessionoption-Objekt, das als Eingabe für einen oder mehrere Parameter eines WS-Management-Cmdlets verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e26b8-158">New-WSManSessionOption: Creates a WSManSessionOption object to use as input to one or more parameters of a WS-Management cmdlet.</span></span>

## <a name="additional-ws-management-information"></a><span data-ttu-id="e26b8-159">Zusätzliche WS-Management Informationen</span><span class="sxs-lookup"><span data-stu-id="e26b8-159">Additional WS-Management Information</span></span>

<span data-ttu-id="e26b8-160">Weitere Informationen zur WS-Verwaltung finden Sie in den folgenden Themen in der Windows-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="e26b8-160">For more information about WS-Management, see the following topics in the Windows documentation.</span></span>

[<span data-ttu-id="e26b8-161">Windows-Remoteverwaltung</span><span class="sxs-lookup"><span data-stu-id="e26b8-161">Windows Remote Management</span></span>](/windows/win32/winrm/portal)

[<span data-ttu-id="e26b8-162">Informationen zu Windows-Remoteverwaltung</span><span class="sxs-lookup"><span data-stu-id="e26b8-162">About Windows Remote Management</span></span>](/windows/win32/winrm/about-windows-remote-management)

[<span data-ttu-id="e26b8-163">Installation und Konfiguration für Windows-Remoteverwaltung</span><span class="sxs-lookup"><span data-stu-id="e26b8-163">Installation and Configuration for Windows Remote Management</span></span>](/windows/win32/winrm/installation-and-configuration-for-windows-remote-management)

[<span data-ttu-id="e26b8-164">Windows-Remoteverwaltung-Architektur</span><span class="sxs-lookup"><span data-stu-id="e26b8-164">Windows Remote Management Architecture</span></span>](/windows/win32/winrm/windows-remote-management-architecture)

[<span data-ttu-id="e26b8-165">WS-Verwaltungsprotokoll</span><span class="sxs-lookup"><span data-stu-id="e26b8-165">WS-Management Protocol</span></span>](/windows/win32/winrm/ws-management-protocol)

[<span data-ttu-id="e26b8-166">Windows-Remoteverwaltung und WMI</span><span class="sxs-lookup"><span data-stu-id="e26b8-166">Windows Remote Management and WMI</span></span>](/windows/win32/winrm/windows-remote-management-and-wmi)

[<span data-ttu-id="e26b8-167">Ressourcen-URIs</span><span class="sxs-lookup"><span data-stu-id="e26b8-167">Resource URIs</span></span>](/windows/win32/winrm/resource-uris)

[<span data-ttu-id="e26b8-168">Remote Hardware Verwaltung</span><span class="sxs-lookup"><span data-stu-id="e26b8-168">Remote Hardware Management</span></span>](/windows/win32/winrm/remote-hardware-management)

[<span data-ttu-id="e26b8-169">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="e26b8-169">Events</span></span>](/windows/win32/winrm/events)

## <a name="see-also"></a><span data-ttu-id="e26b8-170">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="e26b8-170">SEE ALSO</span></span>

[<span data-ttu-id="e26b8-171">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="e26b8-171">Connect-WSMan</span></span>](xref:Microsoft.WSMan.Management.Connect-WSMan)

[<span data-ttu-id="e26b8-172">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="e26b8-172">Disable-WSManCredSSP</span></span>](xref:Microsoft.WSMan.Management.Disable-WSManCredSSP)

[<span data-ttu-id="e26b8-173">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="e26b8-173">Disconnect-WSMan</span></span>](xref:Microsoft.WSMan.Management.Disconnect-WSMan)

[<span data-ttu-id="e26b8-174">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="e26b8-174">Enable-WSManCredSSP</span></span>](xref:Microsoft.WSMan.Management.Enable-WSManCredSSP)

[<span data-ttu-id="e26b8-175">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="e26b8-175">Get-WSManCredSSP</span></span>](xref:Microsoft.WSMan.Management.Get-WSManCredSSP)

[<span data-ttu-id="e26b8-176">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="e26b8-176">Get-WSManInstance</span></span>](xref:Microsoft.WSMan.Management.Get-WSManInstance)

[<span data-ttu-id="e26b8-177">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="e26b8-177">Invoke-WSManAction</span></span>](xref:Microsoft.WSMan.Management.Invoke-WSManAction)

[<span data-ttu-id="e26b8-178">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="e26b8-178">New-WSManInstance</span></span>](xref:Microsoft.WSMan.Management.New-WSManInstance)

[<span data-ttu-id="e26b8-179">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="e26b8-179">Remove-WSManInstance</span></span>](xref:Microsoft.WSMan.Management.Remove-WSManInstance)

[<span data-ttu-id="e26b8-180">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="e26b8-180">Set-WSManInstance</span></span>](xref:Microsoft.WSMan.Management.Set-WSManInstance)

[<span data-ttu-id="e26b8-181">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="e26b8-181">Set-WSManQuickConfig</span></span>](xref:Microsoft.WSMan.Management.Set-WSManQuickConfig)

[<span data-ttu-id="e26b8-182">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="e26b8-182">Test-WSMan</span></span>](xref:Microsoft.WSMan.Management.Test-WSMan)
