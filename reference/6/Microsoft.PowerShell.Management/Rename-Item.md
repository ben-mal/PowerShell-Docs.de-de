---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/03/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/rename-item?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Rename-Item
ms.openlocfilehash: 66a7b82b56028a4801a3aa8c93cd46460a5353ce
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214991"
---
# <span data-ttu-id="bddfb-103">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="bddfb-103">Rename-Item</span></span>

## <span data-ttu-id="bddfb-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="bddfb-104">SYNOPSIS</span></span>
<span data-ttu-id="bddfb-105">Benennt ein Element in einem PowerShell-Anbieter Namespace um.</span><span class="sxs-lookup"><span data-stu-id="bddfb-105">Renames an item in a PowerShell provider namespace.</span></span>

## <span data-ttu-id="bddfb-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="bddfb-106">SYNTAX</span></span>

### <span data-ttu-id="bddfb-107">Bypath (Standard)</span><span class="sxs-lookup"><span data-stu-id="bddfb-107">ByPath (Default)</span></span>

```
Rename-Item [-Path] <String> [-NewName] <String> [-Force] [-PassThru] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm]  [<CommonParameters>]
```

### <span data-ttu-id="bddfb-108">Byliteralpath</span><span class="sxs-lookup"><span data-stu-id="bddfb-108">ByLiteralPath</span></span>

```
Rename-Item -LiteralPath <String> [-NewName] <String> [-Force] [-PassThru]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm]  [<CommonParameters>]
```

## <span data-ttu-id="bddfb-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bddfb-109">DESCRIPTION</span></span>

<span data-ttu-id="bddfb-110">Das- `Rename-Item` Cmdlet ändert den Namen eines angegebenen Elements.</span><span class="sxs-lookup"><span data-stu-id="bddfb-110">The `Rename-Item` cmdlet changes the name of a specified item.</span></span> <span data-ttu-id="bddfb-111">Dieses Cmdlet hat keine Auswirkungen auf den Inhalt des umbenannten Elements.</span><span class="sxs-lookup"><span data-stu-id="bddfb-111">This cmdlet does not affect the content of the item being renamed.</span></span>

<span data-ttu-id="bddfb-112">Sie können nicht verwenden `Rename-Item` , um ein Element zu verschieben, z. b. durch Angeben eines Pfads mit dem neuen Namen.</span><span class="sxs-lookup"><span data-stu-id="bddfb-112">You can't use `Rename-Item` to move an item, such as by specifying a path together with the new name.</span></span> <span data-ttu-id="bddfb-113">Verwenden Sie das-Cmdlet, um ein Element zu verschieben und umzubenennen `Move-Item` .</span><span class="sxs-lookup"><span data-stu-id="bddfb-113">To move and rename an item, use the `Move-Item` cmdlet.</span></span>

## <span data-ttu-id="bddfb-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="bddfb-114">EXAMPLES</span></span>

### <span data-ttu-id="bddfb-115">Beispiel 1: Umbenennen einer Datei</span><span class="sxs-lookup"><span data-stu-id="bddfb-115">Example 1: Rename a file</span></span>

<span data-ttu-id="bddfb-116">Mit diesem Befehl wird die Datei `daily_file.txt` in umbenannt `monday_file.txt` .</span><span class="sxs-lookup"><span data-stu-id="bddfb-116">This command renames the file `daily_file.txt` to `monday_file.txt`.</span></span>

```powershell
Rename-Item -Path "c:\logfiles\daily_file.txt" -NewName "monday_file.txt"
```

### <span data-ttu-id="bddfb-117">Beispiel 2: Umbenennen und Verschieben eines Elements</span><span class="sxs-lookup"><span data-stu-id="bddfb-117">Example 2: Rename and move an item</span></span>

<span data-ttu-id="bddfb-118">Sie können nicht verwenden `Rename-Item` , um ein Element umzubenennen und zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="bddfb-118">You can't use `Rename-Item` to both rename and move an item.</span></span> <span data-ttu-id="bddfb-119">Insbesondere können Sie keinen Pfad für den Wert des **NewName** -Parameters angeben, es sei denn, der Pfad ist identisch mit dem im **path** -Parameter angegebenen Pfad.</span><span class="sxs-lookup"><span data-stu-id="bddfb-119">Specifically, you can't supply a path for the value of the **NewName** parameter, unless the path is identical to the path specified in the **Path** parameter.</span></span> <span data-ttu-id="bddfb-120">Andernfalls ist nur ein neuer Name zulässig.</span><span class="sxs-lookup"><span data-stu-id="bddfb-120">Otherwise, only a new name is permitted.</span></span>

