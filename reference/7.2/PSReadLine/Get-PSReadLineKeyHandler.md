---
external help file: Microsoft.PowerShell.PSReadLine2.dll-Help.xml
Locale: en-US
Module Name: PSReadLine
ms.date: 12/07/2018
online version: https://docs.microsoft.com/powershell/module/psreadline/get-psreadlinekeyhandler?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSReadLineKeyHandler
ms.openlocfilehash: bb1e92a8f4bca96dc369b5b799c7e89245e432be
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602939"
---
# <span data-ttu-id="9ce89-102">Get-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="9ce89-102">Get-PSReadLineKeyHandler</span></span>

## <span data-ttu-id="9ce89-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="9ce89-103">SYNOPSIS</span></span>
<span data-ttu-id="9ce89-104">Ruft die gebundenen Schlüsselfunktionen für das psread Line-Modul ab.</span><span class="sxs-lookup"><span data-stu-id="9ce89-104">Gets the bound key functions for the PSReadLine module.</span></span>

## <span data-ttu-id="9ce89-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9ce89-105">SYNTAX</span></span>

### <span data-ttu-id="9ce89-106">Fulllisting (Standard)</span><span class="sxs-lookup"><span data-stu-id="9ce89-106">FullListing (default)</span></span>

```
Get-PSReadLineKeyHandler [-Bound] [-Unbound] [<CommonParameters>]
```

### <span data-ttu-id="9ce89-107">Spezificbindungen</span><span class="sxs-lookup"><span data-stu-id="9ce89-107">SpecificBindings</span></span>

```
Get-PSReadLineKeyHandler [-Chord] <String[]> [<CommonParameters>]
```

## <span data-ttu-id="9ce89-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9ce89-108">DESCRIPTION</span></span>

<span data-ttu-id="9ce89-109">Wenn kein Parameter angegeben wird, gibt die zurzeit gebundenen Schlüsselfunktionen für das psread Line-Modul zurück.</span><span class="sxs-lookup"><span data-stu-id="9ce89-109">If no parameter is specified, returns the currently bound key functions for the PSReadLine module.</span></span>

<span data-ttu-id="9ce89-110">Wenn der Parameter " **Chord** " angegeben wird, gibt das Cmdlet die spezifischen gebundenen Schlüssel zurück.</span><span class="sxs-lookup"><span data-stu-id="9ce89-110">If **Chord** parameter is specified, the cmdlet returns the specific bound keys.</span></span>

## <span data-ttu-id="9ce89-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="9ce89-111">EXAMPLES</span></span>

### <span data-ttu-id="9ce89-112">Beispiel 1: Get all Key Zuordnungen</span><span class="sxs-lookup"><span data-stu-id="9ce89-112">Example 1: Get all key mappings</span></span>

<span data-ttu-id="9ce89-113">Dieser Befehl gibt alle Schlüssel Zuordnungen zurück, gebunden und ungebunden.</span><span class="sxs-lookup"><span data-stu-id="9ce89-113">This command returns all key mappings, bound and unbound.</span></span>

```powershell
Get-PSReadLineKeyHandler -Bound -Unbound
```

