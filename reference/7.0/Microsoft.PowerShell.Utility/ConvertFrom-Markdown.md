---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: PowerShell, Cmdlet, markdown
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 11/02/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-markdown?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-Markdown
ms.openlocfilehash: 6f1ccedbd8443e1259b5695d1848979336727def
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210924"
---
# <span data-ttu-id="f667c-103">ConvertFrom-Markdown</span><span class="sxs-lookup"><span data-stu-id="f667c-103">ConvertFrom-Markdown</span></span>

## <span data-ttu-id="f667c-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="f667c-104">SYNOPSIS</span></span>
<span data-ttu-id="f667c-105">Konvertiert den Inhalt einer Zeichenfolge oder einer Datei in ein **markdowninfo** -Objekt.</span><span class="sxs-lookup"><span data-stu-id="f667c-105">Convert the contents of a string or a file to a **MarkdownInfo** object.</span></span>

## <span data-ttu-id="f667c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f667c-106">SYNTAX</span></span>

### <span data-ttu-id="f667c-107">Pathparamset (Standard)</span><span class="sxs-lookup"><span data-stu-id="f667c-107">PathParamSet (Default)</span></span>

```
ConvertFrom-Markdown [-Path] <String[]> [-AsVT100EncodedString] [<CommonParameters>]
```

### <span data-ttu-id="f667c-108">Literalparamset</span><span class="sxs-lookup"><span data-stu-id="f667c-108">LiteralParamSet</span></span>

```
ConvertFrom-Markdown -LiteralPath <String[]> [-AsVT100EncodedString] [<CommonParameters>]
```

### <span data-ttu-id="f667c-109">Inputobjparamset</span><span class="sxs-lookup"><span data-stu-id="f667c-109">InputObjParamSet</span></span>

```
ConvertFrom-Markdown -InputObject <PSObject> [-AsVT100EncodedString] [<CommonParameters>]
```

## <span data-ttu-id="f667c-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f667c-110">DESCRIPTION</span></span>

<span data-ttu-id="f667c-111">Dieses Cmdlet konvertiert den angegebenen Inhalt in eine **markdowninfo** .</span><span class="sxs-lookup"><span data-stu-id="f667c-111">This cmdlet converts the specified content into a **MarkdownInfo** .</span></span> <span data-ttu-id="f667c-112">Wenn ein Dateipfad für den **path** -Parameter angegeben wird, wird der Inhalt der Datei konvertiert.</span><span class="sxs-lookup"><span data-stu-id="f667c-112">When a file path is specified for the **Path** parameter, the contents on the file are converted.</span></span> <span data-ttu-id="f667c-113">Das Ausgabe Objekt verfügt über drei Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="f667c-113">The output object has three properties:</span></span>

- <span data-ttu-id="f667c-114">Die **Token** -Eigenschaft verfügt über die abstrakte Syntax Struktur (AST) des konvertierten Objekts.</span><span class="sxs-lookup"><span data-stu-id="f667c-114">The **Token** property has the abstract syntax tree (AST) of the the converted object</span></span>
- <span data-ttu-id="f667c-115">Die **HTML** -Eigenschaft hat die HTML-Konvertierung der angegebenen Eingabe.</span><span class="sxs-lookup"><span data-stu-id="f667c-115">The **Html** property has the HTML conversion of the specified input</span></span>
- <span data-ttu-id="f667c-116">Die **VT100EncodedString** -Eigenschaft hat die konvertierte Zeichenfolge mit ANSI (VT100)-Escapesequenzen, wenn der **AsVT100EncodedString** -Parameter angegeben wurde</span><span class="sxs-lookup"><span data-stu-id="f667c-116">The **VT100EncodedString** property has the converted string with ANSI (VT100) escape sequences if the **AsVT100EncodedString** parameter was specified</span></span>

<span data-ttu-id="f667c-117">Dieses Cmdlet wurde in PowerShell 6,1 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="f667c-117">This cmdlet was introduced in PowerShell 6.1.</span></span>

## <span data-ttu-id="f667c-118">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="f667c-118">EXAMPLES</span></span>

