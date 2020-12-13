---
ms.date: 09/13/2016
ms.topic: reference
title: Erstellen einer breiten Ansicht
description: Erstellen einer breiten Ansicht
ms.openlocfilehash: 4230ef91a3612e962b2773b12e8016df6f760eae
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655607"
---
# <a name="creating-a-wide-view"></a><span data-ttu-id="c6049-103">Erstellen einer breiten Ansicht</span><span class="sxs-lookup"><span data-stu-id="c6049-103">Creating a Wide View</span></span>

<span data-ttu-id="c6049-104">Eine breite Ansicht zeigt einen einzelnen Wert für jedes angezeigte Objekt an.</span><span class="sxs-lookup"><span data-stu-id="c6049-104">A wide view displays a single value for each object that is displayed.</span></span> <span data-ttu-id="c6049-105">Der angezeigte Wert kann der Wert einer .NET-Objekt Eigenschaft oder der Wert eines Skripts sein.</span><span class="sxs-lookup"><span data-stu-id="c6049-105">The displayed value can be the value of a .NET object property or the value of a script.</span></span> <span data-ttu-id="c6049-106">Standardmäßig gibt es für diese Ansicht keine Bezeichnung oder einen Header.</span><span class="sxs-lookup"><span data-stu-id="c6049-106">By default, there is no label or header for this view.</span></span>

## <a name="a-wide-view-display"></a><span data-ttu-id="c6049-107">Eine breite Anzeige Ansicht</span><span class="sxs-lookup"><span data-stu-id="c6049-107">A Wide View Display</span></span>

<span data-ttu-id="c6049-108">Das folgende Beispiel zeigt, wie Windows PowerShell das [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) -Objekt anzeigt, das vom Cmdlet " [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) " zurückgegeben wird, wenn die Ausgabe an das Cmdlet " [Format-Wide](/powershell/module/Microsoft.PowerShell.Utility/Format-Wide) " weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="c6049-108">The following example shows how Windows PowerShell displays the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object that is returned by the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet when its output is piped to the [Format-Wide](/powershell/module/Microsoft.PowerShell.Utility/Format-Wide) cmdlet.</span></span> <span data-ttu-id="c6049-109">(Standardmäßig gibt das [Get-Process-](/powershell/module/Microsoft.PowerShell.Management/Get-Process) Cmdlet eine Tabellenansicht zurück.) In diesem Beispiel werden die beiden Spalten verwendet, um den Namen des Prozesses für jedes zurückgegebene Objekt anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c6049-109">(By default, the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet returns a table view.) In this example, the two columns are used to display the name of the process for each returned object.</span></span> <span data-ttu-id="c6049-110">Der Name der Eigenschaft des Objekts wird nicht angezeigt, sondern nur der Wert der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="c6049-110">The name of the object's property is not displayed, only the value of the property.</span></span>

```
Get-Process | format-wide
AEADISRV                     agrsmsvc
Ati2evxx                     Ati2evxx
audiodg                      CCC
CcmExec                      communicator
Crypserv                     csrss
csrss                        DevDtct2
DM1Service                   dpupdchk
dwm                          DxStudio
EXCEL                        explorer
GoogleToolbarNotifier        GrooveMonitor
hpqwmiex                     hpservice
Idle                         InoRpc
InoRT                        InoTask
ipoint                       lsass
lsm                          MOM
MSASCui                      notepad
...                          ...

```

## <a name="defining-the-wide-view"></a><span data-ttu-id="c6049-111">Definieren der breiten Ansicht</span><span class="sxs-lookup"><span data-stu-id="c6049-111">Defining the Wide View</span></span>

<span data-ttu-id="c6049-112">Der folgende XML-Code zeigt das breite Ansichts Schema für das [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) -Objekt.</span><span class="sxs-lookup"><span data-stu-id="c6049-112">The following XML shows the wide view schema for the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
View>
  <Name>process</Name>
  <ViewSelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </ViewSelectedBy>
  <GroupBy>...</GroupBy>
  <Controls>...</Controls>
  <WideControl>
    <WideEntries>
      <WideEntry>
        <WideItem>
          <PropertyName>ProcessName</PropertyName>
        </WideItem>
      </WideEntry>
    </WideEntries>
  </WideControl>
</View>

