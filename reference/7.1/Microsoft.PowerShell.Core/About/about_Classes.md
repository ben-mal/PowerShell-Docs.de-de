---
description: Beschreibt, wie Sie Klassen verwenden können, um eigene benutzerdefinierte Typen zu erstellen.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 09/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_classes?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Classes
ms.openlocfilehash: 99b72762469032cc24f21d957600b67d0a0db292
ms.sourcegitcommit: 16d62a98449e3ddaf8d7c65bc1848ede1fd8a3e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2020
ms.locfileid: "93219975"
---
# <a name="about-classes"></a><span data-ttu-id="10305-104">Informationen zu Klassen</span><span class="sxs-lookup"><span data-stu-id="10305-104">About Classes</span></span>

## <a name="short-description"></a><span data-ttu-id="10305-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="10305-105">Short description</span></span>
<span data-ttu-id="10305-106">Beschreibt, wie Sie Klassen verwenden können, um eigene benutzerdefinierte Typen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="10305-106">Describes how you can use classes to create your own custom types.</span></span>

## <a name="long-description"></a><span data-ttu-id="10305-107">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="10305-107">Long description</span></span>

<span data-ttu-id="10305-108">PowerShell 5,0 fügt eine formale Syntax zum Definieren von Klassen und anderen benutzerdefinierten Typen hinzu.</span><span class="sxs-lookup"><span data-stu-id="10305-108">PowerShell 5.0 adds a formal syntax to define classes and other user-defined types.</span></span> <span data-ttu-id="10305-109">Das Hinzufügen von Klassen ermöglicht Entwicklern und IT-Experten die Übernahme von PowerShell für eine größere Anzahl von Anwendungsfällen.</span><span class="sxs-lookup"><span data-stu-id="10305-109">The addition of classes enables developers and IT professionals to embrace PowerShell for a wider range of use cases.</span></span> <span data-ttu-id="10305-110">Es vereinfacht die Entwicklung von PowerShell-Artefakten und beschleunigt die Abdeckung von Verwaltungs Oberflächen.</span><span class="sxs-lookup"><span data-stu-id="10305-110">It simplifies development of PowerShell artifacts and accelerates coverage of management surfaces.</span></span>

<span data-ttu-id="10305-111">Eine Klassen Deklaration ist eine Blaupause, mit der Instanzen von Objekten zur Laufzeit erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="10305-111">A class declaration is a blueprint used to create instances of objects at run time.</span></span> <span data-ttu-id="10305-112">Wenn Sie eine Klasse definieren, ist der Klassenname der Name des Typs.</span><span class="sxs-lookup"><span data-stu-id="10305-112">When you define a class, the class name is the name of the type.</span></span> <span data-ttu-id="10305-113">Wenn Sie z. b. eine Klasse mit dem Namen " **Device** " deklarieren und eine Variable `$dev` für eine neue Instanz des **Geräts** initialisieren, `$dev` ist ein Objekt oder eine Instanz vom Typ " **Device** ".</span><span class="sxs-lookup"><span data-stu-id="10305-113">For example, if you declare a class named **Device** and initialize a variable `$dev` to a new instance of **Device** , `$dev` is an object or instance of type **Device**.</span></span> <span data-ttu-id="10305-114">Jede Instanz des **Geräts** kann unterschiedliche Werte in den zugehörigen Eigenschaften aufweisen.</span><span class="sxs-lookup"><span data-stu-id="10305-114">Each instance of **Device** can have different values in its properties.</span></span>

## <a name="supported-scenarios"></a><span data-ttu-id="10305-115">Unterstützte Szenarien</span><span class="sxs-lookup"><span data-stu-id="10305-115">Supported scenarios</span></span>

- <span data-ttu-id="10305-116">Definieren Sie benutzerdefinierte Typen in PowerShell mithilfe der vertrauten objektorientierten Programmier Semantik wie Klassen, Eigenschaften, Methoden, Vererbung usw.</span><span class="sxs-lookup"><span data-stu-id="10305-116">Define custom types in PowerShell using familiar object-oriented programming semantics like classes, properties, methods, inheritance, etc.</span></span>
- <span data-ttu-id="10305-117">Debuggen Sie Typen mithilfe der PowerShell-Sprache.</span><span class="sxs-lookup"><span data-stu-id="10305-117">Debug types using the PowerShell language.</span></span>
- <span data-ttu-id="10305-118">Generieren und behandeln von Ausnahmen mithilfe von formalen Mechanismen</span><span class="sxs-lookup"><span data-stu-id="10305-118">Generate and handle exceptions using formal mechanisms.</span></span>
- <span data-ttu-id="10305-119">Definieren Sie DSC-Ressourcen und die zugehörigen Typen mithilfe der PowerShell-Sprache.</span><span class="sxs-lookup"><span data-stu-id="10305-119">Define DSC resources and their associated types by using the PowerShell language.</span></span>

## <a name="syntax"></a><span data-ttu-id="10305-120">Syntax</span><span class="sxs-lookup"><span data-stu-id="10305-120">Syntax</span></span>

<span data-ttu-id="10305-121">Klassen werden mit der folgenden Syntax deklariert:</span><span class="sxs-lookup"><span data-stu-id="10305-121">Classes are declared using the following syntax:</span></span>

```syntax
class <class-name> [: [<base-class>][,<interface-list]] {
    [[<attribute>] [hidden] [static] <property-definition> ...]
    [<class-name>([<constructor-argument-list>])
      {<constructor-statement-list>} ...]
    [[<attribute>] [hidden] [static] <method-definition> ...]
}
```

<span data-ttu-id="10305-122">Klassen werden mit einer der folgenden Syntaxen instanziiert:</span><span class="sxs-lookup"><span data-stu-id="10305-122">Classes are instantiated using either of the following syntaxes:</span></span>

```syntax
[$<variable-name> =] New-Object -TypeName <class-name> [
  [-ArgumentList] <constructor-argument-list>]
```

```syntax
[$<variable-name> =] [<class-name>]::new([<constructor-argument-list>])
```

