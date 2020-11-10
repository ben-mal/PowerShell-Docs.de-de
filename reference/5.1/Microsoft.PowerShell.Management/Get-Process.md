---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-process?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Process
ms.openlocfilehash: d1a576ce9c718561718bac5fee065983a057d458
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388296"
---
# <span data-ttu-id="29397-103">Get-Process</span><span class="sxs-lookup"><span data-stu-id="29397-103">Get-Process</span></span>

## <span data-ttu-id="29397-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="29397-104">SYNOPSIS</span></span>
<span data-ttu-id="29397-105">Ruft die Prozesse ab, die auf dem lokalen Computer oder einem Remotecomputer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="29397-105">Gets the processes that are running on the local computer or a remote computer.</span></span>

## <span data-ttu-id="29397-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="29397-106">SYNTAX</span></span>

### <span data-ttu-id="29397-107">Name (Standard)</span><span class="sxs-lookup"><span data-stu-id="29397-107">Name (Default)</span></span>

```
Get-Process [[-Name] <String[]>] [-ComputerName <String[]>] [-Module] [-FileVersionInfo] [<CommonParameters>]
```

### <span data-ttu-id="29397-108">Namewithusername</span><span class="sxs-lookup"><span data-stu-id="29397-108">NameWithUserName</span></span>

```
Get-Process [[-Name] <String[]>] [-IncludeUserName] [<CommonParameters>]
```

### <span data-ttu-id="29397-109">Idwithusername</span><span class="sxs-lookup"><span data-stu-id="29397-109">IdWithUserName</span></span>

```
Get-Process -Id <Int32[]> [-IncludeUserName] [<CommonParameters>]
```

### <span data-ttu-id="29397-110">Id</span><span class="sxs-lookup"><span data-stu-id="29397-110">Id</span></span>

```
Get-Process -Id <Int32[]> [-ComputerName <String[]>] [-Module] [-FileVersionInfo] [<CommonParameters>]
```

### <span data-ttu-id="29397-111">Inputobjectwithusername</span><span class="sxs-lookup"><span data-stu-id="29397-111">InputObjectWithUserName</span></span>

```
Get-Process -InputObject <Process[]> [-IncludeUserName] [<CommonParameters>]
```

### <span data-ttu-id="29397-112">InputObject</span><span class="sxs-lookup"><span data-stu-id="29397-112">InputObject</span></span>

```
Get-Process -InputObject <Process[]> [-ComputerName <String[]>] [-Module] [-FileVersionInfo]
 [<CommonParameters>]
```

## <span data-ttu-id="29397-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="29397-113">DESCRIPTION</span></span>

<span data-ttu-id="29397-114">Das- `Get-Process` Cmdlet ruft die Prozesse auf einem lokalen Computer oder einem Remote Computer ab.</span><span class="sxs-lookup"><span data-stu-id="29397-114">The `Get-Process` cmdlet gets the processes on a local or remote computer.</span></span>

<span data-ttu-id="29397-115">Ohne Parameter ruft dieses Cmdlet alle Prozesse auf dem lokalen Computer ab.</span><span class="sxs-lookup"><span data-stu-id="29397-115">Without parameters, this cmdlet gets all of the processes on the local computer.</span></span> <span data-ttu-id="29397-116">Sie können auch einen bestimmten Prozess mit dem Prozessnamen oder der Prozess-ID (PID) angeben oder ein Prozess Objekt über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="29397-116">You can also specify a particular process by process name or process ID (PID) or pass a process object through the pipeline to this cmdlet.</span></span>

<span data-ttu-id="29397-117">Standardmäßig gibt dieses Cmdlet ein Prozess Objekt mit detaillierten Informationen über den Prozess zurück und unterstützt Methoden, mit denen Sie den Prozess starten und abbrechen können.</span><span class="sxs-lookup"><span data-stu-id="29397-117">By default, this cmdlet returns a process object that has detailed information about the process and supports methods that let you start and stop the process.</span></span> <span data-ttu-id="29397-118">Sie können auch die Parameter des `Get-Process` Cmdlets verwenden, um Datei Versionsinformationen für das Programm zu erhalten, das im Prozess ausgeführt wird, und um die vom Prozess geladenen Module zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="29397-118">You can also use the parameters of the `Get-Process` cmdlet to get file version information for the program that runs in the process and to get the modules that the process loaded.</span></span>

## <span data-ttu-id="29397-119">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="29397-119">EXAMPLES</span></span>

### <span data-ttu-id="29397-120">Beispiel 1: erhalten einer Liste aller aktiven Prozesse auf dem lokalen Computer</span><span class="sxs-lookup"><span data-stu-id="29397-120">Example 1: Get a list of all active processes on the local computer</span></span>

```powershell
Get-Process
```

