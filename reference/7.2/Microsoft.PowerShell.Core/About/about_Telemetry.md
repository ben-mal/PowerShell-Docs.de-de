---
description: Beschreibt die Telemetriedaten, die in PowerShell gesammelt werden, und wie Sie sich abmelden.
Locale: en-US
ms.date: 08/09/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_telemetry?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Telemetry
ms.openlocfilehash: 677d43b405fdc92e6b68d6e903847b11cb671a2c
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600499"
---
# <a name="about-telemetry"></a><span data-ttu-id="f2d7d-103">Informationen zu Telemetrie</span><span class="sxs-lookup"><span data-stu-id="f2d7d-103">About Telemetry</span></span>

## <a name="short-description"></a><span data-ttu-id="f2d7d-104">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f2d7d-104">SHORT DESCRIPTION</span></span>

<span data-ttu-id="f2d7d-105">Beschreibt die Telemetriedaten, die in PowerShell gesammelt werden, und wie Sie sich abmelden.</span><span class="sxs-lookup"><span data-stu-id="f2d7d-105">Describes the telemetry collected in PowerShell and how to opt-out.</span></span>

## <a name="long-description"></a><span data-ttu-id="f2d7d-106">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f2d7d-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="f2d7d-107">PowerShell sendet grundlegende Telemetriedaten an Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f2d7d-107">PowerShell sends basic telemetry data to Microsoft.</span></span>
<span data-ttu-id="f2d7d-108">Dadurch wird erkennbar, in welchen Umgebungen PowerShell verwendet wird und welche neuen Funktionen und Problembehebungen Vorrang haben sollten.</span><span class="sxs-lookup"><span data-stu-id="f2d7d-108">This data allows us to better understand the environments where PowerShell is used and enables us to prioritize new features and fixes.</span></span>
<span data-ttu-id="f2d7d-109">Die folgenden telemetriepunkte werden aufgezeichnet:</span><span class="sxs-lookup"><span data-stu-id="f2d7d-109">The following telemetry points are recorded:</span></span>

- <span data-ttu-id="f2d7d-110">Anzahl der PowerShell-Starts nach Typ (API-vs-Konsole)</span><span class="sxs-lookup"><span data-stu-id="f2d7d-110">Count of PowerShell Starts by type (API vs console)</span></span>
- <span data-ttu-id="f2d7d-111">Anzahl der eindeutigen PowerShell-Nutzung</span><span class="sxs-lookup"><span data-stu-id="f2d7d-111">Count of unique PowerShell usage</span></span>
- <span data-ttu-id="f2d7d-112">Anzahl der folgenden Ausführungs Typen:</span><span class="sxs-lookup"><span data-stu-id="f2d7d-112">Count of the following execution types:</span></span>
  - <span data-ttu-id="f2d7d-113">Anwendung (Native Befehle)</span><span class="sxs-lookup"><span data-stu-id="f2d7d-113">Application (native commands)</span></span>
  - <span data-ttu-id="f2d7d-114">Externalscript</span><span class="sxs-lookup"><span data-stu-id="f2d7d-114">ExternalScript</span></span>
  - <span data-ttu-id="f2d7d-115">Skript</span><span class="sxs-lookup"><span data-stu-id="f2d7d-115">Script</span></span>
  - <span data-ttu-id="f2d7d-116">Funktion</span><span class="sxs-lookup"><span data-stu-id="f2d7d-116">Function</span></span>
  - <span data-ttu-id="f2d7d-117">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="f2d7d-117">Cmdlet</span></span>
- <span data-ttu-id="f2d7d-118">Anzahl der aktivierten experimentellen Features von Microsoft oder experimentelle Features, die mit PowerShell ausgeliefert werden</span><span class="sxs-lookup"><span data-stu-id="f2d7d-118">Count of enabled Microsoft owned experimental features or experimental features shipped with PowerShell</span></span>
- <span data-ttu-id="f2d7d-119">Anzahl gehosteter Sitzungen</span><span class="sxs-lookup"><span data-stu-id="f2d7d-119">Count of hosted sessions</span></span>
- <span data-ttu-id="f2d7d-120">Anzahl der geladenen Module im Besitz von Microsoft</span><span class="sxs-lookup"><span data-stu-id="f2d7d-120">Count of Microsoft owned modules loaded</span></span>

<span data-ttu-id="f2d7d-121">Diese Daten umfassen den Betriebssystem Namen, die Betriebssystemversion, die PowerShell-Version und den Verteilungs Kanal.</span><span class="sxs-lookup"><span data-stu-id="f2d7d-121">This data includes the OS name, OS version, the PowerShell version, and the distribution channel.</span></span>

<span data-ttu-id="f2d7d-122">Um diese Telemetrie zu abonnieren, legen Sie die Umgebungsvariable POWERSHELL_TELEMETRY_OPTOUT auf true, ja oder 1 fest.</span><span class="sxs-lookup"><span data-stu-id="f2d7d-122">To opt-out of this telemetry, set the environment variable POWERSHELL_TELEMETRY_OPTOUT to true, yes, or 1.</span></span>

