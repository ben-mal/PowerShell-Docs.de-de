---
description: Verhindert, dass ein Skript ohne die erforderlichen Elemente ausgeführt wird.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 07/01/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_requires?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Requires
ms.openlocfilehash: d499499c58f22bff10d712d33fc3a021e4fa6bbb
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222580"
---
# <a name="about-requires"></a><span data-ttu-id="b03be-104">Informationen zu voraus</span><span class="sxs-lookup"><span data-stu-id="b03be-104">About Requires</span></span>

## <a name="short-description"></a><span data-ttu-id="b03be-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b03be-105">Short description</span></span>
<span data-ttu-id="b03be-106">Verhindert, dass ein Skript ohne die erforderlichen Elemente ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b03be-106">Prevents a script from running without the required elements.</span></span>

## <a name="long-description"></a><span data-ttu-id="b03be-107">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b03be-107">Long description</span></span>

<span data-ttu-id="b03be-108">Mit der `#Requires` -Anweisung wird verhindert, dass ein Skript ausgeführt wird, es sei denn, die PowerShell-Version, die Module (und die Version) oder die Snap-Ins (und die-Version) und die Editions Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="b03be-108">The `#Requires` statement prevents a script from running unless the PowerShell version, modules (and version), or snap-ins (and version), and edition prerequisites are met.</span></span> <span data-ttu-id="b03be-109">Wenn die Voraussetzungen nicht erfüllt sind, führt PowerShell das Skript nicht aus.</span><span class="sxs-lookup"><span data-stu-id="b03be-109">If the prerequisites aren't met, PowerShell doesn't run the script.</span></span>

### <a name="syntax"></a><span data-ttu-id="b03be-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="b03be-110">Syntax</span></span>

```
#Requires -Assembly { <Path to .dll> | <.NET assembly specification> }
#Requires -Version <N>[.<n>]
#Requires -PSSnapin <PSSnapin-Name> [-Version <N>[.<n>]]
#Requires -Modules { <Module-Name> | <Hashtable> }
#Requires -PSEdition <PSEdition-Name>
#Requires -ShellId <ShellId> -PSSnapin <PSSnapin-Name> [-Version <N>[.<n>]]
#Requires -RunAsAdministrator
```

<span data-ttu-id="b03be-111">Weitere Informationen zur Syntax finden Sie unter [scriptrequirequirements](/dotnet/api/system.management.automation.language.scriptrequirements).</span><span class="sxs-lookup"><span data-stu-id="b03be-111">For more information about the syntax, see [ScriptRequirements](/dotnet/api/system.management.automation.language.scriptrequirements).</span></span>

### <a name="rules-for-use"></a><span data-ttu-id="b03be-112">Verwendungs Regeln</span><span class="sxs-lookup"><span data-stu-id="b03be-112">Rules for use</span></span>

<span data-ttu-id="b03be-113">Ein Skript kann mehr als eine `#Requires` Anweisung enthalten.</span><span class="sxs-lookup"><span data-stu-id="b03be-113">A script can include more than one `#Requires` statement.</span></span> <span data-ttu-id="b03be-114">Die- `#Requires` Anweisungen können in einer beliebigen Zeile in einem Skript angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b03be-114">The `#Requires` statements can appear on any line in a script.</span></span>

<span data-ttu-id="b03be-115">Durch das Platzieren einer `#Requires` Anweisung innerhalb einer Funktion wird der Gültigkeitsbereich nicht eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="b03be-115">Placing a `#Requires` statement inside a function does NOT limit its scope.</span></span> <span data-ttu-id="b03be-116">Alle `#Requires` -Anweisungen werden immer global angewendet und müssen erfüllt werden, bevor das Skript ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="b03be-116">All `#Requires` statements are always applied globally, and must be met, before the script can execute.</span></span>

> [!WARNING]
> <span data-ttu-id="b03be-117">Obwohl eine- `#Requires` Anweisung in einer Zeile in einem Skript angezeigt werden kann, wirkt sich die Position in einem Skript nicht auf die Abfolge der Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="b03be-117">Even though a `#Requires` statement can appear on any line in a script, its position in a script does not affect the sequence of its application.</span></span> <span data-ttu-id="b03be-118">Der globale Status, den die- `#Requires` Anweisung darstellt, muss vor der Skriptausführung erfüllt werden.</span><span class="sxs-lookup"><span data-stu-id="b03be-118">The global state the `#Requires` statement presents must be met before script execution.</span></span>

