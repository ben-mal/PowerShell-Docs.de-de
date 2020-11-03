---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/wait-process?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Wait-Process
ms.openlocfilehash: 38e225a1973022f82a40694cfad89b94d050509e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214327"
---
# <span data-ttu-id="16a73-103">Wait-Process</span><span class="sxs-lookup"><span data-stu-id="16a73-103">Wait-Process</span></span>

## <span data-ttu-id="16a73-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="16a73-104">SYNOPSIS</span></span>
<span data-ttu-id="16a73-105">Wartet, bis die Prozesse beendet wurden, bevor weitere Eingaben angenommen werden.</span><span class="sxs-lookup"><span data-stu-id="16a73-105">Waits for the processes to be stopped before accepting more input.</span></span>

## <span data-ttu-id="16a73-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="16a73-106">SYNTAX</span></span>

### <span data-ttu-id="16a73-107">Name (Standard)</span><span class="sxs-lookup"><span data-stu-id="16a73-107">Name (Default)</span></span>

```
Wait-Process [-Name] <String[]> [[-Timeout] <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="16a73-108">Id</span><span class="sxs-lookup"><span data-stu-id="16a73-108">Id</span></span>

```
Wait-Process [-Id] <Int32[]> [[-Timeout] <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="16a73-109">InputObject</span><span class="sxs-lookup"><span data-stu-id="16a73-109">InputObject</span></span>

```
Wait-Process [[-Timeout] <Int32>] -InputObject <Process[]> [<CommonParameters>]
```

## <span data-ttu-id="16a73-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="16a73-110">DESCRIPTION</span></span>
<span data-ttu-id="16a73-111">Das **Wait-Process-** Cmdlet wartet darauf, dass ein oder mehrere laufende Prozesse beendet werden, bevor Eingaben akzeptiert werden.</span><span class="sxs-lookup"><span data-stu-id="16a73-111">The **Wait-Process** cmdlet waits for one or more running processes to be stopped before accepting input.</span></span>
<span data-ttu-id="16a73-112">In der Windows PowerShell-Konsole unterdrückt dieses Cmdlet die Eingabeaufforderung, bis die Prozesse beendet wurden.</span><span class="sxs-lookup"><span data-stu-id="16a73-112">In the Windows PowerShell console, this cmdlet suppresses the command prompt until the processes are stopped.</span></span>
<span data-ttu-id="16a73-113">Sie können einen Prozess anhand des Prozess namens oder der Prozess-ID (PID) angeben oder ein Prozess Objekt an **Wait-Process** übergeben.</span><span class="sxs-lookup"><span data-stu-id="16a73-113">You can specify a process by process name or process ID (PID), or pipe a process object to **Wait-Process** .</span></span>

<span data-ttu-id="16a73-114">**Wait-Process** funktioniert nur bei Prozessen, die auf dem lokalen Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="16a73-114">**Wait-Process** works only on processes running on the local computer.</span></span>

## <span data-ttu-id="16a73-115">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="16a73-115">EXAMPLES</span></span>

### <span data-ttu-id="16a73-116">Beispiel 1: Abbrechen eines Prozesses und warten</span><span class="sxs-lookup"><span data-stu-id="16a73-116">Example 1: Stop a process and wait</span></span>

```
PS C:\> $nid = (Get-Process notepad).id
PS C:\> Stop-Process -Id $nid
PS C:\> Wait-Process -Id $nid
```

<span data-ttu-id="16a73-117">Dieses Beispiel hält den Notepad-Prozess an und wartet dann, bis der Prozess beendet wird, bevor er mit dem nächsten Befehl fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="16a73-117">This example stops the Notepad process and then waits for the process to be stopped before it continues with the next command.</span></span>

<span data-ttu-id="16a73-118">Der erste Befehl verwendet das **Get-Process-** Cmdlet, um die ID des Notepad-Prozesses zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="16a73-118">The first command uses the **Get-Process** cmdlet to get the ID of the Notepad process.</span></span>
<span data-ttu-id="16a73-119">Die ID wird in der $NID Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="16a73-119">It stores the ID in the $nid variable.</span></span>

<span data-ttu-id="16a73-120">Der zweite Befehl verwendet das Cmdlet "Stop-Process", um den Prozess mit der in $NID gespeicherten ID zu unterbinden.</span><span class="sxs-lookup"><span data-stu-id="16a73-120">The second command uses the Stop-Process cmdlet to stop the process with the ID stored in $nid.</span></span>

<span data-ttu-id="16a73-121">Der dritte Befehl verwendet **Wait-Process** , um zu warten, bis der Notepad-Prozess beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="16a73-121">The third command uses **Wait-Process** to wait until the Notepad process is stopped.</span></span>
<span data-ttu-id="16a73-122">Er verwendet den *ID* -Parameter von **Wait-Process** , um den Prozess zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="16a73-122">It uses the *Id* parameter of **Wait-Process** to identify the process.</span></span>

### <span data-ttu-id="16a73-123">Beispiel 2: Angeben eines Prozesses</span><span class="sxs-lookup"><span data-stu-id="16a73-123">Example 2: Specifying a process</span></span>

```
PS C:\> $p = Get-Process notepad
PS C:\> Wait-Process -Id $p.id
PS C:\> Wait-Process -Name "notepad"
PS C:\> Wait-Process -InputObject $p
```

<span data-ttu-id="16a73-124">Diese Befehle zeigen drei verschiedene Methoden zum Angeben eines Prozesses, der **gewartet** werden soll.</span><span class="sxs-lookup"><span data-stu-id="16a73-124">These commands show three different methods of specifying a process to **Wait-Process** .</span></span>
<span data-ttu-id="16a73-125">Der erste Befehl ruft den Notepad-Prozess ab und speichert ihn in der $p Variable.</span><span class="sxs-lookup"><span data-stu-id="16a73-125">The first command gets the Notepad process and stores it in the $p variable.</span></span>

<span data-ttu-id="16a73-126">Der zweite Befehl verwendet den *ID* -Parameter, der dritte Befehl verwendet den *Name* -Parameter, und der vierte Befehl verwendet den *Inputobject* -Parameter.</span><span class="sxs-lookup"><span data-stu-id="16a73-126">The second command uses the *Id* parameter, the third command uses the *Name* parameter, and the fourth command uses the *InputObject* parameter.</span></span>

<span data-ttu-id="16a73-127">Die Ergebnisse dieser Befehle sind identisch und austauschbar.</span><span class="sxs-lookup"><span data-stu-id="16a73-127">These commands have the same results and can be used interchangeably.</span></span>

### <span data-ttu-id="16a73-128">Beispiel 3: warten auf Prozesse für einen angegebenen Zeitraum</span><span class="sxs-lookup"><span data-stu-id="16a73-128">Example 3: Wait for processes for a specified time</span></span>

```
PS C:\> Wait-Process -Name outlook, winword -Timeout 30
```

<span data-ttu-id="16a73-129">Dieser Befehl wartet 30 Sekunden, dass die Prozesse %%amp;quot;Outlook%%amp;quot; und %%amp;quot;Winword%%amp;quot; beendet werden.</span><span class="sxs-lookup"><span data-stu-id="16a73-129">This command waits 30 seconds for the Outlook and Winword processes to stop.</span></span>
<span data-ttu-id="16a73-130">Wenn beide Prozesse nicht beendet werden, zeigt das Cmdlet einen Fehler ohne Abbruch sowie die Eingabeaufforderung an.</span><span class="sxs-lookup"><span data-stu-id="16a73-130">If both processes are not stopped, the cmdlet displays a non-terminating error and the command prompt.</span></span>

## <span data-ttu-id="16a73-131">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="16a73-131">PARAMETERS</span></span>

### <span data-ttu-id="16a73-132">-Id</span><span class="sxs-lookup"><span data-stu-id="16a73-132">-Id</span></span>
<span data-ttu-id="16a73-133">Gibt die Prozess-IDs der Prozesse an.</span><span class="sxs-lookup"><span data-stu-id="16a73-133">Specifies the process IDs of the processes.</span></span>
<span data-ttu-id="16a73-134">Wenn Sie mehrere IDs angeben, trennen Sie diese durch Kommas.</span><span class="sxs-lookup"><span data-stu-id="16a73-134">To specify multiple IDs, use commas to separate the IDs.</span></span>
<span data-ttu-id="16a73-135">Um die PID eines Prozesses zu ermitteln, geben Sie ein `Get-Process` .</span><span class="sxs-lookup"><span data-stu-id="16a73-135">To find the PID of a process, type `Get-Process`.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases: PID, ProcessId

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="16a73-136">-InputObject</span><span class="sxs-lookup"><span data-stu-id="16a73-136">-InputObject</span></span>
<span data-ttu-id="16a73-137">Gibt die Prozesse durch Senden von Prozessobjekten an.</span><span class="sxs-lookup"><span data-stu-id="16a73-137">Specifies the processes by submitting process objects.</span></span>
<span data-ttu-id="16a73-138">Geben Sie eine Variable ein, die die Prozess Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, der die Prozess Objekte abruft, z. b. das Get-Process Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="16a73-138">Enter a variable that contains the process objects, or type a command or expression that gets the process objects, such as the Get-Process cmdlet.</span></span>

```yaml
Type: System.Diagnostics.Process[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="16a73-139">-Name</span><span class="sxs-lookup"><span data-stu-id="16a73-139">-Name</span></span>
<span data-ttu-id="16a73-140">Gibt die Prozessnamen der Prozesse an.</span><span class="sxs-lookup"><span data-stu-id="16a73-140">Specifies the process names of the processes.</span></span>
<span data-ttu-id="16a73-141">Wenn Sie mehrere Namen angeben, trennen Sie diese durch Kommas.</span><span class="sxs-lookup"><span data-stu-id="16a73-141">To specify multiple names, use commas to separate the names.</span></span>
<span data-ttu-id="16a73-142">Platzhalterzeichen werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="16a73-142">Wildcard characters are not supported.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases: ProcessName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="16a73-143">-Timeout</span><span class="sxs-lookup"><span data-stu-id="16a73-143">-Timeout</span></span>
<span data-ttu-id="16a73-144">Gibt die maximale Zeit in Sekunden an, die dieses Cmdlet darauf wartet, dass die angegebenen Prozesse beendet werden.</span><span class="sxs-lookup"><span data-stu-id="16a73-144">Specifies the maximum time, in seconds, that this cmdlet waits for the specified processes to stop.</span></span>
<span data-ttu-id="16a73-145">Wenn dieses Intervall abläuft, zeigt der Befehl einen Fehler ohne Abbruch an, bei dem die noch ausgeführten Prozesse aufgeführt werden, und beendet den Wartevorgang.</span><span class="sxs-lookup"><span data-stu-id="16a73-145">When this interval expires, the command displays a non-terminating error that lists the processes that are still running, and ends the wait.</span></span>
<span data-ttu-id="16a73-146">Standardmäßig ist kein Timeout vorhanden.</span><span class="sxs-lookup"><span data-stu-id="16a73-146">By default, there is no time-out.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: TimeoutSec

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="16a73-147">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="16a73-147">CommonParameters</span></span>
<span data-ttu-id="16a73-148">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="16a73-148">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="16a73-149">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="16a73-149">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="16a73-150">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="16a73-150">INPUTS</span></span>

### <span data-ttu-id="16a73-151">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="16a73-151">System.Diagnostics.Process</span></span>
<span data-ttu-id="16a73-152">Sie können ein Prozess Objekt über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="16a73-152">You can pipe a process object to this cmdlet.</span></span>

## <span data-ttu-id="16a73-153">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="16a73-153">OUTPUTS</span></span>

### <span data-ttu-id="16a73-154">Keine</span><span class="sxs-lookup"><span data-stu-id="16a73-154">None</span></span>
<span data-ttu-id="16a73-155">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="16a73-155">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="16a73-156">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="16a73-156">NOTES</span></span>

* <span data-ttu-id="16a73-157">Dieses Cmdlet verwendet die **WaitForExit** -Methode der System. Diagnostics. Process-Klasse.</span><span class="sxs-lookup"><span data-stu-id="16a73-157">This cmdlet uses the **WaitForExit** method of the System.Diagnostics.Process class.</span></span> <span data-ttu-id="16a73-158">Weitere Informationen zu dieser Methode finden Sie im Microsoft .NET Framework SDK.</span><span class="sxs-lookup"><span data-stu-id="16a73-158">For more information about this method, see the Microsoft .NET Framework SDK.</span></span>

*

## <span data-ttu-id="16a73-159">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="16a73-159">RELATED LINKS</span></span>

[<span data-ttu-id="16a73-160">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="16a73-160">Debug-Process</span></span>](Debug-Process.md)

[<span data-ttu-id="16a73-161">Get-Process</span><span class="sxs-lookup"><span data-stu-id="16a73-161">Get-Process</span></span>](Get-Process.md)

[<span data-ttu-id="16a73-162">Start-Process</span><span class="sxs-lookup"><span data-stu-id="16a73-162">Start-Process</span></span>](Start-Process.md)

[<span data-ttu-id="16a73-163">Stop-Process</span><span class="sxs-lookup"><span data-stu-id="16a73-163">Stop-Process</span></span>](Stop-Process.md)

[<span data-ttu-id="16a73-164">Wait-Process</span><span class="sxs-lookup"><span data-stu-id="16a73-164">Wait-Process</span></span>](Wait-Process.md)
