---
description: Verschiedene Editionen von PowerShell werden auf unterschiedlichen zugrunde liegenden Laufzeiten ausgeführt.
Locale: en-US
ms.date: 03/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_powershell_editions?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PowerShell_Editions
ms.openlocfilehash: 3b1b938874b36919a1a0627f3b492cbc961e4a2f
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600717"
---
# <a name="about-powershell-editions"></a><span data-ttu-id="fa070-103">Informationen zu PowerShell-Editionen</span><span class="sxs-lookup"><span data-stu-id="fa070-103">About PowerShell Editions</span></span>

## <a name="short-description"></a><span data-ttu-id="fa070-104">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fa070-104">Short Description</span></span>
<span data-ttu-id="fa070-105">Verschiedene Editionen von PowerShell werden auf unterschiedlichen zugrunde liegenden Laufzeiten ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="fa070-105">Different editions of PowerShell run on different underlying runtimes.</span></span>

## <a name="long-description"></a><span data-ttu-id="fa070-106">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fa070-106">Long Description</span></span>

<span data-ttu-id="fa070-107">In PowerShell 5,1 gibt es mehrere *Editionen* von PowerShell, die jeweils in einer anderen .NET-Laufzeit ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="fa070-107">From PowerShell 5.1, there are multiple *editions* of PowerShell that each run on a different .NET runtime.</span></span> <span data-ttu-id="fa070-108">Ab PowerShell 6,2 gibt es zwei Editionen von PowerShell:</span><span class="sxs-lookup"><span data-stu-id="fa070-108">As of PowerShell 6.2 there are two editions of PowerShell:</span></span>

- <span data-ttu-id="fa070-109">**Desktop**, der auf .NET Framework ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="fa070-109">**Desktop**, which runs on .NET Framework.</span></span> <span data-ttu-id="fa070-110">PowerShell 4 und niedriger als auch PowerShell 5,1 in voll funktionsfähigen Windows-Editionen wie Windows Desktop, Windows Server, Windows Server Core und die meisten anderen Windows-Betriebssysteme sind Desktop Edition.</span><span class="sxs-lookup"><span data-stu-id="fa070-110">PowerShell 4 and below, as well as PowerShell 5.1 on full-featured Windows editions like Windows Desktop, Windows Server, Windows Server Core and most other Windows operating systems are Desktop edition.</span></span>
  <span data-ttu-id="fa070-111">Dies ist die Original-PowerShell-Edition.</span><span class="sxs-lookup"><span data-stu-id="fa070-111">This is the original PowerShell edition.</span></span>
- <span data-ttu-id="fa070-112">**Core**, das unter .net Core ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="fa070-112">**Core**, which runs on .NET Core.</span></span> <span data-ttu-id="fa070-113">PowerShell 6,0 und höher sowie PowerShell 5,1 auf einigen reduzierten Windows-Editionen wie Windows Nano Server und Windows IOT, wo .NET Framework nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="fa070-113">PowerShell 6.0 and above, as well as PowerShell 5.1 on some reduced-footprint Windows editions such as Windows Nano Server and Windows IoT where .NET Framework is unavailable.</span></span>

<span data-ttu-id="fa070-114">Da die Edition von PowerShell Ihrer .NET-Laufzeit entspricht, ist Sie der primäre Indikator für die Kompatibilität von .NET-API und PowerShell-Modulen. einige .NET-APIs,-Typen oder-Methoden sind nicht in .net-Laufzeiten verfügbar. Dies wirkt sich auf PowerShell-Skripts und-Module aus, die von ihnen abhängen.</span><span class="sxs-lookup"><span data-stu-id="fa070-114">Because the edition of PowerShell corresponds to its .NET runtime, it is the primary indicator of .NET API and PowerShell module compatibility; some .NET APIs, types or methods are not available in both .NET runtimes and this affects PowerShell scripts and modules that depend on them.</span></span>

