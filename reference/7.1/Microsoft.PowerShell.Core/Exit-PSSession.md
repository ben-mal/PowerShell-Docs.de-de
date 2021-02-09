---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 02/08/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/exit-pssession?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Exit-PSSession
ms.openlocfilehash: b764aadc28d175f08fdcbaf56e904ff9310eb35b
ms.sourcegitcommit: 3a1d80e27438976101f216b8c3d623c61b868db8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2021
ms.locfileid: "99975072"
---
# Exit-PSSession

## Übersicht
Beendet eine interaktive Sitzung mit einem Remotecomputer.

## SYNTAX

```
Exit-PSSession [<CommonParameters>]
```

## BESCHREIBUNG

Das `Exit-PSSession` Cmdlet beendet interaktive Sitzungen, die Sie mithilfe des `Enter-PSSession` Cmdlets gestartet haben.

Sie können auch das- `exit` Schlüsselwort verwenden, um eine interaktive Sitzung zu beenden. Der Effekt ist identisch mit der Verwendung von `Exit-PSSession` .

## Beispiele

### Beispiel 1: starten und Beenden einer interaktiven Sitzung

```powershell
PS> Enter-PSSession -ComputerName Server01
Server01\PS> Exit-PSSession
PS>
```

Mit diesen Befehlen starten und beenden Sie eine interaktive Sitzung mit dem Remotecomputer Server01.

### Beispiel 2: starten und Beenden einer interaktiven Sitzung mit einem PSSession-Objekt

```powershell
PS> $s = New-PSSession -ComputerName Server01
PS> Enter-PSSession -Session $s
Server01\PS> Exit-PSSession
PS> $s
Id Name            ComputerName    State    ConfigurationName
-- ----            ------------    -----    -----------------
1  Session1        Server01        Opened   Microsoft.PowerShell
```

Mit diesen Befehlen starten und beenden Sie eine interaktive Sitzung mit dem Server01-Computer, der eine PowerShell-Sitzung (**PSSession**) verwendet.

Da die interaktive Sitzung mithilfe einer PowerShell-Sitzung gestartet wurde, ist die **PSSession** weiterhin verfügbar, wenn die interaktive Sitzung beendet wird. Wenn Sie den _Computername_ -Parameter verwenden, wird von `Enter-PSSession` eine temporäre Sitzung erstellt, die beim Ende der interaktiven Sitzung geschlossen wird.

Der erste Befehl verwendet das `New-PSSession` Cmdlet, um eine **PSSession** auf dem Server01-Computer zu erstellen. Der Befehl speichert die **PSSession** in der `$s` Variablen.

Der zweite Befehl verwendet `Enter-PSSession` , um mithilfe der **PSSession** in eine interaktive Sitzung zu starten `$s` .

Der dritte Befehl verwendet `Exit-PSSession` , um die interaktive Sitzung zu unterbinden.

Der letzte Befehl zeigt die **PSSession** in der `$s` Variablen an. Die **State** -Eigenschaft zeigt, dass die **PSSession** weiterhin geöffnet ist und zur Verwendung verfügbar ist.

### Beispiel 3: Verwenden des Exit-Schlüssel Worts zum Beenden einer Sitzung

```powershell
PS> Enter-PSSession -ComputerName Server01
Server01\PS> exit
PS>
```

Dieses Beispiel verwendet das- `exit` Schlüsselwort, um eine interaktive Sitzung zu beenden, die mit gestartet wurde `Enter-PSSession` . Das- `exit` Schlüsselwort hat dieselbe Auswirkung wie die Verwendung von `Exit-PSSession` .

## Parameter

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Eingaben

### Keine

Objekte können nicht an dieses Cmdlet weitergereicht werden.

## Ausgaben

### Keine

Dieses Cmdlet gibt keine Ausgabe zurück.

## Notizen

Von diesem Cmdlet werden nur allgemeine Parameter verwendet.

## VERWANDTE LINKS

[Connect-PSSession](Connect-PSSession.md)

[Disconnect-PSSession](Disconnect-PSSession.md)

[Enter-PSSession](Enter-PSSession.md)

[Get-PSSession](Get-PSSession.md)

[Invoke-Command](Invoke-Command.md)

[New-PSSession](New-PSSession.md)

[Receive-PSSession](Receive-PSSession.md)

[Remove-PSSession](Remove-PSSession.md)
