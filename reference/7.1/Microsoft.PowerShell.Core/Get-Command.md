---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 05/20/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-command?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Command
ms.openlocfilehash: 5f2752f53fb5f74b6436548c3bd4fa731d2b02d5
ms.sourcegitcommit: 04faa7dc1122bce839295d4891bd8b2f0ecb06ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/05/2021
ms.locfileid: "97879234"
---
# <span data-ttu-id="67aba-103">Get-Command</span><span class="sxs-lookup"><span data-stu-id="67aba-103">Get-Command</span></span>

## <span data-ttu-id="67aba-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="67aba-104">SYNOPSIS</span></span>
<span data-ttu-id="67aba-105">Ruft alle Befehle ab.</span><span class="sxs-lookup"><span data-stu-id="67aba-105">Gets all commands.</span></span>

## <span data-ttu-id="67aba-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="67aba-106">SYNTAX</span></span>

### <span data-ttu-id="67aba-107">CmdletSet (Standard)</span><span class="sxs-lookup"><span data-stu-id="67aba-107">CmdletSet (Default)</span></span>

```
Get-Command [-Verb <String[]>] [-Noun <String[]>] [-Module <String[]>]
 [-FullyQualifiedModule <ModuleSpecification[]>] [-TotalCount <Int32>] [-Syntax] [-ShowCommandInfo]
 [[-ArgumentList] <Object[]>] [-All] [-ListImported] [-ParameterName <String[]>]
 [-ParameterType <PSTypeName[]>] [<CommonParameters>]
```

### <span data-ttu-id="67aba-108">Allcommandset</span><span class="sxs-lookup"><span data-stu-id="67aba-108">AllCommandSet</span></span>

```
Get-Command [[-Name] <String[]>] [-Module <String[]>]
 [-FullyQualifiedModule <ModuleSpecification[]>] [-CommandType <CommandTypes>] [-TotalCount <Int32>]
 [-Syntax] [-ShowCommandInfo] [[-ArgumentList] <Object[]>] [-All] [-ListImported]
 [-ParameterName <String[]>] [-ParameterType <PSTypeName[]>] [-UseFuzzyMatching]
 [-UseAbbreviationExpansion] [<CommonParameters>]
```

## <span data-ttu-id="67aba-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="67aba-109">DESCRIPTION</span></span>

<span data-ttu-id="67aba-110">Das- `Get-Command` Cmdlet ruft alle Befehle ab, die auf dem Computer installiert sind, einschließlich Cmdlets, Aliase, Funktionen, Filter, Skripts und Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="67aba-110">The `Get-Command` cmdlet gets all commands that are installed on the computer, including cmdlets, aliases, functions, filters, scripts, and applications.</span></span> <span data-ttu-id="67aba-111">`Get-Command` Ruft die Befehle aus PowerShell-Modulen und-Befehlen ab, die aus anderen Sitzungen importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="67aba-111">`Get-Command` gets the commands from PowerShell modules and commands that were imported from other sessions.</span></span> <span data-ttu-id="67aba-112">Um nur die Befehle zu erhalten, die in die aktuelle Sitzung importiert wurden, verwenden Sie den **ListImported**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="67aba-112">To get only commands that have been imported into the current session, use the **ListImported** parameter.</span></span>

<span data-ttu-id="67aba-113">Ohne Parameter `Get-Command` Ruft alle-Cmdlets,-Funktionen und-Aliase ab, die auf dem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="67aba-113">Without parameters, `Get-Command` gets all of the cmdlets, functions, and aliases installed on the computer.</span></span> <span data-ttu-id="67aba-114">`Get-Command *` Ruft alle Befehls Typen ab, einschließlich aller nicht-PowerShell-Dateien in der PATH-Umgebungsvariablen ( `$env:Path` ), die Sie im Anwendungs Befehlstyp auflistet.</span><span class="sxs-lookup"><span data-stu-id="67aba-114">`Get-Command *` gets all types of commands, including all of the non-PowerShell files in the Path environment variable (`$env:Path`), which it lists in the Application command type.</span></span>

