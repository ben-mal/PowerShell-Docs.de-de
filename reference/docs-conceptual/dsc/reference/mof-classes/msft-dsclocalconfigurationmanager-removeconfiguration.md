---
ms.date: 07/17/2020
keywords: DSC,PowerShell,Konfiguration,Setup,Einrichtung
title: RemoveConfiguration-Methode
ms.openlocfilehash: ef15c873d8dfaf28e5cdeb611b72a70921c099be
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464348"
---
# <a name="removeconfiguration-method"></a><span data-ttu-id="10fcf-103">RemoveConfiguration-Methode</span><span class="sxs-lookup"><span data-stu-id="10fcf-103">RemoveConfiguration method</span></span>

<span data-ttu-id="10fcf-104">Entfernt die Konfigurationsdateien.</span><span class="sxs-lookup"><span data-stu-id="10fcf-104">Removes the configuration files.</span></span>

## <a name="syntax"></a><span data-ttu-id="10fcf-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="10fcf-105">Syntax</span></span>

```mof
uint32 RemoveConfiguration(
  [in] uint32  Stage,
  [in] boolean Force
);
```

## <a name="parameters"></a><span data-ttu-id="10fcf-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="10fcf-106">Parameters</span></span>

<span data-ttu-id="10fcf-107">**Stage** \[in\] Gibt an, welches Konfigurationsdokument entfernt werden soll.</span><span class="sxs-lookup"><span data-stu-id="10fcf-107">**Stage** \[in\] Specifies which configuration document to remove.</span></span> <span data-ttu-id="10fcf-108">Die folgenden Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="10fcf-108">The following values are valid:</span></span>

|<span data-ttu-id="10fcf-109">Wert</span><span class="sxs-lookup"><span data-stu-id="10fcf-109">Value</span></span> |<span data-ttu-id="10fcf-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="10fcf-110">Description</span></span> |
|:--- |:---|
|<span data-ttu-id="10fcf-111">**1**</span><span class="sxs-lookup"><span data-stu-id="10fcf-111">**1**</span></span> | <span data-ttu-id="10fcf-112">Das **aktuelle** (Current) Konfigurationsdokument (current.mof).</span><span class="sxs-lookup"><span data-stu-id="10fcf-112">The **Current** configuration document (current.mof).</span></span> |
|<span data-ttu-id="10fcf-113">**2**</span><span class="sxs-lookup"><span data-stu-id="10fcf-113">**2**</span></span> | <span data-ttu-id="10fcf-114">Das **ausstehende** (Pending) Konfigurationsdokument (pending.mof).</span><span class="sxs-lookup"><span data-stu-id="10fcf-114">The **Pending** configuration document (pending.mof).</span></span>  |
|<span data-ttu-id="10fcf-115">**4**</span><span class="sxs-lookup"><span data-stu-id="10fcf-115">**4**</span></span> | <span data-ttu-id="10fcf-116">Das **vorherige** (Previous) Konfigurationsdokument (previous.mof).</span><span class="sxs-lookup"><span data-stu-id="10fcf-116">The **Previous** configuration document (previous.mof).</span></span> |

<span data-ttu-id="10fcf-117">*Force* \[in\] **true**, um das Entfernen der Konfiguration zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="10fcf-117">*Force* \[in\] **true** to force the removal of the configuration.</span></span>

## <a name="return-value"></a><span data-ttu-id="10fcf-118">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="10fcf-118">Return value</span></span>

<span data-ttu-id="10fcf-119">Gibt bei Erfolg null zurück, andernfalls einen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="10fcf-119">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="10fcf-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="10fcf-120">Remarks</span></span>

<span data-ttu-id="10fcf-121">Dies ist eine statische Methode.</span><span class="sxs-lookup"><span data-stu-id="10fcf-121">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="10fcf-122">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="10fcf-122">Requirements</span></span>

<span data-ttu-id="10fcf-123">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="10fcf-123">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="10fcf-124">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="10fcf-124">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="10fcf-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="10fcf-125">See also</span></span>

[<span data-ttu-id="10fcf-126">**MSFT_DSCLocalConfigurationManager-Klasse**</span><span class="sxs-lookup"><span data-stu-id="10fcf-126">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
