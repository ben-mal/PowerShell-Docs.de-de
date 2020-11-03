---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 12/14/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-command?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Command
ms.openlocfilehash: 12cf373e5e53a45f7cdadd5e3a9f3fec7a7a8bb8
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93211324"
---
# <span data-ttu-id="68cf8-103">Get-Command</span><span class="sxs-lookup"><span data-stu-id="68cf8-103">Get-Command</span></span>

## <span data-ttu-id="68cf8-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="68cf8-104">SYNOPSIS</span></span>
<span data-ttu-id="68cf8-105">Ruft alle Befehle ab.</span><span class="sxs-lookup"><span data-stu-id="68cf8-105">Gets all commands.</span></span>

## <span data-ttu-id="68cf8-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="68cf8-106">SYNTAX</span></span>

### <span data-ttu-id="68cf8-107">CmdletSet (Standard)</span><span class="sxs-lookup"><span data-stu-id="68cf8-107">CmdletSet (Default)</span></span>

```
Get-Command [-Verb <String[]>] [-Noun <String[]>] [-Module <String[]>]
 [-FullyQualifiedModule <ModuleSpecification[]>] [-TotalCount <Int32>] [-Syntax] [-ShowCommandInfo]
 [[-ArgumentList] <Object[]>] [-All] [-ListImported] [-ParameterName <String[]>]
 [-ParameterType <PSTypeName[]>] [<CommonParameters>]
```

### <span data-ttu-id="68cf8-108">Allcommandset</span><span class="sxs-lookup"><span data-stu-id="68cf8-108">AllCommandSet</span></span>

```
Get-Command [[-Name] <String[]>] [-Module <String[]>]
 [-FullyQualifiedModule <ModuleSpecification[]>] [-CommandType <CommandTypes>] [-TotalCount <Int32>]
 [-Syntax] [-ShowCommandInfo] [[-ArgumentList] <Object[]>] [-All] [-ListImported]
 [-ParameterName <String[]>] [-ParameterType <PSTypeName[]>] [-UseFuzzyMatching]
 [-UseAbbreviationExpansion] [<CommonParameters>]
```

## <span data-ttu-id="68cf8-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="68cf8-109">DESCRIPTION</span></span>

<span data-ttu-id="68cf8-110">Das- `Get-Command` Cmdlet ruft alle Befehle ab, die auf dem Computer installiert sind, einschließlich Cmdlets, Aliase, Funktionen, Filter, Skripts und Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="68cf8-110">The `Get-Command` cmdlet gets all commands that are installed on the computer, including cmdlets, aliases, functions, filters, scripts, and applications.</span></span> <span data-ttu-id="68cf8-111">`Get-Command` Ruft die Befehle aus PowerShell-Modulen und-Befehlen ab, die aus anderen Sitzungen importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="68cf8-111">`Get-Command` gets the commands from PowerShell modules and commands that were imported from other sessions.</span></span> <span data-ttu-id="68cf8-112">Um nur die Befehle zu erhalten, die in die aktuelle Sitzung importiert wurden, verwenden Sie den **ListImported** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="68cf8-112">To get only commands that have been imported into the current session, use the **ListImported** parameter.</span></span>

<span data-ttu-id="68cf8-113">Ohne Parameter `Get-Command` Ruft alle-Cmdlets,-Funktionen und-Aliase ab, die auf dem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="68cf8-113">Without parameters, `Get-Command` gets all of the cmdlets, functions, and aliases installed on the computer.</span></span> <span data-ttu-id="68cf8-114">`Get-Command *` Ruft alle Befehls Typen ab, einschließlich aller nicht-PowerShell-Dateien in der PATH-Umgebungsvariablen ( `$env:Path` ), die Sie im Anwendungs Befehlstyp auflistet.</span><span class="sxs-lookup"><span data-stu-id="68cf8-114">`Get-Command *` gets all types of commands, including all of the non-PowerShell files in the Path environment variable (`$env:Path`), which it lists in the Application command type.</span></span>

