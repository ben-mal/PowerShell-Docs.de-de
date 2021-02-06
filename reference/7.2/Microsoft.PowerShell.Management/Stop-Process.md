---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/stop-process?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Process
ms.openlocfilehash: 8c9e520f1f19444fd538fabee99a48ec08c69992
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599849"
---
# <span data-ttu-id="12a37-102">Stop-Process</span><span class="sxs-lookup"><span data-stu-id="12a37-102">Stop-Process</span></span>

## <span data-ttu-id="12a37-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="12a37-103">SYNOPSIS</span></span>
<span data-ttu-id="12a37-104">Beendet ausgeführte Prozesse.</span><span class="sxs-lookup"><span data-stu-id="12a37-104">Stops one or more running processes.</span></span>

## <span data-ttu-id="12a37-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="12a37-105">SYNTAX</span></span>

### <span data-ttu-id="12a37-106">ID (Standard)</span><span class="sxs-lookup"><span data-stu-id="12a37-106">Id (Default)</span></span>

```
Stop-Process [-Id] <Int32[]> [-PassThru] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="12a37-107">Name</span><span class="sxs-lookup"><span data-stu-id="12a37-107">Name</span></span>

```
Stop-Process -Name <String[]> [-PassThru] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="12a37-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="12a37-108">InputObject</span></span>

