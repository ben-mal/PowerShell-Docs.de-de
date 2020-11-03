---
description: Enthält Hintergrundinformationen über die Windows-Verwaltungsinstrumentation (Windows Management Instrumentation, WMI) und Windows PowerShell.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 12/01/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_wmi_cmdlets?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_WMI_Cmdlets
ms.openlocfilehash: c2099c005cedf64e9621d66d6757419320c9b43e
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223191"
---
# <a name="about-wmi-cmdlets"></a><span data-ttu-id="9f4ac-104">Informationen zu WMI-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="9f4ac-104">About WMI Cmdlets</span></span>

## <a name="short-description"></a><span data-ttu-id="9f4ac-105">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9f4ac-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="9f4ac-106">Enthält Hintergrundinformationen über die Windows-Verwaltungsinstrumentation (Windows Management Instrumentation, WMI) und Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-106">Provides background information about Windows Management Instrumentation (WMI) and Windows PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="9f4ac-107">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9f4ac-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="9f4ac-108">Dieses Thema enthält Informationen zur WMI-Technologie, den WMI-Cmdlets für Windows PowerShell, WMI-basiertes Remoting, WMI-Accelerators und WMI-Problembehandlung.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-108">This topic provides information about WMI technology, the WMI cmdlets for Windows PowerShell, WMI-based remoting, WMI accelerators, and WMI troubleshooting.</span></span> <span data-ttu-id="9f4ac-109">Außerdem enthält dieses Thema Links zu weiteren Informationen über WMI.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-109">This topic also provides links to more information about WMI.</span></span>

### <a name="about-wmi"></a><span data-ttu-id="9f4ac-110">Informationen zu WMI</span><span class="sxs-lookup"><span data-stu-id="9f4ac-110">ABOUT WMI</span></span>

<span data-ttu-id="9f4ac-111">Die Windows-Verwaltungsinstrumentation (Windows Management Instrumentation, WMI) ist die Microsoft-Implementierung von WBEM (Web-Based Enterprise Management). Hierbei handelt es sich um eine Brancheninitiative zum Entwickeln einer Standardtechnologie für den Zugriff auf Verwaltungsinformationen in einer Unternehmensumgebung.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-111">Windows Management Instrumentation (WMI) is the Microsoft implementation of Web-Based Enterprise Management (WBEM), which is an industry initiative to develop a standard technology for accessing management information in an enterprise environment.</span></span> <span data-ttu-id="9f4ac-112">WMI verwendet den Branchenstandard %%amp;quot;Common Information Model (CIM)%%amp;quot; zum Darstellen von Systemen, Anwendungen, Netzwerken, Geräten und anderen verwalteten Komponenten.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-112">WMI uses the Common Information Model (CIM) industry standard to represent systems, applications, networks, devices, and other managed components.</span></span> <span data-ttu-id="9f4ac-113">CIM wird von der Distributed Management Task Force (DMTF) entwickelt und verwaltet.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-113">CIM is developed and maintained by the Distributed Management Task Force (DMTF).</span></span> <span data-ttu-id="9f4ac-114">Sie können WMI verwenden, um sowohl lokale als auch Remote Computer zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-114">You can use WMI to manage both local and remote computers.</span></span> <span data-ttu-id="9f4ac-115">Beispielsweise können Sie mit WMI folgende Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="9f4ac-115">For example, you can use WMI to do the following:</span></span>

- <span data-ttu-id="9f4ac-116">Starten Sie einen Prozess auf einem Remote Computer.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-116">Start a process on a remote computer.</span></span>
- <span data-ttu-id="9f4ac-117">Starten Sie einen Computer remote neu.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-117">Restart a computer remotely.</span></span>
- <span data-ttu-id="9f4ac-118">Sie erhalten eine Liste der Anwendungen, die auf einem lokalen Computer oder einem Remote Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-118">Get a list of the applications that are installed on a local or remote computer.</span></span>
- <span data-ttu-id="9f4ac-119">Abfragen der Windows-Ereignisprotokolle auf einem lokalen Computer oder einem Remote Computer.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-119">Query the Windows event logs on a local or remote computer.</span></span>

### <a name="the-wmi-cmdlets-for-windows-powershell"></a><span data-ttu-id="9f4ac-120">die WMI-Cmdlets für Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9f4ac-120">THE WMI CMDLETS FOR WINDOWS POWERSHELL</span></span>

