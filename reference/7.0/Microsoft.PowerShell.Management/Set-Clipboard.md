---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-clipboard?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Clipboard
ms.openlocfilehash: efb24b14122ad37043636d999afaa4199eb3097b
ms.sourcegitcommit: 7b376314e7640c39a53aac9f0db8bb935514a960
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2020
ms.locfileid: "96564372"
---
# <span data-ttu-id="25735-102">Set-Clipboard</span><span class="sxs-lookup"><span data-stu-id="25735-102">Set-Clipboard</span></span>

## <span data-ttu-id="25735-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="25735-103">SYNOPSIS</span></span>
<span data-ttu-id="25735-104">Legt den Inhalt der Zwischenablage fest.</span><span class="sxs-lookup"><span data-stu-id="25735-104">Sets the contents of the clipboard.</span></span>

## <span data-ttu-id="25735-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="25735-105">SYNTAX</span></span>

```
Set-Clipboard [-Value] <string[]> [-Append] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="25735-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="25735-106">DESCRIPTION</span></span>

<span data-ttu-id="25735-107">Mit dem- `Set-Clipboard` Cmdlet wird der Inhalt der Zwischenablage festgelegt.</span><span class="sxs-lookup"><span data-stu-id="25735-107">The `Set-Clipboard` cmdlet sets the contents of the clipboard.</span></span>

> [!NOTE]
> <span data-ttu-id="25735-108">Unter Linux erfordert dieses Cmdlet, dass sich das `xclip` Hilfsprogramm im Pfad befinden muss.</span><span class="sxs-lookup"><span data-stu-id="25735-108">On Linux, this cmdlet requires the `xclip` utility to be in the path.</span></span>

## <span data-ttu-id="25735-109">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="25735-109">EXAMPLES</span></span>

### <span data-ttu-id="25735-110">Beispiel 1: Kopieren von Text in die Zwischenablage</span><span class="sxs-lookup"><span data-stu-id="25735-110">Example 1: Copy text to the clipboard</span></span>

```powershell
Set-Clipboard -Value "This is a test string"
```

### <span data-ttu-id="25735-111">Beispiel 2: Kopieren des Inhalts einer Datei in die Zwischenablage</span><span class="sxs-lookup"><span data-stu-id="25735-111">Example 2: Copy the contents of a file to the clipboard</span></span>

<span data-ttu-id="25735-112">In diesem Beispiel wird der Inhalt einer Datei in die Zwischenablage geleitet.</span><span class="sxs-lookup"><span data-stu-id="25735-112">This example pipes the contents of a file to the clipboard.</span></span> <span data-ttu-id="25735-113">In diesem Beispiel erhalten wir einen öffentlichen SSH-Schlüssel, damit er in eine andere Anwendung wie GitHub eingefügt werden kann.</span><span class="sxs-lookup"><span data-stu-id="25735-113">In this example, we are getting a public ssh key so that it can be pasted into another application, like GitHub.</span></span>

```powershell
Get-Content C:\Users\user1\.ssh\id_ed25519.pub | Set-Clipboard
```

## <span data-ttu-id="25735-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="25735-114">PARAMETERS</span></span>

### <span data-ttu-id="25735-115">-Anfügen</span><span class="sxs-lookup"><span data-stu-id="25735-115">-Append</span></span>

<span data-ttu-id="25735-116">Gibt an, dass das Cmdlet die Zwischenablage nicht löscht und Inhalt an ihn anfügt.</span><span class="sxs-lookup"><span data-stu-id="25735-116">Indicates that the cmdlet does not clear the clipboard and appends content to it.</span></span>

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

### <span data-ttu-id="25735-117">-Confirm</span><span class="sxs-lookup"><span data-stu-id="25735-117">-Confirm</span></span>

<span data-ttu-id="25735-118">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="25735-118">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="25735-119">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="25735-119">-WhatIf</span></span>

<span data-ttu-id="25735-120">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="25735-120">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="25735-121">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="25735-121">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="25735-122">-Value</span><span class="sxs-lookup"><span data-stu-id="25735-122">-Value</span></span>

<span data-ttu-id="25735-123">Die Zeichen folgen Werte, die der Zwischenablage hinzugefügt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="25735-123">The string values to be added to the clipboard.</span></span>

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

### <span data-ttu-id="25735-124">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="25735-124">CommonParameters</span></span>

<span data-ttu-id="25735-125">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="25735-125">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="25735-126">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="25735-126">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="25735-127">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="25735-127">INPUTS</span></span>

### <span data-ttu-id="25735-128">System.String[]</span><span class="sxs-lookup"><span data-stu-id="25735-128">System.String[]</span></span>

## <span data-ttu-id="25735-129">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="25735-129">OUTPUTS</span></span>

## <span data-ttu-id="25735-130">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="25735-130">NOTES</span></span>

<span data-ttu-id="25735-131">In seltenen Fällen, in denen `Set-Clipboard` Sie mit einer hohen Anzahl von Werten in schneller Folge wie in einer-Schleife verwenden, erhalten Sie möglicherweise sporadisch einen leeren Wert aus der Zwischenablage.</span><span class="sxs-lookup"><span data-stu-id="25735-131">In rare cases when using `Set-Clipboard` with a high number of values in rapid succession, like in a loop, you might sporadically get a blank value from the clipboard.</span></span> <span data-ttu-id="25735-132">Dies kann mithilfe von `Start-Sleep -Milliseconds 1` in der-Schleife korrigiert werden.</span><span class="sxs-lookup"><span data-stu-id="25735-132">This can be fixed by using `Start-Sleep -Milliseconds 1` in the loop.</span></span>

## <span data-ttu-id="25735-133">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="25735-133">RELATED LINKS</span></span>

[<span data-ttu-id="25735-134">Get-Clipboard</span><span class="sxs-lookup"><span data-stu-id="25735-134">Get-Clipboard</span></span>](Get-Clipboard.md)
