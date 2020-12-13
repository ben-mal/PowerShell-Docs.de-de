---
ms.date: 09/12/2016
ms.topic: reference
title: Hinzufügen von zugehörigen Verknüpfungen zu einem Cmdlet-Hilfethema
description: Hinzufügen von zugehörigen Verknüpfungen zu einem Cmdlet-Hilfethema
ms.openlocfilehash: 7f1baefea69310bdf835c52461f8d3f49c4d94e8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92661989"
---
# <a name="how-to-add-related-links-to-a-cmdlet-help-topic"></a>Hinzufügen von zugehörigen Verknüpfungen zu einem Cmdlet-Hilfethema

In diesem Abschnitt wird beschrieben, wie Sie Verweise auf andere Inhalte hinzufügen, die mit einem Hilfethema für PowerShell-Cmdlets verknüpft sind. Da diese Verweise in einem Befehlsfenster angezeigt werden, werden Sie nicht direkt mit dem Inhalt verknüpft, auf den verwiesen wird.

In den Hilfe Themen zu Cmdlets, die in PowerShell enthalten sind, verweisen diese Links auf andere Cmdlets, konzeptionelle Inhalte ( `about_` ) und andere Dokumente und Hilfedateien, die nicht mit PowerShell verknüpft sind.

Der folgende XML-Code zeigt, wie Sie einen **relatedLinks** -Knoten hinzufügen, der zwei Verweise auf Verwandte Themen enthält.

```xml
<maml:relatedLinks>
  <maml:navigationLink>
    <maml:linkText>Topic-name</maml:linkText>
  </maml:navigationLink>
  <maml:navigationLink>
    <maml:linkText>Topic-name</maml:linkText>
  </maml:navigationLink>
</ maml:relatedLinks >
```
