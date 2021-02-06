---
description: Benachrichtigt Benutzer beim Starten von PowerShell, dass eine neue Version von PowerShell veröffentlicht wurde.
Locale: en-US
ms.date: 01/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_update_notifications?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Update_Notifications
ms.openlocfilehash: 1a9f8cfec15f83566fdb77175dcc1aed6d9e8c34
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596966"
---
# <a name="about-update-notifications"></a><span data-ttu-id="9152e-103">Informationen zu Update Benachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="9152e-103">About Update Notifications</span></span>

## <a name="short-description"></a><span data-ttu-id="9152e-104">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9152e-104">SHORT DESCRIPTION</span></span>

<span data-ttu-id="9152e-105">Benachrichtigt Benutzer beim Starten von PowerShell, dass eine neue Version von PowerShell veröffentlicht wurde.</span><span class="sxs-lookup"><span data-stu-id="9152e-105">Notifies users on startup of PowerShell that a new version of PowerShell has been released.</span></span>

## <a name="long-description"></a><span data-ttu-id="9152e-106">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9152e-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="9152e-107">Ab PowerShell 7,0 verwendet PowerShell Update Benachrichtigungen, um Benutzer darauf aufmerksam zu machen, dass Updates für PowerShell vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="9152e-107">Beginning with PowerShell 7.0, PowerShell uses update notifications to alert users to the existence of updates to PowerShell.</span></span> <span data-ttu-id="9152e-108">Einmal pro Tag fragt PowerShell einen Onlinedienst ab, um zu prüfen, ob eine neuere Version verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="9152e-108">Once per day, PowerShell queries an online service to determine if a newer version is available.</span></span>

> [!NOTE]
> <span data-ttu-id="9152e-109">Während die Update Überprüfung während der ersten Sitzung innerhalb eines Zeitraums von 24 Stunden durchgeführt wird, wird die Benachrichtigung aus Leistungsgründen nur zu Beginn der nachfolgenden Sitzungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9152e-109">While the update check happens during the first session in a given 24-hour period, for performance reasons, the notification will only be shown on the start of subsequent sessions.</span></span> <span data-ttu-id="9152e-110">Aus Leistungsgründen wird die Überprüfung auch erst nach mindestens 3 Sekunden nach Beginn der Sitzung gestartet.</span><span class="sxs-lookup"><span data-stu-id="9152e-110">Also for performance reasons, the check will not start until at least 3 seconds after the session begins.</span></span>

<span data-ttu-id="9152e-111">Standardmäßig abonniert PowerShell je nach Version/Branch einen von zwei verschiedenen Benachrichtigungskanälen.</span><span class="sxs-lookup"><span data-stu-id="9152e-111">By default, PowerShell subscribes to one of two different notification channels depending on its version/branch.</span></span> <span data-ttu-id="9152e-112">Unterstützte, allgemein verfügbare (GA-) Versionen von PowerShell geben nur für aktualisierte GA-Releases Benachrichtigungen zurück.</span><span class="sxs-lookup"><span data-stu-id="9152e-112">Supported, Generally Available (GA) versions of PowerShell only return notifications for updated GA releases.</span></span> <span data-ttu-id="9152e-113">Vorschau- und Release Candidate-Releases (RC) benachrichtigen über Updates für Vorschau-, RC- und GA-Releases.</span><span class="sxs-lookup"><span data-stu-id="9152e-113">Preview and Release Candidate (RC) releases notify of updates to preview, RC, and GA releases.</span></span>

<span data-ttu-id="9152e-114">Das Verhalten der Updatebenachrichtigung kann mithilfe der Umgebungsvariablen `POWERSHELL_UPDATECHECK` geändert werden.</span><span class="sxs-lookup"><span data-stu-id="9152e-114">The update notification behavior can be changed using the `POWERSHELL_UPDATECHECK` environment variable.</span></span> <span data-ttu-id="9152e-115">Die folgenden Werte werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="9152e-115">The following values are supported:</span></span>

- <span data-ttu-id="9152e-116">`Off` deaktiviert das Aktualisierungs Benachrichtigungs Feature.</span><span class="sxs-lookup"><span data-stu-id="9152e-116">`Off` turns off the update notification feature</span></span>
- <span data-ttu-id="9152e-117">`Default` entspricht nicht der Definition `POWERSHELL_UPDATECHECK` :</span><span class="sxs-lookup"><span data-stu-id="9152e-117">`Default` is the same as not defining `POWERSHELL_UPDATECHECK`:</span></span>
  - <span data-ttu-id="9152e-118">GA-Releases benachrichtigen zu Updates von GA-Releases.</span><span class="sxs-lookup"><span data-stu-id="9152e-118">GA releases notify of updates to GA releases</span></span>
  - <span data-ttu-id="9152e-119">Vorschau-/RC-Releases benachrichtigen zu Updates von GA- und Vorschau-Releases.</span><span class="sxs-lookup"><span data-stu-id="9152e-119">Preview/RC releases notify of updates to GA and preview releases</span></span>
- <span data-ttu-id="9152e-120">`LTS` benachrichtigt nur Updates für LTS-GA-Releases (Long-Term-Wartung).</span><span class="sxs-lookup"><span data-stu-id="9152e-120">`LTS` only notifies of updates to long-term-servicing (LTS) GA releases</span></span>

<span data-ttu-id="9152e-121">Die folgenden Endpunkte werden derzeit verwendet, um die neueste Version der einzelnen Kanäle zu ermitteln:</span><span class="sxs-lookup"><span data-stu-id="9152e-121">The following endpoints are currently used for determining the latest version of each channel:</span></span>

- <span data-ttu-id="9152e-122">`LTS`: https://aka.ms/pwsh-buildinfo-lts</span><span class="sxs-lookup"><span data-stu-id="9152e-122">`LTS`: https://aka.ms/pwsh-buildinfo-lts</span></span>
- <span data-ttu-id="9152e-123">`Stable`: https://aka.ms/pwsh-buildinfo-stable</span><span class="sxs-lookup"><span data-stu-id="9152e-123">`Stable`: https://aka.ms/pwsh-buildinfo-stable</span></span>
- <span data-ttu-id="9152e-124">`Preview`: https://aka.ms/pwsh-buildinfo-preview</span><span class="sxs-lookup"><span data-stu-id="9152e-124">`Preview`: https://aka.ms/pwsh-buildinfo-preview</span></span>

<span data-ttu-id="9152e-125">Die Update Benachrichtigung bietet keine Möglichkeit, PowerShell automatisch zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="9152e-125">The update notification doesn't provide any way to automatically update PowerShell.</span></span> <span data-ttu-id="9152e-126">In Zukunft gibt es möglicherweise weitere Anweisungen oder Funktionen, die Sie in PowerShell aktualisieren können. Sie sollten aber heute denselben Installationsmechanismus verwenden, den Sie zum Aktualisieren von PowerShell zum Aktualisieren verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="9152e-126">In the future, there may be more instructions or capabilities to update from within PowerShell, but today, you should use the same install mechanism you used to install PowerShell to update it.</span></span>

