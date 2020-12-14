---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 12/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/import-module?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-Module
ms.openlocfilehash: 6b87074f6053189b20b5cc0983f978324420c99b
ms.sourcegitcommit: 7b376314e7640c39a53aac9f0db8bb935514a960
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2020
ms.locfileid: "96564389"
---
# <span data-ttu-id="3c009-102">Import-Module</span><span class="sxs-lookup"><span data-stu-id="3c009-102">Import-Module</span></span>

## <span data-ttu-id="3c009-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="3c009-103">SYNOPSIS</span></span>
<span data-ttu-id="3c009-104">Fügt der aktuellen Sitzung Module hinzu.</span><span class="sxs-lookup"><span data-stu-id="3c009-104">Adds modules to the current session.</span></span>

## <span data-ttu-id="3c009-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3c009-105">SYNTAX</span></span>

### <span data-ttu-id="3c009-106">Name (Standard)</span><span class="sxs-lookup"><span data-stu-id="3c009-106">Name (Default)</span></span>

```
Import-Module [-Global] [-Prefix <String>] [-Name] <String[]> [-Function <String[]>]
 [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force] [-PassThru]
 [-AsCustomObject] [-MinimumVersion <Version>] [-MaximumVersion <String>]
 [-RequiredVersion <Version>] [-ArgumentList <Object[]>] [-DisableNameChecking] [-NoClobber]
 [-Scope <String>] [<CommonParameters>]
```

### <span data-ttu-id="3c009-107">PSSession</span><span class="sxs-lookup"><span data-stu-id="3c009-107">PSSession</span></span>

```
Import-Module [-Global] [-Prefix <String>] [-Name] <String[]> [-Function <String[]>]
 [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force] [-PassThru]
 [-AsCustomObject] [-MinimumVersion <Version>] [-MaximumVersion <String>]
 [-RequiredVersion <Version>] [-ArgumentList <Object[]>] [-DisableNameChecking] [-NoClobber]
 [-Scope <String>] -PSSession <PSSession> [<CommonParameters>]
```

### <span data-ttu-id="3c009-108">CimSession</span><span class="sxs-lookup"><span data-stu-id="3c009-108">CimSession</span></span>

```
Import-Module [-Global] [-Prefix <String>] [-Name] <String[]> [-Function <String[]>]
 [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force] [-PassThru]
 [-AsCustomObject] [-MinimumVersion <Version>] [-MaximumVersion <String>]
 [-RequiredVersion <Version>] [-ArgumentList <Object[]>] [-DisableNameChecking] [-NoClobber]
 [-Scope <String>] -CimSession <CimSession> [-CimResourceUri <Uri>] [-CimNamespace <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="3c009-109">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="3c009-109">FullyQualifiedName</span></span>

```
Import-Module [-Global] [-Prefix <String>] [-FullyQualifiedName] <ModuleSpecification[]>
 [-Function <String[]>] [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force]
 [-PassThru] [-AsCustomObject] [-ArgumentList <Object[]>] [-DisableNameChecking] [-NoClobber]
 [-Scope <String>] [<CommonParameters>]
```

### <span data-ttu-id="3c009-110">Fullyqualifiednameandpssession</span><span class="sxs-lookup"><span data-stu-id="3c009-110">FullyQualifiedNameAndPSSession</span></span>

```
Import-Module [-Global] [-Prefix <String>] [-FullyQualifiedName] <ModuleSpecification[]>
 [-Function <String[]>] [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force]
 [-PassThru] [-AsCustomObject] [-ArgumentList <Object[]>] [-DisableNameChecking] [-NoClobber]
 [-Scope <String>] -PSSession <PSSession> [<CommonParameters>]
