---
description: Die `Format.ps1xml` Dateien in PowerShell definieren die Standard Anzeige von Objekten in der PowerShell-Konsole. Sie können eigene Dateien erstellen `Format.ps1xml` , um die Anzeige von Objekten zu ändern oder Standard anzeigen für neue Objekttypen zu definieren, die Sie in PowerShell erstellen.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 11/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_format.ps1xml?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Format.ps1xml
ms.openlocfilehash: be88007d23ab98b9c2f707b77f9c43578ba9887b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222759"
---
# <a name="about-formatps1xml"></a><span data-ttu-id="d59d7-105">Informationen zu Format.ps1XML</span><span class="sxs-lookup"><span data-stu-id="d59d7-105">About Format.ps1xml</span></span>

## <a name="short-description"></a><span data-ttu-id="d59d7-106">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d59d7-106">Short description</span></span>

<span data-ttu-id="d59d7-107">Die `Format.ps1xml` Dateien in PowerShell definieren die Standard Anzeige von Objekten in der PowerShell-Konsole.</span><span class="sxs-lookup"><span data-stu-id="d59d7-107">The `Format.ps1xml` files in PowerShell define the default display of objects in the PowerShell console.</span></span> <span data-ttu-id="d59d7-108">Sie können eigene Dateien erstellen `Format.ps1xml` , um die Anzeige von Objekten zu ändern oder Standard anzeigen für neue Objekttypen zu definieren, die Sie in PowerShell erstellen.</span><span class="sxs-lookup"><span data-stu-id="d59d7-108">You can create your own `Format.ps1xml` files to change the display of objects or to define default displays for new object types that you create in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="d59d7-109">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d59d7-109">Long description</span></span>

<span data-ttu-id="d59d7-110">Die `Format.ps1xml` Dateien in PowerShell definieren die Standard Anzeige von Objekten in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d59d7-110">The `Format.ps1xml` files in PowerShell define the default display of objects in PowerShell.</span></span> <span data-ttu-id="d59d7-111">Sie können eigene Dateien erstellen `Format.ps1xml` , um die Anzeige von Objekten zu ändern oder Standard anzeigen für neue Objekttypen zu definieren, die Sie in PowerShell erstellen.</span><span class="sxs-lookup"><span data-stu-id="d59d7-111">You can create your own `Format.ps1xml` files to change the display of objects or to define default displays for new object types that you create in PowerShell.</span></span>

<span data-ttu-id="d59d7-112">Wenn PowerShell ein Objekt anzeigt, verwendet es die Daten in strukturierten Formatierungs Dateien, um die Standard Anzeige des Objekts zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="d59d7-112">When PowerShell displays an object, it uses the data in structured formatting files to determine the default display of the object.</span></span> <span data-ttu-id="d59d7-113">Die Daten in den Formatierungs Dateien bestimmen, ob das Objekt in einer Tabelle oder in einer Liste gerendert wird, und legt fest, welche Eigenschaften standardmäßig angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d59d7-113">The data in the formatting files determines whether the object is rendered in a table or in a list, and it determines which properties are displayed by default.</span></span>

<span data-ttu-id="d59d7-114">Die Formatierung wirkt sich nur auf die Anzeige aus.</span><span class="sxs-lookup"><span data-stu-id="d59d7-114">The formatting affects the display only.</span></span> <span data-ttu-id="d59d7-115">Es wirkt sich nicht darauf aus, welche Objekteigenschaften in der Pipeline oder wie Sie übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="d59d7-115">It doesn't affect which object properties are passed down the pipeline or how they're passed.</span></span> <span data-ttu-id="d59d7-116">`Format.ps1xml` Dateien können nicht zum Anpassen des Ausgabeformats für Hash Tabellen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d59d7-116">`Format.ps1xml` files can't be used to customize the output format for hash tables.</span></span>

<span data-ttu-id="d59d7-117">PowerShell enthält sieben Formatierungs Dateien.</span><span class="sxs-lookup"><span data-stu-id="d59d7-117">PowerShell includes seven formatting files.</span></span> <span data-ttu-id="d59d7-118">Diese Dateien befinden sich im-Installationsverzeichnis ( `$PSHOME` ).</span><span class="sxs-lookup"><span data-stu-id="d59d7-118">These files are located in the installation directory (`$PSHOME`).</span></span> <span data-ttu-id="d59d7-119">Jede Datei definiert die Anzeige einer Gruppe von Microsoft .NET Framework-Objekten:</span><span class="sxs-lookup"><span data-stu-id="d59d7-119">Each file defines the display of a group of Microsoft .NET Framework objects:</span></span>

1. `Certificate.Format.ps1xml`

   <span data-ttu-id="d59d7-120">Objekte im Zertifikat Speicher, z. b. X. 509-Zertifikate und Zertifikat Speicher.</span><span class="sxs-lookup"><span data-stu-id="d59d7-120">Objects in the Certificate store, such as X.509 certificates and certificate stores.</span></span>

1. `DotNetTypes.Format.ps1xml`

   <span data-ttu-id="d59d7-121">Andere .NET Framework Typen, z. b. CultureInfo-, FileVersionInfo-und EventLogEntry-Objekte.</span><span class="sxs-lookup"><span data-stu-id="d59d7-121">Other .NET Framework types, such as CultureInfo, FileVersionInfo, and EventLogEntry objects.</span></span>

1. `FileSystem.Format.ps1xml`

   <span data-ttu-id="d59d7-122">Dateisystem Objekte, z. b. Dateien und Verzeichnisse.</span><span class="sxs-lookup"><span data-stu-id="d59d7-122">File system objects, such as files and directories.</span></span>

1. `Help.Format.ps1xml`

   <span data-ttu-id="d59d7-123">Hilfe Ansichten, z. b. ausführliche und vollständige Sichten, Parameter und Beispiele.</span><span class="sxs-lookup"><span data-stu-id="d59d7-123">Help views, such as detailed and full views, parameters, and examples.</span></span>

1. `PowerShellCore.Format.ps1xml`

   <span data-ttu-id="d59d7-124">Objekte, die von PowerShell Core-Cmdlets generiert werden, z `Get-Member` `Get-History` . b. und.</span><span class="sxs-lookup"><span data-stu-id="d59d7-124">Objects generated by PowerShell core cmdlets, such as `Get-Member` and `Get-History`.</span></span>

