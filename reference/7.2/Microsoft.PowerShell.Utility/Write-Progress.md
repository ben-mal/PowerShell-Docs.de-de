---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-progress?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Progress
ms.openlocfilehash: 2e2bd5474198745d72ad2b87c3c305695a198f22
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602517"
---
# <span data-ttu-id="14565-102">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="14565-102">Write-Progress</span></span>

## <span data-ttu-id="14565-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="14565-103">SYNOPSIS</span></span>
<span data-ttu-id="14565-104">Zeigt eine Statusanzeige in einem PowerShell-Befehlsfenster an.</span><span class="sxs-lookup"><span data-stu-id="14565-104">Displays a progress bar within a PowerShell command window.</span></span>

## <span data-ttu-id="14565-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="14565-105">SYNTAX</span></span>

```
Write-Progress [-Activity] <String> [[-Status] <String>] [[-Id] <Int32>] [-PercentComplete <Int32>]
 [-SecondsRemaining <Int32>] [-CurrentOperation <String>] [-ParentId <Int32>] [-Completed] [-SourceId <Int32>]
 [<CommonParameters>]
```

## <span data-ttu-id="14565-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="14565-106">DESCRIPTION</span></span>

<span data-ttu-id="14565-107">Das- `Write-Progress` Cmdlet zeigt eine Statusanzeige in einem PowerShell-Befehlsfenster an, das den Status eines ausgeführten Befehls oder Skripts darstellt.</span><span class="sxs-lookup"><span data-stu-id="14565-107">The `Write-Progress` cmdlet displays a progress bar in a PowerShell command window that depicts the status of a running command or script.</span></span> <span data-ttu-id="14565-108">Sie können die dargestellten Indikatoren wählen, sowie den Text, der über und unter der Statusanzeige erscheint.</span><span class="sxs-lookup"><span data-stu-id="14565-108">You can select the indicators that the bar reflects and the text that appears above and below the progress bar.</span></span>

## <span data-ttu-id="14565-109">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="14565-109">EXAMPLES</span></span>

### <span data-ttu-id="14565-110">Beispiel 1: Anzeigen des Status einer for-Schleife</span><span class="sxs-lookup"><span data-stu-id="14565-110">Example 1: Display the progress of a For loop</span></span>

```powershell
for ($i = 1; $i -le 100; $i++ )
{
    Write-Progress -Activity "Search in Progress" -Status "$i% Complete:" -PercentComplete $i;
}
```

<span data-ttu-id="14565-111">Dieser Befehl zeigt den Status einer For-Schleife an, die von 1 bis 100 zählt.</span><span class="sxs-lookup"><span data-stu-id="14565-111">This command displays the progress of a For loop that counts from 1 to 100.</span></span>

<span data-ttu-id="14565-112">Das `Write-Progress` -Cmdlet umfasst eine Überschrift der Statusleiste `Activity` , eine Statuszeile und die-Variable `$i` (der-Counter in der for-Schleife), die die relative Vollständigkeit der Aufgabe angibt.</span><span class="sxs-lookup"><span data-stu-id="14565-112">The `Write-Progress` cmdlet includes a status bar heading `Activity`, a status line, and the variable `$i` (the counter in the For loop), which indicates the relative completeness of the task.</span></span>

### <span data-ttu-id="14565-113">Beispiel 2: Anzeigen des Fortschritts von schsted for-Schleifen</span><span class="sxs-lookup"><span data-stu-id="14565-113">Example 2: Display the progress of nested For loops</span></span>

```powershell
for($I = 1; $I -lt 101; $I++ )
{
    Write-Progress -Activity Updating -Status 'Progress->' -PercentComplete $I -CurrentOperation OuterLoop
    for($j = 1; $j -lt 101; $j++ )
    {
        Write-Progress -Id 1 -Activity Updating -Status 'Progress' -PercentComplete $j -CurrentOperation InnerLoop
    }
}
```

```Output
Updating
Progress ->
 [ooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooo]
OuterLoop
Updating
Progress
 [oooooooooooooooooo                                                   ]
InnerLoop
```

<span data-ttu-id="14565-114">Dieses Beispiel zeigt den Status zweier geschachtelter For-Schleifen an, die jeweils durch eine Statusanzeige dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="14565-114">This example displays the progress of two nested For loops, each of which is represented by a progress bar.</span></span>

