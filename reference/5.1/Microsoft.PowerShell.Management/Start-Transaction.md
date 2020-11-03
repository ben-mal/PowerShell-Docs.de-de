---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/start-transaction?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Transaction
ms.openlocfilehash: 53be131f45f15e5d2053b183040dc7b3dca4a14c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214391"
---
# Start-Transaction

## ZUSAMMENFASSUNG
Startet eine Transaktion.

## SYNTAX

```
Start-Transaction [-Timeout <Int32>] [-Independent] [-RollbackPreference <RollbackSeverity>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Mit dem " **Start-Transaction"-** Cmdlet wird eine Transaktion gestartet, bei der es sich um eine Reihe von Befehlen handelt, die als Einheit verwaltet werden.
Eine Transaktion kann abgeschlossen oder ein Commit ausgeführt werden.
Alternativ kann Sie vollständig rückgängig gemacht oder ein Rollback ausgeführt werden, sodass alle von der Transaktion geänderten Daten im ursprünglichen Zustand wieder hergestellt werden.
Da die Befehle in einer Transaktion als Einheit verwaltet werden, wird entweder für alle Befehle ein Commit ausgeführt, oder alle Befehle werden zurückgesetzt.

Wenn ein Befehl in der Transaktion einen Fehler generiert, werden für Transaktionen standardmäßig automatisch ein Rollback ausgeführt.
Sie können den *Rollback Preference* -Parameter verwenden, um dieses Verhalten zu ändern.

Die in einer Transaktion verwendeten Cmdlets müssen zum Unterstützen von Transaktionen geeignet sein.
Cmdlets, die Transaktionen unterstützen, verfügen über einen *UseTransaction* -Parameter.
Damit Transaktionen in einem Anbieter ausgeführt werden können, muss der Anbieter Transaktionen unterstützen.
Der Windows PowerShell-Registrierungs Anbieter in Windows Vista und höheren Versionen des Windows-Betriebssystems unterstützt Transaktionen.
Sie können auch die **Microsoft. PowerShell. Commands. Management. transactedstring** -Klasse verwenden, um Ausdrücke in Transaktionen für jede Version des Windows-Systems einzuschließen, das Windows PowerShell unterstützt.
Andere Windows PowerShell-Anbieter können ebenfalls Transaktionen unterstützen.

Es kann jeweils nur eine Transaktion aktiv sein.
Wenn Sie eine neue, unabhängige Transaktion starten, während eine Transaktion ausgeführt wird, wird die neue Transaktion zur aktiven Transaktion, und Sie müssen ein Commit oder ein Rollback der neuen Transaktion ausführen, bevor Sie Änderungen an der ursprünglichen Transaktion vornehmen.

Das Cmdlet " **Start-Transaction** " ist eine Reihe von Cmdlets, die das Transaktions Feature in Windows PowerShell unterstützen.
Weitere Informationen finden Sie unter %%amp;quot;about_Transactions%%amp;quot;.

## BEISPIELE

### Beispiel 1: starten und Rollback einer Transaktion

```
PS C:\> cd hkcu:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item "ContosoCompany" -UseTransaction
PS HKCU:\software> New-ItemProperty "ContosoCompany" -Name "MyKey" -Value 123 -UseTransaction
PS HKCU:\software> Undo-Transaction
```

Mit diesen Befehlen wird eine Transaktion gestartet und dann zurückgesetzt.
Da die Transaktion zurückgesetzt wird, werden keine Änderungen in der Registrierung vorgenommen.

### Beispiel 2: starten und Beenden einer Transaktion

```
PS C:\> cd hkcu:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item "ContosoCompany" -UseTransaction
PS HKCU:\software> New-ItemProperty "ContosoCompany" -Name "MyKey" -Value 123 -UseTransaction
PS HKCU:\software> Complete-Transaction
```

Mit diesen Befehlen wird eine Transaktion gestartet und dann abgeschlossen.
Es werden keine Änderungen an der Registrierung vorgenommen, bis der **Complete-Transaction-** Befehl verwendet wird.

### Beispiel 3: Verwenden von unterschiedlichen Roll Back Einstellungen

```
PS C:\> cd HKCU:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item -Path "NoPath" -Name "ContosoCompany" -UseTransaction
PS HKCU:\software> New-Item -Path . -Name "ContosoCompany" -UseTransaction
PS HKCU:\software> Start-Transaction -RollbackPreference never
PS HKCU:\software> New-Item -Path "NoPath" -Name "ContosoCompany" -UseTransaction
PS HKCU:\software> New-Item -Path . -Name "ContosoCompany" -UseTransaction

