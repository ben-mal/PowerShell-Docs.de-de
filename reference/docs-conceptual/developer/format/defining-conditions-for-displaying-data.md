---
ms.date: 09/13/2016
ms.topic: reference
title: Definieren von Bedingungen für die Datenanzeige
description: Definieren von Bedingungen für die Datenanzeige
ms.openlocfilehash: 9a8b7a618da8c64de978c13b527435a2d7793677
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660305"
---
# <a name="defining-conditions-for-displaying-data"></a><span data-ttu-id="8deea-103">Definieren von Bedingungen für die Datenanzeige</span><span class="sxs-lookup"><span data-stu-id="8deea-103">Defining Conditions for Displaying Data</span></span>

<span data-ttu-id="8deea-104">Wenn Sie definieren, welche Daten von einer Ansicht oder einem Steuerelement angezeigt werden, können Sie eine Bedingung angeben, die vorhanden sein muss, damit die Daten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="8deea-104">When defining what data is displayed by a view or a control, you can specify a condition that must exist for the data to be displayed.</span></span> <span data-ttu-id="8deea-105">Die Bedingung kann durch eine bestimmte Eigenschaft ausgelöst werden, oder wenn ein Skript oder ein Eigenschafts Wert als ausgewertet wird `true` .</span><span class="sxs-lookup"><span data-stu-id="8deea-105">The condition can be triggered by a specific property, or when a script or property value evaluates to `true`.</span></span> <span data-ttu-id="8deea-106">Wenn die Auswahlbedingung erfüllt ist, wird die Definition der Ansicht bzw. des Steuer Elements verwendet.</span><span class="sxs-lookup"><span data-stu-id="8deea-106">When the selection condition is met, the definition of the view or control is used.</span></span>

## <a name="specifying-a-selection-condition-for-a-definition"></a><span data-ttu-id="8deea-107">Angeben einer Auswahlbedingung für eine Definition</span><span class="sxs-lookup"><span data-stu-id="8deea-107">Specifying a Selection Condition for a Definition</span></span>

<span data-ttu-id="8deea-108">Wenn eine Definition für eine Sicht oder ein Steuerelement erstellt wird, wird das- `EntrySelectedBy` Element verwendet, um anzugeben, welche Objekte die Definition verwenden oder welche Bedingung vorhanden sein muss, damit die Definition verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="8deea-108">When creating a definition for a view or control, the `EntrySelectedBy` element is used to specify which objects will use the definition or what condition must exist for the definition to be used.</span></span> <span data-ttu-id="8deea-109">Die Bedingung wird durch das- `SelectionCondition` Element angegeben.</span><span class="sxs-lookup"><span data-stu-id="8deea-109">The condition is specified by the `SelectionCondition` element.</span></span>

<span data-ttu-id="8deea-110">Im folgenden Beispiel wird eine Auswahlbedingung für eine Definition einer Tabellenansicht angegeben.</span><span class="sxs-lookup"><span data-stu-id="8deea-110">In the following example, a selection condition is specified for a definition of a table view.</span></span> <span data-ttu-id="8deea-111">In diesem Beispiel wird die Definition nur verwendet, wenn das angegebene Skript als ausgewertet wird `true` .</span><span class="sxs-lookup"><span data-stu-id="8deea-111">In this example, the definition is used only when the specified script is evaluated to `true`.</span></span>

```xml
<TableRowEntry>
  <EntrySelectedBy>
    <SelectionCondition>
      <ScriptBlock>ScriptToEvaluate</ScriptBlock>
    </SelectionCondition>
  </EntrySelectedBy>
  <TableColumnItems>
  </TableColumnItems>
</TableRowEntry>

```

<span data-ttu-id="8deea-112">Es gibt keine Beschränkung für die Anzahl der Auswahl Bedingungen, die Sie für die Definition einer Sicht oder eines Steuer Elements angeben können.</span><span class="sxs-lookup"><span data-stu-id="8deea-112">There is no limit to the number of selection conditions that you can specify for a definition of a view or control.</span></span> <span data-ttu-id="8deea-113">Die einzigen Anforderungen sind die folgenden:</span><span class="sxs-lookup"><span data-stu-id="8deea-113">The only requirements are the following:</span></span>

- <span data-ttu-id="8deea-114">Die Auswahlbedingung muss einen Eigenschaftsnamen oder ein Skript angeben, um die Bedingung zu initiieren, kann jedoch nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="8deea-114">The selection condition must specify one property name or script to trigger the condition, but cannot specify both.</span></span>

- <span data-ttu-id="8deea-115">Die Auswahlbedingung kann eine beliebige Anzahl von .NET-Typen oder-Auswahl Sätzen angeben, kann jedoch nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="8deea-115">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

## <a name="specifying-a-selection-condition-for-an-item"></a><span data-ttu-id="8deea-116">Angeben einer Auswahlbedingung für ein Element</span><span class="sxs-lookup"><span data-stu-id="8deea-116">Specifying a Selection Condition for an Item</span></span>

