---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/clear-content?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-Content
ms.openlocfilehash: 5a38fd45ff1f645df7004452b5a3c16c6f5cb74a
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93211151"
---
# <span data-ttu-id="ba6cd-103">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="ba6cd-103">Clear-Content</span></span>

## <span data-ttu-id="ba6cd-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="ba6cd-104">SYNOPSIS</span></span>
<span data-ttu-id="ba6cd-105">Löscht den Inhalt eines Elements, jedoch nicht das Element selbst.</span><span class="sxs-lookup"><span data-stu-id="ba6cd-105">Deletes the contents of an item, but does not delete the item.</span></span>

## <span data-ttu-id="ba6cd-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ba6cd-106">SYNTAX</span></span>

### <span data-ttu-id="ba6cd-107">Pfad (Standard)</span><span class="sxs-lookup"><span data-stu-id="ba6cd-107">Path (Default)</span></span>

```
Clear-Content [-Path] <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Force]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-Stream <String>] [<CommonParameters>]
```

### <span data-ttu-id="ba6cd-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="ba6cd-108">LiteralPath</span></span>

```
Clear-Content -LiteralPath <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Force]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-Stream <String>] [<CommonParameters>]
```

## <span data-ttu-id="ba6cd-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ba6cd-109">DESCRIPTION</span></span>

<span data-ttu-id="ba6cd-110">Das- `Clear-Content` Cmdlet löscht den Inhalt eines Elements, z. b. das Löschen des Texts aus einer Datei, aber das Element wird nicht gelöscht.</span><span class="sxs-lookup"><span data-stu-id="ba6cd-110">The `Clear-Content` cmdlet deletes the contents of an item, such as deleting the text from a file, but it does not delete the item.</span></span>
<span data-ttu-id="ba6cd-111">Folglich ist das Element vorhanden, aber leer.</span><span class="sxs-lookup"><span data-stu-id="ba6cd-111">As a result, the item exists, but it is empty.</span></span>
<span data-ttu-id="ba6cd-112">Der `Clear-Content` ähnelt `Clear-Item` , funktioniert jedoch für Elemente mit Inhalt anstelle von Elementen mit Werten.</span><span class="sxs-lookup"><span data-stu-id="ba6cd-112">The `Clear-Content` is similar to `Clear-Item`, but it works on items with contents, instead of items with values.</span></span>

## <span data-ttu-id="ba6cd-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="ba6cd-113">EXAMPLES</span></span>

### <span data-ttu-id="ba6cd-114">Beispiel 1: Löschen aller Inhalte aus einem Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="ba6cd-114">Example 1: Delete all content from a directory</span></span>

```powershell
Clear-Content "..\SmpUsers\*\init.txt"
```

<span data-ttu-id="ba6cd-115">Mit diesem Befehl wird der gesamte Inhalt aus den Dateien mit dem Namen %%amp;quot;init.txt%%amp;quot; in allen Unterverzeichnissen des Verzeichnisses %%amp;quot;SmpUsers%%amp;quot; gelöscht.</span><span class="sxs-lookup"><span data-stu-id="ba6cd-115">This command deletes all of the content from the "init.txt" files in all subdirectories of the SmpUsers directory.</span></span>
<span data-ttu-id="ba6cd-116">Die Dateien werden nicht gelöscht, sie sind anschließend jedoch leer.</span><span class="sxs-lookup"><span data-stu-id="ba6cd-116">The files are not deleted, but they are empty.</span></span>

### <span data-ttu-id="ba6cd-117">Beispiel 2: Löschen des Inhalts aller Dateien mit einem Platzhalter</span><span class="sxs-lookup"><span data-stu-id="ba6cd-117">Example 2: Delete content of all files with a wildcard</span></span>

```powershell
Clear-Content -Path "*" -Filter "*.log" -Force
```

