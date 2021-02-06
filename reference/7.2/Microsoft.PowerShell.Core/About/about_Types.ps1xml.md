---
description: Erläutert `Types.ps1xml` die Verwendung von Dateien zum Erweitern der Objekttypen, die in PowerShell verwendet werden.
Locale: en-US
ms.date: 04/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_types.ps1xml?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Types.ps1xml
ms.openlocfilehash: 9a87394631d3318f3fb3f4b2a0cb2ab8d25408d0
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600489"
---
# <a name="about-typesps1xml"></a><span data-ttu-id="b77a5-103">Informationen zu Types.ps1XML</span><span class="sxs-lookup"><span data-stu-id="b77a5-103">About Types.ps1xml</span></span>

## <a name="short-description"></a><span data-ttu-id="b77a5-104">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b77a5-104">Short description</span></span>
<span data-ttu-id="b77a5-105">Erläutert `Types.ps1xml` die Verwendung von Dateien zum Erweitern der Objekttypen, die in PowerShell verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b77a5-105">Explains how to use `Types.ps1xml` files to extend the types of objects that are used in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="b77a5-106">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b77a5-106">Long description</span></span>

<span data-ttu-id="b77a5-107">Erweiterte Typdaten definieren zusätzliche Eigenschaften und Methoden ("Member") von Objekttypen in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b77a5-107">Extended type data defines additional properties and methods ("members") of object types in PowerShell.</span></span> <span data-ttu-id="b77a5-108">Es gibt zwei Verfahren zum Hinzufügen von erweiterten Typdaten zu einer PowerShell-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="b77a5-108">There are two techniques for adding extended type data to a PowerShell session.</span></span>

- <span data-ttu-id="b77a5-109">`Types.ps1xml` file: eine XML-Datei, die erweiterte Typdaten definiert.</span><span class="sxs-lookup"><span data-stu-id="b77a5-109">`Types.ps1xml` file: An XML file that defines extended type data.</span></span>
- <span data-ttu-id="b77a5-110">`Update-TypeData`: Ein Cmdlet, das Dateien erneut lädt `Types.ps1xml` und erweiterte Daten für Typen in der aktuellen Sitzung definiert.</span><span class="sxs-lookup"><span data-stu-id="b77a5-110">`Update-TypeData`: A cmdlet that reloads `Types.ps1xml` files and defines extended data for types in the current session.</span></span>

<span data-ttu-id="b77a5-111">In diesem Thema werden- `Types.ps1xml` Dateien beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b77a5-111">This topic describes `Types.ps1xml` files.</span></span> <span data-ttu-id="b77a5-112">Weitere Informationen zur Verwendung des `Update-TypeData` Cmdlets, um der aktuellen Sitzung dynamische erweiterte Typdaten hinzuzufügen, finden Sie unter [Update-typedata](xref:Microsoft.PowerShell.Utility.Update-TypeData).</span><span class="sxs-lookup"><span data-stu-id="b77a5-112">For more information about using the `Update-TypeData` cmdlet to add dynamic extended type data to the current session see [Update-TypeData](xref:Microsoft.PowerShell.Utility.Update-TypeData).</span></span>

## <a name="about-extended-type-data"></a><span data-ttu-id="b77a5-113">Informationen zu erweiterten Typdaten</span><span class="sxs-lookup"><span data-stu-id="b77a5-113">About extended type data</span></span>

<span data-ttu-id="b77a5-114">Erweiterte Typdaten definieren zusätzliche Eigenschaften und Methoden ("Member") von Objekttypen in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b77a5-114">Extended type data defines additional properties and methods ("members") of object types in PowerShell.</span></span> <span data-ttu-id="b77a5-115">Sie können jeden von PowerShell unterstützten Typ erweitern und die hinzugefügten Eigenschaften und Methoden auf die gleiche Weise verwenden, wie Sie die Eigenschaften verwenden, die für die Objekttypen definiert sind.</span><span class="sxs-lookup"><span data-stu-id="b77a5-115">You can extend any type that is supported by PowerShell and use the added properties and methods in the same way that you use the properties that are defined on the object types.</span></span>

<span data-ttu-id="b77a5-116">Beispielsweise fügt PowerShell allen  `System.DateTime` Objekten, wie z. b. den vom Cmdlet zurückgegebenen Objekten, eine DateTime-Eigenschaft hinzu `Get-Date` .</span><span class="sxs-lookup"><span data-stu-id="b77a5-116">For example, PowerShell adds a **DateTime** property to all `System.DateTime` objects, such as the ones that the `Get-Date` cmdlet returns.</span></span>

```powershell
(Get-Date).DateTime
```

```Output
Sunday, January 29, 2012 9:43:57 AM
```

<span data-ttu-id="b77a5-117">Die **DateTime** -Eigenschaft wird in der Beschreibung der [System. DateTime](/dotnet/api/system.datetime) -Struktur nicht gefunden, da die Eigenschaft von PowerShell hinzugefügt wird und nur in PowerShell sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="b77a5-117">You won't find the **DateTime** property in the description of the [System.DateTime](/dotnet/api/system.datetime) structure, because PowerShell adds the property and it is visible only in PowerShell.</span></span>

<span data-ttu-id="b77a5-118">PowerShell definiert intern einen Standardsatz erweiterter Typen.</span><span class="sxs-lookup"><span data-stu-id="b77a5-118">PowerShell internally defines a default set of extended types.</span></span> <span data-ttu-id="b77a5-119">Diese Typinformationen werden beim Start in jede PowerShell-Sitzung geladen.</span><span class="sxs-lookup"><span data-stu-id="b77a5-119">This type information is loaded in every PowerShell session at startup.</span></span> <span data-ttu-id="b77a5-120">Die **DateTime** -Eigenschaft ist Teil dieses Standardsatzes.</span><span class="sxs-lookup"><span data-stu-id="b77a5-120">The **DateTime** property is part of this default set.</span></span> <span data-ttu-id="b77a5-121">Vor PowerShell 6 wurden die Typdefinitionen `Types.ps1xml` im PowerShell-Installationsverzeichnis ( `$PSHOME` ) gespeichert.</span><span class="sxs-lookup"><span data-stu-id="b77a5-121">Prior to PowerShell 6, the type definitions were stored the `Types.ps1xml` file in the PowerShell installation directory (`$PSHOME`).</span></span>

