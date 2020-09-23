---
ms.date: 06/10/2020
contributor: manikb
keywords: gallery,powershell,cmdlet,psget
title: Module mit kompatiblen PowerShell-Editionen
ms.openlocfilehash: 522493714916e9fd21f67a6e7bc2cfb165041807
ms.sourcegitcommit: 4a283fe5419f47102e6c1de7060880a934842ee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2020
ms.locfileid: "84671409"
---
# <a name="modules-with-compatible-powershell-editions"></a><span data-ttu-id="b5d0c-103">Module mit kompatiblen PowerShell-Editionen</span><span class="sxs-lookup"><span data-stu-id="b5d0c-103">Modules with compatible PowerShell Editions</span></span>

<span data-ttu-id="b5d0c-104">Ab Version 5.1 steht PowerShell in verschiedenen Editionen zur Verfügung, die unterschiedliche Funktionsgruppen und Plattformkompatibilität bieten.</span><span class="sxs-lookup"><span data-stu-id="b5d0c-104">Starting with version 5.1, PowerShell is available in different editions, which denote varying feature sets and platform compatibility.</span></span>

- <span data-ttu-id="b5d0c-105">**Desktop-Edition:** Basiert auf .NET Framework, gilt für Windows PowerShell v4.0 und niedriger sowie Windows PowerShell 5.1 für Windows Desktop, Windows Server, Windows Server Core und die meisten anderen Editionen von Windows.</span><span class="sxs-lookup"><span data-stu-id="b5d0c-105">**Desktop Edition:** Built on .NET Framework, applies to Windows PowerShell v4.0 and below as well as Windows PowerShell 5.1 on Windows Desktop, Windows Server, Windows Server Core and most other Windows editions.</span></span>
- <span data-ttu-id="b5d0c-106">**Core-Edition:** Basiert auf .NET Core, gilt für PowerShell Core 6.0 und höher sowie Windows PowerShell 5.1 auf reduzierten Editionen von Windows wie z.B. Windows IoT und Windows Nanoserver.</span><span class="sxs-lookup"><span data-stu-id="b5d0c-106">**Core Edition:** Built on .NET Core, applies to PowerShell Core 6.0 and above as well as Windows PowerShell 5.1 on reduced footprint Windows Editions such as Windows IoT and Windows Nanoserver.</span></span>

<span data-ttu-id="b5d0c-107">Weitere Informationen zu den PowerShell-Editionen finden Sie unter [about_PowerShell_Editions][].</span><span class="sxs-lookup"><span data-stu-id="b5d0c-107">For more information on PowerShell editions, see [about_PowerShell_Editions][].</span></span>

## <a name="declaring-compatible-editions"></a><span data-ttu-id="b5d0c-108">Deklarieren von kompatiblen Editionen</span><span class="sxs-lookup"><span data-stu-id="b5d0c-108">Declaring compatible editions</span></span>

<span data-ttu-id="b5d0c-109">Mithilfe des Modulmanifestschlüssels `CompatiblePSEditions` können Modulautoren ihre Module als kompatibel mit einer oder mehreren PowerShell-Editionen deklarieren.</span><span class="sxs-lookup"><span data-stu-id="b5d0c-109">Module authors can declare their modules to be compatible with one or more PowerShell editions using the `CompatiblePSEditions` module manifest key.</span></span> <span data-ttu-id="b5d0c-110">Dieser Schlüssel wird nur auf PowerShell 5.1 oder höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b5d0c-110">This key is only supported on PowerShell 5.1 or later.</span></span>

> [!NOTE]
> <span data-ttu-id="b5d0c-111">Sobald mit dem Schlüssel `CompatiblePSEditions` ein Modulmanifest angegeben wurde oder dieses die Variable `$PSEdition` verwendet, kann es nicht in PowerShell-Version v4 oder niedriger importiert werden.</span><span class="sxs-lookup"><span data-stu-id="b5d0c-111">Once a module manifest is specified with the `CompatiblePSEditions` key or uses the `$PSEdition` variable, it can not be imported on PowerShell v4 or lower.</span></span>

```powershell
New-ModuleManifest -Path .\TestModuleWithEdition.psd1 -CompatiblePSEditions Desktop,Core -PowerShellVersion 5.1
$ModuleInfo = Test-ModuleManifest -Path .\TestModuleWithEdition.psd1
$ModuleInfo.CompatiblePSEditions
```

