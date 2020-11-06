---
ms.date: 07/08/2020
keywords: DSC,PowerShell,Konfiguration,Setup,Einrichtung
title: Schreiben einer benutzerdefinierten DSC-Ressource mit PowerShell-Klassen
description: In diesem Artikel wird gezeigt, wie eine einfache Ressource zum Verwalten einer Datei in einem angegebenen Pfad erstellt wird.
ms.openlocfilehash: 72a828795c29e10ff66f164b8871b0fea7a1e0a8
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92667316"
---
# <a name="writing-a-custom-dsc-resource-with-powershell-classes"></a><span data-ttu-id="9b910-104">Schreiben einer benutzerdefinierten DSC-Ressource mit PowerShell-Klassen</span><span class="sxs-lookup"><span data-stu-id="9b910-104">Writing a custom DSC resource with PowerShell classes</span></span>

> <span data-ttu-id="9b910-105">Gilt für: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="9b910-105">Applies To: Windows PowerShell 5.0</span></span>

<span data-ttu-id="9b910-106">Mit der Einführung der PowerShell-Klassen in Windows PowerShell 5.0 können Sie jetzt eine DSC-Ressourcen durch Erstellen einer Klasse definieren.</span><span class="sxs-lookup"><span data-stu-id="9b910-106">With the introduction of PowerShell classes in Windows PowerShell 5.0, you can now define a DSC resource by creating a class.</span></span> <span data-ttu-id="9b910-107">Die Klasse definiert das Schema und die Implementierung der Ressource, daher besteht keine Notwendigkeit, eine separate MOF-Datei zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9b910-107">The class defines both the schema and the implementation of the resource, so there is no need to create a separate MOF file.</span></span> <span data-ttu-id="9b910-108">Die Ordnerstruktur für eine klassenbasierte Ressource ist auch einfacher, da kein **DSCResources** -Ordner erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="9b910-108">The folder structure for a class-based resource is also simpler, because a **DSCResources** folder is not necessary.</span></span>

