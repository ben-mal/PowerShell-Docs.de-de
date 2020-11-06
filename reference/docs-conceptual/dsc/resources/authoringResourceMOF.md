---
ms.date: 07/08/2020
keywords: DSC,PowerShell,Konfiguration,Setup,Einrichtung
title: Schreiben einer benutzerdefinierten DSC-Ressource mit MOF
description: In diesem Artikel wird das Schema für eine benutzerdefinierte DSC-Ressource in einer MOF-Datei definiert und die Ressource in einer PowerShell-Skriptdatei implementiert.
ms.openlocfilehash: e79a37699c468b2c55c307c96f1c193a2c1595b3
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92667180"
---
# <a name="writing-a-custom-dsc-resource-with-mof"></a><span data-ttu-id="47de0-104">Schreiben einer benutzerdefinierten DSC-Ressource mit MOF</span><span class="sxs-lookup"><span data-stu-id="47de0-104">Writing a custom DSC resource with MOF</span></span>

> <span data-ttu-id="47de0-105">Gilt für: Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="47de0-105">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="47de0-106">In diesem Artikel wird das Schema für eine benutzerdefinierte Windows PowerShell DSC-Ressource in einer MOF-Datei definiert und die Ressource in einer Windows PowerShell-Skriptdatei implementiert.</span><span class="sxs-lookup"><span data-stu-id="47de0-106">In this article, we will define the schema for a Windows PowerShell Desired State Configuration (DSC) custom resource in a MOF file, and implement the resource in a Windows PowerShell script file.</span></span>
<span data-ttu-id="47de0-107">Diese benutzerdefinierte Ressource dient zum Erstellen und Verwalten einer Website.</span><span class="sxs-lookup"><span data-stu-id="47de0-107">This custom resource is for creating and maintaining a web site.</span></span>

## <a name="creating-the-mof-schema"></a><span data-ttu-id="47de0-108">Schreiben des MOF-Schemas</span><span class="sxs-lookup"><span data-stu-id="47de0-108">Creating the MOF schema</span></span>

<span data-ttu-id="47de0-109">Das Schema definiert die Eigenschaften der Ressource, die durch ein DSC-Konfigurationsskript konfiguriert werden können.</span><span class="sxs-lookup"><span data-stu-id="47de0-109">The schema defines the properties of your resource that can be configured by a DSC configuration script.</span></span>

### <a name="folder-structure-for-a-mof-resource"></a><span data-ttu-id="47de0-110">Ordnerstruktur für eine MOF-Ressource</span><span class="sxs-lookup"><span data-stu-id="47de0-110">Folder structure for a MOF resource</span></span>

<span data-ttu-id="47de0-111">Um eine benutzerdefinierte DSC-Ressource mit einem MOF-Schema zu implementieren, erstellen Sie die folgende Ordnerstruktur.</span><span class="sxs-lookup"><span data-stu-id="47de0-111">To implement a DSC custom resource with a MOF schema, create the following folder structure.</span></span> <span data-ttu-id="47de0-112">Das MOF-Schema wird in der Datei `Demo_IISWebsite.schema.mof` definiert und das Ressourcenskript in `Demo_IISWebsite.psm1`.</span><span class="sxs-lookup"><span data-stu-id="47de0-112">The MOF schema is defined in the file `Demo_IISWebsite.schema.mof`, and the resource script is defined in `Demo_IISWebsite.psm1`.</span></span> <span data-ttu-id="47de0-113">Optional können Sie eine Modulmanifestdatei (psd1) erstellen.</span><span class="sxs-lookup"><span data-stu-id="47de0-113">Optionally, you can create a module manifest (psd1) file.</span></span>

```
$env:ProgramFiles\WindowsPowerShell\Modules (folder)
    |- MyDscResources (folder)
        |- DSCResources (folder)
            |- Demo_IISWebsite (folder)
                |- Demo_IISWebsite.psd1 (file, optional)
                |- Demo_IISWebsite.psm1 (file, required)
                |- Demo_IISWebsite.schema.mof (file, required)
```

> [!NOTE]
> <span data-ttu-id="47de0-114">Sie müssen im Ordner der obersten Ebene einen Ordner mit dem Namen „DSCResources“ erstellen, und die Ordnernamen für die einzelnen Ressourcen müssen den Namen der jeweiligen Ressourcen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="47de0-114">It is necessary to create a folder named DSCResources under the top-level folder, and that the folder for each resource must have the same name as the resource.</span></span>

