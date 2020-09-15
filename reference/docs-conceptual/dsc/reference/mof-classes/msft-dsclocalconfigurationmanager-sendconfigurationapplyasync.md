---
ms.date: 07/17/2020
keywords: DSC,PowerShell,Konfiguration,Setup,Einrichtung
title: SendConfigurationApplyAsync-Methode
ms.openlocfilehash: 4cfac5edb5fed94ee69deb98d7aa6be56b51c5b3
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/18/2020
ms.locfileid: "86463736"
---
# <a name="sendconfigurationapplyasync-method"></a><span data-ttu-id="51727-103">SendConfigurationApplyAsync-Methode</span><span class="sxs-lookup"><span data-stu-id="51727-103">SendConfigurationApplyAsync method</span></span>

<span data-ttu-id="51727-104">Sendet das Konfigurationsdokument asynchron an den verwalteten Knoten und verwendet den Konfigurations-Agent, um die Konfiguration anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="51727-104">Sends the configuration document asynchronously to the managed node and uses the Configuration Agent to apply the configuration.</span></span>

## <a name="syntax"></a><span data-ttu-id="51727-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="51727-105">Syntax</span></span>

```mof
uint32 SendConfigurationApplyAsync(
  [in] uint8   ConfigurationData[],
  [in] boolean force,
  [in] string  jobId
);
```

## <a name="parameters"></a><span data-ttu-id="51727-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="51727-106">Parameters</span></span>

<span data-ttu-id="51727-107">**ConfigurationData** \[in\] Die Umgebungsdaten für die Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="51727-107">**ConfigurationData** \[in\] The environment data for the configuration.</span></span>

<span data-ttu-id="51727-108">**force** \[in\] **true**, um das Beenden der Konfiguration zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="51727-108">**force** \[in\] **true** to force the configuration to stop.</span></span>

<span data-ttu-id="51727-109">**jobId** \[in\] Die ID des Auftrags, für den die Konfiguration gesendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="51727-109">**jobId** \[in\] The ID of the job for which to send the configuration.</span></span>

## <a name="return-value"></a><span data-ttu-id="51727-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="51727-110">Return value</span></span>

<span data-ttu-id="51727-111">Gibt bei Erfolg null zurück, andernfalls einen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="51727-111">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="51727-112">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="51727-112">Remarks</span></span>

<span data-ttu-id="51727-113">Dies ist eine statische Methode.</span><span class="sxs-lookup"><span data-stu-id="51727-113">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="51727-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="51727-114">Requirements</span></span>

<span data-ttu-id="51727-115">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="51727-115">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="51727-116">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="51727-116">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="51727-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="51727-117">See also</span></span>

[<span data-ttu-id="51727-118">**MSFT_DSCLocalConfigurationManager-Klasse**</span><span class="sxs-lookup"><span data-stu-id="51727-118">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
