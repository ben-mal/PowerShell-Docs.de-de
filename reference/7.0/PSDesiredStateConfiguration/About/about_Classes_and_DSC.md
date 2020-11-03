---
description: Beschreibt, wie Sie-Klassen verwenden können, um in PowerShell mit DSC (DSC) zu entwickeln.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 1/11/2019
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/about/about_classes_and_dsc?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Classes_and_DSC
ms.openlocfilehash: 272d6872d096de864044ae41449caff472bb1799
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222388"
---
# <a name="about-classes-and-desired-state-configuration"></a><span data-ttu-id="bd61c-104">Informationen zu Klassen und zur Konfiguration des gewünschten Zustands</span><span class="sxs-lookup"><span data-stu-id="bd61c-104">About Classes and Desired State Configuration</span></span>

## <a name="short-description"></a><span data-ttu-id="bd61c-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bd61c-105">Short description</span></span>

<span data-ttu-id="bd61c-106">Beschreibt, wie Sie-Klassen verwenden können, um in PowerShell mit DSC (DSC) zu entwickeln.</span><span class="sxs-lookup"><span data-stu-id="bd61c-106">Describes how you can use classes to develop in PowerShell with Desired State Configuration (DSC).</span></span>

## <a name="long-description"></a><span data-ttu-id="bd61c-107">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bd61c-107">Long description</span></span>

<span data-ttu-id="bd61c-108">Ab Windows PowerShell 5,0 wurde Sprache zum Definieren von Klassen und anderen benutzerdefinierten Typen hinzugefügt, indem formale Syntax und Semantik verwendet werden, die mit anderen objektorientierten Programmiersprachen vergleichbar sind.</span><span class="sxs-lookup"><span data-stu-id="bd61c-108">Starting in Windows PowerShell 5.0, language was added to define classes and other user-defined types, by using formal syntax and semantics that are similar to other object-oriented programming languages.</span></span> <span data-ttu-id="bd61c-109">Ziel ist es, Entwicklern und IT-Experten zu ermöglichen, PowerShell für eine größere Anzahl von Anwendungsfällen zu nutzen, die Entwicklung von PowerShell-Artefakten (z. b. DSC-Ressourcen) zu vereinfachen und die Abdeckung von Verwaltungs Oberflächen zu beschleunigen.</span><span class="sxs-lookup"><span data-stu-id="bd61c-109">The goal is to enable developers and IT professionals to embrace PowerShell for a wider range of use cases, simplify development of PowerShell artifacts such as DSC resources, and accelerate coverage of management surfaces.</span></span>

## <a name="supported-scenarios"></a><span data-ttu-id="bd61c-110">Unterstützte Szenarien</span><span class="sxs-lookup"><span data-stu-id="bd61c-110">Supported scenarios</span></span>

<span data-ttu-id="bd61c-111">Die folgenden Szenarien werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="bd61c-111">The following scenarios are supported:</span></span>

- <span data-ttu-id="bd61c-112">Definieren Sie DSC-Ressourcen und die zugehörigen Typen mithilfe der PowerShell-Sprache.</span><span class="sxs-lookup"><span data-stu-id="bd61c-112">Define DSC resources and their associated types by using the PowerShell language.</span></span>
- <span data-ttu-id="bd61c-113">Definieren Sie benutzerdefinierte Typen in PowerShell mithilfe vertrauter objektorientierter Programmierkonstrukte, wie z. b. Klassen, Eigenschaften, Methoden und Vererbung.</span><span class="sxs-lookup"><span data-stu-id="bd61c-113">Define custom types in PowerShell by using familiar object-oriented programming constructs, such as classes, properties, methods, and inheritance.</span></span>
- <span data-ttu-id="bd61c-114">Debuggen Sie Typen mithilfe der PowerShell-Sprache.</span><span class="sxs-lookup"><span data-stu-id="bd61c-114">Debug types by using the PowerShell language.</span></span>
- <span data-ttu-id="bd61c-115">Generieren und behandeln von Ausnahmen mithilfe von formalen Mechanismen und auf der richtigen Ebene.</span><span class="sxs-lookup"><span data-stu-id="bd61c-115">Generate and handle exceptions by using formal mechanisms, and at the right level.</span></span>

## <a name="define-dsc-resources-with-classes"></a><span data-ttu-id="bd61c-116">Definieren von DSC-Ressourcen mit Klassen</span><span class="sxs-lookup"><span data-stu-id="bd61c-116">Define DSC resources with classes</span></span>

<span data-ttu-id="bd61c-117">Abgesehen von den Syntax Änderungen sind die wichtigsten Unterschiede zwischen einer Klassen definierten DSC-Ressource und einem DSC-Ressourcenanbieter für Cmdlets die folgenden Elemente:</span><span class="sxs-lookup"><span data-stu-id="bd61c-117">Apart from syntax changes, the major differences between a class-defined DSC resource and a cmdlet DSC resource provider are the following items:</span></span>

- <span data-ttu-id="bd61c-118">Eine MOF-Datei (Management Object Format) ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="bd61c-118">A Management Object Format (MOF) file is not required.</span></span>
- <span data-ttu-id="bd61c-119">Der Unterordner DSCResource im Ordner „module“ ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="bd61c-119">A DSCResource subfolder in the module folder is not required.</span></span>
- <span data-ttu-id="bd61c-120">Eine PowerShell-Moduldatei kann mehrere DSC-Ressourcenklassen enthalten.</span><span class="sxs-lookup"><span data-stu-id="bd61c-120">A PowerShell module file can contain multiple DSC resource classes.</span></span>

