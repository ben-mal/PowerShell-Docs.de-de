---
description: Beschreibt, wie Sie-Klassen verwenden können, um in PowerShell mit DSC (DSC) zu entwickeln.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 1/11/2019
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/about/about_classes_and_dsc?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Classes_and_DSC
ms.openlocfilehash: 21a013bb817367dd2a11cc0826263d0f3203796b
ms.sourcegitcommit: cc72c40315fd2981d3009b335accbfa52d57640c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/30/2020
ms.locfileid: "96349828"
---
# <a name="about-classes-and-desired-state-configuration"></a>Informationen zu Klassen und zur Konfiguration des gewünschten Zustands

## <a name="short-description"></a>Kurze Beschreibung

Beschreibt, wie Sie-Klassen verwenden können, um in PowerShell mit DSC (DSC) zu entwickeln.

## <a name="long-description"></a>Lange Beschreibung

Ab Windows PowerShell 5,0 wurde Sprache zum Definieren von Klassen und anderen benutzerdefinierten Typen hinzugefügt, indem formale Syntax und Semantik verwendet werden, die mit anderen objektorientierten Programmiersprachen vergleichbar sind. Ziel ist es, Entwicklern und IT-Experten zu ermöglichen, Windows PowerShell für eine größere Anzahl von Anwendungsfällen zu nutzen, die Entwicklung von PowerShell-Artefakten (z. b. DSC-Ressourcen) zu vereinfachen und die Abdeckung von Verwaltungs Oberflächen zu beschleunigen.

## <a name="supported-scenarios"></a>Unterstützte Szenarios

Die folgenden Szenarien werden unterstützt:

- Definieren Sie DSC-Ressourcen und die zugehörigen Typen mithilfe der PowerShell-Sprache.
- Definieren Sie benutzerdefinierte Typen in PowerShell mithilfe vertrauter objektorientierter Programmierkonstrukte, wie z. b. Klassen, Eigenschaften, Methoden und Vererbung.
- Debuggen Sie Typen mithilfe der PowerShell-Sprache.
- Generieren und behandeln von Ausnahmen mithilfe von formalen Mechanismen und auf der richtigen Ebene.

## <a name="define-dsc-resources-with-classes"></a>Definieren von DSC-Ressourcen mit Klassen

Abgesehen von den Syntax Änderungen sind die wichtigsten Unterschiede zwischen einer Klassen definierten DSC-Ressource und einem DSC-Ressourcenanbieter für Cmdlets die folgenden Elemente:

- Eine MOF-Datei (Management Object Format) ist nicht erforderlich.
- Der Unterordner DSCResource im Ordner „module“ ist nicht erforderlich.
- Eine PowerShell-Moduldatei kann mehrere DSC-Ressourcenklassen enthalten.

## <a name="create-a-class-defined-dsc-resource-provider"></a>Erstellen eines Klassen definierten DSC-Ressourcen Anbieters

Das folgende Beispiel ist ein Klassen definierter DSC-Ressourcenanbieter, der als Modul mydscresource. psm1 gespeichert wird. Sie müssen immer eine Schlüsseleigenschaft in einen Klassen definierten DSC-Ressourcenanbieter einschließen.