1. `PowerShellTrace.Format.ps1xml`

   <span data-ttu-id="d59d7-125">Ablauf Verfolgungs Objekte, z. b. die vom `Trace-Command` Cmdlet generierten.</span><span class="sxs-lookup"><span data-stu-id="d59d7-125">Trace objects, such as those generated by the `Trace-Command` cmdlet.</span></span>

1. `Registry.Format.ps1xml`

   <span data-ttu-id="d59d7-126">Registrierungs Objekte, z. b. Schlüssel und Einträge.</span><span class="sxs-lookup"><span data-stu-id="d59d7-126">Registry objects, such as keys and entries.</span></span>

<span data-ttu-id="d59d7-127">Eine Formatierungs Datei kann vier verschiedene Ansichten der einzelnen Objekte definieren:</span><span class="sxs-lookup"><span data-stu-id="d59d7-127">A formatting file can define four different views of each object:</span></span>

- <span data-ttu-id="d59d7-128">Tabelle</span><span class="sxs-lookup"><span data-stu-id="d59d7-128">Table</span></span>
- <span data-ttu-id="d59d7-129">List</span><span class="sxs-lookup"><span data-stu-id="d59d7-129">List</span></span>
- <span data-ttu-id="d59d7-130">Breite</span><span class="sxs-lookup"><span data-stu-id="d59d7-130">Wide</span></span>
- <span data-ttu-id="d59d7-131">Benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="d59d7-131">Custom</span></span>

<span data-ttu-id="d59d7-132">Wenn z. b. die Ausgabe eines `Get-ChildItem` Befehls an einen Befehl weitergeleitet wird `Format-List` , `Format-List` verwendet die Ansicht in der `FileSystem.Format.ps1xml` Datei, um zu bestimmen, wie die Datei-und Ordner Objekte als Liste angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d59d7-132">For example, when the output of a `Get-ChildItem` command is piped to a `Format-List` command, `Format-List` uses the view in the `FileSystem.Format.ps1xml` file to determine how to display the file and folder objects as a list.</span></span>

<span data-ttu-id="d59d7-133">Wenn eine Formatierungs Datei mehr als eine Ansicht eines Objekts enthält, wendet PowerShell die erste gefundene Ansicht an.</span><span class="sxs-lookup"><span data-stu-id="d59d7-133">When a formatting file includes more than one view of an object, PowerShell applies the first view that it finds.</span></span>

<span data-ttu-id="d59d7-134">In einer `Format.ps1xml` Datei wird eine Ansicht durch einen Satz von XML-Tags definiert, die den Namen der Sicht, den Typ des Objekts, auf das Sie angewendet werden kann, die Spaltenüberschriften und die im Text der Ansicht angezeigten Eigenschaften beschreiben.</span><span class="sxs-lookup"><span data-stu-id="d59d7-134">In a `Format.ps1xml` file, a view is defined by a set of XML tags that describe the name of the view, the type of object to which it can be applied, the column headers, and the properties that are displayed in the body of the view.</span></span> <span data-ttu-id="d59d7-135">Das Format in `Format.ps1xml` Dateien wird angewendet, kurz bevor die Daten dem Benutzer angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d59d7-135">The format in `Format.ps1xml` files is applied just before the data is presented to the user.</span></span>

## <a name="creating-new-formatps1xml-files"></a><span data-ttu-id="d59d7-136">Erstellen neuer Format.ps1XML-Dateien</span><span class="sxs-lookup"><span data-stu-id="d59d7-136">Creating new Format.ps1xml files</span></span>

<span data-ttu-id="d59d7-137">Die `.ps1xml` mit PowerShell installierten Dateien sind digital signiert, um Manipulationen zu verhindern, da die Formatierung Skriptblöcke einschließen kann.</span><span class="sxs-lookup"><span data-stu-id="d59d7-137">The `.ps1xml` files that are installed with PowerShell are digitally signed to prevent tampering because the formatting can include script blocks.</span></span> <span data-ttu-id="d59d7-138">Wenn Sie das Anzeige Format einer vorhandenen Objekt Ansicht ändern oder Ansichten für neue Objekte hinzufügen möchten, erstellen Sie Ihre eigenen `Format.ps1xml` Dateien, und fügen Sie Sie dann der PowerShell-Sitzung hinzu.</span><span class="sxs-lookup"><span data-stu-id="d59d7-138">To change the display format of an existing object view, or to add views for new objects, create your own `Format.ps1xml` files, and then add them to your PowerShell session.</span></span>

<span data-ttu-id="d59d7-139">Kopieren Sie eine vorhandene Datei, um eine neue Datei zu erstellen `Format.ps1xml` .</span><span class="sxs-lookup"><span data-stu-id="d59d7-139">To create a new file, copy an existing `Format.ps1xml` file.</span></span> <span data-ttu-id="d59d7-140">Die neue Datei kann einen beliebigen Namen haben, Sie muss jedoch eine `.ps1xml` Dateinamenerweiterung aufweisen.</span><span class="sxs-lookup"><span data-stu-id="d59d7-140">The new file can have any name, but it must have a `.ps1xml` file name extension.</span></span> <span data-ttu-id="d59d7-141">Sie können die neue Datei in einem beliebigen Verzeichnis platzieren, auf das PowerShell zugreifen kann, aber es ist hilfreich, die Dateien im PowerShell-Installationsverzeichnis ( `$PSHOME` ) oder in einem Unterverzeichnis des Installationsverzeichnisses zu platzieren.</span><span class="sxs-lookup"><span data-stu-id="d59d7-141">You can place the new file in any directory that is accessible to PowerShell, but it's useful to place the files in the PowerShell installation directory (`$PSHOME`) or in a subdirectory of the installation directory.</span></span>

