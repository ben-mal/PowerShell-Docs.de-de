---
external help file: Microsoft.PowerShell.ConsoleHost.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Host
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.host/stop-transcript?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Transcript
ms.openlocfilehash: 16b41711e98276fee37d56f77f57e7372daa4cf3
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596547"
---
# Stop-Transcript

## ZUSAMMENFASSUNG
Beendet eine Aufzeichnung.

## SYNTAX

```
Stop-Transcript [<CommonParameters>]
```

## DESCRIPTION

Das- `Stop-Transcript` Cmdlet beendet eine Aufzeichnung, die vom `Start-Transcript` Cmdlet gestartet wurde.
Alternativ können Sie eine Sitzung beenden, um eine Aufzeichnung zu beenden.

## BEISPIELE

### Beispiel 1: alle Transkriptionen Abbrechen

```powershell
Stop-Transcript
```

Dieser Befehl beendet alle Transkriptionen.

## PARAMETERS

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine

Eingaben können nicht an dieses Cmdlet weitergereicht werden.

## AUSGABEN

### System.String

Dieses Cmdlet gibt eine Zeichenfolge zurück, die eine Statusmeldung und den Pfad zur Ausgabedatei enthält.

## HINWEISE

* Wenn eine Aufzeichnung nicht gestartet wurde, schlägt der Befehl fehl.

*

## VERWANDTE LINKS

[Start-Transcript](Start-Transcript.md)

