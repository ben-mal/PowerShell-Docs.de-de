---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 04/07/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-item?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Item
ms.openlocfilehash: 3d33f0e3ab859d839b22a49a88860624ae06ddf2
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211551"
---
# <span data-ttu-id="91985-103">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="91985-103">Remove-Item</span></span>

## <span data-ttu-id="91985-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="91985-104">SYNOPSIS</span></span>
<span data-ttu-id="91985-105">Löscht die angegebenen Elemente.</span><span class="sxs-lookup"><span data-stu-id="91985-105">Deletes the specified items.</span></span>

## <span data-ttu-id="91985-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="91985-106">SYNTAX</span></span>

### <span data-ttu-id="91985-107">Pfad (Standard)</span><span class="sxs-lookup"><span data-stu-id="91985-107">Path (Default)</span></span>

```
Remove-Item [-Path] <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Recurse] [-Force] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-Stream <String[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="91985-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="91985-108">LiteralPath</span></span>

```
Remove-Item -LiteralPath <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Recurse] [-Force] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-Stream <String[]>]
 [<CommonParameters>]
```

## <span data-ttu-id="91985-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="91985-109">DESCRIPTION</span></span>

<span data-ttu-id="91985-110">Mit dem- `Remove-Item` Cmdlet werden ein oder mehrere Elemente gelöscht.</span><span class="sxs-lookup"><span data-stu-id="91985-110">The `Remove-Item` cmdlet deletes one or more items.</span></span> <span data-ttu-id="91985-111">Da es von vielen Anbietern unterstützt wird, können viele verschiedene Elementtypen, einschließlich Dateien, Ordner, Registrierungsschlüssel, Variablen, Aliase und Funktionen, gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="91985-111">Because it is supported by many providers, it can delete many different types of items, including files, folders, registry keys, variables, aliases, and functions.</span></span>

## <span data-ttu-id="91985-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="91985-112">EXAMPLES</span></span>

### <span data-ttu-id="91985-113">Beispiel 1: Löschen von Dateien mit einer Dateinamenerweiterung</span><span class="sxs-lookup"><span data-stu-id="91985-113">Example 1: Delete files that have any file name extension</span></span>

<span data-ttu-id="91985-114">In diesem Beispiel werden alle Dateien gelöscht, deren Namen einen Punkt ( `.` ) aus dem Ordner enthalten `C:\Test` .</span><span class="sxs-lookup"><span data-stu-id="91985-114">This example deletes all of the files that have names that include a dot (`.`) from the `C:\Test` folder.</span></span> <span data-ttu-id="91985-115">Da der Befehl einen Punkt angibt, löscht der Befehl keine Ordner oder Dateien ohne Dateinamenerweiterung.</span><span class="sxs-lookup"><span data-stu-id="91985-115">Because the command specifies a dot, the command does not delete folders or files that have no file name extension.</span></span>

```powershell
Remove-Item C:\Test\*.*
```

### <span data-ttu-id="91985-116">Beispiel 2: Löschen einiger Dokument Dateien in einem Ordner</span><span class="sxs-lookup"><span data-stu-id="91985-116">Example 2: Delete some of the document files in a folder</span></span>

<span data-ttu-id="91985-117">In diesem Beispiel wird aus dem aktuellen Ordner alle Dateien mit einer `.doc` Dateinamenerweiterung und einem Namen gelöscht, der nicht enthält `*1*` .</span><span class="sxs-lookup"><span data-stu-id="91985-117">This example deletes from the current folder all files that have a `.doc` file name extension and a name that does not include `*1*`.</span></span>

```powershell
Remove-Item * -Include *.doc -Exclude *1*
```

<span data-ttu-id="91985-118">Dabei wird das Platzhalter Zeichen ( `*` ) verwendet, um den Inhalt des aktuellen Ordners anzugeben.</span><span class="sxs-lookup"><span data-stu-id="91985-118">It uses the wildcard character (`*`) to specify the contents of the current folder.</span></span> <span data-ttu-id="91985-119">Er verwendet die Parameter " **include** " und " **Exclude** ", um die zu löschenden Dateien anzugeben.</span><span class="sxs-lookup"><span data-stu-id="91985-119">It uses the **Include** and **Exclude** parameters to specify the files to delete.</span></span>

### <span data-ttu-id="91985-120">Beispiel 3: Löschen ausgeblendeter, Schreib geschützter Dateien</span><span class="sxs-lookup"><span data-stu-id="91985-120">Example 3: Delete hidden, read-only files</span></span>

<span data-ttu-id="91985-121">Mit diesem Befehl wird eine Datei gelöscht, die sowohl *ausgeblendet* als auch schreibgeschützt *ist.*</span><span class="sxs-lookup"><span data-stu-id="91985-121">This command deletes a file that is both *hidden* and *read-only* .</span></span>

```powershell
Remove-Item -Path C:\Test\hidden-RO-file.txt -Force
```

<span data-ttu-id="91985-122">Er verwendet den **path** -Parameter, um die Datei anzugeben.</span><span class="sxs-lookup"><span data-stu-id="91985-122">It uses the **Path** parameter to specify the file.</span></span> <span data-ttu-id="91985-123">Er verwendet den **Force** -Parameter, um ihn zu löschen.</span><span class="sxs-lookup"><span data-stu-id="91985-123">It uses the **Force** parameter to delete it.</span></span> <span data-ttu-id="91985-124">Ohne " **Force** " können Sie keine Schreib _geschützten oder_ _ausgeblendeten_ Dateien löschen.</span><span class="sxs-lookup"><span data-stu-id="91985-124">Without **Force** , you cannot delete _read-only_ or _hidden_ files.</span></span>

### <span data-ttu-id="91985-125">Beispiel 4: rekursiver Löschen von Dateien in Unterordnern</span><span class="sxs-lookup"><span data-stu-id="91985-125">Example 4: Delete files in subfolders recursively</span></span>

<span data-ttu-id="91985-126">Mit diesem Befehl werden alle CSV-Dateien im aktuellen Ordner und alle Unterordner rekursiv gelöscht.</span><span class="sxs-lookup"><span data-stu-id="91985-126">This command deletes all of the CSV files in the current folder and all subfolders recursively.</span></span>

<span data-ttu-id="91985-127">Da der **recurse** -Parameter in `Remove-Item` ein bekanntes Problem aufweist, verwendet der Befehl in diesem Beispiel, `Get-ChildItem` um die gewünschten Dateien zu erhalten, und verwendet dann den Pipeline-Operator, um Sie an zu übergeben `Remove-Item` .</span><span class="sxs-lookup"><span data-stu-id="91985-127">Because the **Recurse** parameter in `Remove-Item` has a known issue, the command in this example uses `Get-ChildItem` to get the desired files, and then uses the pipeline operator to pass them to `Remove-Item`.</span></span>

```powershell
Get-ChildItem * -Include *.csv -Recurse | Remove-Item
```

<span data-ttu-id="91985-128">Im `Get-ChildItem` Befehl hat **path** den Wert ( `*` ), der den Inhalt des aktuellen Ordners darstellt.</span><span class="sxs-lookup"><span data-stu-id="91985-128">In the `Get-ChildItem` command, **Path** has a value of (`*`), which represents the contents of the current folder.</span></span> <span data-ttu-id="91985-129">Er verwendet **include** , um den CSV-Dateityp anzugeben, und verwendet **recurse** , um den Abruf rekursiv zu machen.</span><span class="sxs-lookup"><span data-stu-id="91985-129">It uses **Include** to specify the CSV file type, and it uses **Recurse** to make the retrieval recursive.</span></span> <span data-ttu-id="91985-130">Wenn Sie versuchen, den Dateityp anzugeben, z. b. `-Path *.csv` , interpretiert das Cmdlet den Betreff der Suche als Datei ohne untergeordnete Elemente, und die **Rekurse** schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="91985-130">If you try to specify the file type the path, such as `-Path *.csv`, the cmdlet interprets the subject of the search to be a file that has no child items, and **Recurse** fails.</span></span>

### <span data-ttu-id="91985-131">Beispiel 5: rekursiver Löschen von unter Schlüsseln</span><span class="sxs-lookup"><span data-stu-id="91985-131">Example 5: Delete subkeys recursively</span></span>

<span data-ttu-id="91985-132">Mit diesem Befehl werden der Registrierungsschlüssel "oldapp" und alle zugehörigen Unterschlüssel und Werte gelöscht.</span><span class="sxs-lookup"><span data-stu-id="91985-132">This command deletes the "OldApp" registry key and all its subkeys and values.</span></span> <span data-ttu-id="91985-133">Verwendet `Remove-Item` , um den Schlüssel zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="91985-133">It uses `Remove-Item` to remove the key.</span></span> <span data-ttu-id="91985-134">Der Pfad ist angegeben, der optionale Parameter Name ( **path** ) wird jedoch ausgelassen.</span><span class="sxs-lookup"><span data-stu-id="91985-134">The path is specified, but the optional parameter name ( **Path** ) is omitted.</span></span>

<span data-ttu-id="91985-135">Der **recurse** -Parameter löscht den gesamten Inhalt des "oldapp"-Schlüssels rekursiv.</span><span class="sxs-lookup"><span data-stu-id="91985-135">The **Recurse** parameter deletes all of the contents of the "OldApp" key recursively.</span></span> <span data-ttu-id="91985-136">Wenn der Schlüssel Unterschlüssel enthält und Sie den **recurse** -Parameter weglassen, werden Sie aufgefordert, zu bestätigen, dass Sie den Inhalt des Schlüssels löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="91985-136">If the key contains subkeys and you omit the **Recurse** parameter, you are prompted to confirm that you want to delete the contents of the key.</span></span>

```powershell
Remove-Item HKLM:\Software\MyCompany\OldApp -Recurse
```

### <span data-ttu-id="91985-137">Beispiel 6: Löschen von Dateien mit Sonderzeichen</span><span class="sxs-lookup"><span data-stu-id="91985-137">Example 6: Deleting files with special characters</span></span>

<span data-ttu-id="91985-138">Im folgenden Beispiel wird gezeigt, wie Sie Dateien löschen, die Sonderzeichen wie eckige Klammern oder Klammern enthalten.</span><span class="sxs-lookup"><span data-stu-id="91985-138">The following example shows how to delete files that contain special characters like brackets or parentheses.</span></span>

```powershell
Get-ChildItem
```

```Output
    Directory: C:\temp\Downloads

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a---          6/1/2018  12:19 PM           1362 myFile.txt
-a---          6/1/2018  12:30 PM           1132 myFile[1].txt
-a---          6/1/2018  12:19 PM           1283 myFile[2].txt
-a---          6/1/2018  12:19 PM           1432 myFile[3].txt

