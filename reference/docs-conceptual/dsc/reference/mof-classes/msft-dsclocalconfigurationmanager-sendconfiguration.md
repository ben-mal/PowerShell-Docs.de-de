---
ms.date: 07/17/2020
keywords: DSC,PowerShell,Konfiguration,Setup,Einrichtung
title: SendConfiguration-Methode
ms.openlocfilehash: afd6e8d7acc969df16fad1d0ba15c9fe0b1a26fd
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/18/2020
ms.locfileid: "86463940"
---
# <a name="sendconfiguration-method"></a><span data-ttu-id="d327e-103">SendConfiguration-Methode</span><span class="sxs-lookup"><span data-stu-id="d327e-103">SendConfiguration method</span></span>

<span data-ttu-id="d327e-104">Sendet das Konfigurationsdokument an den verwalteten Knoten und speichert es als ausstehende Änderung.</span><span class="sxs-lookup"><span data-stu-id="d327e-104">Sends the configuration document to the managed node and saves it as a pending change.</span></span>

## <a name="syntax"></a><span data-ttu-id="d327e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="d327e-105">Syntax</span></span>

```mof
uint32 SendConfiguration(
  [in] uint8   ConfigurationData[],
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="d327e-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="d327e-106">Parameters</span></span>

<span data-ttu-id="d327e-107">**ConfigurationData** \[in\] Die Umgebungsdaten für die Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="d327e-107">**ConfigurationData** \[in\] The environment data for the configuration.</span></span>

<span data-ttu-id="d327e-108">**force** \[in\] **true**, um das Beenden der Konfiguration zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="d327e-108">**force** \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="d327e-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d327e-109">Return value</span></span>

<span data-ttu-id="d327e-110">Gibt bei Erfolg null zurück, andernfalls einen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="d327e-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="d327e-111">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="d327e-111">Remarks</span></span>

<span data-ttu-id="d327e-112">Dies ist eine statische Methode.</span><span class="sxs-lookup"><span data-stu-id="d327e-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="d327e-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d327e-113">Requirements</span></span>

<span data-ttu-id="d327e-114">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="d327e-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="d327e-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="d327e-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="d327e-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d327e-116">See also</span></span>

[<span data-ttu-id="d327e-117">**MSFT_DSCLocalConfigurationManager-Klasse**</span><span class="sxs-lookup"><span data-stu-id="d327e-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
