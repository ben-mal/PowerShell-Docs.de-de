---
ms.date: 07/17/2020
ms.topic: reference
title: TestConfiguration-Methode
description: TestConfiguration-Methode
ms.openlocfilehash: ed26fcad2286ca753fb4b1845b8c6ad0741d491b
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92648929"
---
# <a name="testconfiguration-method"></a><span data-ttu-id="a2039-103">TestConfiguration-Methode</span><span class="sxs-lookup"><span data-stu-id="a2039-103">TestConfiguration method</span></span>

<span data-ttu-id="a2039-104">Sendet das Konfigurationsdokument an den verwalteten Knoten und überprüft die aktuelle Konfiguration anhand dieses Dokuments.</span><span class="sxs-lookup"><span data-stu-id="a2039-104">Sends the configuration document to the managed node and verifies the current configuration against the document.</span></span>

## <a name="syntax"></a><span data-ttu-id="a2039-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="a2039-105">Syntax</span></span>

```mof
uint32 TestConfiguration(
  [in]  uint8                          configurationData[],
  [out] boolean                        InDesiredState,
  [out] MSFT_ResourceInDesiredState    ResourcesInDesiredState[],
  [out] MSFT_ResourceNotInDesiredState ResourcesNotInDesiredState[]
);
```

## <a name="parameters"></a><span data-ttu-id="a2039-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="a2039-106">Parameters</span></span>

<span data-ttu-id="a2039-107">**configurationData** \[in\] Die Umgebungsdaten für die Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="a2039-107">**configurationData** \[in\] Environment data for the configuration.</span></span>

<span data-ttu-id="a2039-108">**InDesiredState** \[out\] Gibt bei der Rückgabe an, ob sich der verwaltete Knoten im vom Konfigurationsdokument angegebenen Zustand befindet.</span><span class="sxs-lookup"><span data-stu-id="a2039-108">**InDesiredState** \[out\] On return, specifies whether the managed node is in the state specified by the configuration document.</span></span>

<span data-ttu-id="a2039-109">**ResourcesInDesiredState** \[out\] Enthält bei der Rückgabe eine eingebettete Instanz der **MSFT_ResourceInDesiredState** -Klasse, die Ressourcen angibt, die sich im gewünschten Zustand befinden.</span><span class="sxs-lookup"><span data-stu-id="a2039-109">**ResourcesInDesiredState** \[out\] On return, contains an embedded instance of the **MSFT_ResourceInDesiredState** class that specifies resources that are in the desired state.</span></span>

<span data-ttu-id="a2039-110">**ResourcesNotInDesiredState** \[out\] Enthält bei der Rückgabe eine eingebettete Instanz der **MSFT_ResourceNotInDesiredState** -Klasse, die Ressourcen angibt, die sich nicht im gewünschten Zustand befinden.</span><span class="sxs-lookup"><span data-stu-id="a2039-110">**ResourcesNotInDesiredState** \[out\] On return, contains an embedded instance of the **MSFT_ResourceNotInDesiredState** class that specifies resources that are not in the desired state.</span></span>

## <a name="return-value"></a><span data-ttu-id="a2039-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a2039-111">Return value</span></span>

<span data-ttu-id="a2039-112">Gibt bei Erfolg null zurück, andernfalls einen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="a2039-112">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="a2039-113">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="a2039-113">Remarks</span></span>

<span data-ttu-id="a2039-114">Dies ist eine statische Methode.</span><span class="sxs-lookup"><span data-stu-id="a2039-114">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="a2039-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a2039-115">Requirements</span></span>

<span data-ttu-id="a2039-116">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="a2039-116">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="a2039-117">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="a2039-117">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="a2039-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a2039-118">See also</span></span>

[<span data-ttu-id="a2039-119">**MSFT_DSCLocalConfigurationManager-Klasse**</span><span class="sxs-lookup"><span data-stu-id="a2039-119">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