> [!NOTE]
> <span data-ttu-id="10305-123">Wenn Sie die `[<class-name>]::new()` Syntax verwenden, sind eckige Klammern um den Klassennamen obligatorisch.</span><span class="sxs-lookup"><span data-stu-id="10305-123">When using the `[<class-name>]::new()` syntax, brackets around the class name are mandatory.</span></span> <span data-ttu-id="10305-124">Die Klammern signalisieren eine Typdefinition für PowerShell.</span><span class="sxs-lookup"><span data-stu-id="10305-124">The brackets signal a type definition for PowerShell.</span></span>

### <a name="example-syntax-and-usage"></a><span data-ttu-id="10305-125">Syntax und Verwendung von Beispielen</span><span class="sxs-lookup"><span data-stu-id="10305-125">Example syntax and usage</span></span>

<span data-ttu-id="10305-126">Dieses Beispiel zeigt die minimale Syntax, die zum Erstellen einer verwendbaren Klasse benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="10305-126">This example shows the minimum syntax needed to create a usable class.</span></span>

```powershell
class Device {
    [string]$Brand
}

$dev = [Device]::new()
$dev.Brand = "Microsoft"
$dev
```

```Output
Brand
-----
Microsoft
```

## <a name="class-properties"></a><span data-ttu-id="10305-127">Klasseneigenschaften</span><span class="sxs-lookup"><span data-stu-id="10305-127">Class properties</span></span>

<span data-ttu-id="10305-128">Eigenschaften sind im Klassen Gültigkeitsbereich deklarierte Variablen.</span><span class="sxs-lookup"><span data-stu-id="10305-128">Properties are variables declared at class scope.</span></span> <span data-ttu-id="10305-129">Eine Eigenschaft kann ein beliebiger integrierter Typ oder eine Instanz einer anderen Klasse sein.</span><span class="sxs-lookup"><span data-stu-id="10305-129">A property may be of any built-in type or an instance of another class.</span></span> <span data-ttu-id="10305-130">Klassen haben keine Einschränkung in der Anzahl der Eigenschaften, die Sie besitzen.</span><span class="sxs-lookup"><span data-stu-id="10305-130">Classes have no restriction in the number of properties they have.</span></span>

### <a name="example-class-with-simple-properties"></a><span data-ttu-id="10305-131">Beispiel Klasse mit einfachen Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="10305-131">Example class with simple properties</span></span>

```powershell
class Device {
    [string]$Brand
    [string]$Model
    [string]$VendorSku
}

$device = [Device]::new()
$device.Brand = "Microsoft"
$device.Model = "Surface Pro 4"
$device.VendorSku = "5072641000"

$device
```

```Output
Brand     Model         VendorSku
-----     -----         ---------
Microsoft Surface Pro 4 5072641000
```

### <a name="example-complex-types-in-class-properties"></a><span data-ttu-id="10305-132">Komplexe Beispiel Typen in Klasseneigenschaften</span><span class="sxs-lookup"><span data-stu-id="10305-132">Example complex types in class properties</span></span>

<span data-ttu-id="10305-133">In diesem Beispiel wird eine leere **Rack** -Klasse mithilfe der **Device** -Klasse definiert.</span><span class="sxs-lookup"><span data-stu-id="10305-133">This example defines an empty **Rack** class using the **Device** class.</span></span> <span data-ttu-id="10305-134">In den folgenden Beispielen wird gezeigt, wie Sie dem Rack Geräte hinzufügen und mit einem vorab geladenen Gestell beginnen.</span><span class="sxs-lookup"><span data-stu-id="10305-134">The examples, following this one, show how to add devices to the rack and how to start with a pre-loaded rack.</span></span>

```powershell
class Device {
    [string]$Brand
    [string]$Model
    [string]$VendorSku
}

class Rack {
    [string]$Brand
    [string]$Model
    [string]$VendorSku
    [string]$AssetId
    [Device[]]$Devices = [Device[]]::new(8)

}

$rack = [Rack]::new()

$rack
```

```Output

Brand     :
Model     :
VendorSku :
AssetId   :
Devices   : {$null, $null, $null, $null...}


```

## <a name="class-methods"></a><span data-ttu-id="10305-135">Klassen Methoden</span><span class="sxs-lookup"><span data-stu-id="10305-135">Class methods</span></span>

<span data-ttu-id="10305-136">Methoden definieren die Aktionen, die von einer Klasse ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="10305-136">Methods define the actions that a class can perform.</span></span> <span data-ttu-id="10305-137">Methoden können Parameter annehmen, die Eingabedaten bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="10305-137">Methods may take parameters that provide input data.</span></span> <span data-ttu-id="10305-138">Methoden können die Ausgabe zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="10305-138">Methods can return output.</span></span> <span data-ttu-id="10305-139">Von einer Methode zurückgegebene Daten können einen beliebigen definierten Datentyp aufweisen.</span><span class="sxs-lookup"><span data-stu-id="10305-139">Data returned by a method can be any defined data type.</span></span>

<span data-ttu-id="10305-140">Wenn Sie eine Methode für eine Klasse definieren, verweisen Sie mit der automatischen Variablen auf das aktuelle Klassenobjekt `$this` .</span><span class="sxs-lookup"><span data-stu-id="10305-140">When defining a method for a class, you reference the current class object by using the `$this` automatic variable.</span></span> <span data-ttu-id="10305-141">Auf diese Weise können Sie auf Eigenschaften und andere Methoden zugreifen, die in der aktuellen Klasse definiert sind.</span><span class="sxs-lookup"><span data-stu-id="10305-141">This allows you to access properties and other methods defined in the current class.</span></span>

### <a name="example-simple-class-with-properties-and-methods"></a><span data-ttu-id="10305-142">Beispiel für eine einfache Klasse mit Eigenschaften und Methoden</span><span class="sxs-lookup"><span data-stu-id="10305-142">Example simple class with properties and methods</span></span>

<span data-ttu-id="10305-143">Erweitern der **Rack** -Klasse zum Hinzufügen und Entfernen von Geräten zu oder daraus.</span><span class="sxs-lookup"><span data-stu-id="10305-143">Extending the **Rack** class to add and remove devices to or from it.</span></span>

