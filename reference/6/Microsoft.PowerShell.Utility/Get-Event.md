---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-event?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Event
ms.openlocfilehash: 9a66c7ce0d892b7702aab74fc278b20e59d06a98
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2020
ms.locfileid: "94343452"
---
# Get-Event

## ZUSAMMENFASSUNG
Ruft die Ereignisse in der Ereigniswarteschlange ab.

## SYNTAX

### Bysource (Standard)

```
Get-Event [[-SourceIdentifier] <String>] [<CommonParameters>]
```

### ById

```
Get-Event [-EventIdentifier] <Int32> [<CommonParameters>]
```

## DESCRIPTION

Das- `Get-Event` Cmdlet ruft Ereignisse in der PowerShell-Ereignis Warteschlange für die aktuelle Sitzung ab. Sie können alle Ereignisse oder den **eventidentifier** -oder **SourceIdentifier** -Parameter verwenden, um die Ereignisse anzugeben.

Wenn ein Ereignis auftritt, wird es zur Ereigniswarteschlange hinzugefügt. Die Ereignis Warteschlange enthält Ereignisse, für die Sie sich registriert haben, Ereignisse, die mithilfe des `New-Event` Cmdlets erstellt wurden, und das Ereignis, das ausgelöst wird, wenn PowerShell beendet wird. Sie können `Get-Event` oder verwenden `Wait-Event` , um die Ereignisse zu erhalten.

Dieses Cmdlet ruft keine Ereignisse aus den Protokollen der Ereignisanzeige ab. Um diese Ereignisse zu erhalten, verwenden Sie `Get-WinEvent` oder `Get-EventLog` .

## BEISPIELE

### Beispiel 1: alle Ereignisse erhalten

```
PS C:\> Get-Event
```

Mit diesem Befehl werden alle Ereignisse in der Ereigniswarteschlange abgerufen.

### Beispiel 2: Ereignisse nach Quell Bezeichner

```
PS C:\> Get-Event -SourceIdentifier "PowerShell.ProcessCreated"
```

Dieser Befehl ruft Ereignisse ab, in denen der Wert der SourceIdentifier-Eigenschaft "PowerShell. processcreated" ist.

### Beispiel 3: erhalten eines Ereignisses basierend auf dem Zeitpunkt, an dem es generiert wurde

```
PS C:\> $Events = Get-Event
PS C:\> $Events[0] | Format-List -Property *
ComputerName     :
RunspaceId       : c2153740-256d-46c0-a57c-b805917d1b7b
EventIdentifier  : 1
Sender           : System.Management.ManagementEventWatcher
SourceEventArgs  : System.Management.EventArrivedEventArgs
SourceArgs       : {System.Management.ManagementEventWatcher, System.Management.EventArrivedEventArgs}
SourceIdentifier : ProcessStarted
TimeGenerated    : 11/13/2008 12:09:32 PM
MessageData      : PS C:\> Get-Event | Where {$_.TimeGenerated -ge "11/13/2008 12:15:00 PM"}
ComputerName     :
RunspaceId       : c2153740-256d-46c0-a57c-b8059325d1a0
EventIdentifier  : 1
Sender           : System.Management.ManagementEventWatcher
SourceEventArgs  : System.Management.EventArrivedEventArgs
SourceArgs       : {System.Management.ManagementEventWatcher, System.Management.EventArrivedEventArgs}
SourceIdentifier : ProcessStarted
TimeGenerated    : 11/13/2008 12:15:00 PM
MessageData      :
```

Dieses Beispiel zeigt, wie Ereignisse mithilfe anderer Eigenschaften als „SourceIdentifier“ abgerufen werden.

Der erste Befehl ruft alle Ereignisse in der Ereignis Warteschlange ab und speichert Sie in der `$Events` Variablen.

Der zweite Befehl verwendet die Array Notation, um das erste Ereignis (0-Index) im Array in der `$Events` Variablen zu erhalten. Der Befehl verwendet einen Pipeline Operator ( `|` ), um das Ereignis an den `Format-List` Befehl zu senden, der alle Eigenschaften des Ereignisses in einer Liste anzeigt. Dadurch können Sie die Eigenschaften des Ereignisobjekts überprüfen.

Der dritte Befehl zeigt, wie das `Where-Object` Cmdlet verwendet wird, um ein Ereignis basierend auf dem Zeitpunkt, an dem es generiert wurde, zu erhalten.

### Beispiel 4: erhalten eines Ereignisses anhand seines Bezeichners