<span data-ttu-id="ba6cd-118">Mit diesem Befehl wird der Inhalt aller Dateien mit der Dateinamenerweiterung %%amp;quot;.log%%amp;quot; im aktuellen Verzeichnis gelöscht, einschließlich der Dateien mit Schreibschutzattribut.</span><span class="sxs-lookup"><span data-stu-id="ba6cd-118">This command deletes the contents of all files in the current directory with the ".log" file name extension, including files with the read-only attribute.</span></span>
<span data-ttu-id="ba6cd-119">Das Sternchen ( \* ) im Pfad stellt alle Elemente im aktuellen Verzeichnis dar.</span><span class="sxs-lookup"><span data-stu-id="ba6cd-119">The asterisk (\*) in the path represents all items in the current directory.</span></span>
<span data-ttu-id="ba6cd-120">Der **Force** -Parameter bewirkt, dass der Befehl für schreibgeschützte Dateien wirksam wird.</span><span class="sxs-lookup"><span data-stu-id="ba6cd-120">The **Force** parameter makes the command effective on read-only files.</span></span>
<span data-ttu-id="ba6cd-121">Wenn Sie einen Filter verwenden, um den Befehl auf Dateien mit der Dateinamenerweiterung ". log" zu beschränken, anstatt " \* . log" im Pfad anzugeben, wird der Vorgang beschleunigt.</span><span class="sxs-lookup"><span data-stu-id="ba6cd-121">Using a filter to restrict the command to files with the .log file name extension instead of specifying \*.log in the path makes the operation faster.</span></span>

### <span data-ttu-id="ba6cd-122">Beispiel 3: Löschen aller Daten aus einem Stream</span><span class="sxs-lookup"><span data-stu-id="ba6cd-122">Example 3: Clear all data from a stream</span></span>

<span data-ttu-id="ba6cd-123">Dieses Beispiel zeigt, wie das `Clear-Content` Cmdlet den Inhalt aus einem alternativen Datenstrom löscht, während der Stream unverändert bleibt.</span><span class="sxs-lookup"><span data-stu-id="ba6cd-123">This example shows how the `Clear-Content` cmdlet clears the content from an alternate data stream while leaving the stream intact.</span></span>

<span data-ttu-id="ba6cd-124">Der erste Befehl verwendet das `Get-Content` Cmdlet, um den Inhalt des "Zone. Identifier"-Streams in der Copy-Script.ps1-Datei, die aus dem Internet heruntergeladen wurde, zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="ba6cd-124">The first command uses the `Get-Content` cmdlet to get the content of the Zone.Identifier stream in the Copy-Script.ps1 file, which was downloaded from the Internet.</span></span>

<span data-ttu-id="ba6cd-125">Der zweite Befehl verwendet das `Clear-Content` Cmdlet, um den Inhalt zu löschen.</span><span class="sxs-lookup"><span data-stu-id="ba6cd-125">The second command uses the `Clear-Content` cmdlet to clear the content.</span></span>

<span data-ttu-id="ba6cd-126">Mit dem dritten Befehl wird der erste Befehl wiederholt.</span><span class="sxs-lookup"><span data-stu-id="ba6cd-126">The third command repeats the first command.</span></span> <span data-ttu-id="ba6cd-127">Es überprüft, ob der Inhalt gelöscht wurde, der Stream bleibt jedoch erhalten.</span><span class="sxs-lookup"><span data-stu-id="ba6cd-127">It verifies that the content is cleared, but the stream remains.</span></span> <span data-ttu-id="ba6cd-128">Wenn der Stream gelöscht wurde, generiert der Befehl einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="ba6cd-128">If the stream were deleted, the command would generate an error.</span></span>

<span data-ttu-id="ba6cd-129">Sie können eine Methode wie diese verwenden, um den Inhalt eines alternativen Datenstroms zu löschen.</span><span class="sxs-lookup"><span data-stu-id="ba6cd-129">You can use a method like this one to clear the content of an alternate data stream.</span></span> <span data-ttu-id="ba6cd-130">Es ist jedoch nicht die empfohlene Methode, Sicherheitsüberprüfungen zu deaktivieren, die Dateien blockieren, die aus dem Internet heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="ba6cd-130">However, it is not the recommended way to eliminate security checks that block files that are downloaded from the Internet.</span></span> <span data-ttu-id="ba6cd-131">Wenn Sie überprüfen, ob eine heruntergeladene Datei sicher ist, verwenden Sie das- `Unblock-File` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ba6cd-131">If you verify that a downloaded file is safe, use the `Unblock-File` cmdlet.</span></span>

