---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-event?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Event
ms.openlocfilehash: ce14e6038473e6c53b62b310c288e23f6a7597e2
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217391"
---
# New-Event

## ZUSAMMENFASSUNG
Erstellt ein neues Ereignis.

## SYNTAX

```
New-Event [-SourceIdentifier] <String> [[-Sender] <PSObject>] [[-EventArguments] <PSObject[]>]
 [[-MessageData] <PSObject>] [<CommonParameters>]
```

## DESCRIPTION

Das **New-Event-** Cmdlet erstellt ein neues benutzerdefiniertes Ereignis.

Mit benutzerdefinierten Ereignissen können Sie die Benutzer über Statusänderungen in Ihrem Programm und jede Änderung benachrichtigen, die das Programm erkennen kann, einschließlich Hardware- oder Systembedingungen, Anwendungsstatus, Datenträgerstatus, Netzwerkstatus oder den Abschluss eines Auftrags im Hintergrund.

Benutzerdefinierte Ereignisse werden bei ihrer Auslösung automatisch der Warteschlange in der Sitzung hinzugefügt. Es ist kein Abonnement erforderlich.
Wenn Sie ein Ereignis jedoch an die lokale Sitzung weiterleiten oder eine Aktion zur Reaktion auf das Ereignis angeben möchten, verwenden Sie das Register-EngineEvent-Cmdlet, um das benutzerdefinierte Ereignis zu abonnieren.

Wenn Sie ein benutzerdefiniertes Ereignis abonnieren, wird der Ereignisabonnent Ihrer Sitzung hinzugefügt.
Wenn Sie das Ereignisabonnement mithilfe des Unregister-Event-Cmdlets stornieren, werden der Ereignisabonnent und das benutzerdefinierte Ereignis aus der Sitzung gelöscht.
Wenn Sie das benutzerdefinierte Ereignis nicht abonnieren, müssen Sie zum Löschen des Ereignisses die Programmbedingungen ändern oder die PowerShell-Sitzung schließen.

## BEISPIELE

### Beispiel 1: Erstellen eines neuen Ereignisses in der Ereignis Warteschlange

```
PS C:\> New-Event -SourceIdentifier Timer -Sender windows.timer -MessageData "Test"
```

Dieser Befehl erstellt ein neues Ereignis in der PowerShell-Ereignis Warteschlange.
Er verwendet ein **Windows. Timer** -Objekt, um das Ereignis zu senden.

### Beispiel 2: Ausführen eines Ereignisses als Reaktion auf ein anderes Ereignis

```
PS C:\> function Enable-ProcessCreationEvent
{
   $Query = New-Object System.Management.WqlEventQuery "__InstanceCreationEvent", (New-Object TimeSpan 0,0,1), "TargetInstance isa 'Win32_Process'"
   $ProcessWatcher = New-Object System.Management.ManagementEventWatcher $Query
   $Identifier = "WMI.ProcessCreated"
   Register-ObjectEvent $ProcessWatcher "EventArrived" -SupportEvent $Identifier -Action
   {
      [void] (New-Event -SourceID "PowerShell.ProcessCreated" -Sender $Args[0] -EventArguments $Args[1].SourceEventArgs.NewEvent.TargetInstance)
   }
}
```

Diese Beispiel Funktion verwendet das **New-Event-** Cmdlet, um ein Ereignis als Reaktion auf ein anderes Ereignis aufzurichten.
Der Befehl verwendet das Register-ObjectEvent-Cmdlet zum Abonnieren des Ereignisses der Windows-Verwaltungsinstrumentation (WMI), das beim Erstellen eines neuen Prozesses ausgelöst wird.
Der Befehl verwendet den *Action* -Parameter des Cmdlets, um das **New-Event-** Cmdlet aufzurufen, das das neue Ereignis erstellt.

Da die von **New-Event ausgelösten** Ereignisse der PowerShell-Ereignis Warteschlange automatisch hinzugefügt werden, müssen Sie sich für dieses Ereignis nicht registrieren.

## PARAMETERS

### -Eventarguments

Gibt ein Objekt an, das Optionen für das Ereignis enthält.

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MessageData

Gibt zusätzliche Daten an, die dem Ereignis zugeordnet sind.
Der Wert dieses Parameters wird in der **MessageData** -Eigenschaft des Ereignisobjekts angezeigt.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Absender

Gibt das Objekt an, das das Ereignis auslöst.
Der Standardwert ist das PowerShell-Modul.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceIdentifier

Gibt einen Namen für das neue Ereignis an.
Dieser Parameter ist erforderlich und muss in der Sitzung eindeutig sein.

Der Wert dieses Parameters wird in der **SourceIdentifier** -Eigenschaft der Ereignisse angezeigt.

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

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine

Eingaben können nicht an dieses Cmdlet weitergereicht werden.

## AUSGABEN

### System. Management. Automation. psiebziger args

## HINWEISE

Das neue benutzerdefinierte Ereignis, das Ereignisabonnement und die Ereigniswarteschlange sind nur in der aktuellen Sitzung vorhanden. Wenn Sie die aktuelle Sitzung schließen, wird die Ereigniswarteschlange verworfen, und das Ereignisabonnement wird abgebrochen.

## VERWANDTE LINKS

[Get-Event](Get-Event.md)

[Register-EngineEvent](Register-EngineEvent.md)

[Register-ObjectEvent](Register-ObjectEvent.md)

[Remove-Event](Remove-Event.md)

[Unregister-Event](Unregister-Event.md)

[Wait-Event](Wait-Event.md)

