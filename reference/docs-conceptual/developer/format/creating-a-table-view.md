---
ms.date: 09/13/2016
ms.topic: reference
title: Erstellen einer Tabellenansicht
description: Erstellen einer Tabellenansicht
ms.openlocfilehash: 035d42f7968a9e8babec692a7a5873e24b36cd97
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660301"
---
# <a name="creating-a-table-view"></a><span data-ttu-id="6111f-103">Erstellen einer Tabellenansicht</span><span class="sxs-lookup"><span data-stu-id="6111f-103">Creating a Table View</span></span>

<span data-ttu-id="6111f-104">Eine Tabellen Sicht zeigt Daten in einer oder mehreren Spalten an.</span><span class="sxs-lookup"><span data-stu-id="6111f-104">A table view displays data in one or more columns.</span></span> <span data-ttu-id="6111f-105">Jede Zeile in der Tabelle stellt ein .NET-Objekt dar, und jede Spalte der Tabelle stellt eine Eigenschaft des Objekts oder einen Skript Wert dar.</span><span class="sxs-lookup"><span data-stu-id="6111f-105">Each row in the table represents a .NET object, and each column of the table represents a property of the object or a script value.</span></span> <span data-ttu-id="6111f-106">Sie können eine Tabellen Sicht definieren, in der alle Eigenschaften eines Objekts oder eine Teilmenge der Eigenschaften eines Objekts angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="6111f-106">You can define a table view that displays all the properties of an object or a subset of the properties of an object.</span></span>

## <a name="a-table-view-display"></a><span data-ttu-id="6111f-107">Anzeige der Tabellenansicht</span><span class="sxs-lookup"><span data-stu-id="6111f-107">A Table View Display</span></span>

<span data-ttu-id="6111f-108">Das folgende Beispiel zeigt, wie Windows PowerShell das [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) -Objekt anzeigt, das vom Cmdlet " [Get-Service](/powershell/module/microsoft.powershell.management/get-service) " zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="6111f-108">The following example shows how Windows PowerShell displays the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object that is returned by the [Get-Service](/powershell/module/microsoft.powershell.management/get-service) cmdlet.</span></span> <span data-ttu-id="6111f-109">Für dieses Objekt hat Windows PowerShell eine Tabellen Sicht definiert, in der die `Status` -Eigenschaft, die `Name` -Eigenschaft (diese Eigenschaft ist eine Alias Eigenschaft für die `ServiceName` -Eigenschaft) und die-Eigenschaft angezeigt werden `DisplayName` .</span><span class="sxs-lookup"><span data-stu-id="6111f-109">For this object, Windows PowerShell has defined a table view that displays the `Status` property, the `Name` property (this property is an alias property for the `ServiceName` property), and the `DisplayName` property.</span></span> <span data-ttu-id="6111f-110">Jede Zeile in der Tabelle stellt ein vom Cmdlet zurück gegebenes Objekt dar.</span><span class="sxs-lookup"><span data-stu-id="6111f-110">Each row in the table represents an object returned by the cmdlet.</span></span>

```output
Status   Name               DisplayName
------   ----               -----------
Stopped  AJRouter           AllJoyn Router Service
Stopped  ALG                Application Layer Gateway Service
Stopped  AppIDSvc           Application Identity
Running  Appinfo            Application Information
```

## <a name="defining-the-table-view"></a><span data-ttu-id="6111f-111">Definieren der Tabellenansicht</span><span class="sxs-lookup"><span data-stu-id="6111f-111">Defining the Table View</span></span>

<span data-ttu-id="6111f-112">Der folgende XML-Code zeigt das Tabellen Ansichts Schema zum Anzeigen von [System. ServiceProcess. ServiceController? Displayproperty = FullName](/dotnet/api/System.ServiceProcess.ServiceController) -Objekt.</span><span class="sxs-lookup"><span data-stu-id="6111f-112">The following XML shows the table view schema for displaying the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span> <span data-ttu-id="6111f-113">Sie müssen jede Eigenschaft angeben, die in der Tabellenansicht angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="6111f-113">You must specify each property that you want displayed in the table view.</span></span>

```xml
<View>
  <Name>service</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <TableControl>
    <TableHeaders>
      <TableColumnHeader>
        <Width>8</Width>
      </TableColumnHeader>
      <TableColumnHeader>
        <Width>18</Width>
      </TableColumnHeader>
      <TableColumnHeader>
        <Width>38</Width>
      </TableColumnHeader>
    </TableHeaders>
    <TableRowEntries>
      <TableRowEntry>
        <TableColumnItems>
          <TableColumnItem>
           <PropertyName>Status</PropertyName>
          </TableColumnItem>
          <TableColumnItem>
            <PropertyName>Name</PropertyName>
          </TableColumnItem>
          <TableColumnItem>
            <PropertyName>DisplayName</PropertyName>
          </TableColumnItem>
        </TableColumnItems>
      </TableRowEntry>
    </TableRowEntries>
  </TableControl>
</View>
```

