---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/tee-object?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Tee-Object
ms.openlocfilehash: 47c1eb6b31f762e3950c07f9edec81a081ce616e
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93211423"
---
# <span data-ttu-id="a2bfb-103">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="a2bfb-103">Tee-Object</span></span>

## <span data-ttu-id="a2bfb-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="a2bfb-104">SYNOPSIS</span></span>
<span data-ttu-id="a2bfb-105">Speichert die Ausgabe des Befehls in einer Datei oder einer Variablen, und sendet sie über die Pipeline.</span><span class="sxs-lookup"><span data-stu-id="a2bfb-105">Saves command output in a file or variable and also sends it down the pipeline.</span></span>

## <span data-ttu-id="a2bfb-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a2bfb-106">SYNTAX</span></span>

### <span data-ttu-id="a2bfb-107">File (Standard)</span><span class="sxs-lookup"><span data-stu-id="a2bfb-107">File (Default)</span></span>

```
Tee-Object [-InputObject <PSObject>] [-FilePath] <String> [-Append] [<CommonParameters>]
```

### <span data-ttu-id="a2bfb-108">Literalfile</span><span class="sxs-lookup"><span data-stu-id="a2bfb-108">LiteralFile</span></span>

```
Tee-Object [-InputObject <PSObject>] -LiteralPath <String> [<CommonParameters>]
```

### <span data-ttu-id="a2bfb-109">Variable</span><span class="sxs-lookup"><span data-stu-id="a2bfb-109">Variable</span></span>

```
Tee-Object [-InputObject <PSObject>] -Variable <String> [<CommonParameters>]
```

## <span data-ttu-id="a2bfb-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a2bfb-110">DESCRIPTION</span></span>

<span data-ttu-id="a2bfb-111">Das `Tee-Object` Cmdlet leitet die Ausgabe um, d. h., es sendet die Ausgabe eines Befehls in zwei Richtungen (wie z. b. den Buchstaben T).</span><span class="sxs-lookup"><span data-stu-id="a2bfb-111">The `Tee-Object` cmdlet redirects output, that is, it sends the output of a command in two directions (like the letter T).</span></span> <span data-ttu-id="a2bfb-112">Das Cmdlet speichert die Ausgabe in einer Datei oder einer Variablen und sendet sie über die Pipeline.</span><span class="sxs-lookup"><span data-stu-id="a2bfb-112">It stores the output in a file or variable and also sends it down the pipeline.</span></span> <span data-ttu-id="a2bfb-113">Wenn `Tee-Object` der letzte Befehl in der Pipeline ist, wird die Befehlsausgabe an der Eingabeaufforderung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a2bfb-113">If `Tee-Object` is the last command in the pipeline, the command output is displayed at the prompt.</span></span>

## <span data-ttu-id="a2bfb-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="a2bfb-114">EXAMPLES</span></span>

### <span data-ttu-id="a2bfb-115">Beispiel 1: Ausgabeprozesse in einer Datei und an der Konsole</span><span class="sxs-lookup"><span data-stu-id="a2bfb-115">Example 1: Output processes to a file and to the console</span></span>

<span data-ttu-id="a2bfb-116">Dieses Beispiel ruft eine Liste der Prozesse ab, die auf dem Computer ausgeführt werden, und sendet das Ergebnis an eine Datei.</span><span class="sxs-lookup"><span data-stu-id="a2bfb-116">This example gets a list of the processes running on the computer and sends the result to a file.</span></span>
<span data-ttu-id="a2bfb-117">Da kein zweiter Pfad angegeben ist, werden die Prozesse auch in der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a2bfb-117">Because a second path is not specified, the processes are also displayed in the console.</span></span>

```powershell
Get-Process | Tee-Object -FilePath "C:\Test1\testfile2.txt"
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)    Id ProcessName
-------  ------    -----      ----- -----   ------    -- -----------
83       4     2300       4520    39     0.30    4032 00THotkey
272      6     1400       3944    34     0.06    3088 alg
81       3      804       3284    21     2.45     148 ApntEx
81       4     2008       5808    38     0.75    3684 Apoint
...
```