```
PS C:\> Get-Content C:\Test\Copy-Script.ps1 -Stream Zone.Identifier

[ZoneTransfer]
ZoneId=3

PS C:\>Clear-Content C:\Test\Copy-Script.ps1 -Stream Zone.Identifier

PS C:\>Get-Content C:\Test\Copy-Script.ps1 -Stream Zone.Identifier
PS C:\>
```

## <span data-ttu-id="ba6cd-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ba6cd-132">PARAMETERS</span></span>

### <span data-ttu-id="ba6cd-133">-Stream</span><span class="sxs-lookup"><span data-stu-id="ba6cd-133">-Stream</span></span>

<span data-ttu-id="ba6cd-134">Gibt einen alternativen Datenstrom für den Inhalt an.</span><span class="sxs-lookup"><span data-stu-id="ba6cd-134">Specifies an alternative data stream for content.</span></span>
<span data-ttu-id="ba6cd-135">Wenn der Datenstrom nicht vorhanden ist, wird er von diesem Cmdlet erstellt.</span><span class="sxs-lookup"><span data-stu-id="ba6cd-135">If the stream does not exist, this cmdlet creates it.</span></span>
<span data-ttu-id="ba6cd-136">Platzhalterzeichen werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ba6cd-136">Wildcard characters are not supported.</span></span>

<span data-ttu-id="ba6cd-137">Stream ist ein dynamischer Parameter, den der File System-Anbieter hinzufügt `Clear-Content` .</span><span class="sxs-lookup"><span data-stu-id="ba6cd-137">Stream is a dynamic parameter that the FileSystem provider adds to `Clear-Content`.</span></span>
<span data-ttu-id="ba6cd-138">Dieser Parameter funktioniert nur in Dateisystemlaufwerken.</span><span class="sxs-lookup"><span data-stu-id="ba6cd-138">This parameter works only in file system drives.</span></span>

<span data-ttu-id="ba6cd-139">Sie können das `Clear-Content` Cmdlet verwenden, um den Inhalt des alternativen Datenstroms "Zone. Identifier" zu ändern.</span><span class="sxs-lookup"><span data-stu-id="ba6cd-139">You can use the `Clear-Content` cmdlet to change the content of the Zone.Identifier alternate data stream.</span></span>
<span data-ttu-id="ba6cd-140">Dies wird jedoch nicht empfohlen, um Sicherheitsüberprüfungen zu vermeiden, die Dateien blockieren, die aus dem Internet heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="ba6cd-140">However, we do not recommend this as a way to eliminate security checks that block files that are downloaded from the Internet.</span></span>
<span data-ttu-id="ba6cd-141">Wenn Sie überprüfen, ob eine heruntergeladene Datei sicher ist, verwenden Sie das- `Unblock-File` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ba6cd-141">If you verify that a downloaded file is safe, use the `Unblock-File` cmdlet.</span></span>

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

### <span data-ttu-id="ba6cd-142">-Credential</span><span class="sxs-lookup"><span data-stu-id="ba6cd-142">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="ba6cd-143">Dieser Parameter wird von Anbietern, die mit PowerShell installiert wurden, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ba6cd-143">This parameter is not supported by any providers installed with PowerShell.</span></span> <span data-ttu-id="ba6cd-144">Verwenden Sie zum Annehmen der Identität eines anderen Benutzers oder zum herauf Stufen ihrer Anmelde Informationen bei der Ausführung dieses Cmdlets "Start-Command".</span><span class="sxs-lookup"><span data-stu-id="ba6cd-144">To impersonate another user, or elevate your credentials when running this cmdlet, use Invoke-Command.</span></span>

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

### <span data-ttu-id="ba6cd-145">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="ba6cd-145">-Exclude</span></span>

<span data-ttu-id="ba6cd-146">Gibt Zeichen folgen, die von diesem Cmdlet aus dem Pfad zum Inhalt ausgelassen werden, als Zeichen folgen Array an.</span><span class="sxs-lookup"><span data-stu-id="ba6cd-146">Specifies, as a string array, strings that this cmdlet omits from the path to the content.</span></span>
<span data-ttu-id="ba6cd-147">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="ba6cd-147">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="ba6cd-148">Geben Sie ein Pfadelement oder ein Muster wie %%amp;quot;\*.txt%%amp;quot; ein.</span><span class="sxs-lookup"><span data-stu-id="ba6cd-148">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="ba6cd-149">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="ba6cd-149">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="ba6cd-150">-Filter</span><span class="sxs-lookup"><span data-stu-id="ba6cd-150">-Filter</span></span>