## <a name="adding-extended-type-data-to-powershell"></a><span data-ttu-id="b77a5-122">Hinzufügen von erweiterten Typdaten zu PowerShell</span><span class="sxs-lookup"><span data-stu-id="b77a5-122">Adding extended type data to PowerShell</span></span>

<span data-ttu-id="b77a5-123">Es gibt drei Quellen für erweiterte Typdaten in PowerShell-Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="b77a5-123">There are three sources of extended type data in PowerShell sessions.</span></span>

- <span data-ttu-id="b77a5-124">Der von PowerShell definierte und wird automatisch in jede PowerShell-Sitzung geladen.</span><span class="sxs-lookup"><span data-stu-id="b77a5-124">The defined by PowerShell and is loaded automatically into every PowerShell session.</span></span> <span data-ttu-id="b77a5-125">Ab PowerShell 6 werden diese Informationen in PowerShell kompiliert und sind nicht mehr in einer `Types.ps1xml` Datei enthalten.</span><span class="sxs-lookup"><span data-stu-id="b77a5-125">Beginning with PowerShell 6, this information is compiled into PowerShell and is no longer shipped in a `Types.ps1xml` file.</span></span>

- <span data-ttu-id="b77a5-126">Die `Types.ps1xml` Dateien, die Module exportieren, werden geladen, wenn das Modul in die aktuelle Sitzung importiert wird.</span><span class="sxs-lookup"><span data-stu-id="b77a5-126">The `Types.ps1xml` files that modules export are loaded when the module is imported into the current session.</span></span>

- <span data-ttu-id="b77a5-127">Erweiterte Typdaten, die mithilfe des-Cmdlets definiert werden, werden `Update-TypeData` nur zur aktuellen Sitzung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b77a5-127">Extended type data that is defined by using the `Update-TypeData` cmdlet is added only to the current session.</span></span> <span data-ttu-id="b77a5-128">Er wird nicht in einer Datei gespeichert.</span><span class="sxs-lookup"><span data-stu-id="b77a5-128">It is not saved in a file.</span></span>

<span data-ttu-id="b77a5-129">In der Sitzung werden die erweiterten Typdaten aus den drei Quellen auf die gleiche Weise auf-Objekte angewendet und sind für alle Objekte der angegebenen Typen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b77a5-129">In the session, the extended type data from the three sources is applied to objects in the same way and is available on all objects of the specified types.</span></span>

## <a name="the-typedata-cmdlets"></a><span data-ttu-id="b77a5-130">Die typedata-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="b77a5-130">The TypeData cmdlets</span></span>

<span data-ttu-id="b77a5-131">Die folgenden Cmdlets sind im **Microsoft. PowerShell. Utility** -Modul in PowerShell 3,0 und höher enthalten.</span><span class="sxs-lookup"><span data-stu-id="b77a5-131">The following cmdlets are included in the **Microsoft.PowerShell.Utility** module in PowerShell 3.0 and later.</span></span>

- <span data-ttu-id="b77a5-132">`Get-TypeData`: Ruft erweiterte Typdaten in der aktuellen Sitzung ab.</span><span class="sxs-lookup"><span data-stu-id="b77a5-132">`Get-TypeData`: Gets extended type data in the current session.</span></span>
- <span data-ttu-id="b77a5-133">`Update-TypeData`: Lädt `Types.ps1xml` Dateien erneut.</span><span class="sxs-lookup"><span data-stu-id="b77a5-133">`Update-TypeData`: Reloads `Types.ps1xml` files.</span></span> <span data-ttu-id="b77a5-134">Fügt der aktuellen Sitzung erweiterte Typdaten hinzu.</span><span class="sxs-lookup"><span data-stu-id="b77a5-134">Adds extended type data to the current session.</span></span>
- <span data-ttu-id="b77a5-135">`Remove-TypeData`: Entfernt erweiterte Typdaten aus der aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="b77a5-135">`Remove-TypeData`: Removes extended type data from the current session.</span></span>

<span data-ttu-id="b77a5-136">Weitere Informationen zu diesen Cmdlets finden Sie im Hilfethema für jedes Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b77a5-136">For more information about these cmdlets, see the help topic for each cmdlet.</span></span>

## <a name="built-in-typesps1xml-files"></a><span data-ttu-id="b77a5-137">Integrierte Types.ps1XML-Dateien</span><span class="sxs-lookup"><span data-stu-id="b77a5-137">Built-in Types.ps1xml files</span></span>

<span data-ttu-id="b77a5-138">Die `Types.ps1xml` Dateien im `$PSHOME` Verzeichnis werden jeder Sitzung automatisch hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b77a5-138">The `Types.ps1xml` files in the `$PSHOME` directory are added automatically to every session.</span></span>

<span data-ttu-id="b77a5-139">`Types.ps1xml`Bei der Datei im PowerShell-Installationsverzeichnis ( `$PSHOME` ) handelt es sich um eine XML-basierte Textdatei, mit der Sie den Objekten, die in PowerShell verwendet werden, Eigenschaften und Methoden hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="b77a5-139">The `Types.ps1xml` file in the PowerShell installation directory (`$PSHOME`) is an XML-based text file that lets you add properties and methods to the objects that are used in PowerShell.</span></span> <span data-ttu-id="b77a5-140">PowerShell verfügt über integrierte Dateien, die `Types.ps1xml` den .NET-Typen mehrere Elemente hinzufügen. Sie können jedoch zusätzliche `Types.ps1xml` Dateien erstellen, um die Typen weiter zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="b77a5-140">PowerShell has built-in `Types.ps1xml` files that add several elements to the .NET types, but you can create additional `Types.ps1xml` files to further extend the types.</span></span>

