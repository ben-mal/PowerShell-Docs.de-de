---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-eventsubscriber?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-EventSubscriber
ms.openlocfilehash: 8f36d2af0fe03685e44070a0b0db86b8a276c4ca
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216668"
---
# Get-EventSubscriber

## ZUSAMMENFASSUNG
Ruft die Ereignisabonnenten in der aktuellen Sitzung ab.

## SYNTAX

### Bysource (Standard)

```
Get-EventSubscriber [[-SourceIdentifier] <String>] [-Force] [<CommonParameters>]
```

### ById

```
Get-EventSubscriber [-SubscriptionId] <Int32> [-Force] [<CommonParameters>]
```

## DESCRIPTION

Das **Get-eventsubscriber** -Cmdlet ruft die Ereignis Abonnenten in der aktuellen Sitzung ab.

Wenn Sie ein Ereignis mithilfe eines Register Event-Cmdlets abonnieren, wird der PowerShell-Sitzung ein Ereignis Abonnent hinzugefügt, und die von Ihnen abonnierten Ereignisse werden ihrer Ereignis Warteschlange hinzugefügt, sobald sie ausgelöst werden.
Um ein Ereignisabonnement zu stornieren, löschen Sie den Ereignisabonnenten mithilfe des Unregister-Event-Cmdlets.

## BEISPIELE

### Beispiel 1: erhalten des Ereignis Abonnenten für ein Zeit Geber Ereignis

```
PS C:\> $Timer = New-Object Timers.Timer
PS C:\> $Timer | Get-Member -Type Event
PS C:\> Register-ObjectEvent -InputObject $Timer -EventName Elapsed -SourceIdentifier Timer.Elapsed
PS C:\> Get-EventSubscriber
PS C:\> $Timer = New-Object Timers.Timer
PS C:\> $Timer | Get-Member -Type Event
TypeName: System.Timers.Timer
Name     MemberType Definition
----     ---------- ----------
Disposed Event      System.EventHandler Disposed(System.Object, System.EventArgs)
Elapsed  Event      System.Timers.ElapsedEventHandler Elapsed(System.Object, System.Timers.ElapsedEventArgs) PS C:\> Register-ObjectEvent -InputObject $Timer -EventName Elapsed -SourceIdentifier Timer.Elapsed
PS C:\> Get-EventSubscriber
SubscriptionId   : 4
SourceObject     : System.Timers.Timer
EventName        : Elapsed
SourceIdentifier : Timer.Elapsed
Action           :
HandlerDelegate  :
SupportEvent     : False
ForwardEvent     : False
```

In diesem Beispiel wird ein **Get-eventsubscriber** -Befehl verwendet, um den Ereignis Abonnenten für ein Zeit Geber Ereignis zu erhalten.

Der erste Befehl verwendet das New-Object-Cmdlet, um eine Instanz eines Zeitgeberobjekts zu erstellen.
Das neue Timer-Objekt wird in der $Timer-Variablen gespeichert.

Der zweite Befehl verwendet das Get-Member-Cmdlet, um die für Zeitgeberobjekte verfügbaren Ereignisse anzuzeigen.
Der Befehl verwendet den Type-Parameter des Cmdlets " **Get-Member** " mit dem Wert "Event".

Der dritte Befehl verwendet das Register-ObjectEvent-Cmdlet, um sich für das Elapsed-Ereignis des Zeitgeberobjekts zu registrieren.

Der vierte Befehl verwendet das **Get-eventsubscriber** -Cmdlet, um den Ereignis Abonnenten für das verstrichene Ereignis zu erhalten.

### Beispiel 2: Verwenden des dynamischen Moduls in psiebziger Job in der Action-Eigenschaft des Ereignis Abonnenten

```
PS C:\> $Timer = New-Object Timers.Timer
PS C:\> $Timer.Interval = 500
PS C:\> Register-ObjectEvent -InputObject $Timer -EventName Elapsed -SourceIdentifier Timer.Random -Action { $Random = Get-Random -Min 0 -Max 100 }

Id  Name           State      HasMoreData  Location  Command
--  ----           -----      -----------  --------  -------
3   Timer.Random   NotStarted False                  $Random = Get-Random ...

PS C:\> $Timer.Enabled = $True
PS C:\> $Subscriber = Get-EventSubscriber -SourceIdentifier Timer.Random
PS C:\> ($Subscriber.action).gettype().fullname
System.Management.Automation.PSEventJob
PS C:\> $Subscriber.action | Format-List -Property *

State         : Running
Module        : __DynamicModule_6b5cbe82-d634-41d1-ae5e-ad7fe8d57fe0
StatusMessage :
HasMoreData   : True
Location      :
Command       : $random = Get-Random -Min 0 -Max 100
JobStateInfo  : Running
Finished      : System.Threading.ManualResetEvent
InstanceId    : 88944290-133d-4b44-8752-f901bd8012e2
Id            : 1
Name          : Timer.Random
ChildJobs     : {}
...

PS C:\> & $Subscriber.action.module {$Random}
96
PS C:\> & $Subscriber.action.module {$Random}
23
```

Dieses Beispiel zeigt, wie Sie das dynamische Modul im **psiebziger Job** -Objekt in der Action-Eigenschaft des Ereignis Abonnenten verwenden.