<span data-ttu-id="67aba-115">`Get-Command` der den genauen Namen des Befehls ohne Platzhalter Zeichen verwendet, importiert automatisch das Modul, das den Befehl enthält, sodass Sie den Befehl sofort verwenden können.</span><span class="sxs-lookup"><span data-stu-id="67aba-115">`Get-Command` that uses the exact name of the command, without wildcard characters, automatically imports the module that contains the command so that you can use the command immediately.</span></span> <span data-ttu-id="67aba-116">Verwenden Sie die Preference-Variable, um das automatische Importieren von Modulen zu aktivieren, zu deaktivieren und zu konfigurieren `$PSModuleAutoLoadingPreference` .</span><span class="sxs-lookup"><span data-stu-id="67aba-116">To enable, disable, and configure automatic importing of modules, use the `$PSModuleAutoLoadingPreference` preference variable.</span></span> <span data-ttu-id="67aba-117">Weitere Informationen finden Sie unter [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="67aba-117">For more information, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="67aba-118">`Get-Command` Ruft die zugehörigen Daten direkt aus dem Befehls Code ab, wobei `Get-Help` die Informationen aus Hilfe Themen abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="67aba-118">`Get-Command` gets its data directly from the command code, unlike `Get-Help`, which gets its information from help topics.</span></span>

<span data-ttu-id="67aba-119">Ab Windows PowerShell 5,0 zeigen die Ergebnisse des `Get-Command` Cmdlets standardmäßig eine **Versions** Spalte an.</span><span class="sxs-lookup"><span data-stu-id="67aba-119">Starting in Windows PowerShell 5.0, results of the `Get-Command` cmdlet display a **Version** column by default.</span></span> <span data-ttu-id="67aba-120">Der **CommandInfo** -Klasse wurde eine neue **Versions** Eigenschaft hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="67aba-120">A new **Version** property has been added to the **CommandInfo** class.</span></span>

## <span data-ttu-id="67aba-121">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="67aba-121">EXAMPLES</span></span>

### <span data-ttu-id="67aba-122">Beispiel 1: Cmdlets, Funktionen und Aliase</span><span class="sxs-lookup"><span data-stu-id="67aba-122">Example 1: Get cmdlets, functions, and aliases</span></span>

<span data-ttu-id="67aba-123">Mit diesem Befehl werden die auf dem Computer installierten PowerShell-Cmdlets,-Funktionen und-Aliase abgerufen.</span><span class="sxs-lookup"><span data-stu-id="67aba-123">This command gets the PowerShell cmdlets, functions, and aliases that are installed on the computer.</span></span>

```powershell
Get-Command
```

### <span data-ttu-id="67aba-124">Beispiel 2: Get-Befehle in der aktuellen Sitzung</span><span class="sxs-lookup"><span data-stu-id="67aba-124">Example 2: Get commands in the current session</span></span>

<span data-ttu-id="67aba-125">Dieser Befehl verwendet den **ListImported**-Parameter, um nur die Befehle in der aktuellen Sitzung abzurufen.</span><span class="sxs-lookup"><span data-stu-id="67aba-125">This command uses the **ListImported** parameter to get only the commands in the current session.</span></span>

```powershell
Get-Command -ListImported
```

### <span data-ttu-id="67aba-126">Beispiel 3: Cmdlets erhalten und in der richtigen Reihenfolge angezeigt</span><span class="sxs-lookup"><span data-stu-id="67aba-126">Example 3: Get cmdlets and display them in order</span></span>

<span data-ttu-id="67aba-127">Dieser Befehl ruft alle Cmdlets ab, sortiert sie alphabetisch nach dem Nomen im Cmdlet-Namen und zeigt sie dann in nomenbasierten Gruppen an.</span><span class="sxs-lookup"><span data-stu-id="67aba-127">This command gets all of the cmdlets, sorts them alphabetically by the noun in the cmdlet name, and then displays them in noun-based groups.</span></span> <span data-ttu-id="67aba-128">Diese Anzeige hilft Ihnen dabei, die Cmdlets für eine Aufgabe zu finden.</span><span class="sxs-lookup"><span data-stu-id="67aba-128">This display can help you find the cmdlets for a task.</span></span>

```powershell
Get-Command -Type Cmdlet | Sort-Object -Property Noun | Format-Table -GroupBy Noun
```

### <span data-ttu-id="67aba-129">Beispiel 4: Get-Befehle in einem Modul</span><span class="sxs-lookup"><span data-stu-id="67aba-129">Example 4: Get commands in a module</span></span>

<span data-ttu-id="67aba-130">Dieser Befehl verwendet den **Module** -Parameter, um die Befehle in den Modulen "Microsoft. PowerShell. Security" und "Microsoft. PowerShell. Utility" zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="67aba-130">This command uses the **Module** parameter to get the commands in the Microsoft.PowerShell.Security and Microsoft.PowerShell.Utility modules.</span></span>

```powershell
Get-Command -Module Microsoft.PowerShell.Security, Microsoft.PowerShell.Utility
```

### <span data-ttu-id="67aba-131">Beispiel 5: erhalten von Informationen zu einem Cmdlet</span><span class="sxs-lookup"><span data-stu-id="67aba-131">Example 5: Get information about a cmdlet</span></span>

<span data-ttu-id="67aba-132">Dieser Befehl ruft Informationen über das `Get-AppLockerPolicy` Cmdlet ab.</span><span class="sxs-lookup"><span data-stu-id="67aba-132">This command gets information about the `Get-AppLockerPolicy` cmdlet.</span></span> <span data-ttu-id="67aba-133">Der Befehl importiert auch das **AppLocker**-Modul, das alle Befehle im **AppLocker**-Modul zur aktuellen Sitzung hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="67aba-133">It also imports the **AppLocker** module, which adds all of the commands in the **AppLocker** module to the current session.</span></span>

```powershell
Get-Command Get-AppLockerPolicy
```

<span data-ttu-id="67aba-134">Wenn ein Modul automatisch importiert wird, entspricht der Effekt dem Verwenden des Import-Module-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="67aba-134">When a module is imported automatically, the effect is the same as using the Import-Module cmdlet.</span></span>
<span data-ttu-id="67aba-135">Das Modul kann Befehle, Typen und Formatierungsdateien hinzufügen und Skripts in der Sitzung ausführen.</span><span class="sxs-lookup"><span data-stu-id="67aba-135">The module can add commands, types and formatting files, and run scripts in the session.</span></span> <span data-ttu-id="67aba-136">Verwenden Sie die Preference-Variable, um das automatische Importieren von Modulen zu aktivieren, zu deaktivieren und zu konfigurieren `$PSModuleAutoLoadingPreference` .</span><span class="sxs-lookup"><span data-stu-id="67aba-136">To enable, disable, and configuration automatic importing of modules, use the `$PSModuleAutoLoadingPreference` preference variable.</span></span> <span data-ttu-id="67aba-137">Weitere Informationen finden Sie unter [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="67aba-137">For more information, see [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

### <span data-ttu-id="67aba-138">Beispiel 6: erhalten der Syntax eines Cmdlets</span><span class="sxs-lookup"><span data-stu-id="67aba-138">Example 6: Get the syntax of a cmdlet</span></span>

<span data-ttu-id="67aba-139">Dieser Befehl verwendet den Argument **List** -Parameter und den **Syntax** Parameter, um die Syntax des Cmdlets zu erhalten, `Get-ChildItem` Wenn es im CERT:-Laufwerk verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="67aba-139">This command uses the **ArgumentList** and **Syntax** parameters to get the syntax of the `Get-ChildItem` cmdlet when it is used in the Cert: drive.</span></span> <span data-ttu-id="67aba-140">Das Laufwerk "CERT:" ist ein PowerShell-Laufwerk, das der Zertifikat Anbieter der Sitzung hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="67aba-140">The Cert: drive is a PowerShell drive that the Certificate Provider adds to the session.</span></span>

```powershell
Get-Command  -Name Get-Childitem -Args Cert: -Syntax
```

<span data-ttu-id="67aba-141">Wenn Sie die in der Ausgabe angezeigte Syntax mit der Syntax vergleichen, die angezeigt wird, wenn Sie den **args** -Parameter (Argument **List**) weglassen, sehen Sie, dass der **Zertifikat Anbieter** dem Cmdlet einen dynamischen Parameter, **codeSigningCert**, hinzufügt `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="67aba-141">When you compare the syntax displayed in the output with the syntax that is displayed when you omit the **Args** (**ArgumentList**) parameter, you'll see that the **Certificate provider** adds a dynamic parameter, **CodeSigningCert**, to the `Get-ChildItem` cmdlet.</span></span>

<span data-ttu-id="67aba-142">Weitere Informationen zum Zertifikat Anbieter finden Sie unter [about_Certificate_Provider](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md).</span><span class="sxs-lookup"><span data-stu-id="67aba-142">For more information about the Certificate provider, see [about_Certificate_Provider](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md).</span></span>

### <span data-ttu-id="67aba-143">Beispiel 7: Get Dynamic Parameters</span><span class="sxs-lookup"><span data-stu-id="67aba-143">Example 7: Get dynamic parameters</span></span>

<span data-ttu-id="67aba-144">Der Befehl im Beispiel verwendet die- `Get-DynamicParameters` Funktion, um die dynamischen Parameter zu erhalten, die der Zertifikat Anbieter dem `Get-ChildItem` Cmdlet hinzufügt, wenn er im CERT:-Laufwerk verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="67aba-144">The command in the example uses the `Get-DynamicParameters` function to get the dynamic parameters that the Certificate provider adds to the `Get-ChildItem` cmdlet when it is used in the Cert: drive.</span></span>

```powershell
function Get-DynamicParameters
{
    param ($Cmdlet, $PSDrive)
    (Get-Command -Name $Cmdlet -ArgumentList $PSDrive).ParameterSets | ForEach-Object {$_.Parameters} | Where-Object { $_.IsDynamic } | Select-Object -Property Name -Unique
}
Get-DynamicParameters -Cmdlet Get-ChildItem -PSDrive Cert:
```

```Output
Name
----
CodeSigningCert
```

<span data-ttu-id="67aba-145">Die- `Get-DynamicParameters` Funktion in diesem Beispiel ruft die dynamischen Parameter eines Cmdlets ab.</span><span class="sxs-lookup"><span data-stu-id="67aba-145">The `Get-DynamicParameters` function in this example gets the dynamic parameters of a cmdlet.</span></span> <span data-ttu-id="67aba-146">Dies ist eine Alternative zu der Methode, die im vorherigen Beispiel verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="67aba-146">This is an alternative to the method used in the previous example.</span></span> <span data-ttu-id="67aba-147">Der dynamische Parameter kann durch andere Cmdlets oder einen Anbieter zu einem Cmdlet hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="67aba-147">Dynamic parameter can be added to a cmdlet by another cmdlet or a provider.</span></span>

### <span data-ttu-id="67aba-148">Beispiel 8: alle Befehle aller Typen erhalten</span><span class="sxs-lookup"><span data-stu-id="67aba-148">Example 8: Get all commands of all types</span></span>

<span data-ttu-id="67aba-149">Mit diesem Befehl werden alle Befehle aller Typen auf dem lokalen Computer abgerufen, einschließlich der ausführbaren Dateien in den Pfaden der **path** -Umgebungsvariablen ( `$env:path` ).</span><span class="sxs-lookup"><span data-stu-id="67aba-149">This command gets all commands of all types on the local computer, including executable files in the paths of the **Path** environment variable (`$env:path`).</span></span>

```powershell
Get-Command *
```

<span data-ttu-id="67aba-150">Der Befehl gibt ein **ApplicationInfo**-Objekt (System.Management.Automation.ApplicationInfo) für jede Datei und kein **FileInfo**-Objekt (System.IO.FileInfo) zurück.</span><span class="sxs-lookup"><span data-stu-id="67aba-150">It returns an **ApplicationInfo** object (System.Management.Automation.ApplicationInfo) for each file, not a **FileInfo** object (System.IO.FileInfo).</span></span>

### <span data-ttu-id="67aba-151">Beispiel 9: Cmdlets mithilfe eines Parameter namens und-Typs</span><span class="sxs-lookup"><span data-stu-id="67aba-151">Example 9: Get cmdlets by using a parameter name and type</span></span>

<span data-ttu-id="67aba-152">Dieser Befehl ruft Cmdlets ab, die über einen Parameter verfügen, dessen Name "auth" und dessen Typ " **authenticationmechanism**" ist.</span><span class="sxs-lookup"><span data-stu-id="67aba-152">This command gets cmdlets that have a parameter whose name includes Auth and whose type is **AuthenticationMechanism**.</span></span>

```powershell
Get-Command -ParameterName *Auth* -ParameterType AuthenticationMechanism
```

<span data-ttu-id="67aba-153">Verwenden Sie Befehle wie diesen, um nach Cmdlets zu suchen, mit denen Sie die Methode angeben können, die zum Authentifizieren des Benutzers verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="67aba-153">You can use a command like this one to find cmdlets that let you specify the method that is used to authenticate the user.</span></span>

<span data-ttu-id="67aba-154">Der **ParameterType**-Parameter unterscheidet Parameter, die einen **AuthenticationMechanism**-Wert akzeptieren, von Parametern, die einen **AuthenticationLevel**-Wert akzeptieren, selbst wenn sie ähnliche Namen haben.</span><span class="sxs-lookup"><span data-stu-id="67aba-154">The **ParameterType** parameter distinguishes parameters that take an **AuthenticationMechanism** value from those that take an **AuthenticationLevel** parameter, even when they have similar names.</span></span>

### <span data-ttu-id="67aba-155">Beispiel 10: Holen Sie sich einen Alias</span><span class="sxs-lookup"><span data-stu-id="67aba-155">Example 10: Get an alias</span></span>

<span data-ttu-id="67aba-156">In diesem Beispiel wird gezeigt, wie das `Get-Command` Cmdlet mit einem Alias verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="67aba-156">This example shows how to use the `Get-Command` cmdlet with an alias.</span></span>

```powershell
Get-Command -Name dir
```

```Output
CommandType     Name                                               ModuleName
-----------     ----                                               ----------
Alias           dir -> Get-ChildItem
```

<span data-ttu-id="67aba-157">Obwohl es in der Regel für Cmdlets und Funktionen verwendet wird, ruft `Get-Command` auch Skripts, Funktionen, Aliase und ausführbare Dateien ab.</span><span class="sxs-lookup"><span data-stu-id="67aba-157">Although it is typically used on cmdlets and functions, `Get-Command` also gets scripts, functions, aliases, and executable files.</span></span>

<span data-ttu-id="67aba-158">Die Befehlsausgabe zeigt die Ansicht des **Name**-Eigenschaftswerts für Aliase.</span><span class="sxs-lookup"><span data-stu-id="67aba-158">The output of the command shows the special view of the **Name** property value for aliases.</span></span> <span data-ttu-id="67aba-159">Die Ansicht zeigt den Alias und den vollständigen Befehlsnamen.</span><span class="sxs-lookup"><span data-stu-id="67aba-159">The view shows the alias and the full command name.</span></span>

### <span data-ttu-id="67aba-160">Beispiel 11: erhalten von Syntax aus einem Alias</span><span class="sxs-lookup"><span data-stu-id="67aba-160">Example 11: Get Syntax from an alias</span></span>

<span data-ttu-id="67aba-161">Dieses Beispiel zeigt, wie Sie die Syntax zusammen mit dem Standardnamen eines Alias erhalten.</span><span class="sxs-lookup"><span data-stu-id="67aba-161">This example shows how to get the syntax along with the standard name of an alias.</span></span>

<span data-ttu-id="67aba-162">Die Ausgabe des Befehls zeigt den bezeichneten Alias mit dem Standardnamen an, gefolgt von der Syntax.</span><span class="sxs-lookup"><span data-stu-id="67aba-162">The output of the command shows the labeled alias with the standard name, followed by the syntax.</span></span>

```powershell
Get-Command -Name dir -Syntax
```

```Output
dir (alias) -> Get-ChildItem

dir [[-Path] <string[]>] [[-Filter] <string>] [-Include <string[]>] [-Exclude <string[]>] [-Recurse] [-Depth <uint>] [-Force] [-Name] [-Attributes <FlagsExpression[FileAttributes]>] [-FollowSymlink] [-Directory] [-File] [-Hidden] [-ReadOnly] [-System] [<CommonParameters>]

dir [[-Filter] <string>] -LiteralPath <string[]> [-Include <string[]>] [-Exclude <string[]>] [-Recurse] [-Depth <uint>] [-Force] [-Name] [-Attributes <FlagsExpression[FileAttributes]>] [-FollowSymlink] [-Directory] [-File] [-Hidden] [-ReadOnly] [-System] [<CommonParameters>]
```

### <span data-ttu-id="67aba-163">Beispiel 12: alle Instanzen des Notepad-Befehls erhalten</span><span class="sxs-lookup"><span data-stu-id="67aba-163">Example 12: Get all instances of the Notepad command</span></span>

<span data-ttu-id="67aba-164">In diesem Beispiel wird der **all** -Parameter des `Get-Command` Cmdlets verwendet, um alle Instanzen des `Notepad` Befehls auf dem lokalen Computer anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="67aba-164">This example uses the **All** parameter of the `Get-Command` cmdlet to show all instances of the `Notepad` command on the local computer.</span></span>

```powershell
Get-Command Notepad -All | Format-Table CommandType, Name, Definition
```

```Output
CommandType     Name           Definition
-----------     ----           ----------
Application     notepad.exe    C:\WINDOWS\system32\notepad.exe
Application     NOTEPAD.EXE    C:\WINDOWS\NOTEPAD.EXE
```

<span data-ttu-id="67aba-165">Der **All**-Parameter ist nützlich, wenn es mehr als einen Befehl mit demselben Namen in der Sitzung gibt.</span><span class="sxs-lookup"><span data-stu-id="67aba-165">The **All** parameter is useful when there is more than one command with the same name in the session.</span></span>

<span data-ttu-id="67aba-166">Ab Windows PowerShell 3,0, wenn die Sitzung mehrere Befehle mit demselben Namen enthält, wird von nur der Befehl abgerufen, der ausgeführt wird, `Get-Command` Wenn Sie den Befehlsnamen eingeben.</span><span class="sxs-lookup"><span data-stu-id="67aba-166">Beginning in Windows PowerShell 3.0, by default, when the session includes multiple commands with the same name, `Get-Command` gets only the command that runs when you type the command name.</span></span> <span data-ttu-id="67aba-167">Mit dem **all** -Parameter ruft `Get-Command` alle Befehle mit dem angegebenen Namen ab und gibt Sie in der Ausführungs Rangfolge zurück.</span><span class="sxs-lookup"><span data-stu-id="67aba-167">With the **All** parameter, `Get-Command` gets all commands with the specified name and returns them in execution precedence order.</span></span> <span data-ttu-id="67aba-168">Um einen anderen Befehl als den ersten in der Liste auszuführen, geben Sie den vollqualifizierten Pfad zu dem Befehl ein.</span><span class="sxs-lookup"><span data-stu-id="67aba-168">To run a command other than the first one in the list, type the fully qualified path to the command.</span></span>

<span data-ttu-id="67aba-169">Weitere Informationen zur Befehls Rangfolge finden Sie unter [about_Command_Precedence](About/about_Command_Precedence.md).</span><span class="sxs-lookup"><span data-stu-id="67aba-169">For more information about command precedence, see [about_Command_Precedence](About/about_Command_Precedence.md).</span></span>

### <span data-ttu-id="67aba-170">Beispiel 13: Holen Sie sich den Namen eines Moduls, das ein Cmdlet enthält.</span><span class="sxs-lookup"><span data-stu-id="67aba-170">Example 13: Get the name of a module that contains a cmdlet</span></span>

<span data-ttu-id="67aba-171">Mit diesem Befehl wird der Name des Moduls abgerufen, von dem das `Get-Date` Cmdlet stammt.</span><span class="sxs-lookup"><span data-stu-id="67aba-171">This command gets the name of the module in which the `Get-Date` cmdlet originated.</span></span>
<span data-ttu-id="67aba-172">Der Befehl verwendet die **ModuleName**-Eigenschaft aller Befehle.</span><span class="sxs-lookup"><span data-stu-id="67aba-172">The command uses the **ModuleName** property of all commands.</span></span>

```powershell
(Get-Command Get-Date).ModuleName
```

```Output
Microsoft.PowerShell.Utility
```

<span data-ttu-id="67aba-173">Dieses Befehls Format funktioniert mit Befehlen in PowerShell-Modulen, auch wenn Sie nicht in die Sitzung importiert werden.</span><span class="sxs-lookup"><span data-stu-id="67aba-173">This command format works on commands in PowerShell modules, even if they are not imported into the session.</span></span>

### <span data-ttu-id="67aba-174">Beispiel 14: Cmdlets und Funktionen mit einem Ausgabetyp</span><span class="sxs-lookup"><span data-stu-id="67aba-174">Example 14: Get cmdlets and functions that have an output type</span></span>

```powershell
Get-Command -Type Cmdlet | Where-Object OutputType | Format-List -Property Name, OutputType
```

<span data-ttu-id="67aba-175">Dieser Befehl ruft die Cmdlets und Funktionen ab, die über einen Ausgabetyp verfügen, und den Typ der Objekte, die sie zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="67aba-175">This command gets the cmdlets and functions that have an output type and the type of objects that they return.</span></span>

<span data-ttu-id="67aba-176">Der erste Teil des Befehls ruft alle Cmdlets ab.</span><span class="sxs-lookup"><span data-stu-id="67aba-176">The first part of the command gets all cmdlets.</span></span> <span data-ttu-id="67aba-177">Ein Pipeline Operator ( `|` ) sendet die Cmdlets an das `Where-Object` Cmdlet, das nur diejenigen auswählt, in denen die **OutputType** -Eigenschaft aufgefüllt ist.</span><span class="sxs-lookup"><span data-stu-id="67aba-177">A pipeline operator (`|`) sends the cmdlets to the `Where-Object` cmdlet, which selects only the ones in which the **OutputType** property is populated.</span></span> <span data-ttu-id="67aba-178">Ein weiterer Pipeline Operator sendet die ausgewählten Cmdlet-Objekte an das `Format-List` Cmdlet, das den Namen und den Ausgabetyp der einzelnen Cmdlets in einer Liste anzeigt.</span><span class="sxs-lookup"><span data-stu-id="67aba-178">Another pipeline operator sends the selected cmdlet objects to the `Format-List` cmdlet, which displays the name and output type of each cmdlet in a list.</span></span>

<span data-ttu-id="67aba-179">Die **OutputType**-Eigenschaft eines **CommandInfo**-Objekts hat nur dann einen Nicht-Null-Wert, wenn der Cmdlet-Code das **OutputType**-Attribut für das Cmdlet definiert.</span><span class="sxs-lookup"><span data-stu-id="67aba-179">The **OutputType** property of a **CommandInfo** object has a non-null value only when the cmdlet code defines the **OutputType** attribute for the cmdlet.</span></span>

### <span data-ttu-id="67aba-180">Beispiel 15: Get-Cmdlets, die einen bestimmten Objekttyp als Eingabe annehmen</span><span class="sxs-lookup"><span data-stu-id="67aba-180">Example 15: Get cmdlets that take a specific object type as input</span></span>

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

<span data-ttu-id="67aba-181">Mit diesem Befehl wird nach Cmdlets gesucht, die Netzwerkadapterobjekte als Eingabe akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="67aba-181">This command finds cmdlets that take net adapter objects as input.</span></span> <span data-ttu-id="67aba-182">Verwenden Sie dieses Befehlsformat, um nach den Cmdlets zu suchen, die den Typ von Objekten akzeptieren, die ein beliebiger Befehl zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="67aba-182">You can use this command format to find the cmdlets that accept the type of objects that any command returns.</span></span>

<span data-ttu-id="67aba-183">Der Befehl verwendet die systeminterne Eigenschaft aller Objekte **PSTypeNames**, die die Typen abruft, die das Objekt beschreiben.</span><span class="sxs-lookup"><span data-stu-id="67aba-183">The command uses the **PSTypeNames** intrinsic property of all objects, which gets the types that describe the object.</span></span> <span data-ttu-id="67aba-184">Zum Abrufen der **PSTypeNames**-Eigenschaft eines Netzwerkadapters und nicht der **PSTypeNames**-Eigenschaft einer Auflistung von Netzwerkadaptern verwendet der Befehl die Arraynotation, um den ersten Netzwerkadapter abzurufen, den das Cmdlet zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="67aba-184">To get the **PSTypeNames** property of a net adapter, and not the **PSTypeNames** property of a collection of net adapters, the command uses array notation to get the first net adapter that the cmdlet returns.</span></span>

### <span data-ttu-id="67aba-185">Beispiel 16: Get-Befehle mithilfe einer Fuzzyübereinstimmung</span><span class="sxs-lookup"><span data-stu-id="67aba-185">Example 16: Get commands using a fuzzy match</span></span>

<span data-ttu-id="67aba-186">In diesem Beispiel weist der Name des Befehls absichtlich einen Tippfehler als ' Get-commnd ' auf.</span><span class="sxs-lookup"><span data-stu-id="67aba-186">In this example, the name of the command deliberately has a typo as 'get-commnd'.</span></span>
<span data-ttu-id="67aba-187">Mithilfe des- `-UseFuzzyMatching` Schalters hat das Cmdlet ermittelt, dass die beste Entsprechung `Get-Command` von anderen systemeigenen Befehlen auf dem System gefolgt ist, die eine ähnliche Entsprechung hatten.</span><span class="sxs-lookup"><span data-stu-id="67aba-187">Using the `-UseFuzzyMatching` switch, the cmdlet determined that the best match was `Get-Command` followed by other native commands on the system that were a similar match.</span></span>

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

## <span data-ttu-id="67aba-188">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="67aba-188">PARAMETERS</span></span>

### <span data-ttu-id="67aba-189">-All</span><span class="sxs-lookup"><span data-stu-id="67aba-189">-All</span></span>

<span data-ttu-id="67aba-190">Gibt an, dass dieses Cmdlet alle Befehle abruft, einschließlich Befehlen desselben Typs, die denselben Namen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="67aba-190">Indicates that this cmdlet gets all commands, including commands of the same type that have the same name.</span></span> <span data-ttu-id="67aba-191">Standardmäßig ruft `Get-Command` nur die Befehle ab, die ausgeführt werden, wenn Sie den Befehlsnamen eingeben.</span><span class="sxs-lookup"><span data-stu-id="67aba-191">By default, `Get-Command` gets only the commands that run when you type the command name.</span></span>

<span data-ttu-id="67aba-192">Weitere Informationen zu der Methode, die von PowerShell verwendet wird, um den Befehl auszuwählen, der ausgeführt werden soll, wenn mehrere Befehle denselben Namen aufweisen, finden Sie unter [about_Command_Precedence](About/about_Command_Precedence.md).</span><span class="sxs-lookup"><span data-stu-id="67aba-192">For more information about the method that PowerShell uses to select the command to run when multiple commands have the same name, see [about_Command_Precedence](About/about_Command_Precedence.md).</span></span>
<span data-ttu-id="67aba-193">Informationen zu Modul qualifizierten Befehlsnamen und zum Ausführen von Befehlen, die aufgrund eines Namens Konflikts nicht standardmäßig ausgeführt werden, finden Sie unter [about_Modules](About/about_Modules.md).</span><span class="sxs-lookup"><span data-stu-id="67aba-193">For information about module-qualified command names and running commands that do not run by default because of a name conflict, see [about_Modules](About/about_Modules.md).</span></span>

<span data-ttu-id="67aba-194">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="67aba-194">This parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="67aba-195">In Windows PowerShell 2,0 ruft `Get-Command` standardmäßig alle Befehle ab.</span><span class="sxs-lookup"><span data-stu-id="67aba-195">In Windows PowerShell 2.0, `Get-Command` gets all commands by default.</span></span>

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

### <span data-ttu-id="67aba-196">-Argumentlist</span><span class="sxs-lookup"><span data-stu-id="67aba-196">-ArgumentList</span></span>

<span data-ttu-id="67aba-197">Gibt ein Array von Argumenten an.</span><span class="sxs-lookup"><span data-stu-id="67aba-197">Specifies an array of arguments.</span></span> <span data-ttu-id="67aba-198">Dieses Cmdlet ruft Informationen zu einem Cmdlet oder einer Funktion ab, wenn es mit den angegebenen Parametern ("Argumenten") verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="67aba-198">This cmdlet gets information about a cmdlet or function when it is used with the specified parameters ("arguments").</span></span> <span data-ttu-id="67aba-199">Der Alias für **ArgumentList** ist **Args**.</span><span class="sxs-lookup"><span data-stu-id="67aba-199">The alias for **ArgumentList** is **Args**.</span></span>

<span data-ttu-id="67aba-200">Um dynamische Parameter zu ermitteln, die nur verfügbar sind, wenn bestimmte andere Parameter verwendet werden, legen Sie den Wert von Argument **List** auf die Parameter fest, die die dynamischen Parameter auslöst.</span><span class="sxs-lookup"><span data-stu-id="67aba-200">To detect dynamic parameters that are available only when certain other parameters are used, set the value of **ArgumentList** to the parameters that trigger the dynamic parameters.</span></span>

<span data-ttu-id="67aba-201">Um die dynamischen Parameter zu ermitteln, die ein Anbieter zu einem Cmdlet hinzufügt, legen Sie den Wert des **argumentlist** -Parameters auf einen Pfad im Anbieter Laufwerk fest, z. b. WSMAN:, HKLM: oder CERT:.</span><span class="sxs-lookup"><span data-stu-id="67aba-201">To detect the dynamic parameters that a provider adds to a cmdlet, set the value of the **ArgumentList** parameter to a path in the provider drive, such as WSMan:, HKLM:, or Cert:.</span></span> <span data-ttu-id="67aba-202">Wenn es sich bei dem Befehl um ein PowerShell-Anbieter-Cmdlet handelt, geben Sie in jedem Befehl nur einen Pfad ein.</span><span class="sxs-lookup"><span data-stu-id="67aba-202">When the command is a PowerShell provider cmdlet, enter only one path in each command.</span></span> <span data-ttu-id="67aba-203">Die Anbieter-Cmdlets geben nur die dynamischen Parameter für den ersten Pfad den Wert von **argumentlist** zurück.</span><span class="sxs-lookup"><span data-stu-id="67aba-203">The provider cmdlets return only the dynamic parameters for the first path the value of **ArgumentList**.</span></span> <span data-ttu-id="67aba-204">Weitere Informationen zu den Anbieter-Cmdlets finden Sie unter [about_Providers](About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="67aba-204">For information about the provider cmdlets, see [about_Providers](About/about_Providers.md).</span></span>

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

### <span data-ttu-id="67aba-205">-CommandType</span><span class="sxs-lookup"><span data-stu-id="67aba-205">-CommandType</span></span>

<span data-ttu-id="67aba-206">Gibt die Typen von Befehlen an, die von diesem Cmdlet abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="67aba-206">Specifies the types of commands that this cmdlet gets.</span></span> <span data-ttu-id="67aba-207">Geben Sie einen oder mehrere Befehlstypen ein.</span><span class="sxs-lookup"><span data-stu-id="67aba-207">Enter one or more command types.</span></span> <span data-ttu-id="67aba-208">Verwenden Sie **CommandType** oder dessen Aliasname **Type**.</span><span class="sxs-lookup"><span data-stu-id="67aba-208">Use **CommandType** or its alias, **Type**.</span></span> <span data-ttu-id="67aba-209">Standardmäßig `Get-Command` Ruft alle-Cmdlets,-Funktionen und-Aliase ab.</span><span class="sxs-lookup"><span data-stu-id="67aba-209">By default, `Get-Command` gets all cmdlets, functions, and aliases.</span></span>

<span data-ttu-id="67aba-210">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="67aba-210">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="67aba-211">Alias.</span><span class="sxs-lookup"><span data-stu-id="67aba-211">Alias.</span></span> <span data-ttu-id="67aba-212">Ruft die Aliase aller PowerShell-Befehle ab.</span><span class="sxs-lookup"><span data-stu-id="67aba-212">Gets the aliases of all PowerShell commands.</span></span> <span data-ttu-id="67aba-213">Weitere Informationen finden Sie unter [about_Aliases](About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="67aba-213">For more information, see [about_Aliases](About/about_Aliases.md).</span></span>
- <span data-ttu-id="67aba-214">Alle</span><span class="sxs-lookup"><span data-stu-id="67aba-214">All.</span></span> <span data-ttu-id="67aba-215">Ruft alle Befehlstypen ab.</span><span class="sxs-lookup"><span data-stu-id="67aba-215">Gets all command types.</span></span> <span data-ttu-id="67aba-216">Dieser Parameterwert entspricht `Get-Command *` .</span><span class="sxs-lookup"><span data-stu-id="67aba-216">This parameter value is the equivalent of `Get-Command *`.</span></span>
- <span data-ttu-id="67aba-217">Anwendung:</span><span class="sxs-lookup"><span data-stu-id="67aba-217">Application.</span></span> <span data-ttu-id="67aba-218">Ruft nicht-PowerShell-Dateien in Pfaden ab, die in der **path** -Umgebungsvariablen ($env:p ATH) aufgelistet sind, einschließlich. txt-,. exe-und. dll-Dateien.</span><span class="sxs-lookup"><span data-stu-id="67aba-218">Gets non-PowerShell files in paths listed in the **Path** environment variable ($env:path), including .txt, .exe, and .dll files.</span></span> <span data-ttu-id="67aba-219">Weitere Informationen zur **path** -Umgebungsvariablen finden Sie unter about_Environment_Variables.</span><span class="sxs-lookup"><span data-stu-id="67aba-219">For more information about the **Path** environment variable, see about_Environment_Variables.</span></span>
- <span data-ttu-id="67aba-220">Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="67aba-220">Cmdlet.</span></span> <span data-ttu-id="67aba-221">Ruft alle Cmdlets ab.</span><span class="sxs-lookup"><span data-stu-id="67aba-221">Gets all cmdlets.</span></span>
- <span data-ttu-id="67aba-222">Externalscript.</span><span class="sxs-lookup"><span data-stu-id="67aba-222">ExternalScript.</span></span> <span data-ttu-id="67aba-223">Ruft alle PS1-Dateien in den Pfaden ab, die in der **Path**-Umgebungsvariablen ($env:path) aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="67aba-223">Gets all .ps1 files in the paths listed in the **Path** environment variable ($env:path).</span></span>
- <span data-ttu-id="67aba-224">Filter und function.</span><span class="sxs-lookup"><span data-stu-id="67aba-224">Filter and Function.</span></span> <span data-ttu-id="67aba-225">Ruft alle erweiterten und einfachen PowerShell-Funktionen und-Filter ab.</span><span class="sxs-lookup"><span data-stu-id="67aba-225">Gets all PowerShell advanced and simple functions and filters.</span></span>
- <span data-ttu-id="67aba-226">Skript.</span><span class="sxs-lookup"><span data-stu-id="67aba-226">Script.</span></span> <span data-ttu-id="67aba-227">Ruft alle Skriptblöcke ab.</span><span class="sxs-lookup"><span data-stu-id="67aba-227">Gets all script blocks.</span></span> <span data-ttu-id="67aba-228">Um PowerShell-Skripts (PS1-Dateien) zu erhalten, verwenden Sie den externalscript-Wert.</span><span class="sxs-lookup"><span data-stu-id="67aba-228">To get PowerShell scripts (.ps1 files), use the ExternalScript value.</span></span>

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

### <span data-ttu-id="67aba-229">-Fullyqualifiedmodule</span><span class="sxs-lookup"><span data-stu-id="67aba-229">-FullyQualifiedModule</span></span>

<span data-ttu-id="67aba-230">Gibt Module an, deren Namen in Form von **modulespecification** -Objekten angegeben sind, die im Abschnitt " **Hinweise** " des [modulespecification-Konstruktors (Hash Tabelle)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor?view=powershellsdk-1.1.0#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_)beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="67aba-230">Specifies modules with names that are specified in the form of **ModuleSpecification** objects, described in the **Remarks** section of [ModuleSpecification Constructor (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor?view=powershellsdk-1.1.0#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).</span></span>
<span data-ttu-id="67aba-231">Der **fullyqualifiedmodule** -Parameter akzeptiert z. b. einen Modulnamen, der in einem der folgenden Formate angegeben ist:</span><span class="sxs-lookup"><span data-stu-id="67aba-231">For example, the **FullyQualifiedModule** parameter accepts a module name that is specified in one of the following formats:</span></span>

- `@{ModuleName = "modulename"; ModuleVersion = "version_number"}`
- `@{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}`

<span data-ttu-id="67aba-232">**ModuleName** und **ModuleVersion** sind erforderlich, aber **Guid** ist optional.</span><span class="sxs-lookup"><span data-stu-id="67aba-232">**ModuleName** and **ModuleVersion** are required, but **Guid** is optional.</span></span>

<span data-ttu-id="67aba-233">Sie können den **fullyqualifiedmodule** -Parameter nicht im selben Befehl wie einen **Modul** Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="67aba-233">You cannot specify the **FullyQualifiedModule** parameter in the same command as a **Module** parameter.</span></span> <span data-ttu-id="67aba-234">Die beiden Parameter schließen sich gegenseitig aus.</span><span class="sxs-lookup"><span data-stu-id="67aba-234">The two parameters are mutually exclusive.</span></span>

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

### <span data-ttu-id="67aba-235">-Listimportiert</span><span class="sxs-lookup"><span data-stu-id="67aba-235">-ListImported</span></span>

<span data-ttu-id="67aba-236">Gibt an, dass dieses Cmdlet nur Befehle in der aktuellen Sitzung abruft.</span><span class="sxs-lookup"><span data-stu-id="67aba-236">Indicates that this cmdlet gets only commands in the current session.</span></span>

<span data-ttu-id="67aba-237">Ab PowerShell 3,0 ruft standardmäßig `Get-Command` alle installierten Befehle ab, einschließlich, aber nicht beschränkt auf die Befehle in der aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="67aba-237">Starting in PowerShell 3.0, by default, `Get-Command` gets all installed commands, including, but not limited to, the commands in the current session.</span></span> <span data-ttu-id="67aba-238">In PowerShell 2,0 werden nur Befehle in der aktuellen Sitzung abgerufen.</span><span class="sxs-lookup"><span data-stu-id="67aba-238">In PowerShell 2.0, it gets only commands in the current session.</span></span>

<span data-ttu-id="67aba-239">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="67aba-239">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="67aba-240">-Modul</span><span class="sxs-lookup"><span data-stu-id="67aba-240">-Module</span></span>

<span data-ttu-id="67aba-241">Gibt ein Array von Modulen an.</span><span class="sxs-lookup"><span data-stu-id="67aba-241">Specifies an array of modules.</span></span> <span data-ttu-id="67aba-242">Dieses Cmdlet ruft die Befehle ab, die von den angegebenen Modulen stammen.</span><span class="sxs-lookup"><span data-stu-id="67aba-242">This cmdlet gets the commands that came from the specified modules.</span></span>
<span data-ttu-id="67aba-243">Geben Sie die Namen der Module oder Modul Objekte ein.</span><span class="sxs-lookup"><span data-stu-id="67aba-243">Enter the names of modules or module objects.</span></span>

<span data-ttu-id="67aba-244">Dieser Parameter nimmt Zeichen folgen Werte an, aber der Wert dieses Parameters kann auch ein **psmoduleinfo** -Objekt sein, z. b. die Objekte, die von den `Get-Module` -und- `Import-PSSession` Cmdlets zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="67aba-244">This parameter takes string values, but the value of this parameter can also be a **PSModuleInfo** object, such as the objects that the `Get-Module` and `Import-PSSession` cmdlets return.</span></span>

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

### <span data-ttu-id="67aba-245">-Name</span><span class="sxs-lookup"><span data-stu-id="67aba-245">-Name</span></span>

<span data-ttu-id="67aba-246">Gibt ein Array von Namen an.</span><span class="sxs-lookup"><span data-stu-id="67aba-246">Specifies an array of names.</span></span> <span data-ttu-id="67aba-247">Dieses Cmdlet ruft nur Befehle mit dem angegebenen Namen ab.</span><span class="sxs-lookup"><span data-stu-id="67aba-247">This cmdlet gets only commands that have the specified name.</span></span> <span data-ttu-id="67aba-248">Geben Sie einen Namen oder ein Namensmuster ein.</span><span class="sxs-lookup"><span data-stu-id="67aba-248">Enter a name or name pattern.</span></span> <span data-ttu-id="67aba-249">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="67aba-249">Wildcard characters are permitted.</span></span>

<span data-ttu-id="67aba-250">Um Befehle abzurufen, die den gleichen Namen haben, verwenden Sie den **All**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="67aba-250">To get commands that have the same name, use the **All** parameter.</span></span> <span data-ttu-id="67aba-251">Wenn zwei Befehle denselben Namen haben, ruft standardmäßig den Befehl ab, der ausgeführt wird, `Get-Command` Wenn Sie den Befehlsnamen eingeben.</span><span class="sxs-lookup"><span data-stu-id="67aba-251">When two commands have the same name, by default, `Get-Command` gets the command that runs when you type the command name.</span></span>

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

### <span data-ttu-id="67aba-252">-Substantiv</span><span class="sxs-lookup"><span data-stu-id="67aba-252">-Noun</span></span>

<span data-ttu-id="67aba-253">Gibt ein Array von Befehls-nouns an.</span><span class="sxs-lookup"><span data-stu-id="67aba-253">Specifies an array of command nouns.</span></span> <span data-ttu-id="67aba-254">Dieses Cmdlet ruft die Befehle ab, die Cmdlets, Funktionen und Aliase enthalten, deren Namen das angegebene Substantiv enthalten.</span><span class="sxs-lookup"><span data-stu-id="67aba-254">This cmdlet gets commands, which include cmdlets, functions, and aliases, that have names that include the specified noun.</span></span> <span data-ttu-id="67aba-255">Geben Sie ein oder mehrere Nomen oder Nomenmuster ein.</span><span class="sxs-lookup"><span data-stu-id="67aba-255">Enter one or more nouns or noun patterns.</span></span> <span data-ttu-id="67aba-256">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="67aba-256">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="67aba-257">-Parameter Name</span><span class="sxs-lookup"><span data-stu-id="67aba-257">-ParameterName</span></span>

<span data-ttu-id="67aba-258">Gibt ein Array von Parameternamen an.</span><span class="sxs-lookup"><span data-stu-id="67aba-258">Specifies an array of parameter names.</span></span> <span data-ttu-id="67aba-259">Dieses Cmdlet ruft die Befehle in der Sitzung ab, die über die angegebenen Parameter verfügen.</span><span class="sxs-lookup"><span data-stu-id="67aba-259">This cmdlet gets commands in the session that have the specified parameters.</span></span> <span data-ttu-id="67aba-260">Geben Sie Parameternamen oder Parameter Aliase ein.</span><span class="sxs-lookup"><span data-stu-id="67aba-260">Enter parameter names or parameter aliases.</span></span> <span data-ttu-id="67aba-261">Platzhalterzeichen werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="67aba-261">Wildcard characters are supported.</span></span>

<span data-ttu-id="67aba-262">Die Parameter **ParameterName** und **ParameterType** suchen nur Befehle in der aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="67aba-262">The **ParameterName** and **ParameterType** parameters search only commands in the current session.</span></span>

<span data-ttu-id="67aba-263">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="67aba-263">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="67aba-264">-ParameterType</span><span class="sxs-lookup"><span data-stu-id="67aba-264">-ParameterType</span></span>

<span data-ttu-id="67aba-265">Gibt ein Array von Parameternamen an.</span><span class="sxs-lookup"><span data-stu-id="67aba-265">Specifies an array of parameter names.</span></span> <span data-ttu-id="67aba-266">Dieses Cmdlet ruft die Befehle in der Sitzung ab, die Parameter des angegebenen Typs aufweisen.</span><span class="sxs-lookup"><span data-stu-id="67aba-266">This cmdlet gets commands in the session that have parameters of the specified type.</span></span> <span data-ttu-id="67aba-267">Geben Sie den vollständigen Namen oder Teilnamen eines Parametertyps ein.</span><span class="sxs-lookup"><span data-stu-id="67aba-267">Enter the full name or partial name of a parameter type.</span></span> <span data-ttu-id="67aba-268">Platzhalterzeichen werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="67aba-268">Wildcard characters are supported.</span></span>

<span data-ttu-id="67aba-269">Die Parameter **ParameterName** und **ParameterType** suchen nur Befehle in der aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="67aba-269">The **ParameterName** and **ParameterType** parameters search only commands in the current session.</span></span>

<span data-ttu-id="67aba-270">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="67aba-270">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="67aba-271">-Showcommandinfo</span><span class="sxs-lookup"><span data-stu-id="67aba-271">-ShowCommandInfo</span></span>

<span data-ttu-id="67aba-272">Gibt an, dass dieses Cmdlet Befehls Informationen anzeigt.</span><span class="sxs-lookup"><span data-stu-id="67aba-272">Indicates that this cmdlet displays command information.</span></span>

<span data-ttu-id="67aba-273">Dieser Parameter wurde in Windows PowerShell 5,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="67aba-273">This parameter was introduced in Windows PowerShell 5.0.</span></span>

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

### <span data-ttu-id="67aba-274">-Syntax</span><span class="sxs-lookup"><span data-stu-id="67aba-274">-Syntax</span></span>

<span data-ttu-id="67aba-275">Gibt an, dass dieses Cmdlet nur die folgenden angegebenen Daten über den Befehl abruft:</span><span class="sxs-lookup"><span data-stu-id="67aba-275">Indicates that this cmdlet gets only the following specified data about the command:</span></span>

- <span data-ttu-id="67aba-276">Aliase.</span><span class="sxs-lookup"><span data-stu-id="67aba-276">Aliases.</span></span> <span data-ttu-id="67aba-277">Ruft den Standardnamen und die-Syntax ab.</span><span class="sxs-lookup"><span data-stu-id="67aba-277">Gets the standard name and syntax.</span></span>
- <span data-ttu-id="67aba-278">Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="67aba-278">Cmdlets.</span></span> <span data-ttu-id="67aba-279">Ruft die Syntax ab.</span><span class="sxs-lookup"><span data-stu-id="67aba-279">Gets the syntax.</span></span>
- <span data-ttu-id="67aba-280">Funktionen und Filter.</span><span class="sxs-lookup"><span data-stu-id="67aba-280">Functions and filters.</span></span> <span data-ttu-id="67aba-281">Ruft die Funktionsdefinition ab.</span><span class="sxs-lookup"><span data-stu-id="67aba-281">Gets the function definition.</span></span>
- <span data-ttu-id="67aba-282">Skripts und Anwendungen oder Dateien.</span><span class="sxs-lookup"><span data-stu-id="67aba-282">Scripts and applications or files.</span></span> <span data-ttu-id="67aba-283">Ruft den Pfad und Dateinamen ab.</span><span class="sxs-lookup"><span data-stu-id="67aba-283">Gets the path and filename.</span></span>

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

### <span data-ttu-id="67aba-284">-TotalCount</span><span class="sxs-lookup"><span data-stu-id="67aba-284">-TotalCount</span></span>

<span data-ttu-id="67aba-285">Gibt die Anzahl der auszuführenden Befehle an.</span><span class="sxs-lookup"><span data-stu-id="67aba-285">Specifies the number of commands to get.</span></span> <span data-ttu-id="67aba-286">Mit diesem Parameter können Sie die Ausgabe eines Befehls beschränken.</span><span class="sxs-lookup"><span data-stu-id="67aba-286">You can use this parameter to limit the output of a command.</span></span>

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

### <span data-ttu-id="67aba-287">-Useabationweiterung</span><span class="sxs-lookup"><span data-stu-id="67aba-287">-UseAbbreviationExpansion</span></span>

<span data-ttu-id="67aba-288">Gibt an, dass die Zeichen im Befehl mit einem übereinstimmenden Zeichen in einem Befehl gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="67aba-288">Indicates using matching of the characters in the command to find with uppercase characters in a command.</span></span> <span data-ttu-id="67aba-289">Beispielsweise `i-psdf` würde übereinstimmen, `Import-PowerShellDataFile` Wenn jedes der zu suchenden Zeichen mit einem Großbuchstaben im Ergebnis übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="67aba-289">For example, `i-psdf` would match `Import-PowerShellDataFile` as each of the characters to find matches an uppercase character in the result.</span></span> <span data-ttu-id="67aba-290">Wenn diese Art der Übereinstimmung verwendet wird, ergeben alle Platzhalter keine Übereinstimmungen.</span><span class="sxs-lookup"><span data-stu-id="67aba-290">When using this type of match, any wildcards will result in no matches.</span></span>

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

### <span data-ttu-id="67aba-291">-Usefuzzymatching</span><span class="sxs-lookup"><span data-stu-id="67aba-291">-UseFuzzyMatching</span></span>

<span data-ttu-id="67aba-292">Gibt die Verwendung eines Fuzzyübereinstimmungs Algorithmus beim Suchen von Befehlen</span><span class="sxs-lookup"><span data-stu-id="67aba-292">Indicates using a fuzzy matching algorithm when finding commands.</span></span> <span data-ttu-id="67aba-293">Die Reihenfolge der Ausgabe ist von der nächsten Übereinstimmung bis zum wahrscheinlichsten Abgleich.</span><span class="sxs-lookup"><span data-stu-id="67aba-293">The order of the output is from closest match to least likely match.</span></span> <span data-ttu-id="67aba-294">Platzhalter sollten nicht mit Fuzzyübereinstimmung verwendet werden, da versucht wird, Befehle abzugleichen, die möglicherweise diese Platzhalter Zeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="67aba-294">Wildcards should not be used with fuzzy matching as it will attempt to match commands that may contain those wildcard characters.</span></span>

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

### <span data-ttu-id="67aba-295">-Verb</span><span class="sxs-lookup"><span data-stu-id="67aba-295">-Verb</span></span>

<span data-ttu-id="67aba-296">Gibt ein Array von Befehls Verben an.</span><span class="sxs-lookup"><span data-stu-id="67aba-296">Specifies an array of command verbs.</span></span> <span data-ttu-id="67aba-297">Dieses Cmdlet ruft die Befehle ab, die Cmdlets, Funktionen und Aliase enthalten, deren Namen das angegebene Verb enthalten.</span><span class="sxs-lookup"><span data-stu-id="67aba-297">This cmdlet gets commands, which include cmdlets, functions, and aliases, that have names that include the specified verb.</span></span> <span data-ttu-id="67aba-298">Geben Sie ein oder mehrere Verben oder Verbmuster ein.</span><span class="sxs-lookup"><span data-stu-id="67aba-298">Enter one or more verbs or verb patterns.</span></span> <span data-ttu-id="67aba-299">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="67aba-299">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="67aba-300">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="67aba-300">CommonParameters</span></span>

<span data-ttu-id="67aba-301">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="67aba-301">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="67aba-302">Weitere Informationen findest du unter [about_CommonParameters](About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="67aba-302">For more information, see [about_CommonParameters](About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="67aba-303">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="67aba-303">INPUTS</span></span>

### <span data-ttu-id="67aba-304">System.String</span><span class="sxs-lookup"><span data-stu-id="67aba-304">System.String</span></span>

<span data-ttu-id="67aba-305">Sie können Befehlsnamen an dieses Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="67aba-305">You can pipe command names to this cmdlet.</span></span>

## <span data-ttu-id="67aba-306">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="67aba-306">OUTPUTS</span></span>

### <span data-ttu-id="67aba-307">System. Management. Automation. CommandInfo</span><span class="sxs-lookup"><span data-stu-id="67aba-307">System.Management.Automation.CommandInfo</span></span>

<span data-ttu-id="67aba-308">Dieses Cmdlet gibt Objekte zurück, die von der **CommandInfo** -Klasse abgeleitet wurden.</span><span class="sxs-lookup"><span data-stu-id="67aba-308">This cmdlet returns objects derived from the **CommandInfo** class.</span></span> <span data-ttu-id="67aba-309">Der Typ des Objekts, das zurückgegeben wird, hängt vom Typ des Befehls ab, der abgerufen wird `Get-Command` .</span><span class="sxs-lookup"><span data-stu-id="67aba-309">The type of object that is returned depends on the type of command that `Get-Command` gets.</span></span>

### <span data-ttu-id="67aba-310">System. Management. Automation. AliasInfo</span><span class="sxs-lookup"><span data-stu-id="67aba-310">System.Management.Automation.AliasInfo</span></span>

<span data-ttu-id="67aba-311">Stellt Aliase dar.</span><span class="sxs-lookup"><span data-stu-id="67aba-311">Represents aliases.</span></span>

### <span data-ttu-id="67aba-312">System. Management. Automation. ApplicationInfo</span><span class="sxs-lookup"><span data-stu-id="67aba-312">System.Management.Automation.ApplicationInfo</span></span>

<span data-ttu-id="67aba-313">Stellt Anwendungen und Dateien dar.</span><span class="sxs-lookup"><span data-stu-id="67aba-313">Represents applications and files.</span></span>

### <span data-ttu-id="67aba-314">System. Management. Automation. cmdletinfo</span><span class="sxs-lookup"><span data-stu-id="67aba-314">System.Management.Automation.CmdletInfo</span></span>

<span data-ttu-id="67aba-315">Stellt Cmdlets dar.</span><span class="sxs-lookup"><span data-stu-id="67aba-315">Represents cmdlets.</span></span>

### <span data-ttu-id="67aba-316">System. Management. Automation. functioninfo</span><span class="sxs-lookup"><span data-stu-id="67aba-316">System.Management.Automation.FunctionInfo</span></span>

<span data-ttu-id="67aba-317">Stellt Funktionen und Filter dar.</span><span class="sxs-lookup"><span data-stu-id="67aba-317">Represents functions and filters.</span></span>

## <span data-ttu-id="67aba-318">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="67aba-318">NOTES</span></span>

* <span data-ttu-id="67aba-319">Wenn mehr als ein Befehl mit demselben Namen für die Sitzung verfügbar ist, `Get-Command` gibt den Befehl zurück, der ausgeführt wird, wenn Sie den Befehlsnamen eingeben.</span><span class="sxs-lookup"><span data-stu-id="67aba-319">When more than one command that has the same name is available to the session, `Get-Command` returns the command that runs when you type the command name.</span></span> <span data-ttu-id="67aba-320">Verwenden Sie den **all** -Parameter, um Befehle mit dem gleichen Namen, die in der Reihenfolge der Bestellung aufgeführt sind, zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="67aba-320">To get commands that have the same name, listed in run order, use the **All** parameter.</span></span> <span data-ttu-id="67aba-321">Weitere Informationen finden Sie unter [about_Command_Precedence](../Microsoft.PowerShell.Core/About/about_Command_Precedence.md).</span><span class="sxs-lookup"><span data-stu-id="67aba-321">For more information, see [about_Command_Precedence](../Microsoft.PowerShell.Core/About/about_Command_Precedence.md).</span></span>
* <span data-ttu-id="67aba-322">Wenn ein Modul automatisch importiert wird, entspricht der Effekt dem Verwenden des `Import-Module` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="67aba-322">When a module is imported automatically, the effect is the same as using the `Import-Module` cmdlet.</span></span> <span data-ttu-id="67aba-323">Das Modul kann Befehle, Typen und Formatierungsdateien hinzufügen und Skripts in der Sitzung ausführen.</span><span class="sxs-lookup"><span data-stu-id="67aba-323">The module can add commands, types and formatting files, and run scripts in the session.</span></span>
  <span data-ttu-id="67aba-324">Verwenden Sie die Preference-Variable, um das automatische Importieren von Modulen zu aktivieren, zu deaktivieren und zu konfigurieren `$PSModuleAutoLoadingPreference` .</span><span class="sxs-lookup"><span data-stu-id="67aba-324">To enable, disable, and configuration automatic importing of modules, use the `$PSModuleAutoLoadingPreference` preference variable.</span></span> <span data-ttu-id="67aba-325">Weitere Informationen finden Sie unter [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="67aba-325">For more information, see [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

## <span data-ttu-id="67aba-326">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="67aba-326">RELATED LINKS</span></span>

[<span data-ttu-id="67aba-327">Export-PSSession</span><span class="sxs-lookup"><span data-stu-id="67aba-327">Export-PSSession</span></span>](../Microsoft.PowerShell.Utility/Export-PSSession.md)

[<span data-ttu-id="67aba-328">Get-Help</span><span class="sxs-lookup"><span data-stu-id="67aba-328">Get-Help</span></span>](Get-Help.md)

[<span data-ttu-id="67aba-329">Get-Member</span><span class="sxs-lookup"><span data-stu-id="67aba-329">Get-Member</span></span>](../Microsoft.PowerShell.Utility/Get-Member.md)

[<span data-ttu-id="67aba-330">Get-PSDrive</span><span class="sxs-lookup"><span data-stu-id="67aba-330">Get-PSDrive</span></span>](../Microsoft.PowerShell.Management/Get-PSDrive.md)

[<span data-ttu-id="67aba-331">Import-PSSession</span><span class="sxs-lookup"><span data-stu-id="67aba-331">Import-PSSession</span></span>](../Microsoft.PowerShell.Utility/Import-PSSession.md)

[<span data-ttu-id="67aba-332">about_Command_Precedence</span><span class="sxs-lookup"><span data-stu-id="67aba-332">about_Command_Precedence</span></span>](About/about_Command_Precedence.md)

