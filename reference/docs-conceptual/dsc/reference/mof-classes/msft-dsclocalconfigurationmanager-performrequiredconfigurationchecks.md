---
ms.date: 07/17/2020
keywords: DSC,PowerShell,Konfiguration,Setup,Einrichtung
title: PerformRequiredConfigurationChecks-Methode
ms.openlocfilehash: ea4294ffdcb2580fa7b39b18966b642d58073eb6
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464450"
---
# <a name="performrequiredconfigurationchecks-method"></a>PerformRequiredConfigurationChecks-Methode

Startet eine Konsistenzprüfung unter Verwendung des Taskplaners.

## <a name="syntax"></a>Syntax

```mof
uint32 PerformRequiredConfigurationChecks(
  [in] uint32 Flags
);
```

## <a name="parameters"></a>Parameter

**Flags** \[in\] Eine Bitmaske, die den Typ der auszuführenden Konsistenzprüfung angibt. Die folgenden Werte sind gültig und können mit einem bitweisen **ODER**-Vorgang kombiniert werden:

|Wert |BESCHREIBUNG |
|:--- |:---|
|**1** | Eine normale Konsistenzprüfung. |
|**2** | Die Fortsetzung einer Konsistenzprüfung nach einem Neustart. Dieser Wert sollte nicht mit anderen Werten kombiniert werden. |
|**4** | Die Konfiguration sollte von dem Pull-Server abgerufen werden, der in der Metakonfiguration für den Knoten angegeben ist. Dieser Wert sollte immer mit **1** kombiniert werden, um einen Wert von **5** zu erzielen. |
|**8** | Senden des Status an den Berichtsserver. |

## <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg null zurück, andernfalls einen Fehlercode.

## <a name="remarks"></a>Bemerkungen

Dies ist eine statische Methode.

## <a name="requirements"></a>Requirements (Anforderungen)

**MOF:** DscCore.mof

**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>Weitere Informationen

[**MSFT_DSCLocalConfigurationManager-Klasse**](msft-dsclocalconfigurationmanager.md)
