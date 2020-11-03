---
description: Erläutert `Types.ps1xml` die Verwendung von Dateien zum Erweitern der Objekttypen, die in PowerShell verwendet werden.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 04/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_types.ps1xml?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Types.ps1xml
ms.openlocfilehash: 66c319a6f1e84fb2d7aeea60433a2ddea9fb4616
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222332"
---
# <a name="about-typesps1xml"></a><span data-ttu-id="3da9f-104">Informationen zu Types.ps1XML</span><span class="sxs-lookup"><span data-stu-id="3da9f-104">About Types.ps1xml</span></span>

## <a name="short-description"></a><span data-ttu-id="3da9f-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3da9f-105">Short description</span></span>
<span data-ttu-id="3da9f-106">Erläutert `Types.ps1xml` die Verwendung von Dateien zum Erweitern der Objekttypen, die in PowerShell verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3da9f-106">Explains how to use `Types.ps1xml` files to extend the types of objects that are used in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="3da9f-107">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3da9f-107">Long description</span></span>

<span data-ttu-id="3da9f-108">Erweiterte Typdaten definieren zusätzliche Eigenschaften und Methoden ("Member") von Objekttypen in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3da9f-108">Extended type data defines additional properties and methods ("members") of object types in PowerShell.</span></span> <span data-ttu-id="3da9f-109">Es gibt zwei Verfahren zum Hinzufügen von erweiterten Typdaten zu einer PowerShell-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="3da9f-109">There are two techniques for adding extended type data to a PowerShell session.</span></span>

- <span data-ttu-id="3da9f-110">`Types.ps1xml` file: eine XML-Datei, die erweiterte Typdaten definiert.</span><span class="sxs-lookup"><span data-stu-id="3da9f-110">`Types.ps1xml` file: An XML file that defines extended type data.</span></span>
- <span data-ttu-id="3da9f-111">`Update-TypeData`: Ein Cmdlet, das Dateien erneut lädt `Types.ps1xml` und erweiterte Daten für Typen in der aktuellen Sitzung definiert.</span><span class="sxs-lookup"><span data-stu-id="3da9f-111">`Update-TypeData`: A cmdlet that reloads `Types.ps1xml` files and defines extended data for types in the current session.</span></span>

<span data-ttu-id="3da9f-112">In diesem Thema werden- `Types.ps1xml` Dateien beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3da9f-112">This topic describes `Types.ps1xml` files.</span></span> <span data-ttu-id="3da9f-113">Weitere Informationen zur Verwendung des `Update-TypeData` Cmdlets, um der aktuellen Sitzung dynamische erweiterte Typdaten hinzuzufügen, finden Sie unter [Update-typedata](xref:Microsoft.PowerShell.Utility.Update-TypeData).</span><span class="sxs-lookup"><span data-stu-id="3da9f-113">For more information about using the `Update-TypeData` cmdlet to add dynamic extended type data to the current session see [Update-TypeData](xref:Microsoft.PowerShell.Utility.Update-TypeData).</span></span>

## <a name="about-extended-type-data"></a><span data-ttu-id="3da9f-114">Informationen zu erweiterten Typdaten</span><span class="sxs-lookup"><span data-stu-id="3da9f-114">About extended type data</span></span>

<span data-ttu-id="3da9f-115">Erweiterte Typdaten definieren zusätzliche Eigenschaften und Methoden ("Member") von Objekttypen in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3da9f-115">Extended type data defines additional properties and methods ("members") of object types in PowerShell.</span></span> <span data-ttu-id="3da9f-116">Sie können jeden von PowerShell unterstützten Typ erweitern und die hinzugefügten Eigenschaften und Methoden auf die gleiche Weise verwenden, wie Sie die Eigenschaften verwenden, die für die Objekttypen definiert sind.</span><span class="sxs-lookup"><span data-stu-id="3da9f-116">You can extend any type that is supported by PowerShell and use the added properties and methods in the same way that you use the properties that are defined on the object types.</span></span>

<span data-ttu-id="3da9f-117">Beispielsweise fügt PowerShell allen **DateTime** `System.DateTime` Objekten, wie z. b. den vom Cmdlet zurückgegebenen Objekten, eine DateTime-Eigenschaft hinzu `Get-Date` .</span><span class="sxs-lookup"><span data-stu-id="3da9f-117">For example, PowerShell adds a **DateTime** property to all `System.DateTime` objects, such as the ones that the `Get-Date` cmdlet returns.</span></span>

```powershell
(Get-Date).DateTime
```

```Output
Sunday, January 29, 2012 9:43:57 AM
```

<span data-ttu-id="3da9f-118">Die **DateTime** -Eigenschaft wird in der Beschreibung der [System. DateTime](/dotnet/api/system.datetime) -Struktur nicht gefunden, da die Eigenschaft von PowerShell hinzugefügt wird und nur in PowerShell sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="3da9f-118">You won't find the **DateTime** property in the description of the [System.DateTime](/dotnet/api/system.datetime) structure, because PowerShell adds the property and it is visible only in PowerShell.</span></span>

<span data-ttu-id="3da9f-119">PowerShell definiert intern einen Standardsatz erweiterter Typen.</span><span class="sxs-lookup"><span data-stu-id="3da9f-119">PowerShell internally defines a default set of extended types.</span></span> <span data-ttu-id="3da9f-120">Diese Typinformationen werden beim Start in jede PowerShell-Sitzung geladen.</span><span class="sxs-lookup"><span data-stu-id="3da9f-120">This type information is loaded in every PowerShell session at startup.</span></span> <span data-ttu-id="3da9f-121">Die **DateTime** -Eigenschaft ist Teil dieses Standardsatzes.</span><span class="sxs-lookup"><span data-stu-id="3da9f-121">The **DateTime** property is part of this default set.</span></span> <span data-ttu-id="3da9f-122">Vor PowerShell 6 wurden die Typdefinitionen `Types.ps1xml` im PowerShell-Installationsverzeichnis ( `$PSHOME` ) gespeichert.</span><span class="sxs-lookup"><span data-stu-id="3da9f-122">Prior to PowerShell 6, the type definitions were stored the `Types.ps1xml` file in the PowerShell installation directory (`$PSHOME`).</span></span>

## <a name="adding-extended-type-data-to-powershell"></a><span data-ttu-id="3da9f-123">Hinzufügen von erweiterten Typdaten zu PowerShell</span><span class="sxs-lookup"><span data-stu-id="3da9f-123">Adding extended type data to PowerShell</span></span>

