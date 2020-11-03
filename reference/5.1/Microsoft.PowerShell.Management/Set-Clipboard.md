---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-clipboard?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Clipboard
ms.openlocfilehash: f3230c247296d5fd907d580e719cbbbc560183a9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214468"
---
# <span data-ttu-id="88e2e-103">Set-Clipboard</span><span class="sxs-lookup"><span data-stu-id="88e2e-103">Set-Clipboard</span></span>

## <span data-ttu-id="88e2e-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="88e2e-104">SYNOPSIS</span></span>
<span data-ttu-id="88e2e-105">Legt den aktuellen Windows-Zwischenablage Eintrag fest.</span><span class="sxs-lookup"><span data-stu-id="88e2e-105">Sets the current Windows clipboard entry.</span></span>

## <span data-ttu-id="88e2e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="88e2e-106">SYNTAX</span></span>

### <span data-ttu-id="88e2e-107">Zeichenfolge (Standard)</span><span class="sxs-lookup"><span data-stu-id="88e2e-107">String (Default)</span></span>

```
Set-Clipboard [-Append] [-AsHtml] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="88e2e-108">Wert</span><span class="sxs-lookup"><span data-stu-id="88e2e-108">Value</span></span>

```
Set-Clipboard [-Value] <String[]> [-Append] [-AsHtml] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="88e2e-109">Pfad</span><span class="sxs-lookup"><span data-stu-id="88e2e-109">Path</span></span>

```
Set-Clipboard [-Append] -Path <String[]> [-AsHtml] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="88e2e-110">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="88e2e-110">LiteralPath</span></span>

```
Set-Clipboard [-Append] -LiteralPath <String[]> [-AsHtml] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="88e2e-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="88e2e-111">DESCRIPTION</span></span>

<span data-ttu-id="88e2e-112">Mit dem- `Set-Clipboard` Cmdlet wird der aktuelle Windows-Ablage Eintrag festgelegt.</span><span class="sxs-lookup"><span data-stu-id="88e2e-112">The `Set-Clipboard` cmdlet sets the current Windows clipboard entry.</span></span>

## <span data-ttu-id="88e2e-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="88e2e-113">EXAMPLES</span></span>

### <span data-ttu-id="88e2e-114">Beispiel 1: Kopieren von Text in die Zwischenablage</span><span class="sxs-lookup"><span data-stu-id="88e2e-114">Example 1: Copy text to the clipboard</span></span>

```powershell
Set-Clipboard -Value "This is a test string"
```

### <span data-ttu-id="88e2e-115">Beispiel 2: Kopieren des Inhalts eines Verzeichnisses in die Zwischenablage</span><span class="sxs-lookup"><span data-stu-id="88e2e-115">Example 2: Copy the contents of a directory to the clipboard</span></span>

<span data-ttu-id="88e2e-116">Mit diesem Befehl wird der Inhalt des angegebenen Ordners in die Zwischenablage kopiert.</span><span class="sxs-lookup"><span data-stu-id="88e2e-116">This command copies the content of the specified folder to the clipboard.</span></span>

```powershell
Set-Clipboard -Path "C:\Staging\"
```

## <span data-ttu-id="88e2e-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="88e2e-117">PARAMETERS</span></span>

### <span data-ttu-id="88e2e-118">-Anfügen</span><span class="sxs-lookup"><span data-stu-id="88e2e-118">-Append</span></span>

<span data-ttu-id="88e2e-119">Gibt an, dass das Cmdlet die Zwischenablage nicht löscht und Inhalt an ihn anfügt.</span><span class="sxs-lookup"><span data-stu-id="88e2e-119">Indicates that the cmdlet does not clear the clipboard and appends content to it.</span></span>

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

### <span data-ttu-id="88e2e-120">-Ashtml</span><span class="sxs-lookup"><span data-stu-id="88e2e-120">-AsHtml</span></span>

