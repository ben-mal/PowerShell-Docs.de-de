---
title: Einstieg in die Mitwirkung an PowerShell-Dokumentation
description: Dieser Artikel bietet einen Überblick über die ersten Schritte als Mitwirkender an der PowerShell-Dokumentation.
ms.date: 12/09/2020
ms.topic: conceptual
ms.openlocfilehash: ddcbf79de1ab05b901ce1abd67f65b2524ed164d
ms.sourcegitcommit: 61765d08321623743dc5db5367160f6982fe7857
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/12/2020
ms.locfileid: "99599175"
---
# <a name="get-started-contributing-to-powershell-documentation"></a>Einstieg in die Mitwirkung an PowerShell-Dokumentation

Dieser Artikel bietet einen Überblick über die ersten Schritte als Mitwirkender an der PowerShell-Dokumentation.

## <a name="powershell-docs-structure"></a>Struktur von „PowerShell-Docs“

Das [PowerShell-docs-Repository][psdocs] ist in zwei Inhalts Gruppen unterteilt: Referenz und konzeptionell.

### <a name="reference-content"></a>Referenzinhalt

Der Referenz Inhalt ist die PowerShell-Cmdlet-Referenz für die Cmdlets, die in PowerShell ausgeliefert werden.
Der [Verweis][ref] wird in den Ordner Versionen (5,1, 7,0, 7,1 und 7,2) gesammelt. Dieser Inhalt enthält nur die Cmdlet-Referenz für die Module, die mit PowerShell ausgeliefert werden. Dieser Inhalt wird auch zum Erstellen von Hilfe Informationen verwendet, die vom `Get-Help` Cmdlet angezeigt werden.

### <a name="conceptual-content"></a>Konzeptionelle Inhalte

Die konzeptionelle Dokumentation enthält den folgenden Inhalt:

- Versionshinweise
- Setupanweisungen
- Beispiel Skripts und Anleitungen
- DSC-Dokumentation
- SDK-Dokumentation

Die [konzeptionelle Dokumentation][conceptual] ist nicht nach Version organisiert. Alle Artikel werden für jede Version von PowerShell angezeigt. Wir arbeiten daran, versionsspezifische Artikel zu erstellen. Wenn dieses Feature in unserer Dokumentation verfügbar ist, wird dieses Handbuch mit den entsprechenden Informationen aktualisiert.

> [!NOTE]
> Jedes Mal, wenn ein konzeptioneller Artikel hinzugefügt, entfernt oder umbenannt wird, muss das Inhaltsverzeichnis aktualisiert und in das Pull Request eingeschlossen werden.

## <a name="creating-new-articles"></a>Erstellen neuer Artikel

Für jedes neue Dokument, das Sie mitwirken möchten, muss ein GitHub-Problem erstellt werden. Überprüfen Sie, ob vorhandene Probleme vorhanden sind. Zugewiesene Probleme gelten als `in progress` . Wenn Sie an einem Problem zusammenarbeiten möchten, wenden Sie sich an die Person, die dem Problem zugewiesen ist.

Erstellen Sie, ähnlich wie beim PowerShell- [RFC-Prozess][rfc], ein Problem, bevor Sie den Inhalt schreiben. Das Problem stellt sicher, dass Sie keine Zeit und keinen Aufwand für die Arbeit verschwenden, die vom PowerShell-Docs Team abgelehnt wird. Das Problem ermöglicht es uns, sich über den Umfang des Inhalts und den Speicherort der PowerShell-Dokumentation zu informieren. Alle Artikel müssen im Inhaltsverzeichnis (Inhaltsverzeichnis) enthalten sein. Der vorgeschlagene Speicherort sollte in der Problem Diskussion enthalten sein.

> [!NOTE]
> Das Inhaltsverzeichnis für Referenz Inhalte wird vom Veröffentlichungs System automatisch generiert. Sie müssen das Inhaltsverzeichnis nicht aktualisieren.

## <a name="updating-existing-articles"></a>Aktualisieren vorhandener Artikel

Cmdlet-Referenz Artikel werden ggf. in allen Versionen von PowerShell dupliziert, die in diesem Repository verwaltet werden. Wenn Sie ein Problem über eine Cmdlet-Referenz oder einen `About_` Artikel melden, müssen Sie angeben, welche Versionen von dem Problem betroffen sind. Die Issue-Vorlage in GitHub enthält eine Checkliste der Versionen. Verwenden Sie die Kontrollkästchen, um anzugeben, welche Versionen des Inhalts betroffen sind.

