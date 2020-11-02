---
ms.date: 07/17/2020
ms.topic: reference
title: SendConfigurationApplyAsync-Methode
description: SendConfigurationApplyAsync-Methode
ms.openlocfilehash: 92c9d03a7653e72b1ff04084caea4a8b5aadb0e5
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92644791"
---
# <a name="sendconfigurationapplyasync-method"></a><span data-ttu-id="40112-103">SendConfigurationApplyAsync-Methode</span><span class="sxs-lookup"><span data-stu-id="40112-103">SendConfigurationApplyAsync method</span></span>

<span data-ttu-id="40112-104">Sendet das Konfigurationsdokument asynchron an den verwalteten Knoten und verwendet den Konfigurations-Agent, um die Konfiguration anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="40112-104">Sends the configuration document asynchronously to the managed node and uses the Configuration Agent to apply the configuration.</span></span>

## <a name="syntax"></a><span data-ttu-id="40112-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="40112-105">Syntax</span></span>

```mof
uint32 SendConfigurationApplyAsync(
  [in] uint8   ConfigurationData[],
  [in] boolean force,
  [in] string  jobId
);
```

## <a name="parameters"></a><span data-ttu-id="40112-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="40112-106">Parameters</span></span>

<span data-ttu-id="40112-107">**ConfigurationData** \[in\] Die Umgebungsdaten für die Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="40112-107">**ConfigurationData** \[in\] The environment data for the configuration.</span></span>

<span data-ttu-id="40112-108">**force** \[in\] **true** , um das Beenden der Konfiguration zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="40112-108">**force** \[in\] **true** to force the configuration to stop.</span></span>

<span data-ttu-id="40112-109">**jobId** \[in\] Die ID des Auftrags, für den die Konfiguration gesendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="40112-109">**jobId** \[in\] The ID of the job for which to send the configuration.</span></span>

## <a name="return-value"></a><span data-ttu-id="40112-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="40112-110">Return value</span></span>

<span data-ttu-id="40112-111">Gibt bei Erfolg null zurück, andernfalls einen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="40112-111">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="40112-112">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="40112-112">Remarks</span></span>

<span data-ttu-id="40112-113">Dies ist eine statische Methode.</span><span class="sxs-lookup"><span data-stu-id="40112-113">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="40112-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="40112-114">Requirements</span></span>

<span data-ttu-id="40112-115">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="40112-115">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="40112-116">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="40112-116">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="40112-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="40112-117">See also</span></span>

[<span data-ttu-id="40112-118">**MSFT_DSCLocalConfigurationManager-Klasse**</span><span class="sxs-lookup"><span data-stu-id="40112-118">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