<span data-ttu-id="b03be-119">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b03be-119">Example:</span></span>

```powershell
Get-Module AzureRM.Netcore | Remove-Module
#Requires -Modules AzureRM.Netcore
```

<span data-ttu-id="b03be-120">Möglicherweise denken Sie daran, dass der obige Code nicht ausgeführt werden sollte, da das erforderliche Modul vor der Anweisung entfernt wurde `#Requires` .</span><span class="sxs-lookup"><span data-stu-id="b03be-120">You might think that the above code shouldn't run because the required module was removed before the `#Requires` statement.</span></span> <span data-ttu-id="b03be-121">Der Zustand muss jedoch `#Requires` erfüllt sein, damit das Skript überhaupt ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="b03be-121">However, the `#Requires` state had to be met before the script could even execute.</span></span> <span data-ttu-id="b03be-122">Anschließend hat die erste Zeile des Skripts den erforderlichen Zustand ungültig.</span><span class="sxs-lookup"><span data-stu-id="b03be-122">Then the first line of the script invalidated the required state.</span></span>

### <a name="parameters"></a><span data-ttu-id="b03be-123">Parameter</span><span class="sxs-lookup"><span data-stu-id="b03be-123">Parameters</span></span>

#### <a name="-assembly-assembly-path--net-assembly-specification"></a><span data-ttu-id="b03be-124">-Assembly \<Assembly path> |\<.NET assembly specification></span><span class="sxs-lookup"><span data-stu-id="b03be-124">-Assembly \<Assembly path> | \<.NET assembly specification></span></span>

<span data-ttu-id="b03be-125">Gibt den Pfad zur DLL-Datei der Assembly oder einen .NET-Assemblynamen an.</span><span class="sxs-lookup"><span data-stu-id="b03be-125">Specifies the path to the assembly DLL file or a .NET assembly name.</span></span> <span data-ttu-id="b03be-126">Der **Assembly** -Parameter wurde in PowerShell 5,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="b03be-126">The **Assembly** parameter was introduced in PowerShell 5.0.</span></span> <span data-ttu-id="b03be-127">Weitere Informationen zu .NET-Assemblys [Assembly names](/dotnet/standard/assembly/names)finden Sie unter Assemblynamen.</span><span class="sxs-lookup"><span data-stu-id="b03be-127">For more information about .NET assemblies, see [Assembly names](/dotnet/standard/assembly/names).</span></span>

<span data-ttu-id="b03be-128">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b03be-128">For example:</span></span>

```
#Requires -Assembly path\to\foo.dll
```

```
#Requires -Assembly "System.Management.Automation, Version=3.0.0.0,
  Culture=neutral, PublicKeyToken=31bf3856ad364e35"
```

#### <a name="-version-nn"></a><span data-ttu-id="b03be-129">-Version \<N\> [. \<n\> ]</span><span class="sxs-lookup"><span data-stu-id="b03be-129">-Version \<N\>[.\<n\>]</span></span>

<span data-ttu-id="b03be-130">Gibt die mindestens erforderliche Version von PowerShell an, die für das Skript erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="b03be-130">Specifies the minimum version of PowerShell that the script requires.</span></span> <span data-ttu-id="b03be-131">Geben Sie eine Hauptversionsnummer und optional eine neben Versionsnummer ein.</span><span class="sxs-lookup"><span data-stu-id="b03be-131">Enter a major version number and optional minor version number.</span></span>

<span data-ttu-id="b03be-132">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b03be-132">For example:</span></span>

```powershell
#Requires -Version 5.1
```

#### <a name="-pssnapin-pssnapin-name--version-nn"></a><span data-ttu-id="b03be-133">-PSSnapIn \<PSSnapin-Name\> [-Version \<N\> [. \<n\> ]]</span><span class="sxs-lookup"><span data-stu-id="b03be-133">-PSSnapin \<PSSnapin-Name\> [-Version \<N\>[.\<n\>]]</span></span>