<span data-ttu-id="29397-121">Mit diesem Befehl wird eine Liste aller aktiven Prozesse abgerufen, die auf dem lokalen Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="29397-121">This command gets a list of all active processes running on the local computer.</span></span> <span data-ttu-id="29397-122">Eine Definition der einzelnen Spalten finden Sie im Abschnitt " [Hinweise](#notes) ".</span><span class="sxs-lookup"><span data-stu-id="29397-122">For a definition of each column, see the [Notes](#notes) section.</span></span>

### <span data-ttu-id="29397-123">Beispiel 2: alle verfügbaren Daten zu einem oder mehreren Prozessen</span><span class="sxs-lookup"><span data-stu-id="29397-123">Example 2: Get all available data about one or more processes</span></span>

```powershell
Get-Process winword, explorer | Format-List *
```

<span data-ttu-id="29397-124">Mit diesem Befehl werden alle verfügbaren Daten zum Winword- und zum Explorer-Prozess auf dem Computer abgerufen.</span><span class="sxs-lookup"><span data-stu-id="29397-124">This command gets all available data about the Winword and Explorer processes on the computer.</span></span> <span data-ttu-id="29397-125">Er verwendet den **Name** -Parameter, um die Prozesse anzugeben, der optionale Parameter Name wird jedoch ausgelassen.</span><span class="sxs-lookup"><span data-stu-id="29397-125">It uses the **Name** parameter to specify the processes, but it omits the optional parameter name.</span></span> <span data-ttu-id="29397-126">Der Pipeline Operator `|` übergibt die Daten an das `Format-List` Cmdlet, das alle verfügbaren Eigenschaften `*` der Winword-und Explorer-Prozess Objekte anzeigt.</span><span class="sxs-lookup"><span data-stu-id="29397-126">The pipeline operator `|` passes the data to the `Format-List` cmdlet, which displays all available properties `*` of the Winword and Explorer process objects.</span></span>

<span data-ttu-id="29397-127">Sie können die Prozesse auch anhand ihrer Prozess-IDs angeben.</span><span class="sxs-lookup"><span data-stu-id="29397-127">You can also identify the processes by their process IDs.</span></span> <span data-ttu-id="29397-128">Beispielsweise `Get-Process -Id 664, 2060`.</span><span class="sxs-lookup"><span data-stu-id="29397-128">For instance, `Get-Process -Id 664, 2060`.</span></span>

### <span data-ttu-id="29397-129">Beispiel 3: alle Prozesse mit einem Workingset, das größer ist als die angegebene Größe</span><span class="sxs-lookup"><span data-stu-id="29397-129">Example 3: Get all processes with a working set greater than a specified size</span></span>

```powershell
Get-Process | Where-Object {$_.WorkingSet -gt 20000000}
```

<span data-ttu-id="29397-130">Mit diesem Befehl werden alle Prozesse mit einem Arbeitssatz abgerufen, dessen Größe 20 MB übersteigt.</span><span class="sxs-lookup"><span data-stu-id="29397-130">This command gets all processes that have a working set greater than 20 MB.</span></span> <span data-ttu-id="29397-131">Er verwendet das `Get-Process` Cmdlet, um alle laufenden Prozesse zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="29397-131">It uses the `Get-Process` cmdlet to get all running processes.</span></span> <span data-ttu-id="29397-132">Der Pipeline Operator `|` übergibt die Prozess Objekte an das `Where-Object` Cmdlet, das nur das Objekt auswählt, dessen Wert größer als 20 Millionen Byte für die **Workingset** -Eigenschaft ist.</span><span class="sxs-lookup"><span data-stu-id="29397-132">The pipeline operator `|` passes the process objects to the `Where-Object` cmdlet, which selects only the object with a value greater than 20,000,000 bytes for the **WorkingSet** property.</span></span>

<span data-ttu-id="29397-133">**Workingset** ist eine von vielen Eigenschaften von Prozess Objekten.</span><span class="sxs-lookup"><span data-stu-id="29397-133">**WorkingSet** is one of many properties of process objects.</span></span> <span data-ttu-id="29397-134">Um alle Eigenschaften anzuzeigen, geben Sie ein `Get-Process | Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="29397-134">To see all of the properties, type `Get-Process | Get-Member`.</span></span> <span data-ttu-id="29397-135">Standardmäßig werden die Werte aller Mengeneigenschaften in Bytes angegeben, auch wenn sie in der Standardanzeige in Kilobytes und Megabytes aufgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="29397-135">By default, the values of all amount properties are in bytes, even though the default display lists them in kilobytes and megabytes.</span></span>

### <span data-ttu-id="29397-136">Beispiel 4: Auflisten von Prozessen auf dem Computer in Gruppen basierend auf der Priorität</span><span class="sxs-lookup"><span data-stu-id="29397-136">Example 4: List processes on the computer in groups based on priority</span></span>

```powershell
$A = Get-Process
$A | Get-Process | Format-Table -View priority
```

<span data-ttu-id="29397-137">Diese Befehle Listen die Prozesse auf dem Computer in Gruppen auf Grundlage ihrer Prioritäts Klasse auf.</span><span class="sxs-lookup"><span data-stu-id="29397-137">These commands list the processes on the computer in groups based on their priority class.</span></span> <span data-ttu-id="29397-138">Der erste Befehl ruft alle Prozesse auf dem Computer ab und speichert Sie dann in der `$A` Variablen.</span><span class="sxs-lookup"><span data-stu-id="29397-138">The first command gets all the processes on the computer and then stores them in the `$A` variable.</span></span>

<span data-ttu-id="29397-139">Mit dem zweiten Befehl wird das in der Variablen gespeicherte **Prozess** Objekt `$A` an das `Get-Process` Cmdlet weitergeleitet, dann an das `Format-Table` Cmdlet, das die Prozesse mithilfe der **Prioritäts** Ansicht formatiert.</span><span class="sxs-lookup"><span data-stu-id="29397-139">The second command pipes the **Process** object stored in the `$A` variable to the `Get-Process` cmdlet, then to the `Format-Table` cmdlet, which formats the processes by using the **Priority** view.</span></span>

<span data-ttu-id="29397-140">Die **Prioritäts** Ansicht und andere Ansichten werden in den PS1XML-Format Dateien im PowerShell-Basisverzeichnis ( `$pshome` ) definiert.</span><span class="sxs-lookup"><span data-stu-id="29397-140">The **Priority** view, and other views, are defined in the PS1XML format files in the PowerShell home directory (`$pshome`).</span></span>

### <span data-ttu-id="29397-141">Beispiel 5: Hinzufügen einer Eigenschaft zur Standard Get-Process Ausgabe Anzeige</span><span class="sxs-lookup"><span data-stu-id="29397-141">Example 5: Add a property to the standard Get-Process output display</span></span>

```powershell
Get-Process powershell -ComputerName S1, localhost | Format-Table `
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
     6 23500 31340   142 1.70   1980 S1          powershell
     6 23500 31348   142 2.75   4016 S1          powershell
    27 54572 54520   576 5.52   4428 localhost   powershell
```

<span data-ttu-id="29397-142">In diesem Beispiel werden Prozesse vom lokalen Computer und einem Remote Computer (S1) abgerufen.</span><span class="sxs-lookup"><span data-stu-id="29397-142">This example retrieves processes from the local computer and a remote computer (S1).</span></span> <span data-ttu-id="29397-143">Die abgerufenen Prozesse werden an den Befehl weitergeleitet `Format-Table` , der die **MachineName** -Eigenschaft der Standard `Get-Process` Ausgabe Anzeige hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="29397-143">The retrieved processes are piped to the `Format-Table` command that adds the **MachineName** property to the standard `Get-Process` output display.</span></span>

### <span data-ttu-id="29397-144">Beispiel 6: erhalten von Versionsinformationen für einen Prozess</span><span class="sxs-lookup"><span data-stu-id="29397-144">Example 6: Get version information for a process</span></span>

```powershell
Get-Process powershell -FileVersionInfo
```

```Output
ProductVersion   FileVersion      FileName
--------------   -----------      --------
6.1.6713.1       6.1.6713.1 (f... C:\WINDOWS\system32\WindowsPowerShell\v1.0\powershell.exe
```

<span data-ttu-id="29397-145">Dieser Befehl verwendet den **FileVersionInfo** -Parameter, um die Versionsinformationen für die powershell.exe-Datei zu erhalten, die das Hauptmodul für den PowerShell-Prozess ist.</span><span class="sxs-lookup"><span data-stu-id="29397-145">This command uses the **FileVersionInfo** parameter to get the version information for the powershell.exe file that is the main module for the PowerShell process.</span></span>

<span data-ttu-id="29397-146">Wenn Sie diesen Befehl mit Prozessen ausführen möchten, die Sie nicht unter Windows Vista und höheren Versionen von Windows besitzen, müssen Sie PowerShell mit der Option als Administrator ausführen öffnen.</span><span class="sxs-lookup"><span data-stu-id="29397-146">To run this command with processes that you do not own on Windows Vista and later versions of Windows, you must open PowerShell with the Run as administrator option.</span></span>

### <span data-ttu-id="29397-147">Beispiel 7: Get-Module, die mit dem angegebenen Prozess geladen wurden</span><span class="sxs-lookup"><span data-stu-id="29397-147">Example 7: Get modules loaded with the specified process</span></span>

```powershell
Get-Process SQL* -Module
```

<span data-ttu-id="29397-148">Dieser Befehl verwendet den **Module-Parameter,** um die Module, die vom Prozess geladen wurden, zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="29397-148">This command uses the **Module** parameter to get the modules that have been loaded by the process.</span></span>
<span data-ttu-id="29397-149">Dieser Befehl ruft die Module für die Prozesse ab, deren Namen mit SQL beginnen.</span><span class="sxs-lookup"><span data-stu-id="29397-149">This command gets the modules for the processes that have names that begin with SQL.</span></span>

<span data-ttu-id="29397-150">Wenn Sie diesen Befehl unter Windows Vista und höheren Versionen von Windows mit Prozessen ausführen möchten, die Sie nicht besitzen, müssen Sie PowerShell mit der Option als Administrator ausführen starten.</span><span class="sxs-lookup"><span data-stu-id="29397-150">To run this command on Windows Vista and later versions of Windows with processes that you do not own, you must start PowerShell with the Run as administrator option.</span></span>

### <span data-ttu-id="29397-151">Beispiel 8: Ermitteln des Besitzers eines Prozesses</span><span class="sxs-lookup"><span data-stu-id="29397-151">Example 8: Find the owner of a process</span></span>

```powershell
Get-Process pwsh -IncludeUserName
```

```Output
Handles      WS(K)   CPU(s)     Id UserName            ProcessName
-------      -----   ------     -- --------            -----------
    782     132080     2.08   2188 DOMAIN01\user01     powershell
```

```powershell
$p = Get-WmiObject Win32_Process -Filter "name='powershell.exe'"
$p.GetOwner()
```

```Output
__GENUS          : 2
__CLASS          : __PARAMETERS
__SUPERCLASS     :
__DYNASTY        : __PARAMETERS
__RELPATH        :
__PROPERTY_COUNT : 3
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
Domain           : DOMAIN01
ReturnValue      : 0
User             : user01
```

<span data-ttu-id="29397-152">Der erste Befehl zeigt, wie der Besitzer eines Prozesses ermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="29397-152">The first command shows how to find the owner of a process.</span></span> <span data-ttu-id="29397-153">Der **includeusername** -Parameter erfordert erhöhte Benutzerrechte (als Administrator ausführen).</span><span class="sxs-lookup"><span data-stu-id="29397-153">The **IncludeUserName** parameter requires elevated user rights (Run as Administrator).</span></span> <span data-ttu-id="29397-154">Die Ausgabe zeigt, dass der Besitzer Domain01\user01. ist.</span><span class="sxs-lookup"><span data-stu-id="29397-154">The output reveals that the owner is Domain01\user01.</span></span>

<span data-ttu-id="29397-155">Mit dem zweiten und dritten Befehl können Sie den Besitzer eines Prozesses ermitteln.</span><span class="sxs-lookup"><span data-stu-id="29397-155">The second and third command are another way to find the owner of a process.</span></span>

<span data-ttu-id="29397-156">Der zweite Befehl verwendet `Get-WmiObject` , um den PowerShell-Prozess zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="29397-156">The second command uses `Get-WmiObject` to get the PowerShell process.</span></span>
<span data-ttu-id="29397-157">Sie speichert Sie in der `$p` Variablen.</span><span class="sxs-lookup"><span data-stu-id="29397-157">It saves it in the `$p` variable.</span></span>

<span data-ttu-id="29397-158">Der dritte Befehl verwendet die GetOwner-Methode, um den Besitzer des Prozesses in zu erhalten `$p` .</span><span class="sxs-lookup"><span data-stu-id="29397-158">The third command uses the GetOwner method to get the owner of the process in `$p`.</span></span> <span data-ttu-id="29397-159">Die Ausgabe zeigt, dass der Besitzer Domain01\user01. ist.</span><span class="sxs-lookup"><span data-stu-id="29397-159">The output reveals that the owner is Domain01\user01.</span></span>

### <span data-ttu-id="29397-160">Beispiel 9: Verwenden einer automatischen Variablen zum Identifizieren des Prozesses, der die aktuelle Sitzung gehostet</span><span class="sxs-lookup"><span data-stu-id="29397-160">Example 9: Use an automatic variable to identify the process hosting the current session</span></span>

```powershell
Get-Process powershell
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
308      26        52308      61780   567     3.18   5632 powershell
377      26        62676      63384   575     3.88   5888 powershell
```

```powershell
Get-Process -Id $PID
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
396      26        56488      57236   575     3.90   5888 powershell
```

<span data-ttu-id="29397-161">Diese Befehle zeigen, wie Sie die `$PID` Automatische Variable verwenden, um den Prozess zu identifizieren, der die aktuelle PowerShell-Sitzung gehostet.</span><span class="sxs-lookup"><span data-stu-id="29397-161">These commands show how to use the `$PID` automatic variable to identify the process that is hosting the current PowerShell session.</span></span> <span data-ttu-id="29397-162">Sie können den Hostprozess mithilfe dieser Methode von anderen PowerShell-Prozessen unterscheiden, die Sie beenden oder schließen möchten.</span><span class="sxs-lookup"><span data-stu-id="29397-162">You can use this method to distinguish the host process from other PowerShell processes that you might want to stop or close.</span></span>

<span data-ttu-id="29397-163">Der erste Befehl ruft alle PowerShell-Prozesse in der aktuellen Sitzung ab.</span><span class="sxs-lookup"><span data-stu-id="29397-163">The first command gets all of the PowerShell processes in the current session.</span></span>

<span data-ttu-id="29397-164">Der zweite Befehl ruft den PowerShell-Prozess ab, der die aktuelle Sitzung gehostet.</span><span class="sxs-lookup"><span data-stu-id="29397-164">The second command gets the PowerShell process that is hosting the current session.</span></span>

### <span data-ttu-id="29397-165">Beispiel 10: Hiermit werden alle Prozesse mit einem Hauptfenster Titel und in einer Tabelle angezeigt.</span><span class="sxs-lookup"><span data-stu-id="29397-165">Example 10: Get all processes that have a main window title and display them in a table</span></span>

```powershell
Get-Process | Where-Object {$_.mainWindowTitle} | Format-Table Id, Name, mainWindowtitle -AutoSize
```

<span data-ttu-id="29397-166">Mit diesem Befehl werden alle Prozesse mit einem Hauptfenstertitel abgerufen und in einer Tabelle mit der Prozess-ID und dem Prozessnamen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="29397-166">This command gets all the processes that have a main window title, and it displays them in a table with the process ID and the process name.</span></span>

<span data-ttu-id="29397-167">Die **MainWindowTitle** -Eigenschaft ist nur eine von vielen nützlichen Eigenschaften des **Prozess** Objekts, das `Get-Process` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="29397-167">The **mainWindowTitle** property is just one of many useful properties of the **Process** object that `Get-Process` returns.</span></span> <span data-ttu-id="29397-168">Um alle Eigenschaften anzuzeigen, reichen Sie die Ergebnisse eines Befehls über `Get-Process` die Pipeline an das `Get-Member` Cmdlet weiter `Get-Process | Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="29397-168">To view all of the properties, pipe the results of a `Get-Process` command to the `Get-Member` cmdlet `Get-Process | Get-Member`.</span></span>

## <span data-ttu-id="29397-169">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="29397-169">PARAMETERS</span></span>

### <span data-ttu-id="29397-170">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="29397-170">-ComputerName</span></span>

<span data-ttu-id="29397-171">Gibt die Computer an, für die dieses Cmdlet aktive Prozesse abruft.</span><span class="sxs-lookup"><span data-stu-id="29397-171">Specifies the computers for which this cmdlet gets active processes.</span></span> <span data-ttu-id="29397-172">Die Standardeinstellung ist der lokale Computer.</span><span class="sxs-lookup"><span data-stu-id="29397-172">The default is the local computer.</span></span>

<span data-ttu-id="29397-173">Geben Sie den NetBIOS-Namen, eine IP-Adresse oder einen voll qualifizierten Domänen Namen (Fully Qualified Domain Name, FQDN) eines oder mehrerer Computer ein.</span><span class="sxs-lookup"><span data-stu-id="29397-173">Type the NetBIOS name, an IP address, or a fully qualified domain name (FQDN) of one or more computers.</span></span> <span data-ttu-id="29397-174">Geben Sie den Computernamen, einen Punkt (.) oder einen localhost ein, um den lokalen Computer anzugeben.</span><span class="sxs-lookup"><span data-stu-id="29397-174">To specify the local computer, type the computer name, a dot (.), or localhost.</span></span>

<span data-ttu-id="29397-175">Dieser Parameter beruht nicht auf Windows PowerShell-Remoting.</span><span class="sxs-lookup"><span data-stu-id="29397-175">This parameter does not rely on Windows PowerShell remoting.</span></span> <span data-ttu-id="29397-176">Sie können den Computer **Name** -Parameter dieses Cmdlets auch dann verwenden, wenn der Computer nicht für das Ausführen von Remote Befehlen konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="29397-176">You can use the **ComputerName** parameter of this cmdlet even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name, Id, InputObject
Aliases: Cn

Required: False
Position: Named
Default value: Local computer
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="29397-177">-FileVersionInfo</span><span class="sxs-lookup"><span data-stu-id="29397-177">-FileVersionInfo</span></span>

<span data-ttu-id="29397-178">Gibt an, dass dieses Cmdlet die Datei Versionsinformationen für das Programm abruft, das im Prozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="29397-178">Indicates that this cmdlet gets the file version information for the program that runs in the process.</span></span>

<span data-ttu-id="29397-179">Unter Windows Vista und höheren Versionen von Windows müssen Sie PowerShell mit der Option "als Administrator ausführen" öffnen, um diesen Parameter für Prozesse zu verwenden, deren Besitzer Sie sind.</span><span class="sxs-lookup"><span data-stu-id="29397-179">On Windows Vista and later versions of Windows, you must open PowerShell with the Run as administrator option to use this parameter on processes that you do not own.</span></span>

<span data-ttu-id="29397-180">Der **FileVersionInfo** -Parameter und der **Computername** -Parameter des `Get-Process` Cmdlets können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="29397-180">You cannot use the **FileVersionInfo** and **ComputerName** parameters of the `Get-Process` cmdlet in the same command.</span></span>

<span data-ttu-id="29397-181">Verwenden Sie das-Cmdlet, um die Datei Versionsinformationen für einen Prozess auf einem Remote Computer zu erhalten `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="29397-181">To get file version information for a process on a remote computer, use the `Invoke-Command` cmdlet.</span></span>

<span data-ttu-id="29397-182">Die Verwendung dieses Parameters entspricht dem erhalten der **MainModule. FileVersionInfo** -Eigenschaft für jedes Prozess Objekt.</span><span class="sxs-lookup"><span data-stu-id="29397-182">Using this parameter is equivalent to getting the **MainModule.FileVersionInfo** property of each process object.</span></span> <span data-ttu-id="29397-183">Wenn Sie diesen Parameter verwenden, `Get-Process` gibt ein **FileVersionInfo** -Objekt **System. Diagnostics. FileVersionInfo** zurück, kein Prozess Objekt.</span><span class="sxs-lookup"><span data-stu-id="29397-183">When you use this parameter, `Get-Process` returns a **FileVersionInfo** object **System.Diagnostics.FileVersionInfo** , not a process object.</span></span> <span data-ttu-id="29397-184">Daher können Sie die Ausgabe des Befehls nicht an ein Cmdlet übergeben, das ein Prozess Objekt erwartet, z `Stop-Process` . b..</span><span class="sxs-lookup"><span data-stu-id="29397-184">So, you cannot pipe the output of the command to a cmdlet that expects a process object, such as `Stop-Process`.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Name, Id, InputObject
Aliases: FV, FVI

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="29397-185">-Id</span><span class="sxs-lookup"><span data-stu-id="29397-185">-Id</span></span>

<span data-ttu-id="29397-186">Gibt einen oder mehrere Prozesse anhand der Prozess-ID (PID) an.</span><span class="sxs-lookup"><span data-stu-id="29397-186">Specifies one or more processes by process ID (PID).</span></span> <span data-ttu-id="29397-187">Wenn Sie mehrere IDs angeben, trennen Sie diese durch Kommas.</span><span class="sxs-lookup"><span data-stu-id="29397-187">To specify multiple IDs, use commas to separate the IDs.</span></span> <span data-ttu-id="29397-188">Um die PID eines Prozesses zu ermitteln, geben Sie ein `Get-Process` .</span><span class="sxs-lookup"><span data-stu-id="29397-188">To find the PID of a process, type `Get-Process`.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: IdWithUserName, Id
Aliases: PID

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="29397-189">-Includeusername</span><span class="sxs-lookup"><span data-stu-id="29397-189">-IncludeUserName</span></span>

<span data-ttu-id="29397-190">Gibt an, dass der UserName-Wert des **Prozess** Objekts mit den Ergebnissen des Befehls zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="29397-190">Indicates that the UserName value of the **Process** object is returned with results of the command.</span></span>

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

### <span data-ttu-id="29397-191">-InputObject</span><span class="sxs-lookup"><span data-stu-id="29397-191">-InputObject</span></span>

<span data-ttu-id="29397-192">Gibt Prozessobjekte an.</span><span class="sxs-lookup"><span data-stu-id="29397-192">Specifies one or more process objects.</span></span> <span data-ttu-id="29397-193">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="29397-193">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

```yaml
Type: System.Diagnostics.Process[]
Parameter Sets: InputObjectWithUserName, InputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="29397-194">-Modul</span><span class="sxs-lookup"><span data-stu-id="29397-194">-Module</span></span>

<span data-ttu-id="29397-195">Gibt an, dass dieses Cmdlet die Module abruft, die von den Prozessen geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="29397-195">Indicates that this cmdlet gets the modules that have been loaded by the processes.</span></span>

<span data-ttu-id="29397-196">Unter Windows Vista und höheren Versionen von Windows müssen Sie PowerShell mit der Option " **als Administrator ausführen** " öffnen, um diesen Parameter für Prozesse zu verwenden, deren Besitzer Sie sind.</span><span class="sxs-lookup"><span data-stu-id="29397-196">On Windows Vista and later versions of Windows, you must open PowerShell with the **Run as administrator** option to use this parameter on processes that you do not own.</span></span>

<span data-ttu-id="29397-197">Verwenden Sie das Cmdlet, um die Module, die von einem Prozess auf einem Remote Computer geladen wurden, zu erhalten `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="29397-197">To get the modules that have been loaded by a process on a remote computer, use the `Invoke-Command` cmdlet.</span></span>

<span data-ttu-id="29397-198">Dieser Parameter entspricht dem erhalten der **modules** -Eigenschaft jedes Prozess Objekts.</span><span class="sxs-lookup"><span data-stu-id="29397-198">This parameter is equivalent to getting the **Modules** property of each process object.</span></span> <span data-ttu-id="29397-199">Wenn Sie diesen Parameter verwenden, gibt dieses Cmdlet ein **ProcessModule** -Objekt **System. Diagnostics. ProcessModule** zurück, kein Prozess Objekt.</span><span class="sxs-lookup"><span data-stu-id="29397-199">When you use this parameter, this cmdlet returns a **ProcessModule** object **System.Diagnostics.ProcessModule** , not a process object.</span></span> <span data-ttu-id="29397-200">Daher können Sie die Ausgabe des Befehls nicht an ein Cmdlet übergeben, das ein Prozess Objekt erwartet, z `Stop-Process` . b..</span><span class="sxs-lookup"><span data-stu-id="29397-200">So, you cannot pipe the output of the command to a cmdlet that expects a process object, such as `Stop-Process`.</span></span>

<span data-ttu-id="29397-201">Wenn Sie den *Module* -Parameter und den **FileVersionInfo** -Parameter im gleichen Befehl verwenden, gibt dieses Cmdlet ein **FileVersionInfo** -Objekt mit Informationen zur Dateiversion aller Module zurück.</span><span class="sxs-lookup"><span data-stu-id="29397-201">When you use both the *Module* and **FileVersionInfo** parameters in the same command, this cmdlet returns a **FileVersionInfo** object with information about the file version of all modules.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Name, Id, InputObject
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="29397-202">-Name</span><span class="sxs-lookup"><span data-stu-id="29397-202">-Name</span></span>

<span data-ttu-id="29397-203">Gibt einen oder mehrere Prozesse mit ihrem Prozessnamen an.</span><span class="sxs-lookup"><span data-stu-id="29397-203">Specifies one or more processes by process name.</span></span> <span data-ttu-id="29397-204">Sie können mehrere Prozessnamen eingeben (getrennt durch Kommas) und Platzhalterzeichen verwenden.</span><span class="sxs-lookup"><span data-stu-id="29397-204">You can type multiple process names (separated by commas) and use wildcard characters.</span></span> <span data-ttu-id="29397-205">Der Parametername (Name) ist optional.</span><span class="sxs-lookup"><span data-stu-id="29397-205">The parameter name ("Name") is optional.</span></span>

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

### <span data-ttu-id="29397-206">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="29397-206">CommonParameters</span></span>

<span data-ttu-id="29397-207">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="29397-207">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="29397-208">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="29397-208">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="29397-209">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="29397-209">INPUTS</span></span>

### <span data-ttu-id="29397-210">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="29397-210">System.Diagnostics.Process</span></span>

<span data-ttu-id="29397-211">Sie können ein Prozess Objekt über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="29397-211">You can pipe a process object to this cmdlet.</span></span>

## <span data-ttu-id="29397-212">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="29397-212">OUTPUTS</span></span>

### <span data-ttu-id="29397-213">System. Diagnostics. Process, System. Diagnostics. FileVersionInfo, System. Diagnostics. ProcessModule</span><span class="sxs-lookup"><span data-stu-id="29397-213">System.Diagnostics.Process, System.Diagnostics.FileVersionInfo, System.Diagnostics.ProcessModule</span></span>

<span data-ttu-id="29397-214">Standardmäßig gibt dieses Cmdlet ein **System. Diagnostics. Process** -Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="29397-214">By default, this cmdlet returns a **System.Diagnostics.Process** object.</span></span> <span data-ttu-id="29397-215">Wenn Sie den **FileVersionInfo** -Parameter verwenden, wird ein **System. Diagnostics. FileVersionInfo** -Objekt zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="29397-215">If you use the **FileVersionInfo** parameter, it returns a **System.Diagnostics.FileVersionInfo** object.</span></span> <span data-ttu-id="29397-216">Wenn Sie den **Module** -Parameter ohne den **FileVersionInfo** -Parameter verwenden, wird ein **System. Diagnostics. ProcessModule** -Objekt zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="29397-216">If you use the **Module** parameter, without the **FileVersionInfo** parameter, it returns a **System.Diagnostics.ProcessModule** object.</span></span>

## <span data-ttu-id="29397-217">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="29397-217">NOTES</span></span>

- <span data-ttu-id="29397-218">Sie können dieses Cmdlet auch über die integrierten Aliase, PS und GPS verweisen.</span><span class="sxs-lookup"><span data-stu-id="29397-218">You can also refer to this cmdlet by its built-in aliases, ps and gps.</span></span> <span data-ttu-id="29397-219">Weitere Informationen finden Sie unter [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="29397-219">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>
- <span data-ttu-id="29397-220">Auf Computern, auf denen eine 64-Bit-Version von Windows ausgeführt wird, werden von der 64-Bit-Version von PowerShell nur 64-Bit-Prozessmodule abgerufen, und die 32-Bit-Version von PowerShell erhält nur die 32-Bit-Prozessmodule.</span><span class="sxs-lookup"><span data-stu-id="29397-220">On computers that are running a 64-bit version of Windows, the 64-bit version of PowerShell gets only 64-bit process modules and the 32-bit version of PowerShell gets only 32-bit process modules.</span></span>
- <span data-ttu-id="29397-221">Sie können die Eigenschaften und Methoden des Windows-Verwaltungsinstrumentation (WMI) Win32_Process-Objekts in PowerShell verwenden.</span><span class="sxs-lookup"><span data-stu-id="29397-221">You can use the properties and methods of the Windows Management Instrumentation (WMI) Win32_Process object in PowerShell.</span></span> <span data-ttu-id="29397-222">Weitere Informationen finden Sie unter `Get-WmiObject` und im WMI SDK.</span><span class="sxs-lookup"><span data-stu-id="29397-222">For information, see `Get-WmiObject` and the WMI SDK.</span></span>
- <span data-ttu-id="29397-223">Die Standardanzeige eines Prozesses ist eine Tabelle mit den folgenden Spalten:</span><span class="sxs-lookup"><span data-stu-id="29397-223">The default display of a process is a table that includes the following columns.</span></span> <span data-ttu-id="29397-224">Eine Beschreibung aller Eigenschaften von Prozess Objekten finden Sie unter [Prozess Eigenschaften](/dotnet/api/system.diagnostics.process).</span><span class="sxs-lookup"><span data-stu-id="29397-224">For a description of all of the properties of process objects, see [Process Properties](/dotnet/api/system.diagnostics.process).</span></span>
  - <span data-ttu-id="29397-225">Handles: die Anzahl der Handles, die der Prozess geöffnet hat.</span><span class="sxs-lookup"><span data-stu-id="29397-225">Handles: The number of handles that the process has opened.</span></span>
  - <span data-ttu-id="29397-226">NPM (K): die Menge des vom Prozess verwendeten nicht auslagerbaren Speichers in Kilobyte.</span><span class="sxs-lookup"><span data-stu-id="29397-226">NPM(K): The amount of non-paged memory that the process is using, in kilobytes.</span></span>
  - <span data-ttu-id="29397-227">PM (K): die Menge des vom Prozess verwendeten Speicher abrechenbaren Speichers in Kilobyte.</span><span class="sxs-lookup"><span data-stu-id="29397-227">PM(K): The amount of pageable memory that the process is using, in kilobytes.</span></span>
  - <span data-ttu-id="29397-228">WS (K): die Größe des Workingsets des Prozesses in Kilobyte.</span><span class="sxs-lookup"><span data-stu-id="29397-228">WS(K): The size of the working set of the process, in kilobytes.</span></span>
    <span data-ttu-id="29397-229">Der Arbeitssatz besteht aus Speicherseiten, auf die zuvor vom Prozess verwiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="29397-229">The working set consists of the pages of memory that were recently referenced by the process.</span></span>
  - <span data-ttu-id="29397-230">VM (M): die Menge des vom Prozess verwendeten virtuellen Speichers in Megabyte.</span><span class="sxs-lookup"><span data-stu-id="29397-230">VM(M): The amount of virtual memory that the process is using, in megabytes.</span></span>
    <span data-ttu-id="29397-231">Der virtuelle Speicher umfasst den Speicher der Auslagerungsdateien auf dem Datenträger.</span><span class="sxs-lookup"><span data-stu-id="29397-231">Virtual memory includes storage in the paging files on disk.</span></span>
  - <span data-ttu-id="29397-232">CPU (s): die Prozessorzeit (in Sekunden), die vom Prozess auf allen Prozessoren verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="29397-232">CPU(s): The amount of processor time that the process has used on all processors, in seconds.</span></span>
  - <span data-ttu-id="29397-233">ID: die Prozess-ID (PID) des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="29397-233">ID: The process ID (PID) of the process.</span></span>
  - <span data-ttu-id="29397-234">ProcessName: der Name des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="29397-234">ProcessName: The name of the process.</span></span> <span data-ttu-id="29397-235">Erläuterungen zu den Prozesskonzepten finden Sie im Glossar des Hilfe- und Supportcenters sowie in der Hilfe des Task-Managers.</span><span class="sxs-lookup"><span data-stu-id="29397-235">For explanations of the concepts related to processes, see the Glossary in Help and Support Center and the Help for Task Manager.</span></span>
- <span data-ttu-id="29397-236">Sie können auch die integrierten alternativen Ansichten der Prozesse verwenden, die in verfügbar sind `Format-Table` , z. b. **StartTime** und **Priority** , und Sie können Ihre eigenen Ansichten entwerfen.</span><span class="sxs-lookup"><span data-stu-id="29397-236">You can also use the built-in alternate views of the processes available with `Format-Table`, such as **StartTime** and **Priority** , and you can design your own views.</span></span>

## <span data-ttu-id="29397-237">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="29397-237">RELATED LINKS</span></span>

[<span data-ttu-id="29397-238">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="29397-238">Debug-Process</span></span>](Debug-Process.md)

[<span data-ttu-id="29397-239">Get-Process</span><span class="sxs-lookup"><span data-stu-id="29397-239">Get-Process</span></span>](Get-Process.md)

[<span data-ttu-id="29397-240">Start-Process</span><span class="sxs-lookup"><span data-stu-id="29397-240">Start-Process</span></span>](Start-Process.md)

[<span data-ttu-id="29397-241">Stop-Process</span><span class="sxs-lookup"><span data-stu-id="29397-241">Stop-Process</span></span>](Stop-Process.md)

[<span data-ttu-id="29397-242">Wait-Process</span><span class="sxs-lookup"><span data-stu-id="29397-242">Wait-Process</span></span>](Wait-Process.md)