```

<span data-ttu-id="c6049-113">Die folgenden XML-Elemente werden zum Definieren einer breiten Ansicht verwendet:</span><span class="sxs-lookup"><span data-stu-id="c6049-113">The following XML elements are used to define a wide view:</span></span>

- <span data-ttu-id="c6049-114">Das [View](./view-element-format.md) -Element ist das übergeordnete Element der breiten Ansicht.</span><span class="sxs-lookup"><span data-stu-id="c6049-114">The [View](./view-element-format.md) element is the parent element of the wide view.</span></span> <span data-ttu-id="c6049-115">(Dies ist dasselbe übergeordnete Element für die Tabellen-, Listen-und benutzerdefinierten Steuerelement Sichten.)</span><span class="sxs-lookup"><span data-stu-id="c6049-115">(This is the same parent element for the table, list, and custom control views.)</span></span>

- <span data-ttu-id="c6049-116">Das [Name](./name-element-for-view-format.md) -Element gibt den Namen der Ansicht an.</span><span class="sxs-lookup"><span data-stu-id="c6049-116">The [Name](./name-element-for-view-format.md) element specifies the name of the view.</span></span> <span data-ttu-id="c6049-117">Dieses Element ist für alle Sichten erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c6049-117">This element is required for all views.</span></span>

- <span data-ttu-id="c6049-118">Das [viewselectedby](./viewselectedby-element-format.md) -Element definiert die Objekte, die die Ansicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="c6049-118">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines the objects that use the view.</span></span> <span data-ttu-id="c6049-119">Dieses Element ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c6049-119">This element is required.</span></span>

- <span data-ttu-id="c6049-120">Das [GroupBy](./groupby-element-for-view-format.md) -Element definiert, wann eine neue Gruppe von Objekten angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c6049-120">The [GroupBy](./groupby-element-for-view-format.md) element defines when a new group of objects is displayed.</span></span> <span data-ttu-id="c6049-121">Eine neue Gruppe wird immer dann gestartet, wenn der Wert einer bestimmten Eigenschaft oder eines Skripts geändert wird.</span><span class="sxs-lookup"><span data-stu-id="c6049-121">A new group is started whenever the value of a specific property or script changes.</span></span> <span data-ttu-id="c6049-122">Dieses Element ist optional.</span><span class="sxs-lookup"><span data-stu-id="c6049-122">This element is optional.</span></span>

- <span data-ttu-id="c6049-123">Die [Steuerelemente der](./controls-element-for-view-format.md) Steuerelemente definieren die benutzerdefinierten Steuerelemente, die von der breiten Ansicht definiert werden.</span><span class="sxs-lookup"><span data-stu-id="c6049-123">The [Controls](./controls-element-for-view-format.md) elements defines the custom controls that are defined by the wide view.</span></span> <span data-ttu-id="c6049-124">Steuerelemente geben Ihnen eine Möglichkeit, die Anzeige der Daten weiter anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c6049-124">Controls give you a way to further specify how the data is displayed.</span></span> <span data-ttu-id="c6049-125">Dieses Element ist optional.</span><span class="sxs-lookup"><span data-stu-id="c6049-125">This element is optional.</span></span> <span data-ttu-id="c6049-126">Eine Sicht kann eigene benutzerdefinierte Steuerelemente definieren, oder Sie kann allgemeine Steuerelemente verwenden, die von jeder Ansicht in der Formatierungs Datei verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="c6049-126">A view can define its own custom controls, or it can use common controls that can be used by any view in the formatting file.</span></span> <span data-ttu-id="c6049-127">Weitere Informationen zu benutzerdefinierten Steuerelementen finden Sie unter [Erstellen von benutzerdefinierten Steuerelementen](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="c6049-127">For more information about custom controls, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

- <span data-ttu-id="c6049-128">Das [widecontrol](./widecontrol-element-format.md) -Element und seine untergeordneten Elemente definieren, was in der Ansicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c6049-128">The [WideControl](./widecontrol-element-format.md) element and its child elements define what is displayed in the view.</span></span> <span data-ttu-id="c6049-129">Im vorherigen Beispiel wurde die-Sicht entworfen, um die [System. Diagnostics. Process. ProcessName](/dotnet/api/System.Diagnostics.Process.ProcessName) -Eigenschaft anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c6049-129">In the preceding example, the view is designed to display the [System.Diagnostics.Process.Processname](/dotnet/api/System.Diagnostics.Process.ProcessName) property.</span></span>

<span data-ttu-id="c6049-130">Ein Beispiel für eine komplette Formatierungs Datei, die eine einfache Breite Ansicht definiert, finden Sie unter [Wide View (Basic)](./wide-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="c6049-130">For an example of a complete formatting file that defines a simple wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="providing-definitions-for-your-wide-view"></a><span data-ttu-id="c6049-131">Bereitstellen von Definitionen für Ihre breite Ansicht</span><span class="sxs-lookup"><span data-stu-id="c6049-131">Providing Definitions for Your Wide View</span></span>

<span data-ttu-id="c6049-132">Breite Ansichten können mithilfe der untergeordneten Elemente des [widecontrol](./widecontrol-element-format.md) -Elements eine oder mehrere Definitionen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="c6049-132">Wide views can provide one or more definitions by using the child elements of the [WideControl](./widecontrol-element-format.md) element.</span></span> <span data-ttu-id="c6049-133">In der Regel hat eine Ansicht nur eine Definition.</span><span class="sxs-lookup"><span data-stu-id="c6049-133">Typically, a view will have only one definition.</span></span> <span data-ttu-id="c6049-134">Im folgenden Beispiel stellt die Sicht eine einzelne Definition bereit, in der der Wert der [System. Diagnostics. Process. ProcessName](/dotnet/api/System.Diagnostics.Process.ProcessName) -Eigenschaft angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c6049-134">In the following example, the view provides a single definition that displays the value of the [System.Diagnostics.Process.Processname](/dotnet/api/System.Diagnostics.Process.ProcessName) property.</span></span> <span data-ttu-id="c6049-135">In einer breiten Ansicht kann der Wert einer Eigenschaft oder der Wert eines Skripts angezeigt werden (nicht im Beispiel dargestellt).</span><span class="sxs-lookup"><span data-stu-id="c6049-135">A wide view can display the value of a property or the value of a script (not shown in the example).</span></span>

```xml
<WideControl>
  <AutoSize/>
  <ColumnNumber></ColumnNumber>
  <WideEntries>
    <WideEntry>
      <WideItem>
        <PropertyName>ProcessName</PropertyName>
      </WideItem>
    </WideEntry>
  </WideEntries>