## <a name="create-a-class-defined-dsc-resource-provider"></a><span data-ttu-id="bd61c-121">Erstellen eines Klassen definierten DSC-Ressourcen Anbieters</span><span class="sxs-lookup"><span data-stu-id="bd61c-121">Create a class-defined DSC resource provider</span></span>

<span data-ttu-id="bd61c-122">Das folgende Beispiel ist ein Klassen definierter DSC-Ressourcenanbieter, der als Modul mydscresource. psm1 gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="bd61c-122">The following example is a class-defined DSC resource provider that is saved as a module, MyDSCResource.psm1.</span></span> <span data-ttu-id="bd61c-123">Sie müssen immer eine Schlüsseleigenschaft in einen Klassen definierten DSC-Ressourcenanbieter einschließen.</span><span class="sxs-lookup"><span data-stu-id="bd61c-123">You must always include a key property in a class-defined DSC resource provider.</span></span>

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
        if ($item -eq $null)
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
# This module defines a class for a DSC "FileResource" provider.

enum Ensure
{
    Absent
    Present
}

<# This resource manages the file in a specific path.
[DscResource()] indicates the class is a DSC resource
#>

[DscResource()]
class FileResource{

    <# This is a key property
        [DscResourceKey()] also means the property is required.
        It is guaranteed to be set, other properties may not
        be set if the configuration did not specify values.
    #>
    [DscResourceKey()]
    [string]$Path

    <#
        [DscResourceMandatory()] means the property is required.
        It is guaranteed to be set, other properties may not be set
        if the configuration did not specify values.
    #>
    [DscResourceMandatory()]
    [Ensure] $Ensure

    <#
        [DscResourceMandatory()] means the property is required.
    #>
    [DscResourceMandatory()]
    [string] $SourcePath

