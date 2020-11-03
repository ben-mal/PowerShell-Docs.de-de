---
external help file: Microsoft.PowerShell.PSReadLine2.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSReadline
ms.date: 06/30/2020
online version: https://docs.microsoft.com/powershell/module/psreadline/get-psreadlineoption?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSReadLineOption
ms.openlocfilehash: 7f731014e5a240e0c756640144ff7cae5e48f051
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "93224732"
---
# Get-PSReadLineOption

## ZUSAMMENFASSUNG
Ruft Werte für die Optionen ab, die konfiguriert werden können.

## SYNTAX

```
Get-PSReadLineOption [<CommonParameters>]
```

## DESCRIPTION

Das- `Get-PSReadLineOption` Cmdlet gibt den aktuellen Status der Einstellungen zurück, die mit dem `Set-PSReadLineOption` Cmdlet konfiguriert werden können. Sie können das zurückgegebene-Objekt verwenden, um die **psread Line** -Optionen zu ändern. Dies bietet eine etwas einfachere Möglichkeit zum Festlegen von Syntax Farboptionen für mehrere Arten von Token.

## BEISPIELE

### Beispiel 1: erhalten von Optionen und deren Werten

```powershell
Get-PSReadLineOption
```

```Output
EditMode                               : Windows
AddToHistoryHandler                    : System.Func`2[System.String,System.Object]
HistoryNoDuplicates                    : True
HistorySavePath                        : C:\Users\username\AppData\Roaming\Microsoft\Windows\
                                         PowerShell\PSReadLine\ConsoleHost_history.txt
HistorySaveStyle                       : SaveIncrementally
HistorySearchCaseSensitive             : False
HistorySearchCursorMovesToEnd          : False
MaximumHistoryCount                    : 4096
ContinuationPrompt                     : >>
ExtraPromptLineCount                   : 0
PromptText                             : {> }
BellStyle                              : Audible
DingDuration                           : 50
DingTone                               : 1221
CommandsToValidateScriptBlockArguments : {ForEach-Object, %, Invoke-Command, icm...}
CommandValidationHandler               :
CompletionQueryItems                   : 100
MaximumKillRingCount                   : 10
ShowToolTips                           : True
ViModeIndicator                        : None
WordDelimiters                         : ;:,.[]{}()/\|^&*-=+'"---
AnsiEscapeTimeout                      : 100
CommandColor                           : "$([char]0x1b)[93m"
CommentColor                           : "$([char]0x1b)[32m"
ContinuationPromptColor                : "$([char]0x1b)[37m"
DefaultTokenColor                      : "$([char]0x1b)[37m"
EmphasisColor                          : "$([char]0x1b)[96m"
ErrorColor                             : "$([char]0x1b)[91m"
KeywordColor                           : "$([char]0x1b)[92m"
MemberColor                            : "$([char]0x1b)[97m"
NumberColor                            : "$([char]0x1b)[97m"
OperatorColor                          : "$([char]0x1b)[90m"
ParameterColor                         : "$([char]0x1b)[90m"
SelectionColor                         : "$([char]0x1b)[30;47m"
StringColor                            : "$([char]0x1b)[36m"
TypeColor                              : "$([char]0x1b)[37m"
VariableColor                          : "$([char]0x1b)[92m"
```

Mit diesem Befehl wird die Liste der verfügbaren psread Line-Optionen und ihre aktuellen Werte zurückgegeben.

## PARAMETERS

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine

Objekte können nicht an dieses Cmdlet weitergereicht werden.

## AUSGABEN

### Microsoft. PowerShell. psconsolereadlineoptions

Eine Instanz der aktuellen Optionen. Wenn Sie die Eigenschaftswerte dieses Objekts ändern, werden die Einstellungen in psleline direkt aktualisiert, ohne dass aufgerufen wird `Set-PSReadLineOption` .

## HINWEISE

## VERWANDTE LINKS

[Remove-psread linekeyhandler](Remove-PSReadLineKeyHandler.md)

[Get-psread linekeyhandler](Get-PSReadLineKeyHandler.md)

[Set-psread lineoption](Set-PSReadLineOption.md)

[Set-psread linekeyhandler](Set-PSReadLineKeyHandler.md)