<span data-ttu-id="3da9f-124">Es gibt drei Quellen für erweiterte Typdaten in PowerShell-Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="3da9f-124">There are three sources of extended type data in PowerShell sessions.</span></span>

- <span data-ttu-id="3da9f-125">Der von PowerShell definierte und wird automatisch in jede PowerShell-Sitzung geladen.</span><span class="sxs-lookup"><span data-stu-id="3da9f-125">The defined by PowerShell and is loaded automatically into every PowerShell session.</span></span> <span data-ttu-id="3da9f-126">Ab PowerShell 6 werden diese Informationen in PowerShell kompiliert und sind nicht mehr in einer `Types.ps1xml` Datei enthalten.</span><span class="sxs-lookup"><span data-stu-id="3da9f-126">Beginning with PowerShell 6, this information is compiled into PowerShell and is no longer shipped in a `Types.ps1xml` file.</span></span>

- <span data-ttu-id="3da9f-127">Die `Types.ps1xml` Dateien, die Module exportieren, werden geladen, wenn das Modul in die aktuelle Sitzung importiert wird.</span><span class="sxs-lookup"><span data-stu-id="3da9f-127">The `Types.ps1xml` files that modules export are loaded when the module is imported into the current session.</span></span>

- <span data-ttu-id="3da9f-128">Erweiterte Typdaten, die mithilfe des-Cmdlets definiert werden, werden `Update-TypeData` nur zur aktuellen Sitzung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="3da9f-128">Extended type data that is defined by using the `Update-TypeData` cmdlet is added only to the current session.</span></span> <span data-ttu-id="3da9f-129">Er wird nicht in einer Datei gespeichert.</span><span class="sxs-lookup"><span data-stu-id="3da9f-129">It is not saved in a file.</span></span>

<span data-ttu-id="3da9f-130">In der Sitzung werden die erweiterten Typdaten aus den drei Quellen auf die gleiche Weise auf-Objekte angewendet und sind für alle Objekte der angegebenen Typen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="3da9f-130">In the session, the extended type data from the three sources is applied to objects in the same way and is available on all objects of the specified types.</span></span>

## <a name="the-typedata-cmdlets"></a><span data-ttu-id="3da9f-131">Die typedata-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="3da9f-131">The TypeData cmdlets</span></span>

<span data-ttu-id="3da9f-132">Die folgenden Cmdlets sind im **Microsoft. PowerShell. Utility** -Modul in PowerShell 3,0 und höher enthalten.</span><span class="sxs-lookup"><span data-stu-id="3da9f-132">The following cmdlets are included in the **Microsoft.PowerShell.Utility** module in PowerShell 3.0 and later.</span></span>

- <span data-ttu-id="3da9f-133">`Get-TypeData`: Ruft erweiterte Typdaten in der aktuellen Sitzung ab.</span><span class="sxs-lookup"><span data-stu-id="3da9f-133">`Get-TypeData`: Gets extended type data in the current session.</span></span>
- <span data-ttu-id="3da9f-134">`Update-TypeData`: Lädt `Types.ps1xml` Dateien erneut.</span><span class="sxs-lookup"><span data-stu-id="3da9f-134">`Update-TypeData`: Reloads `Types.ps1xml` files.</span></span> <span data-ttu-id="3da9f-135">Fügt der aktuellen Sitzung erweiterte Typdaten hinzu.</span><span class="sxs-lookup"><span data-stu-id="3da9f-135">Adds extended type data to the current session.</span></span>
- <span data-ttu-id="3da9f-136">`Remove-TypeData`: Entfernt erweiterte Typdaten aus der aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="3da9f-136">`Remove-TypeData`: Removes extended type data from the current session.</span></span>

<span data-ttu-id="3da9f-137">Weitere Informationen zu diesen Cmdlets finden Sie im Hilfethema für jedes Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3da9f-137">For more information about these cmdlets, see the help topic for each cmdlet.</span></span>

## <a name="built-in-typesps1xml-files"></a><span data-ttu-id="3da9f-138">Integrierte Types.ps1XML-Dateien</span><span class="sxs-lookup"><span data-stu-id="3da9f-138">Built-in Types.ps1xml files</span></span>

<span data-ttu-id="3da9f-139">Die `Types.ps1xml` Dateien im `$PSHOME` Verzeichnis werden jeder Sitzung automatisch hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="3da9f-139">The `Types.ps1xml` files in the `$PSHOME` directory are added automatically to every session.</span></span>

<span data-ttu-id="3da9f-140">`Types.ps1xml`Bei der Datei im PowerShell-Installationsverzeichnis ( `$PSHOME` ) handelt es sich um eine XML-basierte Textdatei, mit der Sie den Objekten, die in PowerShell verwendet werden, Eigenschaften und Methoden hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="3da9f-140">The `Types.ps1xml` file in the PowerShell installation directory (`$PSHOME`) is an XML-based text file that lets you add properties and methods to the objects that are used in PowerShell.</span></span> <span data-ttu-id="3da9f-141">PowerShell verfügt über integrierte Dateien, die `Types.ps1xml` den .NET-Typen mehrere Elemente hinzufügen. Sie können jedoch zusätzliche `Types.ps1xml` Dateien erstellen, um die Typen weiter zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="3da9f-141">PowerShell has built-in `Types.ps1xml` files that add several elements to the .NET types, but you can create additional `Types.ps1xml` files to further extend the types.</span></span>

<span data-ttu-id="3da9f-142">Standardmäßig verfügen Array Objekte ( `System.Array` ) z. b. über eine **length** -Eigenschaft, die die Anzahl der Objekte im Array auflistet.</span><span class="sxs-lookup"><span data-stu-id="3da9f-142">For example, by default, array objects (`System.Array`) have a **Length** property that lists the number of objects in the array.</span></span> <span data-ttu-id="3da9f-143">Da die Name- **Länge** die Eigenschaft jedoch nicht eindeutig beschreibt, fügt PowerShell eine Alias Eigenschaft mit dem Namen **count** hinzu, die denselben Wert anzeigt.</span><span class="sxs-lookup"><span data-stu-id="3da9f-143">However, because the name **Length** does not clearly describe the property, PowerShell adds an alias property named **Count** that displays the same value.</span></span> <span data-ttu-id="3da9f-144">Im folgenden XML-Code wird die **count** -Eigenschaft zum-Typ hinzugefügt `System.Array` .</span><span class="sxs-lookup"><span data-stu-id="3da9f-144">The following XML adds the **Count** property to the `System.Array` type.</span></span>