```Output
Desktop
Core
```

```powershell
$ModuleInfo | Get-Member CompatiblePSEditions
```

```Output
   TypeName: System.Management.Automation.PSModuleInfo

Name                 MemberType Definition
----                 ---------- ----------
CompatiblePSEditions Property   System.Collections.Generic.IEnumerable[string] CompatiblePSEditions {get;}
```

<span data-ttu-id="b5d0c-112">Beim Abrufen einer Liste der verfügbaren Module können Sie sie nach PowerShell-Editionen filtern.</span><span class="sxs-lookup"><span data-stu-id="b5d0c-112">When getting a list of available modules, you can filter the list by PowerShell edition.</span></span>

```powershell
Get-Module -ListAvailable -PSEdition Desktop
```

```Output
    Directory: C:\Program Files\WindowsPowerShell\Modules

ModuleType Version    Name                                ExportedCommands
---------- -------    ----                                ----------------
Manifest   1.0        ModuleWithPSEditions
```

```powershell
Get-Module -ListAvailable -PSEdition Core | % CompatiblePSEditions
```

```Output
Desktop
Core
```

<span data-ttu-id="b5d0c-113">Ab PowerShell 6 wird anhand des Werts `CompatiblePSEditions` entschieden, ob ein Modul beim Import aus `$env:windir\System32\WindowsPowerShell\v1.0\Modules` kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="b5d0c-113">Beginning in PowerShell 6, the `CompatiblePSEditions` value is used to decide if a module is compatible when modules are imported from `$env:windir\System32\WindowsPowerShell\v1.0\Modules`.</span></span>
<span data-ttu-id="b5d0c-114">Dieses Verhalten gilt nur für Windows.</span><span class="sxs-lookup"><span data-stu-id="b5d0c-114">This behavior only applies to Windows.</span></span> <span data-ttu-id="b5d0c-115">Ansonsten wird der Wert nur als Metadaten verwendet.</span><span class="sxs-lookup"><span data-stu-id="b5d0c-115">Outside of this scenario, the value is only used as metadata.</span></span>

## <a name="finding-compatible-modules"></a><span data-ttu-id="b5d0c-116">Suchen nach kompatiblen Modulen</span><span class="sxs-lookup"><span data-stu-id="b5d0c-116">Finding compatible modules</span></span>

<span data-ttu-id="b5d0c-117">Benutzer des PowerShell-Katalogs finden mithilfe der Tags **PSEdition_Desktop** und **PSEdition_Core** eine Liste der in einer bestimmten PowerShell-Edition unterstützten Module.</span><span class="sxs-lookup"><span data-stu-id="b5d0c-117">PowerShell Gallery users can find the list of modules supported on a specific PowerShell Edition using tags **PSEdition_Desktop** and **PSEdition_Core**.</span></span>

<span data-ttu-id="b5d0c-118">Module ohne die Tags **PSEdition_Desktop** und **PSEditon_Core** sollten in PowerShell Desktop-Editionen keine Probleme bereiten.</span><span class="sxs-lookup"><span data-stu-id="b5d0c-118">Modules without **PSEdition_Desktop** and **PSEdition_Core** tags are considered to work fine on PowerShell Desktop editions.</span></span>

```powershell
# Find modules supported on PowerShell Desktop edition
Find-Module -Tag PSEdition_Desktop

# Find modules supported on PowerShell Core editions
Find-Module -Tag PSEdition_Core
```

## <a name="targeting-multiple-editions"></a><span data-ttu-id="b5d0c-119">Festlegen von mehreren Editionen als Ziel</span><span class="sxs-lookup"><span data-stu-id="b5d0c-119">Targeting multiple editions</span></span>

<span data-ttu-id="b5d0c-120">Modulautoren können ein einzelnes Modul veröffentlichen, bei dem eine oder beide PowerShell-Editionen (Desktop und Core) als Ziel festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="b5d0c-120">Module authors can publish a single module targeting to either or both PowerShell editions (Desktop and Core).</span></span>