Der erste Befehl verwendet das New-Object-Cmdlet, um ein Zeitgeberobjekt zu erstellen.
Der zweite Befehl legt das Intervall des Zeitgebers auf 500 (Millisekunden) fest.

Der dritte Befehl verwendet das Register-ObjectEvent-Cmdlet, um sich für das Elapsed-Ereignis des Zeitgeberobjekts zu registrieren.
Der Befehl enthält eine Aktion zur Behandlung des Ereignisses.
Wenn das Zeitgeberintervall abläuft, wird ein Ereignis ausgelöst, und die Befehle in der Aktion werden ausgeführt.
In diesem Fall generiert das Cmdlet "Get-Random" eine Zufallszahl zwischen 0 und 100 und speichert Sie in der $Random-Variablen.
Der Quellbezeichner des Ereignisses ist Timer.Random.

Wenn Sie einen *Action* -Parameter in einem **Register-ObjectEvent-** Befehl verwenden, gibt der Befehl ein **psiebziger Job** -Objekt zurück, das die Aktion darstellt.

Der vierte Befehl aktiviert den Zeitgeber.

Der fünfte Befehl verwendet das **Get-eventsubscriber** -Cmdlet, um den Ereignis Abonnenten des Timer. Random-Ereignisses zu erhalten.
Das Ereignis Abonnenten Objekt wird in der $Subscriber Variablen gespeichert.

Der sechste Befehl zeigt, dass die Action-Eigenschaft des Ereignis Abonnenten Objekts ein **peventjob** -Objekt enthält.
Tatsächlich enthält Sie das gleiche **psiebziger Job** -Objekt, das vom **Register-ObjectEvent** -Befehl zurückgegeben wurde.

Der siebte Befehl verwendet das Cmdlet "Format-List", um alle Eigenschaften des **psiebziger Job** -Objekts in der Action-Eigenschaft in einer Liste anzuzeigen.
Das Ergebnis zeigt, dass das **psiebziger Job** -Objekt über eine Module-Eigenschaft verfügt, die ein dynamisches Skript Modul enthält, das die Aktion implementiert.

Die übrigen Befehle verwenden den Aufruf Operator (&), um den Befehl im Modul aufzurufen und den Wert der $Random Variablen anzuzeigen.
Mit dem Aufrufoperator können Sie einen beliebigen Befehl in einem Modul aufrufen, einschließlich nicht exportierter Befehle.
In diesem Fall zeigen die Befehle die Zufallszahl an, die bei Eintritt des Elapsed-Ereignisses generiert wird.

Weitere Informationen zu Modulen finden Sie unter [about_Modules](../Microsoft.PowerShell.Core/About/about_Modules.md).

## PARAMETERS

### -Force

Gibt an, dass dieses Cmdlet alle Ereignis Abonnenten abruft, einschließlich Abonnenten für Ereignisse, die mit dem *supportevent* -Parameter von Register-ObjectEvent, Register-wmievent und Register-engineevent ausgeblendet werden.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceIdentifier

Gibt den **SourceIdentifier** -Eigenschafts Wert an, der nur die Ereignis Abonnenten abruft.
Standardmäßig ruft **Get-eventsubscriber** alle Ereignis Abonnenten in der Sitzung ab.
Platzhalter sind nicht zulässig.
Bei diesem Parameter wird die Groß-/Kleinschreibung beachtet.

```yaml
Type: System.String
Parameter Sets: BySource
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SubscriptionId

Gibt den Abonnement Bezeichner an, der von diesem Cmdlet abgerufen wird.
Standardmäßig ruft **Get-eventsubscriber** alle Ereignis Abonnenten in der Sitzung ab.

```yaml
Type: System.Int32
Parameter Sets: ById
Aliases: Id

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine

Eingaben können nicht an dieses Cmdlet weitergereicht werden.

## AUSGABEN

### System. Management. Automation. psiebziger Subscriber

**Get-eventsubscriber** gibt ein Objekt zurück, das die einzelnen Ereignis Abonnenten darstellt.

## HINWEISE

* Das New-Event-Cmdlet, durch das ein benutzerdefiniertes Ereignis erstellt wird, generiert keinen Abonnenten. Das **Get-eventsubscriber** -Cmdlet findet daher kein Abonnenten Objekt für diese Ereignisse. Wenn Sie jedoch das Cmdlet "Register-EngineEvent" verwenden, um ein benutzerdefiniertes Ereignis zu abonnieren (um das Ereignis weiterzuleiten oder um eine Aktion anzugeben), findet **Get-eventsubscriber** den von **Register-engineevent** generierten Abonnenten.

  Ereignisse, Ereignisabonnements und die Ereigniswarteschlange sind nur in der aktuellen Sitzung vorhanden.
Wenn Sie die aktuelle Sitzung schließen, wird die Ereigniswarteschlange verworfen, und das Ereignisabonnement wird abgebrochen.

*

## VERWANDTE LINKS

[Get-Event](Get-Event.md)

[New-Event](New-Event.md)

[Register-EngineEvent](Register-EngineEvent.md)

[Register-ObjectEvent](Register-ObjectEvent.md)

[Remove-Event](Remove-Event.md)

[Unregister-Event](Unregister-Event.md)

[Wait-Event](Wait-Event.md)