```xml
<Type>
  <Name>System.Array</Name>
  <Members>
    <AliasProperty>
      <Name>Count</Name>
      <ReferencedMemberName>
        Length
      </ReferencedMemberName>
    </AliasProperty>
  </Members>
</Type>
```

<span data-ttu-id="3da9f-145">Um die neue **aliasproperty** zu erhalten, verwenden Sie einen `Get-Member` Befehl für ein beliebiges Array, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="3da9f-145">To get the new **AliasProperty** , use a `Get-Member` command on any array, as shown in the following example.</span></span>

```powershell
Get-Member -InputObject (1,2,3,4)
```

<span data-ttu-id="3da9f-146">Der Befehl gibt die folgenden Ergebnisse zurück.</span><span class="sxs-lookup"><span data-stu-id="3da9f-146">The command returns the following results.</span></span>

```Output
Name       MemberType    Definition
----       ----------    ----------
Count      AliasProperty Count = Length
Address    Method        System.Object& Address(Int32)
Clone      Method        System.Object Clone()
CopyTo     Method        System.Void CopyTo(Array array, Int32 index):
Equals     Method        System.Boolean Equals(Object obj)
Get        Method        System.Object Get(Int32)
# ...
```

<span data-ttu-id="3da9f-147">Daher können Sie entweder die **count** -Eigenschaft oder die **length** -Eigenschaft von Arrays in PowerShell verwenden.</span><span class="sxs-lookup"><span data-stu-id="3da9f-147">As a result, you can use either the **Count** property or the **Length** property of arrays in PowerShell.</span></span> <span data-ttu-id="3da9f-148">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3da9f-148">For example:</span></span>

```powershell
(1, 2, 3, 4).count
4
```

```powershell
(1, 2, 3, 4).length
4
```

## <a name="creating-new-typesps1xml-files"></a><span data-ttu-id="3da9f-149">Erstellen neuer Types.ps1XML-Dateien</span><span class="sxs-lookup"><span data-stu-id="3da9f-149">Creating new Types.ps1xml files</span></span>

<span data-ttu-id="3da9f-150">Die `.ps1xml` mit PowerShell installierten Dateien sind digital signiert, um Manipulationen zu verhindern, da die Formatierung Skriptblöcke einschließen kann.</span><span class="sxs-lookup"><span data-stu-id="3da9f-150">The `.ps1xml` files that are installed with PowerShell are digitally signed to prevent tampering because the formatting can include script blocks.</span></span> <span data-ttu-id="3da9f-151">Wenn Sie also eine Eigenschaft oder Methode zu einem .NET-Typ hinzufügen möchten, erstellen Sie Ihre eigenen `Types.ps1xml` Dateien, und fügen Sie Sie dann der PowerShell-Sitzung hinzu.</span><span class="sxs-lookup"><span data-stu-id="3da9f-151">Therefore, to add a property or method to a .NET type, create your own `Types.ps1xml` files, and then add them to your PowerShell session.</span></span>

<span data-ttu-id="3da9f-152">Um eine neue Datei zu erstellen, kopieren Sie zunächst eine vorhandene `Types.ps1xml` Datei.</span><span class="sxs-lookup"><span data-stu-id="3da9f-152">To create a new file, start by copying an existing `Types.ps1xml` file.</span></span> <span data-ttu-id="3da9f-153">Die neue Datei kann einen beliebigen Namen haben, Sie muss jedoch eine `.ps1xml` Dateinamenerweiterung aufweisen.</span><span class="sxs-lookup"><span data-stu-id="3da9f-153">The new file can have any name, but it must have a `.ps1xml` file name extension.</span></span> <span data-ttu-id="3da9f-154">Sie können die neue Datei in einem beliebigen Verzeichnis platzieren, auf das PowerShell zugreifen kann, aber es ist hilfreich, die Dateien im PowerShell-Installationsverzeichnis ( `$PSHOME` ) oder in einem Unterverzeichnis des Installationsverzeichnisses zu platzieren.</span><span class="sxs-lookup"><span data-stu-id="3da9f-154">You can place the new file in any directory that is accessible to PowerShell, but it is useful to place the files in the PowerShell installation directory (`$PSHOME`) or in a subdirectory of the installation directory.</span></span>

<span data-ttu-id="3da9f-155">Wenn Sie die neue Datei gespeichert haben, verwenden Sie das `Update-TypeData` Cmdlet, um die neue Datei zur PowerShell-Sitzung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="3da9f-155">When you have saved the new file, use the `Update-TypeData` cmdlet to add the new file to your PowerShell session.</span></span> <span data-ttu-id="3da9f-156">Wenn Sie möchten, dass Ihre Typen Vorrang vor den integrierten Typen haben, die definiert sind, verwenden Sie den **prepddata** -Parameter des `Update-TypeData` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="3da9f-156">If you want your types to take precedence over the built-in types that are defined, use the **PrependData** parameter of the `Update-TypeData` cmdlet.</span></span> <span data-ttu-id="3da9f-157">`Update-TypeData` wirkt sich nur auf die aktuelle Sitzung aus.</span><span class="sxs-lookup"><span data-stu-id="3da9f-157">`Update-TypeData` affects only the current session.</span></span> <span data-ttu-id="3da9f-158">Um die Änderung an allen zukünftigen Sitzungen vorzunehmen, exportieren Sie die-Konsole, oder fügen Sie den `Update-TypeData` Befehl zu Ihrem PowerShell-Profil hinzu.</span><span class="sxs-lookup"><span data-stu-id="3da9f-158">To make the change to all future sessions, export the console, or add the `Update-TypeData` command to your PowerShell profile.</span></span>

## <a name="typesps1xml-and-add-member"></a><span data-ttu-id="3da9f-159">Types.ps1XML und Add-Member</span><span class="sxs-lookup"><span data-stu-id="3da9f-159">Types.ps1xml and Add-Member</span></span>

<span data-ttu-id="3da9f-160">Die `Types.ps1xml` Dateien fügen Eigenschaften und Methoden zu allen Instanzen der Objekte des angegebenen .net-Typs in der betroffenen PowerShell-Sitzung hinzu.</span><span class="sxs-lookup"><span data-stu-id="3da9f-160">The `Types.ps1xml` files add properties and methods to all the instances of the objects of the specified .NET type in the affected PowerShell session.</span></span> <span data-ttu-id="3da9f-161">Wenn Sie jedoch nur einer Instanz eines Objekts Eigenschaften oder Methoden hinzufügen müssen, verwenden Sie das- `Add-Member` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3da9f-161">However, if you need to add properties or methods only to one instance of an object, use the `Add-Member` cmdlet.</span></span>

