---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/wait-event?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Wait-Event
ms.openlocfilehash: ee613dd78cbb30dce37c07297411c2d8bf9d832d
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214727"
---
# Wait-Event

## ZUSAMMENFASSUNG
Wartet, bis ein bestimmtes Ereignis ausgelöst wird, bevor die Ausführung fortgesetzt wird.

## SYNTAX

```
Wait-Event [[-SourceIdentifier] <String>] [-Timeout <Int32>] [<CommonParameters>]
```

## DESCRIPTION

Das `Wait-Event` Cmdlet hält die Ausführung eines Skripts oder einer Funktion an, bis ein bestimmtes Ereignis ausgelöst wird. Die Ausführung wird fortgesetzt, wenn das Ereignis erkannt wird. Drücken Sie <kbd>STRG</kbd>C, um den warte Vorgang abzubrechen + <kbd>C</kbd>.

Diese Funktion bietet eine Alternative zum Abruf für ein Ereignis. Außerdem können Sie die Reaktion auf ein Ereignis auf zwei verschiedene Arten bestimmen:

- Verwenden des **Action** -Parameters des Ereignis Abonnements
- warten auf Rückgabe eines Ereignisses und anschließendes reagieren mit einer Aktion

## BEISPIELE

### Beispiel 1: warten auf das nächste Ereignis

In diesem Beispiel wird auf das nächste Ereignis gewartet, das ausgelöst wird.

```powershell
Wait-Event
```

### Beispiel 2: warten auf ein Ereignis mit einem angegebenen Quell Bezeichner

In diesem Beispiel wird auf das nächste Ereignis gewartet, das ausgelöst wird und das den Quell Bezeichner "processstarted" aufweist.

```powershell
Wait-Event -SourceIdentifier "ProcessStarted"
```

### Beispiel 3: warten auf ein abgelaufener Timer-Ereignis

In diesem Beispiel wird das- `Wait-Event` Cmdlet verwendet, um auf ein Zeit Geber Ereignis auf einem Timer zu warten, der für 2000 Millisekunden festgelegt ist.

```powershell
$Timer = New-Object Timers.Timer
$objectEventArgs = @{
    InputObject = $Timer
    EventName = 'Elapsed'
    SourceIdentifier = 'Timer.Elapsed'
}
Register-ObjectEvent @objectEventArgs
$Timer.Interval = 2000
$Timer.Autoreset = $False
$Timer.Enabled = $True
Wait-Event Timer.Elapsed
```

```Output
ComputerName     :
RunspaceId       : bb560b14-ff43-48d4-b801-5adc31bbc6fb
EventIdentifier  : 1
Sender           : System.Timers.Timer
SourceEventArgs  : System.Timers.ElapsedEventArgs
SourceArgs       : {System.Timers.Timer, System.Timers.ElapsedEventArgs}
SourceIdentifier : Timer.Elapsed
TimeGenerated    : 4/23/2020 2:30:37 PM
MessageData      :
```

### Beispiel 4: warten auf ein Ereignis nach einem angegebenen Timeout

In diesem Beispiel werden bis zu 90 Sekunden auf das nächste Ereignis gewartet, das ausgelöst wird und das den Quell Bezeichner " **processstarted** " aufweist. Wenn die angegebene Zeit abgelaufen ist, wird der Wartevorgang beendet.

```powershell
Wait-Event -SourceIdentifier "ProcessStarted" -Timeout 90
```

## PARAMETERS

### -SourceIdentifier

Gibt den Quell Bezeichner an, den dieses Cmdlet auf Ereignisse wartet.
Standardmäßig `Wait-Event` wartet auf ein beliebiges Ereignis.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Timeout

Gibt die maximale Zeit in Sekunden an, die `Wait-Event` auf das Eintreten des Ereignisses wartet. Der Standardwert -1 wartet unbegrenzt. Die zeitliche Steuerung beginnt, wenn Sie den Befehl übermitteln `Wait-Event` .

Wenn die angegebene Zeit überschritten ist, wird der Wartevorgang beendet und die Befehlseingabeaufforderung wieder angezeigt, auch wenn das Ereignis nicht ausgelöst wurde. Es wird keine Fehlermeldung angezeigt.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: TimeoutSec

Required: False
Position: Named
Default value: -1
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System.String

## AUSGABEN

### System. Management. Automation. psiebziger args

## HINWEISE

Ereignisse, Ereignisabonnements und die Ereigniswarteschlange sind nur in der aktuellen Sitzung vorhanden. Wenn Sie die aktuelle Sitzung schließen, wird die Ereigniswarteschlange verworfen, und das Ereignisabonnement wird abgebrochen.

## VERWANDTE LINKS

[Get-Event](Get-Event.md)

[Get-EventSubscriber](Get-EventSubscriber.md)

[New-Event](New-Event.md)

[Register-EngineEvent](Register-EngineEvent.md)

[Register-ObjectEvent](Register-ObjectEvent.md)

[Remove-Event](Remove-Event.md)

[Unregister-Event](Unregister-Event.md)

[Wait-Event](Wait-Event.md)

