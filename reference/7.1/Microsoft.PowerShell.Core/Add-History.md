---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 05/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/add-history?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-History
ms.openlocfilehash: bbc5b6590dc97413350c19c91dbca0b4d08e9bce
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211652"
---
# <span data-ttu-id="ea558-103">Add-History</span><span class="sxs-lookup"><span data-stu-id="ea558-103">Add-History</span></span>

## <span data-ttu-id="ea558-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="ea558-104">SYNOPSIS</span></span>
<span data-ttu-id="ea558-105">Fügt Einträge an den Sitzungsverlauf an.</span><span class="sxs-lookup"><span data-stu-id="ea558-105">Appends entries to the session history.</span></span>

## <span data-ttu-id="ea558-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ea558-106">SYNTAX</span></span>

```
Add-History [[-InputObject] <PSObject[]>] [-Passthru] [<CommonParameters>]
```

## <span data-ttu-id="ea558-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ea558-107">DESCRIPTION</span></span>

<span data-ttu-id="ea558-108">Das- `Add-History` Cmdlet fügt Einträge am Ende des Sitzungs Verlaufs hinzu, d. h. die Liste der Befehle, die während der aktuellen Sitzung eingegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="ea558-108">The `Add-History` cmdlet adds entries to the end of the session history, that is, the list of commands entered during the current session.</span></span>

<span data-ttu-id="ea558-109">Der Sitzungsverlauf ist eine Liste der Befehle, die während der Sitzung eingegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="ea558-109">The session history is a list of the commands entered during the session.</span></span> <span data-ttu-id="ea558-110">Der Sitzungsverlauf stellt die Reihenfolge der Ausführung, den Status und die Start- und Endzeiten des Befehls dar.</span><span class="sxs-lookup"><span data-stu-id="ea558-110">The session history represents the order of execution, the status, and the start and end times of the command.</span></span> <span data-ttu-id="ea558-111">Wenn Sie jeden Befehl eingeben, wird er von PowerShell dem Verlauf hinzugefügt, damit Sie ihn wieder verwenden können.</span><span class="sxs-lookup"><span data-stu-id="ea558-111">As you enter each command, PowerShell adds it to the history so that you can reuse it.</span></span> <span data-ttu-id="ea558-112">Weitere Informationen zum Sitzungsverlauf finden Sie unter [about_History](About/about_History.md).</span><span class="sxs-lookup"><span data-stu-id="ea558-112">For more information about the session history, see [about_History](About/about_History.md).</span></span>

<span data-ttu-id="ea558-113">Der Sitzungsverlauf wird getrennt von dem vom **psread Line** -Modul verwalteten Verlauf verwaltet.</span><span class="sxs-lookup"><span data-stu-id="ea558-113">The session history is managed separately from the history maintained by the **PSReadLine** module.</span></span>
<span data-ttu-id="ea558-114">Beide Verläufe sind in Sitzungen verfügbar, in denen **psread Line** geladen wird.</span><span class="sxs-lookup"><span data-stu-id="ea558-114">Both histories are available in sessions where **PSReadLine** is loaded.</span></span> <span data-ttu-id="ea558-115">Dieses Cmdlet funktioniert nur mit dem Sitzungsverlauf.</span><span class="sxs-lookup"><span data-stu-id="ea558-115">This cmdlet only works with the session history.</span></span> <span data-ttu-id="ea558-116">Weitere Informationen finden Sie unter [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).</span><span class="sxs-lookup"><span data-stu-id="ea558-116">For more information see, [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).</span></span>