<span data-ttu-id="b03be-134">Gibt ein PowerShell-Snap-in an, das für das Skript erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="b03be-134">Specifies a PowerShell snap-in that the script requires.</span></span> <span data-ttu-id="b03be-135">Geben Sie den Snap-in-Namen und eine optionale Versionsnummer ein.</span><span class="sxs-lookup"><span data-stu-id="b03be-135">Enter the snap-in name and an optional version number.</span></span>

<span data-ttu-id="b03be-136">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b03be-136">For example:</span></span>

```powershell
#Requires -PSSnapin DiskSnapin -Version 1.2
```

#### <a name="-modules-module-name--hashtable"></a><span data-ttu-id="b03be-137">-Module \<Module-Name\> |\<Hashtable\></span><span class="sxs-lookup"><span data-stu-id="b03be-137">-Modules \<Module-Name\> | \<Hashtable\></span></span>

<span data-ttu-id="b03be-138">Gibt die PowerShell-Module an, die das Skript erfordert.</span><span class="sxs-lookup"><span data-stu-id="b03be-138">Specifies PowerShell modules that the script requires.</span></span> <span data-ttu-id="b03be-139">Geben Sie den Modulnamen und eine optionale Versionsnummer ein.</span><span class="sxs-lookup"><span data-stu-id="b03be-139">Enter the module name and an optional version number.</span></span>

<span data-ttu-id="b03be-140">Wenn die erforderlichen Module nicht in der aktuellen Sitzung sind, importiert PowerShell Sie.</span><span class="sxs-lookup"><span data-stu-id="b03be-140">If the required modules aren't in the current session, PowerShell imports them.</span></span>
<span data-ttu-id="b03be-141">Wenn die Module nicht importiert werden können, löst PowerShell einen Fehler mit Abbruch aus.</span><span class="sxs-lookup"><span data-stu-id="b03be-141">If the modules can't be imported, PowerShell throws a terminating error.</span></span>

<span data-ttu-id="b03be-142">Geben Sie für jedes Modul den Modulnamen ( \<String\> ) oder eine Hash Tabelle ein.</span><span class="sxs-lookup"><span data-stu-id="b03be-142">For each module, type the module name (\<String\>) or a hash table.</span></span> <span data-ttu-id="b03be-143">Der Wert kann eine Kombination aus Zeichen folgen und Hash Tabellen sein.</span><span class="sxs-lookup"><span data-stu-id="b03be-143">The value can be a combination of strings and hash tables.</span></span> <span data-ttu-id="b03be-144">Die Hash Tabelle verfügt über die folgenden Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="b03be-144">The hash table has the following keys.</span></span>

- <span data-ttu-id="b03be-145">`ModuleName` - **Erforderlich** Gibt den Namen des Moduls an.</span><span class="sxs-lookup"><span data-stu-id="b03be-145">`ModuleName` - **Required** Specifies the module name.</span></span>
- <span data-ttu-id="b03be-146">`GUID` - **Optional** Gibt die GUID des Moduls an.</span><span class="sxs-lookup"><span data-stu-id="b03be-146">`GUID` - **Optional** Specifies the GUID of the module.</span></span>
- <span data-ttu-id="b03be-147">Es ist auch **erforderlich** , einen der drei folgenden Schlüssel anzugeben.</span><span class="sxs-lookup"><span data-stu-id="b03be-147">It's also **Required** to specify one of the three below keys.</span></span> <span data-ttu-id="b03be-148">Diese Schlüssel können nicht gleichzeitig verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b03be-148">These keys can't be used together.</span></span>
  - <span data-ttu-id="b03be-149">`ModuleVersion` : Gibt eine zulässige Mindestversion des Moduls an.</span><span class="sxs-lookup"><span data-stu-id="b03be-149">`ModuleVersion` - Specifies a minimum acceptable version of the module.</span></span>
  - <span data-ttu-id="b03be-150">`RequiredVersion` : Gibt eine exakte, erforderliche Version des Moduls an.</span><span class="sxs-lookup"><span data-stu-id="b03be-150">`RequiredVersion` - Specifies an exact, required version of the module.</span></span>
  - <span data-ttu-id="b03be-151">`MaximumVersion` : Gibt die maximal zulässige Version des Moduls an.</span><span class="sxs-lookup"><span data-stu-id="b03be-151">`MaximumVersion` - Specifies the maximum acceptable version of the module.</span></span>

