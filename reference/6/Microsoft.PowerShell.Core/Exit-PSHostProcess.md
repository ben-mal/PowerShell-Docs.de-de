---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/exit-pshostprocess?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Exit-PSHostProcess
ms.openlocfilehash: 0f076d21ce590b4f1d3eb5b06e891d753dbea638
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "93200840"
---
# Exit-PSHostProcess

## ZUSAMMENFASSUNG
Schließt eine interaktive Sitzung mit einem lokalen Prozess.

## SYNTAX

```
Exit-PSHostProcess [<CommonParameters>]
```

## DESCRIPTION

Das " **Exit-pshostprocess"-** Cmdlet schließt eine interaktive Sitzung mit einem lokalen Prozess, den Sie durch Ausführen des Cmdlets "Enter-PSHostProcess" geöffnet haben. Sie führen das Cmdlet **Exit-pshostprocess** innerhalb des Prozesses aus, wenn Sie das Debuggen abgeschlossen haben oder ein Skript ausführen möchten, das innerhalb eines Prozesses ausgeführt wird.

## BEISPIELE

### Beispiel 1: Beenden eines Prozesses

```
[Process:1520]: PS>  Exit-PSHostProcess
PS>
```

In diesem Beispiel haben Sie in einem aktiven Prozess gearbeitet, um ein Skript zu debuggen, das in einem Runspace im Prozess ausgeführt wird, wie in Enter-pshostprocess beschrieben. Nachdem Sie den Befehl **Exit** zum Beenden des Debuggers eingeben haben, führen Sie das Cmdlet **Exit-pshostprocess** aus, um die interaktive Sitzung mit dem Prozess zu schließen.
Das Cmdlet schließt die Sitzung im Prozess und kehrt zur PS C:- \\ \> Eingabeaufforderung zurück.

## PARAMETERS

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

## AUSGABEN

## HINWEISE

## VERWANDTE LINKS

[Enter-PSHostProcess](Enter-PSHostProcess.md)