```powershell
class Device {
    [string]$Brand
    [string]$Model
    [string]$VendorSku

    [string]ToString(){
        return ("{0}|{1}|{2}" -f $this.Brand, $this.Model, $this.VendorSku)
    }
}

class Rack {
    [int]$Slots = 8
    [string]$Brand
    [string]$Model
    [string]$VendorSku
    [string]$AssetId
    [Device[]]$Devices = [Device[]]::new($this.Slots)

    [void] AddDevice([Device]$dev, [int]$slot){
        ## Add argument validation logic here
        $this.Devices[$slot] = $dev
    }

    [void]RemoveDevice([int]$slot){
        ## Add argument validation logic here
        $this.Devices[$slot] = $null
    }

    [int[]] GetAvailableSlots(){
        [int]$i = 0
        return @($this.Devices.foreach{ if($_ -eq $null){$i}; $i++})
    }
}

$rack = [Rack]::new()

$surface = [Device]::new()
$surface.Brand = "Microsoft"
$surface.Model = "Surface Pro 4"
$surface.VendorSku = "5072641000"

$rack.AddDevice($surface, 2)

$rack
$rack.GetAvailableSlots()
```

```Output

Slots     : 8
Brand     :
Model     :
VendorSku :
AssetId   :
Devices   : {$null, $null, Microsoft|Surface Pro 4|5072641000, $null...}

0
1
3
4
5
6
7

```

## <a name="output-in-class-methods"></a><span data-ttu-id="10305-144">Ausgabe in Klassen Methoden</span><span class="sxs-lookup"><span data-stu-id="10305-144">Output in class methods</span></span>

<span data-ttu-id="10305-145">Für Methoden muss ein Rückgabetyp definiert werden.</span><span class="sxs-lookup"><span data-stu-id="10305-145">Methods should have a return type defined.</span></span> <span data-ttu-id="10305-146">Wenn eine Methode keine Ausgabe zurückgibt, sollte der Ausgabetyp sein `[void]` .</span><span class="sxs-lookup"><span data-stu-id="10305-146">If a method doesn't return output, then the output type should be `[void]`.</span></span>

<span data-ttu-id="10305-147">In Klassen Methoden werden keine Objekte an die Pipeline gesendet, außer den in der- `return` Anweisung erwähnten.</span><span class="sxs-lookup"><span data-stu-id="10305-147">In class methods, no objects get sent to the pipeline except those mentioned in the `return` statement.</span></span> <span data-ttu-id="10305-148">Es gibt keine versehentliche Ausgabe an die Pipeline aus dem Code.</span><span class="sxs-lookup"><span data-stu-id="10305-148">There's no accidental output to the pipeline from the code.</span></span>

> [!NOTE]
> <span data-ttu-id="10305-149">Dies unterscheidet sich grundlegend von der Behandlung der Ausgabe durch PowerShell-Funktionen, bei der alles an die Pipeline weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="10305-149">This is fundamentally different from how PowerShell functions handle output, where everything goes to the pipeline.</span></span>

<span data-ttu-id="10305-150">Nicht abschließende Fehler, die aus einer Klassenmethode in den Fehler Datenstrom geschrieben wurden, werden nicht durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="10305-150">Non-terminating errors written to the error stream from inside a class method are not passed through.</span></span> <span data-ttu-id="10305-151">Sie müssen verwenden `throw` , um einen abschließenden Fehler zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="10305-151">You must use `throw` to surface a terminating error.</span></span>
<span data-ttu-id="10305-152">Mithilfe der `Write-*` Cmdlets können Sie weiterhin in PowerShell-Ausgabedaten Ströme innerhalb einer Klassenmethode schreiben.</span><span class="sxs-lookup"><span data-stu-id="10305-152">Using the `Write-*` cmdlets, you can still write to PowerShell's output streams from within a class method.</span></span> <span data-ttu-id="10305-153">Dies sollte jedoch vermieden werden, damit die-Methode nur dann-Objekte ausgibt, wenn die-Anweisung verwendet wird `return` .</span><span class="sxs-lookup"><span data-stu-id="10305-153">However, this should be avoided so that the method emits objects using only the `return` statement.</span></span>

### <a name="method-output"></a><span data-ttu-id="10305-154">Methoden Ausgabe</span><span class="sxs-lookup"><span data-stu-id="10305-154">Method output</span></span>

<span data-ttu-id="10305-155">Dieses Beispiel zeigt keine versehentliche Ausgabe an die Pipeline aus Klassen Methoden, mit Ausnahme der- `return` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="10305-155">This example demonstrates no accidental output to the pipeline from class methods, except on the `return` statement.</span></span>

```powershell
class FunWithIntegers
{
    [int[]]$Integers = 0..10

    [int[]]GetOddIntegers(){
        return $this.Integers.Where({ ($_ % 2) })
    }

    [void] GetEvenIntegers(){
        # this following line doesn't go to the pipeline
        $this.Integers.Where({ ($_ % 2) -eq 0})
    }

    [string]SayHello(){
        # this following line doesn't go to the pipeline
        "Good Morning"

        # this line goes to the pipeline
        return "Hello World"
    }
}

$ints = [FunWithIntegers]::new()
$ints.GetOddIntegers()
$ints.GetEvenIntegers()
$ints.SayHello()
```

```Output
1
3
5
7
9
Hello World

```

## <a name="constructor"></a><span data-ttu-id="10305-156">Konstruktor</span><span class="sxs-lookup"><span data-stu-id="10305-156">Constructor</span></span>

<span data-ttu-id="10305-157">Konstruktoren ermöglichen es Ihnen, Standardwerte festzulegen und die Objekt Logik zu validieren, wenn die Instanz der-Klasse erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="10305-157">Constructors enable you to set default values and validate object logic at the moment of creating the instance of the class.</span></span> <span data-ttu-id="10305-158">Konstruktoren haben den gleichen Namen wie die Klasse.</span><span class="sxs-lookup"><span data-stu-id="10305-158">Constructors have the same name as the class.</span></span> <span data-ttu-id="10305-159">Konstruktoren können Argumente aufweisen, um die Datenmember des neuen Objekts zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="10305-159">Constructors might have arguments, to initialize the data members of the new object.</span></span>