# Start-Transaction (-rollbackpreference error)

PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item -Path "NoPath" -Name "ContosoCompany" -UseTransaction
New-Item : The registry key at the specified path does not exist.
At line:1 char:9
+ new-item <<<<  -Path NoPath -Name ContosoCompany -UseTransaction

PS HKCU:\software> New-Item -Path . -Name "Contoso" -UseTransaction

New-Item : Cannot use transaction. The transaction has been rolled back or has timed out.
At line:1 char:9
+ new-item <<<<  -Path . -Name ContosoCompany -UseTransaction

# Start-Transaction (-rollbackpreference never)

PS HKCU:\software> Start-Transaction -RollbackPreference never
PS HKCU:\software> New-Item -Path "NoPath" -Name "ContosoCompany" -UseTransaction

New-Item : The registry key at the specified path does not exist.
At line:1 char:9
+ new-item <<<<  -Path NoPath -Name "ContosoCompany" -UseTransaction
PS HKCU:\software> New-Item -Path . -Name "ContosoCompany" -UseTransaction

Hive: HKEY_CURRENT_USER\Software
SKC  VC Name                           Property
---  -- ----                           --------
0   0 ContosoCompany                 {}
PS HKCU:\Software> Complete-Transaction

# Succeeds
```

In diesem Beispiel werden die Auswirkungen der Änderung des *Roll Back Preference* -Parameter Werts veranschaulicht.

In der ersten Befehls Reihe verwendet **Start-Transaction** keine *Rollback Preference* .
Daher wird der Standardwert (Error) verwendet.
Wenn ein Fehler in einem Transaktions Befehl auftritt, d. h. der angegebene Pfad nicht vorhanden ist, wird für die Transaktion automatisch ein Rollback ausgeführt.

Im zweiten Satz von Befehlen verwendet **Start-Transaction** *Roll Back Preference* mit dem Wert Never.
Wenn ein Fehler in einem Transaktionsbefehl auftritt, ist die Transaktion daher weiterhin aktiv und kann erfolgreich abgeschlossen werden.

Da die meisten Transaktionen ohne Fehler ausgeführt werden müssen, wird in der Regel der Standardwert von *Rollback Preference* bevorzugt.

### Beispiel 4: Verwenden Sie dieses Cmdlet, während eine Transaktion ausgeführt wird.

```
PS C:\> cd HKCU:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item "ContosoCompany" -UseTransaction
PS HKCU:\software> Start-Transaction
PS HKCU:\software> Get-Transaction
PS HKCU:\software> New-Item "ContosoCompany2" -UseTransaction
PS HKCU:\software> Complete-Transaction
PS HKCU:\software> Complete-Transaction
PS HKCU:\Software> Get-Transaction
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                2                 Active
```

Dieses Beispiel zeigt die Auswirkung der Verwendung von **Start-Transaction** , während eine Transaktion ausgeführt wird.
Dies entspricht weitgehend dem Hinzufügen der ausgeführten Transaktion.

Obwohl es sich hierbei um einen vereinfachten Befehl handelt, tritt dieses Szenario häufig auf, wenn die Transaktion das Ausführen eines Skripts umfasst, das eine komplette Transaktion einschließt.

Der erste **Start-Transaction-** Befehl startet die Transaktion.
Der erste **New-Item-** Befehl ist Teil der Transaktion.

Der zweite **Start-Transaction-** Befehl fügt der Transaktion einen neuen Abonnenten hinzu.
Der **Get-Transaction-** Befehl gibt nun eine Transaktion mit der Abonnenten Anzahl 2 zurück.
Der zweite **New-Item-** Befehl ist Teil derselben Transaktion.

Es werden keine Änderungen an der Registrierung vorgenommen, bis die gesamte Transaktion abgeschlossen ist.
Zum Abschließen der Transaktion müssen Sie zwei **Complete-Transaction-** Befehle eingeben, einen für jeden Abonnenten.
Wenn Sie die Transaktion an einem beliebigen Punkt zurücksetzen würden, würde für beide Abonnenten ein Rollback für die Transaktion ausgeführt werden.

### Beispiel 5: Starten einer unabhängigen Transaktion, während eine Transaktion ausgeführt wird

```
PS C:\> cd HKCU:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item "ContosoCompany" -UseTransaction
PS HKCU:\software> Start-Transaction -Independent
PS HKCU:\software> Get-Transaction
PS HKCU:\software> Undo-Transaction
PS HKCU:\software> New-ItemProperty -Path "ContosoCompany" -Name "MyKey" -Value 123 -UseTransaction
PS HKCU:\software> Complete-Transaction
PS HKCU:\software> dir contoso*
PS HKCU:\Software> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
PS HKCU:\software> Undo-Transaction
PS HKCU:\software> New-ItemProperty -Path "ContosoCompany" -Name "MyKey" -Value 123 -UseTransaction
MyKey
-----
123
PS HKCU:\software> Complete-Transaction
PS HKCU:\software> dir contoso*
Hive: HKEY_CURRENT_USER\Software
SKC  VC Name                           Property
---  -- ----                           --------
0   1 MyCompany                      {MyKey}
```

Dieses Beispiel zeigt die Auswirkung der Verwendung des *unabhängigen* Parameters von **Start-Transaction** , um eine Transaktion zu starten, während eine andere Transaktion ausgeführt wird.
In diesem Fall wird die neue Transaktion zurückgesetzt, ohne dass dies Auswirkungen auf die ursprüngliche Transaktion hat.

Obwohl die Transaktionen logisch unabhängig sind, da jeweils nur eine Transaktion aktiv sein kann, müssen Sie die neueste Transaktion zurücksetzen oder einen Commit ausführen, bevor Sie weiter mit der ursprünglichen Transaktion arbeiten können.

Mit dem ersten Satz von Befehlen wird eine Transaktion gestartet.
Der **New-Item-** Befehl ist Teil der ersten Transaktion.

Im zweiten Satz von Befehlen verwendet der Befehl **Start-Transaction** den *unabhängigen* Parameter.
Der folgende **Get-Transaction-** Befehl zeigt das Transaktions Objekt für die aktive Transaktion, die das neueste ist.
Die Abonnenten Anzahl ist gleich 1 und zeigt an, dass die Transaktionen nicht verknüpft sind.

Wenn ein Rollback für die aktive Transaktion mit einem Befehl **Rückgängig-Transaktion** ausgeführt wird, wird die ursprüngliche Transaktion wieder aktiv.

Der **New-ItemProperty-** Befehl, der Teil der ursprünglichen Transaktion ist, wird ohne Fehler beendet, und die ursprüngliche Transaktion kann mit dem **Complete-Transaction-** Befehl abgeschlossen werden.
Die Registrierung wird daraufhin geändert.

### Beispiel 6: Ausführen von Befehlen, die nicht Teil einer Transaktion sind

```
PS C:\> cd hkcu:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item "ContosoCompany1" -UseTransaction
PS HKCU:\software> New-Item "ContosoCompany2"
PS HKCU:\software> New-Item "ContosoCompany3" -UseTransaction
PS HKCU:\software> dir contoso*
PS HKCU:\software> Complete-Transaction
PS HKCU:\software> dir contoso*
PS HKCU:\Software> dir contoso*

