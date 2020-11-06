---
ms.date: 07/17/2020
ms.topic: reference
title: ResourceTest-Methode
description: ResourceTest-Methode
ms.openlocfilehash: cbac53ea96a59ec92fa840f75cd264a3125b965a
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92650667"
---
# <a name="resourcetest-method"></a>ResourceTest-Methode

Ruft direkt die **Test** -Methode einer DSC-Ressource auf.

## <a name="syntax"></a>Syntax

```mof
uint32 ResourceTest(
  [in]  string  ResourceType,
  [in]  string  ModuleName,
  [in]  uint8   resourceProperty[],
  [out] boolean InDesiredState
);
```

## <a name="parameters"></a>Parameter

**ResourceType** \[in\] Der Name der aufzurufenden Ressource.

**ModuleName** \[in\] Der Name des Moduls, das die aufzurufende Ressource enthält.

**_resourceProperty_*\[in\] Gibt den Namen der Ressourceneigenschaft und deren Wert in einer Hashtabelle als Schlüssel und Wert an. Verwenden Sie das Cmdlet [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) zum Ermitteln von Ressourceneigenschaften und deren Typen.

*InDesiredState** \[out\] Bei der Rückgabe wird diese Eigenschaft auf **TRUE** festgelegt, wenn sich der Zielknoten im gewünschten Zustand befindet.

## <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg null zurück, andernfalls einen Fehlercode.

## <a name="remarks"></a>Bemerkungen

Dies ist eine statische Methode.

## <a name="requirements"></a>Requirements (Anforderungen)

**MOF:** DscCore.mof

**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>Weitere Informationen

[**MSFT_DSCLocalConfigurationManager-Klasse**](msft-dsclocalconfigurationmanager.md)