<span data-ttu-id="10305-160">Für die-Klasse können NULL oder mehr Konstruktoren definiert werden.</span><span class="sxs-lookup"><span data-stu-id="10305-160">The class can have zero or more constructors defined.</span></span> <span data-ttu-id="10305-161">Wenn kein Konstruktor definiert ist, erhält die Klasse einen Parameter losen Standardkonstruktor.</span><span class="sxs-lookup"><span data-stu-id="10305-161">If no constructor is defined, the class is given a default parameterless constructor.</span></span> <span data-ttu-id="10305-162">Dieser Konstruktor initialisiert alle Member mit ihren Standardwerten.</span><span class="sxs-lookup"><span data-stu-id="10305-162">This constructor initializes all members to their default values.</span></span> <span data-ttu-id="10305-163">Objekttypen und Zeichen folgen werden NULL-Werte zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="10305-163">Object types and strings are given null values.</span></span> <span data-ttu-id="10305-164">Wenn Sie Konstruktor definieren, wird kein standardparameterloser Konstruktor erstellt.</span><span class="sxs-lookup"><span data-stu-id="10305-164">When you define constructor, no default parameterless constructor is created.</span></span> <span data-ttu-id="10305-165">Erstellen Sie einen Parameter losen Konstruktor, wenn ein solcher benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="10305-165">Create a parameterless constructor if one is needed.</span></span>

### <a name="constructor-basic-syntax"></a><span data-ttu-id="10305-166">Grundlegende Konstruktorsyntax</span><span class="sxs-lookup"><span data-stu-id="10305-166">Constructor basic syntax</span></span>

<span data-ttu-id="10305-167">In diesem Beispiel wird die Geräteklasse mit Eigenschaften und einem Konstruktor definiert.</span><span class="sxs-lookup"><span data-stu-id="10305-167">In this example, the Device class is defined with properties and a constructor.</span></span>
<span data-ttu-id="10305-168">Um diese Klasse verwenden zu können, muss der Benutzer Werte für die Parameter angeben, die im Konstruktor aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="10305-168">To use this class, the user is required to provide values for the parameters listed in the constructor.</span></span>

```powershell
class Device {
    [string]$Brand
    [string]$Model
    [string]$VendorSku

    Device(
        [string]$b,
        [string]$m,
        [string]$vsk
    ){
        $this.Brand = $b
        $this.Model = $m
        $this.VendorSku = $vsk
    }
}

[Device]$surface = [Device]::new("Microsoft", "Surface Pro 4", "5072641000")

$surface
```

```Output
Brand     Model         VendorSku
-----     -----         ---------
Microsoft Surface Pro 4 5072641000
```

### <a name="example-with-multiple-constructors"></a><span data-ttu-id="10305-169">Beispiel mit mehreren Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="10305-169">Example with multiple constructors</span></span>

<span data-ttu-id="10305-170">In diesem Beispiel wird die **Geräte** Klasse mit Eigenschaften, einem Standardkonstruktor und einem Konstruktor zum Initialisieren der Instanz definiert.</span><span class="sxs-lookup"><span data-stu-id="10305-170">In this example, the **Device** class is defined with properties, a default constructor, and a constructor to initialize the instance.</span></span>

<span data-ttu-id="10305-171">Der Standardkonstruktor legt die **Marke** auf "nicht **definiert** " fest und verlässt die **Modell** **-und Hersteller-SKU** mit NULL-Werten.</span><span class="sxs-lookup"><span data-stu-id="10305-171">The default constructor sets the **brand** to **Undefined** , and leaves **model** and **vendor-sku** with null values.</span></span>

```powershell
class Device {
    [string]$Brand
    [string]$Model
    [string]$VendorSku

    Device(){
        $this.Brand = 'Undefined'
    }

    Device(
        [string]$b,
        [string]$m,
        [string]$vsk
    ){
        $this.Brand = $b
        $this.Model = $m
        $this.VendorSku = $vsk
    }
}

[Device]$somedevice = [Device]::new()
[Device]$surface = [Device]::new("Microsoft", "Surface Pro 4", "5072641000")

$somedevice
$surface
```

```Output
Brand       Model           VendorSku
-----       -----           ---------
Undefined
Microsoft   Surface Pro 4   5072641000
```

## <a name="hidden-attribute"></a><span data-ttu-id="10305-172">Hidden-Attribut</span><span class="sxs-lookup"><span data-stu-id="10305-172">Hidden attribute</span></span>

<span data-ttu-id="10305-173">Das-Attribut blendet `hidden` eine Eigenschaft oder Methode aus.</span><span class="sxs-lookup"><span data-stu-id="10305-173">The `hidden` attribute hides a property or method.</span></span> <span data-ttu-id="10305-174">Der Benutzer kann weiterhin auf die Eigenschaft oder Methode zugreifen und ist in allen Bereichen verfügbar, in denen das Objekt verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="10305-174">The property or method is still accessible to the user and is available in all scopes in which the object is available.</span></span> <span data-ttu-id="10305-175">Ausgeblendete Member werden aus dem `Get-Member` Cmdlet ausgeblendet und können nicht mit der Befehlszeilen Ergänzung oder IntelliSense außerhalb der Klassendefinition angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="10305-175">Hidden members are hidden from the `Get-Member` cmdlet and can't be displayed using tab completion or IntelliSense outside the class definition.</span></span>

<span data-ttu-id="10305-176">Weitere Informationen finden Sie unter [About_hidden](About_hidden.md).</span><span class="sxs-lookup"><span data-stu-id="10305-176">For more information, see [About_hidden](About_hidden.md).</span></span>

### <a name="example-using-hidden-attributes"></a><span data-ttu-id="10305-177">Beispiel für die Verwendung verborgener Attribute</span><span class="sxs-lookup"><span data-stu-id="10305-177">Example using hidden attributes</span></span>

<span data-ttu-id="10305-178">Wenn ein **Rack** -Objekt erstellt wird, ist die Anzahl der Slots für Geräte ein fester Wert, der zu keinem Zeitpunkt geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="10305-178">When a **Rack** object is created, the number of slots for devices is a fixed value that shouldn't be changed at any time.</span></span> <span data-ttu-id="10305-179">Dieser Wert wird zum Zeitpunkt der Erstellung bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="10305-179">This value is known at creation time.</span></span>