<span data-ttu-id="68cf8-115">`Get-Command` der den genauen Namen des Befehls ohne Platzhalter Zeichen verwendet, importiert automatisch das Modul, das den Befehl enthält, sodass Sie den Befehl sofort verwenden können.</span><span class="sxs-lookup"><span data-stu-id="68cf8-115">`Get-Command` that uses the exact name of the command, without wildcard characters, automatically imports the module that contains the command so that you can use the command immediately.</span></span> <span data-ttu-id="68cf8-116">Verwenden Sie die Preference-Variable, um das automatische Importieren von Modulen zu aktivieren, zu deaktivieren und zu konfigurieren `$PSModuleAutoLoadingPreference` .</span><span class="sxs-lookup"><span data-stu-id="68cf8-116">To enable, disable, and configure automatic importing of modules, use the `$PSModuleAutoLoadingPreference` preference variable.</span></span> <span data-ttu-id="68cf8-117">Weitere Informationen finden Sie unter [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="68cf8-117">For more information, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="68cf8-118">`Get-Command` Ruft die zugehörigen Daten direkt aus dem Befehls Code ab, wobei `Get-Help` die Informationen aus Hilfe Themen abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="68cf8-118">`Get-Command` gets its data directly from the command code, unlike `Get-Help`, which gets its information from help topics.</span></span>

<span data-ttu-id="68cf8-119">Ab Windows PowerShell 5,0 zeigen die Ergebnisse des `Get-Command` Cmdlets standardmäßig eine **Versions** Spalte an.</span><span class="sxs-lookup"><span data-stu-id="68cf8-119">Starting in Windows PowerShell 5.0, results of the `Get-Command` cmdlet display a **Version** column by default.</span></span> <span data-ttu-id="68cf8-120">Der **CommandInfo** -Klasse wurde eine neue **Versions** Eigenschaft hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="68cf8-120">A new **Version** property has been added to the **CommandInfo** class.</span></span>

## <span data-ttu-id="68cf8-121">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="68cf8-121">EXAMPLES</span></span>

### <span data-ttu-id="68cf8-122">Beispiel 1: Cmdlets, Funktionen und Aliase</span><span class="sxs-lookup"><span data-stu-id="68cf8-122">Example 1: Get cmdlets, functions, and aliases</span></span>

<span data-ttu-id="68cf8-123">Mit diesem Befehl werden die auf dem Computer installierten PowerShell-Cmdlets,-Funktionen und-Aliase abgerufen.</span><span class="sxs-lookup"><span data-stu-id="68cf8-123">This command gets the PowerShell cmdlets, functions, and aliases that are installed on the computer.</span></span>

```powershell
Get-Command
```

### <span data-ttu-id="68cf8-124">Beispiel 2: Get-Befehle in der aktuellen Sitzung</span><span class="sxs-lookup"><span data-stu-id="68cf8-124">Example 2: Get commands in the current session</span></span>

<span data-ttu-id="68cf8-125">Dieser Befehl verwendet den **ListImported** -Parameter, um nur die Befehle in der aktuellen Sitzung abzurufen.</span><span class="sxs-lookup"><span data-stu-id="68cf8-125">This command uses the **ListImported** parameter to get only the commands in the current session.</span></span>

```powershell
Get-Command -ListImported
```

### <span data-ttu-id="68cf8-126">Beispiel 3: Cmdlets erhalten und in der richtigen Reihenfolge angezeigt</span><span class="sxs-lookup"><span data-stu-id="68cf8-126">Example 3: Get cmdlets and display them in order</span></span>

<span data-ttu-id="68cf8-127">Dieser Befehl ruft alle Cmdlets ab, sortiert sie alphabetisch nach dem Nomen im Cmdlet-Namen und zeigt sie dann in nomenbasierten Gruppen an.</span><span class="sxs-lookup"><span data-stu-id="68cf8-127">This command gets all of the cmdlets, sorts them alphabetically by the noun in the cmdlet name, and then displays them in noun-based groups.</span></span> <span data-ttu-id="68cf8-128">Diese Anzeige hilft Ihnen dabei, die Cmdlets für eine Aufgabe zu finden.</span><span class="sxs-lookup"><span data-stu-id="68cf8-128">This display can help you find the cmdlets for a task.</span></span>

```powershell
Get-Command -Type Cmdlet | Sort-Object -Property Noun | Format-Table -GroupBy Noun
```

### <span data-ttu-id="68cf8-129">Beispiel 4: Get-Befehle in einem Modul</span><span class="sxs-lookup"><span data-stu-id="68cf8-129">Example 4: Get commands in a module</span></span>

<span data-ttu-id="68cf8-130">Dieser Befehl verwendet den **Module** -Parameter, um die Befehle in den Modulen "Microsoft. PowerShell. Security" und "Microsoft. PowerShell. Utility" zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="68cf8-130">This command uses the **Module** parameter to get the commands in the Microsoft.PowerShell.Security and Microsoft.PowerShell.Utility modules.</span></span>

```powershell
Get-Command -Module Microsoft.PowerShell.Security, Microsoft.PowerShell.Utility
```

### <span data-ttu-id="68cf8-131">Beispiel 5: erhalten von Informationen zu einem Cmdlet</span><span class="sxs-lookup"><span data-stu-id="68cf8-131">Example 5: Get information about a cmdlet</span></span>

<span data-ttu-id="68cf8-132">Dieser Befehl ruft Informationen über das `Get-AppLockerPolicy` Cmdlet ab.</span><span class="sxs-lookup"><span data-stu-id="68cf8-132">This command gets information about the `Get-AppLockerPolicy` cmdlet.</span></span> <span data-ttu-id="68cf8-133">Der Befehl importiert auch das **AppLocker** -Modul, das alle Befehle im **AppLocker** -Modul zur aktuellen Sitzung hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="68cf8-133">It also imports the **AppLocker** module, which adds all of the commands in the **AppLocker** module to the current session.</span></span>

```powershell
Get-Command Get-AppLockerPolicy
```

<span data-ttu-id="68cf8-134">Wenn ein Modul automatisch importiert wird, entspricht der Effekt dem Verwenden des Import-Module-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="68cf8-134">When a module is imported automatically, the effect is the same as using the Import-Module cmdlet.</span></span>
<span data-ttu-id="68cf8-135">Das Modul kann Befehle, Typen und Formatierungsdateien hinzufügen und Skripts in der Sitzung ausführen.</span><span class="sxs-lookup"><span data-stu-id="68cf8-135">The module can add commands, types and formatting files, and run scripts in the session.</span></span> <span data-ttu-id="68cf8-136">Verwenden Sie die Preference-Variable, um das automatische Importieren von Modulen zu aktivieren, zu deaktivieren und zu konfigurieren `$PSModuleAutoLoadingPreference` .</span><span class="sxs-lookup"><span data-stu-id="68cf8-136">To enable, disable, and configuration automatic importing of modules, use the `$PSModuleAutoLoadingPreference` preference variable.</span></span> <span data-ttu-id="68cf8-137">Weitere Informationen finden Sie unter [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="68cf8-137">For more information, see [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

### <span data-ttu-id="68cf8-138">Beispiel 6: erhalten der Syntax eines Cmdlets</span><span class="sxs-lookup"><span data-stu-id="68cf8-138">Example 6: Get the syntax of a cmdlet</span></span>

<span data-ttu-id="68cf8-139">Dieser Befehl verwendet den Argument **List** -Parameter und den **Syntax** Parameter, um die Syntax des Cmdlets zu erhalten, `Get-ChildItem` Wenn es im CERT:-Laufwerk verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="68cf8-139">This command uses the **ArgumentList** and **Syntax** parameters to get the syntax of the `Get-ChildItem` cmdlet when it is used in the Cert: drive.</span></span> <span data-ttu-id="68cf8-140">Das Laufwerk "CERT:" ist ein PowerShell-Laufwerk, das der Zertifikat Anbieter der Sitzung hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="68cf8-140">The Cert: drive is a PowerShell drive that the Certificate Provider adds to the session.</span></span>

```powershell
Get-Command Get-Childitem -Args Cert: -Syntax
```

<span data-ttu-id="68cf8-141">Wenn Sie die in der Ausgabe angezeigte Syntax mit der Syntax vergleichen, die angezeigt wird, wenn Sie den **args** -Parameter (Argument **List** ) weglassen, sehen Sie, dass der **Zertifikat Anbieter** dem Cmdlet einen dynamischen Parameter, **codeSigningCert** , hinzufügt `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="68cf8-141">When you compare the syntax displayed in the output with the syntax that is displayed when you omit the **Args** ( **ArgumentList** ) parameter, you'll see that the **Certificate provider** adds a dynamic parameter, **CodeSigningCert** , to the `Get-ChildItem` cmdlet.</span></span>

<span data-ttu-id="68cf8-142">Weitere Informationen zum Zertifikat Anbieter finden Sie unter [about_Certificate_Provider](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md).</span><span class="sxs-lookup"><span data-stu-id="68cf8-142">For more information about the Certificate provider, see [about_Certificate_Provider](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md).</span></span>

### <span data-ttu-id="68cf8-143">Beispiel 7: Get Dynamic Parameters</span><span class="sxs-lookup"><span data-stu-id="68cf8-143">Example 7: Get dynamic parameters</span></span>

<span data-ttu-id="68cf8-144">Der Befehl im Beispiel verwendet die- `Get-DynamicParameters` Funktion, um die dynamischen Parameter zu erhalten, die der Zertifikat Anbieter dem `Get-ChildItem` Cmdlet hinzufügt, wenn er im CERT:-Laufwerk verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="68cf8-144">The command in the example uses the `Get-DynamicParameters` function to get the dynamic parameters that the Certificate provider adds to the `Get-ChildItem` cmdlet when it is used in the Cert: drive.</span></span>

```powershell
function Get-DynamicParameters
{
    param ($Cmdlet, $PSDrive)
    (Get-Command $Cmdlet -ArgumentList $PSDrive).ParameterSets | ForEach-Object {$_.Parameters} | Where-Object { $_.IsDynamic } | Select-Object -Property Name -Unique
}
Get-DynamicParameters -Cmdlet Get-ChildItem -PSDrive Cert:
```

```Output
Name
----
CodeSigningCert
```

<span data-ttu-id="68cf8-145">Die- `Get-DynamicParameters` Funktion in diesem Beispiel ruft die dynamischen Parameter eines Cmdlets ab.</span><span class="sxs-lookup"><span data-stu-id="68cf8-145">The `Get-DynamicParameters` function in this example gets the dynamic parameters of a cmdlet.</span></span> <span data-ttu-id="68cf8-146">Dies ist eine Alternative zu der Methode, die im vorherigen Beispiel verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="68cf8-146">This is an alternative to the method used in the previous example.</span></span> <span data-ttu-id="68cf8-147">Der dynamische Parameter kann durch andere Cmdlets oder einen Anbieter zu einem Cmdlet hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="68cf8-147">Dynamic parameter can be added to a cmdlet by another cmdlet or a provider.</span></span>

### <span data-ttu-id="68cf8-148">Beispiel 8: alle Befehle aller Typen erhalten</span><span class="sxs-lookup"><span data-stu-id="68cf8-148">Example 8: Get all commands of all types</span></span>

<span data-ttu-id="68cf8-149">Mit diesem Befehl werden alle Befehle aller Typen auf dem lokalen Computer abgerufen, einschließlich der ausführbaren Dateien in den Pfaden der **path** -Umgebungsvariablen ( `$env:path` ).</span><span class="sxs-lookup"><span data-stu-id="68cf8-149">This command gets all commands of all types on the local computer, including executable files in the paths of the **Path** environment variable (`$env:path`).</span></span>

```powershell
Get-Command *
```

<span data-ttu-id="68cf8-150">Der Befehl gibt ein **ApplicationInfo** -Objekt (System.Management.Automation.ApplicationInfo) für jede Datei und kein **FileInfo** -Objekt (System.IO.FileInfo) zurück.</span><span class="sxs-lookup"><span data-stu-id="68cf8-150">It returns an **ApplicationInfo** object (System.Management.Automation.ApplicationInfo) for each file, not a **FileInfo** object (System.IO.FileInfo).</span></span>

### <span data-ttu-id="68cf8-151">Beispiel 9: Cmdlets mithilfe eines Parameter namens und-Typs</span><span class="sxs-lookup"><span data-stu-id="68cf8-151">Example 9: Get cmdlets by using a parameter name and type</span></span>

<span data-ttu-id="68cf8-152">Dieser Befehl ruft Cmdlets ab, die über einen Parameter verfügen, dessen Name "auth" und dessen Typ " **authenticationmechanism** " ist.</span><span class="sxs-lookup"><span data-stu-id="68cf8-152">This command gets cmdlets that have a parameter whose name includes Auth and whose type is **AuthenticationMechanism** .</span></span>

```powershell
Get-Command -ParameterName *Auth* -ParameterType AuthenticationMechanism
```

<span data-ttu-id="68cf8-153">Verwenden Sie Befehle wie diesen, um nach Cmdlets zu suchen, mit denen Sie die Methode angeben können, die zum Authentifizieren des Benutzers verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="68cf8-153">You can use a command like this one to find cmdlets that let you specify the method that is used to authenticate the user.</span></span>

<span data-ttu-id="68cf8-154">Der **ParameterType** -Parameter unterscheidet Parameter, die einen **AuthenticationMechanism** -Wert akzeptieren, von Parametern, die einen **AuthenticationLevel** -Wert akzeptieren, selbst wenn sie ähnliche Namen haben.</span><span class="sxs-lookup"><span data-stu-id="68cf8-154">The **ParameterType** parameter distinguishes parameters that take an **AuthenticationMechanism** value from those that take an **AuthenticationLevel** parameter, even when they have similar names.</span></span>

### <span data-ttu-id="68cf8-155">Beispiel 10: Holen Sie sich einen Alias</span><span class="sxs-lookup"><span data-stu-id="68cf8-155">Example 10: Get an alias</span></span>

<span data-ttu-id="68cf8-156">In diesem Beispiel wird gezeigt, wie das `Get-Command` Cmdlet mit einem Alias verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="68cf8-156">This example shows how to use the `Get-Command` cmdlet with an alias.</span></span>

```powershell
Get-Command dir
```

```Output
CommandType     Name                                               ModuleName
-----------     ----                                               ----------
Alias           dir -> Get-ChildItem
```

<span data-ttu-id="68cf8-157">Obwohl es in der Regel für Cmdlets und Funktionen verwendet wird, ruft `Get-Command` auch Skripts, Funktionen, Aliase und ausführbare Dateien ab.</span><span class="sxs-lookup"><span data-stu-id="68cf8-157">Although it is typically used on cmdlets and functions, `Get-Command` also gets scripts, functions, aliases, and executable files.</span></span>

<span data-ttu-id="68cf8-158">Die Befehlsausgabe zeigt die Ansicht des **Name** -Eigenschaftswerts für Aliase.</span><span class="sxs-lookup"><span data-stu-id="68cf8-158">The output of the command shows the special view of the **Name** property value for aliases.</span></span> <span data-ttu-id="68cf8-159">Die Ansicht zeigt den Alias und den vollständigen Befehlsnamen.</span><span class="sxs-lookup"><span data-stu-id="68cf8-159">The view shows the alias and the full command name.</span></span>

### <span data-ttu-id="68cf8-160">Beispiel 11: alle Instanzen des Notepad-Befehls erhalten</span><span class="sxs-lookup"><span data-stu-id="68cf8-160">Example 11: Get all instances of the Notepad command</span></span>

<span data-ttu-id="68cf8-161">In diesem Beispiel wird der **all** -Parameter des `Get-Command` Cmdlets verwendet, um alle Instanzen des Befehls "Notepad" auf dem lokalen Computer anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="68cf8-161">This example uses the **All** parameter of the `Get-Command` cmdlet to show all instances of the "Notepad" command on the local computer.</span></span>

```powershell
Get-Command Notepad -All | Format-Table CommandType, Name, Definition
```

```Output
CommandType     Name           Definition
-----------     ----           ----------
Application     notepad.exe    C:\WINDOWS\system32\notepad.exe
Application     NOTEPAD.EXE    C:\WINDOWS\NOTEPAD.EXE
```

<span data-ttu-id="68cf8-162">Der **All** -Parameter ist nützlich, wenn es mehr als einen Befehl mit demselben Namen in der Sitzung gibt.</span><span class="sxs-lookup"><span data-stu-id="68cf8-162">The **All** parameter is useful when there is more than one command with the same name in the session.</span></span>

<span data-ttu-id="68cf8-163">Ab Windows PowerShell 3,0, wenn die Sitzung mehrere Befehle mit demselben Namen enthält, wird von nur der Befehl abgerufen, der ausgeführt wird, `Get-Command` Wenn Sie den Befehlsnamen eingeben.</span><span class="sxs-lookup"><span data-stu-id="68cf8-163">Beginning in Windows PowerShell 3.0, by default, when the session includes multiple commands with the same name, `Get-Command` gets only the command that runs when you type the command name.</span></span> <span data-ttu-id="68cf8-164">Mit dem **all** -Parameter ruft `Get-Command` alle Befehle mit dem angegebenen Namen ab und gibt Sie in der Ausführungs Rangfolge zurück.</span><span class="sxs-lookup"><span data-stu-id="68cf8-164">With the **All** parameter, `Get-Command` gets all commands with the specified name and returns them in execution precedence order.</span></span> <span data-ttu-id="68cf8-165">Um einen anderen Befehl als den ersten in der Liste auszuführen, geben Sie den vollqualifizierten Pfad zu dem Befehl ein.</span><span class="sxs-lookup"><span data-stu-id="68cf8-165">To run a command other than the first one in the list, type the fully qualified path to the command.</span></span>

<span data-ttu-id="68cf8-166">Weitere Informationen zur Befehls Rangfolge finden Sie unter [about_Command_Precedence](About/about_Command_Precedence.md).</span><span class="sxs-lookup"><span data-stu-id="68cf8-166">For more information about command precedence, see [about_Command_Precedence](About/about_Command_Precedence.md).</span></span>

### <span data-ttu-id="68cf8-167">Beispiel 12: Holen Sie sich den Namen eines Moduls, das ein Cmdlet enthält.</span><span class="sxs-lookup"><span data-stu-id="68cf8-167">Example 12: Get the name of a module that contains a cmdlet</span></span>

<span data-ttu-id="68cf8-168">Mit diesem Befehl wird der Name des Moduls abgerufen, von dem das `Get-Date` Cmdlet stammt.</span><span class="sxs-lookup"><span data-stu-id="68cf8-168">This command gets the name of the module in which the `Get-Date` cmdlet originated.</span></span>
<span data-ttu-id="68cf8-169">Der Befehl verwendet die **ModuleName** -Eigenschaft aller Befehle.</span><span class="sxs-lookup"><span data-stu-id="68cf8-169">The command uses the **ModuleName** property of all commands.</span></span>

```powershell
(Get-Command Get-Date).ModuleName
```

```Output
Microsoft.PowerShell.Utility
```

<span data-ttu-id="68cf8-170">Dieses Befehls Format funktioniert mit Befehlen in PowerShell-Modulen, auch wenn Sie nicht in die Sitzung importiert werden.</span><span class="sxs-lookup"><span data-stu-id="68cf8-170">This command format works on commands in PowerShell modules, even if they are not imported into the session.</span></span>

### <span data-ttu-id="68cf8-171">Beispiel 13: Cmdlets und Funktionen mit einem Ausgabetyp</span><span class="sxs-lookup"><span data-stu-id="68cf8-171">Example 13: Get cmdlets and functions that have an output type</span></span>

```powershell
Get-Command -Type Cmdlet | Where-Object OutputType | Format-List -Property Name, OutputType
```

<span data-ttu-id="68cf8-172">Dieser Befehl ruft die Cmdlets und Funktionen ab, die über einen Ausgabetyp verfügen, und den Typ der Objekte, die sie zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="68cf8-172">This command gets the cmdlets and functions that have an output type and the type of objects that they return.</span></span>

<span data-ttu-id="68cf8-173">Der erste Teil des Befehls ruft alle Cmdlets ab.</span><span class="sxs-lookup"><span data-stu-id="68cf8-173">The first part of the command gets all cmdlets.</span></span>
<span data-ttu-id="68cf8-174">Ein Pipeline Operator (|) sendet die Cmdlets an das `Where-Object` Cmdlet, das nur die Cmdlets auswählt, in denen die **OutputType** -Eigenschaft aufgefüllt ist.</span><span class="sxs-lookup"><span data-stu-id="68cf8-174">A pipeline operator (|) sends the cmdlets to the `Where-Object` cmdlet, which selects only the ones in which the **OutputType** property is populated.</span></span>
<span data-ttu-id="68cf8-175">Ein weiterer Pipeline Operator sendet die ausgewählten Cmdlet-Objekte an das `Format-List` Cmdlet, das den Namen und den Ausgabetyp der einzelnen Cmdlets in einer Liste anzeigt.</span><span class="sxs-lookup"><span data-stu-id="68cf8-175">Another pipeline operator sends the selected cmdlet objects to the `Format-List` cmdlet, which displays the name and output type of each cmdlet in a list.</span></span>

<span data-ttu-id="68cf8-176">Die **OutputType** -Eigenschaft eines **CommandInfo** -Objekts hat nur dann einen Nicht-Null-Wert, wenn der Cmdlet-Code das **OutputType** -Attribut für das Cmdlet definiert.</span><span class="sxs-lookup"><span data-stu-id="68cf8-176">The **OutputType** property of a **CommandInfo** object has a non-null value only when the cmdlet code defines the **OutputType** attribute for the cmdlet.</span></span>

### <span data-ttu-id="68cf8-177">Beispiel 14: Get-Cmdlets, die einen bestimmten Objekttyp als Eingabe annehmen</span><span class="sxs-lookup"><span data-stu-id="68cf8-177">Example 14: Get cmdlets that take a specific object type as input</span></span>

```powershell
Get-Command -ParameterType (((Get-NetAdapter)[0]).PSTypeNames)
```

```Output
CommandType     Name                                               ModuleName
-----------     ----                                               ----------
Function        Disable-NetAdapter                                 NetAdapter
Function        Enable-NetAdapter                                  NetAdapter
Function        Rename-NetAdapter                                  NetAdapter
Function        Restart-NetAdapter                                 NetAdapter
Function        Set-NetAdapter                                     NetAdapter
```

<span data-ttu-id="68cf8-178">Mit diesem Befehl wird nach Cmdlets gesucht, die Netzwerkadapterobjekte als Eingabe akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="68cf8-178">This command finds cmdlets that take net adapter objects as input.</span></span> <span data-ttu-id="68cf8-179">Verwenden Sie dieses Befehlsformat, um nach den Cmdlets zu suchen, die den Typ von Objekten akzeptieren, die ein beliebiger Befehl zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="68cf8-179">You can use this command format to find the cmdlets that accept the type of objects that any command returns.</span></span>

<span data-ttu-id="68cf8-180">Der Befehl verwendet die systeminterne Eigenschaft aller Objekte **PSTypeNames** , die die Typen abruft, die das Objekt beschreiben.</span><span class="sxs-lookup"><span data-stu-id="68cf8-180">The command uses the **PSTypeNames** intrinsic property of all objects, which gets the types that describe the object.</span></span> <span data-ttu-id="68cf8-181">Zum Abrufen der **PSTypeNames** -Eigenschaft eines Netzwerkadapters und nicht der **PSTypeNames** -Eigenschaft einer Auflistung von Netzwerkadaptern verwendet der Befehl die Arraynotation, um den ersten Netzwerkadapter abzurufen, den das Cmdlet zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="68cf8-181">To get the **PSTypeNames** property of a net adapter, and not the **PSTypeNames** property of a collection of net adapters, the command uses array notation to get the first net adapter that the cmdlet returns.</span></span>

### <span data-ttu-id="68cf8-182">Beispiel 15: Get-Befehle mithilfe einer Fuzzyübereinstimmung</span><span class="sxs-lookup"><span data-stu-id="68cf8-182">Example 15: Get commands using a fuzzy match</span></span>

<span data-ttu-id="68cf8-183">In diesem Beispiel weist der Name des Befehls absichtlich einen Tippfehler als ' Get-commnd ' auf.</span><span class="sxs-lookup"><span data-stu-id="68cf8-183">In this example, the name of the command deliberately has a typo as 'get-commnd'.</span></span>
<span data-ttu-id="68cf8-184">Mithilfe des- `-UseFuzzyMatching` Schalters hat das Cmdlet ermittelt, dass die beste Entsprechung `Get-Command` von anderen systemeigenen Befehlen auf dem System gefolgt ist, die eine ähnliche Entsprechung hatten.</span><span class="sxs-lookup"><span data-stu-id="68cf8-184">Using the `-UseFuzzyMatching` switch, the cmdlet determined that the best match was `Get-Command` followed by other native commands on the system that were a similar match.</span></span>

```powershell
Get-Command get-commnd -UseFuzzyMatching
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Cmdlet          Get-Command                                        6.2.0.0    Microsoft.PowerShell.Core
Application     getconf                                            0.0.0.0    /usr/bin/getconf
Application     command                                            0.0.0.0    /usr/bin/command
```

## <span data-ttu-id="68cf8-185">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="68cf8-185">PARAMETERS</span></span>

### <span data-ttu-id="68cf8-186">-All</span><span class="sxs-lookup"><span data-stu-id="68cf8-186">-All</span></span>

<span data-ttu-id="68cf8-187">Gibt an, dass dieses Cmdlet alle Befehle abruft, einschließlich Befehlen desselben Typs, die denselben Namen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="68cf8-187">Indicates that this cmdlet gets all commands, including commands of the same type that have the same name.</span></span> <span data-ttu-id="68cf8-188">Standardmäßig ruft `Get-Command` nur die Befehle ab, die ausgeführt werden, wenn Sie den Befehlsnamen eingeben.</span><span class="sxs-lookup"><span data-stu-id="68cf8-188">By default, `Get-Command` gets only the commands that run when you type the command name.</span></span>

<span data-ttu-id="68cf8-189">Weitere Informationen zu der Methode, die von PowerShell verwendet wird, um den Befehl auszuwählen, der ausgeführt werden soll, wenn mehrere Befehle denselben Namen aufweisen, finden Sie unter [about_Command_Precedence](About/about_Command_Precedence.md).</span><span class="sxs-lookup"><span data-stu-id="68cf8-189">For more information about the method that PowerShell uses to select the command to run when multiple commands have the same name, see [about_Command_Precedence](About/about_Command_Precedence.md).</span></span>
<span data-ttu-id="68cf8-190">Informationen zu Modul qualifizierten Befehlsnamen und zum Ausführen von Befehlen, die aufgrund eines Namens Konflikts nicht standardmäßig ausgeführt werden, finden Sie unter [about_Modules](About/about_Modules.md).</span><span class="sxs-lookup"><span data-stu-id="68cf8-190">For information about module-qualified command names and running commands that do not run by default because of a name conflict, see [about_Modules](About/about_Modules.md).</span></span>

<span data-ttu-id="68cf8-191">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="68cf8-191">This parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="68cf8-192">In Windows PowerShell 2,0 ruft `Get-Command` standardmäßig alle Befehle ab.</span><span class="sxs-lookup"><span data-stu-id="68cf8-192">In Windows PowerShell 2.0, `Get-Command` gets all commands by default.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="68cf8-193">-Argumentlist</span><span class="sxs-lookup"><span data-stu-id="68cf8-193">-ArgumentList</span></span>

<span data-ttu-id="68cf8-194">Gibt ein Array von Argumenten an.</span><span class="sxs-lookup"><span data-stu-id="68cf8-194">Specifies an array of arguments.</span></span> <span data-ttu-id="68cf8-195">Dieses Cmdlet ruft Informationen zu einem Cmdlet oder einer Funktion ab, wenn es mit den angegebenen Parametern ("Argumenten") verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="68cf8-195">This cmdlet gets information about a cmdlet or function when it is used with the specified parameters ("arguments").</span></span> <span data-ttu-id="68cf8-196">Der Alias für **ArgumentList** ist **Args** .</span><span class="sxs-lookup"><span data-stu-id="68cf8-196">The alias for **ArgumentList** is **Args** .</span></span>

<span data-ttu-id="68cf8-197">Um dynamische Parameter zu ermitteln, die nur verfügbar sind, wenn bestimmte andere Parameter verwendet werden, legen Sie den Wert von Argument **List** auf die Parameter fest, die die dynamischen Parameter auslöst.</span><span class="sxs-lookup"><span data-stu-id="68cf8-197">To detect dynamic parameters that are available only when certain other parameters are used, set the value of **ArgumentList** to the parameters that trigger the dynamic parameters.</span></span>

<span data-ttu-id="68cf8-198">Um die dynamischen Parameter zu ermitteln, die ein Anbieter zu einem Cmdlet hinzufügt, legen Sie den Wert des **argumentlist** -Parameters auf einen Pfad im Anbieter Laufwerk fest, z. b. WSMAN:, HKLM: oder CERT:.</span><span class="sxs-lookup"><span data-stu-id="68cf8-198">To detect the dynamic parameters that a provider adds to a cmdlet, set the value of the **ArgumentList** parameter to a path in the provider drive, such as WSMan:, HKLM:, or Cert:.</span></span> <span data-ttu-id="68cf8-199">Wenn es sich bei dem Befehl um ein PowerShell-Anbieter-Cmdlet handelt, geben Sie in jedem Befehl nur einen Pfad ein.</span><span class="sxs-lookup"><span data-stu-id="68cf8-199">When the command is a PowerShell provider cmdlet, enter only one path in each command.</span></span> <span data-ttu-id="68cf8-200">Die Anbieter-Cmdlets geben nur die dynamischen Parameter für den ersten Pfad den Wert von **argumentlist** zurück.</span><span class="sxs-lookup"><span data-stu-id="68cf8-200">The provider cmdlets return only the dynamic parameters for the first path the value of **ArgumentList** .</span></span> <span data-ttu-id="68cf8-201">Weitere Informationen zu den Anbieter-Cmdlets finden Sie unter [about_Providers](About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="68cf8-201">For information about the provider cmdlets, see [about_Providers](About/about_Providers.md).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases: Args

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="68cf8-202">-CommandType</span><span class="sxs-lookup"><span data-stu-id="68cf8-202">-CommandType</span></span>

<span data-ttu-id="68cf8-203">Gibt die Typen von Befehlen an, die von diesem Cmdlet abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="68cf8-203">Specifies the types of commands that this cmdlet gets.</span></span> <span data-ttu-id="68cf8-204">Geben Sie einen oder mehrere Befehlstypen ein.</span><span class="sxs-lookup"><span data-stu-id="68cf8-204">Enter one or more command types.</span></span> <span data-ttu-id="68cf8-205">Verwenden Sie **CommandType** oder dessen Aliasname **Type** .</span><span class="sxs-lookup"><span data-stu-id="68cf8-205">Use **CommandType** or its alias, **Type** .</span></span> <span data-ttu-id="68cf8-206">Standardmäßig `Get-Command` Ruft alle-Cmdlets,-Funktionen und-Aliase ab.</span><span class="sxs-lookup"><span data-stu-id="68cf8-206">By default, `Get-Command` gets all cmdlets, functions, and aliases.</span></span>

<span data-ttu-id="68cf8-207">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="68cf8-207">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="68cf8-208">Alias.</span><span class="sxs-lookup"><span data-stu-id="68cf8-208">Alias.</span></span> <span data-ttu-id="68cf8-209">Ruft die Aliase aller PowerShell-Befehle ab.</span><span class="sxs-lookup"><span data-stu-id="68cf8-209">Gets the aliases of all PowerShell commands.</span></span> <span data-ttu-id="68cf8-210">Weitere Informationen finden Sie unter [about_Aliases](About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="68cf8-210">For more information, see [about_Aliases](About/about_Aliases.md).</span></span>
- <span data-ttu-id="68cf8-211">Alle</span><span class="sxs-lookup"><span data-stu-id="68cf8-211">All.</span></span> <span data-ttu-id="68cf8-212">Ruft alle Befehlstypen ab.</span><span class="sxs-lookup"><span data-stu-id="68cf8-212">Gets all command types.</span></span> <span data-ttu-id="68cf8-213">Dieser Parameterwert entspricht `Get-Command *` .</span><span class="sxs-lookup"><span data-stu-id="68cf8-213">This parameter value is the equivalent of `Get-Command *`.</span></span>
- <span data-ttu-id="68cf8-214">Anwendung:</span><span class="sxs-lookup"><span data-stu-id="68cf8-214">Application.</span></span> <span data-ttu-id="68cf8-215">Ruft nicht-PowerShell-Dateien in Pfaden ab, die in der **path** -Umgebungsvariablen ($env:p ATH) aufgelistet sind, einschließlich. txt-,. exe-und. dll-Dateien.</span><span class="sxs-lookup"><span data-stu-id="68cf8-215">Gets non-PowerShell files in paths listed in the **Path** environment variable ($env:path), including .txt, .exe, and .dll files.</span></span> <span data-ttu-id="68cf8-216">Weitere Informationen zur **path** -Umgebungsvariablen finden Sie unter about_Environment_Variables.</span><span class="sxs-lookup"><span data-stu-id="68cf8-216">For more information about the **Path** environment variable, see about_Environment_Variables.</span></span>
- <span data-ttu-id="68cf8-217">Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="68cf8-217">Cmdlet.</span></span> <span data-ttu-id="68cf8-218">Ruft alle Cmdlets ab.</span><span class="sxs-lookup"><span data-stu-id="68cf8-218">Gets all cmdlets.</span></span>
- <span data-ttu-id="68cf8-219">Externalscript.</span><span class="sxs-lookup"><span data-stu-id="68cf8-219">ExternalScript.</span></span> <span data-ttu-id="68cf8-220">Ruft alle PS1-Dateien in den Pfaden ab, die in der **Path** -Umgebungsvariablen ($env:path) aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="68cf8-220">Gets all .ps1 files in the paths listed in the **Path** environment variable ($env:path).</span></span>
- <span data-ttu-id="68cf8-221">Filter und function.</span><span class="sxs-lookup"><span data-stu-id="68cf8-221">Filter and Function.</span></span> <span data-ttu-id="68cf8-222">Ruft alle erweiterten und einfachen PowerShell-Funktionen und-Filter ab.</span><span class="sxs-lookup"><span data-stu-id="68cf8-222">Gets all PowerShell advanced and simple functions and filters.</span></span>
- <span data-ttu-id="68cf8-223">Skript.</span><span class="sxs-lookup"><span data-stu-id="68cf8-223">Script.</span></span> <span data-ttu-id="68cf8-224">Ruft alle Skriptblöcke ab.</span><span class="sxs-lookup"><span data-stu-id="68cf8-224">Gets all script blocks.</span></span> <span data-ttu-id="68cf8-225">Um PowerShell-Skripts (PS1-Dateien) zu erhalten, verwenden Sie den externalscript-Wert.</span><span class="sxs-lookup"><span data-stu-id="68cf8-225">To get PowerShell scripts (.ps1 files), use the ExternalScript value.</span></span>

```yaml
Type: System.Management.Automation.CommandTypes
Parameter Sets: AllCommandSet
Aliases: Type
Accepted values: Alias, Function, Filter, Cmdlet, ExternalScript, Application, Script, Workflow, Configuration, All

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="68cf8-226">-Fullyqualifiedmodule</span><span class="sxs-lookup"><span data-stu-id="68cf8-226">-FullyQualifiedModule</span></span>

<span data-ttu-id="68cf8-227">Gibt Module an, deren Namen in Form von **modulespecification** -Objekten angegeben sind, die im Abschnitt " **Hinweise** " des [modulespecification-Konstruktors (Hash Tabelle)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor?view=powershellsdk-1.1.0#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_)beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="68cf8-227">Specifies modules with names that are specified in the form of **ModuleSpecification** objects, described in the **Remarks** section of [ModuleSpecification Constructor (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor?view=powershellsdk-1.1.0#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).</span></span>
<span data-ttu-id="68cf8-228">Der **fullyqualifiedmodule** -Parameter akzeptiert z. b. einen Modulnamen, der in einem der folgenden Formate angegeben ist:</span><span class="sxs-lookup"><span data-stu-id="68cf8-228">For example, the **FullyQualifiedModule** parameter accepts a module name that is specified in one of the following formats:</span></span>

- `@{ModuleName = "modulename"; ModuleVersion = "version_number"}`
- `@{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}`

<span data-ttu-id="68cf8-229">**ModuleName** und **ModuleVersion** sind erforderlich, aber **Guid** ist optional.</span><span class="sxs-lookup"><span data-stu-id="68cf8-229">**ModuleName** and **ModuleVersion** are required, but **Guid** is optional.</span></span>

<span data-ttu-id="68cf8-230">Sie können den **fullyqualifiedmodule** -Parameter nicht im selben Befehl wie einen **Modul** Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="68cf8-230">You cannot specify the **FullyQualifiedModule** parameter in the same command as a **Module** parameter.</span></span> <span data-ttu-id="68cf8-231">Die beiden Parameter schließen sich gegenseitig aus.</span><span class="sxs-lookup"><span data-stu-id="68cf8-231">The two parameters are mutually exclusive.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="68cf8-232">-Listimportiert</span><span class="sxs-lookup"><span data-stu-id="68cf8-232">-ListImported</span></span>

<span data-ttu-id="68cf8-233">Gibt an, dass dieses Cmdlet nur Befehle in der aktuellen Sitzung abruft.</span><span class="sxs-lookup"><span data-stu-id="68cf8-233">Indicates that this cmdlet gets only commands in the current session.</span></span>

<span data-ttu-id="68cf8-234">Ab PowerShell 3,0 ruft standardmäßig `Get-Command` alle installierten Befehle ab, einschließlich, aber nicht beschränkt auf die Befehle in der aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="68cf8-234">Starting in PowerShell 3.0, by default, `Get-Command` gets all installed commands, including, but not limited to, the commands in the current session.</span></span> <span data-ttu-id="68cf8-235">In PowerShell 2,0 werden nur Befehle in der aktuellen Sitzung abgerufen.</span><span class="sxs-lookup"><span data-stu-id="68cf8-235">In PowerShell 2.0, it gets only commands in the current session.</span></span>

<span data-ttu-id="68cf8-236">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="68cf8-236">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="68cf8-237">-Modul</span><span class="sxs-lookup"><span data-stu-id="68cf8-237">-Module</span></span>

<span data-ttu-id="68cf8-238">Gibt ein Array von Modulen an.</span><span class="sxs-lookup"><span data-stu-id="68cf8-238">Specifies an array of modules.</span></span> <span data-ttu-id="68cf8-239">Dieses Cmdlet ruft die Befehle ab, die von den angegebenen Modulen stammen.</span><span class="sxs-lookup"><span data-stu-id="68cf8-239">This cmdlet gets the commands that came from the specified modules.</span></span>
<span data-ttu-id="68cf8-240">Geben Sie die Namen der Module oder Modul Objekte ein.</span><span class="sxs-lookup"><span data-stu-id="68cf8-240">Enter the names of modules or module objects.</span></span>

<span data-ttu-id="68cf8-241">Dieser Parameter nimmt Zeichen folgen Werte an, aber der Wert dieses Parameters kann auch ein **psmoduleinfo** -Objekt sein, z. b. die Objekte, die von den `Get-Module` -und- `Import-PSSession` Cmdlets zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="68cf8-241">This parameter takes string values, but the value of this parameter can also be a **PSModuleInfo** object, such as the objects that the `Get-Module` and `Import-PSSession` cmdlets return.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSSnapin

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="68cf8-242">-Name</span><span class="sxs-lookup"><span data-stu-id="68cf8-242">-Name</span></span>

<span data-ttu-id="68cf8-243">Gibt ein Array von Namen an.</span><span class="sxs-lookup"><span data-stu-id="68cf8-243">Specifies an array of names.</span></span> <span data-ttu-id="68cf8-244">Dieses Cmdlet ruft nur Befehle mit dem angegebenen Namen ab.</span><span class="sxs-lookup"><span data-stu-id="68cf8-244">This cmdlet gets only commands that have the specified name.</span></span> <span data-ttu-id="68cf8-245">Geben Sie einen Namen oder ein Namensmuster ein.</span><span class="sxs-lookup"><span data-stu-id="68cf8-245">Enter a name or name pattern.</span></span> <span data-ttu-id="68cf8-246">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="68cf8-246">Wildcard characters are permitted.</span></span>

<span data-ttu-id="68cf8-247">Um Befehle abzurufen, die den gleichen Namen haben, verwenden Sie den **All** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="68cf8-247">To get commands that have the same name, use the **All** parameter.</span></span> <span data-ttu-id="68cf8-248">Wenn zwei Befehle denselben Namen haben, ruft standardmäßig den Befehl ab, der ausgeführt wird, `Get-Command` Wenn Sie den Befehlsnamen eingeben.</span><span class="sxs-lookup"><span data-stu-id="68cf8-248">When two commands have the same name, by default, `Get-Command` gets the command that runs when you type the command name.</span></span>

```yaml
Type: System.String[]
Parameter Sets: AllCommandSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="68cf8-249">-Substantiv</span><span class="sxs-lookup"><span data-stu-id="68cf8-249">-Noun</span></span>

<span data-ttu-id="68cf8-250">Gibt ein Array von Befehls-nouns an.</span><span class="sxs-lookup"><span data-stu-id="68cf8-250">Specifies an array of command nouns.</span></span> <span data-ttu-id="68cf8-251">Dieses Cmdlet ruft die Befehle ab, die Cmdlets, Funktionen und Aliase enthalten, deren Namen das angegebene Substantiv enthalten.</span><span class="sxs-lookup"><span data-stu-id="68cf8-251">This cmdlet gets commands, which include cmdlets, functions, and aliases, that have names that include the specified noun.</span></span> <span data-ttu-id="68cf8-252">Geben Sie ein oder mehrere Nomen oder Nomenmuster ein.</span><span class="sxs-lookup"><span data-stu-id="68cf8-252">Enter one or more nouns or noun patterns.</span></span> <span data-ttu-id="68cf8-253">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="68cf8-253">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: CmdletSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="68cf8-254">-Parameter Name</span><span class="sxs-lookup"><span data-stu-id="68cf8-254">-ParameterName</span></span>

<span data-ttu-id="68cf8-255">Gibt ein Array von Parameternamen an.</span><span class="sxs-lookup"><span data-stu-id="68cf8-255">Specifies an array of parameter names.</span></span> <span data-ttu-id="68cf8-256">Dieses Cmdlet ruft die Befehle in der Sitzung ab, die über die angegebenen Parameter verfügen.</span><span class="sxs-lookup"><span data-stu-id="68cf8-256">This cmdlet gets commands in the session that have the specified parameters.</span></span> <span data-ttu-id="68cf8-257">Geben Sie Parameternamen oder Parameter Aliase ein.</span><span class="sxs-lookup"><span data-stu-id="68cf8-257">Enter parameter names or parameter aliases.</span></span> <span data-ttu-id="68cf8-258">Platzhalterzeichen werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="68cf8-258">Wildcard characters are supported.</span></span>

<span data-ttu-id="68cf8-259">Die Parameter **ParameterName** und **ParameterType** suchen nur Befehle in der aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="68cf8-259">The **ParameterName** and **ParameterType** parameters search only commands in the current session.</span></span>

<span data-ttu-id="68cf8-260">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="68cf8-260">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="68cf8-261">-ParameterType</span><span class="sxs-lookup"><span data-stu-id="68cf8-261">-ParameterType</span></span>

<span data-ttu-id="68cf8-262">Gibt ein Array von Parameternamen an.</span><span class="sxs-lookup"><span data-stu-id="68cf8-262">Specifies an array of parameter names.</span></span> <span data-ttu-id="68cf8-263">Dieses Cmdlet ruft die Befehle in der Sitzung ab, die Parameter des angegebenen Typs aufweisen.</span><span class="sxs-lookup"><span data-stu-id="68cf8-263">This cmdlet gets commands in the session that have parameters of the specified type.</span></span> <span data-ttu-id="68cf8-264">Geben Sie den vollständigen Namen oder Teilnamen eines Parametertyps ein.</span><span class="sxs-lookup"><span data-stu-id="68cf8-264">Enter the full name or partial name of a parameter type.</span></span> <span data-ttu-id="68cf8-265">Platzhalterzeichen werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="68cf8-265">Wildcard characters are supported.</span></span>

<span data-ttu-id="68cf8-266">Die Parameter **ParameterName** und **ParameterType** suchen nur Befehle in der aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="68cf8-266">The **ParameterName** and **ParameterType** parameters search only commands in the current session.</span></span>

<span data-ttu-id="68cf8-267">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="68cf8-267">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSTypeName[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="68cf8-268">-Showcommandinfo</span><span class="sxs-lookup"><span data-stu-id="68cf8-268">-ShowCommandInfo</span></span>

<span data-ttu-id="68cf8-269">Gibt an, dass dieses Cmdlet Befehls Informationen anzeigt.</span><span class="sxs-lookup"><span data-stu-id="68cf8-269">Indicates that this cmdlet displays command information.</span></span>

<span data-ttu-id="68cf8-270">Dieser Parameter wurde in Windows PowerShell 5,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="68cf8-270">This parameter was introduced in Windows PowerShell 5.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="68cf8-271">-Syntax</span><span class="sxs-lookup"><span data-stu-id="68cf8-271">-Syntax</span></span>

<span data-ttu-id="68cf8-272">Gibt an, dass dieses Cmdlet nur die folgenden angegebenen Daten über den Befehl abruft:</span><span class="sxs-lookup"><span data-stu-id="68cf8-272">Indicates that this cmdlet gets only the following specified data about the command:</span></span>

- <span data-ttu-id="68cf8-273">Aliase.</span><span class="sxs-lookup"><span data-stu-id="68cf8-273">Aliases.</span></span> <span data-ttu-id="68cf8-274">Ruft den Standardnamen ab.</span><span class="sxs-lookup"><span data-stu-id="68cf8-274">Gets the standard name.</span></span>
- <span data-ttu-id="68cf8-275">Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="68cf8-275">Cmdlets.</span></span> <span data-ttu-id="68cf8-276">Ruft die Syntax ab.</span><span class="sxs-lookup"><span data-stu-id="68cf8-276">Gets the syntax.</span></span>
- <span data-ttu-id="68cf8-277">Funktionen und Filter.</span><span class="sxs-lookup"><span data-stu-id="68cf8-277">Functions and filters.</span></span> <span data-ttu-id="68cf8-278">Ruft die Funktionsdefinition ab.</span><span class="sxs-lookup"><span data-stu-id="68cf8-278">Gets the function definition.</span></span>
- <span data-ttu-id="68cf8-279">Skripts und Anwendungen oder Dateien.</span><span class="sxs-lookup"><span data-stu-id="68cf8-279">Scripts and applications or files.</span></span> <span data-ttu-id="68cf8-280">Ruft den Pfad und Dateinamen ab.</span><span class="sxs-lookup"><span data-stu-id="68cf8-280">Gets the path and filename.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="68cf8-281">-TotalCount</span><span class="sxs-lookup"><span data-stu-id="68cf8-281">-TotalCount</span></span>

<span data-ttu-id="68cf8-282">Gibt die Anzahl der auszuführenden Befehle an.</span><span class="sxs-lookup"><span data-stu-id="68cf8-282">Specifies the number of commands to get.</span></span> <span data-ttu-id="68cf8-283">Mit diesem Parameter können Sie die Ausgabe eines Befehls beschränken.</span><span class="sxs-lookup"><span data-stu-id="68cf8-283">You can use this parameter to limit the output of a command.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="68cf8-284">-Useabationweiterung</span><span class="sxs-lookup"><span data-stu-id="68cf8-284">-UseAbbreviationExpansion</span></span>

<span data-ttu-id="68cf8-285">Gibt an, dass die Zeichen im Befehl mit einem übereinstimmenden Zeichen in einem Befehl gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="68cf8-285">Indicates using matching of the characters in the command to find with uppercase characters in a command.</span></span> <span data-ttu-id="68cf8-286">Beispielsweise `i-psdf` würde übereinstimmen, `Import-PowerShellDataFile` Wenn jedes der zu suchenden Zeichen mit einem Großbuchstaben im Ergebnis übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="68cf8-286">For example, `i-psdf` would match `Import-PowerShellDataFile` as each of the characters to find matches an uppercase character in the result.</span></span> <span data-ttu-id="68cf8-287">Wenn diese Art der Übereinstimmung verwendet wird, ergeben alle Platzhalter keine Übereinstimmungen.</span><span class="sxs-lookup"><span data-stu-id="68cf8-287">When using this type of match, any wildcards will result in no matches.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AllCommandSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="68cf8-288">-Usefuzzymatching</span><span class="sxs-lookup"><span data-stu-id="68cf8-288">-UseFuzzyMatching</span></span>

<span data-ttu-id="68cf8-289">Gibt die Verwendung eines Fuzzyübereinstimmungs Algorithmus beim Suchen von Befehlen</span><span class="sxs-lookup"><span data-stu-id="68cf8-289">Indicates using a fuzzy matching algorithm when finding commands.</span></span> <span data-ttu-id="68cf8-290">Die Reihenfolge der Ausgabe ist von der nächsten Übereinstimmung bis zum wahrscheinlichsten Abgleich.</span><span class="sxs-lookup"><span data-stu-id="68cf8-290">The order of the output is from closest match to least likely match.</span></span> <span data-ttu-id="68cf8-291">Platzhalter sollten nicht mit Fuzzyübereinstimmung verwendet werden, da versucht wird, Befehle abzugleichen, die möglicherweise diese Platzhalter Zeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="68cf8-291">Wildcards should not be used with fuzzy matching as it will attempt to match commands that may contain those wildcard characters.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AllCommandSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="68cf8-292">-Verb</span><span class="sxs-lookup"><span data-stu-id="68cf8-292">-Verb</span></span>

<span data-ttu-id="68cf8-293">Gibt ein Array von Befehls Verben an.</span><span class="sxs-lookup"><span data-stu-id="68cf8-293">Specifies an array of command verbs.</span></span> <span data-ttu-id="68cf8-294">Dieses Cmdlet ruft die Befehle ab, die Cmdlets, Funktionen und Aliase enthalten, deren Namen das angegebene Verb enthalten.</span><span class="sxs-lookup"><span data-stu-id="68cf8-294">This cmdlet gets commands, which include cmdlets, functions, and aliases, that have names that include the specified verb.</span></span> <span data-ttu-id="68cf8-295">Geben Sie ein oder mehrere Verben oder Verbmuster ein.</span><span class="sxs-lookup"><span data-stu-id="68cf8-295">Enter one or more verbs or verb patterns.</span></span> <span data-ttu-id="68cf8-296">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="68cf8-296">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: CmdletSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="68cf8-297">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="68cf8-297">CommonParameters</span></span>

<span data-ttu-id="68cf8-298">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="68cf8-298">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="68cf8-299">Weitere Informationen findest du unter [about_CommonParameters](About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="68cf8-299">For more information, see [about_CommonParameters](About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="68cf8-300">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="68cf8-300">INPUTS</span></span>

### <span data-ttu-id="68cf8-301">System.String</span><span class="sxs-lookup"><span data-stu-id="68cf8-301">System.String</span></span>

<span data-ttu-id="68cf8-302">Sie können Befehlsnamen an dieses Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="68cf8-302">You can pipe command names to this cmdlet.</span></span>

## <span data-ttu-id="68cf8-303">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="68cf8-303">OUTPUTS</span></span>

### <span data-ttu-id="68cf8-304">System. Management. Automation. CommandInfo</span><span class="sxs-lookup"><span data-stu-id="68cf8-304">System.Management.Automation.CommandInfo</span></span>

<span data-ttu-id="68cf8-305">Dieses Cmdlet gibt Objekte zurück, die von der **CommandInfo** -Klasse abgeleitet wurden.</span><span class="sxs-lookup"><span data-stu-id="68cf8-305">This cmdlet returns objects derived from the **CommandInfo** class.</span></span> <span data-ttu-id="68cf8-306">Der Typ des Objekts, das zurückgegeben wird, hängt vom Typ des Befehls ab, der abgerufen wird `Get-Command` .</span><span class="sxs-lookup"><span data-stu-id="68cf8-306">The type of object that is returned depends on the type of command that `Get-Command` gets.</span></span>

### <span data-ttu-id="68cf8-307">System. Management. Automation. AliasInfo</span><span class="sxs-lookup"><span data-stu-id="68cf8-307">System.Management.Automation.AliasInfo</span></span>

<span data-ttu-id="68cf8-308">Stellt Aliase dar.</span><span class="sxs-lookup"><span data-stu-id="68cf8-308">Represents aliases.</span></span>

### <span data-ttu-id="68cf8-309">System. Management. Automation. ApplicationInfo</span><span class="sxs-lookup"><span data-stu-id="68cf8-309">System.Management.Automation.ApplicationInfo</span></span>

<span data-ttu-id="68cf8-310">Stellt Anwendungen und Dateien dar.</span><span class="sxs-lookup"><span data-stu-id="68cf8-310">Represents applications and files.</span></span>

### <span data-ttu-id="68cf8-311">System. Management. Automation. cmdletinfo</span><span class="sxs-lookup"><span data-stu-id="68cf8-311">System.Management.Automation.CmdletInfo</span></span>

<span data-ttu-id="68cf8-312">Stellt Cmdlets dar.</span><span class="sxs-lookup"><span data-stu-id="68cf8-312">Represents cmdlets.</span></span>

### <span data-ttu-id="68cf8-313">System. Management. Automation. functioninfo</span><span class="sxs-lookup"><span data-stu-id="68cf8-313">System.Management.Automation.FunctionInfo</span></span>

<span data-ttu-id="68cf8-314">Stellt Funktionen und Filter dar.</span><span class="sxs-lookup"><span data-stu-id="68cf8-314">Represents functions and filters.</span></span>

## <span data-ttu-id="68cf8-315">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="68cf8-315">NOTES</span></span>

* <span data-ttu-id="68cf8-316">Wenn mehr als ein Befehl mit demselben Namen für die Sitzung verfügbar ist, `Get-Command` gibt den Befehl zurück, der ausgeführt wird, wenn Sie den Befehlsnamen eingeben.</span><span class="sxs-lookup"><span data-stu-id="68cf8-316">When more than one command that has the same name is available to the session, `Get-Command` returns the command that runs when you type the command name.</span></span> <span data-ttu-id="68cf8-317">Verwenden Sie den **all** -Parameter, um Befehle mit dem gleichen Namen, die in der Reihenfolge der Bestellung aufgeführt sind, zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="68cf8-317">To get commands that have the same name, listed in run order, use the **All** parameter.</span></span> <span data-ttu-id="68cf8-318">Weitere Informationen finden Sie unter [about_Command_Precedence](../Microsoft.PowerShell.Core/About/about_Command_Precedence.md).</span><span class="sxs-lookup"><span data-stu-id="68cf8-318">For more information, see [about_Command_Precedence](../Microsoft.PowerShell.Core/About/about_Command_Precedence.md).</span></span>
* <span data-ttu-id="68cf8-319">Wenn ein Modul automatisch importiert wird, entspricht der Effekt dem Verwenden des `Import-Module` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="68cf8-319">When a module is imported automatically, the effect is the same as using the `Import-Module` cmdlet.</span></span> <span data-ttu-id="68cf8-320">Das Modul kann Befehle, Typen und Formatierungsdateien hinzufügen und Skripts in der Sitzung ausführen.</span><span class="sxs-lookup"><span data-stu-id="68cf8-320">The module can add commands, types and formatting files, and run scripts in the session.</span></span>
  <span data-ttu-id="68cf8-321">Verwenden Sie die Preference-Variable, um das automatische Importieren von Modulen zu aktivieren, zu deaktivieren und zu konfigurieren `$PSModuleAutoLoadingPreference` .</span><span class="sxs-lookup"><span data-stu-id="68cf8-321">To enable, disable, and configuration automatic importing of modules, use the `$PSModuleAutoLoadingPreference` preference variable.</span></span> <span data-ttu-id="68cf8-322">Weitere Informationen finden Sie unter [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="68cf8-322">For more information, see [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

## <span data-ttu-id="68cf8-323">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="68cf8-323">RELATED LINKS</span></span>

[<span data-ttu-id="68cf8-324">Export-PSSession</span><span class="sxs-lookup"><span data-stu-id="68cf8-324">Export-PSSession</span></span>](../Microsoft.PowerShell.Utility/Export-PSSession.md)

[<span data-ttu-id="68cf8-325">Get-Help</span><span class="sxs-lookup"><span data-stu-id="68cf8-325">Get-Help</span></span>](Get-Help.md)

[<span data-ttu-id="68cf8-326">Get-Member</span><span class="sxs-lookup"><span data-stu-id="68cf8-326">Get-Member</span></span>](../Microsoft.PowerShell.Utility/Get-Member.md)

[<span data-ttu-id="68cf8-327">Get-PSDrive</span><span class="sxs-lookup"><span data-stu-id="68cf8-327">Get-PSDrive</span></span>](../Microsoft.PowerShell.Management/Get-PSDrive.md)

[<span data-ttu-id="68cf8-328">Import-PSSession</span><span class="sxs-lookup"><span data-stu-id="68cf8-328">Import-PSSession</span></span>](../Microsoft.PowerShell.Utility/Import-PSSession.md)

[<span data-ttu-id="68cf8-329">about_Command_Precedence</span><span class="sxs-lookup"><span data-stu-id="68cf8-329">about_Command_Precedence</span></span>](About/about_Command_Precedence.md)