```
Stop-Process [-InputObject] <Process[]> [-PassThru] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="12a37-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="12a37-109">DESCRIPTION</span></span>

<span data-ttu-id="12a37-110">Das Cmdlet " **Stopp-Process** " beendet mindestens einen laufenden Prozess.</span><span class="sxs-lookup"><span data-stu-id="12a37-110">The **Stop-Process** cmdlet stops one or more running processes.</span></span>
<span data-ttu-id="12a37-111">Sie können einen Prozess anhand des Prozess namens oder der Prozess-ID (PID) angeben oder ein Prozess Objekt an "Process **-Process**" übergeben.</span><span class="sxs-lookup"><span data-stu-id="12a37-111">You can specify a process by process name or process ID (PID), or pass a process object to **Stop-Process**.</span></span>
<span data-ttu-id="12a37-112">" **Beendet-Process** " funktioniert nur bei Prozessen, die auf dem lokalen Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="12a37-112">**Stop-Process** works only on processes running on the local computer.</span></span>

<span data-ttu-id="12a37-113">Unter Windows Vista und höheren Versionen des Windows-Betriebssystems müssen Sie PowerShell mit der Option als Administrator ausführen starten, um einen Prozess zu verhindern, der nicht im Besitz des aktuellen Benutzers ist.</span><span class="sxs-lookup"><span data-stu-id="12a37-113">On Windows Vista and later versions of the Windows operating system, to stop a process that is not owned by the current user, you must start PowerShell by using the Run as administrator option.</span></span>
<span data-ttu-id="12a37-114">Außerdem werden Sie nicht zur Bestätigung aufgefordert, es sei denn, Sie geben den *Confirm* -Parameter an.</span><span class="sxs-lookup"><span data-stu-id="12a37-114">Also, you are not prompted for confirmation unless you specify the *Confirm* parameter.</span></span>

## <span data-ttu-id="12a37-115">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="12a37-115">EXAMPLES</span></span>

### <span data-ttu-id="12a37-116">Beispiel 1: alle Instanzen eines Prozesses werden beendet</span><span class="sxs-lookup"><span data-stu-id="12a37-116">Example 1: Stop all instances of a process</span></span>

```
PS C:\> Stop-Process -Name "notepad"
```

<span data-ttu-id="12a37-117">Mit diesem Befehl werden alle Instanzen des Notepad-Prozesses (Editor) auf dem Computer beendet.</span><span class="sxs-lookup"><span data-stu-id="12a37-117">This command stops all instances of the Notepad process on the computer.</span></span>
<span data-ttu-id="12a37-118">Jede Instanz von Editor wird in einem eigenen Prozess ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="12a37-118">Each instance of Notepad runs in its own process.</span></span>
<span data-ttu-id="12a37-119">Er verwendet den *Name* -Parameter, um die Prozesse anzugeben, die alle den gleichen Namen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="12a37-119">It uses the *Name* parameter to specify the processes, all of which have the same name.</span></span>
<span data-ttu-id="12a37-120">Wenn Sie den *ID* -Parameter verwenden, um die gleichen Prozesse anzuhalten, müssten Sie die Prozess-IDs jeder Instanz von Notepad auflisten.</span><span class="sxs-lookup"><span data-stu-id="12a37-120">If you were to use the *Id* parameter to stop the same processes, you would have to list the process IDs of each instance of Notepad.</span></span>

### <span data-ttu-id="12a37-121">Beispiel 2: beendet eine bestimmte Instanz eines Prozesses.</span><span class="sxs-lookup"><span data-stu-id="12a37-121">Example 2: Stop a specific instance of a process</span></span>

```
PS C:\> Stop-Process -Id 3952 -Confirm -PassThru
Confirm
Are you sure you want to perform this action?
Performing operation "Stop-Process" on Target "notepad (3952)".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help
(default is "Y"):y
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
41       2      996       3212    31            3952 notepad
```

<span data-ttu-id="12a37-122">Mit diesem Befehl wird eine bestimmte Instanz des Notepad-Prozesses beendet.</span><span class="sxs-lookup"><span data-stu-id="12a37-122">This command stops a particular instance of the Notepad process.</span></span>
<span data-ttu-id="12a37-123">Der Prozess wird mit der Prozess-ID 3952 angegeben.</span><span class="sxs-lookup"><span data-stu-id="12a37-123">It uses the process ID, 3952, to identify the process.</span></span>
<span data-ttu-id="12a37-124">Der *Confirm* -Parameter weist PowerShell an, Sie einzugeben, bevor der Prozess beendet wird.</span><span class="sxs-lookup"><span data-stu-id="12a37-124">The *Confirm* parameter directs PowerShell to prompt you before it stops the process.</span></span>
<span data-ttu-id="12a37-125">Da die Eingabeaufforderung neben der ID auch den Prozessnamen enthält, ist dies die bewährte Vorgehensweise.</span><span class="sxs-lookup"><span data-stu-id="12a37-125">Because the prompt includes the process namein addition to its ID, this is best practice.</span></span>
<span data-ttu-id="12a37-126">Der *passthru* -Parameter übergibt das Prozess Objekt zur Anzeige an den Formatierer.</span><span class="sxs-lookup"><span data-stu-id="12a37-126">The *PassThru* parameter passes the process object to the formatter for display.</span></span>
<span data-ttu-id="12a37-127">Ohne diesen Parameter wird nach einem Befehl zum **Abbrechen des Vorgangs** keine Anzeige angezeigt.</span><span class="sxs-lookup"><span data-stu-id="12a37-127">Without this parameter, there would be no display after a **Stop-Process** command.</span></span>

### <span data-ttu-id="12a37-128">Beispiel 3: Beenden eines Prozesses und erkennen, dass er beendet wurde</span><span class="sxs-lookup"><span data-stu-id="12a37-128">Example 3: Stop a process and detect that it has stopped</span></span>

```
PS C:\> calc
PS C:\> $p = Get-Process -Name "calc"
PS C:\> Stop-Process -InputObject $p
PS C:\> Get-Process | Where-Object {$_.HasExited}
```

<span data-ttu-id="12a37-129">Mit dieser Reihe von Befehlen wird der Calc-Prozess gestartet und beendet. Anschließend werden Prozesse erkannt, die beendet wurden.</span><span class="sxs-lookup"><span data-stu-id="12a37-129">This series of commands starts and stops the Calc process, and then detects processes that have stopped.</span></span>

<span data-ttu-id="12a37-130">Mit dem ersten Befehl wird eine Instanz des Rechners gestartet.</span><span class="sxs-lookup"><span data-stu-id="12a37-130">The first command starts an instance of the calculator.</span></span>

<span data-ttu-id="12a37-131">Der zweite Befehl verwendet **Get-Process** und ruft ein Objekt ab, das den Calc-Prozess darstellt, und speichert es dann in der $p-Variablen.</span><span class="sxs-lookup"><span data-stu-id="12a37-131">The second command uses **Get-Process** gets an object that represents the Calc process, and then stores it in the $p variable.</span></span>

<span data-ttu-id="12a37-132">Mit dem dritten Befehl wird der Calc-Prozess beendet.</span><span class="sxs-lookup"><span data-stu-id="12a37-132">The third command stops the Calc process.</span></span>
<span data-ttu-id="12a37-133">Er verwendet den *Inputobject* -Parameter, um das Objekt an " **Process-Process**" zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="12a37-133">It uses the *InputObject* parameter to pass the object to **Stop-Process**.</span></span>

<span data-ttu-id="12a37-134">Mit dem letzten Befehl werden alle zuvor auf dem Computer ausgeführten Prozesse abgerufen, die nun beendet sind.</span><span class="sxs-lookup"><span data-stu-id="12a37-134">The last command gets all of the processes on the computer that were running but that are now stopped.</span></span>
<span data-ttu-id="12a37-135">Er verwendet **Get-Process** , um alle Prozesse auf dem Computer zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="12a37-135">It uses **Get-Process** to get all of the processes on the computer.</span></span>
<span data-ttu-id="12a37-136">Der Pipeline Operator (|) übergibt die Ergebnisse an das Where-Object-Cmdlet, das diejenigen auswählt, bei denen der Wert der **HasExited** -Eigenschaft $true ist.</span><span class="sxs-lookup"><span data-stu-id="12a37-136">The pipeline operator (|) passes the results to the Where-Object cmdlet, which selects the ones where the value of the **HasExited** property is $True.</span></span>
<span data-ttu-id="12a37-137">**HasExited** ist nur eine Eigenschaft von Process-Objekten.</span><span class="sxs-lookup"><span data-stu-id="12a37-137">**HasExited** is just one property of process objects.</span></span>
<span data-ttu-id="12a37-138">Um alle Eigenschaften zu suchen, geben Sie ein `Get-Process | Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="12a37-138">To find all the properties, type `Get-Process | Get-Member`.</span></span>