<span data-ttu-id="10305-180">Die Verwendung des ausgeblendeten Attributs ermöglicht es dem Entwickler, die Anzahl der eingeblendeten Slots beizubehalten und unbeabsichtigte Änderungen an der Größe des Racks zu hindern.</span><span class="sxs-lookup"><span data-stu-id="10305-180">Using the hidden attribute allows the developer to keep the number of slots hidden and prevents unintentional changes the size of the rack.</span></span>

```powershell
class Device {
    [string]$Brand
    [string]$Model
}

class Rack {
    [int] hidden $Slots = 8
    [string]$Brand
    [string]$Model
    [Device[]]$Devices = [Device[]]::new($this.Slots)

    Rack ([string]$b, [string]$m, [int]$capacity){
        ## argument validation here

        $this.Brand = $b
        $this.Model = $m
        $this.Slots = $capacity

        ## reset rack size to new capacity
        $this.Devices = [Device[]]::new($this.Slots)
    }
}

[Rack]$r1 = [Rack]::new("Microsoft", "Surface Pro 4", 16)

$r1
$r1.Devices.Length
$r1.Slots
```

```Output
Brand     Model         Devices
-----     -----         -------
Microsoft Surface Pro 4 {$null, $null, $null, $null...}
16
16
```

<span data-ttu-id="10305-181">Die Eigenschaft " **Slots** " wird in der Ausgabe nicht angezeigt `$r1` .</span><span class="sxs-lookup"><span data-stu-id="10305-181">Notice **Slots** property isn't shown in `$r1` output.</span></span> <span data-ttu-id="10305-182">Die Größe wurde jedoch vom Konstruktor geändert.</span><span class="sxs-lookup"><span data-stu-id="10305-182">However, the size was changed by the constructor.</span></span>

## <a name="static-attribute"></a><span data-ttu-id="10305-183">Statisches Attribut</span><span class="sxs-lookup"><span data-stu-id="10305-183">Static attribute</span></span>

<span data-ttu-id="10305-184">Das `static` -Attribut definiert eine Eigenschaft oder eine Methode, die in der Klasse vorhanden ist und keine Instanz benötigt.</span><span class="sxs-lookup"><span data-stu-id="10305-184">The `static` attribute defines a property or a method that exists in the class and needs no instance.</span></span>

<span data-ttu-id="10305-185">Eine statische Eigenschaft ist unabhängig von der Klassen Instanziierung immer verfügbar.</span><span class="sxs-lookup"><span data-stu-id="10305-185">A static property is always available, independent of class instantiation.</span></span> <span data-ttu-id="10305-186">Eine statische Eigenschaft wird für alle Instanzen der Klasse freigegeben.</span><span class="sxs-lookup"><span data-stu-id="10305-186">A static property is shared across all instances of the class.</span></span> <span data-ttu-id="10305-187">Eine statische Methode ist immer verfügbar.</span><span class="sxs-lookup"><span data-stu-id="10305-187">A static method is available always.</span></span> <span data-ttu-id="10305-188">Alle statischen Eigenschaften werden für die gesamte Sitzungs Spanne Live angezeigt.</span><span class="sxs-lookup"><span data-stu-id="10305-188">All static properties live for the entire session span.</span></span>

### <a name="example-using-static-attributes-and-methods"></a><span data-ttu-id="10305-189">Beispiel für die Verwendung statischer Attribute und Methoden</span><span class="sxs-lookup"><span data-stu-id="10305-189">Example using static attributes and methods</span></span>

<span data-ttu-id="10305-190">Nehmen Sie an, dass die hier instanziierten Racks im Rechenzentrum vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="10305-190">Assume the racks instantiated here exist in your data center.</span></span> <span data-ttu-id="10305-191">Sie möchten also die Racks in Ihrem Code nachverfolgen.</span><span class="sxs-lookup"><span data-stu-id="10305-191">So, you would like to keep track of the racks in your code.</span></span>

```powershell
class Device {
    [string]$Brand
    [string]$Model
}

class Rack {
    hidden [int] $Slots = 8
    static [Rack[]]$InstalledRacks = @()
    [string]$Brand
    [string]$Model
    [string]$AssetId
    [Device[]]$Devices = [Device[]]::new($this.Slots)

    Rack ([string]$b, [string]$m, [string]$id, [int]$capacity){
        ## argument validation here

        $this.Brand = $b
        $this.Model = $m
        $this.AssetId = $id
        $this.Slots = $capacity

        ## reset rack size to new capacity
        $this.Devices = [Device[]]::new($this.Slots)

        ## add rack to installed racks
        [Rack]::InstalledRacks += $this
    }

    static [void]PowerOffRacks(){
        foreach ($rack in [Rack]::InstalledRacks) {
            Write-Warning ("Turning off rack: " + ($rack.AssetId))
        }
    }
}
```

### <a name="testing-static-property-and-method-exist"></a><span data-ttu-id="10305-192">Das Testen der statischen Eigenschaft und Methode ist vorhanden.</span><span class="sxs-lookup"><span data-stu-id="10305-192">Testing static property and method exist</span></span>

```
PS> [Rack]::InstalledRacks.Length
0

PS> [Rack]::PowerOffRacks()

PS> (1..10) | ForEach-Object {
>>   [Rack]::new("Adatum Corporation", "Standard-16",
>>     $_.ToString("Std0000"), 16)
>> } > $null

PS> [Rack]::InstalledRacks.Length
10

PS> [Rack]::InstalledRacks[3]
Brand              Model       AssetId Devices
-----              -----       ------- -------
Adatum Corporation Standard-16 Std0004 {$null, $null, $null, $null...}

PS> [Rack]::PowerOffRacks()
WARNING: Turning off rack: Std0001
WARNING: Turning off rack: Std0002
WARNING: Turning off rack: Std0003
WARNING: Turning off rack: Std0004
WARNING: Turning off rack: Std0005
WARNING: Turning off rack: Std0006
WARNING: Turning off rack: Std0007
WARNING: Turning off rack: Std0008
WARNING: Turning off rack: Std0009
WARNING: Turning off rack: Std0010
```