<span data-ttu-id="9f4ac-121">Windows PowerShell implementiert WMI-Funktionen über eine Reihe von Cmdlets, die standardmäßig in Windows PowerShell verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-121">Windows PowerShell implements WMI functionality through a set of cmdlets that are available in Windows PowerShell by default.</span></span> <span data-ttu-id="9f4ac-122">Sie können diese Cmdlets verwenden, um die End-to-End-Aufgaben abzuschließen, die zum Verwalten von lokalen Computern und Remote Computern erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-122">You can use these cmdlets to complete the end-to-end tasks necessary to manage local and remote computers.</span></span>

<span data-ttu-id="9f4ac-123">Die folgenden WMI-Cmdlets sind enthalten.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-123">The following WMI cmdlets are included.</span></span>

|<span data-ttu-id="9f4ac-124">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="9f4ac-124">Cmdlet</span></span>           |<span data-ttu-id="9f4ac-125">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9f4ac-125">Description</span></span>                                   |
|-----------------|----------------------------------------------|
|<span data-ttu-id="9f4ac-126">Get-WmiObject</span><span class="sxs-lookup"><span data-stu-id="9f4ac-126">Get-WmiObject</span></span>    |<span data-ttu-id="9f4ac-127">Ruft Instanzen von WMI-Klassen oder-Informationen ab.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-127">Gets instances of WMI classes or information</span></span>  |
|                 |<span data-ttu-id="9f4ac-128">Informationen zu den verfügbaren Klassen.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-128">about the available classes.</span></span>                  |
|<span data-ttu-id="9f4ac-129">Invoke-WmiMethod</span><span class="sxs-lookup"><span data-stu-id="9f4ac-129">Invoke-WmiMethod</span></span> |<span data-ttu-id="9f4ac-130">Ruft WMI-Methoden auf.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-130">Calls WMI methods.</span></span>                            |
|<span data-ttu-id="9f4ac-131">Register-WmiEvent</span><span class="sxs-lookup"><span data-stu-id="9f4ac-131">Register-WmiEvent</span></span>|<span data-ttu-id="9f4ac-132">Abonniert ein WMI-Ereignis.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-132">Subscribes to a WMI event.</span></span>                    |
|<span data-ttu-id="9f4ac-133">Remove-WmiObject</span><span class="sxs-lookup"><span data-stu-id="9f4ac-133">Remove-WmiObject</span></span> |<span data-ttu-id="9f4ac-134">Löscht WMI-Klassen und -Instanzen.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-134">Deletes WMI classes and instances.</span></span>            |
|<span data-ttu-id="9f4ac-135">Set-WmiInstance</span><span class="sxs-lookup"><span data-stu-id="9f4ac-135">Set-WmiInstance</span></span>  |<span data-ttu-id="9f4ac-136">Erstellt oder ändert Instanzen von WMI-Klassen.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-136">Creates or modifies instances of WMI classes.</span></span> |

### <a name="sample-commands"></a><span data-ttu-id="9f4ac-137">Beispiel Befehle</span><span class="sxs-lookup"><span data-stu-id="9f4ac-137">SAMPLE COMMANDS</span></span>
<span data-ttu-id="9f4ac-138">Mit dem folgenden Befehl werden die BIOS-Informationen für den lokalen Computer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-138">The following command displays the BIOS information for the local computer.</span></span>

```powershell
C:\PS> get-wmiobject win32_bios | format-list *
```

<span data-ttu-id="9f4ac-139">Mit dem folgenden Befehl werden Informationen zum WinRM-Dienst für drei Remote Computer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-139">The following command displays information about the WinRM service for three remote computers.</span></span>

```powershell
$wql = "select * from win32_service where name='WinRM'"
get-wmiobject -query $wql -computername server01, server01, server03
```

<span data-ttu-id="9f4ac-140">Mit dem folgenden komplexeren Befehl werden alle Instanzen eines Programms beendet.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-140">The following more complex command exits all instances of a program.</span></span>

```powershell
C:\PS> notepad.exe
C:\PS> $wql = "select * from win32_process where name='notepad.exe'"
C:\PS> $np = get-wmiobject -query $wql
C:\PS> $np | remove-wmiobject
```

### <a name="wmi-based-remoting"></a><span data-ttu-id="9f4ac-141">WMI-basiertes Remoting</span><span class="sxs-lookup"><span data-stu-id="9f4ac-141">WMI-BASED REMOTING</span></span>

