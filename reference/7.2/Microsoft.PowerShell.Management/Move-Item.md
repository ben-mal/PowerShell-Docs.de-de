---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 05/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/move-item?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Move-Item
ms.openlocfilehash: a47c017371fe5fe87618c11551cd1ecba76d5c60
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600314"
---
# <span data-ttu-id="09591-102">Move-Item</span><span class="sxs-lookup"><span data-stu-id="09591-102">Move-Item</span></span>

## <span data-ttu-id="09591-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="09591-103">SYNOPSIS</span></span>
<span data-ttu-id="09591-104">Verschiebt ein Element von einem Speicherort an einen anderen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="09591-104">Moves an item from one location to another.</span></span>

## <span data-ttu-id="09591-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="09591-105">SYNTAX</span></span>

### <span data-ttu-id="09591-106">Pfad (Standard)</span><span class="sxs-lookup"><span data-stu-id="09591-106">Path (Default)</span></span>

```
Move-Item [-Path] <String[]> [[-Destination] <String>] [-Force] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-PassThru] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="09591-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="09591-107">LiteralPath</span></span>

```
Move-Item -LiteralPath <String[]> [[-Destination] <String>] [-Force] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-PassThru] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="09591-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="09591-108">DESCRIPTION</span></span>

<span data-ttu-id="09591-109">`Move-Item`Mit dem-Cmdlet wird ein Element einschließlich seiner Eigenschaften, Inhalte und untergeordneten Elemente von einem Speicherort an einen anderen Speicherort verschoben.</span><span class="sxs-lookup"><span data-stu-id="09591-109">The `Move-Item` cmdlet moves an item, including its properties, contents, and child items, from one location to another location.</span></span> <span data-ttu-id="09591-110">Die Speicherorte müssen vom selben Anbieter unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="09591-110">The locations must be supported by the same provider.</span></span>
<span data-ttu-id="09591-111">Beispielsweise kann eine Datei oder ein Unterverzeichnis von einem Verzeichnis in ein anderes oder ein Registrierungsunterschlüssel von einem Schlüssel in einen anderen verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="09591-111">For example, it can move a file or subdirectory from one directory to another or move a registry subkey from one key to another.</span></span>
<span data-ttu-id="09591-112">Beim Verschieben eines Elements wird dieses am neuen Speicherort hinzugefügt und an seinem ursprünglichen Speicherort gelöscht.</span><span class="sxs-lookup"><span data-stu-id="09591-112">When you move an item, it is added to the new location and deleted from its original location.</span></span>

## <span data-ttu-id="09591-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="09591-113">EXAMPLES</span></span>

### <span data-ttu-id="09591-114">Beispiel 1: Verschieben einer Datei in ein anderes Verzeichnis und Umbenennen</span><span class="sxs-lookup"><span data-stu-id="09591-114">Example 1: Move a file to another directory and rename it</span></span>

<span data-ttu-id="09591-115">Dieser Befehl verschiebt die `Test.txt` Datei vom `C:` Laufwerk in das `E:\Temp` Verzeichnis und benennt Sie von `test.txt` in um `tst.txt` .</span><span class="sxs-lookup"><span data-stu-id="09591-115">This command moves the `Test.txt` file from the `C:` drive to the `E:\Temp` directory and renames it from `test.txt` to `tst.txt`.</span></span>

```powershell
Move-Item -Path C:\test.txt -Destination E:\Temp\tst.txt
```

### <span data-ttu-id="09591-116">Beispiel 2: Verschieben eines Verzeichnisses und seiner Inhalte in ein anderes Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="09591-116">Example 2: Move a directory and its contents to another directory</span></span>

<span data-ttu-id="09591-117">Dieser Befehl verschiebt das `C:\Temp` Verzeichnis und seinen Inhalt in das `C:\Logs` Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="09591-117">This command moves the `C:\Temp` directory and its contents to the `C:\Logs` directory.</span></span>
<span data-ttu-id="09591-118">Das Verzeichnis "Temp" und alle zugehörigen Unterverzeichnisse und Dateien werden dann im Verzeichnis "Logs" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="09591-118">The "Temp" directory, and all of its subdirectories and files, then appear in the "Logs" directory.</span></span>