<span data-ttu-id="14565-115">Der `Write-Progress` Befehl für die zweite Statusanzeige enthält den **ID** -Parameter, der ihn von der ersten Statusanzeige unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="14565-115">The `Write-Progress` command for the second progress bar includes the **Id** parameter that distinguishes it from the first progress bar.</span></span>

<span data-ttu-id="14565-116">Ohne den **ID** -Parameter würden die Status anzeigen einander ausgesetzt werden, anstatt nebeneinander angezeigt zu werden.</span><span class="sxs-lookup"><span data-stu-id="14565-116">Without the **Id** parameter, the progress bars would be superimposed on each other instead of being displayed one below the other.</span></span>

### <span data-ttu-id="14565-117">Beispiel 3: Anzeigen des Fortschritts beim Suchen nach einer Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="14565-117">Example 3: Display the progress while searching for a string</span></span>

```powershell
# Use Get-EventLog to get the events in the System log and store them in the $Events variable.
$Events = Get-EventLog -LogName system
# Pipe the events to the ForEach-Object cmdlet.
$Events | ForEach-Object -Begin {
    # In the Begin block, use Clear-Host to clear the screen.
    Clear-Host
    # Set the $i counter variable to zero.
    $i = 0
    # Set the $out variable to a empty string.
    $out = ""
} -Process {
    # In the Process script block search the message property of each incoming object for "bios".
    if($_.message -like "*bios*")
    {
        # Append the matching message to the out variable.
        $out=$out + $_.Message
    }
    # Increment the $i counter variable which is used to create the progress bar.
    $i = $i+1
    # Use Write-Progress to output a progress bar.
    # The Activity and Status parameters create the first and second lines of the progress bar heading, respectively.
    Write-Progress -Activity "Searching Events" -Status "Progress:" -PercentComplete ($i/$Events.count*100)
} -End {
    # Display the matching messages using the out variable.
    $out
}
```

<span data-ttu-id="14565-118">Dieser Befehl zeigt den Status eines Befehls zum Suchen der Zeichenfolge „bios“ im Systemereignisprotokoll an.</span><span class="sxs-lookup"><span data-stu-id="14565-118">This command displays the progress of a command to find the string "bios" in the System event log.</span></span>

<span data-ttu-id="14565-119">Der Wert für den Wert für " **prozentucomplete** " wird berechnet, indem die Anzahl der Ereignisse, die `$I` von der Gesamtzahl der abgerufenen Ereignisse verarbeitet wurden, dividiert `$Events.count` und dann das Ergebnis mit 100 multipliziert wird.</span><span class="sxs-lookup"><span data-stu-id="14565-119">The **PercentComplete** parameter value is calculated by dividing the number of events that have been processed `$I` by the total number of events retrieved `$Events.count` and then multiplying that result by 100.</span></span>

### <span data-ttu-id="14565-120">Beispiel 4: Anzeigen des Fortschritts für jede Ebene eines genetzten Prozesses</span><span class="sxs-lookup"><span data-stu-id="14565-120">Example 4: Display progress for each level of a nested process</span></span>

```powershell
foreach ( $i in 1..10 ) {
  Write-Progress -Id 0 "Step $i"
  foreach ( $j in 1..10 ) {
    Write-Progress -Id 1 -ParentId 0 "Step $i - Substep $j"
    foreach ( $k in 1..10 ) {
      Write-Progress -Id 2  -ParentId 1 "Step $i - Substep $j - iteration $k"; start-sleep -m 150
    }
  }
}
```

```Output
Step 1
     Processing
    Step 1 - Substep 2
         Processing
        Step 1 - Substep 2 - Iteration 3
             Processing
```

<span data-ttu-id="14565-121">In diesem Beispiel können Sie den Parameter "Parameter" verwenden, um eine eingerückt **-** Ausgabe zum Anzeigen von Beziehungen zwischen übergeordneten und untergeordneten Elementen im Status der einzelnen Schritte zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="14565-121">In this example you can use the **ParentId** parameter to have indented output to show parent/child relationships in the progress of each step.</span></span>

## <span data-ttu-id="14565-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="14565-122">PARAMETERS</span></span>

### <span data-ttu-id="14565-123">-Aktivität</span><span class="sxs-lookup"><span data-stu-id="14565-123">-Activity</span></span>

