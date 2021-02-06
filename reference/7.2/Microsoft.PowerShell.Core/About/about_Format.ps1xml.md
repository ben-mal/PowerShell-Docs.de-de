---
description: Ab PowerShell 6 werden die Standardansichten für-Objekte im PowerShell-Quellcode definiert.  Sie können eigene Dateien erstellen `Format.ps1xml` , um die Anzeige von Objekten zu ändern oder Standard anzeigen für neue Objekttypen zu definieren, die Sie in PowerShell erstellen.
Locale: en-US
ms.date: 11/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_format.ps1xml?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Format.ps1xml
ms.openlocfilehash: 56bac204e33c39aa6192da9e6a899f00b0a4a743
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603703"
---
# <a name="about-formatps1xml"></a><span data-ttu-id="3a593-104">Informationen zu Format.ps1XML</span><span class="sxs-lookup"><span data-stu-id="3a593-104">About Format.ps1xml</span></span>

## <a name="short-description"></a><span data-ttu-id="3a593-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3a593-105">Short description</span></span>

<span data-ttu-id="3a593-106">Ab PowerShell 6 werden die Standardansichten für-Objekte im PowerShell-Quellcode definiert.</span><span class="sxs-lookup"><span data-stu-id="3a593-106">Beginning in PowerShell 6, the default views for objects are defined in PowerShell source code.</span></span>

<span data-ttu-id="3a593-107">Sie können eigene Dateien erstellen `Format.ps1xml` , um die Anzeige von Objekten zu ändern oder Standard anzeigen für neue Objekttypen zu definieren, die Sie in PowerShell erstellen.</span><span class="sxs-lookup"><span data-stu-id="3a593-107">You can create your own `Format.ps1xml` files to change the display of objects or to define default displays for new object types that you create in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="3a593-108">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3a593-108">Long description</span></span>

<span data-ttu-id="3a593-109">Ab PowerShell 6 werden die Standardansichten im PowerShell-Quellcode definiert.</span><span class="sxs-lookup"><span data-stu-id="3a593-109">Beginning in PowerShell 6, the default views are defined in PowerShell source code.</span></span> <span data-ttu-id="3a593-110">Die `Format.ps1xml` Dateien aus PowerShell 5,1 und früheren Versionen sind in PowerShell 6 und höheren Versionen nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="3a593-110">The `Format.ps1xml` files from PowerShell 5.1 and earlier versions don't exist in PowerShell 6 and later versions.</span></span>

<span data-ttu-id="3a593-111">Der PowerShell-Quellcode definiert die Standard Anzeige von Objekten in der PowerShell-Konsole.</span><span class="sxs-lookup"><span data-stu-id="3a593-111">The PowerShell source code defines the default display of objects in the PowerShell console.</span></span> <span data-ttu-id="3a593-112">Sie können eigene Dateien erstellen `Format.ps1xml` , um die Anzeige von Objekten zu ändern oder Standard anzeigen für neue Objekttypen zu definieren, die Sie in PowerShell erstellen.</span><span class="sxs-lookup"><span data-stu-id="3a593-112">You can create your own `Format.ps1xml` files to change the display of objects or to define default displays for new object types that you create in PowerShell.</span></span>

<span data-ttu-id="3a593-113">Wenn PowerShell ein Objekt anzeigt, verwendet es die Daten in strukturierten Formatierungs Dateien, um die Standard Anzeige des Objekts zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="3a593-113">When PowerShell displays an object, it uses the data in structured formatting files to determine the default display of the object.</span></span> <span data-ttu-id="3a593-114">Die Daten in den Formatierungs Dateien bestimmen, ob das Objekt in einer Tabelle oder in einer Liste gerendert wird, und legt fest, welche Eigenschaften standardmäßig angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="3a593-114">The data in the formatting files determines whether the object is rendered in a table or in a list, and it determines which properties are displayed by default.</span></span>

<span data-ttu-id="3a593-115">Die Formatierung wirkt sich nur auf die Anzeige aus.</span><span class="sxs-lookup"><span data-stu-id="3a593-115">The formatting affects the display only.</span></span> <span data-ttu-id="3a593-116">Es wirkt sich nicht darauf aus, welche Objekteigenschaften in der Pipeline oder wie Sie übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="3a593-116">It doesn't affect which object properties are passed down the pipeline or how they're passed.</span></span> <span data-ttu-id="3a593-117">`Format.ps1xml` Dateien können nicht zum Anpassen des Ausgabeformats für Hash Tabellen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3a593-117">`Format.ps1xml` files can't be used to customize the output format for hash tables.</span></span>

<span data-ttu-id="3a593-118">Eine `.ps1xml` Formatierungs Datei kann vier verschiedene Ansichten der einzelnen Objekte definieren:</span><span class="sxs-lookup"><span data-stu-id="3a593-118">A `.ps1xml` formatting file can define four different views of each object:</span></span>

- <span data-ttu-id="3a593-119">Tabelle</span><span class="sxs-lookup"><span data-stu-id="3a593-119">Table</span></span>
- <span data-ttu-id="3a593-120">List</span><span class="sxs-lookup"><span data-stu-id="3a593-120">List</span></span>
- <span data-ttu-id="3a593-121">Breite</span><span class="sxs-lookup"><span data-stu-id="3a593-121">Wide</span></span>
- <span data-ttu-id="3a593-122">Benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="3a593-122">Custom</span></span>

