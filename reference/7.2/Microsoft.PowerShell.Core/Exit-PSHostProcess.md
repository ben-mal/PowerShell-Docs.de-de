---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 11/06/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/exit-pshostprocess?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Exit-PSHostProcess
ms.openlocfilehash: a1a8c6fcc16bcddc3bfcdade56cd75aadd179b74
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603514"
---
# Exit-PSHostProcess

## ZUSAMMENFASSUNG
Schließt eine interaktive Sitzung mit einem lokalen Prozess.

## SYNTAX

```
Exit-PSHostProcess [<CommonParameters>]
```

## DESCRIPTION

Das `Exit-PSHostProcess` Cmdlet schließt eine interaktive Sitzung mit einem lokalen Prozess, den Sie durch Ausführen des `Enter-PSHostProcess` Cmdlets geöffnet haben. Sie führen das `Exit-PSHostProcess` Cmdlet innerhalb des Prozesses aus, wenn Sie das Debuggen oder die Problembehandlung eines Skripts abgeschlossen haben, das innerhalb eines Prozesses ausgeführt wird. Ab PowerShell 6,2 wird dieses Cmdlet auf nicht-Windows-Plattformen unterstützt.

## BEISPIELE

### Beispiel 1: Beenden eines Prozesses

```
[Process:1520]: PS>  Exit-PSHostProcess
PS>
```

In diesem Beispiel haben Sie in einem aktiven Prozess gearbeitet, um ein Skript zu debuggen, das in einem Runspace im Prozess ausgeführt wird, wie unter beschrieben `Enter-PSHostProcess` . Nachdem Sie den `exit` Befehl zum Beenden des Debuggers eingeben haben, führen Sie das `Exit-PSHostProcess` Cmdlet aus, um die interaktive Sitzung mit dem Prozess zu schließen.
Das Cmdlet schließt die Sitzung im Prozess und kehrt zur `PS C:\>` Eingabeaufforderung zurück.

## PARAMETERS

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

## AUSGABEN

## HINWEISE

## VERWANDTE LINKS

[Enter-PSHostProcess](Enter-PSHostProcess.md)