## <a name="the-psedition-automatic-variable"></a><span data-ttu-id="fa070-115">Die `$PSEdition` Automatische Variable.</span><span class="sxs-lookup"><span data-stu-id="fa070-115">The `$PSEdition` automatic variable</span></span>

<span data-ttu-id="fa070-116">In PowerShell 5,1 und höher können Sie herausfinden, welche Edition Sie mit der `$PSEdition` automatischen Variablen ausführen:</span><span class="sxs-lookup"><span data-stu-id="fa070-116">In PowerShell 5.1 and above, you can find out what edition you are running with the `$PSEdition` automatic variable:</span></span>

```powershell
$PSEdition
```

```Output
Core
```

<span data-ttu-id="fa070-117">In PowerShell 4 und niedriger ist die Variable nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="fa070-117">In PowerShell 4 and below, this variable does not exist.</span></span> <span data-ttu-id="fa070-118">`$PSEdition` NULL sollte als identisch mit dem Wert behandelt werden `Desktop` .</span><span class="sxs-lookup"><span data-stu-id="fa070-118">`$PSEdition` being null should be treated as the same as having the value `Desktop`.</span></span>

### <a name="edition-in-psversiontable"></a><span data-ttu-id="fa070-119">Edition in `$PSVersionTable`</span><span class="sxs-lookup"><span data-stu-id="fa070-119">Edition in `$PSVersionTable`</span></span>

<span data-ttu-id="fa070-120">Die `$PSVersionTable` Automatische Variable enthält auch Editions Informationen in PowerShell 5,1 und höher:</span><span class="sxs-lookup"><span data-stu-id="fa070-120">The `$PSVersionTable` automatic variable also has edition information in PowerShell 5.1 and above:</span></span>

```powershell
$PSVersionTable
```

```Output
Name                           Value
----                           -----
PSVersion                      6.2.0-rc.1
PSEdition                      Core           # <-- Edition information
GitCommitId                    6.2.0-rc.1
OS                             Microsoft Windows 10.0.18865
Platform                       Win32NT
PSCompatibleVersions           {1.0, 2.0, 3.0, 4.0...}
PSRemotingProtocolVersion      2.3
SerializationVersion           1.1.0.1
WSManStackVersion              3.0
```

<span data-ttu-id="fa070-121">Das `PSEdition` Feld hat denselben Wert wie die `$PSEdition` Automatische Variable.</span><span class="sxs-lookup"><span data-stu-id="fa070-121">The `PSEdition` field will have the same value as the `$PSEdition` automatic variable.</span></span>

## <a name="the-compatiblepseditions-module-manifest-field"></a><span data-ttu-id="fa070-122">Das `CompatiblePSEditions` Modul Manifest-Feld</span><span class="sxs-lookup"><span data-stu-id="fa070-122">The `CompatiblePSEditions` module manifest field</span></span>

<span data-ttu-id="fa070-123">PowerShell-Module können mithilfe des- `CompatiblePSEditions` Felds des Modul Manifests deklarieren, mit welchen PowerShell-Editionen Sie kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="fa070-123">PowerShell modules can declare what editions of PowerShell they are compatible with using the `CompatiblePSEditions` field of the module manifest.</span></span>

<span data-ttu-id="fa070-124">Ein Modul Manifest deklariert beispielsweise die Kompatibilität mit den `Desktop` `Core` Editionen und von PowerShell:</span><span class="sxs-lookup"><span data-stu-id="fa070-124">For example, a module manifest declaring compatibility with both `Desktop` and `Core` editions of PowerShell:</span></span>

```powershell
@{
    ModuleVersion = '1.0'
    FunctionsToExport = @('Test-MyModule')
    CompatiblePSEditions = @('Desktop', 'Core')
}
```

<span data-ttu-id="fa070-125">Ein Beispiel für ein Modul Manifest mit nur `Desktop` Kompatibilität:</span><span class="sxs-lookup"><span data-stu-id="fa070-125">An example of a module manifest with only `Desktop` compatibility:</span></span>

