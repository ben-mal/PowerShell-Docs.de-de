---
ms.date: 09/12/2016
ms.topic: reference
title: Hinzufügen von Rückgabewerten zu einem Cmdlet-Hilfethema
description: Hinzufügen von Rückgabewerten zu einem Cmdlet-Hilfethema
ms.openlocfilehash: 8c556821a257451a320916231cb20fc82e75ebb4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "94389741"
---
# <a name="how-to-add-return-values-to-a-cmdlet-help-topic"></a>Hinzufügen von Rückgabewerten zu einem Cmdlet-Hilfethema

In diesem Abschnitt wird beschrieben, wie Sie einem PowerShell-Cmdlet-Hilfethema einen Ausgaben Abschnitt hinzufügen. Im Abschnitt " **Outputs** " werden die .NET-Klassen von Objekten aufgelistet, die vom Cmdlet zurückgegeben oder an die Pipeline übergeben werden.

Es gibt keine Beschränkung für die Anzahl der Klassen **, die Sie dem Ausgabe Abschnitt** hinzufügen können. Die Rückgabe Typen eines Cmdlets werden in einen- `<command:returnValues>` Knoten eingeschlossen, wobei jede Klasse in ein- `<command:returnValue>` Element eingeschlossen ist.

Wenn ein Cmdlet keine Ausgabe generiert, verwenden Sie diesen Abschnitt, um anzugeben, dass keine Ausgabe vorhanden ist. Schreiben Sie z. b. anstelle des Klassen namens **None** , und stellen Sie eine kurze Erläuterung bereit. Wenn das Cmdlet die Ausgabe bedingt generiert, verwenden Sie diesen Knoten, um die Bedingungen zu erläutern und die bedingte Ausgabe zu beschreiben.

Das Schema enthält zwei- `<maml:description>` Elemente in jedem- `<command:returnValue>` Element.
Das- `Get-Help` Cmdlet zeigt jedoch nur den Inhalt des- `<command:returnValue>/<maml:description>` Elements an.

Ab PowerShell 3,0 `Get-Help` zeigt das Cmdlet den Inhalt des-Elements an `<maml:uri>` .
Mit diesem Element können Sie Benutzer an Themen weiterleiten, in denen die .NET-Klasse beschrieben wird.

Der folgende XML-Code zeigt den- `<maml:returnValues>` Knoten.

```xml
<command:returnValues>
  <command:returnValue>
    <dev:type>
      <maml:name> Class Name </maml:name>
      <maml:uri>  URI of a topic that describes the class </maml:uri>
      <maml:description/>
    </dev:type>
    <maml:description>
       <maml:para> Brief description <maml:para>

</maml:description>
  </command: returnValue>
</command: returnValues>
```

Der folgende XML-Code zeigt ein Beispiel für die Verwendung des- `<maml:returnValues>` Knotens zum Dokumentieren eines Ausgabe Typs.

```xml
<command:returnValues>
  <command:returnValue>
    <dev:type>
      <maml:name> System.DateTime </maml:name>
      <maml:uri>  https://docs.microsoft.com/dotnet/api/system.datetime </maml:uri>
      <maml:description/>
    </dev:type>
    <maml:description>
      <maml:para> Get-Date returns a DateTime object. <maml:para>
    </maml:description>
  </command: returnValue>
</command: returnValues>
```
