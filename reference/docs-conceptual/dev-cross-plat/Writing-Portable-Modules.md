---
ms.date: 10/21/2020
keywords: powershell,cmdlet
title: Schreiben von portablen Modulen
description: In diesem Artikel wird das Erstellen neuer Module oder das Aktualisieren vorhandener Module zu dem Zweck erläutert, dass sie übergreifend auf allen von PowerShell unterstützten Plattformen funktionieren.
ms.openlocfilehash: 6d5c36263c3c6d1219f963cea2e94ae92b07e863
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500792"
---
# <a name="portable-modules"></a><span data-ttu-id="ac517-104">Portable Module</span><span class="sxs-lookup"><span data-stu-id="ac517-104">Portable Modules</span></span>

<span data-ttu-id="ac517-105">Windows PowerShell ist für [.NET Framework][] geschrieben, PowerShell Core hingegen für [.NET Core][].</span><span class="sxs-lookup"><span data-stu-id="ac517-105">Windows PowerShell is written for [.NET Framework][] while PowerShell Core is written for [.NET Core][].</span></span> <span data-ttu-id="ac517-106">Portable Module sind Module, die sowohl in Windows PowerShell als auch PowerShell Core funktionieren.</span><span class="sxs-lookup"><span data-stu-id="ac517-106">Portable modules are modules that work in both Windows PowerShell and PowerShell Core.</span></span> <span data-ttu-id="ac517-107">.NET Framework und .NET Core sind zwar hoch kompatibel, doch gibt es zwischen beiden Unterschiede bei den verfügbaren APIs.</span><span class="sxs-lookup"><span data-stu-id="ac517-107">While .NET Framework and .NET Core are highly compatible, there are differences in the available APIs between the two.</span></span> <span data-ttu-id="ac517-108">Es gibt auch Unterschiede bei den in Windows PowerShell und PowerShell Core verfügbaren APIs.</span><span class="sxs-lookup"><span data-stu-id="ac517-108">There are also differences in the APIs available in Windows PowerShell and PowerShell Core.</span></span> <span data-ttu-id="ac517-109">Bei Modulen, die in beiden Umgebungen verwendet werden sollen, müssen diese Unterschiede beachtet werden.</span><span class="sxs-lookup"><span data-stu-id="ac517-109">Modules intended to be used in both environments need to be aware of these differences.</span></span>

## <a name="porting-an-existing-module"></a><span data-ttu-id="ac517-110">Portieren eines vorhandenen Moduls</span><span class="sxs-lookup"><span data-stu-id="ac517-110">Porting an existing module</span></span>

### <a name="porting-a-pssnapin"></a><span data-ttu-id="ac517-111">Portieren eines PSSnapIn</span><span class="sxs-lookup"><span data-stu-id="ac517-111">Porting a PSSnapIn</span></span>

<span data-ttu-id="ac517-112">PowerShell [SnapIns](/powershell/scripting/developer/cmdlet/modules-and-snap-ins) werden in PowerShell Core nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ac517-112">PowerShell [SnapIns](/powershell/scripting/developer/cmdlet/modules-and-snap-ins) aren't supported in PowerShell Core.</span></span> <span data-ttu-id="ac517-113">Es ist jedoch einfach, ein PSSnapIn in ein PowerShell-Modul zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="ac517-113">However, it's trivial to convert a PSSnapIn to a PowerShell module.</span></span> <span data-ttu-id="ac517-114">In der Regel befindet sich der PSSnapIn-Registrierungscode in einer einzelnen Quelldatei einer Klasse, die von [PSSnapIn][] abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="ac517-114">Typically, the PSSnapIn registration code is in a single source file of a class that derives from [PSSnapIn][].</span></span> <span data-ttu-id="ac517-115">Entfernen Sie diese Quelldatei aus dem Build, denn sie ist nicht mehr erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ac517-115">Remove this source file from the build; it's no longer needed.</span></span>