```powershell
enum Ensure
{
    Absent
    Present
}

<#
    This resource manages the file in a specific path.
    [DscResource()] indicates the class is a DSC resource
#>

[DscResource()]
class FileResource
{
    <#
        This property is the fully qualified path to the file that is
        expected to be present or absent.

        The [DscProperty(Key)] attribute indicates the property is a
        key and its value uniquely identifies a resource instance.
        Defining this attribute also means the property is required
        and DSC will ensure a value is set before calling the resource.

        A DSC resource must define at least one key property.
    #>
    [DscProperty(Key)]
    [string]$Path

    <#
        This property indicates if the settings should be present or absent
        on the system. For present, the resource ensures the file pointed
        to by $Path exists. For absent, it ensures the file point to by
        $Path does not exist.

        The [DscProperty(Mandatory)] attribute indicates the property is
        required and DSC will guarantee it is set.

        If Mandatory is not specified or if it is defined as
        Mandatory=$false, the value is not guaranteed to be set when DSC
        calls the resource.  This is appropriate for optional properties.
    #>
    [DscProperty(Mandatory)]
    [Ensure] $Ensure

    <#
        This property defines the fully qualified path to a file that will
        be placed on the system if $Ensure = Present and $Path does not
        exist.

        NOTE: This property is required because [DscProperty(Mandatory)] is
        set.
    #>
    [DscProperty(Mandatory)]
    [string] $SourcePath

    <#
        This property reports the file's create timestamp.

        [DscProperty(NotConfigurable)] attribute indicates the property is
        not configurable in DSC configuration.  Properties marked this way
        are populated by the Get() method to report additional details
        about the resource when it is present.

    #>
    [DscProperty(NotConfigurable)]
    [Nullable[datetime]] $CreationTime

    <#
        This method is equivalent of the Set-TargetResource script function.
        It sets the resource to the desired state.
    #>
    [void] Set()
    {
        $fileExists = $this.TestFilePath($this.Path)
        if($this.ensure -eq [Ensure]::Present)
        {
            if(-not $fileExists)
            {
                $this.CopyFile()
            }
        }
        else
        {
            if($fileExists)
            {
                Write-Verbose -Message "Deleting the file $($this.Path)"
                Remove-Item -LiteralPath $this.Path -Force
            }
        }
    }

    <#

        This method is equivalent of the Test-TargetResource script
        function. It should return True or False, showing whether the
        resource is in a desired state.
    #>
    [bool] Test()
    {
        $present = $this.TestFilePath($this.Path)

        if($this.Ensure -eq [Ensure]::Present)
        {
            return $present
        }
        else
{
            return -not $present
        }
    }

    <#
        This method is equivalent of the Get-TargetResource script function.
        The implementation should use the keys to find appropriate
        resources. This method returns an instance of this class with the
        updated key properties.
    #>
    [FileResource] Get()
    {
        $present = $this.TestFilePath($this.Path)

        if ($present)
        {
            $file = Get-ChildItem -LiteralPath $this.Path
            $this.CreationTime = $file.CreationTime
            $this.Ensure = [Ensure]::Present
        }
        else
        {
            $this.CreationTime = $null
            $this.Ensure = [Ensure]::Absent
        }
        return $this
    }

    <#
        Helper method to check if the file exists and it is correct file
    #>
    [bool] TestFilePath([string] $location)
    {
        $present = $true

        $item = Get-ChildItem -LiteralPath $location -ea Ignore
        if ($null -eq $item)
        {
            $present = $false
        }
        elseif( $item.PSProvider.Name -ne "FileSystem")
        {
            throw "Path $($location) is not a file path."
        }
        elseif($item.PSIsContainer)
        {
            throw "Path $($location) is a directory path."
        }
        return $present
    }

    <#
        Helper method to copy file from source to path
    #>
    [void] CopyFile()
    {
        if(-not $this.TestFilePath($this.SourcePath))
        {
            throw "SourcePath $($this.SourcePath) is not found."
        }

        [System.IO.FileInfo]
        $destFileInfo = new-object System.IO.FileInfo($this.Path)

        if (-not $destFileInfo.Directory.Exists)
        {
            $FullName = $destFileInfo.Directory.FullName
            $Message = "Creating directory $FullName"

            Write-Verbose -Message $Message

            #use CreateDirectory instead of New-Item to avoid code
            # to handle the non-terminating error
            [System.IO.Directory]::CreateDirectory($FullName)
        }

        if(Test-Path -LiteralPath $this.Path -PathType Container)
        {
            throw "Path $($this.Path) is a directory path"
        }

        Write-Verbose -Message "Copying $this.SourcePath to $this.Path"

        #DSC engine catches and reports any error that occurs
        Copy-Item -Path $this.SourcePath -Destination $this.Path -Force
    }
}
```

## <a name="create-a-module-manifest"></a>Erstellen eines Modul Manifests