### <a name="the-contents-of-the-mof-file"></a><span data-ttu-id="47de0-115">Inhalt der MOF-Datei</span><span class="sxs-lookup"><span data-stu-id="47de0-115">The contents of the MOF file</span></span>

<span data-ttu-id="47de0-116">Die folgende MOF-Beispieldatei kann für eine benutzerdefinierte Websiteressource verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="47de0-116">Following is an example MOF file that can be used for a custom website resource.</span></span> <span data-ttu-id="47de0-117">Um dieses Beispiel anzuwenden, speichern Sie das Schema in einer Datei, und rufen Sie die Datei `Demo_IISWebsite.schema.mof` auf.</span><span class="sxs-lookup"><span data-stu-id="47de0-117">To follow this example, save this schema to a file, and call the file `Demo_IISWebsite.schema.mof`.</span></span>

```
[ClassVersion("1.0.0"), FriendlyName("Website")]
class Demo_IISWebsite : OMI_BaseResource
{
  [Key] string Name;
  [Required] string PhysicalPath;
  [write,ValueMap{"Present", "Absent"},Values{"Present", "Absent"}] string Ensure;
  [write,ValueMap{"Started","Stopped"},Values{"Started", "Stopped"}] string State;
  [write] string Protocol[];
  [write] string BindingInfo[];
  [write] string ApplicationPool;
  [read] string ID;
};
```

<span data-ttu-id="47de0-118">Beachten Sie Folgendes im Zusammenhang mit dem vorherigen Code:</span><span class="sxs-lookup"><span data-stu-id="47de0-118">Note the following about the previous code:</span></span>

- <span data-ttu-id="47de0-119">`FriendlyName` definiert den Namen, den Sie verwenden können, um auf diese benutzerdefinierte Ressource in DSC-Konfigurationsskripts zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="47de0-119">`FriendlyName` defines the name you can use to refer to this custom resource in DSC configuration scripts.</span></span> <span data-ttu-id="47de0-120">In diesem Beispiel entspricht `Website` dem Anzeigenamen `Archive` für die integrierten Ressource „Archive“.</span><span class="sxs-lookup"><span data-stu-id="47de0-120">In this example, `Website` is equivalent to the friendly name `Archive` for the built-in Archive resource.</span></span>
- <span data-ttu-id="47de0-121">Die Klasse, die Sie für die benutzerdefinierte Ressource definieren, muss von `OMI_BaseResource` abgeleitet sein.</span><span class="sxs-lookup"><span data-stu-id="47de0-121">The class you define for your custom resource must derive from `OMI_BaseResource`.</span></span>
- <span data-ttu-id="47de0-122">Der Typqualifizierer `[Key]` für eine Eigenschaft gibt an, dass die Ressourceninstanz durch diese Eigenschaft eindeutig identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="47de0-122">The type qualifier, `[Key]`, on a property indicates that this property will uniquely identify the resource instance.</span></span> <span data-ttu-id="47de0-123">Mindestens eine `[Key]`-Eigenschaft ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="47de0-123">At least one `[Key]` property is required.</span></span>
- <span data-ttu-id="47de0-124">Der Qualifizierer `[Required]` gibt an, dass die Eigenschaft erforderlich ist (der Wert muss in jedem Konfigurationsskript, in dem die Ressource verwendet wird, angegeben werden).</span><span class="sxs-lookup"><span data-stu-id="47de0-124">The `[Required]` qualifier indicates that the property is required (a value must be specified in any configuration script that uses this resource).</span></span>
- <span data-ttu-id="47de0-125">Der Qualifizierer `[write]` gibt an, dass diese Eigenschaft bei Verwendung der benutzerdefinierten Ressource in einem Konfigurationsskript optional ist.</span><span class="sxs-lookup"><span data-stu-id="47de0-125">The `[write]` qualifier indicates that this property is optional when using the custom resource in a configuration script.</span></span> <span data-ttu-id="47de0-126">Der Qualifizierer `[read]` gibt an, dass eine Eigenschaft nicht durch eine Konfiguration festgelegt werden kann und nur zu Berichtszwecken dient.</span><span class="sxs-lookup"><span data-stu-id="47de0-126">The `[read]` qualifier indicates that a property cannot be set by a configuration, and is for reporting purposes only.</span></span>
- <span data-ttu-id="47de0-127">`Values` schränkt die Werte, die der Eigenschaft zugewiesen werden können, auf die in `ValueMap` definierte Werteliste ein.</span><span class="sxs-lookup"><span data-stu-id="47de0-127">`Values` restricts the values that can be assigned to the property to the list of values defined in `ValueMap`.</span></span> <span data-ttu-id="47de0-128">Weitere Informationen finden Sie unter [Die Qualifizierer „ValueMap“ und „Value“](/windows/desktop/WmiSdk/value-map).</span><span class="sxs-lookup"><span data-stu-id="47de0-128">For more information, see [ValueMap and Value Qualifiers](/windows/desktop/WmiSdk/value-map).</span></span>
- <span data-ttu-id="47de0-129">Eine empfohlene Methode, einen konsistenten Stil mit integrierten DSC-Ressourcen beizubehalten, ist das Hinzufügen einer Eigenschaft namens `Ensure`, die die Werte `Present` und `Absent` aufweist, zu Ihrer Ressource.</span><span class="sxs-lookup"><span data-stu-id="47de0-129">Including a property called `Ensure` with values `Present` and `Absent` in your resource is recommended as a way to maintain a consistent style with built-in DSC resources.</span></span>
- <span data-ttu-id="47de0-130">Benennen Sie die Schemadatei für die benutzerdefinierte Ressource wie folgt: `classname.schema.mof`, wobei `classname` der Bezeichner ist, der dem Schlüsselwort `class` in der Schemadefinition folgt.</span><span class="sxs-lookup"><span data-stu-id="47de0-130">Name the schema file for your custom resource as follows: `classname.schema.mof`, where `classname` is the identifier that follows the `class` keyword in your schema definition.</span></span>