<span data-ttu-id="10305-193">Beachten Sie, dass die Anzahl der Racks bei jedem Ausführen dieses Beispiels zunimmt.</span><span class="sxs-lookup"><span data-stu-id="10305-193">Notice that the number of racks increases each time you run this example.</span></span>

## <a name="property-validation-attributes"></a><span data-ttu-id="10305-194">Eigenschafts Validierungs Attribute</span><span class="sxs-lookup"><span data-stu-id="10305-194">Property validation attributes</span></span>

<span data-ttu-id="10305-195">Über Validierungs Attribute können Sie testen, ob die den Eigenschaften gegebenen Werte den definierten Anforderungen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="10305-195">Validation attributes allow you to test that values given to properties meet defined requirements.</span></span> <span data-ttu-id="10305-196">Die Validierung wird in dem Moment ausgelöst, in dem der Wert zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="10305-196">Validation is triggered the moment that the value is assigned.</span></span> <span data-ttu-id="10305-197">Siehe [about_functions_advanced_parameters](about_functions_advanced_parameters.md).</span><span class="sxs-lookup"><span data-stu-id="10305-197">See [about_functions_advanced_parameters](about_functions_advanced_parameters.md).</span></span>

### <a name="example-using-validation-attributes"></a><span data-ttu-id="10305-198">Beispiel für die Verwendung von Validierungs Attributen</span><span class="sxs-lookup"><span data-stu-id="10305-198">Example using validation attributes</span></span>

```powershell
class Device {
    [ValidateNotNullOrEmpty()][string]$Brand
    [ValidateNotNullOrEmpty()][string]$Model
}

[Device]$dev = [Device]::new()

Write-Output "Testing dev"
$dev

$dev.Brand = ""
```

```Output
Testing dev

Brand Model
----- -----

Exception setting "Brand": "The argument is null or empty. Provide an
argument that is not null or empty, and then try the command again."
At C:\tmp\Untitled-5.ps1:11 char:1
+ $dev.Brand = ""
+ ~~~~~~~~~~~~~~~
    + CategoryInfo          : NotSpecified: (:) [], SetValueInvocationException
    + FullyQualifiedErrorId : ExceptionWhenSetting
```

## <a name="inheritance-in-powershell-classes"></a><span data-ttu-id="10305-199">Vererbung in PowerShell-Klassen</span><span class="sxs-lookup"><span data-stu-id="10305-199">Inheritance in PowerShell classes</span></span>

<span data-ttu-id="10305-200">Sie können eine Klasse erweitern, indem Sie eine neue Klasse erstellen, die von einer vorhandenen Klasse abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="10305-200">You can extend a class by creating a new class that derives from an existing class.</span></span> <span data-ttu-id="10305-201">Die abgeleitete Klasse erbt die Eigenschaften der Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="10305-201">The derived class inherits the properties of the base class.</span></span> <span data-ttu-id="10305-202">Sie können Methoden und Eigenschaften nach Bedarf hinzufügen oder überschreiben.</span><span class="sxs-lookup"><span data-stu-id="10305-202">You can add or override methods and properties as required.</span></span>

<span data-ttu-id="10305-203">PowerShell unterstützt keine Mehrfachvererbung.</span><span class="sxs-lookup"><span data-stu-id="10305-203">PowerShell does not support multiple inheritance.</span></span> <span data-ttu-id="10305-204">Klassen können nicht von mehr als einer Klasse erben.</span><span class="sxs-lookup"><span data-stu-id="10305-204">Classes cannot inherit from more than one class.</span></span> <span data-ttu-id="10305-205">Sie können jedoch Schnittstellen zu diesem Zweck verwenden.</span><span class="sxs-lookup"><span data-stu-id="10305-205">However, you can use interfaces for that purpose.</span></span>

<span data-ttu-id="10305-206">Die Vererbungs Implementierung wird vom- `:` Operator definiert. Dies bedeutet, diese Klasse zu erweitern oder diese Schnittstellen zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="10305-206">Inheritance implementation is defined by the `:` operator; which means to extend this class or implements these interfaces.</span></span> <span data-ttu-id="10305-207">Die abgeleitete Klasse sollte immer ganz links in der Klassen Deklaration sein.</span><span class="sxs-lookup"><span data-stu-id="10305-207">The derived class should always be leftmost in the class declaration.</span></span>

### <a name="example-using-simple-inheritance-syntax"></a><span data-ttu-id="10305-208">Beispiel für die einfache Vererbungs Syntax</span><span class="sxs-lookup"><span data-stu-id="10305-208">Example using simple inheritance syntax</span></span>

<span data-ttu-id="10305-209">Dieses Beispiel zeigt die einfache Vererbungs Syntax für die PowerShell-Klasse.</span><span class="sxs-lookup"><span data-stu-id="10305-209">This example shows the simple PowerShell class inheritance syntax.</span></span>

```powershell
Class Derived : Base {...}
```

<span data-ttu-id="10305-210">Dieses Beispiel zeigt eine Vererbung mit einer Schnittstellen Deklaration, die hinter der-Basisklasse steht.</span><span class="sxs-lookup"><span data-stu-id="10305-210">This example shows inheritance with an interface declaration coming after the base class.</span></span>

```powershell
Class Derived : Base, Interface {...}
```

### <a name="example-of-simple-inheritance-in-powershell-classes"></a><span data-ttu-id="10305-211">Beispiel für einfache Vererbung in PowerShell-Klassen</span><span class="sxs-lookup"><span data-stu-id="10305-211">Example of simple inheritance in PowerShell classes</span></span>

<span data-ttu-id="10305-212">In diesem Beispiel sind die in den vorherigen Beispielen verwendeten **Rack** -und **Geräte** Klassen besser definiert für: Vermeiden von Eigenschafts Wiederholungen, besseres Ausrichten allgemeiner Eigenschaften und wieder verwenden allgemeiner Geschäftslogik.</span><span class="sxs-lookup"><span data-stu-id="10305-212">In this example the **Rack** and **Device** classes used in the previous examples are better defined to: avoid property repetitions, better align common properties, and reuse common business logic.</span></span>

