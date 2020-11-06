---
ms.date: 06/12/2017
keywords: DSC,PowerShell,Konfiguration,Setup,Einrichtung
title: DSCAutomationHostEnabled (Registrierungsschlüssel)
description: In diesem Artikel werden die Werte definiert, die im Registrierungsschlüssel DSCAutomationHostEnabled festgelegt werden können.
ms.openlocfilehash: 50f752dd882e9b0787ed4a4cbc22731fc1d608f5
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92656180"
---
# <a name="dscautomationhostenabled-registry-key"></a><span data-ttu-id="12321-104">DSCAutomationHostEnabled (Registrierungsschlüssel)</span><span class="sxs-lookup"><span data-stu-id="12321-104">DSCAutomationHostEnabled registry key</span></span>

> <span data-ttu-id="12321-105">Gilt für: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="12321-105">Applies to: Windows PowerShell 5.0</span></span>

<span data-ttu-id="12321-106">DSC verwendet den Registrierungsschlüssel **DSCAutomationHostEnabled** unter **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System** , um die Konfiguration des Computer beim ersten Start zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="12321-106">DSC uses the **DSCAutomationHostEnabled** registry key under **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System** to enable configuration of the machine at initial boot-up.</span></span> <span data-ttu-id="12321-107">**DSCAutomationHostEnabled** unterstützt drei Modi:</span><span class="sxs-lookup"><span data-stu-id="12321-107">**DSCAutomationHostEnabled** supports three modes:</span></span>

| <span data-ttu-id="12321-108">DSCAutomationHostEnabled-Wert</span><span class="sxs-lookup"><span data-stu-id="12321-108">DSCAutomationHostEnabled Value</span></span> |                                              <span data-ttu-id="12321-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="12321-109">Description</span></span>                                              |
| ------------------------------ | ----------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="12321-110">0</span><span class="sxs-lookup"><span data-stu-id="12321-110">0</span></span>                              | <span data-ttu-id="12321-111">Konfiguration des Computers beim Hochfahren deaktivieren</span><span class="sxs-lookup"><span data-stu-id="12321-111">Disable configuring the machine at boot-up.</span></span>                                                           |
| <span data-ttu-id="12321-112">1</span><span class="sxs-lookup"><span data-stu-id="12321-112">1</span></span>                              | <span data-ttu-id="12321-113">Konfiguration des Computers beim Hochfahren aktivieren</span><span class="sxs-lookup"><span data-stu-id="12321-113">Enable configuring the machine at boot-up.</span></span>                                                            |
| <span data-ttu-id="12321-114">2</span><span class="sxs-lookup"><span data-stu-id="12321-114">2</span></span>                              | <span data-ttu-id="12321-115">Konfiguration des Computers nur dann aktivieren, wenn DSC sich im Status „ausstehend“ oder „aktuell“ befindet.</span><span class="sxs-lookup"><span data-stu-id="12321-115">Enable configuring the machine only if DSC is in pending or current state.</span></span> <span data-ttu-id="12321-116">Dies ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="12321-116">This is the default value.</span></span> |

## <a name="see-also"></a><span data-ttu-id="12321-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="12321-117">See Also</span></span>

<span data-ttu-id="12321-118">Ein Beispiel dazu, wie Sie dieses Features zum Ausführen von Konfigurationen beim ersten Hochfahren verwenden, finden Sie unter [Konfigurieren eines virtuellen Computers beim ersten Hochfahren mithilfe von DSC](bootstrapDsc.md).</span><span class="sxs-lookup"><span data-stu-id="12321-118">For an example of how to use this feature to run configurations at initial boot-up, see [Configure a virtual machines at initial boot-up by using DSC](bootstrapDsc.md).</span></span>
