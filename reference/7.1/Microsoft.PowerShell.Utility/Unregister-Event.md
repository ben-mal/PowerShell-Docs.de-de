---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/unregister-event?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-Event
ms.openlocfilehash: 748ef22203f59090be6f5491ea76b50d54930a95
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217564"
---
# Unregister-Event

## ZUSAMMENFASSUNG
Storniert ein Ereignisabonnement.

## SYNTAX

### Bysource (Standard)

```
Unregister-Event [-SourceIdentifier] <String> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ById

```
Unregister-Event [-SubscriptionId] <Int32> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Das **Unregister-Event-** Cmdlet bricht ein Ereignis Abonnement ab, das mit dem Cmdlet Register-engineevent, Register-ObjectEvent oder Register-WmiEvent erstellt wurde.

Wenn ein Ereignisabonnement gekündigt wird, wird der Ereignisabonnent aus der Sitzung gelöscht und die abonnierten Ereignisse werden nicht mehr der Ereigniswarteschlange hinzugefügt.
Wenn Sie ein Abonnement für ein Ereignis kündigen, das mithilfe des New-Event-Cmdlets erstellt wurde, wird das neue Ereignis auch aus der Sitzung gelöscht.

**Unregister-Event** löscht keine Ereignisse aus der Ereignis Warteschlange.
Um Ereignisse zu löschen, verwenden Sie das Remove-Event-Cmdlet.

## BEISPIELE

### Beispiel 1: Abbrechen eines Ereignis Abonnements nach Quell Bezeichner

```
PS C:\> Unregister-Event -SourceIdentifier "ProcessStarted"
```

Mit diesem Befehl wird das Ereignis Abonnement abgebrochen, das den Quell Bezeichner "processstarted" aufweist.

Um den Quellenbezeichner eines Ereignisses zu finden, verwenden Sie das Get-Event-Cmdlet.
Verwenden Sie das **Get-eventsubscriber** -Cmdlet, um den Quell Bezeichner eines Ereignis Abonnements zu ermitteln.

### Beispiel 2: Abbrechen eines Ereignis Abonnements nach Abonnement Bezeichner

```
PS C:\> Unregister-Event -SubscriptionId 2
```

Mit diesem Befehl wird das Ereignisabonnement gekündigt, das den Abonnementbezeichner „2“ aufweist.

Verwenden Sie das **Get-eventsubscriber** -Cmdlet, um den Abonnement Bezeichner eines Ereignis Abonnements zu ermitteln.

### Beispiel 3: Abbrechen aller Ereignis Abonnements

```
PS C:\> Get-EventSubscriber -Force | Unregister-Event -Force
```

Mit diesem Befehl werden alle Ereignisabonnements in der Sitzung gekündigt.

Der Befehl verwendet das **Get-eventsubscriber** -Cmdlet, um alle Ereignis Abonnenten Objekte in der Sitzung zu erhalten, einschließlich der Abonnenten, die mit dem *supportevent* -Parameter der Cmdlets für die Ereignis Registrierung ausgeblendet sind.

Er verwendet einen Pipeline Operator (|), um die Abonnenten Objekte an **Unregister-Event** zu senden, das Sie aus der Sitzung löscht.
Um die Aufgabe abzuschließen, ist der *Force* -Parameter auch für **Unregister-Event** erforderlich.

## PARAMETERS

### -Force
Bricht alle Ereignis Abonnements ab, einschließlich Abonnements, die mit dem *supportevent* -Parameter von **Register-ObjectEvent** , **Register-wmievent** und **Register-engineevent** ausgeblendet wurden.

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

### -SourceIdentifier
Gibt einen Quell Bezeichner an, mit dem dieses Cmdlet Ereignis Abonnements abbricht.

Ein *SourceIdentifier* -oder *Abonnement-ID* -Parameter muss in jedem Befehl enthalten sein.

```yaml
Type: System.String
Parameter Sets: BySource
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SubscriptionId
Gibt eine quellbezeichnerkennung an, mit der dieses Cmdlet Ereignis Abonnements abbricht.

Ein *SourceIdentifier* -oder *Abonnement-ID* -Parameter muss in jedem Befehl enthalten sein.

```yaml
Type: System.Int32
Parameter Sets: ById
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.

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

### -WhatIf
Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.
Das Cmdlet wird nicht ausgeführt.

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

### CommonParameters
Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System. Management. Automation. psiebziger Subscriber
Sie können die Ausgabe von Get-EventSubscriber an **Unregister-Event** übergeben.

## AUSGABEN

### Keine
Dieses Cmdlet gibt keine Ausgabe zurück.

## HINWEISE

* Ereignisse, Ereignisabonnements und die Ereigniswarteschlange sind nur in der aktuellen Sitzung vorhanden. Wenn Sie die aktuelle Sitzung schließen, wird die Ereigniswarteschlange verworfen, und das Ereignisabonnement wird abgebrochen.

  **Unregister-Event** kann Ereignisse nicht löschen, die mit dem Cmdlet "New-Event" erstellt wurden, es sei denn, Sie haben das Ereignis mithilfe des **Register-engineevent** -Cmdlets abonniert.
Um ein benutzerdefiniertes Ereignis aus der Sitzung zu löschen, müssen Sie es programmgesteuert entfernen oder die Sitzung schließen.

*

## VERWANDTE LINKS

[Get-Event](Get-Event.md)

[Get-EventSubscriber](Get-EventSubscriber.md)

[New-Event](New-Event.md)

[Register-EngineEvent](Register-EngineEvent.md)

[Register-ObjectEvent](Register-ObjectEvent.md)

[Remove-Event](Remove-Event.md)

[Unregister-Event](Unregister-Event.md)

[Wait-Event](Wait-Event.md)

