---
ms.date: 07/17/2020
ms.topic: reference
title: RollBack-Methode
description: RollBack-Methode
ms.openlocfilehash: 82ca54ed23a3a892b785f603be3b423def5ee636
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92650629"
---
# <a name="rollback-method"></a><span data-ttu-id="d1474-103">RollBack-Methode</span><span class="sxs-lookup"><span data-stu-id="d1474-103">RollBack method</span></span>

<span data-ttu-id="d1474-104">Führt einen Rollback der Konfiguration zu einer früheren Version durch.</span><span class="sxs-lookup"><span data-stu-id="d1474-104">Rolls back the configuration to a previous version.</span></span>

## <a name="syntax"></a><span data-ttu-id="d1474-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="d1474-105">Syntax</span></span>

```mof
uint32 RollBack(
  [in] uint8 configurationNumber
);
```

## <a name="parameters"></a><span data-ttu-id="d1474-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="d1474-106">Parameters</span></span>

<span data-ttu-id="d1474-107">**configurationNumber** \[in\] Gibt die angeforderte Konfiguration an.</span><span class="sxs-lookup"><span data-stu-id="d1474-107">**configurationNumber** \[in\] Specifies the requested configuration.</span></span>

## <a name="return-value"></a><span data-ttu-id="d1474-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d1474-108">Return value</span></span>

<span data-ttu-id="d1474-109">Gibt bei Erfolg null zurück, andernfalls einen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="d1474-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="d1474-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="d1474-110">Remarks</span></span>

<span data-ttu-id="d1474-111">Dies ist eine statische Methode.</span><span class="sxs-lookup"><span data-stu-id="d1474-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="d1474-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d1474-112">Requirements</span></span>

<span data-ttu-id="d1474-113">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="d1474-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="d1474-114">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="d1474-114">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="d1474-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d1474-115">See also</span></span>

[<span data-ttu-id="d1474-116">**MSFT_DSCLocalConfigurationManager-Klasse**</span><span class="sxs-lookup"><span data-stu-id="d1474-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