### <span data-ttu-id="a2bfb-118">Beispiel 2: Ausgabeprozesse für eine Variable und `Select-Object`</span><span class="sxs-lookup"><span data-stu-id="a2bfb-118">Example 2: Output processes to a variable and `Select-Object`</span></span>

<span data-ttu-id="a2bfb-119">Dieses Beispiel ruft eine Liste der Prozesse ab, die auf dem Computer ausgeführt werden, speichert Sie in der `$proc` Variablen und leitet Sie an weiter `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="a2bfb-119">This example gets a list of the processes running on the computer, saves them to the `$proc` variable, and pipes them to `Select-Object`.</span></span>

```powershell
Get-Process notepad | Tee-Object -Variable proc | Select-Object processname,handles
```

```Output
ProcessName                              Handles
-----------                              -------
notepad                                  43
notepad                                  37
notepad                                  38
notepad                                  38
```

<span data-ttu-id="a2bfb-120">Mit dem `Select-Object` -Cmdlet werden die Eigenschaften **ProcessName** und **Handles** ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="a2bfb-120">The `Select-Object` cmdlet selects the **ProcessName** and **Handles** properties.</span></span> <span data-ttu-id="a2bfb-121">Beachten Sie, dass die- `$proc` Variable die von zurückgegebenen Standardinformationen enthält `Get-Process` .</span><span class="sxs-lookup"><span data-stu-id="a2bfb-121">Note that the `$proc` variable includes the default information returned by `Get-Process`.</span></span>

### <span data-ttu-id="a2bfb-122">Beispiel 3: Ausgabe von Systemdateien in zwei Protokolldateien</span><span class="sxs-lookup"><span data-stu-id="a2bfb-122">Example 3: Output system files to two log files</span></span>

<span data-ttu-id="a2bfb-123">In diesem Beispiel wird eine Liste von Systemdateien in zwei Protokolldateien gespeichert, einer kumulativen Datei und einer aktuellen Datei.</span><span class="sxs-lookup"><span data-stu-id="a2bfb-123">This example saves a list of system files in a two log files, a cumulative file and a current file.</span></span>

```powershell
Get-ChildItem -Path D: -File -System -Recurse |
  Tee-Object -FilePath "c:\test\AllSystemFiles.txt" -Append |
    Out-File c:\test\NewSystemFiles.txt
```

<span data-ttu-id="a2bfb-124">Der Befehl verwendet das `Get-ChildItem` Cmdlet, um eine rekursive Suche nach Systemdateien auf dem Laufwerk "D:" durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="a2bfb-124">The command uses the `Get-ChildItem` cmdlet to do a recursive search for system files on the D: drive.</span></span> <span data-ttu-id="a2bfb-125">Ein Pipeline Operator (|) sendet die Liste an `Tee-Object` , die die Liste an die AllSystemFiles.txt Datei anfügt und die Liste über die Pipeline an das `Out-File` Cmdlet übergibt, das die Liste in der NewSystemFiles.txt Datei speichert.</span><span class="sxs-lookup"><span data-stu-id="a2bfb-125">A pipeline operator (|) sends the list to `Tee-Object`, which appends the list to the AllSystemFiles.txt file and passes the list down the pipeline to the `Out-File` cmdlet, which saves the list in the NewSystemFiles.txt file.</span></span>

## <span data-ttu-id="a2bfb-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a2bfb-126">PARAMETERS</span></span>

### <span data-ttu-id="a2bfb-127">-Anfügen</span><span class="sxs-lookup"><span data-stu-id="a2bfb-127">-Append</span></span>

<span data-ttu-id="a2bfb-128">Gibt an, dass das Cmdlet die Ausgabe an die angegebene Datei anfügt.</span><span class="sxs-lookup"><span data-stu-id="a2bfb-128">Indicates that the cmdlet appends the output to the specified file.</span></span> <span data-ttu-id="a2bfb-129">Ohne diesen Parameter ersetzt der neue Inhalt vorhandene Inhalte in der Datei ohne Warnung.</span><span class="sxs-lookup"><span data-stu-id="a2bfb-129">Without this parameter, the new content replaces any existing content in the file without warning.</span></span>

<span data-ttu-id="a2bfb-130">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="a2bfb-130">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: File
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a2bfb-131">-FilePath</span><span class="sxs-lookup"><span data-stu-id="a2bfb-131">-FilePath</span></span>

<span data-ttu-id="a2bfb-132">Gibt eine Datei an, die von diesem Cmdlet zum Speichern des Objekts in Platzhalter Zeichen zulässig ist, aber in eine einzelne Datei aufgelöst werden muss.</span><span class="sxs-lookup"><span data-stu-id="a2bfb-132">Specifies a file that this cmdlet saves the object to Wildcard characters are permitted, but must resolve to a single file.</span></span>

```yaml
Type: System.String
Parameter Sets: File
Aliases: Path

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="a2bfb-133">-InputObject</span><span class="sxs-lookup"><span data-stu-id="a2bfb-133">-InputObject</span></span>