</WideControl>
```

<span data-ttu-id="c6049-136">Die folgenden XML-Elemente können verwendet werden, um Definitionen für eine breite Ansicht bereitzustellen:</span><span class="sxs-lookup"><span data-stu-id="c6049-136">The following XML elements can be used to provide definitions for a wide view:</span></span>

- <span data-ttu-id="c6049-137">Das [widecontrol](./widecontrol-element-format.md) -Element und seine untergeordneten Elemente definieren, was in der Ansicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c6049-137">The [WideControl](./widecontrol-element-format.md) element and its child elements define what is displayed in the view.</span></span>

- <span data-ttu-id="c6049-138">Das [AutoSize](./autosize-element-for-widecontrol-format.md) -Element gibt an, ob die Spaltengröße und die Anzahl der Spalten basierend auf der Größe der Daten angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="c6049-138">The [AutoSize](./autosize-element-for-widecontrol-format.md) element specifies whether the column size and the number of columns are adjusted based on the size of the data.</span></span> <span data-ttu-id="c6049-139">Dieses Element ist optional.</span><span class="sxs-lookup"><span data-stu-id="c6049-139">This element is optional.</span></span>

- <span data-ttu-id="c6049-140">Das [ColumnNumber](./columnnumber-element-for-widecontrol-format.md) -Element gibt die Anzahl der Spalten an, die in der breiten Ansicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c6049-140">The [ColumnNumber](./columnnumber-element-for-widecontrol-format.md) element specifies the number of columns displayed in the wide view.</span></span> <span data-ttu-id="c6049-141">Dieses Element ist optional.</span><span class="sxs-lookup"><span data-stu-id="c6049-141">This element is optional.</span></span>

- <span data-ttu-id="c6049-142">Das [wideentries](./wideentries-element-for-widecontrol-format.md) -Element stellt die Definitionen der Sicht bereit.</span><span class="sxs-lookup"><span data-stu-id="c6049-142">The [WideEntries](./wideentries-element-for-widecontrol-format.md) element provides the definitions of the view.</span></span> <span data-ttu-id="c6049-143">In den meisten Fällen weist eine Ansicht nur eine Definition auf.</span><span class="sxs-lookup"><span data-stu-id="c6049-143">In most cases, a view will have only one definition.</span></span> <span data-ttu-id="c6049-144">Dieses Element ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c6049-144">This element is required.</span></span>

- <span data-ttu-id="c6049-145">Das [wideentry](./wideentry-element-for-widecontrol-format.md) -Element stellt eine Definition der Sicht bereit.</span><span class="sxs-lookup"><span data-stu-id="c6049-145">The [WideEntry](./wideentry-element-for-widecontrol-format.md) element provides a definition of the view.</span></span> <span data-ttu-id="c6049-146">Mindestens ein " [wideentry](./wideentry-element-for-widecontrol-format.md) " ist erforderlich. Es gibt jedoch keine maximale Beschränkung für die Anzahl der Elemente, die Sie hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="c6049-146">At least one [WideEntry](./wideentry-element-for-widecontrol-format.md) is required; however, there is no maximum limit to the number of elements that you can add.</span></span> <span data-ttu-id="c6049-147">In den meisten Fällen weist eine Ansicht nur eine Definition auf.</span><span class="sxs-lookup"><span data-stu-id="c6049-147">In most cases, a view will have only one definition.</span></span>

- <span data-ttu-id="c6049-148">Das [entryselectedby](./entryselectedby-element-for-wideentry-format.md) -Element gibt die Objekte an, die von einer bestimmten Definition angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c6049-148">The [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md) element specifies the objects that are displayed by a specific definition.</span></span> <span data-ttu-id="c6049-149">Dieses Element ist optional und nur erforderlich, wenn Sie mehrere [wideentry](./wideentry-element-for-widecontrol-format.md) -Elemente definieren, die verschiedene-Objekte anzeigen.</span><span class="sxs-lookup"><span data-stu-id="c6049-149">This element is optional and is needed only when you define multiple [WideEntry](./wideentry-element-for-widecontrol-format.md) elements that display different objects.</span></span>

- <span data-ttu-id="c6049-150">Das [wideitem](./wideitem-element-for-widecontrol-format.md) -Element gibt die Daten an, die von der Sicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c6049-150">The [WideItem](./wideitem-element-for-widecontrol-format.md) element specifies the data that is displayed by the view.</span></span> <span data-ttu-id="c6049-151">Im Gegensatz zu anderen Sicht Typen kann ein breites Steuerelement nur ein Element anzeigen.</span><span class="sxs-lookup"><span data-stu-id="c6049-151">In contrast to other types of views, a wide control can display only one item.</span></span>

- <span data-ttu-id="c6049-152">Das [propertyName](./propertyname-element-for-wideitem-for-widecontrol-format.md) -Element gibt die Eigenschaft an, deren Wert von der Sicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c6049-152">The [PropertyName](./propertyname-element-for-wideitem-for-widecontrol-format.md) element specifies the property whose value is displayed by the view.</span></span> <span data-ttu-id="c6049-153">Sie müssen entweder eine Eigenschaft oder ein Skript angeben, aber Sie können nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="c6049-153">You must specify either a property or a script, but you cannot specify both.</span></span>

- <span data-ttu-id="c6049-154">Das [ScriptBlock](./scriptblock-element-for-wideitem-for-widecontrol-format.md) -Element gibt das Skript an, dessen Wert von der Sicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c6049-154">The [ScriptBlock](./scriptblock-element-for-wideitem-for-widecontrol-format.md) element specifies the script whose value is displayed by the view.</span></span> <span data-ttu-id="c6049-155">Sie müssen entweder ein-Skript oder eine-Eigenschaft angeben, aber Sie können nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="c6049-155">You must specify either a script or a property, but you cannot specify both.</span></span>

- <span data-ttu-id="c6049-156">Das [FormatString](./formatstring-element-for-wideitem-for-widecontrol-format.md) -Element gibt ein Muster an, das zum Anzeigen der Daten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c6049-156">The [FormatString](./formatstring-element-for-wideitem-for-widecontrol-format.md) element specifies a pattern that is used to display the data.</span></span> <span data-ttu-id="c6049-157">Dieses Element ist optional.</span><span class="sxs-lookup"><span data-stu-id="c6049-157">This element is optional.</span></span>

<span data-ttu-id="c6049-158">Ein Beispiel für eine komplette Formatierungs Datei, die eine breite Sicht Definition definiert, finden Sie unter [Wide View (Basic)](./wide-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="c6049-158">For an example of a complete formatting file that defines a wide view definition, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="defining-the-objects-that-use-the-wide-view"></a><span data-ttu-id="c6049-159">Definieren der Objekte, die die Breite Ansicht verwenden</span><span class="sxs-lookup"><span data-stu-id="c6049-159">Defining the Objects That Use the Wide View</span></span>

<span data-ttu-id="c6049-160">Es gibt zwei Möglichkeiten, um zu definieren, welche .NET-Objekte die Breite Ansicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="c6049-160">There are two ways to define which .NET objects use the wide view.</span></span> <span data-ttu-id="c6049-161">Sie können das [viewselectedby](./viewselectedby-element-format.md) -Element verwenden, um die Objekte zu definieren, die von allen Definitionen der Sicht angezeigt werden können, oder Sie können das [entryselectedby](./entryselectedby-element-for-wideentry-format.md) -Element verwenden, um zu definieren, welche Objekte von einer bestimmten Definition der Sicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c6049-161">You can use the [ViewSelectedBy](./viewselectedby-element-format.md) element to define the objects that can be displayed by all the definitions of the view, or you can use the [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md) element to define which objects are displayed by a specific definition of the view.</span></span> <span data-ttu-id="c6049-162">In den meisten Fällen verfügt eine Sicht nur über eine Definition, sodass Objekte normalerweise durch das [viewselectedby](./viewselectedby-element-format.md) -Element definiert werden.</span><span class="sxs-lookup"><span data-stu-id="c6049-162">In most cases, a view has only one definition, so objects are typically defined by the [ViewSelectedBy](./viewselectedby-element-format.md) element.</span></span>

<span data-ttu-id="c6049-163">Im folgenden Beispiel wird gezeigt, wie die-Objekte definiert werden, die von der breiten Ansicht mithilfe der Elemente [viewselectedby](./viewselectedby-element-format.md) und [tygtame](./typename-element-for-viewselectedby-format.md) angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c6049-163">The following example shows how to define the objects that are displayed by the wide view using the [ViewSelectedBy](./viewselectedby-element-format.md) and [TypeName](./typename-element-for-viewselectedby-format.md) elements.</span></span> <span data-ttu-id="c6049-164">Es gibt keine Beschränkung für die Anzahl der [tyname](./typename-element-for-viewselectedby-format.md) -Elemente, die Sie angeben können, und ihre Reihenfolge ist nicht signifikant.</span><span class="sxs-lookup"><span data-stu-id="c6049-164">There is no limit to the number of [TypeName](./typename-element-for-viewselectedby-format.md) elements that you can specify, and their order is not significant.</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </ViewSelectedBy>
  <WideControl>...</WideControl>
</View>
```

