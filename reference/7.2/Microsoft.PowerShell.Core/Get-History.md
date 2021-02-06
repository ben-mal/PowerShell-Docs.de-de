---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 10/06/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-history?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-History
ms.openlocfilehash: be47925211c57760ddbd0bd4c8e985e161d24593
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602935"
---
# <span data-ttu-id="54052-102">Get-History</span><span class="sxs-lookup"><span data-stu-id="54052-102">Get-History</span></span>

## <span data-ttu-id="54052-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="54052-103">SYNOPSIS</span></span>
<span data-ttu-id="54052-104">Ruft eine Liste der Befehle ab, die während der aktuellen Sitzung eingegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="54052-104">Gets a list of the commands entered during the current session.</span></span>

## <span data-ttu-id="54052-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="54052-105">SYNTAX</span></span>

```
Get-History [[-Id] <Int64[]>] [[-Count] <Int32>] [<CommonParameters>]
```

## <span data-ttu-id="54052-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="54052-106">DESCRIPTION</span></span>

<span data-ttu-id="54052-107">Mit dem- `Get-History` Cmdlet wird der Sitzungsverlauf abgerufen, d. h. die Liste der Befehle, die während der aktuellen Sitzung eingegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="54052-107">The `Get-History` cmdlet gets the session history, that is, the list of commands entered during the current session.</span></span>

<span data-ttu-id="54052-108">PowerShell verwaltet automatisch einen Verlauf jeder Sitzung.</span><span class="sxs-lookup"><span data-stu-id="54052-108">PowerShell automatically maintains a history of each session.</span></span> <span data-ttu-id="54052-109">Die Anzahl von Einträgen im Sitzungsverlauf wird durch den Wert der `$MaximumHistoryCount` Preference-Variablen bestimmt.</span><span class="sxs-lookup"><span data-stu-id="54052-109">The number of entries in the session history is determined by the value of the `$MaximumHistoryCount` preference variable.</span></span> <span data-ttu-id="54052-110">Ab Windows PowerShell 3,0 lautet der Standardwert `4096` .</span><span class="sxs-lookup"><span data-stu-id="54052-110">Beginning in Windows PowerShell 3.0, the default value is `4096`.</span></span> <span data-ttu-id="54052-111">Standardmäßig werden Verlaufsdateien im Basisverzeichnis gespeichert, Sie können die Datei jedoch an einem beliebigen Speicherort speichern.</span><span class="sxs-lookup"><span data-stu-id="54052-111">By default, history files are saved in the home directory, but you can save the file in any location.</span></span> <span data-ttu-id="54052-112">Weitere Informationen zu den Verlaufs Funktionen in PowerShell finden Sie unter [about_History](About/about_History.md).</span><span class="sxs-lookup"><span data-stu-id="54052-112">For more information about the history features in PowerShell, see [about_History](About/about_History.md).</span></span>

<span data-ttu-id="54052-113">Der Sitzungsverlauf wird getrennt von dem vom **psread Line** -Modul verwalteten Verlauf verwaltet.</span><span class="sxs-lookup"><span data-stu-id="54052-113">The session history is managed separately from the history maintained by the **PSReadLine** module.</span></span>
<span data-ttu-id="54052-114">Beide Verläufe sind in Sitzungen verfügbar, in denen **psread Line** geladen wird.</span><span class="sxs-lookup"><span data-stu-id="54052-114">Both histories are available in sessions where **PSReadLine** is loaded.</span></span> <span data-ttu-id="54052-115">Dieses Cmdlet funktioniert nur mit dem Sitzungsverlauf.</span><span class="sxs-lookup"><span data-stu-id="54052-115">This cmdlet only works with the session history.</span></span> <span data-ttu-id="54052-116">Weitere Informationen finden Sie unter [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).</span><span class="sxs-lookup"><span data-stu-id="54052-116">For more information see, [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).</span></span>

## <span data-ttu-id="54052-117">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="54052-117">EXAMPLES</span></span>

### <span data-ttu-id="54052-118">Beispiel 1: Get the Session History</span><span class="sxs-lookup"><span data-stu-id="54052-118">Example 1: Get the session history</span></span>

