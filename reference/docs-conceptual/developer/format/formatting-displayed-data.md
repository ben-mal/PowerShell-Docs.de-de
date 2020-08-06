---
title: Formatieren angezeigter Daten | Microsoft-Dokumentation
ms.date: 09/12/2016
ms.openlocfilehash: 97d23b3079b2779e518b6b6d2f2ac0c5e9d1f3a3
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781510"
---
# <a name="formatting-displayed-data"></a><span data-ttu-id="a99b8-102">Formatieren von angezeigten Daten</span><span class="sxs-lookup"><span data-stu-id="a99b8-102">Formatting Displayed Data</span></span>

<span data-ttu-id="a99b8-103">Sie können angeben, wie die einzelnen Datenpunkte in der Listen-, Tabellen-oder breiten Ansicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="a99b8-103">You can specify how the individual data points in your List, Table, or Wide view are displayed.</span></span> <span data-ttu-id="a99b8-104">Sie können das- `FormatString` Element verwenden, wenn Sie die Elemente der Ansicht definieren, oder Sie können das- `ScriptBlock` Element verwenden, um die- `FormatString` Methode für die Daten aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="a99b8-104">You can use the `FormatString` element when defining the items of your view, or you can use the `ScriptBlock` element to call the `FormatString` method on the data.</span></span>

## <a name="using-the-formatstring-element"></a><span data-ttu-id="a99b8-105">Verwenden des FormatString-Elements</span><span class="sxs-lookup"><span data-stu-id="a99b8-105">Using the FormatString Element</span></span>

<span data-ttu-id="a99b8-106">Im folgenden Beispiel wird der Wert der- `TotalProcessorTime` Eigenschaft des [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) -Objekts mit dem FormatString-Element formatiert.</span><span class="sxs-lookup"><span data-stu-id="a99b8-106">In the following example the value of the `TotalProcessorTime` property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object is formatted using the FormatString element.</span></span> <span data-ttu-id="a99b8-107">die- `TotalProcessorTime` Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="a99b8-107">the `TotalProcessorTime` property</span></span>

```
<TableColumnItem>
  <PropertyName>TotalProcessorTime</PropertyName>
  <FormatString>{0:MMM}{0:dd}{0:HH}:{0:mm}</FormatString>
</TableColumnItem>
```