<span data-ttu-id="3a593-123">Wenn z. b. die Ausgabe eines `Get-ChildItem` Befehls an einen Befehl weitergeleitet wird `Format-List` , `Format-List` verwendet die Listenansicht, die im Quellcode definiert ist, um zu bestimmen, wie die Datei-und Ordner Objekte als Liste angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="3a593-123">For example, when the output of a `Get-ChildItem` command is piped to a `Format-List` command, `Format-List` uses the list view defined in the source code to determine how to display the file and folder objects as a list.</span></span>

<span data-ttu-id="3a593-124">Wenn eine Formatierungs Datei mehr als eine Ansicht eines Objekts enthält, wendet PowerShell die erste gefundene Ansicht an.</span><span class="sxs-lookup"><span data-stu-id="3a593-124">When a formatting file includes more than one view of an object, PowerShell applies the first view that it finds.</span></span>

<span data-ttu-id="3a593-125">In einer benutzerdefinierten `Format.ps1xml` Datei wird eine Ansicht durch eine Reihe von XML-Tags definiert, die den Namen der Ansicht, den Typ des Objekts, auf das es angewendet werden kann, die Spaltenüberschriften und die im Text der Ansicht angezeigten Eigenschaften beschreiben.</span><span class="sxs-lookup"><span data-stu-id="3a593-125">In a custom `Format.ps1xml` file, a view is defined by a set of XML tags that describe the name of the view, the type of object to which it can be applied, the column headers, and the properties that are displayed in the body of the view.</span></span> <span data-ttu-id="3a593-126">Das Format in `Format.ps1xml` Dateien wird angewendet, kurz bevor die Daten dem Benutzer angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="3a593-126">The format in `Format.ps1xml` files is applied just before the data is presented to the user.</span></span>

## <a name="creating-new-formatps1xml-files"></a><span data-ttu-id="3a593-127">Erstellen neuer Format.ps1XML-Dateien</span><span class="sxs-lookup"><span data-stu-id="3a593-127">Creating new Format.ps1xml files</span></span>

<span data-ttu-id="3a593-128">Wenn Sie das Anzeige Format einer vorhandenen Objekt Ansicht ändern oder Ansichten für neue Objekte hinzufügen möchten, erstellen Sie Ihre eigenen `Format.ps1xml` Dateien, und fügen Sie Sie dann der PowerShell-Sitzung hinzu.</span><span class="sxs-lookup"><span data-stu-id="3a593-128">To change the display format of an existing object view, or to add views for new objects, create your own `Format.ps1xml` files, and then add them to your PowerShell session.</span></span>

<span data-ttu-id="3a593-129">`Format.ps1xml`Verwenden Sie die Cmdlets [Get-formatdata](xref:Microsoft.PowerShell.Utility.Get-FormatData) und [Export-formatdata](xref:Microsoft.PowerShell.Utility.Export-FormatData) , um eine Datei zum Definieren einer benutzerdefinierten Ansicht zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3a593-129">To create a `Format.ps1xml` file to define a custom view, use the [Get-FormatData](xref:Microsoft.PowerShell.Utility.Get-FormatData) and [Export-FormatData](xref:Microsoft.PowerShell.Utility.Export-FormatData) cmdlets.</span></span> <span data-ttu-id="3a593-130">Verwenden Sie einen Text-Editor, um die Datei zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="3a593-130">Use a text editor to edit the file.</span></span> <span data-ttu-id="3a593-131">Die Datei kann in einem beliebigen Verzeichnis gespeichert werden, auf das PowerShell zugreifen kann, z. b. ein Unterverzeichnis von `$HOME` .</span><span class="sxs-lookup"><span data-stu-id="3a593-131">The file can be saved to any directory that PowerShell can access, such as a subdirectory of `$HOME`.</span></span>

<span data-ttu-id="3a593-132">Um die Formatierung einer aktuellen Ansicht zu ändern, suchen Sie die Ansicht in der Formatierungs Datei, und verwenden Sie dann die Tags, um die Ansicht zu ändern.</span><span class="sxs-lookup"><span data-stu-id="3a593-132">To change the formatting of a current view, locate the view in the formatting file, and then use the tags to change the view.</span></span> <span data-ttu-id="3a593-133">Um eine Ansicht für einen neuen Objekttyp zu erstellen, erstellen Sie eine neue Ansicht, oder verwenden Sie eine vorhandene Sicht als Modell.</span><span class="sxs-lookup"><span data-stu-id="3a593-133">To create a view for a new object type, create a new view, or use an existing view as a model.</span></span> <span data-ttu-id="3a593-134">Die Tags werden im nächsten Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3a593-134">The tags are described in the next section.</span></span> <span data-ttu-id="3a593-135">Sie können dann alle anderen Sichten in der Datei löschen, damit die Änderungen offensichtlich von allen Benutzern untersucht werden, die die Datei überprüfen.</span><span class="sxs-lookup"><span data-stu-id="3a593-135">You can then delete all the other views in the file so that the changes are obvious to anyone examining the file.</span></span>

<span data-ttu-id="3a593-136">Nachdem Sie die Änderungen gespeichert haben, verwenden Sie [Update-formatdata](xref:Microsoft.PowerShell.Utility.Update-FormatData) , um die neue Datei zur PowerShell-Sitzung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="3a593-136">After you save the changes, use the [Update-FormatData](xref:Microsoft.PowerShell.Utility.Update-FormatData) to add the new file to your PowerShell session.</span></span> <span data-ttu-id="3a593-137">Wenn Sie möchten, dass Ihre Ansicht Vorrang vor einer Ansicht hat, die in den integrierten Dateien definiert ist, verwenden Sie den **prepdpath** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="3a593-137">If you want your view to take precedence over a view defined in the built-in files, use the **PrependPath** parameter.</span></span> <span data-ttu-id="3a593-138">`Update-FormatData` wirkt sich nur auf die aktuelle Sitzung aus.</span><span class="sxs-lookup"><span data-stu-id="3a593-138">`Update-FormatData` affects only the current session.</span></span> <span data-ttu-id="3a593-139">Fügen Sie den `Update-FormatData` Befehl zu Ihrem PowerShell-Profil hinzu, um die Änderung an allen zukünftigen Sitzungen vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="3a593-139">To make the change to all future sessions, add the `Update-FormatData` command to your PowerShell profile.</span></span>

