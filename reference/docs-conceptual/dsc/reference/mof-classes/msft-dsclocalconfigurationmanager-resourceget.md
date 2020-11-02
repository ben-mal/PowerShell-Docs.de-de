---
ms.date: 07/17/2020
ms.topic: reference
title: ResourceGet-Methode
description: ResourceGet-Methode
ms.openlocfilehash: bff737f04e02740fa09fd82d7b27c75b11303dad
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92650766"
---
# <a name="resourceget-method"></a><span data-ttu-id="fa870-103">ResourceGet-Methode</span><span class="sxs-lookup"><span data-stu-id="fa870-103">ResourceGet method</span></span>

<span data-ttu-id="fa870-104">Ruft direkt die **Get** -Methode einer DSC-Ressource auf.</span><span class="sxs-lookup"><span data-stu-id="fa870-104">Directly calls the **Get** method of a DSC resource.</span></span>

## <a name="syntax"></a><span data-ttu-id="fa870-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="fa870-105">Syntax</span></span>

```mof
uint32 ResourceGet(
  [in]  string           ResourceType,
  [in]  string           ModuleName,
  [in]  uint8            resourceProperty[],
  [out] OMI_BaseResource configurations
);
```

## <a name="parameters"></a><span data-ttu-id="fa870-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="fa870-106">Parameters</span></span>

<span data-ttu-id="fa870-107">**ResourceType** \[in\] Der Name der aufzurufenden Ressource.</span><span class="sxs-lookup"><span data-stu-id="fa870-107">**ResourceType** \[in\] The name of the resource to call.</span></span>

<span data-ttu-id="fa870-108">**ModuleName** \[in\] Der Name des Moduls, das die aufzurufende Ressource enthält.</span><span class="sxs-lookup"><span data-stu-id="fa870-108">**ModuleName** \[in\] The name of the module that contains the resource to call.</span></span>

<span data-ttu-id="fa870-109">**resourceProperty** \[in\] Gibt den Namen der Ressourceneigenschaft und deren Wert in einer Hashtabelle als Schlüssel und Wert an.</span><span class="sxs-lookup"><span data-stu-id="fa870-109">**resourceProperty** \[in\] Specifies the resource property name and its value in a hash table as key and value, respectively.</span></span> <span data-ttu-id="fa870-110">Verwenden Sie das Cmdlet [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) zum Ermitteln von Ressourceneigenschaften und deren Typen.</span><span class="sxs-lookup"><span data-stu-id="fa870-110">Use the [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) cmdlet to discover resource properties and their types.</span></span>

<span data-ttu-id="fa870-111">**configurations** \[out\] Enthält bei Rückgabe eine eingebettete Instanz der Konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="fa870-111">**configurations** \[out\] On return, contains an embedded instance of the configurations.</span></span>

## <a name="return-value"></a><span data-ttu-id="fa870-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="fa870-112">Return value</span></span>

<span data-ttu-id="fa870-113">Gibt bei Erfolg null zurück, andernfalls einen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="fa870-113">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="fa870-114">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="fa870-114">Remarks</span></span>

<span data-ttu-id="fa870-115">Dies ist eine statische Methode.</span><span class="sxs-lookup"><span data-stu-id="fa870-115">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="fa870-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="fa870-116">Requirements</span></span>

<span data-ttu-id="fa870-117">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="fa870-117">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="fa870-118">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="fa870-118">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="fa870-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fa870-119">See also</span></span>

[<span data-ttu-id="fa870-120">**MSFT_DSCLocalConfigurationManager-Klasse**</span><span class="sxs-lookup"><span data-stu-id="fa870-120">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
