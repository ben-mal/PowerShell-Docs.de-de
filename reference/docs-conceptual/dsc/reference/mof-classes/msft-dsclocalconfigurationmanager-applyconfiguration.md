---
ms.date: 07/14/2020
ms.topic: reference
title: ApplyConfiguration-Methode
description: ApplyConfiguration-Methode
ms.openlocfilehash: aa99221b33d39c3ecc70156a11eaee10b540e2dc
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92664282"
---
# <a name="applyconfiguration-method"></a><span data-ttu-id="6264c-103">ApplyConfiguration-Methode</span><span class="sxs-lookup"><span data-stu-id="6264c-103">ApplyConfiguration method</span></span>

<span data-ttu-id="6264c-104">Verwendet den Konfigurations-Agent, um die ausstehende Konfiguration anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="6264c-104">Uses the Configuration Agent to apply the configuration that is pending.</span></span>

<span data-ttu-id="6264c-105">Wenn keine ausstehende Konfiguration vorhanden ist, wendet diese Methode die aktuelle Konfiguration erneut an.</span><span class="sxs-lookup"><span data-stu-id="6264c-105">If there is no configuration pending, this method reapplies the current configuration.</span></span>

## <a name="syntax"></a><span data-ttu-id="6264c-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="6264c-106">Syntax</span></span>

```mof
uint32 ApplyConfiguration(
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="6264c-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="6264c-107">Parameters</span></span>

### <a name="force"></a><span data-ttu-id="6264c-108">force</span><span class="sxs-lookup"><span data-stu-id="6264c-108">force</span></span>

<span data-ttu-id="6264c-109">Wenn dies **true** ist, wird die aktuelle Konfiguration erneut angewendet, auch wenn eine Konfiguration aussteht.</span><span class="sxs-lookup"><span data-stu-id="6264c-109">If this is **true** , the current configuration is reapplied, even if there is a configuration pending.</span></span>

## <a name="return-value"></a><span data-ttu-id="6264c-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6264c-110">Return value</span></span>

<span data-ttu-id="6264c-111">Gibt bei Erfolg null zurück, andernfalls einen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="6264c-111">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="6264c-112">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="6264c-112">Remarks</span></span>

<span data-ttu-id="6264c-113">Dies ist eine statische Methode.</span><span class="sxs-lookup"><span data-stu-id="6264c-113">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="6264c-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="6264c-114">Requirements</span></span>

<span data-ttu-id="6264c-115">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="6264c-115">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="6264c-116">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="6264c-116">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="6264c-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6264c-117">See also</span></span>

[<span data-ttu-id="6264c-118">**MSFT_DSCLocalConfigurationManager-Klasse**</span><span class="sxs-lookup"><span data-stu-id="6264c-118">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