```

### <span data-ttu-id="3c009-111">Assembly</span><span class="sxs-lookup"><span data-stu-id="3c009-111">Assembly</span></span>

```
Import-Module [-Global] [-Prefix <String>] [-Assembly] <Assembly[]> [-Function <String[]>]
 [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force] [-PassThru]
 [-AsCustomObject] [-ArgumentList <Object[]>] [-DisableNameChecking] [-NoClobber] [-Scope <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="3c009-112">ModuleInfo</span><span class="sxs-lookup"><span data-stu-id="3c009-112">ModuleInfo</span></span>

```
Import-Module [-Global] [-Prefix <String>] [-Function <String[]>] [-Cmdlet <String[]>]
 [-Variable <String[]>] [-Alias <String[]>] [-Force] [-PassThru] [-AsCustomObject]
 [-ModuleInfo] <PSModuleInfo[]> [-ArgumentList <Object[]>] [-DisableNameChecking] [-NoClobber]
 [-Scope <String>] [<CommonParameters>]
```

## <span data-ttu-id="3c009-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3c009-113">DESCRIPTION</span></span>

<span data-ttu-id="3c009-114">Mit dem- `Import-Module` Cmdlet werden der aktuellen Sitzung ein oder mehrere Module hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="3c009-114">The `Import-Module` cmdlet adds one or more modules to the current session.</span></span> <span data-ttu-id="3c009-115">Ab PowerShell 3,0 werden installierte Module automatisch in die Sitzung importiert, wenn Sie Befehle oder Anbieter im Modul verwenden.</span><span class="sxs-lookup"><span data-stu-id="3c009-115">Starting in PowerShell 3.0, installed modules are automatically imported to the session when you use any commands or providers in the module.</span></span> <span data-ttu-id="3c009-116">Sie können jedoch weiterhin den-Befehl verwenden, `Import-Module` um ein Modul zu importieren.</span><span class="sxs-lookup"><span data-stu-id="3c009-116">However, you can still use the `Import-Module` command to import a module.</span></span>
<span data-ttu-id="3c009-117">Sie können das automatische Importieren von Modulen mithilfe der `$PSModuleAutoloadingPreference` Preference-Variablen deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="3c009-117">You can disable automatic module importing using the `$PSModuleAutoloadingPreference` preference variable.</span></span> <span data-ttu-id="3c009-118">Weitere Informationen zur- `$PSModuleAutoloadingPreference` Variablen finden Sie unter [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="3c009-118">For more information about the `$PSModuleAutoloadingPreference` variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="3c009-119">Ein Modul ist ein Paket, das Elemente enthält, die in PowerShell verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="3c009-119">A module is a package that contains members that can be used in PowerShell.</span></span> <span data-ttu-id="3c009-120">Zu den Membern gehören Cmdlets, Anbieter, Skripts, Funktionen, Variablen und andere Tools und Dateien.</span><span class="sxs-lookup"><span data-stu-id="3c009-120">Members include cmdlets, providers, scripts, functions, variables, and other tools and files.</span></span> <span data-ttu-id="3c009-121">Nachdem ein Modul importiert wurde, können Sie die Modulelemente in der Sitzung verwenden.</span><span class="sxs-lookup"><span data-stu-id="3c009-121">After a module is imported, you can use the module members in your session.</span></span> <span data-ttu-id="3c009-122">Weitere Informationen zu Modulen finden Sie unter [about_Modules](About/about_Modules.md).</span><span class="sxs-lookup"><span data-stu-id="3c009-122">For more information about modules, see [about_Modules](About/about_Modules.md).</span></span>

<span data-ttu-id="3c009-123">Standardmäßig importiert alle Member, die `Import-Module` das Modul exportiert, aber Sie können die Parameter **Alias**, **Function**, **Cmdlet** und **Variable** verwenden, um einzuschränken, welche Member importiert werden.</span><span class="sxs-lookup"><span data-stu-id="3c009-123">By default, `Import-Module` imports all members that the module exports, but you can use the **Alias**, **Function**, **Cmdlet**, and **Variable** parameters to restrict which members are imported.</span></span> <span data-ttu-id="3c009-124">Der **noClobber** -Parameter verhindert `Import-Module` , dass Elemente importiert werden, die denselben Namen wie die Member in der aktuellen Sitzung haben.</span><span class="sxs-lookup"><span data-stu-id="3c009-124">The **NoClobber** parameter prevents `Import-Module` from importing members that have the same names as members in the current session.</span></span>

<span data-ttu-id="3c009-125">`Import-Module` importiert ein Modul nur in die aktuelle Sitzung.</span><span class="sxs-lookup"><span data-stu-id="3c009-125">`Import-Module` imports a module only into the current session.</span></span> <span data-ttu-id="3c009-126">Um das Modul in jede neue Sitzung zu importieren, fügen Sie `Import-Module` Ihrem PowerShell-Profil einen Befehl hinzu.</span><span class="sxs-lookup"><span data-stu-id="3c009-126">To import the module into every new session, add an `Import-Module` command to your PowerShell profile.</span></span> <span data-ttu-id="3c009-127">Weitere Informationen zu Profilen finden Sie unter [about_Profiles](About/about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="3c009-127">For more information about profiles, see [about_Profiles](About/about_Profiles.md).</span></span>

<span data-ttu-id="3c009-128">Sie können Windows-Remote Computer verwalten, auf denen PowerShell-Remoting aktiviert ist, indem Sie eine **PSSession** auf dem Remote Computer erstellen.</span><span class="sxs-lookup"><span data-stu-id="3c009-128">You can manage remote Windows computers that have PowerShell remoting enabled by creating a **PSSession** on the remote computer.</span></span> <span data-ttu-id="3c009-129">Verwenden Sie dann den **PSSession** -Parameter von `Import-Module` , um die Module zu importieren, die auf dem Remote Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="3c009-129">Then use the **PSSession** parameter of `Import-Module` to import the modules that are installed on the remote computer.</span></span> <span data-ttu-id="3c009-130">Wenn Sie die importierten Befehle in der aktuellen Sitzung verwenden, werden die Befehle implizit auf dem Remote Computer ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="3c009-130">When you use the imported commands in the current session the commands implicitly run on the remote computer.</span></span>

<span data-ttu-id="3c009-131">Ab Windows PowerShell 3,0 können Sie verwenden, `Import-Module` um Common Information Model (CIM)-Module zu importieren.</span><span class="sxs-lookup"><span data-stu-id="3c009-131">Starting in Windows PowerShell 3.0, you can use `Import-Module` to import Common Information Model (CIM) modules.</span></span> <span data-ttu-id="3c009-132">CIM-Module definieren Cmdlets in cdxml-Dateien (Cmdlet Definition XML).</span><span class="sxs-lookup"><span data-stu-id="3c009-132">CIM modules define cmdlets in Cmdlet Definition XML (CDXML) files.</span></span> <span data-ttu-id="3c009-133">Mit dieser Funktion können Sie Cmdlets verwenden, die in nicht verwalteten Codeassemblys implementiert sind, z. b. in C++ geschriebene Assemblys.</span><span class="sxs-lookup"><span data-stu-id="3c009-133">This feature lets you use cmdlets that are implemented in non-managed code assemblies, such as those written in C++.</span></span>

<span data-ttu-id="3c009-134">Bei Remote Computern, auf denen PowerShell-Remoting nicht aktiviert ist, einschließlich Computern, auf denen das Windows-Betriebssystem nicht ausgeführt wird, können Sie den **cimsession** -Parameter von verwenden, `Import-Module` um CIM-Module vom Remote Computer zu importieren.</span><span class="sxs-lookup"><span data-stu-id="3c009-134">For remote computers that don't have PowerShell remoting enabled, including computers that aren't running the Windows operating system, you can use the **CIMSession** parameter of `Import-Module` to import CIM modules from the remote computer.</span></span> <span data-ttu-id="3c009-135">Die importierten Befehle werden implizit auf dem Remote Computer ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="3c009-135">The imported commands run implicitly on the remote computer.</span></span> <span data-ttu-id="3c009-136">Eine **cimsession** ist eine Verbindung mit Windows-Verwaltungsinstrumentation (WMI) auf dem Remote Computer.</span><span class="sxs-lookup"><span data-stu-id="3c009-136">A **CIMSession** is a connection to Windows Management Instrumentation (WMI) on the remote computer.</span></span>

## <span data-ttu-id="3c009-137">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="3c009-137">EXAMPLES</span></span>

### <span data-ttu-id="3c009-138">Beispiel 1: Importieren der Member eines Moduls in die aktuelle Sitzung</span><span class="sxs-lookup"><span data-stu-id="3c009-138">Example 1: Import the members of a module into the current session</span></span>

<span data-ttu-id="3c009-139">In diesem Beispiel werden die Member des **psdiagnostics** -Moduls in die aktuelle Sitzung importiert.</span><span class="sxs-lookup"><span data-stu-id="3c009-139">This example imports the members of the **PSDiagnostics** module into the current session.</span></span>

```powershell
Import-Module -Name PSDiagnostics
```

### <span data-ttu-id="3c009-140">Beispiel 2: Importieren aller vom Modulpfad angegebenen Module</span><span class="sxs-lookup"><span data-stu-id="3c009-140">Example 2: Import all modules specified by the module path</span></span>

<span data-ttu-id="3c009-141">In diesem Beispiel werden alle verfügbaren Module in dem von der `$env:PSModulePath` Umgebungsvariablen angegebenen Pfad in die aktuelle Sitzung importiert.</span><span class="sxs-lookup"><span data-stu-id="3c009-141">This example imports all available modules in the path specified by the `$env:PSModulePath` environment variable into the current session.</span></span>

```powershell
Get-Module -ListAvailable | Import-Module
```

### <span data-ttu-id="3c009-142">Beispiel 3: Importieren der Mitglieder mehrerer Module in die aktuelle Sitzung</span><span class="sxs-lookup"><span data-stu-id="3c009-142">Example 3: Import the members of several modules into the current session</span></span>

<span data-ttu-id="3c009-143">In diesem Beispiel werden die Member der **psdiagnostics** - **und** der-instanzmodule in die aktuelle Sitzung importiert.</span><span class="sxs-lookup"><span data-stu-id="3c009-143">This example imports the members of the **PSDiagnostics** and **Dism** modules into the current session.</span></span>

```powershell
$m = Get-Module -ListAvailable PSDiagnostics, Dism
Import-Module -ModuleInfo $m
```

<span data-ttu-id="3c009-144">Das `Get-Module` **-** Cmdlet ruft die **psdiagnostics** -und die-initiatormodule ab und speichert die Objekte in der `$m` Variablen.</span><span class="sxs-lookup"><span data-stu-id="3c009-144">The `Get-Module` cmdlet gets the **PSDiagnostics** and **Dism** modules and saves the objects in the `$m` variable.</span></span> <span data-ttu-id="3c009-145">Der **listavailable** -Parameter ist erforderlich, wenn Sie Module erhalten, die noch nicht in die Sitzung importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="3c009-145">The **ListAvailable** parameter is required when you're getting modules that aren't yet imported into the session.</span></span>

<span data-ttu-id="3c009-146">Der **ModuleInfo** -Parameter von `Import-Module` wird verwendet, um die Module in die aktuelle Sitzung zu importieren.</span><span class="sxs-lookup"><span data-stu-id="3c009-146">The **ModuleInfo** parameter of `Import-Module` is used to import the modules into the current session.</span></span>

### <span data-ttu-id="3c009-147">Beispiel 4: Importieren aller durch einen Pfad angegebenen Module</span><span class="sxs-lookup"><span data-stu-id="3c009-147">Example 4: Import all modules specified by a path</span></span>

<span data-ttu-id="3c009-148">Dieses Beispiel verwendet einen expliziten Pfad zum Identifizieren des zu importierenden Moduls.</span><span class="sxs-lookup"><span data-stu-id="3c009-148">This example uses an explicit path to identify the module to import.</span></span>

```powershell
Import-Module -Name c:\ps-test\modules\test -Verbose
```

```Output
VERBOSE: Loading module from path 'C:\ps-test\modules\Test\Test.psm1'.
VERBOSE: Exporting function 'my-parm'.
VERBOSE: Exporting function 'Get-Parameter'.
VERBOSE: Exporting function 'Get-Specification'.
VERBOSE: Exporting function 'Get-SpecDetails'.
```

<span data-ttu-id="3c009-149">Wenn der **verbose** -Parameter verwendet wird `Import-Module` , meldet der Fortschritt beim Laden des Moduls.</span><span class="sxs-lookup"><span data-stu-id="3c009-149">Using the **Verbose** parameter causes `Import-Module` to report progress as it loads the module.</span></span>
<span data-ttu-id="3c009-150">Ohne den **verbose**-, **passthru**-oder **ascustomobject** -Parameter `Import-Module` generiert keine Ausgabe, wenn ein Modul importiert wird.</span><span class="sxs-lookup"><span data-stu-id="3c009-150">Without the **Verbose**, **PassThru**, or **AsCustomObject** parameter, `Import-Module` does not generate any output when it imports a module.</span></span>

### <span data-ttu-id="3c009-151">Beispiel 5: Einschränken von in eine Sitzung importierten Modulmembern</span><span class="sxs-lookup"><span data-stu-id="3c009-151">Example 5: Restrict module members imported into a session</span></span>

<span data-ttu-id="3c009-152">Dieses Beispiel zeigt, wie Sie einschränken, welche Modulmember in die Sitzung importiert werden und welche Auswirkungen dieser Befehl auf die Sitzung hat.</span><span class="sxs-lookup"><span data-stu-id="3c009-152">This example shows how to restrict which module members are imported into the session and the effect of this command on the session.</span></span> <span data-ttu-id="3c009-153">Der **Funktions** Parameter schränkt die Member ein, die aus dem Modul importiert werden.</span><span class="sxs-lookup"><span data-stu-id="3c009-153">The **Function** parameter limits the members that are imported from the module.</span></span> <span data-ttu-id="3c009-154">Sie können auch die Parameter **Alias**, **Variable** und **Cmdlet** verwenden, um andere Member einzuschränken, die von einem Modul importiert werden.</span><span class="sxs-lookup"><span data-stu-id="3c009-154">You can also use the **Alias**, **Variable**, and **Cmdlet** parameters to restrict other members that a module imports.</span></span>

<span data-ttu-id="3c009-155">Mit dem- `Get-Module` Cmdlet wird das-Objekt abgerufen, das das **psdiagnostics** -Modul darstellt.</span><span class="sxs-lookup"><span data-stu-id="3c009-155">The `Get-Module` cmdlet gets the object that represents the **PSDiagnostics** module.</span></span> <span data-ttu-id="3c009-156">Mit der **exportedcmdlets** -Eigenschaft werden alle Cmdlets aufgelistet, die vom Modul exportiert werden, auch wenn Sie nicht alle importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="3c009-156">The **ExportedCmdlets** property lists all the cmdlets that the module exports, even though they were not all imported.</span></span>

```powershell
Import-Module PSDiagnostics -Function Disable-PSTrace, Enable-PSTrace
(Get-Module PSDiagnostics).ExportedCommands
```

```Output
Key                          Value
---                          -----
Disable-PSTrace              Disable-PSTrace
Disable-PSWSManCombinedTrace Disable-PSWSManCombinedTrace
Disable-WSManTrace           Disable-WSManTrace
Enable-PSTrace               Enable-PSTrace
Enable-PSWSManCombinedTrace  Enable-PSWSManCombinedTrace
Enable-WSManTrace            Enable-WSManTrace
Get-LogProperties            Get-LogProperties
Set-LogProperties            Set-LogProperties
Start-Trace                  Start-Trace
Stop-Trace                   Stop-Trace
```

```powershell
Get-Command -Module PSDiagnostics
```

```Output
CommandType     Name                 Version    Source
-----------     ----                 -------    ------
Function        Disable-PSTrace      6.1.0.0    PSDiagnostics
Function        Enable-PSTrace       6.1.0.0    PSDiagnostics
```

<span data-ttu-id="3c009-157">Mit dem **Module** -Parameter des `Get-Command` Cmdlets werden die Befehle angezeigt, die aus dem **psdiagnostics** -Modul importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="3c009-157">Using the **Module** parameter of the `Get-Command` cmdlet shows the commands that were imported from the **PSDiagnostics** module.</span></span> <span data-ttu-id="3c009-158">Die Ergebnisse bestätigen, dass nur `Disable-PSTrace` die `Enable-PSTrace` Cmdlets und importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="3c009-158">The results confirm that only the `Disable-PSTrace` and `Enable-PSTrace` cmdlets were imported.</span></span>

### <span data-ttu-id="3c009-159">Beispiel 6: Importieren der Member eines Moduls und Hinzufügen eines Präfixes</span><span class="sxs-lookup"><span data-stu-id="3c009-159">Example 6: Import the members of a module and add a prefix</span></span>

<span data-ttu-id="3c009-160">In diesem Beispiel wird das **psdiagnostics** -Modul in die aktuelle Sitzung importiert, ein Präfix zu den Elementnamen hinzugefügt und dann die Namen des vorangestellten Elements angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3c009-160">This example imports the **PSDiagnostics** module into the current session, adds a prefix to the member names, and then displays the prefixed member names.</span></span> <span data-ttu-id="3c009-161">Der **prefix** -Parameter von `Import-Module` fügt allen Membern, die aus dem Modul importiert werden, das **x** -Präfix hinzu.</span><span class="sxs-lookup"><span data-stu-id="3c009-161">The **Prefix** parameter of `Import-Module` adds the **x** prefix to all members that are imported from the module.</span></span> <span data-ttu-id="3c009-162">Das Präfix gilt nur für die Elemente in der aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="3c009-162">The prefix applies only to the members in the current session.</span></span> <span data-ttu-id="3c009-163">Es ändert nicht das Modul.</span><span class="sxs-lookup"><span data-stu-id="3c009-163">It does not change the module.</span></span> <span data-ttu-id="3c009-164">Der **passthru** -Parameter gibt ein Modul Objekt zurück, das das importierte Modul darstellt.</span><span class="sxs-lookup"><span data-stu-id="3c009-164">The **PassThru** parameter returns a module object that represents the imported module.</span></span>

```powershell
Import-Module PSDiagnostics -Prefix x -PassThru
```

```Output
ModuleType Version    Name               ExportedCommands
---------- -------    ----               ----------------
Script     6.1.0.0    PSDiagnostics      {Disable-xPSTrace, Disable-xPSWSManCombinedTrace, Disable-xW...
```

```powershell
Get-Command -Module PSDiagnostics
```

```Output
CommandType     Name                                   Version    Source
-----------     ----                                   -------    ------
Function        Disable-xPSTrace                       6.1.0.0    PSDiagnostics
Function        Disable-xPSWSManCombinedTrace          6.1.0.0    PSDiagnostics
Function        Disable-xWSManTrace                    6.1.0.0    PSDiagnostics
Function        Enable-xPSTrace                        6.1.0.0    PSDiagnostics
Function        Enable-xPSWSManCombinedTrace           6.1.0.0    PSDiagnostics
Function        Enable-xWSManTrace                     6.1.0.0    PSDiagnostics
Function        Get-xLogProperties                     6.1.0.0    PSDiagnostics
Function        Set-xLogProperties                     6.1.0.0    PSDiagnostics
Function        Start-xTrace                           6.1.0.0    PSDiagnostics
Function        Stop-xTrace                            6.1.0.0    PSDiagnostics
```

<span data-ttu-id="3c009-165">`Get-Command` Ruft die Member ab, die aus dem Modul importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="3c009-165">`Get-Command` gets the members that have been imported from the module.</span></span> <span data-ttu-id="3c009-166">Die Ausgabe zeigt, dass die Modulelemente ordnungsgemäß mit dem Präfix versehen wurden.</span><span class="sxs-lookup"><span data-stu-id="3c009-166">The output shows that the module members were correctly prefixed.</span></span>

### <span data-ttu-id="3c009-167">Beispiel 7: erhalten und Verwenden eines benutzerdefinierten Objekts</span><span class="sxs-lookup"><span data-stu-id="3c009-167">Example 7: Get and use a custom object</span></span>

<span data-ttu-id="3c009-168">In diesem Beispiel wird veranschaulicht, wie das von zurückgegebene benutzerdefinierte Objekt erhalten und verwendet wird `Import-Module` .</span><span class="sxs-lookup"><span data-stu-id="3c009-168">This example demonstrates how to get and use the custom object returned by `Import-Module`.</span></span>

<span data-ttu-id="3c009-169">Benutzerdefinierte Objekte beinhalten synthetische Elemente, die jedes der importierten Modulelemente darstellen.</span><span class="sxs-lookup"><span data-stu-id="3c009-169">Custom objects include synthetic members that represent each of the imported module members.</span></span> <span data-ttu-id="3c009-170">Beispielsweise werden die Cmdlets und Funktionen in einem Modul in Skriptmethoden des benutzerdefinierten Objekts konvertiert.</span><span class="sxs-lookup"><span data-stu-id="3c009-170">For example, the cmdlets and functions in a module are converted to script methods of the custom object.</span></span>

<span data-ttu-id="3c009-171">Benutzerdefinierte Objekte sind bei der Skripterstellung nützlich.</span><span class="sxs-lookup"><span data-stu-id="3c009-171">Custom objects are useful in scripting.</span></span> <span data-ttu-id="3c009-172">Sie sind außerdem nützlich, wenn mehrere importierte Objekte die gleichen Namen haben.</span><span class="sxs-lookup"><span data-stu-id="3c009-172">They are also useful when several imported objects have the same names.</span></span> <span data-ttu-id="3c009-173">Die Skriptmethode eines Objekts entspricht der Angabe des vollqualifizierten Namens eines importierten Elements, darunter der Modulname.</span><span class="sxs-lookup"><span data-stu-id="3c009-173">Using the script method of an object is equivalent to specifying the fully qualified name of an imported member, including its module name.</span></span>

<span data-ttu-id="3c009-174">Der **ascustomobject** -Parameter kann nur beim Importieren eines Skript Moduls verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3c009-174">The **AsCustomObject** parameter can be used only when importing a script module.</span></span> <span data-ttu-id="3c009-175">Verwenden `Get-Module` Sie, um zu bestimmen, welches der verfügbaren Module ein Skript Modul ist.</span><span class="sxs-lookup"><span data-stu-id="3c009-175">Use `Get-Module` to determine which of the available modules is a script module.</span></span>

```powershell
Get-Module -List | Format-Table -Property Name, ModuleType -AutoSize
```

```Output
Name          ModuleType
----          ----------
Show-Calendar     Script
BitsTransfer    Manifest
PSDiagnostics   Manifest
TestCmdlets       Script
...
```

```powershell
$a = Import-Module -Name Show-Calendar -AsCustomObject -Passthru
$a | Get-Member
```

```Output
    TypeName: System.Management.Automation.PSCustomObject
Name          MemberType   Definition
----          ----------   ----------
Equals        Method       bool Equals(System.Object obj)
GetHashCode   Method       int GetHashCode()
GetType       Method       type GetType()
ToString      Method       string ToString()
Show-Calendar ScriptMethod System.Object Show-Calendar();
```

```powershell
$a."Show-Calendar"()
```

<span data-ttu-id="3c009-176">Das `Show-Calendar` Skript Modul wird mithilfe des **ascustomobject** -Parameters importiert, um ein benutzerdefiniertes Objekt anzufordern, und der **passthru** -Parameter, um das Objekt zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="3c009-176">The `Show-Calendar` script module is imported using the **AsCustomObject** parameter to request a custom object and the **PassThru** parameter to return the object.</span></span> <span data-ttu-id="3c009-177">Das resultierende benutzerdefinierte Objekt wird in der `$a` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="3c009-177">The resulting custom object is saved in the `$a` variable.</span></span>

<span data-ttu-id="3c009-178">Die- `$a` Variable wird an das `Get-Member` Cmdlet weitergeleitet, um die Eigenschaften und Methoden des gespeicherten Objekts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="3c009-178">The `$a` variable is piped to the `Get-Member` cmdlet to show the properties and methods of the saved object.</span></span> <span data-ttu-id="3c009-179">Die Ausgabe zeigt eine `Show-Calendar` Skript Methode.</span><span class="sxs-lookup"><span data-stu-id="3c009-179">The output shows a `Show-Calendar` script method.</span></span>

<span data-ttu-id="3c009-180">Um die `Show-Calendar` Skript Methode aufzurufen, muss der Methodenname in Anführungszeichen eingeschlossen werden, da der Name einen Bindestrich enthält.</span><span class="sxs-lookup"><span data-stu-id="3c009-180">To call the `Show-Calendar` script method, the method name must be enclosed in quotation marks because the name includes a hyphen.</span></span>

### <span data-ttu-id="3c009-181">Beispiel 8: erneportieren eines Moduls in dieselbe Sitzung</span><span class="sxs-lookup"><span data-stu-id="3c009-181">Example 8: Reimport a module into the same session</span></span>

<span data-ttu-id="3c009-182">In diesem Beispiel wird gezeigt, wie der **Force** -Parameter von verwendet wird, `Import-Module` Wenn ein Modul in dieselbe Sitzung importiert wird.</span><span class="sxs-lookup"><span data-stu-id="3c009-182">This example shows how to use the **Force** parameter of `Import-Module` when you're reimporting a module into the same session.</span></span> <span data-ttu-id="3c009-183">Der **Force** -Parameter entfernt das geladene Modul und importiert es dann erneut.</span><span class="sxs-lookup"><span data-stu-id="3c009-183">The **Force** parameter removes the loaded module and then imports it again.</span></span>

```powershell
Import-Module PSDiagnostics
Import-Module PSDiagnostics -Force -Prefix PS
```

<span data-ttu-id="3c009-184">Der erste Befehl importiert das **psdiagnostics** -Modul.</span><span class="sxs-lookup"><span data-stu-id="3c009-184">The first command imports the **PSDiagnostics** module.</span></span> <span data-ttu-id="3c009-185">Der zweite Befehl importiert das Modul erneut, dieses Mal mit dem **Prefix**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="3c009-185">The second command imports the module again, this time using the **Prefix** parameter.</span></span>

<span data-ttu-id="3c009-186">Ohne den **Force** -Parameter würde die Sitzung zwei Kopien jedes **psdiagnostics** -Cmdlets enthalten, eine mit dem Standardnamen und eine mit dem Namen mit dem Präfix.</span><span class="sxs-lookup"><span data-stu-id="3c009-186">Without the **Force** parameter, the session would include two copies of each **PSDiagnostics** cmdlet, one with the standard name and one with the prefixed name.</span></span>

### <span data-ttu-id="3c009-187">Beispiel 9: Ausführen von Befehlen, die von importierten Befehlen ausgeblendet wurden</span><span class="sxs-lookup"><span data-stu-id="3c009-187">Example 9: Run commands that have been hidden by imported commands</span></span>

<span data-ttu-id="3c009-188">In diesem Beispiel wird veranschaulicht, wie Befehle ausgeführt werden, die von importierten Befehlen ausgeblendet wurden.</span><span class="sxs-lookup"><span data-stu-id="3c009-188">This example shows how to run commands that have been hidden by imported commands.</span></span> <span data-ttu-id="3c009-189">Das **Testmodule** -Modul enthält eine Funktion `Get-Date` mit dem Namen, die das Jahr und den Tag des Jahres zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="3c009-189">The **TestModule** module includes a function named `Get-Date` that returns the year and day of the year.</span></span>

```powershell
Get-Date
```

```Output
Thursday, August 15, 2019 2:26:12 PM
```

```powershell
Import-Module TestModule
Get-Date
```

```Output
19227
```

```powershell
Get-Command Get-Date -All | Format-Table -Property CommandType, Name, ModuleName -AutoSize
```

```Output
CommandType     Name         ModuleName
-----------     ----         ----------
Function        Get-Date     TestModule
Cmdlet          Get-Date     Microsoft.PowerShell.Utility
```

```powershell
Microsoft.PowerShell.Utility\Get-Date
```

```Output
Thursday, August 15, 2019 2:28:31 PM
```

<span data-ttu-id="3c009-190">Das erste `Get-Date` Cmdlet gibt ein **DateTime** -Objekt mit dem aktuellen Datum zurück.</span><span class="sxs-lookup"><span data-stu-id="3c009-190">The first `Get-Date` cmdlet returns a **DateTime** object with the current date.</span></span> <span data-ttu-id="3c009-191">Nach dem Importieren des **Testmodule** `Get-Date` -Moduls gibt das Jahr und den Tag des Jahres zurück.</span><span class="sxs-lookup"><span data-stu-id="3c009-191">After importing the **TestModule** module, `Get-Date` returns the year and day of the year.</span></span>

<span data-ttu-id="3c009-192">Mit dem **all** -Parameter von werden `Get-Command` alle `Get-Date` Befehle in der Sitzung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3c009-192">Using the **All** parameter of `Get-Command` show all the `Get-Date` commands in the session.</span></span> <span data-ttu-id="3c009-193">Die Ergebnisse zeigen, dass es zwei `Get-Date` Befehle in der Sitzung gibt, eine Funktion aus dem **Testmodule** -Modul und ein Cmdlet aus dem **Microsoft. PowerShell. Utility** -Modul.</span><span class="sxs-lookup"><span data-stu-id="3c009-193">The results show that there are two `Get-Date` commands in the session, a function from the **TestModule** module and a cmdlet from the **Microsoft.PowerShell.Utility** module.</span></span>

<span data-ttu-id="3c009-194">Da Funktionen Vorrang vor Cmdlets haben, wird die- `Get-Date` Funktion aus dem **Testmodule** -Modul anstelle des- `Get-Date` Cmdlets ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="3c009-194">Because functions take precedence over cmdlets, the `Get-Date` function from the **TestModule** module runs, instead of the `Get-Date` cmdlet.</span></span> <span data-ttu-id="3c009-195">Um die ursprüngliche Version von auszuführen `Get-Date` , müssen Sie den Befehlsnamen mit dem Modulnamen qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="3c009-195">To run the original version of `Get-Date`, you must qualify the command name with the module name.</span></span>

<span data-ttu-id="3c009-196">Weitere Informationen zur Befehls Rangfolge in PowerShell finden Sie unter [about_Command_Precedence](about/about_Command_Precedence.md).</span><span class="sxs-lookup"><span data-stu-id="3c009-196">For more information about command precedence in PowerShell, see [about_Command_Precedence](about/about_Command_Precedence.md).</span></span>

### <span data-ttu-id="3c009-197">Beispiel 10: Importieren einer Mindestversion eines Moduls</span><span class="sxs-lookup"><span data-stu-id="3c009-197">Example 10: Import a minimum version of a module</span></span>

<span data-ttu-id="3c009-198">In diesem Beispiel wird das **PowerShellGet** -Modul importiert.</span><span class="sxs-lookup"><span data-stu-id="3c009-198">This example imports the **PowerShellGet** module.</span></span> <span data-ttu-id="3c009-199">Er verwendet den **Minimum Version** -Parameter von `Import-Module` , um nur Version 2.0.0 oder höher des Moduls zu importieren.</span><span class="sxs-lookup"><span data-stu-id="3c009-199">It uses the **MinimumVersion** parameter of `Import-Module` to import only version 2.0.0 or greater of the module.</span></span>

```powershell
Import-Module -Name PowerShellGet -MinimumVersion 2.0.0
```

<span data-ttu-id="3c009-200">Sie können auch den Parameter "Requirements **dversion** " verwenden, um eine bestimmte Version eines Moduls zu importieren, oder die **Modul** -und **Versions** Parameter des `#Requires` Schlüssel Worts verwenden, um eine bestimmte Version eines Moduls in einem Skript anzufordern.</span><span class="sxs-lookup"><span data-stu-id="3c009-200">You can also use the **RequiredVersion** parameter to import a particular version of a module, or use the **Module** and **Version** parameters of the `#Requires` keyword to require a particular version of a module in a script.</span></span>

### <span data-ttu-id="3c009-201">Beispiel 11: Importieren mit einem voll qualifizierten Namen</span><span class="sxs-lookup"><span data-stu-id="3c009-201">Example 11: Import using a fully qualified name</span></span>

<span data-ttu-id="3c009-202">In diesem Beispiel wird eine bestimmte Version eines Moduls mit dem FullyQualifiedName importiert.</span><span class="sxs-lookup"><span data-stu-id="3c009-202">This example imports a specific version of a module using the FullyQualifiedName.</span></span>

```powershell
PS> Get-Module -ListAvailable PowerShellGet | Select-Object Name, Version

Name          Version
----          -------
PowerShellGet 2.2.1
PowerShellGet 2.1.3
PowerShellGet 2.1.2
PowerShellGet 1.0.0.1

PS> Import-Module -FullyQualifiedName @{ModuleName = 'PowerShellGet'; ModuleVersion = '2.1.3' }
```

### <span data-ttu-id="3c009-203">Beispiel 12: Importieren mithilfe eines voll qualifizierten Pfads</span><span class="sxs-lookup"><span data-stu-id="3c009-203">Example 12: Import using a fully qualified path</span></span>

<span data-ttu-id="3c009-204">In diesem Beispiel wird eine bestimmte Version eines Moduls mit dem voll qualifizierten Pfad importiert.</span><span class="sxs-lookup"><span data-stu-id="3c009-204">This example imports a specific version of a module using the fully qualified path.</span></span>

```powershell
PS> Get-Module -ListAvailable PowerShellGet | Select-Object Path

Path
----
C:\Program Files\PowerShell\Modules\PowerShellGet\2.2.1\PowerShellGet.psd1
C:\program files\powershell\6\Modules\PowerShellGet\PowerShellGet.psd1
C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\2.1.2\PowerShellGet.psd1
C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\1.0.0.1\PowerShellGet.psd1

PS> Import-Module -Name 'C:\Program Files\PowerShell\Modules\PowerShellGet\2.2.1\PowerShellGet.psd1'
```

### <span data-ttu-id="3c009-205">Beispiel 13: Importieren eines Moduls von einem Remote Computer</span><span class="sxs-lookup"><span data-stu-id="3c009-205">Example 13: Import a module from a remote computer</span></span>

<span data-ttu-id="3c009-206">In diesem Beispiel wird gezeigt, wie Sie mit dem- `Import-Module` Cmdlet ein Modul von einem Remote Computer importieren.</span><span class="sxs-lookup"><span data-stu-id="3c009-206">This example shows how to use the `Import-Module` cmdlet to import a module from a remote computer.</span></span>
<span data-ttu-id="3c009-207">Dieser Befehl verwendet das implizite Remoting-Feature von PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3c009-207">This command uses the Implicit Remoting feature of PowerShell.</span></span>

<span data-ttu-id="3c009-208">Wenn Sie Module aus einer anderen Sitzung importieren, können Sie die Cmdlets in der aktuellen Sitzung verwenden.</span><span class="sxs-lookup"><span data-stu-id="3c009-208">When you import modules from another session, you can use the cmdlets in the current session.</span></span>
<span data-ttu-id="3c009-209">Befehle, die die Cmdlets verwenden, werden jedoch in der Remote Sitzung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="3c009-209">However, commands that use the cmdlets run in the remote session.</span></span>

```powershell
$s = New-PSSession -ComputerName Server01
Get-Module -PSSession $s -ListAvailable -Name NetSecurity
```

```Output
ModuleType Name             ExportedCommands
---------- ----             ----------------
Manifest   NetSecurity      {New-NetIPsecAuthProposal, New-NetIPsecMainModeCryptoProposal, New-Ne...
```

```powershell
Import-Module -PSSession $s -Name NetSecurity
Get-Command -Module NetSecurity -Name Get-*Firewall*
```

```Output
CommandType     Name                                               ModuleName
-----------     ----                                               ----------
Function        Get-NetFirewallAddressFilter                       NetSecurity
Function        Get-NetFirewallApplicationFilter                   NetSecurity
Function        Get-NetFirewallInterfaceFilter                     NetSecurity
Function        Get-NetFirewallInterfaceTypeFilter                 NetSecurity
Function        Get-NetFirewallPortFilter                          NetSecurity
Function        Get-NetFirewallProfile                             NetSecurity
Function        Get-NetFirewallRule                                NetSecurity
Function        Get-NetFirewallSecurityFilter                      NetSecurity
Function        Get-NetFirewallServiceFilter                       NetSecurity
Function        Get-NetFirewallSetting                             NetSecurity
```

```powershell
Get-NetFirewallRule -DisplayName "Windows Remote Management*" |
  Format-Table -Property DisplayName, Name -AutoSize
```

```Output
DisplayName                                              Name
-----------                                              ----
Windows Remote Management (HTTP-In)                      WINRM-HTTP-In-TCP
Windows Remote Management (HTTP-In)                      WINRM-HTTP-In-TCP-PUBLIC
Windows Remote Management - Compatibility Mode (HTTP-In) WINRM-HTTP-Compat-In-TCP
```

<span data-ttu-id="3c009-210">`New-PSSession` erstellt eine Remote Sitzung (**PSSession**) mit dem Server01-Computer.</span><span class="sxs-lookup"><span data-stu-id="3c009-210">`New-PSSession` creates a remote session (**PSSession**) to the Server01 computer.</span></span> <span data-ttu-id="3c009-211">Die **PSSession** wird in der `$s` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="3c009-211">The **PSSession** is saved in the `$s` variable.</span></span>

<span data-ttu-id="3c009-212">Das Ausführen `Get-Module` von mit dem **PSSession** -Parameter zeigt an, dass das **Netsecurity** -Modul auf dem Remote Computer installiert und verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="3c009-212">Running `Get-Module` with the **PSSession** parameter shows that the **NetSecurity** module is installed and available on the remote computer.</span></span> <span data-ttu-id="3c009-213">Dieser Befehl entspricht der Verwendung des- `Invoke-Command` Cmdlets zum Ausführen des `Get-Module` Befehls in der Remote Sitzung.</span><span class="sxs-lookup"><span data-stu-id="3c009-213">This command is equivalent to using the `Invoke-Command` cmdlet to run `Get-Module` command in the remote session.</span></span> <span data-ttu-id="3c009-214">Beispiel: (`Invoke-Command $s {Get-Module -ListAvailable -Name NetSecurity`</span><span class="sxs-lookup"><span data-stu-id="3c009-214">For example: (`Invoke-Command $s {Get-Module -ListAvailable -Name NetSecurity`</span></span>

<span data-ttu-id="3c009-215">Beim Ausführen `Import-Module` mit dem **PSSession** -Parameter wird das **Netsecurity** -Modul vom Remote Computer in die aktuelle Sitzung importiert.</span><span class="sxs-lookup"><span data-stu-id="3c009-215">Running `Import-Module` with the **PSSession** parameter imports the **NetSecurity** module from the remote computer into the current session.</span></span> <span data-ttu-id="3c009-216">Das- `Get-Command` Cmdlet wird verwendet, um Befehle zu erhalten, die mit **Get** und include **Firewall** aus dem **Netsecurity** -Modul beginnen.</span><span class="sxs-lookup"><span data-stu-id="3c009-216">The `Get-Command` cmdlet is used to get commands that begin with **Get** and include **Firewall** from the **NetSecurity** module.</span></span> <span data-ttu-id="3c009-217">Die Ausgabe bestätigt, dass das Modul und die zugehörigen Cmdlets in die aktuelle Sitzung importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="3c009-217">The output confirms that the module and its cmdlets were imported into the current session.</span></span>

<span data-ttu-id="3c009-218">Als nächstes `Get-NetFirewallRule` Ruft das Cmdlet Windows-Remoteverwaltung Firewallregeln auf dem Computer "Server01" ab.</span><span class="sxs-lookup"><span data-stu-id="3c009-218">Next, the `Get-NetFirewallRule` cmdlet gets Windows Remote Management firewall rules on the Server01 computer.</span></span> <span data-ttu-id="3c009-219">Dies entspricht der Verwendung des- `Invoke-Command` Cmdlets, um `Get-NetFirewallRule` in der Remote Sitzung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="3c009-219">This is equivalent to using the `Invoke-Command` cmdlet to run `Get-NetFirewallRule` on the remote session.</span></span>

### <span data-ttu-id="3c009-220">Beispiel 14: Verwalten von Speicher auf einem Remote Computer ohne das Windows-Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="3c009-220">Example 14: Manage storage on a remote computer without the Windows operating system</span></span>

<span data-ttu-id="3c009-221">In diesem Beispiel hat der Administrator des Computers den WMI-Anbieter für die Modul Ermittlung installiert, mit dem Sie CIM-Befehle verwenden können, die für den Anbieter entwickelt wurden.</span><span class="sxs-lookup"><span data-stu-id="3c009-221">In this example, the administrator of the computer has installed the Module Discovery WMI provider, which allows you to use CIM commands that are designed for the provider.</span></span>

<span data-ttu-id="3c009-222">Mit dem- `New-CimSession` Cmdlet wird eine Sitzung auf dem Remote Computer mit dem Namen RSDGF03 erstellt.</span><span class="sxs-lookup"><span data-stu-id="3c009-222">The `New-CimSession` cmdlet creates a session on the remote computer named RSDGF03.</span></span> <span data-ttu-id="3c009-223">Die Sitzung stellt eine Verbindung mit dem WMI-Dienst auf dem Remote Computer her.</span><span class="sxs-lookup"><span data-stu-id="3c009-223">The session connects to the WMI service on the remote computer.</span></span> <span data-ttu-id="3c009-224">Die CIM-Sitzung wird in der `$cs` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="3c009-224">The CIM session is saved in the `$cs` variable.</span></span>
<span data-ttu-id="3c009-225">`Import-Module` verwendet **cimsession** in `$cs` , um das **Storage** -CIM-Modul vom RSDGF03-Computer zu importieren.</span><span class="sxs-lookup"><span data-stu-id="3c009-225">`Import-Module` uses the **CimSession** in `$cs` to import the **Storage** CIM module from the RSDGF03 computer.</span></span>

<span data-ttu-id="3c009-226">Das- `Get-Command` Cmdlet zeigt den `Get-Disk` Befehl im **Storage** -Modul an.</span><span class="sxs-lookup"><span data-stu-id="3c009-226">The `Get-Command` cmdlet shows the `Get-Disk` command in the **Storage** module.</span></span> <span data-ttu-id="3c009-227">Wenn Sie ein CIM-Modul in die lokale Sitzung importieren, konvertiert PowerShell die cdxml-Dateien für jeden Befehl in PowerShell-Skripts, die als Funktionen in der lokalen Sitzung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="3c009-227">When you import a CIM module into the local session, PowerShell converts the CDXML files for each command into PowerShell scripts, which appear as functions in the local session.</span></span>

<span data-ttu-id="3c009-228">Obwohl `Get-Disk` in der lokalen Sitzung typisiert ist, wird das Cmdlet implizit auf dem Remote Computer ausgeführt, von dem er importiert wurde.</span><span class="sxs-lookup"><span data-stu-id="3c009-228">Although `Get-Disk` is typed in the local session, the cmdlet implicitly runs on the remote computer from which it was imported.</span></span> <span data-ttu-id="3c009-229">Der Befehl gibt Objekte vom Remote Computer an die lokale Sitzung zurück.</span><span class="sxs-lookup"><span data-stu-id="3c009-229">The command returns objects from the remote computer to the local session.</span></span>

```powershell
$cs = New-CimSession -ComputerName RSDGF03
Import-Module -CimSession $cs -Name Storage
# Importing a CIM module, converts the CDXML files for each command into PowerShell scripts.
# These appear as functions in the local session.
Get-Command Get-Disk
```

```Output
CommandType     Name                  ModuleName
-----------     ----                  ----------
Function        Get-Disk              Storage
```

```powershell
# Use implicit remoting to query disks on the remote computer from which the module was imported.
Get-Disk
```

```Output
Number Friendly Name           OperationalStatus  Total Size Partition Style
------ -------------           -----------------  ---------- ---------------
0      Virtual HD ATA Device   Online                  40 GB MBR
```

## <span data-ttu-id="3c009-230">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3c009-230">PARAMETERS</span></span>

### <span data-ttu-id="3c009-231">-Alias</span><span class="sxs-lookup"><span data-stu-id="3c009-231">-Alias</span></span>

<span data-ttu-id="3c009-232">Gibt die Aliase an, die dieses Cmdlet aus dem Modul in die aktuelle Sitzung importiert.</span><span class="sxs-lookup"><span data-stu-id="3c009-232">Specifies the aliases that this cmdlet imports from the module into the current session.</span></span> <span data-ttu-id="3c009-233">Geben Sie eine durch Kommas getrennte Liste der Aliase ein.</span><span class="sxs-lookup"><span data-stu-id="3c009-233">Enter a comma-separated list of aliases.</span></span> <span data-ttu-id="3c009-234">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="3c009-234">Wildcard characters are permitted.</span></span>

<span data-ttu-id="3c009-235">Einige Module exportieren automatisch ausgewählte Aliase in Ihre Sitzung, wenn Sie das Modul importieren.</span><span class="sxs-lookup"><span data-stu-id="3c009-235">Some modules automatically export selected aliases into your session when you import the module.</span></span>
<span data-ttu-id="3c009-236">Mit diesem Parameter können Sie eine Auswahl aus den exportierten Aliasen treffen.</span><span class="sxs-lookup"><span data-stu-id="3c009-236">This parameter lets you select from among the exported aliases.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="3c009-237">-Argumentlist</span><span class="sxs-lookup"><span data-stu-id="3c009-237">-ArgumentList</span></span>

<span data-ttu-id="3c009-238">Gibt ein Array von Argumenten oder Parameterwerten an, die während des Befehls an ein Skript Modul übergeben werden `Import-Module` .</span><span class="sxs-lookup"><span data-stu-id="3c009-238">Specifies an array of arguments, or parameter values, that are passed to a script module during the `Import-Module` command.</span></span> <span data-ttu-id="3c009-239">Dieser Parameter ist nur gültig, wenn Sie ein Skript Modul importieren.</span><span class="sxs-lookup"><span data-stu-id="3c009-239">This parameter is valid only when you're importing a script module.</span></span>

<span data-ttu-id="3c009-240">Sie können auch über den Alias " **args**" auf den Argument **List** -Parameter verweisen.</span><span class="sxs-lookup"><span data-stu-id="3c009-240">You can also refer to the **ArgumentList** parameter by its alias, **args**.</span></span> <span data-ttu-id="3c009-241">Weitere Informationen zum Verhalten von **argumentlist** finden Sie unter [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span><span class="sxs-lookup"><span data-stu-id="3c009-241">For more information about the behavior of **ArgumentList**, see [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3c009-242">-Ascustomobject</span><span class="sxs-lookup"><span data-stu-id="3c009-242">-AsCustomObject</span></span>

<span data-ttu-id="3c009-243">Gibt an, dass dieses Cmdlet ein benutzerdefiniertes Objekt mit Membern zurückgibt, die die importierten Modul Elemente darstellen.</span><span class="sxs-lookup"><span data-stu-id="3c009-243">Indicates that this cmdlet returns a custom object with members that represent the imported module members.</span></span> <span data-ttu-id="3c009-244">Dieser Parameter gilt nur für Skriptmodule.</span><span class="sxs-lookup"><span data-stu-id="3c009-244">This parameter is valid only for script modules.</span></span>

<span data-ttu-id="3c009-245">Wenn Sie den **ascustomobject** -Parameter verwenden, `Import-Module` importiert die Modul Elemente in die Sitzung und gibt dann ein **pscustomobject** -Objekt anstelle eines **psmoduleinfo** -Objekts zurück.</span><span class="sxs-lookup"><span data-stu-id="3c009-245">When you use the **AsCustomObject** parameter, `Import-Module` imports the module members into the session and then returns a **PSCustomObject** object instead of a **PSModuleInfo** object.</span></span> <span data-ttu-id="3c009-246">Sie können das benutzerdefinierte Objekt in einer Variablen speichern und die punktierte Schreibweise verwenden, um die Elemente aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="3c009-246">You can save the custom object in a variable and use dot notation to invoke the members.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3c009-247">-Assembly</span><span class="sxs-lookup"><span data-stu-id="3c009-247">-Assembly</span></span>

<span data-ttu-id="3c009-248">Gibt ein Array von assemblyobjekten an.</span><span class="sxs-lookup"><span data-stu-id="3c009-248">Specifies an array of assembly objects.</span></span> <span data-ttu-id="3c009-249">Mit diesem Cmdlet werden die in den angegebenen assemblyobjekten implementierten Cmdlets und Anbieter importiert.</span><span class="sxs-lookup"><span data-stu-id="3c009-249">This cmdlet imports the cmdlets and providers implemented in the specified assembly objects.</span></span> <span data-ttu-id="3c009-250">Geben Sie eine Variable ein, die Assemblyobjekte enthält, oder geben Sie einen Befehl ein, mit dem die Assemblyobjekte erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="3c009-250">Enter a variable that contains assembly objects or a command that creates assembly objects.</span></span> <span data-ttu-id="3c009-251">Sie können ein Assemblyobjekt auch über die Pipeline an senden `Import-Module` .</span><span class="sxs-lookup"><span data-stu-id="3c009-251">You can also pipe an assembly object to `Import-Module`.</span></span>

<span data-ttu-id="3c009-252">Wenn Sie diesen Parameter verwenden, werden nur die Cmdlets und Anbieter importiert, die durch die angegebenen Assemblys implementiert wurden.</span><span class="sxs-lookup"><span data-stu-id="3c009-252">When you use this parameter, only the cmdlets and providers implemented by the specified assemblies are imported.</span></span> <span data-ttu-id="3c009-253">Wenn das Modul andere Dateien enthält, werden Sie nicht importiert, und möglicherweise fehlen wichtige Member des Moduls.</span><span class="sxs-lookup"><span data-stu-id="3c009-253">If the module contains other files, they aren't imported, and you might be missing important members of the module.</span></span> <span data-ttu-id="3c009-254">Verwenden Sie diesen Parameter zum Debuggen und Testen des Moduls, oder wenn Sie angewiesen werden, es vom Modul Autor zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="3c009-254">Use this parameter for debugging and testing the module, or when you're instructed to use it by the module author.</span></span>

```yaml
Type: System.Reflection.Assembly[]
Parameter Sets: Assembly
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="3c009-255">-Cimnamespace</span><span class="sxs-lookup"><span data-stu-id="3c009-255">-CimNamespace</span></span>

<span data-ttu-id="3c009-256">Gibt den Namespace eines alternativen CIM-Anbieters an, der CIM-Module verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="3c009-256">Specifies the namespace of an alternate CIM provider that exposes CIM modules.</span></span> <span data-ttu-id="3c009-257">Der Standardwert ist der Namespace des WMI-Anbieters für die Modulerkennung.</span><span class="sxs-lookup"><span data-stu-id="3c009-257">The default value is the namespace of the Module Discovery WMI provider.</span></span>

<span data-ttu-id="3c009-258">Verwenden Sie diesen Parameter, um CIM-Module von Computern und Geräten zu importieren, auf denen kein Windows-Betriebssystem ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3c009-258">Use this parameter to import CIM modules from computers and devices that aren't running a Windows operating system.</span></span>

<span data-ttu-id="3c009-259">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="3c009-259">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: CimSession
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3c009-260">-Cimresourceuri</span><span class="sxs-lookup"><span data-stu-id="3c009-260">-CimResourceUri</span></span>

<span data-ttu-id="3c009-261">Gibt einen alternativen Speicherort für die CIM-Module an.</span><span class="sxs-lookup"><span data-stu-id="3c009-261">Specifies an alternate location for CIM modules.</span></span> <span data-ttu-id="3c009-262">Der Standardwert ist der Ressourcen-URI des WMI-Anbieters für die Modul Ermittlung auf dem Remote Computer.</span><span class="sxs-lookup"><span data-stu-id="3c009-262">The default value is the resource URI of the Module Discovery WMI provider on the remote computer.</span></span>

<span data-ttu-id="3c009-263">Verwenden Sie diesen Parameter, um CIM-Module von Computern und Geräten zu importieren, auf denen kein Windows-Betriebssystem ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3c009-263">Use this parameter to import CIM modules from computers and devices that aren't running a Windows operating system.</span></span>

<span data-ttu-id="3c009-264">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="3c009-264">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Uri
Parameter Sets: CimSession
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3c009-265">-CimSession</span><span class="sxs-lookup"><span data-stu-id="3c009-265">-CimSession</span></span>

<span data-ttu-id="3c009-266">Gibt eine CIM-Sitzung auf dem Remotecomputer an.</span><span class="sxs-lookup"><span data-stu-id="3c009-266">Specifies a CIM session on the remote computer.</span></span> <span data-ttu-id="3c009-267">Geben Sie eine Variable ein, die die CIM-Sitzung oder einen Befehl enthält, der die CIM-Sitzung abruft, z. b. den Befehl [Get-cimsession](../CimCmdlets/Get-CimSession.md) .</span><span class="sxs-lookup"><span data-stu-id="3c009-267">Enter a variable that contains the CIM session or a command that gets the CIM session, such as a [Get-CimSession](../CimCmdlets/Get-CimSession.md) command.</span></span>

<span data-ttu-id="3c009-268">`Import-Module` verwendet die CIM-Sitzungs Verbindung, um Module vom Remote Computer in die aktuelle Sitzung zu importieren.</span><span class="sxs-lookup"><span data-stu-id="3c009-268">`Import-Module` uses the CIM session connection to import modules from the remote computer into the current session.</span></span> <span data-ttu-id="3c009-269">Wenn Sie die Befehle aus dem importierten Modul in der aktuellen Sitzung verwenden, werden die Befehle auf dem Remote Computer ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="3c009-269">When you use the commands from the imported module in the current session, the commands run on the remote computer.</span></span>

<span data-ttu-id="3c009-270">Sie können diesen Parameter verwenden, um Module von Computern und Geräten zu importieren, auf denen das Windows-Betriebssystem nicht ausgeführt wird, sowie von Windows-Computern mit PowerShell, für die PowerShell-Remoting nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="3c009-270">You can use this parameter to import modules from computers and devices that aren't running the Windows operating system, and Windows computers that have PowerShell, but don't have PowerShell remoting enabled.</span></span>

<span data-ttu-id="3c009-271">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="3c009-271">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession
Parameter Sets: CimSession
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3c009-272">-Cmdlet</span><span class="sxs-lookup"><span data-stu-id="3c009-272">-Cmdlet</span></span>

<span data-ttu-id="3c009-273">Gibt ein Array von Cmdlets an, die von diesem Cmdlet aus dem Modul in die aktuelle Sitzung importiert werden.</span><span class="sxs-lookup"><span data-stu-id="3c009-273">Specifies an array of cmdlets that this cmdlet imports from the module into the current session.</span></span>
<span data-ttu-id="3c009-274">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="3c009-274">Wildcard characters are permitted.</span></span>

<span data-ttu-id="3c009-275">Einige Module exportieren automatisch ausgewählte Cmdlets in Ihre Sitzung, wenn Sie das Modul importieren.</span><span class="sxs-lookup"><span data-stu-id="3c009-275">Some modules automatically export selected cmdlets into your session when you import the module.</span></span>
<span data-ttu-id="3c009-276">Mit diesem Parameter können Sie eine Auswahl aus den exportierten Cmdlets treffen.</span><span class="sxs-lookup"><span data-stu-id="3c009-276">This parameter lets you select from among the exported cmdlets.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="3c009-277">-Disablenamecheck</span><span class="sxs-lookup"><span data-stu-id="3c009-277">-DisableNameChecking</span></span>

<span data-ttu-id="3c009-278">Gibt an, dass dieses Cmdlet die Meldung unterdrückt, die Sie warnt, wenn Sie ein Cmdlet oder eine Funktion importieren, deren Name ein nicht genehmigtes Verb oder ein unzulässiges Zeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="3c009-278">Indicates that this cmdlet suppresses the message that warns you when you import a cmdlet or function whose name includes an unapproved verb or a prohibited character.</span></span>

<span data-ttu-id="3c009-279">Wenn ein Modul, das Sie importieren, Cmdlets oder Funktionen exportiert, die nicht genehmigte Verben in ihren Namen haben, zeigt PowerShell standardmäßig die folgende Warnmeldung an:</span><span class="sxs-lookup"><span data-stu-id="3c009-279">By default, when a module that you import exports cmdlets or functions that have unapproved verbs in their names, PowerShell displays the following warning message:</span></span>

> <span data-ttu-id="3c009-280">Warnung: einige importierte Befehlsnamen enthalten nicht genehmigte Verben, die Sie möglicherweise weniger auffallen machen.</span><span class="sxs-lookup"><span data-stu-id="3c009-280">WARNING: Some imported command names include unapproved verbs which might make them less discoverable.</span></span> <span data-ttu-id="3c009-281">Verwenden Sie den Verbose-Parameter für weitere Details, oder geben Sie „Get-Verb“ ein, um die Liste der zulässigen Verben anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="3c009-281">Use the Verbose parameter for more detail or type Get-Verb to see the list of approved verbs.</span></span>

<span data-ttu-id="3c009-282">Diese Meldung ist nur eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="3c009-282">This message is only a warning.</span></span> <span data-ttu-id="3c009-283">Es wird trotzdem das gesamte Modul einschließlich nicht konformer Befehle importiert.</span><span class="sxs-lookup"><span data-stu-id="3c009-283">The complete module is still imported, including the non-conforming commands.</span></span> <span data-ttu-id="3c009-284">Obwohl die Meldung für Modulbenutzer angezeigt wird, sollte das Namensproblem vom Modulautor behoben werden.</span><span class="sxs-lookup"><span data-stu-id="3c009-284">Although the message is displayed to module users, the naming problem should be fixed by the module author.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3c009-285">-Force</span><span class="sxs-lookup"><span data-stu-id="3c009-285">-Force</span></span>

<span data-ttu-id="3c009-286">Dieser Parameter bewirkt, dass ein Modul über den aktuellen Anfang geladen oder neu geladen wird.</span><span class="sxs-lookup"><span data-stu-id="3c009-286">This parameter causes a module to be loaded, or reloaded, over top of the current one.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3c009-287">-FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="3c009-287">-FullyQualifiedName</span></span>

<span data-ttu-id="3c009-288">Gibt den voll qualifizierten Namen des Moduls als Hash Tabelle an.</span><span class="sxs-lookup"><span data-stu-id="3c009-288">Specifies the fully qualified name of the module as a hash table.</span></span> <span data-ttu-id="3c009-289">Der Wert kann eine Kombination aus Zeichen folgen und Hash Tabellen sein.</span><span class="sxs-lookup"><span data-stu-id="3c009-289">The value can be a combination of strings and hash tables.</span></span> <span data-ttu-id="3c009-290">Die Hash Tabelle verfügt über die folgenden Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="3c009-290">The hash table has the following keys.</span></span>

- <span data-ttu-id="3c009-291">`ModuleName` - **Erforderlich** Gibt den Namen des Moduls an.</span><span class="sxs-lookup"><span data-stu-id="3c009-291">`ModuleName` - **Required** Specifies the module name.</span></span>
- <span data-ttu-id="3c009-292">`GUID` - **Optional** Gibt die GUID des Moduls an.</span><span class="sxs-lookup"><span data-stu-id="3c009-292">`GUID` - **Optional** Specifies the GUID of the module.</span></span>
- <span data-ttu-id="3c009-293">Es ist auch **erforderlich** , einen der drei folgenden Schlüssel anzugeben.</span><span class="sxs-lookup"><span data-stu-id="3c009-293">It's also **Required** to specify one of the three below keys.</span></span> <span data-ttu-id="3c009-294">Diese Schlüssel können nicht gleichzeitig verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3c009-294">These keys can't be used together.</span></span>
  - <span data-ttu-id="3c009-295">`ModuleVersion` : Gibt eine zulässige Mindestversion des Moduls an.</span><span class="sxs-lookup"><span data-stu-id="3c009-295">`ModuleVersion` - Specifies a minimum acceptable version of the module.</span></span>
  - <span data-ttu-id="3c009-296">`RequiredVersion` : Gibt eine exakte, erforderliche Version des Moduls an.</span><span class="sxs-lookup"><span data-stu-id="3c009-296">`RequiredVersion` - Specifies an exact, required version of the module.</span></span>
  - <span data-ttu-id="3c009-297">`MaximumVersion` : Gibt die maximal zulässige Version des Moduls an.</span><span class="sxs-lookup"><span data-stu-id="3c009-297">`MaximumVersion` - Specifies the maximum acceptable version of the module.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification[]
Parameter Sets: FullyQualifiedName, FullyQualifiedNameAndPSSession
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="3c009-298">-Funktion</span><span class="sxs-lookup"><span data-stu-id="3c009-298">-Function</span></span>

<span data-ttu-id="3c009-299">Gibt ein Array von Funktionen an, die dieses Cmdlet aus dem Modul in die aktuelle Sitzung importiert.</span><span class="sxs-lookup"><span data-stu-id="3c009-299">Specifies an array of functions that this cmdlet imports from the module into the current session.</span></span>
<span data-ttu-id="3c009-300">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="3c009-300">Wildcard characters are permitted.</span></span> <span data-ttu-id="3c009-301">Einige Module exportieren automatisch ausgewählte Funktionen in Ihre Sitzung, wenn Sie das Modul importieren.</span><span class="sxs-lookup"><span data-stu-id="3c009-301">Some modules automatically export selected functions into your session when you import the module.</span></span> <span data-ttu-id="3c009-302">Mit diesem Parameter können Sie eine Auswahl aus den exportierten Funktionen treffen.</span><span class="sxs-lookup"><span data-stu-id="3c009-302">This parameter lets you select from among the exported functions.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="3c009-303">-Global</span><span class="sxs-lookup"><span data-stu-id="3c009-303">-Global</span></span>

<span data-ttu-id="3c009-304">Gibt an, dass dieses Cmdlet Module in den globalen Sitzungszustand importiert, sodass Sie für alle Befehle in der Sitzung verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="3c009-304">Indicates that this cmdlet imports modules into the global session state so they are available to all commands in the session.</span></span>

<span data-ttu-id="3c009-305">Wenn `Import-Module` das Cmdlet von der Eingabeaufforderung, von der Skriptdatei oder von ScriptBlock aufgerufen wird, werden standardmäßig alle Befehle in den globalen Sitzungszustand importiert.</span><span class="sxs-lookup"><span data-stu-id="3c009-305">By default, when `Import-Module` cmdlet is called from the command prompt, script file, or scriptblock, all the commands are imported into the global session state.</span></span>

<span data-ttu-id="3c009-306">Wenn Sie von einem anderen Modul aufgerufen wird, `Import-Module` importiert das Cmdlet die Befehle in einem Modul, einschließlich der Befehle aus den in einem Modul eingefügten Modulen, in den Sitzungszustand des aufrufenden Moduls</span><span class="sxs-lookup"><span data-stu-id="3c009-306">When invoked from another module, `Import-Module` cmdlet imports the commands in a module, including commands from nested modules, into the calling module's session state.</span></span>

> [!TIP]
> <span data-ttu-id="3c009-307">Vermeiden Sie das Aufrufen `Import-Module` von innerhalb eines Moduls.</span><span class="sxs-lookup"><span data-stu-id="3c009-307">You should avoid calling `Import-Module` from within a module.</span></span> <span data-ttu-id="3c009-308">Deklarieren Sie das Zielmodul stattdessen als ein gestreamtes Modul im Manifest des übergeordneten Moduls.</span><span class="sxs-lookup"><span data-stu-id="3c009-308">Instead, declare the target module as a nested module in the parent module's manifest.</span></span> <span data-ttu-id="3c009-309">Das Deklarieren von geschsted Modulen verbessert die Auffindbarkeit von Abhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="3c009-309">Declaring nested modules improves the discoverability of dependencies.</span></span>

<span data-ttu-id="3c009-310">Der **Global**-Parameter entspricht dem **Scope**-Parameter mit dem Wert **Global**.</span><span class="sxs-lookup"><span data-stu-id="3c009-310">The **Global** parameter is equivalent to the **Scope** parameter with a value of **Global**.</span></span>

<span data-ttu-id="3c009-311">Um die Befehle einzuschränken, die ein Modul exportiert, verwenden Sie einen `Export-ModuleMember` Befehl im Skript Modul.</span><span class="sxs-lookup"><span data-stu-id="3c009-311">To restrict the commands that a module exports, use an `Export-ModuleMember` command in the script module.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3c009-312">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="3c009-312">-MaximumVersion</span></span>

<span data-ttu-id="3c009-313">Gibt eine maximale Version an.</span><span class="sxs-lookup"><span data-stu-id="3c009-313">Specifies a maximum version.</span></span> <span data-ttu-id="3c009-314">Dieses Cmdlet importiert nur eine Version des Moduls, die kleiner oder gleich dem angegebenen Wert ist.</span><span class="sxs-lookup"><span data-stu-id="3c009-314">This cmdlet imports only a version of the module that is less than or equal to the specified value.</span></span> <span data-ttu-id="3c009-315">Wenn keine Version qualifiziert ist, wird `Import-Module` ein Fehler zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3c009-315">If no version qualifies, `Import-Module` returns an error.</span></span>

```yaml
Type: System.String
Parameter Sets: Name, PSSession, CimSession
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3c009-316">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="3c009-316">-MinimumVersion</span></span>

<span data-ttu-id="3c009-317">Gibt eine Mindestversion an.</span><span class="sxs-lookup"><span data-stu-id="3c009-317">Specifies a minimum version.</span></span> <span data-ttu-id="3c009-318">Dieses Cmdlet importiert nur eine Version des Moduls, das größer als der angegebene Wert oder gleich dem angegebenen Wert ist.</span><span class="sxs-lookup"><span data-stu-id="3c009-318">This cmdlet imports only a version of the module that is greater than or equal to the specified value.</span></span> <span data-ttu-id="3c009-319">Verwenden Sie den **MinimumVersion**-Parameternamen oder dessen Alias **Version**.</span><span class="sxs-lookup"><span data-stu-id="3c009-319">Use the **MinimumVersion** parameter name or its alias, **Version**.</span></span> <span data-ttu-id="3c009-320">Wenn keine Version qualifiziert ist, wird von `Import-Module` ein Fehler generiert.</span><span class="sxs-lookup"><span data-stu-id="3c009-320">If no version qualifies, `Import-Module` generates an error.</span></span>

<span data-ttu-id="3c009-321">Verwenden Sie zum Angeben einer genauen Version den **RequiredVersion**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="3c009-321">To specify an exact version, use the **RequiredVersion** parameter.</span></span> <span data-ttu-id="3c009-322">Sie können auch die **Module** -und **Versions** Parameter des **#requires** -Schlüssel Worts verwenden, um eine bestimmte Version eines Moduls in einem Skript anzufordern.</span><span class="sxs-lookup"><span data-stu-id="3c009-322">You can also use the **Module** and **Version** parameters of the **#Requires** keyword to require a specific version of a module in a script.</span></span>

<span data-ttu-id="3c009-323">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="3c009-323">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Version
Parameter Sets: Name, PSSession, CimSession
Aliases: Version

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3c009-324">-ModuleInfo</span><span class="sxs-lookup"><span data-stu-id="3c009-324">-ModuleInfo</span></span>

<span data-ttu-id="3c009-325">Gibt ein Array der zu importierenden Modul Objekte an.</span><span class="sxs-lookup"><span data-stu-id="3c009-325">Specifies an array of module objects to import.</span></span> <span data-ttu-id="3c009-326">Geben Sie eine Variable ein, die die Modul Objekte enthält, oder einen Befehl, mit dem die Modul Objekte abgerufen werden, z. b. den folgenden Befehl: `Get-Module -ListAvailable` .</span><span class="sxs-lookup"><span data-stu-id="3c009-326">Enter a variable that contains the module objects, or a command that gets the module objects, such as the following command: `Get-Module -ListAvailable`.</span></span> <span data-ttu-id="3c009-327">Sie können Modul Objekte auch über die Pipeline an übergeben `Import-Module` .</span><span class="sxs-lookup"><span data-stu-id="3c009-327">You can also pipe module objects to `Import-Module`.</span></span>

```yaml
Type: System.Management.Automation.PSModuleInfo[]
Parameter Sets: ModuleInfo
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="3c009-328">-Name</span><span class="sxs-lookup"><span data-stu-id="3c009-328">-Name</span></span>

<span data-ttu-id="3c009-329">Gibt die Namen der zu importierenden Module an.</span><span class="sxs-lookup"><span data-stu-id="3c009-329">Specifies the names of the modules to import.</span></span> <span data-ttu-id="3c009-330">Geben Sie den Namen des Moduls oder den Namen einer Datei im Modul ein, z. b. eine-,-,- `.psd1` `.psm1` oder- `.dll` `.ps1` Datei.</span><span class="sxs-lookup"><span data-stu-id="3c009-330">Enter the name of the module or the name of a file in the module, such as a `.psd1`, `.psm1`, `.dll`, or `.ps1` file.</span></span> <span data-ttu-id="3c009-331">Dateipfade sind optional.</span><span class="sxs-lookup"><span data-stu-id="3c009-331">File paths are optional.</span></span> <span data-ttu-id="3c009-332">Platzhalter Zeichen sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="3c009-332">Wildcard characters aren't permitted.</span></span> <span data-ttu-id="3c009-333">Sie können Modulnamen und Dateinamen auch über die Pipeline an übergeben `Import-Module` .</span><span class="sxs-lookup"><span data-stu-id="3c009-333">You can also pipe module names and filenames to `Import-Module`.</span></span>

<span data-ttu-id="3c009-334">Wenn Sie einen Pfad weglassen, `Import-Module` sucht das Modul in den Pfaden, die in der `$env:PSModulePath` Umgebungsvariablen gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="3c009-334">If you omit a path, `Import-Module` looks for the module in the paths saved in the `$env:PSModulePath` environment variable.</span></span>

<span data-ttu-id="3c009-335">Geben Sie nach Möglichkeit nur den Namen des Moduls an.</span><span class="sxs-lookup"><span data-stu-id="3c009-335">Specify only the module name whenever possible.</span></span> <span data-ttu-id="3c009-336">Wenn Sie einen Dateinamen angeben, werden nur die in dieser Datei implementierten Elemente importiert.</span><span class="sxs-lookup"><span data-stu-id="3c009-336">When you specify a file name, only the members that are implemented in that file are imported.</span></span> <span data-ttu-id="3c009-337">Wenn das Modul andere Dateien enthält, werden Sie nicht importiert, und möglicherweise fehlen wichtige Member des Moduls.</span><span class="sxs-lookup"><span data-stu-id="3c009-337">If the module contains other files, they aren't imported, and you might be missing important members of the module.</span></span>

> [!NOTE]
> <span data-ttu-id="3c009-338">Obwohl es möglich ist, eine Skriptdatei ( `.ps1` ) als Modul zu importieren, sind Skriptdateien in der Regel nicht wie die Skript Modul Datei Datei ( `.psm1` ) strukturiert.</span><span class="sxs-lookup"><span data-stu-id="3c009-338">While it is possible to import a script (`.ps1`) file as a module, script files are usually not structured like script modules file (`.psm1`) file.</span></span> <span data-ttu-id="3c009-339">Das Importieren einer Skriptdatei garantiert nicht, dass Sie als Modul verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="3c009-339">Importing a script file does not guarantee that it is usable as a module.</span></span> <span data-ttu-id="3c009-340">Weitere Informationen finden Sie unter [about_Modules](about/about_Modules.md).</span><span class="sxs-lookup"><span data-stu-id="3c009-340">For more information, see [about_Modules](about/about_Modules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name, PSSession, CimSession
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="3c009-341">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="3c009-341">-NoClobber</span></span>

<span data-ttu-id="3c009-342">Verhindert das Importieren von Befehlen, die denselben Namen wie vorhandene Befehle in der aktuellen Sitzung haben.</span><span class="sxs-lookup"><span data-stu-id="3c009-342">Prevents importing commands that have the same names as existing commands in the current session.</span></span> <span data-ttu-id="3c009-343">Standardmäßig werden `Import-Module` alle exportierten Modul Befehle importiert.</span><span class="sxs-lookup"><span data-stu-id="3c009-343">By default, `Import-Module` imports all exported module commands.</span></span>

<span data-ttu-id="3c009-344">Befehle mit den gleichen Namen können Befehle in der Sitzung ausblenden oder ersetzen.</span><span class="sxs-lookup"><span data-stu-id="3c009-344">Commands that have the same names can hide or replace commands in the session.</span></span> <span data-ttu-id="3c009-345">Um Konflikte bei Befehlsnamen in einer Sitzung zu vermeiden, verwenden Sie die Parameter **Prefix** oder **NoClobber**.</span><span class="sxs-lookup"><span data-stu-id="3c009-345">To avoid command name conflicts in a session, use the **Prefix** or **NoClobber** parameters.</span></span> <span data-ttu-id="3c009-346">Weitere Informationen (womöglich nur in englischer Sprache) zu Namenskonflikten und zur Befehlsrangfolge finden Sie unter „Module und Namenskonflikte“ in [about_Modules](about/about_Modules.md) und [about_Command_Precedence](about/about_Command_Precedence.md).</span><span class="sxs-lookup"><span data-stu-id="3c009-346">For more information about name conflicts and command precedence, see "Modules and Name Conflicts" in [about_Modules](about/about_Modules.md) and [about_Command_Precedence](about/about_Command_Precedence.md).</span></span>

<span data-ttu-id="3c009-347">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="3c009-347">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NoOverwrite

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3c009-348">-PassThru</span><span class="sxs-lookup"><span data-stu-id="3c009-348">-PassThru</span></span>

<span data-ttu-id="3c009-349">Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="3c009-349">Returns an object representing the item with which you're working.</span></span> <span data-ttu-id="3c009-350">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="3c009-350">By default, this cmdlet does not generate any output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3c009-351">-Präfix</span><span class="sxs-lookup"><span data-stu-id="3c009-351">-Prefix</span></span>

<span data-ttu-id="3c009-352">Gibt ein Präfix an, das dieses Cmdlet den Substantiven in den Namen importierter Modul Elemente hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="3c009-352">Specifies a prefix that this cmdlet adds to the nouns in the names of imported module members.</span></span>

<span data-ttu-id="3c009-353">Verwenden Sie diesen Parameter, um Namenskonflikte zu vermeiden, die auftreten können, wenn verschiedene Elemente in der Sitzung den gleichen Namen haben.</span><span class="sxs-lookup"><span data-stu-id="3c009-353">Use this parameter to avoid name conflicts that might occur when different members in the session have the same name.</span></span> <span data-ttu-id="3c009-354">Dieser Parameter ändert nicht das Modul und wirkt sich nicht auf Dateien aus, die das Modul zur eigenen Verwendung importiert.</span><span class="sxs-lookup"><span data-stu-id="3c009-354">This parameter does not change the module, and it does not affect files that the module imports for its own use.</span></span> <span data-ttu-id="3c009-355">Diese werden als "geduckte Module" bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="3c009-355">These are known as nested modules.</span></span> <span data-ttu-id="3c009-356">Dieses Cmdlet wirkt sich nur auf die Namen von Membern in der aktuellen Sitzung aus.</span><span class="sxs-lookup"><span data-stu-id="3c009-356">This cmdlet affects only the names of members in the current session.</span></span>

<span data-ttu-id="3c009-357">Wenn Sie z. b. das Präfix UTC angeben und dann ein `Get-Date` Cmdlet importieren, ist das Cmdlet in der Sitzung als bekannt `Get-UTCDate` und nicht mit dem ursprünglichen `Get-Date` Cmdlet verwechselt.</span><span class="sxs-lookup"><span data-stu-id="3c009-357">For example, if you specify the prefix UTC and then import a `Get-Date` cmdlet, the cmdlet is known in the session as `Get-UTCDate`, and it is not confused with the original `Get-Date` cmdlet.</span></span>

<span data-ttu-id="3c009-358">Der Wert dieses Parameters hat Vorrang vor der **DefaultCommandPrefix**-Eigenschaft des Moduls, die das Standardpräfix angibt.</span><span class="sxs-lookup"><span data-stu-id="3c009-358">The value of this parameter takes precedence over the **DefaultCommandPrefix** property of the module, which specifies the default prefix.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3c009-359">-PSSession</span><span class="sxs-lookup"><span data-stu-id="3c009-359">-PSSession</span></span>

<span data-ttu-id="3c009-360">Gibt eine vom Benutzer verwaltete PowerShell-Sitzung (**PSSession**) an, aus der dieses Cmdlet Module in die aktuelle Sitzung importiert.</span><span class="sxs-lookup"><span data-stu-id="3c009-360">Specifies a PowerShell user-managed session (**PSSession**) from which this cmdlet imports modules into the current session.</span></span> <span data-ttu-id="3c009-361">Geben Sie eine Variable ein, die eine **PSSession** oder einen Befehl enthält, mit dem eine **PSSession** abgerufen wird, z. b. ein- `Get-PSSession` Befehl.</span><span class="sxs-lookup"><span data-stu-id="3c009-361">Enter a variable that contains a **PSSession** or a command that gets a **PSSession**, such as a `Get-PSSession` command.</span></span>

<span data-ttu-id="3c009-362">Beim Importieren eines Moduls aus einer anderen Sitzung in die aktuelle Sitzung können Sie die Cmdlets aus dem Modul in der aktuellen Sitzung verwenden, so wie Sie Cmdlets aus einem lokalen Modul verwenden würden.</span><span class="sxs-lookup"><span data-stu-id="3c009-362">When you import a module from a different session into the current session, you can use the cmdlets from the module in the current session, just as you would use cmdlets from a local module.</span></span> <span data-ttu-id="3c009-363">Befehle, die die Remote-Cmdlets verwenden, werden in der Remote Sitzung ausgeführt, aber die remotingdetails werden von PowerShell im Hintergrund verwaltet.</span><span class="sxs-lookup"><span data-stu-id="3c009-363">Commands that use the remote cmdlets run in the remote session, but the remoting details are managed in the background by PowerShell.</span></span>

<span data-ttu-id="3c009-364">Dieser Parameter verwendet das implizite Remoting-Feature von PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3c009-364">This parameter uses the Implicit Remoting feature of PowerShell.</span></span> <span data-ttu-id="3c009-365">Dies entspricht der Verwendung des- `Import-PSSession` Cmdlets, um bestimmte Module aus einer Sitzung zu importieren.</span><span class="sxs-lookup"><span data-stu-id="3c009-365">It is equivalent to using the `Import-PSSession` cmdlet to import particular modules from a session.</span></span>

<span data-ttu-id="3c009-366">`Import-Module` PowerShell-Kernmodule können nicht aus einer anderen Sitzung importiert werden.</span><span class="sxs-lookup"><span data-stu-id="3c009-366">`Import-Module` cannot import PowerShell Core modules from another session.</span></span> <span data-ttu-id="3c009-367">Die PowerShell-Kernmodule verfügen über Namen, die mit Microsoft. PowerShell beginnen.</span><span class="sxs-lookup"><span data-stu-id="3c009-367">The PowerShell Core modules have names that begin with Microsoft.PowerShell.</span></span>

<span data-ttu-id="3c009-368">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="3c009-368">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession
Parameter Sets: PSSession, FullyQualifiedNameAndPSSession
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3c009-369">-Requirements dversion</span><span class="sxs-lookup"><span data-stu-id="3c009-369">-RequiredVersion</span></span>

<span data-ttu-id="3c009-370">Gibt eine Version des Moduls an, das von diesem Cmdlet importiert wird.</span><span class="sxs-lookup"><span data-stu-id="3c009-370">Specifies a version of the module that this cmdlet imports.</span></span> <span data-ttu-id="3c009-371">Wenn die Version nicht installiert ist, wird von `Import-Module` ein Fehler generiert.</span><span class="sxs-lookup"><span data-stu-id="3c009-371">If the version is not installed, `Import-Module` generates an error.</span></span>

<span data-ttu-id="3c009-372">Standardmäßig `Import-Module` importiert das Modul, ohne die Versionsnummer zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="3c009-372">By default, `Import-Module` imports the module without checking the version number.</span></span>

<span data-ttu-id="3c009-373">Verwenden Sie zum Angeben einer Mindestversion den **MinimumVersion**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="3c009-373">To specify a minimum version, use the **MinimumVersion** parameter.</span></span> <span data-ttu-id="3c009-374">Sie können auch die **Module** -und **Versions** Parameter des **#requires** -Schlüssel Worts verwenden, um eine bestimmte Version eines Moduls in einem Skript anzufordern.</span><span class="sxs-lookup"><span data-stu-id="3c009-374">You can also use the **Module** and **Version** parameters of the **#Requires** keyword to require a specific version of a module in a script.</span></span>

<span data-ttu-id="3c009-375">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="3c009-375">This parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="3c009-376">Skripts, die "Requirements **dversion** " zum Importieren von Modulen verwenden, die in vorhandenen Versionen des Windows-Betriebssystems enthalten sind, werden nicht automatisch in zukünftigen Versionen des Windows-Betriebssystems ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="3c009-376">Scripts that use **RequiredVersion** to import modules that are included with existing releases of the Windows operating system don't automatically run in future releases of the Windows operating system.</span></span> <span data-ttu-id="3c009-377">Dies liegt daran, dass die Versionsnummern von PowerShell-Modulen in zukünftigen Versionen des Windows-Betriebssystems höher sind als die Modul Versionsnummern in vorhandenen Versionen des Windows-Betriebssystems.</span><span class="sxs-lookup"><span data-stu-id="3c009-377">This is because PowerShell module version numbers in future releases of the Windows operating system are higher than module version numbers in existing releases of the Windows operating system.</span></span>

```yaml
Type: System.Version
Parameter Sets: Name, PSSession, CimSession
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3c009-378">-Bereich</span><span class="sxs-lookup"><span data-stu-id="3c009-378">-Scope</span></span>

<span data-ttu-id="3c009-379">Gibt einen Bereich an, in den dieses Cmdlet das Modul importiert.</span><span class="sxs-lookup"><span data-stu-id="3c009-379">Specifies a scope into which this cmdlet imports the module.</span></span>

<span data-ttu-id="3c009-380">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="3c009-380">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="3c009-381">**Global**.</span><span class="sxs-lookup"><span data-stu-id="3c009-381">**Global**.</span></span> <span data-ttu-id="3c009-382">Für alle Befehle in der Sitzung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="3c009-382">Available to all commands in the session.</span></span> <span data-ttu-id="3c009-383">Entspricht dem **Global**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="3c009-383">Equivalent to the **Global** parameter.</span></span>
- <span data-ttu-id="3c009-384">**Lokal**.</span><span class="sxs-lookup"><span data-stu-id="3c009-384">**Local**.</span></span> <span data-ttu-id="3c009-385">Nur im aktuellen Bereich verfügbar.</span><span class="sxs-lookup"><span data-stu-id="3c009-385">Available only in the current scope.</span></span>

<span data-ttu-id="3c009-386">Wenn `Import-Module` das Cmdlet von der Eingabeaufforderung, von der Skriptdatei oder von ScriptBlock aufgerufen wird, werden standardmäßig alle Befehle in den globalen Sitzungszustand importiert.</span><span class="sxs-lookup"><span data-stu-id="3c009-386">By default, when `Import-Module` cmdlet is called from the command prompt, script file, or scriptblock, all the commands are imported into the global session state.</span></span> <span data-ttu-id="3c009-387">Sie können den- `-Scope Local` Parameter verwenden, um Modul Inhalt in das Skript oder den ScriptBlock-Bereich zu importieren.</span><span class="sxs-lookup"><span data-stu-id="3c009-387">You can use the `-Scope Local` parameter to import module content into the script or scriptblock scope.</span></span>

<span data-ttu-id="3c009-388">Wenn Sie von einem anderen Modul aufgerufen wird, `Import-Module` importiert das Cmdlet die Befehle in einem Modul, einschließlich der Befehle aus den in einem Modul vorgerufenen Modulen, in den Sitzungszustand des Aufrufers</span><span class="sxs-lookup"><span data-stu-id="3c009-388">When invoked from another module, `Import-Module` cmdlet imports the commands in a module, including commands from nested modules, into the caller's session state.</span></span> <span data-ttu-id="3c009-389">Durch `-Scope Global` angeben `-Global` von oder wird angegeben, dass dieses Cmdlet Module in den globalen Sitzungszustand importiert, sodass Sie für alle Befehle in der Sitzung verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="3c009-389">Specifying `-Scope Global` or `-Global` indicates that this cmdlet imports modules into the global session state so they are available to all commands in the session.</span></span>

<span data-ttu-id="3c009-390">Der **Global**-Parameter entspricht dem **Scope**-Parameter mit dem Wert **Global**.</span><span class="sxs-lookup"><span data-stu-id="3c009-390">The **Global** parameter is equivalent to the **Scope** parameter with a value of **Global**.</span></span>

<span data-ttu-id="3c009-391">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="3c009-391">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Local, Global

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3c009-392">-Variable</span><span class="sxs-lookup"><span data-stu-id="3c009-392">-Variable</span></span>

<span data-ttu-id="3c009-393">Gibt ein Array von Variablen an, die von diesem Cmdlet aus dem Modul in die aktuelle Sitzung importiert werden.</span><span class="sxs-lookup"><span data-stu-id="3c009-393">Specifies an array of variables that this cmdlet imports from the module into the current session.</span></span>
<span data-ttu-id="3c009-394">Geben Sie eine Liste der Variablen ein.</span><span class="sxs-lookup"><span data-stu-id="3c009-394">Enter a list of variables.</span></span> <span data-ttu-id="3c009-395">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="3c009-395">Wildcard characters are permitted.</span></span>

<span data-ttu-id="3c009-396">Einige Module exportieren automatisch ausgewählte Variablen in Ihre Sitzung, wenn Sie das Modul importieren.</span><span class="sxs-lookup"><span data-stu-id="3c009-396">Some modules automatically export selected variables into your session when you import the module.</span></span>
<span data-ttu-id="3c009-397">Mit diesem Parameter können Sie eine Auswahl aus den exportierten Variablen treffen.</span><span class="sxs-lookup"><span data-stu-id="3c009-397">This parameter lets you select from among the exported variables.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="3c009-398">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="3c009-398">CommonParameters</span></span>
<span data-ttu-id="3c009-399">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3c009-399">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3c009-400">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="3c009-400">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3c009-401">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="3c009-401">INPUTS</span></span>

### <span data-ttu-id="3c009-402">System. String, System. Management. Automation. psmoduleinfo, System. Reflection. Assembly</span><span class="sxs-lookup"><span data-stu-id="3c009-402">System.String, System.Management.Automation.PSModuleInfo, System.Reflection.Assembly</span></span>

<span data-ttu-id="3c009-403">Sie können einen Modulnamen, ein Modul Objekt oder ein Assemblyobjekt über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="3c009-403">You can pipe a module name, module object, or assembly object to this cmdlet.</span></span>

## <span data-ttu-id="3c009-404">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="3c009-404">OUTPUTS</span></span>

### <span data-ttu-id="3c009-405">"None", "System. Management. Automation. psmoduleinfo" oder "System. Management. Automation. pscustomobject"</span><span class="sxs-lookup"><span data-stu-id="3c009-405">None, System.Management.Automation.PSModuleInfo, or System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="3c009-406">Standardmäßig `Import-Module` generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="3c009-406">By default, `Import-Module` does not generate any output.</span></span> <span data-ttu-id="3c009-407">Wenn Sie den **passthru** -Parameter angeben, generiert das Cmdlet ein **System. Management. Automation. psmoduleinfo** -Objekt, das das Modul darstellt.</span><span class="sxs-lookup"><span data-stu-id="3c009-407">If you specify the **PassThru** parameter, the cmdlet generates a **System.Management.Automation.PSModuleInfo** object that represents the module.</span></span> <span data-ttu-id="3c009-408">Wenn Sie den **ascustomobject** -Parameter angeben, generiert er ein **pscustomobject** -Objekt.</span><span class="sxs-lookup"><span data-stu-id="3c009-408">If you specify the **AsCustomObject** parameter, it generates a **PSCustomObject** object.</span></span>

## <span data-ttu-id="3c009-409">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="3c009-409">NOTES</span></span>

- <span data-ttu-id="3c009-410">Bevor Sie ein Modul importieren können, muss das Modul auf dem lokalen Computer installiert sein.</span><span class="sxs-lookup"><span data-stu-id="3c009-410">Before you can import a module, the module must be installed on the local computer.</span></span> <span data-ttu-id="3c009-411">Das heißt, das Modul Verzeichnis muss in ein Verzeichnis kopiert werden, auf das der lokale Computer zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="3c009-411">That is, the module directory must be copied to a directory that is accessible to your local computer.</span></span> <span data-ttu-id="3c009-412">Weitere Informationen finden Sie unter [about_Modules](About/about_Modules.md).</span><span class="sxs-lookup"><span data-stu-id="3c009-412">For more information, see [about_Modules](About/about_Modules.md).</span></span>

  <span data-ttu-id="3c009-413">Sie können auch die Parameter **PSSession** und **CIMSession** verwenden, um Module zu importieren, die auf Remotecomputern installiert sind.</span><span class="sxs-lookup"><span data-stu-id="3c009-413">You can also use the **PSSession** and **CIMSession** parameters to import modules that are installed on remote computers.</span></span> <span data-ttu-id="3c009-414">Befehle, die die Cmdlets in diesen Modulen verwenden, werden jedoch in der Remote Sitzung auf dem Remote Computer ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="3c009-414">However, commands that use the cmdlets in these modules run in the remote session on the remote computer.</span></span>

- <span data-ttu-id="3c009-415">Wenn Sie Member mit demselben Namen und demselben Typ in die Sitzung importieren, verwendet PowerShell den zuletzt importierten Member standardmäßig.</span><span class="sxs-lookup"><span data-stu-id="3c009-415">If you import members with the same name and the same type into your session, PowerShell uses the member imported last by default.</span></span> <span data-ttu-id="3c009-416">Variablen und Aliase werden ersetzt, und die Originale sind nicht zugänglich.</span><span class="sxs-lookup"><span data-stu-id="3c009-416">Variables and aliases are replaced, and the originals aren't accessible.</span></span> <span data-ttu-id="3c009-417">Funktionen, Cmdlets und Anbieter werden lediglich von den neuen Membern schattiert.</span><span class="sxs-lookup"><span data-stu-id="3c009-417">Functions, cmdlets, and providers are merely shadowed by the new members.</span></span> <span data-ttu-id="3c009-418">Sie können darauf zugreifen, indem Sie den Befehlsnamen mit dem Namen seines Snap-Ins, Moduls oder Funktions Pfads qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="3c009-418">They can be accessed by qualifying the command name with the name of its snap-in, module, or function path.</span></span>

- <span data-ttu-id="3c009-419">Verwenden Sie das-Cmdlet, um die Formatierungsdaten für Befehle zu aktualisieren, die aus einem Modul importiert wurden `Update-FormatData` .</span><span class="sxs-lookup"><span data-stu-id="3c009-419">To update the formatting data for commands that have been imported from a module, use the `Update-FormatData` cmdlet.</span></span> <span data-ttu-id="3c009-420">`Update-FormatData` aktualisiert auch die Formatierungsdaten für Befehle in der Sitzung, die aus Modulen importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="3c009-420">`Update-FormatData` also updates the formatting data for commands in the session that were imported from modules.</span></span> <span data-ttu-id="3c009-421">Wenn die Formatierungs Datei für ein Modul geändert wird, können Sie einen Befehl ausführen, `Update-FormatData` um die Formatierungsdaten für importierte Befehle zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="3c009-421">If the formatting file for a module changes, you can run an `Update-FormatData` command to update the formatting data for imported commands.</span></span> <span data-ttu-id="3c009-422">Sie müssen das Modul nicht erneut importieren.</span><span class="sxs-lookup"><span data-stu-id="3c009-422">You don't need to import the module again.</span></span>

- <span data-ttu-id="3c009-423">Ab Windows PowerShell 3,0 werden die mit PowerShell installierten Hauptbefehle in Module gepackt.</span><span class="sxs-lookup"><span data-stu-id="3c009-423">Starting in Windows PowerShell 3.0, the core commands that are installed with PowerShell are packaged in modules.</span></span> <span data-ttu-id="3c009-424">In Windows PowerShell 2,0 und in Host Programmen, die in neueren Versionen von PowerShell ältere Sitzungen erstellen, werden die Hauptbefehle in Snap-Ins (**pssnapins**) gepackt.</span><span class="sxs-lookup"><span data-stu-id="3c009-424">In Windows PowerShell 2.0, and in host programs that create older-style sessions in later versions of PowerShell, the core commands are packaged in snap-ins (**PSSnapins**).</span></span> <span data-ttu-id="3c009-425">Die Ausnahme ist **Microsoft. PowerShell. Core**, bei der es sich immer um ein Snap-in handelt.</span><span class="sxs-lookup"><span data-stu-id="3c009-425">The exception is **Microsoft.PowerShell.Core**, which is always a snap-in.</span></span> <span data-ttu-id="3c009-426">Remote Sitzungen, wie z. b. die vom `New-PSSession` Cmdlet gestarteten, sind auch ältere Sitzungen, die Core-Snap-Ins enthalten.</span><span class="sxs-lookup"><span data-stu-id="3c009-426">Also, remote sessions, such as those started by the `New-PSSession` cmdlet, are older-style sessions that include core snap-ins.</span></span>

  <span data-ttu-id="3c009-427">Weitere Informationen über die **CreateDefault2** -Methode, die Sitzungen im neueren Stil mit Kernmodulen erstellt, finden Sie unter der [CreateDefault2-Methode](/dotnet/api/system.management.automation.runspaces.initialsessionstate.createdefault2).</span><span class="sxs-lookup"><span data-stu-id="3c009-427">For information about the **CreateDefault2** method that creates newer-style sessions with core modules, see the [CreateDefault2 Method](/dotnet/api/system.management.automation.runspaces.initialsessionstate.createdefault2).</span></span>

- <span data-ttu-id="3c009-428">In Windows PowerShell 2,0 wurden einige der Eigenschaftswerte des Modul Objekts, z. b. die Eigenschaften Werte **exportedcmdlets** und **netstedmodules** , erst aufgefüllt, wenn das Modul importiert wurde.</span><span class="sxs-lookup"><span data-stu-id="3c009-428">In Windows PowerShell 2.0, some of the property values of the module object, such as the **ExportedCmdlets** and **NestedModules** property values, were not populated until the module was imported.</span></span>

- <span data-ttu-id="3c009-429">Wenn Sie versuchen, ein Modul zu importieren, das Assemblys im gemischten Modus enthält, die nicht mit Windows PowerShell 3.0 + kompatibel sind, wird `Import-Module` eine Fehlermeldung wie die folgende zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3c009-429">If you attempt to import a module that contains mixed-mode assemblies that aren't compatible with Windows PowerShell 3.0+, `Import-Module` returns an error message like the following one.</span></span>

  > <span data-ttu-id="3c009-430">Import-Module: die Assembly im gemischten Modus wird für die Version "v 2.0.50727" der Laufzeit erstellt und kann nicht ohne zusätzliche Konfigurationsinformationen in der Laufzeitumgebung von 4,0 geladen werden.</span><span class="sxs-lookup"><span data-stu-id="3c009-430">Import-Module : Mixed mode assembly is built against version 'v2.0.50727' of the runtime and cannot be loaded in the 4.0 runtime without additional configuration information.</span></span>

  <span data-ttu-id="3c009-431">Dieser Fehler tritt auf, wenn ein Modul, das für Windows PowerShell 2,0 entworfen wurde, mindestens eine Assembly mit gemischtem Modul enthält.</span><span class="sxs-lookup"><span data-stu-id="3c009-431">This error occurs when a module that is designed for Windows PowerShell 2.0 contains at least one mixed-module assembly.</span></span> <span data-ttu-id="3c009-432">Eine Assembly mit gemischtem Modul, die sowohl verwalteten als auch nicht verwalteten Code umfasst, z. b. C++ und c#.</span><span class="sxs-lookup"><span data-stu-id="3c009-432">A mixed-module assembly that includes both managed and non-managed code, such as C++ and C#.</span></span>

  <span data-ttu-id="3c009-433">Zum Importieren eines Moduls, das Assemblys im gemischten Modus enthält, starten Sie Windows PowerShell 2,0 mit dem folgenden Befehl, und `Import-Module` Wiederholen Sie dann den Befehl.</span><span class="sxs-lookup"><span data-stu-id="3c009-433">To import a module that contains mixed-mode assemblies, start Windows PowerShell 2.0 by using the following command, and then try the `Import-Module` command again.</span></span>

  `PowerShell.exe -Version 2.0`

- <span data-ttu-id="3c009-434">Um die CIM-Sitzung zu verwenden, müssen auf dem Remotecomputer WS-Management-Remoting und Windows-Verwaltungsinstrumentation (WMI) verfügbar sein, wobei es sich um die Microsoft-Implementierung des Common Information Model (CIM)-Standards handelt.</span><span class="sxs-lookup"><span data-stu-id="3c009-434">To use the CIM session feature, the remote computer must have WS-Management remoting and Windows Management Instrumentation (WMI), which is the Microsoft implementation of the Common Information Model (CIM) standard.</span></span> <span data-ttu-id="3c009-435">Der Computer muss auch den WMI-Anbieter für die Modulerkennung oder einen anderen CIM-Anbieter haben, der die gleichen grundlegenden Funktionen hat.</span><span class="sxs-lookup"><span data-stu-id="3c009-435">The computer must also have the Module Discovery WMI provider or an alternate CIM provider that has the same basic features.</span></span>

  <span data-ttu-id="3c009-436">Sie können die CIM-Sitzungs Funktion auf Computern verwenden, auf denen kein Windows-Betriebssystem ausgeführt wird, sowie auf Windows-Computern mit PowerShell, auf denen PowerShell-Remoting nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="3c009-436">You can use the CIM session feature on computers that aren't running a Windows operating system and on Windows computers that have PowerShell, but don't have PowerShell remoting enabled.</span></span>

  <span data-ttu-id="3c009-437">Sie können auch die CIM-Parameter verwenden, um CIM-Module von Computern zu erhalten, auf denen PowerShell-Remoting aktiviert ist, einschließlich des lokalen Computers.</span><span class="sxs-lookup"><span data-stu-id="3c009-437">You can also use the CIM parameters to get CIM modules from computers that have PowerShell remoting enabled, including the local computer.</span></span> <span data-ttu-id="3c009-438">Wenn Sie eine CIM-Sitzung auf dem lokalen Computer erstellen, verwendet PowerShell DCOM anstelle von WMI, um die Sitzung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3c009-438">When you create a CIM session on the local computer, PowerShell uses DCOM, instead of WMI, to create the session.</span></span>

- <span data-ttu-id="3c009-439">Standardmäßig `Import-Module` importiert Module in den globalen Gültigkeitsbereich, auch wenn Sie von einem Nachfolger Bereich aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="3c009-439">By default, `Import-Module` imports modules in the global scope even when called from a descendant scope.</span></span> <span data-ttu-id="3c009-440">Der Bereich der obersten Ebene und alle untergeordneten Bereiche haben Zugriff auf die exportierten Elemente des Moduls.</span><span class="sxs-lookup"><span data-stu-id="3c009-440">The top-level scope and all descendant scopes have access to the module's exported elements.</span></span>

  <span data-ttu-id="3c009-441">In einem Nachfolger Bereich `-Scope Local` beschränkt den Import auf diesen Bereich und alle untergeordneten Bereiche.</span><span class="sxs-lookup"><span data-stu-id="3c009-441">In a descendant scope, `-Scope Local` limits the import to that scope and all its descendant scopes.</span></span> <span data-ttu-id="3c009-442">Übergeordnete Bereiche werden dann die importierten Member nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3c009-442">Parent scopes then do not see the imported members.</span></span>

  > [!NOTE]
  > <span data-ttu-id="3c009-443">`Get-Module` zeigt alle in der aktuellen Sitzung geladenen Module an.</span><span class="sxs-lookup"><span data-stu-id="3c009-443">`Get-Module` shows all modules loaded in the current session.</span></span> <span data-ttu-id="3c009-444">Dies schließt Module ein, die lokal in einem Nachfolger Bereich geladen werden.</span><span class="sxs-lookup"><span data-stu-id="3c009-444">This includes modules loaded locally in a descendant scope.</span></span> <span data-ttu-id="3c009-445">Verwenden `Get-Command -Module modulename` Sie, um anzuzeigen, welche Member im aktuellen Bereich geladen werden.</span><span class="sxs-lookup"><span data-stu-id="3c009-445">Use `Get-Command -Module modulename` to see which members are loaded in the current scope.</span></span>

  <span data-ttu-id="3c009-446">`Import-Module` lädt keine Klassen-und Enumerationsdefinitionen im Modul.</span><span class="sxs-lookup"><span data-stu-id="3c009-446">`Import-Module` does not load class and enum definitions in the module.</span></span> <span data-ttu-id="3c009-447">Verwenden Sie die- `using module` Anweisung am Anfang des Skripts.</span><span class="sxs-lookup"><span data-stu-id="3c009-447">Use the `using module` statement at the beginning of your script.</span></span> <span data-ttu-id="3c009-448">Dadurch wird das Modul importiert, einschließlich der Klassen-und Enumerationsdefinitionen.</span><span class="sxs-lookup"><span data-stu-id="3c009-448">This imports the module, including the class and enum definitions.</span></span> <span data-ttu-id="3c009-449">Weitere Informationen finden Sie unter [about_Using](About/about_Using.md).</span><span class="sxs-lookup"><span data-stu-id="3c009-449">For more information, see [about_Using](About/about_Using.md).</span></span>

## <span data-ttu-id="3c009-450">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="3c009-450">RELATED LINKS</span></span>

[<span data-ttu-id="3c009-451">about_Modules</span><span class="sxs-lookup"><span data-stu-id="3c009-451">about_Modules</span></span>](about/about_Modules.md)

[<span data-ttu-id="3c009-452">Export-ModuleMember</span><span class="sxs-lookup"><span data-stu-id="3c009-452">Export-ModuleMember</span></span>](Export-ModuleMember.md)

[<span data-ttu-id="3c009-453">Get-Module</span><span class="sxs-lookup"><span data-stu-id="3c009-453">Get-Module</span></span>](Get-Module.md)

[<span data-ttu-id="3c009-454">New-Module</span><span class="sxs-lookup"><span data-stu-id="3c009-454">New-Module</span></span>](New-Module.md)

[<span data-ttu-id="3c009-455">Remove-Module</span><span class="sxs-lookup"><span data-stu-id="3c009-455">Remove-Module</span></span>](Remove-Module.md)