```powershell
Move-Item -Path C:\Temp -Destination C:\Logs
```

### <span data-ttu-id="09591-119">Beispiel 3: Verschieben aller Dateien einer angegebenen Erweiterung aus dem aktuellen Verzeichnis in ein anderes Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="09591-119">Example 3: Move all files of a specified extension from the current directory to another directory</span></span>

<span data-ttu-id="09591-120">Mit diesem Befehl werden alle Textdateien ( `*.txt` ) im aktuellen Verzeichnis (dargestellt durch einen Punkt ( `.` )) in das Verzeichnis verschoben `C:\Logs` .</span><span class="sxs-lookup"><span data-stu-id="09591-120">This command moves all of the text files (`*.txt`) in the current directory (represented by a dot (`.`)) to the `C:\Logs` directory.</span></span>

```powershell
Move-Item -Path .\*.txt -Destination C:\Logs
```

### <span data-ttu-id="09591-121">Beispiel 4: rekursiver Verschieben aller Dateien einer angegebenen Erweiterung aus dem aktuellen Verzeichnis in ein anderes Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="09591-121">Example 4: Recursively move all files of a specified extension from the current directory to another directory</span></span>

<span data-ttu-id="09591-122">Mit diesem Befehl werden alle Textdateien aus dem aktuellen Verzeichnis und allen Unterverzeichnissen rekursiv in das Verzeichnis "c:\textfiles" verschoben.</span><span class="sxs-lookup"><span data-stu-id="09591-122">This command moves all of the text files from the current directory and all subdirectories, recursively, to the "C:\TextFiles" directory.</span></span>

```powershell
Get-ChildItem -Path ".\*.txt" -Recurse | Move-Item -Destination "C:\TextFiles"
```

<span data-ttu-id="09591-123">Der Befehl verwendet das `Get-ChildItem` Cmdlet, um alle untergeordneten Elemente im aktuellen Verzeichnis (dargestellt durch den Punkt \[ \] ) und seine Unterverzeichnisse mit der *Dateinamenerweiterung ". txt" abzurufen. Er verwendet den **recurse** -Parameter, um den Abruf rekursiv zu machen, und den Include-Parameter, um den Abruf auf "*. txt"-Dateien zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="09591-123">The command uses the `Get-ChildItem` cmdlet to get all of the child items in the current directory (represented by the dot \[.\]) and its subdirectories that have a "*.txt" file name extension. It uses the **Recurse** parameter to make the retrieval recursive and the Include parameter to limit the retrieval to "*.txt" files.</span></span>

<span data-ttu-id="09591-124">Der Pipeline Operator ( `|` ) sendet die Ergebnisse dieses Befehls an `Move-Item` , wodurch die Textdateien in das Verzeichnis "Textfiles" verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="09591-124">The pipeline operator (`|`) sends the results of this command to `Move-Item`, which moves the text files to the "TextFiles" directory.</span></span>

<span data-ttu-id="09591-125">Wenn Dateien, die in "c:\textfiles" verschoben werden sollen, denselben Namen aufweisen, wird von `Move-Item` ein Fehler angezeigt und der Vorgang fortgesetzt, es wird jedoch nur eine Datei mit jedem Namen in "c:\textfiles" verschoben.</span><span class="sxs-lookup"><span data-stu-id="09591-125">If files that are to be moved to "C:\Textfiles" have the same name, `Move-Item` displays an error and continues, but it moves only one file with each name to "C:\Textfiles".</span></span>
<span data-ttu-id="09591-126">Die anderen Dateien verbleiben in ihren ursprünglichen Verzeichnissen.</span><span class="sxs-lookup"><span data-stu-id="09591-126">The other files remain in their original directories.</span></span>

