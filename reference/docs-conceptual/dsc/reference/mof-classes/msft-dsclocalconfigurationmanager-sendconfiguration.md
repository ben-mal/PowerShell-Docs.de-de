---
ms.date: 07/17/2020
ms.topic: reference
title: SendConfiguration-Methode
description: SendConfiguration-Methode
ms.openlocfilehash: 3939a76ab6672b49559847b0ef1408f1c7be6d0c
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92650557"
---
# <a name="sendconfiguration-method"></a><span data-ttu-id="0999e-103">SendConfiguration-Methode</span><span class="sxs-lookup"><span data-stu-id="0999e-103">SendConfiguration method</span></span>

<span data-ttu-id="0999e-104">Sendet das Konfigurationsdokument an den verwalteten Knoten und speichert es als ausstehende Änderung.</span><span class="sxs-lookup"><span data-stu-id="0999e-104">Sends the configuration document to the managed node and saves it as a pending change.</span></span>

## <a name="syntax"></a><span data-ttu-id="0999e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="0999e-105">Syntax</span></span>

```mof
uint32 SendConfiguration(
  [in] uint8   ConfigurationData[],
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="0999e-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="0999e-106">Parameters</span></span>

<span data-ttu-id="0999e-107">**ConfigurationData** \[in\] Die Umgebungsdaten für die Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="0999e-107">**ConfigurationData** \[in\] The environment data for the configuration.</span></span>

<span data-ttu-id="0999e-108">**force** \[in\] **true** , um das Beenden der Konfiguration zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="0999e-108">**force** \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="0999e-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0999e-109">Return value</span></span>

<span data-ttu-id="0999e-110">Gibt bei Erfolg null zurück, andernfalls einen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="0999e-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="0999e-111">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="0999e-111">Remarks</span></span>

<span data-ttu-id="0999e-112">Dies ist eine statische Methode.</span><span class="sxs-lookup"><span data-stu-id="0999e-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="0999e-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="0999e-113">Requirements</span></span>

<span data-ttu-id="0999e-114">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="0999e-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="0999e-115">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="0999e-115">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="0999e-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0999e-116">See also</span></span>

[<span data-ttu-id="0999e-117">**MSFT_DSCLocalConfigurationManager-Klasse**</span><span class="sxs-lookup"><span data-stu-id="0999e-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