### <a name="example-add-calendar-data-to-culture-objects"></a><span data-ttu-id="3a593-140">Beispiel: Hinzufügen von Kalenderdaten zu Kultur Objekten</span><span class="sxs-lookup"><span data-stu-id="3a593-140">Example: Add calendar data to culture objects</span></span>

<span data-ttu-id="3a593-141">In diesem Beispiel wird gezeigt, wie die Formatierung der Culture-Objekte **System. Globalization. CultureInfo** geändert wird, die durch das `Get-Culture` Cmdlet in der aktuellen PowerShell-Sitzung generiert werden.</span><span class="sxs-lookup"><span data-stu-id="3a593-141">This example shows how to change the formatting of the culture objects **System.Globalization.CultureInfo** generated by the `Get-Culture` cmdlet in the current PowerShell session.</span></span> <span data-ttu-id="3a593-142">Mit den Befehlen in diesem Beispiel wird die **Calendar** -Eigenschaft der standardmäßigen Tabellen Ansichts Anzeige von Culture-Objekten hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="3a593-142">The commands in the example add the **Calendar** property to the default table view display of culture objects.</span></span>

<span data-ttu-id="3a593-143">Rufen Sie zunächst die Format Daten aus der Quell Code Datei ab, und erstellen Sie eine `Format.ps1xml` Datei, die die aktuelle Ansicht der Kultur Objekte enthält.</span><span class="sxs-lookup"><span data-stu-id="3a593-143">To begin, get the format data from the source code file and create a `Format.ps1xml` file that contains the current view of the culture objects.</span></span>

```powershell
Get-FormatData -TypeName System.Globalization.CultureInfo |
  Export-FormatData -Path $HOME\Format\CultureInfo.Format.ps1xml
```

<span data-ttu-id="3a593-144">Öffnen Sie die `CultureInfo.Format.ps1xml` Datei in einem beliebigen XML-oder Text-Editor, z. b. Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="3a593-144">Open the `CultureInfo.Format.ps1xml` file in any XML or text editor, such as Visual Studio Code.</span></span> <span data-ttu-id="3a593-145">Der folgende XML-Code definiert die Ansichten des **CultureInfo** -Objekts.</span><span class="sxs-lookup"><span data-stu-id="3a593-145">The following XML defines the views of the **CultureInfo** object.</span></span>

<span data-ttu-id="3a593-146">Die `CultureInfo.Format.ps1xml` Datei sollte wie im folgenden Beispiel aussehen:</span><span class="sxs-lookup"><span data-stu-id="3a593-146">The `CultureInfo.Format.ps1xml` file should look like the following sample:</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<Configuration>
  <ViewDefinitions>
    <View>
      <Name>System.Globalization.CultureInfo</Name>
      <ViewSelectedBy>
        <TypeName>System.Globalization.CultureInfo</TypeName>
      </ViewSelectedBy>
      <TableControl>
        <TableHeaders>
          <TableColumnHeader>
            <Width>16</Width>
          </TableColumnHeader>
          <TableColumnHeader>
            <Width>16</Width>
          </TableColumnHeader>
          <TableColumnHeader />
        </TableHeaders>
        <TableRowEntries>
          <TableRowEntry>
            <TableColumnItems>
              <TableColumnItem>
                <PropertyName>LCID</PropertyName>
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
  </ViewDefinitions>
</Configuration>
```

<span data-ttu-id="3a593-147">Erstellen Sie eine neue Spalte für die **Calendar** -Eigenschaft, indem Sie einen neuen Satz von Tags hinzufügen `<TableColumnHeader>` .</span><span class="sxs-lookup"><span data-stu-id="3a593-147">Create a new column for the **Calendar** property by adding a new set of `<TableColumnHeader>` tags.</span></span> <span data-ttu-id="3a593-148">Der Wert der **Calendar** -Eigenschaft kann lang sein. Geben Sie daher einen Wert von 45 Zeichen als an `<Width>` .</span><span class="sxs-lookup"><span data-stu-id="3a593-148">The value of the **Calendar** property can be long, so specify a value of 45 characters as the `<Width>`.</span></span>

```xml
<TableHeaders>
  <TableColumnHeader>
    <Width>16</Width>
  </TableColumnHeader>
  <TableColumnHeader>
    <Width>16</Width>
  </TableColumnHeader>
  <TableColumnHeader>
    <Width>45</Width>
  </TableColumnHeader>
  <TableColumnHeader/>
</TableHeaders>
```

<span data-ttu-id="3a593-149">Fügen Sie ein neues Spalten Element für **Calendar** in den Tabellenzeilen mithilfe `<TableColumnItem>` der `<PropertyName` Tags und hinzu:</span><span class="sxs-lookup"><span data-stu-id="3a593-149">Add a new column item for **Calendar** in the table rows using the `<TableColumnItem>` and `<PropertyName` tags:</span></span>

```xml
<TableRowEntries>
  <TableRowEntry>
    <TableColumnItems>
      <TableColumnItem>
        <PropertyName>LCID</PropertyName>
      </TableColumnItem>
      <TableColumnItem>
        <PropertyName>Name</PropertyName>
      </TableColumnItem>
      <TableColumnItem>
        <PropertyName>Calendar</PropertyName>
      </TableColumnItem>
      <TableColumnItem>
        <PropertyName>DisplayName</PropertyName>
      </TableColumnItem>
    </TableColumnItems>
  </TableRowEntry>