```powershell
@{
    ModuleVersion = '1.0'
    FunctionsToExport = @('Test-MyModule')
    CompatiblePSEditions = @('Desktop')
}
```

<span data-ttu-id="fa070-126">Das Weglassen des `CompatiblePSEditions` Felds aus einem Modul Manifest hat denselben Effekt wie das Festlegen von `Desktop` , da Module, die vor der Einführung dieses Felds erstellt wurden, implizit für diese Edition geschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="fa070-126">Omitting the `CompatiblePSEditions` field from a module manifest will have the same effect as setting it to `Desktop`, since modules created before this field was introduced were implicitly written for this edition.</span></span>

<span data-ttu-id="fa070-127">Für Module, die nicht als Teil von Windows ausgeliefert werden (d. h. Module, die Sie im Katalog schreiben oder installieren), ist dieses Feld nur Informationszwecken. PowerShell ändert das Verhalten nicht auf der Grundlage des `CompatiblePSEditions` Felds, sondern macht es für das `PSModuleInfo` Objekt, das von zurückgegeben wird, `Get-Module` für Ihre eigene Logik verfügbar:</span><span class="sxs-lookup"><span data-stu-id="fa070-127">For modules not shipped as part of Windows (i.e. modules you write or install from the gallery), this field is informational only; PowerShell does not change behavior based on the `CompatiblePSEditions` field, but does expose it on the `PSModuleInfo` object (returned by `Get-Module`) for your own logic:</span></span>

```powershell
New-ModuleManifest -Path .\TestModuleWithEdition.psd1 -CompatiblePSEditions Desktop,Core -PowerShellVersion '5.1'
$ModuleInfo = Test-ModuleManifest -Path .\TestModuleWithEdition.psd1
$ModuleInfo.CompatiblePSEditions
```

```Output
Desktop
Core
```

> [!NOTE]
> <span data-ttu-id="fa070-128">Das `CompatiblePSEditions` Modul Feld ist nur mit PowerShell 5,1 und höher kompatibel.</span><span class="sxs-lookup"><span data-stu-id="fa070-128">The `CompatiblePSEditions` module field is only compatible with PowerShell 5.1 and above.</span></span>
> <span data-ttu-id="fa070-129">Das Einschließen dieses Felds führt dazu, dass ein Modul mit PowerShell 4 und niedriger inkompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="fa070-129">Including this field will cause a module to be incompatible with PowerShell 4 and below.</span></span>
> <span data-ttu-id="fa070-130">Da das Feld rein informativ ist, kann es in späteren PowerShell-Versionen sicher weggelassen werden.</span><span class="sxs-lookup"><span data-stu-id="fa070-130">Since the field is purely informational, it can be safely omitted in later PowerShell versions.</span></span>

<span data-ttu-id="fa070-131">In PowerShell 6,1 `Get-Module -ListAvailable` hat der Formatierer des Formatierers aktualisiert, um die Editions Kompatibilität der einzelnen Module anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="fa070-131">In PowerShell 6.1, `Get-Module -ListAvailable` has had its formatter updated to display the edition-compatibility of each module:</span></span>

```PowerShell
Get-Module -ListAvailable
```

```Output

    Directory: C:\Users\me\Documents\PowerShell\Modules

ModuleType Version    Name                                PSEdition ExportedCommands
---------- -------    ----                                --------- ----------------
Script     1.4.0      Az                                  Core,Desk
Script     1.3.1      Az.Accounts                         Core,Desk {Disable-AzDataCollection, Disable-AzContextAutosave, E...
Script     1.0.1      Az.Aks                              Core,Desk {Get-AzAks, New-AzAks, Remove-AzAks, Import-AzAksCreden...

...

Script     4.4.0      Pester                              Desk      {Describe, Context, It, Should...}
Script     1.18.0     PSScriptAnalyzer                    Desk      {Get-ScriptAnalyzerRule, Invoke-ScriptAnalyzer, Invoke-...
Script     1.0.0      WindowsCompatibility                Core      {Initialize-WinSession, Add-WinFunction, Invoke-WinComm...

```