<span data-ttu-id="b5d0c-121">Ein einzelnes Modul kann sowohl in der Desktop- als auch in der Core-Edition funktionieren, wenn der Modulautor die dafür benötigte Logik mithilfe der Variable `$PSEdition` zu „RootModule“ oder dem Modulmanifest hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="b5d0c-121">A single module can work on both Desktop and Core editions, in that module author has to add required logic in either RootModule or in the module manifest using `$PSEdition` variable.</span></span> <span data-ttu-id="b5d0c-122">Module können über zwei Gruppen kompilierter DLLs verfügen, die beide **CoreCLR** und **FullCLR** als Ziel verwenden.</span><span class="sxs-lookup"><span data-stu-id="b5d0c-122">Modules can have two sets of compiled DLLs targeting both **CoreCLR** and **FullCLR**.</span></span> <span data-ttu-id="b5d0c-123">Die folgenden Paketoptionen enthalten Logik zum Laden der korrekten DLLs:</span><span class="sxs-lookup"><span data-stu-id="b5d0c-123">Here are the packaging options with logic for loading proper DLLs.</span></span>

### <a name="option-1-packaging-a-module-for-targeting-multiple-versions-and-multiple-editions-of-powershell"></a><span data-ttu-id="b5d0c-124">Option 1: Packen eines Moduls für die Adressierung mehrerer Versionen und Editionen von PowerShell</span><span class="sxs-lookup"><span data-stu-id="b5d0c-124">Option 1: Packaging a module for targeting multiple versions and multiple editions of PowerShell</span></span>

<span data-ttu-id="b5d0c-125">Inhalt des Modulordners</span><span class="sxs-lookup"><span data-stu-id="b5d0c-125">Module folder contents</span></span>

- <span data-ttu-id="b5d0c-126">Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll</span><span class="sxs-lookup"><span data-stu-id="b5d0c-126">Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll</span></span>
- <span data-ttu-id="b5d0c-127">Microsoft.Windows.PowerShell.ScriptAnalyzer.dll</span><span class="sxs-lookup"><span data-stu-id="b5d0c-127">Microsoft.Windows.PowerShell.ScriptAnalyzer.dll</span></span>
- <span data-ttu-id="b5d0c-128">PSScriptAnalyzer.psd1</span><span class="sxs-lookup"><span data-stu-id="b5d0c-128">PSScriptAnalyzer.psd1</span></span>
- <span data-ttu-id="b5d0c-129">PSScriptAnalyzer.psm1</span><span class="sxs-lookup"><span data-stu-id="b5d0c-129">PSScriptAnalyzer.psm1</span></span>
- <span data-ttu-id="b5d0c-130">ScriptAnalyzer.format.ps1xml</span><span class="sxs-lookup"><span data-stu-id="b5d0c-130">ScriptAnalyzer.format.ps1xml</span></span>
- <span data-ttu-id="b5d0c-131">ScriptAnalyzer.types.ps1xml</span><span class="sxs-lookup"><span data-stu-id="b5d0c-131">ScriptAnalyzer.types.ps1xml</span></span>
- <span data-ttu-id="b5d0c-132">coreclr\Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll</span><span class="sxs-lookup"><span data-stu-id="b5d0c-132">coreclr\Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll</span></span>
- <span data-ttu-id="b5d0c-133">coreclr\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll</span><span class="sxs-lookup"><span data-stu-id="b5d0c-133">coreclr\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll</span></span>
- <span data-ttu-id="b5d0c-134">en-US\about_PSScriptAnalyzer.help.txt</span><span class="sxs-lookup"><span data-stu-id="b5d0c-134">en-US\about_PSScriptAnalyzer.help.txt</span></span>
- <span data-ttu-id="b5d0c-135">en-US\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll-Help.xml</span><span class="sxs-lookup"><span data-stu-id="b5d0c-135">en-US\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll-Help.xml</span></span>
- <span data-ttu-id="b5d0c-136">PSv3\Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll</span><span class="sxs-lookup"><span data-stu-id="b5d0c-136">PSv3\Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll</span></span>
- <span data-ttu-id="b5d0c-137">PSv3\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll</span><span class="sxs-lookup"><span data-stu-id="b5d0c-137">PSv3\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll</span></span>
- <span data-ttu-id="b5d0c-138">Settings\CmdletDesign.psd1</span><span class="sxs-lookup"><span data-stu-id="b5d0c-138">Settings\CmdletDesign.psd1</span></span>
- <span data-ttu-id="b5d0c-139">Settings\DSC.psd1</span><span class="sxs-lookup"><span data-stu-id="b5d0c-139">Settings\DSC.psd1</span></span>
- <span data-ttu-id="b5d0c-140">Settings\ScriptFunctions.psd1</span><span class="sxs-lookup"><span data-stu-id="b5d0c-140">Settings\ScriptFunctions.psd1</span></span>
- <span data-ttu-id="b5d0c-141">Settings\ScriptingStyle.psd1</span><span class="sxs-lookup"><span data-stu-id="b5d0c-141">Settings\ScriptingStyle.psd1</span></span>
- <span data-ttu-id="b5d0c-142">Settings\ScriptSecurity.psd1</span><span class="sxs-lookup"><span data-stu-id="b5d0c-142">Settings\ScriptSecurity.psd1</span></span>