Überprüfen Sie die gesamte Version des Artikels, um festzustellen, ob die gleiche Änderung in den anderen Versionen erforderlich ist. Wenden Sie die entsprechenden Änderungen auf jede Version der Datei an.

## <a name="localized-content"></a>Lokalisierter Inhalt

Die PowerShell-Dokumentation ist auf Englisch geschrieben und in 17 andere Sprachen übersetzt. Der englische Inhalt wird im GitHub-Repository mit dem Namen gespeichert `MicrosoftDocs/PowerShell-Docs` . Der lokalisierte Inhalt wird in einem separaten Repository für jede Sprache gespeichert. Die Repository verwenden denselben basename, aber fügen den Namen des Gebiets Schemas am Ende hinzu. Beispielsweise `MicrosoftDocs/PowerShell-Docs.de-de` enthält den Inhalt, der in Deutsch übersetzt wurde.

Im Allgemeinen sollten Probleme und Änderungen an das englische Repository übermittelt werden. Alle Übersetzungen beginnen zuerst mit dem englischen Inhalt. Wir verwenden sowohl die Übersetzung von Menschen als auch Maschinelles

| Übersetzungsmethode  |                              Sprachen                               |
| ------------------- | -------------------------------------------------------------------- |
| Menschliche Übersetzung   | de-de, es-es, fr-FR, IT-IT, ja-JP, ko-kr, pt-br, ru-ru, zh-cn, zh-tw |
| Maschinelle Übersetzung | CS-CZ, HU-HU, nl-nl, PL-PL, pt-pt, SV-SE, TR-TR                      |

Der von der maschinellen Übersetzung übersetzte Inhalt führt möglicherweise nicht immer zu richtigen Wort Auswahl und Grammatik. Wenn Sie einen Fehler in der Übersetzung für eine beliebige Sprache und nicht in den technischen Details des Artikels finden, öffnen Sie ein Problem im lokalisierten Repository. Erläutern Sie, warum die Übersetzung falsch ist. Unser Lokalisierungsteam prüft diese Probleme und reagiert darauf.

## <a name="next-steps"></a>Nächste Schritte

Es gibt zwei gängige Methoden zum Übermitteln von Änderungen in GitHub. Beide Methoden werden im Leitfaden für den zentralen Mitwirkenden beschrieben:

1. Sie können in der GitHub-Webschnittstelle [schnelle Änderungen an vorhandenen Dokumenten](/contribute/#quick-edits-to-existing-documents) vornehmen.
1. Verwenden Sie den [vollständigen GitHub-Workflow][making-changes] zum Hinzufügen neuer Artikel, zum Aktualisieren mehrerer Dateien oder zu anderen großen Änderungen.

Vor dem Starten von Änderungen sollten Sie eine Verzweigung des PowerShell-Docs-Repository erstellen. Die Änderungen sollten in einer funktionierenden Verzweigung in Ihrer Kopie der PowerShell-Dokumente vorgenommen werden. Wenn Sie die Methode für die **schnelle Bearbeitung** in GitHub verwenden, werden diese Schritte für Sie erledigt. Wenn Sie den **vollständigen GitHub-Workflow** verwenden, müssen Sie für die [lokale][fork]Ausführung eingerichtet sein.

Beide Methoden enden mit der Erstellung eines Pull Requests (PR). Weitere Informationen und bewährte Methoden finden Sie unter [Senden einer Pull Request](pull-requests.md) .

<!--link refs-->
[conceptual]: https://github.com/MicrosoftDocs/PowerShell-Docs/tree/staging/reference/docs-conceptual
[fork]: /contribute/get-started-setup-local#fork-the-repository
[making-changes]: /contribute/how-to-write-workflows-major#making-your-changes
[psdocs]: https://github.com/MicrosoftDocs/PowerShell-Docs
[ref]: https://github.com/MicrosoftDocs/PowerShell-Docs/tree/staging/reference
[rfc]: https://github.com/PowerShell/powershell-rfc/blob/master/RFC0000-RFC-Process.md