<span data-ttu-id="ea558-117">Sie können das `Get-History` Cmdlet verwenden, um die Befehle zu erhalten und Sie an zu übergeben `Add-History` , oder Sie können die Befehle in eine CSV-oder XML-Datei exportieren, die Befehle importieren und die importierte Datei an übergeben `Add-History` .</span><span class="sxs-lookup"><span data-stu-id="ea558-117">You can use the `Get-History` cmdlet to get the commands and pass them to `Add-History`, or you can export the commands to a CSV or XML file, then import the commands, and pass the imported file to `Add-History`.</span></span> <span data-ttu-id="ea558-118">Sie können dieses Cmdlet verwenden, um bestimmte Befehle zum Verlauf hinzuzufügen oder eine einzelne Verlaufsdatei zu erstellen, die Befehle aus mehreren Sitzungen enthält.</span><span class="sxs-lookup"><span data-stu-id="ea558-118">You can use this cmdlet to add specific commands to the history or to create a single history file that includes commands from more than one session.</span></span>

## <span data-ttu-id="ea558-119">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="ea558-119">EXAMPLES</span></span>

### <span data-ttu-id="ea558-120">Beispiel 1: Hinzufügen von Befehlen zum Verlauf einer anderen Sitzung</span><span class="sxs-lookup"><span data-stu-id="ea558-120">Example 1: Add commands to the history of a different session</span></span>

<span data-ttu-id="ea558-121">In diesem Beispiel werden die in einer PowerShell-Sitzung eingegebenen Befehle dem Verlauf einer anderen PowerShell-Sitzung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ea558-121">This example add the commands typed in one PowerShell session to the history of a different PowerShell session.</span></span>

```powershell
Get-History | Export-Csv c:\testing\history.csv -IncludeTypeInformation
Import-Csv c:\testing\history.csv | Add-History
```

<span data-ttu-id="ea558-122">Der erste Befehl ruft die Objekte ab, die die Befehle im Verlauf darstellen, und exportiert Sie in die `History.csv` Datei.</span><span class="sxs-lookup"><span data-stu-id="ea558-122">The first command gets objects representing the commands in the history and exports them to the `History.csv` file.</span></span>

<span data-ttu-id="ea558-123">Der zweite Befehl wird in der Befehlszeile einer anderen Sitzung eingegeben.</span><span class="sxs-lookup"><span data-stu-id="ea558-123">The second command is typed at the command line of a different session.</span></span> <span data-ttu-id="ea558-124">Er verwendet das `Import-Csv` Cmdlet, um die Objekte in die `History.csv` Datei zu importieren.</span><span class="sxs-lookup"><span data-stu-id="ea558-124">It uses the `Import-Csv` cmdlet to import the objects in the `History.csv` file.</span></span> <span data-ttu-id="ea558-125">Der Pipeline Operator ( `|` ) übergibt die Objekte an das `Add-History` Cmdlet, wodurch die Objekte, die die Befehle in der `History.csv` Datei darstellen, dem aktuellen Sitzungsverlauf hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="ea558-125">The pipeline operator (`|`) passes the objects to the `Add-History` cmdlet, which adds the objects representing the commands in the `History.csv` file to the current session history.</span></span>

### <span data-ttu-id="ea558-126">Beispiel 2: Importieren und Ausführen von Befehlen</span><span class="sxs-lookup"><span data-stu-id="ea558-126">Example 2: Import and run commands</span></span>

<span data-ttu-id="ea558-127">In diesem Beispiel werden Befehle aus der `History.xml` Datei importiert, dem aktuellen Sitzungsverlauf hinzugefügt und dann die Befehle im kombinierten Verlauf ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ea558-127">This example imports commands from the `History.xml` file, adds them to the current session history, and then runs the commands in the combined history.</span></span>

```powershell
Import-Clixml c:\temp\history.xml | Add-History -PassThru | ForEach-Object -Process {Invoke-History}
```

