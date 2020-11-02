---
ms.date: 07/17/2020
ms.topic: reference
title: EnableDebugConfiguration-Methode
description: EnableDebugConfiguration-Methode
ms.openlocfilehash: 536366e6e1627a249f3bc2dc19bfd8ff3de42117
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92644768"
---
# <a name="enabledebugconfiguration-method"></a><span data-ttu-id="5f3c0-103">EnableDebugConfiguration-Methode</span><span class="sxs-lookup"><span data-stu-id="5f3c0-103">EnableDebugConfiguration method</span></span>

<span data-ttu-id="5f3c0-104">Aktiviert das Debuggen von DSC-Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="5f3c0-104">Enables DSC resource debugging.</span></span>

## <a name="syntax"></a><span data-ttu-id="5f3c0-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="5f3c0-105">Syntax</span></span>

```mof
uint32 EnableDebugConfiguration(
  [in] boolean BreakAll
);
```

## <a name="parameters"></a><span data-ttu-id="5f3c0-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="5f3c0-106">Parameters</span></span>

<span data-ttu-id="5f3c0-107">**BreakAll** \[in\] Legt einen Breakpoint in jeder Zeile im Ressourcenskript fest.</span><span class="sxs-lookup"><span data-stu-id="5f3c0-107">**BreakAll** \[in\] Sets a breakpoint at every line in the resource script.</span></span>

## <a name="return-value"></a><span data-ttu-id="5f3c0-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5f3c0-108">Return value</span></span>

<span data-ttu-id="5f3c0-109">Gibt bei Erfolg null zurück, andernfalls einen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="5f3c0-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="5f3c0-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="5f3c0-110">Remarks</span></span>

<span data-ttu-id="5f3c0-111">Dies ist eine statische Methode.</span><span class="sxs-lookup"><span data-stu-id="5f3c0-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="5f3c0-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="5f3c0-112">Requirements</span></span>

<span data-ttu-id="5f3c0-113">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="5f3c0-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="5f3c0-114">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="5f3c0-114">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="5f3c0-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5f3c0-115">See also</span></span>

[<span data-ttu-id="5f3c0-116">**MSFT_DSCLocalConfigurationManager-Klasse**</span><span class="sxs-lookup"><span data-stu-id="5f3c0-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