<span data-ttu-id="ba6cd-151">Gibt einen Filter im Format oder in der Sprache des Anbieters an.</span><span class="sxs-lookup"><span data-stu-id="ba6cd-151">Specifies a filter in the provider's format or language.</span></span>
<span data-ttu-id="ba6cd-152">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="ba6cd-152">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="ba6cd-153">Die Syntax des Filters einschließlich der Verwendung von Platzhaltern ist vom Anbieter abhängig.</span><span class="sxs-lookup"><span data-stu-id="ba6cd-153">The syntax of the filter, including the use of wildcards, depends on the provider.</span></span>
<span data-ttu-id="ba6cd-154">Filter sind effizienter als andere Parameter, da Sie vom Anbieter beim Abrufen der Objekte angewendet werden, anstatt dass PowerShell die Objekte nach dem Abrufen filtert.</span><span class="sxs-lookup"><span data-stu-id="ba6cd-154">Filters are more efficient than other parameters, because the provider applies them when retrieving the objects, rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="ba6cd-155">-Force</span><span class="sxs-lookup"><span data-stu-id="ba6cd-155">-Force</span></span>

<span data-ttu-id="ba6cd-156">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="ba6cd-156">Forces the command to run without asking for user confirmation.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ba6cd-157">-Include</span><span class="sxs-lookup"><span data-stu-id="ba6cd-157">-Include</span></span>

<span data-ttu-id="ba6cd-158">Gibt den Inhalt, den dieses Cmdlet löscht, als Zeichen folgen Array an.</span><span class="sxs-lookup"><span data-stu-id="ba6cd-158">Specifies, as a string array, content that this cmdlet clears.</span></span>
<span data-ttu-id="ba6cd-159">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="ba6cd-159">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="ba6cd-160">Geben Sie ein Pfadelement oder ein Muster wie %%amp;quot;\*.txt%%amp;quot; ein.</span><span class="sxs-lookup"><span data-stu-id="ba6cd-160">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="ba6cd-161">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="ba6cd-161">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="ba6cd-162">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="ba6cd-162">-LiteralPath</span></span>

<span data-ttu-id="ba6cd-163">Gibt die Pfade zu den Elementen an, aus denen der Inhalt gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="ba6cd-163">Specifies the paths to the items from which content is deleted.</span></span>
<span data-ttu-id="ba6cd-164">Im Gegensatz zum **Path** -Parameter wird der Wert des **LiteralPath** -Parameters genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="ba6cd-164">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it is typed.</span></span>
<span data-ttu-id="ba6cd-165">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="ba6cd-165">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="ba6cd-166">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="ba6cd-166">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="ba6cd-167">Einfache Anführungszeichen geben an, dass PowerShell Zeichen nicht als Escapesequenzen interpretieren soll.</span><span class="sxs-lookup"><span data-stu-id="ba6cd-167">Single quotation marks tell having PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="ba6cd-168">-Path</span><span class="sxs-lookup"><span data-stu-id="ba6cd-168">-Path</span></span>

<span data-ttu-id="ba6cd-169">Gibt die Pfade zu den Elementen an, aus denen der Inhalt gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="ba6cd-169">Specifies the paths to the items from which content is deleted.</span></span>
<span data-ttu-id="ba6cd-170">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="ba6cd-170">Wildcards are permitted.</span></span>
<span data-ttu-id="ba6cd-171">Die Pfade müssen auf Elemente und nicht auf Container zeigen.</span><span class="sxs-lookup"><span data-stu-id="ba6cd-171">The paths must be paths to items, not to containers.</span></span>
<span data-ttu-id="ba6cd-172">Sie müssen beispielsweise einen Pfad zu Dateien angeben, ein Pfad zu einem Verzeichnis ist nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="ba6cd-172">For example, you must specify a path to one or more files, not a path to a directory.</span></span>
<span data-ttu-id="ba6cd-173">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="ba6cd-173">Wildcards are permitted.</span></span>
<span data-ttu-id="ba6cd-174">Dieser Parameter ist erforderlich, der Parametername (Path) ist jedoch optional.</span><span class="sxs-lookup"><span data-stu-id="ba6cd-174">This parameter is required, but the parameter name ("Path") is optional.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="ba6cd-175">-Confirm</span><span class="sxs-lookup"><span data-stu-id="ba6cd-175">-Confirm</span></span>