<span data-ttu-id="ea558-128">Der erste Befehl verwendet das `Import-Clixml` Cmdlet, um einen Befehlsverlauf zu importieren, der in die Datei exportiert wurde `History.xml` .</span><span class="sxs-lookup"><span data-stu-id="ea558-128">The first command uses the `Import-Clixml` cmdlet to import a command history that was exported to the `History.xml` file.</span></span> <span data-ttu-id="ea558-129">Der Pipeline Operator übergibt die Befehle an das `Add-History` Cmdlet, wodurch die Befehle dem aktuellen Sitzungsverlauf hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="ea558-129">The pipeline operator passes the commands to the `Add-History` cmdlet, which adds the commands to the current session history.</span></span> <span data-ttu-id="ea558-130">Der **passthru** -Parameter übergibt die Objekte, die die hinzugefügten Befehle darstellen, in der Pipeline.</span><span class="sxs-lookup"><span data-stu-id="ea558-130">The **PassThru** parameter passes the objects representing the added commands down the pipeline.</span></span>

<span data-ttu-id="ea558-131">Der Befehl verwendet dann das `ForEach-Object` Cmdlet, um den `Invoke-History` Befehl auf jeden der Befehle im kombinierten Verlauf anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="ea558-131">The command then uses the `ForEach-Object` cmdlet to apply the `Invoke-History` command to each of the commands in the combined history.</span></span> <span data-ttu-id="ea558-132">Der `Invoke-History` Befehl wird als Skriptblock formatiert, der in geschweiften Klammern () eingeschlossen ist `{}` , wie dies für den **Process** -Parameter des `ForEach-Object` Cmdlets erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="ea558-132">The `Invoke-History` command is formatted as a script block, enclosed in braces (`{}`), as required by the **Process** parameter of the `ForEach-Object` cmdlet.</span></span>

### <span data-ttu-id="ea558-133">Beispiel 3: Hinzufügen von Befehlen im Verlauf am Ende des Verlaufs</span><span class="sxs-lookup"><span data-stu-id="ea558-133">Example 3: Add commands in the history to the end of the history</span></span>

<span data-ttu-id="ea558-134">In diesem Beispiel werden die ersten fünf Befehle im Verlauf am Ende der Verlaufs Liste hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ea558-134">This example adds the first five commands in the history to the end of the history list.</span></span>

```powershell
Get-History -Id 5 -Count 5 | Add-History
```

<span data-ttu-id="ea558-135">Mit dem- `Get-History` Cmdlet werden die fünf Befehle abgerufen, die mit dem Befehl 5 enden.</span><span class="sxs-lookup"><span data-stu-id="ea558-135">The `Get-History` cmdlet gets the five commands ending in command 5.</span></span> <span data-ttu-id="ea558-136">Der Pipeline Operator übergibt sie an das- `Add-History` Cmdlet, das Sie an den aktuellen Verlauf anfügt.</span><span class="sxs-lookup"><span data-stu-id="ea558-136">The pipeline operator passes them to the `Add-History` cmdlet, which appends them to the current history.</span></span> <span data-ttu-id="ea558-137">Der `Add-History` Befehl enthält keine Parameter, aber PowerShell verknüpft die Objekte, die durch die Pipeline übergeben werden, mit dem **Inputobject** -Parameter von `Add-History` .</span><span class="sxs-lookup"><span data-stu-id="ea558-137">The `Add-History` command does not include any parameters, but PowerShell associates the objects passed through the pipeline with the **InputObject** parameter of `Add-History`.</span></span>

### <span data-ttu-id="ea558-138">Beispiel 4: Hinzufügen von Befehlen in einer CSV-Datei zum aktuellen Verlauf</span><span class="sxs-lookup"><span data-stu-id="ea558-138">Example 4: Add commands in a .csv file to the current history</span></span>

<span data-ttu-id="ea558-139">In diesem Beispiel werden die Befehle in der `History.csv` Datei dem aktuellen Sitzungsverlauf hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ea558-139">This example add the commands in the `History.csv` file to the current session history.</span></span>

```powershell
$a = Import-Csv c:\testing\history.csv
Add-History -InputObject $a -PassThru
```

<span data-ttu-id="ea558-140">Mit dem `Import-Csv` -Cmdlet werden die Befehle in der `History.csv` Datei importiert und der Inhalt in der Variablen gespeichert `$a` .</span><span class="sxs-lookup"><span data-stu-id="ea558-140">The `Import-Csv` cmdlet imports the commands in the `History.csv` file and store its contents in the variable `$a`.</span></span>

