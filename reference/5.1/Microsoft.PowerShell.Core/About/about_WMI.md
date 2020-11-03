---
description: Windows-Verwaltungsinstrumentation (WMI) verwendet die Common Information Model (CIM) zur Darstellung von Systemen, Anwendungen, Netzwerken, Geräten und anderen verwaltbaren Komponenten des modernen Unternehmens.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_wmi?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_WMI
ms.openlocfilehash: d24b952ee167e51815d6d9920e95bbc9a6bb9608
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223207"
---
# <a name="about-wmi"></a><span data-ttu-id="783d7-104">Informationen zu WMI</span><span class="sxs-lookup"><span data-stu-id="783d7-104">About WMI</span></span>

## <a name="short-description"></a><span data-ttu-id="783d7-105">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="783d7-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="783d7-106">Windows-Verwaltungsinstrumentation (WMI) verwendet die Common Information Model (CIM) zur Darstellung von Systemen, Anwendungen, Netzwerken, Geräten und anderen verwaltbaren Komponenten des modernen Unternehmens.</span><span class="sxs-lookup"><span data-stu-id="783d7-106">Windows Management Instrumentation (WMI) uses the Common Information Model (CIM) to represent systems, applications, networks, devices, and other manageable components of the modern enterprise.</span></span>

## <a name="long-description"></a><span data-ttu-id="783d7-107">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="783d7-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="783d7-108">Windows-Verwaltungsinstrumentation (WMI) ist die Microsoft-Implementierung von Web-Based Enterprise Management (WBEM), dem Industriestandard.</span><span class="sxs-lookup"><span data-stu-id="783d7-108">Windows Management Instrumentation (WMI) is Microsoft's implementation of Web-Based Enterprise Management (WBEM), the industry standard.</span></span>

<span data-ttu-id="783d7-109">Klassisches WMI verwendet DCOM für die Kommunikation mit vernetzten Geräten, um Remote Systeme zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="783d7-109">Classic WMI uses DCOM to communicate with networked devices to manage remote systems.</span></span> <span data-ttu-id="783d7-110">Windows PowerShell 3,0 führt ein CIM-Anbieter Modell ein, das WinRM verwendet, um die Abhängigkeit von DCOM zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="783d7-110">Windows PowerShell 3.0 introduces a CIM provider model that uses WinRM to remove the dependency on DCOM.</span></span> <span data-ttu-id="783d7-111">Dieses CIM-Anbieter Modell verwendet auch neue WMI-Anbieter-APIs, mit denen Entwickler Windows PowerShell-Cmdlets in nativem Code (C) schreiben können \+ \+ .</span><span class="sxs-lookup"><span data-stu-id="783d7-111">This CIM provider model also uses new WMI provider APIs that enable developers to write Windows PowerShell cmdlets in native code (C\+\+).</span></span>

<span data-ttu-id="783d7-112">Verwechseln Sie WMI-Anbieter nicht mit Windows PowerShell-Anbietern.</span><span class="sxs-lookup"><span data-stu-id="783d7-112">Do not confuse WMI providers with Windows PowerShell providers.</span></span> <span data-ttu-id="783d7-113">Viele Windows-Features verfügen über einen zugeordneten WMI-Anbieter, der Ihre Verwaltungsfunktionen verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="783d7-113">Many Windows features have an associated WMI provider that exposes their management capabilities.</span></span> <span data-ttu-id="783d7-114">Zum Abrufen von WMI-Anbietern führen Sie eine WMI-Abfrage aus, mit der Instanzen der WMI-Klasse __Provider abgerufen werden, z. b. die folgende Abfrage.</span><span class="sxs-lookup"><span data-stu-id="783d7-114">To get WMI providers, run a WMI query that gets instances of the __Provider WMI class, such as the following query.</span></span>

```powershell
Get-WmiObject -Class __Provider
```

## <a name="three-components-of-wmi"></a><span data-ttu-id="783d7-115">drei WMI-Komponenten</span><span class="sxs-lookup"><span data-stu-id="783d7-115">THREE COMPONENTS OF WMI</span></span>

<span data-ttu-id="783d7-116">Die folgenden drei Komponenten von WMI interagieren mit Windows PowerShell: Namespaces, Anbieter und Klassen.</span><span class="sxs-lookup"><span data-stu-id="783d7-116">The following three components of WMI interact with Windows PowerShell: Namespaces, Providers, and Classes.</span></span>