Nach dem Erstellen des klassenbasierten DSC-Ressourcenanbieters und dessen Speicherung als Modul erstellen Sie ein Modulmanifest für das Modul. Um eine klassenbasierte Ressource für die DSC-Engine verfügbar zu machen, müssen Sie eine `DscResourcesToExport`-Anweisung zur Manifestdatei hinzufügen, die die Engine anweist, die Ressource zu exportieren. Bei diesem Beispiel wird das folgende Modulmanifest als MyDscResource.psd1 gespeichert.

```powershell
@{

# Script module or binary module file associated with this manifest.
RootModule = 'MyDscResource.psm1'

DscResourcesToExport = 'FileResource'

# Version number of this module.
ModuleVersion = '1.0'

# ID used to uniquely identify this module
GUID = '81624038-5e71-40f8-8905-b1a87afe22d7'

# Author of this module
Author = 'Microsoft Corporation'

# Company or vendor of this module
CompanyName = 'Microsoft Corporation'

# Copyright statement for this module
Copyright = '(c) 2014 Microsoft. All rights reserved.'

# Description of the functionality provided by this module
# Description = ''

# Minimum version of the PowerShell engine required by this module
PowerShellVersion = '5.0'

# Name of the PowerShell host required by this module
# PowerShellHostName = ''

}
```

## <a name="deploy-a-dsc-resource-provider"></a>Bereitstellen eines DSC-Ressourcen Anbieters

Stellen Sie den neuen DSC-Ressourcenanbieter bereit, indem Sie in oder einen Ordner mydscresource erstellen `$pshome\Modules` `$env:SystemDrive\ProgramFiles\WindowsPowerShell\Modules` .

Sie müssen nicht den Unterordner „DSCResource“ erstellen. Kopieren Sie die Modul- und Modulmanifestdatei (MyDscResource.psm1 und MyDscResource.psd1) in den Ordner MyDscResource.

Anschließend muss wie bei allen anderen DSC-Ressourcen ein Konfigurationsskript erstellt und ausgeführt werden.

## <a name="create-a-dsc-configuration-script"></a>Erstellen eines DSC-Konfigurationsskripts

Nachdem Sie die Klasse und die Manifestdateien, wie zuvor beschrieben, in der Ordnerstruktur gespeichert haben, können Sie eine Konfiguration erstellen, die die neue Ressource verwendet. Die folgende Konfiguration verweist auf das Modul mydscresource. Speichern Sie die Konfiguration als Skript, MyResource.ps1.

Informationen dazu, wie Sie eine DSC-Konfiguration ausführen, finden Sie unter [Windows PowerShell](/powershell/scripting/dsc/overview/dscforengineers)DSC.

Erstellen Sie vor dem Ausführen der Konfiguration `C:\test.txt` . Die Konfiguration überprüft, ob die Datei unter vorhanden ist `c:\test\test.txt` . Wenn die Datei nicht vorhanden ist, wird die Datei von der Konfiguration kopiert `C:\test.txt` .

```powershell
Configuration Test
{
    Import-DSCResource -module MyDscResource
    FileResource file
    {
        Path = "C:\test\test.txt"
        SourcePath = "C:\test.txt"
        Ensure = "Present"
    }
}
Test
Start-DscConfiguration -Wait -Force Test
```

Führen Sie dieses Skript wie ein beliebiges DSC-Konfigurationsskript aus. Führen Sie zum Starten der Konfiguration in einer PowerShell-Konsole mit erhöhten Rechten Folgendes aus:

`PS C:\test> .\MyResource.ps1`

## <a name="inheritance-in-powershell-classes"></a>Vererbung in PowerShell-Klassen

### <a name="declare-base-classes-for-powershell-classes"></a>Deklarieren von Basisklassen für PowerShell-Klassen

Sie können eine PowerShell-Klasse als Basistyp für eine andere PowerShell-Klasse deklarieren, wie im folgenden Beispiel gezeigt, in dem **Frucht** ein Basistyp für **Apple** ist.

```powershell
class fruit
{
    [int]sold() {return 100500}
}

class apple : fruit {}
    [apple]::new().sold() # return 100500
```

