---
ms.date: 07/17/2020
keywords: DSC,PowerShell,Konfiguration,Setup,Einrichtung
title: RollBack-Methode
ms.openlocfilehash: 301b8926d2ebf1ebe524f52a67928d34e26d860e
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464331"
---
# <a name="rollback-method"></a><span data-ttu-id="19175-103">RollBack-Methode</span><span class="sxs-lookup"><span data-stu-id="19175-103">RollBack method</span></span>

<span data-ttu-id="19175-104">Führt einen Rollback der Konfiguration zu einer früheren Version durch.</span><span class="sxs-lookup"><span data-stu-id="19175-104">Rolls back the configuration to a previous version.</span></span>

## <a name="syntax"></a><span data-ttu-id="19175-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="19175-105">Syntax</span></span>

```mof
uint32 RollBack(
  [in] uint8 configurationNumber
);
```

## <a name="parameters"></a><span data-ttu-id="19175-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="19175-106">Parameters</span></span>

<span data-ttu-id="19175-107">**configurationNumber** \[in\] Gibt die angeforderte Konfiguration an.</span><span class="sxs-lookup"><span data-stu-id="19175-107">**configurationNumber** \[in\] Specifies the requested configuration.</span></span>

## <a name="return-value"></a><span data-ttu-id="19175-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="19175-108">Return value</span></span>

<span data-ttu-id="19175-109">Gibt bei Erfolg null zurück, andernfalls einen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="19175-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="19175-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="19175-110">Remarks</span></span>

<span data-ttu-id="19175-111">Dies ist eine statische Methode.</span><span class="sxs-lookup"><span data-stu-id="19175-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="19175-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="19175-112">Requirements</span></span>

<span data-ttu-id="19175-113">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="19175-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="19175-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="19175-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="19175-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="19175-115">See also</span></span>

[<span data-ttu-id="19175-116">**MSFT_DSCLocalConfigurationManager-Klasse**</span><span class="sxs-lookup"><span data-stu-id="19175-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