<span data-ttu-id="54052-119">In diesem Beispiel werden die Einträge im Sitzungsverlauf abgerufen.</span><span class="sxs-lookup"><span data-stu-id="54052-119">This example gets the entries in the session history.</span></span> <span data-ttu-id="54052-120">Die Standard Anzeige zeigt jeden Befehl und seine ID an, der die Reihenfolge angibt, in der Sie ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="54052-120">The default display shows each command and its ID, which indicates the order in which they ran.</span></span>

```powershell
Get-History
```

### <span data-ttu-id="54052-121">Beispiel 2: Get-Einträge, die eine Zeichenfolge enthalten</span><span class="sxs-lookup"><span data-stu-id="54052-121">Example 2: Get entries that include a string</span></span>

<span data-ttu-id="54052-122">In diesem Beispiel werden Einträge im Befehlsverlauf abgerufen, die den Zeichen folgen Dienst einschließen.</span><span class="sxs-lookup"><span data-stu-id="54052-122">This example gets entries in the command history that include the string service.</span></span> <span data-ttu-id="54052-123">Der erste Befehl ruft alle Einträge im Sitzungsverlauf ab.</span><span class="sxs-lookup"><span data-stu-id="54052-123">The first command gets all entries in the session history.</span></span> <span data-ttu-id="54052-124">Der Pipeline Operator ( `|` ) übergibt die Ergebnisse an das `Where-Object` Cmdlet, das nur die Befehle auswählt, die den Dienst einschließen.</span><span class="sxs-lookup"><span data-stu-id="54052-124">The pipeline operator (`|`) passes the results to the `Where-Object` cmdlet, which selects only the commands that include service.</span></span>

```powershell
Get-History | Where-Object {$_.CommandLine -like "*Service*"}
```

### <span data-ttu-id="54052-125">Beispiel 3: Exportieren von Verlaufs Einträgen bis zu einer bestimmten ID</span><span class="sxs-lookup"><span data-stu-id="54052-125">Example 3: Export history entries up to a specific ID</span></span>

<span data-ttu-id="54052-126">In diesem Beispiel werden die fünf letzten Verlaufs Einträge abgerufen, die mit dem Eintrag 7 enden.</span><span class="sxs-lookup"><span data-stu-id="54052-126">This example gets the five most recent history entries ending with entry 7.</span></span> <span data-ttu-id="54052-127">Der Pipeline Operator übergibt das Ergebnis an das `Export-Csv` Cmdlet, das den Verlauf als durch Trennzeichen getrennten Text formatiert und in der History.csv-Datei speichert.</span><span class="sxs-lookup"><span data-stu-id="54052-127">The pipeline operator passes the result to the `Export-Csv` cmdlet, which formats the history as comma-separated text and saves it in the History.csv file.</span></span> <span data-ttu-id="54052-128">Die Datei enthält die Daten, die beim Formatieren des Verlaufs als Liste angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="54052-128">The file includes the data that is displayed when you format the history as a list.</span></span> <span data-ttu-id="54052-129">Dies schließt den Status und die Start-und Endzeit des Befehls ein.</span><span class="sxs-lookup"><span data-stu-id="54052-129">This includes the status and start and end times of the command.</span></span>

```powershell
Get-History -ID 7 -Count 5 | Export-Csv History.csv
```

### <span data-ttu-id="54052-130">Beispiel 4: Anzeigen des neuesten Befehls</span><span class="sxs-lookup"><span data-stu-id="54052-130">Example 4: Display the most recent command</span></span>

<span data-ttu-id="54052-131">In diesem Beispiel wird der letzte Befehl im Befehlsverlauf abgerufen.</span><span class="sxs-lookup"><span data-stu-id="54052-131">This example gets the last command in the command history.</span></span> <span data-ttu-id="54052-132">Der letzte Befehl ist der zuletzt eingegebene Befehl.</span><span class="sxs-lookup"><span data-stu-id="54052-132">The last command is the most recently entered command.</span></span> <span data-ttu-id="54052-133">Dieser Befehl verwendet den **count** -Parameter, um nur einen Befehl anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="54052-133">This command uses the **Count** parameter to display just one command.</span></span> <span data-ttu-id="54052-134">Standardmäßig ruft `Get-History` die neuesten Befehle ab.</span><span class="sxs-lookup"><span data-stu-id="54052-134">By default, `Get-History` gets the most recent commands.</span></span> <span data-ttu-id="54052-135">Dieser Befehl kann mit „h -c 1“ abgekürzt werden und entspricht dem Drücken der NACH-OBEN-TASTE.</span><span class="sxs-lookup"><span data-stu-id="54052-135">This command can be abbreviated to "h -c 1" and is equivalent to pressing the up-arrow key.</span></span>

