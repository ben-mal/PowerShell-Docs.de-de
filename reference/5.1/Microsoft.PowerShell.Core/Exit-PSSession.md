---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/exit-pssession?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Exit-PSSession
ms.openlocfilehash: efe0e6c9287b3595988aa3ffc520ce46699cafda
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212068"
---
# Exit-PSSession

## ZUSAMMENFASSUNG
Beendet eine interaktive Sitzung mit einem Remotecomputer.

## SYNTAX

```
Exit-PSSession [<CommonParameters>]
```

## DESCRIPTION
Das **Exit-PSSession** -Cmdlet beendet interaktive Sitzungen, die Sie mit dem Cmdlet "Enter-PSSession" gestartet haben.

Sie können auch das **Exit** -Schlüsselwort verwenden, um eine interaktive Sitzung zu beenden.
Der Effekt ist mit der Verwendung von **Exit-PSSession** identisch.

## BEISPIELE

### Beispiel 1: starten und Beenden einer interaktiven Sitzung

```
PS C:\> Enter-PSSession -computername Server01
Server01\PS> Exit-PSSession
PS C:\>
```

Mit diesen Befehlen starten und beenden Sie eine interaktive Sitzung mit dem Remotecomputer Server01.

### Beispiel 2: starten und Beenden einer interaktiven Sitzung mit einem PSSession-Objekt

```
PS C:\> $s = New-PSSession -ComputerName Server01
PS C:\> Enter-PSSession -Session $s
Server01\PS> Exit-PSSession
PS C:\> $s
Id Name            ComputerName    State    ConfigurationName
-- ----            ------------    -----    -----------------
1  Session1        Server01        Opened   Microsoft.PowerShell
```

Mit diesen Befehlen starten und beenden Sie eine interaktive Sitzung mit dem Server01-Computer, auf dem eine Windows PowerShell-Sitzung ( **PSSession** ) verwendet wird.

Da die interaktive Sitzung mithilfe einer Windows PowerShell-Sitzung gestartet wurde, ist die **PSSession** weiterhin verfügbar, wenn die interaktive Sitzung beendet wird.
Wenn Sie den *Computername* -Parameter verwenden, erstellt **Enter-PSSession** eine temporäre Sitzung, die beim Ende der interaktiven Sitzung geschlossen wird.

Der erste Befehl verwendet das Cmdlet "New-PSSession", um eine **PSSession** auf dem Server01-Computer zu erstellen.
Der Befehl speichert die **PSSession** in der $s Variable.

Der zweite Befehl verwendet **Enter-PSSession** , um eine interaktive Sitzung mithilfe der **PSSession** in $s zu starten.

Der dritte Befehl verwendet **Exit-PSSession** , um die interaktive Sitzung zu beenden.

Der letzte Befehl zeigt die **PSSession** in der $s Variable an.
Die **State** -Eigenschaft zeigt, dass die **PSSession** weiterhin geöffnet ist und zur Verwendung verfügbar ist.

### Beispiel 3: Verwenden des Exit-Schlüssel Worts zum Beenden einer Sitzung

```
PS C:\> Enter-PSSession -computername Server01
Server01\PS> exit
PS C:\>
```

Dieses Beispiel verwendet das **Exit** -Schlüsselwort, um eine interaktive Sitzung zu beenden, die mit **Enter-PSSession** gestartet wurde.
Das **Exit** -Schlüsselwort hat dieselbe Auswirkung wie die Verwendung von **Exit-PSSession** .

## PARAMETERS

### CommonParameters
Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine
Objekte können nicht an dieses Cmdlet weitergereicht werden.

## AUSGABEN

### Keine
Dieses Cmdlet gibt keine Ausgabe zurück.

## HINWEISE

* Von diesem Cmdlet werden nur allgemeine Parameter verwendet.


## VERWANDTE LINKS

[Connect-PSSession](Connect-PSSession.md)

[Disconnect-PSSession](Disconnect-PSSession.md)

[Enter-PSSession](Enter-PSSession.md)

[Get-PSSession](Get-PSSession.md)

[Invoke-Command](Invoke-Command.md)

[New-PSSession](New-PSSession.md)

[Receive-PSSession](Receive-PSSession.md)

[Remove-PSSession](Remove-PSSession.md)