<span data-ttu-id="ac517-116">Erstellen Sie mit [New-ModuleManifest][] ein neues Modulmanifest, das den PSSnapIn-Registrierungscode überflüssig macht.</span><span class="sxs-lookup"><span data-stu-id="ac517-116">Use [New-ModuleManifest][] to create a new module manifest that replaces the need for the PSSnapIn registration code.</span></span> <span data-ttu-id="ac517-117">Einige der Werte aus dem **PSSnapIn** (z.B. **Description** ) können innerhalb des Modulmanifests wiederverwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ac517-117">Some of the values from the **PSSnapIn** (such as **Description** ) can be reused within the module manifest.</span></span>

<span data-ttu-id="ac517-118">Die **RootModule** -Eigenschaft im Modulmanifest sollte auf den Namen der Assembly (DLL) festgelegt werden, die die Cmdlets implementiert.</span><span class="sxs-lookup"><span data-stu-id="ac517-118">The **RootModule** property in the module manifest should be set to the name of the assembly (dll) implementing the cmdlets.</span></span>

### <a name="the-net-portability-analyzer-aka-apiport"></a><span data-ttu-id="ac517-119">Der .NET Portability Analyzer (auch bekannt als APIPort)</span><span class="sxs-lookup"><span data-stu-id="ac517-119">The .NET Portability Analyzer (aka APIPort)</span></span>

<span data-ttu-id="ac517-120">Um für Windows PowerShell geschriebene Module zum Arbeiten mit PowerShell Core zu portieren, beginnen Sie mit dem [.NET Portability Analyzer][].</span><span class="sxs-lookup"><span data-stu-id="ac517-120">To port modules written for Windows PowerShell to work with PowerShell Core, start with the [.NET Portability Analyzer][].</span></span> <span data-ttu-id="ac517-121">Führen Sie dieses Tool für die kompilierte Assembly aus, um zu bestimmen, ob die im Modul verwendeten .NET-APIs mit .NET Framework, .NET Core und anderen .NET-Runtimes kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="ac517-121">Run this tool against your compiled assembly to determine if the .NET APIs used in the module are compatible with .NET Framework, .NET Core, and other .NET runtimes.</span></span> <span data-ttu-id="ac517-122">Das Tool schlägt alternative APIs vor, wenn sie vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="ac517-122">The tool suggests alternate APIs if they exist.</span></span> <span data-ttu-id="ac517-123">Andernfalls müssen Sie unter Umständen [Runtimeüberprüfungen][] hinzufügen und in bestimmten Runtimes nicht verfügbare Funktionen einschränken.</span><span class="sxs-lookup"><span data-stu-id="ac517-123">Otherwise, you may need to add [runtime checks][] and restrict capabilities not available in specific runtimes.</span></span>

## <a name="creating-a-new-module"></a><span data-ttu-id="ac517-124">Erstellen eines neuen Moduls</span><span class="sxs-lookup"><span data-stu-id="ac517-124">Creating a new module</span></span>

<span data-ttu-id="ac517-125">Wenn Sie ein neues Modul erstellen, sollten Sie die [.NET CLI][] verwenden.</span><span class="sxs-lookup"><span data-stu-id="ac517-125">If creating a new module, the recommendation is to use the [.NET CLI][].</span></span>

### <a name="installing-the-powershell-standard-module-template"></a><span data-ttu-id="ac517-126">Installieren der PowerShell Standard-Modulvorlage</span><span class="sxs-lookup"><span data-stu-id="ac517-126">Installing the PowerShell Standard module template</span></span>

<span data-ttu-id="ac517-127">Sobald die .NET CLI installiert ist, installieren Sie eine Vorlagenbibliothek zum Generieren eines einfachen PowerShell-Moduls.</span><span class="sxs-lookup"><span data-stu-id="ac517-127">Once the .NET CLI is installed, install a template library to generate a simple PowerShell module.</span></span>
<span data-ttu-id="ac517-128">Das Modul wird mit Windows PowerShell, PowerShell Core, Windows, Linux und macOS kompatibel sein.</span><span class="sxs-lookup"><span data-stu-id="ac517-128">The module will be compatible with Windows PowerShell, PowerShell Core, Windows, Linux, and macOS.</span></span>

<span data-ttu-id="ac517-129">Im folgenden Beispiel wird veranschaulicht, wie Sie die Vorlage installieren:</span><span class="sxs-lookup"><span data-stu-id="ac517-129">The following example shows how to install the template:</span></span>