<span data-ttu-id="d59d7-142">Um die Formatierung einer aktuellen Ansicht zu ändern, suchen Sie die Ansicht in der Formatierungs Datei, und verwenden Sie dann die Tags, um die Ansicht zu ändern.</span><span class="sxs-lookup"><span data-stu-id="d59d7-142">To change the formatting of a current view, locate the view in the formatting file, and then use the tags to change the view.</span></span> <span data-ttu-id="d59d7-143">Um eine Ansicht für einen neuen Objekttyp zu erstellen, erstellen Sie eine neue Ansicht, oder verwenden Sie eine vorhandene Sicht als Modell.</span><span class="sxs-lookup"><span data-stu-id="d59d7-143">To create a view for a new object type, create a new view, or use an existing view as a model.</span></span> <span data-ttu-id="d59d7-144">Die Tags werden im nächsten Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d59d7-144">The tags are described in the next section.</span></span> <span data-ttu-id="d59d7-145">Sie können dann alle anderen Sichten in der Datei löschen, damit die Änderungen offensichtlich von allen Benutzern untersucht werden, die die Datei überprüfen.</span><span class="sxs-lookup"><span data-stu-id="d59d7-145">You can then delete all the other views in the file so that the changes are obvious to anyone examining the file.</span></span>

<span data-ttu-id="d59d7-146">Nachdem Sie die Änderungen gespeichert haben, verwenden Sie das `Update-FormatData` Cmdlet, um die neue Datei zur PowerShell-Sitzung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="d59d7-146">After you save the changes, use the `Update-FormatData` cmdlet to add the new file to your PowerShell session.</span></span> <span data-ttu-id="d59d7-147">Wenn Sie möchten, dass Ihre Ansicht Vorrang vor einer Ansicht hat, die in den integrierten Dateien definiert ist, verwenden Sie den **prepdpath** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="d59d7-147">If you want your view to take precedence over a view defined in the built-in files, use the **PrependPath** parameter.</span></span>
<span data-ttu-id="d59d7-148">`Update-FormatData` wirkt sich nur auf die aktuelle Sitzung aus.</span><span class="sxs-lookup"><span data-stu-id="d59d7-148">`Update-FormatData` affects only the current session.</span></span> <span data-ttu-id="d59d7-149">Fügen Sie den `Update-FormatData` Befehl zu Ihrem PowerShell-Profil hinzu, um die Änderung an allen zukünftigen Sitzungen vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="d59d7-149">To make the change to all future sessions, add the `Update-FormatData` command to your PowerShell profile.</span></span>

### <a name="example-adding-calendar-data-to-culture-objects"></a><span data-ttu-id="d59d7-150">Beispiel: Hinzufügen von Kalenderdaten zu Kultur Objekten</span><span class="sxs-lookup"><span data-stu-id="d59d7-150">Example: Adding calendar data to culture objects</span></span>

<span data-ttu-id="d59d7-151">In diesem Beispiel wird gezeigt, wie die Formatierung der Culture-Objekte **System. Globalization. CultureInfo** geändert wird, die durch das `Get-Culture` Cmdlet in der aktuellen PowerShell-Sitzung generiert werden.</span><span class="sxs-lookup"><span data-stu-id="d59d7-151">This example shows how to change the formatting of the culture objects **System.Globalization.CultureInfo** generated by the `Get-Culture` cmdlet in the current PowerShell session.</span></span> <span data-ttu-id="d59d7-152">Mit den Befehlen in diesem Beispiel wird die **Calendar** -Eigenschaft der standardmäßigen Tabellen Ansichts Anzeige von Culture-Objekten hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="d59d7-152">The commands in the example add the **Calendar** property to the default table view display of culture objects.</span></span>

<span data-ttu-id="d59d7-153">Der erste Schritt besteht darin, die `Format.ps1xml` Datei zu suchen, die die aktuelle Ansicht der Kultur Objekte enthält.</span><span class="sxs-lookup"><span data-stu-id="d59d7-153">The first step is to find the `Format.ps1xml` file that contains the current view of the culture objects.</span></span> <span data-ttu-id="d59d7-154">Der folgende `Select-String` Befehl sucht nach der Datei:</span><span class="sxs-lookup"><span data-stu-id="d59d7-154">The following `Select-String` command finds the file:</span></span>

```powershell
$Parms = @{
  Path = "$PSHOME\*Format.ps1xml"
  Pattern = "System.Globalization.CultureInfo"
}

Select-String @Parms
```

```Output
C:\Windows\System32\WindowsPowerShell\v1.0\DotNetTypes.format.ps1xml:113:
     <Name>System.Globalization.CultureInfo</Name>
C:\Windows\System32\WindowsPowerShell\v1.0\DotNetTypes.format.ps1xml:115:
<TypeName>System.Globalization.CultureInfo</TypeName>
```

<span data-ttu-id="d59d7-155">Dieser Befehl zeigt, dass die Definition in der `DotNetTypes.Format.ps1xml` Datei gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="d59d7-155">This command reveals that the definition is in the `DotNetTypes.Format.ps1xml` file.</span></span>

<span data-ttu-id="d59d7-156">Der nächste Befehl kopiert den Dateiinhalt in eine neue Datei, `MyDotNetTypes.Format.ps1xml` .</span><span class="sxs-lookup"><span data-stu-id="d59d7-156">The next command copies the file contents to a new file, `MyDotNetTypes.Format.ps1xml`.</span></span>

```powershell
Copy-Item $PSHome\DotNetTypes.format.ps1xml MyDotNetTypes.Format.ps1xml
```

<span data-ttu-id="d59d7-157">Öffnen Sie die `MyDotNetTypes.Format.ps1xml` Datei in einem beliebigen XML-oder Text-Editor, z. b. Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="d59d7-157">Open the `MyDotNetTypes.Format.ps1xml` file in any XML or text editor, such as Visual Studio Code.</span></span> <span data-ttu-id="d59d7-158">Suchen Sie den Abschnitt **System. Globalization. CultureInfo** -Objekt.</span><span class="sxs-lookup"><span data-stu-id="d59d7-158">Find the **System.Globalization.CultureInfo** object section.</span></span> <span data-ttu-id="d59d7-159">Der folgende XML-Code definiert die Ansichten des **CultureInfo** -Objekts.</span><span class="sxs-lookup"><span data-stu-id="d59d7-159">The following XML defines the views of the **CultureInfo** object.</span></span> <span data-ttu-id="d59d7-160">Das-Objekt verfügt nur über eine **tablecontrol** -Sicht.</span><span class="sxs-lookup"><span data-stu-id="d59d7-160">The object has only a **TableControl** view.</span></span>