</TableRowEntries>
```

<span data-ttu-id="3a593-150">Speichern und schließen Sie die Datei.</span><span class="sxs-lookup"><span data-stu-id="3a593-150">Save and close the file.</span></span> <span data-ttu-id="3a593-151">Verwenden Sie `Update-FormatData` , um der aktuellen PowerShell-Sitzung die neue Format Datei hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="3a593-151">Use `Update-FormatData` to add the new format file to the current PowerShell session.</span></span>

<span data-ttu-id="3a593-152">In diesem Beispiel wird der **prepdpath** -Parameter verwendet, um die neue Datei in einer höheren Rangfolge als die ursprüngliche Datei zu platzieren.</span><span class="sxs-lookup"><span data-stu-id="3a593-152">This example uses the **PrependPath** parameter to place the new file in a higher precedence order than the original file.</span></span> <span data-ttu-id="3a593-153">Weitere Informationen finden Sie unter [Update-formatdata](xref:Microsoft.PowerShell.Utility.Update-FormatData).</span><span class="sxs-lookup"><span data-stu-id="3a593-153">For more information, see [Update-FormatData](xref:Microsoft.PowerShell.Utility.Update-FormatData).</span></span>

```powershell
Update-FormatData -PrependPath $HOME\Format\CultureInfo.Format.ps1xml
```

<span data-ttu-id="3a593-154">Zum Testen der Änderung geben Sie ein, `Get-Culture` und überprüfen Sie die Ausgabe, die die **Calendar** -Eigenschaft enthält.</span><span class="sxs-lookup"><span data-stu-id="3a593-154">To test the change, type `Get-Culture` and review the output that includes the **Calendar** property.</span></span>

```powershell
Get-Culture
```

```Output
LCID  Name   Calendar                                DisplayName
----  ----   --------                                -----------
1033  en-US  System.Globalization.GregorianCalendar  English (United States)
```

## <a name="the-xml-in-formatps1xml-files"></a><span data-ttu-id="3a593-155">Der XML-Code in Format.ps1XML-Dateien</span><span class="sxs-lookup"><span data-stu-id="3a593-155">The XML in Format.ps1xml files</span></span>

<span data-ttu-id="3a593-156">Die vollständige Schema Definition finden Sie in der [Datei "Format. xsd](https://github.com/PowerShell/PowerShell/blob/master/src/Schemas/Format.xsd) " im PowerShell-Quellcoderepository auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="3a593-156">The full schema definition can be found in [Format.xsd](https://github.com/PowerShell/PowerShell/blob/master/src/Schemas/Format.xsd) in the PowerShell source code repository on GitHub.</span></span>

<span data-ttu-id="3a593-157">Der **viewdefinitions** -Abschnitt jeder `Format.ps1xml` Datei enthält die `<View>` Tags, die jede Ansicht definieren.</span><span class="sxs-lookup"><span data-stu-id="3a593-157">The **ViewDefinitions** section of each `Format.ps1xml` file contains the `<View>` tags that define each view.</span></span> <span data-ttu-id="3a593-158">Ein typisches `<View>` Tag umfasst die folgenden Tags:</span><span class="sxs-lookup"><span data-stu-id="3a593-158">A typical `<View>` tag includes the following tags:</span></span>

- <span data-ttu-id="3a593-159">`<Name>` identifiziert den Namen der Ansicht.</span><span class="sxs-lookup"><span data-stu-id="3a593-159">`<Name>` identifies the name of the view.</span></span>
- <span data-ttu-id="3a593-160">`<ViewSelectedBy>` Gibt den Objekttyp oder die Typen an, für die die Ansicht gilt.</span><span class="sxs-lookup"><span data-stu-id="3a593-160">`<ViewSelectedBy>` specifies the object type or types to which the view applies.</span></span>
- <span data-ttu-id="3a593-161">`<GroupBy>` Gibt an, wie Elemente in der Ansicht in Gruppen kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="3a593-161">`<GroupBy>` specifies how items in the view will be combined in groups.</span></span>
- <span data-ttu-id="3a593-162">`<TableControl>`, `<ListControl>` , `<WideControl>` und `<CustomControl>` enthalten die Tags, die angeben, wie die einzelnen Elemente angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="3a593-162">`<TableControl>`, `<ListControl>`, `<WideControl>`, and `<CustomControl>` contain the tags that specify how each item will be displayed.</span></span>

### <a name="viewselectedby-tag"></a><span data-ttu-id="3a593-163">Viewselectedby-Tag</span><span class="sxs-lookup"><span data-stu-id="3a593-163">ViewSelectedBy tag</span></span>

<span data-ttu-id="3a593-164">Das- `<ViewSelectedBy>` Tag kann ein- `<TypeName>` Tag für jeden Objekttyp enthalten, auf den die Ansicht angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="3a593-164">The `<ViewSelectedBy>` tag can contain a `<TypeName>` tag for each object type to which the view applies.</span></span> <span data-ttu-id="3a593-165">Oder es kann ein Tag enthalten sein `<SelectionSetName>` , das auf einen Auswahl Satz verweist, der an anderer Stelle mithilfe eines Tags definiert wird `<SelectionSet>` .</span><span class="sxs-lookup"><span data-stu-id="3a593-165">Or, it can contain a `<SelectionSetName>` tag that references a selection set that is defined elsewhere by using a `<SelectionSet>` tag.</span></span>

### <a name="groupby-tag"></a><span data-ttu-id="3a593-166">GroupBy-Tag</span><span class="sxs-lookup"><span data-stu-id="3a593-166">GroupBy tag</span></span>

<span data-ttu-id="3a593-167">Das- `<GroupBy>` Tag enthält ein- `<PropertyName>` Tag, das die Objekt Eigenschaft angibt, nach der Elemente gruppiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="3a593-167">The `<GroupBy>` tag contains a `<PropertyName>` tag that specifies the object property by which items are to be grouped.</span></span> <span data-ttu-id="3a593-168">Sie enthält auch ein `<Label>` Tag, das eine Zeichenfolge angibt, die als Bezeichnung für jede Gruppe oder ein Tag verwendet wird, `<CustomControlName>` das auf ein benutzerdefiniertes Steuerelement verweist, das an anderer Stelle mithilfe eines Tags definiert ist `<Control>` .</span><span class="sxs-lookup"><span data-stu-id="3a593-168">It also contains either a `<Label>` tag that specifies a string to be used as a label for each group or a `<CustomControlName>` tag that references a custom control defined elsewhere using a `<Control>` tag.</span></span> <span data-ttu-id="3a593-169">Das `<Control>` Tag enthält ein `<Name>` Tag und ein `<CustomControl>` Tag.</span><span class="sxs-lookup"><span data-stu-id="3a593-169">The `<Control>` tag contains a `<Name>` tag and a `<CustomControl>` tag.</span></span>

### <a name="tablecontroltag"></a><span data-ttu-id="3a593-170">Tablecontroltag</span><span class="sxs-lookup"><span data-stu-id="3a593-170">TableControlTag</span></span>

<span data-ttu-id="3a593-171">Das- `<TableControl>` Tag enthält normalerweise `<TableHeaders>` -und- `<TableRowEntries>` Tags, die die Formatierung für den Kopf und die Zeilen der Tabelle definieren.</span><span class="sxs-lookup"><span data-stu-id="3a593-171">The `<TableControl>` tag typically contains `<TableHeaders>` and `<TableRowEntries>` tags that define the formatting for the table's heads and rows.</span></span> <span data-ttu-id="3a593-172">Das `<TableHeaders>` -Tag enthält in der Regel `<TableColumnHeader>` Tags, die `<Label>` `<Width>` -,-und- `<Alignment>` Tags enthalten.</span><span class="sxs-lookup"><span data-stu-id="3a593-172">The `<TableHeaders>` tag typically contains `<TableColumnHeader>` tags that contain `<Label>`, `<Width>`, and `<Alignment>` tags.</span></span> <span data-ttu-id="3a593-173">Das `<TableRowEntries>` Tag enthält `<TableRowEntry>` Tags für jede Zeile in der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="3a593-173">The `<TableRowEntries>` tag contains `<TableRowEntry>` tags for each row in the table.</span></span> <span data-ttu-id="3a593-174">Das- `<TableRowEntry>` Tag enthält ein-Tag `<TableColumnItems>` , das ein- `<TableColumnItem>` Tag für jede Spalte in der Zeile enthält.</span><span class="sxs-lookup"><span data-stu-id="3a593-174">The `<TableRowEntry>` tag contains a `<TableColumnItems>` tag that contains a `<TableColumnItem>` tag for each column in the row.</span></span> <span data-ttu-id="3a593-175">In der Regel `<TableColumnItem>` enthält das Tag entweder ein `<PropertyName>` Tag, das die Objekt Eigenschaft angibt, die am definierten Speicherort angezeigt werden soll, oder ein `<ScriptBlock>` Tag, das Skriptcode enthält, der ein Ergebnis berechnet, das am Speicherort angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="3a593-175">Typically, the `<TableColumnItem>` tag contains either a `<PropertyName>` tag that identifies the object property to be displayed in the defined location, or a `<ScriptBlock>` tag that contains script code that calculates a result that is to be displayed in the location.</span></span>

> [!NOTE]
> <span data-ttu-id="3a593-176">Skriptblöcke können auch an anderen Speicherorten verwendet werden, an denen berechnete Ergebnisse nützlich sein können.</span><span class="sxs-lookup"><span data-stu-id="3a593-176">Script blocks can also be used elsewhere in locations where calculated results can be useful.</span></span>

<span data-ttu-id="3a593-177">Das- `<TableColumnItem>` Tag kann auch ein- `<FormatString>` Tag enthalten, das angibt, wie die-Eigenschaft oder die berechneten Ergebnisse angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="3a593-177">The `<TableColumnItem>` tag can also contain a `<FormatString>` tag that specifies how the property or the calculated results will be displayed.</span></span>

### <a name="listcontrol-tag"></a><span data-ttu-id="3a593-178">ListControl-Tag</span><span class="sxs-lookup"><span data-stu-id="3a593-178">ListControl tag</span></span>

<span data-ttu-id="3a593-179">Das- `<ListControl>` Tag enthält normalerweise ein- `<ListEntries>` Tag.</span><span class="sxs-lookup"><span data-stu-id="3a593-179">The `<ListControl>` tag typically contains a `<ListEntries>` tag.</span></span> <span data-ttu-id="3a593-180">Das `<ListEntries>` Tag enthält ein `<ListEntry>` Tag.</span><span class="sxs-lookup"><span data-stu-id="3a593-180">The `<ListEntries>` tag contains a `<ListEntry>` tag.</span></span> <span data-ttu-id="3a593-181">Das `<ListEntry>` Tag enthält ein `<ListItems>` Tag.</span><span class="sxs-lookup"><span data-stu-id="3a593-181">The `<ListEntry>` tag contains a `<ListItems>` tag.</span></span> <span data-ttu-id="3a593-182">Das- `<ListItems>` Tag enthält `<ListItem>` Tags, die `<PropertyName>` Tags enthalten.</span><span class="sxs-lookup"><span data-stu-id="3a593-182">The `<ListItems>` tag contains `<ListItem>` tags, which contain `<PropertyName>` tags.</span></span> <span data-ttu-id="3a593-183">`<PropertyName>`Mit den Tags wird die Objekt Eigenschaft angegeben, die an der angegebenen Position in der Liste angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="3a593-183">The `<PropertyName>` tags specify the object property to be displayed at the specified location in the list.</span></span> <span data-ttu-id="3a593-184">Wenn die Ansichts Auswahl mithilfe eines Auswahl Satzes definiert ist, `<ListControl>` `<ListEntry>` können die Tags und auch ein `<EntrySelectedBy>` Tag enthalten, das ein oder mehrere `<TypeName>` Tags enthält.</span><span class="sxs-lookup"><span data-stu-id="3a593-184">If the view selection is defined using a selection set, the `<ListControl>` and `<ListEntry>` tags can also contain an `<EntrySelectedBy>` tag that contains one or more `<TypeName>` tags.</span></span> <span data-ttu-id="3a593-185">Diese `<TypeName>` Tags geben den Objekttyp an, der vom `<ListControl>` Tag angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="3a593-185">These `<TypeName>` tags specify the object type that the `<ListControl>` tag is intended to display.</span></span>

### <a name="widecontrol-tag"></a><span data-ttu-id="3a593-186">Widecontrol-Tag</span><span class="sxs-lookup"><span data-stu-id="3a593-186">WideControl tag</span></span>

<span data-ttu-id="3a593-187">Das- `<WideControl>` Tag enthält normalerweise ein- `<WideEntries>` Tag.</span><span class="sxs-lookup"><span data-stu-id="3a593-187">The `<WideControl>` tag typically contains a `<WideEntries>` tag.</span></span> <span data-ttu-id="3a593-188">Das- `<WideEntries>` Tag enthält ein oder mehrere `<WideEntry>` Tags.</span><span class="sxs-lookup"><span data-stu-id="3a593-188">The `<WideEntries>` tag contains one or more `<WideEntry>` tags.</span></span> <span data-ttu-id="3a593-189">Ein- `<WideEntry>` Tag enthält normalerweise ein- `<PropertyName>` Tag, das die Eigenschaft angibt, die an der angegebenen Position in der Ansicht angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="3a593-189">A `<WideEntry>` tag typically contains a `<PropertyName>` tag that specifies the property to be displayed at the specified location in the view.</span></span> <span data-ttu-id="3a593-190">Das- `<PropertyName>` Tag kann ein- `<FormatString>` Tag enthalten, das angibt, wie die-Eigenschaft angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="3a593-190">The `<PropertyName>` tag can contain a `<FormatString>` tag that specifies how the property is to be displayed.</span></span>

### <a name="customcontrol-tag"></a><span data-ttu-id="3a593-191">CustomControl-Tag</span><span class="sxs-lookup"><span data-stu-id="3a593-191">CustomControl tag</span></span>

<span data-ttu-id="3a593-192">Mit dem- `<CustomControl>` Tag können Sie einen Skriptblock verwenden, um ein Format zu definieren.</span><span class="sxs-lookup"><span data-stu-id="3a593-192">The `<CustomControl>` tag lets you use a script block to define a format.</span></span> <span data-ttu-id="3a593-193">Ein `<CustomControl>` Tag enthält normalerweise ein `<CustomEntries>` Tag, das mehrere `<CustomEntry>` Tags enthält.</span><span class="sxs-lookup"><span data-stu-id="3a593-193">A `<CustomControl>` tag typically contains a `<CustomEntries>` tag that contains multiple `<CustomEntry>` tags.</span></span> <span data-ttu-id="3a593-194">Jedes `<CustomEntry>` Tag enthält ein `<CustomItem>` Tag, das eine Vielzahl von Tags enthalten kann, die den Inhalt und die Formatierung der angegebenen Position in der Sicht angeben, einschließlich der `<Text>` `<Indentation>` Tags,, `<ExpressionBinding>` und `<NewLine>` .</span><span class="sxs-lookup"><span data-stu-id="3a593-194">Each `<CustomEntry>` tag contains a `<CustomItem>` tag that can contain a variety of tags that specify contents and formatting of the specified location in the view, including `<Text>`, `<Indentation>`, `<ExpressionBinding>`, and `<NewLine>` tags.</span></span>

## <a name="tracing-formatps1xml-file-use"></a><span data-ttu-id="3a593-195">Ablauf Verfolgung Format.ps1XML-Datei Verwendung</span><span class="sxs-lookup"><span data-stu-id="3a593-195">Tracing Format.ps1xml file use</span></span>

<span data-ttu-id="3a593-196">Verwenden Sie zum Erkennen von Fehlern beim Laden oder bei der Anwendung von `Format.ps1xml` Dateien das- `Trace-Command` Cmdlet mit den folgenden Format Komponenten als Wert für den **Name** -Parameter:</span><span class="sxs-lookup"><span data-stu-id="3a593-196">To detect errors in the loading or application of `Format.ps1xml` files, use the `Trace-Command` cmdlet with any of the following format components as the value of the **Name** parameter:</span></span>

- <span data-ttu-id="3a593-197">Formatfileloading</span><span class="sxs-lookup"><span data-stu-id="3a593-197">FormatFileLoading</span></span>
- <span data-ttu-id="3a593-198">Formatviewbinding</span><span class="sxs-lookup"><span data-stu-id="3a593-198">FormatViewBinding</span></span>

<span data-ttu-id="3a593-199">Weitere Informationen finden Sie unter [Trace-Command](xref:Microsoft.PowerShell.Utility.Trace-Command) und [Get-TraceSource](xref:Microsoft.PowerShell.Utility.Get-TraceSource).</span><span class="sxs-lookup"><span data-stu-id="3a593-199">For more information, see [Trace-Command](xref:Microsoft.PowerShell.Utility.Trace-Command) and [Get-TraceSource](xref:Microsoft.PowerShell.Utility.Get-TraceSource).</span></span>

## <a name="signing-a-formatps1xml-file"></a><span data-ttu-id="3a593-200">Signieren einer Format.ps1-XML-Datei</span><span class="sxs-lookup"><span data-stu-id="3a593-200">Signing a Format.ps1xml file</span></span>

<span data-ttu-id="3a593-201">`Format.ps1xml`Signieren Sie die Datei mithilfe einer digitalen Signatur, um die Benutzer Ihrer-Datei zu schützen.</span><span class="sxs-lookup"><span data-stu-id="3a593-201">To protect the users of your `Format.ps1xml` file, sign the file using a digital signature.</span></span> <span data-ttu-id="3a593-202">Weitere Informationen finden Sie unter [about_Signing](about_Signing.md).</span><span class="sxs-lookup"><span data-stu-id="3a593-202">For more information, see [about_Signing](about_Signing.md).</span></span>

## <a name="sample-xml-for-a-format-table-custom-view"></a><span data-ttu-id="3a593-203">Beispiel-XML für eine Format-Table benutzerdefinierte Ansicht</span><span class="sxs-lookup"><span data-stu-id="3a593-203">Sample XML for a Format-Table custom view</span></span>

<span data-ttu-id="3a593-204">Im folgenden XML `Format-Table` -Beispiel wird eine benutzerdefinierte Ansicht für die **System. IO. directeryinfo** -und **System. IO. FileInfo** -Objekte erstellt, die von erstellt werden `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="3a593-204">The following XML sample creates a `Format-Table` custom view for the **System.IO.DirectoryInfo** and **System.IO.FileInfo** objects created by `Get-ChildItem`.</span></span> <span data-ttu-id="3a593-205">Die benutzerdefinierte Ansicht hat den Namen **mygciview** und fügt der Tabelle die Spalte " **kreationtime** " hinzu.</span><span class="sxs-lookup"><span data-stu-id="3a593-205">The custom view is named **mygciview** and adds the **CreationTime** column to the table.</span></span>