<span data-ttu-id="14565-124">Gibt die erste Textzeile in der Überschrift über der Statusanzeige an.</span><span class="sxs-lookup"><span data-stu-id="14565-124">Specifies the first line of text in the heading above the status bar.</span></span>
<span data-ttu-id="14565-125">Dieser Text beschreibt die Aktivität, deren Status gemeldet wird.</span><span class="sxs-lookup"><span data-stu-id="14565-125">This text describes the activity whose progress is being reported.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="14565-126">-Abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="14565-126">-Completed</span></span>

<span data-ttu-id="14565-127">Gibt an, ob die Statusanzeige sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="14565-127">Indicates whether the progress bar is visible.</span></span>
<span data-ttu-id="14565-128">Wenn dieser Parameter ausgelassen wird, werden Status `Write-Progress` Informationen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="14565-128">If this parameter is omitted, `Write-Progress` displays progress information.</span></span>

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

### <span data-ttu-id="14565-129">-CurrentOperation</span><span class="sxs-lookup"><span data-stu-id="14565-129">-CurrentOperation</span></span>

<span data-ttu-id="14565-130">Gibt die Textzeile unterhalb der Statusanzeige an.</span><span class="sxs-lookup"><span data-stu-id="14565-130">Specifies the line of text below the progress bar.</span></span>
<span data-ttu-id="14565-131">Dieser Text beschreibt den derzeit stattfindenden Vorgang.</span><span class="sxs-lookup"><span data-stu-id="14565-131">This text describes the operation that is currently taking place.</span></span>

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

### <span data-ttu-id="14565-132">-Id</span><span class="sxs-lookup"><span data-stu-id="14565-132">-Id</span></span>

<span data-ttu-id="14565-133">Gibt eine ID an, die die einzelnen Statusanzeigen voneinander unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="14565-133">Specifies an ID that distinguishes each progress bar from the others.</span></span> <span data-ttu-id="14565-134">Verwenden Sie diesen Parameter, wenn Sie in einem einzigen Befehl mehr als eine Statusanzeige erstellen.</span><span class="sxs-lookup"><span data-stu-id="14565-134">Use this parameter when you are creating more than one progress bar in a single command.</span></span> <span data-ttu-id="14565-135">Wenn die Statusanzeigen nicht über unterschiedliche IDs verfügen, werden sie aufeinander statt in einer Reihe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="14565-135">If the progress bars do not have different IDs, they are superimposed instead of being displayed in a series.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="14565-136">-Entid</span><span class="sxs-lookup"><span data-stu-id="14565-136">-ParentId</span></span>

<span data-ttu-id="14565-137">Gibt die übergeordnete Aktivität der aktuellen Aktivität an.</span><span class="sxs-lookup"><span data-stu-id="14565-137">Specifies the parent activity of the current activity.</span></span>
<span data-ttu-id="14565-138">Verwenden Sie den Wert -1, wenn die aktuelle Aktivität keine übergeordnete Aktivität besitzt.</span><span class="sxs-lookup"><span data-stu-id="14565-138">Use the value -1 if the current activity has no parent activity.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="14565-139">-Prozentuabgeschlossen</span><span class="sxs-lookup"><span data-stu-id="14565-139">-PercentComplete</span></span>

<span data-ttu-id="14565-140">Gibt den ausgeführten Anteil der Aktivität in Prozent an.</span><span class="sxs-lookup"><span data-stu-id="14565-140">Specifies the percentage of the activity that is completed.</span></span>
<span data-ttu-id="14565-141">Verwenden Sie den Wert -1, wenn der Prozentsatz unbekannt oder nicht zutreffend ist.</span><span class="sxs-lookup"><span data-stu-id="14565-141">Use the value -1 if the percentage complete is unknown or not applicable.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="14565-142">-Secondsrestdauer</span><span class="sxs-lookup"><span data-stu-id="14565-142">-SecondsRemaining</span></span>

<span data-ttu-id="14565-143">Gibt die voraussichtliche Anzahl von Sekunden an, bis die Aktivität abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="14565-143">Specifies the projected number of seconds remaining until the activity is completed.</span></span>
<span data-ttu-id="14565-144">Verwenden Sie den Wert -1, wenn die Anzahl der verbleibenden Sekunden unbekannt oder nicht zutreffend ist.</span><span class="sxs-lookup"><span data-stu-id="14565-144">Use the value -1 if the number of seconds remaining is unknown or not applicable.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="14565-145">-SourceID</span><span class="sxs-lookup"><span data-stu-id="14565-145">-SourceId</span></span>