### <a name="writing-the-resource-script"></a><span data-ttu-id="47de0-131">Schreiben des Ressourcenskripts</span><span class="sxs-lookup"><span data-stu-id="47de0-131">Writing the resource script</span></span>

<span data-ttu-id="47de0-132">Das Ressourcenskript implementiert die Logik der Ressource.</span><span class="sxs-lookup"><span data-stu-id="47de0-132">The resource script implements the logic of the resource.</span></span> <span data-ttu-id="47de0-133">In diesem Modul fügen Sie die drei Funktionen `Get-TargetResource`, `Set-TargetResource`, und `Test-TargetResource` hinzu.</span><span class="sxs-lookup"><span data-stu-id="47de0-133">In this module, you must include three functions called `Get-TargetResource`, `Set-TargetResource`, and `Test-TargetResource`.</span></span> <span data-ttu-id="47de0-134">Alle drei Funktionen verwenden einen Parametersatz, der identisch mit dem Satz von Eigenschaften ist, die im MOF-Schema definiert wurden, das Sie für die Ressource erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="47de0-134">All three functions must take a parameter set that is identical to the set of properties defined in the MOF schema that you created for your resource.</span></span> <span data-ttu-id="47de0-135">In diesem Dokument wird dieser Eigenschaftensatz als die „Ressourceneigenschaften“ bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="47de0-135">In this document, this set of properties is referred to as the "resource properties."</span></span> <span data-ttu-id="47de0-136">Speichern Sie die drei Funktionen in einer Datei namens `<ResourceName>.psm1`.</span><span class="sxs-lookup"><span data-stu-id="47de0-136">Store these three functions in a file called `<ResourceName>.psm1`.</span></span> <span data-ttu-id="47de0-137">Im folgenden Beispiel werden die Funktionen in einer Datei namens `Demo_IISWebsite.psm1` gespeichert.</span><span class="sxs-lookup"><span data-stu-id="47de0-137">In the following example, the functions are stored in a file called `Demo_IISWebsite.psm1`.</span></span>

