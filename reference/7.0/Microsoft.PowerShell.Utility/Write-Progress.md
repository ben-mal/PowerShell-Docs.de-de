---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-progress?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Progress
ms.openlocfilehash: 35b417b35d67e5cbe0df8719ba790135645d64e1
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "93224412"
---
# <span data-ttu-id="0cbc5-103">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="0cbc5-103">Write-Progress</span></span>

## <span data-ttu-id="0cbc5-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="0cbc5-104">SYNOPSIS</span></span>
<span data-ttu-id="0cbc5-105">Zeigt eine Statusanzeige in einem PowerShell-Befehlsfenster an.</span><span class="sxs-lookup"><span data-stu-id="0cbc5-105">Displays a progress bar within a PowerShell command window.</span></span>

## <span data-ttu-id="0cbc5-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0cbc5-106">SYNTAX</span></span>

```
Write-Progress [-Activity] <String> [[-Status] <String>] [[-Id] <Int32>] [-PercentComplete <Int32>]
 [-SecondsRemaining <Int32>] [-CurrentOperation <String>] [-ParentId <Int32>] [-Completed] [-SourceId <Int32>]
 [<CommonParameters>]
```

## <span data-ttu-id="0cbc5-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0cbc5-107">DESCRIPTION</span></span>

<span data-ttu-id="0cbc5-108">Das- `Write-Progress` Cmdlet zeigt eine Statusanzeige in einem PowerShell-Befehlsfenster an, das den Status eines ausgeführten Befehls oder Skripts darstellt.</span><span class="sxs-lookup"><span data-stu-id="0cbc5-108">The `Write-Progress` cmdlet displays a progress bar in a PowerShell command window that depicts the status of a running command or script.</span></span> <span data-ttu-id="0cbc5-109">Sie können die dargestellten Indikatoren wählen, sowie den Text, der über und unter der Statusanzeige erscheint.</span><span class="sxs-lookup"><span data-stu-id="0cbc5-109">You can select the indicators that the bar reflects and the text that appears above and below the progress bar.</span></span>

## <span data-ttu-id="0cbc5-110">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="0cbc5-110">EXAMPLES</span></span>

### <span data-ttu-id="0cbc5-111">Beispiel 1: Anzeigen des Status einer for-Schleife</span><span class="sxs-lookup"><span data-stu-id="0cbc5-111">Example 1: Display the progress of a For loop</span></span>

```powershell
for ($i = 1; $i -le 100; $i++ )
{
    Write-Progress -Activity "Search in Progress" -Status "$i% Complete:" -PercentComplete $i;
}
```

<span data-ttu-id="0cbc5-112">Dieser Befehl zeigt den Status einer For-Schleife an, die von 1 bis 100 zählt.</span><span class="sxs-lookup"><span data-stu-id="0cbc5-112">This command displays the progress of a For loop that counts from 1 to 100.</span></span>

<span data-ttu-id="0cbc5-113">Das `Write-Progress` -Cmdlet umfasst eine Überschrift der Statusleiste `Activity` , eine Statuszeile und die-Variable `$i` (der-Counter in der for-Schleife), die die relative Vollständigkeit der Aufgabe angibt.</span><span class="sxs-lookup"><span data-stu-id="0cbc5-113">The `Write-Progress` cmdlet includes a status bar heading `Activity`, a status line, and the variable `$i` (the counter in the For loop), which indicates the relative completeness of the task.</span></span>

### <span data-ttu-id="0cbc5-114">Beispiel 2: Anzeigen des Fortschritts von schsted for-Schleifen</span><span class="sxs-lookup"><span data-stu-id="0cbc5-114">Example 2: Display the progress of nested For loops</span></span>

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

<span data-ttu-id="0cbc5-115">Dieses Beispiel zeigt den Status zweier geschachtelter For-Schleifen an, die jeweils durch eine Statusanzeige dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="0cbc5-115">This example displays the progress of two nested For loops, each of which is represented by a progress bar.</span></span>

<span data-ttu-id="0cbc5-116">Der `Write-Progress` Befehl für die zweite Statusanzeige enthält den **ID** -Parameter, der ihn von der ersten Statusanzeige unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="0cbc5-116">The `Write-Progress` command for the second progress bar includes the **Id** parameter that distinguishes it from the first progress bar.</span></span>

