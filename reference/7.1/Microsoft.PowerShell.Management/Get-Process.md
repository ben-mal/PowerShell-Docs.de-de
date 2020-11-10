---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-process?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Process
ms.openlocfilehash: 1d4881638b616d93414851b98b0a75fca72169ff
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94389792"
---
# <span data-ttu-id="b57d9-103">Get-Process</span><span class="sxs-lookup"><span data-stu-id="b57d9-103">Get-Process</span></span>

## <span data-ttu-id="b57d9-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="b57d9-104">SYNOPSIS</span></span>
<span data-ttu-id="b57d9-105">Ruft die Prozesse ab, die auf dem lokalen Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b57d9-105">Gets the processes that are running on the local computer.</span></span>

## <span data-ttu-id="b57d9-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b57d9-106">SYNTAX</span></span>

### <span data-ttu-id="b57d9-107">Name (Standard)</span><span class="sxs-lookup"><span data-stu-id="b57d9-107">Name (Default)</span></span>

```
Get-Process [[-Name] <String[]>] [-Module] [-FileVersionInfo] [<CommonParameters>]
```

### <span data-ttu-id="b57d9-108">Namewithusername</span><span class="sxs-lookup"><span data-stu-id="b57d9-108">NameWithUserName</span></span>

```
Get-Process [[-Name] <String[]>] -IncludeUserName [<CommonParameters>]
```

### <span data-ttu-id="b57d9-109">Id</span><span class="sxs-lookup"><span data-stu-id="b57d9-109">Id</span></span>

```
Get-Process -Id <Int32[]> [-Module] [-FileVersionInfo] [<CommonParameters>]
```

### <span data-ttu-id="b57d9-110">Idwithusername</span><span class="sxs-lookup"><span data-stu-id="b57d9-110">IdWithUserName</span></span>

```
Get-Process -Id <Int32[]> -IncludeUserName [<CommonParameters>]
```

### <span data-ttu-id="b57d9-111">InputObject</span><span class="sxs-lookup"><span data-stu-id="b57d9-111">InputObject</span></span>

```
Get-Process -InputObject <Process[]> [-Module] [-FileVersionInfo] [<CommonParameters>]
```

### <span data-ttu-id="b57d9-112">Inputobjectwithusername</span><span class="sxs-lookup"><span data-stu-id="b57d9-112">InputObjectWithUserName</span></span>

```
Get-Process -InputObject <Process[]> -IncludeUserName [<CommonParameters>]
```

## <span data-ttu-id="b57d9-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b57d9-113">DESCRIPTION</span></span>

<span data-ttu-id="b57d9-114">Das- `Get-Process` Cmdlet ruft die Prozesse auf einem lokalen Computer oder einem Remote Computer ab.</span><span class="sxs-lookup"><span data-stu-id="b57d9-114">The `Get-Process` cmdlet gets the processes on a local or remote computer.</span></span>

<span data-ttu-id="b57d9-115">Ohne Parameter ruft dieses Cmdlet alle Prozesse auf dem lokalen Computer ab.</span><span class="sxs-lookup"><span data-stu-id="b57d9-115">Without parameters, this cmdlet gets all of the processes on the local computer.</span></span> <span data-ttu-id="b57d9-116">Sie können auch einen bestimmten Prozess mit dem Prozessnamen oder der Prozess-ID (PID) angeben oder ein Prozess Objekt über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="b57d9-116">You can also specify a particular process by process name or process ID (PID) or pass a process object through the pipeline to this cmdlet.</span></span>

<span data-ttu-id="b57d9-117">Standardmäßig gibt dieses Cmdlet ein Prozess Objekt mit detaillierten Informationen über den Prozess zurück und unterstützt Methoden, mit denen Sie den Prozess starten und abbrechen können.</span><span class="sxs-lookup"><span data-stu-id="b57d9-117">By default, this cmdlet returns a process object that has detailed information about the process and supports methods that let you start and stop the process.</span></span> <span data-ttu-id="b57d9-118">Sie können auch die Parameter des `Get-Process` Cmdlets verwenden, um Datei Versionsinformationen für das Programm zu erhalten, das im Prozess ausgeführt wird, und um die vom Prozess geladenen Module zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="b57d9-118">You can also use the parameters of the `Get-Process` cmdlet to get file version information for the program that runs in the process and to get the modules that the process loaded.</span></span>

## <span data-ttu-id="b57d9-119">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="b57d9-119">EXAMPLES</span></span>

### <span data-ttu-id="b57d9-120">Beispiel 1: erhalten einer Liste aller aktiven Prozesse auf dem lokalen Computer</span><span class="sxs-lookup"><span data-stu-id="b57d9-120">Example 1: Get a list of all active processes on the local computer</span></span>

```powershell
Get-Process
```