<span data-ttu-id="3da9f-162">Weitere Informationen finden Sie unter [Add-Member](xref:Microsoft.PowerShell.Utility.Add-Member).</span><span class="sxs-lookup"><span data-stu-id="3da9f-162">For more information, see [Add-Member](xref:Microsoft.PowerShell.Utility.Add-Member).</span></span>

## <a name="example-adding-an-age-member-to-fileinfo-objects"></a><span data-ttu-id="3da9f-163">Beispiel: Hinzufügen eines Age-Members zu filinput Info-Objekten</span><span class="sxs-lookup"><span data-stu-id="3da9f-163">Example: Adding an Age member to FileInfo objects</span></span>

<span data-ttu-id="3da9f-164">Dieses Beispiel zeigt, wie Sie **System. IO. filinput Info** -Objekten eine **Age** -Eigenschaft hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="3da9f-164">This example shows how to add an **Age** property to **System.IO.FileInfo** objects.</span></span> <span data-ttu-id="3da9f-165">Das Alter einer Datei ist der Unterschied zwischen der Erstellungszeit und der aktuellen Zeit (in Tagen).</span><span class="sxs-lookup"><span data-stu-id="3da9f-165">The age of a file is the difference between its creation time and the current time in days.</span></span>

<span data-ttu-id="3da9f-166">Da die **Age** -Eigenschaft mit einem Skriptblock berechnet wird, suchen Sie `<ScriptProperty>` nach einem Tag, das als Modell für die neue **Age** -Eigenschaft verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="3da9f-166">Because the **Age** property is calculated by using a script block, find a `<ScriptProperty>` tag to use as a model for the new **Age** property.</span></span>

<span data-ttu-id="3da9f-167">Speichern Sie den folgenden XML-Code in der Datei `$PSHOME\MyTypes.ps1xml` .</span><span class="sxs-lookup"><span data-stu-id="3da9f-167">Save the follow XML code to the file `$PSHOME\MyTypes.ps1xml`.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<Types>
  <Type>
    <Name>System.IO.FileInfo</Name>
    <Members>
      <ScriptProperty>
        <Name>Age</Name>
        <GetScriptBlock>
          ((Get-Date) - ($this.CreationTime)).Days
        </GetScriptBlock>
      </ScriptProperty>
    </Members>
  </Type>
</Types>
```

<span data-ttu-id="3da9f-168">Führen Sie aus `Update-TypeData` , um die neue `Types.ps1xml` Datei zur aktuellen Sitzung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="3da9f-168">Run `Update-TypeData` to add the new `Types.ps1xml` file to the current session.</span></span> <span data-ttu-id="3da9f-169">Der Befehl verwendet den **prepddata** -Parameter, um die neue Datei in einer Rangfolge zu platzieren, die höher als die ursprünglichen Definitionen ist.</span><span class="sxs-lookup"><span data-stu-id="3da9f-169">The command uses the **PrependData** parameter to place the new file in a precedence order higher than the original definitions.</span></span>

<span data-ttu-id="3da9f-170">Weitere Informationen zu `Update-TypeData` finden Sie unter [Update-typedata](xref:Microsoft.PowerShell.Utility.Update-TypeData).</span><span class="sxs-lookup"><span data-stu-id="3da9f-170">For more information about `Update-TypeData`, see [Update-TypeData](xref:Microsoft.PowerShell.Utility.Update-TypeData).</span></span>

```powershell
Update-Typedata -PrependPath $PSHOME\MyTypes.ps1xml
```

<span data-ttu-id="3da9f-171">Um die Änderung zu testen, führen Sie einen `Get-ChildItem` Befehl aus, um die PowerShell.exe-Datei im Verzeichnis zu erhalten `$PSHOME` , und übergeben Sie die Datei dann an das `Format-List` Cmdlet, um alle Eigenschaften der Datei aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="3da9f-171">To test the change, run a `Get-ChildItem` command to get the PowerShell.exe file in the `$PSHOME` directory, and then pipe the file to the `Format-List` cmdlet to list all of the properties of the file.</span></span> <span data-ttu-id="3da9f-172">Aufgrund der Änderung wird die **Age** -Eigenschaft in der Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3da9f-172">As a result of the change, the **Age** property appears in the list.</span></span>

```powershell
Get-ChildItem $PSHOME\pwsh.exe | Select-Object Age
```

```Output
142
```

## <a name="the-xml-in-typesps1xml-files"></a><span data-ttu-id="3da9f-173">Der XML-Code in Types.ps1XML-Dateien</span><span class="sxs-lookup"><span data-stu-id="3da9f-173">The XML in Types.ps1xml files</span></span>

<span data-ttu-id="3da9f-174">Die vollständige Schema Definition finden Sie in der Datei " [types. xsd](https://github.com/PowerShell/PowerShell/blob/master/src/Schemas/Types.xsd) " im PowerShell-Quellcoderepository auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="3da9f-174">The full schema definition can be found in [Types.xsd](https://github.com/PowerShell/PowerShell/blob/master/src/Schemas/Types.xsd) in the PowerShell source code repository on GitHub.</span></span>

<span data-ttu-id="3da9f-175">Das- `<Types>` Tag schließt alle Typen ein, die in der Datei definiert sind.</span><span class="sxs-lookup"><span data-stu-id="3da9f-175">The `<Types>` tag encloses all of the types that are defined in the file.</span></span> <span data-ttu-id="3da9f-176">Es darf nur ein Tag vorhanden sein `<Types>` .</span><span class="sxs-lookup"><span data-stu-id="3da9f-176">There should be only one `<Types>` tag.</span></span>

<span data-ttu-id="3da9f-177">Jeder in der Datei erwähnte .NET-Typ sollte durch ein- `<Type>` Tag dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="3da9f-177">Each .NET type mentioned in the file should be represented by a `<Type>` tag.</span></span>

<span data-ttu-id="3da9f-178">Die typtags müssen die folgenden Tags enthalten:</span><span class="sxs-lookup"><span data-stu-id="3da9f-178">The type tags must contain the following tags:</span></span>

<span data-ttu-id="3da9f-179">`<Name>`: Enschließt den Namen des betroffenen .net-Typs.</span><span class="sxs-lookup"><span data-stu-id="3da9f-179">`<Name>`: Encloses the name of the affected .NET type.</span></span>

<span data-ttu-id="3da9f-180">`<Members>`: Schließt die Tags für die neuen Eigenschaften und Methoden ein, die für den .NET-Typ definiert sind.</span><span class="sxs-lookup"><span data-stu-id="3da9f-180">`<Members>`: Encloses the tags for the new properties and methods that are defined for the .NET type.</span></span>

<span data-ttu-id="3da9f-181">Jedes der folgenden Member-Tags kann sich im- `<Members>` Tag befinden.</span><span class="sxs-lookup"><span data-stu-id="3da9f-181">Any of the following member tags can be inside the `<Members>` tag.</span></span>

<span data-ttu-id="3da9f-182">`<AliasProperty>`: Definiert einen neuen Namen für eine vorhandene Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="3da9f-182">`<AliasProperty>`: Defines a new name for an existing property.</span></span>

<span data-ttu-id="3da9f-183">Das `<AliasProperty>` -Tag muss über ein `<Name>` -Tag verfügen, das den Namen der neuen Eigenschaft und ein `<ReferencedMemberName>` Tag angibt, das die vorhandene Eigenschaft angibt.</span><span class="sxs-lookup"><span data-stu-id="3da9f-183">The `<AliasProperty>` tag must have a `<Name>` tag that specifies the name of the new property and a `<ReferencedMemberName>` tag that specifies the existing property.</span></span>

<span data-ttu-id="3da9f-184">Beispielsweise ist die **count** -Alias Eigenschaft ein Alias für die **length** -Eigenschaft von Array-Objekten.</span><span class="sxs-lookup"><span data-stu-id="3da9f-184">For example, the **Count** alias property is an alias for the **Length** property of array objects.</span></span>

```xml
<Type>
  <Name>System.Array</Name>
  <Members>
    <AliasProperty>
      <Name>Count</Name>
      <ReferencedMemberName>Length</ReferencedMemberName>
    </AliasProperty>
  </Members>