### <a name="declare-implemented-interfaces-for-powershell-classes"></a>Deklarieren Sie implementierte Schnittstellen für PowerShell-Klassen

Sie können implementierte Schnittstellen nach Basis Typen oder unmittelbar nach einem Doppelpunkt () deklarieren, `:` Wenn kein Basistyp angegeben ist. Trennen Sie alle Typnamen durch Kommas. Dies ähnelt der c#-Syntax.

```powershell
class MyComparable : system.IComparable
{
    [int] CompareTo([object] $obj)
    {
        return 0;
    }
}

class MyComparableTest : test, system.IComparable
{
    [int] CompareTo([object] $obj)
    {
        return 0;
    }
}
```

### <a name="call-base-class-constructors"></a>Basisklassenkonstruktoren abrufen

Um einen Basisklassenkonstruktor aus einer Unterklasse aufzurufen, fügen Sie das- `base` Schlüsselwort hinzu, wie im folgenden Beispiel gezeigt:

```powershell
class A {
    [int]$a
    A([int]$a)
    {
        $this.a = $a
    }
}

class B : A
{
    B() : base(103) {}
}

    [B]::new().a # return 103
```

Wenn eine Basisklasse über einen Standardkonstruktor (keine Parameter) verfügt, können Sie wie gezeigt einen expliziten konstruktorbefehl weglassen.

```powershell
class C : B
{
    C([int]$c) {}
}
```

### <a name="call-base-class-methods"></a>Methoden zum Abrufen von Basisklassen

Sie können vorhandene Methoden in Unterklassen überschreiben. Um die Überschreibung zu überschreiben, deklarieren Sie Methoden mit dem gleichen Namen und der gleichen Signatur.

```powershell
class baseClass
{
    [int]days() {return 100500}
}
class childClass1 : baseClass
{
    [int]days () {return 200600}
}

    [childClass1]::new().days() # return 200600
```

Zum Aufrufen von Basisklassen Methoden aus überschriebenen Implementierungen wandeln Sie beim Aufruf in die Basisklasse um `([baseclass]$this)` .

```powershell
class childClass2 : baseClass
{
    [int]days()
    {
        return 3 * ([baseClass]$this).days()
    }
}

    [childClass2]::new().days() # return 301500
```

Alle PowerShell-Methoden sind virtuell. Sie können nicht virtuelle .NET-Methoden in einer Unterklasse ausblenden, indem Sie dieselbe Syntax wie für eine außer Kraft Setzung verwenden: Deklarieren Sie Methoden mit dem gleichen Namen und der gleichen Signatur.

```powershell
class MyIntList : system.collections.generic.list[int]
{
    # Add is final in system.collections.generic.list
    [void] Add([int]$arg)
    {
        ([system.collections.generic.list[int]]$this).Add($arg * 2)
    }
}

$list = [MyIntList]::new()
$list.Add(100)
$list[0] # return 200
```

### <a name="current-limitations-with-class-inheritance"></a>Aktuelle Einschränkungen bei der Klassen Vererbung

Eine Einschränkung bei der Klassen Vererbung besteht darin, dass keine Syntax zum Deklarieren von Schnittstellen in PowerShell vorhanden ist.

## <a name="defining-custom-types-in-powershell"></a>Definieren benutzerdefinierter Typen in PowerShell

In Windows PowerShell 5,0 wurden mehrere Sprachelemente eingeführt.

### <a name="class-keyword"></a>Schlüsselwort „Class“

Definiert eine neue Klasse.
Das `class` Schlüsselwort ist ein true-.NET Framework Typs.
Klassenmember sind öffentlich.

```powershell
class MyClass
{
}
```

### <a name="enum-keyword-and-enumerations"></a>Schlüsselwort „enum“ und Enumerationen

Es wurde Unterstützung für das `enum` -Schlüsselwort hinzugefügt und ist eine Breaking Change. Das `enum` Trennzeichen ist zurzeit ein Zeilen Trennzeichen. Eine Problem Umgehung für diejenigen, die bereits verwenden, `enum` besteht darin, ein kaufmännisches und-( `&` ) vor dem Wort einzufügen. Aktuelle Einschränkungen: Sie können einen Enumerator nicht im Hinblick auf sich selbst definieren, aber Sie können `enum` die Initialisierung im Hinblick auf einen anderen durchlaufen `enum` , wie im folgenden Beispiel gezeigt:

