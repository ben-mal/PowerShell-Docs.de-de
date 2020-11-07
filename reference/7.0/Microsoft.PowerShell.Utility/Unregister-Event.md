---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/unregister-event?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-Event
ms.openlocfilehash: b7aab2ef1e97ae1cc19d42b07145bd7a057f33fc
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2020
ms.locfileid: "94347753"
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

Mit dem- `Unregister-Event` Cmdlet wird ein Ereignis Abonnement abgebrochen, das mit `Register-EngineEvent` dem `Register-ObjectEvent` Cmdlet, oder erstellt wurde `Register-WmiEvent` .

Wenn ein Ereignisabonnement gekündigt wird, wird der Ereignisabonnent aus der Sitzung gelöscht und die abonnierten Ereignisse werden nicht mehr der Ereigniswarteschlange hinzugefügt. Wenn Sie ein Abonnement für ein Ereignis abbrechen, das mit dem `New-Event` Cmdlet erstellt wurde, wird das neue Ereignis auch aus der Sitzung gelöscht.

`Unregister-Event` löscht keine Ereignisse aus der Ereignis Warteschlange. Verwenden Sie das-Cmdlet, um Ereignisse zu löschen `Remove-Event` .

## BEISPIELE

### Beispiel 1: Abbrechen eines Ereignis Abonnements nach Quell Bezeichner

```
PS C:\> Unregister-Event -SourceIdentifier "ProcessStarted"
```

Mit diesem Befehl wird das Ereignis Abonnement abgebrochen, das den Quell Bezeichner "processstarted" aufweist.

Verwenden Sie das-Cmdlet, um den Quell Bezeichner eines Ereignisses zu finden `Get-Event` . Verwenden Sie das-Cmdlet, um den Quell Bezeichner eines Ereignis Abonnements zu ermitteln `Get-EventSubscriber` .

### Beispiel 2: Abbrechen eines Ereignis Abonnements nach Abonnement Bezeichner

```
PS C:\> Unregister-Event -SubscriptionId 2
```

Mit diesem Befehl wird das Ereignisabonnement gekündigt, das den Abonnementbezeichner „2“ aufweist.

Verwenden Sie das-Cmdlet, um den Abonnement Bezeichner eines Ereignis Abonnements zu ermitteln `Get-EventSubscriber` .

### Beispiel 3: Abbrechen aller Ereignis Abonnements

```
PS C:\> Get-EventSubscriber -Force | Unregister-Event -Force
```

Mit diesem Befehl werden alle Ereignisabonnements in der Sitzung gekündigt.

Der Befehl verwendet das `Get-EventSubscriber` Cmdlet, um alle Ereignis Abonnenten Objekte in der Sitzung zu erhalten, einschließlich der Abonnenten, die mit dem **supportevent** -Parameter der Cmdlets für die Ereignis Registrierung ausgeblendet werden.

Er verwendet einen Pipeline Operator ( `|` ), um die Abonnenten Objekte an zu senden `Unregister-Event` , wodurch Sie aus der Sitzung gelöscht werden. Um die Aufgabe abzuschließen, ist der **Force** -Parameter auch für erforderlich `Unregister-Event` .

## PARAMETERS

### -Force

Bricht alle Ereignis Abonnements ab, einschließlich Abonnements, die mit dem **supportevent** -Parameter von `Register-ObjectEvent` , `Register-WmiEvent` und ausgeblendet wurden `Register-EngineEvent` .

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

Ein **SourceIdentifier** -oder **Abonnement-ID** -Parameter muss in jedem Befehl enthalten sein.

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

Ein **SourceIdentifier** -oder **Abonnement-ID** -Parameter muss in jedem Befehl enthalten sein.

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

### System. Management. Automation. psiebziger Subscriber

Sie können die Ausgabe von an die Pipeline `Get-EventSubscriber` übergeben `Unregister-Event` .

## AUSGABEN

### Keine

Dieses Cmdlet gibt keine Ausgabe zurück.

## HINWEISE

Auf den Linux-oder macOS-Plattformen sind keine Ereignis Quellen verfügbar.

Ereignisse, Ereignisabonnements und die Ereigniswarteschlange sind nur in der aktuellen Sitzung vorhanden. Wenn Sie die aktuelle Sitzung schließen, wird die Ereigniswarteschlange verworfen, und das Ereignisabonnement wird abgebrochen.

`Unregister-Event` Ereignisse, die mit dem Cmdlet erstellt wurden, können nicht gelöscht werden `New-Event` , es sei denn, Sie haben das Ereignis mithilfe des `Register-EngineEvent` Cmdlets abonniert. Um ein benutzerdefiniertes Ereignis aus der Sitzung zu löschen, müssen Sie es programmgesteuert entfernen oder die Sitzung schließen.

## VERWANDTE LINKS

[Get-Event](Get-Event.md)

[Get-EventSubscriber](Get-EventSubscriber.md)

[New-Event](New-Event.md)

[Register-EngineEvent](Register-EngineEvent.md)

[Register-ObjectEvent](Register-ObjectEvent.md)

[Remove-Event](Remove-Event.md)

[Unregister-Event](Unregister-Event.md)

[Wait-Event](Wait-Event.md)
