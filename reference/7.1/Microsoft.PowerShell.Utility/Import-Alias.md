---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/import-alias?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-Alias
ms.openlocfilehash: 50bc53d284fada31cf01b0504d89128eeb1710e2
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212980"
---
# <span data-ttu-id="116c9-103">Import-Alias</span><span class="sxs-lookup"><span data-stu-id="116c9-103">Import-Alias</span></span>

## <span data-ttu-id="116c9-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="116c9-104">SYNOPSIS</span></span>
<span data-ttu-id="116c9-105">Importiert eine Aliasliste aus einer Datei.</span><span class="sxs-lookup"><span data-stu-id="116c9-105">Imports an alias list from a file.</span></span>

## <span data-ttu-id="116c9-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="116c9-106">SYNTAX</span></span>

### <span data-ttu-id="116c9-107">Bypath (Standard)</span><span class="sxs-lookup"><span data-stu-id="116c9-107">ByPath (Default)</span></span>

```
Import-Alias [-Path] <String> [-Scope <String>] [-PassThru] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="116c9-108">Byliteralpath</span><span class="sxs-lookup"><span data-stu-id="116c9-108">ByLiteralPath</span></span>

```
Import-Alias -LiteralPath <String> [-Scope <String>] [-PassThru] [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="116c9-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="116c9-109">DESCRIPTION</span></span>

<span data-ttu-id="116c9-110">Mit dem- `Import-Alias` Cmdlet wird eine Alias Liste aus einer Datei importiert.</span><span class="sxs-lookup"><span data-stu-id="116c9-110">The `Import-Alias` cmdlet imports an alias list from a file.</span></span>

<span data-ttu-id="116c9-111">Ab Windows PowerShell 3,0, als Sicherheits Feature, werden `Import-Alias` vorhandene Aliase nicht standardmäßig überschrieben.</span><span class="sxs-lookup"><span data-stu-id="116c9-111">Beginning in Windows PowerShell 3.0, as a security feature, `Import-Alias` does not overwrite existing aliases by default.</span></span>
<span data-ttu-id="116c9-112">Zum Überschreiben eines vorhandenen Alias vergewissern Sie sich zunächst, dass der Inhalt der Aliasdatei sicher ist, und verwenden Sie dann den **Force** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="116c9-112">To overwrite an existing alias, after assuring that the contents of the alias file is safe, use the **Force** parameter.</span></span>

## <span data-ttu-id="116c9-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="116c9-113">EXAMPLES</span></span>

### <span data-ttu-id="116c9-114">Beispiel 1: Importieren von Aliasen aus einer Datei</span><span class="sxs-lookup"><span data-stu-id="116c9-114">Example 1: Import aliases from a file</span></span>

```powershell
Import-Alias test.txt
```

<span data-ttu-id="116c9-115">Dieser Befehl importiert die Aliasinformationen aus der Datei „test.txt“.</span><span class="sxs-lookup"><span data-stu-id="116c9-115">This command imports alias information from a file named test.txt.</span></span>

## <span data-ttu-id="116c9-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="116c9-116">PARAMETERS</span></span>

### <span data-ttu-id="116c9-117">-Force</span><span class="sxs-lookup"><span data-stu-id="116c9-117">-Force</span></span>

<span data-ttu-id="116c9-118">Ermöglicht dem Cmdlet das Importieren eines Alias, der bereits definiert oder schreibgeschützt ist.</span><span class="sxs-lookup"><span data-stu-id="116c9-118">Allows the cmdlet to import an alias that is already defined or is read only.</span></span>
<span data-ttu-id="116c9-119">Verwenden Sie folgenden Befehl, um Informationen über die aktuell definierten Aliase anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="116c9-119">You can use the following command to display information about the currently-defined aliases:</span></span>

`Get-Alias | Select-Object Name, Options`

<span data-ttu-id="116c9-120">Wenn der entsprechende Alias schreibgeschützt ist, wird dies im Wert der **Options** -Eigenschaft angezeigt.</span><span class="sxs-lookup"><span data-stu-id="116c9-120">If the corresponding alias is read-only, it will be displayed in the value of the **Options** property.</span></span>

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

### <span data-ttu-id="116c9-121">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="116c9-121">-LiteralPath</span></span>

<span data-ttu-id="116c9-122">Gibt den Pfad zu einer Datei an, die exportierte Aliasinformationen enthält.</span><span class="sxs-lookup"><span data-stu-id="116c9-122">Specifies the path to a file that includes exported alias information.</span></span>
<span data-ttu-id="116c9-123">Im Gegensatz zum **Path** -Parameter wird der Wert des **LiteralPath** -Parameters genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="116c9-123">Unlike the **Path** parameter, the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span>
<span data-ttu-id="116c9-124">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="116c9-124">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="116c9-125">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="116c9-125">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="116c9-126">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="116c9-126">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="116c9-127">-PassThru</span><span class="sxs-lookup"><span data-stu-id="116c9-127">-PassThru</span></span>

<span data-ttu-id="116c9-128">Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="116c9-128">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="116c9-129">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="116c9-129">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="116c9-130">-Path</span><span class="sxs-lookup"><span data-stu-id="116c9-130">-Path</span></span>

<span data-ttu-id="116c9-131">Gibt den Pfad zu einer Datei an, die exportierte Aliasinformationen enthält.</span><span class="sxs-lookup"><span data-stu-id="116c9-131">Specifies the path to a file that includes exported alias information.</span></span>
<span data-ttu-id="116c9-132">Platzhalter sind zulässig, aber sie müssen in einem einzigen Namen aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="116c9-132">Wildcards are allowed but they must resolve to a single name.</span></span>

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="116c9-133">-Bereich</span><span class="sxs-lookup"><span data-stu-id="116c9-133">-Scope</span></span>

<span data-ttu-id="116c9-134">Gibt den Bereich an, in den die Aliase importiert werden.</span><span class="sxs-lookup"><span data-stu-id="116c9-134">Specifies the scope into which the aliases are imported.</span></span>
<span data-ttu-id="116c9-135">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="116c9-135">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="116c9-136">Global</span><span class="sxs-lookup"><span data-stu-id="116c9-136">Global</span></span>
- <span data-ttu-id="116c9-137">Lokal</span><span class="sxs-lookup"><span data-stu-id="116c9-137">Local</span></span>
- <span data-ttu-id="116c9-138">Skript</span><span class="sxs-lookup"><span data-stu-id="116c9-138">Script</span></span>
- <span data-ttu-id="116c9-139">Eine Zahl relativ zum aktuellen Bereich (0 bis zur Anzahl der Bereiche, wobei 0 der aktuelle Bereich und 1 der übergeordnete Bereich ist)</span><span class="sxs-lookup"><span data-stu-id="116c9-139">A number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent)</span></span>

