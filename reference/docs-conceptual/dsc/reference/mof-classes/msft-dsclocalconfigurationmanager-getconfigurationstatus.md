---
ms.date: 07/17/2020
ms.topic: reference
title: GetConfigurationStatus-Methode
description: GetConfigurationStatus-Methode
ms.openlocfilehash: fe25d17069d9011e931ac50fec27cb9ebafba365
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92650859"
---
# <a name="getconfigurationstatus-method"></a><span data-ttu-id="043a9-103">GetConfigurationStatus-Methode</span><span class="sxs-lookup"><span data-stu-id="043a9-103">GetConfigurationStatus method</span></span>

<span data-ttu-id="043a9-104">Abrufen des Konfigurationsstatusverlaufs.</span><span class="sxs-lookup"><span data-stu-id="043a9-104">Get the configuration status history.</span></span>

## <a name="syntax"></a><span data-ttu-id="043a9-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="043a9-105">Syntax</span></span>

```mof
uint32 GetConfigurationStatus(
  [in]  boolean                     All,
  [out] MSFT_DSCConfigurationStatus configurationStatus[]
);
```

## <a name="parameters"></a><span data-ttu-id="043a9-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="043a9-106">Parameters</span></span>

<span data-ttu-id="043a9-107">**All** \[in\] **true** , wenn diese Methode Informationen zu allen Konfigurationsausführungen auf dem Computer zurückgeben soll, einschließlich der Konfigurationsanwendung und der Konsistenzprüfung.</span><span class="sxs-lookup"><span data-stu-id="043a9-107">**All** \[in\] **true** if this method should return information about all the configuration runs on the machine, including the configuration application and the consistency check.</span></span>

<span data-ttu-id="043a9-108">**configurationStatus** \[out\] Enthält bei der Rückgabe eine eingebettete Instanz der **MSFT_DSCConfigurationStatus** -Klasse, die die Einstellungen definiert.</span><span class="sxs-lookup"><span data-stu-id="043a9-108">**configurationStatus** \[out\] On return, contains an embedded instance of the **MSFT_DSCConfigurationStatus** class that defines the settings.</span></span>

## <a name="return-value"></a><span data-ttu-id="043a9-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="043a9-109">Return value</span></span>

<span data-ttu-id="043a9-110">Gibt bei Erfolg null zurück, andernfalls einen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="043a9-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="043a9-111">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="043a9-111">Remarks</span></span>

<span data-ttu-id="043a9-112">Dies ist eine statische Methode.</span><span class="sxs-lookup"><span data-stu-id="043a9-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="043a9-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="043a9-113">Requirements</span></span>

<span data-ttu-id="043a9-114">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="043a9-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="043a9-115">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="043a9-115">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="043a9-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="043a9-116">See also</span></span>

[<span data-ttu-id="043a9-117">**MSFT_DSCLocalConfigurationManager-Klasse**</span><span class="sxs-lookup"><span data-stu-id="043a9-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