Hive: HKEY_CURRENT_USER\Software
SKC  VC Name                           Property
---  -- ----                           --------
0   0 ContosoCompany2                {}

PS HKCU:\Software> Complete-Transaction
PS HKCU:\Software> dir contoso*

Hive: HKEY_CURRENT_USER\Software
SKC  VC Name                           Property
---  -- ----                           --------
0   0 ContosoCompany1                     {}
0   0 ContosoCompany2                     {}
0   0 ContosoCompany3                     {}
```

In diesem Beispiel wird veranschaulicht, dass Befehle, die gesendet werden, während eine Transaktion ausgeführt wird, in der Transaktion eingeschlossen oder nicht eingeschlossen werden können.
Nur Befehle, die den *UseTransaction* -Parameter verwenden, sind Teil der Transaktion.

Der erste und der dritte **New-Item-** Befehl verwenden den *UseTransaction* -Parameter.
Diese Befehle sind Teil der Transaktion.
Da der zweite **New-Item-** Befehl den *UseTransaction* -Parameter nicht verwendet, ist er nicht Teil der Transaktion.

Der erste dir-Befehl zeigt den Effekt.
Der zweite **New-Item-** Befehl wird sofort abgeschlossen, der erste und der dritte **New-Item-** Befehl werden jedoch erst wirksam, wenn für die Transaktion ein Commit ausgeführt wird.

Der **Complete-Transaction-** Befehl führt einen Commit für die Transaktion aus.
Folglich zeigt der zweite dir-Befehl, dass alle neuen Elemente der Registrierung hinzugefügt werden.

### Beispiel 7: Ausführen eines Rollbacks für eine Transaktion, die nicht in einem angegebenen Zeitraum beendet wird

```
PS C:\> Start-Transaction -Timeout 2