<span data-ttu-id="b77a5-141">Standardmäßig verfügen Array Objekte ( `System.Array` ) z. b. über eine **length** -Eigenschaft, die die Anzahl der Objekte im Array auflistet.</span><span class="sxs-lookup"><span data-stu-id="b77a5-141">For example, by default, array objects (`System.Array`) have a **Length** property that lists the number of objects in the array.</span></span> <span data-ttu-id="b77a5-142">Da die Name- **Länge** die Eigenschaft jedoch nicht eindeutig beschreibt, fügt PowerShell eine Alias Eigenschaft mit dem Namen **count** hinzu, die denselben Wert anzeigt.</span><span class="sxs-lookup"><span data-stu-id="b77a5-142">However, because the name **Length** does not clearly describe the property, PowerShell adds an alias property named **Count** that displays the same value.</span></span> <span data-ttu-id="b77a5-143">Im folgenden XML-Code wird die **count** -Eigenschaft zum-Typ hinzugefügt `System.Array` .</span><span class="sxs-lookup"><span data-stu-id="b77a5-143">The following XML adds the **Count** property to the `System.Array` type.</span></span>

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

<span data-ttu-id="b77a5-144">Um die neue **aliasproperty** zu erhalten, verwenden Sie einen `Get-Member` Befehl für ein beliebiges Array, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="b77a5-144">To get the new **AliasProperty**, use a `Get-Member` command on any array, as shown in the following example.</span></span>

```powershell
Get-Member -InputObject (1,2,3,4)
```

<span data-ttu-id="b77a5-145">Der Befehl gibt die folgenden Ergebnisse zurück.</span><span class="sxs-lookup"><span data-stu-id="b77a5-145">The command returns the following results.</span></span>

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

<span data-ttu-id="b77a5-146">Daher können Sie entweder die **count** -Eigenschaft oder die **length** -Eigenschaft von Arrays in PowerShell verwenden.</span><span class="sxs-lookup"><span data-stu-id="b77a5-146">As a result, you can use either the **Count** property or the **Length** property of arrays in PowerShell.</span></span> <span data-ttu-id="b77a5-147">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b77a5-147">For example:</span></span>

```powershell
(1, 2, 3, 4).count
4
```

```powershell
(1, 2, 3, 4).length
4
```

## <a name="creating-new-typesps1xml-files"></a><span data-ttu-id="b77a5-148">Erstellen neuer Types.ps1XML-Dateien</span><span class="sxs-lookup"><span data-stu-id="b77a5-148">Creating new Types.ps1xml files</span></span>

<span data-ttu-id="b77a5-149">Die `.ps1xml` mit PowerShell installierten Dateien sind digital signiert, um Manipulationen zu verhindern, da die Formatierung Skriptblöcke einschließen kann.</span><span class="sxs-lookup"><span data-stu-id="b77a5-149">The `.ps1xml` files that are installed with PowerShell are digitally signed to prevent tampering because the formatting can include script blocks.</span></span> <span data-ttu-id="b77a5-150">Wenn Sie also eine Eigenschaft oder Methode zu einem .NET-Typ hinzufügen möchten, erstellen Sie Ihre eigenen `Types.ps1xml` Dateien, und fügen Sie Sie dann der PowerShell-Sitzung hinzu.</span><span class="sxs-lookup"><span data-stu-id="b77a5-150">Therefore, to add a property or method to a .NET type, create your own `Types.ps1xml` files, and then add them to your PowerShell session.</span></span>

<span data-ttu-id="b77a5-151">Um eine neue Datei zu erstellen, kopieren Sie zunächst eine vorhandene `Types.ps1xml` Datei.</span><span class="sxs-lookup"><span data-stu-id="b77a5-151">To create a new file, start by copying an existing `Types.ps1xml` file.</span></span> <span data-ttu-id="b77a5-152">Die neue Datei kann einen beliebigen Namen haben, Sie muss jedoch eine `.ps1xml` Dateinamenerweiterung aufweisen.</span><span class="sxs-lookup"><span data-stu-id="b77a5-152">The new file can have any name, but it must have a `.ps1xml` file name extension.</span></span> <span data-ttu-id="b77a5-153">Sie können die neue Datei in einem beliebigen Verzeichnis platzieren, auf das PowerShell zugreifen kann, aber es ist hilfreich, die Dateien im PowerShell-Installationsverzeichnis ( `$PSHOME` ) oder in einem Unterverzeichnis des Installationsverzeichnisses zu platzieren.</span><span class="sxs-lookup"><span data-stu-id="b77a5-153">You can place the new file in any directory that is accessible to PowerShell, but it is useful to place the files in the PowerShell installation directory (`$PSHOME`) or in a subdirectory of the installation directory.</span></span>

<span data-ttu-id="b77a5-154">Wenn Sie die neue Datei gespeichert haben, verwenden Sie das `Update-TypeData` Cmdlet, um die neue Datei zur PowerShell-Sitzung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="b77a5-154">When you have saved the new file, use the `Update-TypeData` cmdlet to add the new file to your PowerShell session.</span></span> <span data-ttu-id="b77a5-155">Wenn Sie möchten, dass Ihre Typen Vorrang vor den integrierten Typen haben, die definiert sind, verwenden Sie den **prepddata** -Parameter des `Update-TypeData` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="b77a5-155">If you want your types to take precedence over the built-in types that are defined, use the **PrependData** parameter of the `Update-TypeData` cmdlet.</span></span> <span data-ttu-id="b77a5-156">`Update-TypeData` wirkt sich nur auf die aktuelle Sitzung aus.</span><span class="sxs-lookup"><span data-stu-id="b77a5-156">`Update-TypeData` affects only the current session.</span></span> <span data-ttu-id="b77a5-157">Um die Änderung an allen zukünftigen Sitzungen vorzunehmen, exportieren Sie die-Konsole, oder fügen Sie den `Update-TypeData` Befehl zu Ihrem PowerShell-Profil hinzu.</span><span class="sxs-lookup"><span data-stu-id="b77a5-157">To make the change to all future sessions, export the console, or add the `Update-TypeData` command to your PowerShell profile.</span></span>

