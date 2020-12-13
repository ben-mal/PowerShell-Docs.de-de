---
ms.date: 10/20/2020
ms.topic: reference
title: Hinzufügen von Anmerkungen zu einem Cmdlet-Hilfethema
description: Hinzufügen von Anmerkungen zu einem Cmdlet-Hilfethema
ms.openlocfilehash: 61363c26ab0172277d1332ed1e9de080d8da200c
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659570"
---
# <a name="how-to-add-notes-to-a-cmdlet-help-topic"></a><span data-ttu-id="63c82-103">Hinzufügen von Anmerkungen zu einem Cmdlet-Hilfethema</span><span class="sxs-lookup"><span data-stu-id="63c82-103">How to Add Notes to a Cmdlet Help Topic</span></span>

<span data-ttu-id="63c82-104">In diesem Abschnitt wird beschrieben, wie Sie einem PowerShell-Cmdlet-Hilfethema einen Abschnitt **NOTES** (Notizen) hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="63c82-104">This section describes how to add a **NOTES** section to a PowerShell cmdlet Help topic.</span></span> <span data-ttu-id="63c82-105">Der Abschnitt **NOTES** wird verwendet, um Details zu erläutern, die nicht recht in die anderen strukturierten Abschnitte passen, zum Beispiel ausführlichere Erläuterungen eines Parameters.</span><span class="sxs-lookup"><span data-stu-id="63c82-105">The **NOTES** section is used to explain details that do not fit easily into the other structured sections, such as a more detailed explanation of a parameter.</span></span> <span data-ttu-id="63c82-106">Dieser Inhalt enthält möglicherweise auch Kommentare zu Themen, wie das Cmdlet mit einem bestimmten Anbieter funktioniert, einige eindeutige aber wichtige Verwendungsmöglichkeiten des Cmdlets oder auch Möglichkeiten zum Vermeiden möglicher Fehlerbedingungen.</span><span class="sxs-lookup"><span data-stu-id="63c82-106">This content could include comments on how the cmdlet works with a specific provider, some unique, yet important, uses of the cmdlet, or ways to avoid possible error conditions.</span></span>

<span data-ttu-id="63c82-107">Der Abschnitt **NOTES** ist mit einem einzelnen `<maml:alertset>`-Knoten definiert.</span><span class="sxs-lookup"><span data-stu-id="63c82-107">The **NOTES** section is defined using a single `<maml:alertset>` node.</span></span> <span data-ttu-id="63c82-108">Es gibt keine Beschränkung für die Anzahl von Notizen, die Sie zu einem „Notes“-Abschnitt hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="63c82-108">There are no limits to the number of notes that you can add to a Notes section.</span></span> <span data-ttu-id="63c82-109">Fügen Sie für jeden Hinweis dem `<maml:alertset>`-Knoten ein `<maml:alert>`-Tagpaar hinzu.</span><span class="sxs-lookup"><span data-stu-id="63c82-109">For each note, add a pair of `<maml:alert>` tags to the `<maml:alertset>` node.</span></span> <span data-ttu-id="63c82-110">Der Inhalt der einzelnen Notiz wird innerhalb eines `<maml:para>`-Tagpaares hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="63c82-110">The content of each note is added within a set of `<maml:para>` tags.</span></span> <span data-ttu-id="63c82-111">Verwenden Sie leere `<maml:para>`-Tags für den Abstand.</span><span class="sxs-lookup"><span data-stu-id="63c82-111">Use blank `<maml:para>` tags for spacing.</span></span>

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