<span data-ttu-id="6111f-114">Die folgenden XML-Elemente werden verwendet, um eine Listenansicht zu definieren:</span><span class="sxs-lookup"><span data-stu-id="6111f-114">The following XML elements are used to define a list view:</span></span>

- <span data-ttu-id="6111f-115">Das [View](./view-element-format.md) -Element ist das übergeordnete Element der Tabellen Sicht.</span><span class="sxs-lookup"><span data-stu-id="6111f-115">The [View](./view-element-format.md) element is the parent element of the table view.</span></span> <span data-ttu-id="6111f-116">(Dies ist dasselbe übergeordnete Element für die Listen-, Wide-und Custom-Steuerelement Sichten.)</span><span class="sxs-lookup"><span data-stu-id="6111f-116">(This is the same parent element for the list, wide, and custom control views.)</span></span>

- <span data-ttu-id="6111f-117">Das [Name](./name-element-for-view-format.md) -Element gibt den Namen der Ansicht an.</span><span class="sxs-lookup"><span data-stu-id="6111f-117">The [Name](./name-element-for-view-format.md) element specifies the name of the view.</span></span> <span data-ttu-id="6111f-118">Dieses Element ist für alle Sichten erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6111f-118">This element is required for all views.</span></span>

- <span data-ttu-id="6111f-119">Das [viewselectedby](./viewselectedby-element-format.md) -Element definiert die Objekte, die die Ansicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="6111f-119">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines the objects that use the view.</span></span> <span data-ttu-id="6111f-120">Dieses Element ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6111f-120">This element is required.</span></span>

- <span data-ttu-id="6111f-121">Das [GroupBy](./groupby-element-for-view-format.md) -Element (in diesem Beispiel nicht gezeigt) definiert, wann eine neue Gruppe von Objekten angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="6111f-121">The [GroupBy](./groupby-element-for-view-format.md) element (not shown in this example) defines when a new group of objects is displayed.</span></span> <span data-ttu-id="6111f-122">Eine neue Gruppe wird immer dann gestartet, wenn der Wert einer bestimmten Eigenschaft oder eines Skripts geändert wird.</span><span class="sxs-lookup"><span data-stu-id="6111f-122">A new group is started whenever the value of a specific property or script changes.</span></span> <span data-ttu-id="6111f-123">Dieses Element ist optional.</span><span class="sxs-lookup"><span data-stu-id="6111f-123">This element is optional.</span></span>