<span data-ttu-id="ea558-141">Der zweite Befehl verwendet das `Add-History` Cmdlet, um die Befehle aus `History.csv` dem aktuellen Sitzungsverlauf hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="ea558-141">The second command uses the `Add-History` cmdlet to add the commands from `History.csv` to the current session history.</span></span> <span data-ttu-id="ea558-142">Er verwendet den **Inputobject** -Parameter, um die Variable anzugeben, `$a` und den **passthru** -Parameter, um ein Objekt zu generieren, das in der Befehlszeile angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="ea558-142">It uses the **InputObject** parameter to specify the `$a` variable and the **PassThru** parameter to generate an object to display at the command line.</span></span> <span data-ttu-id="ea558-143">Ohne den **passthru** -Parameter `Add-History` generiert das Cmdlet keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="ea558-143">Without the **PassThru** parameter, the `Add-History` cmdlet does not generate any output.</span></span>

### <span data-ttu-id="ea558-144">Beispiel 5: Hinzufügen von Befehlen in einer XML-Datei zum aktuellen Verlauf</span><span class="sxs-lookup"><span data-stu-id="ea558-144">Example 5: Add commands in an .xml file to the current history</span></span>

<span data-ttu-id="ea558-145">In diesem Beispiel werden die Befehle in der `history.xml` Datei dem aktuellen Sitzungsverlauf hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ea558-145">This example adds the commands in the `history.xml` file to the current session history.</span></span>

```powershell
Add-History -InputObject (Import-Clixml c:\temp\history.xml)
```

<span data-ttu-id="ea558-146">Der **Inputobject** -Parameter übergibt die Ergebnisse des Befehls in Klammern an das `Add-History` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ea558-146">The **InputObject** parameter passes the results of the command in parentheses to the `Add-History` cmdlet.</span></span> <span data-ttu-id="ea558-147">Der Befehl in Klammern, der zuerst ausgeführt wird, importiert die `history.xml` Datei in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ea558-147">The command in parentheses, which is executed first, imports the `history.xml` file into PowerShell.</span></span> <span data-ttu-id="ea558-148">Das `Add-History` Cmdlet fügt dann die Befehle in der Datei dem Sitzungsverlauf hinzu.</span><span class="sxs-lookup"><span data-stu-id="ea558-148">The `Add-History` cmdlet then adds the commands in the file to the session history.</span></span>

## <span data-ttu-id="ea558-149">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ea558-149">PARAMETERS</span></span>

### <span data-ttu-id="ea558-150">-InputObject</span><span class="sxs-lookup"><span data-stu-id="ea558-150">-InputObject</span></span>

<span data-ttu-id="ea558-151">Gibt ein Array von Einträgen an, die dem Verlauf als **historyinfo** -Objekt zum Sitzungsverlauf hinzugefügt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ea558-151">Specifies an array of entries to add to the history as **HistoryInfo** object to the session history.</span></span>
<span data-ttu-id="ea558-152">Sie können diesen Parameter verwenden, um ein **historyinfo** -Objekt, z. b. diejenigen, die von `Get-History` den `Import-Clixml` Cmdlets, oder zurückgegeben werden `Import-Csv` , an zu senden `Add-History` .</span><span class="sxs-lookup"><span data-stu-id="ea558-152">You can use this parameter to submit a **HistoryInfo** object, such as the ones that are returned by the `Get-History`, `Import-Clixml`, or `Import-Csv` cmdlets, to `Add-History`.</span></span>

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="ea558-153">-Passthru</span><span class="sxs-lookup"><span data-stu-id="ea558-153">-Passthru</span></span>

<span data-ttu-id="ea558-154">Gibt an, dass dieses Cmdlet ein **historyinfo** -Objekt für jeden Verlaufs Eintrag zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="ea558-154">Indicates that this cmdlet returns a **HistoryInfo** object for each history entry.</span></span> <span data-ttu-id="ea558-155">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="ea558-155">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="ea558-156">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ea558-156">CommonParameters</span></span>

