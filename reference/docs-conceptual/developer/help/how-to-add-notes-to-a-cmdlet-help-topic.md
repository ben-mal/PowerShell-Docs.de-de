---
title: Hinzufügen von Anmerkungen zu einem Cmdlet-Hilfethema
ms.date: 10/20/2020
ms.openlocfilehash: 7f8be34a82de2c12cfd2a05deed139ddb30da95f
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "92298308"
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
