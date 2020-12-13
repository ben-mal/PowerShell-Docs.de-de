---
ms.date: 09/12/2016
ms.topic: reference
title: Formatieren von angezeigten Daten
description: Formatieren von angezeigten Daten
ms.openlocfilehash: 40f6b3b4fa36062ee0bad3f197ad159f571445c8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667860"
---
# <a name="formatting-displayed-data"></a><span data-ttu-id="dc576-103">Formatieren von angezeigten Daten</span><span class="sxs-lookup"><span data-stu-id="dc576-103">Formatting Displayed Data</span></span>

<span data-ttu-id="dc576-104">Sie können angeben, wie die einzelnen Datenpunkte in der Listen-, Tabellen-oder breiten Ansicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="dc576-104">You can specify how the individual data points in your List, Table, or Wide view are displayed.</span></span> <span data-ttu-id="dc576-105">Sie können das- `FormatString` Element verwenden, wenn Sie die Elemente der Ansicht definieren, oder Sie können das- `ScriptBlock` Element verwenden, um die- `FormatString` Methode für die Daten aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="dc576-105">You can use the `FormatString` element when defining the items of your view, or you can use the `ScriptBlock` element to call the `FormatString` method on the data.</span></span>

## <a name="using-the-formatstring-element"></a><span data-ttu-id="dc576-106">Verwenden des FormatString-Elements</span><span class="sxs-lookup"><span data-stu-id="dc576-106">Using the FormatString Element</span></span>

<span data-ttu-id="dc576-107">Im folgenden Beispiel wird der Wert der- `TotalProcessorTime` Eigenschaft des [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) -Objekts mit dem FormatString-Element formatiert.</span><span class="sxs-lookup"><span data-stu-id="dc576-107">In the following example the value of the `TotalProcessorTime` property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object is formatted using the FormatString element.</span></span> <span data-ttu-id="dc576-108">die- `TotalProcessorTime` Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="dc576-108">the `TotalProcessorTime` property</span></span>

```
<TableColumnItem>
  <PropertyName>TotalProcessorTime</PropertyName>
  <FormatString>{0:MMM}{0:dd}{0:HH}:{0:mm}</FormatString>
</TableColumnItem>
```