```powershell
dotnet new -i Microsoft.PowerShell.Standard.Module.Template
```

```output
  Restoring packages for C:\Users\Steve\.templateengine\dotnetcli\v2.1.302\scratch\restore.csproj...
  Installing Microsoft.PowerShell.Standard.Module.Template 0.1.3.
  Generating MSBuild file C:\Users\Steve\.templateengine\dotnetcli\v2.1.302\scratch\obj\restore.csproj.nuget.g.props.
  Generating MSBuild file C:\Users\Steve\.templateengine\dotnetcli\v2.1.302\scratch\obj\restore.csproj.nuget.g.targets.
  Restore completed in 1.66 sec for C:\Users\Steve\.templateengine\dotnetcli\v2.1.302\scratch\restore.csproj.

Usage: new [options]

Options:
  -h, --help          Displays help for this command.
  -l, --list          Lists templates containing the specified name. If no name is specified, lists all templates.
  -n, --name          The name for the output being created. If no name is specified, the name of the current directory is used.
  -o, --output        Location to place the generated output.
  -i, --install       Installs a source or a template pack.
  -u, --uninstall     Uninstalls a source or a template pack.
  --nuget-source      Specifies a NuGet source to use during install.
  --type              Filters templates based on available types. Predefined values are "project", "item" or "other".
  --force             Forces content to be generated even if it would change existing files.
  -lang, --language   Filters templates based on language and specifies the language of the template to create.


Templates                        Short Name         Language          Tags
-----------------------------------------------------------------------------------------------
Console Application              console            [C#], F#, VB      Common/Console
Class library                    classlib           [C#], F#, VB      Common/Library
PowerShell Standard Module       psmodule           [C#]              Library/PowerShell/Module
...
```

### <a name="creating-a-new-module-project"></a><span data-ttu-id="ac517-130">Erstellen eines neuen Modulprojekts</span><span class="sxs-lookup"><span data-stu-id="ac517-130">Creating a new module project</span></span>

<span data-ttu-id="ac517-131">Nachdem die Vorlage installiert ist, können Sie ein neues PowerShell-Modulprojekt mit der Vorlage erstellen.</span><span class="sxs-lookup"><span data-stu-id="ac517-131">After the template is installed, you can create a new PowerShell module project using that template.</span></span> <span data-ttu-id="ac517-132">In diesem Beispiel wird das Beispielmodul „myModule“ genannt.</span><span class="sxs-lookup"><span data-stu-id="ac517-132">In this example, the sample module is called 'myModule'.</span></span>

```
PS> mkdir myModule

    Directory: C:\Users\Steve

Mode LastWriteTime Length Name
---- ------------- ------ ----
d----- 8/3/2018 2:41 PM myModule

PS> cd myModule
PS C:\Users\Steve\myModule> dotnet new psmodule

The template "PowerShell Standard Module" was created successfully.

Processing post-creation actions...
Running 'dotnet restore' on C:\Users\Steve\myModule\myModule.csproj...
  Restoring packages for C:\Users\Steve\myModule\myModule.csproj...
  Installing PowerShellStandard.Library 5.1.0.
  Generating MSBuild file C:\Users\Steve\myModule\obj\myModule.csproj.nuget.g.props.
  Generating MSBuild file C:\Users\Steve\myModule\obj\myModule.csproj.nuget.g.targets.
  Restore completed in 1.76 sec for C:\Users\Steve\myModule\myModule.csproj.

Restore succeeded.
```

### <a name="building-the-module"></a><span data-ttu-id="ac517-133">Erstellen des Moduls</span><span class="sxs-lookup"><span data-stu-id="ac517-133">Building the module</span></span>

<span data-ttu-id="ac517-134">Verwenden Sie standardmäßige .NET CLI-Befehle, um das Projekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ac517-134">Use standard .NET CLI commands to build the project.</span></span>

```powershell
dotnet build
```

```output
PS C:\Users\Steve\myModule> dotnet build
Microsoft (R) Build Engine version 15.7.179.6572 for .NET Core
Copyright (C) Microsoft Corporation. All rights reserved.

  Restore completed in 76.85 ms for C:\Users\Steve\myModule\myModule.csproj.
  myModule -> C:\Users\Steve\myModule\bin\Debug\netstandard2.0\myModule.dll

Build succeeded.
    0 Warning(s)
    0 Error(s)

Time Elapsed 00:00:05.40
```