<span data-ttu-id="88e2e-121">Gibt an, dass das Cmdlet den Inhalt in der Zwischenablage als HTML-Code rendert.</span><span class="sxs-lookup"><span data-stu-id="88e2e-121">Indicates that the cmdlet renders the content as HTML to the clipboard.</span></span>

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

### <span data-ttu-id="88e2e-122">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="88e2e-122">-LiteralPath</span></span>

<span data-ttu-id="88e2e-123">Gibt den Pfad zu dem Element an, das in die Zwischenablage kopiert wird.</span><span class="sxs-lookup"><span data-stu-id="88e2e-123">Specifies the path to the item that is copied to the clipboard.</span></span> <span data-ttu-id="88e2e-124">Im Gegensatz zu **Path** wird der Wert von **LiteralPath** genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="88e2e-124">Unlike **Path** , the value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="88e2e-125">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="88e2e-125">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="88e2e-126">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="88e2e-126">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="88e2e-127">Einfache Anführungszeichen veranlassen Windows PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="88e2e-127">Single quotation marks tell Windows PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="88e2e-128">-Path</span><span class="sxs-lookup"><span data-stu-id="88e2e-128">-Path</span></span>

<span data-ttu-id="88e2e-129">Gibt den Pfad zu dem Element an, das in die Zwischenablage kopiert wird.</span><span class="sxs-lookup"><span data-stu-id="88e2e-129">Specifies the path to the item that is copied to the clipboard.</span></span> <span data-ttu-id="88e2e-130">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="88e2e-130">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="88e2e-131">-Value</span><span class="sxs-lookup"><span data-stu-id="88e2e-131">-Value</span></span>

<span data-ttu-id="88e2e-132">Gibt den Inhalt, der in die Zwischenablage kopiert werden soll, als Zeichen folgen Array an.</span><span class="sxs-lookup"><span data-stu-id="88e2e-132">Specifies, as a string array, the content to copy to the clipboard.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Value
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="88e2e-133">-Confirm</span><span class="sxs-lookup"><span data-stu-id="88e2e-133">-Confirm</span></span>

<span data-ttu-id="88e2e-134">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="88e2e-134">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="88e2e-135">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="88e2e-135">-WhatIf</span></span>

<span data-ttu-id="88e2e-136">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="88e2e-136">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="88e2e-137">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="88e2e-137">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="88e2e-138">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="88e2e-138">CommonParameters</span></span>

<span data-ttu-id="88e2e-139">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="88e2e-139">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="88e2e-140">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="88e2e-140">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="88e2e-141">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="88e2e-141">INPUTS</span></span>

### <span data-ttu-id="88e2e-142">System.String[]</span><span class="sxs-lookup"><span data-stu-id="88e2e-142">System.String[]</span></span>

## <span data-ttu-id="88e2e-143">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="88e2e-143">OUTPUTS</span></span>

## <span data-ttu-id="88e2e-144">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="88e2e-144">NOTES</span></span>

<span data-ttu-id="88e2e-145">In seltenen Fällen, in denen `Set-Clipboard` Sie mit einer hohen Anzahl von Werten in schneller Folge wie in einer-Schleife verwenden, erhalten Sie möglicherweise sporadisch einen leeren Wert aus der Zwischenablage.</span><span class="sxs-lookup"><span data-stu-id="88e2e-145">In rare cases when using `Set-Clipboard` with a high number of values in rapid succession, like in a loop, you might sporadically get a blank value from the clipboard.</span></span> <span data-ttu-id="88e2e-146">Dies kann mithilfe von `Start-Sleep -Milliseconds 1` in der-Schleife korrigiert werden.</span><span class="sxs-lookup"><span data-stu-id="88e2e-146">This can be fixed by using `Start-Sleep -Milliseconds 1` in the loop.</span></span>

## <span data-ttu-id="88e2e-147">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="88e2e-147">RELATED LINKS</span></span>

[<span data-ttu-id="88e2e-148">Get-Clipboard</span><span class="sxs-lookup"><span data-stu-id="88e2e-148">Get-Clipboard</span></span>](Get-Clipboard.md)