<span data-ttu-id="783d7-117">WMI-Namespaces organisieren WMI-Anbieter und WMI-Klassen in Gruppen verwandter Komponenten.</span><span class="sxs-lookup"><span data-stu-id="783d7-117">WMI Namespaces organize WMI providers and WMI classes into groups of related components.</span></span> <span data-ttu-id="783d7-118">Auf diese Weise ähneln sie .NET Framework Namespaces.</span><span class="sxs-lookup"><span data-stu-id="783d7-118">In this way, they are similar to .NET Framework namespaces.</span></span>
<span data-ttu-id="783d7-119">Namespaces sind keine physischen Speicherorte, sondern eher wie logische Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="783d7-119">Namespaces are not physical locations, but are more like logical databases.</span></span>
<span data-ttu-id="783d7-120">Alle WMI-Namespaces sind Instanzen der __Namespace System Klasse.</span><span class="sxs-lookup"><span data-stu-id="783d7-120">All WMI namespaces are instances of the __Namespace system class.</span></span> <span data-ttu-id="783d7-121">Der standardmäßige WMI-Namespace ist root \/ CIMV2 (seit Microsoft Windows 2000).</span><span class="sxs-lookup"><span data-stu-id="783d7-121">The default WMI namespace is Root\/CIMV2 (since Microsoft Windows 2000).</span></span> <span data-ttu-id="783d7-122">Wenn Sie Windows PowerShell zum Verwenden von WMI-Namespaces in der aktuellen Sitzung verwenden möchten, verwenden Sie einen Befehl mit dem folgenden Format.</span><span class="sxs-lookup"><span data-stu-id="783d7-122">To use Windows PowerShell to get WMI namespaces in the current session, use a command with the following format.</span></span>

```powershell
Get-WmiObject -Class __Namespace
```

<span data-ttu-id="783d7-123">Um WMI-Namespaces in anderen Namespaces zu erhalten, verwenden Sie den Namespace-Parameter, um den Speicherort der Suche zu ändern.</span><span class="sxs-lookup"><span data-stu-id="783d7-123">To get WMI namespaces in other namespaces, use the Namespace parameter to change the location of the search.</span></span> <span data-ttu-id="783d7-124">Der folgende Befehl sucht nach WMI-Namespaces, die sich im Root/Cimv2/Applications-Namespace befinden.</span><span class="sxs-lookup"><span data-stu-id="783d7-124">The following command finds WMI namespaces that reside in the Root/Cimv2/Applications namespace.</span></span>

```powershell
Get-WmiObject -Class __Namespace -Namespace root/CIMv2/applications
```

<span data-ttu-id="783d7-125">WMI-Namespaces sind hierarchisch.</span><span class="sxs-lookup"><span data-stu-id="783d7-125">WMI namespaces are hierarchical.</span></span> <span data-ttu-id="783d7-126">Daher muss beim Abrufen einer Liste aller Namespaces auf einem bestimmten System eine rekursive Abfrage gestartet werden, die mit dem Stamm Namespace beginnt.</span><span class="sxs-lookup"><span data-stu-id="783d7-126">Therefore, obtaining a list of all namespaces on a particular system requires performing a recursive query starting at the root namespace.</span></span>

<span data-ttu-id="783d7-127">WMI-Anbieter machen Informationen zu überschaubaren Windows-Objekten verfügbar.</span><span class="sxs-lookup"><span data-stu-id="783d7-127">WMI Providers expose information about Windows manageable objects.</span></span> <span data-ttu-id="783d7-128">Ein Anbieter ruft Daten von einer-Komponente ab und übergibt diese Daten über WMI an eine Verwaltungs Anwendung, wie z. b. Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="783d7-128">A provider retrieves data from a component, and passes that data through WMI to a management application, such as Windows PowerShell.</span></span> <span data-ttu-id="783d7-129">Die meisten WMI-Anbieter sind dynamische Anbieter. Dies bedeutet, dass Sie die Daten dynamisch abrufen, wenn Sie über die Verwaltungs Anwendung angefordert werden.</span><span class="sxs-lookup"><span data-stu-id="783d7-129">Most WMI providers are dynamic providers, which means that they obtain the data dynamically when it is requested through the management application.</span></span>