### <a name="testing-the-module"></a><span data-ttu-id="ac517-135">Testen des Moduls</span><span class="sxs-lookup"><span data-stu-id="ac517-135">Testing the module</span></span>

<span data-ttu-id="ac517-136">Nach dem Erstellen des Moduls können Sie es importieren und das Beispielcmdlet ausführen.</span><span class="sxs-lookup"><span data-stu-id="ac517-136">After building the module, you can import it and execute the sample cmdlet.</span></span>

```powershell
Import-Module .\bin\Debug\netstandard2.0\myModule.dll
Test-SampleCmdlet -?
Test-SampleCmdlet -FavoriteNumber 7 -FavoritePet Cat
```

```output
NAME
    Test-SampleCmdlet

SYNTAX
    Test-SampleCmdlet [-FavoriteNumber] <int> [[-FavoritePet] {Cat | Dog | Horse}] [<CommonParameters>]


ALIASES
    None


REMARKS
    None


FavoriteNumber FavoritePet
-------------- -----------
             7 Cat
```

### <a name="debugging-the-module"></a><span data-ttu-id="ac517-137">Debuggen des Moduls</span><span class="sxs-lookup"><span data-stu-id="ac517-137">Debugging the module</span></span>

<span data-ttu-id="ac517-138">Eine Anleitung zum Einrichten von Visual Studio Code zum Debuggen des Moduls finden Sie unter [Verwenden von Visual Studio Code zum Debuggen kompilierter Cmdlets][].</span><span class="sxs-lookup"><span data-stu-id="ac517-138">For a guide on setting up Visual Studio Code to debug the module, see [Using Visual Studio Code for debugging compiled cmdlets][].</span></span>

## <a name="supporting-technologies"></a><span data-ttu-id="ac517-139">Unterstützende Technologien</span><span class="sxs-lookup"><span data-stu-id="ac517-139">Supporting technologies</span></span>

<span data-ttu-id="ac517-140">In den folgenden Abschnitten werden einige der von dieser Vorlage verwendeten Technologien ausführlich beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ac517-140">The following sections describe in detail some of the technologies used by this template.</span></span>

### <a name="net-standard-library"></a><span data-ttu-id="ac517-141">.NET Standard-Bibliothek</span><span class="sxs-lookup"><span data-stu-id="ac517-141">.NET Standard Library</span></span>

<span data-ttu-id="ac517-142">[.NET Standard][] ist eine formale Spezifikation von .NET-APIs, die in allen .NET-Implementierungen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="ac517-142">[.NET Standard][] is a formal specification of .NET APIs that are available in all .NET implementations.</span></span> <span data-ttu-id="ac517-143">Für .NET Standard bestimmter verwalteter Code kann mit den Versionen von .NET Framework und .NET Core verwendet werden, die mit dieser Version von .NET Standard kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="ac517-143">Managed code targeting .NET Standard works with the .NET Framework and .NET Core versions that are compatible with that version of the .NET Standard.</span></span>

> [!NOTE]
> <span data-ttu-id="ac517-144">Weil die API-Implementierung in .NET Core auch dann eine `PlatformNotSupportedException` während der Runtime auslösen kann, wenn eine API in .NET Standard vorhanden ist, sollten Sie als bewährte Methode in beiden Umgebungen Tests für das Modul ausführen, um die Kompatibilität mit Windows PowerShell und PowerShell Core zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="ac517-144">Although an API may exist in .NET Standard, the API implementation in .NET Core may throw a `PlatformNotSupportedException` at runtime, so to verify compatibility with Windows PowerShell and PowerShell Core, the best practice is to run tests for your module within both environments.</span></span>
> <span data-ttu-id="ac517-145">Führen Sie auch dann Tests unter Linux und macOS aus, wenn Ihr Modul plattformübergreifend verwendbar sein soll.</span><span class="sxs-lookup"><span data-stu-id="ac517-145">Also run tests on Linux and macOS if your module is intended to be cross-platform.</span></span>

