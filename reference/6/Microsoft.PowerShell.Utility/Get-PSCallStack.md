---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-pscallstack?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSCallStack
ms.openlocfilehash: 0052543842f97dc1a19caae15222fd1b97d49902
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "93200856"
---
# Get-PSCallStack

## ZUSAMMENFASSUNG
Zeigt die aktuelle Aufrufliste an.

## SYNTAX

```
Get-PSCallStack [<CommonParameters>]
```

## DESCRIPTION

Das **Get-pscallstack-** Cmdlet zeigt die aktuelle-aufrufste an.

Obwohl Sie für die Verwendung mit dem PowerShell-Debugger konzipiert ist, können Sie dieses Cmdlet verwenden, um die aufrufsstapel in einem Skript oder einer Funktion außerhalb des Debuggers anzuzeigen.

Um einen **Get-pscallstack** -Befehl im Debugger auszuführen, geben Sie `k` oder ein `Get-PSCallStack` .

## BEISPIELE

### Beispiel 1: Abrufen der aufrufsstapel für eine Funktion

```
PS C:\> function my-alias {
$p = $args[0]
Get-Alias | where {$_.definition -like "*$p"} | format-table definition, name -auto
}
PS C:\ps-test> Set-PSBreakpoint -Command my-alias
Command    : my-alias
Action     :
Enabled    : True
HitCount   : 0
Id         : 0
Script     : prompt PS C:\> my-alias Get-Content

Entering debug mode. Use h or ? for help.
Hit Command breakpoint on 'prompt:my-alias'
my-alias get-content
[DBG]: PS C:\ps-test> s
$p = $args[0]
DEBUG: Stepped to ':    $p = $args[0]    '
[DBG]: PS C:\ps-test> s
get-alias | Where {$_.Definition -like "*$p*"} | format-table Definition,
[DBG]: PS C:\ps-test>get-pscallstack

Name        CommandLineParameters         UnboundArguments              Location
----        ---------------------         ----------------              --------
prompt      {}                            {}                            prompt
my-alias    {}                            {get-content}                 prompt
prompt      {}                            {}                            prompt PS C:\> [DBG]: PS C:\ps-test> o
Definition  Name
----------  ----
Get-Content gc
Get-Content cat
Get-Content type
```

Dieser Befehl verwendet das **Get-pscallstack-** Cmdlet, um die Aufrufe für "My-Alias" anzuzeigen, eine einfache Funktion, die die Aliase für einen Cmdlet-Namen abruft.

Der erste Befehl gibt die Funktion an der PowerShell-Eingabeaufforderung ein.
Der zweite Befehl verwendet das Set-PSBreakpoint-Cmdlet um einen Haltepunkt für die My-Alias-Funktion festzulegen.
Der dritte Befehl verwendet die My-Alias-Funktion, um alle Aliase in der aktuellen Sitzung für das Get-Content-Cmdlet abzurufen.

Der Debugger unterbricht den Funktionsaufruf.
Zwei aufeinander folgende step-into (s)-Befehle beginnen, die Funktion zeilenweise auszuführen.
Anschließend wird ein **Get-pscallstack-** Befehl verwendet, um die-Rückruf Stapel abzurufen.

Der letzte Befehl ist ein Step-Out (o)-Befehl, der den Debugger beendet und das Skript bis zu seinem Abschluss weiter ausführt.

## PARAMETERS

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine

Objekte können nicht an dieses Cmdlet weitergereicht werden.

## AUSGABEN

### System. Management. Automation. callstackframe

**Get-pscallstack** gibt ein Objekt zurück, das die Elemente in der aufrufsstapel darstellt.

## HINWEISE

## VERWANDTE LINKS

[Disable-PSBreakpoint](Disable-PSBreakpoint.md)

[Enable-PSBreakpoint](Enable-PSBreakpoint.md)

[Format-Table](Format-Table.md)

[Get-PSBreakpoint](Get-PSBreakpoint.md)

[Remove-PSBreakpoint](Remove-PSBreakpoint.md)

[Set-PSBreakpoint](Set-PSBreakpoint.md)
