---
ms.date: 06/12/2017
title: Entfernen von Paketen aus der Liste
description: Der PowerShell-Katalog unterstützt nicht das endgültige Löschen von Paketen durch Benutzer. So können andere Benutzer Abhängigkeiten von Ihren Paketen festlegen, ohne darauf zu achten, ob diese in Zukunft verfügbar sind.
ms.openlocfilehash: 738167011f64b5174df3504c8e1d06146f4c7db5
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92662415"
---
# <a name="unlisting-packages"></a><span data-ttu-id="3ce56-104">Entfernen von Paketen aus der Liste</span><span class="sxs-lookup"><span data-stu-id="3ce56-104">Unlisting Packages</span></span>

<span data-ttu-id="3ce56-105">**Weshalb wird keine Option zum Entfernen von Paketen aus dem PowerShell-Katalog angezeigt?**</span><span class="sxs-lookup"><span data-stu-id="3ce56-105">**Why is removing a package from PowerShell Gallery not exposed as an option?**</span></span>

<span data-ttu-id="3ce56-106">Der PowerShell-Katalog unterstützt nicht das endgültige Löschen von Paketen durch Benutzer.</span><span class="sxs-lookup"><span data-stu-id="3ce56-106">The PowerShell Gallery does not support users permanently deleting their packages.</span></span> <span data-ttu-id="3ce56-107">So können andere Benutzer Abhängigkeiten von Ihren Paketen festlegen, ohne darauf zu achten, ob diese in Zukunft verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="3ce56-107">This enables others to take dependencies on your packages without worrying about possible breaks in the future.</span></span>
<span data-ttu-id="3ce56-108">Wenn das Pester-Modul z. B. vom Azure-Modul abhängig ist und das Azure-Modul aus dem Katalog entfernt wird, können Benutzer das Pester-Modul nicht mehr verwenden.</span><span class="sxs-lookup"><span data-stu-id="3ce56-108">For example, if the Pester module depends on the Azure module and the Azure module is removed from the gallery, then users can no longer use the Pester module.</span></span>

<span data-ttu-id="3ce56-109">Anstatt ein Paket zu entfernen, können Sie die Auflistung aufheben.</span><span class="sxs-lookup"><span data-stu-id="3ce56-109">Instead of removing a package you can unlist it.</span></span>

<span data-ttu-id="3ce56-110">**Was geschieht, wenn ein Paket aus der Liste im PowerShell-Katalog entfernt wird?**</span><span class="sxs-lookup"><span data-stu-id="3ce56-110">**What does unlisting a package on PowerShell Gallery do?**</span></span>

<span data-ttu-id="3ce56-111">Wenn ein Paket, z. B. ein Modul oder ein Skript, aus der Liste im PowerShell-Katalog entfernt wird, wird es nicht länger auf der Registerkarte „Pakete“ angezeigt. Außerdem werden aus der Liste entfernte Pakete nicht mehr über die Suchleiste gefunden.</span><span class="sxs-lookup"><span data-stu-id="3ce56-111">Unlisting a package such as a module or script in the PowerShell Gallery removes it from the Packages tab. In addition, unlisted packages will not be discoverable using the search bar.</span></span> <span data-ttu-id="3ce56-112">Pakete, die aus der Liste entfernt wurden, können nur bei Angabe des genauen Namens und der Version des Pakets herunterladen werden.</span><span class="sxs-lookup"><span data-stu-id="3ce56-112">The only way to download an unlisted package is to specify the exact name and version of the package.</span></span> <span data-ttu-id="3ce56-113">Folglich treten infolge des Entfernens eines Pakets aus der Liste keine Probleme bei Modulen oder Skripts auf, die von diesem Paket abhängen.</span><span class="sxs-lookup"><span data-stu-id="3ce56-113">Because of this, the unlisting of a package will not break other modules or scripts that depend on it.</span></span>

<span data-ttu-id="3ce56-114">Um Ihr Paket aus der Liste zu entfernen, rufen Sie die Seite „Paketdetails“ auf, und wählen Sie „Modul löschen“ aus.</span><span class="sxs-lookup"><span data-stu-id="3ce56-114">To unlist your package, visit the package details page and select 'Delete Module'.</span></span> <span data-ttu-id="3ce56-115">Deaktivieren Sie das Kontrollkästchen „Aufgelistet“, und wählen Sie „Speichern“ aus.</span><span class="sxs-lookup"><span data-stu-id="3ce56-115">Uncheck the 'Listed' checkbox, and select 'Save'.</span></span>

<span data-ttu-id="3ce56-116">**Wie kann ich ein Paket entfernen?**</span><span class="sxs-lookup"><span data-stu-id="3ce56-116">**How can I remove a package?**</span></span>

<span data-ttu-id="3ce56-117">Wenn ein Paket gelöscht werden muss, wenden Sie sich an die PowerShell-Katalogadministratoren.</span><span class="sxs-lookup"><span data-stu-id="3ce56-117">If you experience a scenario where package deletion is necessary, contact the PowerShell Gallery Administrators.</span></span> <span data-ttu-id="3ce56-118">In folgenden Fällen ist das Löschen eines Elements zulässig:</span><span class="sxs-lookup"><span data-stu-id="3ce56-118">Valid deletion scenarios are:</span></span>

- <span data-ttu-id="3ce56-119">Probleme aufgrund von Urheberrechtsverletzungen.</span><span class="sxs-lookup"><span data-stu-id="3ce56-119">Issues of copyright infringement.</span></span>
- <span data-ttu-id="3ce56-120">Das Paket enthält potenziell schädlichen Inhalt.</span><span class="sxs-lookup"><span data-stu-id="3ce56-120">Package contains potentially harmful content.</span></span>
- <span data-ttu-id="3ce56-121">Das Paket enthält sensible Daten.</span><span class="sxs-lookup"><span data-stu-id="3ce56-121">Package contains sensitive data.</span></span>

<span data-ttu-id="3ce56-122">Um eine Anforderung zum Löschen eines Pakets an die PowerShell-Katalogadministratoren zu senden, wählen Sie auf der Seite „Paketdetails“ die Option „Support kontaktieren“ aus.</span><span class="sxs-lookup"><span data-stu-id="3ce56-122">To submit a Delete Package Request to the PowerShell Gallery Administrators, visit your package's detail page and select Contact Support.</span></span>
