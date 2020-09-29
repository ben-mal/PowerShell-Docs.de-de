---
ms.date: 07/17/2020
keywords: DSC,PowerShell,Konfiguration,Setup,Einrichtung
title: TestConfiguration-Methode
ms.openlocfilehash: 0611c4d5543c49b879bef9b60cafdd0b055c9b86
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464297"
---
# <a name="testconfiguration-method"></a><span data-ttu-id="126bc-103">TestConfiguration-Methode</span><span class="sxs-lookup"><span data-stu-id="126bc-103">TestConfiguration method</span></span>

<span data-ttu-id="126bc-104">Sendet das Konfigurationsdokument an den verwalteten Knoten und überprüft die aktuelle Konfiguration anhand dieses Dokuments.</span><span class="sxs-lookup"><span data-stu-id="126bc-104">Sends the configuration document to the managed node and verifies the current configuration against the document.</span></span>

## <a name="syntax"></a><span data-ttu-id="126bc-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="126bc-105">Syntax</span></span>

```mof
uint32 TestConfiguration(
  [in]  uint8                          configurationData[],
  [out] boolean                        InDesiredState,
  [out] MSFT_ResourceInDesiredState    ResourcesInDesiredState[],
  [out] MSFT_ResourceNotInDesiredState ResourcesNotInDesiredState[]
);
```

## <a name="parameters"></a><span data-ttu-id="126bc-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="126bc-106">Parameters</span></span>

<span data-ttu-id="126bc-107">**configurationData** \[in\] Die Umgebungsdaten für die Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="126bc-107">**configurationData** \[in\] Environment data for the configuration.</span></span>

<span data-ttu-id="126bc-108">**InDesiredState** \[out\] Gibt bei der Rückgabe an, ob sich der verwaltete Knoten im vom Konfigurationsdokument angegebenen Zustand befindet.</span><span class="sxs-lookup"><span data-stu-id="126bc-108">**InDesiredState** \[out\] On return, specifies whether the managed node is in the state specified by the configuration document.</span></span>

<span data-ttu-id="126bc-109">**ResourcesInDesiredState** \[out\] Enthält bei der Rückgabe eine eingebettete Instanz der **MSFT_ResourceInDesiredState**-Klasse, die Ressourcen angibt, die sich im gewünschten Zustand befinden.</span><span class="sxs-lookup"><span data-stu-id="126bc-109">**ResourcesInDesiredState** \[out\] On return, contains an embedded instance of the **MSFT_ResourceInDesiredState** class that specifies resources that are in the desired state.</span></span>

<span data-ttu-id="126bc-110">**ResourcesNotInDesiredState** \[out\] Enthält bei der Rückgabe eine eingebettete Instanz der **MSFT_ResourceNotInDesiredState**-Klasse, die Ressourcen angibt, die sich nicht im gewünschten Zustand befinden.</span><span class="sxs-lookup"><span data-stu-id="126bc-110">**ResourcesNotInDesiredState** \[out\] On return, contains an embedded instance of the **MSFT_ResourceNotInDesiredState** class that specifies resources that are not in the desired state.</span></span>

## <a name="return-value"></a><span data-ttu-id="126bc-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="126bc-111">Return value</span></span>

<span data-ttu-id="126bc-112">Gibt bei Erfolg null zurück, andernfalls einen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="126bc-112">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="126bc-113">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="126bc-113">Remarks</span></span>

<span data-ttu-id="126bc-114">Dies ist eine statische Methode.</span><span class="sxs-lookup"><span data-stu-id="126bc-114">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="126bc-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="126bc-115">Requirements</span></span>

<span data-ttu-id="126bc-116">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="126bc-116">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="126bc-117">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="126bc-117">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="126bc-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="126bc-118">See also</span></span>

[<span data-ttu-id="126bc-119">**MSFT_DSCLocalConfigurationManager-Klasse**</span><span class="sxs-lookup"><span data-stu-id="126bc-119">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