<span data-ttu-id="b5d0c-143">Inhalt der Datei `PSScriptAnalyzer.psd1`:</span><span class="sxs-lookup"><span data-stu-id="b5d0c-143">Contents of `PSScriptAnalyzer.psd1` file</span></span>

```powershell
@{

# Author of this module
Author = 'Microsoft Corporation'

# Script module or binary module file associated with this manifest.
RootModule = 'PSScriptAnalyzer.psm1'

# Version number of this module.
ModuleVersion = '1.6.1'

# ---
}
```

<span data-ttu-id="b5d0c-144">Die nachstehende Logik lädt die erforderlichen Assemblys abhängig von der aktuellen Edition oder Version.</span><span class="sxs-lookup"><span data-stu-id="b5d0c-144">Below logic loads the required assemblies depending on the current edition or version.</span></span>

<span data-ttu-id="b5d0c-145">Inhalt der Datei `PSScriptAnalyzer.psm1`:</span><span class="sxs-lookup"><span data-stu-id="b5d0c-145">Contents of `PSScriptAnalyzer.psm1` file:</span></span>

```powershell
#
# Script module for module 'PSScriptAnalyzer'
#
Set-StrictMode -Version Latest

# Set up some helper variables to make it easier to work with the module
$PSModule = $ExecutionContext.SessionState.Module
$PSModuleRoot = $PSModule.ModuleBase

# Import the appropriate nested binary module based on the current PowerShell version
$binaryModuleRoot = $PSModuleRoot


if (($PSVersionTable.Keys -contains "PSEdition") -and ($PSVersionTable.PSEdition -ne 'Desktop')) {
    $binaryModuleRoot = Join-Path -Path $PSModuleRoot -ChildPath 'coreclr'
}
else
{
    if ($PSVersionTable.PSVersion -lt [Version]'5.0')
    {
        $binaryModuleRoot = Join-Path -Path $PSModuleRoot -ChildPath 'PSv3'
    }
}

$binaryModulePath = Join-Path -Path $binaryModuleRoot -ChildPath 'Microsoft.Windows.PowerShell.ScriptAnalyzer.dll'
$binaryModule = Import-Module -Name $binaryModulePath -PassThru

# When the module is unloaded, remove the nested binary module that was loaded with it
$PSModule.OnRemove = {
    Remove-Module -ModuleInfo $binaryModule
}
```

### <a name="option-2-use-psedition-variable-in-the-psd1-file-to-load-the-proper-dlls"></a><span data-ttu-id="b5d0c-146">Option 2: Verwenden der Variable „$PSEdition“ in der PSD1-Datei zum Laden der korrekten DLLs</span><span class="sxs-lookup"><span data-stu-id="b5d0c-146">Option 2: Use $PSEdition variable in the PSD1 file to load the proper DLLs</span></span>

<span data-ttu-id="b5d0c-147">In PS 5.1 oder höher ist die globale Variable `$PSEdition` in der Modulmanifestdatei zulässig.</span><span class="sxs-lookup"><span data-stu-id="b5d0c-147">In PS 5.1 or newer, `$PSEdition` global variable is allowed in the module manifest file.</span></span> <span data-ttu-id="b5d0c-148">Durch die Verwendung dieser Variable kann der Modulautor die bedingten Werte in der Modulmanifestdatei angeben.</span><span class="sxs-lookup"><span data-stu-id="b5d0c-148">Using this variable, module author can specify the conditional values in the module manifest file.</span></span> <span data-ttu-id="b5d0c-149">Auf die Variable `$PSEdition` kann im eingeschränkten Sprachmodus oder in einem Data-Abschnitt verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="b5d0c-149">`$PSEdition` variable can be referenced in restricted language mode or a Data section.</span></span>

