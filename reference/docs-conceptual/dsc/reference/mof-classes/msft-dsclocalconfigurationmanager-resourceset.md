---
ms.date: 07/17/2020
keywords: DSC,PowerShell,Konfiguration,Setup,Einrichtung
title: ResourceSet-Methode
ms.openlocfilehash: c015960b2a5ffca0d28b714d571aa616400555bd
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464049"
---
# <a name="resourceset-method"></a><span data-ttu-id="03826-103">ResourceSet-Methode</span><span class="sxs-lookup"><span data-stu-id="03826-103">ResourceSet method</span></span>

<span data-ttu-id="03826-104">Ruft direkt die **Set**-Methode einer DSC-Ressource auf.</span><span class="sxs-lookup"><span data-stu-id="03826-104">Directly calls the **Set** method of a DSC resource.</span></span>

## <a name="syntax"></a><span data-ttu-id="03826-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="03826-105">Syntax</span></span>

```mof
uint32 ResourceSet(
  [in]  string  ResourceType,
  [in]  string  ModuleName,
  [in]  uint8   resourceProperty[],
  [out] boolean RebootRequired
);
```

## <a name="parameters"></a><span data-ttu-id="03826-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="03826-106">Parameters</span></span>

<span data-ttu-id="03826-107">**ResourceType** \[in\] Der Name der aufzurufenden Ressource.</span><span class="sxs-lookup"><span data-stu-id="03826-107">**ResourceType** \[in\] The name of the resource to call.</span></span>

<span data-ttu-id="03826-108">**ModuleName** \[in\] Der Name des Moduls, das die aufzurufende Ressource enthält.</span><span class="sxs-lookup"><span data-stu-id="03826-108">**ModuleName** \[in\] The name of the module that contains the resource to call.</span></span>

<span data-ttu-id="03826-109">**resourceProperty** \[in\] Gibt den Namen der Ressourceneigenschaft und deren Wert in einer Hashtabelle als Schlüssel und Wert an.</span><span class="sxs-lookup"><span data-stu-id="03826-109">**resourceProperty** \[in\] Specifies the resource property name and its value in a hash table as key and value, respectively.</span></span> <span data-ttu-id="03826-110">Verwenden Sie das Cmdlet [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) zum Ermitteln von Ressourceneigenschaften und deren Typen.</span><span class="sxs-lookup"><span data-stu-id="03826-110">Use the [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) cmdlet to discover resource properties and their types.</span></span>

<span data-ttu-id="03826-111">**RebootRequired** \[out\] Bei der Rückgabe wird diese Eigenschaft auf **true** festgelegt, wenn der Zielknoten neu gestartet werden muss.</span><span class="sxs-lookup"><span data-stu-id="03826-111">**RebootRequired** \[out\] On return, this property is set to **true** if the target node needs to be rebooted.</span></span>

## <a name="return-value"></a><span data-ttu-id="03826-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="03826-112">Return value</span></span>

<span data-ttu-id="03826-113">Gibt bei Erfolg null zurück, andernfalls einen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="03826-113">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="03826-114">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="03826-114">Remarks</span></span>

<span data-ttu-id="03826-115">Dies ist eine statische Methode.</span><span class="sxs-lookup"><span data-stu-id="03826-115">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="03826-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="03826-116">Requirements</span></span>

<span data-ttu-id="03826-117">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="03826-117">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="03826-118">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="03826-118">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="03826-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="03826-119">See also</span></span>

[<span data-ttu-id="03826-120">**MSFT_DSCLocalConfigurationManager-Klasse**</span><span class="sxs-lookup"><span data-stu-id="03826-120">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
