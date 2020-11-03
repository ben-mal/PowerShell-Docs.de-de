---
description: Beschreibt, wie Sie Klassen verwenden können, um eigene benutzerdefinierte Typen zu erstellen.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 09/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_classes?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Classes
ms.openlocfilehash: e4e3379c18b8e63e5c494b71485d6dab5c7689f2
ms.sourcegitcommit: 16d62a98449e3ddaf8d7c65bc1848ede1fd8a3e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2020
ms.locfileid: "93219972"
---
# <a name="about-classes"></a>Informationen zu Klassen

## <a name="short-description"></a>Kurze Beschreibung
Beschreibt, wie Sie Klassen verwenden können, um eigene benutzerdefinierte Typen zu erstellen.

## <a name="long-description"></a>Lange Beschreibung

PowerShell 5,0 fügt eine formale Syntax zum Definieren von Klassen und anderen benutzerdefinierten Typen hinzu. Das Hinzufügen von Klassen ermöglicht Entwicklern und IT-Experten die Übernahme von PowerShell für eine größere Anzahl von Anwendungsfällen. Es vereinfacht die Entwicklung von PowerShell-Artefakten und beschleunigt die Abdeckung von Verwaltungs Oberflächen.

Eine Klassen Deklaration ist eine Blaupause, mit der Instanzen von Objekten zur Laufzeit erstellt werden. Wenn Sie eine Klasse definieren, ist der Klassenname der Name des Typs. Wenn Sie z. b. eine Klasse mit dem Namen " **Device** " deklarieren und eine Variable `$dev` für eine neue Instanz des **Geräts** initialisieren, `$dev` ist ein Objekt oder eine Instanz vom Typ " **Device** ". Jede Instanz des **Geräts** kann unterschiedliche Werte in den zugehörigen Eigenschaften aufweisen.

## <a name="supported-scenarios"></a>Unterstützte Szenarien

- Definieren Sie benutzerdefinierte Typen in PowerShell mithilfe der vertrauten objektorientierten Programmier Semantik wie Klassen, Eigenschaften, Methoden, Vererbung usw.
- Debuggen Sie Typen mithilfe der PowerShell-Sprache.
- Generieren und behandeln von Ausnahmen mithilfe von formalen Mechanismen
- Definieren Sie DSC-Ressourcen und die zugehörigen Typen mithilfe der PowerShell-Sprache.

## <a name="syntax"></a>Syntax

Klassen werden mit der folgenden Syntax deklariert:

```syntax
class <class-name> [: [<base-class>][,<interface-list]] {
    [[<attribute>] [hidden] [static] <property-definition> ...]
    [<class-name>([<constructor-argument-list>])
      {<constructor-statement-list>} ...]
    [[<attribute>] [hidden] [static] <method-definition> ...]
}
```

Klassen werden mit einer der folgenden Syntaxen instanziiert:

```syntax
[$<variable-name> =] New-Object -TypeName <class-name> [
  [-ArgumentList] <constructor-argument-list>]
```

```syntax
[$<variable-name> =] [<class-name>]::new([<constructor-argument-list>])
```

> [!NOTE]
> Wenn Sie die `[<class-name>]::new()` Syntax verwenden, sind eckige Klammern um den Klassennamen obligatorisch. Die Klammern signalisieren eine Typdefinition für PowerShell.

### <a name="example-syntax-and-usage"></a>Syntax und Verwendung von Beispielen

Dieses Beispiel zeigt die minimale Syntax, die zum Erstellen einer verwendbaren Klasse benötigt wird.

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

## <a name="class-properties"></a>Klasseneigenschaften

Eigenschaften sind im Klassen Gültigkeitsbereich deklarierte Variablen. Eine Eigenschaft kann ein beliebiger integrierter Typ oder eine Instanz einer anderen Klasse sein. Klassen haben keine Einschränkung in der Anzahl der Eigenschaften, die Sie besitzen.

### <a name="example-class-with-simple-properties"></a>Beispiel Klasse mit einfachen Eigenschaften

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

### <a name="example-complex-types-in-class-properties"></a>Komplexe Beispiel Typen in Klasseneigenschaften