<span data-ttu-id="09591-127">Wenn das Verzeichnis "Textfiles" (oder ein beliebiges anderes Element des Zielpfads) nicht vorhanden ist, schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="09591-127">If the "Textfiles" directory (or any other element of the destination path) does not exist, the command fails.</span></span>
<span data-ttu-id="09591-128">Das fehlende Verzeichnis wird nicht für Sie erstellt, auch wenn Sie den **Force** -Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="09591-128">The missing directory is not created for you, even if you use the **Force** parameter.</span></span>
<span data-ttu-id="09591-129">`Move-Item` Verschiebt das erste Element in eine Datei mit dem Namen "Textfiles" und zeigt dann einen Fehler an, in dem erläutert wird, dass die Datei bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="09591-129">`Move-Item` moves the first item to a file called "Textfiles" and then displays an error explaining that the file already exists.</span></span>

<span data-ttu-id="09591-130">Außerdem werden von standardmäßig keine ausgeblendeten `Get-ChildItem` Dateien verschoben.</span><span class="sxs-lookup"><span data-stu-id="09591-130">Also, by default, `Get-ChildItem` does not move hidden files.</span></span>
<span data-ttu-id="09591-131">Um verborgene Dateien zu verschieben, verwenden Sie den **Force** -Parameter mit `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="09591-131">To move hidden files, use the **Force** parameter with `Get-ChildItem`.</span></span>

> [!NOTE]
> <span data-ttu-id="09591-132">In Windows PowerShell 2,0 muss bei Verwendung des **recurse** -Parameters des `Get-ChildItem` Cmdlets der Wert des **path** -Parameters ein Container sein.</span><span class="sxs-lookup"><span data-stu-id="09591-132">In Windows PowerShell 2.0, when using the **Recurse** parameter of the `Get-ChildItem` cmdlet, the value of the **Path** parameter must be a container.</span></span>
> <span data-ttu-id="09591-133">Geben Sie den Filter für die Dateinamenerweiterung %%amp;quot;.txt%%amp;quot; mithilfe des **Include**-Parameters an (`Get-ChildItem -Path .\* -Include *.txt -Recurse | Move-Item -Destination C:\TextFiles`).</span><span class="sxs-lookup"><span data-stu-id="09591-133">Use the **Include** parameter to specify the .txt file name extension filter (`Get-ChildItem -Path .\* -Include *.txt -Recurse | Move-Item -Destination C:\TextFiles`).</span></span>

### <span data-ttu-id="09591-134">Beispiel 5: Verschieben von Registrierungs Schlüsseln und-Werten in einen anderen Schlüssel</span><span class="sxs-lookup"><span data-stu-id="09591-134">Example 5: Move registry keys and values to another key</span></span>

<span data-ttu-id="09591-135">Mit diesem Befehl werden die Registrierungsschlüssel und-Werte innerhalb des Registrierungsschlüssels "MyCompany" in in `HKLM\Software` den Schlüssel "mynewcompany" verschoben.</span><span class="sxs-lookup"><span data-stu-id="09591-135">This command moves the registry keys and values within the "MyCompany" registry key in `HKLM\Software` to the "MyNewCompany" key.</span></span>
<span data-ttu-id="09591-136">Das Platzhalter Zeichen ( `*` ) gibt an, dass der Inhalt des Schlüssels "MyCompany" und nicht der Schlüssel selbst verschoben werden soll.</span><span class="sxs-lookup"><span data-stu-id="09591-136">The wildcard character (`*`) indicates that the contents of the "MyCompany" key should be moved, not the key itself.</span></span>
<span data-ttu-id="09591-137">In diesem Befehl werden die optionalen **Pfad** -und **Ziel** Parameternamen ausgelassen.</span><span class="sxs-lookup"><span data-stu-id="09591-137">In this command, the optional **Path** and **Destination** parameter names are omitted.</span></span>

```powershell
Move-Item "HKLM:\software\mycompany\*" "HKLM:\software\mynewcompany"
```

### <span data-ttu-id="09591-138">Beispiel 6: Verschieben eines Verzeichnisses und seiner Inhalte in ein Unterverzeichnis des angegebenen Verzeichnisses</span><span class="sxs-lookup"><span data-stu-id="09591-138">Example 6: Move a directory and its contents to a subdirectory of the specified directory</span></span>

<span data-ttu-id="09591-139">Mit diesem Befehl wird das Verzeichnis "Logs \[ \` \] . 06" (und dessen Inhalt) in das Verzeichnis "Logs \[ 2006 \] " verschoben.</span><span class="sxs-lookup"><span data-stu-id="09591-139">This command moves the "Logs\[Sept\`06\]" directory (and its contents) into the "Logs\[2006\]" directory.</span></span>

```powershell
Move-Item -LiteralPath 'Logs[Sept`06]' -Destination 'Logs[2006]'
```

<span data-ttu-id="09591-140">Der **literalpath** -Parameter wird anstelle von **path** verwendet, da der ursprüngliche Verzeichnisname linke eckige Klammer und rechte eckige Klammern (" \[ " und " \] ") enthält.</span><span class="sxs-lookup"><span data-stu-id="09591-140">The **LiteralPath** parameter is used instead of **Path**, because the original directory name includes left bracket and right bracket characters ("\[" and "\]").</span></span>
<span data-ttu-id="09591-141">Der Pfad wird auch in einfache Anführungszeichen (' ') eingeschlossen, sodass das Graviszeichen-Symbol ( \` ) nicht falsch interpretiert wird.</span><span class="sxs-lookup"><span data-stu-id="09591-141">The path is also enclosed in single quotation marks (' '), so that the backtick symbol (\`) is not misinterpreted.</span></span>

<span data-ttu-id="09591-142">Der **Destination** -Parameter erfordert keinen literalen Pfad, da die Zielvariable auch in einfache Anführungszeichen eingeschlossen werden muss, da Sie eckige Klammern enthält, die falsch interpretiert werden können.</span><span class="sxs-lookup"><span data-stu-id="09591-142">The **Destination** parameter does not require a literal path, because the Destination variable also must be enclosed in single quotation marks, because it includes brackets that can be misinterpreted.</span></span>

## <span data-ttu-id="09591-143">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="09591-143">PARAMETERS</span></span>

### <span data-ttu-id="09591-144">-Credential</span><span class="sxs-lookup"><span data-stu-id="09591-144">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="09591-145">Dieser Parameter wird von Anbietern, die mit PowerShell installiert wurden, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="09591-145">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="09591-146">Verwenden Sie zum Annehmen der Identität eines anderen Benutzers oder zum herauf Stufen ihrer Anmelde Informationen bei der Ausführung dieses Cmdlets "Start [-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)".</span><span class="sxs-lookup"><span data-stu-id="09591-146">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="09591-147">-Destination</span><span class="sxs-lookup"><span data-stu-id="09591-147">-Destination</span></span>

<span data-ttu-id="09591-148">Gibt den Pfad zum Speicherort an, an den die Elemente verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="09591-148">Specifies the path to the location where the items are being moved.</span></span>
<span data-ttu-id="09591-149">Der Standardwert ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="09591-149">The default is the current directory.</span></span>
<span data-ttu-id="09591-150">Platzhalter sind zulässig, das Ergebnis muss jedoch ein einziger Speicherort sein.</span><span class="sxs-lookup"><span data-stu-id="09591-150">Wildcards are permitted, but the result must specify a single location.</span></span>

<span data-ttu-id="09591-151">Um das Element umzubenennen, das verschoben wird, geben Sie im Wert des **Destination** -Parameters einen neuen Namen an.</span><span class="sxs-lookup"><span data-stu-id="09591-151">To rename the item being moved, specify a new name in the value of the **Destination** parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: Current directory
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="09591-152">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="09591-152">-Exclude</span></span>

<span data-ttu-id="09591-153">Gibt als Zeichen folgen Array ein Element oder Elemente an, die von diesem Cmdlet im Vorgang ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="09591-153">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="09591-154">Der Wert dieses Parameters qualifiziert den **Path**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="09591-154">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="09591-155">Geben Sie ein Pfad Element oder-Muster ein, z `*.txt` . b..</span><span class="sxs-lookup"><span data-stu-id="09591-155">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="09591-156">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="09591-156">Wildcard characters are permitted.</span></span> <span data-ttu-id="09591-157">Der **Exclude** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.</span><span class="sxs-lookup"><span data-stu-id="09591-157">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="09591-158">-Filter</span><span class="sxs-lookup"><span data-stu-id="09591-158">-Filter</span></span>

<span data-ttu-id="09591-159">Gibt einen Filter zum Qualifizieren des **path** -Parameters an.</span><span class="sxs-lookup"><span data-stu-id="09591-159">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="09591-160">Der [File System](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) -Anbieter ist der einzige installierte PowerShell-Anbieter, der die Verwendung von Filtern unterstützt.</span><span class="sxs-lookup"><span data-stu-id="09591-160">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="09591-161">Die Syntax für die Filter Sprache des **Dateisystems** finden Sie in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="09591-161">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="09591-162">Filter sind effizienter als andere Parameter, da Sie vom Anbieter angewendet werden, wenn das Cmdlet die Objekte abruft, statt dass PowerShell die Objekte nach dem Abrufen filtert.</span><span class="sxs-lookup"><span data-stu-id="09591-162">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="09591-163">-Force</span><span class="sxs-lookup"><span data-stu-id="09591-163">-Force</span></span>

<span data-ttu-id="09591-164">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="09591-164">Forces the command to run without asking for user confirmation.</span></span>
<span data-ttu-id="09591-165">Die Implementierung unterscheidet sich bei den einzelnen Anbietern.</span><span class="sxs-lookup"><span data-stu-id="09591-165">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="09591-166">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="09591-166">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="09591-167">-Include</span><span class="sxs-lookup"><span data-stu-id="09591-167">-Include</span></span>

<span data-ttu-id="09591-168">Gibt als Zeichen folgen Array ein Element oder Elemente an, die dieses Cmdlet in den Vorgang einschließt.</span><span class="sxs-lookup"><span data-stu-id="09591-168">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="09591-169">Der Wert dieses Parameters qualifiziert den **Path**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="09591-169">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="09591-170">Geben Sie ein Pfad Element oder-Muster ein, z `"*.txt"` . b..</span><span class="sxs-lookup"><span data-stu-id="09591-170">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="09591-171">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="09591-171">Wildcard characters are permitted.</span></span> <span data-ttu-id="09591-172">Der **include** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.</span><span class="sxs-lookup"><span data-stu-id="09591-172">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="09591-173">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="09591-173">-LiteralPath</span></span>

<span data-ttu-id="09591-174">Gibt einen Pfad zu einem oder mehreren Speicherorten an.</span><span class="sxs-lookup"><span data-stu-id="09591-174">Specifies a path to one or more locations.</span></span> <span data-ttu-id="09591-175">Der Wert von **literalpath** wird genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="09591-175">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="09591-176">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="09591-176">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="09591-177">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="09591-177">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="09591-178">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="09591-178">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="09591-179">Weitere Informationen finden Sie unter [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="09591-179">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="09591-180">-PassThru</span><span class="sxs-lookup"><span data-stu-id="09591-180">-PassThru</span></span>

<span data-ttu-id="09591-181">Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="09591-181">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="09591-182">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="09591-182">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="09591-183">-Path</span><span class="sxs-lookup"><span data-stu-id="09591-183">-Path</span></span>

<span data-ttu-id="09591-184">Gibt den Pfad zum aktuellen Speicherort der Elemente an.</span><span class="sxs-lookup"><span data-stu-id="09591-184">Specifies the path to the current location of the items.</span></span>
<span data-ttu-id="09591-185">Der Standardwert ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="09591-185">The default is the current directory.</span></span>
<span data-ttu-id="09591-186">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="09591-186">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: Current directory
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="09591-187">-Confirm</span><span class="sxs-lookup"><span data-stu-id="09591-187">-Confirm</span></span>

<span data-ttu-id="09591-188">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="09591-188">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="09591-189">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="09591-189">-WhatIf</span></span>

<span data-ttu-id="09591-190">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="09591-190">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="09591-191">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="09591-191">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="09591-192">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="09591-192">CommonParameters</span></span>

<span data-ttu-id="09591-193">Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="09591-193">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="09591-194">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="09591-194">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="09591-195">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="09591-195">INPUTS</span></span>

### <span data-ttu-id="09591-196">System.String</span><span class="sxs-lookup"><span data-stu-id="09591-196">System.String</span></span>

<span data-ttu-id="09591-197">Sie können eine Zeichenfolge weiterreichen, die einen Pfad zu diesem Cmdlet enthält.</span><span class="sxs-lookup"><span data-stu-id="09591-197">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="09591-198">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="09591-198">OUTPUTS</span></span>

### <span data-ttu-id="09591-199">None oder ein Objekt, das das verschoderte Element darstellt.</span><span class="sxs-lookup"><span data-stu-id="09591-199">None or an object representing the moved item</span></span>

<span data-ttu-id="09591-200">Wenn Sie den *passthru* -Parameter verwenden, generiert dieses Cmdlet ein Objekt, das das verschoderte Element darstellt.</span><span class="sxs-lookup"><span data-stu-id="09591-200">When you use the *PassThru* parameter, this cmdlet generates an object representing the moved item.</span></span>
<span data-ttu-id="09591-201">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="09591-201">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="09591-202">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="09591-202">NOTES</span></span>

- <span data-ttu-id="09591-203">Mit diesem Cmdlet werden Dateien Zwischenlauf Werken verschoben, die vom gleichen Anbieter unterstützt werden. die Verzeichnisse werden jedoch nur auf demselben Laufwerk verschoben.</span><span class="sxs-lookup"><span data-stu-id="09591-203">This cmdlet will move files between drives that are supported by the same provider, but it will move directories only within the same drive.</span></span>
- <span data-ttu-id="09591-204">Da `Move-Item` mit einem Befehl die Eigenschaften, Inhalte und untergeordneten Elemente eines Elements verschoben werden, sind alle Verschiebungen standardmäßig rekursiv.</span><span class="sxs-lookup"><span data-stu-id="09591-204">Because a `Move-Item` command moves the properties, contents, and child items of an item, all moves are recursive by default.</span></span>
- <span data-ttu-id="09591-205">Dieses Cmdlet ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="09591-205">This cmdlet is designed to work with the data exposed by any provider.</span></span>
  <span data-ttu-id="09591-206">Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="09591-206">To list the providers available in your session, type `Get-PSProvider`.</span></span>
  <span data-ttu-id="09591-207">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="09591-207">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="09591-208">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="09591-208">RELATED LINKS</span></span>

[<span data-ttu-id="09591-209">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="09591-209">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="09591-210">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="09591-210">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="09591-211">Get-Item</span><span class="sxs-lookup"><span data-stu-id="09591-211">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="09591-212">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="09591-212">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="09591-213">New-Item</span><span class="sxs-lookup"><span data-stu-id="09591-213">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="09591-214">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="09591-214">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="09591-215">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="09591-215">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="09591-216">Set-Item</span><span class="sxs-lookup"><span data-stu-id="09591-216">Set-Item</span></span>](Set-Item.md)

[<span data-ttu-id="09591-217">about_Providers</span><span class="sxs-lookup"><span data-stu-id="09591-217">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

