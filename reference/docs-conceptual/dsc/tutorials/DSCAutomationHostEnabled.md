---
ms.date: 06/12/2017
keywords: DSC,PowerShell,Konfiguration,Setup,Einrichtung
title: DSCAutomationHostEnabled (Registrierungsschlüssel)
description: In diesem Artikel werden die Werte definiert, die im Registrierungsschlüssel DSCAutomationHostEnabled festgelegt werden können.
ms.openlocfilehash: 50f752dd882e9b0787ed4a4cbc22731fc1d608f5
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92656180"
---
# <a name="dscautomationhostenabled-registry-key"></a>DSCAutomationHostEnabled (Registrierungsschlüssel)

> Gilt für: Windows PowerShell 5.0

DSC verwendet den Registrierungsschlüssel **DSCAutomationHostEnabled** unter **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System** , um die Konfiguration des Computer beim ersten Start zu ermöglichen. **DSCAutomationHostEnabled** unterstützt drei Modi:

| DSCAutomationHostEnabled-Wert |                                              BESCHREIBUNG                                              |
| ------------------------------ | ----------------------------------------------------------------------------------------------------- |
| 0                              | Konfiguration des Computers beim Hochfahren deaktivieren                                                           |
| 1                              | Konfiguration des Computers beim Hochfahren aktivieren                                                            |
| 2                              | Konfiguration des Computers nur dann aktivieren, wenn DSC sich im Status „ausstehend“ oder „aktuell“ befindet. Dies ist der Standardwert. |

## <a name="see-also"></a>Weitere Informationen

Ein Beispiel dazu, wie Sie dieses Features zum Ausführen von Konfigurationen beim ersten Hochfahren verwenden, finden Sie unter [Konfigurieren eines virtuellen Computers beim ersten Hochfahren mithilfe von DSC](bootstrapDsc.md).
