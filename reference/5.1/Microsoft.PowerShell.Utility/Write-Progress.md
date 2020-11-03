---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-progress?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Progress
ms.openlocfilehash: 5a0c197387f67dae1830b6d9ebd4145e96383b39
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "93224308"
---
# Write-Progress

## ZUSAMMENFASSUNG
Zeigt eine Statusanzeige in einem PowerShell-Befehlsfenster an.

## SYNTAX

```
Write-Progress [-Activity] <String> [[-Status] <String>] [[-Id] <Int32>] [-PercentComplete <Int32>]
 [-SecondsRemaining <Int32>] [-CurrentOperation <String>] [-ParentId <Int32>] [-Completed] [-SourceId <Int32>]
 [<CommonParameters>]
```

## DESCRIPTION

Das- `Write-Progress` Cmdlet zeigt eine Statusanzeige in einem PowerShell-Befehlsfenster an, das den Status eines ausgeführten Befehls oder Skripts darstellt. Sie können die dargestellten Indikatoren wählen, sowie den Text, der über und unter der Statusanzeige erscheint.

## BEISPIELE

### Beispiel 1: Anzeigen des Status einer for-Schleife

```powershell
for ($i = 1; $i -le 100; $i++ )
{
    Write-Progress -Activity "Search in Progress" -Status "$i% Complete:" -PercentComplete $i;
}
```

Dieser Befehl zeigt den Status einer For-Schleife an, die von 1 bis 100 zählt.

Das `Write-Progress` -Cmdlet umfasst eine Überschrift der Statusleiste `Activity` , eine Statuszeile und die-Variable `$i` (der-Counter in der for-Schleife), die die relative Vollständigkeit der Aufgabe angibt.

### Beispiel 2: Anzeigen des Fortschritts von schsted for-Schleifen

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

Dieses Beispiel zeigt den Status zweier geschachtelter For-Schleifen an, die jeweils durch eine Statusanzeige dargestellt werden.

Der `Write-Progress` Befehl für die zweite Statusanzeige enthält den **ID** -Parameter, der ihn von der ersten Statusanzeige unterscheidet.

Ohne den **ID** -Parameter würden die Status anzeigen einander ausgesetzt werden, anstatt nebeneinander angezeigt zu werden.

### Beispiel 3: Anzeigen des Fortschritts beim Suchen nach einer Zeichenfolge

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

Dieser Befehl zeigt den Status eines Befehls zum Suchen der Zeichenfolge „bios“ im Systemereignisprotokoll an.

Der Wert für den Wert für " **prozentucomplete** " wird berechnet, indem die Anzahl der Ereignisse, die `$I` von der Gesamtzahl der abgerufenen Ereignisse verarbeitet wurden, dividiert `$Events.count` und dann das Ergebnis mit 100 multipliziert wird.

### Beispiel 4: Anzeigen des Fortschritts für jede Ebene eines genetzten Prozesses

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

In diesem Beispiel können Sie den Parameter "Parameter" verwenden, um eine eingerückt **-** Ausgabe zum Anzeigen von Beziehungen zwischen übergeordneten und untergeordneten Elementen im Status der einzelnen Schritte zu erhalten.

## PARAMETERS

### -Aktivität

Gibt die erste Textzeile in der Überschrift über der Statusanzeige an.
Dieser Text beschreibt die Aktivität, deren Status gemeldet wird.

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

### -Abgeschlossen

Gibt an, ob die Statusanzeige sichtbar ist.
Wenn dieser Parameter ausgelassen wird, werden Status `Write-Progress` Informationen angezeigt.

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

### -CurrentOperation

Gibt die Textzeile unterhalb der Statusanzeige an.
Dieser Text beschreibt den derzeit stattfindenden Vorgang.

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

### -Id

Gibt eine ID an, die die einzelnen Statusanzeigen voneinander unterscheidet. Verwenden Sie diesen Parameter, wenn Sie in einem einzigen Befehl mehr als eine Statusanzeige erstellen. Wenn die Statusanzeigen nicht über unterschiedliche IDs verfügen, werden sie aufeinander statt in einer Reihe angezeigt.

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

### -Entid

Gibt die übergeordnete Aktivität der aktuellen Aktivität an.
Verwenden Sie den Wert -1, wenn die aktuelle Aktivität keine übergeordnete Aktivität besitzt.

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

### -Prozentuabgeschlossen

Gibt den ausgeführten Anteil der Aktivität in Prozent an.
Verwenden Sie den Wert -1, wenn der Prozentsatz unbekannt oder nicht zutreffend ist.

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

### -Secondsrestdauer

Gibt die voraussichtliche Anzahl von Sekunden an, bis die Aktivität abgeschlossen ist.
Verwenden Sie den Wert -1, wenn die Anzahl der verbleibenden Sekunden unbekannt oder nicht zutreffend ist.

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

### -SourceID

Gibt die Quelle des Datensatzes an. Sie können diese anstelle der **ID** verwenden, aber Sie können nicht mit anderen Parametern wie z. b. " **Parser** " verwendet werden.

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

### -Status

Gibt die zweite Textzeile in der Überschrift über der Statusanzeige an.
Dieser Text beschreibt den aktuellen Status der Aktivität.

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

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## EINGABEN

### Keine

Eingaben können nicht an dieses Cmdlet weitergereicht werden.

## AUSGABEN

### Keine

`Write-Progress` generiert keine Ausgabe.

## HINWEISE

Wenn die Statusanzeige nicht angezeigt wird, überprüfen Sie den Wert der `$ProgressPreference` Variablen. Wenn der Wert auf SilentlyContinue festgelegt ist, wird die Statusanzeige nicht angezeigt. Weitere Informationen zu PowerShell-Einstellungen finden Sie unter [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).

Die Parameter des Cmdlets entsprechen den Eigenschaften der **System. Management. Automation. progressrecord** -Klasse. Weitere Informationen finden Sie unter [progressrecord-Klasse](/dotnet/api/system.management.automation.progressrecord).

## VERWANDTE LINKS

[Write-Debug](Write-Debug.md)

[Schreibfehler](Write-Error.md)

[Write-Host](Write-Host.md)

[Write-Output](Write-Output.md)

[Write-Progress](Write-Progress.md)

[Write-Verbose](Write-Verbose.md)

[Write-Warning](Write-Warning.md)
