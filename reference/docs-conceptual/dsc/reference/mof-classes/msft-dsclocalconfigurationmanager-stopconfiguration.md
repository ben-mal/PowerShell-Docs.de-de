---
ms.date: 07/17/2020
keywords: DSC,PowerShell,Konfiguration,Setup,Einrichtung
title: StopConfiguration-Methode
ms.openlocfilehash: 76e50c98b09dca86983320918c6899082580672a
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/18/2020
ms.locfileid: "86463702"
---
# <a name="stopconfiguration-method"></a><span data-ttu-id="e2141-103">StopConfiguration-Methode</span><span class="sxs-lookup"><span data-stu-id="e2141-103">StopConfiguration method</span></span>

<span data-ttu-id="e2141-104">Beende die Konfigurationsänderung, die gerade ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e2141-104">Stops the configuration change that is in progress.</span></span>

## <a name="syntax"></a><span data-ttu-id="e2141-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e2141-105">Syntax</span></span>

```mof
uint32 StopConfiguration(
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="e2141-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="e2141-106">Parameters</span></span>

<span data-ttu-id="e2141-107">**force** \[in\] **true**, um das Beenden der Konfiguration zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="e2141-107">**force** \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="e2141-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e2141-108">Return value</span></span>

<span data-ttu-id="e2141-109">Gibt bei Erfolg null zurück, andernfalls einen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="e2141-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="e2141-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="e2141-110">Remarks</span></span>

<span data-ttu-id="e2141-111">Dies ist eine statische Methode.</span><span class="sxs-lookup"><span data-stu-id="e2141-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="e2141-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e2141-112">Requirements</span></span>

<span data-ttu-id="e2141-113">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="e2141-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="e2141-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="e2141-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="e2141-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e2141-115">See also</span></span>

[<span data-ttu-id="e2141-116">**MSFT_DSCLocalConfigurationManager-Klasse**</span><span class="sxs-lookup"><span data-stu-id="e2141-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