### <span data-ttu-id="f667c-119">Beispiel 1: Konvertieren einer Datei mit markdown-Inhalt in HTML</span><span class="sxs-lookup"><span data-stu-id="f667c-119">Example 1: Convert a file containing Markdown content to HTML</span></span>

```powershell
ConvertFrom-Markdown -Path .\README.md
```

<span data-ttu-id="f667c-120">Das **markdowninfo** -Objekt wird zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f667c-120">The **MarkdownInfo** object is returned.</span></span> <span data-ttu-id="f667c-121">Die **Tokens** -Eigenschaft verfügt über die Ast des konvertierten Inhalts der `README.md` Datei.</span><span class="sxs-lookup"><span data-stu-id="f667c-121">The **Tokens** property has the AST of the converted content of the `README.md` file.</span></span> <span data-ttu-id="f667c-122">Die **HTML** -Eigenschaft verfügt über den HTML-konvertierten Inhalt der `README.md` Datei.</span><span class="sxs-lookup"><span data-stu-id="f667c-122">The **Html** property has the HTML converted content of the `README.md` file.</span></span>

### <span data-ttu-id="f667c-123">Beispiel 2: Konvertieren einer Datei, die markdown-Inhalte enthält, in eine VT100-codierte Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f667c-123">Example 2: Convert a file containing Markdown content to a VT100-encoded string</span></span>

```powershell
ConvertFrom-Markdown -Path .\README.md -AsVT100EncodedString
```

<span data-ttu-id="f667c-124">Das **markdowninfo** -Objekt wird zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f667c-124">The **MarkdownInfo** object is returned.</span></span> <span data-ttu-id="f667c-125">Die **Tokens** -Eigenschaft verfügt über die Ast des konvertierten Inhalts der `README.md` Datei.</span><span class="sxs-lookup"><span data-stu-id="f667c-125">The **Tokens** property has the AST of the converted content of the `README.md` file.</span></span> <span data-ttu-id="f667c-126">Die **VT100EncodedString** -Eigenschaft weist den VT100-codierten Zeichen folgen konvertierten Inhalt der `README.md` Datei auf.</span><span class="sxs-lookup"><span data-stu-id="f667c-126">The **VT100EncodedString** property has the VT100-encoded string converted content of the `README.md` file.</span></span>

### <span data-ttu-id="f667c-127">Beispiel 3: Konvertieren eines Eingabe Objekts mit markdown-Inhalt in eine VT100-codierte Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f667c-127">Example 3: Convert input object containing Markdown content to a VT100-encoded string</span></span>

```powershell
Get-Item .\README.md | ConvertFrom-Markdown -AsVT100EncodedString
```

<span data-ttu-id="f667c-128">Das **markdowninfo** -Objekt wird zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f667c-128">The **MarkdownInfo** object is returned.</span></span> <span data-ttu-id="f667c-129">Das **FileInfo** -Objekt von `Get-Item` wird in eine VT100-codierte Zeichenfolge konvertiert.</span><span class="sxs-lookup"><span data-stu-id="f667c-129">The **FileInfo** object from `Get-Item` is converted to a VT100-encoded string.</span></span> <span data-ttu-id="f667c-130">Die **Tokens** -Eigenschaft verfügt über die Ast des konvertierten Inhalts der `README.md` Datei.</span><span class="sxs-lookup"><span data-stu-id="f667c-130">The **Tokens** property has the AST of the converted content of the `README.md` file.</span></span> <span data-ttu-id="f667c-131">Die **VT100EncodedString** -Eigenschaft weist den VT100-codierten Zeichen folgen konvertierten Inhalt der `README.md` Datei auf.</span><span class="sxs-lookup"><span data-stu-id="f667c-131">The **VT100EncodedString** property has the VT100-encoded string converted content of the `README.md` file.</span></span>

### <span data-ttu-id="f667c-132">Beispiel 4: Konvertieren einer Zeichenfolge mit markdown-Inhalt in eine VT100-codierte Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f667c-132">Example 4: Convert a string containing Markdown content to a VT100-encoded string</span></span>

```powershell
"**Bold text**" | ConvertFrom-Markdown -AsVT100EncodedString
```