```Output
Key                   Function                Description
---                   --------                -----------
Enter                 AcceptLine              Accept the input or move to the next line if input is missing a closing token.
Shift+Enter           AddLine                 Move the cursor to the next line without attempting to execute the input
Escape                RevertLine              Equivalent to undo all edits (clears the line except lines imported from history)
LeftArrow             BackwardChar            Move the cursor back one character
RightArrow            ForwardChar             Move the cursor forward one character
Ctrl+LeftArrow        BackwardWord            Move the cursor to the beginning of the current or previous word
Ctrl+RightArrow       NextWord                Move the cursor forward to the start of the next word
Shift+LeftArrow       SelectBackwardChar      Adjust the current selection to include the previous character
Shift+RightArrow      SelectForwardChar       Adjust the current selection to include the next character
Ctrl+Shift+LeftArrow  SelectBackwardWord      Adjust the current selection to include the previous word
Ctrl+Shift+RightArrow SelectNextWord          Adjust the current selection to include the next word
UpArrow               PreviousHistory         Replace the input with the previous item in the history
DownArrow             NextHistory             Replace the input with the next item in the history
Home                  BeginningOfLine         Move the cursor to the beginning of the line
End                   EndOfLine               Move the cursor to the end of the line
Shift+Home            SelectBackwardsLine     Adjust the current selection to include from the cursor to the end of the line
Shift+End             SelectLine              Adjust the current selection to include from the cursor to the start of the line
Delete                DeleteChar              Delete the character under the cursor
Backspace             BackwardDeleteChar      Delete the character before the cursor
Ctrl+Spacebar         MenuComplete            Complete the input if there is a single completion, otherwise complete the input by selecting from a menu o...
Tab                   TabCompleteNext         Complete the input using the next completion
Shift+Tab             TabCompletePrevious     Complete the input using the previous completion
Ctrl+a                SelectAll               Select the entire line. Moves the cursor to the end of the line
Ctrl+c                CopyOrCancelLine        Either copy selected text to the clipboard, or if no text is selected, cancel editing the line with Cancel...
Ctrl+C                Copy                    Copy selected region to the system clipboard.  If no region is selected, copy the whole line
Ctrl+l                ClearScreen             Clear the screen and redraw the current line at the top of the screen
Ctrl+r                ReverseSearchHistory    Search history backwards interactively
...
```

### <span data-ttu-id="9ce89-114">Beispiel 2: erhalten von gebundenen Schlüsseln</span><span class="sxs-lookup"><span data-stu-id="9ce89-114">Example 2: Get bound keys</span></span>

<span data-ttu-id="9ce89-115">Mit diesem Befehl werden nur gebundene Schlüssel und Tastenkombinationen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9ce89-115">This command returns only bound keys and key combinations.</span></span>

```powershell
Get-PSReadLineKeyHandler
```

```Output
Key                   Function                Description
---                   --------                -----------
Enter                 AcceptLine              Accept the input or move to the next line if input is missing a closing token.
Shift+Enter           AddLine                 Move the cursor to the next line without attempting to execute the input
Escape                RevertLine              Equivalent to undo all edits (clears the line except lines imported from history)
LeftArrow             BackwardChar            Move the cursor back one character
RightArrow            ForwardChar             Move the cursor forward one character
Ctrl+LeftArrow        BackwardWord            Move the cursor to the beginning of the current or previous word
Ctrl+RightArrow       NextWord                Move the cursor forward to the start of the next word
Shift+LeftArrow       SelectBackwardChar      Adjust the current selection to include the previous character
Shift+RightArrow      SelectForwardChar       Adjust the current selection to include the next character
Ctrl+Shift+LeftArrow  SelectBackwardWord      Adjust the current selection to include the previous word
Ctrl+Shift+RightArrow SelectNextWord          Adjust the current selection to include the next word
UpArrow               PreviousHistory         Replace the input with the previous item in the history
DownArrow             NextHistory             Replace the input with the next item in the history
Home                  BeginningOfLine         Move the cursor to the beginning of the line
End                   EndOfLine               Move the cursor to the end of the line
Shift+Home            SelectBackwardsLine     Adjust the current selection to include from the cursor to the end of the line
Shift+End             SelectLine              Adjust the current selection to include from the cursor to the start of the line
Delete                DeleteChar              Delete the character under the cursor
Backspace             BackwardDeleteChar      Delete the character before the cursor
Ctrl+Spacebar         MenuComplete            Complete the input if there is a single completion, otherwise complete the input by selecting from a menu o...
Tab                   TabCompleteNext         Complete the input using the next completion
...
```

### <span data-ttu-id="9ce89-116">Beispiel 3: Get Specific Key-Bindungen</span><span class="sxs-lookup"><span data-stu-id="9ce89-116">Example 3: Get specific key bindings</span></span>

