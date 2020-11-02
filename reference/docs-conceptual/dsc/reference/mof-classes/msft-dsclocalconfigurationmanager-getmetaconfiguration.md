---
ms.date: 07/17/2020
ms.topic: reference
title: GetMetaConfiguration-Methode
description: GetMetaConfiguration-Methode
ms.openlocfilehash: deca6b8ec342a34543bbe0e1fabbc2a740a88feb
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92644723"
---
# <a name="getmetaconfiguration-method"></a><span data-ttu-id="8f9d0-103">GetMetaConfiguration-Methode</span><span class="sxs-lookup"><span data-stu-id="8f9d0-103">GetMetaConfiguration method</span></span>

<span data-ttu-id="8f9d0-104">Ruft die Einstellungen des lokalen Konfigurations-Managers ab, die zur Steuerung des Konfigurations-Agents verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8f9d0-104">Gets the local Configuration Manager settings that are used to control the Configuration Agent.</span></span>

## <a name="syntax"></a><span data-ttu-id="8f9d0-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="8f9d0-105">Syntax</span></span>

```mof
uint32 GetMetaConfiguration(
  [out] MSFT_DSCMetaConfiguration MetaConfiguration
);
```

## <a name="parameters"></a><span data-ttu-id="8f9d0-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="8f9d0-106">Parameters</span></span>

<span data-ttu-id="8f9d0-107">**MetaConfiguration** \[out\] Enthält bei der Rückgabe eine eingebettete Instanz der **MSFT_DSCMetaConfiguration** -Klasse, die die Einstellungen definiert.</span><span class="sxs-lookup"><span data-stu-id="8f9d0-107">**MetaConfiguration** \[out\] On return, contains an embedded instance of the **MSFT_DSCMetaConfiguration** class that defines the settings.</span></span>

## <a name="return-value"></a><span data-ttu-id="8f9d0-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8f9d0-108">Return value</span></span>

<span data-ttu-id="8f9d0-109">Gibt bei Erfolg null zurück, andernfalls einen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="8f9d0-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="8f9d0-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="8f9d0-110">Remarks</span></span>

<span data-ttu-id="8f9d0-111">Dies ist eine statische Methode.</span><span class="sxs-lookup"><span data-stu-id="8f9d0-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="8f9d0-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="8f9d0-112">Requirements</span></span>

<span data-ttu-id="8f9d0-113">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="8f9d0-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="8f9d0-114">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="8f9d0-114">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="8f9d0-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8f9d0-115">See also</span></span>

[<span data-ttu-id="8f9d0-116">**MSFT_DSCLocalConfigurationManager-Klasse**</span><span class="sxs-lookup"><span data-stu-id="8f9d0-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
