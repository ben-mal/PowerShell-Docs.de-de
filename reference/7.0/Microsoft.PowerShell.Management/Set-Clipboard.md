---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 08/09/2019
online version: https://go.microsoft.com/fwlink/?linkid=526220
schema: 2.0.0
title: Set-Clipboard
ms.openlocfilehash: 271d9191a0968b03b1e7ec3d283eacc36e633516
ms.sourcegitcommit: fcf7bd222f5ee3fdbe21ffddcae47050cffe7e42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "93239801"
---
# <span data-ttu-id="1c3ef-103">Set-Clipboard</span><span class="sxs-lookup"><span data-stu-id="1c3ef-103">Set-Clipboard</span></span>

## <span data-ttu-id="1c3ef-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="1c3ef-104">SYNOPSIS</span></span>
<span data-ttu-id="1c3ef-105">Legt den Inhalt der Zwischenablage fest.</span><span class="sxs-lookup"><span data-stu-id="1c3ef-105">Sets the contents of the clipboard.</span></span>

## <span data-ttu-id="1c3ef-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1c3ef-106">SYNTAX</span></span>

```
Set-Clipboard [-Value] <string[]> [-Append] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="1c3ef-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1c3ef-107">DESCRIPTION</span></span>

<span data-ttu-id="1c3ef-108">Mit dem- `Set-Clipboard` Cmdlet wird der Inhalt der Zwischenablage festgelegt.</span><span class="sxs-lookup"><span data-stu-id="1c3ef-108">The `Set-Clipboard` cmdlet sets the contents of the clipboard.</span></span>

> [!NOTE]
> <span data-ttu-id="1c3ef-109">Unter Linux erfordert dieses Cmdlet, dass sich das `xclip` Hilfsprogramm im Pfad befinden muss.</span><span class="sxs-lookup"><span data-stu-id="1c3ef-109">On Linux, this cmdlet requires the `xclip` utility to be in the path.</span></span>

## <span data-ttu-id="1c3ef-110">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="1c3ef-110">EXAMPLES</span></span>

### <span data-ttu-id="1c3ef-111">Beispiel 1: Kopieren von Text in die Zwischenablage</span><span class="sxs-lookup"><span data-stu-id="1c3ef-111">Example 1: Copy text to the clipboard</span></span>

```powershell
Set-Clipboard -Value "This is a test string"
```

## <span data-ttu-id="1c3ef-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1c3ef-112">PARAMETERS</span></span>

### <span data-ttu-id="1c3ef-113">-Anfügen</span><span class="sxs-lookup"><span data-stu-id="1c3ef-113">-Append</span></span>

<span data-ttu-id="1c3ef-114">Gibt an, dass das Cmdlet die Zwischenablage nicht löscht und Inhalt an ihn anfügt.</span><span class="sxs-lookup"><span data-stu-id="1c3ef-114">Indicates that the cmdlet does not clear the clipboard and appends content to it.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1c3ef-115">-Confirm</span><span class="sxs-lookup"><span data-stu-id="1c3ef-115">-Confirm</span></span>

<span data-ttu-id="1c3ef-116">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="1c3ef-116">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1c3ef-117">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="1c3ef-117">-WhatIf</span></span>

<span data-ttu-id="1c3ef-118">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1c3ef-118">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="1c3ef-119">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1c3ef-119">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1c3ef-120">-Value</span><span class="sxs-lookup"><span data-stu-id="1c3ef-120">-Value</span></span>

<span data-ttu-id="1c3ef-121">Die Zeichen folgen Werte, die der Zwischenablage hinzugefügt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1c3ef-121">The string values to be added to the clipboard.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="1c3ef-122">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="1c3ef-122">CommonParameters</span></span>

<span data-ttu-id="1c3ef-123">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1c3ef-123">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1c3ef-124">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1c3ef-124">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1c3ef-125">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="1c3ef-125">INPUTS</span></span>

### <span data-ttu-id="1c3ef-126">System.String[]</span><span class="sxs-lookup"><span data-stu-id="1c3ef-126">System.String[]</span></span>

## <span data-ttu-id="1c3ef-127">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="1c3ef-127">OUTPUTS</span></span>

## <span data-ttu-id="1c3ef-128">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="1c3ef-128">NOTES</span></span>

<span data-ttu-id="1c3ef-129">In seltenen Fällen, in denen `Set-Clipboard` Sie mit einer hohen Anzahl von Werten in schneller Folge wie in einer-Schleife verwenden, erhalten Sie möglicherweise sporadisch einen leeren Wert aus der Zwischenablage.</span><span class="sxs-lookup"><span data-stu-id="1c3ef-129">In rare cases when using `Set-Clipboard` with a high number of values in rapid succession, like in a loop, you might sporadically get a blank value from the clipboard.</span></span> <span data-ttu-id="1c3ef-130">Dies kann mithilfe von `Start-Sleep -Milliseconds 1` in der-Schleife korrigiert werden.</span><span class="sxs-lookup"><span data-stu-id="1c3ef-130">This can be fixed by using `Start-Sleep -Milliseconds 1` in the loop.</span></span>

## <span data-ttu-id="1c3ef-131">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="1c3ef-131">RELATED LINKS</span></span>

[<span data-ttu-id="1c3ef-132">Get-Clipboard</span><span class="sxs-lookup"><span data-stu-id="1c3ef-132">Get-Clipboard</span></span>](Get-Clipboard.md)