<span data-ttu-id="f667c-133">Das **markdowninfo** -Objekt wird zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f667c-133">The **MarkdownInfo** object is returned.</span></span> <span data-ttu-id="f667c-134">Die angegebene Zeichenfolge `**Bold text**` wird in eine VT100-codierte Zeichenfolge konvertiert und ist in der **VT100EncodedString** -Eigenschaft verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f667c-134">The specified string `**Bold text**` is converted to a VT100-encoded string and available in **VT100EncodedString** property.</span></span>

## <span data-ttu-id="f667c-135">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f667c-135">PARAMETERS</span></span>

### <span data-ttu-id="f667c-136">-AsVT100EncodedString</span><span class="sxs-lookup"><span data-stu-id="f667c-136">-AsVT100EncodedString</span></span>

<span data-ttu-id="f667c-137">Gibt an, ob die Ausgabe als Zeichenfolge mit VT100-Escapecodes codiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="f667c-137">Specifies if the output should be encoded as a string with VT100 escape codes.</span></span>

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

### <span data-ttu-id="f667c-138">-InputObject</span><span class="sxs-lookup"><span data-stu-id="f667c-138">-InputObject</span></span>

<span data-ttu-id="f667c-139">Gibt das zu konvertierende Objekt an.</span><span class="sxs-lookup"><span data-stu-id="f667c-139">Specifies the object to be converted.</span></span> <span data-ttu-id="f667c-140">Wenn ein Objekt vom Typ " **System. String** " angegeben wird, wird die Zeichenfolge konvertiert.</span><span class="sxs-lookup"><span data-stu-id="f667c-140">When an object of type **System.String** is specified, the string is converted.</span></span> <span data-ttu-id="f667c-141">Wenn ein Objekt vom Typ **System. IO. FileInfo** angegeben wird, wird der Inhalt der durch das-Objekt angegebenen Datei konvertiert.</span><span class="sxs-lookup"><span data-stu-id="f667c-141">When an object of type **System.IO.FileInfo** is specified, the contents of the file specified by the object are converted.</span></span> <span data-ttu-id="f667c-142">Objekte eines beliebigen anderen Typs führen zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="f667c-142">Objects of any other type result in an error.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: InputObjParamSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="f667c-143">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="f667c-143">-LiteralPath</span></span>

<span data-ttu-id="f667c-144">Gibt einen Pfad zu der Datei an, die konvertiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="f667c-144">Specifies a path to the file to be converted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralParamSet
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f667c-145">-Path</span><span class="sxs-lookup"><span data-stu-id="f667c-145">-Path</span></span>

<span data-ttu-id="f667c-146">Gibt einen Pfad zu der Datei an, die konvertiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="f667c-146">Specifies a path to the file to be converted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PathParamSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="f667c-147">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f667c-147">CommonParameters</span></span>

<span data-ttu-id="f667c-148">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f667c-148">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f667c-149">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f667c-149">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f667c-150">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="f667c-150">INPUTS</span></span>

### <span data-ttu-id="f667c-151">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="f667c-151">System.Management.Automation.PSObject</span></span>

## <span data-ttu-id="f667c-152">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="f667c-152">OUTPUTS</span></span>

### <span data-ttu-id="f667c-153">Microsoft. PowerShell. markdownrendering. markdowninfo</span><span class="sxs-lookup"><span data-stu-id="f667c-153">Microsoft.PowerShell.MarkdownRender.MarkdownInfo</span></span>

## <span data-ttu-id="f667c-154">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="f667c-154">NOTES</span></span>

## <span data-ttu-id="f667c-155">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="f667c-155">RELATED LINKS</span></span>

[<span data-ttu-id="f667c-156">Markdownparser</span><span class="sxs-lookup"><span data-stu-id="f667c-156">Markdown Parser</span></span>](https://github.com/lunet-io/markdig)

[<span data-ttu-id="f667c-157">ANSI-Escapecode</span><span class="sxs-lookup"><span data-stu-id="f667c-157">ANSI escape code</span></span>](https://wikipedia.org/wiki/ANSI_escape_code)