# Wait two minutes...

PS C:\> Get-Transaction
PS C:\> New-Item HKCU:\Software\ContosoCompany -UseTransaction
PS C:\> Start-Transaction -Timeout 2

# Wait two minutes...

PS C:\> > Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   -----------
Error                1                 RolledBack

PS C:\> New-Item HKCU:\Software\ContosoCompany -UseTransaction

New-Item : Cannot use transaction. The transaction has been rolled back or has timed out.
At line:1 char:9
+ new-item <<<<  MyCompany -UseTransaction
```

Dieser Befehl verwendet den *Timeout* -Parameter von **Start-Transaction** , um eine Transaktion zu starten, die innerhalb von zwei Minuten abgeschlossen werden muss.
Wenn die Transaktion bei Ablauf des Timeouts nicht abgeschlossen ist, wird automatisch ein Rollback ausgeführt.

Wenn das Timeout abläuft, werden Sie nicht benachrichtigt, die **Status** -Eigenschaft des Transaktions Objekts wird jedoch auf rolledback festgelegt, und Befehle, die den *UseTransaction* -Parameter verwenden, schlagen fehl.

## PARAMETERS

### -Unabhängig
Gibt an, dass dieses Cmdlet eine Transaktion startet, die unabhängig von Transaktionen ist, die gerade ausgeführt werden.
Wenn Sie **Start-Transaction** verwenden, während eine andere Transaktion ausgeführt wird, wird der Transaktion standardmäßig ein neuer Abonnent hinzugefügt.
Dieser Parameter hat nur Auswirkungen, wenn bereits eine Transaktion in der Sitzung ausgeführt wird.

Wenn Sie **Start-Transaction** verwenden, während eine Transaktion ausgeführt wird, wird das vorhandene Transaktions Objekt standardmäßig wieder verwendet, und die Abonnenten Anzahl wird erhöht.
Dies entspricht weitgehend dem Hinzufügen der ursprünglichen Transaktion.
Ein Undo-Transaction Befehl führt einen Rollback für die gesamte Transaktion aus.
Zum Abschließen der Transaktion müssen Sie den Befehl %%amp;quot;Complete-Transaction%%amp;quot; für jeden Abonnenten eingeben.
Da die meisten Transaktionen, die gleichzeitig ausgeführt werden, miteinander in Zusammenhang stehen, ist der Standardwert in den meisten Fällen ausreichend.

Wenn Sie den *unabhängigen* Parameter angeben, erstellt dieses Cmdlet eine neue Transaktion, die abgeschlossen oder rückgängig gemacht werden kann, ohne dass sich dies auf die ursprüngliche Transaktion auswirkt.
Da jedoch nur jeweils eine Transaktion aktiv sein kann, müssen Sie die neue Transaktion abschließen oder zurücksetzen, bevor Sie mit der ursprünglichen Transaktion weiterarbeiten.

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

### -Rollbackpreference
Gibt die Bedingungen an, unter denen eine Transaktion automatisch zurückgesetzt wird.
Zulässige Werte für diesen Parameter:

- Fehler.
Die Transaktion wird automatisch zurückgesetzt, wenn ein Fehler mit oder ohne Abbruch auftritt.
- Terminatingerror.
Die Transaktion wird automatisch zurückgesetzt, wenn ein Fehler mit Abbruch auftritt.
- Nie
Die Transaktion nie wird automatisch zurückgesetzt.

Der Standardwert ist "Error".

```yaml
Type: System.Management.Automation.RollbackSeverity
Parameter Sets: (All)
Aliases:
Accepted values: Error, TerminatingError, Never

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Timeout
Gibt die maximale Zeit in Minuten an, die die Transaktion aktiv ist.
Wenn das Timeout abläuft, wird die Transaktion automatisch zurückgesetzt.

Standardmäßig gibt es kein Timeout für Transaktionen, die über die Befehlszeile gestartet wurden.
Wenn Transaktionen von einem Skript gestartet werden, beträgt der Standardtimeoutwert 30 Minuten.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: TimeoutMins

Required: False
Position: Named
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
Dieses Cmdlet generiert keine Ausgabe.

## HINWEISE

## VERWANDTE LINKS

[Complete-Transaction](Complete-Transaction.md)

[Get-Transaction](Get-Transaction.md)

[Undo-Transaction](Undo-Transaction.md)

[Use-Transaction](Use-Transaction.md)