<span data-ttu-id="c6049-165">Die folgenden XML-Elemente können verwendet werden, um die Objekte anzugeben, die von der breiten Ansicht verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="c6049-165">The following XML elements can be used to specify the objects that are used by the wide view:</span></span>

- <span data-ttu-id="c6049-166">Das [viewselectedby](./viewselectedby-element-format.md) -Element definiert, welche Objekte von der breiten Ansicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c6049-166">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines which objects are displayed by the wide view.</span></span>

- <span data-ttu-id="c6049-167">Das [tygtame](./typename-element-for-viewselectedby-format.md) -Element gibt das von der Sicht angezeigte .net an.</span><span class="sxs-lookup"><span data-stu-id="c6049-167">The [TypeName](./typename-element-for-viewselectedby-format.md) element specifies the .NET that is displayed by the view.</span></span> <span data-ttu-id="c6049-168">Der voll qualifizierte .net-Typname ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c6049-168">The fully qualified .NET type name is required.</span></span> <span data-ttu-id="c6049-169">Sie müssen mindestens einen Typ oder einen Auswahl Satz für die Sicht angeben, es gibt jedoch keine maximale Anzahl von Elementen, die angegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="c6049-169">You must specify at least one type or selection set for the view, but there is no maximum number of elements that can be specified.</span></span>

