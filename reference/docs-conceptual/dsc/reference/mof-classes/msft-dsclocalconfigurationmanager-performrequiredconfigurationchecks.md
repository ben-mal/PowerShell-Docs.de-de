---
ms.date: 07/17/2020
ms.topic: reference
title: PerformRequiredConfigurationChecks-Methode
description: PerformRequiredConfigurationChecks-Methode
ms.openlocfilehash: c5e847cda6376f4266cc771dc947032a279e25f4
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92650832"
---
# <a name="performrequiredconfigurationchecks-method"></a><span data-ttu-id="ad6bb-103">PerformRequiredConfigurationChecks-Methode</span><span class="sxs-lookup"><span data-stu-id="ad6bb-103">PerformRequiredConfigurationChecks method</span></span>

<span data-ttu-id="ad6bb-104">Startet eine Konsistenzprüfung unter Verwendung des Taskplaners.</span><span class="sxs-lookup"><span data-stu-id="ad6bb-104">Starts a consistency check by using the Task Scheduler.</span></span>

## <a name="syntax"></a><span data-ttu-id="ad6bb-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="ad6bb-105">Syntax</span></span>

```mof
uint32 PerformRequiredConfigurationChecks(
  [in] uint32 Flags
);
```

## <a name="parameters"></a><span data-ttu-id="ad6bb-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="ad6bb-106">Parameters</span></span>

<span data-ttu-id="ad6bb-107">**Flags** \[in\] Eine Bitmaske, die den Typ der auszuführenden Konsistenzprüfung angibt.</span><span class="sxs-lookup"><span data-stu-id="ad6bb-107">**Flags** \[in\] A bitmask that specifies the type of consistency check to run.</span></span> <span data-ttu-id="ad6bb-108">Die folgenden Werte sind gültig und können mit einem bitweisen **ODER** -Vorgang kombiniert werden:</span><span class="sxs-lookup"><span data-stu-id="ad6bb-108">The following values are valid, and can be combined by using a bitwise **OR** operation:</span></span>

|<span data-ttu-id="ad6bb-109">Wert</span><span class="sxs-lookup"><span data-stu-id="ad6bb-109">Value</span></span> |<span data-ttu-id="ad6bb-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ad6bb-110">Description</span></span> |
|:--- |:---|
|<span data-ttu-id="ad6bb-111">**1**</span><span class="sxs-lookup"><span data-stu-id="ad6bb-111">**1**</span></span> | <span data-ttu-id="ad6bb-112">Eine normale Konsistenzprüfung.</span><span class="sxs-lookup"><span data-stu-id="ad6bb-112">A normal consistency check.</span></span> |
|<span data-ttu-id="ad6bb-113">**2**</span><span class="sxs-lookup"><span data-stu-id="ad6bb-113">**2**</span></span> | <span data-ttu-id="ad6bb-114">Die Fortsetzung einer Konsistenzprüfung nach einem Neustart.</span><span class="sxs-lookup"><span data-stu-id="ad6bb-114">A continuation of a consistency check after a reboot.</span></span> <span data-ttu-id="ad6bb-115">Dieser Wert sollte nicht mit anderen Werten kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="ad6bb-115">This value should not be combined with other values.</span></span> |
|<span data-ttu-id="ad6bb-116">**4**</span><span class="sxs-lookup"><span data-stu-id="ad6bb-116">**4**</span></span> | <span data-ttu-id="ad6bb-117">Die Konfiguration sollte von dem Pull-Server abgerufen werden, der in der Metakonfiguration für den Knoten angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="ad6bb-117">The configuration should be pulled from the pull server specified in the metaconfiguration for the node.</span></span> <span data-ttu-id="ad6bb-118">Dieser Wert sollte immer mit **1** kombiniert werden, um einen Wert von **5** zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="ad6bb-118">This value should always be combined with **1** , for a value of **5** .</span></span> |
|<span data-ttu-id="ad6bb-119">**8**</span><span class="sxs-lookup"><span data-stu-id="ad6bb-119">**8**</span></span> | <span data-ttu-id="ad6bb-120">Senden des Status an den Berichtsserver.</span><span class="sxs-lookup"><span data-stu-id="ad6bb-120">Send status to the report server.</span></span> |

## <a name="return-value"></a><span data-ttu-id="ad6bb-121">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ad6bb-121">Return value</span></span>

<span data-ttu-id="ad6bb-122">Gibt bei Erfolg null zurück, andernfalls einen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="ad6bb-122">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="ad6bb-123">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ad6bb-123">Remarks</span></span>

<span data-ttu-id="ad6bb-124">Dies ist eine statische Methode.</span><span class="sxs-lookup"><span data-stu-id="ad6bb-124">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="ad6bb-125">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ad6bb-125">Requirements</span></span>

<span data-ttu-id="ad6bb-126">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="ad6bb-126">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="ad6bb-127">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="ad6bb-127">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="ad6bb-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ad6bb-128">See also</span></span>

[<span data-ttu-id="ad6bb-129">**MSFT_DSCLocalConfigurationManager-Klasse**</span><span class="sxs-lookup"><span data-stu-id="ad6bb-129">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
