---
ms.date: 09/13/2016
ms.topic: reference
title: Benutzerdefinierte Formatierungsdateien
description: Benutzerdefinierte Formatierungsdateien
ms.openlocfilehash: 16e1c1046e25b35ff346585a5fd930c449c04bf8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653236"
---
# <a name="custom-formatting-files"></a><span data-ttu-id="d1c39-103">Benutzerdefinierte Formatierungsdateien</span><span class="sxs-lookup"><span data-stu-id="d1c39-103">Custom Formatting Files</span></span>

<span data-ttu-id="d1c39-104">Das Anzeige Format für die von Cmdlets, Funktionen und Skripts zurückgegebenen Objekte wird mithilfe von Formatierungs Dateien (format.ps1XML-Dateien) definiert.</span><span class="sxs-lookup"><span data-stu-id="d1c39-104">The display format for the objects returned by cmdlets, functions, and scripts are defined using formatting files (format.ps1xml files).</span></span> <span data-ttu-id="d1c39-105">Einige dieser Dateien werden von Windows PowerShell bereitgestellt, um das Standard Anzeige Format für die von Windows PowerShell-Cmdlets zurückgegebenen Objekte zu definieren.</span><span class="sxs-lookup"><span data-stu-id="d1c39-105">Several of these files are provided by Windows PowerShell to define the default display format for those objects returned by Windows PowerShell cmdlets.</span></span> <span data-ttu-id="d1c39-106">Sie können jedoch auch eigene benutzerdefinierte Formatierungs Dateien erstellen, um die Standard Anzeige Formate zu überschreiben oder die Anzeige von Objekten zu definieren, die von ihren eigenen Befehlen zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d1c39-106">However, you can also create your own custom formatting files to overwrite the default display formats or to define the display of objects returned by your own commands.</span></span>

<span data-ttu-id="d1c39-107">Windows PowerShell verwendet die Daten in diesen Formatierungs Dateien, um zu bestimmen, was angezeigt wird und wie die Daten formatiert werden.</span><span class="sxs-lookup"><span data-stu-id="d1c39-107">Windows PowerShell uses the data in these formatting files to determine what is displayed and how the data is formatted.</span></span> <span data-ttu-id="d1c39-108">Die angezeigten Daten können die Eigenschaften eines Objekts oder den Wert eines Skript Blocks enthalten.</span><span class="sxs-lookup"><span data-stu-id="d1c39-108">The displayed data can include the properties of an object or the value of a script block.</span></span>  <span data-ttu-id="d1c39-109">Skriptblöcke werden verwendet, wenn Sie einen Wert anzeigen möchten, der nicht direkt aus den Eigenschaften eines Objekts verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="d1c39-109">Script blocks are used if you want to display some value that is not available directly from the properties of an object.</span></span> <span data-ttu-id="d1c39-110">Beispielsweise können Sie den Wert von zwei Eigenschaften eines Objekts hinzufügen und die Summe als separates Datenelement anzeigen.</span><span class="sxs-lookup"><span data-stu-id="d1c39-110">For example, you may want to add the value of two properties of an object and display the sum as a separate piece of data.</span></span> <span data-ttu-id="d1c39-111">Wenn Sie eine eigene Formatierungs Datei schreiben, müssen Sie *Sichten* für die Objekte definieren, die Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="d1c39-111">When you write your own formatting file, you will need to define *views* for the objects that you want to display.</span></span> <span data-ttu-id="d1c39-112">Sie können für jedes Objekt eine einzelne Ansicht definieren, Sie können eine einzelne Ansicht für mehrere Objekte definieren, oder Sie können mehrere Ansichten für dasselbe Objekt definieren.</span><span class="sxs-lookup"><span data-stu-id="d1c39-112">You can define a single view for each object, you can define a single view for multiple objects, or you can define multiple views for the same object.</span></span> <span data-ttu-id="d1c39-113">Es gibt keine Beschränkung für die Anzahl der Sichten, die Sie definieren können.</span><span class="sxs-lookup"><span data-stu-id="d1c39-113">There is no limit to the number of views that you can define.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d1c39-114">Beim Formatieren von Dateien werden die Elemente eines Objekts, die an die Pipeline zurückgegeben werden, nicht bestimmt.</span><span class="sxs-lookup"><span data-stu-id="d1c39-114">Formatting files do not determine the elements of an object that are returned to the pipeline.</span></span> <span data-ttu-id="d1c39-115">Wenn ein Objekt an die Pipeline zurückgegeben wird, sind alle Member dieses Objekts verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d1c39-115">When an object is returned to the pipeline, all members of that object are available.</span></span>

## <a name="format-views"></a><span data-ttu-id="d1c39-116">Formatieren von Sichten</span><span class="sxs-lookup"><span data-stu-id="d1c39-116">Format Views</span></span>