## <a name="edition-compatibility-for-modules-that-ship-as-part-of-windows"></a><span data-ttu-id="fa070-132">Editions Kompatibilität für Module, die als Teil von Windows ausgeliefert werden</span><span class="sxs-lookup"><span data-stu-id="fa070-132">Edition-compatibility for modules that ship as part of Windows</span></span>

<span data-ttu-id="fa070-133">Bei Modulen, die Teil von Windows sind (oder als Teil einer Rolle oder eines Features installiert werden), wird das Feld von PowerShell 6,1 und höher `CompatiblePSEditions` anders behandelt.</span><span class="sxs-lookup"><span data-stu-id="fa070-133">For modules that come as part of Windows (or are installed as part of a role or feature), PowerShell 6.1 and above treat the `CompatiblePSEditions` field differently.</span></span> <span data-ttu-id="fa070-134">Solche Module befinden sich im Verzeichnis "Windows PowerShell-Systemmodule" ( `%windir%\System\WindowsPowerShell\v1.0\Modules` ).</span><span class="sxs-lookup"><span data-stu-id="fa070-134">Such modules are found in the Windows PowerShell system modules directory (`%windir%\System\WindowsPowerShell\v1.0\Modules`).</span></span>

<span data-ttu-id="fa070-135">Bei Modulen, die aus diesem Verzeichnis geladen oder darin enthalten sind, verwendet PowerShell 6,1 und höher das- `CompatiblePSEditions` Feld, um zu bestimmen, ob das Modul mit der aktuellen Sitzung kompatibel ist und sich entsprechend verhält.</span><span class="sxs-lookup"><span data-stu-id="fa070-135">For modules loaded from or found in this directory, PowerShell 6.1 and above uses the `CompatiblePSEditions` field to determine whether the module will be compatible with the current session and behaves accordingly.</span></span>

<span data-ttu-id="fa070-136">Wenn `Import-Module` verwendet wird, wird ein Modul ohne `Core` in `CompatiblePSEditions` nicht importiert, und es wird ein Fehler angezeigt:</span><span class="sxs-lookup"><span data-stu-id="fa070-136">When `Import-Module` is used, a module without `Core` in `CompatiblePSEditions` will not be imported and an error will be displayed:</span></span>

```powershell
Import-Module BitsTransfer
```

```Output
Import-Module : Module 'C:\WINDOWS\system32\WindowsPowerShell\v1.0\Modules\BitsTransfer\BitsTransfer.psd1' does not support current PowerShell edition 'Core'. Its supported editions are 'Desktop'. Use 'Import-Module -SkipEditionCheck' to ignore the compatibility of this module.
At line:1 char:1
+ Import-Module BitsTransfer
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : ResourceUnavailable: (C:\WINDOWS\system32\u2026r\BitsTransfer.psd1:String) [Import-Module], InvalidOperationException
+ FullyQualifiedErrorId : Modules_PSEditionNotSupported,Microsoft.PowerShell.Commands.ImportModuleCommand
```

<span data-ttu-id="fa070-137">Wenn `Get-Module -ListAvailable` verwendet wird, werden Module ohne `Core` in `CompatiblePSEditions` nicht angezeigt:</span><span class="sxs-lookup"><span data-stu-id="fa070-137">When `Get-Module -ListAvailable` is used, modules without `Core` in `CompatiblePSEditions` will not be displayed:</span></span>

```powershell
Get-Module -ListAvailable BitsTransfer
```

```Output
# No output
```

<span data-ttu-id="fa070-138">In beiden Fällen kann der `-SkipEditionCheck` Switch-Parameter verwendet werden, um dieses Verhalten zu überschreiben:</span><span class="sxs-lookup"><span data-stu-id="fa070-138">In both cases, the `-SkipEditionCheck` switch parameter can be used to override this behavior:</span></span>