    [DscResource

    <#
        This method replaces the Set-TargetResource DSC script function.
        It sets the resource to the desired state.
    #>
    [void] Set()
    {
        $fileExists = Test-Path -path $this.Path -PathType Leaf
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
                Write-Verbose -Message "Deleting the file $this.Path"
                Remove-Item -LiteralPath $this.Path
            }
        }
    }

    <#

        This method replaces the Test-TargetResource function.
        It should return True or False, showing whether the resource
        is in a desired state.
    #>

    [bool] Test()
    {
        if(Test-Path -path $this.Path -PathType Container)
        {
            throw "Path '$this.Path' is a directory path."
        }

        $fileExists = Test-Path -path $this.Path -PathType Leaf

        if($this.ensure -eq [Ensure]::Present)
        {
            return $fileExists
        }

        return (-not $fileExists)
    }

    <#
        This method replaces the Get-TargetResource function.
        The implementation should use the keys to find appropriate
        resources. This method returns an instance of this class with the
        updated key properties.
    #>

    [FileResource] Get()
    {
        $file = Get-item $this.Path
        return $this
    }

    <#
        Helper method to copy file from source to path.
        Because this resource provider run under system,
        Only the Administrators and system have full
        access to the new created directory and file
    #>
    CopyFile()
    {
        if(Test-Path -path $this.SourcePath -PathType Container)
        {
            throw "SourcePath '$this.SourcePath' is a directory path"
        }

        if( -not (Test-Path -path $this.SourcePath -PathType Leaf))
        {
            throw "SourcePath '$this.SourcePath' is not found."
        }

        [System.IO.FileInfo]
        $destFileInfo = new-object System.IO.FileInfo($this.Path)

        if (-not $destFileInfo.Directory.Exists)
        {
            $FullName = $destFileInfo.Directory.FullName
            $Message = "Creating directory $FullName"

            Write-Verbose -Message $Message

            #use CreateDirectory instead of New-Item to avoid lines
            # to handle the non-terminating error
            [System.IO.Directory]::CreateDirectory($FullName)
        }

        if(Test-Path -path $this.Path -PathType Container)
        {
            throw "Path '$this.Path' is a directory path"
        }

        Write-Verbose -Message "Copying $this.SourcePath to $this.Path"

        #DSC engine catches and reports any error that occurs
        Copy-Item -Path $this.SourcePath -Destination $this.Path -Force
    }
}
```

## <a name="create-a-module-manifest"></a><span data-ttu-id="bd61c-124">Erstellen eines Modul Manifests</span><span class="sxs-lookup"><span data-stu-id="bd61c-124">Create a module manifest</span></span>

<span data-ttu-id="bd61c-125">Nach dem Erstellen des klassenbasierten DSC-Ressourcenanbieters und dessen Speicherung als Modul erstellen Sie ein Modulmanifest für das Modul.</span><span class="sxs-lookup"><span data-stu-id="bd61c-125">After creating the class-defined DSC resource provider, and saving it as a module, create a module manifest for the module.</span></span> <span data-ttu-id="bd61c-126">Um eine klassenbasierte Ressource für die DSC-Engine verfügbar zu machen, müssen Sie eine `DscResourcesToExport`-Anweisung zur Manifestdatei hinzufügen, die die Engine anweist, die Ressource zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="bd61c-126">To make a class-based resource available to the DSC engine, you must include a `DscResourcesToExport` statement in the manifest file that instructs the module to export the resource.</span></span> <span data-ttu-id="bd61c-127">Bei diesem Beispiel wird das folgende Modulmanifest als MyDscResource.psd1 gespeichert.</span><span class="sxs-lookup"><span data-stu-id="bd61c-127">In this example, the following module manifest is saved as MyDscResource.psd1.</span></span>

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

## <a name="deploy-a-dsc-resource-provider"></a><span data-ttu-id="bd61c-128">Bereitstellen eines DSC-Ressourcen Anbieters</span><span class="sxs-lookup"><span data-stu-id="bd61c-128">Deploy a DSC resource provider</span></span>

<span data-ttu-id="bd61c-129">Stellen Sie den neuen DSC-Ressourcenanbieter bereit, indem Sie in oder einen Ordner mydscresource erstellen `$pshome\Modules` `$env:SystemDrive\ProgramFiles\WindowsPowerShell\Modules` .</span><span class="sxs-lookup"><span data-stu-id="bd61c-129">Deploy the new DSC resource provider by creating a MyDscResource folder in `$pshome\Modules` or `$env:SystemDrive\ProgramFiles\WindowsPowerShell\Modules`.</span></span>

<span data-ttu-id="bd61c-130">Sie müssen nicht den Unterordner „DSCResource“ erstellen.</span><span class="sxs-lookup"><span data-stu-id="bd61c-130">You do not need to create a DSCResource subfolder.</span></span> <span data-ttu-id="bd61c-131">Kopieren Sie die Modul- und Modulmanifestdatei (MyDscResource.psm1 und MyDscResource.psd1) in den Ordner MyDscResource.</span><span class="sxs-lookup"><span data-stu-id="bd61c-131">Copy the module and module manifest files (MyDscResource.psm1 and MyDscResource.psd1) to the MyDscResource folder.</span></span>

<span data-ttu-id="bd61c-132">Anschließend muss wie bei allen anderen DSC-Ressourcen ein Konfigurationsskript erstellt und ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="bd61c-132">From this point, you create and run a configuration script as you would with any DSC resource.</span></span>

## <a name="create-a-dsc-configuration-script"></a><span data-ttu-id="bd61c-133">Erstellen eines DSC-Konfigurationsskripts</span><span class="sxs-lookup"><span data-stu-id="bd61c-133">Create a DSC configuration script</span></span>

<span data-ttu-id="bd61c-134">Nachdem Sie die Klasse und die Manifestdateien, wie zuvor beschrieben, in der Ordnerstruktur gespeichert haben, können Sie eine Konfiguration erstellen, die die neue Ressource verwendet.</span><span class="sxs-lookup"><span data-stu-id="bd61c-134">After saving the class and manifest files in the folder structure as described earlier, you can create a configuration that uses the new resource.</span></span> <span data-ttu-id="bd61c-135">Die folgende Konfiguration verweist auf das Modul mydscresource.</span><span class="sxs-lookup"><span data-stu-id="bd61c-135">The following configuration references the MyDSCResource module.</span></span> <span data-ttu-id="bd61c-136">Speichern Sie die Konfiguration als Skript, MyResource.ps1.</span><span class="sxs-lookup"><span data-stu-id="bd61c-136">Save the configuration as a script, MyResource.ps1.</span></span>

<span data-ttu-id="bd61c-137">Informationen dazu, wie Sie eine DSC-Konfiguration ausführen, finden Sie unter [Windows PowerShell](/powershell/scripting/dsc/overview/dscforengineers)DSC.</span><span class="sxs-lookup"><span data-stu-id="bd61c-137">For information about how to run a DSC configuration, see [Windows PowerShell Desired State Configuration Overview](/powershell/scripting/dsc/overview/dscforengineers).</span></span>

<span data-ttu-id="bd61c-138">Erstellen Sie vor dem Ausführen der Konfiguration `C:\test.txt` .</span><span class="sxs-lookup"><span data-stu-id="bd61c-138">Before you run the configuration, create `C:\test.txt`.</span></span> <span data-ttu-id="bd61c-139">Die Konfiguration überprüft, ob die Datei unter vorhanden ist `c:\test\test.txt` .</span><span class="sxs-lookup"><span data-stu-id="bd61c-139">The configuration checks if the file exists at `c:\test\test.txt`.</span></span> <span data-ttu-id="bd61c-140">Wenn die Datei nicht vorhanden ist, wird die Datei von der Konfiguration kopiert `C:\test.txt` .</span><span class="sxs-lookup"><span data-stu-id="bd61c-140">If the file does not exist, the configuration copies the file from `C:\test.txt`.</span></span>

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

<span data-ttu-id="bd61c-141">Führen Sie dieses Skript wie ein beliebiges DSC-Konfigurationsskript aus.</span><span class="sxs-lookup"><span data-stu-id="bd61c-141">Run this script as you would any DSC configuration script.</span></span> <span data-ttu-id="bd61c-142">Führen Sie zum Starten der Konfiguration in einer PowerShell-Konsole mit erhöhten Rechten Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="bd61c-142">To start the configuration, in an elevated PowerShell console, run the following:</span></span>

`PS C:\test> .\MyResource.ps1`

## <a name="inheritance-in-powershell-classes"></a><span data-ttu-id="bd61c-143">Vererbung in PowerShell-Klassen</span><span class="sxs-lookup"><span data-stu-id="bd61c-143">Inheritance in PowerShell classes</span></span>

### <a name="declare-base-classes-for-powershell-classes"></a><span data-ttu-id="bd61c-144">Deklarieren von Basisklassen für PowerShell-Klassen</span><span class="sxs-lookup"><span data-stu-id="bd61c-144">Declare base classes for PowerShell classes</span></span>

<span data-ttu-id="bd61c-145">Sie können eine PowerShell-Klasse als Basistyp für eine andere PowerShell-Klasse deklarieren, wie im folgenden Beispiel gezeigt, in dem **Frucht** ein Basistyp für **Apple** ist.</span><span class="sxs-lookup"><span data-stu-id="bd61c-145">You can declare a PowerShell class as a base type for another PowerShell class, as shown in the following example, in which **fruit** is a base type for **apple**.</span></span>

```powershell
class fruit
{
    [int]sold() {return 100500}
}