<span data-ttu-id="0cbc5-117">Ohne den **ID** -Parameter würden die Status anzeigen einander ausgesetzt werden, anstatt nebeneinander angezeigt zu werden.</span><span class="sxs-lookup"><span data-stu-id="0cbc5-117">Without the **Id** parameter, the progress bars would be superimposed on each other instead of being displayed one below the other.</span></span>

### <span data-ttu-id="0cbc5-118">Beispiel 3: Anzeigen des Fortschritts beim Suchen nach einer Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0cbc5-118">Example 3: Display the progress while searching for a string</span></span>

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

<span data-ttu-id="0cbc5-119">Dieser Befehl zeigt den Status eines Befehls zum Suchen der Zeichenfolge „bios“ im Systemereignisprotokoll an.</span><span class="sxs-lookup"><span data-stu-id="0cbc5-119">This command displays the progress of a command to find the string "bios" in the System event log.</span></span>

<span data-ttu-id="0cbc5-120">Der Wert für den Wert für " **prozentucomplete** " wird berechnet, indem die Anzahl der Ereignisse, die `$I` von der Gesamtzahl der abgerufenen Ereignisse verarbeitet wurden, dividiert `$Events.count` und dann das Ergebnis mit 100 multipliziert wird.</span><span class="sxs-lookup"><span data-stu-id="0cbc5-120">The **PercentComplete** parameter value is calculated by dividing the number of events that have been processed `$I` by the total number of events retrieved `$Events.count` and then multiplying that result by 100.</span></span>

### <span data-ttu-id="0cbc5-121">Beispiel 4: Anzeigen des Fortschritts für jede Ebene eines genetzten Prozesses</span><span class="sxs-lookup"><span data-stu-id="0cbc5-121">Example 4: Display progress for each level of a nested process</span></span>

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

<span data-ttu-id="0cbc5-122">In diesem Beispiel können Sie den Parameter "Parameter" verwenden, um eine eingerückt **-** Ausgabe zum Anzeigen von Beziehungen zwischen übergeordneten und untergeordneten Elementen im Status der einzelnen Schritte zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="0cbc5-122">In this example you can use the **ParentId** parameter to have indented output to show parent/child relationships in the progress of each step.</span></span>

## <span data-ttu-id="0cbc5-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0cbc5-123">PARAMETERS</span></span>

### <span data-ttu-id="0cbc5-124">-Aktivität</span><span class="sxs-lookup"><span data-stu-id="0cbc5-124">-Activity</span></span>

<span data-ttu-id="0cbc5-125">Gibt die erste Textzeile in der Überschrift über der Statusanzeige an.</span><span class="sxs-lookup"><span data-stu-id="0cbc5-125">Specifies the first line of text in the heading above the status bar.</span></span>
<span data-ttu-id="0cbc5-126">Dieser Text beschreibt die Aktivität, deren Status gemeldet wird.</span><span class="sxs-lookup"><span data-stu-id="0cbc5-126">This text describes the activity whose progress is being reported.</span></span>

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

### <span data-ttu-id="0cbc5-127">-Abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="0cbc5-127">-Completed</span></span>

<span data-ttu-id="0cbc5-128">Gibt an, ob die Statusanzeige sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="0cbc5-128">Indicates whether the progress bar is visible.</span></span>
<span data-ttu-id="0cbc5-129">Wenn dieser Parameter ausgelassen wird, werden Status `Write-Progress` Informationen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0cbc5-129">If this parameter is omitted, `Write-Progress` displays progress information.</span></span>

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

### <span data-ttu-id="0cbc5-130">-CurrentOperation</span><span class="sxs-lookup"><span data-stu-id="0cbc5-130">-CurrentOperation</span></span>

<span data-ttu-id="0cbc5-131">Gibt die Textzeile unterhalb der Statusanzeige an.</span><span class="sxs-lookup"><span data-stu-id="0cbc5-131">Specifies the line of text below the progress bar.</span></span>
<span data-ttu-id="0cbc5-132">Dieser Text beschreibt den derzeit stattfindenden Vorgang.</span><span class="sxs-lookup"><span data-stu-id="0cbc5-132">This text describes the operation that is currently taking place.</span></span>

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