> [!NOTE]
> <span data-ttu-id="47de0-138">Wenn Sie das gleiche Konfigurationsskript mehrfach für Ihre Ressource ausführen, sollten keine Fehler ausgegeben werden, und die Ressource sollte sich im gleichen Zustand wie nach der einmaligen Ausführung des Skripts befinden.</span><span class="sxs-lookup"><span data-stu-id="47de0-138">When you run the same configuration script on your resource more than once, you should receive no errors and the resource should remain in the same state as running the script once.</span></span> <span data-ttu-id="47de0-139">Stellen Sie dazu sicher, dass Ihre Funktionen `Get-TargetResource` und `Test-TargetResource` die Ressource unverändert verlassen, und dass das Ergebnis der Funktion `Set-TargetResource` mit denselben Parameterwerten immer identisch ist, egal, ob Sie die Funktion einmal oder mehrfach aufrufen.</span><span class="sxs-lookup"><span data-stu-id="47de0-139">To accomplish this, ensure that your `Get-TargetResource` and `Test-TargetResource` functions leave the resource unchanged, and that invoking the `Set-TargetResource` function more than once in a sequence with the same parameter values is always equivalent to invoking it once.</span></span>

<span data-ttu-id="47de0-140">Verwenden Sie in der Implementierung der Funktion `Get-TargetResource` die Schlüsselressourcen-Eigenschaftswerte, die als Parameter bereitgestellt werden, um den Status der angegebenen Ressourceninstanz zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="47de0-140">In the `Get-TargetResource` function implementation, use the key resource property values that are provided as parameters to check the status of the specified resource instance.</span></span> <span data-ttu-id="47de0-141">Diese Funktion muss eine Hashtabelle zurückgeben, in der alle Ressourceneigenschaften als Schlüssel und die tatsächlichen Werte dieser Eigenschaften als die entsprechende Werte aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="47de0-141">This function must return a hash table that lists all the resource properties as keys and the actual values of these properties as the corresponding values.</span></span> <span data-ttu-id="47de0-142">Der folgende Code gibt ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="47de0-142">The following code provides an example.</span></span>

```powershell
# DSC uses the Get-TargetResource function to fetch the status of the resource instance
# specified in the parameters for the target machine
function Get-TargetResource
{
    param
    (
        [ValidateSet("Present", "Absent")]
        [string]$Ensure = "Present",

        [Parameter(Mandatory)]
        [ValidateNotNullOrEmpty()]
        [string]$Name,

        [Parameter(Mandatory)]
        [ValidateNotNullOrEmpty()]
        [string]$PhysicalPath,

        [ValidateSet("Started", "Stopped")]
        [string]$State = "Started",

        [string]$ApplicationPool,

        [string[]]$BindingInfo,

        [string[]]$Protocol
    )

        $getTargetResourceResult = $null;

        <#
          Insert logic that uses the mandatory parameter values to get the website and
          assign it to a variable called $Website
          Set $ensureResult to "Present" if the requested website exists and to "Absent" otherwise
        #>

        # Add all Website properties to the hash table
        # This simple example assumes that $Website is not null
        $getTargetResourceResult = @{
            Name = $Website.Name
            Ensure = $ensureResult
            PhysicalPath = $Website.physicalPath
            State = $Website.state
            ID = $Website.id
            ApplicationPool = $Website.applicationPool
            Protocol = $Website.bindings.Collection.protocol
            Binding = $Website.bindings.Collection.bindingInformation
        }

        $getTargetResourceResult
}
```

<span data-ttu-id="47de0-143">Abhängig von den Werten, die für die Ressourceneigenschaften im Konfigurationsskript angegeben sind, muss die Funktion `Set-TargetResource` eine der folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="47de0-143">Depending on the values that are specified for the resource properties in the configuration script, the `Set-TargetResource` must do one of the following:</span></span>

- <span data-ttu-id="47de0-144">Erstellen einer neuen Website</span><span class="sxs-lookup"><span data-stu-id="47de0-144">Create a new website</span></span>
- <span data-ttu-id="47de0-145">Aktualisieren einer vorhandenen Website</span><span class="sxs-lookup"><span data-stu-id="47de0-145">Update an existing website</span></span>
- <span data-ttu-id="47de0-146">Löschen einer vorhandenen Website</span><span class="sxs-lookup"><span data-stu-id="47de0-146">Delete an existing website</span></span>

<span data-ttu-id="47de0-147">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="47de0-147">The following example illustrates this.</span></span>