<span data-ttu-id="ac517-146">Die Orientierung an .NET Standard stellt sicher, dass bei der Weiterentwicklung des Moduls nicht versehentlich inkompatible APIs in das Modul eingeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ac517-146">Targeting .NET Standard helps ensure that, as the module evolves, incompatible APIs don't accidentally get introduced into the module.</span></span> <span data-ttu-id="ac517-147">Inkompatibilitäten werden zum Zeitpunkt der Kompilierung statt während der Runtime festgestellt.</span><span class="sxs-lookup"><span data-stu-id="ac517-147">Incompatibilities are discovered at compile time instead of runtime.</span></span>

<span data-ttu-id="ac517-148">Solange Sie kompatible APIs verwenden, ist eine Orientierung an .NET Standard allerdings nicht erforderlich, damit ein Modul mit Windows PowerShell und PowerShell Core funktioniert.</span><span class="sxs-lookup"><span data-stu-id="ac517-148">However, it isn't required to target .NET Standard for a module to work with both Windows PowerShell and PowerShell Core, as long as you use compatible APIs.</span></span> <span data-ttu-id="ac517-149">Die Zwischensprache (Intermediate Language, IL) ist mit beiden Runtimes kompatibel.</span><span class="sxs-lookup"><span data-stu-id="ac517-149">The Intermediate Language (IL) is compatible between the two runtimes.</span></span> <span data-ttu-id="ac517-150">Sie können sich an .NET Framework 4.6.1 orientieren, das mit .NET Standard 2.0 kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="ac517-150">You can target .NET Framework 4.6.1, which is compatible with .NET Standard 2.0.</span></span> <span data-ttu-id="ac517-151">Wenn Sie außerhalb von .NET Standard 2.0 keine APIs verwenden, funktioniert Ihr Modul ohne erneute Kompilierung mit PowerShell Core 6.</span><span class="sxs-lookup"><span data-stu-id="ac517-151">If you don't use APIs outside of .NET Standard 2.0, then your module works with PowerShell Core 6 without recompilation.</span></span>

### <a name="powershell-standard-library"></a><span data-ttu-id="ac517-152">PowerShell Standard-Bibliothek</span><span class="sxs-lookup"><span data-stu-id="ac517-152">PowerShell Standard Library</span></span>

<span data-ttu-id="ac517-153">Die [PowerShell Standard][]-Bibliothek ist eine formale Spezifikation von PowerShell-APIs, die in allen PowerShell-Versionen verfügbar sind, die der Version dieses Standards entsprechen oder höher sind.</span><span class="sxs-lookup"><span data-stu-id="ac517-153">The [PowerShell Standard][] library is a formal specification of PowerShell APIs available in all PowerShell versions greater than or equal to the version of that standard.</span></span>

<span data-ttu-id="ac517-154">[PowerShell Standard 5.1][] ist z.B. sowohl mit Windows PowerShell 5.1 als auch mit PowerShell Core 6.0 oder höher kompatibel.</span><span class="sxs-lookup"><span data-stu-id="ac517-154">For example, [PowerShell Standard 5.1][] is compatible with both Windows PowerShell 5.1 and PowerShell Core 6.0 or newer.</span></span>

<span data-ttu-id="ac517-155">Sie sollten Ihr Modul mit der PowerShell Standard-Bibliothek kompilieren.</span><span class="sxs-lookup"><span data-stu-id="ac517-155">We recommend you compile your module using PowerShell Standard Library.</span></span> <span data-ttu-id="ac517-156">Die Bibliothek stellt sicher, dass die APIs verfügbar und sowohl in Windows PowerShell als auch PowerShell Core 6 implementiert sind.</span><span class="sxs-lookup"><span data-stu-id="ac517-156">The library ensures the APIs are available and implemented in both Windows PowerShell and PowerShell Core 6.</span></span>
<span data-ttu-id="ac517-157">PowerShell Standard soll stets aufwärtskompatibel sein.</span><span class="sxs-lookup"><span data-stu-id="ac517-157">PowerShell Standard is intended to always be forwards-compatible.</span></span> <span data-ttu-id="ac517-158">Ein mithilfe der PowerShell Standard-Bibliothek 5.1 erstelltes Modul ist immer mit zukünftigen Versionen von PowerShell kompatibel.</span><span class="sxs-lookup"><span data-stu-id="ac517-158">A module built using PowerShell Standard Library 5.1 will always be compatible with future versions of PowerShell.</span></span>