<span data-ttu-id="10305-213">Die meisten Objekte im Rechenzentrum sind Unternehmensressourcen. Dies ist sinnvoll, um Sie als Ressourcen zu verfolgen.</span><span class="sxs-lookup"><span data-stu-id="10305-213">Most objects in the data center are company assets, which makes sense to start tracking them as assets.</span></span> <span data-ttu-id="10305-214">Gerätetypen werden von der- `DeviceType` Enumeration definiert. Weitere Informationen zu Enumerationen finden Sie unter [about_Enum](about_Enum.md) .</span><span class="sxs-lookup"><span data-stu-id="10305-214">Device types are defined by the `DeviceType` enumeration, see [about_Enum](about_Enum.md) for details on enumerations.</span></span>

<span data-ttu-id="10305-215">In unserem Beispiel definieren wir nur `Rack` und `ComputeServer` ; beide Erweiterungen der- `Device` Klasse.</span><span class="sxs-lookup"><span data-stu-id="10305-215">In our example, we're only defining `Rack` and `ComputeServer`; both extensions to the `Device` class.</span></span>

```powershell
enum DeviceType {
    Undefined = 0
    Compute = 1
    Storage = 2
    Networking = 4
    Communications = 8
    Power = 16
    Rack = 32
}

class Asset {
    [string]$Brand
    [string]$Model
}

class Device : Asset {
    hidden [DeviceType]$devtype = [DeviceType]::Undefined
    [string]$Status

    [DeviceType] GetDeviceType(){
        return $this.devtype
    }
}

class ComputeServer : Device {
    hidden [DeviceType]$devtype = [DeviceType]::Compute
    [string]$ProcessorIdentifier
    [string]$Hostname
}

class Rack : Device {
    hidden [DeviceType]$devtype = [DeviceType]::Rack
    hidden [int]$Slots = 8

    [string]$Datacenter
    [string]$Location
    [Device[]]$Devices = [Device[]]::new($this.Slots)

    Rack (){
        ## Just create the default rack with 8 slots
    }

    Rack ([int]$s){
        ## Add argument validation logic here
        $this.Devices = [Device[]]::new($s)
    }

    [void] AddDevice([Device]$dev, [int]$slot){
        ## Add argument validation logic here
        $this.Devices[$slot] = $dev
    }

    [void] RemoveDevice([int]$slot){
        ## Add argument validation logic here
        $this.Devices[$slot] = $null
    }
}

$FirstRack = [Rack]::new(16)
$FirstRack.Status = "Operational"
$FirstRack.Datacenter = "PNW"
$FirstRack.Location = "F03R02.J10"

(0..15).ForEach({
    $ComputeServer = [ComputeServer]::new()
    $ComputeServer.Brand = "Fabrikam, Inc."       ## Inherited from Asset
    $ComputeServer.Model = "Fbk5040"              ## Inherited from Asset
    $ComputeServer.Status = "Installed"           ## Inherited from Device
    $ComputeServer.ProcessorIdentifier = "x64"    ## ComputeServer
    $ComputeServer.Hostname = ("r1s" + $_.ToString("000")) ## ComputeServer
    $FirstRack.AddDevice($ComputeServer, $_)
  })

$FirstRack
$FirstRack.Devices
```

```Output
Datacenter : PNW
Location   : F03R02.J10
Devices    : {r1s000, r1s001, r1s002, r1s003...}
Status     : Operational
Brand      :
Model      :

ProcessorIdentifier : x64
Hostname            : r1s000
Status              : Installed
Brand               : Fabrikam, Inc.
Model               : Fbk5040

ProcessorIdentifier : x64
Hostname            : r1s001
Status              : Installed
Brand               : Fabrikam, Inc.
Model               : Fbk5040

<... content truncated here for brevity ...>

ProcessorIdentifier : x64
Hostname            : r1s015
Status              : Installed
Brand               : Fabrikam, Inc.
Model               : Fbk5040
```

### <a name="calling-base-class-constructors"></a><span data-ttu-id="10305-216">Aufrufen von Basisklassenkonstruktoren</span><span class="sxs-lookup"><span data-stu-id="10305-216">Calling base class constructors</span></span>

<span data-ttu-id="10305-217">Um einen Basisklassenkonstruktor aus einer Unterklasse aufzurufen, fügen Sie das- `base` Schlüsselwort hinzu.</span><span class="sxs-lookup"><span data-stu-id="10305-217">To invoke a base class constructor from a subclass, add the `base` keyword.</span></span>

```powershell
class Person {
    [int]$Age

    Person([int]$a)
    {
        $this.Age = $a
    }
}

class Child : Person
{
    [string]$School

    Child([int]$a, [string]$s ) : base($a) {
        $this.School = $s
    }
}

[Child]$littleone = [Child]::new(10, "Silver Fir Elementary School")

$littleone.Age
```

```Output

10
```

### <a name="invoke-base-class-methods"></a><span data-ttu-id="10305-218">Aufrufen von Basisklassen Methoden</span><span class="sxs-lookup"><span data-stu-id="10305-218">Invoke base class methods</span></span>

<span data-ttu-id="10305-219">Wenn Sie vorhandene Methoden in Unterklassen überschreiben möchten, deklarieren Sie Methoden mit dem gleichen Namen und der gleichen Signatur.</span><span class="sxs-lookup"><span data-stu-id="10305-219">To override existing methods in subclasses, declare methods using the same name and signature.</span></span>

```powershell
class BaseClass
{
    [int]days() {return 1}
}
class ChildClass1 : BaseClass
{
    [int]days () {return 2}
}

[ChildClass1]::new().days()
```

```Output

2
```

<span data-ttu-id="10305-220">Zum Aufrufen von Basisklassen Methoden aus überschriebenen Implementierungen wandeln Sie beim Aufruf in die Basisklasse ([BaseClass] $This) um.</span><span class="sxs-lookup"><span data-stu-id="10305-220">To call base class methods from overridden implementations, cast to the base class ([baseclass]$this) on invocation.</span></span>

```powershell
class BaseClass
{
    [int]days() {return 1}
}
class ChildClass1 : BaseClass
{
    [int]days () {return 2}
    [int]basedays() {return ([BaseClass]$this).days()}
}

[ChildClass1]::new().days()
[ChildClass1]::new().basedays()
```

```Output

2
1
```

### <a name="inheriting-from-interfaces"></a><span data-ttu-id="10305-221">Erben von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="10305-221">Inheriting from interfaces</span></span>