</Type>
```

<span data-ttu-id="3da9f-185">`<CodeMethod>`: Verweist auf eine statische Methode einer .NET-Klasse.</span><span class="sxs-lookup"><span data-stu-id="3da9f-185">`<CodeMethod>`:  References a static method of a .NET class.</span></span>

<span data-ttu-id="3da9f-186">Das `<CodeMethod>` -Tag muss über ein `<Name>` -Tag verfügen, das den Namen der neuen Methode und ein `<GetCodeReference>` Tag angibt, das den Code angibt, in dem die Methode definiert ist.</span><span class="sxs-lookup"><span data-stu-id="3da9f-186">The `<CodeMethod>` tag must have a `<Name>` tag that specifies the name of the new method and a `<GetCodeReference>` tag that specifies the code in which the method is defined.</span></span>

<span data-ttu-id="3da9f-187">Beispielsweise ist die **Mode** -Eigenschaft von- `System.IO.DirectoryInfo` Objekten eine im PowerShell-Dateisystem Anbieter definierte Code Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="3da9f-187">For example, the **Mode** property of `System.IO.DirectoryInfo` objects is a code property defined in the PowerShell FileSystem provider.</span></span>

```xml
<Type>
  <Name>System.IO.DirectoryInfo</Name>
  <Members>
    <CodeProperty>
      <Name>Mode</Name>
      <GetCodeReference>
        <TypeName>
          Microsoft.PowerShell.Commands.FileSystemProvider
        </TypeName>
        <MethodName>Mode</MethodName>
      </GetCodeReference>
    </CodeProperty>
  </Members>
</Type>
```

<span data-ttu-id="3da9f-188">`<CodeProperty>`: Verweist auf eine statische Methode einer .NET-Klasse.</span><span class="sxs-lookup"><span data-stu-id="3da9f-188">`<CodeProperty>`: References a static method of a .NET class.</span></span>

<span data-ttu-id="3da9f-189">Das `<CodeProperty>` -Tag muss über ein `<Name>` -Tag verfügen, das den Namen der neuen Eigenschaft und ein `<GetCodeReference>` Tag angibt, das den Code angibt, in dem die Eigenschaft definiert ist.</span><span class="sxs-lookup"><span data-stu-id="3da9f-189">The `<CodeProperty>` tag must have a `<Name>` tag that specifies the name of the new property and a `<GetCodeReference>` tag that specifies the code in which the property is defined.</span></span>

<span data-ttu-id="3da9f-190">Beispielsweise ist die **Mode** -Eigenschaft von- `System.IO.DirectoryInfo` Objekten eine im PowerShell-Dateisystem Anbieter definierte Code Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="3da9f-190">For example, the **Mode** property of `System.IO.DirectoryInfo` objects is a code property defined in the PowerShell FileSystem provider.</span></span>

```xml
<Type>
  <Name>System.IO.DirectoryInfo</Name>
  <Members>
    <CodeProperty>
      <Name>Mode</Name>
      <GetCodeReference>
        <TypeName>
          Microsoft.PowerShell.Commands.FileSystemProvider
        </TypeName>
        <MethodName>Mode</MethodName>
      </GetCodeReference>
    </CodeProperty>
  </Members>
