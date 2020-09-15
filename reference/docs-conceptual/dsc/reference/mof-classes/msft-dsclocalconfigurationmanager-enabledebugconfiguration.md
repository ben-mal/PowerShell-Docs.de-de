---
ms.date: 07/17/2020
keywords: DSC,PowerShell,Konfiguration,Setup,Einrichtung
title: EnableDebugConfiguration-Methode
ms.openlocfilehash: be75b1012f49db79eb75a68c6912ffd5772bf16f
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464093"
---
# <a name="enabledebugconfiguration-method"></a><span data-ttu-id="a775c-103">EnableDebugConfiguration-Methode</span><span class="sxs-lookup"><span data-stu-id="a775c-103">EnableDebugConfiguration method</span></span>

<span data-ttu-id="a775c-104">Aktiviert das Debuggen von DSC-Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="a775c-104">Enables DSC resource debugging.</span></span>

## <a name="syntax"></a><span data-ttu-id="a775c-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="a775c-105">Syntax</span></span>

```mof
uint32 EnableDebugConfiguration(
  [in] boolean BreakAll
);
```

## <a name="parameters"></a><span data-ttu-id="a775c-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="a775c-106">Parameters</span></span>

<span data-ttu-id="a775c-107">**BreakAll** \[in\] Legt einen Breakpoint in jeder Zeile im Ressourcenskript fest.</span><span class="sxs-lookup"><span data-stu-id="a775c-107">**BreakAll** \[in\] Sets a breakpoint at every line in the resource script.</span></span>

## <a name="return-value"></a><span data-ttu-id="a775c-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a775c-108">Return value</span></span>

<span data-ttu-id="a775c-109">Gibt bei Erfolg null zurück, andernfalls einen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="a775c-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="a775c-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="a775c-110">Remarks</span></span>

<span data-ttu-id="a775c-111">Dies ist eine statische Methode.</span><span class="sxs-lookup"><span data-stu-id="a775c-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="a775c-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a775c-112">Requirements</span></span>

<span data-ttu-id="a775c-113">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="a775c-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="a775c-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="a775c-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="a775c-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a775c-115">See also</span></span>

[<span data-ttu-id="a775c-116">**MSFT_DSCLocalConfigurationManager-Klasse**</span><span class="sxs-lookup"><span data-stu-id="a775c-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
