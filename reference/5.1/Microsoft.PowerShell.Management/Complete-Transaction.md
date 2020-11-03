---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/complete-transaction?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Complete-Transaction
ms.openlocfilehash: 20fbdd86aab07dda065492eff2da4f358fb2ffca
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215556"
---
# Complete-Transaction

## ZUSAMMENFASSUNG
Führt einen Commit für die aktive Transaktion aus.

## SYNTAX

```
Complete-Transaction [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Das **Complete-Transaction-** Cmdlet führt einen Commit für eine aktive Transaktion aus.
Wenn Sie für eine Transaktion einen Commit ausführen, werden die Befehle in der Transaktion abgeschlossen, und die von den Befehlen betroffenen Daten werden geändert.

Wenn die Transaktion mehrere Abonnenten umfasst, müssen Sie für jeden Start-Transaction Befehl einen **Complete-Transaction-** Befehl eingeben, um ein Commit für die Transaktion auszuführen.

Das Cmdlet **Complete-Transaction** ist einer von einem Satz von Cmdlets, die das Transaktions Feature in Windows PowerShell unterstützen.
Weitere Informationen finden Sie unter %%amp;quot;about_Transactions%%amp;quot;.

## BEISPIELE

### Beispiel 1: Commit für eine Transaktion ausführen

```
PS C:\> cd hkcu:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item MyCompany -UseTransaction
PS HKCU:\software> dir m*
Hive: HKEY_CURRENT_USER\software

SKC  VC Name                           Property
---  -- ----                           --------
82   1 Microsoft                      {(default)}

PS HKCU:\software> Complete-Transaction
PS HKCU:\software> dir m*
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
82   1 Microsoft                      {(default)}
0   0 MyCompany                      {}
```

Dieses Beispiel zeigt, was geschieht, wenn Sie mit dem Cmdlet **Complete-Transaction** einen Commit für eine Transaktion ausführen.

Der **Start-Transaction-** Befehl startet die Transaktion.
Der New-Item Befehl verwendet den *UseTransaction* -Parameter, um den Befehl in die Transaktion einzubeziehen.

Der erste dir-Befehl (Get-ChildItem) zeigt an, dass das neue Element noch nicht zur Registrierung hinzugefügt wurde.

Der **Complete-Transaction-** Befehl führt einen Commit für die Transaktion aus, wodurch die Registrierungs Änderung wirksam wird.
Folglich zeigt der zweite dir-Befehl, dass die Registrierung geändert wurde.

### Beispiel 2: Commit für eine Transaktion mit mehreren Abonnenten

```
PS C:\> cd hkcu:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item MyCompany -UseTransaction
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
0   0 MyCompany                      {}

PS HKCU:\software> Start-Transaction
PS HKCU:\Software> Get-Transaction

RollbackPreference   SubscriberCount  Status
------------------   ---------------  ------
Error                2                Active

PS HKCU:\software> New-ItemProperty -Path MyCompany -Name MyKey -Value -UseTransaction

MyKey
-----
123

PS HKCU:\software> Complete-Transaction
PS HKCU:\software> Get-Transaction

RollbackPreference   SubscriberCount  Status
------------------   ---------------  ------
Error                1                Active

PS HKCU:\software> dir m*
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
82   1 Microsoft                      {(default)}

