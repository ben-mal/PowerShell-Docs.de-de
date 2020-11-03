---
description: Erläutert das Erstellen von-Objekten in PowerShell.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 09/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_object_creation?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Object_Creation
ms.openlocfilehash: 8903af794c83e4c84709e3eeb21489557458e988
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223428"
---
# <a name="about-object-creation"></a><span data-ttu-id="fec82-104">Informationen zur Objekt Erstellung</span><span class="sxs-lookup"><span data-stu-id="fec82-104">About Object Creation</span></span>

## <a name="short-description"></a><span data-ttu-id="fec82-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fec82-105">Short description</span></span>

<span data-ttu-id="fec82-106">Erläutert das Erstellen von-Objekten in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fec82-106">Explains how to create objects in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="fec82-107">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fec82-107">Long description</span></span>

<span data-ttu-id="fec82-108">Sie können-Objekte in PowerShell erstellen und die Objekte verwenden, die Sie in Befehlen und Skripts erstellen.</span><span class="sxs-lookup"><span data-stu-id="fec82-108">You can create objects in PowerShell and use the objects that you create in commands and scripts.</span></span>

<span data-ttu-id="fec82-109">Es gibt viele Möglichkeiten, Objekte zu erstellen. diese Liste ist nicht definitiv:</span><span class="sxs-lookup"><span data-stu-id="fec82-109">There are many ways to create objects, this list is not definitive:</span></span>

- <span data-ttu-id="fec82-110">[New-Object](xref:Microsoft.PowerShell.Utility.New-Object): erstellt eine Instanz eines .NET Framework Objekts oder eines COM-Objekts.</span><span class="sxs-lookup"><span data-stu-id="fec82-110">[New-Object](xref:Microsoft.PowerShell.Utility.New-Object): Creates an instance of a .NET Framework object or COM object.</span></span>
- <span data-ttu-id="fec82-111">[Import-CSV](xref:Microsoft.PowerShell.Utility.Import-Csv) /
   [ConvertFrom-CSV](xref:Microsoft.PowerShell.Utility.ConvertFrom-Csv): erstellt benutzerdefinierte Objekte ( **pscustomobject** ) aus den Elementen, die als durch Trennzeichen getrennte Werte definiert sind.</span><span class="sxs-lookup"><span data-stu-id="fec82-111">[Import-Csv](xref:Microsoft.PowerShell.Utility.Import-Csv)/
  [ConvertFrom-CSV](xref:Microsoft.PowerShell.Utility.ConvertFrom-Csv): Creates custom objects ( **PSCustomObject** ) from the items defined as comma separated values.</span></span>