- <span data-ttu-id="6111f-124">Das [Controls](./controls-element-for-view-format.md) -Element (in diesem Beispiel nicht gezeigt) definiert die benutzerdefinierten Steuerelemente, die von der Tabellenansicht definiert werden.</span><span class="sxs-lookup"><span data-stu-id="6111f-124">The [Controls](./controls-element-for-view-format.md) element (not shown in this example) defines the custom controls that are defined by the table view.</span></span> <span data-ttu-id="6111f-125">Steuerelemente geben Ihnen eine Möglichkeit, die Anzeige der Daten weiter anzugeben.</span><span class="sxs-lookup"><span data-stu-id="6111f-125">Controls give you a way to further specify how the data is displayed.</span></span> <span data-ttu-id="6111f-126">Dieses Element ist optional.</span><span class="sxs-lookup"><span data-stu-id="6111f-126">This element is optional.</span></span> <span data-ttu-id="6111f-127">Eine Sicht kann eigene benutzerdefinierte Steuerelemente definieren, oder Sie kann allgemeine Steuerelemente verwenden, die von jeder Ansicht in der Formatierungs Datei verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="6111f-127">A view can define its own custom controls, or it can use common controls that can be used by any view in the formatting file.</span></span> <span data-ttu-id="6111f-128">Weitere Informationen zu benutzerdefinierten Steuerelementen finden Sie unter [Erstellen von benutzerdefinierten Steuerelementen](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="6111f-128">For more information about custom controls, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

- <span data-ttu-id="6111f-129">Das [hidetableheaders](./hidetableheaders-element-format.md) -Element (in diesem Beispiel nicht angezeigt) gibt an, dass in der Tabelle keine Bezeichnungen am Anfang der Tabelle angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="6111f-129">The [HideTableHeaders](./hidetableheaders-element-format.md) element (not show in this example) specifies that the table will not show any labels at the top of the table.</span></span> <span data-ttu-id="6111f-130">Dieses Element ist optional.</span><span class="sxs-lookup"><span data-stu-id="6111f-130">This element is optional.</span></span>

- <span data-ttu-id="6111f-131">Das [tablecontrol](./tablecontrol-element-format.md) -Element, das die Header-und Zeilen Informationen der Tabelle definiert.</span><span class="sxs-lookup"><span data-stu-id="6111f-131">The [TableControl](./tablecontrol-element-format.md) element that defines the header and row information of the table.</span></span> <span data-ttu-id="6111f-132">Ähnlich wie alle anderen Sichten kann eine Tabellenansicht die Werte der Objekteigenschaften oder von Skripts generierten Werte anzeigen.</span><span class="sxs-lookup"><span data-stu-id="6111f-132">Similar to all other views, a table view can display the values of object properties or values generated by scripts.</span></span>

## <a name="defining-column-headers"></a><span data-ttu-id="6111f-133">Definieren von Spalten Headern</span><span class="sxs-lookup"><span data-stu-id="6111f-133">Defining Column Headers</span></span>

1. <span data-ttu-id="6111f-134">Das [tableHeaders](./tableheaders-element-format.md) -Element und seine untergeordneten Elemente definieren, was am oberen Rand der Tabelle angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="6111f-134">The [TableHeaders](./tableheaders-element-format.md) element and its child elements define what is displayed at the top of the table.</span></span>

2. <span data-ttu-id="6111f-135">Das [tablecolumnheader](./tablecolumnheader-element-format.md) -Element definiert, was oben in einer Spalte der Tabelle angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="6111f-135">The [TableColumnHeader](./tablecolumnheader-element-format.md) element defines what is displayed at the top of a column of the table.</span></span> <span data-ttu-id="6111f-136">Geben Sie diese Elemente in der Reihenfolge an, in der die Header angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6111f-136">Specify these elements in the order that you want the headers displayed.</span></span>

   <span data-ttu-id="6111f-137">Es gibt keine Beschränkung für die Anzahl dieser Elemente, die Sie verwenden können, aber die Anzahl der [tablecolumnheader](./tablecolumnheader-element-format.md) -Elemente in der Tabellenansicht muss der Anzahl der [tablerowentry](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md) -Elemente entsprechen, die Sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="6111f-137">There is no limit to the number of these element that you can use, but the number of [TableColumnHeader](./tablecolumnheader-element-format.md) elements in your table view must equal the number of [TableRowEntry](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md) elements that you use.</span></span>

3. <span data-ttu-id="6111f-138">Das [Label](./label-element-for-tablecolumnheader-for-tablecontrol-format.md) -Element gibt den Text an, der angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="6111f-138">The [Label](./label-element-for-tablecolumnheader-for-tablecontrol-format.md) element specifies the text that is displayed.</span></span> <span data-ttu-id="6111f-139">Dieses Element ist optional.</span><span class="sxs-lookup"><span data-stu-id="6111f-139">This element is optional.</span></span>

4. <span data-ttu-id="6111f-140">Das [Width](./width-element-for-tablecolumnheader-for-tablecontrol-format.md) -Element gibt die Breite (in Zeichen) der Spalte an.</span><span class="sxs-lookup"><span data-stu-id="6111f-140">The [Width](./width-element-for-tablecolumnheader-for-tablecontrol-format.md) element specifies the width (in characters) of the column.</span></span> <span data-ttu-id="6111f-141">Dieses Element ist optional.</span><span class="sxs-lookup"><span data-stu-id="6111f-141">This element is optional.</span></span>

5. <span data-ttu-id="6111f-142">Das [Alignment](./alignment-element-for-tablecolumnheader-for-tablecontrol-format.md) -Element gibt an, wie die Bezeichnung angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="6111f-142">The [Alignment](./alignment-element-for-tablecolumnheader-for-tablecontrol-format.md) element specifies how the label is displayed.</span></span> <span data-ttu-id="6111f-143">Die Bezeichnung kann Links, rechts oder zentriert ausgerichtet werden.</span><span class="sxs-lookup"><span data-stu-id="6111f-143">The label can be aligned to the left, to the right, or centered.</span></span> <span data-ttu-id="6111f-144">Dieses Element ist optional.</span><span class="sxs-lookup"><span data-stu-id="6111f-144">This element is optional.</span></span>

## <a name="defining-the-table-rows"></a><span data-ttu-id="6111f-145">Definieren der Tabellenzeilen</span><span class="sxs-lookup"><span data-stu-id="6111f-145">Defining the Table Rows</span></span>

<span data-ttu-id="6111f-146">Tabellen Sichten können eine oder mehrere Definitionen bereitstellen, die angeben, welche Daten in den Zeilen der Tabelle angezeigt werden, indem die untergeordneten Elemente des [tablerowentries](./tablerowentries-element-for-tablecontrol-format.md) -Elements verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6111f-146">Table views can provide one or more definitions that specify what data is displayed in the rows of the table by using the child elements of the [TableRowEntries](./tablerowentries-element-for-tablecontrol-format.md) element.</span></span> <span data-ttu-id="6111f-147">Beachten Sie, dass Sie mehrere Definitionen für die Zeilen der Tabelle angeben können, die Header für die Zeilen jedoch unverändert bleiben, unabhängig davon, welche Zeilen Definition verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6111f-147">Notice that you can specify multiple definitions for the rows of the table, but the headers for the rows remains the same, regardless of what row definition is used.</span></span> <span data-ttu-id="6111f-148">In der Regel enthält eine Tabelle nur eine Definition.</span><span class="sxs-lookup"><span data-stu-id="6111f-148">Typically, a table will have only one definition.</span></span>

<span data-ttu-id="6111f-149">Im folgenden Beispiel stellt die Sicht eine einzelne Definition bereit, in der die Werte mehrerer Eigenschaften von [System. Diagnostics. Process angezeigt werden? Displayproperty = FullName](/dotnet/api/System.Diagnostics.Process) -Objekt.</span><span class="sxs-lookup"><span data-stu-id="6111f-149">In the following example, the view provides a single definition that displays the values of several properties of the [System.Diagnostics.Process?Displayproperty=Fullname](/dotnet/api/System.Diagnostics.Process) object.</span></span> <span data-ttu-id="6111f-150">In einer Tabellen Sicht kann der Wert einer Eigenschaft oder der Wert eines Skripts (nicht im Beispiel) in den Zeilen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="6111f-150">A table view can display the value of a property or the value of a script (not shown in the example) in its rows.</span></span>

```xml
<TableRowEntries>
      <TableRowEntry>
        <TableColumnItems>
          <TableColumnItem>
           <PropertyName>Status</PropertyName>
          </TableColumnItem>
          <TableColumnItem>
            <PropertyName>Name</PropertyName>
          </TableColumnItem>
          <TableColumnItem>
            <PropertyName>DisplayName</PropertyName>
          </TableColumnItem>
        </TableColumnItems>
      </TableRowEntry>
    </TableRowEntries>

```

<span data-ttu-id="6111f-151">Die folgenden XML-Elemente können verwendet werden, um Definitionen für eine Zeile bereitzustellen:</span><span class="sxs-lookup"><span data-stu-id="6111f-151">The following XML elements can be used to provide definitions for a row:</span></span>

- <span data-ttu-id="6111f-152">Das [tablerowentries](./tablerowentries-element-for-tablecontrol-format.md) -Element und seine untergeordneten Elemente definieren, was in den Zeilen der Tabelle angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="6111f-152">The [TableRowEntries](./tablerowentries-element-for-tablecontrol-format.md) element and its child elements define what is displayed in the rows of the table.</span></span>

- <span data-ttu-id="6111f-153">Das [tablerowentry](./listentry-element-for-listcontrol-format.md) -Element stellt eine Definition der Zeile bereit.</span><span class="sxs-lookup"><span data-stu-id="6111f-153">The [TableRowEntry](./listentry-element-for-listcontrol-format.md) element provides a definition of the row.</span></span> <span data-ttu-id="6111f-154">Mindestens ein [tablerowentry](./listentry-element-for-listcontrol-format.md) ist erforderlich. Es gibt jedoch keine maximale Beschränkung für die Anzahl der Elemente, die Sie hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="6111f-154">At least one [TableRowEntry](./listentry-element-for-listcontrol-format.md) is required; however, there is no maximum limit to the number of elements that you can add.</span></span> <span data-ttu-id="6111f-155">In den meisten Fällen weist eine Ansicht nur eine Definition auf.</span><span class="sxs-lookup"><span data-stu-id="6111f-155">In most cases, a view will have only one definition.</span></span>

- <span data-ttu-id="6111f-156">Das [entryselectedby](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md) -Element gibt die Objekte an, die von einer bestimmten Definition angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="6111f-156">The [EntrySelectedBy](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md) element specifies the objects that are displayed by a specific definition.</span></span> <span data-ttu-id="6111f-157">Dieses Element ist optional und wird nur benötigt, wenn Sie mehrere [tablerowentry](./listentry-element-for-listcontrol-format.md) -Elemente definieren, die verschiedene-Objekte anzeigen.</span><span class="sxs-lookup"><span data-stu-id="6111f-157">This element is optional and is needed only when you define multiple [TableRowEntry](./listentry-element-for-listcontrol-format.md) elements that display different objects.</span></span>

- <span data-ttu-id="6111f-158">Das [Wrap](./wrap-element-for-tablerowentry-for-tablecontrol-format.md) -Element gibt an, dass der Text, der die Spaltenbreite überschreitet, in der nächsten Zeile angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="6111f-158">The [Wrap](./wrap-element-for-tablerowentry-for-tablecontrol-format.md) element specifies that text that exceeds the column width is displayed on the next line.</span></span> <span data-ttu-id="6111f-159">Standardmäßig wird Text, der die Spaltenbreite überschreitet, abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="6111f-159">By default, text that exceeds the column width is truncated.</span></span>

- <span data-ttu-id="6111f-160">Das [tablecolumnitems](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md) -Element definiert die Eigenschaften oder Skripts, deren Werte in der Zeile angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="6111f-160">The [TableColumnItems](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md) element defines the properties or scripts whose values are displayed in the row.</span></span>

- <span data-ttu-id="6111f-161">Das [tablecolumnitem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) -Element definiert die Eigenschaft oder das Skript, dessen Wert in der Spalte der Zeile angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="6111f-161">The [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) element defines the property or script whose value is displayed in the column of the row.</span></span> <span data-ttu-id="6111f-162">Für jede Spalte der Zeile ist ein [tablecolumnitem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) -Element erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6111f-162">A [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) element is required for each column of the row.</span></span> <span data-ttu-id="6111f-163">Der erste Eintrag wird in der ersten Spalte angezeigt, der zweite Eintrag in der zweiten Spalte usw.</span><span class="sxs-lookup"><span data-stu-id="6111f-163">The first entry is displayed in first column, the second entry in the second column, and so on.</span></span>

- <span data-ttu-id="6111f-164">Das [propertyName](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md) -Element gibt die-Eigenschaft an, deren Wert in der Zeile angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="6111f-164">The [PropertyName](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md) element specifies the property whose value is displayed in the row.</span></span> <span data-ttu-id="6111f-165">Sie müssen entweder eine Eigenschaft oder ein Skript angeben, aber Sie können nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="6111f-165">You must specify either a property or a script, but you cannot specify both.</span></span>

- <span data-ttu-id="6111f-166">Das [ScriptBlock](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md) -Element gibt das Skript an, dessen Wert in der Zeile angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="6111f-166">The [ScriptBlock](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md) element specifies the script whose value is displayed in the row.</span></span> <span data-ttu-id="6111f-167">Sie müssen entweder ein-Skript oder eine-Eigenschaft angeben, aber Sie können nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="6111f-167">You must specify either a script or a property, but you cannot specify both.</span></span>

- <span data-ttu-id="6111f-168">Das Format [String](./label-element-for-listitem-for-listcontrol-format.md) -Element gibt ein Format Muster an, das definiert, wie der Eigenschafts-oder Skript Wert angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="6111f-168">The [FormatString](./label-element-for-listitem-for-listcontrol-format.md) element specifies a format pattern that defines how the property or script value is displayed.</span></span> <span data-ttu-id="6111f-169">Dieses Element ist optional.</span><span class="sxs-lookup"><span data-stu-id="6111f-169">This element is optional.</span></span>

- <span data-ttu-id="6111f-170">Das [Alignment](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md) -Element gibt an, wie der Wert der Eigenschaft oder des Skripts angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="6111f-170">The [Alignment](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md) element specifies how the value of the property or script is displayed.</span></span> <span data-ttu-id="6111f-171">Der Wert kann Links, rechts oder zentriert ausgerichtet werden.</span><span class="sxs-lookup"><span data-stu-id="6111f-171">The value can be aligned to the left, to the right, or centered.</span></span> <span data-ttu-id="6111f-172">Dieses Element ist optional.</span><span class="sxs-lookup"><span data-stu-id="6111f-172">This element is optional.</span></span>

## <a name="defining-the-objects-that-use-the-table-view"></a><span data-ttu-id="6111f-173">Definieren der Objekte, die die Tabellenansicht verwenden</span><span class="sxs-lookup"><span data-stu-id="6111f-173">Defining the Objects That Use the Table View</span></span>

<span data-ttu-id="6111f-174">Es gibt zwei Möglichkeiten, um zu definieren, welche .NET-Objekte die Tabellenansicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="6111f-174">There are two ways to define which .NET objects use the table view.</span></span> <span data-ttu-id="6111f-175">Sie können das [viewselectedby](./viewselectedby-element-format.md) -Element verwenden, um die Objekte zu definieren, die von allen Definitionen der Sicht angezeigt werden können, oder Sie können das [entryselectedby](./entryselectedby-element-for-listentry-for-listcontrol-format.md) -Element verwenden, um zu definieren, welche Objekte von einer bestimmten Definition der Sicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="6111f-175">You can use the [ViewSelectedBy](./viewselectedby-element-format.md) element to define the objects that can be displayed by all the definitions of the view, or you can use the [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) element to define which objects are displayed by a specific definition of the view.</span></span> <span data-ttu-id="6111f-176">In den meisten Fällen verfügt eine Sicht nur über eine Definition, sodass Objekte normalerweise durch das [viewselectedby](./viewselectedby-element-format.md) -Element definiert werden.</span><span class="sxs-lookup"><span data-stu-id="6111f-176">In most cases, a view has only one definition, so objects are typically defined by the [ViewSelectedBy](./viewselectedby-element-format.md) element.</span></span>

<span data-ttu-id="6111f-177">Im folgenden Beispiel wird gezeigt, wie die Objekte definiert werden, die von der Tabellenansicht mithilfe der Elemente [viewselectedby](./viewselectedby-element-format.md) und [tygtame](./typename-element-for-viewselectedby-format.md) angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="6111f-177">The following example shows how to define the objects that are displayed by the table view using the [ViewSelectedBy](./viewselectedby-element-format.md) and [TypeName](./typename-element-for-viewselectedby-format.md) elements.</span></span> <span data-ttu-id="6111f-178">Es gibt keine Beschränkung für die Anzahl der [tyname](./typename-element-for-viewselectedby-format.md) -Elemente, die Sie angeben können, und ihre Reihenfolge ist nicht signifikant.</span><span class="sxs-lookup"><span data-stu-id="6111f-178">There is no limit to the number of [TypeName](./typename-element-for-viewselectedby-format.md) elements that you can specify, and their order is not significant.</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <TableControl>...</TableControl>
</View>
```

<span data-ttu-id="6111f-179">Die folgenden XML-Elemente können verwendet werden, um die Objekte anzugeben, die von der Tabellenansicht verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="6111f-179">The following XML elements can be used to specify the objects that are used by the table view:</span></span>

- <span data-ttu-id="6111f-180">Das [viewselectedby](./viewselectedby-element-format.md) -Element definiert, welche Objekte von der Listenansicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="6111f-180">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines which objects are displayed by the list view.</span></span>

- <span data-ttu-id="6111f-181">Das [tykame](./typename-element-for-viewselectedby-format.md) -Element gibt das .NET-Objekt an, das von der Sicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="6111f-181">The [TypeName](./typename-element-for-viewselectedby-format.md) element specifies the .NET object that is displayed by the view.</span></span> <span data-ttu-id="6111f-182">Der voll qualifizierte .net-Typname ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6111f-182">The fully qualified .NET type name is required.</span></span> <span data-ttu-id="6111f-183">Sie müssen mindestens einen Typ oder einen Auswahl Satz für die Sicht angeben, es gibt jedoch keine maximale Anzahl von Elementen, die angegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="6111f-183">You must specify at least one type or selection set for the view, but there is no maximum number of elements that can be specified.</span></span>

<span data-ttu-id="6111f-184">Im folgenden Beispiel werden die Elemente [viewselectedby](./viewselectedby-element-format.md) und [selectionsetname](./selectionsetname-element-for-viewselectedby-format.md) verwendet.</span><span class="sxs-lookup"><span data-stu-id="6111f-184">The following example uses the [ViewSelectedBy](./viewselectedby-element-format.md) and [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) elements.</span></span> <span data-ttu-id="6111f-185">Verwenden Sie Auswahl Sätze, bei denen Sie über einen zugehörigen Satz von Objekten verfügen, die mithilfe mehrerer Sichten angezeigt werden, z. b. Wenn Sie eine Listenansicht und eine Tabellenansicht für dieselben Objekte definieren.</span><span class="sxs-lookup"><span data-stu-id="6111f-185">Use selection sets where you have a related set of objects that are displayed using multiple views, such as when you define a list view and a table view for the same objects.</span></span> <span data-ttu-id="6111f-186">Weitere Informationen zum Erstellen eines Auswahl Satzes finden Sie unter Definieren von [Auswahl Sätzen](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="6111f-186">For more information about how to create a selection set, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <SelectionSetName>.NET Type Set</SelectionSetName>
  </ViewSelectedBy>
  <TableControl>...</TableControl>
</View>
```

<span data-ttu-id="6111f-187">Die folgenden XML-Elemente können verwendet werden, um die Objekte anzugeben, die von der Listenansicht verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="6111f-187">The following XML elements can be used to specify the objects that are used by the list view:</span></span>

- <span data-ttu-id="6111f-188">Das [viewselectedby](./viewselectedby-element-format.md) -Element definiert, welche Objekte von der Listenansicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="6111f-188">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines which objects are displayed by the list view.</span></span>

- <span data-ttu-id="6111f-189">Das [selectionsetname](./selectionsetname-element-for-viewselectedby-format.md) -Element gibt eine Gruppe von-Objekten an, die von der Sicht angezeigt werden können.</span><span class="sxs-lookup"><span data-stu-id="6111f-189">The [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) element specifies a set of objects that can be displayed by the view.</span></span> <span data-ttu-id="6111f-190">Sie müssen mindestens einen Auswahl Satz oder-Typ für die Sicht angeben, es gibt jedoch keine maximale Anzahl von Elementen, die angegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="6111f-190">You must specify at least one selection set or type for the view, but there is no maximum number of elements that can be specified.</span></span>

<span data-ttu-id="6111f-191">Im folgenden Beispiel wird gezeigt, wie die Objekte, die durch eine bestimmte Definition der Tabellenansicht angezeigt werden, mithilfe des [entryselectedby](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md) -Elements definiert werden.</span><span class="sxs-lookup"><span data-stu-id="6111f-191">The following example shows how to define the objects displayed by a specific definition of the table view using the [EntrySelectedBy](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md) element.</span></span> <span data-ttu-id="6111f-192">Mit diesem Element können Sie den .NET-Typnamen des Objekts, einen Auswahl Satz von Objekten oder eine Auswahlbedingung angeben, die angibt, wann die Definition verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6111f-192">Using this element, you can specify the .NET type name of the object, a selection set of objects, or a selection condition that specifies when the definition is used.</span></span> <span data-ttu-id="6111f-193">Weitere Informationen zum Erstellen von Auswahl Bedingungen finden Sie unter Definieren von [Bedingungen zum Anzeigen von Daten](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="6111f-193">For more information about how to create a selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

> [!NOTE]
> <span data-ttu-id="6111f-194">Wenn Sie mehrere Definitionen der Tabellenansicht erstellen, können Sie keine anderen Spaltenheader angeben.</span><span class="sxs-lookup"><span data-stu-id="6111f-194">When creating multiple definitions of the table view you cannot specify different column headers.</span></span> <span data-ttu-id="6111f-195">Sie können nur angeben, was in den Zeilen der Tabelle angezeigt wird, z. b. welche Objekte angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="6111f-195">You can specify only what is displayed in the rows of the table, such as what objects are displayed.</span></span>

```xml
<TableRowEntry>
  <EntrySelectedBy>
    <TypeName>.NET Type</TypeName>
  </EntrySelectedBy>
</TableRowEntry>
```

<span data-ttu-id="6111f-196">Die folgenden XML-Elemente können verwendet werden, um die Objekte anzugeben, die von einer bestimmten Definition der Listenansicht verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="6111f-196">The following XML elements can be used to specify the objects that are used by a specific definition of the list view:</span></span>

- <span data-ttu-id="6111f-197">Das [entryselectedby](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md) -Element definiert, welche Objekte von der Definition angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="6111f-197">The [EntrySelectedBy](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md) element defines which objects are displayed by the definition.</span></span>

- <span data-ttu-id="6111f-198">Das [tykame](./typename-element-for-entryselectedby-for-listcontrol-format.md) -Element gibt das .NET-Objekt an, das von der Definition angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="6111f-198">The [TypeName](./typename-element-for-entryselectedby-for-listcontrol-format.md) element specifies the .NET object that is displayed by the definition.</span></span> <span data-ttu-id="6111f-199">Wenn Sie dieses Element verwenden, ist der voll qualifizierte .net-Typname erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6111f-199">When using this element, the fully qualified .NET type name is required.</span></span> <span data-ttu-id="6111f-200">Sie müssen mindestens einen Typ, einen Auswahl Satz oder eine Auswahlbedingung für die Definition angeben, es gibt jedoch keine maximale Anzahl von Elementen, die angegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="6111f-200">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span>

- <span data-ttu-id="6111f-201">Das [selectionsetname](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md) -Element (nicht angezeigt) gibt eine Gruppe von Objekten an, die von dieser Definition angezeigt werden können.</span><span class="sxs-lookup"><span data-stu-id="6111f-201">The [SelectionSetName](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md) element (not shown) specifies a set of objects that can be displayed by this definition.</span></span> <span data-ttu-id="6111f-202">Sie müssen mindestens einen Typ, einen Auswahl Satz oder eine Auswahlbedingung für die Definition angeben, es gibt jedoch keine maximale Anzahl von Elementen, die angegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="6111f-202">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span>

- <span data-ttu-id="6111f-203">Das [selectioncondition](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md) -Element (nicht angezeigt) gibt eine Bedingung an, die vorhanden sein muss, damit diese Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="6111f-203">The [SelectionCondition](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md) element (not shown) specifies a condition that must exist for this definition to be used.</span></span> <span data-ttu-id="6111f-204">Sie müssen mindestens einen Typ, einen Auswahl Satz oder eine Auswahlbedingung für die Definition angeben, es gibt jedoch keine maximale Anzahl von Elementen, die angegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="6111f-204">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span> <span data-ttu-id="6111f-205">Weitere Informationen zum Definieren von Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen zum Anzeigen von Daten](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="6111f-205">For more information about defining selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="using-format-strings"></a><span data-ttu-id="6111f-206">Using-Format</span><span class="sxs-lookup"><span data-stu-id="6111f-206">Using Format Strings</span></span>

<span data-ttu-id="6111f-207">Formatierungs Zeichenfolgen können einer Ansicht hinzugefügt werden, um die Anzeige der Daten weiter zu definieren.</span><span class="sxs-lookup"><span data-stu-id="6111f-207">Formatting strings can be added to a view to further define how the data is displayed.</span></span> <span data-ttu-id="6111f-208">Im folgenden Beispiel wird gezeigt, wie eine Formatierungs Zeichenfolge für den Wert der-Eigenschaft definiert wird `StartTime` .</span><span class="sxs-lookup"><span data-stu-id="6111f-208">The following example shows how to define a formatting string for the value of the `StartTime` property.</span></span>

```xml
<TableColumnItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</TableColumnItem>
```

<span data-ttu-id="6111f-209">Die folgenden XML-Elemente können verwendet werden, um ein Format Muster anzugeben:</span><span class="sxs-lookup"><span data-stu-id="6111f-209">The following XML elements can be used to specify a format pattern:</span></span>

- <span data-ttu-id="6111f-210">Das [tablecolumnitem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) -Element definiert die Eigenschaft oder das Skript, dessen Wert in der Spalte der Zeile angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="6111f-210">The [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) element defines the property or script whose value is displayed in the column of the row.</span></span> <span data-ttu-id="6111f-211">Für jede Spalte der Zeile ist ein [tablecolumnitem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) -Element erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6111f-211">A [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) element is required for each column of the row.</span></span> <span data-ttu-id="6111f-212">Der erste Eintrag wird in der ersten Spalte angezeigt, der zweite Eintrag in der zweiten Spalte usw.</span><span class="sxs-lookup"><span data-stu-id="6111f-212">The first entry is displayed in first column, the second entry in the second column, and so on.</span></span>

- <span data-ttu-id="6111f-213">Das [propertyName](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md) -Element gibt die-Eigenschaft an, deren Wert in der Zeile angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="6111f-213">The [PropertyName](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md) element specifies the property whose value is displayed in the row.</span></span> <span data-ttu-id="6111f-214">Sie müssen entweder eine Eigenschaft oder ein Skript angeben, aber Sie können nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="6111f-214">You must specify either a property or a script, but you cannot specify both.</span></span>

- <span data-ttu-id="6111f-215">Das Format [String](./label-element-for-listitem-for-listcontrol-format.md) -Element gibt ein Format Muster an, das definiert, wie der Eigenschafts-oder Skript Wert angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="6111f-215">The [FormatString](./label-element-for-listitem-for-listcontrol-format.md) element specifies a format pattern that defines how the property or script value is displayed.</span></span>

<span data-ttu-id="6111f-216">Im folgenden Beispiel wird die- `ToString` Methode aufgerufen, um den Wert des Skripts zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="6111f-216">In the following example, the `ToString` method is called to format the value of the script.</span></span> <span data-ttu-id="6111f-217">Skripts können beliebige Methoden eines Objekts aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="6111f-217">Scripts can call any method of an object.</span></span> <span data-ttu-id="6111f-218">Wenn ein Objekt über eine-Methode verfügt, z. b. `ToString` mit Formatierungs Parametern, kann das Skript daher diese Methode zum Formatieren des Ausgabe Werts des Skripts aufruft.</span><span class="sxs-lookup"><span data-stu-id="6111f-218">Therefore, if an object has a method, such as `ToString`, that has formatting parameters, the script can call that method to format the output value of the script.</span></span>

```xml
<ListItem>
  <ScriptBlock>
    [String]::Format("(0,10) (1,8)", .LastWriteTime.ToString("d"),
    $_.LastWriteTime.Totring("t"))
  </ScriptBlock>
</ListItem>
```

<span data-ttu-id="6111f-219">Das folgende XML-Element kann zum Aufrufen der- `ToString` Methode verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="6111f-219">The following XML element can be used to calling the `ToString` method:</span></span>

- <span data-ttu-id="6111f-220">Das [tablecolumnitem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) -Element definiert die Eigenschaft oder das Skript, dessen Wert in der Spalte der Zeile angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="6111f-220">The [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) element defines the property or script whose value is displayed in the column of the row.</span></span> <span data-ttu-id="6111f-221">Für jede Spalte der Zeile ist ein [tablecolumnitem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) -Element erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6111f-221">A [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) element is required for each column of the row.</span></span> <span data-ttu-id="6111f-222">Der erste Eintrag wird in der ersten Spalte angezeigt, der zweite Eintrag in der zweiten Spalte usw.</span><span class="sxs-lookup"><span data-stu-id="6111f-222">The first entry is displayed in first column, the second entry in the second column, and so on.</span></span>

- <span data-ttu-id="6111f-223">Das [ScriptBlock](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md) -Element gibt das Skript an, dessen Wert in der Zeile angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="6111f-223">The [ScriptBlock](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md) element specifies the script whose value is displayed in the row.</span></span> <span data-ttu-id="6111f-224">Sie müssen entweder ein-Skript oder eine-Eigenschaft angeben, aber Sie können nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="6111f-224">You must specify either a script or a property, but you cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="6111f-225">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6111f-225">See Also</span></span>

[<span data-ttu-id="6111f-226">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="6111f-226">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