<span data-ttu-id="bddfb-121">In diesem Beispiel wird versucht, die `project.txt` Datei im aktuellen Verzeichnis `old-project.txt` im Verzeichnis in umzubenennen `D:\Archive` .</span><span class="sxs-lookup"><span data-stu-id="bddfb-121">This example attempts to rename the `project.txt` file in the current directory to `old-project.txt` in the `D:\Archive` directory.</span></span> <span data-ttu-id="bddfb-122">Das Ergebnis ist der in der Ausgabe angezeigte Fehler.</span><span class="sxs-lookup"><span data-stu-id="bddfb-122">The result is the error shown in the output.</span></span>

```powershell
Rename-Item -Path "project.txt" -NewName "d:\archive\old-project.txt"
```

```Output
Rename-Item : can't rename because the target specified represents a path or device name.
At line:1 char:12
+ Rename-Item <<<<  -path project.txt -NewName d:\archive\old-project.txt
+ CategoryInfo          : InvalidArgument: (:) [Rename-Item], PS>  Move-Item -Path "project.txt" -De
stination "d:\archive\old-project.txt"
```

### <span data-ttu-id="bddfb-123">Beispiel 3: Umbenennen eines Registrierungsschlüssels</span><span class="sxs-lookup"><span data-stu-id="bddfb-123">Example 3: Rename a registry key</span></span>

<span data-ttu-id="bddfb-124">In diesem Beispiel wird ein Registrierungsschlüssel von " **Werbung** " in " **Marketing** " umbenannt.</span><span class="sxs-lookup"><span data-stu-id="bddfb-124">This example renames a registry key from **Advertising** to **Marketing** .</span></span> <span data-ttu-id="bddfb-125">Nach Abschluss des Befehls wurde der Schlüssel umbenannt, die Registrierungseinträge im Schlüssel sind jedoch unverändert.</span><span class="sxs-lookup"><span data-stu-id="bddfb-125">When the command is complete, the key is renamed, but the registry entries in the key are unchanged.</span></span>

```powershell
Rename-Item -Path "HKLM:\Software\MyCompany\Advertising" -NewName "Marketing"
```

### <span data-ttu-id="bddfb-126">Beispiel 4: Umbenennen mehrerer Dateien</span><span class="sxs-lookup"><span data-stu-id="bddfb-126">Example 4: Rename multiple files</span></span>

<span data-ttu-id="bddfb-127">In diesem Beispiel werden alle `*.txt` Dateien im aktuellen Verzeichnis in umbenannt `*.log` .</span><span class="sxs-lookup"><span data-stu-id="bddfb-127">This example renames all the `*.txt` files in the current directory to `*.log`.</span></span>

```powershell
Get-ChildItem *.txt
```

```Output
    Directory: C:\temp\files

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        10/3/2019   7:47 AM           2918 Friday.TXT
-a----        10/3/2019   7:46 AM           2918 Monday.Txt
-a----        10/3/2019   7:47 AM           2918 Wednesday.txt
```

```powershell
Get-ChildItem *.txt | Rename-Item -NewName { $_.Name -replace '.txt','.log' }
Get-ChildItem *.log
```

```Output
    Directory: C:\temp\files

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        10/3/2019   7:47 AM           2918 Friday.log
-a----        10/3/2019   7:46 AM           2918 Monday.log
-a----        10/3/2019   7:47 AM           2918 Wednesday.log
```

<span data-ttu-id="bddfb-128">Mit dem- `Get-ChildItem` Cmdlet werden alle Dateien im aktuellen Ordner `.txt` mit einer Dateierweiterung abgerufen und an weitergeleitet `Rename-Item` .</span><span class="sxs-lookup"><span data-stu-id="bddfb-128">The `Get-ChildItem` cmdlet gets all the files in the current folder that have a `.txt` file extension then pipes them to `Rename-Item`.</span></span> <span data-ttu-id="bddfb-129">Der Wert von **NewName** ist ein Skriptblock, der ausgeführt wird, bevor der Wert an den **NewName** -Parameter gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="bddfb-129">The value of **NewName** is a script block that runs before the value is submitted to the **NewName** parameter.</span></span>

<span data-ttu-id="bddfb-130">Im Skriptblock `$_` stellt die automatische Variable jedes Datei Objekt dar, wie es über die Pipeline an den Befehl gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="bddfb-130">In the script block, the `$_` automatic variable represents each file object as it comes to the command through the pipeline.</span></span> <span data-ttu-id="bddfb-131">Der Skriptblock verwendet den- `-replace` Operator, um die Dateierweiterung der einzelnen Dateien durch zu ersetzen `.log` .</span><span class="sxs-lookup"><span data-stu-id="bddfb-131">The script block uses the `-replace` operator to replace the file extension of each file with `.log`.</span></span> <span data-ttu-id="bddfb-132">Beachten Sie, dass bei der Übereinstimmung mit dem- `-replace` Operator nicht zwischen Groß-</span><span class="sxs-lookup"><span data-stu-id="bddfb-132">Notice that matching using the `-replace` operator is not case sensitive.</span></span>