<span data-ttu-id="d1c39-117">Durch das Formatieren von Sichten können Objekte in einem Tabellenformat, einem Listenformat, einem breiten Format und einem benutzerdefinierten Format angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d1c39-117">Formatting views can display objects in a table format, a list format, a wide format, and a custom format.</span></span> <span data-ttu-id="d1c39-118">In den meisten Fällen wird jede Formatierungs Definition durch eine Reihe von XML-Tags beschrieben, die eine Sicht beschreiben.</span><span class="sxs-lookup"><span data-stu-id="d1c39-118">For the most part, each formatting definition is described by a set of XML tags that describe a view.</span></span> <span data-ttu-id="d1c39-119">Jede Ansicht enthält den Namen der Ansicht, die Objekte, die die Sicht verwenden, und die Elemente der Ansicht, z. b. die Spalten-und Zeilen Informationen für eine Tabellen Sicht.</span><span class="sxs-lookup"><span data-stu-id="d1c39-119">Each view contains the name of the view, the objects that use the view, and the elements of the view, such as the column and row information for a table view.</span></span>

<span data-ttu-id="d1c39-120">Die folgenden Ansichten sind verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d1c39-120">The following views are available.</span></span>

<span data-ttu-id="d1c39-121">In der Tabellenansicht werden die Eigenschaften eines Objekts oder eines Skriptblock Werts in mindestens einer Spalte aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="d1c39-121">Table view Lists the properties of an object or a script block value in one or more columns.</span></span> <span data-ttu-id="d1c39-122">Jede Spalte stellt eine Eigenschaft des Objekts oder eines Skriptblock Werts dar.</span><span class="sxs-lookup"><span data-stu-id="d1c39-122">Each column represents a property of the object or a script block value.</span></span> <span data-ttu-id="d1c39-123">Sie können eine Tabellen Sicht definieren, in der alle Eigenschaften eines Objekts, eine Teilmenge der Eigenschaften eines Objekts oder eine Kombination von Eigenschaften und Skriptblock Werten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d1c39-123">You can define a table view that displays all the properties of an object, a subset of the properties of an object, or a combination of properties and script block values.</span></span> <span data-ttu-id="d1c39-124">Jede Zeile der Tabelle stellt ein zurück gegebenes Objekt dar.</span><span class="sxs-lookup"><span data-stu-id="d1c39-124">Each row of the table represents a returned object.</span></span> <span data-ttu-id="d1c39-125">Weitere Informationen zu dieser Ansicht finden Sie unter [Tabellen Sicht](../format/creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="d1c39-125">For more information about this view, see [Table View](../format/creating-a-table-view.md).</span></span>

