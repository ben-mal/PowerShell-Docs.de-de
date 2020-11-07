---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/wait-process?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Wait-Process
ms.openlocfilehash: 2d991ec8e992d98425cf72f7e63e0f7f6e2089c0
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2020
ms.locfileid: "94345747"
---
# Wait-Process

## ZUSAMMENFASSUNG
Wartet, bis die Prozesse beendet wurden, bevor weitere Eingaben angenommen werden.

## SYNTAX

### Name (Standard)

```
Wait-Process [-Name] <String[]> [[-Timeout] <Int32>] [<CommonParameters>]
```

### Id

```
Wait-Process [-Id] <Int32[]> [[-Timeout] <Int32>] [<CommonParameters>]
```

### InputObject

```
Wait-Process [[-Timeout] <Int32>] -InputObject <Process[]> [<CommonParameters>]
```

## DESCRIPTION

Das **Wait-Process-** Cmdlet wartet darauf, dass ein oder mehrere laufende Prozesse beendet werden, bevor Eingaben akzeptiert werden.
In der PowerShell-Konsole unterdrückt dieses Cmdlet die Eingabeaufforderung, bis die Prozesse beendet wurden.
Sie können einen Prozess anhand des Prozess namens oder der Prozess-ID (PID) angeben oder ein Prozess Objekt an **Wait-Process** übergeben.

**Wait-Process** funktioniert nur bei Prozessen, die auf dem lokalen Computer ausgeführt werden.

## BEISPIELE

### Beispiel 1: Abbrechen eines Prozesses und warten

```
PS C:\> $nid = (Get-Process notepad).id
PS C:\> Stop-Process -Id $nid
PS C:\> Wait-Process -Id $nid
```

Dieses Beispiel hält den Notepad-Prozess an und wartet dann, bis der Prozess beendet wird, bevor er mit dem nächsten Befehl fortgesetzt wird.

Der erste Befehl verwendet das **Get-Process-** Cmdlet, um die ID des Notepad-Prozesses zu erhalten.
Die ID wird in der $NID Variablen gespeichert.

Der zweite Befehl verwendet das Cmdlet "Stop-Process", um den Prozess mit der in $NID gespeicherten ID zu unterbinden.

Der dritte Befehl verwendet **Wait-Process** , um zu warten, bis der Notepad-Prozess beendet wurde.
Er verwendet den *ID* -Parameter von **Wait-Process** , um den Prozess zu identifizieren.

### Beispiel 2: Angeben eines Prozesses

```
PS C:\> $p = Get-Process notepad
PS C:\> Wait-Process -Id $p.id
PS C:\> Wait-Process -Name "notepad"
PS C:\> Wait-Process -InputObject $p
```

Diese Befehle zeigen drei verschiedene Methoden zum Angeben eines Prozesses, der **gewartet** werden soll.
Der erste Befehl ruft den Notepad-Prozess ab und speichert ihn in der $p Variable.

Der zweite Befehl verwendet den *ID* -Parameter, der dritte Befehl verwendet den *Name* -Parameter, und der vierte Befehl verwendet den *Inputobject* -Parameter.

Die Ergebnisse dieser Befehle sind identisch und austauschbar.

### Beispiel 3: warten auf Prozesse für einen angegebenen Zeitraum

```
PS C:\> Wait-Process -Name outlook, winword -Timeout 30
```

Dieser Befehl wartet 30 Sekunden, dass die Prozesse %%amp;quot;Outlook%%amp;quot; und %%amp;quot;Winword%%amp;quot; beendet werden.
Wenn beide Prozesse nicht beendet werden, zeigt das Cmdlet einen Fehler ohne Abbruch sowie die Eingabeaufforderung an.

## PARAMETERS

### -Id

Gibt die Prozess-IDs der Prozesse an.
Wenn Sie mehrere IDs angeben, trennen Sie diese durch Kommas.
Um die PID eines Prozesses zu ermitteln, geben Sie ein `Get-Process` .

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases: PID, ProcessId

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject

Gibt die Prozesse durch Senden von Prozessobjekten an.
Geben Sie eine Variable ein, die die Prozess Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, der die Prozess Objekte abruft, z. b. das Get-Process Cmdlet.

```yaml
Type: System.Diagnostics.Process[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name

Gibt die Prozessnamen der Prozesse an.
Wenn Sie mehrere Namen angeben, trennen Sie diese durch Kommas.
Platzhalterzeichen werden nicht unterstützt.

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases: ProcessName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Timeout

Gibt die maximale Zeit in Sekunden an, die dieses Cmdlet darauf wartet, dass die angegebenen Prozesse beendet werden.
Wenn dieses Intervall abläuft, zeigt der Befehl einen Fehler ohne Abbruch an, bei dem die noch ausgeführten Prozesse aufgeführt werden, und beendet den Wartevorgang.
Standardmäßig ist kein Timeout vorhanden.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: TimeoutSec

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System.Diagnostics.Process

Sie können ein Prozess Objekt über die Pipeline an dieses Cmdlet übergeben.

## AUSGABEN

### Keine

Dieses Cmdlet generiert keine Ausgabe.

## HINWEISE

Das-Cmdlet wird nur auf Windows-Plattformen unterstützt.

Dieses Cmdlet verwendet die **WaitForExit** -Methode der **System. Diagnostics. Process** -Klasse.

## VERWANDTE LINKS

[Debug-Process](Debug-Process.md)

[Get-Process](Get-Process.md)

[Start-Process](Start-Process.md)

[Stop-Process](Stop-Process.md)

[Wait-Process](Wait-Process.md)