<span data-ttu-id="9f4ac-142">Obwohl die Möglichkeit zur Verwaltung eines lokalen Systems über WMI nützlich ist, sind dies die Remoting-Funktionen, die WMI zu einem leistungsfähigen Verwaltungs Tool machen.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-142">While the ability to manage a local system through WMI is useful, it is the remoting capabilities that make WMI a powerful administrative tool.</span></span> <span data-ttu-id="9f4ac-143">WMI verwendet das verteilte Component Object Model (DCOM) von Microsoft, um eine Verbindung mit Systemen herzustellen und diese zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-143">WMI uses Microsoft's Distributed Component Object Model (DCOM) to connect to and manage systems.</span></span> <span data-ttu-id="9f4ac-144">Möglicherweise müssen Sie einige Systeme so konfigurieren, dass DCOM-Verbindungen zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-144">You might have to configure some systems to allow DCOM connections.</span></span>
<span data-ttu-id="9f4ac-145">Firewalleinstellungen und gesperrte DCOM-Berechtigungen können die Fähigkeit von WMI blockieren, Systeme Remote zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-145">Firewall settings and locked-down DCOM permissions can block WMI's ability to remotely manage systems.</span></span>

### <a name="wmi-type-accelerators"></a><span data-ttu-id="9f4ac-146">WMI-typacceleratoren</span><span class="sxs-lookup"><span data-stu-id="9f4ac-146">WMI TYPE ACCELERATORS</span></span>

<span data-ttu-id="9f4ac-147">Windows PowerShell enthält WMI-typaccelerators.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-147">Windows PowerShell includes WMI type accelerators.</span></span> <span data-ttu-id="9f4ac-148">Diese WMI-typaccelerators (Verknüpfungen) ermöglichen einen direkteren Zugriff auf WMI-Objekte, als es bei einem nicht-Typ-Accelerator-Ansatz möglich wäre.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-148">These WMI type accelerators (shortcuts) allow more direct access to a WMI objects than a non-type accelerator approach would allow.</span></span>

<span data-ttu-id="9f4ac-149">Die folgenden typacceleratoren werden von WMI unterstützt:</span><span class="sxs-lookup"><span data-stu-id="9f4ac-149">The following type accelerators are supported with WMI:</span></span>

<span data-ttu-id="9f4ac-150">[Wmisearcher]: eine Verknüpfung für die Suche nach WMI-Objekten.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-150">[WMISEARCHER] - A shortcut for searching for WMI objects.</span></span>

<span data-ttu-id="9f4ac-151">[WMIClass]: eine Verknüpfung für den Zugriff auf die statischen Eigenschaften und Methoden einer Klasse.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-151">[WMICLASS] - A shortcut for accessing the static properties and methods of a class.</span></span>

<span data-ttu-id="9f4ac-152">[WMI]: eine Verknüpfung zum erhalten einer einzelnen Instanz einer Klasse.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-152">[WMI] - A shortcut for getting a single instance of a class.</span></span>

<span data-ttu-id="9f4ac-153">[Wmisearcher] ist eine typbeschleunigung für einen ManagementObjectSearcher.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-153">[WMISEARCHER] is a type accelerator for a ManagementObjectSearcher.</span></span> <span data-ttu-id="9f4ac-154">Es kann einen Zeichenfolgenkonstruktor verwenden, um einen Suchvorgang zu erstellen, für den Sie dann einen get ()-Vorgang ausführen können.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-154">It can take a string constructor to create a searcher that you can then do a GET() on.</span></span>

<span data-ttu-id="9f4ac-155">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9f4ac-155">For example:</span></span>

```powershell
PS> $s = [WmiSearcher]'Select * from Win32_Process where Handlecount > 1000'
PS> $s.Get() |sort handlecount |ft handlecount,__path,name -auto

count  __PATH                                              name
-----  ------                                              ----
1105   \\SERVER01\root\cimv2:Win32_Process.Handle="3724"   PowerShell...
1132   \\SERVER01\root\cimv2:Win32_Process.Handle="1388"   winlogon.exe
1495   \\SERVER01\root\cimv2:Win32_Process.Handle="2852"   iexplore.exe
1699   \\SERVER01\root\cimv2:Win32_Process.Handle="1204"   OUTLOOK.EXE
1719   \\SERVER01\root\cimv2:Win32_Process.Handle="1912"   iexplore.exe
2579   \\SERVER01\root\cimv2:Win32_Process.Handle="1768"   svchost.exe
```