```
PS C:\> Get-Event -EventIdentifier 2
```

Dieser Befehl ruft das Ereignis mit der Ereignis-ID 2 ab.

## PARAMETERS

### -Eventidentifier

Gibt die Ereignis Bezeichner an, für die dieses Cmdlet Ereignisse abruft.

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

### -SourceIdentifier

Gibt Quell Bezeichner an, für die dieses Cmdlet Ereignisse abruft. Standardmäßig werden alle Ereignisse in der Ereigniswarteschlange abgerufen. Platzhalter sind nicht zulässig.

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

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine

Eingaben können nicht an dieses Cmdlet weitergereicht werden.

## AUSGABEN

### System. Management. Automation. psiebziger args

`Get-Event` Gibt ein **peventargs** -Objekt für jedes Ereignis zurück. Um eine Beschreibung dieses Objekts anzuzeigen, geben Sie ein, `Get-Help Get-Event -Full` und lesen Sie den Abschnitt "Hinweise" des Hilfe Themas.

## HINWEISE

Auf den Linux-oder macOS-Plattformen sind keine Ereignis Quellen verfügbar.

Ereignisse, Ereignisabonnements und die Ereigniswarteschlange sind nur in der aktuellen Sitzung vorhanden. Wenn Sie die aktuelle Sitzung schließen, wird die Ereigniswarteschlange verworfen, und das Ereignisabonnement wird abgebrochen.

Das- `Get-Event` Cmdlet gibt ein **psiebziger args** -Objekt ( **System. Management. Automation. psiebargs** ) mit den folgenden Eigenschaften zurück:

- Computername. Der Name des Computers, auf dem das Ereignis aufgetreten ist. Dieser Eigenschaftswert wird nur aufgefüllt, wenn das Ereignis von einem Remotecomputer weitergeleitet wird.

- Runspaceid. Eine GUID, die die Sitzung, in der das Ereignis aufgetreten ist, eindeutig identifiziert. Dieser Eigenschaftswert wird nur aufgefüllt, wenn das Ereignis von einem Remotecomputer weitergeleitet wird.

- EventIdentifier. Eine ganze Zahl (Int32), die die Ereignisbenachrichtigung in der aktuellen Sitzung eindeutig identifiziert.

- Sen. Das Objekt, das das Ereignis generiert hat. Im Wert des **Action** -Parameters enthält die `$Sender` Automatische Variable das Sender-Objekt.

- SourceEventArgs. Der erste Parameter, der von EventArgs abgeleitet wird, falls vorhanden. Beispielsweise enthält die **sourceeventargs** -Eigenschaft in einem Ereignis mit Timer-verstrichenen Ereignissen, bei dem die Signatur das Formular Objekt Absender, **Timer. ElapsedEventArgs** e, die Eigenschaft " **Timers. ElapsedEventArgs** ". Im Wert des **Action** -Parameters enthält die `$EventArgs` Automatische Variable diesen Wert.

- Sourceargs. Alle Parameter der ursprünglichen Ereignissignatur. Für eine Standard Ereignis Signatur `$Args[0]` stellt den Absender dar und `$Args[1]` stellt die **sourceeventargs** dar. Im Wert des **Action** -Parameters enthält die `$Args` Automatische Variable diesen Wert.

- SourceIdentifier. Eine Zeichenfolge, die das Ereignisabonnement bezeichnet. Im Wert des **Action** -Parameters enthält die **SourceIdentifier** -Eigenschaft der `$Event` automatischen Variablen diesen Wert.

- TimeGenerated. Ein **DateTime** -Objekt, das die Uhrzeit darstellt, zu der das Ereignis generiert wurde.
  Im Wert des **Action** -Parameters enthält die **TimeGenerated** -Eigenschaft der `$Event` automatischen Variablen diesen Wert.

- MessageData. Die dem Ereignisabonnement zugeordneten Daten. Benutzer geben diese Daten an, wenn sie ein Ereignis registrieren. Im Wert des **Action** -Parameters enthält die **messageData** -Eigenschaft der `$Event` automatischen Variablen diesen Wert.

## VERWANDTE LINKS

[New-Event](New-Event.md)

[Register-EngineEvent](Register-EngineEvent.md)

[Register-ObjectEvent](Register-ObjectEvent.md)

[Remove-Event](Remove-Event.md)

[Unregister-Event](Unregister-Event.md)

[Wait-Event](Wait-Event.md)