### <span data-ttu-id="0cbc5-133">-Id</span><span class="sxs-lookup"><span data-stu-id="0cbc5-133">-Id</span></span>

<span data-ttu-id="0cbc5-134">Gibt eine ID an, die die einzelnen Statusanzeigen voneinander unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="0cbc5-134">Specifies an ID that distinguishes each progress bar from the others.</span></span> <span data-ttu-id="0cbc5-135">Verwenden Sie diesen Parameter, wenn Sie in einem einzigen Befehl mehr als eine Statusanzeige erstellen.</span><span class="sxs-lookup"><span data-stu-id="0cbc5-135">Use this parameter when you are creating more than one progress bar in a single command.</span></span> <span data-ttu-id="0cbc5-136">Wenn die Statusanzeigen nicht über unterschiedliche IDs verfügen, werden sie aufeinander statt in einer Reihe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0cbc5-136">If the progress bars do not have different IDs, they are superimposed instead of being displayed in a series.</span></span>

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

### <span data-ttu-id="0cbc5-137">-Entid</span><span class="sxs-lookup"><span data-stu-id="0cbc5-137">-ParentId</span></span>

<span data-ttu-id="0cbc5-138">Gibt die übergeordnete Aktivität der aktuellen Aktivität an.</span><span class="sxs-lookup"><span data-stu-id="0cbc5-138">Specifies the parent activity of the current activity.</span></span>
<span data-ttu-id="0cbc5-139">Verwenden Sie den Wert -1, wenn die aktuelle Aktivität keine übergeordnete Aktivität besitzt.</span><span class="sxs-lookup"><span data-stu-id="0cbc5-139">Use the value -1 if the current activity has no parent activity.</span></span>

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

### <span data-ttu-id="0cbc5-140">-Prozentuabgeschlossen</span><span class="sxs-lookup"><span data-stu-id="0cbc5-140">-PercentComplete</span></span>

<span data-ttu-id="0cbc5-141">Gibt den ausgeführten Anteil der Aktivität in Prozent an.</span><span class="sxs-lookup"><span data-stu-id="0cbc5-141">Specifies the percentage of the activity that is completed.</span></span>
<span data-ttu-id="0cbc5-142">Verwenden Sie den Wert -1, wenn der Prozentsatz unbekannt oder nicht zutreffend ist.</span><span class="sxs-lookup"><span data-stu-id="0cbc5-142">Use the value -1 if the percentage complete is unknown or not applicable.</span></span>

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

### <span data-ttu-id="0cbc5-143">-Secondsrestdauer</span><span class="sxs-lookup"><span data-stu-id="0cbc5-143">-SecondsRemaining</span></span>

<span data-ttu-id="0cbc5-144">Gibt die voraussichtliche Anzahl von Sekunden an, bis die Aktivität abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="0cbc5-144">Specifies the projected number of seconds remaining until the activity is completed.</span></span>
<span data-ttu-id="0cbc5-145">Verwenden Sie den Wert -1, wenn die Anzahl der verbleibenden Sekunden unbekannt oder nicht zutreffend ist.</span><span class="sxs-lookup"><span data-stu-id="0cbc5-145">Use the value -1 if the number of seconds remaining is unknown or not applicable.</span></span>

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

### <span data-ttu-id="0cbc5-146">-SourceID</span><span class="sxs-lookup"><span data-stu-id="0cbc5-146">-SourceId</span></span>

<span data-ttu-id="0cbc5-147">Gibt die Quelle des Datensatzes an.</span><span class="sxs-lookup"><span data-stu-id="0cbc5-147">Specifies the source of the record.</span></span> <span data-ttu-id="0cbc5-148">Sie können diese anstelle der **ID** verwenden, aber Sie können nicht mit anderen Parametern wie z. b. " **Parser** " verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0cbc5-148">You can use this in place of **Id** but cannot be used with other parameters like **ParentId** .</span></span>

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