```powershell
Get-History -Count 1
```

### <span data-ttu-id="54052-136">Beispiel 5: Anzeigen aller Eigenschaften der Einträge im Verlauf</span><span class="sxs-lookup"><span data-stu-id="54052-136">Example 5: Display all the properties of the entries in the history</span></span>

<span data-ttu-id="54052-137">In diesem Beispiel werden alle Eigenschaften von Einträgen im Sitzungsverlauf angezeigt.</span><span class="sxs-lookup"><span data-stu-id="54052-137">This example displays all of the properties of entries in the session history.</span></span> <span data-ttu-id="54052-138">Der Pipeline Operator übergibt die Ergebnisse eines `Get-History` Befehls an das `Format-List` Cmdlet, das alle Eigenschaften jedes Verlaufs Eintrags anzeigt.</span><span class="sxs-lookup"><span data-stu-id="54052-138">The pipeline operator passes the results of a `Get-History` command to the `Format-List` cmdlet, which displays all of the properties of each history entry.</span></span> <span data-ttu-id="54052-139">Dies schließt die ID, den Status und die Start-und Endzeiten des Befehls ein.</span><span class="sxs-lookup"><span data-stu-id="54052-139">This includes the ID, status, and start and end times of the command.</span></span>

```powershell
Get-History | Format-List -Property *
```

## <span data-ttu-id="54052-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="54052-140">PARAMETERS</span></span>

### <span data-ttu-id="54052-141">-Anzahl</span><span class="sxs-lookup"><span data-stu-id="54052-141">-Count</span></span>

<span data-ttu-id="54052-142">Gibt die Anzahl der letzten Verlaufs Einträge an, die von diesem Cmdlet abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="54052-142">Specifies the number of the most recent history entries that this cmdlet gets.</span></span> <span data-ttu-id="54052-143">Standardmäßig ruft `Get-History` alle Einträge im Sitzungsverlauf ab.</span><span class="sxs-lookup"><span data-stu-id="54052-143">By, default, `Get-History` gets all entries in the session history.</span></span> <span data-ttu-id="54052-144">Wenn Sie sowohl den **Count**- als auch den **Id**-Parameter in einem Befehl verwenden, endet die Anzeige mit dem Befehl, der vom **Id**-Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="54052-144">If you use both the **Count** and **Id** parameters in a command, the display ends with the command that is specified by the **Id** parameter.</span></span>

<span data-ttu-id="54052-145">In Windows PowerShell 2,0 werden standardmäßig `Get-History` die letzten 32 Einträge abgerufen.</span><span class="sxs-lookup"><span data-stu-id="54052-145">In Windows PowerShell 2.0, by default, `Get-History` gets the 32 most recent entries.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="54052-146">-Id</span><span class="sxs-lookup"><span data-stu-id="54052-146">-Id</span></span>

<span data-ttu-id="54052-147">Gibt ein Array der IDs von Einträgen im Sitzungsverlauf an.</span><span class="sxs-lookup"><span data-stu-id="54052-147">Specifies an array of the IDs of entries in the session history.</span></span> <span data-ttu-id="54052-148">`Get-History` Ruft nur angegebene Einträge ab.</span><span class="sxs-lookup"><span data-stu-id="54052-148">`Get-History` gets only specified entries.</span></span> <span data-ttu-id="54052-149">Wenn Sie in einem Befehl sowohl den **ID** -als auch den **count** -Parameter verwenden, ruft `Get-History` die letzten Einträge ab, die mit dem durch den **ID** -Parameter angegebenen Eintrag enden.</span><span class="sxs-lookup"><span data-stu-id="54052-149">If you use both the **Id** and **Count** parameters in a command, `Get-History` gets the most recent entries ending with the entry specified by the **Id** parameter.</span></span>

