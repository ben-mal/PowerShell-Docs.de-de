---
title: Übermitteln von Pull Requests
description: In diesem Artikel wird erläutert, wie Pull Requests an das PowerShell-Docs-Team übermittelt werden.
ms.date: 12/09/2020
ms.topic: conceptual
ms.openlocfilehash: 1a21c25e19189aec4f48ad034147b02f4f804f9d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "99603911"
---
# <a name="how-to-submit-pull-requests"></a>Übermitteln von Pull Requests

Wenn Sie inhaltliche Änderungen vornehmen möchten, übermitteln Sie einen Pull Request (PR) aus Ihrer Fork. Eine Pull Request muss überprüft werden, bevor Sie zusammengeführt werden kann. Um optimale Ergebnisse zu erzielen, überprüfen Sie die [Checkliste für die Bearbeitung](editorial-checklist.md), bevor Sie Ihren Pull Request einreichen.

## <a name="using-git-branches"></a>Verwenden von git-branches

Der standardbranch für PowerShell-Docs ist die `staging` Verzweigung. Änderungen, die an arbeitsbranches vorgenommen werden, werden in der `staging` Verzweigung zusammengeführt, bevor Sie veröffentlicht werden. Die `staging` Verzweigung wird `live` alle Wochentage um 3:00 Uhr (Pacific Time) in der Verzweigung zusammengeführt. Der `live` Branch enthält den Inhalt, der in docs.Microsoft.com veröffentlicht wird.

Erstellen Sie vor dem Starten von Änderungen einen arbeitbranch in Ihrer lokalen Kopie des PowerShell-Docs Repository. Wenn Sie lokal arbeiten, achten Sie darauf, das lokale Repository zu synchronisieren, bevor Sie den arbeitsbranch erstellen. Der arbeitbranch sollte aus einer Update-to-date-Kopie der `staging` Verzweigung erstellt werden.

Alle Pull Requests müssen den Branch `staging` als Ziel haben. Senden Sie keine Änderungen an die `live` Verzweigung.
Änderungen, die im Branch `staging` vorgenommen werden, werden in den Branch `live` gemergt, wobei alle Änderungen an `live` überschrieben werden.

## <a name="make-the-pull-request-process-work-better-for-everyone"></a>Verbessern des Pull Request-Prozesses für alle Beteiligten

Je einfacher und zielgerichteter Sie Ihren PR gestalten, desto schneller kann er überprüft und gemergt werden.

### <a name="avoid-pull-requests-that-update-large-numbers-of-files-or-contain-unrelated-changes"></a>Vermeiden von Pull Requests, die eine große Anzahl von Dateien aktualisieren oder nicht verknüpfte Änderungen enthalten

Vermeiden Sie das Erstellen von PRs mit unzusammenhängenden Änderungen. Trennen Sie kleinere Updates bestehender Artikel von neuen Artikeln oder größeren Neufassungen. Arbeiten Sie an diesen Änderungen in separaten Bearbeitungsbranches.

Bei Massenänderungen werden PRs mit einer großen Anzahl geänderter Dateien erstellt. Beschränken Sie Ihre PRs auf maximal 50 geänderte Dateien. Große PRs sind schwer zu überprüfen und anfälliger für Fehler.

### <a name="renaming-or-deleting-files"></a>Umbenennen oder Löschen von Dateien

Beim Umbenennen oder Löschen von Dateien muss ein Problem mit dem PR bestehen. In diesem Issue muss die Notwendigkeit des Umbenennens oder Löschens der Dateien diskutiert werden.

Vermeiden Sie die Vermischung von Inhaltsergänzungen oder -änderungen mit Dateiumbenennungen und -löschungen. Alle Dateien, die umbenannt oder gelöscht werden, müssen der globalen Umleitungs Datei hinzugefügt werden. Aktualisieren Sie nach Möglichkeit alle Dateien, die mit dem umbenannten oder gelöschten Inhalt verknüpft sind, einschließlich aller Inhaltsverzeichnis Dateien.

## <a name="docs-pr-validation-service"></a>Validierungsdienst für auf die Dokumentation bezogene PRs

Der Validierungs Dienst von docs PR ist eine GitHub-APP, die Validierungsregeln für Ihre Änderungen ausführt. Sie müssen alle Fehler oder Warnungen beheben, die vom Validierungs Dienst gemeldet werden.

Sie erkennen das folgende Verhalten:

1. Sie übermitteln einen PR.
1. Im GitHub-Kommentar, der den Status Ihres Pull Requests anzeigt, sehen Sie den für das Repository aktivierten Zustand „Überprüfungen“. In diesem Beispiel sind zwei Überprüfungen aktiviert: "Commit Validation" und "openpublishing. Build":

   ![Überprüfungszustand: einige Überprüfungen sind fehlgeschlagen](media/pull-requests/validation-failed.png)

   Der Build kann fortgesetzt werden, auch wenn die Überprüfung des Commits fehlschlägt.

1. Klicken Sie auf **Details**, um weitere Informationen zu erhalten.
1. Auf der Seite „Details“ werden alle fehlgeschlagenen Validierungsprüfungen angezeigt, und zwar mit Informationen zur Behebung der Issues.
1. Wenn die Validierung erfolgreich ist, wird dem PR der folgende Kommentar hinzugefügt:

   ![Überprüfungszustand: Erfolg](media/pull-requests/build-validation.png)

> [!NOTE]
> Wenn Sie ein externer Mitwirkender (kein Mitarbeiter von Microsoft) sind, haben Sie keinen Zugriff auf die detaillierten Buildberichte oder Vorschaulinks.

Wenn der PR überprüft wird, werden Sie möglicherweise aufgefordert, Änderungen vorzunehmen oder Validierungs Warnmeldungen zu beheben. Das PowerShell-Docs Team kann Ihnen helfen, Validierungs Fehler und redaktionelle Anforderungen zu verstehen.

## <a name="next-steps"></a>Nächste Schritte

[Styleguide für die PowerShell-Dokumentation](powershell-style-guide.md)

## <a name="additional-resources"></a>Zusätzliche Ressourcen

[Verwalten von Pull Requests](managing-pull-requests.md)

<!--link refs-->
[fork]: /contribute/get-started-setup-local#fork-the-repository
