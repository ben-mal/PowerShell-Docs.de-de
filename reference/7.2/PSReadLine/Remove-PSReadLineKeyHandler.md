---
external help file: Microsoft.PowerShell.PSReadLine2.dll-Help.xml
Locale: en-US
Module Name: PSReadLine
ms.date: 12/07/2018
online version: https://docs.microsoft.com/powershell/module/psreadline/remove-psreadlinekeyhandler?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PSReadLineKeyHandler
ms.openlocfilehash: d280eba2e717ccfb0b896d62f42079390d1db848
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599194"
---
# <span data-ttu-id="f2b95-102">Remove-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="f2b95-102">Remove-PSReadLineKeyHandler</span></span>

## <span data-ttu-id="f2b95-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="f2b95-103">SYNOPSIS</span></span>
<span data-ttu-id="f2b95-104">Entfernt eine tastenbindung.</span><span class="sxs-lookup"><span data-stu-id="f2b95-104">Removes a key binding.</span></span>

## <span data-ttu-id="f2b95-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f2b95-105">SYNTAX</span></span>

```
Remove-PSReadLineKeyHandler [-Chord] <String[]> [-ViMode <ViMode>] [<CommonParameters>]
```

## <span data-ttu-id="f2b95-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f2b95-106">DESCRIPTION</span></span>

<span data-ttu-id="f2b95-107">Mit dem- `Remove-PSReadLineKeyHandler` Cmdlet wird eine angegebene schlüsselbindung entfernt.</span><span class="sxs-lookup"><span data-stu-id="f2b95-107">The `Remove-PSReadLineKeyHandler` cmdlet removes a specified key binding.</span></span>

## <span data-ttu-id="f2b95-108">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="f2b95-108">EXAMPLES</span></span>

### <span data-ttu-id="f2b95-109">Beispiel 1: Entfernen einer Bindung</span><span class="sxs-lookup"><span data-stu-id="f2b95-109">Example 1: Remove a binding</span></span>

```powershell
Remove-PSReadLineKeyHandler -Chord Ctrl+B
```

<span data-ttu-id="f2b95-110">Mit diesem Befehl wird die Bindung aus der Tastenkombination (oder dem Akkord) entfernt `Ctrl+B` .</span><span class="sxs-lookup"><span data-stu-id="f2b95-110">This command removes the binding from the key combination, or chord, `Ctrl+B`.</span></span> <span data-ttu-id="f2b95-111">Der `Ctrl+B` Akkord wird im Artikel erstellt `Set-PSReadLineKeyHandler` .</span><span class="sxs-lookup"><span data-stu-id="f2b95-111">The `Ctrl+B` chord is created in the `Set-PSReadLineKeyHandler` article.</span></span>

## <span data-ttu-id="f2b95-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f2b95-112">PARAMETERS</span></span>

### <span data-ttu-id="f2b95-113">-Akkord</span><span class="sxs-lookup"><span data-stu-id="f2b95-113">-Chord</span></span>

<span data-ttu-id="f2b95-114">Gibt ein Array von Schlüsseln oder Sequenzen von Schlüsseln an, die entfernt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f2b95-114">Specifies an array of keys or sequences of keys to be removed.</span></span> <span data-ttu-id="f2b95-115">Eine einzelne Bindung wird mit einer einzelnen Zeichenfolge angegeben.</span><span class="sxs-lookup"><span data-stu-id="f2b95-115">A single binding is specified by using a single string.</span></span> <span data-ttu-id="f2b95-116">Wenn die Bindung eine Sequenz von Schlüsseln ist, trennen Sie die Schlüssel durch ein Komma, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="f2b95-116">If the binding is a sequence of keys, separate the keys by a comma, as in the following example:</span></span>

`Ctrl+x,Ctrl+l`

<span data-ttu-id="f2b95-117">Dieser Parameter akzeptiert ein Array von Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="f2b95-117">This parameter accepts an array of strings.</span></span> <span data-ttu-id="f2b95-118">Jede Zeichenfolge ist eine separate Bindung und keine Sequenz von Schlüsseln für eine einzelne Bindung.</span><span class="sxs-lookup"><span data-stu-id="f2b95-118">Each string is a separate binding, not a sequence of keys for a single binding.</span></span>

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

### <span data-ttu-id="f2b95-119">-Vimode</span><span class="sxs-lookup"><span data-stu-id="f2b95-119">-ViMode</span></span>

<span data-ttu-id="f2b95-120">Geben Sie den VI-Modus an, für den die Bindung gilt.</span><span class="sxs-lookup"><span data-stu-id="f2b95-120">Specify which vi mode the binding applies to.</span></span> <span data-ttu-id="f2b95-121">Mögliche Werte sind: INSERT, Command.</span><span class="sxs-lookup"><span data-stu-id="f2b95-121">Possible values are: Insert, Command.</span></span>

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

### <span data-ttu-id="f2b95-122">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f2b95-122">CommonParameters</span></span>

<span data-ttu-id="f2b95-123">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f2b95-123">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f2b95-124">Weitere Informationen findest du unter [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f2b95-124">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f2b95-125">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="f2b95-125">INPUTS</span></span>

### <span data-ttu-id="f2b95-126">Keine</span><span class="sxs-lookup"><span data-stu-id="f2b95-126">None</span></span>

<span data-ttu-id="f2b95-127">Objekte können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="f2b95-127">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="f2b95-128">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="f2b95-128">OUTPUTS</span></span>

### <span data-ttu-id="f2b95-129">Keine</span><span class="sxs-lookup"><span data-stu-id="f2b95-129">None</span></span>

## <span data-ttu-id="f2b95-130">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="f2b95-130">NOTES</span></span>

## <span data-ttu-id="f2b95-131">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="f2b95-131">RELATED LINKS</span></span>

[<span data-ttu-id="f2b95-132">Get-psread linekeyhandler</span><span class="sxs-lookup"><span data-stu-id="f2b95-132">Get-PSReadLineKeyHandler</span></span>](Get-PSReadLineKeyHandler.md)

[<span data-ttu-id="f2b95-133">Get-psread lineoption</span><span class="sxs-lookup"><span data-stu-id="f2b95-133">Get-PSReadLineOption</span></span>](Get-PSReadLineOption.md)

[<span data-ttu-id="f2b95-134">Set-psread lineoption</span><span class="sxs-lookup"><span data-stu-id="f2b95-134">Set-PSReadLineOption</span></span>](Set-PSReadLineOption.md)

[<span data-ttu-id="f2b95-135">Set-psread linekeyhandler</span><span class="sxs-lookup"><span data-stu-id="f2b95-135">Set-PSReadLineKeyHandler</span></span>](Set-PSReadLineKeyHandler.md)