```

```powershell
Get-ChildItem | Where-Object Name -Like '*`[*'
```

```Output
    Directory: C:\temp\Downloads

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a---          6/1/2018  12:30 PM           1132 myFile[1].txt
-a---          6/1/2018  12:19 PM           1283 myFile[2].txt
-a---          6/1/2018  12:19 PM           1432 myFile[3].txt

```

```powershell
Get-ChildItem | Where-Object Name -Like '*`[*' | ForEach-Object { Remove-Item -LiteralPath $_.Name }
Get-ChildItem
```

```Output
    Directory: C:\temp\Downloads

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a---          6/1/2018  12:19 PM           1362 myFile.txt
```

### <span data-ttu-id="91985-139">Beispiel 7: Entfernen eines alternativen Datenstroms</span><span class="sxs-lookup"><span data-stu-id="91985-139">Example 7: Remove an alternate data stream</span></span>

<span data-ttu-id="91985-140">Dieses Beispiel zeigt, wie Sie den dynamischen **Stream** -Parameter des `Remove-Item` Cmdlets verwenden, um einen alternativen Datenstrom zu löschen.</span><span class="sxs-lookup"><span data-stu-id="91985-140">This example shows how to use the **Stream** dynamic parameter of the `Remove-Item` cmdlet to delete an alternate data stream.</span></span> <span data-ttu-id="91985-141">Der Stream-Parameter wird in Windows PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="91985-141">The stream parameter is introduced in Windows PowerShell 3.0.</span></span>

```powershell
Get-Item C:\Test\Copy-Script.ps1 -Stream Zone.Identifier
```

```Output
   FileName: \\C:\Test\Copy-Script.ps1