```powershell
# The Set-TargetResource function is used to create, delete or configure a website on the target machine.
function Set-TargetResource
{
    [CmdletBinding(SupportsShouldProcess=$true)]
    param
    (
        [ValidateSet("Present", "Absent")]
        [string]$Ensure = "Present",

        [Parameter(Mandatory)]
        [ValidateNotNullOrEmpty()]
        [string]$Name,

        [Parameter(Mandatory)]
        [ValidateNotNullOrEmpty()]
        [string]$PhysicalPath,

        [ValidateSet("Started", "Stopped")]
        [string]$State = "Started",

        [string]$ApplicationPool,

        [string[]]$BindingInfo,

        [string[]]$Protocol
    )

    <#
        If Ensure is set to "Present" and the website specified in the mandatory input parameters
          does not exist, then create it using the specified parameter values
        Else, if Ensure is set to "Present" and the website does exist, then update its properties
          to match the values provided in the non-mandatory parameter values
        Else, if Ensure is set to "Absent" and the website does not exist, then do nothing
        Else, if Ensure is set to "Absent" and the website does exist, then delete the website
    #>
}
```

<span data-ttu-id="47de0-148">Schließlich muss die Funktion `Test-TargetResource` den gleichen Parametersatz verwenden wie `Get-TargetResource` und `Set-TargetResource`.</span><span class="sxs-lookup"><span data-stu-id="47de0-148">Finally, the `Test-TargetResource` function must take the same parameter set as `Get-TargetResource` and `Set-TargetResource`.</span></span> <span data-ttu-id="47de0-149">Überprüfen Sie in der Implementierung von `Test-TargetResource` den Status der in den Schlüsselparametern angegebenen Ressourceninstanz.</span><span class="sxs-lookup"><span data-stu-id="47de0-149">In your implementation of `Test-TargetResource`, check the status of the resource instance that is specified in the key parameters.</span></span> <span data-ttu-id="47de0-150">Wenn der aktuelle Status der Ressourceninstanz nicht mit den im Parametersatz angegebenen Werten übereinstimmt, wird `$false` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="47de0-150">If the actual status of the resource instance does not match the values specified in the parameter set, return `$false`.</span></span> <span data-ttu-id="47de0-151">Andernfalls wird `$true` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="47de0-151">Otherwise, return `$true`.</span></span>

<span data-ttu-id="47de0-152">Der folgende Code implementiert die Funktion `Test-TargetResource`.</span><span class="sxs-lookup"><span data-stu-id="47de0-152">The following code implements the `Test-TargetResource` function.</span></span>

```powershell
function Test-TargetResource
{
    [CmdletBinding()]
    [OutputType([System.Boolean])]
    param
    (
        [ValidateSet("Present","Absent")]
        [System.String]
        $Ensure,

        [parameter(Mandatory = $true)]
        [System.String]
        $Name,

        [parameter(Mandatory = $true)]
        [System.String]
        $PhysicalPath,

        [ValidateSet("Started","Stopped")]
        [System.String]
        $State,

        [System.String[]]
        $Protocol,

        [System.String[]]
        $BindingData,

        [System.String]
        $ApplicationPool
    )

    # Get the current state
    $currentState = Get-TargetResource -Ensure $Ensure -Name $Name -PhysicalPath $PhysicalPath -State $State -ApplicationPool $ApplicationPool -BindingInfo $BindingInfo -Protocol $Protocol

    # Write-Verbose "Use this cmdlet to deliver information about command processing."

    # Write-Debug "Use this cmdlet to write debug information while troubleshooting."

    # Include logic to
    $result = [System.Boolean]
    # Add logic to test whether the website is present and its status matches the supplied
    # parameter values. If it does, return true. If it does not, return false.
    $result
}
```

