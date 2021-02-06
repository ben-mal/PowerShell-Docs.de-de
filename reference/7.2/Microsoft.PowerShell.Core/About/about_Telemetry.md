---
description: Beschreibt die Telemetriedaten, die in PowerShell gesammelt werden, und wie Sie sich abmelden.
Locale: en-US
ms.date: 08/09/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_telemetry?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Telemetry
ms.openlocfilehash: 677d43b405fdc92e6b68d6e903847b11cb671a2c
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600499"
---
# <a name="about-telemetry"></a>Informationen zu Telemetrie

## <a name="short-description"></a>KURZE BESCHREIBUNG

Beschreibt die Telemetriedaten, die in PowerShell gesammelt werden, und wie Sie sich abmelden.

## <a name="long-description"></a>LANGE BESCHREIBUNG

PowerShell sendet grundlegende Telemetriedaten an Microsoft.
Dadurch wird erkennbar, in welchen Umgebungen PowerShell verwendet wird und welche neuen Funktionen und Problembehebungen Vorrang haben sollten.
Die folgenden telemetriepunkte werden aufgezeichnet:

- Anzahl der PowerShell-Starts nach Typ (API-vs-Konsole)
- Anzahl der eindeutigen PowerShell-Nutzung
- Anzahl der folgenden Ausführungs Typen:
  - Anwendung (Native Befehle)
  - Externalscript
  - Skript
  - Funktion
  - Cmdlet
- Anzahl der aktivierten experimentellen Features von Microsoft oder experimentelle Features, die mit PowerShell ausgeliefert werden
- Anzahl gehosteter Sitzungen
- Anzahl der geladenen Module im Besitz von Microsoft

Diese Daten umfassen den Betriebssystem Namen, die Betriebssystemversion, die PowerShell-Version und den Verteilungs Kanal.

Um diese Telemetrie zu abonnieren, legen Sie die Umgebungsvariable POWERSHELL_TELEMETRY_OPTOUT auf true, ja oder 1 fest.