```xml
<View>
  <Name>System.Globalization.CultureInfo</Name>
  <ViewSelectedBy>
    <TypeName>Deserialized.System.Globalization.CultureInfo</TypeName>
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
```

<span data-ttu-id="d59d7-161">Löschen Sie den Rest der Datei mit Ausnahme der öffnenden `<?xml>` `<Configuration>` Tags,, und `<ViewDefinitions>` und der schließenden `<ViewDefinitions>` -und- `<Configuration>` Tags.</span><span class="sxs-lookup"><span data-stu-id="d59d7-161">Delete the remainder of the file, except for the opening `<?xml>`, `<Configuration>`, and `<ViewDefinitions>` tags and the closing `<ViewDefinitions>` and `<Configuration>` tags.</span></span> <span data-ttu-id="d59d7-162">Wenn eine digitale Signatur vorhanden ist, löschen Sie Sie aus der benutzerdefinierten `Format.ps1xml` Datei.</span><span class="sxs-lookup"><span data-stu-id="d59d7-162">If there is a digital signature, delete it from your custom `Format.ps1xml`file.</span></span>

<span data-ttu-id="d59d7-163">Die `MyDotNetTypes.Format.ps1xml` Datei sollte nun wie im folgenden Beispiel aussehen:</span><span class="sxs-lookup"><span data-stu-id="d59d7-163">The `MyDotNetTypes.Format.ps1xml` file should now look like the following sample:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<Configuration>
<ViewDefinitions>
<View>
  <Name>System.Globalization.CultureInfo</Name>
  <ViewSelectedBy>
    <TypeName>Deserialized.System.Globalization.CultureInfo</TypeName>
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
      <TableColumnHeader/>
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

<span data-ttu-id="d59d7-164">Erstellen Sie eine neue Spalte für die **Calendar** -Eigenschaft, indem Sie einen neuen Satz von Tags hinzufügen `<TableColumnHeader>` .</span><span class="sxs-lookup"><span data-stu-id="d59d7-164">Create a new column for the **Calendar** property by adding a new set of `<TableColumnHeader>` tags.</span></span> <span data-ttu-id="d59d7-165">Der Wert der **Calendar** -Eigenschaft kann lang sein. Geben Sie daher einen Wert von 45 Zeichen als an `<Width>` .</span><span class="sxs-lookup"><span data-stu-id="d59d7-165">The value of the **Calendar** property can be long, so specify a value of 45 characters as the `<Width>`.</span></span>

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

<span data-ttu-id="d59d7-166">Fügen Sie ein neues Spalten Element für **Calendar** in den Tabellenzeilen mithilfe `<TableColumnItem>` der `<PropertyName` Tags und hinzu:</span><span class="sxs-lookup"><span data-stu-id="d59d7-166">Add a new column item for **Calendar** in the table rows using the `<TableColumnItem>` and `<PropertyName` tags:</span></span>

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

<span data-ttu-id="d59d7-167">Speichern und schließen Sie die Datei.</span><span class="sxs-lookup"><span data-stu-id="d59d7-167">Save and close the file.</span></span> <span data-ttu-id="d59d7-168">Verwenden Sie `Update-FormatData` , um der aktuellen PowerShell-Sitzung die neue Format Datei hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="d59d7-168">Use `Update-FormatData` to add the new format file to the current PowerShell session.</span></span>

<span data-ttu-id="d59d7-169">In diesem Beispiel wird der **prepdpath** -Parameter verwendet, um die neue Datei in einer höheren Rangfolge als die ursprüngliche Datei zu platzieren.</span><span class="sxs-lookup"><span data-stu-id="d59d7-169">This example uses the **PrependPath** parameter to place the new file in a higher precedence order than the original file.</span></span> <span data-ttu-id="d59d7-170">Weitere Informationen finden Sie unter [Update-formatdata](xref:Microsoft.PowerShell.Utility.Update-FormatData).</span><span class="sxs-lookup"><span data-stu-id="d59d7-170">For more information, see [Update-FormatData](xref:Microsoft.PowerShell.Utility.Update-FormatData).</span></span>

```powershell
Update-FormatData -PrependPath $PSHOME\MyDotNetTypes.Format.ps1xml
```

<span data-ttu-id="d59d7-171">Zum Testen der Änderung geben Sie ein, `Get-Culture` und überprüfen Sie die Ausgabe, die die **Calendar** -Eigenschaft enthält.</span><span class="sxs-lookup"><span data-stu-id="d59d7-171">To test the change, type `Get-Culture` and review the output that includes the **Calendar** property.</span></span>

```powershell
Get-Culture
```

```Output
LCID Name  Calendar                               DisplayName
---- ----  --------                               -----------
1033 en-US System.Globalization.GregorianCalendar English (United States)
```

## <a name="the-xml-in-formatps1xml-files"></a><span data-ttu-id="d59d7-172">Der XML-Code in Format.ps1XML-Dateien</span><span class="sxs-lookup"><span data-stu-id="d59d7-172">The XML in Format.ps1xml files</span></span>

