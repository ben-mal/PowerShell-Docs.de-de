---
external help file: Microsoft.PowerShell.PSReadLine2.dll-Help.xml
Locale: en-US
Module Name: PSReadLine
ms.date: 06/30/2020
online version: https://docs.microsoft.com/powershell/module/psreadline/get-psreadlineoption?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSReadLineOption
ms.openlocfilehash: 3b2c789225a1d76391015c39e3fc919ba65f0a1b
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600708"
---
# <span data-ttu-id="e96a0-102">Get-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="e96a0-102">Get-PSReadLineOption</span></span>

## <span data-ttu-id="e96a0-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="e96a0-103">SYNOPSIS</span></span>
<span data-ttu-id="e96a0-104">Ruft Werte für die Optionen ab, die konfiguriert werden können.</span><span class="sxs-lookup"><span data-stu-id="e96a0-104">Gets values for the options that can be configured.</span></span>

## <span data-ttu-id="e96a0-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e96a0-105">SYNTAX</span></span>

```
Get-PSReadLineOption [<CommonParameters>]
```

## <span data-ttu-id="e96a0-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e96a0-106">DESCRIPTION</span></span>

<span data-ttu-id="e96a0-107">Das- `Get-PSReadLineOption` Cmdlet gibt den aktuellen Status der Einstellungen zurück, die mit dem `Set-PSReadLineOption` Cmdlet konfiguriert werden können.</span><span class="sxs-lookup"><span data-stu-id="e96a0-107">The `Get-PSReadLineOption` cmdlet returns the current state of the settings that can be configured by using the `Set-PSReadLineOption` cmdlet.</span></span> <span data-ttu-id="e96a0-108">Sie können das zurückgegebene-Objekt verwenden, um die **psread Line** -Optionen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="e96a0-108">You can use the returned object to change **PSReadLine** options.</span></span> <span data-ttu-id="e96a0-109">Dies bietet eine etwas einfachere Möglichkeit zum Festlegen von Syntax Farboptionen für mehrere Arten von Token.</span><span class="sxs-lookup"><span data-stu-id="e96a0-109">This provides a slightly simpler way to set syntax coloring options for multiple kinds of tokens.</span></span>

## <span data-ttu-id="e96a0-110">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="e96a0-110">EXAMPLES</span></span>

### <span data-ttu-id="e96a0-111">Beispiel 1: erhalten von Optionen und deren Werten</span><span class="sxs-lookup"><span data-stu-id="e96a0-111">Example 1: Get options and their values</span></span>

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
CommandColor                           : "`e[93m"
CommentColor                           : "`e[32m"
ContinuationPromptColor                : "`e[97m"
DefaultTokenColor                      : "`e[97m"
EmphasisColor                          : "`e[96m"
ErrorColor                             : "`e[91m"
KeywordColor                           : "`e[92m"
MemberColor                            : "`e[97m"
NumberColor                            : "`e[97m"
OperatorColor                          : "`e[90m"
ParameterColor                         : "`e[90m"
SelectionColor                         : "`e[30;107m"
StringColor                            : "`e[36m"
TypeColor                              : "`e[37m"
VariableColor                          : "`e[92m"
```

<span data-ttu-id="e96a0-112">Mit diesem Befehl wird die Liste der verfügbaren psread Line-Optionen und ihre aktuellen Werte zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e96a0-112">This command returns the list of available PSReadLine options and their current values.</span></span>

## <span data-ttu-id="e96a0-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e96a0-113">PARAMETERS</span></span>

### <span data-ttu-id="e96a0-114">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e96a0-114">CommonParameters</span></span>

<span data-ttu-id="e96a0-115">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e96a0-115">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e96a0-116">Weitere Informationen findest du unter [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e96a0-116">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e96a0-117">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="e96a0-117">INPUTS</span></span>

### <span data-ttu-id="e96a0-118">Keine</span><span class="sxs-lookup"><span data-stu-id="e96a0-118">None</span></span>

<span data-ttu-id="e96a0-119">Objekte können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="e96a0-119">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="e96a0-120">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="e96a0-120">OUTPUTS</span></span>

### <span data-ttu-id="e96a0-121">Microsoft. PowerShell. psconsolereadlineoptions</span><span class="sxs-lookup"><span data-stu-id="e96a0-121">Microsoft.PowerShell.PSConsoleReadLineOptions</span></span>

<span data-ttu-id="e96a0-122">Eine Instanz der aktuellen Optionen.</span><span class="sxs-lookup"><span data-stu-id="e96a0-122">An instance of the current options.</span></span> <span data-ttu-id="e96a0-123">Wenn Sie die Eigenschaftswerte dieses Objekts ändern, werden die Einstellungen in psleline direkt aktualisiert, ohne dass aufgerufen wird `Set-PSReadLineOption` .</span><span class="sxs-lookup"><span data-stu-id="e96a0-123">Changing the property values of this object updates the settings in PSReadLine directly without invoking `Set-PSReadLineOption`.</span></span>

## <span data-ttu-id="e96a0-124">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="e96a0-124">NOTES</span></span>

## <span data-ttu-id="e96a0-125">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="e96a0-125">RELATED LINKS</span></span>

[<span data-ttu-id="e96a0-126">Remove-psread linekeyhandler</span><span class="sxs-lookup"><span data-stu-id="e96a0-126">Remove-PSReadLineKeyHandler</span></span>](Remove-PSReadLineKeyHandler.md)

[<span data-ttu-id="e96a0-127">Get-psread linekeyhandler</span><span class="sxs-lookup"><span data-stu-id="e96a0-127">Get-PSReadLineKeyHandler</span></span>](Get-PSReadLineKeyHandler.md)

[<span data-ttu-id="e96a0-128">Set-psread lineoption</span><span class="sxs-lookup"><span data-stu-id="e96a0-128">Set-PSReadLineOption</span></span>](Set-PSReadLineOption.md)

[<span data-ttu-id="e96a0-129">Set-psread linekeyhandler</span><span class="sxs-lookup"><span data-stu-id="e96a0-129">Set-PSReadLineKeyHandler</span></span>](Set-PSReadLineKeyHandler.md)