<span data-ttu-id="3a593-206">Um die benutzerdefinierte Ansicht zu erstellen, `Get-FormatData` verwenden `Export-FormatData` Sie die Cmdlets und, um eine Datei zu generieren `.ps1xml` .</span><span class="sxs-lookup"><span data-stu-id="3a593-206">To create the custom view, use the `Get-FormatData` and `Export-FormatData` cmdlets to generate a `.ps1xml` file.</span></span> <span data-ttu-id="3a593-207">Bearbeiten Sie dann `.ps1xml` die Datei, um den Code für die benutzerdefinierte Ansicht zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3a593-207">Then, edit your `.ps1xml` file to create the code for your custom view.</span></span> <span data-ttu-id="3a593-208">Die `.ps1xml` Datei kann in einem beliebigen Verzeichnis gespeichert werden, auf das PowerShell zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="3a593-208">The `.ps1xml` file can be stored in any directory that PowerShell can access.</span></span> <span data-ttu-id="3a593-209">Beispielsweise ein Unterverzeichnis von `$HOME` .</span><span class="sxs-lookup"><span data-stu-id="3a593-209">For example, a subdirectory of `$HOME`.</span></span>

<span data-ttu-id="3a593-210">Nachdem die `.ps1xml` Datei erstellt wurde, verwenden `Update-FormatData` Sie das Cmdlet, um die Ansicht in die aktuelle PowerShell-Sitzung einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="3a593-210">After the `.ps1xml` file is created, use the `Update-FormatData` cmdlet to include the view in the current PowerShell session.</span></span> <span data-ttu-id="3a593-211">Sie können auch den Update-Befehl zu Ihrem PowerShell-Profil hinzufügen, wenn Sie die Ansicht in allen PowerShell-Sitzungen verfügbar benötigen.</span><span class="sxs-lookup"><span data-stu-id="3a593-211">Or, add the update command to your PowerShell profile if you need the view available in all PowerShell sessions.</span></span>