<span data-ttu-id="a2bfb-134">Gibt das zu speichernde und anzuzeigende Objekt an.</span><span class="sxs-lookup"><span data-stu-id="a2bfb-134">Specifies the object to be saved and displayed.</span></span> <span data-ttu-id="a2bfb-135">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, durch den die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="a2bfb-135">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span> <span data-ttu-id="a2bfb-136">Sie können ein Objekt auch über die Pipeline an übergeben `Tee-Object` .</span><span class="sxs-lookup"><span data-stu-id="a2bfb-136">You can also pipe an object to `Tee-Object`.</span></span>

<span data-ttu-id="a2bfb-137">Wenn Sie den **Inputobject** -Parameter mit verwenden `Tee-Object` , anstatt Befehls Ergebnisse an zu übergeben `Tee-Object` , wird der **Inputobject** -Wert als einzelnes Objekt behandelt, auch wenn der Wert eine Auflistung ist.</span><span class="sxs-lookup"><span data-stu-id="a2bfb-137">When you use the **InputObject** parameter with `Tee-Object`, instead of piping command results to `Tee-Object`, the **InputObject** value is treated as a single object even if the value is a collection.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="a2bfb-138">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="a2bfb-138">-LiteralPath</span></span>

<span data-ttu-id="a2bfb-139">Gibt eine Datei an, in der dieses Cmdlet das Objekt speichert.</span><span class="sxs-lookup"><span data-stu-id="a2bfb-139">Specifies a file that this cmdlet saves the object to.</span></span> <span data-ttu-id="a2bfb-140">Im Gegensatz zu **FilePath** wird der Wert des **LiteralPath** -Parameters genau wie eingegeben verwendet.</span><span class="sxs-lookup"><span data-stu-id="a2bfb-140">Unlike **FilePath** , the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="a2bfb-141">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="a2bfb-141">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="a2bfb-142">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="a2bfb-142">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="a2bfb-143">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="a2bfb-143">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: LiteralFile
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a2bfb-144">-Variable</span><span class="sxs-lookup"><span data-stu-id="a2bfb-144">-Variable</span></span>

<span data-ttu-id="a2bfb-145">Gibt eine Variable an, in der das Cmdlet das Objekt speichert.</span><span class="sxs-lookup"><span data-stu-id="a2bfb-145">Specifies a variable that the cmdlet saves the object to.</span></span> <span data-ttu-id="a2bfb-146">Geben Sie einen Variablennamen ohne das vorherige Dollarzeichen ( `$` ) ein.</span><span class="sxs-lookup"><span data-stu-id="a2bfb-146">Enter a variable name without the preceding dollar sign (`$`).</span></span>