- <span data-ttu-id="fec82-112">[ConvertFrom-JSON](xref:Microsoft.PowerShell.Utility.ConvertFrom-Json): erstellt benutzerdefinierte Objekte, die in JavaScript Object Notation (JSON) definiert sind.</span><span class="sxs-lookup"><span data-stu-id="fec82-112">[ConvertFrom-Json](xref:Microsoft.PowerShell.Utility.ConvertFrom-Json): Creates custom objects defined in JavaScript Object Notation (JSON).</span></span>
- <span data-ttu-id="fec82-113">[ConvertFrom-String](xref:Microsoft.PowerShell.Utility.ConvertFrom-String): basiert auf " [Flash Extract](https://www.microsoft.com/research/publication/flashextract-framework-data-extraction-examples)" und `ConvertFrom-String` erstellt benutzerdefinierte Objekte aus strukturierten Zeichen folgen Daten.</span><span class="sxs-lookup"><span data-stu-id="fec82-113">[ConvertFrom-String](xref:Microsoft.PowerShell.Utility.ConvertFrom-String): Built on top of [FlashExtract](https://www.microsoft.com/research/publication/flashextract-framework-data-extraction-examples), `ConvertFrom-String` creates custom objects from structured string data.</span></span>
  <span data-ttu-id="fec82-114">In diesem Thema werden die einzelnen Methoden erläutert und erläutert.</span><span class="sxs-lookup"><span data-stu-id="fec82-114">This topic will demonstrate and discuss each of these methods.</span></span>
- <span data-ttu-id="fec82-115">[ConvertFrom-StringData](xref:Microsoft.PowerShell.Utility.ConvertFrom-StringData): erstellt benutzerdefinierte Objekte, die als Schlüssel-Wert-Paare definiert sind.</span><span class="sxs-lookup"><span data-stu-id="fec82-115">[ConvertFrom-StringData](xref:Microsoft.PowerShell.Utility.ConvertFrom-StringData): Creates custom objects defined as key value pairs.</span></span>
- <span data-ttu-id="fec82-116">[Add-Type](xref:Microsoft.PowerShell.Utility.Add-Type): ermöglicht Ihnen das Definieren einer Klasse in der PowerShell-Sitzung, die Sie mit instanziieren können `New-Object` .</span><span class="sxs-lookup"><span data-stu-id="fec82-116">[Add-Type](xref:Microsoft.PowerShell.Utility.Add-Type): Allows you to define a class in your PowerShell session that you can instantiate with `New-Object`.</span></span>
- <span data-ttu-id="fec82-117">[New-Module](xref:Microsoft.PowerShell.Core.New-Module): der **ascustomobject** -Parameter erstellt ein benutzerdefiniertes Objekt, das Sie mit dem Skriptblock definieren.</span><span class="sxs-lookup"><span data-stu-id="fec82-117">[New-Module](xref:Microsoft.PowerShell.Core.New-Module): The **AsCustomObject** parameter creates a custom object you define using script block.</span></span>
- <span data-ttu-id="fec82-118">[Add-Member](xref:Microsoft.PowerShell.Utility.Add-Member): fügt vorhandenen Objekten Eigenschaften hinzu.</span><span class="sxs-lookup"><span data-stu-id="fec82-118">[Add-Member](xref:Microsoft.PowerShell.Utility.Add-Member): Adds properties to existing objects.</span></span> <span data-ttu-id="fec82-119">Sie können verwenden, `Add-Member` um ein benutzerdefiniertes Objekt aus einem einfachen Typ zu erstellen, wie z `[System.Int32]` . b..</span><span class="sxs-lookup"><span data-stu-id="fec82-119">You can use `Add-Member` to create a custom object out of a simple type, like `[System.Int32]`.</span></span>
- <span data-ttu-id="fec82-120">[Select-Object](xref:Microsoft.PowerShell.Utility.Select-Object): wählt Eigenschaften für ein Objekt aus.</span><span class="sxs-lookup"><span data-stu-id="fec82-120">[Select-Object](xref:Microsoft.PowerShell.Utility.Select-Object): Selects properties on an object.</span></span> <span data-ttu-id="fec82-121">Sie können verwenden `Select-Object` , um benutzerdefinierte und berechnete Eigenschaften für ein bereits instanziertes Objekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fec82-121">You can use `Select-Object` to create custom and calculated properties on an already instantiated object.</span></span>

<span data-ttu-id="fec82-122">Die folgenden zusätzlichen Methoden werden in diesem Artikel behandelt:</span><span class="sxs-lookup"><span data-stu-id="fec82-122">The following additional methods are covered in this article:</span></span>

- <span data-ttu-id="fec82-123">Durch Aufrufen des Konstruktors eines Typs mit einer statischen `new()` Methode</span><span class="sxs-lookup"><span data-stu-id="fec82-123">By calling a type's constructor using a static `new()` method</span></span>
- <span data-ttu-id="fec82-124">Durch Typecasting von Hash Tabellen mit Eigenschaftsnamen und Eigenschafts Werten</span><span class="sxs-lookup"><span data-stu-id="fec82-124">By typecasting hash tables of property names and property values</span></span>

## <a name="static-new-method"></a><span data-ttu-id="fec82-125">Static New ()-Methode</span><span class="sxs-lookup"><span data-stu-id="fec82-125">Static new() method</span></span>

<span data-ttu-id="fec82-126">Alle .NET-Typen verfügen über eine- `new()` Methode, die es Ihnen ermöglicht,-Instanzen einfacher zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fec82-126">All .NET types have a `new()` method that allows you to construct instances more easily.</span></span> <span data-ttu-id="fec82-127">Sie können auch alle verfügbaren Konstruktoren für einen bestimmten Typ anzeigen.</span><span class="sxs-lookup"><span data-stu-id="fec82-127">You can also see all the available constructors for a given type.</span></span>

<span data-ttu-id="fec82-128">Geben Sie den `new` Methodennamen nach dem Typnamen an, und drücken Sie, um die Konstruktoren für einen Typ anzuzeigen `<ENTER>` .</span><span class="sxs-lookup"><span data-stu-id="fec82-128">To see the constructors for a type, specify the `new` method name after the type name and press `<ENTER>`.</span></span>

```powershell
[System.Uri]::new
```

```Output
OverloadDefinitions
-------------------
uri new(string uriString)
uri new(string uriString, bool dontEscape)
uri new(uri baseUri, string relativeUri, bool dontEscape)
uri new(string uriString, System.UriKind uriKind)
uri new(uri baseUri, string relativeUri)
uri new(uri baseUri, uri relativeUri)
```

<span data-ttu-id="fec82-129">Nun können Sie einen **System. Uri** erstellen, indem Sie den entsprechenden Konstruktor angeben.</span><span class="sxs-lookup"><span data-stu-id="fec82-129">Now, you can create a **System.Uri** by specifying the appropriate constructor.</span></span>

```powershell
[System.Uri]::new("https://www.bing.com")
```

```Output
AbsolutePath   : /
AbsoluteUri    : https://www.bing.com/
LocalPath      : /
Authority      : www.bing.com
...
```

<span data-ttu-id="fec82-130">Sie können das folgende Beispiel verwenden, um zu bestimmen, welche .NET-Typen derzeit für die instanziieren geladen werden.</span><span class="sxs-lookup"><span data-stu-id="fec82-130">You can use the following sample to determine what .NET types are currently loaded for you to instantiate.</span></span>

```powershell
[AppDomain]::CurrentDomain.GetAssemblies() |
  ForEach-Object {
    $_.GetExportedTypes() |
      ForEach-Object { $_.FullName }
  }
```

<span data-ttu-id="fec82-131">Objekte, die mit der-Methode erstellt wurden `new()` , haben möglicherweise nicht dieselben Eigenschaften wie Objekte desselben Typs, die von PowerShell-Cmdlets erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="fec82-131">Objects created using the `new()` method may not have the same properties as objects of the same type that are created by PowerShell cmdlets.</span></span> <span data-ttu-id="fec82-132">PowerShell-Cmdlets,-Anbieter und das erweiterte Typsystem können der-Instanz zusätzliche Eigenschaften hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="fec82-132">PowerShell cmdlets, providers, and Extended Type System can add extra properties to the instance.</span></span>

<span data-ttu-id="fec82-133">Beispielsweise fügt der File System-Anbieter in PowerShell sechs **NoteProperty** -Werte zum **DirectoryInfo** -Objekt hinzu, das von zurückgegeben wird `Get-Item` .</span><span class="sxs-lookup"><span data-stu-id="fec82-133">For example, the FileSystem provider in PowerShell adds six **NoteProperty** values to the **DirectoryInfo** object returned by `Get-Item`.</span></span>

```powershell
$PSDirInfo = Get-Item /
$PSDirInfo | Get-Member | Group-Object MemberType | Select-Object Count, Name
```

```Output
Count Name
----- ----
    4 CodeProperty
   13 Property
    6 NoteProperty
    1 ScriptProperty
   18 Method
```

<span data-ttu-id="fec82-134">Wenn Sie ein **DirectoryInfo** -Objekt direkt erstellen, verfügt es nicht über diese sechs **NoteProperty** -Werte.</span><span class="sxs-lookup"><span data-stu-id="fec82-134">When you create a **DirectoryInfo** object directly, it does not have those six **NoteProperty** values.</span></span>

```powershell
$NewDirInfo = [System.IO.DirectoryInfo]::new('/')
$NewDirInfo | Get-Member | Group-Object MemberType | Select-Object Count, Name
```

```Output
Count Name
----- ----
    4 CodeProperty
   13 Property
    1 ScriptProperty
   18 Method
```

<span data-ttu-id="fec82-135">Weitere Informationen zum erweiterten Typsystem finden Sie unter [about_Types.ps1XML](about_Types.ps1xml.md).</span><span class="sxs-lookup"><span data-stu-id="fec82-135">For more information about the Extended Type System, see [about_Types.ps1xml](about_Types.ps1xml.md).</span></span>

<span data-ttu-id="fec82-136">Diese Funktion wurde in PowerShell 5,0 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="fec82-136">This feature was added in PowerShell 5.0</span></span>

## <a name="create-objects-from-hash-tables"></a><span data-ttu-id="fec82-137">Erstellen von Objekten aus Hash Tabellen</span><span class="sxs-lookup"><span data-stu-id="fec82-137">Create objects from hash tables</span></span>

<span data-ttu-id="fec82-138">Sie können ein Objekt aus einer Hash Tabelle mit Eigenschaften und Eigenschafts Werten erstellen.</span><span class="sxs-lookup"><span data-stu-id="fec82-138">You can create an object from a hash table of properties and property values.</span></span>

<span data-ttu-id="fec82-139">Die Syntax ist wie folgt:</span><span class="sxs-lookup"><span data-stu-id="fec82-139">The syntax is as follows:</span></span>

```
[<class-name>]@{
  <property-name>=<property-value>
  <property-name>=<property-value>
}
```

<span data-ttu-id="fec82-140">Diese Methode funktioniert nur für Klassen, die über einen Parameter losen Konstruktor verfügen.</span><span class="sxs-lookup"><span data-stu-id="fec82-140">This method works only for classes that have a parameterless constructor.</span></span> <span data-ttu-id="fec82-141">Die Objekteigenschaften müssen öffentlich und feststellbar sein.</span><span class="sxs-lookup"><span data-stu-id="fec82-141">The object properties must be public and settable.</span></span>

<span data-ttu-id="fec82-142">Diese Funktion wurde in PowerShell-Version 3,0 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="fec82-142">This feature was added in PowerShell version 3.0</span></span>

## <a name="create-custom-objects-from-hash-tables"></a><span data-ttu-id="fec82-143">Erstellen von benutzerdefinierten Objekten aus Hash Tabellen</span><span class="sxs-lookup"><span data-stu-id="fec82-143">Create custom objects from hash tables</span></span>

<span data-ttu-id="fec82-144">Benutzerdefinierte Objekte sind sehr nützlich und können problemlos mithilfe der Hash Tabellen Methode erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="fec82-144">Custom objects are very useful and are easy to create using the hash table method.</span></span> <span data-ttu-id="fec82-145">Die **pscustomobject** -Klasse ist speziell für diesen Zweck konzipiert.</span><span class="sxs-lookup"><span data-stu-id="fec82-145">The **PSCustomObject** class is designed specifically for this purpose.</span></span>

<span data-ttu-id="fec82-146">Benutzerdefinierte Objekte sind eine hervorragende Möglichkeit, eine angepasste Ausgabe einer Funktion oder eines Skripts zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="fec82-146">Custom objects are an excellent way to return customized output from a function or script.</span></span> <span data-ttu-id="fec82-147">Dies ist nützlicher als das Zurückgeben von formatierter Ausgabe, die nicht neu formatiert oder an andere Befehle weitergeleitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="fec82-147">This is more useful than returning formatted output that cannot be reformatted or piped to other commands.</span></span>

<span data-ttu-id="fec82-148">Die Befehle im `Test-Object function` legen einige Variablen Werte fest und verwenden diese Werte dann, um ein benutzerdefiniertes Objekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fec82-148">The commands in the `Test-Object function` set some variable values and then use those values to create a custom object.</span></span> <span data-ttu-id="fec82-149">Dieses Objekt wird im Beispiel Abschnitt des `Update-Help` Cmdlet-Hilfe Themas verwendet.</span><span class="sxs-lookup"><span data-stu-id="fec82-149">You can see this object in use in the example section of the `Update-Help` cmdlet help topic.</span></span>

```powershell
function Test-Object {
  $ModuleName = "PSScheduledJob"
  $HelpCulture = "en-us"
  $HelpVersion = "3.1.0.0"
  [PSCustomObject]@{
    "ModuleName"=$ModuleName
    "UICulture"=$HelpCulture
    "Version"=$HelpVersion
  }
  $ModuleName = "PSWorkflow"
  $HelpCulture = "en-us"
  $HelpVersion = "3.0.0.0"
  [PSCustomObject]@{
    "ModuleName"=$ModuleName
    "UICulture"=$HelpCulture
    "Version"=$HelpVersion
  }
}
Test-Object
```

<span data-ttu-id="fec82-150">Die Ausgabe dieser Funktion ist eine Auflistung benutzerdefinierter Objekte, die standardmäßig als Tabelle formatiert sind.</span><span class="sxs-lookup"><span data-stu-id="fec82-150">The output of this function is a collection of custom objects formatted as a table by default.</span></span>

```Output
ModuleName        UICulture      Version
---------         ---------      -------
PSScheduledJob    en-us          3.1.0.0
PSWorkflow        en-us          3.0.0.0
```

<span data-ttu-id="fec82-151">Benutzer können die Eigenschaften der benutzerdefinierten Objekte genau wie bei Standardobjekten verwalten.</span><span class="sxs-lookup"><span data-stu-id="fec82-151">Users can manage the properties of the custom objects just as they do with standard objects.</span></span>

```powershell
(Test-Object).ModuleName
```

```Output
 PSScheduledJob
 PSWorkflow
```

## <a name="create-non-custom-objects-from-hash-tables"></a><span data-ttu-id="fec82-152">Erstellen von Nichtbenutzer definierten Objekten aus Hash Tabellen</span><span class="sxs-lookup"><span data-stu-id="fec82-152">Create non-custom objects from hash tables</span></span>

<span data-ttu-id="fec82-153">Sie können auch Hash Tabellen verwenden, um-Objekte für Nichtbenutzer definierte Klassen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fec82-153">You can also use hash tables to create objects for non-custom classes.</span></span> <span data-ttu-id="fec82-154">Wenn Sie ein Objekt für eine Nichtbenutzer definierte Klasse erstellen, ist der mit einem Namespace qualifizierte Typname erforderlich, obwohl Sie möglicherweise eine anfängliche **System** -Namespace Komponente weglassen.</span><span class="sxs-lookup"><span data-stu-id="fec82-154">When you create an object for a non-custom class, the namespace-qualified type name is required, although you may omit any initial **System** namespace component.</span></span>

<span data-ttu-id="fec82-155">Der folgende Befehl erstellt z. b. ein Sitzungs Options Objekt.</span><span class="sxs-lookup"><span data-stu-id="fec82-155">For example, the following command creates a session option object.</span></span>

```powershell
[System.Management.Automation.Remoting.PSSessionOption]@{
  IdleTimeout=43200000
  SkipCnCheck=$True
}
```

<span data-ttu-id="fec82-156">Die Anforderungen des Hash Tabellen-Features, insbesondere die Parameter losen konstruktoranforderungen, eliminieren viele vorhandene Klassen.</span><span class="sxs-lookup"><span data-stu-id="fec82-156">The requirements of the hash table feature, especially the parameterless constructor requirement, eliminate many existing classes.</span></span> <span data-ttu-id="fec82-157">Die meisten PowerShell- _options_ Klassen sind jedoch für die Verwendung dieser Funktion sowie für andere sehr nützliche Klassen, wie z. b. die **ProcessStartInfo** -Klasse, konzipiert.</span><span class="sxs-lookup"><span data-stu-id="fec82-157">However, most PowerShell _option_ classes are designed to work with this feature, as well as other very useful classes, such as the **ProcessStartInfo** class.</span></span>

```powershell
[System.Diagnostics.ProcessStartInfo]@{
  CreateNoWindow="$true"
  Verb="run as"
}
```

```Output
Arguments               :
ArgumentList            : {}
CreateNoWindow          : True
EnvironmentVariables    : {OneDriveConsumer, PROCESSOR_ARCHITECTURE,
                           CommonProgramFiles(x86), APPDATA...}
Environment             : {[OneDriveConsumer, C:\Users\user1\OneDrive],
                           [PROCESSOR_ARCHITECTURE, AMD64],
                           [CommonProgramFiles(x86),
                           C:\Program Files (x86)\Common Files],
                           [APPDATA, C:\Users\user1\AppData\Roaming]...}
RedirectStandardInput   : False
RedirectStandardOutput  : False
RedirectStandardError   : False
...
```

<span data-ttu-id="fec82-158">Sie können auch die Hash Tabellen Funktion verwenden, wenn Sie Parameterwerte festlegen.</span><span class="sxs-lookup"><span data-stu-id="fec82-158">You can also use the hash table feature when setting parameter values.</span></span> <span data-ttu-id="fec82-159">Beispielsweise der Wert des **sessionoption** -Parameters von `New-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="fec82-159">For example, the value of the **SessionOption** parameter of the `New-PSSession`.</span></span>
<span data-ttu-id="fec82-160">-Cmdlet kann eine Hash Tabelle sein.</span><span class="sxs-lookup"><span data-stu-id="fec82-160">cmdlet can be a hash table.</span></span>

```powershell
New-PSSession -ComputerName Server01 -SessionOption @{
  IdleTimeout=43200000
  SkipCnCheck=$True
}
Register-ScheduledJob Name Test -FilePath .\Get-Inventory.ps1 -Trigger @{
  Frequency="Daily"
  At="15:00"
}
```

## <a name="generic-objects"></a><span data-ttu-id="fec82-161">Generische Objekte</span><span class="sxs-lookup"><span data-stu-id="fec82-161">Generic objects</span></span>

<span data-ttu-id="fec82-162">Sie können auch generische Objekte in PowerShell erstellen.</span><span class="sxs-lookup"><span data-stu-id="fec82-162">You can also create generic objects in PowerShell.</span></span> <span data-ttu-id="fec82-163">Generics sind Klassen, Strukturen, Schnittstellen und Methoden, die über Platzhalter (Typparameter) für einen oder mehrere der Typen verfügen, die sie speichern oder verwenden.</span><span class="sxs-lookup"><span data-stu-id="fec82-163">Generics are classes, structures, interfaces, and methods that have placeholders (type parameters) for one or more of the types that they store or use.</span></span>

<span data-ttu-id="fec82-164">Im folgenden Beispiel wird ein **Dictionary** -Objekt erstellt.</span><span class="sxs-lookup"><span data-stu-id="fec82-164">The following example creates a **Dictionary** object.</span></span>

```powershell
$dict = New-Object 'System.Collections.Generic.Dictionary[String,Int]'
$dict.Add("One", 1)
$dict
```

```Output
Key Value
--- -----
One     1
```

<span data-ttu-id="fec82-165">Weitere Informationen zu Generika finden Sie unter [Generika in .net](/dotnet/standard/generics).</span><span class="sxs-lookup"><span data-stu-id="fec82-165">For more information on Generics, see [Generics in .NET](/dotnet/standard/generics).</span></span>

## <a name="see-also"></a><span data-ttu-id="fec82-166">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="fec82-166">See also</span></span>

[<span data-ttu-id="fec82-167">about_Objects</span><span class="sxs-lookup"><span data-stu-id="fec82-167">about_Objects</span></span>](about_Objects.md)

[<span data-ttu-id="fec82-168">about_Methods</span><span class="sxs-lookup"><span data-stu-id="fec82-168">about_Methods</span></span>](about_Methods.md)

[<span data-ttu-id="fec82-169">about_Properties</span><span class="sxs-lookup"><span data-stu-id="fec82-169">about_Properties</span></span>](about_Properties.md)

[<span data-ttu-id="fec82-170">about_Pipelines</span><span class="sxs-lookup"><span data-stu-id="fec82-170">about_Pipelines</span></span>](about_Pipelines.md)

[<span data-ttu-id="fec82-171">about_Types.ps1xml</span><span class="sxs-lookup"><span data-stu-id="fec82-171">about_Types.ps1xml</span></span>](about_Types.ps1xml.md)