</Type>
```

<span data-ttu-id="3da9f-191">`<MemberSet>`: Definiert eine Auflistung von Membern (Eigenschaften und Methoden).</span><span class="sxs-lookup"><span data-stu-id="3da9f-191">`<MemberSet>`: Defines a collection of members (properties and methods).</span></span>

<span data-ttu-id="3da9f-192">Die `<MemberSet>` Tags werden innerhalb der primären `<Members>` Tags angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3da9f-192">The `<MemberSet>` tags appear within the primary `<Members>` tags.</span></span> <span data-ttu-id="3da9f-193">Die Tags müssen ein Tag umschließen `<Name>` , das den Namen des Element Satzes umschließt, und ein sekundäres `<Members>` Tag, das die Elemente (Eigenschaften und Methoden) in der Menge umschließt.</span><span class="sxs-lookup"><span data-stu-id="3da9f-193">The tags must enclose a `<Name>` tag surrounding the name of the member set and a secondary `<Members>` tag that surround the members (properties and methods) in the set.</span></span> <span data-ttu-id="3da9f-194">Alle Tags, die eine Eigenschaft (z. b. `<NoteProperty>` oder `<ScriptProperty>` ) oder eine Methode (z. b. `<Method>` oder) erstellen, `<ScriptMethod>` können Member der Menge sein.</span><span class="sxs-lookup"><span data-stu-id="3da9f-194">Any of the tags that create a property (such as `<NoteProperty>` or `<ScriptProperty>`) or a method (such as `<Method>` or `<ScriptMethod>`) can be members of the set.</span></span>

<span data-ttu-id="3da9f-195">In- `Types.ps1xml` Dateien wird das- `<MemberSet>` Tag verwendet, um die Standard Sichten der .NET-Objekte in PowerShell zu definieren.</span><span class="sxs-lookup"><span data-stu-id="3da9f-195">In `Types.ps1xml` files, the `<MemberSet>` tag is used to define the default views of the .NET objects in PowerShell.</span></span> <span data-ttu-id="3da9f-196">In diesem Fall ist der Name des Element Satzes (der Wert innerhalb der `<Name>` Tags) immer **psstandardmembers** , und die Namen der Eigenschaften (der Wert des `<Name>` Tags) sind eines der folgenden:</span><span class="sxs-lookup"><span data-stu-id="3da9f-196">In this case, the name of the member set (the value within the `<Name>` tags) is always **PsStandardMembers** , and the names of the properties (the value of the `<Name>` tag) are one of the following:</span></span>

- <span data-ttu-id="3da9f-197">`DefaultDisplayProperty`: Eine einzelne Eigenschaft eines Objekts.</span><span class="sxs-lookup"><span data-stu-id="3da9f-197">`DefaultDisplayProperty`: A single property of an object.</span></span>

- <span data-ttu-id="3da9f-198">`DefaultDisplayPropertySet`: Eine oder mehrere Eigenschaften eines Objekts.</span><span class="sxs-lookup"><span data-stu-id="3da9f-198">`DefaultDisplayPropertySet`: One or more properties of an object.</span></span>

- <span data-ttu-id="3da9f-199">`DefaultKeyPropertySet`: Eine oder mehrere Schlüsseleigenschaften eines Objekts.</span><span class="sxs-lookup"><span data-stu-id="3da9f-199">`DefaultKeyPropertySet`: One or more key properties of an object.</span></span> <span data-ttu-id="3da9f-200">Eine Schlüsseleigenschaft identifiziert Instanzen von Eigenschafts Werten, z. b. die ID-Anzahl von Elementen in einem Sitzungsverlauf.</span><span class="sxs-lookup"><span data-stu-id="3da9f-200">A key property identifies instances of property values, such as the ID number of items in a session history.</span></span>

<span data-ttu-id="3da9f-201">Der folgende XML-Code definiert z. b. die Standard Anzeige der Dienste (- `System.ServiceProcess.ServiceController` Objekte), die vom `Get-Service` Cmdlet zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="3da9f-201">For example, the following XML defines the default display of services (`System.ServiceProcess.ServiceController` objects) that are returned by the `Get-Service` cmdlet.</span></span> <span data-ttu-id="3da9f-202">Er definiert einen Member-Satz mit dem Namen " **psstandardmembers** ", der aus einem Standardeigenschaften Satz mit den Eigenschaften " **Status** ", " **Name** " und " **Display Name** " besteht.</span><span class="sxs-lookup"><span data-stu-id="3da9f-202">It defines a member set named **PsStandardMembers** that consists of a default property set with the **Status** , **Name** , and **DisplayName** properties.</span></span>

```xml
<Type>
  <Name>System.ServiceProcess.ServiceController</Name>
  <Members>
    <MemberSet>
      <Name>PSStandardMembers</Name>
      <Members>
        <PropertySet>
          <Name>DefaultDisplayPropertySet</Name>
          <ReferencedProperties>
            <Name>Status</Name>
            <Name>Name</Name>
            <Name>DisplayName</Name>
          </ReferencedProperties>
        </PropertySet>
      </Members>
    </MemberSet>
  </Members>
</Type>
```

<span data-ttu-id="3da9f-203">`<Method>`: Verweist auf eine native Methode des zugrunde liegenden-Objekts.</span><span class="sxs-lookup"><span data-stu-id="3da9f-203">`<Method>`: References a native method of the underlying object.</span></span>

<span data-ttu-id="3da9f-204">`<Methods>`: Eine Auflistung der Methoden des-Objekts.</span><span class="sxs-lookup"><span data-stu-id="3da9f-204">`<Methods>`: A collection of the methods of the object.</span></span>

<span data-ttu-id="3da9f-205">`<NoteProperty>`: Definiert eine Eigenschaft mit einem statischen Wert.</span><span class="sxs-lookup"><span data-stu-id="3da9f-205">`<NoteProperty>`: Defines a property with a static value.</span></span>

<span data-ttu-id="3da9f-206">Das `<NoteProperty>` -Tag muss über ein `<Name>` -Tag verfügen, das den Namen der neuen Eigenschaft und ein `<Value>` Tag angibt, das den Wert der-Eigenschaft angibt.</span><span class="sxs-lookup"><span data-stu-id="3da9f-206">The `<NoteProperty>` tag must have a `<Name>` tag that specifies the name of the new property and a `<Value>` tag that specifies the value of the property.</span></span>

<span data-ttu-id="3da9f-207">Der folgende XML-Code erstellt z. b. eine **Status** Eigenschaft für **System. IO. directoriyinfo** -Objekte.</span><span class="sxs-lookup"><span data-stu-id="3da9f-207">For example, the following XML creates a **Status** property for **System.IO.DirectoryInfo** objects.</span></span> <span data-ttu-id="3da9f-208">Der Wert der **Status** -Eigenschaft lautet immer **erfolgreich**.</span><span class="sxs-lookup"><span data-stu-id="3da9f-208">The value of the **Status** property is always **Success**.</span></span>

```xml
<Type>
  <Name>System.IO.DirectoryInfo</Name>
  <Members>
    <NoteProperty>
      <Name>Status</Name>
      <Value>Success</Value>
    </NoteProperty>
  </Members>
