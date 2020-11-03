---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-transaction?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Transaction
ms.openlocfilehash: bb8e9e1f204c67207f31613181f856d3bcaf8dc3
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "93200799"
---
# Get-Transaction

## ZUSAMMENFASSUNG
Ruft die aktuelle (aktive) Transaktion ab.

## SYNTAX

```
Get-Transaction [<CommonParameters>]
```

## DESCRIPTION
Mit dem " **Get-Transaction"-** Cmdlet wird ein Objekt abgerufen, das die aktuelle Transaktion in der Sitzung darstellt.

Dieses Cmdlet gibt nie mehr als ein Objekt zurück, da jeweils nur eine Transaktion aktiv ist.
Wenn Sie eine oder mehrere unabhängige Transaktionen (mit dem Independent-Parameter von Start-Transaction) starten, ist die zuletzt gestartete Transaktion aktiv, und das ist die Transaktion, die von **Get-Transaction** zurückgegeben wird.

Wenn für alle aktiven Transaktionen entweder ein Rollback oder ein Commit ausgeführt wurde, zeigt dieses Cmdlet die Transaktion an, die zuletzt in der Sitzung aktiv war.

Dieses Cmdlet ist eine Reihe von Cmdlets, die das Transaktions Feature in Windows PowerShell unterstützen.
Weitere Informationen finden Sie unter %%amp;quot;about_Transactions%%amp;quot;.

## BEISPIELE

### Beispiel 1: erhalten der aktuellen Transaktion

```
PS C:\> Start-Transaction
PS C:\> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
```

Dieser Befehl ruft mit dem Cmdlet %%amp;quot;Get-Transaction%%amp;quot; die aktuelle Transaktion ab.

### Beispiel 2: Anzeigen der Eigenschaften und Methoden des Transaktions Objekts

```
PS C:\> Get-Transaction | Get-Member

Name               MemberType Definition
----               ---------- ----------
Dispose            Method     System.Void Dispose(), System.Void Dispose(Boolean disposing)
Equals             Method     System.Boolean Equals(Object obj)
GetHashCode        Method     System.Int32 GetHashCode()
GetType            Method     System.Type GetType()
ToString           Method     System.String ToString()
IsCommitted        Property   System.Boolean IsCommitted {get;}
IsRolledBack       Property   System.Boolean IsRolledBack {get;}
RollbackPreference Property   System.Management.Automation.RollbackSeverity RollbackPreference {get;}
SubscriberCount    Property   System.Int32 SubscriberCount {get;set;}
```

Dieser Befehl zeigt mit dem Cmdlet %%amp;quot;Get-Member%%amp;quot; die Eigenschaften und Methoden des Transaktionsobjekts an.

### Beispiel 3: Anzeigen der Eigenschaftswerte einer Rollback-Transaktion

```
PS C:\> cd hklm:\software
HKLM:\SOFTWARE> Start-Transaction
HKLM:\SOFTWARE> New-Item MyCompany -UseTransaction
HKLM:\SOFTWARE> Undo-Transaction
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ----------
Error                0                 RolledBack
```

Dieser Befehl zeigt die Eigenschaftenwerte eines Transaktionsobjekts für eine Transaktion an, die zurückgesetzt wurde.

### Beispiel 4: Anzeigen der Eigenschaftswerte einer Transaktion mit Commit

```
PS C:\> cd hklm:\software
HKLM:\SOFTWARE> Start-Transaction
HKLM:\SOFTWARE> New-Item MyCompany -UseTransaction
HKLM:\SOFTWARE> Complete-Transaction
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ---------
Error                1                 Committed
```

Dieser Befehl zeigt die Eigenschaftenwerte eines Transaktionsobjekts für eine Transaktion an, für die ein Commit ausgeführt wurde.

### Beispiel 5: Starten einer Transaktion, während eine andere Transaktion ausgeführt wird

```
PS C:\> cd hklm:\software
HKLM:\SOFTWARE> Start-Transaction
HKLM:\SOFTWARE> New-Item MyCompany -UseTransaction
HKLM:\SOFTWARE> Start-Transaction
HKLM:\SOFTWARE> New-Item MyCompany2 -UseTransaction
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                2                 Active

HKLM:\SOFTWARE> Complete-Transaction
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active

HKLM:\SOFTWARE> Complete-Transaction
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ---------
Error                1                 Committed
```