```yaml
Type: System.Int64[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="54052-150">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="54052-150">CommonParameters</span></span>

<span data-ttu-id="54052-151">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="54052-151">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="54052-152">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="54052-152">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="54052-153">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="54052-153">INPUTS</span></span>

### <span data-ttu-id="54052-154">System.Int64</span><span class="sxs-lookup"><span data-stu-id="54052-154">System.Int64</span></span>

<span data-ttu-id="54052-155">Sie können eine Verlaufs-ID an dieses Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="54052-155">You can pipe a history ID to this cmdlet.</span></span>

## <span data-ttu-id="54052-156">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="54052-156">OUTPUTS</span></span>

### <span data-ttu-id="54052-157">Microsoft. PowerShell. Commands. historyinfo</span><span class="sxs-lookup"><span data-stu-id="54052-157">Microsoft.PowerShell.Commands.HistoryInfo</span></span>

<span data-ttu-id="54052-158">Dieses Cmdlet gibt ein Verlaufs Objekt für jedes Verlaufs Element zurück, das es abruft.</span><span class="sxs-lookup"><span data-stu-id="54052-158">This cmdlet returns a history object for each history item that it gets.</span></span>

## <span data-ttu-id="54052-159">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="54052-159">NOTES</span></span>

<span data-ttu-id="54052-160">Der Sitzungsverlauf ist eine Liste der Befehle, die während der Sitzung eingegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="54052-160">The session history is a list of the commands entered during the session.</span></span> <span data-ttu-id="54052-161">Der Sitzungsverlauf stellt die Reihenfolge, den Status und die Start-und Endzeiten des Befehls dar.</span><span class="sxs-lookup"><span data-stu-id="54052-161">The session history represents the run order, the status, and the start and end times of the command.</span></span> <span data-ttu-id="54052-162">Wenn Sie jeden Befehl eingeben, wird er von PowerShell dem Verlauf hinzugefügt, damit Sie ihn wieder verwenden können.</span><span class="sxs-lookup"><span data-stu-id="54052-162">As you enter each command, PowerShell adds it to the history so that you can reuse it.</span></span> <span data-ttu-id="54052-163">Weitere Informationen zum Befehlsverlauf finden Sie unter [about_History](About/about_History.md).</span><span class="sxs-lookup"><span data-stu-id="54052-163">For more information about the command history, see [about_History](About/about_History.md).</span></span>

<span data-ttu-id="54052-164">Ab Windows PowerShell 3,0 lautet der Standardwert der Einstellungs `$MaximumHistoryCount` Variablen `4096` .</span><span class="sxs-lookup"><span data-stu-id="54052-164">Starting in Windows PowerShell 3.0, the default value of the `$MaximumHistoryCount` preference variable is `4096`.</span></span> <span data-ttu-id="54052-165">In Windows PowerShell 2,0 ist der Standardwert `64` .</span><span class="sxs-lookup"><span data-stu-id="54052-165">In Windows PowerShell 2.0, the default value is `64`.</span></span> <span data-ttu-id="54052-166">Weitere Informationen zur- `$MaximumHistoryCount` Variablen finden Sie unter [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="54052-166">For more information about the `$MaximumHistoryCount` variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

## <span data-ttu-id="54052-167">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="54052-167">RELATED LINKS</span></span>

[<span data-ttu-id="54052-168">Add-History</span><span class="sxs-lookup"><span data-stu-id="54052-168">Add-History</span></span>](Add-History.md)

[<span data-ttu-id="54052-169">Clear-History</span><span class="sxs-lookup"><span data-stu-id="54052-169">Clear-History</span></span>](Clear-History.md)

[<span data-ttu-id="54052-170">Invoke-History</span><span class="sxs-lookup"><span data-stu-id="54052-170">Invoke-History</span></span>](Invoke-History.md)

[<span data-ttu-id="54052-171">about_History</span><span class="sxs-lookup"><span data-stu-id="54052-171">about_History</span></span>](About/about_History.md)