Der Basistyp kann derzeit nicht angegeben werden. Der Basistyp ist immer [int].

```powershell
enum Color2
{
    Yellow = [Color]::Blue
}
```

Ein Enumeratorwert muss eine Konstante zur Analysezeit sein. Der Enumeratorwert kann nicht auf das Ergebnis eines aufgerufenen Befehls festgelegt werden.

```powershell
enum MyEnum
{
    Enum1
    Enum2
    Enum3 = 42
    Enum4 = [int]::MaxValue
}
```

`Enum` unterstützt arithmetische Operationen, wie im folgenden Beispiel gezeigt:

```powershell
enum SomeEnum { Max = 42 }
enum OtherEnum { Max = [SomeEnum]::Max + 1 }
```

### <a name="hidden-keyword"></a>Hidden-Schlüsselwort

Das `hidden` Schlüsselwort, das in Windows PowerShell 5,0 eingeführt wurde, verbirgt Klassenmember aus Standard `Get-Member` Ergebnissen. Geben Sie die Hidden-Eigenschaft an, wie in der folgenden Zeile dargestellt:

```powershell
hidden [type] $classmember = <value>
```

Ausgeblendete Member werden nicht mit der Vervollständigung mit der Tab-Taste oder mit IntelliSense angezeigt, es sei denn, der Abschluss tritt in der Klasse auf, die

Das neue Attribut **System. Management. Automation. hiddenattribute** wurde hinzugefügt, sodass der c#-Code in PowerShell die gleiche Semantik aufweisen kann.

Weitere Informationen finden Sie unter [about_Hidden](../../Microsoft.PowerShell.Core/About/about_hidden.md).

### <a name="import-dscresource"></a>Import-DscResource

`Import-DscResource` ist jetzt ein tatsächlich dynamisches Schlüsselwort. PowerShell analysiert das Stammmodul des angegebenen Moduls und sucht Klassen, die das DscResource-Attribut enthalten.

### <a name="properties"></a>Eigenschaften

Ein neues Feld, `ImplementingAssembly` , wurde hinzugefügt `ModuleInfo` . , Wenn das Skript Klassen definiert, oder die geladene Assembly für binäre Module `ImplementingAssembly` auf die dynamische Assembly festgelegt ist, die für ein Skript Modul erstellt wurde. Falls „ModuleType = Manifest“, wird es nicht festgelegt.

Die Reflektion für das `ImplementingAssembly` Feld ermittelt Ressourcen in einem Modul. Dies bedeutet, dass Sie Ressourcen ermitteln können, die in PowerShell oder anderen verwalteten Sprachen geschrieben wurden.

Felder mit Initialisierern.

`[int] $i = 5`

Static wird unterstützt und funktioniert wie ein Attribut, sodass es in beliebiger Reihenfolge angegeben werden kann.

`static [int] $count = 0`

Ein Typ ist optional.

`$s = "hello"`

Alle Member sind öffentlich. Eigenschaften erfordern ein Zeilenumbruchzeichen oder Semikolon. Wenn kein Objekttyp angegeben ist, ist der Eigenschaftentyp **Object**.

### <a name="constructors-and-instantiation"></a>Konstruktoren und Instanziierung

PowerShell-Klassen können Konstruktoren haben, die denselben Namen wie Ihre Klasse haben. Konstruktoren können überladen werden. Statische Konstruktoren werden unterstützt.
Eigenschaften mit Initialisierungsausdrücken werden vor dem Ausführen von Code in einem Konstruktor initialisiert. Statische Eigenschaften werden vor dem Hauptteil eines statischen Konstruktors initialisiert. Instanzeigenschaften werden vor dem Hauptteil des nicht statischen Konstruktors initialisiert. Derzeit gibt es keine Syntax zum Aufrufen eines Konstruktors von einem anderen Konstruktor, wie z. b. der c#-Syntax: `": this()")` . Eine Behelfslösung ist das Definieren einer allgemeinen „Init“-Methode.

