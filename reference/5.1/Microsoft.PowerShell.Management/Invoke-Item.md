---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/invoke-item?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-Item
ms.openlocfilehash: 6aac74b9b084996377b97997ab78972cb28b0959
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215383"
---
# <span data-ttu-id="d084e-103">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="d084e-103">Invoke-Item</span></span>

## <span data-ttu-id="d084e-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="d084e-104">SYNOPSIS</span></span>
<span data-ttu-id="d084e-105">Führt die Standardaktion für das angegebene Element aus.</span><span class="sxs-lookup"><span data-stu-id="d084e-105">Performs the default action on the specified item.</span></span>

## <span data-ttu-id="d084e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d084e-106">SYNTAX</span></span>

### <span data-ttu-id="d084e-107">Pfad (Standard)</span><span class="sxs-lookup"><span data-stu-id="d084e-107">Path (Default)</span></span>

```
Invoke-Item [-Path] <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="d084e-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="d084e-108">LiteralPath</span></span>

```
Invoke-Item -LiteralPath <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="d084e-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d084e-109">DESCRIPTION</span></span>

<span data-ttu-id="d084e-110">Das- `Invoke-Item` Cmdlet führt die Standardaktion für das angegebene Element aus.</span><span class="sxs-lookup"><span data-stu-id="d084e-110">The `Invoke-Item` cmdlet performs the default action on the specified item.</span></span>
<span data-ttu-id="d084e-111">Beispielsweise wird eine ausführbare Datei ausgeführt oder eine Dokumentdatei in der Anwendung geöffnet, die dem Dokumentdateityp zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="d084e-111">For example, it runs an executable file or opens a document file in the application associated with the document file type.</span></span>
<span data-ttu-id="d084e-112">Die Standardaktion hängt vom Typ des Elements ab und wird vom PowerShell-Anbieter bestimmt, der den Zugriff auf die Daten ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="d084e-112">The default action depends on the type of item and is determined by the PowerShell provider that provides access to the data.</span></span>

## <span data-ttu-id="d084e-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="d084e-113">EXAMPLES</span></span>

### <span data-ttu-id="d084e-114">Beispiel 1: Öffnen einer Datei</span><span class="sxs-lookup"><span data-stu-id="d084e-114">Example 1: Open a file</span></span>

<span data-ttu-id="d084e-115">Mit diesem Befehl wird die Datei "aliasApr04.doc" in Microsoft Office Word geöffnet.</span><span class="sxs-lookup"><span data-stu-id="d084e-115">This command opens the file "aliasApr04.doc" in Microsoft Office Word.</span></span>
<span data-ttu-id="d084e-116">In diesem Fall ist das Öffnen in Word die Standardaktion für doc-Dateien.</span><span class="sxs-lookup"><span data-stu-id="d084e-116">In this case, opening in Word is the default action for ".doc" files.</span></span>

```powershell
Invoke-Item "C:\Test\aliasApr04.doc"
```

### <span data-ttu-id="d084e-117">Beispiel 2: Öffnen aller Dateien eines bestimmten Typs</span><span class="sxs-lookup"><span data-stu-id="d084e-117">Example 2: Open all files of a specific type</span></span>

<span data-ttu-id="d084e-118">Mit diesem Befehl werden alle Microsoft Office Excel-Tabellen im Ordner "c:\Dokumente und einstellunen\eigene Dokumente" geöffnet.</span><span class="sxs-lookup"><span data-stu-id="d084e-118">This command opens all of the Microsoft Office Excel spreadsheets in the "C:\Documents and Settings\Lister\My Documents" folder.</span></span>
<span data-ttu-id="d084e-119">Jede Tabelle wird in einer neuen Excel-Instanz geöffnet.</span><span class="sxs-lookup"><span data-stu-id="d084e-119">Each spreadsheet is opened in a new instance of Excel.</span></span>
<span data-ttu-id="d084e-120">In diesem Fall ist das Öffnen in Excel die Standardaktion für XLS-Dateien.</span><span class="sxs-lookup"><span data-stu-id="d084e-120">In this case, opening in Excel is the default action for ".xls" files.</span></span>