## <span data-ttu-id="bddfb-133">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bddfb-133">PARAMETERS</span></span>

### <span data-ttu-id="bddfb-134">-Credential</span><span class="sxs-lookup"><span data-stu-id="bddfb-134">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="bddfb-135">Dieser Parameter wird von Anbietern, die mit PowerShell installiert wurden, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="bddfb-135">This parameter is not supported by any providers installed with PowerShell.</span></span> <span data-ttu-id="bddfb-136">Verwenden Sie zum Annehmen der Identität eines anderen Benutzers oder zum herauf Stufen ihrer Anmelde Informationen bei der Ausführung dieses Cmdlets "Start [-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)".</span><span class="sxs-lookup"><span data-stu-id="bddfb-136">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="bddfb-137">-Force</span><span class="sxs-lookup"><span data-stu-id="bddfb-137">-Force</span></span>

<span data-ttu-id="bddfb-138">Zwingt das Cmdlet, Elemente umzubenennen, die anderweitig nicht geändert werden können, z. b. ausgeblendete oder schreibgeschützte Dateien oder schreibgeschützte Aliase oder Variablen.</span><span class="sxs-lookup"><span data-stu-id="bddfb-138">Forces the cmdlet to rename items that can't otherwise be changed, such as hidden or read-only files or read-only aliases or variables.</span></span> <span data-ttu-id="bddfb-139">Mit dem-Cmdlet können keine Konstanten Aliase oder Variablen geändert werden.</span><span class="sxs-lookup"><span data-stu-id="bddfb-139">The cmdlet can't change constant aliases or variables.</span></span>
<span data-ttu-id="bddfb-140">Die Implementierung unterscheidet sich bei den einzelnen Anbietern.</span><span class="sxs-lookup"><span data-stu-id="bddfb-140">Implementation varies from provider to provider.</span></span> <span data-ttu-id="bddfb-141">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="bddfb-141">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

<span data-ttu-id="bddfb-142">Selbst bei Verwendung des **Force** -Parameters kann das Cmdlet keine Sicherheitseinschränkungen außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="bddfb-142">Even using the **Force** parameter, the cmdlet can't override security restrictions.</span></span>

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

### <span data-ttu-id="bddfb-143">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="bddfb-143">-LiteralPath</span></span>