<span data-ttu-id="ba6cd-176">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="ba6cd-176">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ba6cd-177">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="ba6cd-177">-WhatIf</span></span>

<span data-ttu-id="ba6cd-178">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ba6cd-178">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="ba6cd-179">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ba6cd-179">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="ba6cd-180">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ba6cd-180">CommonParameters</span></span>

<span data-ttu-id="ba6cd-181">Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="ba6cd-181">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="ba6cd-182">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="ba6cd-182">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="ba6cd-183">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="ba6cd-183">INPUTS</span></span>

### <span data-ttu-id="ba6cd-184">Keine</span><span class="sxs-lookup"><span data-stu-id="ba6cd-184">None</span></span>

<span data-ttu-id="ba6cd-185">Objekte können nicht an übergeben werden `Clear-Content` .</span><span class="sxs-lookup"><span data-stu-id="ba6cd-185">You cannot pipe objects to `Clear-Content`.</span></span>

## <span data-ttu-id="ba6cd-186">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="ba6cd-186">OUTPUTS</span></span>

### <span data-ttu-id="ba6cd-187">Keine</span><span class="sxs-lookup"><span data-stu-id="ba6cd-187">None</span></span>

<span data-ttu-id="ba6cd-188">Dieses Cmdlet gibt keine Objekte zurück.</span><span class="sxs-lookup"><span data-stu-id="ba6cd-188">This cmdlet does not return any objects.</span></span>

## <span data-ttu-id="ba6cd-189">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="ba6cd-189">NOTES</span></span>

<span data-ttu-id="ba6cd-190">Sie können `Clear-Content` mit dem PowerShell-File System-Anbieter und mit anderen Anbietern verwenden, die den Inhalt bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="ba6cd-190">You can use `Clear-Content` with the PowerShell FileSystem provider and with other providers that manipulate content.</span></span>
<span data-ttu-id="ba6cd-191">Verwenden Sie, um Elemente zu löschen, die nicht als Inhalt angesehen werden, z. b. Elemente, die vom PowerShell-Zertifikat oder von Registrierungs Anbietern verwaltet werden `Clear-Item` .</span><span class="sxs-lookup"><span data-stu-id="ba6cd-191">To clear items that are not considered to be content, such as items managed by the PowerShell Certificate or Registry providers, use `Clear-Item`.</span></span>

<span data-ttu-id="ba6cd-192">Das- `Clear-Content` Cmdlet ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="ba6cd-192">The `Clear-Content` cmdlet is designed to work with the data exposed by any provider.</span></span>
<span data-ttu-id="ba6cd-193">Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PsProvider` .</span><span class="sxs-lookup"><span data-stu-id="ba6cd-193">To list the providers available in your session, type `Get-PsProvider`.</span></span>
<span data-ttu-id="ba6cd-194">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="ba6cd-194">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="ba6cd-195">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="ba6cd-195">RELATED LINKS</span></span>

[<span data-ttu-id="ba6cd-196">Add-Content</span><span class="sxs-lookup"><span data-stu-id="ba6cd-196">Add-Content</span></span>](Add-Content.md)

[<span data-ttu-id="ba6cd-197">Get-Content</span><span class="sxs-lookup"><span data-stu-id="ba6cd-197">Get-Content</span></span>](Get-Content.md)

[<span data-ttu-id="ba6cd-198">Get-Item</span><span class="sxs-lookup"><span data-stu-id="ba6cd-198">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="ba6cd-199">Set-Content</span><span class="sxs-lookup"><span data-stu-id="ba6cd-199">Set-Content</span></span>](Set-Content.md)

[<span data-ttu-id="ba6cd-200">about_Providers</span><span class="sxs-lookup"><span data-stu-id="ba6cd-200">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