Stream                   Length
------                   ------
Zone.Identifier              26

```

```powershell
Remove-Item C:\Test\Copy-Script.ps1 -Stream Zone.Identifier
Get-Item C:\Test\Copy-Script.ps1 -Stream Zone.Identifier
```

```Output
Get-Item : Could not open alternate data stream 'Zone.Identifier' of file 'C:\Test\Copy-Script.ps1'.
At line:1 char:1
+ Get-Item 'C:\Test\Copy-Script.ps1' -Stream Zone.Identifier
+ [!INCLUDE[]()][!INCLUDE[]()][!INCLUDE[]()][!INCLUDE[]()][!INCLUDE[]()]~~
    + CategoryInfo          : ObjectNotFound: (C:\Test\Copy-Script.ps1:String) [Get-Item], FileNotFoundE
   xception
    + FullyQualifiedErrorId : AlternateDataStreamNotFound,Microsoft.PowerShell.Commands.GetItemCommand

```

<span data-ttu-id="91985-142">Der **Stream** -Parameter ruft `Get-Item` den " **Zone. Identifier** "-Stream der `Copy-Script.ps1` Datei ab.</span><span class="sxs-lookup"><span data-stu-id="91985-142">The **Stream** parameter `Get-Item` gets the **Zone.Identifier** stream of the `Copy-Script.ps1` file.</span></span> <span data-ttu-id="91985-143">`Remove-Item` verwendet den **Stream** -Parameter, um den " **Zone. Identifier** "-Stream der Datei zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="91985-143">`Remove-Item` uses the **Stream** parameter to remove the **Zone.Identifier** stream of the file.</span></span> <span data-ttu-id="91985-144">Zum Schluss `Get-Item` zeigt das Cmdlet, dass der Datenstrom " **Zone. Identifier** " gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="91985-144">Finally, the `Get-Item` cmdlet shows that the **Zone.Identifier** stream was deleted.</span></span>

## <span data-ttu-id="91985-145">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="91985-145">PARAMETERS</span></span>

### <span data-ttu-id="91985-146">-Credential</span><span class="sxs-lookup"><span data-stu-id="91985-146">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="91985-147">Dieser Parameter wird von Anbietern, die mit PowerShell installiert wurden, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="91985-147">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="91985-148">Verwenden Sie zum Annehmen der Identität eines anderen Benutzers oder zum herauf Stufen ihrer Anmelde Informationen bei der Ausführung dieses Cmdlets "Start [-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)".</span><span class="sxs-lookup"><span data-stu-id="91985-148">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="91985-149">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="91985-149">-Exclude</span></span>

<span data-ttu-id="91985-150">Gibt als Zeichen folgen Array ein Element oder Elemente an, die von diesem Cmdlet im Vorgang ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="91985-150">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="91985-151">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="91985-151">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="91985-152">Geben Sie ein Pfad Element oder-Muster ein, z `*.txt` . b..</span><span class="sxs-lookup"><span data-stu-id="91985-152">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="91985-153">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="91985-153">Wildcard characters are permitted.</span></span> <span data-ttu-id="91985-154">Der **Exclude** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.</span><span class="sxs-lookup"><span data-stu-id="91985-154">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="91985-155">-Filter</span><span class="sxs-lookup"><span data-stu-id="91985-155">-Filter</span></span>

<span data-ttu-id="91985-156">Gibt einen Filter zum Qualifizieren des **path** -Parameters an.</span><span class="sxs-lookup"><span data-stu-id="91985-156">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="91985-157">Der [File System](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) -Anbieter ist der einzige installierte PowerShell-Anbieter, der die Verwendung von Filtern unterstützt.</span><span class="sxs-lookup"><span data-stu-id="91985-157">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="91985-158">Die Syntax für die Filter Sprache des **Dateisystems** finden Sie in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="91985-158">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="91985-159">Filter sind effizienter als andere Parameter, da Sie vom Anbieter angewendet werden, wenn das Cmdlet die Objekte abruft, statt dass PowerShell die Objekte nach dem Abrufen filtert.</span><span class="sxs-lookup"><span data-stu-id="91985-159">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="91985-160">-Force</span><span class="sxs-lookup"><span data-stu-id="91985-160">-Force</span></span>

<span data-ttu-id="91985-161">Zwingt das Cmdlet, Elemente zu entfernen, die anderweitig nicht geändert werden können, z. b. ausgeblendete oder schreibgeschützte Dateien oder schreibgeschützte Aliase oder Variablen.</span><span class="sxs-lookup"><span data-stu-id="91985-161">Forces the cmdlet to remove items that cannot otherwise be changed, such as hidden or read-only files or read-only aliases or variables.</span></span> <span data-ttu-id="91985-162">Mit dem Cmdlet können keine konstanten Aliase oder Variablen entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="91985-162">The cmdlet cannot remove constant aliases or variables.</span></span>
<span data-ttu-id="91985-163">Die Implementierung unterscheidet sich bei den einzelnen Anbietern.</span><span class="sxs-lookup"><span data-stu-id="91985-163">Implementation varies from provider to provider.</span></span> <span data-ttu-id="91985-164">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="91985-164">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span> <span data-ttu-id="91985-165">Selbst bei Verwendung des **Force** -Parameters kann das Cmdlet keine Sicherheitseinschränkungen außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="91985-165">Even using the **Force** parameter, the cmdlet cannot override security restrictions.</span></span>

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

### <span data-ttu-id="91985-166">-Include</span><span class="sxs-lookup"><span data-stu-id="91985-166">-Include</span></span>

<span data-ttu-id="91985-167">Gibt als Zeichen folgen Array ein Element oder Elemente an, die dieses Cmdlet in den Vorgang einschließt.</span><span class="sxs-lookup"><span data-stu-id="91985-167">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="91985-168">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="91985-168">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="91985-169">Geben Sie ein Pfad Element oder-Muster ein, z `"*.txt"` . b..</span><span class="sxs-lookup"><span data-stu-id="91985-169">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="91985-170">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="91985-170">Wildcard characters are permitted.</span></span> <span data-ttu-id="91985-171">Der **include** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.</span><span class="sxs-lookup"><span data-stu-id="91985-171">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="91985-172">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="91985-172">-LiteralPath</span></span>

<span data-ttu-id="91985-173">Gibt einen Pfad zu einem oder mehreren Speicherorten an.</span><span class="sxs-lookup"><span data-stu-id="91985-173">Specifies a path to one or more locations.</span></span> <span data-ttu-id="91985-174">Der Wert von **literalpath** wird genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="91985-174">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="91985-175">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="91985-175">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="91985-176">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="91985-176">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="91985-177">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="91985-177">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="91985-178">Weitere Informationen finden Sie unter [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="91985-178">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="91985-179">-Path</span><span class="sxs-lookup"><span data-stu-id="91985-179">-Path</span></span>

<span data-ttu-id="91985-180">Gibt einen Pfad zu den Elementen an, die entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="91985-180">Specifies a path of the items being removed.</span></span>
<span data-ttu-id="91985-181">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="91985-181">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="91985-182">-Recurse</span><span class="sxs-lookup"><span data-stu-id="91985-182">-Recurse</span></span>

<span data-ttu-id="91985-183">Gibt an, dass dieses Cmdlet die Elemente an den angegebenen Speicherorten und in allen untergeordneten Elementen der Speicherorte löscht.</span><span class="sxs-lookup"><span data-stu-id="91985-183">Indicates that this cmdlet deletes the items in the specified locations and in all child items of the locations.</span></span>

<span data-ttu-id="91985-184">Bei Verwendung mit dem **include** -Parameter löscht der **recurse** -Parameter möglicherweise nicht alle Unterordner oder alle untergeordneten Elemente.</span><span class="sxs-lookup"><span data-stu-id="91985-184">When it is used with the **Include** parameter, the **Recurse** parameter might not delete all subfolders or all child items.</span></span> <span data-ttu-id="91985-185">Dies ist ein bekanntes Problem.</span><span class="sxs-lookup"><span data-stu-id="91985-185">This is a known issue.</span></span> <span data-ttu-id="91985-186">Um dieses Problem zu umgehen, können Sie die Ergebnisse des `Get-ChildItem -Recurse` Befehls an weiterleiten `Remove-Item` , wie in "Beispiel 4" in diesem Thema beschrieben.</span><span class="sxs-lookup"><span data-stu-id="91985-186">As a workaround, try piping results of the `Get-ChildItem -Recurse` command to `Remove-Item`, as described in "Example 4" in this topic.</span></span>

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

### <span data-ttu-id="91985-187">-Stream</span><span class="sxs-lookup"><span data-stu-id="91985-187">-Stream</span></span>

<span data-ttu-id="91985-188">Der **Stream** -Parameter ist ein dynamischer Parameter, den der File System-Anbieter hinzufügt `Remove-Item` .</span><span class="sxs-lookup"><span data-stu-id="91985-188">The **Stream** parameter is a dynamic parameter that the FileSystem provider adds to `Remove-Item`.</span></span>
<span data-ttu-id="91985-189">Dieser Parameter funktioniert nur in Dateisystemlaufwerken.</span><span class="sxs-lookup"><span data-stu-id="91985-189">This parameter works only in file system drives.</span></span>

<span data-ttu-id="91985-190">Sie können verwenden `Remove-Item` , um einen alternativen Datenstrom zu löschen.</span><span class="sxs-lookup"><span data-stu-id="91985-190">You can use `Remove-Item` to delete an alternative data stream.</span></span> <span data-ttu-id="91985-191">Es ist jedoch nicht die empfohlene Methode, Sicherheitsüberprüfungen zu deaktivieren, die Dateien blockieren, die aus dem Internet heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="91985-191">However, it is not the recommended way to eliminate security checks that block files that are downloaded from the Internet.</span></span> <span data-ttu-id="91985-192">Wenn Sie überprüfen, ob eine heruntergeladene Datei sicher ist, verwenden Sie das- `Unblock-File` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="91985-192">If you verify that a downloaded file is safe, use the `Unblock-File` cmdlet.</span></span>

<span data-ttu-id="91985-193">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="91985-193">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="91985-194">-Confirm</span><span class="sxs-lookup"><span data-stu-id="91985-194">-Confirm</span></span>

<span data-ttu-id="91985-195">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="91985-195">Prompts you for confirmation before running the cmdlet.</span></span> <span data-ttu-id="91985-196">Weitere Informationen finden Sie in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="91985-196">For more information, see the following articles:</span></span>

- [<span data-ttu-id="91985-197">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="91985-197">about_Preference_Variables</span></span>](../microsoft.powershell.core/about/about_preference_variables.md#confirmpreference)
- [<span data-ttu-id="91985-198">about_Functions_CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="91985-198">about_Functions_CmdletBindingAttribute</span></span>](../microsoft.powershell.core/about/about_functions_cmdletbindingattribute.md?#confirmimpact)

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

### <span data-ttu-id="91985-199">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="91985-199">-WhatIf</span></span>

<span data-ttu-id="91985-200">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="91985-200">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="91985-201">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="91985-201">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="91985-202">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="91985-202">CommonParameters</span></span>

<span data-ttu-id="91985-203">Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="91985-203">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="91985-204">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="91985-204">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="91985-205">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="91985-205">INPUTS</span></span>

### <span data-ttu-id="91985-206">System.String</span><span class="sxs-lookup"><span data-stu-id="91985-206">System.String</span></span>

<span data-ttu-id="91985-207">Sie können eine Zeichenfolge, die einen Pfad, aber keinen literalpfad enthält, an dieses Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="91985-207">You can pipe a string that contains a path, but not a literal path, to this cmdlet.</span></span>

## <span data-ttu-id="91985-208">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="91985-208">OUTPUTS</span></span>

### <span data-ttu-id="91985-209">Keine</span><span class="sxs-lookup"><span data-stu-id="91985-209">None</span></span>

<span data-ttu-id="91985-210">Dieses Cmdlet gibt keine Ausgabe zurück.</span><span class="sxs-lookup"><span data-stu-id="91985-210">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="91985-211">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="91985-211">NOTES</span></span>

<span data-ttu-id="91985-212">Das- `Remove-Item` Cmdlet ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="91985-212">The `Remove-Item` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="91985-213">Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PsProvider` .</span><span class="sxs-lookup"><span data-stu-id="91985-213">To list the providers available in your session, type `Get-PsProvider`.</span></span> <span data-ttu-id="91985-214">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="91985-214">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