<span data-ttu-id="bddfb-144">Gibt einen Pfad zu einem oder mehreren Speicherorten an.</span><span class="sxs-lookup"><span data-stu-id="bddfb-144">Specifies a path to one or more locations.</span></span> <span data-ttu-id="bddfb-145">Der Wert von **literalpath** wird genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="bddfb-145">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="bddfb-146">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="bddfb-146">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="bddfb-147">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="bddfb-147">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="bddfb-148">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="bddfb-148">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="bddfb-149">Weitere Informationen finden Sie unter [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="bddfb-149">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="bddfb-150">-Newname</span><span class="sxs-lookup"><span data-stu-id="bddfb-150">-NewName</span></span>

<span data-ttu-id="bddfb-151">Gibt den neuen Namen des Elements an.</span><span class="sxs-lookup"><span data-stu-id="bddfb-151">Specifies the new name of the item.</span></span> <span data-ttu-id="bddfb-152">Geben Sie nur einen Namen ein, nicht einen Pfad und einen Namen.</span><span class="sxs-lookup"><span data-stu-id="bddfb-152">Enter only a name, not a path and name.</span></span> <span data-ttu-id="bddfb-153">Wenn Sie einen Pfad eingeben, der von dem im **path** -Parameter angegebenen Pfad abweicht, `Rename-Item` generiert einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="bddfb-153">If you enter a path that differs from the path that is specified in the **Path** parameter, `Rename-Item` generates an error.</span></span>
<span data-ttu-id="bddfb-154">Verwenden Sie, um ein Element umzubenennen und zu verschieben `Move-Item` .</span><span class="sxs-lookup"><span data-stu-id="bddfb-154">To rename and move an item, use `Move-Item`.</span></span>

<span data-ttu-id="bddfb-155">Sie können keine Platzhalter Zeichen im Wert des **NewName** -Parameters verwenden.</span><span class="sxs-lookup"><span data-stu-id="bddfb-155">You can't use wildcard characters in the value of the **NewName** parameter.</span></span> <span data-ttu-id="bddfb-156">Wenn Sie einen Namen für mehrere Dateien angeben möchten, verwenden Sie den **Replace** -Operator in einem regulären Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="bddfb-156">To specify a name for multiple files, use the **Replace** operator in a regular expression.</span></span> <span data-ttu-id="bddfb-157">Weitere Informationen zum Replace-Operator finden Sie unter [about_Comparison_Operators](../Microsoft.PowerShell.Core/About/about_Comparison_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="bddfb-157">For more information about the Replace operator, see [about_Comparison_Operators](../Microsoft.PowerShell.Core/About/about_Comparison_Operators.md).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="bddfb-158">-PassThru</span><span class="sxs-lookup"><span data-stu-id="bddfb-158">-PassThru</span></span>

<span data-ttu-id="bddfb-159">Gibt ein Objekt zurück, das das Element für die Pipeline darstellt.</span><span class="sxs-lookup"><span data-stu-id="bddfb-159">Returns an object that represents the item to the pipeline.</span></span> <span data-ttu-id="bddfb-160">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="bddfb-160">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="bddfb-161">-Path</span><span class="sxs-lookup"><span data-stu-id="bddfb-161">-Path</span></span>

<span data-ttu-id="bddfb-162">Gibt den Pfad des umzubenennenden Elements an.</span><span class="sxs-lookup"><span data-stu-id="bddfb-162">Specifies the path of the item to rename.</span></span>

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="bddfb-163">-Confirm</span><span class="sxs-lookup"><span data-stu-id="bddfb-163">-Confirm</span></span>

<span data-ttu-id="bddfb-164">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="bddfb-164">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="bddfb-165">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="bddfb-165">-WhatIf</span></span>

<span data-ttu-id="bddfb-166">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="bddfb-166">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="bddfb-167">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="bddfb-167">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="bddfb-168">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="bddfb-168">CommonParameters</span></span>

<span data-ttu-id="bddfb-169">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="bddfb-169">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="bddfb-170">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="bddfb-170">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="bddfb-171">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="bddfb-171">INPUTS</span></span>

### <span data-ttu-id="bddfb-172">System.String</span><span class="sxs-lookup"><span data-stu-id="bddfb-172">System.String</span></span>

<span data-ttu-id="bddfb-173">Sie können eine Zeichenfolge weiterreichen, die einen Pfad zu diesem Cmdlet enthält.</span><span class="sxs-lookup"><span data-stu-id="bddfb-173">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="bddfb-174">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="bddfb-174">OUTPUTS</span></span>

### <span data-ttu-id="bddfb-175">None oder ein Objekt, das das umbenannte Element darstellt.</span><span class="sxs-lookup"><span data-stu-id="bddfb-175">None or an object that represents the renamed item.</span></span>

<span data-ttu-id="bddfb-176">Dieses Cmdlet generiert ein Objekt, das das umbenannte Element darstellt, wenn Sie den **passthru** -Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="bddfb-176">This cmdlet generates an object that represents the renamed item, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="bddfb-177">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="bddfb-177">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="bddfb-178">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="bddfb-178">NOTES</span></span>

<span data-ttu-id="bddfb-179">`Rename-Item` ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="bddfb-179">`Rename-Item` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="bddfb-180">Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PsProvider` .</span><span class="sxs-lookup"><span data-stu-id="bddfb-180">To list the providers available in your session, type `Get-PsProvider`.</span></span> <span data-ttu-id="bddfb-181">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="bddfb-181">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="bddfb-182">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="bddfb-182">RELATED LINKS</span></span>

[<span data-ttu-id="bddfb-183">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="bddfb-183">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="bddfb-184">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="bddfb-184">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="bddfb-185">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="bddfb-185">Get-ChildItem</span></span>](Get-ChildItem.md)

[<span data-ttu-id="bddfb-186">Get-Item</span><span class="sxs-lookup"><span data-stu-id="bddfb-186">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="bddfb-187">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="bddfb-187">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="bddfb-188">Move-Item</span><span class="sxs-lookup"><span data-stu-id="bddfb-188">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="bddfb-189">New-Item</span><span class="sxs-lookup"><span data-stu-id="bddfb-189">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="bddfb-190">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="bddfb-190">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="bddfb-191">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="bddfb-191">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="bddfb-192">Set-Item</span><span class="sxs-lookup"><span data-stu-id="bddfb-192">Set-Item</span></span>](Set-Item.md)

[<span data-ttu-id="bddfb-193">about_Providers</span><span class="sxs-lookup"><span data-stu-id="bddfb-193">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
