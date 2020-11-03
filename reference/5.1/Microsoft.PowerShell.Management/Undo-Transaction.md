---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/undo-transaction?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Undo-Transaction
ms.openlocfilehash: 1acb06ea7b05a2127b04a22c4c51b92cd68056f2
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214340"
---
# Undo-Transaction

## ZUSAMMENFASSUNG
Setzt die aktive Transaktion zurück.

## SYNTAX

```
Undo-Transaction [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Das **Undo-Transaction-** Cmdlet führt einen Rollback für die aktive Transaktion aus.
Wenn Sie ein Rollback für eine Transaktion ausführen, werden die von den Befehlen in der Transaktion vorgenommenen Änderungen verworfen, und die Daten werden in ihrer ursprünglichen Form wieder hergestellt.

Wenn die Transaktion mehrere Abonnenten umfasst, führt ein **Rückgängig-Transaction-** Befehl ein Rollback für die gesamte Transaktion für alle Abonnenten aus.

Standardmäßig werden Transaktionen automatisch zurückgesetzt, wenn ein Befehl in der Transaktion einen Fehler generiert.
Transaktionen können jedoch mit einer anderen Roll Back Einstellung gestartet werden, und Sie können mit diesem Cmdlet jederzeit ein Rollback für die aktive Transaktion ausführen.

Das **Undo-Transaction-** Cmdlet ist einer der Cmdlets, die das Transaktions Feature in Windows PowerShell unterstützen.
Weitere Informationen finden Sie unter %%amp;quot;about_Transactions%%amp;quot;.

## BEISPIELE

### Beispiel 1: Rollback der aktuellen Transaktion

```
PS C:\> Undo-Transaction
```

Mit diesem Befehl wird ein Rollback der aktuellen aktiven Transaktion ausgeführt.

### Beispiel 2: starten und Rollback einer Transaktion

```
PS C:\> cd hkcu:\software
PS HKCU:\Software> Start-Transaction
PS HKCU:\Software> New-Item -Path "ContosoCompany" -UseTransaction
PS HKCU:\Software> Undo-Transaction
```

In diesem Beispiel wird eine Transaktion gestartet und anschließend ein Rollback ausgeführt.
Es werden daher keine Änderungen an der Registrierung vorgenommen.

### Beispiel 3: Ausführen eines Rollbacks für eine Transaktion für alle Abonnenten

```
PS C:\> cd hkcu:\software
PS HKCU:\Software> Start-Transaction
PS HKCU:\Software> New-Item -Path "ContosoCompany" -UseTransaction
PS HKCU:\Software> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   -----
Error                1                 Active

PS HKCU:\Software> Start-Transaction
PS HKCU:\Software> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   -----
Error                2                 Active

PS HKCU:\Software> Undo-Transaction
PS HKCU:\Software> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   -----
Error                0                 RolledBack
```

In diesem Beispiel wird veranschaulicht, dass für die gesamte Transaktion für alle Abonnenten ein Rollback ausgeführt wird, wenn ein Abonnent eine Transaktion zurücksetzt.

Mit dem ersten Befehl wird der Speicherort des Registrierungsschlüssels %%amp;quot;HKCU:\Software%%amp;quot; geändert.

Der zweite Befehl startet eine Transaktion.

Der dritte Befehl erstellt mit dem Cmdlet %%amp;quot;New-Item%%amp;quot; einen neuen Registrierungsschlüssel.
Der Befehl verwendet den *UseTransaction* -Parameter, um die Änderung in die Transaktion einzubeziehen.

Der vierte Befehl ruft mit dem Cmdlet %%amp;quot;Get-Transaction%%amp;quot; die aktive Transaktion ab.
Beachten Sie, dass der Status %%amp;quot;Aktiv%%amp;quot; ist und die Anzahl der Abonnenten 1 lautet.

Der fünfte Befehl verwendet wieder den Befehl %%amp;quot;Start-Transaction%%amp;quot;.
Das Starten einer Transaktion während einer anderen Transaktion erfolgt in der Regel, wenn ein von der Haupt Transaktion verwendetes Skript eine eigene, komplette Transaktion enthält.
Dieses Beispiel wird interaktiv ausgeführt, sodass Sie es in Phasen untersuchen können.
Wenn Sie einen **Start-Transaction-** Befehl ausführen, während eine andere Transaktion ausgeführt wird, verknüpfen die Befehle die vorhandene Transaktion als neuer Abonnent, und die Abonnenten Anzahl wird inkrementiert.

Der sechste Befehl verwendet das **Get-Transaction-** Cmdlet, um die aktive Transaktion zu erhalten.
Beachten Sie, dass die Abonnentenanzahl nun 2 lautet.

Der siebte Befehl verwendet die **Rückgängig-Transaktion** , um ein Rollback für die Transaktion auszuführen.
Dieser Befehl gibt keine Objekte zurück.

Der letzte Befehl ist ein **Get-Transaction-** Befehl, mit dem der aktive oder in diesem Fall die zuletzt aktive Transaktion abgerufen wird.
Das Ergebnis zeigt, dass die Transaktion zurückgesetzt wurde und dass die Abonnentenanzahl den Wert %%amp;quot;0%%amp;quot; aufweist. Dies gibt an, dass die Transaktion für alle Abonnenten zurückgesetzt wurde.

## PARAMETERS

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

### Keine
Eingaben können nicht an dieses Cmdlet weitergereicht werden.

## AUSGABEN

### Keine
Dieses Cmdlet gibt keine Ausgabe zurück.

## HINWEISE

* Sie können keine Transaktion zurücksetzen, für die ein Commit ausgeführt wurde.

  Sie können keine andere Transaktion als die aktive Transaktion zurücksetzen.
Zum Zurücksetzen einer anderen, unabhängigen Transaktion müssen Sie zuerst einen Commit für die aktive Transaktion ausführen oder diese zurücksetzen.

  Das Zurücksetzen der Transaktion beendet diese.
Wenn Sie eine Transaktion wiederverwenden möchten, müssen Sie eine neue Transaktion starten.

## VERWANDTE LINKS

[Complete-Transaction](Complete-Transaction.md)

[Get-Transaction](Get-Transaction.md)

[Start-Transaction](Start-Transaction.md)

[Use-Transaction](Use-Transaction.md)