```powershell
Get-Module -ListAvailable -SkipEditionCheck BitsTransfer
```

```Output

    Directory: C:\WINDOWS\system32\WindowsPowerShell\v1.0\Modules

ModuleType Version    Name                                PSEdition ExportedCommands
---------- -------    ----                                --------- ----------------
Manifest   2.0.0.0    BitsTransfer                        Desk      {Add-BitsFile, Complete-BitsTransfer, Get-BitsTransfer,...

```

> [!WARNING]
> <span data-ttu-id="fa070-139">`Import-Module -SkipEditionCheck` scheint für ein Modul erfolgreich zu sein, aber die Verwendung dieses Moduls führt zu einem späteren Zeitpunkt das Risiko einer Inkompatibilität. während das Laden des Moduls anfänglich erfolgreich ist, kann ein Befehl später eine inkompatible API und einen Fehler auslösen.</span><span class="sxs-lookup"><span data-stu-id="fa070-139">`Import-Module -SkipEditionCheck` may appear to succeed for a module, but using that module runs the risk of encountering an incompatibility later on; while loading the module initially succeeds, a command may later call an incompatible API and fail spontaneously.</span></span>

## <a name="authoring-powershell-modules-for-edition-cross-compatibility"></a><span data-ttu-id="fa070-140">Erstellen von PowerShell-Modulen für die Editions übergreifende Kompatibilität</span><span class="sxs-lookup"><span data-stu-id="fa070-140">Authoring PowerShell modules for edition cross-compatibility</span></span>

<span data-ttu-id="fa070-141">Wenn Sie ein PowerShell-Modul schreiben, das sowohl `Desktop` als auch `Core` Editionen von PowerShell als Ziel hat, gibt es Dinge, die Sie tun können, um die übergreifende Kompatibilität sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="fa070-141">When writing a PowerShell module to target both `Desktop` and `Core` editions of PowerShell, there are things you can do to ensure cross-edition compatibility.</span></span>

<span data-ttu-id="fa070-142">Die einzige echte Möglichkeit zum bestätigen und kontinuierlichen Validieren der Kompatibilität besteht darin, Tests für Ihr Skript oder Modul zu schreiben und Sie für alle Versionen und Editionen von PowerShell auszuführen, mit denen Sie Kompatibilität benötigen.</span><span class="sxs-lookup"><span data-stu-id="fa070-142">The only true way to confirm and continually validate compatibility however is to write tests for your script or module and run them on all versions and editions of PowerShell you need compatibility with.</span></span> <span data-ttu-id="fa070-143">Ein empfohlenes Test Framework hierfür ist [Pester][].</span><span class="sxs-lookup"><span data-stu-id="fa070-143">A recommended testing framework for this is [Pester][].</span></span>

### <a name="powershell-script"></a><span data-ttu-id="fa070-144">PowerShell-Skript</span><span class="sxs-lookup"><span data-stu-id="fa070-144">PowerShell script</span></span>

<span data-ttu-id="fa070-145">In der Sprache funktioniert PowerShell zwischen den Editionen. Dabei handelt es sich um die Cmdlets, Module und .NET-APIs, die von der Editions Kompatibilität betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="fa070-145">As a language, PowerShell works the same between editions; it is the cmdlets, modules and .NET APIs you use that are affected by edition compatibility.</span></span>

<span data-ttu-id="fa070-146">Im Allgemeinen funktionieren Skripts, die in PowerShell 6,1 und höher funktionieren, mit Windows PowerShell 5,1, es gibt jedoch einige Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="fa070-146">Generally, scripts that work in PowerShell 6.1 and above will work with Windows PowerShell 5.1, but there are some exceptions.</span></span>