<span data-ttu-id="3a593-212">In diesem Beispiel muss die benutzerdefinierte Sicht das Tabellenformat verwenden, andernfalls `Format-Table` schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="3a593-212">For this example, the custom view must use the table format, otherwise, `Format-Table` fails.</span></span>

<span data-ttu-id="3a593-213">Verwenden `Format-Table` Sie mit dem **View** -Parameter, um den Namen der benutzerdefinierten Ansicht ( **mygciview**) anzugeben, und formatieren Sie die Ausgabe der Tabelle mit der Spalte " **kreationtime** ".</span><span class="sxs-lookup"><span data-stu-id="3a593-213">Use `Format-Table` with the **View** parameter to specify the custom view's name, **mygciview**, and format the table's output with the **CreationTime** column.</span></span> <span data-ttu-id="3a593-214">Ein Beispiel für die Art und Weise, wie der Befehl ausgeführt wird, finden Sie unter [Format-Table](xref:Microsoft.PowerShell.Utility.Format-Table).</span><span class="sxs-lookup"><span data-stu-id="3a593-214">For an example of how the command is run, see [Format-Table](xref:Microsoft.PowerShell.Utility.Format-Table).</span></span>

> [!NOTE]
> <span data-ttu-id="3a593-215">Obwohl Sie den Formatierungs-XML-Code aus dem Quellcode zum Erstellen einer benutzerdefinierten Ansicht erhalten können, ist möglicherweise eine größere Entwicklung erforderlich, um das gewünschte Ergebnis zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="3a593-215">Although you can get the formatting XML from the source code to create a custom view, more development might be needed to get the desired result.</span></span>