<span data-ttu-id="8deea-117">Sie können auch angeben, wann ein Element einer Listenansicht oder eines Steuer Elements verwendet wird, indem Sie das- `ItemSelectionCondition` Element in die Element Definition einschließen.</span><span class="sxs-lookup"><span data-stu-id="8deea-117">You can also specify when an item of a list view or control is used by including the `ItemSelectionCondition` element in the item definition.</span></span> <span data-ttu-id="8deea-118">Im folgenden Beispiel wird eine Auswahlbedingung für ein Element einer Listenansicht angegeben.</span><span class="sxs-lookup"><span data-stu-id="8deea-118">In the following example, a selection condition is specified for an item of a list view.</span></span> <span data-ttu-id="8deea-119">In diesem Beispiel wird das Element nur verwendet, wenn das Skript als ausgewertet wird `true` .</span><span class="sxs-lookup"><span data-stu-id="8deea-119">In this example, the item is used only when the script is evaluated to `true`.</span></span>

```xml
<ListItem>
  <ItemSelectionCondition>
    <ScriptBlock>ScriptToEvaluate</ScriptBlock>
  </ItemSelectionCondition>
</ListItem>

```

<span data-ttu-id="8deea-120">Sie können nur eine Auswahlbedingung für ein Element angeben.</span><span class="sxs-lookup"><span data-stu-id="8deea-120">You can specify only one selection condition for an item.</span></span> <span data-ttu-id="8deea-121">Und die Bedingung muss einen Eigenschaftsnamen oder ein Skript angeben, um die Bedingung zu initiieren, kann jedoch nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="8deea-121">And the condition must specify one property name or script to trigger the condition, but cannot specify both.</span></span>

## <a name="xml-elements"></a><span data-ttu-id="8deea-122">XML-Elemente</span><span class="sxs-lookup"><span data-stu-id="8deea-122">XML Elements</span></span>

 <span data-ttu-id="8deea-123">Die folgenden XML-Elemente werden verwendet, um eine Auswahlbedingung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8deea-123">The following XML elements are used to create a selection condition.</span></span>

- <span data-ttu-id="8deea-124">Die folgenden Elemente geben Auswahl Bedingungen für Sicht Definitionen an:</span><span class="sxs-lookup"><span data-stu-id="8deea-124">The following elements specify selection conditions for view definitions:</span></span>

  - [<span data-ttu-id="8deea-125">Element „SelectionCondition“ für EntrySelectedBy für TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="8deea-125">SelectionCondition Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

  - [<span data-ttu-id="8deea-126">Element „SelectionCondition“ für EntrySelectedBy für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="8deea-126">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

  - [<span data-ttu-id="8deea-127">Element „SelectionCondition“ für EntrySelectedBy für WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="8deea-127">SelectionCondition Element for EntrySelectedBy for WideControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

  - [<span data-ttu-id="8deea-128">Element „SelectionCondition“ für EntrySelectedBy für CustomControl (Format)</span><span class="sxs-lookup"><span data-stu-id="8deea-128">SelectionCondition Element for EntrySelectedBy for CustomControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

- <span data-ttu-id="8deea-129">Die folgenden Elemente geben Auswahl Bedingungen für allgemeine und Ansicht-Steuerelement Definitionen an:</span><span class="sxs-lookup"><span data-stu-id="8deea-129">The following elements specify selection conditions for common and view control definitions:</span></span>

  - [<span data-ttu-id="8deea-130">Element „SelectionCondition“ für EntrySelectedBy für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="8deea-130">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

  - [<span data-ttu-id="8deea-131">Element „SelectionCondition“ für EntrySelectedBy für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="8deea-131">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)

- <span data-ttu-id="8deea-132">Mit dem folgenden Element wird die Auswahlbedingung zum Erweitern von Auflistungs Objekten angegeben:</span><span class="sxs-lookup"><span data-stu-id="8deea-132">The following element specifies the selection condition for expanding collection objects:</span></span>

  - [<span data-ttu-id="8deea-133">Element „SelectionCondition“ für EntrySelectedBy für EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="8deea-133">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

- <span data-ttu-id="8deea-134">Das folgende Element gibt die Auswahlbedingung zum Anzeigen einer neuen Gruppe von Daten an:</span><span class="sxs-lookup"><span data-stu-id="8deea-134">The following element specifies the selection condition for displaying a new group of data:</span></span>

  - [<span data-ttu-id="8deea-135">Element „SelectionCondition“ für EntrySelectedBy für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="8deea-135">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

- <span data-ttu-id="8deea-136">Das folgende Element gibt eine Elementauswahl Bedingung für eine Listenansicht an:</span><span class="sxs-lookup"><span data-stu-id="8deea-136">The following element specifies an item selection condition for a list view:</span></span>

  - [<span data-ttu-id="8deea-137">Element „ItemSelectionCondition“ für ListItem für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="8deea-137">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)

- <span data-ttu-id="8deea-138">Die folgenden Elemente geben eine Elementauswahl Bedingung für-Steuerelemente an:</span><span class="sxs-lookup"><span data-stu-id="8deea-138">The following elements specify an item selection condition for controls:</span></span>

  - [<span data-ttu-id="8deea-139">Element „ItemSelectionCondition“ für ExpressionBinding für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="8deea-139">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)

  - [<span data-ttu-id="8deea-140">Element „ItemSelectionCondition“ für ExpressionBinding für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="8deea-140">ItemSelectionCondition Element for ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

  - [<span data-ttu-id="8deea-141">Element „ItemSelectionCondition“ für ExpressionBinding für CustomControl (Format)</span><span class="sxs-lookup"><span data-stu-id="8deea-141">ItemSelectionCondition Element for ExpressionBinding for CustomControl (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

## <a name="see-also"></a><span data-ttu-id="8deea-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8deea-142">See Also</span></span>

[<span data-ttu-id="8deea-143">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="8deea-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