<span data-ttu-id="fa070-147">Version 1.18.0 das [psscriptanalyzer][] -Modul verfügt über Regeln wie [`PSUseCompatibleCommands`][] und [`PSUseCompatibleTypes`][] , die die möglicherweise nicht kompatible Verwendung von Befehlen und .NET-APIs in PowerShell-Skripts erkennen können.</span><span class="sxs-lookup"><span data-stu-id="fa070-147">Version 1.18.0 [PSScriptAnalyzer][] module has rules like [`PSUseCompatibleCommands`][] and [`PSUseCompatibleTypes`][] that are able to detect possibly incompatible usage of commands and .NET APIs in PowerShell scripts.</span></span>

### <a name="net-assemblies"></a><span data-ttu-id="fa070-148">.NET-Assemblys</span><span class="sxs-lookup"><span data-stu-id="fa070-148">.NET assemblies</span></span>

<span data-ttu-id="fa070-149">Wenn Sie ein binäres Modul oder ein Modul schreiben, das aus Quellcode generierte .NET-Assemblys (DLLs) enthält, sollten Sie eine Kompilierung für [.NET Standard][] und [PowerShell Standard][] zur Kompilierzeit-Kompatibilitäts Überprüfung von .net und PowerShell-API-Kompatibilität durchgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="fa070-149">If you are writing a binary module or a module that incorporates .NET assemblies (DLLs) generated from source code, you should compile against [.NET Standard][] and [PowerShell Standard][] for compile-time compatibility validation of .NET and PowerShell API compatibility.</span></span>

<span data-ttu-id="fa070-150">Obwohl diese Bibliotheken einige Kompatibilitäts Möglichkeiten zur Kompilierzeit überprüfen können, sind Sie nicht in der Lage, mögliche Verhaltensunterschiede zwischen den Editionen abzufangen.</span><span class="sxs-lookup"><span data-stu-id="fa070-150">Although these libraries are able to check some compatibility at compile time, they won't be able to catch possible behavioral differences between editions.</span></span> <span data-ttu-id="fa070-151">Hierfür müssen Sie weiterhin Tests schreiben.</span><span class="sxs-lookup"><span data-stu-id="fa070-151">For this you must still write tests.</span></span>

## <a name="see-also"></a><span data-ttu-id="fa070-152">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fa070-152">See also</span></span>

- [<span data-ttu-id="fa070-153">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="fa070-153">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)
- [<span data-ttu-id="fa070-154">Import-Module</span><span class="sxs-lookup"><span data-stu-id="fa070-154">Import-Module</span></span>](xref:Microsoft.PowerShell.Core.Import-Module)
- [<span data-ttu-id="fa070-155">Get-Module</span><span class="sxs-lookup"><span data-stu-id="fa070-155">Get-Module</span></span>](xref:Microsoft.PowerShell.Core.Get-Module)
- [<span data-ttu-id="fa070-156">Module mit kompatiblen PowerShell-Editionen</span><span class="sxs-lookup"><span data-stu-id="fa070-156">Modules with compatible PowerShell Editions</span></span>](/powershell/scripting/gallery/concepts/module-psedition-support)

[Pester]: https://github.com/pester/Pester/wiki/Pester
[PSScriptAnalyzer]: https://github.com/PowerShell/PSScriptAnalyzer
["Psuabcompatiblecommands"]: https://github.com/PowerShell/PSScriptAnalyzer/blob/master/RuleDocumentation/UseCompatibleCommands.md
[`PSUseCompatibleCommands`]: https://github.com/PowerShell/PSScriptAnalyzer/blob/master/RuleDocumentation/UseCompatibleCommands.md
["Psutarcompatibletypes"]: https://github.com/PowerShell/PSScriptAnalyzer/blob/master/RuleDocumentation/UseCompatibleTypes.md
[`PSUseCompatibleTypes`]: https://github.com/PowerShell/PSScriptAnalyzer/blob/master/RuleDocumentation/UseCompatibleTypes.md
[.NET Standard]: /dotnet/standard/net-standard
[PowerShell Standard]: https://devblogs.microsoft.com/powershell/powershell-standard-library-build-single-module-that-works-across-windows-powershell-and-powershell-core/