### <a name="module-manifest"></a><span data-ttu-id="ac517-159">Modulmanifest</span><span class="sxs-lookup"><span data-stu-id="ac517-159">Module Manifest</span></span>

#### <a name="indicating-compatibility-with-windows-powershell-and-powershell-core"></a><span data-ttu-id="ac517-160">Angeben der Kompatibilität mit Windows PowerShell und PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="ac517-160">Indicating Compatibility With Windows PowerShell and PowerShell Core</span></span>

<span data-ttu-id="ac517-161">Nachdem Sie überprüft haben, ob Ihr Modul sowohl mit Windows PowerShell als auch PowerShell Core funktioniert, sollte das Modulmanifest explizit mit der [CompatiblePSEditions][]-Eigenschaft die Kompatibilität angeben.</span><span class="sxs-lookup"><span data-stu-id="ac517-161">After validating that your module works with both Windows PowerShell and PowerShell Core, the module manifest should explicitly indicate compatibility by using the [CompatiblePSEditions][] property.</span></span> <span data-ttu-id="ac517-162">Der Wert `Desktop` bedeutet, dass das Modul mit Windows PowerShell kompatibel ist, während der Wert `Core` bedeutet, dass das Modul mit PowerShell Core kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="ac517-162">A value of `Desktop` means that the module is compatible with Windows PowerShell, while a value of `Core` means that the module is compatible with PowerShell Core.</span></span> <span data-ttu-id="ac517-163">Sowohl `Desktop` als auch `Core` einzubeziehen bedeutet, dass das Modul mit Windows PowerShell und PowerShell Core kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="ac517-163">Including both `Desktop` and `Core` means that the module is compatible with both Windows PowerShell and PowerShell Core.</span></span>

> [!NOTE]
> <span data-ttu-id="ac517-164">`Core` bedeutet nicht automatisch, dass das Modul mit Windows, Linux und macOS kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="ac517-164">`Core` does not automatically mean that the module is compatible with Windows, Linux, and macOS.</span></span>
> <span data-ttu-id="ac517-165">Die **CompatiblePSEditions** -Eigenschaft wurde in PowerShell v5 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ac517-165">The **CompatiblePSEditions** property was introduced in PowerShell v5.</span></span> <span data-ttu-id="ac517-166">Bei Modulmanifesten, die die **CompatiblePSEditions** -Eigenschaft verwenden, tritt in Versionen vor PowerShell v5 beim Laden ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="ac517-166">Module manifests that use the **CompatiblePSEditions** property fail to load in versions prior to PowerShell v5.</span></span>

### <a name="indicating-os-compatibility"></a><span data-ttu-id="ac517-167">Angeben der Betriebssystemkompatibilität</span><span class="sxs-lookup"><span data-stu-id="ac517-167">Indicating OS Compatibility</span></span>

<span data-ttu-id="ac517-168">Überprüfen Sie zunächst, ob Ihr Modul unter Linux und macOS funktioniert.</span><span class="sxs-lookup"><span data-stu-id="ac517-168">First, validate that your module works on Linux and macOS.</span></span> <span data-ttu-id="ac517-169">Geben Sie als Nächstes die Kompatibilität mit diesen Betriebssystemen im Modulmanifest an.</span><span class="sxs-lookup"><span data-stu-id="ac517-169">Next, indicate compatibility with those operating systems in the module manifest.</span></span> <span data-ttu-id="ac517-170">Dies erleichtert den Benutzern, die mit ihren Betriebssystemen kompatiblen Versionen Ihres Moduls zu finden, wenn es im [PowerShell-Katalog][] veröffentlicht wird.</span><span class="sxs-lookup"><span data-stu-id="ac517-170">This makes it easier for users to find your module for their operating system when published to the [PowerShell Gallery][].</span></span>

