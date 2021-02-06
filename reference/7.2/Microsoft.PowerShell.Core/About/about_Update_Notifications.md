---
description: Benachrichtigt Benutzer beim Starten von PowerShell, dass eine neue Version von PowerShell veröffentlicht wurde.
Locale: en-US
ms.date: 01/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_update_notifications?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Update_Notifications
ms.openlocfilehash: 1a9f8cfec15f83566fdb77175dcc1aed6d9e8c34
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596966"
---
# <a name="about-update-notifications"></a>Informationen zu Update Benachrichtigungen

## <a name="short-description"></a>KURZE BESCHREIBUNG

Benachrichtigt Benutzer beim Starten von PowerShell, dass eine neue Version von PowerShell veröffentlicht wurde.

## <a name="long-description"></a>LANGE BESCHREIBUNG

Ab PowerShell 7,0 verwendet PowerShell Update Benachrichtigungen, um Benutzer darauf aufmerksam zu machen, dass Updates für PowerShell vorhanden sind. Einmal pro Tag fragt PowerShell einen Onlinedienst ab, um zu prüfen, ob eine neuere Version verfügbar ist.

> [!NOTE]
> Während die Update Überprüfung während der ersten Sitzung innerhalb eines Zeitraums von 24 Stunden durchgeführt wird, wird die Benachrichtigung aus Leistungsgründen nur zu Beginn der nachfolgenden Sitzungen angezeigt. Aus Leistungsgründen wird die Überprüfung auch erst nach mindestens 3 Sekunden nach Beginn der Sitzung gestartet.

Standardmäßig abonniert PowerShell je nach Version/Branch einen von zwei verschiedenen Benachrichtigungskanälen. Unterstützte, allgemein verfügbare (GA-) Versionen von PowerShell geben nur für aktualisierte GA-Releases Benachrichtigungen zurück. Vorschau- und Release Candidate-Releases (RC) benachrichtigen über Updates für Vorschau-, RC- und GA-Releases.

Das Verhalten der Updatebenachrichtigung kann mithilfe der Umgebungsvariablen `POWERSHELL_UPDATECHECK` geändert werden. Die folgenden Werte werden unterstützt:

- `Off` deaktiviert das Aktualisierungs Benachrichtigungs Feature.
- `Default` entspricht nicht der Definition `POWERSHELL_UPDATECHECK` :
  - GA-Releases benachrichtigen zu Updates von GA-Releases.
  - Vorschau-/RC-Releases benachrichtigen zu Updates von GA- und Vorschau-Releases.
- `LTS` benachrichtigt nur Updates für LTS-GA-Releases (Long-Term-Wartung).

Die folgenden Endpunkte werden derzeit verwendet, um die neueste Version der einzelnen Kanäle zu ermitteln:

- `LTS`: https://aka.ms/pwsh-buildinfo-lts
- `Stable`: https://aka.ms/pwsh-buildinfo-stable
- `Preview`: https://aka.ms/pwsh-buildinfo-preview

Die Update Benachrichtigung bietet keine Möglichkeit, PowerShell automatisch zu aktualisieren. In Zukunft gibt es möglicherweise weitere Anweisungen oder Funktionen, die Sie in PowerShell aktualisieren können. Sie sollten aber heute denselben Installationsmechanismus verwenden, den Sie zum Aktualisieren von PowerShell zum Aktualisieren verwendet haben.