## <a name="finding-wmi-classes"></a><span data-ttu-id="783d7-130">Suchen von WMI-Klassen</span><span class="sxs-lookup"><span data-stu-id="783d7-130">FINDING WMI CLASSES</span></span>

<span data-ttu-id="783d7-131">In einer Standardinstallation von Windows 8 sind mehr als 1.100 WMI-Klassen in root \/ Cimv2 vorhanden.</span><span class="sxs-lookup"><span data-stu-id="783d7-131">In a default installation of Windows 8, there are more than 1,100 WMI classes in Root\/Cimv2.</span></span> <span data-ttu-id="783d7-132">Mit diesen vielen WMI-Klassen identifiziert die Herausforderung die geeignete WMI-Klasse, die zum Ausführen einer bestimmten Aufgabe verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="783d7-132">With this many WMI classes, the challenge becomes identifying the appropriate WMI class to use to perform a specific task.</span></span> <span data-ttu-id="783d7-133">Windows PowerShell 3,0 bietet zwei Möglichkeiten, um WMI-Klassen zu finden, die mit einem bestimmten Thema verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="783d7-133">Windows PowerShell 3.0 provides two ways to find WMI classes that are related to a specific topic.</span></span>

<span data-ttu-id="783d7-134">Wenn Sie z. b. WMI-Klassen im Stamm-CIMV2-WMI-Namespace im Zusammenhang mit Datenträgern suchen möchten \\ , können Sie eine Abfrage wie die hier gezeigte verwenden.</span><span class="sxs-lookup"><span data-stu-id="783d7-134">For example,to find WMI classes in the root\\CIMV2 WMI namespace that are related to disks, you can use a query such as the one shown here.</span></span>

```powershell
Get-WmiObject -List *disk*
```

<span data-ttu-id="783d7-135">Zum Ermitteln von WMI-Klassen, die sich auf den Arbeitsspeicher beziehen, können Sie eine Abfrage wie die hier gezeigte verwenden.</span><span class="sxs-lookup"><span data-stu-id="783d7-135">To find WMI classes that are related to memory, you might use a query such as the one shown here.</span></span>

```powershell
Get-WmiObject -List *memory*
```

<span data-ttu-id="783d7-136">Die CIM-Cmdlets bieten außerdem die Möglichkeit, WMI-Klassen zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="783d7-136">The CIM cmdlets also provide the ability to discover WMI classes.</span></span> <span data-ttu-id="783d7-137">Verwenden Sie hierzu das Cmdlet "Get-CIMClass".</span><span class="sxs-lookup"><span data-stu-id="783d7-137">To do this, use the Get-CIMClass cmdlet.</span></span> <span data-ttu-id="783d7-138">Der hier gezeigte Befehl listet WMI-Klassen auf, die mit Video verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="783d7-138">The command shown here lists WMI classes related to video.</span></span>

```powershell
Get-CimClass *video*
```

<span data-ttu-id="783d7-139">Die Tabulator Erweiterung funktioniert bei der Änderung von WMI-Namespaces. Daher sind untergeordnete WMI-Namespaces durch die Verwendung der Tabulator Erweiterung leicht erkennbar.</span><span class="sxs-lookup"><span data-stu-id="783d7-139">Tab expansion works when changing WMI namespaces, and therefore use of tab expansion makes sub-WMI namespaces easily discoverable.</span></span> <span data-ttu-id="783d7-140">Im folgenden Beispiel werden mit dem Cmdlet "Get-CimClass" WMI-Klassen aufgelistet, die mit den Energie Einstellungen verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="783d7-140">In the following example, the Get-CimClass cmdlet lists WMI classes related to power settings.</span></span>
<span data-ttu-id="783d7-141">Um es zu suchen, geben Sie den `root/CIMV2/` -Namespace ein, und drücken Sie dann mehrmals die Tab-Taste, bis der Power-Namespace angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="783d7-141">To find it, type the `root/CIMV2/` namespace and then press the Tab key several times until the power namespace appears.</span></span> <span data-ttu-id="783d7-142">Hier ist der Befehl:</span><span class="sxs-lookup"><span data-stu-id="783d7-142">Here is the command:</span></span>

```powershell
Get-CimClass *power* -Namespace root/cimv2/power
```