</Type>
```

<span data-ttu-id="3da9f-209">`<ParameterizedProperty>`: Eigenschaften, die Argumente annehmen und einen Wert zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="3da9f-209">`<ParameterizedProperty>`: Properties that take arguments and return a value.</span></span>

<span data-ttu-id="3da9f-210">`<Properties>`: Eine Auflistung der Eigenschaften des-Objekts.</span><span class="sxs-lookup"><span data-stu-id="3da9f-210">`<Properties>`: A collection of the properties of the object.</span></span>

<span data-ttu-id="3da9f-211">`<Property>`: Eine Eigenschaft des Basis Objekts.</span><span class="sxs-lookup"><span data-stu-id="3da9f-211">`<Property>`: A property of the base object.</span></span>

<span data-ttu-id="3da9f-212">`<PropertySet>`: Definiert eine Auflistung von Eigenschaften des-Objekts.</span><span class="sxs-lookup"><span data-stu-id="3da9f-212">`<PropertySet>`: Defines a collection of properties of the object.</span></span>

<span data-ttu-id="3da9f-213">Das `<PropertySet>` -Tag muss über ein `<Name>` -Tag verfügen, das den Namen des Eigenschaften Satzes und ein `<ReferencedProperty>` Tag angibt, das die Eigenschaften angibt.</span><span class="sxs-lookup"><span data-stu-id="3da9f-213">The `<PropertySet>` tag must have a `<Name>` tag that specifies the name of the property set and a `<ReferencedProperty>` tag that specifies the properties.</span></span> <span data-ttu-id="3da9f-214">Die Namen der Eigenschaften werden in Tag eingeschlossen `<Name>` .</span><span class="sxs-lookup"><span data-stu-id="3da9f-214">The names of the properties are enclosed in `<Name>` tag.</span></span>

<span data-ttu-id="3da9f-215">In `Types.ps1xml` `<PropertySet>` werden Tags verwendet, um Gruppen von Eigenschaften für die Standard Anzeige eines Objekts zu definieren.</span><span class="sxs-lookup"><span data-stu-id="3da9f-215">In `Types.ps1xml`, `<PropertySet>` tags are used to define sets of properties for the default display of an object.</span></span> <span data-ttu-id="3da9f-216">Sie können die Standard anzeigen durch den Wert **psstandardmembers** im `<Name>` Tag eines `<MemberSet>` Tags ermitteln.</span><span class="sxs-lookup"><span data-stu-id="3da9f-216">You can identify the default displays by the value **PsStandardMembers** in the `<Name>` tag of a `<MemberSet>` tag.</span></span>

<span data-ttu-id="3da9f-217">Der folgende XML-Code erstellt beispielsweise eine **Status** -Eigenschaft für das- `System.IO.DirectoryInfo` Objekt.</span><span class="sxs-lookup"><span data-stu-id="3da9f-217">For example, the following XML creates a **Status** property for the `System.IO.DirectoryInfo` object.</span></span> <span data-ttu-id="3da9f-218">Der Wert der **Status** -Eigenschaft lautet immer **erfolgreich**.</span><span class="sxs-lookup"><span data-stu-id="3da9f-218">The value of the **Status** property is always **Success**.</span></span>

```xml
<Type>
  <Name>System.ServiceProcess.ServiceController</Name>
  <Members>
    <MemberSet>
      <Name>PSStandardMembers</Name>
      <Members>
        <PropertySet>
          <Name>DefaultDisplayPropertySet</Name>
          <ReferencedProperties>
            <Name>Status</Name>
            <Name>Name</Name>
            <Name>DisplayName</Name>
          </ReferencedProperties>
        </PropertySet>
      </Members>
    </MemberSet>
  </Members>
</Type>
```

<span data-ttu-id="3da9f-219">`<ScriptMethod>`: Definiert eine Methode, deren Wert die Ausgabe eines Skripts ist.</span><span class="sxs-lookup"><span data-stu-id="3da9f-219">`<ScriptMethod>`: Defines a method whose value is the output of a script.</span></span>

<span data-ttu-id="3da9f-220">Das `<ScriptMethod>` -Tag muss über ein `<Name>` -Tag verfügen, das den Namen der neuen Methode und ein `<Script>` Tag, das den Skriptblock einschließt, der das Methoden Ergebnis zurückgibt, angibt.</span><span class="sxs-lookup"><span data-stu-id="3da9f-220">The `<ScriptMethod>` tag must have a `<Name>` tag that specifies the name of the new method and a `<Script>` tag that encloses the script block that returns the method result.</span></span>

<span data-ttu-id="3da9f-221">Die `ConvertToDateTime` -Methode und die- `ConvertFromDateTime` Methode von Management Objects () sind z. b `System.System.Management.ManagementObject` . Skript Methoden, die die `ToDateTime` statischen Methoden und der- `ToDmtfDateTime` Klasse verwenden `System.Management.ManagementDateTimeConverter` .</span><span class="sxs-lookup"><span data-stu-id="3da9f-221">For example, the `ConvertToDateTime` and `ConvertFromDateTime` methods of management objects (`System.System.Management.ManagementObject`) are script methods that use the `ToDateTime` and `ToDmtfDateTime` static methods of the `System.Management.ManagementDateTimeConverter` class.</span></span>

```xml
<Type>
 <Name>System.Management.ManagementObject</Name>
 <Members>
 <ScriptMethod>
   <Name>ConvertToDateTime</Name>
   <Script>
   [System.Management.ManagementDateTimeConverter]::ToDateTime($args[0])
   </Script>
 </ScriptMethod>
 <ScriptMethod>
   <Name>ConvertFromDateTime</Name>
   <Script>
   [System.Management.ManagementDateTimeConverter]::ToDmtfDateTime($args[0])
   </Script>
 </ScriptMethod>
 </Members>
</Type>
```

<span data-ttu-id="3da9f-222">`<ScriptProperty>`: Definiert eine Eigenschaft, deren Wert die Ausgabe eines Skripts ist.</span><span class="sxs-lookup"><span data-stu-id="3da9f-222">`<ScriptProperty>`: Defines a property whose value is the output of a script.</span></span>

<span data-ttu-id="3da9f-223">Das `<ScriptProperty>` -Tag muss über ein `<Name>` -Tag verfügen, das den Namen der neuen Eigenschaft und ein Tag angibt, das `<GetScriptBlock>` den Skriptblock einschließt, der den Eigenschafts Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="3da9f-223">The `<ScriptProperty>` tag must have a `<Name>` tag that specifies the name of the new property and a `<GetScriptBlock>` tag that encloses the script block that returns the property value.</span></span>

<span data-ttu-id="3da9f-224">Beispielsweise ist die **VERSIONINFO** -Eigenschaft des **System. IO. FileInfo** -Objekts eine Skript Eigenschaft, die sich aus der Verwendung der **FullName** -Eigenschaft der statischen **GetVersionInfo** -Methode der **System. Diagnostics. FileVersionInfo** -Objekte ergibt.</span><span class="sxs-lookup"><span data-stu-id="3da9f-224">For example, the **VersionInfo** property of the **System.IO.FileInfo** object is a script property that results from using the **FullName** property of the **GetVersionInfo** static method of **System.Diagnostics.FileVersionInfo** objects.</span></span>

```xml
<Type>
  <Name>System.IO.FileInfo</Name>
  <Members>
    <ScriptProperty>
      <Name>VersionInfo</Name>
      <GetScriptBlock>
      [System.Diagnostics.FileVersionInfo]::GetVersionInfo($this.FullName)
      </GetScriptBlock>
    </ScriptProperty>
  </Members>