> [!NOTE]
> <span data-ttu-id="47de0-153">Verwenden Sie zum einfacheren Debuggen in Ihrer Implementierung der vorherigen drei Funktionen das Cmdlet `Write-Verbose`.</span><span class="sxs-lookup"><span data-stu-id="47de0-153">For easier debugging, use the `Write-Verbose` cmdlet in your implementation of the previous three functions.</span></span> <span data-ttu-id="47de0-154">Dieses Cmdlet schreibt Text in den Stream für ausführliche Meldungen.</span><span class="sxs-lookup"><span data-stu-id="47de0-154">This cmdlet writes text to the verbose message stream.</span></span> <span data-ttu-id="47de0-155">Standardmäßig wird der Stream für ausführliche Meldungen nicht angezeigt. Sie können ihn jedoch anzeigen, indem Sie den Wert der Variablen **$VerbosePreference** ändern den Parameter **Verbose** in „DSC cmdlets = new“ verwenden.</span><span class="sxs-lookup"><span data-stu-id="47de0-155">By default, the verbose message stream is not displayed, but you can display it by changing the value of the **$VerbosePreference** variable or by using the **Verbose** parameter in the DSC cmdlets = new.</span></span>

### <a name="creating-the-module-manifest"></a><span data-ttu-id="47de0-156">Erstellen das Modulmanifest</span><span class="sxs-lookup"><span data-stu-id="47de0-156">Creating the module manifest</span></span>

<span data-ttu-id="47de0-157">Verwenden Sie abschließend das Cmdlet `New-ModuleManifest`, um eine `<ResourceName>.psd1`-Datei für das benutzerdefinierte Ressourcenmodul zu definieren.</span><span class="sxs-lookup"><span data-stu-id="47de0-157">Finally, use the `New-ModuleManifest` cmdlet to define a `<ResourceName>.psd1` file for your custom resource module.</span></span> <span data-ttu-id="47de0-158">Wenn Sie dieses Cmdlet aufrufen, verweisen Sie auf die im vorherigen Abschnitt beschriebene Skriptmoduldatei (.psm1).</span><span class="sxs-lookup"><span data-stu-id="47de0-158">When you invoke this cmdlet, reference the script module (.psm1) file described in the previous section.</span></span> <span data-ttu-id="47de0-159">Fügen Sie `Get-TargetResource`, `Set-TargetResource` und `Test-TargetResource` zur Liste der zu exportierenden Funktionen hinzu.</span><span class="sxs-lookup"><span data-stu-id="47de0-159">Include `Get-TargetResource`, `Set-TargetResource`, and `Test-TargetResource` in the list of functions to export.</span></span> <span data-ttu-id="47de0-160">Im Folgenden finden Sie eine Beispielmanifestdatei.</span><span class="sxs-lookup"><span data-stu-id="47de0-160">Following is an example manifest file.</span></span>

```powershell
# Module manifest for module 'Demo.IIS.Website'
#
# Generated on: 1/10/2013
#

@{

# Script module or binary module file associated with this manifest.
# RootModule = ''

# Version number of this module.
ModuleVersion = '1.0'

# ID used to uniquely identify this module
GUID = '6AB5ED33-E923-41d8-A3A4-5ADDA2B301DE'

# Author of this module
Author = 'Contoso'

# Company or vendor of this module
CompanyName = 'Contoso'

# Copyright statement for this module
Copyright = 'Contoso. All rights reserved.'

# Description of the functionality provided by this module
Description = 'This Module is used to support the creation and configuration of IIS Websites through Get, Set and Test API on the DSC managed nodes.'

# Minimum version of the Windows PowerShell engine required by this module
PowerShellVersion = '4.0'

# Minimum version of the common language runtime (CLR) required by this module
CLRVersion = '4.0'

# Modules that must be imported into the global environment prior to importing this module
RequiredModules = @("WebAdministration")

# Modules to import as nested modules of the module specified in RootModule/ModuleToProcess
NestedModules = @("Demo_IISWebsite.psm1")

# Functions to export from this module
FunctionsToExport = @("Get-TargetResource", "Set-TargetResource", "Test-TargetResource")

# Cmdlets to export from this module
#CmdletsToExport = '*'

# HelpInfo URI of this module
# HelpInfoURI = ''
}
```

## <a name="supporting-psdscrunascredential"></a><span data-ttu-id="47de0-161">Unterstützung von PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="47de0-161">Supporting PsDscRunAsCredential</span></span>

> [!Note]
> <span data-ttu-id="47de0-162">**PsDscRunAsCredential** wird in PowerShell 5.0 und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="47de0-162">**PsDscRunAsCredential** is supported in PowerShell 5.0 and later.</span></span>

