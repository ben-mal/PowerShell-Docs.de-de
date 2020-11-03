---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/use-transaction?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Use-Transaction
ms.openlocfilehash: db8423aef6dc4b25c4ddd13f9b29b774463c6a6c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214356"
---
# Use-Transaction

## ZUSAMMENFASSUNG
Fügt den Skriptblock der aktiven Transaktion hinzu.

## SYNTAX

```
Use-Transaction [-TransactedScript] <ScriptBlock> [-UseTransaction] [<CommonParameters>]
```

## DESCRIPTION
Das **use-Transaction-** Cmdlet fügt einer aktiven Transaktion einen Skriptblock hinzu.
Dies ermöglicht eine transaktive Skripterstellung mithilfe von Transaktions aktivierten Microsoft .net Frameworkobjekten.
Der Skriptblock darf nur transaktionsfähige .NET Framework-Objekte enthalten, z. B. Instanzen der Microsoft.PowerShell.Commands.Management.TransactedString-Klasse.

Der *UseTransaction* -Parameter, der für die meisten Cmdlets optional ist, ist erforderlich, wenn Sie dieses Cmdlet verwenden.

**Use-Transaction** ist ein Satz von Cmdlets, die das Transaktions Feature in Windows PowerShell unterstützen.
Weitere Informationen finden Sie unter %%amp;quot;about_Transactions%%amp;quot;.

## BEISPIELE

### Beispiel 1: Skripterstellung mithilfe eines transaktionsfähigen Objekts

```
PS C:\> Start-Transaction
PS C:\> $transactedString = New-Object Microsoft.PowerShell.Commands.Management.TransactedString
PS C:\> $transactedString.Append("Hello")
PS C:\> Use-Transaction -TransactedScript { $transactedString.Append(", World") } -UseTransaction
PS C:\> $transactedString.ToString()
Hello
PS C:\> Use-Transaction -TransactedScript { $transactedString.ToString() } -UseTransaction
Hello, World
PS C:\> Complete-Transaction
PS C:\> $transactedString.ToString()
Hello, World
```

In diesem Beispiel wird gezeigt, wie **use-Transaction** verwendet wird, um ein Skript für ein Transaktions fähiges .NET Framework Objekt zu erstellen.
In diesem Fall ist das Objekt ein **transactedstring** -Objekt.

Der erste Befehl startet mit dem Cmdlet %%amp;quot;Start-Transaction%%amp;quot; eine Transaktion.

Der zweite Befehl verwendet den New-Object-Befehl, um ein **transactedstring** -Objekt zu erstellen.
Das Objekt wird in der Variablen %%amp;quot;$TransactedString%%amp;quot; gespeichert.

Der dritte und vierte Befehl verwenden die **Append** -Methode des **transactedstring** -Objekts, um dem Wert $TransactedString Text hinzuzufügen.
Ein Befehl ist ein Teil der Transaktion.
Der andere Befehl ist nicht.

Der dritte Befehl verwendet die **Append** -Methode der transaktiven Zeichenfolge, um Hello zum Wert von $TransactedString hinzuzufügen.
Da der Befehl nicht Teil der Transaktion ist, wird die Änderung sofort übernommen.

Der vierte Befehl verwendet **use-Transaction** , um der Zeichenfolge in der Transaktion Text hinzuzufügen.
Der Befehl verwendet die **Append** -Methode, um dem Wert von $TransactedString ", World" hinzuzufügen.
Der Befehl wird in geschweifte Klammern ( {} ) eingeschlossen, um einen Skriptblock zu erstellen.
Der *UseTransaction* -Parameter ist in diesem Befehl erforderlich.

Der fünfte und sechste Befehl verwenden die **Methode "** -Methode" des **transactedstring** -Objekts, um den Wert von " **transactedstring** " als Zeichenfolge anzuzeigen.
Auch hier ist ein Befehl Teil der Transaktion.
Bei der anderen Transaktion handelt es sich nicht um.