> [!NOTE]
> <span data-ttu-id="b03be-152">`RequiredVersion` wurde in Windows PowerShell 5,0 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b03be-152">`RequiredVersion` was added in Windows PowerShell 5.0.</span></span>
> <span data-ttu-id="b03be-153">`MaximumVersion` wurde in Windows PowerShell 5,1 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b03be-153">`MaximumVersion` was added in Windows PowerShell 5.1.</span></span>

<span data-ttu-id="b03be-154">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b03be-154">For example:</span></span>

<span data-ttu-id="b03be-155">Erfordert, dass `Hyper-V` (Version `1.1` oder höher) installiert ist.</span><span class="sxs-lookup"><span data-stu-id="b03be-155">Require that `Hyper-V` (version `1.1` or greater) is installed.</span></span>

```powershell
#Requires -Modules @{ ModuleName="Hyper-V"; ModuleVersion="1.1" }
```

<span data-ttu-id="b03be-156">Erfordert, dass `Hyper-V` ( **nur** Version `1.1` ) installiert ist.</span><span class="sxs-lookup"><span data-stu-id="b03be-156">Requires that `Hyper-V` ( **only** version `1.1`) is installed.</span></span>

```powershell
#Requires -Modules @{ ModuleName="Hyper-V"; RequiredVersion="1.1" }
```

<span data-ttu-id="b03be-157">Erfordert, dass `Hyper-V` (Version `1.1` oder weniger) installiert ist.</span><span class="sxs-lookup"><span data-stu-id="b03be-157">Requires that `Hyper-V` (version `1.1` or lesser) is installed.</span></span>

```powershell
#Requires -Modules @{ ModuleName="Hyper-V"; MaximumVersion="1.1" }
```

<span data-ttu-id="b03be-158">Erfordert, dass eine beliebige Version von `PSScheduledJob` und `PSWorkflow` installiert ist.</span><span class="sxs-lookup"><span data-stu-id="b03be-158">Requires that any version of `PSScheduledJob` and `PSWorkflow`, is installed.</span></span>

```powershell
#Requires -Modules PSWorkflow, PSScheduledJob
```

<span data-ttu-id="b03be-159">Wenn Sie den `RequiredVersion` Schlüssel verwenden, stellen Sie sicher, dass die Versions Zeichenfolge genau mit der gewünschten Versions Zeichenfolge übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="b03be-159">When using the `RequiredVersion` key, ensure your version string exactly matches the version string you wish to require.</span></span>

```powershell
Get-Module Hyper-V
```

```Output
ModuleType Version    Name     ExportedCommands
---------- -------    ----     ------------------
Binary     2.0.0.0    hyper-v  {Add-VMAssignableDevice, ...}
```

<span data-ttu-id="b03be-160">Das folgende Beispiel schlägt fehl, da **2.0.0** nicht exakt mit **2.0.0.0** übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="b03be-160">The following example fails because **2.0.0** doesn't exactly match **2.0.0.0**.</span></span>

```powershell
#Requires -Modules @{ ModuleName="Hyper-V"; RequiredVersion="2.0.0" }
```

#### <a name="-psedition-psedition-name"></a><span data-ttu-id="b03be-161">-P\* dition \<PSEdition-Name\></span><span class="sxs-lookup"><span data-stu-id="b03be-161">-PSEdition \<PSEdition-Name\></span></span>

<span data-ttu-id="b03be-162">Gibt eine PowerShell-Edition an, die für das Skript erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="b03be-162">Specifies a PowerShell edition that the script requires.</span></span> <span data-ttu-id="b03be-163">Gültige Werte sind **Core** für PowerShell Core und **Desktop** für Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b03be-163">Valid values are **Core** for PowerShell Core and **Desktop** for Windows PowerShell.</span></span>

<span data-ttu-id="b03be-164">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b03be-164">For example:</span></span>

```powershell
#Requires -PSEdition Core
```

#### <a name="-shellid"></a><span data-ttu-id="b03be-165">-Shellid</span><span class="sxs-lookup"><span data-stu-id="b03be-165">-ShellId</span></span>

