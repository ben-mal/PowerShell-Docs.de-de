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
# <a name="removeconfiguration-method"></a>RemoveConfiguration-Methode

Entfernt die Konfigurationsdateien.

## <a name="syntax"></a>Syntax

```mof
uint32 RemoveConfiguration(
  [in] uint32  Stage,
  [in] boolean Force
);
```

## <a name="parameters"></a>Parameter

**Stage** \[in\] Gibt an, welches Konfigurationsdokument entfernt werden soll. Die folgenden Werte sind gültig:

|Wert |BESCHREIBUNG |
|:--- |:---|
|**1** | Das **aktuelle** (Current) Konfigurationsdokument (current.mof). |
|**2** | Das **ausstehende** (Pending) Konfigurationsdokument (pending.mof).  |
|**4** | Das **vorherige** (Previous) Konfigurationsdokument (previous.mof). |

*Force* \[in\] **true**, um das Entfernen der Konfiguration zu erzwingen.

## <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg null zurück, andernfalls einen Fehlercode.

## <a name="remarks"></a>Bemerkungen

Dies ist eine statische Methode.

## <a name="requirements"></a>Requirements (Anforderungen)

**MOF:** DscCore.mof

**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>Weitere Informationen

[**MSFT_DSCLocalConfigurationManager-Klasse**](msft-dsclocalconfigurationmanager.md)
