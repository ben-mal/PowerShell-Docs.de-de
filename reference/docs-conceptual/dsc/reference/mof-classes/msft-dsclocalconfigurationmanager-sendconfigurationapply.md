---
ms.date: 07/17/2020
keywords: DSC,PowerShell,Konfiguration,Setup,Einrichtung
title: SendConfigurationApply-Methode
ms.openlocfilehash: 9b684790e5a7d6c7bdf074caca6040e13807f1ca
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464314"
---
# <a name="sendconfigurationapply-method"></a><span data-ttu-id="ee6f3-103">SendConfigurationApply-Methode</span><span class="sxs-lookup"><span data-stu-id="ee6f3-103">SendConfigurationApply method</span></span>

<span data-ttu-id="ee6f3-104">Sendet das Konfigurationsdokument an den verwalteten Knoten und verwendet den Konfigurations-Agent zum Anwenden der Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="ee6f3-104">Sends the configuration document to the managed node and uses the Configuration Agent to apply the configuration.</span></span>

## <a name="syntax"></a><span data-ttu-id="ee6f3-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="ee6f3-105">Syntax</span></span>

```mof
uint32 SendConfigurationApply(
  [in] uint8   ConfigurationData[],
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="ee6f3-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="ee6f3-106">Parameters</span></span>

<span data-ttu-id="ee6f3-107">**ConfigurationData** \[in\] Die Umgebungsdaten für die Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="ee6f3-107">**ConfigurationData** \[in\] The environment data for the configuration.</span></span>

<span data-ttu-id="ee6f3-108">**force** \[in\] **true**, um das Beenden der Konfiguration zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="ee6f3-108">**force** \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="ee6f3-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ee6f3-109">Return value</span></span>

<span data-ttu-id="ee6f3-110">Gibt bei Erfolg null zurück, andernfalls einen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="ee6f3-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="ee6f3-111">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ee6f3-111">Remarks</span></span>

<span data-ttu-id="ee6f3-112">Dies ist eine statische Methode.</span><span class="sxs-lookup"><span data-stu-id="ee6f3-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="ee6f3-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ee6f3-113">Requirements</span></span>

<span data-ttu-id="ee6f3-114">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="ee6f3-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="ee6f3-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="ee6f3-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="ee6f3-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ee6f3-116">See also</span></span>

[<span data-ttu-id="ee6f3-117">**MSFT_DSCLocalConfigurationManager-Klasse**</span><span class="sxs-lookup"><span data-stu-id="ee6f3-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