Der fünfte Befehl verwendet die **Methode "** ", um den aktuellen Wert der $TransactedString Variablen anzuzeigen.
Da er kein Teil der Transaktion ist, wird nur der aktuelle Status der Zeichenfolge angezeigt.

Der sechste Befehl verwendet **use-Transaction** , um denselben Befehl in der Transaktion auszuführen.
Da der Befehl Teil der Transaktion ist, wird der aktuelle Wert der Zeichenfolge in der Transaktion angezeigt, ähnlich wie eine Vorschau der Transaktions Änderungen.

Der siebte Befehl führt mit dem Cmdlet %%amp;quot;Complete-Transaction%%amp;quot; einen Commit für die Transaktion aus.

Der letzte Befehl zeigt mithilfe der Methode " **destring** " den resultierenden Wert der Variablen als Zeichenfolge an.

### Beispiel 2: Rollback einer Transaktion

```
PS C:\> Start-Transaction
PS C:\> $transactedString = New-Object Microsoft.PowerShell.Commands.Management.TransactedString
PS C:\> $transactedString.Append("Hello")
PS C:\> Use-Transaction -TransactedScript { $transactedString.Append(", World") } -UseTransaction
PS C:\> Undo-Transaction
PS C:\> $transactedString.ToString()
Hello
```

Dieses Beispiel zeigt die Auswirkungen des Rollbacks einer Transaktion, die **use-Transaction-** Befehle enthält.
Wie alle Befehle in einer Transaktion werden die Transaktionsänderungen beim Zurücksetzen der Transaktion verworfen, und die Daten sind unverändert.

Der erste Befehl verwendet **Start-Transaction** , um eine Transaktion zu starten.

Der zweite Befehl verwendet **New-Object** , um ein **transactedstring** -Objekt zu erstellen.
Das Objekt wird in der Variablen %%amp;quot;$TransactedString%%amp;quot; gespeichert.

Der dritte Befehl, der nicht Teil der Transaktion ist, verwendet die **Append** -Methode, um dem Wert von $TransactedString "Hello" hinzuzufügen.

Der vierte Befehl verwendet **use-Transaction** , um einen anderen Befehl auszuführen, der die **Append** -Methode in der Transaktion verwendet.
Der Befehl verwendet die **Append** -Methode, um dem Wert von $TransactedString ", World" hinzuzufügen.

Der fünfte Befehl setzt die Transaktion mit dem Cmdlet %%amp;quot;Undo-Transaction%%amp;quot; zurück.
Folglich werden alle Befehle, die in der Transaktion ausgeführt werden, rückgängig gemacht.

Der letzte Befehl zeigt mithilfe der Methode " **destring** " den resultierenden Wert von "$TransactedString" als Zeichenfolge an.
Die Ergebnisse zeigen, dass nur die Änderungen, die außerhalb der Transaktion vorgenommen wurden, auf das-Objekt angewendet wurden.

## PARAMETERS

### -Transactedscript
Gibt den Skriptblock an, der in der Transaktion ausgeführt wird.
Geben Sie einen beliebigen gültigen Skriptblock in geschweiften Klammern ({}) ein.
Dieser Parameter ist erforderlich.

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseTransaction
Schließt den Befehl in die aktive Transaktion ein.
Dieser Parameter ist nur gültig, wenn gerade eine Transaktion ausgeführt wird.
Weitere Informationen finden Sie unter about_transactions.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

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

### PSObject
Dieses Cmdlet gibt das Ergebnis der Transaktion zurück.

## HINWEISE

* Der *UseTransaction* -Parameter schließt den Befehl in die aktive Transaktion ein. Da das **use-Transaction-** Cmdlet immer in Transaktionen verwendet wird, ist dieser Parameter erforderlich, damit jeder **use-Transaction-** Befehl wirksam wird.

*

## VERWANDTE LINKS

[Complete-Transaction](Complete-Transaction.md)

[Get-Transaction](Get-Transaction.md)

[Start-Transaction](Start-Transaction.md)

[Undo-Transaction](Undo-Transaction.md)