<span data-ttu-id="3a593-216">Im folgenden `Get-FormatData` Befehl gibt es eine Alternative zum **PowerShellVersion** -Parameter, um sicherzustellen, dass alle lokalen Formatierungsinformationen zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="3a593-216">In the following `Get-FormatData` command, there's an alternative for the **PowerShellVersion** parameter to ensure that all local formatting information is returned.</span></span> <span data-ttu-id="3a593-217">Verwenden Sie `-PowerShellVersion $PSVersionTable.PSVersion` anstelle einer bestimmten PowerShell-Version.</span><span class="sxs-lookup"><span data-stu-id="3a593-217">Use `-PowerShellVersion $PSVersionTable.PSVersion` rather than a specific PowerShell version.</span></span>

```powershell
Get-FormatData -PowerShellVersion 5.1 -TypeName System.IO.DirectoryInfo |
   Export-FormatData -Path ./Mygciview.Format.ps1xml
Update-FormatData -AppendPath ./Mygciview.Format.ps1xml
```

```xml
<?xml version="1.0" encoding="utf-8"?>
<Configuration>
  <ViewDefinitions>
    <View>
      <Name>mygciview</Name>
      <ViewSelectedBy>
        <TypeName>System.IO.DirectoryInfo</TypeName>
        <TypeName>System.IO.FileInfo</TypeName>
      </ViewSelectedBy>
      <GroupBy>
        <PropertyName>PSParentPath</PropertyName>
      </GroupBy>
      <TableControl>
        <TableHeaders>
          <TableColumnHeader>
            <Label>Mode</Label>
            <Width>7</Width>
            <Alignment>Left</Alignment>
          </TableColumnHeader>
          <TableColumnHeader>
            <Label>LastWriteTime</Label>
            <Width>26</Width>
            <Alignment>Right</Alignment>
          </TableColumnHeader>
          <TableColumnHeader>
            <Label>CreationTime</Label>
            <Width>26</Width>
            <Alignment>Right</Alignment>
          </TableColumnHeader>
          <TableColumnHeader>
            <Label>Length</Label>
            <Width>14</Width>
            <Alignment>Right</Alignment>
          </TableColumnHeader>
          <TableColumnHeader>
            <Label>Name</Label>
            <Alignment>Left</Alignment>
          </TableColumnHeader>
        </TableHeaders>
        <TableRowEntries>
          <TableRowEntry>
            <Wrap />
            <TableColumnItems>
              <TableColumnItem>
                <PropertyName>ModeWithoutHardLink</PropertyName>
              </TableColumnItem>
              <TableColumnItem>
                <PropertyName>LastWriteTime</PropertyName>
              </TableColumnItem>
              <TableColumnItem>
                <PropertyName>CreationTime</PropertyName>
              </TableColumnItem>
              <TableColumnItem>
                <PropertyName>Length</PropertyName>
              </TableColumnItem>
              <TableColumnItem>
                <PropertyName>Name</PropertyName>
              </TableColumnItem>
            </TableColumnItems>
          </TableRowEntry>
        </TableRowEntries>
      </TableControl>
    </View>
  </ViewDefinitions>
</Configuration>
```