<span data-ttu-id="ea558-157">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ea558-157">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ea558-158">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ea558-158">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ea558-159">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="ea558-159">INPUTS</span></span>

### <span data-ttu-id="ea558-160">Microsoft. PowerShell. Commands. historyinfo</span><span class="sxs-lookup"><span data-stu-id="ea558-160">Microsoft.PowerShell.Commands.HistoryInfo</span></span>

<span data-ttu-id="ea558-161">Sie können ein **historyinfo** -Objekt über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="ea558-161">You can pipe a **HistoryInfo** object to this cmdlet.</span></span>

## <span data-ttu-id="ea558-162">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="ea558-162">OUTPUTS</span></span>

### <span data-ttu-id="ea558-163">None oder Microsoft. PowerShell. Commands. historyinfo</span><span class="sxs-lookup"><span data-stu-id="ea558-163">None or Microsoft.PowerShell.Commands.HistoryInfo</span></span>

<span data-ttu-id="ea558-164">Dieses Cmdlet gibt ein **historyinfo** -Objekt zurück, wenn Sie den **passthru** -Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="ea558-164">This cmdlet returns a **HistoryInfo** object if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="ea558-165">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="ea558-165">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="ea558-166">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="ea558-166">NOTES</span></span>

<span data-ttu-id="ea558-167">Der Sitzungsverlauf ist eine Liste der Befehle, die während der Sitzung eingegeben wurden, mit der ID.</span><span class="sxs-lookup"><span data-stu-id="ea558-167">The session history is a list of the commands entered during the session together with the ID.</span></span> <span data-ttu-id="ea558-168">Der Sitzungsverlauf stellt die Reihenfolge der Ausführung, den Status und die Start- und Endzeiten des Befehls dar.</span><span class="sxs-lookup"><span data-stu-id="ea558-168">The session history represents the order of execution, the status, and the start and end times of the command.</span></span> <span data-ttu-id="ea558-169">Wenn Sie jeden Befehl eingeben, wird er von PowerShell dem Verlauf hinzugefügt, damit Sie ihn wieder verwenden können.</span><span class="sxs-lookup"><span data-stu-id="ea558-169">As you enter each command, PowerShell adds it to the history so that you can reuse it.</span></span> <span data-ttu-id="ea558-170">Weitere Informationen zum Sitzungsverlauf finden Sie unter [about_History](About/about_History.md).</span><span class="sxs-lookup"><span data-stu-id="ea558-170">For more information about the session history, see [about_History](About/about_History.md).</span></span>

<span data-ttu-id="ea558-171">Verwenden Sie zum Angeben der Befehle, die dem Verlauf hinzugefügt werden sollen, den **InputObject** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="ea558-171">To specify the commands to add to the history, use the **InputObject** parameter.</span></span> <span data-ttu-id="ea558-172">Der `Add-History` Befehl akzeptiert nur **historyinfo** -Objekte, z. b. die, die für jeden Befehl vom `Get-History` Cmdlet zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ea558-172">The `Add-History` command accepts only **HistoryInfo** objects, such as those returned for each command by the `Get-History` cmdlet.</span></span> <span data-ttu-id="ea558-173">Sie können ihm keinen Pfad und Dateinamen bzw. eine Befehlsliste übergeben.</span><span class="sxs-lookup"><span data-stu-id="ea558-173">You cannot pass it a path and file name or a list of commands.</span></span>