<span data-ttu-id="47de0-163">Mithilfe der Eigenschaft **PsDscRunAsCredential** kann im Ressourcenblock [DSC configurations](../configurations/configurations.md) angegeben werden, dass die Ressource mit einem festgelegten Satz an Anmeldeinformationen ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="47de0-163">The **PsDscRunAsCredential** property can be used in [DSC configurations](../configurations/configurations.md) resource block to specify that the resource should be run under a specified set of credentials.</span></span> <span data-ttu-id="47de0-164">Weitere Informationen finden Sie unter [Ausführen von DSC mit Benutzeranmeldeinformationen](../configurations/runAsUser.md).</span><span class="sxs-lookup"><span data-stu-id="47de0-164">For more information, see [Running DSC with user credentials](../configurations/runAsUser.md).</span></span>

<span data-ttu-id="47de0-165">Um aus einer benutzerdefinierten Ressource auf den Benutzerkontext zuzugreifen, können Sie die automatische Variable `$PsDscContext` verwenden.</span><span class="sxs-lookup"><span data-stu-id="47de0-165">To access the user context from within a custom resource, you can use the automatic variable `$PsDscContext`.</span></span>

<span data-ttu-id="47de0-166">Beispielsweise wird mit dem folgenden Code der Benutzerkontext für die Ressourcenausführung in den ausführlichen Ausgabestream geschrieben:</span><span class="sxs-lookup"><span data-stu-id="47de0-166">For example the following code would write the user context under which the resource is running to the verbose output stream:</span></span>

```powershell
if (PsDscContext.RunAsUser) {
    Write-Verbose "User: $PsDscContext.RunAsUser";
}
```

## <a name="rebooting-the-node"></a><span data-ttu-id="47de0-167">Neustarten des Knotens</span><span class="sxs-lookup"><span data-stu-id="47de0-167">Rebooting the Node</span></span>

<span data-ttu-id="47de0-168">Wenn die Aktionen in Ihrer `Set-TargetResource`-Funktion einen Neustart erfordern, können Sie ein globales Flag verwenden, um den lokalen Konfigurations-Manager zum Neustart des Knotens anzuweisen.</span><span class="sxs-lookup"><span data-stu-id="47de0-168">If the actions taken in your `Set-TargetResource` function require a reboot, you can use a global flag to tell the LCM to reboot the Node.</span></span> <span data-ttu-id="47de0-169">Dieser Neustart tritt unmittelbar nach Abschluss der `Set-TargetResource`-Funktion auf.</span><span class="sxs-lookup"><span data-stu-id="47de0-169">This reboot occurs directly after the `Set-TargetResource` function completes.</span></span>

<span data-ttu-id="47de0-170">Fügen Sie die folgende Codezeile in Ihre `Set-TargetResource`-Funktion ein.</span><span class="sxs-lookup"><span data-stu-id="47de0-170">Inside your `Set-TargetResource` function, add the following line of code.</span></span>

```powershell
# Include this line if the resource requires a system reboot.
$global:DSCMachineStatus = 1
```

<span data-ttu-id="47de0-171">Damit der lokale Konfigurations-Manager den Knoten neu startet, muss das Flag **RebootNodeIfNeeded** auf `$true` festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="47de0-171">In order for the LCM to reboot the Node, the **RebootNodeIfNeeded** flag needs to be set to `$true`.</span></span>
<span data-ttu-id="47de0-172">Außerdem sollte die Einstellung **ActionAfterReboot** auf **ContinueConfiguration** festgelegt sein. Dabei handelt es sich um die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="47de0-172">The **ActionAfterReboot** setting should also be set to **ContinueConfiguration** , which is the default.</span></span> <span data-ttu-id="47de0-173">Weitere Informationen zum Konfigurieren des lokalen Konfigurations-Managers finden Sie unter [Configuring the Local Configuration Manager (Konfigurieren des lokalen Konfigurations-Managers)](../managing-nodes/metaConfig.md) und [Configuring the Local Configuration Manager (v4) (Konfigurieren des lokalen Konfigurations-Managers (PowerShell 4.0))](../managing-nodes/metaConfig4.md).</span><span class="sxs-lookup"><span data-stu-id="47de0-173">For more information on configuring the LCM, see [Configuring the Local Configuration Manager](../managing-nodes/metaConfig.md), or [Configuring the Local Configuration Manager (v4)](../managing-nodes/metaConfig4.md).</span></span>
