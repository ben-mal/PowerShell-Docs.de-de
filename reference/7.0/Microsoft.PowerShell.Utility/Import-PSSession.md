---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/import-pssession?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-PSSession
ms.openlocfilehash: c64a59300cdaffe71de04c7843bf644df49530d5
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94390115"
---
# <span data-ttu-id="dc761-103">Import-PSSession</span><span class="sxs-lookup"><span data-stu-id="dc761-103">Import-PSSession</span></span>

## <span data-ttu-id="dc761-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="dc761-104">SYNOPSIS</span></span>
<span data-ttu-id="dc761-105">Importiert Befehle aus einer anderen Sitzung in die aktuelle Sitzung.</span><span class="sxs-lookup"><span data-stu-id="dc761-105">Imports commands from another session into the current session.</span></span>

## <span data-ttu-id="dc761-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="dc761-106">SYNTAX</span></span>

```
Import-PSSession [-Prefix <String>] [-DisableNameChecking] [[-CommandName] <String[]>] [-AllowClobber]
 [-ArgumentList <Object[]>] [-CommandType <CommandTypes>] [-Module <String[]>]
 [-FullyQualifiedModule <ModuleSpecification[]>] [[-FormatTypeName] <String[]>]
 [-Certificate <X509Certificate2>] [-Session] <PSSession> [<CommonParameters>]
```

## <span data-ttu-id="dc761-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="dc761-107">DESCRIPTION</span></span>

<span data-ttu-id="dc761-108">Das- `Import-PSSession` Cmdlet importiert Befehle, z. b. Cmdlets, Funktionen und Aliase, von einer PSSession auf einem lokalen oder Remote Computer in die aktuelle Sitzung.</span><span class="sxs-lookup"><span data-stu-id="dc761-108">The `Import-PSSession` cmdlet imports commands , such as cmdlets, functions, and aliases, from a PSSession on a local or remote computer into the current session.</span></span> <span data-ttu-id="dc761-109">Sie können jeden Befehl importieren, den das `Get-Command` Cmdlet in der PSSession finden kann.</span><span class="sxs-lookup"><span data-stu-id="dc761-109">You can import any command that the `Get-Command` cmdlet can find in the PSSession.</span></span>

<span data-ttu-id="dc761-110">Verwenden `Import-PSSession` Sie einen Befehl zum Importieren von Befehlen aus einer angepassten Shell (z. b. eine Microsoft Exchange Server-Shell) oder aus einer Sitzung, die Windows PowerShell-Module und-Snap-Ins oder andere Elemente enthält, die sich nicht in der aktuellen Sitzung befinden.</span><span class="sxs-lookup"><span data-stu-id="dc761-110">Use an `Import-PSSession` command to import commands from a customized shell, such as a Microsoft Exchange Server shell, or from a session that includes Windows PowerShell modules and snap-ins or other elements that are not in the current session.</span></span>

<span data-ttu-id="dc761-111">Zum Importieren von Befehlen verwenden Sie zunächst das `New-PSSession` Cmdlet, um eine PSSession zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="dc761-111">To import commands, first use the `New-PSSession` cmdlet to create a PSSession.</span></span> <span data-ttu-id="dc761-112">Verwenden Sie dann das `Import-PSSession` Cmdlet, um die Befehle zu importieren.</span><span class="sxs-lookup"><span data-stu-id="dc761-112">Then, use the `Import-PSSession` cmdlet to import the commands.</span></span> <span data-ttu-id="dc761-113">Standardmäßig `Import-PSSession` importiert alle Befehle mit Ausnahme von Befehlen, die denselben Namen wie die Befehle in der aktuellen Sitzung haben.</span><span class="sxs-lookup"><span data-stu-id="dc761-113">By default, `Import-PSSession` imports all commands except for commands that have the same names as commands in the current session.</span></span> <span data-ttu-id="dc761-114">Zum Importieren aller Befehle verwenden Sie den **AllowClobber** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="dc761-114">To import all the commands, use the **AllowClobber** parameter.</span></span>

<span data-ttu-id="dc761-115">Sie können importierte Befehle genauso wie jeden anderen Befehl in der Sitzung ausführen.</span><span class="sxs-lookup"><span data-stu-id="dc761-115">You can use imported commands just as you would use any command in the session.</span></span> <span data-ttu-id="dc761-116">Wenn Sie einen importierten Befehl verwenden, wird der importierte Teil des Befehls implizit in der Sitzung ausgeführt, aus der er importiert wurde.</span><span class="sxs-lookup"><span data-stu-id="dc761-116">When you use an imported command, the imported part of the command runs implicitly in the session from which it was imported.</span></span> <span data-ttu-id="dc761-117">Die Remotevorgänge werden jedoch vollständig von Windows PowerShell verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="dc761-117">However, the remote operations are handled entirely by Windows PowerShell.</span></span> <span data-ttu-id="dc761-118">Abgesehen davon, dass die Verbindung mit der anderen Sitzung (PSSession) geöffnet bleiben muss, können Remotevorgänge vollständig unbeaufsichtigt ablaufen.</span><span class="sxs-lookup"><span data-stu-id="dc761-118">You need not even be aware of them, except that you must keep the connection to the other session (PSSession) open.</span></span> <span data-ttu-id="dc761-119">Wenn Sie die Verbindung trennen, sind die importierten Befehle nicht mehr verfügbar.</span><span class="sxs-lookup"><span data-stu-id="dc761-119">If you close it, the imported commands are no longer available.</span></span>

