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
# <span data-ttu-id="c52bd-103">Get-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="c52bd-103">Get-PSReadLineOption</span></span>

## <span data-ttu-id="c52bd-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="c52bd-104">SYNOPSIS</span></span>
<span data-ttu-id="c52bd-105">Ruft Werte für die Optionen ab, die konfiguriert werden können.</span><span class="sxs-lookup"><span data-stu-id="c52bd-105">Gets values for the options that can be configured.</span></span>

## <span data-ttu-id="c52bd-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c52bd-106">SYNTAX</span></span>

```
Get-PSReadLineOption [<CommonParameters>]
```

## <span data-ttu-id="c52bd-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c52bd-107">DESCRIPTION</span></span>

<span data-ttu-id="c52bd-108">Das- `Get-PSReadLineOption` Cmdlet gibt den aktuellen Status der Einstellungen zurück, die mit dem `Set-PSReadLineOption` Cmdlet konfiguriert werden können.</span><span class="sxs-lookup"><span data-stu-id="c52bd-108">The `Get-PSReadLineOption` cmdlet returns the current state of the settings that can be configured by using the `Set-PSReadLineOption` cmdlet.</span></span> <span data-ttu-id="c52bd-109">Sie können das zurückgegebene-Objekt verwenden, um die **psread Line** -Optionen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="c52bd-109">You can use the returned object to change **PSReadLine** options.</span></span> <span data-ttu-id="c52bd-110">Dies bietet eine etwas einfachere Möglichkeit zum Festlegen von Syntax Farboptionen für mehrere Arten von Token.</span><span class="sxs-lookup"><span data-stu-id="c52bd-110">This provides a slightly simpler way to set syntax coloring options for multiple kinds of tokens.</span></span>

## <span data-ttu-id="c52bd-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="c52bd-111">EXAMPLES</span></span>

### <span data-ttu-id="c52bd-112">Beispiel 1: erhalten von Optionen und deren Werten</span><span class="sxs-lookup"><span data-stu-id="c52bd-112">Example 1: Get options and their values</span></span>

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

<span data-ttu-id="c52bd-113">Mit diesem Befehl wird die Liste der verfügbaren psread Line-Optionen und ihre aktuellen Werte zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c52bd-113">This command returns the list of available PSReadLine options and their current values.</span></span>

## <span data-ttu-id="c52bd-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c52bd-114">PARAMETERS</span></span>

### <span data-ttu-id="c52bd-115">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c52bd-115">CommonParameters</span></span>

<span data-ttu-id="c52bd-116">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c52bd-116">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c52bd-117">Weitere Informationen findest du unter [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c52bd-117">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c52bd-118">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="c52bd-118">INPUTS</span></span>

### <span data-ttu-id="c52bd-119">Keine</span><span class="sxs-lookup"><span data-stu-id="c52bd-119">None</span></span>

<span data-ttu-id="c52bd-120">Objekte können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="c52bd-120">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="c52bd-121">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="c52bd-121">OUTPUTS</span></span>

### <span data-ttu-id="c52bd-122">Microsoft. PowerShell. psconsolereadlineoptions</span><span class="sxs-lookup"><span data-stu-id="c52bd-122">Microsoft.PowerShell.PSConsoleReadLineOptions</span></span>

<span data-ttu-id="c52bd-123">Eine Instanz der aktuellen Optionen.</span><span class="sxs-lookup"><span data-stu-id="c52bd-123">An instance of the current options.</span></span> <span data-ttu-id="c52bd-124">Wenn Sie die Eigenschaftswerte dieses Objekts ändern, werden die Einstellungen in psleline direkt aktualisiert, ohne dass aufgerufen wird `Set-PSReadLineOption` .</span><span class="sxs-lookup"><span data-stu-id="c52bd-124">Changing the property values of this object updates the settings in PSReadLine directly without invoking `Set-PSReadLineOption`.</span></span>

## <span data-ttu-id="c52bd-125">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="c52bd-125">NOTES</span></span>

## <span data-ttu-id="c52bd-126">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="c52bd-126">RELATED LINKS</span></span>

[<span data-ttu-id="c52bd-127">Remove-psread linekeyhandler</span><span class="sxs-lookup"><span data-stu-id="c52bd-127">Remove-PSReadLineKeyHandler</span></span>](Remove-PSReadLineKeyHandler.md)

[<span data-ttu-id="c52bd-128">Get-psread linekeyhandler</span><span class="sxs-lookup"><span data-stu-id="c52bd-128">Get-PSReadLineKeyHandler</span></span>](Get-PSReadLineKeyHandler.md)

[<span data-ttu-id="c52bd-129">Set-psread lineoption</span><span class="sxs-lookup"><span data-stu-id="c52bd-129">Set-PSReadLineOption</span></span>](Set-PSReadLineOption.md)

[<span data-ttu-id="c52bd-130">Set-psread linekeyhandler</span><span class="sxs-lookup"><span data-stu-id="c52bd-130">Set-PSReadLineKeyHandler</span></span>](Set-PSReadLineKeyHandler.md)