<span data-ttu-id="ac517-171">Im Modulmanifest hat die `PrivateData`-Eigenschaft eine `PSData`-Untereigenschaft.</span><span class="sxs-lookup"><span data-stu-id="ac517-171">Within the module manifest, the `PrivateData` property has a `PSData` sub-property.</span></span> <span data-ttu-id="ac517-172">Die optionale `Tags`-Eigenschaft von `PSData` akzeptiert ein Array von Werten, die im PowerShell-Katalog angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ac517-172">The optional `Tags` property of `PSData` takes an array of values that show up in PowerShell Gallery.</span></span> <span data-ttu-id="ac517-173">Der PowerShell-Katalog unterstützt die folgenden Kompatibilitätswerte:</span><span class="sxs-lookup"><span data-stu-id="ac517-173">The PowerShell Gallery supports the following compatibility values:</span></span>

| <span data-ttu-id="ac517-174">Tag</span><span class="sxs-lookup"><span data-stu-id="ac517-174">Tag</span></span>               | <span data-ttu-id="ac517-175">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ac517-175">Description</span></span>                                |
|-------------------|--------------------------------------------|
| <span data-ttu-id="ac517-176">PSEdition_Core</span><span class="sxs-lookup"><span data-stu-id="ac517-176">PSEdition_Core</span></span>    | <span data-ttu-id="ac517-177">Kompatibel mit PowerShell Core 6</span><span class="sxs-lookup"><span data-stu-id="ac517-177">Compatible with PowerShell Core 6</span></span>          |
| <span data-ttu-id="ac517-178">PSEdition_Desktop</span><span class="sxs-lookup"><span data-stu-id="ac517-178">PSEdition_Desktop</span></span> | <span data-ttu-id="ac517-179">Kompatibel mit Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ac517-179">Compatible with Windows PowerShell</span></span>         |
| <span data-ttu-id="ac517-180">Windows</span><span class="sxs-lookup"><span data-stu-id="ac517-180">Windows</span></span>           | <span data-ttu-id="ac517-181">Kompatibel mit Windows</span><span class="sxs-lookup"><span data-stu-id="ac517-181">Compatible with Windows</span></span>                    |
| <span data-ttu-id="ac517-182">Linux</span><span class="sxs-lookup"><span data-stu-id="ac517-182">Linux</span></span>             | <span data-ttu-id="ac517-183">Kompatibel mit Linux (keine spezifische Distribution)</span><span class="sxs-lookup"><span data-stu-id="ac517-183">Compatible with Linux (no specific distro)</span></span> |
| <span data-ttu-id="ac517-184">macOS</span><span class="sxs-lookup"><span data-stu-id="ac517-184">macOS</span></span>             | <span data-ttu-id="ac517-185">Kompatibel mit macOS</span><span class="sxs-lookup"><span data-stu-id="ac517-185">Compatible with macOS</span></span>                      |

<span data-ttu-id="ac517-186">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ac517-186">Example:</span></span>

```powershell
@{
    GUID = "4ae9fd46-338a-459c-8186-07f910774cb8"
    Author = "Microsoft Corporation"
    CompanyName = "Microsoft Corporation"
    Copyright = "(C) Microsoft Corporation. All rights reserved."
    HelpInfoUri = "https://go.microsoft.com/fwlink/?linkid=855962"
    ModuleVersion = "1.2.4"
    PowerShellVersion = "3.0"
    ClrVersion = "4.0"
    RootModule = "PackageManagement.psm1"
    Description = 'PackageManagement (a.k.a. OneGet) is a new way to discover and install software packages from around the web.
 It is a manager or multiplexer of existing package managers (also called package providers) that unifies Windows package management with a single Windows PowerShell interface. With PackageManagement, you can do the following.
  - Manage a list of software repositories in which packages can be searched, acquired and installed
  - Discover software packages
  - Seamlessly install, uninstall, and inventory packages from one or more software repositories'

    CmdletsToExport = @(
        'Find-Package',
        'Get-Package',
        'Get-PackageProvider',
        'Get-PackageSource',
        'Install-Package',
        'Import-PackageProvider'
        'Find-PackageProvider'
        'Install-PackageProvider'
        'Register-PackageSource',
        'Set-PackageSource',
        'Unregister-PackageSource',
        'Uninstall-Package'
        'Save-Package'
    )

    FormatsToProcess  = @('PackageManagement.format.ps1xml')

    PrivateData = @{
        PSData = @{
            Tags = @('PackageManagement', 'PSEdition_Core', 'PSEdition_Desktop', 'Windows', 'Linux', 'macOS')
            ProjectUri = 'https://oneget.org'
        }
    }
}
```

