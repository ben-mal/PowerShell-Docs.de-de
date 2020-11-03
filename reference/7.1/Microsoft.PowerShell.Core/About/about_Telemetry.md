---
description: Beschreibt die Telemetriedaten, die in PowerShell gesammelt werden, und wie Sie sich abmelden.
keywords: powershell
Locale: en-US
ms.date: 08/09/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_telemetry?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Telemetry
ms.openlocfilehash: ef921d0feefe277c2832c0a459ae150c9a6b4acb
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222340"
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

