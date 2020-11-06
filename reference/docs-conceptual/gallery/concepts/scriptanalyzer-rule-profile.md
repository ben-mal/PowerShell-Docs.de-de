---
ms.date: 06/12/2017
title: 'ScriptAnalyzer-Regel: Profil für den Katalog'
description: Erläutert, wie PowerShell ScriptAnalyzer in den PowerShell-Katalog integriert ist.
ms.openlocfilehash: 3af710e8811f0fabfb02f5317d5b4ff9c320f29a
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92646766"
---
# <a name="scriptanalyzer-rule-profile-for-gallery"></a>ScriptAnalyzer-Regel: Profil für den Katalog

Um die Qualität der im PowerShell-Katalog veröffentlichen Pakete sicherzustellen, werden [PowerShell ScriptAnalyzer](https://github.com/PowerShell/PSScriptAnalyzer)-Regeln ausgeführt, die die übermittelten Skripts auf Verstöße überprüfen.

Eine Liste der ausgeführte Regeln finden Sie auf der [GitHub-Seite von ScriptAnalyzer](https://github.com/PowerShell/PSScriptAnalyzer/blob/development/Engine/Settings/PSGallery.psd1).
Bei Bedenken bezüglich der ausgeführten Regeln wenden Sie sich bitte an die Administratoren des PowerShell-Katalogs oder melden Sie ein Problem mit ScriptAnalyzer.

Die ScriptAnalyzer-Ergebnisse werden im kommenden Release auf jeder einzelnen Paketseite des Katalogs angezeigt. Paketbesitzern wird empfohlen, ihre Pakete zu überprüfen, damit veröffentlichte Pakete keine schwerwiegenden Fehler enthalten.