</Type>
```

<span data-ttu-id="3da9f-225">Weitere Informationen finden Sie im [Windows PowerShell Software Development Kit (SDK)](/powershell/scripting/developer/windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="3da9f-225">For more information, see the [Windows PowerShell Software Development Kit (SDK)](/powershell/scripting/developer/windows-powershell).</span></span>

## <a name="update-typedata"></a><span data-ttu-id="3da9f-226">Update-TypeData</span><span class="sxs-lookup"><span data-stu-id="3da9f-226">Update-TypeData</span></span>

<span data-ttu-id="3da9f-227">`Types.ps1xml`Führen Sie das-Cmdlet aus, um die Dateien in eine PowerShell-Sitzung zu laden `Update-TypeData` .</span><span class="sxs-lookup"><span data-stu-id="3da9f-227">To load your `Types.ps1xml` files into a PowerShell session, run the `Update-TypeData` cmdlet.</span></span> <span data-ttu-id="3da9f-228">Wenn Sie möchten, dass die Typen in der Datei Vorrang vor Typen in der integrierten `Types.ps1xml` Datei haben, fügen Sie den **prepddata** -Parameter von hinzu `Update-TypeData` .</span><span class="sxs-lookup"><span data-stu-id="3da9f-228">If you want the types in your file to take precedence over types in the built-in `Types.ps1xml` file, add the **PrependData** parameter of `Update-TypeData`.</span></span> <span data-ttu-id="3da9f-229">`Update-TypeData` wirkt sich nur auf die aktuelle Sitzung aus.</span><span class="sxs-lookup"><span data-stu-id="3da9f-229">`Update-TypeData` affects only the current session.</span></span> <span data-ttu-id="3da9f-230">Um die Änderung an allen zukünftigen Sitzungen vorzunehmen, exportieren Sie die Sitzung, oder fügen Sie den `Update-TypeData` Befehl zu Ihrem PowerShell-Profil hinzu.</span><span class="sxs-lookup"><span data-stu-id="3da9f-230">To make the change to all future sessions, export the session, or add the `Update-TypeData` command to your PowerShell profile.</span></span>

<span data-ttu-id="3da9f-231">Ausnahmen, die in Eigenschaften auftreten, oder das Hinzufügen von Eigenschaften zu einem `Update-TypeData` Befehl, melden keine Fehler an `StdErr` .</span><span class="sxs-lookup"><span data-stu-id="3da9f-231">Exceptions that occur in properties, or from adding properties to an `Update-TypeData` command, do not report errors to `StdErr`.</span></span> <span data-ttu-id="3da9f-232">Dadurch werden Ausnahmen unterdrückt, die während der Formatierung und Ausgabe in vielen gängigen Typen auftreten würden.</span><span class="sxs-lookup"><span data-stu-id="3da9f-232">This is to suppress exceptions that would occur in many common types during formatting and outputting.</span></span> <span data-ttu-id="3da9f-233">Wenn Sie .net-Eigenschaften erhalten, können Sie die Unterdrückung von Ausnahmen umgehen, indem Sie stattdessen die Methoden Syntax verwenden, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="3da9f-233">If you are getting .NET properties, you can work around the suppression of exceptions by using method syntax instead, as shown in the following example:</span></span>

```powershell
"hello".get_Length()
```

<span data-ttu-id="3da9f-234">Beachten Sie, dass die Methoden Syntax nur mit .net-Eigenschaften verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="3da9f-234">Note that method syntax can only be used with .NET properties.</span></span> <span data-ttu-id="3da9f-235">Eigenschaften, die durch das Ausführen des `Update-TypeData` Cmdlets hinzugefügt werden, können keine Methoden Syntax verwenden.</span><span class="sxs-lookup"><span data-stu-id="3da9f-235">Properties that are added by running the `Update-TypeData` cmdlet cannot use method syntax.</span></span>

## <a name="signing-a-typesps1xml-file"></a><span data-ttu-id="3da9f-236">Signieren einer Types.ps1-XML-Datei</span><span class="sxs-lookup"><span data-stu-id="3da9f-236">Signing a Types.ps1xml file</span></span>

<span data-ttu-id="3da9f-237">Um Benutzer Ihrer Datei zu schützen `Types.ps1xml` , können Sie die Datei mit einer digitalen Signatur signieren.</span><span class="sxs-lookup"><span data-stu-id="3da9f-237">To protect users of your `Types.ps1xml` file, you can sign the file using a digital signature.</span></span> <span data-ttu-id="3da9f-238">Weitere Informationen finden Sie unter [about_Signing](about_Signing.md).</span><span class="sxs-lookup"><span data-stu-id="3da9f-238">For more information, see [about_Signing](about_Signing.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3da9f-239">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="3da9f-239">See also</span></span>

[<span data-ttu-id="3da9f-240">about_Signing</span><span class="sxs-lookup"><span data-stu-id="3da9f-240">about_Signing</span></span>](about_Signing.md)

[<span data-ttu-id="3da9f-241">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="3da9f-241">Copy-Item</span></span>](xref:Microsoft.PowerShell.Management.Copy-Item)

[<span data-ttu-id="3da9f-242">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="3da9f-242">Copy-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Copy-ItemProperty)

[<span data-ttu-id="3da9f-243">Get-Member</span><span class="sxs-lookup"><span data-stu-id="3da9f-243">Get-Member</span></span>](xref:Microsoft.PowerShell.Utility.Get-Member)

[<span data-ttu-id="3da9f-244">Get-TypeData</span><span class="sxs-lookup"><span data-stu-id="3da9f-244">Get-TypeData</span></span>](xref:Microsoft.PowerShell.Utility.Get-TypeData)

[<span data-ttu-id="3da9f-245">Remove-TypeData</span><span class="sxs-lookup"><span data-stu-id="3da9f-245">Remove-TypeData</span></span>](xref:Microsoft.PowerShell.Utility.Remove-TypeData)

[<span data-ttu-id="3da9f-246">Update-TypeData</span><span class="sxs-lookup"><span data-stu-id="3da9f-246">Update-TypeData</span></span>](xref:Microsoft.PowerShell.Utility.Update-TypeData)

