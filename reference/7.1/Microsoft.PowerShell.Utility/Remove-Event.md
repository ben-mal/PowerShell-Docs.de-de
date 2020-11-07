---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/remove-event?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Event
ms.openlocfilehash: 101732472611943a52c54e6517f42f523b513cfa
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2020
ms.locfileid: "94347651"
---
# Remove-Event

## ZUSAMMENFASSUNG
Löscht Ereignisse aus der Ereigniswarteschlange.

## SYNTAX

### Bysource (Standard)

```
Remove-Event [-SourceIdentifier] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Byidentifier

```
Remove-Event [-EventIdentifier] <Int32> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Das- `Remove-Event` Cmdlet löscht Ereignisse aus der Ereignis Warteschlange in der aktuellen Sitzung.

Mit diesem Cmdlet werden nur Ereignisse gelöscht, die sich aktuell in der Warteschlange befinden. Verwenden Sie das Cmdlet, um Ereignis Registrierungen abzubrechen oder das Abonnement abzubestellen `Unregister-Event` .

## BEISPIELE

### Beispiel 1: Entfernen eines Ereignisses nach dem Quell Bezeichner

```
PS C:\> Remove-Event -SourceIdentifier "ProcessStarted"
```

Dieser Befehl löscht Ereignisse mit einem Quell Bezeichner des Prozesses, der aus der Ereignis Warteschlange gestartet wurde.

### Beispiel 2: Entfernen eines Ereignisses nach Ereignis Bezeichner

```
PS C:\> Remove-Event -EventIdentifier 30
```

Dieser Befehl löscht das Ereignis mit der Ereignis-ID 30 aus der Ereigniswarteschlange.

### Beispiel 3: Entfernen aller Ereignisse

```
PS C:\> Get-Event | Remove-Event
```

Dieser Befehl löscht alle Ereignisse aus der Ereigniswarteschlange.

## PARAMETERS

### -Eventidentifier

Gibt den Ereignis Bezeichner an, den das Cmdlet löscht. Ein **eventidentifier** -oder **SourceIdentifier** -Parameter ist in jedem Befehl erforderlich.

```yaml
Type: System.Int32
Parameter Sets: ByIdentifier
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SourceIdentifier

Gibt den Quell Bezeichner an, aus dem dieses Cmdlet Ereignisse löscht. Platzhalter sind nicht zulässig. Ein **eventidentifier** -oder **SourceIdentifier** -Parameter ist in jedem Befehl erforderlich.

```yaml
Type: System.String
Parameter Sets: BySource
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
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

Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird. Das Cmdlet wird nicht ausgeführt.

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

### System. Management. Automation. psiebziger args

Ereignisse können von `Get-Event` an übergeben werden `Remove-Event` .

## AUSGABEN

### Keine

Das Cmdlet generiert keine Ausgabe.

## HINWEISE

Auf den Linux-oder macOS-Plattformen sind keine Ereignis Quellen verfügbar.

Ereignisse, Ereignisabonnements und die Ereigniswarteschlange sind nur in der aktuellen Sitzung vorhanden. Wenn Sie die aktuelle Sitzung schließen, wird die Ereigniswarteschlange verworfen, und das Ereignisabonnement wird abgebrochen.

## VERWANDTE LINKS

[Get-Event](Get-Event.md)

[New-Event](New-Event.md)

[Register-EngineEvent](Register-EngineEvent.md)

[Register-ObjectEvent](Register-ObjectEvent.md)

[Remove-Event](Remove-Event.md)

[Unregister-Event](Unregister-Event.md)

[Wait-Event](Wait-Event.md)
