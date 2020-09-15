---
ms.date: 07/14/2020
keywords: DSC,PowerShell,Konfiguration,Setup,Einrichtung
title: ApplyConfiguration-Methode
ms.openlocfilehash: bec74ccd6f75448484adfd26bf8a4af4e224eb3f
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/18/2020
ms.locfileid: "86463838"
---
# <a name="applyconfiguration-method"></a><span data-ttu-id="17f09-103">ApplyConfiguration-Methode</span><span class="sxs-lookup"><span data-stu-id="17f09-103">ApplyConfiguration method</span></span>

<span data-ttu-id="17f09-104">Verwendet den Konfigurations-Agent, um die ausstehende Konfiguration anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="17f09-104">Uses the Configuration Agent to apply the configuration that is pending.</span></span>

<span data-ttu-id="17f09-105">Wenn keine ausstehende Konfiguration vorhanden ist, wendet diese Methode die aktuelle Konfiguration erneut an.</span><span class="sxs-lookup"><span data-stu-id="17f09-105">If there is no configuration pending, this method reapplies the current configuration.</span></span>

## <a name="syntax"></a><span data-ttu-id="17f09-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="17f09-106">Syntax</span></span>

```mof
uint32 ApplyConfiguration(
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="17f09-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="17f09-107">Parameters</span></span>

### <a name="force"></a><span data-ttu-id="17f09-108">force</span><span class="sxs-lookup"><span data-stu-id="17f09-108">force</span></span>

<span data-ttu-id="17f09-109">Wenn dies **true** ist, wird die aktuelle Konfiguration erneut angewendet, auch wenn eine Konfiguration aussteht.</span><span class="sxs-lookup"><span data-stu-id="17f09-109">If this is **true**, the current configuration is reapplied, even if there is a configuration pending.</span></span>

## <a name="return-value"></a><span data-ttu-id="17f09-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="17f09-110">Return value</span></span>

<span data-ttu-id="17f09-111">Gibt bei Erfolg null zurück, andernfalls einen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="17f09-111">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="17f09-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="17f09-112">Remarks</span></span>

<span data-ttu-id="17f09-113">Dies ist eine statische Methode.</span><span class="sxs-lookup"><span data-stu-id="17f09-113">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="17f09-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="17f09-114">Requirements</span></span>

<span data-ttu-id="17f09-115">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="17f09-115">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="17f09-116">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="17f09-116">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="17f09-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="17f09-117">See also</span></span>

[<span data-ttu-id="17f09-118">**MSFT_DSCLocalConfigurationManager-Klasse**</span><span class="sxs-lookup"><span data-stu-id="17f09-118">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