```powershell
Invoke-Item "C:\Documents and Settings\Lister\My Documents\*.xls"
```

## <span data-ttu-id="d084e-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d084e-121">PARAMETERS</span></span>

### <span data-ttu-id="d084e-122">-Credential</span><span class="sxs-lookup"><span data-stu-id="d084e-122">-Credential</span></span>

<span data-ttu-id="d084e-123">Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="d084e-123">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="d084e-124">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="d084e-124">The default is the current user.</span></span>

<span data-ttu-id="d084e-125">Geben Sie einen Benutzernamen ein, z. B. %%amp;quot;User01%%amp;quot; oder %%amp;quot;Domain01\User01%%amp;quot;, oder geben Sie ein **PSCredential** -Objekt ein, z. B. ein vom `Get-Credential`-Cmdlet generiertes Objekt.</span><span class="sxs-lookup"><span data-stu-id="d084e-125">Type a user name, such as "User01" or "Domain01\User01", or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span>
<span data-ttu-id="d084e-126">Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="d084e-126">If you type a user name, you are prompted for a password.</span></span>

> [!WARNING]
> <span data-ttu-id="d084e-127">Dieser Parameter wird nicht von mit Windows PowerShell installierten Anbietern unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d084e-127">This parameter is not supported by any providers installed with Windows PowerShell.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d084e-128">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="d084e-128">-Exclude</span></span>

<span data-ttu-id="d084e-129">Gibt als Zeichen folgen Array ein Element oder Elemente an, die von diesem Cmdlet aus dem Vorgang ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="d084e-129">Specifies, as a string array, an item or items that this cmdlet excludes from the operation.</span></span>
<span data-ttu-id="d084e-130">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="d084e-130">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="d084e-131">Geben Sie ein Pfadelement oder ein Muster wie %%amp;quot;\*.txt%%amp;quot; ein.</span><span class="sxs-lookup"><span data-stu-id="d084e-131">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="d084e-132">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="d084e-132">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="d084e-133">-Filter</span><span class="sxs-lookup"><span data-stu-id="d084e-133">-Filter</span></span>

<span data-ttu-id="d084e-134">Gibt einen Filter im Format oder in der Sprache des Anbieters an.</span><span class="sxs-lookup"><span data-stu-id="d084e-134">Specifies a filter in the format or language of the provider.</span></span>
<span data-ttu-id="d084e-135">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="d084e-135">The value of this parameter qualifies the **Path** parameter.</span></span>

<span data-ttu-id="d084e-136">Die Syntax des Filters, einschließlich der Verwendung von Platzhalter Zeichen, hängt vom Anbieter ab.</span><span class="sxs-lookup"><span data-stu-id="d084e-136">The syntax of the filter, including the use of wildcard characters, depends on the provider.</span></span>
<span data-ttu-id="d084e-137">Filter sind effizienter als andere Parameter, da Sie vom Anbieter angewendet werden, wenn das Cmdlet die Objekte abruft, statt dass PowerShell die Objekte nach dem Abrufen filtert.</span><span class="sxs-lookup"><span data-stu-id="d084e-137">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="d084e-138">-Include</span><span class="sxs-lookup"><span data-stu-id="d084e-138">-Include</span></span>

<span data-ttu-id="d084e-139">Gibt als Zeichen folgen Array ein Element oder Elemente an, die dieses Cmdlet in den Vorgang einschließt.</span><span class="sxs-lookup"><span data-stu-id="d084e-139">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span>
<span data-ttu-id="d084e-140">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="d084e-140">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="d084e-141">Geben Sie ein Pfadelement oder ein Muster wie %%amp;quot;\*.txt%%amp;quot; ein.</span><span class="sxs-lookup"><span data-stu-id="d084e-141">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="d084e-142">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="d084e-142">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d084e-143">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="d084e-143">-LiteralPath</span></span>