Es folgen Methoden zum Instanziieren von Klassen:

- Instanziieren mithilfe des Standardkonstruktors. Beachten Sie, dass `New-Object` in dieser Version nicht unterstützt wird.

  `$a = [MyClass]::new()`

- Aufrufen eines Konstruktors mit einem Parameter.

  `$b = [MyClass]::new(42)`

- Übergeben ein Arrays an einen Konstruktor mit mehreren Parametern

  `$c = [MyClass]::new(@(42,43,44), "Hello")`

In dieser Version ist der Typname nur lexikalisch sichtbar, was bedeutet, dass er außerhalb des Moduls oder Skripts, das die Klasse definiert, nicht sichtbar ist. Funktionen können Instanzen einer Klasse zurückgeben, die in PowerShell definiert ist, und Instanzen funktionieren gut außerhalb des Moduls oder Skripts.

Der `Get-Member` **statische** Parameter listet Konstruktoren auf, sodass Sie über Ladungen wie andere Methoden anzeigen können. Die Leistung dieser Syntax ist auch erheblich schneller als `New-Object`.

Die pseudostatische Methode **new** funktioniert mit .NET-Typen, wie im folgenden Beispiel gezeigt. `[hashtable]::new()`

Sie können jetzt Konstruktorüberladungen mit `Get-Member` oder wie in diesem Beispiel anzeigen:

```powershell
[hashtable]::new
OverloadDefinitions
-------------------
hashtable new()
hashtable new(int capacity)
hashtable new(int capacity, float loadFactor)
```

### <a name="methods"></a>Methoden

Eine PowerShell-Klassenmethode wird als **Skriptblock** mit nur einem „end“-Block implementiert. Alle Methoden sind öffentlich. Nachstehend sehen Sie ein Beispiel der Definition einer Methode namens **DoSomething**.

```powershell
class MyClass
{
    DoSomething($x)
    {
        $this._doSomething($x)       # method syntax
    }
    private _doSomething($a) {}
}
```

### <a name="method-invocation"></a>Methodenaufruf

Überladene Methoden werden unterstützt. Überladene Methoden werden genauso benannt wie eine vorhandene Methode, unterscheiden sich jedoch durch die angegebenen Werte.

```powershell
$b = [MyClass]::new()
$b.DoSomething(42)
```

### <a name="invocation"></a>Aufruf

Siehe [Methodenaufruf](#method-invocation).

### <a name="attributes"></a>Attribute

Es wurden drei neue Attribute hinzugefügt: `DscResource` , `DscResourceKey` und `DscResourceMandatory` .

### <a name="return-types"></a>Rückgabetypen

Der Rückgabetyp ist ein Vertrag. Der Rückgabewert wird in den erwarteten Typ konvertiert.
Falls kein Rückgabetyp angegeben wird, ist der Rückgabetyp „void“. Es gibt kein Streaming von Objekten, und Objekte können entweder absichtlich oder versehentlich nicht in die Pipeline geschrieben werden.

### <a name="lexical-scoping-of-variables"></a>Lexikalische Eingrenzung von Variablen

Das folgende Beispiel zeigt, wie die lexikalische Eingrenzung in dieser Version funktioniert.

```powershell
$d = 42  # Script scope

function bar
{
    $d = 0  # Function scope
    [MyClass]::DoSomething()
}

class MyClass
{
    static [object] DoSomething()
    {
        return $d  # error, not found dynamically
        return $script:d # no error

        $d = $script:d
        return $d # no error, found lexically
    }
}

$v = bar
$v -eq $d # true
```

## <a name="example-create-custom-classes"></a>Beispiel: Erstellen von benutzerdefinierten Klassen

Das folgende Beispiel erstellt mehrere neue, benutzerdefinierte Klassen, um eine HTML-DSL (Dynamic Stylesheet Language) zu implementieren. Im Beispiel werden Hilfsfunktionen hinzugefügt, um bestimmte Elementtypen als Teil der Element Klasse zu erstellen, z. b. Überschrift Stile und Tabellen, da Typen nicht außerhalb des Gültigkeits Bereichs eines Moduls verwendet werden können.

```powershell
# Classes that define the structure of the document
#
class Html
{
    [string] $docType
    [HtmlHead] $Head
    [Element[]] $Body

    [string] Render()
    {
        $text = "<html>`n<head>`n"
        $text += $Head
        $text += "`n</head>`n<body>`n"
        $text += $Body -join "`n" # Render all of the body elements
        $text += "</body>`n</html>"
        return $text
    }
    [string] ToString() { return $this.Render() }
}