<span data-ttu-id="dc761-120">Da die Ausführung importierter Befehle länger dauern kann als lokale Befehle, `Import-PSSession` fügt jedem importierten Befehl einen **AsJob** -Parameter hinzu.</span><span class="sxs-lookup"><span data-stu-id="dc761-120">Because imported commands might take longer to run than local commands, `Import-PSSession` adds an **AsJob** parameter to every imported command.</span></span> <span data-ttu-id="dc761-121">Durch diesen Parameter können Sie den Befehl in Windows PowerShell als Hintergrundauftrag ausführen.</span><span class="sxs-lookup"><span data-stu-id="dc761-121">This parameter allows you to run the command as a Windows PowerShell background job.</span></span> <span data-ttu-id="dc761-122">Weitere Informationen finden Sie unter [about_Jobs](../Microsoft.PowerShell.Core/about/about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="dc761-122">For more information, see [about_Jobs](../Microsoft.PowerShell.Core/about/about_Jobs.md).</span></span>

<span data-ttu-id="dc761-123">Wenn Sie verwenden `Import-PSSession` , fügt Windows PowerShell die importierten Befehle einem temporären Modul hinzu, das nur in der Sitzung vorhanden ist, und gibt ein Objekt zurück, das das Modul darstellt.</span><span class="sxs-lookup"><span data-stu-id="dc761-123">When you use `Import-PSSession`, Windows PowerShell adds the imported commands to a temporary module that exists only in your session and returns an object that represents the module.</span></span> <span data-ttu-id="dc761-124">Verwenden Sie das-Cmdlet, um ein dauerhaftes Modul zu erstellen, das Sie in zukünftigen Sitzungen verwenden können `Export-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="dc761-124">To create a persistent module that you can use in future sessions, use the `Export-PSSession` cmdlet.</span></span>

<span data-ttu-id="dc761-125">Das- `Import-PSSession` Cmdlet verwendet das implizite Remoting-Feature von Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dc761-125">The `Import-PSSession` cmdlet uses the implicit remoting feature of Windows PowerShell.</span></span> <span data-ttu-id="dc761-126">Wenn Sie Befehle in die aktuelle Sitzung importieren, werden Sie implizit in der ursprünglichen Sitzung oder in einer ähnlichen Sitzung auf dem ursprünglichen Computer ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="dc761-126">When you import commands into the current session, they run implicitly in the original session or in a similar session on the originating computer.</span></span>

<span data-ttu-id="dc761-127">Ab Windows PowerShell 3,0 können Sie das `Import-Module` Cmdlet verwenden, um Module aus einer Remote Sitzung in die aktuelle Sitzung zu importieren.</span><span class="sxs-lookup"><span data-stu-id="dc761-127">Beginning in Windows PowerShell 3.0, you can use the `Import-Module` cmdlet to import modules from a remote session into the current session.</span></span> <span data-ttu-id="dc761-128">Dieses Feature verwendet implizites Remoting.</span><span class="sxs-lookup"><span data-stu-id="dc761-128">This feature uses implicit remoting.</span></span> <span data-ttu-id="dc761-129">Dies entspricht `Import-PSSession` der Verwendung von, um ausgewählte Module aus einer Remote Sitzung in die aktuelle Sitzung zu importieren.</span><span class="sxs-lookup"><span data-stu-id="dc761-129">It is equivalent to using `Import-PSSession` to import selected modules from a remote session into the current session.</span></span>

## <span data-ttu-id="dc761-130">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="dc761-130">EXAMPLES</span></span>

### <span data-ttu-id="dc761-131">Beispiel 1: Importieren aller Befehle aus einer PSSession</span><span class="sxs-lookup"><span data-stu-id="dc761-131">Example 1: Import all commands from a PSSession</span></span>

```
PS C:\> $S = New-PSSession -ComputerName Server01
PS C:\> Import-PSSession -Session $S
```

<span data-ttu-id="dc761-132">Dieser Befehl importiert alle Befehle einer PSSession auf Computer Server01 in die aktuelle Sitzung. Dies gilt nicht für Befehle, die über dieselben Namen wie Befehle in der aktuellen Sitzung verfügen.</span><span class="sxs-lookup"><span data-stu-id="dc761-132">This command imports all commands from a PSSession on the Server01 computer into the current session, except for commands that have the same names as commands in the current session.</span></span>

<span data-ttu-id="dc761-133">Da der **CommandName** -Parameter von diesem Befehl nicht verwendet wird, werden außerdem alle für die importierten Befehle erforderlichen Formatierungsdaten importiert.</span><span class="sxs-lookup"><span data-stu-id="dc761-133">Because this command does not use the **CommandName** parameter, it also imports all of the formatting data required for the imported commands.</span></span>

### <span data-ttu-id="dc761-134">Beispiel 2: Importieren von Befehlen, die mit einer bestimmten Zeichenfolge enden</span><span class="sxs-lookup"><span data-stu-id="dc761-134">Example 2: Import commands that end with a specific string</span></span>

```
PS C:\> $S = New-PSSession https://ps.testlabs.com/powershell
PS C:\> Import-PSSession -Session $S -CommandName *-test -FormatTypeName *
PS C:\> New-Test -Name Test1
PS C:\> Get-Test test1 | Run-Test
```

<span data-ttu-id="dc761-135">Durch diese Befehle werden die auf „-test“ endenden Namen aus einer PSSession in die lokale Sitzung importiert. Anschließend wird die Verwendung eines importierten Cmdlets gezeigt.</span><span class="sxs-lookup"><span data-stu-id="dc761-135">These commands import the commands with names that end in "-test" from a PSSession into the local session, and then they show how to use an imported cmdlet.</span></span>

<span data-ttu-id="dc761-136">Der erste Befehl verwendet das `New-PSSession` Cmdlet, um eine PSSession zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="dc761-136">The first command uses the `New-PSSession` cmdlet to create a PSSession.</span></span> <span data-ttu-id="dc761-137">Er speichert die PSSession in der `$S` Variablen.</span><span class="sxs-lookup"><span data-stu-id="dc761-137">It saves the PSSession in the `$S` variable.</span></span>

<span data-ttu-id="dc761-138">Der zweite Befehl verwendet das `Import-PSSession` Cmdlet, um Befehle aus der PSSession in in `$S` die aktuelle Sitzung zu importieren.</span><span class="sxs-lookup"><span data-stu-id="dc761-138">The second command uses the `Import-PSSession` cmdlet to import commands from the PSSession in `$S` into the current session.</span></span> <span data-ttu-id="dc761-139">Er verwendet den **CommandName** -Parameter, um Befehle mit dem Substantiv „Test“ anzugeben, und den **FormatTypeName** -Parameter, um die Formatierungsdaten für die Test-Befehle zu importieren.</span><span class="sxs-lookup"><span data-stu-id="dc761-139">It uses the **CommandName** parameter to specify commands with the Test noun and the **FormatTypeName** parameter to import the formatting data for the Test commands.</span></span>

<span data-ttu-id="dc761-140">Vom dritten und vierten Befehl werden die importierten Befehle in der aktuellen Sitzung verwendet.</span><span class="sxs-lookup"><span data-stu-id="dc761-140">The third and fourth commands use the imported commands in the current session.</span></span> <span data-ttu-id="dc761-141">Importierte Befehle werden der aktuellen Sitzung tatsächlich hinzugefügt, sodass Sie sie mithilfe lokaler Syntax ausführen.</span><span class="sxs-lookup"><span data-stu-id="dc761-141">Because imported commands are actually added to the current session, you use the local syntax to run them.</span></span> <span data-ttu-id="dc761-142">Sie müssen das `Invoke-Command` Cmdlet nicht verwenden, um einen importierten Befehl auszuführen.</span><span class="sxs-lookup"><span data-stu-id="dc761-142">You do not need to use the `Invoke-Command` cmdlet to run an imported command.</span></span>

### <span data-ttu-id="dc761-143">Beispiel 3: Importieren von Cmdlets aus einer PSSession</span><span class="sxs-lookup"><span data-stu-id="dc761-143">Example 3: Import cmdlets from a PSSession</span></span>

```
PS C:\> $S1 = New-PSSession -ComputerName s1
PS C:\> $S2 = New-PSSession -ComputerName s2
PS C:\> Import-PSSession -Session s1 -Type cmdlet -Name New-Test, Get-Test -FormatTypeName *
PS C:\> Import-PSSession -Session s2 -Type Cmdlet -Name Set-Test -FormatTypeName *
PS C:\> New-Test Test1 | Set-Test -RunType Full
```

<span data-ttu-id="dc761-144">Dieses Beispiel zeigt, dass Sie importierte Cmdlets genauso verwenden, wie Sie lokale Cmdlets verwenden würden.</span><span class="sxs-lookup"><span data-stu-id="dc761-144">This example shows that you can use imported cmdlets just as you would use local cmdlets.</span></span>

<span data-ttu-id="dc761-145">Mit diesen Befehlen werden die `New-Test` -und- `Get-Test` Cmdlets aus einer PSSession auf dem Server01-Computer und das `Set-Test` Cmdlet aus einer PSSession auf dem Server02-Computer importiert.</span><span class="sxs-lookup"><span data-stu-id="dc761-145">These commands import the `New-Test` and `Get-Test` cmdlets from a PSSession on the Server01 computer and the `Set-Test` cmdlet from a PSSession on the Server02 computer.</span></span>

<span data-ttu-id="dc761-146">Obwohl die Cmdlets aus verschiedenen PSSessions importiert wurden, können Sie ein Objekt aus einem Cmdlet fehlerfrei an ein anderes Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="dc761-146">Even though the cmdlets were imported from different PSSessions, you can pipe an object from one cmdlet to another without error.</span></span>

### <span data-ttu-id="dc761-147">Beispiel 4: Ausführen eines importierten Befehls als Hintergrund Auftrag</span><span class="sxs-lookup"><span data-stu-id="dc761-147">Example 4: Run an imported command as a background job</span></span>

```
PS C:\> $S = New-PSSession -ComputerName Server01
PS C:\> Import-PSSession -Session $S -CommandName *-test* -FormatTypeName *
PS C:\> $batch = New-Test -Name Batch -AsJob
PS C:\> Receive-Job $batch
```

<span data-ttu-id="dc761-148">In diesem Beispiel wird erläutert, wie ein importierter Befehl als Hintergrundauftrag ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="dc761-148">This example shows how to run an imported command as a background job.</span></span>

<span data-ttu-id="dc761-149">Da die Ausführung importierter Befehle länger dauern kann als lokale Befehle, `Import-PSSession` fügt jedem importierten Befehl einen **AsJob** -Parameter hinzu.</span><span class="sxs-lookup"><span data-stu-id="dc761-149">Because imported commands might take longer to run than local commands, `Import-PSSession` adds an **AsJob** parameter to every imported command.</span></span> <span data-ttu-id="dc761-150">Der **AsJob** -Parameter ermöglicht Ihnen die Ausführung des Befehls als Hintergrundauftrag.</span><span class="sxs-lookup"><span data-stu-id="dc761-150">The **AsJob** parameter lets you run the command as a background job.</span></span>

<span data-ttu-id="dc761-151">Der erste Befehl erstellt eine PSSession auf dem Server01-Computer und speichert das PSSession-Objekt in der `$S` Variablen.</span><span class="sxs-lookup"><span data-stu-id="dc761-151">The first command creates a PSSession on the Server01 computer and saves the PSSession object in the `$S` variable.</span></span>

<span data-ttu-id="dc761-152">Der zweite Befehl verwendet `Import-PSSession` , um die Test-Cmdlets aus der PSSession in `$S` in die aktuelle Sitzung zu importieren.</span><span class="sxs-lookup"><span data-stu-id="dc761-152">The second command uses `Import-PSSession` to import the Test cmdlets from the PSSession in `$S` into the current session.</span></span>

<span data-ttu-id="dc761-153">Der dritte Befehl verwendet den **AsJob** -Parameter des importierten `New-Test` Cmdlets, um einen `New-Test` Befehl als Hintergrund Auftrag auszuführen.</span><span class="sxs-lookup"><span data-stu-id="dc761-153">The third command uses the **AsJob** parameter of the imported `New-Test` cmdlet to run a `New-Test` command as a background job.</span></span> <span data-ttu-id="dc761-154">Der Befehl speichert das Auftrags Objekt, das `New-Test` in der Variablen zurückgegeben wird `$batch` .</span><span class="sxs-lookup"><span data-stu-id="dc761-154">The command saves the job object that `New-Test` returns in the `$batch` variable.</span></span>

<span data-ttu-id="dc761-155">Der vierte Befehl verwendet das `Receive-Job` Cmdlet, um die Ergebnisse des Auftrags in der Variablen zu erhalten `$batch` .</span><span class="sxs-lookup"><span data-stu-id="dc761-155">The fourth command uses the `Receive-Job` cmdlet to get the results of the job in the `$batch` variable.</span></span>

### <span data-ttu-id="dc761-156">Beispiel 5: Importieren von Cmdlets und Funktionen aus einem Windows PowerShell-Modul</span><span class="sxs-lookup"><span data-stu-id="dc761-156">Example 5: Import cmdlets and functions from a Windows PowerShell module</span></span>

```
PS C:\> $S = New-PSSession -ComputerName Server01
PS C:\> Invoke-Command -Session $S {Import-Module TestManagement}
PS C:\> Import-PSSession -Session $S -Module TestManagement
```

<span data-ttu-id="dc761-157">In diesem Beispiel wird veranschaulicht, wie Cmdlets und Funktionen aus einem Windows PowerShell-Modul auf einem Remotecomputer in die aktuelle Sitzung importiert werden.</span><span class="sxs-lookup"><span data-stu-id="dc761-157">This example shows how to import the cmdlets and functions from a Windows PowerShell module on a remote computer into the current session.</span></span>

<span data-ttu-id="dc761-158">Der erste Befehl erstellt eine PSSession auf dem Server01-Computer und speichert Sie in der `$S` Variablen.</span><span class="sxs-lookup"><span data-stu-id="dc761-158">The first command creates a PSSession on the Server01 computer and saves it in the `$S` variable.</span></span>

<span data-ttu-id="dc761-159">Der zweite Befehl verwendet das `Invoke-Command` Cmdlet, um einen `Import-Module` Befehl in der PSSession in auszuführen `$S` .</span><span class="sxs-lookup"><span data-stu-id="dc761-159">The second command uses the `Invoke-Command` cmdlet to run an `Import-Module` command in the PSSession in `$S`.</span></span>

<span data-ttu-id="dc761-160">Normalerweise würde das Modul allen Sitzungen durch einen `Import-Module` Befehl in einem Windows PowerShell-Profil hinzugefügt werden, aber Profile werden nicht in pssessions ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="dc761-160">Typically, the module would be added to all sessions by an `Import-Module` command in a Windows PowerShell profile, but profiles are not run in PSSessions.</span></span>

<span data-ttu-id="dc761-161">Der dritte Befehl verwendet den **Module** -Parameter von `Import-PSSession` , um die Cmdlets und Funktionen im Modul in die aktuelle Sitzung zu importieren.</span><span class="sxs-lookup"><span data-stu-id="dc761-161">The third command uses the **Module** parameter of `Import-PSSession` to import the cmdlets and functions in the module into the current session.</span></span>

### <span data-ttu-id="dc761-162">Beispiel 6: Erstellen eines Moduls in einer temporären Datei</span><span class="sxs-lookup"><span data-stu-id="dc761-162">Example 6: Create a module in a temporary file</span></span>

```
PS C:\> Import-PSSession $S -CommandName Get-Date, SearchHelp -FormatTypeName * -AllowClobber

Name              : tmp_79468106-4e1d-4d90-af97-1154f9317239_tcw1zunz.ttf
Path              : C:\Users\User01\AppData\Local\Temp\tmp_79468106-4e1d-4d90-af97-1154f9317239_tcw1
zunz.ttf\tmp_79468106-4e1d-4d90-af97-1154f9317239_
tcw1zunz.ttf.psm1
Description       : Implicit remoting for http://server01.corp.fabrikam.com/wsman
Guid              : 79468106-4e1d-4d90-af97-1154f9317239
Version           : 1.0
ModuleBase        : C:\Users\User01\AppData\Local\Temp\tmp_79468106-4e1d-4d90-af97-1154f9317239_tcw1
zunz.ttf
ModuleType        : Script
PrivateData       : {ImplicitRemoting}
AccessMode        : ReadWrite
ExportedAliases   : {}
ExportedCmdlets   : {}
ExportedFunctions : {[Get-Date, Get-Date], [SearchHelp, SearchHelp]}
ExportedVariables : {}
NestedModules     : {}
```

<span data-ttu-id="dc761-163">Dieses Beispiel zeigt, dass `Import-PSSession` ein Modul in einer temporären Datei auf dem Datenträger erstellt.</span><span class="sxs-lookup"><span data-stu-id="dc761-163">This example shows that `Import-PSSession` creates a module in a temporary file on disk.</span></span> <span data-ttu-id="dc761-164">Außerdem wird veranschaulicht, dass alle Befehle vor dem Import in die aktuelle Sitzung in Funktionen konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="dc761-164">It also shows that all commands are converted into functions before they are imported into the current session.</span></span>

<span data-ttu-id="dc761-165">Der Befehl verwendet das `Import-PSSession` Cmdlet, um ein `Get-Date` Cmdlet und eine SearchHelp-Funktion in die aktuelle Sitzung zu importieren.</span><span class="sxs-lookup"><span data-stu-id="dc761-165">The command uses the `Import-PSSession` cmdlet to import a `Get-Date` cmdlet and a SearchHelp function into the current session.</span></span>

<span data-ttu-id="dc761-166">Das- `Import-PSSession` Cmdlet gibt ein **psmoduleinfo** -Objekt zurück, das das temporäre Modul darstellt.</span><span class="sxs-lookup"><span data-stu-id="dc761-166">The `Import-PSSession` cmdlet returns a **PSModuleInfo** object that represents the temporary module.</span></span> <span data-ttu-id="dc761-167">Der Wert der **path** -Eigenschaft zeigt, dass `Import-PSSession` eine Skript Modul Datei (. psm1) an einem temporären Speicherort erstellt hat.</span><span class="sxs-lookup"><span data-stu-id="dc761-167">The value of the **Path** property shows that `Import-PSSession` created a script module (.psm1) file in a temporary location.</span></span> <span data-ttu-id="dc761-168">Die **exportedfunctions** -Eigenschaft zeigt, dass das `Get-Date` Cmdlet und die SearchHelp-Funktion beide als Funktionen importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="dc761-168">The **ExportedFunctions** property shows that the `Get-Date` cmdlet and the SearchHelp function were both imported as functions.</span></span>

### <span data-ttu-id="dc761-169">Beispiel 7: Ausführen eines Befehls, der von einem importierten Befehl ausgeblendet wird</span><span class="sxs-lookup"><span data-stu-id="dc761-169">Example 7: Run a command that is hidden by an imported command</span></span>

```
PS C:\> Import-PSSession $S -CommandName Get-Date -FormatTypeName * -AllowClobber

PS C:\> Get-Command Get-Date -All

CommandType   Name       Definition
-----------   ----       ----------
Function      Get-Date   ...
Cmdlet        Get-Date   Get-Date [[-Date] <DateTime>] [-Year <Int32>] [-Month <Int32>]

PS C:\> Get-Date
09074

PS C:\> (Get-Command -Type Cmdlet -Name Get-Date).PSSnapin.Name
Microsoft.PowerShell.Utility

PS C:\> Microsoft.PowerShell.Utility\Get-Date
Sunday, March 15, 2009 2:08:26 PM
```

<span data-ttu-id="dc761-170">In diesem Beispiel wird die Ausführung eines Befehls veranschaulicht, der von einem importierten Befehl ausgeblendet wird.</span><span class="sxs-lookup"><span data-stu-id="dc761-170">This example shows how to run a command that is hidden by an imported command.</span></span>

<span data-ttu-id="dc761-171">Der erste Befehl importiert ein `Get-Date` Cmdlet aus der PSSession in der `$S` Variablen.</span><span class="sxs-lookup"><span data-stu-id="dc761-171">The first command imports a `Get-Date` cmdlet from the PSSession in the `$S` variable.</span></span> <span data-ttu-id="dc761-172">Da die aktuelle Sitzung ein `Get-Date` Cmdlet enthält, ist der **allowclobber** -Parameter im Befehl erforderlich.</span><span class="sxs-lookup"><span data-stu-id="dc761-172">Because the current session includes a `Get-Date` cmdlet, the **AllowClobber** parameter is required in the command.</span></span>

<span data-ttu-id="dc761-173">Der zweite Befehl verwendet den **all** -Parameter des `Get-Command` Cmdlets, um alle `Get-Date` Befehle in der aktuellen Sitzung zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="dc761-173">The second command uses the **All** parameter of the `Get-Command` cmdlet to get all `Get-Date` commands in the current session.</span></span> <span data-ttu-id="dc761-174">Die Ausgabe zeigt, dass die Sitzung das ursprüngliche `Get-Date` Cmdlet und eine `Get-Date` Funktion enthält.</span><span class="sxs-lookup"><span data-stu-id="dc761-174">The output shows that the session includes the original `Get-Date` cmdlet and a `Get-Date` function.</span></span> <span data-ttu-id="dc761-175">Die- `Get-Date` Funktion führt das importierte `Get-Date` Cmdlet in der PSSession in aus `$S` .</span><span class="sxs-lookup"><span data-stu-id="dc761-175">The `Get-Date` function runs the imported `Get-Date` cmdlet in the PSSession in `$S`.</span></span>

<span data-ttu-id="dc761-176">Der dritte Befehl führt einen `Get-Date` Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="dc761-176">The third command runs a `Get-Date` command.</span></span> <span data-ttu-id="dc761-177">Da Funktionen Vorrang vor Cmdlets haben, führt Windows PowerShell die importierte `Get-Date` Funktion aus, die ein Julianischer Datum zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="dc761-177">Because functions take precedence over cmdlets, Windows PowerShell runs the imported `Get-Date` function, which returns a Julian date.</span></span>

<span data-ttu-id="dc761-178">Der vierte und fünfte Befehl zeigen, wie ein Befehl, der von einem importierten Befehl ausgeblendet wird, anhand eines qualifizierten Namens ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="dc761-178">The fourth and fifth commands show how to use a qualified name to run a command that is hidden by an imported command.</span></span>

<span data-ttu-id="dc761-179">Mit dem vierten Befehl wird der Name des Windows PowerShell-Snap-Ins abgerufen, das das ursprüngliche `Get-Date` Cmdlet zur aktuellen Sitzung hinzugefügt hat.</span><span class="sxs-lookup"><span data-stu-id="dc761-179">The fourth command gets the name of the Windows PowerShell snap-in that added the original `Get-Date` cmdlet to the current session.</span></span>

<span data-ttu-id="dc761-180">Der fünfte Befehl verwendet den mit dem Snap-in qualifizierten Namen des `Get-Date` Cmdlets, um einen `Get-Date` Befehl auszuführen.</span><span class="sxs-lookup"><span data-stu-id="dc761-180">The fifth command uses the snap-in-qualified name of the `Get-Date` cmdlet to run a `Get-Date` command.</span></span>

<span data-ttu-id="dc761-181">Weitere Informationen zur Befehlsrangfolge und zu ausgeblendeten Befehlen finden Sie unter [about_Command_Precedence](../Microsoft.PowerShell.Core/about/about_Command_Precedence.md).</span><span class="sxs-lookup"><span data-stu-id="dc761-181">For more information about command precedence and hidden commands, see [about_Command_Precedence](../Microsoft.PowerShell.Core/about/about_Command_Precedence.md).</span></span>

### <span data-ttu-id="dc761-182">Beispiel 8: Importieren von Befehlen, die eine bestimmte Zeichenfolge in ihren Namen haben</span><span class="sxs-lookup"><span data-stu-id="dc761-182">Example 8: Import commands that have a specific string in their names</span></span>

```
PS C:\> Import-PSSession -Session $S -CommandName **Item** -AllowClobber
```

<span data-ttu-id="dc761-183">Mit diesem Befehl werden Befehle importiert, deren Namen ein Element aus der PSSession in enthalten `$S` .</span><span class="sxs-lookup"><span data-stu-id="dc761-183">This command imports commands whose names include Item from the PSSession in `$S`.</span></span> <span data-ttu-id="dc761-184">Da der Befehl den **CommandName** -Parameter, aber nicht den **formattypedata** -Parameter enthält, wird nur der-Befehl importiert.</span><span class="sxs-lookup"><span data-stu-id="dc761-184">Because the command includes the **CommandName** parameter but not the **FormatTypeData** parameter, only the command is imported.</span></span>

<span data-ttu-id="dc761-185">Verwenden Sie diesen Befehl, wenn Sie verwenden `Import-PSSession` , um einen Befehl auf einem Remote Computer auszuführen, und Sie bereits über die Formatierungsdaten für den Befehl in der aktuellen Sitzung verfügen.</span><span class="sxs-lookup"><span data-stu-id="dc761-185">Use this command when you are using `Import-PSSession` to run a command on a remote computer and you already have the formatting data for the command in the current session.</span></span>

### <span data-ttu-id="dc761-186">Beispiel 9: Verwenden Sie den Module-Parameter, um zu ermitteln, welche Befehle in die Sitzung importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="dc761-186">Example 9: Use the Module parameter to discover which commands were imported into the session</span></span>

```
PS C:\> $M = Import-PSSession -Session $S -CommandName *bits* -FormatTypeName *bits*
PS C:\> Get-Command -Module $M
CommandType     Name
-----------     ----
Function        Add-BitsFile
Function        Complete-BitsTransfer
Function        Get-BitsTransfer
Function        Remove-BitsTransfer
Function        Resume-BitsTransfer
Function        Set-BitsTransfer
Function        Start-BitsTransfer
Function        Suspend-BitsTransfer
```

<span data-ttu-id="dc761-187">Dieser Befehl zeigt, wie der **Modul** Parameter von verwendet `Get-Command` wird, um herauszufinden, welche Befehle von einem Befehl in die Sitzung importiert wurden `Import-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="dc761-187">This command shows how to use the **Module** parameter of `Get-Command` to find out which commands were imported into the session by an `Import-PSSession` command.</span></span>

<span data-ttu-id="dc761-188">Der erste Befehl verwendet das `Import-PSSession` Cmdlet, um Befehle zu importieren, deren Namen "Bits" aus der PSSession in der `$S` Variablen enthalten.</span><span class="sxs-lookup"><span data-stu-id="dc761-188">The first command uses the `Import-PSSession` cmdlet to import commands whose names include "bits" from the PSSession in the `$S` variable.</span></span> <span data-ttu-id="dc761-189">Der `Import-PSSession` Befehl gibt ein temporäres Modul zurück, und der Befehl speichert das Modul in der `$m` Variablen.</span><span class="sxs-lookup"><span data-stu-id="dc761-189">The `Import-PSSession` command returns a temporary module, and the command saves the module in the `$m` variable.</span></span>

<span data-ttu-id="dc761-190">Der zweite Befehl verwendet das `Get-Command` Cmdlet, um die Befehle, die vom Modul in der Variablen exportiert werden, zu erhalten `$M` .</span><span class="sxs-lookup"><span data-stu-id="dc761-190">The second command uses the `Get-Command` cmdlet to get the commands that are exported by the module in the `$M` variable.</span></span>

<span data-ttu-id="dc761-191">Der **Module** -Parameter akzeptiert einen Zeichenfolgenwert, der eigens für den Modulnamen erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="dc761-191">The **Module** parameter takes a string value, which is designed for the module name.</span></span> <span data-ttu-id="dc761-192">Wenn Sie ein Modulobjekt senden, verwendet Windows PowerShell jedoch die **ToString** -Methode für das Modulobjekt, das den Modulnamen zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="dc761-192">However, when you submit a module object, Windows PowerShell uses the **ToString** method on the module object, which returns the module name.</span></span>

<span data-ttu-id="dc761-193">Der `Get-Command` Befehl ist das Äquivalent zu `Get-Command $M.Name` ".</span><span class="sxs-lookup"><span data-stu-id="dc761-193">The `Get-Command` command is the equivalent of `Get-Command $M.Name`".</span></span>

## <span data-ttu-id="dc761-194">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="dc761-194">PARAMETERS</span></span>

### <span data-ttu-id="dc761-195">-Allowclobber</span><span class="sxs-lookup"><span data-stu-id="dc761-195">-AllowClobber</span></span>

<span data-ttu-id="dc761-196">Gibt an, dass dieses Cmdlet die angegebenen Befehle importiert, auch wenn Sie dieselben Namen wie die Befehle in der aktuellen Sitzung haben.</span><span class="sxs-lookup"><span data-stu-id="dc761-196">Indicates that this cmdlet imports the specified commands, even if they have the same names as commands in the current session.</span></span>

<span data-ttu-id="dc761-197">Wenn Sie einen Befehl importieren, der denselben Namen wie der Befehl in der aktuellen Sitzung hat, werden die ursprünglichen Befehle durch den importierten Befehl ausgeblendet oder ersetzt.</span><span class="sxs-lookup"><span data-stu-id="dc761-197">If you import a command with the same name as a command in the current session, the imported command hides or replaces the original commands.</span></span> <span data-ttu-id="dc761-198">Weitere Informationen finden Sie unter [about_Command_Precedence](../Microsoft.PowerShell.Core/about/about_Command_Precedence.md).</span><span class="sxs-lookup"><span data-stu-id="dc761-198">For more information, see [about_Command_Precedence](../Microsoft.PowerShell.Core/about/about_Command_Precedence.md).</span></span>

<span data-ttu-id="dc761-199">Standardmäßig `Import-PSSession` importiert keine Befehle, die denselben Namen wie die Befehle in der aktuellen Sitzung haben.</span><span class="sxs-lookup"><span data-stu-id="dc761-199">By default, `Import-PSSession` does not import commands that have the same name as commands in the current session.</span></span>

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

### <span data-ttu-id="dc761-200">-Argumentlist</span><span class="sxs-lookup"><span data-stu-id="dc761-200">-ArgumentList</span></span>

<span data-ttu-id="dc761-201">Gibt ein Array von Befehlen an, die sich aus der Verwendung der angegebenen Argumente (Parameterwerte) ergeben.</span><span class="sxs-lookup"><span data-stu-id="dc761-201">Specifies an array of commands that results from using the specified arguments (parameter values).</span></span>

<span data-ttu-id="dc761-202">So importieren Sie beispielsweise die Variante des `Get-Item` Befehls im Zertifikat (CERT:) Geben Sie in die PSSession in ein `$S` , und geben Sie ein `Import-PSSession -Session $S -Command Get-Item -ArgumentList cert:` .</span><span class="sxs-lookup"><span data-stu-id="dc761-202">For instance, to import the variant of the `Get-Item` command in the certificate (Cert:) drive in the PSSession in `$S`, type `Import-PSSession -Session $S -Command Get-Item -ArgumentList cert:`.</span></span>

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

### <span data-ttu-id="dc761-203">-Zertifikat</span><span class="sxs-lookup"><span data-stu-id="dc761-203">-Certificate</span></span>

<span data-ttu-id="dc761-204">Gibt das Client Zertifikat an, das zum Signieren der Format Dateien (\* .Format.ps1XML) oder Skript Moduldateien (. psm1) im temporären Modul verwendet wird, das von `Import-PSSession` erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="dc761-204">Specifies the client certificate that is used to sign the format files (\*.Format.ps1xml) or script module files (.psm1) in the temporary module that `Import-PSSession` creates.</span></span>

<span data-ttu-id="dc761-205">Geben Sie eine Variable ein, die ein Zertifikat, einen Befehl oder einen Ausdruck enthält, durch die das Zertifikat abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="dc761-205">Enter a variable that contains a certificate or a command or expression that gets the certificate.</span></span>

<span data-ttu-id="dc761-206">Um ein Zertifikat zu suchen, verwenden Sie das `Get-PfxCertificate` Cmdlet, oder verwenden Sie das `Get-ChildItem` Cmdlet im Zertifikat (CERT:). Antrie.</span><span class="sxs-lookup"><span data-stu-id="dc761-206">To find a certificate, use the `Get-PfxCertificate` cmdlet or use the `Get-ChildItem` cmdlet in the Certificate (Cert:) drive.</span></span> <span data-ttu-id="dc761-207">Wenn das Zertifikat ungültig ist oder keine qualifizierte Zertifizierungsstelle aufweist, verursacht der Befehl einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="dc761-207">If the certificate is not valid or does not have sufficient authority, the command fails.</span></span>

```yaml
Type: System.Security.Cryptography.X509Certificates.X509Certificate2
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dc761-208">-CommandName</span><span class="sxs-lookup"><span data-stu-id="dc761-208">-CommandName</span></span>

<span data-ttu-id="dc761-209">Gibt Befehle mit den angegebenen Namen oder namens Mustern an.</span><span class="sxs-lookup"><span data-stu-id="dc761-209">Specifies commands with the specified names or name patterns.</span></span> <span data-ttu-id="dc761-210">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="dc761-210">Wildcards are permitted.</span></span> <span data-ttu-id="dc761-211">Verwenden Sie **CommandName** oder den Alias **Name**.</span><span class="sxs-lookup"><span data-stu-id="dc761-211">Use **CommandName** or its alias, **Name**.</span></span>

<span data-ttu-id="dc761-212">Standardmäßig `Import-PSSession` importiert alle Befehle aus der Sitzung, mit Ausnahme von Befehlen, die denselben Namen wie die Befehle in der aktuellen Sitzung haben.</span><span class="sxs-lookup"><span data-stu-id="dc761-212">By default, `Import-PSSession` imports all commands from the session, except for commands that have the same names as commands in the current session.</span></span> <span data-ttu-id="dc761-213">Dadurch wird verhindert, dass Befehle in der Sitzung durch importierte Befehle ausgeblendet oder ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="dc761-213">This prevents imported commands from hiding or replacing commands in the session.</span></span> <span data-ttu-id="dc761-214">Um alle Befehle zu importieren, also auch die Befehle, durch die andere Befehle ausgeblendet oder ersetzt werden, verwenden Sie den **AllowClobber** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="dc761-214">To import all commands, even those that hide or replace other commands, use the **AllowClobber** parameter.</span></span>

<span data-ttu-id="dc761-215">Bei Verwendung des **CommandName** -Parameters werden die Formatierungsdateien für die Befehle nicht importiert, sofern nicht der **FormatTypeName** -Parameter verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="dc761-215">If you use the **CommandName** parameter, the formatting files for the commands are not imported unless you use the **FormatTypeName** parameter.</span></span> <span data-ttu-id="dc761-216">Entsprechend werden bei Verwendung des **FormatTypeName** -Parameters keine Befehle importiert, sofern Sie nicht den **CommandName** -Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="dc761-216">Similarly, if you use the **FormatTypeName** parameter, no commands are imported unless you use the **CommandName** parameter.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Name

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dc761-217">-CommandType</span><span class="sxs-lookup"><span data-stu-id="dc761-217">-CommandType</span></span>

<span data-ttu-id="dc761-218">Gibt den Typ von Befehls Objekten an.</span><span class="sxs-lookup"><span data-stu-id="dc761-218">Specifies the type of command objects.</span></span> <span data-ttu-id="dc761-219">Der Standardwert ist Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="dc761-219">The default value is Cmdlet.</span></span> <span data-ttu-id="dc761-220">Verwenden Sie **CommandType** oder dessen Aliasname **Type**.</span><span class="sxs-lookup"><span data-stu-id="dc761-220">Use **CommandType** or its alias, **Type**.</span></span> <span data-ttu-id="dc761-221">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="dc761-221">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="dc761-222">Alias.</span><span class="sxs-lookup"><span data-stu-id="dc761-222">Alias.</span></span> <span data-ttu-id="dc761-223">Die Windows PowerShell-Aliase in der Remotesitzung.</span><span class="sxs-lookup"><span data-stu-id="dc761-223">The Windows PowerShell aliases in the remote session.</span></span>
- <span data-ttu-id="dc761-224">Alle</span><span class="sxs-lookup"><span data-stu-id="dc761-224">All.</span></span> <span data-ttu-id="dc761-225">Die Cmdlets und Funktionen in der Remotesitzung.</span><span class="sxs-lookup"><span data-stu-id="dc761-225">The cmdlets and functions in the remote session.</span></span>
- <span data-ttu-id="dc761-226">Anwendung:</span><span class="sxs-lookup"><span data-stu-id="dc761-226">Application.</span></span> <span data-ttu-id="dc761-227">Alle Dateien außer Windows-PowerShell Dateien in den Pfaden, die in der PATH-Umgebungsvariablen ( `$env:path` ) in der Remote Sitzung aufgelistet sind, einschließlich txt-, exe-und dll-Dateien.</span><span class="sxs-lookup"><span data-stu-id="dc761-227">All the files other than Windows-PowerShell files in the paths that are listed in the Path environment variable (`$env:path`) in the remote session, including .txt, .exe, and .dll files.</span></span>
- <span data-ttu-id="dc761-228">Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="dc761-228">Cmdlet.</span></span> <span data-ttu-id="dc761-229">Die Cmdlets in der Remotesitzung.</span><span class="sxs-lookup"><span data-stu-id="dc761-229">The cmdlets in the remote session.</span></span> <span data-ttu-id="dc761-230">Der Standardwert ist Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="dc761-230">"Cmdlet" is the default.</span></span>
- <span data-ttu-id="dc761-231">Externalscript.</span><span class="sxs-lookup"><span data-stu-id="dc761-231">ExternalScript.</span></span> <span data-ttu-id="dc761-232">Die PS1-Dateien in den Pfaden, die in der PATH-Umgebungsvariablen ( `$env:path` ) in der Remote Sitzung aufgelistet sind.</span><span class="sxs-lookup"><span data-stu-id="dc761-232">The .ps1 files in the paths listed in the Path environment variable (`$env:path`) in the remote session.</span></span>
- <span data-ttu-id="dc761-233">Filter und function.</span><span class="sxs-lookup"><span data-stu-id="dc761-233">Filter and Function.</span></span> <span data-ttu-id="dc761-234">Die Windows PowerShell-Funktionen in der Remotesitzung.</span><span class="sxs-lookup"><span data-stu-id="dc761-234">The Windows PowerShell functions in the remote session.</span></span>
- <span data-ttu-id="dc761-235">Skript.</span><span class="sxs-lookup"><span data-stu-id="dc761-235">Script.</span></span> <span data-ttu-id="dc761-236">Die Skriptblöcke in der Remotesitzung.</span><span class="sxs-lookup"><span data-stu-id="dc761-236">The script blocks in the remote session.</span></span>

```yaml
Type: System.Management.Automation.CommandTypes
Parameter Sets: (All)
Aliases: Type
Accepted values: Alias, Function, Filter, Cmdlet, ExternalScript, Application, Script, Workflow, Configuration, All

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dc761-237">-Disablenamecheck</span><span class="sxs-lookup"><span data-stu-id="dc761-237">-DisableNameChecking</span></span>

<span data-ttu-id="dc761-238">Gibt an, dass dieses Cmdlet die Meldung unterdrückt, die Sie warnt, wenn Sie ein Cmdlet oder eine Funktion importieren, deren Name ein nicht genehmigtes Verb oder ein unzulässiges Zeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="dc761-238">Indicates that this cmdlet suppresses the message that warns you when you import a cmdlet or function whose name includes an unapproved verb or a prohibited character.</span></span>

<span data-ttu-id="dc761-239">Wenn ein Modul, das Sie importieren, Cmdlets oder Funktionen exportiert, die nicht genehmigte Verben in ihren Namen haben, zeigt Windows PowerShell standardmäßig die folgende Warnmeldung an:</span><span class="sxs-lookup"><span data-stu-id="dc761-239">By default, when a module that you import exports cmdlets or functions that have unapproved verbs in their names, the Windows PowerShell displays the following warning message:</span></span>

<span data-ttu-id="dc761-240">"Warnung: einige importierte Befehlsnamen enthalten nicht genehmigte Verben, die Sie möglicherweise weniger auffallen machen.</span><span class="sxs-lookup"><span data-stu-id="dc761-240">"WARNING: Some imported command names include unapproved verbs which might make them less discoverable.</span></span> <span data-ttu-id="dc761-241">Verwenden Sie den Verbose-Parameter, um weitere Details `Get-Verb` anzuzeigen, oder geben Sie ein, um die Liste der genehmigten Verben anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="dc761-241">Use the Verbose parameter for more detail or type `Get-Verb` to see the list of approved verbs."</span></span>

<span data-ttu-id="dc761-242">Diese Meldung ist nur eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="dc761-242">This message is only a warning.</span></span> <span data-ttu-id="dc761-243">Es wird trotzdem das gesamte Modul einschließlich nicht konformer Befehle importiert.</span><span class="sxs-lookup"><span data-stu-id="dc761-243">The complete module is still imported, including the non-conforming commands.</span></span> <span data-ttu-id="dc761-244">Obwohl die Meldung für Modulbenutzer angezeigt wird, sollte das Namensproblem vom Modulautor behoben werden.</span><span class="sxs-lookup"><span data-stu-id="dc761-244">Although the message is displayed to module users, the naming problem should be fixed by the module author.</span></span>

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

### <span data-ttu-id="dc761-245">-Formattyname</span><span class="sxs-lookup"><span data-stu-id="dc761-245">-FormatTypeName</span></span>

<span data-ttu-id="dc761-246">Gibt Formatierungs Anweisungen für die angegebenen Microsoft .NET Framework-Typen an.</span><span class="sxs-lookup"><span data-stu-id="dc761-246">Specifies formatting instructions for the specified Microsoft .NET Framework types.</span></span>
<span data-ttu-id="dc761-247">Geben Sie die Typnamen ein.</span><span class="sxs-lookup"><span data-stu-id="dc761-247">Enter the type names.</span></span>
<span data-ttu-id="dc761-248">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="dc761-248">Wildcards are permitted.</span></span>

<span data-ttu-id="dc761-249">Der Wert dieses Parameters muss dem Namen eines Typs entsprechen, der von einem `Get-FormatData` Befehl in der Sitzung zurückgegeben wird, aus der die Befehle importiert werden.</span><span class="sxs-lookup"><span data-stu-id="dc761-249">The value of this parameter must be the name of a type that is returned by a `Get-FormatData` command in the session from which the commands are being imported.</span></span> <span data-ttu-id="dc761-250">Um alle Formatierungsdaten in der Remote Sitzung zu erhalten, geben Sie ein `*` .</span><span class="sxs-lookup"><span data-stu-id="dc761-250">To get all of the formatting data in the remote session, type `*`.</span></span>

<span data-ttu-id="dc761-251">Wenn der Befehl weder den **CommandName** -Parameter noch den **formattypame** -Parameter enthält, `Import-PSSession` importiert Formatierungs Anweisungen für alle .NET Framework Typen, die von einem `Get-FormatData` Befehl in der Remote Sitzung zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="dc761-251">If the command does not include either the **CommandName** or **FormatTypeName** parameter, `Import-PSSession` imports formatting instructions for all .NET Framework types returned by a `Get-FormatData` command in the remote session.</span></span>

<span data-ttu-id="dc761-252">Wenn Sie den **FormatTypeName** -Parameter verwenden, werden keine Befehle importiert, sofern nicht der **CommandName** -Parameter verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="dc761-252">If you use the **FormatTypeName** parameter, no commands are imported unless you use the **CommandName** parameter.</span></span>

<span data-ttu-id="dc761-253">Entsprechend werden bei Verwendung des **CommandName** -Parameters die Formatierungsdateien für die Befehle nicht importiert, sofern Sie nicht den **FormatTypeName** -Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="dc761-253">Similarly, if you use the **CommandName** parameter, the formatting files for the commands are not imported unless you use the **FormatTypeName** parameter.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dc761-254">-Fullyqualifiedmodule</span><span class="sxs-lookup"><span data-stu-id="dc761-254">-FullyQualifiedModule</span></span>

<span data-ttu-id="dc761-255">Gibt Module an, deren Namen in Form von **modulespecification** -Objekten angegeben sind (im Abschnitt "Hinweise" des [modulespecification-Konstruktors (Hash Tabelle)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_) im PowerShell-SDK beschrieben.</span><span class="sxs-lookup"><span data-stu-id="dc761-255">Specifies modules with names that are specified in the form of **ModuleSpecification** objects (described in the Remarks section of [ModuleSpecification Constructor (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_) in the PowerShell SDK.</span></span> <span data-ttu-id="dc761-256">Der **fullyqualifiedmodule** -Parameter akzeptiert z. b. einen Modulnamen, der im folgenden Format angegeben ist:</span><span class="sxs-lookup"><span data-stu-id="dc761-256">For example, the **FullyQualifiedModule** parameter accepts a module name that is specified in the format:</span></span>

- <span data-ttu-id="dc761-257">`@{ModuleName = "modulename"; ModuleVersion = "version_number"}` oder</span><span class="sxs-lookup"><span data-stu-id="dc761-257">`@{ModuleName = "modulename"; ModuleVersion = "version_number"}` or</span></span>
- <span data-ttu-id="dc761-258">`@{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}`.</span><span class="sxs-lookup"><span data-stu-id="dc761-258">`@{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}`.</span></span>

<span data-ttu-id="dc761-259">**ModuleName** und **ModuleVersion** sind erforderlich, aber **Guid** ist optional.</span><span class="sxs-lookup"><span data-stu-id="dc761-259">**ModuleName** and **ModuleVersion** are required, but **Guid** is optional.</span></span>

<span data-ttu-id="dc761-260">Sie können den **fullyqualifiedmodule** -Parameter nicht im selben Befehl wie einen **Modul** Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="dc761-260">You cannot specify the **FullyQualifiedModule** parameter in the same command as a **Module** parameter.</span></span> <span data-ttu-id="dc761-261">Die beiden Parameter schließen sich gegenseitig aus.</span><span class="sxs-lookup"><span data-stu-id="dc761-261">The two parameters are mutually exclusive.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dc761-262">-Modul</span><span class="sxs-lookup"><span data-stu-id="dc761-262">-Module</span></span>

<span data-ttu-id="dc761-263">Gibt und ein Array von Befehlen in den Windows PowerShell-Snap-Ins und-Modulen an.</span><span class="sxs-lookup"><span data-stu-id="dc761-263">Specifies and array of commands in the Windows PowerShell snap-ins and modules.</span></span> <span data-ttu-id="dc761-264">Geben Sie die Snap-In- und Modulnamen ein.</span><span class="sxs-lookup"><span data-stu-id="dc761-264">Enter the snap-in and module names.</span></span> <span data-ttu-id="dc761-265">Platzhalter sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="dc761-265">Wildcards are not permitted.</span></span>

<span data-ttu-id="dc761-266">`Import-PSSession` Anbieter können nicht aus einem Snap-in importiert werden.</span><span class="sxs-lookup"><span data-stu-id="dc761-266">`Import-PSSession` cannot import providers from a snap-in.</span></span>

<span data-ttu-id="dc761-267">Weitere Informationen finden Sie unter [about_PSSnapins](/powershell/module/Microsoft.PowerShell.Core/About/about_PSSnapins) und [about_Modules](../Microsoft.PowerShell.Core/About/about_Modules.md).</span><span class="sxs-lookup"><span data-stu-id="dc761-267">For more information, see [about_PSSnapins](/powershell/module/Microsoft.PowerShell.Core/About/about_PSSnapins) and [about_Modules](../Microsoft.PowerShell.Core/About/about_Modules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSSnapin

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dc761-268">-Präfix</span><span class="sxs-lookup"><span data-stu-id="dc761-268">-Prefix</span></span>

<span data-ttu-id="dc761-269">Gibt ein Präfix der Nomen in den Namen importierter Befehle an.</span><span class="sxs-lookup"><span data-stu-id="dc761-269">Specifies a prefix to the nouns in the names of imported commands.</span></span>

<span data-ttu-id="dc761-270">Verwenden Sie diesen Parameter, um Namenskonflikte zu vermeiden, die auftreten können, wenn verschiedene Befehle in der Sitzung denselben Namen haben.</span><span class="sxs-lookup"><span data-stu-id="dc761-270">Use this parameter to avoid name conflicts that might occur when different commands in the session have the same name.</span></span>

<span data-ttu-id="dc761-271">Wenn Sie beispielsweise das Präfix Remote angeben und dann ein `Get-Date` Cmdlet importieren, ist das Cmdlet in der Sitzung als bekannt `Get-RemoteDate` und nicht mit dem ursprünglichen `Get-Date` Cmdlet verwechselt.</span><span class="sxs-lookup"><span data-stu-id="dc761-271">For instance, if you specify the prefix Remote and then import a `Get-Date` cmdlet, the cmdlet is known in the session as `Get-RemoteDate`, and it is not confused with the original `Get-Date` cmdlet.</span></span>

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

### <span data-ttu-id="dc761-272">-Sitzung</span><span class="sxs-lookup"><span data-stu-id="dc761-272">-Session</span></span>

<span data-ttu-id="dc761-273">Gibt die **PSSession** an, aus der die Cmdlets importiert werden.</span><span class="sxs-lookup"><span data-stu-id="dc761-273">Specifies the **PSSession** from which the cmdlets are imported.</span></span> <span data-ttu-id="dc761-274">Geben Sie eine Variable ein, die ein Sitzungs Objekt oder einen Befehl zum Abrufen eines Sitzungs Objekts enthält, z. b. einen- `New-PSSession` oder- `Get-PSSession` Befehl.</span><span class="sxs-lookup"><span data-stu-id="dc761-274">Enter a variable that contains a session object or a command that gets a session object, such as a `New-PSSession` or `Get-PSSession` command.</span></span> <span data-ttu-id="dc761-275">Sie können jeweils nur eine Sitzung angeben.</span><span class="sxs-lookup"><span data-stu-id="dc761-275">You can specify only one session.</span></span> <span data-ttu-id="dc761-276">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="dc761-276">This parameter is required.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dc761-277">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="dc761-277">CommonParameters</span></span>

<span data-ttu-id="dc761-278">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="dc761-278">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="dc761-279">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="dc761-279">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="dc761-280">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="dc761-280">INPUTS</span></span>

### <span data-ttu-id="dc761-281">Keine</span><span class="sxs-lookup"><span data-stu-id="dc761-281">None</span></span>

<span data-ttu-id="dc761-282">Objekte können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="dc761-282">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="dc761-283">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="dc761-283">OUTPUTS</span></span>

### <span data-ttu-id="dc761-284">System. Management. Automation. psmoduleinfo</span><span class="sxs-lookup"><span data-stu-id="dc761-284">System.Management.Automation.PSModuleInfo</span></span>

<span data-ttu-id="dc761-285">`Import-PSSession` Gibt das gleiche Modul Objekt zurück, das `New-Module` und die `Get-Module` Cmdlets zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="dc761-285">`Import-PSSession` returns the same module object that `New-Module` and `Get-Module` cmdlets return.</span></span>
<span data-ttu-id="dc761-286">Das importierte Modul ist jedoch temporär und nur in der aktuellen Sitzung vorhanden.</span><span class="sxs-lookup"><span data-stu-id="dc761-286">However, the imported module is temporary and exists only in the current session.</span></span> <span data-ttu-id="dc761-287">Verwenden Sie das-Cmdlet, um ein dauerhaftes Modul auf dem Datenträger zu erstellen `Export-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="dc761-287">To create a permanent module on disk, use the `Export-PSSession` cmdlet.</span></span>

## <span data-ttu-id="dc761-288">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="dc761-288">NOTES</span></span>

- <span data-ttu-id="dc761-289">`Import-PSSession` basiert auf der PowerShell-Remoting-Infrastruktur.</span><span class="sxs-lookup"><span data-stu-id="dc761-289">`Import-PSSession` relies on the  PowerShell remoting infrastructure.</span></span> <span data-ttu-id="dc761-290">Zur Verwendung dieses Cmdlets muss der Computer für das WS-Management-Remoting konfiguriert sein.</span><span class="sxs-lookup"><span data-stu-id="dc761-290">To use this cmdlet, the computer must be configured for WS-Management remoting.</span></span> <span data-ttu-id="dc761-291">Weitere Informationen finden Sie unter [about_Remote](../Microsoft.PowerShell.Core/about/about_Remote.md) und [about_Remote_Requirements](../Microsoft.PowerShell.Core/about/about_Remote_Requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc761-291">For more information, see [about_Remote](../Microsoft.PowerShell.Core/about/about_Remote.md) and [about_Remote_Requirements](../Microsoft.PowerShell.Core/about/about_Remote_Requirements.md).</span></span>
- <span data-ttu-id="dc761-292">`Import-PSSession` keine Variablen oder PowerShell-Anbieter werden importiert.</span><span class="sxs-lookup"><span data-stu-id="dc761-292">`Import-PSSession` does not import variables or  PowerShell providers.</span></span>
- <span data-ttu-id="dc761-293">Beim Importieren von Befehlen, die denselben Namen wie die Befehle in der aktuellen Sitzung haben, können die importierten Befehle Aliase, Funktionen und Cmdlets in der Sitzung ausblenden sowie Funktionen und Variablen in der Sitzung ersetzen.</span><span class="sxs-lookup"><span data-stu-id="dc761-293">When you import commands that have the same names as commands in the current session, the imported commands can hide aliases, functions, and cmdlets in the session and they can replace functions and variables in the session.</span></span> <span data-ttu-id="dc761-294">Um Namenskonflikte zu vermeiden, verwenden Sie den **Prefix** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="dc761-294">To prevent name conflicts, use the **Prefix** parameter.</span></span> <span data-ttu-id="dc761-295">Weitere Informationen finden Sie unter [about_Command_Precedence](../Microsoft.PowerShell.Core/about/about_Command_Precedence.md).</span><span class="sxs-lookup"><span data-stu-id="dc761-295">For more information, see [about_Command_Precedence](../Microsoft.PowerShell.Core/about/about_Command_Precedence.md).</span></span>
- <span data-ttu-id="dc761-296">`Import-PSSession` konvertiert alle Befehle in Funktionen, bevor Sie importiert werden.</span><span class="sxs-lookup"><span data-stu-id="dc761-296">`Import-PSSession` converts all commands into functions before it imports them.</span></span> <span data-ttu-id="dc761-297">Folglich zeigen importierte Befehle ein etwas anderes Verhalten, als wenn sie den ursprünglichen Befehlstyp behalten würden.</span><span class="sxs-lookup"><span data-stu-id="dc761-297">As a result, imported commands behave a bit differently than they would if they retained their original command type.</span></span> <span data-ttu-id="dc761-298">Wenn Sie z. B. ein Cmdlet aus einer PSSession importieren und dann ein Cmdlet desselben Namens aus einem Modul oder Snap-In importieren, wird standardmäßig das aus der PSSession importierte Cmdlet ausgeführt, weil Funktionen Vorrang vor Cmdlets haben.</span><span class="sxs-lookup"><span data-stu-id="dc761-298">For example, if you import a cmdlet from a PSSession and then import a cmdlet with the same name from a module or snap-in, the cmdlet that is imported from the PSSession always runs by default because functions take precedence over cmdlets.</span></span> <span data-ttu-id="dc761-299">Wenn Sie dagegen einen Alias in eine Sitzung importieren, die über einen Alias desselben Namens verfügt, wird immer der ursprüngliche Alias verwendet, weil Aliase Vorrang vor Funktionen haben.</span><span class="sxs-lookup"><span data-stu-id="dc761-299">Conversely, if you import an alias into a session that has an alias with the same name, the original alias is always used, because aliases take precedence over functions.</span></span> <span data-ttu-id="dc761-300">Weitere Informationen finden Sie unter [about_Command_Precedence](../Microsoft.PowerShell.Core/about/about_Command_Precedence.md).</span><span class="sxs-lookup"><span data-stu-id="dc761-300">For more information, see [about_Command_Precedence](../Microsoft.PowerShell.Core/about/about_Command_Precedence.md).</span></span>
- <span data-ttu-id="dc761-301">`Import-PSSession` verwendet das `Write-Progress` Cmdlet, um den Fortschritt des Befehls anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="dc761-301">`Import-PSSession` uses the `Write-Progress` cmdlet to display the progress of the command.</span></span> <span data-ttu-id="dc761-302">Während der Befehlsausführung wird u. U. die Statusanzeige angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dc761-302">You might see the progress bar while the command is running.</span></span>
- <span data-ttu-id="dc761-303">Zum Ermitteln der zu importierenden Befehle `Import-PSSession` verwendet das `Invoke-Command` Cmdlet, um einen `Get-Command` Befehl in der PSSession auszuführen.</span><span class="sxs-lookup"><span data-stu-id="dc761-303">To find the commands to import, `Import-PSSession` uses the `Invoke-Command` cmdlet to run a `Get-Command` command in the PSSession.</span></span> <span data-ttu-id="dc761-304">Um Formatierungsdaten für die Befehle zu erhalten, wird das- `Get-FormatData` Cmdlet verwendet.</span><span class="sxs-lookup"><span data-stu-id="dc761-304">To get formatting data for the commands, it uses the `Get-FormatData` cmdlet.</span></span> <span data-ttu-id="dc761-305">Wenn Sie einen Befehl ausführen, werden möglicherweise Fehlermeldungen von diesen Cmdlets angezeigt `Import-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="dc761-305">You might see error messages from these cmdlets when you run an `Import-PSSession` command.</span></span> <span data-ttu-id="dc761-306">Kann auch keine `Import-PSSession` Befehle aus einer PSSession importieren, die nicht die `Get-Command` `Get-FormatData` `Select-Object` Cmdlets,, und enthält `Get-Help` .</span><span class="sxs-lookup"><span data-stu-id="dc761-306">Also, `Import-PSSession` cannot import commands from a PSSession that does not include the `Get-Command`, `Get-FormatData`, `Select-Object`, and `Get-Help` cmdlets.</span></span>
- <span data-ttu-id="dc761-307">Importierte Befehle unterliegen den gleichen Beschränkungen wie andere Remotebefehle. Beispielweise können sie kein Programm mit einer Benutzeroberfläche, z. B. den Editor, starten.</span><span class="sxs-lookup"><span data-stu-id="dc761-307">Imported commands have the same limitations as other remote commands, including the inability to start a program with a user interface, such as Notepad.</span></span>
- <span data-ttu-id="dc761-308">Da Windows PowerShell-Profile nicht in pssessions ausgeführt werden, stehen die Befehle, die ein Profil einer Sitzung hinzufügt, nicht für zur Verfügung `Import-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="dc761-308">Because Windows PowerShell profiles are not run in PSSessions, the commands that a profile adds to a session are not available to `Import-PSSession`.</span></span> <span data-ttu-id="dc761-309">Zum Importieren von Befehlen aus einem Profil verwenden Sie einen- `Invoke-Command` Befehl, um das Profil manuell in der PSSession auszuführen, bevor Sie Befehle importieren.</span><span class="sxs-lookup"><span data-stu-id="dc761-309">To import commands from a profile, use an `Invoke-Command` command to run the profile in the PSSession manually before importing commands.</span></span>
- <span data-ttu-id="dc761-310">Das temporäre Modul, das `Import-PSSession` erstellt, kann eine Formatierungs Datei enthalten, auch wenn der Befehl keine Formatierungsdaten importiert.</span><span class="sxs-lookup"><span data-stu-id="dc761-310">The temporary module that `Import-PSSession` creates might include a formatting file, even if the command does not import formatting data.</span></span> <span data-ttu-id="dc761-311">Wenn durch den Befehl keine Formatierungsdaten importiert werden, enthält keine der erstellten Formatierungsdateien Formatierungsdaten.</span><span class="sxs-lookup"><span data-stu-id="dc761-311">If the command does not import formatting data, any formatting files that are created will not contain formatting data.</span></span>
- <span data-ttu-id="dc761-312">Um zu verwenden `Import-PSSession` , kann die Ausführungs Richtlinie in der aktuellen Sitzung nicht eingeschränkt oder AllSigned sein, da das temporäre Modul, das `Import-PSSession` erstellt, nicht signierte Skriptdateien enthält, die von diesen Richtlinien nicht unterbunden werden.</span><span class="sxs-lookup"><span data-stu-id="dc761-312">To use `Import-PSSession`, the execution policy in the current session cannot be Restricted or AllSigned, because the temporary module that `Import-PSSession` creates contains unsigned script files that are prohibited by these policies.</span></span> <span data-ttu-id="dc761-313">Wenn Sie `Import-PSSession` ohne Änderung der Ausführungs Richtlinie für den lokalen Computer verwenden möchten, verwenden Sie den **Scope** -Parameter von, `Set-ExecutionPolicy` um eine weniger restriktive Ausführungs Richtlinie für einen einzelnen Prozess festzulegen.</span><span class="sxs-lookup"><span data-stu-id="dc761-313">To use `Import-PSSession` without changing the execution policy for the local computer, use the **Scope** parameter of `Set-ExecutionPolicy` to set a less restrictive execution policy for a single process.</span></span>
- <span data-ttu-id="dc761-314">In Windows PowerShell 2.0 enthalten Hilfethemen zu Befehlen, die aus einer anderen Sitzung importiert werden, nicht das über den **Prefix** -Parameter zugewiesene Präfix.</span><span class="sxs-lookup"><span data-stu-id="dc761-314">In Windows PowerShell 2.0, help topics for commands that are imported from another session do not include the prefix that you assign by using the **Prefix** parameter.</span></span> <span data-ttu-id="dc761-315">Um Hilfe zu einem importierten Befehl in Windows PowerShell 2.0 zu erhalten, verwenden Sie den ursprünglichen Befehlsnamen (ohne Präfix).</span><span class="sxs-lookup"><span data-stu-id="dc761-315">To get help for an imported command in Windows PowerShell 2.0, use the original (non-prefixed) command name.</span></span>

## <span data-ttu-id="dc761-316">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="dc761-316">RELATED LINKS</span></span>

[<span data-ttu-id="dc761-317">Export-PSSession</span><span class="sxs-lookup"><span data-stu-id="dc761-317">Export-PSSession</span></span>](Export-PSSession.md)
