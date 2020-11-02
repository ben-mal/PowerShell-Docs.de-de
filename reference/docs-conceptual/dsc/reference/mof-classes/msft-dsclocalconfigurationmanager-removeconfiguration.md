---
ms.date: 07/17/2020
ms.topic: reference
title: RemoveConfiguration-Methode
description: RemoveConfiguration-Methode
ms.openlocfilehash: d5988ac014c457407c56a097c9a376427376eb3f
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92650718"
---
# <a name="removeconfiguration-method"></a><span data-ttu-id="763e6-103">RemoveConfiguration-Methode</span><span class="sxs-lookup"><span data-stu-id="763e6-103">RemoveConfiguration method</span></span>

<span data-ttu-id="763e6-104">Entfernt die Konfigurationsdateien.</span><span class="sxs-lookup"><span data-stu-id="763e6-104">Removes the configuration files.</span></span>

## <a name="syntax"></a><span data-ttu-id="763e6-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="763e6-105">Syntax</span></span>

```mof
uint32 RemoveConfiguration(
  [in] uint32  Stage,
  [in] boolean Force
);
```

## <a name="parameters"></a><span data-ttu-id="763e6-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="763e6-106">Parameters</span></span>

<span data-ttu-id="763e6-107">**Stage** \[in\] Gibt an, welches Konfigurationsdokument entfernt werden soll.</span><span class="sxs-lookup"><span data-stu-id="763e6-107">**Stage** \[in\] Specifies which configuration document to remove.</span></span> <span data-ttu-id="763e6-108">Die folgenden Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="763e6-108">The following values are valid:</span></span>

|<span data-ttu-id="763e6-109">Wert</span><span class="sxs-lookup"><span data-stu-id="763e6-109">Value</span></span> |<span data-ttu-id="763e6-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="763e6-110">Description</span></span> |
|:--- |:---|
|<span data-ttu-id="763e6-111">**1**</span><span class="sxs-lookup"><span data-stu-id="763e6-111">**1**</span></span> | <span data-ttu-id="763e6-112">Das **aktuelle** (Current) Konfigurationsdokument (current.mof).</span><span class="sxs-lookup"><span data-stu-id="763e6-112">The **Current** configuration document (current.mof).</span></span> |
|<span data-ttu-id="763e6-113">**2**</span><span class="sxs-lookup"><span data-stu-id="763e6-113">**2**</span></span> | <span data-ttu-id="763e6-114">Das **ausstehende** (Pending) Konfigurationsdokument (pending.mof).</span><span class="sxs-lookup"><span data-stu-id="763e6-114">The **Pending** configuration document (pending.mof).</span></span>  |
|<span data-ttu-id="763e6-115">**4**</span><span class="sxs-lookup"><span data-stu-id="763e6-115">**4**</span></span> | <span data-ttu-id="763e6-116">Das **vorherige** (Previous) Konfigurationsdokument (previous.mof).</span><span class="sxs-lookup"><span data-stu-id="763e6-116">The **Previous** configuration document (previous.mof).</span></span> |

<span data-ttu-id="763e6-117">*Force* \[in\] **true** , um das Entfernen der Konfiguration zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="763e6-117">*Force* \[in\] **true** to force the removal of the configuration.</span></span>

## <a name="return-value"></a><span data-ttu-id="763e6-118">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="763e6-118">Return value</span></span>

<span data-ttu-id="763e6-119">Gibt bei Erfolg null zurück, andernfalls einen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="763e6-119">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="763e6-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="763e6-120">Remarks</span></span>

<span data-ttu-id="763e6-121">Dies ist eine statische Methode.</span><span class="sxs-lookup"><span data-stu-id="763e6-121">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="763e6-122">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="763e6-122">Requirements</span></span>

<span data-ttu-id="763e6-123">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="763e6-123">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="763e6-124">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="763e6-124">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="763e6-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="763e6-125">See also</span></span>

[<span data-ttu-id="763e6-126">**MSFT_DSCLocalConfigurationManager-Klasse**</span><span class="sxs-lookup"><span data-stu-id="763e6-126">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