<span data-ttu-id="b57d9-121">Mit diesem Befehl wird eine Liste aller aktiven Prozesse abgerufen, die auf dem lokalen Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b57d9-121">This command gets a list of all active processes running on the local computer.</span></span> <span data-ttu-id="b57d9-122">Eine Definition der einzelnen Spalten finden Sie im Abschnitt " [Hinweise](#notes) ".</span><span class="sxs-lookup"><span data-stu-id="b57d9-122">For a definition of each column, see the [Notes](#notes) section.</span></span>

### <span data-ttu-id="b57d9-123">Beispiel 2: alle verfügbaren Daten zu einem oder mehreren Prozessen</span><span class="sxs-lookup"><span data-stu-id="b57d9-123">Example 2: Get all available data about one or more processes</span></span>

```powershell
Get-Process winword, explorer | Format-List *
```

<span data-ttu-id="b57d9-124">Mit diesem Befehl werden alle verfügbaren Daten zum Winword- und zum Explorer-Prozess auf dem Computer abgerufen.</span><span class="sxs-lookup"><span data-stu-id="b57d9-124">This command gets all available data about the Winword and Explorer processes on the computer.</span></span> <span data-ttu-id="b57d9-125">Er verwendet den **Name** -Parameter, um die Prozesse anzugeben, der optionale Parameter Name wird jedoch ausgelassen.</span><span class="sxs-lookup"><span data-stu-id="b57d9-125">It uses the **Name** parameter to specify the processes, but it omits the optional parameter name.</span></span> <span data-ttu-id="b57d9-126">Der Pipeline Operator `|` übergibt die Daten an das `Format-List` Cmdlet, das alle verfügbaren Eigenschaften `*` der Winword-und Explorer-Prozess Objekte anzeigt.</span><span class="sxs-lookup"><span data-stu-id="b57d9-126">The pipeline operator `|` passes the data to the `Format-List` cmdlet, which displays all available properties `*` of the Winword and Explorer process objects.</span></span>

<span data-ttu-id="b57d9-127">Sie können die Prozesse auch anhand ihrer Prozess-IDs angeben.</span><span class="sxs-lookup"><span data-stu-id="b57d9-127">You can also identify the processes by their process IDs.</span></span> <span data-ttu-id="b57d9-128">Beispielsweise `Get-Process -Id 664, 2060`.</span><span class="sxs-lookup"><span data-stu-id="b57d9-128">For instance, `Get-Process -Id 664, 2060`.</span></span>

### <span data-ttu-id="b57d9-129">Beispiel 3: alle Prozesse mit einem Workingset, das größer ist als die angegebene Größe</span><span class="sxs-lookup"><span data-stu-id="b57d9-129">Example 3: Get all processes with a working set greater than a specified size</span></span>

```powershell
Get-Process | Where-Object {$_.WorkingSet -gt 20000000}
```

<span data-ttu-id="b57d9-130">Mit diesem Befehl werden alle Prozesse mit einem Arbeitssatz abgerufen, dessen Größe 20 MB übersteigt.</span><span class="sxs-lookup"><span data-stu-id="b57d9-130">This command gets all processes that have a working set greater than 20 MB.</span></span> <span data-ttu-id="b57d9-131">Er verwendet das `Get-Process` Cmdlet, um alle laufenden Prozesse zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="b57d9-131">It uses the `Get-Process` cmdlet to get all running processes.</span></span> <span data-ttu-id="b57d9-132">Der Pipeline Operator `|` übergibt die Prozess Objekte an das `Where-Object` Cmdlet, das nur das Objekt auswählt, dessen Wert größer als 20 Millionen Byte für die **Workingset** -Eigenschaft ist.</span><span class="sxs-lookup"><span data-stu-id="b57d9-132">The pipeline operator `|` passes the process objects to the `Where-Object` cmdlet, which selects only the object with a value greater than 20,000,000 bytes for the **WorkingSet** property.</span></span>

<span data-ttu-id="b57d9-133">**Workingset** ist eine von vielen Eigenschaften von Prozess Objekten.</span><span class="sxs-lookup"><span data-stu-id="b57d9-133">**WorkingSet** is one of many properties of process objects.</span></span> <span data-ttu-id="b57d9-134">Um alle Eigenschaften anzuzeigen, geben Sie ein `Get-Process | Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="b57d9-134">To see all of the properties, type `Get-Process | Get-Member`.</span></span> <span data-ttu-id="b57d9-135">Standardmäßig werden die Werte aller Mengeneigenschaften in Bytes angegeben, auch wenn sie in der Standardanzeige in Kilobytes und Megabytes aufgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b57d9-135">By default, the values of all amount properties are in bytes, even though the default display lists them in kilobytes and megabytes.</span></span>

### <span data-ttu-id="b57d9-136">Beispiel 4: Auflisten von Prozessen auf dem Computer in Gruppen basierend auf der Priorität</span><span class="sxs-lookup"><span data-stu-id="b57d9-136">Example 4: List processes on the computer in groups based on priority</span></span>

```powershell
$A = Get-Process
$A | Get-Process | Format-Table -View priority
```

<span data-ttu-id="b57d9-137">Diese Befehle Listen die Prozesse auf dem Computer in Gruppen auf Grundlage ihrer Prioritäts Klasse auf.</span><span class="sxs-lookup"><span data-stu-id="b57d9-137">These commands list the processes on the computer in groups based on their priority class.</span></span> <span data-ttu-id="b57d9-138">Der erste Befehl ruft alle Prozesse auf dem Computer ab und speichert Sie dann in der `$A` Variablen.</span><span class="sxs-lookup"><span data-stu-id="b57d9-138">The first command gets all the processes on the computer and then stores them in the `$A` variable.</span></span>

<span data-ttu-id="b57d9-139">Mit dem zweiten Befehl wird das in der Variablen gespeicherte **Prozess** Objekt `$A` an das `Get-Process` Cmdlet weitergeleitet, dann an das `Format-Table` Cmdlet, das die Prozesse mithilfe der **Prioritäts** Ansicht formatiert.</span><span class="sxs-lookup"><span data-stu-id="b57d9-139">The second command pipes the **Process** object stored in the `$A` variable to the `Get-Process` cmdlet, then to the `Format-Table` cmdlet, which formats the processes by using the **Priority** view.</span></span>

<span data-ttu-id="b57d9-140">Die **Prioritäts** Ansicht und andere Ansichten werden in den PS1XML-Format Dateien im PowerShell-Basisverzeichnis ( `$pshome` ) definiert.</span><span class="sxs-lookup"><span data-stu-id="b57d9-140">The **Priority** view, and other views, are defined in the PS1XML format files in the PowerShell home directory (`$pshome`).</span></span>

### <span data-ttu-id="b57d9-141">Beispiel 5: Hinzufügen einer Eigenschaft zur Standard Get-Process Ausgabe Anzeige</span><span class="sxs-lookup"><span data-stu-id="b57d9-141">Example 5: Add a property to the standard Get-Process output display</span></span>

```powershell
Get-Process pwsh | Format-Table `
    @{Label = "NPM(K)"; Expression = {[int]($_.NPM / 1024)}},
    @{Label = "PM(K)"; Expression = {[int]($_.PM / 1024)}},
    @{Label = "WS(K)"; Expression = {[int]($_.WS / 1024)}},
    @{Label = "VM(M)"; Expression = {[int]($_.VM / 1MB)}},
    @{Label = "CPU(s)"; Expression = {if ($_.CPU) {$_.CPU.ToString("N")}}},
    Id, MachineName, ProcessName -AutoSize
```

```Output
NPM(K) PM(K) WS(K) VM(M) CPU(s)   Id MachineName ProcessName
------ ----- ----- ----- ------   -- ----------- -----------
     6 23500 31340   142 1.70   1980 .           pwsh
     6 23500 31348   142 2.75   4016 .           pwsh
    27 54572 54520   576 5.52   4428 .           pwsh
```

<span data-ttu-id="b57d9-142">In diesem Beispiel werden Prozesse vom lokalen Computer und einem Remote Computer (S1) abgerufen.</span><span class="sxs-lookup"><span data-stu-id="b57d9-142">This example retrieves processes from the local computer and a remote computer (S1).</span></span> <span data-ttu-id="b57d9-143">Die abgerufenen Prozesse werden an den Befehl weitergeleitet `Format-Table` , der die **MachineName** -Eigenschaft der Standard `Get-Process` Ausgabe Anzeige hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="b57d9-143">The retrieved processes are piped to the `Format-Table` command that adds the **MachineName** property to the standard `Get-Process` output display.</span></span>

### <span data-ttu-id="b57d9-144">Beispiel 6: erhalten von Versionsinformationen für einen Prozess</span><span class="sxs-lookup"><span data-stu-id="b57d9-144">Example 6: Get version information for a process</span></span>

```powershell
Get-Process pwsh -FileVersionInfo
```

```Output
ProductVersion   FileVersion      FileName
--------------   -----------      --------
6.1.2            6.1.2            C:\Program Files\PowerShell\6\pwsh.exe
```

<span data-ttu-id="b57d9-145">Dieser Befehl verwendet den **FileVersionInfo** -Parameter, um die Versionsinformationen für die pwsh.exe-Datei zu erhalten, die das Hauptmodul für den PowerShell-Prozess ist.</span><span class="sxs-lookup"><span data-stu-id="b57d9-145">This command uses the **FileVersionInfo** parameter to get the version information for the pwsh.exe file that is the main module for the PowerShell process.</span></span>

<span data-ttu-id="b57d9-146">Wenn Sie diesen Befehl mit Prozessen ausführen möchten, die Sie nicht unter Windows Vista und höheren Versionen von Windows besitzen, müssen Sie PowerShell mit der Option als Administrator ausführen öffnen.</span><span class="sxs-lookup"><span data-stu-id="b57d9-146">To run this command with processes that you do not own on Windows Vista and later versions of Windows, you must open PowerShell with the Run as administrator option.</span></span>

### <span data-ttu-id="b57d9-147">Beispiel 7: Get-Module, die mit dem angegebenen Prozess geladen wurden</span><span class="sxs-lookup"><span data-stu-id="b57d9-147">Example 7: Get modules loaded with the specified process</span></span>

```powershell
Get-Process SQL* -Module
```

<span data-ttu-id="b57d9-148">Dieser Befehl verwendet den **Module-Parameter,** um die Module, die vom Prozess geladen wurden, zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="b57d9-148">This command uses the **Module** parameter to get the modules that have been loaded by the process.</span></span>
<span data-ttu-id="b57d9-149">Dieser Befehl ruft die Module für die Prozesse ab, deren Namen mit SQL beginnen.</span><span class="sxs-lookup"><span data-stu-id="b57d9-149">This command gets the modules for the processes that have names that begin with SQL.</span></span>

<span data-ttu-id="b57d9-150">Wenn Sie diesen Befehl unter Windows Vista und höheren Versionen von Windows mit Prozessen ausführen möchten, die Sie nicht besitzen, müssen Sie PowerShell mit der Option als Administrator ausführen starten.</span><span class="sxs-lookup"><span data-stu-id="b57d9-150">To run this command on Windows Vista and later versions of Windows with processes that you do not own, you must start PowerShell with the Run as administrator option.</span></span>

### <span data-ttu-id="b57d9-151">Beispiel 8: Ermitteln des Besitzers eines Prozesses</span><span class="sxs-lookup"><span data-stu-id="b57d9-151">Example 8: Find the owner of a process</span></span>

```powershell
Get-Process pwsh -IncludeUserName
```

```Output
Handles      WS(K)   CPU(s)     Id UserName            ProcessName
-------      -----   ------     -- --------            -----------
    782     132080     2.08   2188 DOMAIN01\user01     pwsh
```

<span data-ttu-id="b57d9-152">Dieser Befehl zeigt, wie der Besitzer eines Prozesses ermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="b57d9-152">This command shows how to find the owner of a process.</span></span>
<span data-ttu-id="b57d9-153">Unter Windows sind für den **includeusername** -Parameter erhöhte Benutzerrechte erforderlich (als Administrator ausführen).</span><span class="sxs-lookup"><span data-stu-id="b57d9-153">On Windows, the **IncludeUserName** parameter requires elevated user rights (Run as Administrator).</span></span>
<span data-ttu-id="b57d9-154">Die Ausgabe zeigt, dass der Besitzer Domain01\user01. ist.</span><span class="sxs-lookup"><span data-stu-id="b57d9-154">The output reveals that the owner is Domain01\user01.</span></span>

### <span data-ttu-id="b57d9-155">Beispiel 9: Verwenden einer automatischen Variablen zum Identifizieren des Prozesses, der die aktuelle Sitzung gehostet</span><span class="sxs-lookup"><span data-stu-id="b57d9-155">Example 9: Use an automatic variable to identify the process hosting the current session</span></span>

```powershell
Get-Process pwsh
```

```Output
NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
------    -----      -----     ------      --  -- -----------
    83    96.21     105.95       4.33    1192  10 pwsh
    79    83.81     117.61       2.16   10580  10 pwsh
```

```powershell
Get-Process -Id $PID
```

```Output
NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
------    -----      -----     ------      --  -- -----------
    83    96.21      77.53       4.39    1192  10 pwsh
```

<span data-ttu-id="b57d9-156">Diese Befehle zeigen, wie Sie die `$PID` Automatische Variable verwenden, um den Prozess zu identifizieren, der die aktuelle PowerShell-Sitzung gehostet.</span><span class="sxs-lookup"><span data-stu-id="b57d9-156">These commands show how to use the `$PID` automatic variable to identify the process that is hosting the current PowerShell session.</span></span> <span data-ttu-id="b57d9-157">Sie können den Hostprozess mithilfe dieser Methode von anderen PowerShell-Prozessen unterscheiden, die Sie beenden oder schließen möchten.</span><span class="sxs-lookup"><span data-stu-id="b57d9-157">You can use this method to distinguish the host process from other PowerShell processes that you might want to stop or close.</span></span>

<span data-ttu-id="b57d9-158">Der erste Befehl ruft alle PowerShell-Prozesse in der aktuellen Sitzung ab.</span><span class="sxs-lookup"><span data-stu-id="b57d9-158">The first command gets all of the PowerShell processes in the current session.</span></span>

<span data-ttu-id="b57d9-159">Der zweite Befehl ruft den PowerShell-Prozess ab, der die aktuelle Sitzung gehostet.</span><span class="sxs-lookup"><span data-stu-id="b57d9-159">The second command gets the PowerShell process that is hosting the current session.</span></span>

### <span data-ttu-id="b57d9-160">Beispiel 10: Hiermit werden alle Prozesse mit einem Hauptfenster Titel und in einer Tabelle angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b57d9-160">Example 10: Get all processes that have a main window title and display them in a table</span></span>

```powershell
Get-Process | Where-Object {$_.mainWindowTitle} | Format-Table Id, Name, mainWindowtitle -AutoSize
```

<span data-ttu-id="b57d9-161">Mit diesem Befehl werden alle Prozesse mit einem Hauptfenstertitel abgerufen und in einer Tabelle mit der Prozess-ID und dem Prozessnamen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b57d9-161">This command gets all the processes that have a main window title, and it displays them in a table with the process ID and the process name.</span></span>

<span data-ttu-id="b57d9-162">Die **MainWindowTitle** -Eigenschaft ist nur eine von vielen nützlichen Eigenschaften des **Prozess** Objekts, das `Get-Process` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="b57d9-162">The **mainWindowTitle** property is just one of many useful properties of the **Process** object that `Get-Process` returns.</span></span> <span data-ttu-id="b57d9-163">Um alle Eigenschaften anzuzeigen, reichen Sie die Ergebnisse eines Befehls über `Get-Process` die Pipeline an das `Get-Member` Cmdlet weiter `Get-Process | Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="b57d9-163">To view all of the properties, pipe the results of a `Get-Process` command to the `Get-Member` cmdlet `Get-Process | Get-Member`.</span></span>

## <span data-ttu-id="b57d9-164">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b57d9-164">PARAMETERS</span></span>

### <span data-ttu-id="b57d9-165">-FileVersionInfo</span><span class="sxs-lookup"><span data-stu-id="b57d9-165">-FileVersionInfo</span></span>

<span data-ttu-id="b57d9-166">Gibt an, dass dieses Cmdlet die Datei Versionsinformationen für das Programm abruft, das im Prozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b57d9-166">Indicates that this cmdlet gets the file version information for the program that runs in the process.</span></span>

<span data-ttu-id="b57d9-167">Unter Windows Vista und höheren Versionen von Windows müssen Sie PowerShell mit der Option "als Administrator ausführen" öffnen, um diesen Parameter für Prozesse zu verwenden, deren Besitzer Sie sind.</span><span class="sxs-lookup"><span data-stu-id="b57d9-167">On Windows Vista and later versions of Windows, you must open PowerShell with the Run as administrator option to use this parameter on processes that you do not own.</span></span>

<span data-ttu-id="b57d9-168">Verwenden Sie das-Cmdlet, um die Datei Versionsinformationen für einen Prozess auf einem Remote Computer zu erhalten `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="b57d9-168">To get file version information for a process on a remote computer, use the `Invoke-Command` cmdlet.</span></span>

<span data-ttu-id="b57d9-169">Die Verwendung dieses Parameters entspricht dem erhalten der **MainModule. FileVersionInfo** -Eigenschaft für jedes Prozess Objekt.</span><span class="sxs-lookup"><span data-stu-id="b57d9-169">Using this parameter is equivalent to getting the **MainModule.FileVersionInfo** property of each process object.</span></span> <span data-ttu-id="b57d9-170">Wenn Sie diesen Parameter verwenden, `Get-Process` gibt ein **FileVersionInfo** -Objekt **System. Diagnostics. FileVersionInfo** zurück, kein Prozess Objekt.</span><span class="sxs-lookup"><span data-stu-id="b57d9-170">When you use this parameter, `Get-Process` returns a **FileVersionInfo** object **System.Diagnostics.FileVersionInfo** , not a process object.</span></span> <span data-ttu-id="b57d9-171">Daher können Sie die Ausgabe des Befehls nicht an ein Cmdlet übergeben, das ein Prozess Objekt erwartet, z `Stop-Process` . b..</span><span class="sxs-lookup"><span data-stu-id="b57d9-171">So, you cannot pipe the output of the command to a cmdlet that expects a process object, such as `Stop-Process`.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Name, Id, InputObject
Aliases: FV, FVI

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b57d9-172">-Id</span><span class="sxs-lookup"><span data-stu-id="b57d9-172">-Id</span></span>

<span data-ttu-id="b57d9-173">Gibt einen oder mehrere Prozesse anhand der Prozess-ID (PID) an.</span><span class="sxs-lookup"><span data-stu-id="b57d9-173">Specifies one or more processes by process ID (PID).</span></span> <span data-ttu-id="b57d9-174">Wenn Sie mehrere IDs angeben, trennen Sie diese durch Kommas.</span><span class="sxs-lookup"><span data-stu-id="b57d9-174">To specify multiple IDs, use commas to separate the IDs.</span></span> <span data-ttu-id="b57d9-175">Um die PID eines Prozesses zu ermitteln, geben Sie ein `Get-Process` .</span><span class="sxs-lookup"><span data-stu-id="b57d9-175">To find the PID of a process, type `Get-Process`.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: Id, IdWithUserName
Aliases: PID

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b57d9-176">-Includeusername</span><span class="sxs-lookup"><span data-stu-id="b57d9-176">-IncludeUserName</span></span>

<span data-ttu-id="b57d9-177">Gibt an, dass der UserName-Wert des **Prozess** Objekts mit den Ergebnissen des Befehls zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="b57d9-177">Indicates that the UserName value of the **Process** object is returned with results of the command.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NameWithUserName, IdWithUserName, InputObjectWithUserName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b57d9-178">-InputObject</span><span class="sxs-lookup"><span data-stu-id="b57d9-178">-InputObject</span></span>

<span data-ttu-id="b57d9-179">Gibt Prozessobjekte an.</span><span class="sxs-lookup"><span data-stu-id="b57d9-179">Specifies one or more process objects.</span></span> <span data-ttu-id="b57d9-180">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="b57d9-180">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

```yaml
Type: System.Diagnostics.Process[]
Parameter Sets: InputObject, InputObjectWithUserName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="b57d9-181">-Modul</span><span class="sxs-lookup"><span data-stu-id="b57d9-181">-Module</span></span>

<span data-ttu-id="b57d9-182">Gibt an, dass dieses Cmdlet die Module abruft, die von den Prozessen geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="b57d9-182">Indicates that this cmdlet gets the modules that have been loaded by the processes.</span></span>

<span data-ttu-id="b57d9-183">Unter Windows Vista und höheren Versionen von Windows müssen Sie PowerShell mit der Option " **als Administrator ausführen** " öffnen, um diesen Parameter für Prozesse zu verwenden, deren Besitzer Sie sind.</span><span class="sxs-lookup"><span data-stu-id="b57d9-183">On Windows Vista and later versions of Windows, you must open PowerShell with the **Run as administrator** option to use this parameter on processes that you do not own.</span></span>

<span data-ttu-id="b57d9-184">Verwenden Sie das Cmdlet, um die Module, die von einem Prozess auf einem Remote Computer geladen wurden, zu erhalten `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="b57d9-184">To get the modules that have been loaded by a process on a remote computer, use the `Invoke-Command` cmdlet.</span></span>

<span data-ttu-id="b57d9-185">Dieser Parameter entspricht dem erhalten der **modules** -Eigenschaft jedes Prozess Objekts.</span><span class="sxs-lookup"><span data-stu-id="b57d9-185">This parameter is equivalent to getting the **Modules** property of each process object.</span></span> <span data-ttu-id="b57d9-186">Wenn Sie diesen Parameter verwenden, gibt dieses Cmdlet ein **ProcessModule** -Objekt **System. Diagnostics. ProcessModule** zurück, kein Prozess Objekt.</span><span class="sxs-lookup"><span data-stu-id="b57d9-186">When you use this parameter, this cmdlet returns a **ProcessModule** object **System.Diagnostics.ProcessModule** , not a process object.</span></span> <span data-ttu-id="b57d9-187">Daher können Sie die Ausgabe des Befehls nicht an ein Cmdlet übergeben, das ein Prozess Objekt erwartet, z `Stop-Process` . b..</span><span class="sxs-lookup"><span data-stu-id="b57d9-187">So, you cannot pipe the output of the command to a cmdlet that expects a process object, such as `Stop-Process`.</span></span>

<span data-ttu-id="b57d9-188">Wenn Sie den *Module* -Parameter und den **FileVersionInfo** -Parameter im gleichen Befehl verwenden, gibt dieses Cmdlet ein **FileVersionInfo** -Objekt mit Informationen zur Dateiversion aller Module zurück.</span><span class="sxs-lookup"><span data-stu-id="b57d9-188">When you use both the *Module* and **FileVersionInfo** parameters in the same command, this cmdlet returns a **FileVersionInfo** object with information about the file version of all modules.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Name, Id, InputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b57d9-189">-Name</span><span class="sxs-lookup"><span data-stu-id="b57d9-189">-Name</span></span>

<span data-ttu-id="b57d9-190">Gibt einen oder mehrere Prozesse mit ihrem Prozessnamen an.</span><span class="sxs-lookup"><span data-stu-id="b57d9-190">Specifies one or more processes by process name.</span></span> <span data-ttu-id="b57d9-191">Sie können mehrere Prozessnamen eingeben (getrennt durch Kommas) und Platzhalterzeichen verwenden.</span><span class="sxs-lookup"><span data-stu-id="b57d9-191">You can type multiple process names (separated by commas) and use wildcard characters.</span></span> <span data-ttu-id="b57d9-192">Der Parametername (Name) ist optional.</span><span class="sxs-lookup"><span data-stu-id="b57d9-192">The parameter name ("Name") is optional.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name, NameWithUserName
Aliases: ProcessName

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="b57d9-193">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b57d9-193">CommonParameters</span></span>

<span data-ttu-id="b57d9-194">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b57d9-194">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b57d9-195">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="b57d9-195">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="b57d9-196">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="b57d9-196">INPUTS</span></span>

### <span data-ttu-id="b57d9-197">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="b57d9-197">System.Diagnostics.Process</span></span>

<span data-ttu-id="b57d9-198">Sie können ein Prozess Objekt über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="b57d9-198">You can pipe a process object to this cmdlet.</span></span>

## <span data-ttu-id="b57d9-199">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="b57d9-199">OUTPUTS</span></span>

### <span data-ttu-id="b57d9-200">System. Diagnostics. Process, System. Diagnostics. FileVersionInfo, System. Diagnostics. ProcessModule</span><span class="sxs-lookup"><span data-stu-id="b57d9-200">System.Diagnostics.Process, System.Diagnostics.FileVersionInfo, System.Diagnostics.ProcessModule</span></span>

<span data-ttu-id="b57d9-201">Standardmäßig gibt dieses Cmdlet ein **System. Diagnostics. Process** -Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="b57d9-201">By default, this cmdlet returns a **System.Diagnostics.Process** object.</span></span> <span data-ttu-id="b57d9-202">Wenn Sie den **FileVersionInfo** -Parameter verwenden, wird ein **System. Diagnostics. FileVersionInfo** -Objekt zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b57d9-202">If you use the **FileVersionInfo** parameter, it returns a **System.Diagnostics.FileVersionInfo** object.</span></span> <span data-ttu-id="b57d9-203">Wenn Sie den **Module** -Parameter ohne den **FileVersionInfo** -Parameter verwenden, wird ein **System. Diagnostics. ProcessModule** -Objekt zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b57d9-203">If you use the **Module** parameter, without the **FileVersionInfo** parameter, it returns a **System.Diagnostics.ProcessModule** object.</span></span>

## <span data-ttu-id="b57d9-204">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="b57d9-204">NOTES</span></span>

- <span data-ttu-id="b57d9-205">Sie können dieses Cmdlet auch über die integrierten Aliase, PS und GPS verweisen.</span><span class="sxs-lookup"><span data-stu-id="b57d9-205">You can also refer to this cmdlet by its built-in aliases, ps and gps.</span></span> <span data-ttu-id="b57d9-206">Weitere Informationen finden Sie unter [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="b57d9-206">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>
- <span data-ttu-id="b57d9-207">Auf Computern, auf denen eine 64-Bit-Version von Windows ausgeführt wird, werden von der 64-Bit-Version von PowerShell nur 64-Bit-Prozessmodule abgerufen, und die 32-Bit-Version von PowerShell erhält nur die 32-Bit-Prozessmodule.</span><span class="sxs-lookup"><span data-stu-id="b57d9-207">On computers that are running a 64-bit version of Windows, the 64-bit version of PowerShell gets only 64-bit process modules and the 32-bit version of PowerShell gets only 32-bit process modules.</span></span>
- <span data-ttu-id="b57d9-208">Sie können die Eigenschaften und Methoden des Windows-Verwaltungsinstrumentation (WMI) Win32_Process-Objekts in PowerShell verwenden.</span><span class="sxs-lookup"><span data-stu-id="b57d9-208">You can use the properties and methods of the Windows Management Instrumentation (WMI) Win32_Process object in PowerShell.</span></span> <span data-ttu-id="b57d9-209">Weitere Informationen finden Sie unter `Get-WmiObject` und im WMI SDK.</span><span class="sxs-lookup"><span data-stu-id="b57d9-209">For information, see `Get-WmiObject` and the WMI SDK.</span></span>
- <span data-ttu-id="b57d9-210">Die Standardanzeige eines Prozesses ist eine Tabelle mit den folgenden Spalten:</span><span class="sxs-lookup"><span data-stu-id="b57d9-210">The default display of a process is a table that includes the following columns.</span></span> <span data-ttu-id="b57d9-211">Eine Beschreibung aller Eigenschaften von Prozess Objekten finden Sie unter [Prozess Eigenschaften](/dotnet/api/system.diagnostics.process).</span><span class="sxs-lookup"><span data-stu-id="b57d9-211">For a description of all of the properties of process objects, see [Process Properties](/dotnet/api/system.diagnostics.process).</span></span>
  - <span data-ttu-id="b57d9-212">Handles: die Anzahl der Handles, die der Prozess geöffnet hat.</span><span class="sxs-lookup"><span data-stu-id="b57d9-212">Handles: The number of handles that the process has opened.</span></span>
  - <span data-ttu-id="b57d9-213">NPM (K): die Menge des vom Prozess verwendeten nicht auslagerbaren Speichers in Kilobyte.</span><span class="sxs-lookup"><span data-stu-id="b57d9-213">NPM(K): The amount of non-paged memory that the process is using, in kilobytes.</span></span>
  - <span data-ttu-id="b57d9-214">PM (K): die Menge des vom Prozess verwendeten Speicher abrechenbaren Speichers in Kilobyte.</span><span class="sxs-lookup"><span data-stu-id="b57d9-214">PM(K): The amount of pageable memory that the process is using, in kilobytes.</span></span>
  - <span data-ttu-id="b57d9-215">WS (K): die Größe des Workingsets des Prozesses in Kilobyte.</span><span class="sxs-lookup"><span data-stu-id="b57d9-215">WS(K): The size of the working set of the process, in kilobytes.</span></span>
    <span data-ttu-id="b57d9-216">Der Arbeitssatz besteht aus Speicherseiten, auf die zuvor vom Prozess verwiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="b57d9-216">The working set consists of the pages of memory that were recently referenced by the process.</span></span>
  - <span data-ttu-id="b57d9-217">VM (M): die Menge des vom Prozess verwendeten virtuellen Speichers in Megabyte.</span><span class="sxs-lookup"><span data-stu-id="b57d9-217">VM(M): The amount of virtual memory that the process is using, in megabytes.</span></span>
    <span data-ttu-id="b57d9-218">Der virtuelle Speicher umfasst den Speicher der Auslagerungsdateien auf dem Datenträger.</span><span class="sxs-lookup"><span data-stu-id="b57d9-218">Virtual memory includes storage in the paging files on disk.</span></span>
  - <span data-ttu-id="b57d9-219">CPU (s): die Prozessorzeit (in Sekunden), die vom Prozess auf allen Prozessoren verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="b57d9-219">CPU(s): The amount of processor time that the process has used on all processors, in seconds.</span></span>
  - <span data-ttu-id="b57d9-220">ID: die Prozess-ID (PID) des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="b57d9-220">ID: The process ID (PID) of the process.</span></span>
  - <span data-ttu-id="b57d9-221">ProcessName: der Name des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="b57d9-221">ProcessName: The name of the process.</span></span> <span data-ttu-id="b57d9-222">Erläuterungen zu den Prozesskonzepten finden Sie im Glossar des Hilfe- und Supportcenters sowie in der Hilfe des Task-Managers.</span><span class="sxs-lookup"><span data-stu-id="b57d9-222">For explanations of the concepts related to processes, see the Glossary in Help and Support Center and the Help for Task Manager.</span></span>
- <span data-ttu-id="b57d9-223">Sie können auch die integrierten alternativen Ansichten der Prozesse verwenden, die in verfügbar sind `Format-Table` , z. b. **StartTime** und **Priority** , und Sie können Ihre eigenen Ansichten entwerfen.</span><span class="sxs-lookup"><span data-stu-id="b57d9-223">You can also use the built-in alternate views of the processes available with `Format-Table`, such as **StartTime** and **Priority** , and you can design your own views.</span></span>

## <span data-ttu-id="b57d9-224">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="b57d9-224">RELATED LINKS</span></span>

[<span data-ttu-id="b57d9-225">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="b57d9-225">Debug-Process</span></span>](Debug-Process.md)

[<span data-ttu-id="b57d9-226">Get-Process</span><span class="sxs-lookup"><span data-stu-id="b57d9-226">Get-Process</span></span>](Get-Process.md)

[<span data-ttu-id="b57d9-227">Start-Process</span><span class="sxs-lookup"><span data-stu-id="b57d9-227">Start-Process</span></span>](Start-Process.md)

[<span data-ttu-id="b57d9-228">Stop-Process</span><span class="sxs-lookup"><span data-stu-id="b57d9-228">Stop-Process</span></span>](Stop-Process.md)

[<span data-ttu-id="b57d9-229">Wait-Process</span><span class="sxs-lookup"><span data-stu-id="b57d9-229">Wait-Process</span></span>](Wait-Process.md)