## <a name="typesps1xml-and-add-member"></a><span data-ttu-id="b77a5-158">Types.ps1XML und Add-Member</span><span class="sxs-lookup"><span data-stu-id="b77a5-158">Types.ps1xml and Add-Member</span></span>

<span data-ttu-id="b77a5-159">Die `Types.ps1xml` Dateien fügen Eigenschaften und Methoden zu allen Instanzen der Objekte des angegebenen .net-Typs in der betroffenen PowerShell-Sitzung hinzu.</span><span class="sxs-lookup"><span data-stu-id="b77a5-159">The `Types.ps1xml` files add properties and methods to all the instances of the objects of the specified .NET type in the affected PowerShell session.</span></span> <span data-ttu-id="b77a5-160">Wenn Sie jedoch nur einer Instanz eines Objekts Eigenschaften oder Methoden hinzufügen müssen, verwenden Sie das- `Add-Member` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b77a5-160">However, if you need to add properties or methods only to one instance of an object, use the `Add-Member` cmdlet.</span></span>

<span data-ttu-id="b77a5-161">Weitere Informationen finden Sie unter [Add-Member](xref:Microsoft.PowerShell.Utility.Add-Member).</span><span class="sxs-lookup"><span data-stu-id="b77a5-161">For more information, see [Add-Member](xref:Microsoft.PowerShell.Utility.Add-Member).</span></span>

## <a name="example-adding-an-age-member-to-fileinfo-objects"></a><span data-ttu-id="b77a5-162">Beispiel: Hinzufügen eines Age-Members zu filinput Info-Objekten</span><span class="sxs-lookup"><span data-stu-id="b77a5-162">Example: Adding an Age member to FileInfo objects</span></span>

<span data-ttu-id="b77a5-163">Dieses Beispiel zeigt, wie Sie **System. IO. filinput Info** -Objekten eine **Age** -Eigenschaft hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b77a5-163">This example shows how to add an **Age** property to **System.IO.FileInfo** objects.</span></span> <span data-ttu-id="b77a5-164">Das Alter einer Datei ist der Unterschied zwischen der Erstellungszeit und der aktuellen Zeit (in Tagen).</span><span class="sxs-lookup"><span data-stu-id="b77a5-164">The age of a file is the difference between its creation time and the current time in days.</span></span>

<span data-ttu-id="b77a5-165">Da die **Age** -Eigenschaft mit einem Skriptblock berechnet wird, suchen Sie `<ScriptProperty>` nach einem Tag, das als Modell für die neue **Age** -Eigenschaft verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="b77a5-165">Because the **Age** property is calculated by using a script block, find a `<ScriptProperty>` tag to use as a model for the new **Age** property.</span></span>

<span data-ttu-id="b77a5-166">Speichern Sie den folgenden XML-Code in der Datei `$PSHOME\MyTypes.ps1xml` .</span><span class="sxs-lookup"><span data-stu-id="b77a5-166">Save the follow XML code to the file `$PSHOME\MyTypes.ps1xml`.</span></span>

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

<span data-ttu-id="b77a5-167">Führen Sie aus `Update-TypeData` , um die neue `Types.ps1xml` Datei zur aktuellen Sitzung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="b77a5-167">Run `Update-TypeData` to add the new `Types.ps1xml` file to the current session.</span></span> <span data-ttu-id="b77a5-168">Der Befehl verwendet den **prepddata** -Parameter, um die neue Datei in einer Rangfolge zu platzieren, die höher als die ursprünglichen Definitionen ist.</span><span class="sxs-lookup"><span data-stu-id="b77a5-168">The command uses the **PrependData** parameter to place the new file in a precedence order higher than the original definitions.</span></span>

<span data-ttu-id="b77a5-169">Weitere Informationen zu `Update-TypeData` finden Sie unter [Update-typedata](xref:Microsoft.PowerShell.Utility.Update-TypeData).</span><span class="sxs-lookup"><span data-stu-id="b77a5-169">For more information about `Update-TypeData`, see [Update-TypeData](xref:Microsoft.PowerShell.Utility.Update-TypeData).</span></span>

```powershell
Update-Typedata -PrependPath $PSHOME\MyTypes.ps1xml
```

<span data-ttu-id="b77a5-170">Um die Änderung zu testen, führen Sie einen `Get-ChildItem` Befehl aus, um die PowerShell.exe-Datei im Verzeichnis zu erhalten `$PSHOME` , und übergeben Sie die Datei dann an das `Format-List` Cmdlet, um alle Eigenschaften der Datei aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="b77a5-170">To test the change, run a `Get-ChildItem` command to get the PowerShell.exe file in the `$PSHOME` directory, and then pipe the file to the `Format-List` cmdlet to list all of the properties of the file.</span></span> <span data-ttu-id="b77a5-171">Aufgrund der Änderung wird die **Age** -Eigenschaft in der Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b77a5-171">As a result of the change, the **Age** property appears in the list.</span></span>

```powershell
Get-ChildItem $PSHOME\pwsh.exe | Select-Object Age
```

```Output
142
```

## <a name="the-xml-in-typesps1xml-files"></a><span data-ttu-id="b77a5-172">Der XML-Code in Types.ps1XML-Dateien</span><span class="sxs-lookup"><span data-stu-id="b77a5-172">The XML in Types.ps1xml files</span></span>