```yaml
Type: System.String
Parameter Sets: Variable
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a2bfb-147">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a2bfb-147">CommonParameters</span></span>

<span data-ttu-id="a2bfb-148">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a2bfb-148">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a2bfb-149">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a2bfb-149">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a2bfb-150">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="a2bfb-150">INPUTS</span></span>

### <span data-ttu-id="a2bfb-151">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="a2bfb-151">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="a2bfb-152">Sie können Objekte über die Pipeline an übergeben `Tee-Object` .</span><span class="sxs-lookup"><span data-stu-id="a2bfb-152">You can pipe objects to `Tee-Object`.</span></span>

## <span data-ttu-id="a2bfb-153">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="a2bfb-153">OUTPUTS</span></span>

### <span data-ttu-id="a2bfb-154">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="a2bfb-154">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="a2bfb-155">`Tee-Object` Gibt das-Objekt zurück, das es umleitet.</span><span class="sxs-lookup"><span data-stu-id="a2bfb-155">`Tee-Object` returns the object that it redirects.</span></span>

## <span data-ttu-id="a2bfb-156">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="a2bfb-156">NOTES</span></span>

<span data-ttu-id="a2bfb-157">Sie können auch das `Out-File` Cmdlet oder den Umleitungs Operator verwenden, die beide die Ausgabe in einer Datei speichern, aber nicht über die Pipeline senden.</span><span class="sxs-lookup"><span data-stu-id="a2bfb-157">You can also use the `Out-File` cmdlet or the redirection operator, both of which save the output in a file but do not send it down the pipeline.</span></span>

<span data-ttu-id="a2bfb-158">Ab PowerShell 6 `Tee-Object` verwendet die BOM-lose UTF-8-Codierung beim Schreiben in Dateien.</span><span class="sxs-lookup"><span data-stu-id="a2bfb-158">Beginning in PowerShell 6, `Tee-Object` uses BOM-less UTF-8 encoding when it writes to files.</span></span> <span data-ttu-id="a2bfb-159">Wenn Sie eine andere Codierung benötigen, verwenden Sie das- `Out-File` Cmdlet mit dem **Encoding** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="a2bfb-159">If you need a different encoding, use the `Out-File` cmdlet with the **Encoding** parameter.</span></span>

## <span data-ttu-id="a2bfb-160">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="a2bfb-160">RELATED LINKS</span></span>

[<span data-ttu-id="a2bfb-161">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="a2bfb-161">Compare-Object</span></span>](Compare-Object.md)

[<span data-ttu-id="a2bfb-162">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="a2bfb-162">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="a2bfb-163">Group-Object</span><span class="sxs-lookup"><span data-stu-id="a2bfb-163">Group-Object</span></span>](Group-Object.md)

[<span data-ttu-id="a2bfb-164">Measure-Object</span><span class="sxs-lookup"><span data-stu-id="a2bfb-164">Measure-Object</span></span>](Measure-Object.md)

[<span data-ttu-id="a2bfb-165">New-Object</span><span class="sxs-lookup"><span data-stu-id="a2bfb-165">New-Object</span></span>](New-Object.md)

[<span data-ttu-id="a2bfb-166">Select-Object</span><span class="sxs-lookup"><span data-stu-id="a2bfb-166">Select-Object</span></span>](Select-Object.md)

[<span data-ttu-id="a2bfb-167">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="a2bfb-167">Sort-Object</span></span>](Sort-Object.md)

[<span data-ttu-id="a2bfb-168">Where-Object</span><span class="sxs-lookup"><span data-stu-id="a2bfb-168">Where-Object</span></span>](../Microsoft.PowerShell.Core/Where-Object.md)

[<span data-ttu-id="a2bfb-169">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="a2bfb-169">about_Redirection</span></span>](../Microsoft.PowerShell.Core/About/about_Redirection.md)
