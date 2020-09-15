---
ms.date: 07/17/2020
keywords: DSC,PowerShell,Konfiguration,Setup,Einrichtung
title: SendMetaConfigurationApply-Methode
ms.openlocfilehash: 896afe2f3370e108b48583aafb33ee7b0eb1301b
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/18/2020
ms.locfileid: "86463719"
---
# <a name="sendmetaconfigurationapply-method"></a><span data-ttu-id="8f95e-103">SendMetaConfigurationApply-Methode</span><span class="sxs-lookup"><span data-stu-id="8f95e-103">SendMetaConfigurationApply method</span></span>

<span data-ttu-id="8f95e-104">Legt die Einstellungen des lokalen Konfigurations-Managers fest, die zur Steuerung des Konfigurations-Agents verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8f95e-104">Sets the Local Configuration Manager settings that are used to control the Configuration Agent.</span></span>

## <a name="syntax"></a><span data-ttu-id="8f95e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="8f95e-105">Syntax</span></span>

```mof
uint32 SendMetaConfigurationApply(
  [in] uint8   ConfigurationData[],
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="8f95e-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="8f95e-106">Parameters</span></span>

<span data-ttu-id="8f95e-107">**ConfigurationData** \[in\] Die Umgebungsdaten für die Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="8f95e-107">**ConfigurationData** \[in\] The environment data for the configuration.</span></span>

<span data-ttu-id="8f95e-108">**force** \[in\] **true**, um das Beenden der Konfiguration zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="8f95e-108">**force** \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="8f95e-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8f95e-109">Return value</span></span>

<span data-ttu-id="8f95e-110">Gibt bei Erfolg null zurück, andernfalls einen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="8f95e-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="8f95e-111">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="8f95e-111">Remarks</span></span>

<span data-ttu-id="8f95e-112">Dies ist eine statische Methode.</span><span class="sxs-lookup"><span data-stu-id="8f95e-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="8f95e-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="8f95e-113">Requirements</span></span>

<span data-ttu-id="8f95e-114">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="8f95e-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="8f95e-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="8f95e-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="8f95e-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8f95e-116">See also</span></span>

[<span data-ttu-id="8f95e-117">**MSFT_DSCLocalConfigurationManager-Klasse**</span><span class="sxs-lookup"><span data-stu-id="8f95e-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