class apple : fruit {}
    [apple]::new().sold() # return 100500
```

### <a name="declare-implemented-interfaces-for-powershell-classes"></a><span data-ttu-id="bd61c-146">Deklarieren Sie implementierte Schnittstellen für PowerShell-Klassen</span><span class="sxs-lookup"><span data-stu-id="bd61c-146">Declare implemented interfaces for PowerShell classes</span></span>

<span data-ttu-id="bd61c-147">Sie können implementierte Schnittstellen nach Basis Typen oder unmittelbar nach einem Doppelpunkt () deklarieren, `:` Wenn kein Basistyp angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="bd61c-147">You can declare implemented interfaces after base types, or immediately after a colon (`:`) if there is no base type specified.</span></span> <span data-ttu-id="bd61c-148">Trennen Sie alle Typnamen durch Kommas.</span><span class="sxs-lookup"><span data-stu-id="bd61c-148">Separate all type names by using commas.</span></span> <span data-ttu-id="bd61c-149">Dies ähnelt der c#-Syntax.</span><span class="sxs-lookup"><span data-stu-id="bd61c-149">This is similar to C# syntax.</span></span>

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

### <a name="call-base-class-constructors"></a><span data-ttu-id="bd61c-150">Basisklassenkonstruktoren abrufen</span><span class="sxs-lookup"><span data-stu-id="bd61c-150">Call base class constructors</span></span>

<span data-ttu-id="bd61c-151">Um einen Basisklassenkonstruktor aus einer Unterklasse aufzurufen, fügen Sie das- `base` Schlüsselwort hinzu, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="bd61c-151">To call a base class constructor from a subclass, add the `base` keyword, as shown in the following example:</span></span>

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

<span data-ttu-id="bd61c-152">Wenn eine Basisklasse über einen Standardkonstruktor (keine Parameter) verfügt, können Sie wie gezeigt einen expliziten konstruktorbefehl weglassen.</span><span class="sxs-lookup"><span data-stu-id="bd61c-152">If a base class has a default constructor (no parameters), you can omit an explicit constructor call, as shown.</span></span>

```powershell
class C : B
{
    C([int]$c) {}
}
```

### <a name="call-base-class-methods"></a><span data-ttu-id="bd61c-153">Methoden zum Abrufen von Basisklassen</span><span class="sxs-lookup"><span data-stu-id="bd61c-153">Call base class methods</span></span>

<span data-ttu-id="bd61c-154">Sie können vorhandene Methoden in Unterklassen überschreiben.</span><span class="sxs-lookup"><span data-stu-id="bd61c-154">You can override existing methods in subclasses.</span></span> <span data-ttu-id="bd61c-155">Um die Überschreibung zu überschreiben, deklarieren Sie Methoden mit dem gleichen Namen und der gleichen Signatur.</span><span class="sxs-lookup"><span data-stu-id="bd61c-155">To do the override, declare methods by using the same name and signature.</span></span>

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

<span data-ttu-id="bd61c-156">Zum Aufrufen von Basisklassen Methoden aus überschriebenen Implementierungen wandeln Sie beim Aufruf in die Basisklasse um `([baseclass]$this)` .</span><span class="sxs-lookup"><span data-stu-id="bd61c-156">To call base class methods from overridden implementations, cast to the base class `([baseclass]$this)` on invocation.</span></span>

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

<span data-ttu-id="bd61c-157">Alle PowerShell-Methoden sind virtuell.</span><span class="sxs-lookup"><span data-stu-id="bd61c-157">All PowerShell methods are virtual.</span></span> <span data-ttu-id="bd61c-158">Sie können nicht virtuelle .NET-Methoden in einer Unterklasse ausblenden, indem Sie dieselbe Syntax wie für eine außer Kraft Setzung verwenden: Deklarieren Sie Methoden mit dem gleichen Namen und der gleichen Signatur.</span><span class="sxs-lookup"><span data-stu-id="bd61c-158">You can hide non-virtual .NET methods in a subclass by using the same syntax as you do for an override: declare methods with same name and signature.</span></span>

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

### <a name="current-limitations-with-class-inheritance"></a><span data-ttu-id="bd61c-159">Aktuelle Einschränkungen bei der Klassen Vererbung</span><span class="sxs-lookup"><span data-stu-id="bd61c-159">Current limitations with class inheritance</span></span>

<span data-ttu-id="bd61c-160">Eine Einschränkung bei der Klassen Vererbung besteht darin, dass keine Syntax zum Deklarieren von Schnittstellen in PowerShell vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="bd61c-160">A limitation with class inheritance is that there is no syntax to declare interfaces in PowerShell.</span></span>

## <a name="defining-custom-types-in-powershell"></a><span data-ttu-id="bd61c-161">Definieren benutzerdefinierter Typen in PowerShell</span><span class="sxs-lookup"><span data-stu-id="bd61c-161">Defining custom types in PowerShell</span></span>

<span data-ttu-id="bd61c-162">In Windows PowerShell 5,0 wurden mehrere Sprachelemente eingeführt.</span><span class="sxs-lookup"><span data-stu-id="bd61c-162">Windows PowerShell 5.0 introduced several language elements.</span></span>

### <a name="class-keyword"></a><span data-ttu-id="bd61c-163">Schlüsselwort „Class“</span><span class="sxs-lookup"><span data-stu-id="bd61c-163">Class keyword</span></span>

<span data-ttu-id="bd61c-164">Definiert eine neue Klasse.</span><span class="sxs-lookup"><span data-stu-id="bd61c-164">Defines a new class.</span></span>
<span data-ttu-id="bd61c-165">Das `class` Schlüsselwort ist ein true-.NET Framework Typs.</span><span class="sxs-lookup"><span data-stu-id="bd61c-165">The `class` keyword is a true .NET Framework type.</span></span>
<span data-ttu-id="bd61c-166">Klassenmember sind öffentlich.</span><span class="sxs-lookup"><span data-stu-id="bd61c-166">Class members are public.</span></span>

```powershell
class MyClass
{
}
```

### <a name="enum-keyword-and-enumerations"></a><span data-ttu-id="bd61c-167">Schlüsselwort „enum“ und Enumerationen</span><span class="sxs-lookup"><span data-stu-id="bd61c-167">Enum keyword and enumerations</span></span>

<span data-ttu-id="bd61c-168">Es wurde Unterstützung für das `enum` -Schlüsselwort hinzugefügt und ist eine Breaking Change.</span><span class="sxs-lookup"><span data-stu-id="bd61c-168">Support for the `enum` keyword was added and is a breaking change.</span></span> <span data-ttu-id="bd61c-169">Das `enum` Trennzeichen ist zurzeit ein Zeilen Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="bd61c-169">The `enum` delimiter is currently a newline.</span></span> <span data-ttu-id="bd61c-170">Eine Problem Umgehung für diejenigen, die bereits verwenden, `enum` besteht darin, ein kaufmännisches und-( `&` ) vor dem Wort einzufügen.</span><span class="sxs-lookup"><span data-stu-id="bd61c-170">A workaround for those who are already using `enum` is to insert an ampersand (`&`) before the word.</span></span> <span data-ttu-id="bd61c-171">Aktuelle Einschränkungen: Sie können einen Enumerator nicht im Hinblick auf sich selbst definieren, aber Sie können `enum` die Initialisierung im Hinblick auf einen anderen durchlaufen `enum` , wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="bd61c-171">Current limitations: you cannot define an enumerator in terms of itself, but you can initialize `enum` in terms of another `enum`, as shown in the following example:</span></span>

<span data-ttu-id="bd61c-172">Der Basistyp kann derzeit nicht angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="bd61c-172">The base type cannot currently be specified.</span></span> <span data-ttu-id="bd61c-173">Der Basistyp ist immer [int].</span><span class="sxs-lookup"><span data-stu-id="bd61c-173">The base type is always [int].</span></span>

```powershell
enum Color2
{
    Yellow = [Color]::Blue
}
```

<span data-ttu-id="bd61c-174">Ein Enumeratorwert muss eine Konstante zur Analysezeit sein.</span><span class="sxs-lookup"><span data-stu-id="bd61c-174">An enumerator value must be a parse time constant.</span></span> <span data-ttu-id="bd61c-175">Der Enumeratorwert kann nicht auf das Ergebnis eines aufgerufenen Befehls festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="bd61c-175">The enumerator value cannot be set to the result of an invoked command.</span></span>

```powershell
enum MyEnum
{
    Enum1
    Enum2
    Enum3 = 42
    Enum4 = [int]::MaxValue
}
```

<span data-ttu-id="bd61c-176">`Enum` unterstützt arithmetische Operationen, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="bd61c-176">`Enum` supports arithmetic operations, as shown in the following example:</span></span>

```powershell
enum SomeEnum { Max = 42 }
enum OtherEnum { Max = [SomeEnum]::Max + 1 }
```

### <a name="hidden-keyword"></a><span data-ttu-id="bd61c-177">Hidden-Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="bd61c-177">Hidden keyword</span></span>

<span data-ttu-id="bd61c-178">Das `hidden` Schlüsselwort, das in Windows PowerShell 5,0 eingeführt wurde, verbirgt Klassenmember aus Standard `Get-Member` Ergebnissen.</span><span class="sxs-lookup"><span data-stu-id="bd61c-178">The `hidden` keyword, introduced in Windows PowerShell 5.0, hides class members from default `Get-Member` results.</span></span> <span data-ttu-id="bd61c-179">Geben Sie die Hidden-Eigenschaft an, wie in der folgenden Zeile dargestellt:</span><span class="sxs-lookup"><span data-stu-id="bd61c-179">Specify the hidden property as shown in the following line:</span></span>

```powershell
hidden [type] $classmember = <value>
```

<span data-ttu-id="bd61c-180">Ausgeblendete Member werden nicht mit der Vervollständigung mit der Tab-Taste oder mit IntelliSense angezeigt, es sei denn, der Abschluss tritt in der Klasse auf, die</span><span class="sxs-lookup"><span data-stu-id="bd61c-180">Hidden members are not displayed by using tab completion or IntelliSense, unless the completion occurs in the class that defines the hidden member.</span></span>

<span data-ttu-id="bd61c-181">Das neue Attribut **System. Management. Automation. hiddenattribute** wurde hinzugefügt, sodass der c#-Code in PowerShell die gleiche Semantik aufweisen kann.</span><span class="sxs-lookup"><span data-stu-id="bd61c-181">A new attribute, **System.Management.Automation.HiddenAttribute** , was added, so that C# code can have the same semantics within PowerShell.</span></span>

<span data-ttu-id="bd61c-182">Weitere Informationen finden Sie unter [about_Hidden](../../Microsoft.PowerShell.Core/About/about_hidden.md).</span><span class="sxs-lookup"><span data-stu-id="bd61c-182">For more information, see [about_Hidden](../../Microsoft.PowerShell.Core/About/about_hidden.md).</span></span>

### <a name="import-dscresource"></a><span data-ttu-id="bd61c-183">Import-DscResource</span><span class="sxs-lookup"><span data-stu-id="bd61c-183">Import-DscResource</span></span>

<span data-ttu-id="bd61c-184">`Import-DscResource` ist jetzt ein tatsächlich dynamisches Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="bd61c-184">`Import-DscResource` is now a true dynamic keyword.</span></span> <span data-ttu-id="bd61c-185">PowerShell analysiert das Stammmodul des angegebenen Moduls und sucht Klassen, die das DscResource-Attribut enthalten.</span><span class="sxs-lookup"><span data-stu-id="bd61c-185">PowerShell parses the specified module's root module, searching for classes that contain the DscResource attribute.</span></span>

### <a name="properties"></a><span data-ttu-id="bd61c-186">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="bd61c-186">Properties</span></span>

<span data-ttu-id="bd61c-187">Ein neues Feld, `ImplementingAssembly` , wurde hinzugefügt `ModuleInfo` .</span><span class="sxs-lookup"><span data-stu-id="bd61c-187">A new field, `ImplementingAssembly`, was added to `ModuleInfo`.</span></span> <span data-ttu-id="bd61c-188">, Wenn das Skript Klassen definiert, oder die geladene Assembly für binäre Module `ImplementingAssembly` auf die dynamische Assembly festgelegt ist, die für ein Skript Modul erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="bd61c-188">If the script defines classes, or the loaded assembly for binary modules `ImplementingAssembly` is set to the dynamic assembly created for a script module.</span></span> <span data-ttu-id="bd61c-189">Falls „ModuleType = Manifest“, wird es nicht festgelegt.</span><span class="sxs-lookup"><span data-stu-id="bd61c-189">It is not set when ModuleType = Manifest.</span></span>

<span data-ttu-id="bd61c-190">Die Reflektion für das `ImplementingAssembly` Feld ermittelt Ressourcen in einem Modul.</span><span class="sxs-lookup"><span data-stu-id="bd61c-190">Reflection on the `ImplementingAssembly` field discovers resources in a module.</span></span> <span data-ttu-id="bd61c-191">Dies bedeutet, dass Sie Ressourcen ermitteln können, die in PowerShell oder anderen verwalteten Sprachen geschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="bd61c-191">This means you can discover resources written in either PowerShell or other managed languages.</span></span>

<span data-ttu-id="bd61c-192">Felder mit Initialisierern.</span><span class="sxs-lookup"><span data-stu-id="bd61c-192">Fields with initializers.</span></span>

`[int] $i = 5`

<span data-ttu-id="bd61c-193">Static wird unterstützt und funktioniert wie ein Attribut, sodass es in beliebiger Reihenfolge angegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="bd61c-193">Static is supported and works like an attribute, similar to the type constraints, so it can be specified in any order.</span></span>

`static [int] $count = 0`

<span data-ttu-id="bd61c-194">Ein Typ ist optional.</span><span class="sxs-lookup"><span data-stu-id="bd61c-194">A type is optional.</span></span>

`$s = "hello"`

<span data-ttu-id="bd61c-195">Alle Member sind öffentlich.</span><span class="sxs-lookup"><span data-stu-id="bd61c-195">All members are public.</span></span> <span data-ttu-id="bd61c-196">Eigenschaften erfordern ein Zeilenumbruchzeichen oder Semikolon.</span><span class="sxs-lookup"><span data-stu-id="bd61c-196">Properties require either a newline or semicolon.</span></span> <span data-ttu-id="bd61c-197">Wenn kein Objekttyp angegeben ist, ist der Eigenschaftentyp **Object**.</span><span class="sxs-lookup"><span data-stu-id="bd61c-197">If no object type is specified, the property type is **Object**.</span></span>

### <a name="constructors-and-instantiation"></a><span data-ttu-id="bd61c-198">Konstruktoren und Instanziierung</span><span class="sxs-lookup"><span data-stu-id="bd61c-198">Constructors and instantiation</span></span>

<span data-ttu-id="bd61c-199">PowerShell-Klassen können Konstruktoren haben, die denselben Namen wie Ihre Klasse haben.</span><span class="sxs-lookup"><span data-stu-id="bd61c-199">PowerShell classes can have constructors that have the same name as their class.</span></span> <span data-ttu-id="bd61c-200">Konstruktoren können überladen werden.</span><span class="sxs-lookup"><span data-stu-id="bd61c-200">Constructors can be overloaded.</span></span> <span data-ttu-id="bd61c-201">Statische Konstruktoren werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="bd61c-201">Static constructors are supported.</span></span>
<span data-ttu-id="bd61c-202">Eigenschaften mit Initialisierungsausdrücken werden vor dem Ausführen von Code in einem Konstruktor initialisiert.</span><span class="sxs-lookup"><span data-stu-id="bd61c-202">Properties with initialization expressions are initialized before running any code in a constructor.</span></span> <span data-ttu-id="bd61c-203">Statische Eigenschaften werden vor dem Hauptteil eines statischen Konstruktors initialisiert. Instanzeigenschaften werden vor dem Hauptteil des nicht statischen Konstruktors initialisiert.</span><span class="sxs-lookup"><span data-stu-id="bd61c-203">Static properties are initialized before the body of a static constructor, and instance properties are initialized before the body of the non-static constructor.</span></span> <span data-ttu-id="bd61c-204">Derzeit gibt es keine Syntax zum Aufrufen eines Konstruktors von einem anderen Konstruktor, wie z. b. der c#-Syntax: `": this()")` .</span><span class="sxs-lookup"><span data-stu-id="bd61c-204">Currently, there is no syntax for calling a constructor from another constructor such as the C# syntax: `": this()")`.</span></span> <span data-ttu-id="bd61c-205">Eine Behelfslösung ist das Definieren einer allgemeinen „Init“-Methode.</span><span class="sxs-lookup"><span data-stu-id="bd61c-205">The workaround is to define a common Init method.</span></span>

<span data-ttu-id="bd61c-206">Es folgen Methoden zum Instanziieren von Klassen:</span><span class="sxs-lookup"><span data-stu-id="bd61c-206">The following are ways of instantiating classes:</span></span>

- <span data-ttu-id="bd61c-207">Instanziieren mithilfe des Standardkonstruktors.</span><span class="sxs-lookup"><span data-stu-id="bd61c-207">Instantiating by using the default constructor.</span></span> <span data-ttu-id="bd61c-208">Beachten Sie, dass `New-Object` in dieser Version nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="bd61c-208">Note that `New-Object` is not supported in this release.</span></span>

  `$a = [MyClass]::new()`

- <span data-ttu-id="bd61c-209">Aufrufen eines Konstruktors mit einem Parameter.</span><span class="sxs-lookup"><span data-stu-id="bd61c-209">Calling a constructor with a parameter.</span></span>

  `$b = [MyClass]::new(42)`

- <span data-ttu-id="bd61c-210">Übergeben ein Arrays an einen Konstruktor mit mehreren Parametern</span><span class="sxs-lookup"><span data-stu-id="bd61c-210">Passing an array to a constructor with multiple parameters</span></span>

  `$c = [MyClass]::new(@(42,43,44), "Hello")`

<span data-ttu-id="bd61c-211">In dieser Version ist der Typname nur lexikalisch sichtbar, was bedeutet, dass er außerhalb des Moduls oder Skripts, das die Klasse definiert, nicht sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="bd61c-211">For this release, the type name is only visible lexically, meaning it is not visible outside of the module or script that defines the class.</span></span> <span data-ttu-id="bd61c-212">Funktionen können Instanzen einer Klasse zurückgeben, die in PowerShell definiert ist, und Instanzen funktionieren gut außerhalb des Moduls oder Skripts.</span><span class="sxs-lookup"><span data-stu-id="bd61c-212">Functions can return instances of a class defined in PowerShell, and instances work well outside of the module or script.</span></span>

<span data-ttu-id="bd61c-213">Der `Get-Member` **statische** Parameter listet Konstruktoren auf, sodass Sie über Ladungen wie andere Methoden anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="bd61c-213">The `Get-Member` **Static** parameter lists constructors, so you can view overloads like any other method.</span></span> <span data-ttu-id="bd61c-214">Die Leistung dieser Syntax ist auch erheblich schneller als `New-Object`.</span><span class="sxs-lookup"><span data-stu-id="bd61c-214">The performance of this syntax is also considerably faster than `New-Object`.</span></span>

<span data-ttu-id="bd61c-215">Die pseudostatische Methode **new** funktioniert mit .NET-Typen, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="bd61c-215">The pseudo-static method named **new** works with .NET types, as shown in the following example.</span></span> `[hashtable]::new()`

<span data-ttu-id="bd61c-216">Sie können jetzt Konstruktorüberladungen mit `Get-Member` oder wie in diesem Beispiel anzeigen:</span><span class="sxs-lookup"><span data-stu-id="bd61c-216">You can now see constructor overloads with `Get-Member`, or as shown in this example:</span></span>

```powershell
[hashtable]::new
OverloadDefinitions
-------------------
hashtable new()
hashtable new(int capacity)
hashtable new(int capacity, float loadFactor)
```

### <a name="methods"></a><span data-ttu-id="bd61c-217">Methoden</span><span class="sxs-lookup"><span data-stu-id="bd61c-217">Methods</span></span>

<span data-ttu-id="bd61c-218">Eine PowerShell-Klassenmethode wird als **Skriptblock** mit nur einem „end“-Block implementiert.</span><span class="sxs-lookup"><span data-stu-id="bd61c-218">A PowerShell class method is implemented as a **ScriptBlock** that has only an end block.</span></span> <span data-ttu-id="bd61c-219">Alle Methoden sind öffentlich.</span><span class="sxs-lookup"><span data-stu-id="bd61c-219">All methods are public.</span></span> <span data-ttu-id="bd61c-220">Nachstehend sehen Sie ein Beispiel der Definition einer Methode namens **DoSomething**.</span><span class="sxs-lookup"><span data-stu-id="bd61c-220">The following shows an example of defining a method named **DoSomething**.</span></span>

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

### <a name="method-invocation"></a><span data-ttu-id="bd61c-221">Methodenaufruf</span><span class="sxs-lookup"><span data-stu-id="bd61c-221">Method invocation</span></span>

<span data-ttu-id="bd61c-222">Überladene Methoden werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="bd61c-222">Overloaded methods are supported.</span></span> <span data-ttu-id="bd61c-223">Überladene Methoden werden genauso benannt wie eine vorhandene Methode, unterscheiden sich jedoch durch die angegebenen Werte.</span><span class="sxs-lookup"><span data-stu-id="bd61c-223">Overloaded methods are named the same as an existing method but differentiated by their specified values.</span></span>

```powershell
$b = [MyClass]::new()
$b.DoSomething(42)
```

### <a name="invocation"></a><span data-ttu-id="bd61c-224">Aufruf</span><span class="sxs-lookup"><span data-stu-id="bd61c-224">Invocation</span></span>

<span data-ttu-id="bd61c-225">Siehe [Methodenaufruf](#method-invocation).</span><span class="sxs-lookup"><span data-stu-id="bd61c-225">See [Method invocation](#method-invocation).</span></span>

### <a name="attributes"></a><span data-ttu-id="bd61c-226">Attribute</span><span class="sxs-lookup"><span data-stu-id="bd61c-226">Attributes</span></span>

<span data-ttu-id="bd61c-227">Es wurden drei neue Attribute hinzugefügt: `DscResource` , `DscResourceKey` und `DscResourceMandatory` .</span><span class="sxs-lookup"><span data-stu-id="bd61c-227">Three new attributes were added: `DscResource`, `DscResourceKey`, and `DscResourceMandatory`.</span></span>

### <a name="return-types"></a><span data-ttu-id="bd61c-228">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="bd61c-228">Return types</span></span>

<span data-ttu-id="bd61c-229">Der Rückgabetyp ist ein Vertrag.</span><span class="sxs-lookup"><span data-stu-id="bd61c-229">Return type is a contract.</span></span> <span data-ttu-id="bd61c-230">Der Rückgabewert wird in den erwarteten Typ konvertiert.</span><span class="sxs-lookup"><span data-stu-id="bd61c-230">The return value is converted to the expected type.</span></span>
<span data-ttu-id="bd61c-231">Falls kein Rückgabetyp angegeben wird, ist der Rückgabetyp „void“.</span><span class="sxs-lookup"><span data-stu-id="bd61c-231">If no return type is specified, the return type is void.</span></span> <span data-ttu-id="bd61c-232">Es gibt kein Streaming von Objekten, und Objekte können entweder absichtlich oder versehentlich nicht in die Pipeline geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="bd61c-232">There is no streaming of objects and objects cannot be written to the pipeline either intentionally or by accident.</span></span>

### <a name="lexical-scoping-of-variables"></a><span data-ttu-id="bd61c-233">Lexikalische Eingrenzung von Variablen</span><span class="sxs-lookup"><span data-stu-id="bd61c-233">Lexical scoping of variables</span></span>

<span data-ttu-id="bd61c-234">Das folgende Beispiel zeigt, wie die lexikalische Eingrenzung in dieser Version funktioniert.</span><span class="sxs-lookup"><span data-stu-id="bd61c-234">The following shows an example of how lexical scoping works in this release.</span></span>

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

## <a name="example-create-custom-classes"></a><span data-ttu-id="bd61c-235">Beispiel: Erstellen von benutzerdefinierten Klassen</span><span class="sxs-lookup"><span data-stu-id="bd61c-235">Example: Create custom classes</span></span>

<span data-ttu-id="bd61c-236">Das folgende Beispiel erstellt mehrere neue, benutzerdefinierte Klassen, um eine HTML-DSL (Dynamic Stylesheet Language) zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="bd61c-236">The following example creates several new, custom classes to implement an HTML Dynamic Stylesheet Language (DSL).</span></span> <span data-ttu-id="bd61c-237">Im Beispiel werden Hilfsfunktionen hinzugefügt, um bestimmte Elementtypen als Teil der Element Klasse zu erstellen, z. b. Überschrift Stile und Tabellen, da Typen nicht außerhalb des Gültigkeits Bereichs eines Moduls verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="bd61c-237">The example adds helper functions to create specific element types as part of the element class, such as heading styles and tables, because types cannot be used outside the scope of a module.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="bd61c-238">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="bd61c-238">See also</span></span>

[<span data-ttu-id="bd61c-239">about_Enum</span><span class="sxs-lookup"><span data-stu-id="bd61c-239">about_Enum</span></span>](../../Microsoft.PowerShell.Core/About/about_Enum.md)

[<span data-ttu-id="bd61c-240">about_Hidden</span><span class="sxs-lookup"><span data-stu-id="bd61c-240">about_Hidden</span></span>](../../Microsoft.PowerShell.Core/About/about_hidden.md)

[<span data-ttu-id="bd61c-241">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="bd61c-241">about_Language_Keywords</span></span>](../../Microsoft.PowerShell.Core/About/about_Language_Keywords.md)

[<span data-ttu-id="bd61c-242">about_Methods</span><span class="sxs-lookup"><span data-stu-id="bd61c-242">about_Methods</span></span>](../../Microsoft.PowerShell.Core/About/about_Methods.md)

[<span data-ttu-id="bd61c-243">Erstellen von benutzerdefinierten PowerShell DSC-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="bd61c-243">Build Custom PowerShell Desired State Configuration Resources</span></span>](/powershell/scripting/dsc/resources/authoringResource)
