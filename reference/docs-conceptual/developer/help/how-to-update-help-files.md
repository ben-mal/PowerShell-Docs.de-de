---
ms.date: 09/12/2016
ms.topic: reference
title: Aktualisieren von Hilfedateien
description: Aktualisieren von Hilfedateien
ms.openlocfilehash: 19bf501cf91b1eb5dabb334c2179953590b40232
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649582"
---
# <a name="how-to-update-help-files"></a>Aktualisieren von Hilfedateien

In diesem Thema wird erläutert, wie Sie Hilfedateien für ein Modul aktualisieren, das aktualisierbare Hilfe unterstützt.

## <a name="updating-help-files"></a>Aktualisieren von Hilfedateien

Es gibt viele Gründe, Hilfedateien zu aktualisieren, wie z. b. das Beheben von Fehlern, das verdeutlichen eines Konzepts, das Beantworten einer häufig gestellten Frage, das Hinzufügen neuer Dateien oder das Hinzufügen neuer und besserer Beispiele.

So aktualisieren Sie eine Hilfedatei:

1. Ändern Sie die Dateien.
1. Übersetzen Sie die Dateien in andere Benutzeroberflächen Kulturen.
1. Sammeln Sie alle Hilfedateien (neu, geändert und unverändert) für das Modul in jeder Benutzeroberflächen Kultur.
1. Überprüfen Sie die Dateien anhand des XML-Schemas.
1. Erstellen Sie die CAB-Dateien für jede Benutzeroberflächen Kultur neu.
1. Erhöhen Sie in der helpinfo-XML-Datei die Versionsnummern der CAB-Datei für jede Benutzeroberflächen Kultur.
1. Laden Sie die neuen CAB-Dateien an den Speicherort hoch, der durch den Wert des **helpcontenturi** -Elements in der helpinfo-XML-Datei angegeben wird. Ersetzen Sie die älteren CAB-Dateien durch die neuen CAB-Dateien.
1. Laden Sie die aktualisierte helpinfo-XML-Datei an den Speicherort hoch, der durch den **helpinfouri** -Schlüssel im Modul Manifest angegeben wird. Ersetzen Sie die ältere helpinfo-XML-Datei durch die neue Datei.