<span data-ttu-id="ea558-174">Sie können den **Inputobject** -Parameter verwenden, um eine Datei mit **historyinfo** -Objekten an zu übergeben `Add-History` .</span><span class="sxs-lookup"><span data-stu-id="ea558-174">You can use the **InputObject** parameter to pass a file of **HistoryInfo** objects to `Add-History`.</span></span> <span data-ttu-id="ea558-175">Exportieren Sie dazu die Ergebnisse eines `Get-History` Befehls mithilfe des `Export-Csv` Cmdlets oder in eine Datei, `Export-Clixml` und importieren Sie die Datei dann mithilfe der `Import-Csv` `Import-Clixml` Cmdlets oder.</span><span class="sxs-lookup"><span data-stu-id="ea558-175">To do so, export the results of a `Get-History` command to a file by using the `Export-Csv` or `Export-Clixml` cmdlet and then import the file by using the `Import-Csv` or `Import-Clixml` cmdlets.</span></span> <span data-ttu-id="ea558-176">Anschließend können Sie die Datei importierter **historyinfo** -Objekte `Add-History` über eine Pipeline oder eine Variable an übergeben.</span><span class="sxs-lookup"><span data-stu-id="ea558-176">You can then pass the file of imported **HistoryInfo** objects to `Add-History` through a pipeline or in a variable.</span></span> <span data-ttu-id="ea558-177">Weitere Informationen finden Sie in den Beispielen.</span><span class="sxs-lookup"><span data-stu-id="ea558-177">For more information, see the examples.</span></span>

<span data-ttu-id="ea558-178">Die Datei der **historyinfo** -Objekte, die Sie an das `Add-History` Cmdlet übergeben, muss die Typinformationen, Spaltenüberschriften und alle Eigenschaften der **historyinfo** -Objekte enthalten.</span><span class="sxs-lookup"><span data-stu-id="ea558-178">The file of **HistoryInfo** objects that you pass to the `Add-History` cmdlet must include the type information, column headings, and all of the properties of the **HistoryInfo** objects.</span></span> <span data-ttu-id="ea558-179">Wenn Sie beabsichtigen, die Objekte zurück an zu übergeben `Add-History` , verwenden Sie nicht den **notypeinformation** -Parameter des `Export-Csv` Cmdlets, und löschen Sie nicht die Typinformationen, Spaltenüberschriften oder Felder in der Datei.</span><span class="sxs-lookup"><span data-stu-id="ea558-179">If you intend to pass the objects back to `Add-History`, do not use the **NoTypeInformation** parameter of the `Export-Csv` cmdlet and do not delete the type information, column headings, or any fields in the file.</span></span>

<span data-ttu-id="ea558-180">Um den Sitzungsverlauf zu ändern, exportieren Sie die Sitzung in eine CSV-oder XML-Datei, ändern Sie die Datei, importieren Sie die Datei, und verwenden `Add-History` Sie Sie, um Sie an den aktuellen Sitzungsverlauf anzufügen.</span><span class="sxs-lookup"><span data-stu-id="ea558-180">To modify the session history, export the session to a CSV or XML file, modify the file, import the file, and use `Add-History` to append it to the current session history.</span></span>

## <span data-ttu-id="ea558-181">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="ea558-181">RELATED LINKS</span></span>

[<span data-ttu-id="ea558-182">Clear-History</span><span class="sxs-lookup"><span data-stu-id="ea558-182">Clear-History</span></span>](Clear-History.md)

[<span data-ttu-id="ea558-183">Get-History</span><span class="sxs-lookup"><span data-stu-id="ea558-183">Get-History</span></span>](Get-History.md)

[<span data-ttu-id="ea558-184">Invoke-History</span><span class="sxs-lookup"><span data-stu-id="ea558-184">Invoke-History</span></span>](Invoke-History.md)

[<span data-ttu-id="ea558-185">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="ea558-185">about_PSReadLine</span></span>](../PSReadLine/About/about_PSReadLine.md)

[<span data-ttu-id="ea558-186">Get-psread lineoption</span><span class="sxs-lookup"><span data-stu-id="ea558-186">Get-PSReadLineOption</span></span>](/powershell/module/psreadline/get-psreadlineoption)

[<span data-ttu-id="ea558-187">Set-psread lineoption</span><span class="sxs-lookup"><span data-stu-id="ea558-187">Set-PSReadLineOption</span></span>](/powershell/module/psreadline/set-psreadlineoption)