### <span data-ttu-id="12a37-139">Beispiel 4: Beendigung eines Prozesses, der nicht im Besitz des aktuellen Benutzers ist</span><span class="sxs-lookup"><span data-stu-id="12a37-139">Example 4: Stop a process not owned by the current user</span></span>

```
PS C:\> Get-Process -Name "lsass" | Stop-Process

Stop-Process : Cannot stop process 'lsass (596)' because of the following error: Access is denied
At line:1 char:34
+ Get-Process -Name "lsass" | Stop-Process <<<<

[ADMIN]: PS C:\> Get-Process -Name "lsass" | Stop-Process

Warning!
Are you sure you want to perform this action?
Performing operation 'Stop-Process' on Target 'lsass(596)'
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
[ADMIN]: PS C:\> Get-Process -Name "lsass" | Stop-Process -Force
[ADMIN]: PS C:\>
```

<span data-ttu-id="12a37-140">Diese Befehle zeigen die Auswirkung der Verwendung von *Force* zum Abbrechen eines Prozesses, der nicht im Besitz des Benutzers ist.</span><span class="sxs-lookup"><span data-stu-id="12a37-140">These commands show the effect of using *Force* to stop a process that is not owned by the user.</span></span>

<span data-ttu-id="12a37-141">Der erste Befehl verwendet **Get-Process** , um den LSASS-Prozess zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="12a37-141">The first command uses **Get-Process** to get the Lsass process.</span></span>
<span data-ttu-id="12a37-142">Ein Pipeline Operator sendet den Prozess an den Prozess **zum Abbrechen, um ihn** zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="12a37-142">A pipeline operator sends the process to **Stop-Process** to stop it.</span></span>
<span data-ttu-id="12a37-143">Wie in der Beispielausgabe gezeigt, schlägt der erste Befehl mit der Meldung "Zugriff verweigert" fehl, da dieser Vorgang nur von einem Mitglied der Administrator Gruppe auf dem Computer beendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="12a37-143">As shown in the sample output, the first command fails with an Access denied message, because this process can be stopped only by a member of the Administrator group on the computer.</span></span>

<span data-ttu-id="12a37-144">Wenn PowerShell mit der Option als Administrator ausführen geöffnet wird und der Befehl wiederholt wird, werden Sie von PowerShell zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="12a37-144">When PowerShell is opened by using the Run as administrator option, and the command is repeated, PowerShell prompts you for confirmation.</span></span>