<span data-ttu-id="b5d0c-150">Beispiel für eine Modulmanifestdatei mit dem Schlüssel `CompatiblePSEditions`:</span><span class="sxs-lookup"><span data-stu-id="b5d0c-150">Sample module manifest file with `CompatiblePSEditions` key.</span></span>

```powershell
@{
    # Script module or binary module file associated with this manifest.
    RootModule = if($PSEdition -eq 'Core')
    {
        'coreclr\MyCoreClrRM.dll'
    }
    else # Desktop
    {
        'clr\MyFullClrRM.dll'
    }

    # Supported PSEditions
    CompatiblePSEditions = 'Desktop', 'Core'

    # Modules to import as nested modules of the module specified in RootModule/ModuleToProcess
    NestedModules = if($PSEdition -eq 'Core')
    {
        'coreclr\MyCoreClrNM1.dll',
        'coreclr\MyCoreClrNM2.dll'
    }
    else # Desktop
    {
        'clr\MyFullClrNM1.dll',
        'clr\MyFullClrNM2.dll'
    }
}
```

<span data-ttu-id="b5d0c-151">Modulinhalte</span><span class="sxs-lookup"><span data-stu-id="b5d0c-151">Module contents</span></span>

- <span data-ttu-id="b5d0c-152">ModuleWithEditions\ModuleWithEditions.psd1</span><span class="sxs-lookup"><span data-stu-id="b5d0c-152">ModuleWithEditions\ModuleWithEditions.psd1</span></span>
- <span data-ttu-id="b5d0c-153">ModuleWithEditions\clr\MyFullClrNM1.dll</span><span class="sxs-lookup"><span data-stu-id="b5d0c-153">ModuleWithEditions\clr\MyFullClrNM1.dll</span></span>
- <span data-ttu-id="b5d0c-154">ModuleWithEditions\clr\MyFullClrNM2.dll</span><span class="sxs-lookup"><span data-stu-id="b5d0c-154">ModuleWithEditions\clr\MyFullClrNM2.dll</span></span>
- <span data-ttu-id="b5d0c-155">ModuleWithEditions\clr\MyFullClrRM.dll</span><span class="sxs-lookup"><span data-stu-id="b5d0c-155">ModuleWithEditions\clr\MyFullClrRM.dll</span></span>
- <span data-ttu-id="b5d0c-156">ModuleWithEditions\coreclr\MyCoreClrNM1.dll</span><span class="sxs-lookup"><span data-stu-id="b5d0c-156">ModuleWithEditions\coreclr\MyCoreClrNM1.dll</span></span>
- <span data-ttu-id="b5d0c-157">ModuleWithEditions\coreclr\MyCoreClrNM2.dll</span><span class="sxs-lookup"><span data-stu-id="b5d0c-157">ModuleWithEditions\coreclr\MyCoreClrNM2.dll</span></span>
- <span data-ttu-id="b5d0c-158">ModuleWithEditions\coreclr\MyCoreClrRM.dll</span><span class="sxs-lookup"><span data-stu-id="b5d0c-158">ModuleWithEditions\coreclr\MyCoreClrRM.dll</span></span>

## <a name="more-details"></a><span data-ttu-id="b5d0c-159">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b5d0c-159">More details</span></span>

[<span data-ttu-id="b5d0c-160">Skripts mit PowerShell-Editionen</span><span class="sxs-lookup"><span data-stu-id="b5d0c-160">Scripts with PSEditions</span></span>](script-psedition-support.md)

[<span data-ttu-id="b5d0c-161">Unterstützung von PowerShell-Editionen im PowerShell-Katalog</span><span class="sxs-lookup"><span data-stu-id="b5d0c-161">PSEditions support on PowerShellGallery</span></span>](../how-to/finding-packages/searching-by-compatibility.md)

[<span data-ttu-id="b5d0c-162">Modulmanifest aktualisieren</span><span class="sxs-lookup"><span data-stu-id="b5d0c-162">Update module manifest</span></span>](/powershell/module/powershellget/update-modulemanifest)

<span data-ttu-id="b5d0c-163">[about_PowerShell_Editions][]</span><span class="sxs-lookup"><span data-stu-id="b5d0c-163">[about_PowerShell_Editions][]</span></span>

[about_PowerShell_Editions]: /powershell/module/Microsoft.PowerShell.Core/About/about_PowerShell_Editions
