---
ms.date: 07/17/2020
ms.topic: reference
title: SendMetaConfigurationApply-Methode
description: SendMetaConfigurationApply-Methode
ms.openlocfilehash: 27c58819c0249ace011c475e500e565e5daed9bb
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92648950"
---
# <a name="sendmetaconfigurationapply-method"></a><span data-ttu-id="f9198-103">SendMetaConfigurationApply-Methode</span><span class="sxs-lookup"><span data-stu-id="f9198-103">SendMetaConfigurationApply method</span></span>

<span data-ttu-id="f9198-104">Legt die Einstellungen des lokalen Konfigurations-Managers fest, die zur Steuerung des Konfigurations-Agents verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f9198-104">Sets the Local Configuration Manager settings that are used to control the Configuration Agent.</span></span>

## <a name="syntax"></a><span data-ttu-id="f9198-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f9198-105">Syntax</span></span>

```mof
uint32 SendMetaConfigurationApply(
  [in] uint8   ConfigurationData[],
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="f9198-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="f9198-106">Parameters</span></span>

<span data-ttu-id="f9198-107">**ConfigurationData** \[in\] Die Umgebungsdaten für die Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="f9198-107">**ConfigurationData** \[in\] The environment data for the configuration.</span></span>

<span data-ttu-id="f9198-108">**force** \[in\] **true** , um das Beenden der Konfiguration zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="f9198-108">**force** \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="f9198-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f9198-109">Return value</span></span>

<span data-ttu-id="f9198-110">Gibt bei Erfolg null zurück, andernfalls einen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="f9198-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="f9198-111">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="f9198-111">Remarks</span></span>

<span data-ttu-id="f9198-112">Dies ist eine statische Methode.</span><span class="sxs-lookup"><span data-stu-id="f9198-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="f9198-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f9198-113">Requirements</span></span>

<span data-ttu-id="f9198-114">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="f9198-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="f9198-115">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="f9198-115">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="f9198-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f9198-116">See also</span></span>

[<span data-ttu-id="f9198-117">**MSFT_DSCLocalConfigurationManager-Klasse**</span><span class="sxs-lookup"><span data-stu-id="f9198-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