<span data-ttu-id="12a37-145">Der zweite Befehl gibt *Force* an, um die Eingabeaufforderung zu unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="12a37-145">The second command specifies *Force* to suppress the prompt.</span></span>
<span data-ttu-id="12a37-146">Der Prozess wird daher ohne Bestätigung beendet.</span><span class="sxs-lookup"><span data-stu-id="12a37-146">As a result, the process is stopped without confirmation.</span></span>

## <span data-ttu-id="12a37-147">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="12a37-147">PARAMETERS</span></span>

### <span data-ttu-id="12a37-148">-Force</span><span class="sxs-lookup"><span data-stu-id="12a37-148">-Force</span></span>

<span data-ttu-id="12a37-149">Beendet die angegebenen Prozesse, ohne zum Bestätigen aufzufordern.</span><span class="sxs-lookup"><span data-stu-id="12a37-149">Stops the specified processes without prompting for confirmation.</span></span>
<span data-ttu-id="12a37-150">Standardmäßig fordert **Stop-Process** vor dem Beenden eines Prozesses, der nicht im Besitz des aktuellen Benutzers ist, zur Bestätigung auf.</span><span class="sxs-lookup"><span data-stu-id="12a37-150">By default, **Stop-Process** prompts for confirmation before stopping any process that is not owned by the current user.</span></span>

<span data-ttu-id="12a37-151">Um den Besitzer eines Prozesses zu suchen, verwenden Sie das `Get-CimInstance` Cmdlet, um ein **Win32_Process** Objekt zu erhalten, das den Prozess darstellt, und verwenden Sie dann die **GetOwner** -Methode des Objekts.</span><span class="sxs-lookup"><span data-stu-id="12a37-151">To find the owner of a process, use the `Get-CimInstance` cmdlet to get a **Win32_Process** object that represents the process, and then use the **GetOwner** method of the object.</span></span>

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

### <span data-ttu-id="12a37-152">-Id</span><span class="sxs-lookup"><span data-stu-id="12a37-152">-Id</span></span>

<span data-ttu-id="12a37-153">Gibt die Prozess-IDs der Prozesse an, die beendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="12a37-153">Specifies the process IDs of the processes to stop.</span></span>
<span data-ttu-id="12a37-154">Wenn Sie mehrere IDs angeben, trennen Sie diese durch Kommas.</span><span class="sxs-lookup"><span data-stu-id="12a37-154">To specify multiple IDs, use commas to separate the IDs.</span></span>
<span data-ttu-id="12a37-155">Um die PID eines Prozesses zu ermitteln, geben Sie ein `Get-Process` .</span><span class="sxs-lookup"><span data-stu-id="12a37-155">To find the PID of a process, type `Get-Process`.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="12a37-156">-InputObject</span><span class="sxs-lookup"><span data-stu-id="12a37-156">-InputObject</span></span>

<span data-ttu-id="12a37-157">Gibt die Prozess Objekte an, die beendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="12a37-157">Specifies the process objects to stop.</span></span>
<span data-ttu-id="12a37-158">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="12a37-158">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