class HtmlHead
{
    $Title
    $Base
    $Link
    $Style
    $Meta
    $Script
    [string] Render() { return "<title>$Title</title>" }
    [string] ToString() { return $this.Render() }
}

class Element
{
    [string] $Tag
    [string] $Text
    [hashtable] $Attributes
    [string] Render() {
        $attributesText= ""
        if ($Attributes)
        {
            foreach ($attr in $Attributes.Keys)
            {
                $attributesText = " $attr=`"$($Attributes[$attr])`""
            }
        }

        return "<${tag}${attributesText}>$text</$tag>`n"
    }
    [string] ToString() { return $this.Render() }
}

#
# Helper functions for creating specific element types on top of the classes.
# These are required because types aren't visible outside of the module.
#
function H1 {[Element] @{Tag = "H1"; Text = $args.foreach{$_} -join " "}}
function H2 {[Element] @{Tag = "H2"; Text = $args.foreach{$_} -join " "}}
function H3 {[Element] @{Tag = "H3"; Text = $args.foreach{$_} -join " "}}
function P  {[Element] @{Tag = "P" ; Text = $args.foreach{$_} -join " "}}
function B  {[Element] @{Tag = "B" ; Text = $args.foreach{$_} -join " "}}
function I  {[Element] @{Tag = "I" ; Text = $args.foreach{$_} -join " "}}
function HREF
{
    param (
        $Name,
        $Link
    )

    return [Element] @{
        Tag = "A"
        Attributes = @{ HREF = $link }
        Text = $name
    }
}
function Table
{
    param (
        [Parameter(Mandatory)]
        [object[]]
            $Data,
        [Parameter()]
        [string[]]
            $Properties = "*",
        [Parameter()]
        [hashtable]
            $Attributes = @{ border=2; cellpadding=2; cellspacing=2 }
    )

    $bodyText = ""
    # Add the header tags
    $bodyText +=  $Properties.foreach{TH $_}
    # Add the rows
    $bodyText += foreach ($row in $Data)
                {
                            TR (-join $Properties.Foreach{ TD ($row.$_) } )
                }

    $table = [Element] @{
                Tag = "Table"
                Attributes = $Attributes
                Text = $bodyText
            }
    $table
}
function TH  {([Element] @{Tag="TH"; Text=$args.foreach{$_} -join " "})}
function TR  {([Element] @{Tag="TR"; Text=$args.foreach{$_} -join " "})}
function TD  {([Element] @{Tag="TD"; Text=$args.foreach{$_} -join " "})}

function Style
{
    return  [Element]  @{
        Tag = "style"
        Text = "$args"
    }
}

# Takes a hash table, casts it to and HTML document
# and then returns the resulting type.
#
function Html ([HTML] $doc) { return $doc }
```

## <a name="see-also"></a>Siehe auch

[about_DesiredStateConfiguration](../../Microsoft.PowerShell.Core/About/about_desiredstateconfiguration.md)

[about_Enum](../../Microsoft.PowerShell.Core/About/about_Enum.md)

[about_Hidden](../../Microsoft.PowerShell.Core/About/about_hidden.md)

[about_Language_Keywords](../../Microsoft.PowerShell.Core/About/about_Language_Keywords.md)

[about_Methods](../../Microsoft.PowerShell.Core/About/about_Methods.md)

[Erstellen von benutzerdefinierten Windows PowerShell DSC-Ressourcen](/powershell/scripting/dsc/resources/authoringResource)