<span data-ttu-id="9b910-109">In einer klassenbasierten DSC-Ressource wird das Schema als Eigenschaften der Klasse definiert, die mit Attributen für den Eigenschaftstyp geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="9b910-109">In a class-based DSC resource, the schema is defined as properties of the class which can be modified with attributes to specify the property type..</span></span> <span data-ttu-id="9b910-110">Die Ressource wird mit den Methoden `Get()` , `Set()` und `Test()` implementiert (entspricht den Funktionen `Get-TargetResource`, `Set-TargetResource` und `Test-TargetResource` in einer Skriptressource.</span><span class="sxs-lookup"><span data-stu-id="9b910-110">The resource is implemented by `Get()`, `Set()`, and `Test()` methods (equivalent to the `Get-TargetResource`, `Set-TargetResource`, and `Test-TargetResource` functions in a script resource.</span></span>

<span data-ttu-id="9b910-111">In diesem Artikel wird eine einfache Ressource mit dem Namen **FileResource** erstellt, die eine Datei unter einem angegebenen Pfad verwaltet.</span><span class="sxs-lookup"><span data-stu-id="9b910-111">In this article, we will create a simple resource named **FileResource** that manages a file in a specified path.</span></span>

<span data-ttu-id="9b910-112">Weitere Informationen zu DSC-Ressourcen finden Sie unter [Erstellen von benutzerdefinierten Windows PowerShell DSC-Ressourcen](authoringResource.md).</span><span class="sxs-lookup"><span data-stu-id="9b910-112">For more information about DSC resources, see [Build Custom Windows PowerShell Desired State Configuration Resources](authoringResource.md)</span></span>

> [!Note]
> <span data-ttu-id="9b910-113">Generische Sammlungen werden nicht in auf Klassen basierenden Ressourcen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9b910-113">Generic collections are not supported in class-based resources.</span></span>

## <a name="folder-structure-for-a-class-resource"></a><span data-ttu-id="9b910-114">Ordnerstruktur für eine Klassenressource</span><span class="sxs-lookup"><span data-stu-id="9b910-114">Folder structure for a class resource</span></span>

<span data-ttu-id="9b910-115">Um eine benutzerdefinierte DSC-Ressource mit einer PowerShell-Klasse zu implementieren, erstellen Sie die folgende Ordnerstruktur.</span><span class="sxs-lookup"><span data-stu-id="9b910-115">To implement a DSC custom resource with a PowerShell class, create the following folder structure.</span></span>
<span data-ttu-id="9b910-116">Die Klasse wird in `MyDscResource.psm1` und das Modulmanifest in `MyDscResource.psd1` definiert.</span><span class="sxs-lookup"><span data-stu-id="9b910-116">The class is defined in `MyDscResource.psm1` and the module manifest is defined in `MyDscResource.psd1`.</span></span>

```
$env:ProgramFiles\WindowsPowerShell\Modules (folder)
    |- MyDscResource (folder)
        MyDscResource.psm1
        MyDscResource.psd1
```

## <a name="create-the-class"></a><span data-ttu-id="9b910-117">Erstellen einer Klasse</span><span class="sxs-lookup"><span data-stu-id="9b910-117">Create the class</span></span>

<span data-ttu-id="9b910-118">Sie verwenden das Schlüsselwort „class“ zum Erstellen einer PowerShell-Klasse.</span><span class="sxs-lookup"><span data-stu-id="9b910-118">You use the class keyword to create a PowerShell class.</span></span> <span data-ttu-id="9b910-119">Um anzugeben, dass eine Klasse eine DSC-Ressource ist, verwenden Sie das Attribut `DscResource()` .</span><span class="sxs-lookup"><span data-stu-id="9b910-119">To specify that a class is a DSC resource, use the `DscResource()` attribute.</span></span> <span data-ttu-id="9b910-120">Der Name der Klasse ist der Name der DSC-Ressource.</span><span class="sxs-lookup"><span data-stu-id="9b910-120">The name of the class is the name of the DSC resource.</span></span>

```powershell
[DscResource()]
class FileResource {
}
```

### <a name="declare-properties"></a><span data-ttu-id="9b910-121">Deklarieren von Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="9b910-121">Declare properties</span></span>

<span data-ttu-id="9b910-122">Das DSC-Ressourcenschema wird als Eigenschaften der Klasse definiert.</span><span class="sxs-lookup"><span data-stu-id="9b910-122">The DSC resource schema is defined as properties of the class.</span></span> <span data-ttu-id="9b910-123">Es wurden die folgenden drei Eigenschaften deklariert.</span><span class="sxs-lookup"><span data-stu-id="9b910-123">We declare three properties as follows.</span></span>

```powershell
[DscProperty(Key)]
[string]$Path

[DscProperty(Mandatory)]
[Ensure] $Ensure

[DscProperty(Mandatory)]
[string] $SourcePath

[DscProperty(NotConfigurable)]
[Nullable[datetime]] $CreationTime
```

<span data-ttu-id="9b910-124">Beachten Sie, dass die Eigenschaften durch Attribute geändert werden.</span><span class="sxs-lookup"><span data-stu-id="9b910-124">Notice that the properties are modified by attributes.</span></span> <span data-ttu-id="9b910-125">Die Attribute haben folgende Bedeutungen:</span><span class="sxs-lookup"><span data-stu-id="9b910-125">The meaning of the attributes is as follows:</span></span>

- <span data-ttu-id="9b910-126">**DscProperty(Key)** : Die Eigenschaft ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9b910-126">**DscProperty(Key)** : The property is required.</span></span> <span data-ttu-id="9b910-127">Die Eigenschaft ist ein Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="9b910-127">The property is a key.</span></span> <span data-ttu-id="9b910-128">Die Werte aller als Schlüssel gekennzeichneten Eigenschaften in Kombination müssen eine Ressourceninstanz in einer Konfiguration eindeutig identifizieren.</span><span class="sxs-lookup"><span data-stu-id="9b910-128">The values of all properties marked as keys must combine to uniquely identify a resource instance within a configuration.</span></span>
- <span data-ttu-id="9b910-129">**DscProperty(Mandatory)** : Die Eigenschaft ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9b910-129">**DscProperty(Mandatory)** : The property is required.</span></span>
- <span data-ttu-id="9b910-130">**DscProperty(NotConfigurable)** : Die Eigenschaft ist schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="9b910-130">**DscProperty(NotConfigurable)** : The property is read-only.</span></span> <span data-ttu-id="9b910-131">Eigenschaften, die mit diesem Attribut gekennzeichnet sind, können nicht von einer Konfiguration festgelegt werden, sondern werden durch die Methode `Get()` , wenn vorhanden, aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="9b910-131">Properties marked with this attribute cannot be set by a configuration, but are populated by the `Get()` method when present.</span></span>
- <span data-ttu-id="9b910-132">**DscProperty()** : Die Eigenschaft ist konfigurierbar, aber nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9b910-132">**DscProperty()** : The property is configurable, but it is not required.</span></span>

<span data-ttu-id="9b910-133">Die Eigenschaften `$Path` und `$SourcePath` stellen Zeichenfolgen dar.</span><span class="sxs-lookup"><span data-stu-id="9b910-133">The `$Path` and `$SourcePath` properties are both strings.</span></span> <span data-ttu-id="9b910-134">`$CreationTime` ist eine [DateTime](/dotnet/api/system.datetime)-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="9b910-134">The `$CreationTime` is a [DateTime](/dotnet/api/system.datetime) property.</span></span> <span data-ttu-id="9b910-135">Die Eigenschaft `$Ensure` ist ein Enumerationstyp, der wie folgt definiert ist:</span><span class="sxs-lookup"><span data-stu-id="9b910-135">The `$Ensure` property is an enumeration type, defined as follows.</span></span>

```powershell
enum Ensure
{
    Absent
    Present
}
```

### <a name="implementing-the-methods"></a><span data-ttu-id="9b910-136">Implementieren der Methoden</span><span class="sxs-lookup"><span data-stu-id="9b910-136">Implementing the methods</span></span>

<span data-ttu-id="9b910-137">Die Methoden `Get()` , `Set()` und `Test()` werden analog zu den Funktionen `Get-TargetResource`, `Set-TargetResource` und `Test-TargetResource` in einer Skriptressource implementiert.</span><span class="sxs-lookup"><span data-stu-id="9b910-137">The `Get()`, `Set()`, and `Test()` methods are analogous to the `Get-TargetResource`, `Set-TargetResource`, and `Test-TargetResource` functions in a script resource.</span></span>

<span data-ttu-id="9b910-138">Dieser Code umfasst auch die Hilfsfunktion `CopyFile()`, die die Datei von `$SourcePath` nach `$Path` kopiert.</span><span class="sxs-lookup"><span data-stu-id="9b910-138">This code also includes the `CopyFile()` function, a helper function that copies the file from `$SourcePath` to `$Path`.</span></span>

```powershell
    <#
        This method is equivalent of the Set-TargetResource script function.
        It sets the resource to the desired state.
    #>
    [void] Set()
    {
        $fileExists = $this.TestFilePath($this.Path)

        if ($this.ensure -eq [Ensure]::Present)
        {
            if(-not $fileExists)
            {
                $this.CopyFile()
            }
        }
        else
        {
            if ($fileExists)
            {
                Write-Verbose -Message "Deleting the file $($this.Path)"
                Remove-Item -LiteralPath $this.Path -Force
            }
        }
    }

    <#
        This method is equivalent of the Test-TargetResource script function.
        It should return True or False, showing whether the resource
        is in a desired state.
    #>
    [bool] Test()
    {
        $present = $this.TestFilePath($this.Path)

        if ($this.Ensure -eq [Ensure]::Present)
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
        The implementation should use the keys to find appropriate resources.
        This method returns an instance of this class with the updated key
         properties.
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
        Helper method to check if the file exists and it is file
    #>
    [bool] TestFilePath([string] $location)
    {
        $present = $true

        $item = Get-ChildItem -LiteralPath $location -ErrorAction Ignore

        if ($item -eq $null)
        {
            $present = $false
        }
        elseif ($item.PSProvider.Name -ne "FileSystem")
        {
            throw "Path $($location) is not a file path."
        }
        elseif ($item.PSIsContainer)
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
        if (-not $this.TestFilePath($this.SourcePath))
        {
            throw "SourcePath $($this.SourcePath) is not found."
        }

        [System.IO.FileInfo] $destFileInfo = New-Object -TypeName System.IO.FileInfo($this.Path)

        if (-not $destFileInfo.Directory.Exists)
        {
            Write-Verbose -Message "Creating directory $($destFileInfo.Directory.FullName)"

            <#
                Use CreateDirectory instead of New-Item to avoid code
                to handle the non-terminating error
            #>
            [System.IO.Directory]::CreateDirectory($destFileInfo.Directory.FullName)
        }

        if (Test-Path -LiteralPath $this.Path -PathType Container)
        {
            throw "Path $($this.Path) is a directory path"
        }

        Write-Verbose -Message "Copying $($this.SourcePath) to $($this.Path)"

        # DSC engine catches and reports any error that occurs
        Copy-Item -LiteralPath $this.SourcePath -Destination $this.Path -Force
    }
```

### <a name="the-complete-file"></a><span data-ttu-id="9b910-139">Die vollständige Datei</span><span class="sxs-lookup"><span data-stu-id="9b910-139">The complete file</span></span>

<span data-ttu-id="9b910-140">Die vollständige Klassendatei folgt.</span><span class="sxs-lookup"><span data-stu-id="9b910-140">The complete class file follows.</span></span>

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
        if ($this.ensure -eq [Ensure]::Present)
        {
            if (-not $fileExists)
            {
                $this.CopyFile()
            }
        }
        else
        {
            if ($fileExists)
            {
                Write-Verbose -Message "Deleting the file $($this.Path)"
                Remove-Item -LiteralPath $this.Path -Force
            }
        }
    }

    <#
        This method is equivalent of the Test-TargetResource script function.
        It should return True or False, showing whether the resource
        is in a desired state.
    #>
    [bool] Test()
    {
        $present = $this.TestFilePath($this.Path)

        if ($this.Ensure -eq [Ensure]::Present)
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
        The implementation should use the keys to find appropriate resources.
        This method returns an instance of this class with the updated key
         properties.
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
        Helper method to check if the file exists and it is file
    #>
    [bool] TestFilePath([string] $location)
    {
        $present = $true

        $item = Get-ChildItem -LiteralPath $location -ea Ignore
        if ($item -eq $null)
        {
            $present = $false
        }
        elseif ($item.PSProvider.Name -ne "FileSystem")
        {
            throw "Path $($location) is not a file path."
        }
        elseif ($item.PSIsContainer)
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
        if (-not $this.TestFilePath($this.SourcePath))
        {
            throw "SourcePath $($this.SourcePath) is not found."
        }

        [System.IO.FileInfo] $destFileInfo = new-object System.IO.FileInfo($this.Path)
        if (-not $destFileInfo.Directory.Exists)
        {
            Write-Verbose -Message "Creating directory $($destFileInfo.Directory.FullName)"

            <#
                Use CreateDirectory instead of New-Item to avoid code
                 to handle the non-terminating error
            #>
            [System.IO.Directory]::CreateDirectory($destFileInfo.Directory.FullName)
        }

        if (Test-Path -LiteralPath $this.Path -PathType Container)
        {
            throw "Path $($this.Path) is a directory path"
        }

        Write-Verbose -Message "Copying $($this.SourcePath) to $($this.Path)"

        # DSC engine catches and reports any error that occurs
        Copy-Item -LiteralPath $this.SourcePath -Destination $this.Path -Force
    }
} # This module defines a class for a DSC "FileResource" provider.
```

## <a name="create-a-manifest"></a><span data-ttu-id="9b910-141">Erstellen eines Manifests</span><span class="sxs-lookup"><span data-stu-id="9b910-141">Create a manifest</span></span>

<span data-ttu-id="9b910-142">Um eine klassenbasierte Ressource für die DSC-Engine verfügbar zu machen, müssen Sie eine `DscResourcesToExport`-Anweisung zur Manifestdatei hinzufügen, die die Engine anweist, die Ressource zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="9b910-142">To make a class-based resource available to the DSC engine, you must include a `DscResourcesToExport` statement in the manifest file that instructs the module to export the resource.</span></span> <span data-ttu-id="9b910-143">Unser Manifest sieht folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="9b910-143">Our manifest looks like this:</span></span>

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

# Minimum version of the Windows PowerShell engine required by this module
PowerShellVersion = '5.0'

# Name of the Windows PowerShell host required by this module
# PowerShellHostName = ''
}
```

## <a name="test-the-resource"></a><span data-ttu-id="9b910-144">Testen der Ressource</span><span class="sxs-lookup"><span data-stu-id="9b910-144">Test the resource</span></span>

<span data-ttu-id="9b910-145">Nachdem Sie die Klasse und die Manifestdateien, wie zuvor beschrieben, in der Ordnerstruktur gespeichert haben, können Sie eine Konfiguration erstellen, die die neue Ressource verwendet.</span><span class="sxs-lookup"><span data-stu-id="9b910-145">After saving the class and manifest files in the folder structure as described earlier, you can create a configuration that uses the new resource.</span></span> <span data-ttu-id="9b910-146">Informationen dazu, wie Sie eine DSC-Konfiguration ausführen, finden Sie unter [Inkraftsetzung von Konfigurationen](../pull-server/enactingConfigurations.md).</span><span class="sxs-lookup"><span data-stu-id="9b910-146">For information about how to run a DSC configuration, see [Enacting configurations](../pull-server/enactingConfigurations.md).</span></span> <span data-ttu-id="9b910-147">Die folgende Konfiguration überprüft, ob die Datei unter `c:\test\test.txt` vorhanden ist, und kopiert sie bei Bedarf aus `c:\test.txt` (Sie sollten `c:\test.txt` vor dem Ausführen der Konfiguration erstellen).</span><span class="sxs-lookup"><span data-stu-id="9b910-147">The following configuration will check to see whether the file at `c:\test\test.txt` exists, and, if not, copies the file from `c:\test.txt` (you should create `c:\test.txt` before you run the configuration).</span></span>

```powershell
Configuration Test
{
    Import-DSCResource -module MyDscResource
    FileResource file
    {
        Path = "C:\test\test.txt"
        SourcePath = "c:\test.txt"
        Ensure = "Present"
    }
}
Test
Start-DscConfiguration -Wait -Force Test
```

## <a name="supporting-psdscrunascredential"></a><span data-ttu-id="9b910-148">Unterstützung von PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="9b910-148">Supporting PsDscRunAsCredential</span></span>

> <span data-ttu-id="9b910-149">Hinweis: **PsDscRunAsCredential** wird ab PowerShell 5.0 unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9b910-149">[Note] **PsDscRunAsCredential** is supported in PowerShell 5.0 and later.</span></span>

<span data-ttu-id="9b910-150">Mithilfe der Eigenschaft **PsDscRunAsCredential** kann im Ressourcenblock [DSC configurations](../configurations/configurations.md) angegeben werden, dass die Ressource mit einem festgelegten Satz an Anmeldeinformationen ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9b910-150">The **PsDscRunAsCredential** property can be used in [DSC configurations](../configurations/configurations.md) resource block to specify that the resource should be run under a specified set of credentials.</span></span> <span data-ttu-id="9b910-151">Weitere Informationen finden Sie unter [Ausführen von DSC mit Benutzeranmeldeinformationen](../configurations/runAsUser.md).</span><span class="sxs-lookup"><span data-stu-id="9b910-151">For more information, see [Running DSC with user credentials](../configurations/runAsUser.md).</span></span>

### <a name="require-or-disallow-psdscrunascredential-for-your-resource"></a><span data-ttu-id="9b910-152">Anfordern oder Untersagen von PsDscRunAsCredential für Ihre Ressource</span><span class="sxs-lookup"><span data-stu-id="9b910-152">Require or disallow PsDscRunAsCredential for your resource</span></span>

<span data-ttu-id="9b910-153">Das Attribut `DscResource()` verwendet einen optionalen Parameter **RunAsCredential**.</span><span class="sxs-lookup"><span data-stu-id="9b910-153">The `DscResource()` attribute takes an optional parameter **RunAsCredential**.</span></span> <span data-ttu-id="9b910-154">Dieser Parameter kann einen von drei Werten annehmen:</span><span class="sxs-lookup"><span data-stu-id="9b910-154">This parameter takes one of three values:</span></span>

- <span data-ttu-id="9b910-155">`Optional` **PsDscRunAsCredential** ist optional für Konfigurationen, die diese Ressource aufrufen.</span><span class="sxs-lookup"><span data-stu-id="9b910-155">`Optional` **PsDscRunAsCredential** is optional for configurations that call this resource.</span></span> <span data-ttu-id="9b910-156">Dies ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="9b910-156">This is the default value.</span></span>
- <span data-ttu-id="9b910-157">`Mandatory` **PsDscRunAsCredential** muss für alle Konfigurationen verwendet werden, die diese Ressource aufrufen.</span><span class="sxs-lookup"><span data-stu-id="9b910-157">`Mandatory` **PsDscRunAsCredential** must be used for any configuration that calls this resource.</span></span>
- <span data-ttu-id="9b910-158">`NotSupported`Konfigurationen, die diese Ressource aufrufen, können **PsDscRunAsCredential** nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="9b910-158">`NotSupported` Configurations that call this resource cannot use **PsDscRunAsCredential**.</span></span>
- <span data-ttu-id="9b910-159">`Default` Identisch mit `Optional`.</span><span class="sxs-lookup"><span data-stu-id="9b910-159">`Default` Same as `Optional`.</span></span>

<span data-ttu-id="9b910-160">Verwenden Sie beispielsweise das folgende Attribut, um anzugeben, dass Ihre benutzerdefinierte Ressource die Verwendung von **PsDscRunAsCredential** nicht unterstützt:</span><span class="sxs-lookup"><span data-stu-id="9b910-160">For example, use the following attribute to specify that your custom resource does not support using **PsDscRunAsCredential** :</span></span>

```powershell
[DscResource(RunAsCredential=NotSupported)]
class FileResource {
}
```

### <a name="declaring-multiple-class-resources-in-a-module"></a><span data-ttu-id="9b910-161">Deklarieren von Ressourcen mit mehreren Klassen in einem Modul</span><span class="sxs-lookup"><span data-stu-id="9b910-161">Declaring multiple class resources in a module</span></span>

<span data-ttu-id="9b910-162">Ein Modul kann mehrere klassenbasierte DSC-Ressourcen definieren.</span><span class="sxs-lookup"><span data-stu-id="9b910-162">A module can define multiple class based DSC resources.</span></span> <span data-ttu-id="9b910-163">Sie können die Ordnerstruktur auf folgende Weise erstellen:</span><span class="sxs-lookup"><span data-stu-id="9b910-163">You can create the folder structure in the following ways:</span></span>

1. <span data-ttu-id="9b910-164">Definieren Sie die erste Ressource in der Datei `<ModuleName>.psm1` und die nachfolgenden Ressourcen unter dem Ordner **DSCResources**.</span><span class="sxs-lookup"><span data-stu-id="9b910-164">Define the first resource in the `<ModuleName>.psm1` file and subsequent resources under the **DSCResources** folder.</span></span>

   ```
   $env:ProgramFiles\WindowsPowerShell\Modules (folder)
        |- MyDscResource (folder)
           |- MyDscResource.psm1
              MyDscResource.psd1
        |- DSCResources
           |- SecondResource.psm1
   ```

1. <span data-ttu-id="9b910-165">Definieren Sie alle Ressourcen unter dem Ordner **DSCResources**.</span><span class="sxs-lookup"><span data-stu-id="9b910-165">Define all resources under the **DSCResources** folder.</span></span>

   ```
   $env:ProgramFiles\WindowsPowerShell\Modules (folder)
        |- MyDscResource (folder)
           |- MyDscResource.psm1
              MyDscResource.psd1
        |- DSCResources
           |- FirstResource.psm1
              SecondResource.psm1
   ```

> [!NOTE]
> <span data-ttu-id="9b910-166">Fügen Sie in den Beispielen oben alle PSM1-Dateien unter **DSCResources** dem Schlüssel **NestedModules** in Ihrer PSD1-Datei hinzu.</span><span class="sxs-lookup"><span data-stu-id="9b910-166">In the examples above, add any PSM1 files under the **DSCResources** to the **NestedModules** key in your PSD1 file.</span></span>

### <a name="access-the-user-context"></a><span data-ttu-id="9b910-167">Zugriff auf den Benutzerkontext</span><span class="sxs-lookup"><span data-stu-id="9b910-167">Access the user context</span></span>

<span data-ttu-id="9b910-168">Um aus einer benutzerdefinierten Ressource auf den Benutzerkontext zuzugreifen, können Sie die automatische Variable `$global:PsDscContext` verwenden.</span><span class="sxs-lookup"><span data-stu-id="9b910-168">To access the user context from within a custom resource, you can use the automatic variable `$global:PsDscContext`.</span></span>

<span data-ttu-id="9b910-169">Beispielsweise wird mit dem folgenden Code der Benutzerkontext für die Ressourcenausführung in den ausführlichen Ausgabestream geschrieben:</span><span class="sxs-lookup"><span data-stu-id="9b910-169">For example the following code would write the user context under which the resource is running to the verbose output stream:</span></span>

```powershell
if (PsDscContext.RunAsUser) {
    Write-Verbose "User: $global:PsDscContext.RunAsUser";
}
```

## <a name="see-also"></a><span data-ttu-id="9b910-170">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9b910-170">See Also</span></span>

[<span data-ttu-id="9b910-171">Erstellen von benutzerdefinierten Windows PowerShell DSC-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="9b910-171">Build Custom Windows PowerShell Desired State Configuration Resources</span></span>](authoringResource.md)