<span data-ttu-id="116c9-140">Der Standardwert ist local.</span><span class="sxs-lookup"><span data-stu-id="116c9-140">The default is Local.</span></span>
<span data-ttu-id="116c9-141">Weitere Informationen finden Sie unter „about_Scopes“.</span><span class="sxs-lookup"><span data-stu-id="116c9-141">For more information, see about_Scopes.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="116c9-142">-Confirm</span><span class="sxs-lookup"><span data-stu-id="116c9-142">-Confirm</span></span>

<span data-ttu-id="116c9-143">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="116c9-143">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="116c9-144">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="116c9-144">-WhatIf</span></span>

<span data-ttu-id="116c9-145">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="116c9-145">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="116c9-146">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="116c9-146">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="116c9-147">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="116c9-147">CommonParameters</span></span>

<span data-ttu-id="116c9-148">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="116c9-148">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="116c9-149">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="116c9-149">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="116c9-150">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="116c9-150">INPUTS</span></span>

### <span data-ttu-id="116c9-151">System.String</span><span class="sxs-lookup"><span data-stu-id="116c9-151">System.String</span></span>

<span data-ttu-id="116c9-152">Sie können eine Zeichenfolge über die Pipeline übergeben, die einen Pfad zu enthält `Import-Alias` .</span><span class="sxs-lookup"><span data-stu-id="116c9-152">You can pipe a string that contains a path to `Import-Alias`.</span></span>

## <span data-ttu-id="116c9-153">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="116c9-153">OUTPUTS</span></span>

### <span data-ttu-id="116c9-154">None oder System. Management. Automation. AliasInfo</span><span class="sxs-lookup"><span data-stu-id="116c9-154">None or System.Management.Automation.AliasInfo</span></span>

<span data-ttu-id="116c9-155">Wenn Sie den **passthru** -Parameter verwenden, `Import-Alias` gibt ein **System. Management. Automation. AliasInfo** -Objekt zurück, das den Alias darstellt.</span><span class="sxs-lookup"><span data-stu-id="116c9-155">When you use the **Passthru** parameter, `Import-Alias` returns a **System.Management.Automation.AliasInfo** object that represents the alias.</span></span>
<span data-ttu-id="116c9-156">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="116c9-156">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="116c9-157">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="116c9-157">NOTES</span></span>

## <span data-ttu-id="116c9-158">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="116c9-158">RELATED LINKS</span></span>

[<span data-ttu-id="116c9-159">Export-Alias</span><span class="sxs-lookup"><span data-stu-id="116c9-159">Export-Alias</span></span>](Export-Alias.md)

[<span data-ttu-id="116c9-160">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="116c9-160">Get-Alias</span></span>](Get-Alias.md)

[<span data-ttu-id="116c9-161">New-Alias</span><span class="sxs-lookup"><span data-stu-id="116c9-161">New-Alias</span></span>](New-Alias.md)

[<span data-ttu-id="116c9-162">Set-Alias</span><span class="sxs-lookup"><span data-stu-id="116c9-162">Set-Alias</span></span>](Set-Alias.md)