```yaml
Type: System.Diagnostics.Process[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="12a37-159">-Name</span><span class="sxs-lookup"><span data-stu-id="12a37-159">-Name</span></span>

<span data-ttu-id="12a37-160">Gibt die Prozessnamen der zu stoppenden Prozesse an.</span><span class="sxs-lookup"><span data-stu-id="12a37-160">Specifies the process names of the processes to stop.</span></span>
<span data-ttu-id="12a37-161">Sie können mehrere Prozessnamen eingeben, durch Kommas getrennt oder Platzhalter Zeichen verwenden.</span><span class="sxs-lookup"><span data-stu-id="12a37-161">You can type multiple process names, separated by commas, or use wildcard characters.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases: ProcessName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="12a37-162">-PassThru</span><span class="sxs-lookup"><span data-stu-id="12a37-162">-PassThru</span></span>

<span data-ttu-id="12a37-163">Gibt ein Objekt zurück, das den Prozess darstellt.</span><span class="sxs-lookup"><span data-stu-id="12a37-163">Returns an object that represents the process.</span></span>
<span data-ttu-id="12a37-164">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="12a37-164">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="12a37-165">-Confirm</span><span class="sxs-lookup"><span data-stu-id="12a37-165">-Confirm</span></span>

<span data-ttu-id="12a37-166">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="12a37-166">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="12a37-167">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="12a37-167">-WhatIf</span></span>

<span data-ttu-id="12a37-168">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="12a37-168">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="12a37-169">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="12a37-169">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="12a37-170">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="12a37-170">CommonParameters</span></span>
<span data-ttu-id="12a37-171">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="12a37-171">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="12a37-172">Weitere Informationen findest du unter [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="12a37-172">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="12a37-173">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="12a37-173">INPUTS</span></span>

### <span data-ttu-id="12a37-174">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="12a37-174">System.Diagnostics.Process</span></span>

<span data-ttu-id="12a37-175">Sie können ein Prozess Objekt über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="12a37-175">You can pipe a process object to this cmdlet.</span></span>

## <span data-ttu-id="12a37-176">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="12a37-176">OUTPUTS</span></span>

### <span data-ttu-id="12a37-177">None, System. Diagnostics. Process</span><span class="sxs-lookup"><span data-stu-id="12a37-177">None, System.Diagnostics.Process</span></span>

<span data-ttu-id="12a37-178">Dieses Cmdlet gibt ein **System. Diagnostics. Process** -Objekt zurück, das den beendeten Prozess darstellt, wenn Sie den *passthru* -Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="12a37-178">This cmdlet returns a **System.Diagnostics.Process** object that represents the stopped process, if you specify the *PassThru* parameter.</span></span>
<span data-ttu-id="12a37-179">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="12a37-179">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="12a37-180">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="12a37-180">NOTES</span></span>

* <span data-ttu-id="12a37-181">Weitere Informationen finden Sie auch unter **Beenden/verarbeiten** durch die integrierten Aliase, **Kill** und **SPPS**.</span><span class="sxs-lookup"><span data-stu-id="12a37-181">You can also refer to **Stop-Process** by its built-in aliases, **kill** and **spps**.</span></span> <span data-ttu-id="12a37-182">Weitere Informationen finden Sie unter %%amp;quot;about_Aliases%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="12a37-182">For more information, see about_Aliases.</span></span>

  <span data-ttu-id="12a37-183">Sie können auch die Eigenschaften und Methoden des Windows-Verwaltungsinstrumentation (WMI) **Win32_Process** -Objekts in Windows PowerShell verwenden.</span><span class="sxs-lookup"><span data-stu-id="12a37-183">You can also use the properties and methods of the Windows Management Instrumentation (WMI) **Win32_Process** object in Windows PowerShell.</span></span>
<span data-ttu-id="12a37-184">Weitere Informationen finden Sie unter `Get-CimInstance` und im WMI SDK.</span><span class="sxs-lookup"><span data-stu-id="12a37-184">For more information, see `Get-CimInstance` and the WMI SDK.</span></span>

* <span data-ttu-id="12a37-185">Wenn Sie Prozesse beenden, beachten Sie, dass durch das Beenden eines Prozesses Prozess und Dienste angehalten werden können, die vom Prozess abhängen.</span><span class="sxs-lookup"><span data-stu-id="12a37-185">When stopping processes, realize that stopping a process can stop process and services that depend on the process.</span></span>
<span data-ttu-id="12a37-186">Im Extremfall kann durch Beenden eines Prozesses sogar Windows beendet werden.</span><span class="sxs-lookup"><span data-stu-id="12a37-186">In an extreme case, stopping a process can stop Windows.</span></span>

## <span data-ttu-id="12a37-187">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="12a37-187">RELATED LINKS</span></span>

[<span data-ttu-id="12a37-188">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="12a37-188">Debug-Process</span></span>](Debug-Process.md)

[<span data-ttu-id="12a37-189">Get-Process</span><span class="sxs-lookup"><span data-stu-id="12a37-189">Get-Process</span></span>](Get-Process.md)

[<span data-ttu-id="12a37-190">Start-Process</span><span class="sxs-lookup"><span data-stu-id="12a37-190">Start-Process</span></span>](Start-Process.md)

[<span data-ttu-id="12a37-191">Stop-Process</span><span class="sxs-lookup"><span data-stu-id="12a37-191">Stop-Process</span></span>](Stop-Process.md)

[<span data-ttu-id="12a37-192">Wait-Process</span><span class="sxs-lookup"><span data-stu-id="12a37-192">Wait-Process</span></span>](Wait-Process.md)

