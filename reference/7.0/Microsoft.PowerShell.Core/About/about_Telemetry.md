---
description: Beschreibt die Telemetriedaten, die in PowerShell gesammelt werden, und wie Sie sich abmelden.
keywords: powershell
Locale: en-US
ms.date: 08/09/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_telemetry?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Telemetry
ms.openlocfilehash: 4aeab828d66d1f015946051419facd81ce2b78c1
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93220532"
---
# <a name="about-telemetry"></a><span data-ttu-id="2ba96-104">Informationen zu Telemetrie</span><span class="sxs-lookup"><span data-stu-id="2ba96-104">About Telemetry</span></span>

## <a name="short-description"></a><span data-ttu-id="2ba96-105">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2ba96-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="2ba96-106">Beschreibt die Telemetriedaten, die in PowerShell gesammelt werden, und wie Sie sich abmelden.</span><span class="sxs-lookup"><span data-stu-id="2ba96-106">Describes the telemetry collected in PowerShell and how to opt-out.</span></span>

## <a name="long-description"></a><span data-ttu-id="2ba96-107">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2ba96-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="2ba96-108">PowerShell sendet grundlegende Telemetriedaten an Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2ba96-108">PowerShell sends basic telemetry data to Microsoft.</span></span>
<span data-ttu-id="2ba96-109">Dadurch wird erkennbar, in welchen Umgebungen PowerShell verwendet wird und welche neuen Funktionen und Problembehebungen Vorrang haben sollten.</span><span class="sxs-lookup"><span data-stu-id="2ba96-109">This data allows us to better understand the environments where PowerShell is used and enables us to prioritize new features and fixes.</span></span>
<span data-ttu-id="2ba96-110">Die folgenden telemetriepunkte werden aufgezeichnet:</span><span class="sxs-lookup"><span data-stu-id="2ba96-110">The following telemetry points are recorded:</span></span>

- <span data-ttu-id="2ba96-111">Anzahl der PowerShell-Starts nach Typ (API-vs-Konsole)</span><span class="sxs-lookup"><span data-stu-id="2ba96-111">Count of PowerShell Starts by type (API vs console)</span></span>
- <span data-ttu-id="2ba96-112">Anzahl der eindeutigen PowerShell-Nutzung</span><span class="sxs-lookup"><span data-stu-id="2ba96-112">Count of unique PowerShell usage</span></span>
- <span data-ttu-id="2ba96-113">Anzahl der folgenden Ausführungs Typen:</span><span class="sxs-lookup"><span data-stu-id="2ba96-113">Count of the following execution types:</span></span>
  - <span data-ttu-id="2ba96-114">Anwendung (Native Befehle)</span><span class="sxs-lookup"><span data-stu-id="2ba96-114">Application (native commands)</span></span>
  - <span data-ttu-id="2ba96-115">Externalscript</span><span class="sxs-lookup"><span data-stu-id="2ba96-115">ExternalScript</span></span>
  - <span data-ttu-id="2ba96-116">Skript</span><span class="sxs-lookup"><span data-stu-id="2ba96-116">Script</span></span>
  - <span data-ttu-id="2ba96-117">Funktion</span><span class="sxs-lookup"><span data-stu-id="2ba96-117">Function</span></span>
  - <span data-ttu-id="2ba96-118">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="2ba96-118">Cmdlet</span></span>
- <span data-ttu-id="2ba96-119">Anzahl der aktivierten experimentellen Features von Microsoft oder experimentelle Features, die mit PowerShell ausgeliefert werden</span><span class="sxs-lookup"><span data-stu-id="2ba96-119">Count of enabled Microsoft owned experimental features or experimental features shipped with PowerShell</span></span>
- <span data-ttu-id="2ba96-120">Anzahl gehosteter Sitzungen</span><span class="sxs-lookup"><span data-stu-id="2ba96-120">Count of hosted sessions</span></span>
- <span data-ttu-id="2ba96-121">Anzahl der geladenen Module im Besitz von Microsoft</span><span class="sxs-lookup"><span data-stu-id="2ba96-121">Count of Microsoft owned modules loaded</span></span>

<span data-ttu-id="2ba96-122">Diese Daten umfassen den Betriebssystem Namen, die Betriebssystemversion, die PowerShell-Version und den Verteilungs Kanal.</span><span class="sxs-lookup"><span data-stu-id="2ba96-122">This data includes the OS name, OS version, the PowerShell version, and the distribution channel.</span></span>

<span data-ttu-id="2ba96-123">Um diese Telemetrie zu abonnieren, legen Sie die Umgebungsvariable POWERSHELL_TELEMETRY_OPTOUT auf true, ja oder 1 fest.</span><span class="sxs-lookup"><span data-stu-id="2ba96-123">To opt-out of this telemetry, set the environment variable POWERSHELL_TELEMETRY_OPTOUT to true, yes, or 1.</span></span>