### <a name="dependency-on-native-libraries"></a><span data-ttu-id="ac517-187">Abhängigkeit von nativen Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="ac517-187">Dependency on Native Libraries</span></span>

<span data-ttu-id="ac517-188">Bei Modulen, die für die Verwendung über verschiedene Betriebssysteme oder Prozessorarchitekturen hinweg konzipiert sind, besteht möglicherweise eine Abhängigkeit von einer verwalteten Bibliothek, die ihrerseits selbst von einigen nativen Bibliotheken abhängig ist.</span><span class="sxs-lookup"><span data-stu-id="ac517-188">Modules intended for use across different operating systems or processor architectures may depend on a managed library that itself depends on some native libraries.</span></span>

<span data-ttu-id="ac517-189">Vor PowerShell 7 war benutzerdefinierter Code erforderlich, um die entsprechende native DLL zu laden, damit sie von der verwalteten Bibliothek gefunden werden kann.</span><span class="sxs-lookup"><span data-stu-id="ac517-189">Prior to PowerShell 7, one would have to have custom code to load the appropriate native dll so that the managed library can find it correctly.</span></span>

<span data-ttu-id="ac517-190">Ab PowerShell 7 wird in Unterordnern des Speicherorts der verwalteten Bibliothek nach nativen Binärdateien gesucht, die geladen werden sollen. Die Suche erfolgt gemäß einer Teilmenge der [.NET-RID-Katalog][]-Notation.</span><span class="sxs-lookup"><span data-stu-id="ac517-190">With PowerShell 7, native binaries to load are searched in sub-folders within the managed library's location following a subset of the [.NET RID Catalog][] notation.</span></span>

```
managed.dll folder
    |
    |--- 'win-x64' folder
    |       |--- native.dll
    |
    |--- 'win-x86' folder
    |       |--- native.dll
    |
    |--- 'win-arm' folder
    |       |--- native.dll
    |
    |--- 'win-arm64' folder
    |       |--- native.dll
    |
    |--- 'linux-x64' folder
    |       |--- native.so
    |
    |--- 'linux-x86' folder
    |       |--- native.so
    |
    |--- 'linux-arm' folder
    |       |--- native.so
    |
    |--- 'linux-arm64' folder
    |       |--- native.so
    |
    |--- 'osx-x64' folder
    |       |--- native.dylib
```

<!-- reference links -->
[.NET Framework]: /dotnet/framework/
[.NET Core]: /dotnet/core/
[PSSnapIn]: /dotnet/api/system.management.automation.pssnapin
[New-ModuleManifest]: /powershell/module/microsoft.powershell.core/new-modulemanifest
[Runtimeüberprüfungen]: /dotnet/api/system.runtime.interopservices.runtimeinformation.frameworkdescription#System_Runtime_InteropServices_RuntimeInformation_FrameworkDescription
[runtime checks]: /dotnet/api/system.runtime.interopservices.runtimeinformation.frameworkdescription#System_Runtime_InteropServices_RuntimeInformation_FrameworkDescription
[.NET CLI]: /dotnet/core/tools/?tabs=netcore2x
[Verwenden von Visual Studio Code zum Debuggen kompilierter Cmdlets]: vscode/using-vscode-for-debugging-compiled-cmdlets.md
[Using Visual Studio Code for debugging compiled cmdlets]: vscode/using-vscode-for-debugging-compiled-cmdlets.md
[.NET Standard]: /dotnet/standard/net-standard
[PowerShell Standard]: https://github.com/PowerShell/PowerShellStandard
[PowerShell Standard 5.1]: https://www.nuget.org/packages/PowerShellStandard.Library/5.1.0
[PowerShell Gallery]: https://www.powershellgallery.com
[.NET Portability Analyzer]: https://github.com/Microsoft/dotnet-apiport
[CompatiblePSEditions]: /powershell/scripting/gallery/concepts/module-psedition-support
[.NET-RID-Katalog]: /dotnet/core/rid-catalog
[.NET RID Catalog]: /dotnet/core/rid-catalog