<span data-ttu-id="d1c39-126">In der Listenansicht werden die Eigenschaften eines Objekts oder eines Skriptblock Werts in einer einzelnen Spalte aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="d1c39-126">List view Lists the properties of an object or a script block value in a single column.</span></span> <span data-ttu-id="d1c39-127">Jede Zeile der Liste zeigt eine optionale Bezeichnung oder den Eigenschaftsnamen gefolgt vom Wert der Eigenschaft oder des Skript Blocks an.</span><span class="sxs-lookup"><span data-stu-id="d1c39-127">Each row of the list displays an optional label or the property name followed by the value of the property or script block.</span></span> <span data-ttu-id="d1c39-128">Weitere Informationen zu dieser Ansicht finden Sie in der [Listenansicht](../format/creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="d1c39-128">For more information about this view, see [List View](../format/creating-a-list-view.md).</span></span>

<span data-ttu-id="d1c39-129">Die Breite Ansicht Listet eine einzelne Eigenschaft eines Objekts oder einen Skriptblock Wert in einer oder mehreren Spalten auf.</span><span class="sxs-lookup"><span data-stu-id="d1c39-129">Wide view Lists a single property of an object or a script block value in one or more columns.</span></span> <span data-ttu-id="d1c39-130">Für diese Ansicht gibt es keine Bezeichnung oder einen Header.</span><span class="sxs-lookup"><span data-stu-id="d1c39-130">There is no label or header for this view.</span></span> <span data-ttu-id="d1c39-131">Weitere Informationen zu dieser Ansicht finden Sie unter [Wide View](../format/creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="d1c39-131">For more information about this view, see [Wide View](../format/creating-a-wide-view.md).</span></span>

<span data-ttu-id="d1c39-132">Die benutzerdefinierte Ansicht zeigt eine anpassbare Ansicht von Objekteigenschaften oder Skriptblock Werten an, die nicht der festen Struktur von Tabellen Sichten, Listenansichten oder breiten Ansichten entspricht.</span><span class="sxs-lookup"><span data-stu-id="d1c39-132">Custom view Displays a customizable view of object properties or script block values that does not adhere to the rigid structure of table views, list views, or wide views.</span></span> <span data-ttu-id="d1c39-133">Sie können eine eigenständige benutzerdefinierte Ansicht definieren, oder Sie können eine benutzerdefinierte Ansicht definieren, die von einer anderen Ansicht verwendet wird, z. b. eine Tabellen-oder Listenansicht.</span><span class="sxs-lookup"><span data-stu-id="d1c39-133">You can define a standalone custom view, or you can define a custom view that is used by another view, such as a table view or list view.</span></span> <span data-ttu-id="d1c39-134">Weitere Informationen zu dieser Ansicht finden Sie unter [benutzerdefinierte Ansicht](../format/creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="d1c39-134">For more information about this view, see [Custom View](../format/creating-custom-controls.md).</span></span>

## <a name="view-xml-elements"></a><span data-ttu-id="d1c39-135">Anzeigen von XML-Elementen</span><span class="sxs-lookup"><span data-stu-id="d1c39-135">View XML Elements</span></span>

<span data-ttu-id="d1c39-136">Das folgende Beispiel zeigt die XML-Tags, mit denen eine Tabellen Sicht definiert wird, die zwei Spalten enthält.</span><span class="sxs-lookup"><span data-stu-id="d1c39-136">The following example shows the XML tags used to define a table view that contains two columns.</span></span> <span data-ttu-id="d1c39-137">Das [viewdefinitions](../format/viewdefinitions-element-format.md) -Element ist das Containerelement für alle Sichten, die in der Formatierungs Datei definiert sind.</span><span class="sxs-lookup"><span data-stu-id="d1c39-137">The [ViewDefinitions](../format/viewdefinitions-element-format.md) element is the container element for all the views defined in the formatting file.</span></span> <span data-ttu-id="d1c39-138">Das [Ansichts](../format/view-element-format.md) Element definiert die spezifische Tabelle, die Liste, die Breite oder die benutzerdefinierte Sicht.</span><span class="sxs-lookup"><span data-stu-id="d1c39-138">The [View](../format/view-element-format.md) element defines the specific table, list, wide, or custom view.</span></span> <span data-ttu-id="d1c39-139">In jeder Ansicht gibt das [Name](../format/name-element-for-view-format.md) -Element den Namen der Ansicht an, das [viewselectedby](../format/viewselectedby-element-format.md) -Element definiert die Objekte, die die Sicht verwenden, und die verschiedenen Steuerelemente (z. b. das- `TableControl` Element) definieren das Format der Sicht.</span><span class="sxs-lookup"><span data-stu-id="d1c39-139">Within each view, the [Name](../format/name-element-for-view-format.md) element specifies the name of the view, the [ViewSelectedBy](../format/viewselectedby-element-format.md) element defines the objects that use the view, and the different control elements (such as the `TableControl` element) define the format of the view.</span></span>

```xml
ViewDefinitions
  <View>
    <Name>Name of View</Name>
    <ViewSelectedBy>
      <TypeName>Object to display using this view</TypeName>
      <TypeName>Object to display using this view</TypeName>
    </ViewSelectedBy>
    <TableControl>
      <TableHeaders>
        <TableColumnHeader>
          <Width></Width>
        </TableColumnHeader>
        <TableColumnHeader>
          <Width></Width>
        </TableColumnHeader>
      </TableHeaders>
      <TableRowEntries>
        <TableRowEntry>
          <TableColumnItems>
            <TableColumnItem>
              <PropertyName>Header for column 1</PropertyName>
            </TableColumnItem>
            <TableColumnItem>
              <PropertyName>Header for column 2</PropertyName>
            </TableColumnItem>
          </TableColumnItems>
        </TableRowEntry>
      </TableRowEntries>
    </TableControl)
  </View>
</ViewDefinitions>

```

## <a name="see-also"></a><span data-ttu-id="d1c39-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d1c39-140">See Also</span></span>

[<span data-ttu-id="d1c39-141">Tabellenansicht</span><span class="sxs-lookup"><span data-stu-id="d1c39-141">Table View</span></span>](../format/creating-a-table-view.md)

[<span data-ttu-id="d1c39-142">Listenansicht</span><span class="sxs-lookup"><span data-stu-id="d1c39-142">List View</span></span>](../format/creating-a-list-view.md)

[<span data-ttu-id="d1c39-143">Breite Ansicht</span><span class="sxs-lookup"><span data-stu-id="d1c39-143">Wide View</span></span>](../format/creating-a-wide-view.md)

[<span data-ttu-id="d1c39-144">Benutzerdefinierte Ansicht</span><span class="sxs-lookup"><span data-stu-id="d1c39-144">Custom View</span></span>](../format/creating-custom-controls.md)

[<span data-ttu-id="d1c39-145">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="d1c39-145">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
