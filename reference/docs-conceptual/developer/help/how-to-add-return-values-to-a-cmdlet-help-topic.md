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
# <a name="how-to-add-return-values-to-a-cmdlet-help-topic"></a><span data-ttu-id="7ba77-103">Hinzufügen von Rückgabewerten zu einem Cmdlet-Hilfethema</span><span class="sxs-lookup"><span data-stu-id="7ba77-103">How to Add Return Values to a Cmdlet Help Topic</span></span>

<span data-ttu-id="7ba77-104">In diesem Abschnitt wird beschrieben, wie Sie einem PowerShell-Cmdlet-Hilfethema einen Ausgaben Abschnitt hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="7ba77-104">This section describes how to add an OUTPUTS section to a PowerShell cmdlet Help topic.</span></span> <span data-ttu-id="7ba77-105">Im Abschnitt " **Outputs** " werden die .NET-Klassen von Objekten aufgelistet, die vom Cmdlet zurückgegeben oder an die Pipeline übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="7ba77-105">The **OUTPUTS** section lists the .NET classes of objects that the cmdlet returns or passes down the pipeline.</span></span>

<span data-ttu-id="7ba77-106">Es gibt keine Beschränkung für die Anzahl der Klassen **, die Sie dem Ausgabe Abschnitt** hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="7ba77-106">There is no limit to the number of classes that you can add to the **OUTPUTS** section.</span></span> <span data-ttu-id="7ba77-107">Die Rückgabe Typen eines Cmdlets werden in einen- `<command:returnValues>` Knoten eingeschlossen, wobei jede Klasse in ein- `<command:returnValue>` Element eingeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="7ba77-107">The return types of a cmdlet are enclosed in a `<command:returnValues>` node, with each class enclosed in a `<command:returnValue>` element.</span></span>

<span data-ttu-id="7ba77-108">Wenn ein Cmdlet keine Ausgabe generiert, verwenden Sie diesen Abschnitt, um anzugeben, dass keine Ausgabe vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="7ba77-108">If a cmdlet does not generate any output, use this section to indicate that there is no output.</span></span> <span data-ttu-id="7ba77-109">Schreiben Sie z. b. anstelle des Klassen namens **None** , und stellen Sie eine kurze Erläuterung bereit.</span><span class="sxs-lookup"><span data-stu-id="7ba77-109">For example, in place of the class name, write **None** and provide a brief explanation.</span></span> <span data-ttu-id="7ba77-110">Wenn das Cmdlet die Ausgabe bedingt generiert, verwenden Sie diesen Knoten, um die Bedingungen zu erläutern und die bedingte Ausgabe zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="7ba77-110">If the cmdlet generates output conditionally, use this node to explain the conditions and describe the conditional output.</span></span>

<span data-ttu-id="7ba77-111">Das Schema enthält zwei- `<maml:description>` Elemente in jedem- `<command:returnValue>` Element.</span><span class="sxs-lookup"><span data-stu-id="7ba77-111">The schema includes two `<maml:description>` elements in each `<command:returnValue>` element.</span></span>
<span data-ttu-id="7ba77-112">Das- `Get-Help` Cmdlet zeigt jedoch nur den Inhalt des- `<command:returnValue>/<maml:description>` Elements an.</span><span class="sxs-lookup"><span data-stu-id="7ba77-112">However, the `Get-Help` cmdlet displays only the content of the `<command:returnValue>/<maml:description>` element.</span></span>

<span data-ttu-id="7ba77-113">Ab PowerShell 3,0 `Get-Help` zeigt das Cmdlet den Inhalt des-Elements an `<maml:uri>` .</span><span class="sxs-lookup"><span data-stu-id="7ba77-113">Beginning in PowerShell 3.0, the `Get-Help` cmdlet displays the content of the `<maml:uri>` element.</span></span>
<span data-ttu-id="7ba77-114">Mit diesem Element können Sie Benutzer an Themen weiterleiten, in denen die .NET-Klasse beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="7ba77-114">This element lets you direct users to topics that describe the .NET class.</span></span>

<span data-ttu-id="7ba77-115">Der folgende XML-Code zeigt den- `<maml:returnValues>` Knoten.</span><span class="sxs-lookup"><span data-stu-id="7ba77-115">The following XML shows the `<maml:returnValues>` node.</span></span>

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

<span data-ttu-id="7ba77-116">Der folgende XML-Code zeigt ein Beispiel für die Verwendung des- `<maml:returnValues>` Knotens zum Dokumentieren eines Ausgabe Typs.</span><span class="sxs-lookup"><span data-stu-id="7ba77-116">The following XML shows an example of using the `<maml:returnValues>` node to document an output type.</span></span>

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