<span data-ttu-id="d59d7-173">Die vollständige Schema Definition finden Sie in der [Datei "Format. xsd](https://github.com/PowerShell/PowerShell/blob/master/src/Schemas/Format.xsd) " im PowerShell-Quellcoderepository auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="d59d7-173">The full schema definition can be found in [Format.xsd](https://github.com/PowerShell/PowerShell/blob/master/src/Schemas/Format.xsd) in the PowerShell source code repository on GitHub.</span></span>

<span data-ttu-id="d59d7-174">Der **viewdefinitions** -Abschnitt jeder `Format.ps1xml` Datei enthält die `<View>` Tags, die jede Ansicht definieren.</span><span class="sxs-lookup"><span data-stu-id="d59d7-174">The **ViewDefinitions** section of each `Format.ps1xml` file contains the `<View>` tags that define each view.</span></span> <span data-ttu-id="d59d7-175">Ein typisches `<View>` Tag umfasst die folgenden Tags:</span><span class="sxs-lookup"><span data-stu-id="d59d7-175">A typical `<View>` tag includes the following tags:</span></span>

- <span data-ttu-id="d59d7-176">`<Name>` identifiziert den Namen der Ansicht.</span><span class="sxs-lookup"><span data-stu-id="d59d7-176">`<Name>` identifies the name of the view.</span></span>
- <span data-ttu-id="d59d7-177">`<ViewSelectedBy>` Gibt den Objekttyp oder die Typen an, für die die Ansicht gilt.</span><span class="sxs-lookup"><span data-stu-id="d59d7-177">`<ViewSelectedBy>` specifies the object type or types to which the view applies.</span></span>
- <span data-ttu-id="d59d7-178">`<GroupBy>` Gibt an, wie Elemente in der Ansicht in Gruppen kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="d59d7-178">`<GroupBy>` specifies how items in the view will be combined in groups.</span></span>
- <span data-ttu-id="d59d7-179">`<TableControl>`, `<ListControl>` , `<WideControl>` und `<CustomControl>` enthalten die Tags, die angeben, wie die einzelnen Elemente angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d59d7-179">`<TableControl>`, `<ListControl>`, `<WideControl>`, and `<CustomControl>` contain the tags that specify how each item will be displayed.</span></span>

### <a name="viewselectedby-tag"></a><span data-ttu-id="d59d7-180">Viewselectedby-Tag</span><span class="sxs-lookup"><span data-stu-id="d59d7-180">ViewSelectedBy tag</span></span>

<span data-ttu-id="d59d7-181">Das- `<ViewSelectedBy>` Tag kann ein- `<TypeName>` Tag für jeden Objekttyp enthalten, auf den die Ansicht angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="d59d7-181">The `<ViewSelectedBy>` tag can contain a `<TypeName>` tag for each object type to which the view applies.</span></span> <span data-ttu-id="d59d7-182">Oder es kann ein Tag enthalten sein `<SelectionSetName>` , das auf einen Auswahl Satz verweist, der an anderer Stelle mithilfe eines Tags definiert wird `<SelectionSet>` .</span><span class="sxs-lookup"><span data-stu-id="d59d7-182">Or, it can contain a `<SelectionSetName>` tag that references a selection set that is defined elsewhere by using a `<SelectionSet>` tag.</span></span>

### <a name="groupby-tag"></a><span data-ttu-id="d59d7-183">GroupBy-Tag</span><span class="sxs-lookup"><span data-stu-id="d59d7-183">GroupBy tag</span></span>

<span data-ttu-id="d59d7-184">Das- `<GroupBy>` Tag enthält ein- `<PropertyName>` Tag, das die Objekt Eigenschaft angibt, nach der Elemente gruppiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d59d7-184">The `<GroupBy>` tag contains a `<PropertyName>` tag that specifies the object property by which items are to be grouped.</span></span> <span data-ttu-id="d59d7-185">Sie enthält auch ein `<Label>` Tag, das eine Zeichenfolge angibt, die als Bezeichnung für jede Gruppe oder ein Tag verwendet wird, `<CustomControlName>` das auf ein benutzerdefiniertes Steuerelement verweist, das an anderer Stelle mithilfe eines Tags definiert ist `<Control>` .</span><span class="sxs-lookup"><span data-stu-id="d59d7-185">It also contains either a `<Label>` tag that specifies a string to be used as a label for each group or a `<CustomControlName>` tag that references a custom control defined elsewhere using a `<Control>` tag.</span></span> <span data-ttu-id="d59d7-186">Das `<Control>` Tag enthält ein `<Name>` Tag und ein `<CustomControl>` Tag.</span><span class="sxs-lookup"><span data-stu-id="d59d7-186">The `<Control>` tag contains a `<Name>` tag and a `<CustomControl>` tag.</span></span>

### <a name="tablecontroltag"></a><span data-ttu-id="d59d7-187">Tablecontroltag</span><span class="sxs-lookup"><span data-stu-id="d59d7-187">TableControlTag</span></span>

<span data-ttu-id="d59d7-188">Das- `<TableControl>` Tag enthält normalerweise `<TableHeaders>` -und- `<TableRowEntries>` Tags, die die Formatierung für den Kopf und die Zeilen der Tabelle definieren.</span><span class="sxs-lookup"><span data-stu-id="d59d7-188">The `<TableControl>` tag typically contains `<TableHeaders>` and `<TableRowEntries>` tags that define the formatting for the table's heads and rows.</span></span> <span data-ttu-id="d59d7-189">Das `<TableHeaders>` -Tag enthält in der Regel `<TableColumnHeader>` Tags, die `<Label>` `<Width>` -,-und- `<Alignment>` Tags enthalten.</span><span class="sxs-lookup"><span data-stu-id="d59d7-189">The `<TableHeaders>` tag typically contains `<TableColumnHeader>` tags that contain `<Label>`, `<Width>`, and `<Alignment>` tags.</span></span> <span data-ttu-id="d59d7-190">Das `<TableRowEntries>` Tag enthält `<TableRowEntry>` Tags für jede Zeile in der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="d59d7-190">The `<TableRowEntries>` tag contains `<TableRowEntry>` tags for each row in the table.</span></span> <span data-ttu-id="d59d7-191">Das- `<TableRowEntry>` Tag enthält ein-Tag `<TableColumnItems>` , das ein- `<TableColumnItem>` Tag für jede Spalte in der Zeile enthält.</span><span class="sxs-lookup"><span data-stu-id="d59d7-191">The `<TableRowEntry>` tag contains a `<TableColumnItems>` tag that contains a `<TableColumnItem>` tag for each column in the row.</span></span> <span data-ttu-id="d59d7-192">In der Regel `<TableColumnItem>` enthält das Tag entweder ein `<PropertyName>` Tag, das die Objekt Eigenschaft angibt, die am definierten Speicherort angezeigt werden soll, oder ein `<ScriptBlock>` Tag, das Skriptcode enthält, der ein Ergebnis berechnet, das am Speicherort angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="d59d7-192">Typically, the `<TableColumnItem>` tag contains either a `<PropertyName>` tag that identifies the object property to be displayed in the defined location, or a `<ScriptBlock>` tag that contains script code that calculates a result that is to be displayed in the location.</span></span>

> [!NOTE]
> <span data-ttu-id="d59d7-193">Skriptblöcke können auch an anderen Speicherorten verwendet werden, an denen berechnete Ergebnisse nützlich sein können.</span><span class="sxs-lookup"><span data-stu-id="d59d7-193">Script blocks can also be used elsewhere in locations where calculated results can be useful.</span></span>

<span data-ttu-id="d59d7-194">Das- `<TableColumnItem>` Tag kann auch ein- `<FormatString>` Tag enthalten, das angibt, wie die-Eigenschaft oder die berechneten Ergebnisse angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d59d7-194">The `<TableColumnItem>` tag can also contain a `<FormatString>` tag that specifies how the property or the calculated results will be displayed.</span></span>

### <a name="listcontrol-tag"></a><span data-ttu-id="d59d7-195">ListControl-Tag</span><span class="sxs-lookup"><span data-stu-id="d59d7-195">ListControl tag</span></span>

<span data-ttu-id="d59d7-196">Das- `<ListControl>` Tag enthält normalerweise ein- `<ListEntries>` Tag.</span><span class="sxs-lookup"><span data-stu-id="d59d7-196">The `<ListControl>` tag typically contains a `<ListEntries>` tag.</span></span> <span data-ttu-id="d59d7-197">Das `<ListEntries>` Tag enthält ein `<ListEntry>` Tag.</span><span class="sxs-lookup"><span data-stu-id="d59d7-197">The `<ListEntries>` tag contains a `<ListEntry>` tag.</span></span> <span data-ttu-id="d59d7-198">Das `<ListEntry>` Tag enthält ein `<ListItems>` Tag.</span><span class="sxs-lookup"><span data-stu-id="d59d7-198">The `<ListEntry>` tag contains a `<ListItems>` tag.</span></span> <span data-ttu-id="d59d7-199">Das- `<ListItems>` Tag enthält `<ListItem>` Tags, die `<PropertyName>` Tags enthalten.</span><span class="sxs-lookup"><span data-stu-id="d59d7-199">The `<ListItems>` tag contains `<ListItem>` tags, which contain `<PropertyName>` tags.</span></span> <span data-ttu-id="d59d7-200">`<PropertyName>`Mit den Tags wird die Objekt Eigenschaft angegeben, die an der angegebenen Position in der Liste angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="d59d7-200">The `<PropertyName>` tags specify the object property to be displayed at the specified location in the list.</span></span> <span data-ttu-id="d59d7-201">Wenn die Ansichts Auswahl mithilfe eines Auswahl Satzes definiert ist, `<ListControl>` `<ListEntry>` können die Tags und auch ein `<EntrySelectedBy>` Tag enthalten, das ein oder mehrere `<TypeName>` Tags enthält.</span><span class="sxs-lookup"><span data-stu-id="d59d7-201">If the view selection is defined using a selection set, the `<ListControl>` and `<ListEntry>` tags can also contain an `<EntrySelectedBy>` tag that contains one or more `<TypeName>` tags.</span></span> <span data-ttu-id="d59d7-202">Diese `<TypeName>` Tags geben den Objekttyp an, der vom `<ListControl>` Tag angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="d59d7-202">These `<TypeName>` tags specify the object type that the `<ListControl>` tag is intended to display.</span></span>

### <a name="widecontrol-tag"></a><span data-ttu-id="d59d7-203">Widecontrol-Tag</span><span class="sxs-lookup"><span data-stu-id="d59d7-203">WideControl tag</span></span>

<span data-ttu-id="d59d7-204">Das- `<WideControl>` Tag enthält normalerweise ein- `<WideEntries>` Tag.</span><span class="sxs-lookup"><span data-stu-id="d59d7-204">The `<WideControl>` tag typically contains a `<WideEntries>` tag.</span></span> <span data-ttu-id="d59d7-205">Das- `<WideEntries>` Tag enthält ein oder mehrere `<WideEntry>` Tags.</span><span class="sxs-lookup"><span data-stu-id="d59d7-205">The `<WideEntries>` tag contains one or more `<WideEntry>` tags.</span></span> <span data-ttu-id="d59d7-206">Ein- `<WideEntry>` Tag enthält normalerweise ein- `<PropertyName>` Tag, das die Eigenschaft angibt, die an der angegebenen Position in der Ansicht angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="d59d7-206">A `<WideEntry>` tag typically contains a `<PropertyName>` tag that specifies the property to be displayed at the specified location in the view.</span></span> <span data-ttu-id="d59d7-207">Das- `<PropertyName>` Tag kann ein- `<FormatString>` Tag enthalten, das angibt, wie die-Eigenschaft angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="d59d7-207">The `<PropertyName>` tag can contain a `<FormatString>` tag that specifies how the property is to be displayed.</span></span>

### <a name="customcontrol-tag"></a><span data-ttu-id="d59d7-208">CustomControl-Tag</span><span class="sxs-lookup"><span data-stu-id="d59d7-208">CustomControl tag</span></span>

<span data-ttu-id="d59d7-209">Mit dem- `<CustomControl>` Tag können Sie einen Skriptblock verwenden, um ein Format zu definieren.</span><span class="sxs-lookup"><span data-stu-id="d59d7-209">The `<CustomControl>` tag lets you use a script block to define a format.</span></span> <span data-ttu-id="d59d7-210">Ein `<CustomControl>` Tag enthält normalerweise ein `<CustomEntries>` Tag, das mehrere `<CustomEntry>` Tags enthält.</span><span class="sxs-lookup"><span data-stu-id="d59d7-210">A `<CustomControl>` tag typically contains a `<CustomEntries>` tag that contains multiple `<CustomEntry>` tags.</span></span> <span data-ttu-id="d59d7-211">Jedes `<CustomEntry>` Tag enthält ein `<CustomItem>` Tag, das eine Vielzahl von Tags enthalten kann, die den Inhalt und die Formatierung der angegebenen Position in der Sicht angeben, einschließlich der `<Text>` `<Indentation>` Tags,, `<ExpressionBinding>` und `<NewLine>` .</span><span class="sxs-lookup"><span data-stu-id="d59d7-211">Each `<CustomEntry>` tag contains a `<CustomItem>` tag that can contain a variety of tags that specify contents and formatting of the specified location in the view, including `<Text>`, `<Indentation>`, `<ExpressionBinding>`, and `<NewLine>` tags.</span></span>

## <a name="default-displays-in-typesps1xml"></a><span data-ttu-id="d59d7-212">Standard Anzeige in Types.ps1XML</span><span class="sxs-lookup"><span data-stu-id="d59d7-212">Default displays in Types.ps1xml</span></span>

<span data-ttu-id="d59d7-213">Die Standard Anzeige einiger grundlegender Objekttypen wird in der `Types.ps1xml` Datei im Verzeichnis definiert `$PSHOME` .</span><span class="sxs-lookup"><span data-stu-id="d59d7-213">The default displays of some basic object types are defined in the `Types.ps1xml` file in the `$PSHOME` directory.</span></span> <span data-ttu-id="d59d7-214">Die Knoten haben den Namen **psstandardmembers** , und die untergeordneten Knoten verwenden eines der folgenden Tags:</span><span class="sxs-lookup"><span data-stu-id="d59d7-214">The nodes are named **PsStandardMembers** , and the subnodes use one of the following tags:</span></span>

- `<DefaultDisplayProperty>`
- `<DefaultDisplayPropertySet>`
- `<DefaultKeyPropertySet>`

<span data-ttu-id="d59d7-215">Weitere Informationen finden Sie unter [about_Types.ps1XML](about_Types.ps1xml.md).</span><span class="sxs-lookup"><span data-stu-id="d59d7-215">For more information, see [about_Types.ps1xml](about_Types.ps1xml.md).</span></span>

## <a name="tracing-formatps1xml-file-use"></a><span data-ttu-id="d59d7-216">Ablauf Verfolgung Format.ps1XML-Datei Verwendung</span><span class="sxs-lookup"><span data-stu-id="d59d7-216">Tracing Format.ps1xml file use</span></span>

<span data-ttu-id="d59d7-217">Verwenden Sie zum Erkennen von Fehlern beim Laden oder bei der Anwendung von `Format.ps1xml` Dateien das- `Trace-Command` Cmdlet mit den folgenden Format Komponenten als Wert für den **Name** -Parameter:</span><span class="sxs-lookup"><span data-stu-id="d59d7-217">To detect errors in the loading or application of `Format.ps1xml` files, use the `Trace-Command` cmdlet with any of the following format components as the value of the **Name** parameter:</span></span>

- <span data-ttu-id="d59d7-218">Formatfileloading</span><span class="sxs-lookup"><span data-stu-id="d59d7-218">FormatFileLoading</span></span>
- <span data-ttu-id="d59d7-219">Formatviewbinding</span><span class="sxs-lookup"><span data-stu-id="d59d7-219">FormatViewBinding</span></span>

<span data-ttu-id="d59d7-220">Weitere Informationen finden Sie unter [Trace-Command](xref:Microsoft.PowerShell.Utility.Trace-Command) und [Get-TraceSource](xref:Microsoft.PowerShell.Utility.Get-TraceSource).</span><span class="sxs-lookup"><span data-stu-id="d59d7-220">For more information, see [Trace-Command](xref:Microsoft.PowerShell.Utility.Trace-Command) and [Get-TraceSource](xref:Microsoft.PowerShell.Utility.Get-TraceSource).</span></span>

## <a name="signing-a-formatps1xml-file"></a><span data-ttu-id="d59d7-221">Signieren einer Format.ps1-XML-Datei</span><span class="sxs-lookup"><span data-stu-id="d59d7-221">Signing a Format.ps1xml file</span></span>

<span data-ttu-id="d59d7-222">`Format.ps1xml`Signieren Sie die Datei mithilfe einer digitalen Signatur, um die Benutzer Ihrer-Datei zu schützen.</span><span class="sxs-lookup"><span data-stu-id="d59d7-222">To protect the users of your `Format.ps1xml` file, sign the file using a digital signature.</span></span> <span data-ttu-id="d59d7-223">Weitere Informationen finden Sie unter [about_Signing](about_Signing.md).</span><span class="sxs-lookup"><span data-stu-id="d59d7-223">For more information, see [about_Signing](about_Signing.md).</span></span>

## <a name="sample-xml-for-a-format-table-custom-view"></a><span data-ttu-id="d59d7-224">Beispiel-XML für eine Format-Table benutzerdefinierte Ansicht</span><span class="sxs-lookup"><span data-stu-id="d59d7-224">Sample XML for a Format-Table custom view</span></span>

<span data-ttu-id="d59d7-225">Im folgenden Beispiel wird eine `Format-Table` benutzerdefinierte Ansicht für die **System. IO. directeryinfo** -und **System. IO. FileInfo** -Objekte erstellt, die von erstellt werden `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="d59d7-225">The following sample creates a `Format-Table` custom view for the **System.IO.DirectoryInfo** and **System.IO.FileInfo** objects created by `Get-ChildItem`.</span></span> <span data-ttu-id="d59d7-226">Die benutzerdefinierte Ansicht hat den Namen **mygciview** und fügt der Tabelle die Spalte " **kreationtime** " hinzu.</span><span class="sxs-lookup"><span data-stu-id="d59d7-226">The custom view is named **mygciview** and adds the **CreationTime** column to the table.</span></span>

<span data-ttu-id="d59d7-227">Die benutzerdefinierte Ansicht wird aus einer bearbeiteten Version der `FileSystem.Format.ps1xml` Datei erstellt, die in in `$PSHOME` PowerShell 5,1 gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="d59d7-227">The custom view is created from an edited version of the `FileSystem.Format.ps1xml` file that's stored in `$PSHOME` on PowerShell 5.1.</span></span>

<span data-ttu-id="d59d7-228">Nachdem die benutzerdefinierte `.ps1xml` Datei gespeichert wurde, verwenden `Update-FormatData` Sie, um die Ansicht in eine PowerShell-Sitzung einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="d59d7-228">After your custom `.ps1xml` file is saved, use `Update-FormatData` to include the view in a PowerShell session.</span></span> <span data-ttu-id="d59d7-229">In diesem Beispiel muss die benutzerdefinierte Sicht das Tabellenformat verwenden, andernfalls `Format-Table` schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="d59d7-229">For this example, the custom view must use the table format, otherwise, `Format-Table` fails.</span></span>

<span data-ttu-id="d59d7-230">Verwenden `Format-Table` Sie mit dem **View** -Parameter, um den Namen der benutzerdefinierten Ansicht anzugeben und die Ausgabe der Tabelle zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="d59d7-230">Use `Format-Table` with the **View** parameter to specify the custom view's name and format the table's output.</span></span> <span data-ttu-id="d59d7-231">Ein Beispiel für die Art und Weise, wie der Befehl ausgeführt wird, finden Sie unter [Format-Table](xref:Microsoft.PowerShell.Utility.Format-Table).</span><span class="sxs-lookup"><span data-stu-id="d59d7-231">For an example of how the command is run, see [Format-Table](xref:Microsoft.PowerShell.Utility.Format-Table).</span></span>

```powershell
$Parms = @{
  Path = "$PSHOME\*Format.ps1xml"
  Pattern = "System.IO.DirectoryInfo"
}
Select-String @Parms
Copy-Item $PSHome\FileSystem.format.ps1xml .\MyFileSystem.Format.ps1xml
Update-FormatData -PrependPath $PSHOME\Format\MyFileSystem.Format.ps1xml
```

> [!NOTE]
> <span data-ttu-id="d59d7-232">Um das XML-Beispiel in Einschränkungen der Zeilenbreite zu integrieren, war es erforderlich, einen Einzug zu komprimieren und Zeilenumbrüche innerhalb des Codes zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="d59d7-232">To fit the XML sample within line width limitations, it was necessary to compress some indentation and use line breaks within the code.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<Configuration>
    <SelectionSets>
        <SelectionSet>
            <Name>FileSystemTypes</Name>
            <Types>
                <TypeName>System.IO.DirectoryInfo</TypeName>
                <TypeName>System.IO.FileInfo</TypeName>
            </Types>
        </SelectionSet>
    </SelectionSets>
<Controls>
<Control>
<Name>FileSystemTypes-GroupingFormat</Name>
<CustomControl>
 <CustomEntries>
  <CustomEntry>
    <CustomItem>
    <Frame>
    <LeftIndent>4</LeftIndent>
    <CustomItem>
    <Text AssemblyName="System.Management.Automation"
    BaseName="FileSystemProviderStrings"
    ResourceId="DirectoryDisplayGrouping"/>
    <ExpressionBinding>
     <ScriptBlock>
      $_.PSParentPath.Replace("Microsoft.PowerShell.Core\FileSystem::", "")
     </ScriptBlock>
    </ExpressionBinding>
    <NewLine/>
    </CustomItem>
    </Frame>
    </CustomItem>
    </CustomEntry>
 </CustomEntries>
</CustomControl>
</Control>
</Controls>
<ViewDefinitions>
    <View>
    <Name>mygciview</Name>
    <ViewSelectedBy>
        <SelectionSetName>FileSystemTypes</SelectionSetName>
    </ViewSelectedBy>
    <GroupBy>
      <PropertyName>PSParentPath</PropertyName>
      <CustomControlName>FileSystemTypes-GroupingFormat</CustomControlName>
    </GroupBy>
        <TableControl>
            <TableHeaders>
                <TableColumnHeader>
                    <Label>Mode</Label>
                    <Width>7</Width>
                    <Alignment>left</Alignment>
                </TableColumnHeader>
                <TableColumnHeader>
                    <Label>LastWriteTime</Label>
                    <Width>25</Width>
                    <Alignment>right</Alignment>
                </TableColumnHeader>
                <TableColumnHeader>
                    <Label>CreationTime</Label>
                    <Width>25</Width>
                    <Alignment>right</Alignment>
                </TableColumnHeader>
                <TableColumnHeader>
                    <Label>Length</Label>
                    <Width>14</Width>
                    <Alignment>right</Alignment>
                </TableColumnHeader>
                <TableColumnHeader/>
            </TableHeaders>
            <TableRowEntries>
                <TableRowEntry>
                    <Wrap/>
                    <TableColumnItems>
                        <TableColumnItem>
                            <PropertyName>Mode</PropertyName>
                        </TableColumnItem>
                        <TableColumnItem>
                            <ScriptBlock>
                                [String]::Format("{0,10}  {1,8}",
                                    $_.LastWriteTime.ToString("d"),
                                    $_.LastWriteTime.ToString("t"))
                            </ScriptBlock>
                        </TableColumnItem>
                        <TableColumnItem>
                            <ScriptBlock>
                                [String]::Format("{0,10}  {1,8}",
                                    $_.CreationTime.ToString("d"),
                                    $_.LastWriteTime.ToString("t"))
                            </ScriptBlock>
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

## <a name="see-also"></a><span data-ttu-id="d59d7-233">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="d59d7-233">See also</span></span>

[<span data-ttu-id="d59d7-234">Export-FormatData</span><span class="sxs-lookup"><span data-stu-id="d59d7-234">Export-FormatData</span></span>](xref:Microsoft.PowerShell.Utility.Export-FormatData)

[<span data-ttu-id="d59d7-235">Get-FormatData</span><span class="sxs-lookup"><span data-stu-id="d59d7-235">Get-FormatData</span></span>](xref:Microsoft.PowerShell.Utility.Get-FormatData)

[<span data-ttu-id="d59d7-236">Get-TraceSource</span><span class="sxs-lookup"><span data-stu-id="d59d7-236">Get-TraceSource</span></span>](xref:Microsoft.PowerShell.Utility.Get-TraceSource)

[<span data-ttu-id="d59d7-237">Formatschema – XML-Referenz</span><span class="sxs-lookup"><span data-stu-id="d59d7-237">Format Schema XML Reference</span></span>](/powershell/scripting/developer/format/format-schema-xml-reference)

[<span data-ttu-id="d59d7-238">Trace-Command</span><span class="sxs-lookup"><span data-stu-id="d59d7-238">Trace-Command</span></span>](xref:Microsoft.PowerShell.Utility.Trace-Command)

[<span data-ttu-id="d59d7-239">Update-FormatData</span><span class="sxs-lookup"><span data-stu-id="d59d7-239">Update-FormatData</span></span>](xref:Microsoft.PowerShell.Utility.Update-FormatData)

[<span data-ttu-id="d59d7-240">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="d59d7-240">Writing a PowerShell Formatting File</span></span>](/powershell/scripting/developer/format/writing-a-powershell-formatting-file)
