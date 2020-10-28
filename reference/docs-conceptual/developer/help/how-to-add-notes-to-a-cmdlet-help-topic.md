---
ms.date: 10/20/2020
ms.topic: reference
title: Hinzufügen von Anmerkungen zu einem Cmdlet-Hilfethema
description: Hinzufügen von Anmerkungen zu einem Cmdlet-Hilfethema
ms.openlocfilehash: 61363c26ab0172277d1332ed1e9de080d8da200c
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92659570"
---
# <a name="how-to-add-notes-to-a-cmdlet-help-topic"></a>Hinzufügen von Anmerkungen zu einem Cmdlet-Hilfethema

In diesem Abschnitt wird beschrieben, wie Sie einem PowerShell-Cmdlet-Hilfethema einen Abschnitt **NOTES** (Notizen) hinzufügen. Der Abschnitt **NOTES** wird verwendet, um Details zu erläutern, die nicht recht in die anderen strukturierten Abschnitte passen, zum Beispiel ausführlichere Erläuterungen eines Parameters. Dieser Inhalt enthält möglicherweise auch Kommentare zu Themen, wie das Cmdlet mit einem bestimmten Anbieter funktioniert, einige eindeutige aber wichtige Verwendungsmöglichkeiten des Cmdlets oder auch Möglichkeiten zum Vermeiden möglicher Fehlerbedingungen.

Der Abschnitt **NOTES** ist mit einem einzelnen `<maml:alertset>`-Knoten definiert. Es gibt keine Beschränkung für die Anzahl von Notizen, die Sie zu einem „Notes“-Abschnitt hinzufügen können. Fügen Sie für jeden Hinweis dem `<maml:alertset>`-Knoten ein `<maml:alert>`-Tagpaar hinzu. Der Inhalt der einzelnen Notiz wird innerhalb eines `<maml:para>`-Tagpaares hinzugefügt. Verwenden Sie leere `<maml:para>`-Tags für den Abstand.

```xml
<maml:alertSet>
  <maml:title>Optional title for Note</maml:title>
  <maml:alert>
    <maml:para>Note 1</maml:para>
    <maml:para>Note a</maml:para>
  </maml:alert>
  <maml:alert>
    <maml:para>Note 2</maml:para>
  </maml:alert>
</maml:alertSet>
```