### <span data-ttu-id="0cbc5-149">-Status</span><span class="sxs-lookup"><span data-stu-id="0cbc5-149">-Status</span></span>

<span data-ttu-id="0cbc5-150">Gibt die zweite Textzeile in der Überschrift über der Statusanzeige an.</span><span class="sxs-lookup"><span data-stu-id="0cbc5-150">Specifies the second line of text in the heading above the status bar.</span></span>
<span data-ttu-id="0cbc5-151">Dieser Text beschreibt den aktuellen Status der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="0cbc5-151">This text describes current state of the activity.</span></span>

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

### <span data-ttu-id="0cbc5-152">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0cbc5-152">CommonParameters</span></span>

<span data-ttu-id="0cbc5-153">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0cbc5-153">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0cbc5-154">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="0cbc5-154">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="0cbc5-155">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="0cbc5-155">INPUTS</span></span>

### <span data-ttu-id="0cbc5-156">Keine</span><span class="sxs-lookup"><span data-stu-id="0cbc5-156">None</span></span>

<span data-ttu-id="0cbc5-157">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="0cbc5-157">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="0cbc5-158">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="0cbc5-158">OUTPUTS</span></span>

### <span data-ttu-id="0cbc5-159">Keine</span><span class="sxs-lookup"><span data-stu-id="0cbc5-159">None</span></span>

<span data-ttu-id="0cbc5-160">`Write-Progress` generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="0cbc5-160">`Write-Progress` does not generate any output.</span></span>

## <span data-ttu-id="0cbc5-161">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="0cbc5-161">NOTES</span></span>

<span data-ttu-id="0cbc5-162">Wenn die Statusanzeige nicht angezeigt wird, überprüfen Sie den Wert der `$ProgressPreference` Variablen.</span><span class="sxs-lookup"><span data-stu-id="0cbc5-162">If the progress bar does not appear, check the value of the `$ProgressPreference` variable.</span></span> <span data-ttu-id="0cbc5-163">Wenn der Wert auf SilentlyContinue festgelegt ist, wird die Statusanzeige nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0cbc5-163">If the value is set to SilentlyContinue, the progress bar is not displayed.</span></span> <span data-ttu-id="0cbc5-164">Weitere Informationen zu PowerShell-Einstellungen finden Sie unter [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="0cbc5-164">For more information about PowerShell preferences, see [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="0cbc5-165">Die Parameter des Cmdlets entsprechen den Eigenschaften der **System. Management. Automation. progressrecord** -Klasse.</span><span class="sxs-lookup"><span data-stu-id="0cbc5-165">The parameters of the cmdlet correspond to the properties of the **System.Management.Automation.ProgressRecord** class.</span></span> <span data-ttu-id="0cbc5-166">Weitere Informationen finden Sie unter [progressrecord-Klasse](/dotnet/api/system.management.automation.progressrecord).</span><span class="sxs-lookup"><span data-stu-id="0cbc5-166">For more information, see [ProgressRecord Class](/dotnet/api/system.management.automation.progressrecord).</span></span>

## <span data-ttu-id="0cbc5-167">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="0cbc5-167">RELATED LINKS</span></span>

[<span data-ttu-id="0cbc5-168">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="0cbc5-168">Write-Debug</span></span>](Write-Debug.md)

[<span data-ttu-id="0cbc5-169">Schreibfehler</span><span class="sxs-lookup"><span data-stu-id="0cbc5-169">Write-Error</span></span>](Write-Error.md)

[<span data-ttu-id="0cbc5-170">Write-Host</span><span class="sxs-lookup"><span data-stu-id="0cbc5-170">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="0cbc5-171">Write-Output</span><span class="sxs-lookup"><span data-stu-id="0cbc5-171">Write-Output</span></span>](Write-Output.md)

[<span data-ttu-id="0cbc5-172">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="0cbc5-172">Write-Progress</span></span>](Write-Progress.md)

[<span data-ttu-id="0cbc5-173">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="0cbc5-173">Write-Verbose</span></span>](Write-Verbose.md)

[<span data-ttu-id="0cbc5-174">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="0cbc5-174">Write-Warning</span></span>](Write-Warning.md)