<span data-ttu-id="b03be-166">Gibt die Shell an, die für das Skript erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="b03be-166">Specifies the shell that the script requires.</span></span> <span data-ttu-id="b03be-167">Geben Sie die Shell-ID ein.</span><span class="sxs-lookup"><span data-stu-id="b03be-167">Enter the shell ID.</span></span> <span data-ttu-id="b03be-168">Wenn Sie den **shellid-** Parameter verwenden, müssen Sie auch den **PSSnapIn** -Parameter einschließen.</span><span class="sxs-lookup"><span data-stu-id="b03be-168">If you use the **ShellId** parameter, you must also include the **PSSnapin** parameter.</span></span>
<span data-ttu-id="b03be-169">Sie können die aktuelle **shellid** ermitteln, indem Sie die `$ShellId` Automatische Variable Abfragen.</span><span class="sxs-lookup"><span data-stu-id="b03be-169">You can find the current **ShellId** by querying the `$ShellId` automatic variable.</span></span>

<span data-ttu-id="b03be-170">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b03be-170">For example:</span></span>

```powershell
#Requires -ShellId MyLocalShell -PSSnapin Microsoft.PowerShell.Core
```

> [!NOTE]
> <span data-ttu-id="b03be-171">Dieser Parameter ist für die Verwendung in Mini Shells vorgesehen, die veraltet sind.</span><span class="sxs-lookup"><span data-stu-id="b03be-171">This parameter is intended for use in mini-shells, which have been deprecated.</span></span>

#### <a name="-runasadministrator"></a><span data-ttu-id="b03be-172">-Runasadministrator</span><span class="sxs-lookup"><span data-stu-id="b03be-172">-RunAsAdministrator</span></span>

<span data-ttu-id="b03be-173">Wenn dieser Switch-Parameter der-Anweisung hinzugefügt wird `#Requires` , gibt er an, dass die PowerShell-Sitzung, in der das Skript ausgeführt wird, mit erhöhten Benutzerrechten gestartet werden muss.</span><span class="sxs-lookup"><span data-stu-id="b03be-173">When this switch parameter is added to your `#Requires` statement, it specifies that the PowerShell session in which you're running the script must be started with elevated user rights.</span></span> <span data-ttu-id="b03be-174">Der Parameter **runasadministrator** wird bei einem nicht-Windows-Betriebssystem ignoriert.</span><span class="sxs-lookup"><span data-stu-id="b03be-174">The **RunAsAdministrator** parameter is ignored on a non-Windows operating system.</span></span> <span data-ttu-id="b03be-175">Der **runasadministrator** -Parameter wurde in PowerShell 4,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="b03be-175">The **RunAsAdministrator** parameter was introduced in PowerShell 4.0.</span></span>

<span data-ttu-id="b03be-176">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b03be-176">For example:</span></span>

```powershell
#Requires -RunAsAdministrator
```

### <a name="examples"></a><span data-ttu-id="b03be-177">Beispiele</span><span class="sxs-lookup"><span data-stu-id="b03be-177">Examples</span></span>

<span data-ttu-id="b03be-178">Das folgende Skript verfügt über zwei- `#Requires` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="b03be-178">The following script has two `#Requires` statements.</span></span> <span data-ttu-id="b03be-179">Wenn die in beiden Anweisungen angegebenen Anforderungen nicht erfüllt sind, wird das Skript nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b03be-179">If the requirements specified in both statements aren't met, the script doesn't run.</span></span> <span data-ttu-id="b03be-180">Jede `#Requires` Anweisung muss das erste Element in einer Zeile sein:</span><span class="sxs-lookup"><span data-stu-id="b03be-180">Each `#Requires` statement must be the first item on a line:</span></span>

```powershell
#Requires -Modules PSWorkflow
#Requires -Version 3
Param
(
    [parameter(Mandatory=$true)]
    [String[]]
    $Path
)
...
```

## <a name="see-also"></a><span data-ttu-id="b03be-181">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="b03be-181">See also</span></span>

[<span data-ttu-id="b03be-182">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="b03be-182">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="b03be-183">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="b03be-183">about_Language_Keywords</span></span>](about_Language_Keywords.md)

[<span data-ttu-id="b03be-184">about_PSSnapins</span><span class="sxs-lookup"><span data-stu-id="b03be-184">about_PSSnapins</span></span>](about_PSSnapins.md)

[<span data-ttu-id="b03be-185">Get-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="b03be-185">Get-PSSnapin</span></span>](xref:Microsoft.PowerShell.Core.Get-PSSnapin)