In diesem Beispiel wird eine leere **Rack** -Klasse mithilfe der **Device** -Klasse definiert. In den folgenden Beispielen wird gezeigt, wie Sie dem Rack Geräte hinzufügen und mit einem vorab geladenen Gestell beginnen.

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

## <a name="class-methods"></a>Klassen Methoden

Methoden definieren die Aktionen, die von einer Klasse ausgeführt werden können. Methoden können Parameter annehmen, die Eingabedaten bereitstellen. Methoden können die Ausgabe zurückgeben. Von einer Methode zurückgegebene Daten können einen beliebigen definierten Datentyp aufweisen.

Wenn Sie eine Methode für eine Klasse definieren, verweisen Sie mit der automatischen Variablen auf das aktuelle Klassenobjekt `$this` . Auf diese Weise können Sie auf Eigenschaften und andere Methoden zugreifen, die in der aktuellen Klasse definiert sind.

### <a name="example-simple-class-with-properties-and-methods"></a>Beispiel für eine einfache Klasse mit Eigenschaften und Methoden

Erweitern der **Rack** -Klasse zum Hinzufügen und Entfernen von Geräten zu oder daraus.

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

## <a name="output-in-class-methods"></a>Ausgabe in Klassen Methoden

Für Methoden muss ein Rückgabetyp definiert werden. Wenn eine Methode keine Ausgabe zurückgibt, sollte der Ausgabetyp sein `[void]` .

In Klassen Methoden werden keine Objekte an die Pipeline gesendet, außer den in der- `return` Anweisung erwähnten. Es gibt keine versehentliche Ausgabe an die Pipeline aus dem Code.

> [!NOTE]
> Dies unterscheidet sich grundlegend von der Behandlung der Ausgabe durch PowerShell-Funktionen, bei der alles an die Pipeline weitergeleitet wird.

Nicht abschließende Fehler, die aus einer Klassenmethode in den Fehler Datenstrom geschrieben wurden, werden nicht durchlaufen. Sie müssen verwenden `throw` , um einen abschließenden Fehler zu verwenden.
Mithilfe der `Write-*` Cmdlets können Sie weiterhin in PowerShell-Ausgabedaten Ströme innerhalb einer Klassenmethode schreiben. Dies sollte jedoch vermieden werden, damit die-Methode nur dann-Objekte ausgibt, wenn die-Anweisung verwendet wird `return` .

### <a name="method-output"></a>Methoden Ausgabe

Dieses Beispiel zeigt keine versehentliche Ausgabe an die Pipeline aus Klassen Methoden, mit Ausnahme der- `return` Anweisung.

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

## <a name="constructor"></a>Konstruktor

Konstruktoren ermöglichen es Ihnen, Standardwerte festzulegen und die Objekt Logik zu validieren, wenn die Instanz der-Klasse erstellt wird. Konstruktoren haben den gleichen Namen wie die Klasse. Konstruktoren können Argumente aufweisen, um die Datenmember des neuen Objekts zu initialisieren.

Für die-Klasse können NULL oder mehr Konstruktoren definiert werden. Wenn kein Konstruktor definiert ist, erhält die Klasse einen Parameter losen Standardkonstruktor. Dieser Konstruktor initialisiert alle Member mit ihren Standardwerten. Objekttypen und Zeichen folgen werden NULL-Werte zugewiesen. Wenn Sie Konstruktor definieren, wird kein standardparameterloser Konstruktor erstellt. Erstellen Sie einen Parameter losen Konstruktor, wenn ein solcher benötigt wird.

### <a name="constructor-basic-syntax"></a>Grundlegende Konstruktorsyntax

In diesem Beispiel wird die Geräteklasse mit Eigenschaften und einem Konstruktor definiert.
Um diese Klasse verwenden zu können, muss der Benutzer Werte für die Parameter angeben, die im Konstruktor aufgeführt sind.

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

### <a name="example-with-multiple-constructors"></a>Beispiel mit mehreren Konstruktoren

In diesem Beispiel wird die **Geräte** Klasse mit Eigenschaften, einem Standardkonstruktor und einem Konstruktor zum Initialisieren der Instanz definiert.

Der Standardkonstruktor legt die **Marke** auf "nicht **definiert** " fest und verlässt die **Modell** **-und Hersteller-SKU** mit NULL-Werten.

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

