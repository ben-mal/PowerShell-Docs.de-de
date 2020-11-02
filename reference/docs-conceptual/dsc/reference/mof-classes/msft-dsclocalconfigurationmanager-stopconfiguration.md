---
ms.date: 07/17/2020
ms.topic: reference
title: StopConfiguration-Methode
description: StopConfiguration-Methode
ms.openlocfilehash: 854c0dbe8554c08413735a5a7bc872776e0b0a6c
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92644624"
---
# <a name="stopconfiguration-method"></a><span data-ttu-id="32fb7-103">StopConfiguration-Methode</span><span class="sxs-lookup"><span data-stu-id="32fb7-103">StopConfiguration method</span></span>

<span data-ttu-id="32fb7-104">Beende die Konfigurationsänderung, die gerade ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="32fb7-104">Stops the configuration change that is in progress.</span></span>

## <a name="syntax"></a><span data-ttu-id="32fb7-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="32fb7-105">Syntax</span></span>

```mof
uint32 StopConfiguration(
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="32fb7-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="32fb7-106">Parameters</span></span>

<span data-ttu-id="32fb7-107">**force** \[in\] **true** , um das Beenden der Konfiguration zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="32fb7-107">**force** \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="32fb7-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="32fb7-108">Return value</span></span>

<span data-ttu-id="32fb7-109">Gibt bei Erfolg null zurück, andernfalls einen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="32fb7-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="32fb7-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="32fb7-110">Remarks</span></span>

<span data-ttu-id="32fb7-111">Dies ist eine statische Methode.</span><span class="sxs-lookup"><span data-stu-id="32fb7-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="32fb7-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="32fb7-112">Requirements</span></span>

<span data-ttu-id="32fb7-113">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="32fb7-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="32fb7-114">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="32fb7-114">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="32fb7-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="32fb7-115">See also</span></span>

[<span data-ttu-id="32fb7-116">**MSFT_DSCLocalConfigurationManager-Klasse**</span><span class="sxs-lookup"><span data-stu-id="32fb7-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