<span data-ttu-id="14565-146">Gibt die Quelle des Datensatzes an.</span><span class="sxs-lookup"><span data-stu-id="14565-146">Specifies the source of the record.</span></span> <span data-ttu-id="14565-147">Sie können diese anstelle der **ID** verwenden, aber Sie können nicht mit anderen Parametern wie z. b. " **Parser**" verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="14565-147">You can use this in place of **Id** but cannot be used with other parameters like **ParentId**.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="14565-148">-Status</span><span class="sxs-lookup"><span data-stu-id="14565-148">-Status</span></span>

<span data-ttu-id="14565-149">Gibt die zweite Textzeile in der Überschrift über der Statusanzeige an.</span><span class="sxs-lookup"><span data-stu-id="14565-149">Specifies the second line of text in the heading above the status bar.</span></span>
<span data-ttu-id="14565-150">Dieser Text beschreibt den aktuellen Status der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="14565-150">This text describes current state of the activity.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="14565-151">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="14565-151">CommonParameters</span></span>

<span data-ttu-id="14565-152">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="14565-152">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="14565-153">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="14565-153">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="14565-154">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="14565-154">INPUTS</span></span>

### <span data-ttu-id="14565-155">Keine</span><span class="sxs-lookup"><span data-stu-id="14565-155">None</span></span>

<span data-ttu-id="14565-156">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="14565-156">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="14565-157">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="14565-157">OUTPUTS</span></span>

### <span data-ttu-id="14565-158">Keine</span><span class="sxs-lookup"><span data-stu-id="14565-158">None</span></span>

<span data-ttu-id="14565-159">`Write-Progress` generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="14565-159">`Write-Progress` does not generate any output.</span></span>

## <span data-ttu-id="14565-160">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="14565-160">NOTES</span></span>

<span data-ttu-id="14565-161">Wenn die Statusanzeige nicht angezeigt wird, überprüfen Sie den Wert der `$ProgressPreference` Variablen.</span><span class="sxs-lookup"><span data-stu-id="14565-161">If the progress bar does not appear, check the value of the `$ProgressPreference` variable.</span></span> <span data-ttu-id="14565-162">Wenn der Wert auf SilentlyContinue festgelegt ist, wird die Statusanzeige nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="14565-162">If the value is set to SilentlyContinue, the progress bar is not displayed.</span></span> <span data-ttu-id="14565-163">Weitere Informationen zu PowerShell-Einstellungen finden Sie unter [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="14565-163">For more information about PowerShell preferences, see [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="14565-164">Die Parameter des Cmdlets entsprechen den Eigenschaften der **System. Management. Automation. progressrecord** -Klasse.</span><span class="sxs-lookup"><span data-stu-id="14565-164">The parameters of the cmdlet correspond to the properties of the **System.Management.Automation.ProgressRecord** class.</span></span> <span data-ttu-id="14565-165">Weitere Informationen finden Sie unter [progressrecord-Klasse](/dotnet/api/system.management.automation.progressrecord).</span><span class="sxs-lookup"><span data-stu-id="14565-165">For more information, see [ProgressRecord Class](/dotnet/api/system.management.automation.progressrecord).</span></span>

## <span data-ttu-id="14565-166">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="14565-166">RELATED LINKS</span></span>

[<span data-ttu-id="14565-167">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="14565-167">Write-Debug</span></span>](Write-Debug.md)

[<span data-ttu-id="14565-168">Write-Error</span><span class="sxs-lookup"><span data-stu-id="14565-168">Write-Error</span></span>](Write-Error.md)

[<span data-ttu-id="14565-169">Write-Host</span><span class="sxs-lookup"><span data-stu-id="14565-169">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="14565-170">Write-Output</span><span class="sxs-lookup"><span data-stu-id="14565-170">Write-Output</span></span>](Write-Output.md)

[<span data-ttu-id="14565-171">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="14565-171">Write-Progress</span></span>](Write-Progress.md)

[<span data-ttu-id="14565-172">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="14565-172">Write-Verbose</span></span>](Write-Verbose.md)

[<span data-ttu-id="14565-173">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="14565-173">Write-Warning</span></span>](Write-Warning.md)
