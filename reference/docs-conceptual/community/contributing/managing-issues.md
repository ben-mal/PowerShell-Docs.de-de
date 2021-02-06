---
title: Verwalten von Issues
description: In diesem Artikel wird erläutert, wie das PowerShell-Docs-Team Issues verwaltet.
ms.date: 12/09/2020
ms.topic: conceptual
ms.openlocfilehash: 72267137a2657f51e5f616113adf92d80647acad
ms.sourcegitcommit: 61765d08321623743dc5db5367160f6982fe7857
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/12/2020
ms.locfileid: "99598380"
---
# <a name="how-we-manage-issues"></a>Verwalten von Issues

In diesem Artikel wird beschrieben, wie Issues im Repository „PowerShell-Docs“ verwaltet werden. Dieser Artikel ist als Arbeitshilfe für Mitglieder des PowerShell-Docs-Teams gedacht. Es wird hier veröffentlicht, um Prozesstransparenz für unsere öffentlichen Mitwirkenden bereitzustellen.

## <a name="sources-of-issues"></a>Quellen von Issues

- Mitwirkende an der Community
- Interne Mitwirkende
- Transkriptionen von Kommentaren aus Kanälen in sozialen Medien
- Feedback über das Docs-Feedbackformular

## <a name="response-time-targets"></a>Zielzeit für Antworten

80% der neuen Probleme werden innerhalb von drei Werktagen geschlossen.

- Über einen Zeitraum von 1 Werktage
- Korrigieren oder ändern-10 Werktage

### <a name="labeling--milestones"></a>Bezeichnung und Meilensteine

#### <a name="label-types"></a>Bezeichnungstypen

|   type   | BESCHREIBUNG                                                         |
| -------- | ------------------------------------------------------------------- |
| Bereich     | Dient zur Angabe des Teils von PowerShell oder der Dokumentation, der im Issue diskutiert wird.<br>Nützlich für Zuständige für Features, um Issues für ihr Feature zu finden. |
| Problem    | Gibt den Typ des Problems an.                                         |
| Priorität | Gibt die Priorität des Problems an. Wertebereich 0 (hoch)-4 (niedrig)  |
| Status   | Gibt den Status des Arbeits Elements an oder warum es geschlossen wurde.          |
| Tag      | Bezeichnungen, die für die weitere Klassifizierung verwendet werden                        |
| Wartend  | Gibt an, dass wir auf ein oder mehrere andere Ereignisse warten.         |

#### <a name="milestones"></a>Meilensteine

Issues und Pull Requests (PRs) müssen mit dem entsprechenden Meilenstein gekennzeichnet sein. Wenn das Problem nicht für eine bestimmte Version gilt, wird kein Meilenstein verwendet. PRS und verwandte Probleme bei Änderungen, die noch in der PowerShell-Codebasis zusammengeführt werden müssen, sollten dem **zukünftigen** Meilenstein zugewiesen werden. Nachdem die Codeänderung gemergt wurde, ändern Sie den Meilenstein in die entsprechende Version.

|    Meilenstein     |                    BESCHREIBUNG                     |
| ---------------- | -------------------------------------------------- |
| 7.0.0            | Mit PowerShell 7.0 verknüpfte Arbeitselemente               |
| 7.1.0            | Mit PowerShell 7.1 verknüpfte Arbeitselemente               |
| 7.2.0            | Mit PowerShell 7,2 verknüpfte Arbeitselemente               |
| Zukunft           | Arbeitselemente in einer zukünftigen Version von PowerShell          |

## <a name="triage-process"></a>Sichtungsprozess

PowerShell docs Teammitglieder überprüfen die Probleme täglich und selektiert neue Probleme, sobald sie eintreffen. Das Team tagt wöchentlich, um Probleme zu erörtern, die selektiert werden müssen oder nicht aufgelöst werden müssen.

### <a name="misplaced-product-feedback"></a>Falsch gemeldetes Produktfeedback

- Geben Sie einen Kommentar ein, der den Kunden zum richtigen Feedback Kanal umleitet.
- Optional: Kopieren Sie das Issue an die entsprechende Stelle für Produktfeedback, fügen Sie einen Link zu dem kopierten Element hinzu, und schließen Sie das Issue. Kopieren Sie Issues NICHT in UserVoice.

  Der Standard Speicherort für PowerShell-Probleme ist [https://github.com/PowerShell/PowerShell/issues/new/choose](https://github.com/PowerShell/PowerShell/issues/new/choose) .

  Die folgenden Themenbereiche haben unterschiedliche Speicherorte für Probleme:

  | Themen |                                                     Produktfeedback-URL                                                     |
  | -------- | ---------------------------------------------------------------------------------------------------------------------------- |
  | DSC      | [https://windowsserver.uservoice.com/forums/301869-powershell](https://windowsserver.uservoice.com/forums/301869-powershell) |
  | Katalog  | [https://github.com/powershell/powershellgallery/issues/new](https://github.com/powershell/powershellgallery/issues/new)     |
  | jea      | [https://github.com/powershell/jea/issues/new](https://github.com/powershell/jea/issues/new)                                 |
  | wmf      | [https://windowsserver.uservoice.com/forums/301869-powershell](https://windowsserver.uservoice.com/forums/301869-powershell) |

### <a name="support-requests"></a>Supportanfragen

- Wenn die Supportfrage einfach ist, beantworten Sie sie höflich, und schließen Sie das Issue.
- Wenn die Frage komplizierter ist oder der Fragensteller mit weiteren Fragen antwortet, leiten Sie ihn an Foren und Supportkanäle weiter. Vorgeschlagener Text für die Umleitung zu Foren:

  ```Markdown
  > This is not the right forum for these kinds of questions. Try posting your question in a
  > community support forum. For a list of community forums see:
  > https://docs.microsoft.com/powershell/scripting/community/community-support
  ```

### <a name="code-of-conduct-violations"></a>Verstöße gegen Verhaltensregeln

- Bearbeiten Sie das Issue, um ggf. anstößige Inhalte zu entfernen.
- Geben Sie einen Kommentar ein, dass es sich bei dem Issue um Spam handelt, schließen Sie das Issue, und sperren Sie es anschließend, um weitere Kommentare zu verhindern.
- Jede Verletzung sollte in der wöchentlichen Selektion erläutert werden, um den Bedarf an weiteren Maßnahmen zu ermitteln (melden Sie GitHub oder Microsoft legal).