## <a name="hidden-attribute"></a>Hidden-Attribut

Das-Attribut blendet `hidden` eine Eigenschaft oder Methode aus. Der Benutzer kann weiterhin auf die Eigenschaft oder Methode zugreifen und ist in allen Bereichen verfügbar, in denen das Objekt verfügbar ist. Ausgeblendete Member werden aus dem `Get-Member` Cmdlet ausgeblendet und können nicht mit der Befehlszeilen Ergänzung oder IntelliSense außerhalb der Klassendefinition angezeigt werden.

Weitere Informationen finden Sie unter [About_hidden](About_hidden.md).

### <a name="example-using-hidden-attributes"></a>Beispiel für die Verwendung verborgener Attribute

Wenn ein **Rack** -Objekt erstellt wird, ist die Anzahl der Slots für Geräte ein fester Wert, der zu keinem Zeitpunkt geändert werden sollte. Dieser Wert wird zum Zeitpunkt der Erstellung bezeichnet.

Die Verwendung des ausgeblendeten Attributs ermöglicht es dem Entwickler, die Anzahl der eingeblendeten Slots beizubehalten und unbeabsichtigte Änderungen an der Größe des Racks zu hindern.

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

Die Eigenschaft " **Slots** " wird in der Ausgabe nicht angezeigt `$r1` . Die Größe wurde jedoch vom Konstruktor geändert.

## <a name="static-attribute"></a>Statisches Attribut

Das `static` -Attribut definiert eine Eigenschaft oder eine Methode, die in der Klasse vorhanden ist und keine Instanz benötigt.

Eine statische Eigenschaft ist unabhängig von der Klassen Instanziierung immer verfügbar. Eine statische Eigenschaft wird für alle Instanzen der Klasse freigegeben. Eine statische Methode ist immer verfügbar. Alle statischen Eigenschaften werden für die gesamte Sitzungs Spanne Live angezeigt.

### <a name="example-using-static-attributes-and-methods"></a>Beispiel für die Verwendung statischer Attribute und Methoden

Nehmen Sie an, dass die hier instanziierten Racks im Rechenzentrum vorhanden sind. Sie möchten also die Racks in Ihrem Code nachverfolgen.

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

### <a name="testing-static-property-and-method-exist"></a>Das Testen der statischen Eigenschaft und Methode ist vorhanden.

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

Beachten Sie, dass die Anzahl der Racks bei jedem Ausführen dieses Beispiels zunimmt.

## <a name="property-validation-attributes"></a>Eigenschafts Validierungs Attribute

Über Validierungs Attribute können Sie testen, ob die den Eigenschaften gegebenen Werte den definierten Anforderungen entsprechen. Die Validierung wird in dem Moment ausgelöst, in dem der Wert zugewiesen wird. Siehe [about_functions_advanced_parameters](about_functions_advanced_parameters.md).

### <a name="example-using-validation-attributes"></a>Beispiel für die Verwendung von Validierungs Attributen

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

## <a name="inheritance-in-powershell-classes"></a>Vererbung in PowerShell-Klassen

Sie können eine Klasse erweitern, indem Sie eine neue Klasse erstellen, die von einer vorhandenen Klasse abgeleitet wird. Die abgeleitete Klasse erbt die Eigenschaften der Basisklasse. Sie können Methoden und Eigenschaften nach Bedarf hinzufügen oder überschreiben.

PowerShell unterstützt keine Mehrfachvererbung. Klassen können nicht von mehr als einer Klasse erben. Sie können jedoch Schnittstellen zu diesem Zweck verwenden.

Die Vererbungs Implementierung wird vom- `:` Operator definiert. Dies bedeutet, diese Klasse zu erweitern oder diese Schnittstellen zu implementieren. Die abgeleitete Klasse sollte immer ganz links in der Klassen Deklaration sein.

### <a name="example-using-simple-inheritance-syntax"></a>Beispiel für die einfache Vererbungs Syntax

Dieses Beispiel zeigt die einfache Vererbungs Syntax für die PowerShell-Klasse.

```powershell
Class Derived : Base {...}
```