<span data-ttu-id="10305-222">PowerShell-Klassen können eine Schnittstelle implementieren, die dieselbe Vererbungs Syntax verwendet, mit der Basisklassen erweitert werden.</span><span class="sxs-lookup"><span data-stu-id="10305-222">PowerShell classes can implement an interface using the same inheritance syntax used to extend base classes.</span></span> <span data-ttu-id="10305-223">Da Schnittstellen mehrere Vererbung zulassen, kann eine PowerShell-Klasse, die eine Schnittstelle implementiert, von mehreren Typen erben, indem die Typnamen nach dem Doppelpunkt ( `:` ) durch Kommas () getrennt werden `,` .</span><span class="sxs-lookup"><span data-stu-id="10305-223">Because interfaces allow multiple inheritance, a PowerShell class implementing an interface may inherit from multiple types, by separating the type names after the colon (`:`) with commas (`,`).</span></span> <span data-ttu-id="10305-224">Eine PowerShell-Klasse, die eine Schnittstelle implementiert, muss alle Member dieser Schnittstelle implementieren.</span><span class="sxs-lookup"><span data-stu-id="10305-224">A PowerShell class that implements an interface must implement all the members of that interface.</span></span> <span data-ttu-id="10305-225">Das Weglassen der Schnittstellenmember der Implementierung verursacht einen Analysefehler im Skript.</span><span class="sxs-lookup"><span data-stu-id="10305-225">Omitting the implemention interface members causes a parse-time error in the script.</span></span>

> [!NOTE]
> <span data-ttu-id="10305-226">PowerShell unterstützt derzeit nicht das Deklarieren neuer Schnittstellen im PowerShell-Skript.</span><span class="sxs-lookup"><span data-stu-id="10305-226">PowerShell does not currently support declaring new interfaces in PowerShell script.</span></span>

```powershell
class MyComparable : System.IComparable
{
    [int] CompareTo([object] $obj)
    {
        return 0;
    }
}

class MyComparableBar : bar, System.IComparable
{
    [int] CompareTo([object] $obj)
    {
        return 0;
    }
}
```

## <a name="importing-classes-from-a-powershell-module"></a><span data-ttu-id="10305-227">Importieren von Klassen aus einem PowerShell-Modul</span><span class="sxs-lookup"><span data-stu-id="10305-227">Importing classes from a PowerShell module</span></span>

<span data-ttu-id="10305-228">`Import-Module` und die- `#requires` Anweisung importiert nur die Modulfunktionen, Aliase und Variablen, wie vom Modul definiert.</span><span class="sxs-lookup"><span data-stu-id="10305-228">`Import-Module` and the `#requires` statement only import the module functions, aliases, and variables, as defined by the module.</span></span> <span data-ttu-id="10305-229">Klassen werden nicht importiert.</span><span class="sxs-lookup"><span data-stu-id="10305-229">Classes are not imported.</span></span> <span data-ttu-id="10305-230">Die- `using module` Anweisung importiert die im Modul definierten Klassen.</span><span class="sxs-lookup"><span data-stu-id="10305-230">The `using module` statement imports the classes defined in the module.</span></span> <span data-ttu-id="10305-231">Wenn das Modul nicht in die aktuelle Sitzung geladen wird, `using` schlägt die Anweisung fehl.</span><span class="sxs-lookup"><span data-stu-id="10305-231">If the module isn't loaded in the current session, the `using` statement fails.</span></span> <span data-ttu-id="10305-232">Weitere Informationen zur- `using` Anweisung finden Sie unter [about_Using](about_Using.md).</span><span class="sxs-lookup"><span data-stu-id="10305-232">For more information about the `using` statement, see [about_Using](about_Using.md).</span></span>

## <a name="the-psreference-type-is-not-supported-with-class-members"></a><span data-ttu-id="10305-233">Der psreference-Typ wird für Klassenmember nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="10305-233">The PSReference type is not supported with class members</span></span>

<span data-ttu-id="10305-234">Wenn Sie die `[ref]` Typumwandlung mit einem Klassenmember verwenden, tritt ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="10305-234">Using the `[ref]` type-cast with a class member silently fails.</span></span> <span data-ttu-id="10305-235">APIs, die `[ref]` Parameter verwenden, können nicht mit Klassenmembern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="10305-235">APIs that use `[ref]` parameters cannot be used with class members.</span></span> <span data-ttu-id="10305-236">Der **psreference** wurde zur Unterstützung von COM-Objekten entwickelt.</span><span class="sxs-lookup"><span data-stu-id="10305-236">The **PSReference** was designed to support COM objects.</span></span> <span data-ttu-id="10305-237">COM-Objekte verfügen über Fälle, in denen Sie einen Wert als Verweis übergeben müssen.</span><span class="sxs-lookup"><span data-stu-id="10305-237">COM objects have cases where you need to pass a value in by reference.</span></span>

<span data-ttu-id="10305-238">Weitere Informationen zum- `[ref]` Typ finden Sie unter [psreference-Klasse](/dotnet/api/system.management.automation.psreference).</span><span class="sxs-lookup"><span data-stu-id="10305-238">For more information about the `[ref]` type, see [PSReference Class](/dotnet/api/system.management.automation.psreference).</span></span>

## <a name="see-also"></a><span data-ttu-id="10305-239">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="10305-239">See also</span></span>

- [<span data-ttu-id="10305-240">About_hidden</span><span class="sxs-lookup"><span data-stu-id="10305-240">About_hidden</span></span>](About_hidden.md)
- [<span data-ttu-id="10305-241">about_Enum</span><span class="sxs-lookup"><span data-stu-id="10305-241">about_Enum</span></span>](about_Enum.md)
- [<span data-ttu-id="10305-242">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="10305-242">about_Language_Keywords</span></span>](about_language_keywords.md)
- [<span data-ttu-id="10305-243">about_Methods</span><span class="sxs-lookup"><span data-stu-id="10305-243">about_Methods</span></span>](about_methods.md)
- [<span data-ttu-id="10305-244">about_Using</span><span class="sxs-lookup"><span data-stu-id="10305-244">about_Using</span></span>](about_using.md)