<span data-ttu-id="9f4ac-156">[WMIClass] ist eine typbeschleunigung für ManagementClass.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-156">[WMICLASS] is a type accelerator for ManagementClass.</span></span> <span data-ttu-id="9f4ac-157">Dies hat einen Zeichenfolgenkonstruktor, der einen lokalen oder absoluten WMI-Pfad zu einer WMI-Klasse annimmt und ein Objekt zurückgibt, das an diese Klasse gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-157">This has a string constructor that takes a local or absolute WMI path to a WMI class and returns an object that is bound to that class.</span></span>

<span data-ttu-id="9f4ac-158">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9f4ac-158">For example:</span></span>

```powershell
PS> $c = [WMICLASS]"root\cimv2:WIn32_Process"
PS> $c |fl *
Name             : Win32_Process
__GENUS          : 1
__CLASS          : Win32_Process
__SUPERCLASS     : CIM_Process
__DYNASTY        : CIM_ManagedSystemElement
__RELPATH        : Win32_Process
__PROPERTY_COUNT : 45
__DERIVATION     : {CIM_Process, CIM_LogicalElement,
                   CIM_ManagedSystemElement}
__SERVER         : SERVER01
__NAMESPACE      : ROOT\cimv2
__PATH           : \\SERVER01\ROOT\cimv2:Win32_Process
```

<span data-ttu-id="9f4ac-159">[WMI] ist eine typbeschleunigung für ManagementObject.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-159">[WMI] is a type accelerator for ManagementObject.</span></span> <span data-ttu-id="9f4ac-160">Dies hat einen Zeichenfolgenkonstruktor, der einen lokalen oder absoluten WMI-Pfad zu einer WMI-Instanz annimmt und ein an diese Instanz gebundenes Objekt zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-160">This has a string constructor that takes a local or absolute WMI path to a WMI instance and returns an object that is bound to that instance.</span></span>

<span data-ttu-id="9f4ac-161">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9f4ac-161">For example:</span></span>

```powershell
PS> $p = [WMI]'\\SERVER01\root\cimv2:Win32_Process.Handle="1204"'
PS> $p.Name
OUTLOOK.EXE
```

### <a name="wmi-troubleshooting"></a><span data-ttu-id="9f4ac-162">WMI-Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="9f4ac-162">WMI TROUBLESHOOTING</span></span>

<span data-ttu-id="9f4ac-163">Die folgenden Probleme sind die häufigsten Probleme, die auftreten können, wenn Sie versuchen, eine Verbindung mit einem Remote Computer herzustellen.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-163">The following problems are the most common problems that might occur when you try to connect to a remote computer.</span></span>

<span data-ttu-id="9f4ac-164">Problem 1: der Remote Computer ist nicht online.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-164">Problem 1: The remote computer is not online.</span></span>

<span data-ttu-id="9f4ac-165">Wenn ein Computer offline ist, können Sie mithilfe von WMI keine Verbindung mit ihm herstellen.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-165">If a computer is offline, you will not be able to connect to it by using WMI.</span></span>
<span data-ttu-id="9f4ac-166">Sie erhalten ggf. eine Fehlermeldung der folgenden Art:</span><span class="sxs-lookup"><span data-stu-id="9f4ac-166">You may receive the following error message:</span></span>

```
Remote server machine does not exist or is unavailable
```

<span data-ttu-id="9f4ac-167">Wenn Sie diese Fehlermeldung erhalten, überprüfen Sie, ob der Computer online ist.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-167">If you receive this error message, verify that the computer is online.</span></span> <span data-ttu-id="9f4ac-168">Versuchen Sie, den Remote Computer zu pingen.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-168">Try to ping the remote computer.</span></span>

<span data-ttu-id="9f4ac-169">Problem 2: Sie verfügen nicht über lokale Administratorrechte auf dem Remote Computer.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-169">Problem 2: You do not have local administrator rights on the remote computer.</span></span>

<span data-ttu-id="9f4ac-170">Um WMI Remote verwenden zu können, müssen Sie über lokale Administratorrechte auf dem Remote Computer verfügen.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-170">To use WMI remotely, you must have local administrator rights on the remote computer.</span></span> <span data-ttu-id="9f4ac-171">Andernfalls wird der Zugriff auf diesen Computer verweigert.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-171">If you do not, access to that computer will be denied.</span></span>

<span data-ttu-id="9f4ac-172">So überprüfen Sie die Namespace Sicherheit:</span><span class="sxs-lookup"><span data-stu-id="9f4ac-172">To verify namespace security:</span></span>