PS HKCU:\software> Complete-Transaction
PS HKCU:\software> dir m*
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
82   1 Microsoft                      {(default)}
0   1 MyCompany                      {MyKey}
```

In diesem Beispiel wird gezeigt, wie mit **Complete-Transaction** ein Commit für eine Transaktion ausgeführt wird, die über mehr als einen Abonnenten verfügt.

Um einen Commit für eine Transaktion mit mehreren Abonnenten auszuführen, müssen Sie für jeden **Start-Transaction** -Befehl einen **Complete-Transaction-** Befehl eingeben.
Die Daten werden nur geändert, wenn der abschließende **Complete-Transaction-** Befehl übermittelt wird.

Für Demonstrationszwecke werden in diesem Beispiel eine Reihe von Befehlen in der Befehlszeile eingegeben.
In der Praxis werden Transaktionen häufig in Skripts ausgeführt, wobei die sekundäre Transaktion von einer Funktion oder einem Hilfsskript ausgeführt wird, das vom Hauptskript aufgerufen wird.

In diesem Beispiel startet ein **Start-Transaction-** Befehl die Transaktion.
Ein **New-Item-** Befehl mit dem *UseTransaction* -Parameter fügt den Schlüssel MyCompany zum Software Schlüssel hinzu.
Obwohl das Cmdlet " **New-Item** " ein Schlüsselobjekt zurückgibt, werden die Daten in der Registrierung noch nicht geändert.

Ein zweiter **Start-Transaction-** Befehl fügt der vorhandenen Transaktion einen zweiten Abonnenten hinzu.
Das Cmdlet **Get-Transaction** bestätigt, dass die Abonnenten Anzahl 2 beträgt.
Ein New-ItemProperty Befehl mit dem *UseTransaction* -Parameter fügt dem neuen MyCompany-Schlüssel einen Registrierungs Eintrag hinzu.
Auch hier gibt der Befehl einen Wert zurück, die Registrierung wird jedoch nicht geändert.

Der erste **Complete-Transaction-** Befehl reduziert die Anzahl der Abonnenten um 1.
Dies wird durch einen **Get-Transaction-** Befehl bestätigt.
Es werden jedoch keine Daten geändert, wie durch den Befehl dir m * ( **Get-ChildItem** ) gezeigt.

Der zweite **Complete-Transaction-** Befehl führt einen Commit für die gesamte Transaktion aus und ändert die Daten in der Registrierung.
Dies wird durch einen zweiten Befehl "dir m *" bestätigt, der die Änderungen anzeigt.

### Beispiel 3: Ausführen einer Transaktion, bei der keine Daten geändert werden

```
PS C:\> cd hkcu:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item MyCompany -UseTransaction
PS HKCU:\software> dir m*
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
82   1 Microsoft                      {(default)}

PS HKCU:\software> dir m* -UseTransaction
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
82   1 Microsoft                      {(default)}
0   0 MyCompany                      {}

PS HKCU:\software> Complete-Transaction
```

Dieses Beispiel zeigt den Wert der Verwendung von get- \* Befehlen und anderer Befehle, die keine Daten in einer Transaktion ändern.
Wenn ein get- \* Command in einer Transaktion verwendet wird, werden die Objekte abgerufen, die Teil der Transaktion sind.
So können Sie die Änderungen in der Transaktion in der Vorschau anzeigen, bevor ein Commit für die Änderungen ausgeführt wird.

In diesem Beispiel wird eine Transaktion gestartet.
Ein New-Item Befehl mit dem *UseTransaction* -Parameter fügt der Registrierung als Teil der Transaktion einen neuen Schlüssel hinzu.

Da der neue Registrierungsschlüssel der Registrierung erst hinzugefügt wird, wenn der Befehl **Complete-Transaction** ausgeführt wird, zeigt ein einfacher dir-Befehl ( **Get-ChildItem** ) die Registrierung ohne den neuen Schlüssel an.

Wenn Sie dem dir-Befehl jedoch den *UseTransaction* -Parameter hinzufügen, wird der Befehl Teil der Transaktion und ruft die Elemente in der Transaktion ab, auch wenn Sie den Daten noch nicht hinzugefügt wurden.

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
Objekte können nicht an dieses Cmdlet weitergereicht werden.

## AUSGABEN

### Keine
Dieses Cmdlet generiert keine Ausgabe.

## HINWEISE

* Sie können keine Transaktion zurücksetzen, für die ein Commit ausgeführt wurde, oder einen Commit für eine Transaktion ausführen, die zurückgesetzt wurde.

  Sie können keine andere Transaktion als die aktive Transaktion zurücksetzen.
Zum Zurücksetzen einer anderen Transaktion müssen Sie zuerst einen Commit für die aktive Transaktion ausführen oder diese zurücksetzen.

  Wenn für einen Teil einer Transaktion kein Commit ausgeführt werden kann, z. B. wenn ein Befehl in der Transaktion zu einem Fehler führt, wird standardmäßig die gesamte Transaktion zurückgesetzt.

*

## VERWANDTE LINKS

[Get-Transaction](Get-Transaction.md)

[Start-Transaction](Start-Transaction.md)

[Undo-Transaction](Undo-Transaction.md)

[Use-Transaction](Use-Transaction.md)

[Get-ChildItem](Get-ChildItem.md)

[New-Item](New-Item.md)

[New-ItemProperty](New-ItemProperty.md)