<span data-ttu-id="9ce89-117">Mit diesem Befehl werden nur die Bindungen für die angegebenen Schlüssel zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9ce89-117">This command returns only the bindings for the specified keys.</span></span>

```powershell
Get-PSReadLineKeyHandler -Chord Enter, Shift+Enter
```

```Output
Key         Function   Description
---         --------   -----------
Enter       AcceptLine Accept the input or move to the next line if input is missing a closing token.
Shift+Enter AddLine    Move the cursor to the next line without attempting to execute the input
...
```

## <span data-ttu-id="9ce89-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9ce89-118">PARAMETERS</span></span>

### <span data-ttu-id="9ce89-119">-Gebunden</span><span class="sxs-lookup"><span data-stu-id="9ce89-119">-Bound</span></span>

<span data-ttu-id="9ce89-120">Gibt an, dass dieses Cmdlet Funktionen zurückgibt, die gebunden sind.</span><span class="sxs-lookup"><span data-stu-id="9ce89-120">Indicates that this cmdlet returns functions that are bound.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: FullListing
Aliases:

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9ce89-121">-Ungebunden</span><span class="sxs-lookup"><span data-stu-id="9ce89-121">-Unbound</span></span>

<span data-ttu-id="9ce89-122">Gibt an, dass dieses Cmdlet Funktionen zurückgibt, die nicht gebunden sind.</span><span class="sxs-lookup"><span data-stu-id="9ce89-122">Indicates that this cmdlet returns functions that are unbound.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: FullListing
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9ce89-123">-Akkord</span><span class="sxs-lookup"><span data-stu-id="9ce89-123">-Chord</span></span>

<span data-ttu-id="9ce89-124">Gibt nur Funktionen zurück, die an bestimmte Schlüssel oder Sequenzen gebunden sind.</span><span class="sxs-lookup"><span data-stu-id="9ce89-124">Return only functions bound to specific keys or sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: SpecificBindings
Aliases: Key

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9ce89-125">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="9ce89-125">CommonParameters</span></span>

<span data-ttu-id="9ce89-126">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9ce89-126">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9ce89-127">Weitere Informationen findest du unter [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="9ce89-127">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9ce89-128">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="9ce89-128">INPUTS</span></span>

### <span data-ttu-id="9ce89-129">Keine</span><span class="sxs-lookup"><span data-stu-id="9ce89-129">None</span></span>

<span data-ttu-id="9ce89-130">Objekte können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="9ce89-130">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="9ce89-131">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="9ce89-131">OUTPUTS</span></span>

### <span data-ttu-id="9ce89-132">Microsoft. PowerShell. KeyHandler</span><span class="sxs-lookup"><span data-stu-id="9ce89-132">Microsoft.PowerShell.KeyHandler</span></span>

## <span data-ttu-id="9ce89-133">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="9ce89-133">NOTES</span></span>

## <span data-ttu-id="9ce89-134">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="9ce89-134">RELATED LINKS</span></span>

[<span data-ttu-id="9ce89-135">Remove-psread linekeyhandler</span><span class="sxs-lookup"><span data-stu-id="9ce89-135">Remove-PSReadLineKeyHandler</span></span>](Remove-PSReadLineKeyHandler.md)

[<span data-ttu-id="9ce89-136">Get-psread lineoption</span><span class="sxs-lookup"><span data-stu-id="9ce89-136">Get-PSReadLineOption</span></span>](Get-PSReadLineOption.md)

[<span data-ttu-id="9ce89-137">Set-psread lineoption</span><span class="sxs-lookup"><span data-stu-id="9ce89-137">Set-PSReadLineOption</span></span>](Set-PSReadLineOption.md)

[<span data-ttu-id="9ce89-138">Set-psread linekeyhandler</span><span class="sxs-lookup"><span data-stu-id="9ce89-138">Set-PSReadLineKeyHandler</span></span>](Set-PSReadLineKeyHandler.md)