<span data-ttu-id="d084e-144">Gibt den Pfad zum Element an.</span><span class="sxs-lookup"><span data-stu-id="d084e-144">Specifies a path to the item.</span></span>
<span data-ttu-id="d084e-145">Im Gegensatz zum **Path** -Parameter wird der Wert des **LiteralPath** -Parameters genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="d084e-145">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it is typed.</span></span>
<span data-ttu-id="d084e-146">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="d084e-146">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="d084e-147">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="d084e-147">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="d084e-148">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="d084e-148">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="d084e-149">-Path</span><span class="sxs-lookup"><span data-stu-id="d084e-149">-Path</span></span>

<span data-ttu-id="d084e-150">Gibt den Pfad zum ausgewählten Element an.</span><span class="sxs-lookup"><span data-stu-id="d084e-150">Specifies the path to the selected item.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="d084e-151">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="d084e-151">-UseTransaction</span></span>

<span data-ttu-id="d084e-152">Schließt den Befehl in die aktive Transaktion ein.</span><span class="sxs-lookup"><span data-stu-id="d084e-152">Includes the command in the active transaction.</span></span>
<span data-ttu-id="d084e-153">Dieser Parameter ist nur gültig, wenn gerade eine Transaktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d084e-153">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="d084e-154">Weitere Informationen finden Sie unter about_transactions.</span><span class="sxs-lookup"><span data-stu-id="d084e-154">For more information, see about_transactions.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d084e-155">-Confirm</span><span class="sxs-lookup"><span data-stu-id="d084e-155">-Confirm</span></span>
<span data-ttu-id="d084e-156">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="d084e-156">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="d084e-157">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="d084e-157">-WhatIf</span></span>

<span data-ttu-id="d084e-158">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d084e-158">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="d084e-159">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d084e-159">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="d084e-160">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d084e-160">CommonParameters</span></span>

<span data-ttu-id="d084e-161">Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="d084e-161">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="d084e-162">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="d084e-162">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="d084e-163">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="d084e-163">INPUTS</span></span>

### <span data-ttu-id="d084e-164">System.String</span><span class="sxs-lookup"><span data-stu-id="d084e-164">System.String</span></span>

<span data-ttu-id="d084e-165">Sie können eine Zeichenfolge weiterreichen, die einen Pfad zu diesem Cmdlet enthält.</span><span class="sxs-lookup"><span data-stu-id="d084e-165">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="d084e-166">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="d084e-166">OUTPUTS</span></span>

### <span data-ttu-id="d084e-167">Keine</span><span class="sxs-lookup"><span data-stu-id="d084e-167">None</span></span>

<span data-ttu-id="d084e-168">Der Befehl generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="d084e-168">The command does not generate any output.</span></span>
<span data-ttu-id="d084e-169">Das Element, das vom Befehl aufgerufen wird, kann jedoch eine Ausgabe generieren.</span><span class="sxs-lookup"><span data-stu-id="d084e-169">However, output might be generated by the item that it invokes.</span></span>

## <span data-ttu-id="d084e-170">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="d084e-170">NOTES</span></span>

<span data-ttu-id="d084e-171">Dieses Cmdlet ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="d084e-171">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="d084e-172">Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="d084e-172">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="d084e-173">Weitere Informationen finden Sie unter %%amp;quot;about_Providers%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="d084e-173">For more information, see about_Providers.</span></span>

## <span data-ttu-id="d084e-174">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="d084e-174">RELATED LINKS</span></span>

[<span data-ttu-id="d084e-175">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="d084e-175">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="d084e-176">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="d084e-176">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="d084e-177">Get-Item</span><span class="sxs-lookup"><span data-stu-id="d084e-177">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="d084e-178">Move-Item</span><span class="sxs-lookup"><span data-stu-id="d084e-178">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="d084e-179">New-Item</span><span class="sxs-lookup"><span data-stu-id="d084e-179">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="d084e-180">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="d084e-180">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="d084e-181">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="d084e-181">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="d084e-182">Set-Item</span><span class="sxs-lookup"><span data-stu-id="d084e-182">Set-Item</span></span>](Set-Item.md)
