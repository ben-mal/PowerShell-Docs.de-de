---
ms.date: 07/17/2020
ms.topic: reference
title: GetConfigurationResultOutput-Methode
description: GetConfigurationResultOutput-Methode
ms.openlocfilehash: 7c885109b3078189b7ac653733a5fb24db66312e
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92644691"
---
# <a name="getconfigurationresultoutput-method"></a><span data-ttu-id="51668-103">GetConfigurationResultOutput-Methode</span><span class="sxs-lookup"><span data-stu-id="51668-103">GetConfigurationResultOutput method</span></span>

<span data-ttu-id="51668-104">Ruft die Konfigurations-Agent-Ausgabe im Zusammenhang mit einem bestimmten Auftrag ab.</span><span class="sxs-lookup"><span data-stu-id="51668-104">Gets the Configuration Agent output associated with a specific job.</span></span>

## <a name="syntax"></a><span data-ttu-id="51668-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="51668-105">Syntax</span></span>

```mof
uint32 GetConfigurationResultOutput(
  [in]  string                      jobId,
  [in]  uint8                       resumeOutputBookmark[],
  [out] MSFT_DSCConfigurationOutput output[]
);
```

## <a name="parameters"></a><span data-ttu-id="51668-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="51668-106">Parameters</span></span>

<span data-ttu-id="51668-107">**jobId** \[in\] Die ID des Auftrags, für den Ausgabedaten abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="51668-107">**jobId** \[in\] The ID of the job for which to get output data.</span></span>

<span data-ttu-id="51668-108">**resumeOutputBookmark** \[in\] Gibt an, dass die Ausgabe eine Fortsetzung eines vorherigen Lesezeichens sein soll.</span><span class="sxs-lookup"><span data-stu-id="51668-108">**resumeOutputBookmark** \[in\] Specifies that the output should be a continuation from a previous bookmark.</span></span>

<span data-ttu-id="51668-109">**output** \[out\] Die Ausgabe für den angegebenen Auftrag.</span><span class="sxs-lookup"><span data-stu-id="51668-109">**output** \[out\] The output for the specified job.</span></span>

## <a name="return-value"></a><span data-ttu-id="51668-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="51668-110">Return value</span></span>

<span data-ttu-id="51668-111">Gibt bei Erfolg null zurück, andernfalls einen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="51668-111">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="51668-112">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="51668-112">Remarks</span></span>

<span data-ttu-id="51668-113">Dies ist eine statische Methode.</span><span class="sxs-lookup"><span data-stu-id="51668-113">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="51668-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="51668-114">Requirements</span></span>

<span data-ttu-id="51668-115">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="51668-115">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="51668-116">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="51668-116">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="51668-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="51668-117">See also</span></span>

[<span data-ttu-id="51668-118">**MSFT_DSCLocalConfigurationManager-Klasse**</span><span class="sxs-lookup"><span data-stu-id="51668-118">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
