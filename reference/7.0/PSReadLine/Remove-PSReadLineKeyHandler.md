---
external help file: Microsoft.PowerShell.PSReadLine2.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSReadLine
ms.date: 12/07/2018
online version: https://docs.microsoft.com/powershell/module/psreadline/remove-psreadlinekeyhandler?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PSReadLineKeyHandler
ms.openlocfilehash: 1c6a21880bba0f074388c6e32baa8e1c7e93413d
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "93225063"
---
# <span data-ttu-id="60822-103">Remove-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="60822-103">Remove-PSReadLineKeyHandler</span></span>

## <span data-ttu-id="60822-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="60822-104">SYNOPSIS</span></span>
<span data-ttu-id="60822-105">Entfernt eine tastenbindung.</span><span class="sxs-lookup"><span data-stu-id="60822-105">Removes a key binding.</span></span>

## <span data-ttu-id="60822-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="60822-106">SYNTAX</span></span>

```
Remove-PSReadLineKeyHandler [-Chord] <String[]> [-ViMode <ViMode>] [<CommonParameters>]
```

## <span data-ttu-id="60822-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="60822-107">DESCRIPTION</span></span>

<span data-ttu-id="60822-108">Mit dem- `Remove-PSReadLineKeyHandler` Cmdlet wird eine angegebene schlüsselbindung entfernt.</span><span class="sxs-lookup"><span data-stu-id="60822-108">The `Remove-PSReadLineKeyHandler` cmdlet removes a specified key binding.</span></span>

## <span data-ttu-id="60822-109">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="60822-109">EXAMPLES</span></span>

### <span data-ttu-id="60822-110">Beispiel 1: Entfernen einer Bindung</span><span class="sxs-lookup"><span data-stu-id="60822-110">Example 1: Remove a binding</span></span>

```powershell
Remove-PSReadLineKeyHandler -Chord Ctrl+B
```

<span data-ttu-id="60822-111">Mit diesem Befehl wird die Bindung aus der Tastenkombination (oder dem Akkord) entfernt `Ctrl+B` .</span><span class="sxs-lookup"><span data-stu-id="60822-111">This command removes the binding from the key combination, or chord, `Ctrl+B`.</span></span> <span data-ttu-id="60822-112">Der `Ctrl+B` Akkord wird im Artikel erstellt `Set-PSReadLineKeyHandler` .</span><span class="sxs-lookup"><span data-stu-id="60822-112">The `Ctrl+B` chord is created in the `Set-PSReadLineKeyHandler` article.</span></span>

## <span data-ttu-id="60822-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="60822-113">PARAMETERS</span></span>

### <span data-ttu-id="60822-114">-Akkord</span><span class="sxs-lookup"><span data-stu-id="60822-114">-Chord</span></span>

<span data-ttu-id="60822-115">Gibt ein Array von Schlüsseln oder Sequenzen von Schlüsseln an, die entfernt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="60822-115">Specifies an array of keys or sequences of keys to be removed.</span></span> <span data-ttu-id="60822-116">Eine einzelne Bindung wird mit einer einzelnen Zeichenfolge angegeben.</span><span class="sxs-lookup"><span data-stu-id="60822-116">A single binding is specified by using a single string.</span></span> <span data-ttu-id="60822-117">Wenn die Bindung eine Sequenz von Schlüsseln ist, trennen Sie die Schlüssel durch ein Komma, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="60822-117">If the binding is a sequence of keys, separate the keys by a comma, as in the following example:</span></span>

`Ctrl+x,Ctrl+l`

<span data-ttu-id="60822-118">Dieser Parameter akzeptiert ein Array von Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="60822-118">This parameter accepts an array of strings.</span></span> <span data-ttu-id="60822-119">Jede Zeichenfolge ist eine separate Bindung und keine Sequenz von Schlüsseln für eine einzelne Bindung.</span><span class="sxs-lookup"><span data-stu-id="60822-119">Each string is a separate binding, not a sequence of keys for a single binding.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Key

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="60822-120">-Vimode</span><span class="sxs-lookup"><span data-stu-id="60822-120">-ViMode</span></span>

<span data-ttu-id="60822-121">Geben Sie den VI-Modus an, für den die Bindung gilt.</span><span class="sxs-lookup"><span data-stu-id="60822-121">Specify which vi mode the binding applies to.</span></span> <span data-ttu-id="60822-122">Mögliche Werte sind: INSERT, Command.</span><span class="sxs-lookup"><span data-stu-id="60822-122">Possible values are: Insert, Command.</span></span>

```yaml
Type: Microsoft.PowerShell.ViMode
Parameter Sets: (All)
Aliases:
Accepted values: Insert, Command

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="60822-123">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="60822-123">CommonParameters</span></span>

<span data-ttu-id="60822-124">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="60822-124">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="60822-125">Weitere Informationen findest du unter [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="60822-125">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="60822-126">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="60822-126">INPUTS</span></span>

### <span data-ttu-id="60822-127">Keine</span><span class="sxs-lookup"><span data-stu-id="60822-127">None</span></span>

<span data-ttu-id="60822-128">Objekte können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="60822-128">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="60822-129">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="60822-129">OUTPUTS</span></span>

### <span data-ttu-id="60822-130">Keine</span><span class="sxs-lookup"><span data-stu-id="60822-130">None</span></span>

## <span data-ttu-id="60822-131">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="60822-131">NOTES</span></span>

## <span data-ttu-id="60822-132">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="60822-132">RELATED LINKS</span></span>

[<span data-ttu-id="60822-133">Get-psread linekeyhandler</span><span class="sxs-lookup"><span data-stu-id="60822-133">Get-PSReadLineKeyHandler</span></span>](Get-PSReadLineKeyHandler.md)

[<span data-ttu-id="60822-134">Get-psread lineoption</span><span class="sxs-lookup"><span data-stu-id="60822-134">Get-PSReadLineOption</span></span>](Get-PSReadLineOption.md)

[<span data-ttu-id="60822-135">Set-psread lineoption</span><span class="sxs-lookup"><span data-stu-id="60822-135">Set-PSReadLineOption</span></span>](Set-PSReadLineOption.md)

[<span data-ttu-id="60822-136">Set-psread linekeyhandler</span><span class="sxs-lookup"><span data-stu-id="60822-136">Set-PSReadLineKeyHandler</span></span>](Set-PSReadLineKeyHandler.md)