In diesem Beispiel werden die Auswirkungen auf das Transaktionsobjekt veranschaulicht, wenn eine Transaktion gestartet wird, während eine andere Transaktion ausgeführt wird.
Dies geschieht normalerweise, wenn ein Skript, das eine Transaktion ausführt, eine Funktion enthält oder ein Skript aufruft, die bzw. das eine andere vollständige Transaktion enthält.

Wenn der zweite **Start-Transaction-** Befehl nicht den *Independent* -Parameter enthält, wird von **Start-Transaction** keine neue Transaktion erstellt.
Stattdessen wird der ursprünglichen Transaktion ein zweiter Abonnent hinzugefügt.

Der erste **Start-Transaction-** Befehl startet die Transaktion.
Ein New-Item Befehl mit dem *UseTransaction* -Parameter ist Teil der Transaktion.

Ein zweiter **Start-Transaction-** Befehl fügt der Transaktion einen Abonnenten hinzu.
Der nächste Befehl %%amp;quot;New-Item%%amp;quot; ist ebenfalls Teil der Transaktion.

Der erste **Get-Transaction-** Befehl zeigt die Transaktion mit mehreren Abonnenten an.
Beachten Sie, dass die Abonnentenanzahl 2 beträgt.

Der erste Befehl %%amp;quot;Complete-Transaction%%amp;quot; führt keinen Commit für die Transaktion aus, die Abonnentenanzahl wird jedoch auf 1 verringert.

Der zweite **Complete-Transaction-** Befehl führt einen Commit für die Transaktion aus.

### Beispiel 6: Starten einer unabhängigen Transaktion, während eine andere Transaktion ausgeführt wird

```
PS C:\>
HKLM:\SOFTWARE> Start-Transaction
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   IsRolledBack   IsCommitted
------------------   ---------------   ------------   -----------
Error                1                 False          False

HKLM:\SOFTWARE> Start-Transaction -Independent
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   IsRolledBack   IsCommitted
------------------   ---------------   ------------   -----------
Error                1                 False          False

HKLM:\SOFTWARE> Complete-Transaction
HKLM:\SOFTWARE> Get-Transaction
HKLM:\SOFTWARE> Complete-Transaction
HKLM:\SOFTWARE> Get-Transaction
```

In diesem Beispiel werden die Auswirkungen auf das Transaktionsobjekt veranschaulicht, wenn eine unabhängige Transaktion gestartet wird, während eine andere Transaktion ausgeführt wird.

Der erste **Start-Transaction-** Befehl startet die Transaktion.
Ein **New-Item-** Befehl mit dem *UseTransaction* -Parameter ist Teil der Transaktion.

Ein zweiter **Start-Transaction-** Befehl fügt der Transaktion einen Abonnenten hinzu.
Der nächste **New-Item-** Befehl ist auch Teil der Transaktion.

Der erste **Get-Transaction-** Befehl zeigt die Transaktion mit mehreren Abonnenten an.
Beachten Sie, dass die Abonnentenanzahl 2 beträgt.

Der **Complete-Transaction-** Befehl reduziert die Anzahl der Abonnenten auf 1, führt jedoch keinen Commit für die Transaktion aus.

Der zweite **Complete-Transaction-** Befehl führt einen Commit für die Transaktion aus.

## PARAMETERS

### CommonParameters
Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine
Objekte können nicht an dieses Cmdlet weitergereicht werden.

## AUSGABEN

### System. Management. Automation. pstransaction
Dieses Cmdlet gibt ein Objekt zurück, das die aktuelle Transaktion darstellt.

## HINWEISE

## VERWANDTE LINKS

[Complete-Transaction](Complete-Transaction.md)

[Start-Transaction](Start-Transaction.md)

[Undo-Transaction](Undo-Transaction.md)

[Use-Transaction](Use-Transaction.md)

[New-Item](New-Item.md)