<span data-ttu-id="91985-215">Wenn Sie versuchen, einen Ordner zu löschen, der Elemente ohne Verwendung des **recurse** -Parameters enthält, fordert das Cmdlet zur Bestätigung auf.</span><span class="sxs-lookup"><span data-stu-id="91985-215">When you try to delete a folder that contains items without using the **Recurse** parameter, the cmdlet prompts for confirmation.</span></span> <span data-ttu-id="91985-216">Die Verwendung von `-Confirm:$false` unterdrückt die Eingabeaufforderung nicht.</span><span class="sxs-lookup"><span data-stu-id="91985-216">Using `-Confirm:$false` does not suppress the prompt.</span></span> <span data-ttu-id="91985-217">Dies ist beabsichtigt.</span><span class="sxs-lookup"><span data-stu-id="91985-217">This is by design.</span></span>

## <span data-ttu-id="91985-218">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="91985-218">RELATED LINKS</span></span>

[<span data-ttu-id="91985-219">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="91985-219">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="91985-220">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="91985-220">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="91985-221">Get-Item</span><span class="sxs-lookup"><span data-stu-id="91985-221">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="91985-222">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="91985-222">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="91985-223">Move-Item</span><span class="sxs-lookup"><span data-stu-id="91985-223">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="91985-224">New-Item</span><span class="sxs-lookup"><span data-stu-id="91985-224">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="91985-225">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="91985-225">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="91985-226">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="91985-226">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="91985-227">Set-Item</span><span class="sxs-lookup"><span data-stu-id="91985-227">Set-Item</span></span>](Set-Item.md)

[<span data-ttu-id="91985-228">about_Providers</span><span class="sxs-lookup"><span data-stu-id="91985-228">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="91985-229">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="91985-229">about_Preference_Variables</span></span>](../microsoft.powershell.core/about/about_preference_variables.md#confirmpreference)

[<span data-ttu-id="91985-230">about_Functions_CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="91985-230">about_Functions_CmdletBindingAttribute</span></span>](../microsoft.powershell.core/about/about_functions_cmdletbindingattribute.md?#confirmimpact)