<span data-ttu-id="c6049-170">Ein Beispiel für eine komplette Formatierungs Datei finden Sie unter [Wide View (Basic)](./wide-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="c6049-170">For an example of a complete formatting file, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

<span data-ttu-id="c6049-171">Im folgenden Beispiel werden die Elemente [viewselectedby](./viewselectedby-element-format.md) und [selectionsetname](./selectionsetname-element-for-viewselectedby-format.md) verwendet.</span><span class="sxs-lookup"><span data-stu-id="c6049-171">The following example uses the [ViewSelectedBy](./viewselectedby-element-format.md) and [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) elements.</span></span> <span data-ttu-id="c6049-172">Verwenden Sie Auswahl Sätze, bei denen Sie über einen zugehörigen Satz von Objekten verfügen, die mithilfe mehrerer Sichten angezeigt werden, z. b. Wenn Sie eine breite Ansicht und eine Tabellenansicht für dieselben Objekte definieren.</span><span class="sxs-lookup"><span data-stu-id="c6049-172">Use selection sets where you have a related set of objects that are displayed using multiple views, such as when you define a wide view and a table view for the same objects.</span></span> <span data-ttu-id="c6049-173">Weitere Informationen zum Erstellen eines Auswahl Satzes finden Sie unter Definieren von [Auswahl Sätzen](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="c6049-173">For more information about how to create a selection set, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <SelectionSetName>.NET Type Set</SelectionSetName>
  </ViewSelectedBy>
  <WideControl>...</WideControl>
</View>
```

<span data-ttu-id="c6049-174">Die folgenden XML-Elemente können verwendet werden, um die Objekte anzugeben, die von der breiten Ansicht verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="c6049-174">The following XML elements can be used to specify the objects that are used by the wide view:</span></span>

- <span data-ttu-id="c6049-175">Das [viewselectedby](./viewselectedby-element-format.md) -Element definiert, welche Objekte von der breiten Ansicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c6049-175">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines which objects are displayed by the wide view.</span></span>

- <span data-ttu-id="c6049-176">Das [selectionsetname](./selectionsetname-element-for-viewselectedby-format.md) -Element gibt eine Gruppe von-Objekten an, die von der Sicht angezeigt werden können.</span><span class="sxs-lookup"><span data-stu-id="c6049-176">The [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) element specifies a set of objects that can be displayed by the view.</span></span> <span data-ttu-id="c6049-177">Sie müssen mindestens einen Auswahl Satz oder-Typ für die Sicht angeben, es gibt jedoch keine maximale Anzahl von Elementen, die angegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="c6049-177">You must specify at least one selection set or type for the view, but there is no maximum number of elements that can be specified.</span></span>

<span data-ttu-id="c6049-178">Im folgenden Beispiel wird gezeigt, wie die-Objekte, die durch eine bestimmte Definition der breiten Ansicht angezeigt werden, mithilfe des [entryselectedby](./entryselectedby-element-for-wideentry-format.md) -Elements definiert werden.</span><span class="sxs-lookup"><span data-stu-id="c6049-178">The following example shows how to define the objects displayed by a specific definition of the wide view using the [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md) element.</span></span> <span data-ttu-id="c6049-179">Mit diesem Element können Sie den .NET-Typnamen des Objekts, einen Auswahl Satz von Objekten oder eine Auswahlbedingung angeben, die angibt, wann die Definition verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c6049-179">Using this element, you can specify the .NET type name of the object, a selection set of objects, or a selection condition that specifies when the definition is used.</span></span> <span data-ttu-id="c6049-180">Weitere Informationen zum Erstellen von Auswahl Bedingungen finden Sie unter Definieren von [Bedingungen zum Anzeigen von Daten](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="c6049-180">For more information about how to create a selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

```xml
<WideEntry>
  <EntrySelectedBy>
    <TypeName>.NET Type</TypeName>
  </EntrySelectedBy>
</WideEntry>
```

<span data-ttu-id="c6049-181">Die folgenden XML-Elemente können verwendet werden, um die Objekte anzugeben, die von einer bestimmten Definition der breiten Ansicht verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="c6049-181">The following XML elements can be used to specify the objects that are used by a specific definition of the wide view:</span></span>

- <span data-ttu-id="c6049-182">Das [entryselectedby](./entryselectedby-element-for-wideentry-format.md) -Element definiert, welche Objekte von der Definition angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c6049-182">The [EntrySelectedBy](./entryselectedby-element-for-wideentry-format.md) element defines which objects are displayed by the definition.</span></span>

- <span data-ttu-id="c6049-183">Das [tykame](./typename-element-for-viewselectedby-format.md) -Element gibt das .net an, das von der Definition angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c6049-183">The [TypeName](./typename-element-for-viewselectedby-format.md) element specifies the .NET that is displayed by the definition.</span></span> <span data-ttu-id="c6049-184">Wenn Sie dieses Element verwenden, ist der voll qualifizierte .net-Typname erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c6049-184">When using this element the fully qualified .NET type name is required.</span></span> <span data-ttu-id="c6049-185">Sie müssen mindestens einen Typ, einen Auswahl Satz oder eine Auswahlbedingung für die Definition angeben, es gibt jedoch keine maximale Anzahl von Elementen, die angegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="c6049-185">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span>

- <span data-ttu-id="c6049-186">Das [selectionsetname](./selectionsetname-element-for-viewselectedby-format.md) -Element (nicht angezeigt) gibt eine Gruppe von Objekten an, die von dieser Definition angezeigt werden können.</span><span class="sxs-lookup"><span data-stu-id="c6049-186">The [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) element (not shown) specifies a set of objects that can be displayed by this definition.</span></span> <span data-ttu-id="c6049-187">Sie müssen mindestens einen Typ, einen Auswahl Satz oder eine Auswahlbedingung für die Definition angeben, es gibt jedoch keine maximale Anzahl von Elementen, die angegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="c6049-187">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span>

- <span data-ttu-id="c6049-188">Das [selectioncondition](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md) -Element (nicht angezeigt) gibt eine Bedingung an, die vorhanden sein muss, damit diese Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="c6049-188">The [SelectionCondition](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md) element (not shown) specifies a condition that must exist for this definition to be used.</span></span> <span data-ttu-id="c6049-189">Sie müssen mindestens einen Typ, einen Auswahl Satz oder eine Auswahlbedingung für die Definition angeben, es gibt jedoch keine maximale Anzahl von Elementen, die angegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="c6049-189">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span> <span data-ttu-id="c6049-190">Weitere Informationen zum Definieren von Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen zum Anzeigen von Daten](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="c6049-190">For more information about defining selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="displaying-groups-of-objects-in-a-wide-view"></a><span data-ttu-id="c6049-191">Anzeigen von Gruppen von Objekten in einer breiten Ansicht</span><span class="sxs-lookup"><span data-stu-id="c6049-191">Displaying Groups of objects in a Wide View</span></span>

<span data-ttu-id="c6049-192">Sie können die Objekte, die von der breiten Ansicht angezeigt werden, in Gruppen aufteilen.</span><span class="sxs-lookup"><span data-stu-id="c6049-192">You can separate the objects that are displayed by the wide view into groups.</span></span> <span data-ttu-id="c6049-193">Dies bedeutet nicht, dass Sie eine Gruppe definieren, sondern nur, dass Windows PowerShell eine neue Gruppe startet, wenn der Wert einer bestimmten Eigenschaft oder eines Skripts geändert wird.</span><span class="sxs-lookup"><span data-stu-id="c6049-193">This does not mean that you define a group, only that Windows PowerShell starts a new group whenever the value of a specific property or script changes.</span></span> <span data-ttu-id="c6049-194">Im folgenden Beispiel wird eine neue Gruppe immer dann gestartet, wenn sich der Wert der [System. ServiceProcess. ServiceController. ServiceType](/dotnet/api/System.ServiceProcess.ServiceController.ServiceType) -Eigenschaft ändert.</span><span class="sxs-lookup"><span data-stu-id="c6049-194">In the following example, a new group is started whenever the value of the [System.Serviceprocess.Servicecontroller.Servicetype](/dotnet/api/System.ServiceProcess.ServiceController.ServiceType) property changes.</span></span>

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

<span data-ttu-id="c6049-195">Die folgenden XML-Elemente werden verwendet, um zu definieren, wann eine Gruppe gestartet wird:</span><span class="sxs-lookup"><span data-stu-id="c6049-195">The following XML elements are used to define when a group is started:</span></span>

- <span data-ttu-id="c6049-196">Das [GroupBy](./groupby-element-for-view-format.md) -Element definiert die Eigenschaft oder das Skript, das die neue Gruppe startet und definiert, wie die Gruppe angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c6049-196">The [GroupBy](./groupby-element-for-view-format.md) element defines the property or script that starts the new group and defines how the group is displayed.</span></span>

- <span data-ttu-id="c6049-197">Das [propertyName](./propertyname-element-for-groupby-format.md) -Element gibt die Eigenschaft an, die eine neue Gruppe startet, wenn sich der Wert ändert.</span><span class="sxs-lookup"><span data-stu-id="c6049-197">The [PropertyName](./propertyname-element-for-groupby-format.md) element specifies the property that starts a new group whenever its value changes.</span></span> <span data-ttu-id="c6049-198">Sie müssen eine Eigenschaft oder ein Skript angeben, um die Gruppe zu starten, aber Sie können nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="c6049-198">You must specify a property or script to start the group, but you cannot specify both.</span></span>

- <span data-ttu-id="c6049-199">Das [ScriptBlock](./scriptblock-element-for-groupby-format.md) -Element gibt das Skript an, das eine neue Gruppe startet, wenn sich der Wert ändert.</span><span class="sxs-lookup"><span data-stu-id="c6049-199">The [ScriptBlock](./scriptblock-element-for-groupby-format.md) element specifies the script that starts a new group whenever its value changes.</span></span> <span data-ttu-id="c6049-200">Sie müssen ein Skript oder eine Eigenschaft angeben, um die Gruppe zu starten, aber Sie können nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="c6049-200">You must specify a script or property to start the group, but you cannot specify both.</span></span>

- <span data-ttu-id="c6049-201">Das [Label](./label-element-for-groupby-format.md) -Element definiert eine Bezeichnung, die am Anfang jeder Gruppe angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c6049-201">The [Label](./label-element-for-groupby-format.md) element defines a label that is displayed at the beginning of each group.</span></span> <span data-ttu-id="c6049-202">Zusätzlich zu dem Text, der von diesem Element angegeben wird, zeigt Windows PowerShell den Wert an, der die neue Gruppe ausgelöst hat, und fügt vor und nach der Bezeichnung eine leere Zeile hinzu.</span><span class="sxs-lookup"><span data-stu-id="c6049-202">In addition to the text specified by this element, Windows PowerShell displays the value that triggered the new group and adds a blank line before and after the label.</span></span> <span data-ttu-id="c6049-203">Dieses Element ist optional.</span><span class="sxs-lookup"><span data-stu-id="c6049-203">This element is optional.</span></span>

- <span data-ttu-id="c6049-204">Das [CustomControl](./customcontrol-element-for-groupby-format.md) -Element definiert ein Steuerelement, das zum Anzeigen der Daten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c6049-204">The [CustomControl](./customcontrol-element-for-groupby-format.md) element defines a control that is used to display the data.</span></span> <span data-ttu-id="c6049-205">Dieses Element ist optional.</span><span class="sxs-lookup"><span data-stu-id="c6049-205">This element is optional.</span></span>

- <span data-ttu-id="c6049-206">Das [customcontrolname](./customcontrolname-element-for-groupby-format.md) -Element gibt ein Common-oder View-Steuerelement an, das zum Anzeigen der Daten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c6049-206">The [CustomControlName](./customcontrolname-element-for-groupby-format.md) element specifies a common or view control that is used to display the data.</span></span> <span data-ttu-id="c6049-207">Dieses Element ist optional.</span><span class="sxs-lookup"><span data-stu-id="c6049-207">This element is optional.</span></span>

<span data-ttu-id="c6049-208">Ein Beispiel für eine komplette Formatierungs Datei, die Gruppen definiert, finden Sie unter [Wide View (GroupBy)](./wide-view-groupby.md).</span><span class="sxs-lookup"><span data-stu-id="c6049-208">For an example of a complete formatting file that defines groups, see [Wide View (GroupBy)](./wide-view-groupby.md).</span></span>

## <a name="using-format-strings"></a><span data-ttu-id="c6049-209">Using-Format</span><span class="sxs-lookup"><span data-stu-id="c6049-209">Using Format Strings</span></span>

<span data-ttu-id="c6049-210">Formatierungs Zeichenfolgen können einer breiten Ansicht hinzugefügt werden, um die Anzeige der Daten weiter zu definieren.</span><span class="sxs-lookup"><span data-stu-id="c6049-210">Formatting strings can be added to a wide view to further define how the data is displayed.</span></span> <span data-ttu-id="c6049-211">Im folgenden Beispiel wird gezeigt, wie eine Formatierungs Zeichenfolge für den Wert der-Eigenschaft definiert wird `StartTime` .</span><span class="sxs-lookup"><span data-stu-id="c6049-211">The following example shows how to define a formatting string for the value of the `StartTime` property.</span></span>

```xml
<WideItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</WideItem>
```

<span data-ttu-id="c6049-212">Die folgenden XML-Elemente können verwendet werden, um ein Format Muster anzugeben:</span><span class="sxs-lookup"><span data-stu-id="c6049-212">The following XML elements can be used to specify a format pattern:</span></span>

- <span data-ttu-id="c6049-213">Das [wideitem](./wideitem-element-for-widecontrol-format.md) -Element gibt die Daten an, die von der Sicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c6049-213">The [WideItem](./wideitem-element-for-widecontrol-format.md) element specifies the data that is displayed by the view.</span></span>

- <span data-ttu-id="c6049-214">Das [propertyName](./propertyname-element-for-wideitem-for-widecontrol-format.md) -Element gibt die Eigenschaft an, deren Wert von der Sicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c6049-214">The [PropertyName](./propertyname-element-for-wideitem-for-widecontrol-format.md) element specifies the property whose value is displayed by the view.</span></span> <span data-ttu-id="c6049-215">Sie müssen entweder eine Eigenschaft oder ein Skript angeben, aber Sie können nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="c6049-215">You must specify either a property or a script, but you cannot specify both.</span></span>

- <span data-ttu-id="c6049-216">Das Format [String](./formatstring-element-for-wideitem-for-widecontrol-format.md) -Element gibt ein Format Muster an, das definiert, wie der Eigenschafts-oder Skript Wert in der Ansicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c6049-216">The [FormatString](./formatstring-element-for-wideitem-for-widecontrol-format.md) element specifies a format pattern that defines how the property or script value is displayed in the view</span></span>

- <span data-ttu-id="c6049-217">Das [ScriptBlock](./scriptblock-element-for-wideitem-for-widecontrol-format.md) -Element (nicht angezeigt) gibt das Skript an, dessen Wert von der Sicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c6049-217">The [ScriptBlock](./scriptblock-element-for-wideitem-for-widecontrol-format.md) element (not shown) specifies the script whose value is displayed by the view.</span></span> <span data-ttu-id="c6049-218">Sie müssen entweder ein-Skript oder eine-Eigenschaft angeben, aber Sie können nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="c6049-218">You must specify either a script or a property, but you cannot specify both.</span></span>

<span data-ttu-id="c6049-219">Im folgenden Beispiel wird die- `ToString` Methode aufgerufen, um den Wert des Skripts zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="c6049-219">In the following example, the `ToString` method is called to format the value of the script.</span></span> <span data-ttu-id="c6049-220">Skripts können beliebige Methoden eines Objekts aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="c6049-220">Scripts can call any method of an object.</span></span> <span data-ttu-id="c6049-221">Wenn ein Objekt über eine-Methode verfügt, z. b. `ToString` mit Formatierungs Parametern, kann das Skript daher diese Methode zum Formatieren des Ausgabe Werts des Skripts aufruft.</span><span class="sxs-lookup"><span data-stu-id="c6049-221">Therefore, if an object has a method, such as `ToString`, that has formatting parameters, the script can call that method to format the output value of the script.</span></span>

```xml
<WideItem>
  <ScriptBlock>
    [String}::Format("(0,10) (1,8)", .LastWriteTime.ToString("d"),
    $_.LastWriteTime.Totring("t"))
  </ScriptBlock>
</WideItem>
```

<span data-ttu-id="c6049-222">Das folgende XML-Element kann zum Aufrufen der- `ToString` Methode verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="c6049-222">The following XML element can be used to calling the `ToString` method:</span></span>

- <span data-ttu-id="c6049-223">Das [wideitem](./wideitem-element-for-widecontrol-format.md) -Element gibt die Daten an, die von der Sicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c6049-223">The [WideItem](./wideitem-element-for-widecontrol-format.md) element specifies the data that is displayed by the view.</span></span>

- <span data-ttu-id="c6049-224">Das [ScriptBlock](./scriptblock-element-for-wideitem-for-widecontrol-format.md) -Element (nicht angezeigt) gibt das Skript an, dessen Wert von der Sicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c6049-224">The [ScriptBlock](./scriptblock-element-for-wideitem-for-widecontrol-format.md) element (not shown) specifies the script whose value is displayed by the view.</span></span> <span data-ttu-id="c6049-225">Sie müssen entweder ein-Skript oder eine-Eigenschaft angeben, aber Sie können nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="c6049-225">You must specify either a script or a property, but you cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="c6049-226">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c6049-226">See Also</span></span>

[<span data-ttu-id="c6049-227">Breite Ansicht (Basic)</span><span class="sxs-lookup"><span data-stu-id="c6049-227">Wide View (Basic)</span></span>](./wide-view-basic.md)

[<span data-ttu-id="c6049-228">Breite Ansicht (GroupBy)</span><span class="sxs-lookup"><span data-stu-id="c6049-228">Wide View (GroupBy)</span></span>](./wide-view-groupby.md)

[<span data-ttu-id="c6049-229">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="c6049-229">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