## <a name="see-also"></a><span data-ttu-id="3a593-218">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3a593-218">See also</span></span>

[<span data-ttu-id="3a593-219">Export-FormatData</span><span class="sxs-lookup"><span data-stu-id="3a593-219">Export-FormatData</span></span>](xref:Microsoft.PowerShell.Utility.Export-FormatData)

[<span data-ttu-id="3a593-220">Get-FormatData</span><span class="sxs-lookup"><span data-stu-id="3a593-220">Get-FormatData</span></span>](xref:Microsoft.PowerShell.Utility.Get-FormatData)

[<span data-ttu-id="3a593-221">Get-TraceSource</span><span class="sxs-lookup"><span data-stu-id="3a593-221">Get-TraceSource</span></span>](xref:Microsoft.PowerShell.Utility.Get-TraceSource)

[<span data-ttu-id="3a593-222">Formatschema – XML-Referenz</span><span class="sxs-lookup"><span data-stu-id="3a593-222">Format Schema XML Reference</span></span>](/powershell/scripting/developer/format/format-schema-xml-reference)

[<span data-ttu-id="3a593-223">Trace-Command</span><span class="sxs-lookup"><span data-stu-id="3a593-223">Trace-Command</span></span>](xref:Microsoft.PowerShell.Utility.Trace-Command)

[<span data-ttu-id="3a593-224">Update-FormatData</span><span class="sxs-lookup"><span data-stu-id="3a593-224">Update-FormatData</span></span>](xref:Microsoft.PowerShell.Utility.Update-FormatData)

[<span data-ttu-id="3a593-225">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="3a593-225">Writing a PowerShell Formatting File</span></span>](/powershell/scripting/developer/format/writing-a-powershell-formatting-file)