1. <span data-ttu-id="9f4ac-173">Klicken Sie im Startmenü mit der rechten Maustaste auf Arbeitsplatz, und klicken Sie dann auf verwalten.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-173">Click Start, right-click My Computer, and then click Manage.</span></span>
2. <span data-ttu-id="9f4ac-174">Erweitern Sie in der Computer Verwaltung Dienste und Anwendungen, klicken Sie mit der rechten Maustaste auf WMI-Steuerung, und klicken Sie dann auf Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-174">In Computer Management, expand Services and Applications, right-click WMI Control, and then click Properties.</span></span>
3. <span data-ttu-id="9f4ac-175">Klicken Sie im Dialogfeld Eigenschaften von WMI-Steuerung auf die Registerkarte Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-175">In the WMI Control Properties dialog box, click  the Security tab.</span></span>

<span data-ttu-id="9f4ac-176">Problem 3: eine Firewall blockiert den Zugriff auf den Remote Computer.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-176">Problem 3: A firewall is blocking access to the remote computer.</span></span>

<span data-ttu-id="9f4ac-177">WMI verwendet die Protokolle DCOM (verteiltes com) und RPC (Remote Prozedur Aufruf), um das Netzwerk zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-177">WMI uses the DCOM (Distributed COM) and RPC (Remote Procedure Call) protocols to traverse the network.</span></span> <span data-ttu-id="9f4ac-178">Standardmäßig blockieren viele Firewalls DCOM-und RPC-Datenverkehr.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-178">By default, many firewalls block DCOM and RPC traffic.</span></span> <span data-ttu-id="9f4ac-179">Wenn die Firewall diese Protokolle blockiert, tritt bei der Verbindung ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-179">If your firewall is blocking these protocols, your connection will fail.</span></span> <span data-ttu-id="9f4ac-180">Beispielsweise ist die Windows-Firewall in Microsoft Windows XP Service Pack 2 so konfiguriert, dass der gesamte nicht angeforderte Netzwerk Datenverkehr, einschließlich DCOM und WMI, automatisch blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="9f4ac-180">For example, Windows Firewall in Microsoft Windows XP Service Pack 2 is configured to automatically block all unsolicited network traffic, including DCOM and WMI.</span></span> <span data-ttu-id="9f4ac-181">In der Standardkonfiguration lehnt die Windows-Firewall eine eingehende WMI-Anforderung ab, und Sie erhalten die folgende Fehlermeldung:</span><span class="sxs-lookup"><span data-stu-id="9f4ac-181">In its default configuration, Windows Firewall rejects an incoming WMI request, and you receive the following error message:</span></span>

```
Remote server machine does not exist or is unavailable
```

## <a name="see-also"></a><span data-ttu-id="9f4ac-182">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="9f4ac-182">SEE ALSO</span></span>

[<span data-ttu-id="9f4ac-183">Informationen zu WMI</span><span class="sxs-lookup"><span data-stu-id="9f4ac-183">About WMI</span></span>](/windows/win32/wmisdk/about-wmi)

[<span data-ttu-id="9f4ac-184">WMI-Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="9f4ac-184">WMI Troubleshooting</span></span>](/windows/win32/wmisdk/wmi-troubleshooting)

[<span data-ttu-id="9f4ac-185">Get-WmiObject</span><span class="sxs-lookup"><span data-stu-id="9f4ac-185">Get-WmiObject</span></span>](xref:Microsoft.PowerShell.Management.Get-WmiObject)

[<span data-ttu-id="9f4ac-186">Invoke-WmiMethod</span><span class="sxs-lookup"><span data-stu-id="9f4ac-186">Invoke-WmiMethod</span></span>](xref:Microsoft.PowerShell.Management.Invoke-WmiMethod)

[<span data-ttu-id="9f4ac-187">Register-WmiEvent</span><span class="sxs-lookup"><span data-stu-id="9f4ac-187">Register-WmiEvent</span></span>](xref:Microsoft.PowerShell.Management.Register-WmiEvent)

[<span data-ttu-id="9f4ac-188">Remove-WmiObject</span><span class="sxs-lookup"><span data-stu-id="9f4ac-188">Remove-WmiObject</span></span>](xref:Microsoft.PowerShell.Management.Remove-WmiObject)

[<span data-ttu-id="9f4ac-189">Set-WmiInstance</span><span class="sxs-lookup"><span data-stu-id="9f4ac-189">Set-WmiInstance</span></span>](xref:Microsoft.PowerShell.Management.Set-WmiInstance)