<span data-ttu-id="b77a5-173">Die vollständige Schema Definition finden Sie in der Datei " [types. xsd](https://github.com/PowerShell/PowerShell/blob/master/src/Schemas/Types.xsd) " im PowerShell-Quellcoderepository auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="b77a5-173">The full schema definition can be found in [Types.xsd](https://github.com/PowerShell/PowerShell/blob/master/src/Schemas/Types.xsd) in the PowerShell source code repository on GitHub.</span></span>

<span data-ttu-id="b77a5-174">Das- `<Types>` Tag schließt alle Typen ein, die in der Datei definiert sind.</span><span class="sxs-lookup"><span data-stu-id="b77a5-174">The `<Types>` tag encloses all of the types that are defined in the file.</span></span> <span data-ttu-id="b77a5-175">Es darf nur ein Tag vorhanden sein `<Types>` .</span><span class="sxs-lookup"><span data-stu-id="b77a5-175">There should be only one `<Types>` tag.</span></span>

<span data-ttu-id="b77a5-176">Jeder in der Datei erwähnte .NET-Typ sollte durch ein- `<Type>` Tag dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="b77a5-176">Each .NET type mentioned in the file should be represented by a `<Type>` tag.</span></span>

<span data-ttu-id="b77a5-177">Die typtags müssen die folgenden Tags enthalten:</span><span class="sxs-lookup"><span data-stu-id="b77a5-177">The type tags must contain the following tags:</span></span>

<span data-ttu-id="b77a5-178">`<Name>`: Enschließt den Namen des betroffenen .net-Typs.</span><span class="sxs-lookup"><span data-stu-id="b77a5-178">`<Name>`: Encloses the name of the affected .NET type.</span></span>

<span data-ttu-id="b77a5-179">`<Members>`: Schließt die Tags für die neuen Eigenschaften und Methoden ein, die für den .NET-Typ definiert sind.</span><span class="sxs-lookup"><span data-stu-id="b77a5-179">`<Members>`: Encloses the tags for the new properties and methods that are defined for the .NET type.</span></span>

<span data-ttu-id="b77a5-180">Jedes der folgenden Member-Tags kann sich im- `<Members>` Tag befinden.</span><span class="sxs-lookup"><span data-stu-id="b77a5-180">Any of the following member tags can be inside the `<Members>` tag.</span></span>

<span data-ttu-id="b77a5-181">`<AliasProperty>`: Definiert einen neuen Namen für eine vorhandene Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="b77a5-181">`<AliasProperty>`: Defines a new name for an existing property.</span></span>

<span data-ttu-id="b77a5-182">Das `<AliasProperty>` -Tag muss über ein `<Name>` -Tag verfügen, das den Namen der neuen Eigenschaft und ein `<ReferencedMemberName>` Tag angibt, das die vorhandene Eigenschaft angibt.</span><span class="sxs-lookup"><span data-stu-id="b77a5-182">The `<AliasProperty>` tag must have a `<Name>` tag that specifies the name of the new property and a `<ReferencedMemberName>` tag that specifies the existing property.</span></span>

<span data-ttu-id="b77a5-183">Beispielsweise ist die **count** -Alias Eigenschaft ein Alias für die **length** -Eigenschaft von Array-Objekten.</span><span class="sxs-lookup"><span data-stu-id="b77a5-183">For example, the **Count** alias property is an alias for the **Length** property of array objects.</span></span>

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

<span data-ttu-id="b77a5-184">`<CodeMethod>`: Verweist auf eine statische Methode einer .NET-Klasse.</span><span class="sxs-lookup"><span data-stu-id="b77a5-184">`<CodeMethod>`:  References a static method of a .NET class.</span></span>

<span data-ttu-id="b77a5-185">Das `<CodeMethod>` -Tag muss über ein `<Name>` -Tag verfügen, das den Namen der neuen Methode und ein `<GetCodeReference>` Tag angibt, das den Code angibt, in dem die Methode definiert ist.</span><span class="sxs-lookup"><span data-stu-id="b77a5-185">The `<CodeMethod>` tag must have a `<Name>` tag that specifies the name of the new method and a `<GetCodeReference>` tag that specifies the code in which the method is defined.</span></span>

<span data-ttu-id="b77a5-186">Beispielsweise ist die **Mode** -Eigenschaft von- `System.IO.DirectoryInfo` Objekten eine im PowerShell-Dateisystem Anbieter definierte Code Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="b77a5-186">For example, the **Mode** property of `System.IO.DirectoryInfo` objects is a code property defined in the PowerShell FileSystem provider.</span></span>

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

<span data-ttu-id="b77a5-187">`<CodeProperty>`: Verweist auf eine statische Methode einer .NET-Klasse.</span><span class="sxs-lookup"><span data-stu-id="b77a5-187">`<CodeProperty>`: References a static method of a .NET class.</span></span>

<span data-ttu-id="b77a5-188">Das `<CodeProperty>` -Tag muss über ein `<Name>` -Tag verfügen, das den Namen der neuen Eigenschaft und ein `<GetCodeReference>` Tag angibt, das den Code angibt, in dem die Eigenschaft definiert ist.</span><span class="sxs-lookup"><span data-stu-id="b77a5-188">The `<CodeProperty>` tag must have a `<Name>` tag that specifies the name of the new property and a `<GetCodeReference>` tag that specifies the code in which the property is defined.</span></span>

<span data-ttu-id="b77a5-189">Beispielsweise ist die **Mode** -Eigenschaft von- `System.IO.DirectoryInfo` Objekten eine im PowerShell-Dateisystem Anbieter definierte Code Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="b77a5-189">For example, the **Mode** property of `System.IO.DirectoryInfo` objects is a code property defined in the PowerShell FileSystem provider.</span></span>

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

<span data-ttu-id="b77a5-190">`<MemberSet>`: Definiert eine Auflistung von Membern (Eigenschaften und Methoden).</span><span class="sxs-lookup"><span data-stu-id="b77a5-190">`<MemberSet>`: Defines a collection of members (properties and methods).</span></span>

<span data-ttu-id="b77a5-191">Die `<MemberSet>` Tags werden innerhalb der primären `<Members>` Tags angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b77a5-191">The `<MemberSet>` tags appear within the primary `<Members>` tags.</span></span> <span data-ttu-id="b77a5-192">Die Tags müssen ein Tag umschließen `<Name>` , das den Namen des Element Satzes umschließt, und ein sekundäres `<Members>` Tag, das die Elemente (Eigenschaften und Methoden) in der Menge umschließt.</span><span class="sxs-lookup"><span data-stu-id="b77a5-192">The tags must enclose a `<Name>` tag surrounding the name of the member set and a secondary `<Members>` tag that surround the members (properties and methods) in the set.</span></span> <span data-ttu-id="b77a5-193">Alle Tags, die eine Eigenschaft (z. b. `<NoteProperty>` oder `<ScriptProperty>` ) oder eine Methode (z. b. `<Method>` oder) erstellen, `<ScriptMethod>` können Member der Menge sein.</span><span class="sxs-lookup"><span data-stu-id="b77a5-193">Any of the tags that create a property (such as `<NoteProperty>` or `<ScriptProperty>`) or a method (such as `<Method>` or `<ScriptMethod>`) can be members of the set.</span></span>

<span data-ttu-id="b77a5-194">In- `Types.ps1xml` Dateien wird das- `<MemberSet>` Tag verwendet, um die Standard Sichten der .NET-Objekte in PowerShell zu definieren.</span><span class="sxs-lookup"><span data-stu-id="b77a5-194">In `Types.ps1xml` files, the `<MemberSet>` tag is used to define the default views of the .NET objects in PowerShell.</span></span> <span data-ttu-id="b77a5-195">In diesem Fall ist der Name des Element Satzes (der Wert innerhalb der `<Name>` Tags) immer **psstandardmembers**, und die Namen der Eigenschaften (der Wert des `<Name>` Tags) sind eines der folgenden:</span><span class="sxs-lookup"><span data-stu-id="b77a5-195">In this case, the name of the member set (the value within the `<Name>` tags) is always **PsStandardMembers**, and the names of the properties (the value of the `<Name>` tag) are one of the following:</span></span>

- <span data-ttu-id="b77a5-196">`DefaultDisplayProperty`: Eine einzelne Eigenschaft eines Objekts.</span><span class="sxs-lookup"><span data-stu-id="b77a5-196">`DefaultDisplayProperty`: A single property of an object.</span></span>

- <span data-ttu-id="b77a5-197">`DefaultDisplayPropertySet`: Eine oder mehrere Eigenschaften eines Objekts.</span><span class="sxs-lookup"><span data-stu-id="b77a5-197">`DefaultDisplayPropertySet`: One or more properties of an object.</span></span>

- <span data-ttu-id="b77a5-198">`DefaultKeyPropertySet`: Eine oder mehrere Schlüsseleigenschaften eines Objekts.</span><span class="sxs-lookup"><span data-stu-id="b77a5-198">`DefaultKeyPropertySet`: One or more key properties of an object.</span></span> <span data-ttu-id="b77a5-199">Eine Schlüsseleigenschaft identifiziert Instanzen von Eigenschafts Werten, z. b. die ID-Anzahl von Elementen in einem Sitzungsverlauf.</span><span class="sxs-lookup"><span data-stu-id="b77a5-199">A key property identifies instances of property values, such as the ID number of items in a session history.</span></span>

<span data-ttu-id="b77a5-200">Der folgende XML-Code definiert z. b. die Standard Anzeige der Dienste (- `System.ServiceProcess.ServiceController` Objekte), die vom `Get-Service` Cmdlet zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b77a5-200">For example, the following XML defines the default display of services (`System.ServiceProcess.ServiceController` objects) that are returned by the `Get-Service` cmdlet.</span></span> <span data-ttu-id="b77a5-201">Er definiert einen Member-Satz mit dem Namen " **psstandardmembers** ", der aus einem Standardeigenschaften Satz mit den Eigenschaften " **Status**", " **Name**" und " **Display Name** " besteht.</span><span class="sxs-lookup"><span data-stu-id="b77a5-201">It defines a member set named **PsStandardMembers** that consists of a default property set with the **Status**, **Name**, and **DisplayName** properties.</span></span>

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

<span data-ttu-id="b77a5-202">`<Method>`: Verweist auf eine native Methode des zugrunde liegenden-Objekts.</span><span class="sxs-lookup"><span data-stu-id="b77a5-202">`<Method>`: References a native method of the underlying object.</span></span>

<span data-ttu-id="b77a5-203">`<Methods>`: Eine Auflistung der Methoden des-Objekts.</span><span class="sxs-lookup"><span data-stu-id="b77a5-203">`<Methods>`: A collection of the methods of the object.</span></span>

<span data-ttu-id="b77a5-204">`<NoteProperty>`: Definiert eine Eigenschaft mit einem statischen Wert.</span><span class="sxs-lookup"><span data-stu-id="b77a5-204">`<NoteProperty>`: Defines a property with a static value.</span></span>

<span data-ttu-id="b77a5-205">Das `<NoteProperty>` -Tag muss über ein `<Name>` -Tag verfügen, das den Namen der neuen Eigenschaft und ein `<Value>` Tag angibt, das den Wert der-Eigenschaft angibt.</span><span class="sxs-lookup"><span data-stu-id="b77a5-205">The `<NoteProperty>` tag must have a `<Name>` tag that specifies the name of the new property and a `<Value>` tag that specifies the value of the property.</span></span>

<span data-ttu-id="b77a5-206">Der folgende XML-Code erstellt z. b. eine **Status** Eigenschaft für **System. IO. directoriyinfo** -Objekte.</span><span class="sxs-lookup"><span data-stu-id="b77a5-206">For example, the following XML creates a **Status** property for **System.IO.DirectoryInfo** objects.</span></span> <span data-ttu-id="b77a5-207">Der Wert der **Status** -Eigenschaft lautet immer **erfolgreich**.</span><span class="sxs-lookup"><span data-stu-id="b77a5-207">The value of the **Status** property is always **Success**.</span></span>

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

<span data-ttu-id="b77a5-208">`<ParameterizedProperty>`: Eigenschaften, die Argumente annehmen und einen Wert zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="b77a5-208">`<ParameterizedProperty>`: Properties that take arguments and return a value.</span></span>

<span data-ttu-id="b77a5-209">`<Properties>`: Eine Auflistung der Eigenschaften des-Objekts.</span><span class="sxs-lookup"><span data-stu-id="b77a5-209">`<Properties>`: A collection of the properties of the object.</span></span>

<span data-ttu-id="b77a5-210">`<Property>`: Eine Eigenschaft des Basis Objekts.</span><span class="sxs-lookup"><span data-stu-id="b77a5-210">`<Property>`: A property of the base object.</span></span>

<span data-ttu-id="b77a5-211">`<PropertySet>`: Definiert eine Auflistung von Eigenschaften des-Objekts.</span><span class="sxs-lookup"><span data-stu-id="b77a5-211">`<PropertySet>`: Defines a collection of properties of the object.</span></span>

<span data-ttu-id="b77a5-212">Das `<PropertySet>` -Tag muss über ein `<Name>` -Tag verfügen, das den Namen des Eigenschaften Satzes und ein `<ReferencedProperty>` Tag angibt, das die Eigenschaften angibt.</span><span class="sxs-lookup"><span data-stu-id="b77a5-212">The `<PropertySet>` tag must have a `<Name>` tag that specifies the name of the property set and a `<ReferencedProperty>` tag that specifies the properties.</span></span> <span data-ttu-id="b77a5-213">Die Namen der Eigenschaften werden in Tag eingeschlossen `<Name>` .</span><span class="sxs-lookup"><span data-stu-id="b77a5-213">The names of the properties are enclosed in `<Name>` tag.</span></span>

<span data-ttu-id="b77a5-214">In `Types.ps1xml` `<PropertySet>` werden Tags verwendet, um Gruppen von Eigenschaften für die Standard Anzeige eines Objekts zu definieren.</span><span class="sxs-lookup"><span data-stu-id="b77a5-214">In `Types.ps1xml`, `<PropertySet>` tags are used to define sets of properties for the default display of an object.</span></span> <span data-ttu-id="b77a5-215">Sie können die Standard anzeigen durch den Wert **psstandardmembers** im `<Name>` Tag eines `<MemberSet>` Tags ermitteln.</span><span class="sxs-lookup"><span data-stu-id="b77a5-215">You can identify the default displays by the value **PsStandardMembers** in the `<Name>` tag of a `<MemberSet>` tag.</span></span>

<span data-ttu-id="b77a5-216">Der folgende XML-Code erstellt beispielsweise eine **Status** -Eigenschaft für das- `System.IO.DirectoryInfo` Objekt.</span><span class="sxs-lookup"><span data-stu-id="b77a5-216">For example, the following XML creates a **Status** property for the `System.IO.DirectoryInfo` object.</span></span> <span data-ttu-id="b77a5-217">Der Wert der **Status** -Eigenschaft lautet immer **erfolgreich**.</span><span class="sxs-lookup"><span data-stu-id="b77a5-217">The value of the **Status** property is always **Success**.</span></span>

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

<span data-ttu-id="b77a5-218">`<ScriptMethod>`: Definiert eine Methode, deren Wert die Ausgabe eines Skripts ist.</span><span class="sxs-lookup"><span data-stu-id="b77a5-218">`<ScriptMethod>`: Defines a method whose value is the output of a script.</span></span>

<span data-ttu-id="b77a5-219">Das `<ScriptMethod>` -Tag muss über ein `<Name>` -Tag verfügen, das den Namen der neuen Methode und ein `<Script>` Tag, das den Skriptblock einschließt, der das Methoden Ergebnis zurückgibt, angibt.</span><span class="sxs-lookup"><span data-stu-id="b77a5-219">The `<ScriptMethod>` tag must have a `<Name>` tag that specifies the name of the new method and a `<Script>` tag that encloses the script block that returns the method result.</span></span>

<span data-ttu-id="b77a5-220">Die `ConvertToDateTime` -Methode und die- `ConvertFromDateTime` Methode von Management Objects () sind z. b `System.System.Management.ManagementObject` . Skript Methoden, die die `ToDateTime` statischen Methoden und der- `ToDmtfDateTime` Klasse verwenden `System.Management.ManagementDateTimeConverter` .</span><span class="sxs-lookup"><span data-stu-id="b77a5-220">For example, the `ConvertToDateTime` and `ConvertFromDateTime` methods of management objects (`System.System.Management.ManagementObject`) are script methods that use the `ToDateTime` and `ToDmtfDateTime` static methods of the `System.Management.ManagementDateTimeConverter` class.</span></span>

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

<span data-ttu-id="b77a5-221">`<ScriptProperty>`: Definiert eine Eigenschaft, deren Wert die Ausgabe eines Skripts ist.</span><span class="sxs-lookup"><span data-stu-id="b77a5-221">`<ScriptProperty>`: Defines a property whose value is the output of a script.</span></span>

<span data-ttu-id="b77a5-222">Das `<ScriptProperty>` -Tag muss über ein `<Name>` -Tag verfügen, das den Namen der neuen Eigenschaft und ein Tag angibt, das `<GetScriptBlock>` den Skriptblock einschließt, der den Eigenschafts Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="b77a5-222">The `<ScriptProperty>` tag must have a `<Name>` tag that specifies the name of the new property and a `<GetScriptBlock>` tag that encloses the script block that returns the property value.</span></span>

<span data-ttu-id="b77a5-223">Beispielsweise ist die **VERSIONINFO** -Eigenschaft des **System. IO. FileInfo** -Objekts eine Skript Eigenschaft, die sich aus der Verwendung der **FullName** -Eigenschaft der statischen **GetVersionInfo** -Methode der **System. Diagnostics. FileVersionInfo** -Objekte ergibt.</span><span class="sxs-lookup"><span data-stu-id="b77a5-223">For example, the **VersionInfo** property of the **System.IO.FileInfo** object is a script property that results from using the **FullName** property of the **GetVersionInfo** static method of **System.Diagnostics.FileVersionInfo** objects.</span></span>

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

<span data-ttu-id="b77a5-224">Weitere Informationen finden Sie im [Windows PowerShell Software Development Kit (SDK)](/powershell/scripting/developer/windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="b77a5-224">For more information, see the [Windows PowerShell Software Development Kit (SDK)](/powershell/scripting/developer/windows-powershell).</span></span>

## <a name="update-typedata"></a><span data-ttu-id="b77a5-225">Update-TypeData</span><span class="sxs-lookup"><span data-stu-id="b77a5-225">Update-TypeData</span></span>

<span data-ttu-id="b77a5-226">`Types.ps1xml`Führen Sie das-Cmdlet aus, um die Dateien in eine PowerShell-Sitzung zu laden `Update-TypeData` .</span><span class="sxs-lookup"><span data-stu-id="b77a5-226">To load your `Types.ps1xml` files into a PowerShell session, run the `Update-TypeData` cmdlet.</span></span> <span data-ttu-id="b77a5-227">Wenn Sie möchten, dass die Typen in der Datei Vorrang vor Typen in der integrierten `Types.ps1xml` Datei haben, fügen Sie den **prepddata** -Parameter von hinzu `Update-TypeData` .</span><span class="sxs-lookup"><span data-stu-id="b77a5-227">If you want the types in your file to take precedence over types in the built-in `Types.ps1xml` file, add the **PrependData** parameter of `Update-TypeData`.</span></span> <span data-ttu-id="b77a5-228">`Update-TypeData` wirkt sich nur auf die aktuelle Sitzung aus.</span><span class="sxs-lookup"><span data-stu-id="b77a5-228">`Update-TypeData` affects only the current session.</span></span> <span data-ttu-id="b77a5-229">Um die Änderung an allen zukünftigen Sitzungen vorzunehmen, exportieren Sie die Sitzung, oder fügen Sie den `Update-TypeData` Befehl zu Ihrem PowerShell-Profil hinzu.</span><span class="sxs-lookup"><span data-stu-id="b77a5-229">To make the change to all future sessions, export the session, or add the `Update-TypeData` command to your PowerShell profile.</span></span>

<span data-ttu-id="b77a5-230">Ausnahmen, die in Eigenschaften auftreten, oder das Hinzufügen von Eigenschaften zu einem `Update-TypeData` Befehl, melden keine Fehler an `StdErr` .</span><span class="sxs-lookup"><span data-stu-id="b77a5-230">Exceptions that occur in properties, or from adding properties to an `Update-TypeData` command, do not report errors to `StdErr`.</span></span> <span data-ttu-id="b77a5-231">Dadurch werden Ausnahmen unterdrückt, die während der Formatierung und Ausgabe in vielen gängigen Typen auftreten würden.</span><span class="sxs-lookup"><span data-stu-id="b77a5-231">This is to suppress exceptions that would occur in many common types during formatting and outputting.</span></span> <span data-ttu-id="b77a5-232">Wenn Sie .net-Eigenschaften erhalten, können Sie die Unterdrückung von Ausnahmen umgehen, indem Sie stattdessen die Methoden Syntax verwenden, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="b77a5-232">If you are getting .NET properties, you can work around the suppression of exceptions by using method syntax instead, as shown in the following example:</span></span>

```powershell
"hello".get_Length()
```

<span data-ttu-id="b77a5-233">Beachten Sie, dass die Methoden Syntax nur mit .net-Eigenschaften verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="b77a5-233">Note that method syntax can only be used with .NET properties.</span></span> <span data-ttu-id="b77a5-234">Eigenschaften, die durch das Ausführen des `Update-TypeData` Cmdlets hinzugefügt werden, können keine Methoden Syntax verwenden.</span><span class="sxs-lookup"><span data-stu-id="b77a5-234">Properties that are added by running the `Update-TypeData` cmdlet cannot use method syntax.</span></span>

## <a name="signing-a-typesps1xml-file"></a><span data-ttu-id="b77a5-235">Signieren einer Types.ps1-XML-Datei</span><span class="sxs-lookup"><span data-stu-id="b77a5-235">Signing a Types.ps1xml file</span></span>

<span data-ttu-id="b77a5-236">Um Benutzer Ihrer Datei zu schützen `Types.ps1xml` , können Sie die Datei mit einer digitalen Signatur signieren.</span><span class="sxs-lookup"><span data-stu-id="b77a5-236">To protect users of your `Types.ps1xml` file, you can sign the file using a digital signature.</span></span> <span data-ttu-id="b77a5-237">Weitere Informationen finden Sie unter [about_Signing](about_Signing.md).</span><span class="sxs-lookup"><span data-stu-id="b77a5-237">For more information, see [about_Signing](about_Signing.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b77a5-238">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b77a5-238">See also</span></span>

[<span data-ttu-id="b77a5-239">about_Signing</span><span class="sxs-lookup"><span data-stu-id="b77a5-239">about_Signing</span></span>](about_Signing.md)

[<span data-ttu-id="b77a5-240">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="b77a5-240">Copy-Item</span></span>](xref:Microsoft.PowerShell.Management.Copy-Item)

[<span data-ttu-id="b77a5-241">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b77a5-241">Copy-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Copy-ItemProperty)

[<span data-ttu-id="b77a5-242">Get-Member</span><span class="sxs-lookup"><span data-stu-id="b77a5-242">Get-Member</span></span>](xref:Microsoft.PowerShell.Utility.Get-Member)

[<span data-ttu-id="b77a5-243">Get-TypeData</span><span class="sxs-lookup"><span data-stu-id="b77a5-243">Get-TypeData</span></span>](xref:Microsoft.PowerShell.Utility.Get-TypeData)

[<span data-ttu-id="b77a5-244">Remove-TypeData</span><span class="sxs-lookup"><span data-stu-id="b77a5-244">Remove-TypeData</span></span>](xref:Microsoft.PowerShell.Utility.Remove-TypeData)

[<span data-ttu-id="b77a5-245">Update-TypeData</span><span class="sxs-lookup"><span data-stu-id="b77a5-245">Update-TypeData</span></span>](xref:Microsoft.PowerShell.Utility.Update-TypeData)