Dieses Beispiel zeigt eine Vererbung mit einer Schnittstellen Deklaration, die hinter der-Basisklasse steht.

```powershell
Class Derived : Base, Interface {...}
```

### <a name="example-of-simple-inheritance-in-powershell-classes"></a>Beispiel für einfache Vererbung in PowerShell-Klassen

In diesem Beispiel sind die in den vorherigen Beispielen verwendeten **Rack** -und **Geräte** Klassen besser definiert für: Vermeiden von Eigenschafts Wiederholungen, besseres Ausrichten allgemeiner Eigenschaften und wieder verwenden allgemeiner Geschäftslogik.

Die meisten Objekte im Rechenzentrum sind Unternehmensressourcen. Dies ist sinnvoll, um Sie als Ressourcen zu verfolgen. Gerätetypen werden von der- `DeviceType` Enumeration definiert. Weitere Informationen zu Enumerationen finden Sie unter [about_Enum](about_Enum.md) .

In unserem Beispiel definieren wir nur `Rack` und `ComputeServer` ; beide Erweiterungen der- `Device` Klasse.

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

### <a name="calling-base-class-constructors"></a>Aufrufen von Basisklassenkonstruktoren

Um einen Basisklassenkonstruktor aus einer Unterklasse aufzurufen, fügen Sie das- `base` Schlüsselwort hinzu.

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

### <a name="invoke-base-class-methods"></a>Aufrufen von Basisklassen Methoden

Wenn Sie vorhandene Methoden in Unterklassen überschreiben möchten, deklarieren Sie Methoden mit dem gleichen Namen und der gleichen Signatur.

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

Zum Aufrufen von Basisklassen Methoden aus überschriebenen Implementierungen wandeln Sie beim Aufruf in die Basisklasse ([BaseClass] $This) um.

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

### <a name="inheriting-from-interfaces"></a>Erben von Schnittstellen

PowerShell-Klassen können eine Schnittstelle implementieren, die dieselbe Vererbungs Syntax verwendet, mit der Basisklassen erweitert werden. Da Schnittstellen mehrere Vererbung zulassen, kann eine PowerShell-Klasse, die eine Schnittstelle implementiert, von mehreren Typen erben, indem die Typnamen nach dem Doppelpunkt ( `:` ) durch Kommas () getrennt werden `,` . Eine PowerShell-Klasse, die eine Schnittstelle implementiert, muss alle Member dieser Schnittstelle implementieren. Das Weglassen der Schnittstellenmember der Implementierung verursacht einen Analysefehler im Skript.

> [!NOTE]
> PowerShell unterstützt derzeit nicht das Deklarieren neuer Schnittstellen im PowerShell-Skript.

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

## <a name="importing-classes-from-a-powershell-module"></a>Importieren von Klassen aus einem PowerShell-Modul

`Import-Module` und die- `#requires` Anweisung importiert nur die Modulfunktionen, Aliase und Variablen, wie vom Modul definiert. Klassen werden nicht importiert. Die- `using module` Anweisung importiert die im Modul definierten Klassen. Wenn das Modul nicht in die aktuelle Sitzung geladen wird, `using` schlägt die Anweisung fehl. Weitere Informationen zur- `using` Anweisung finden Sie unter [about_Using](about_Using.md).

## <a name="the-psreference-type-is-not-supported-with-class-members"></a>Der psreference-Typ wird für Klassenmember nicht unterstützt.

Wenn Sie die `[ref]` Typumwandlung mit einem Klassenmember verwenden, tritt ein Fehler auf. APIs, die `[ref]` Parameter verwenden, können nicht mit Klassenmembern verwendet werden. Der **psreference** wurde zur Unterstützung von COM-Objekten entwickelt. COM-Objekte verfügen über Fälle, in denen Sie einen Wert als Verweis übergeben müssen.

Weitere Informationen zum- `[ref]` Typ finden Sie unter [psreference-Klasse](/dotnet/api/system.management.automation.psreference).

## <a name="see-also"></a>Weitere Informationen:

- [About_hidden](About_hidden.md)
- [about_Enum](about_Enum.md)
- [about_Language_Keywords](about_language_keywords.md)
- [about_Methods](about_methods.md)
- [about_Using](about_using.md)
