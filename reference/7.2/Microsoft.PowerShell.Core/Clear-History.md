---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 05/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/clear-history?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-History
ms.openlocfilehash: 1b465779f56c6bd71d7adfa7ffb5b391f5402656
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600910"
---
# <span data-ttu-id="9a204-102">Clear-History</span><span class="sxs-lookup"><span data-stu-id="9a204-102">Clear-History</span></span>

## <span data-ttu-id="9a204-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="9a204-103">SYNOPSIS</span></span>
<span data-ttu-id="9a204-104">Löscht Einträge aus dem PowerShell-Sitzungs Befehlsverlauf.</span><span class="sxs-lookup"><span data-stu-id="9a204-104">Deletes entries from the PowerShell session command history.</span></span>

## <span data-ttu-id="9a204-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9a204-105">SYNTAX</span></span>

### <span data-ttu-id="9a204-106">IDParameter (Standard)</span><span class="sxs-lookup"><span data-stu-id="9a204-106">IDParameter (Default)</span></span>

```
Clear-History [[-Id] <int[]>] [[-Count] <int>] [-Newest] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="9a204-107">Commandlineparameter</span><span class="sxs-lookup"><span data-stu-id="9a204-107">CommandLineParameter</span></span>

```
Clear-History [[-Count] <int>] [-CommandLine <string[]>] [-Newest] [-WhatIf] [-Confirm]
[<CommonParameters>]
```

## <span data-ttu-id="9a204-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9a204-108">DESCRIPTION</span></span>

<span data-ttu-id="9a204-109">`Clear-History` Löscht den Befehlsverlauf aus einer PowerShell-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="9a204-109">`Clear-History` deletes the command history from a PowerShell session.</span></span> <span data-ttu-id="9a204-110">Jede PowerShell-Sitzung verfügt über einen eigenen Befehlsverlauf.</span><span class="sxs-lookup"><span data-stu-id="9a204-110">Each PowerShell session has its own command history.</span></span> <span data-ttu-id="9a204-111">Verwenden Sie das-Cmdlet, um den Befehlsverlauf anzuzeigen `Get-History` .</span><span class="sxs-lookup"><span data-stu-id="9a204-111">To display the command history, use the `Get-History` cmdlet.</span></span>

<span data-ttu-id="9a204-112">Standardmäßig wird `Clear-History` der gesamte Befehlsverlauf aus einer PowerShell-Sitzung gelöscht.</span><span class="sxs-lookup"><span data-stu-id="9a204-112">By default, `Clear-History` deletes the entire command history from a PowerShell session.</span></span> <span data-ttu-id="9a204-113">Sie können Parameter mit verwenden `Clear-History` , um ausgewählte Befehle zu löschen.</span><span class="sxs-lookup"><span data-stu-id="9a204-113">You can use parameters with `Clear-History` to delete selected commands.</span></span>

<span data-ttu-id="9a204-114">`Clear-History` Löscht die Befehls Verlaufs `PSReadLine` Datei nicht.</span><span class="sxs-lookup"><span data-stu-id="9a204-114">`Clear-History` does not clear the `PSReadLine` command history file.</span></span> <span data-ttu-id="9a204-115">Das `PSReadLine` Modul speichert eine Verlaufs Datei, die jeden PowerShell-Befehl in jeder PowerShell-Sitzung enthält.</span><span class="sxs-lookup"><span data-stu-id="9a204-115">The `PSReadLine` module stores a history file that contains every PowerShell command from every PowerShell session.</span></span> <span data-ttu-id="9a204-116">Verwenden Sie an einer PowerShell-Eingabeaufforderung die Pfeile nach oben und nach unten auf der Tastatur, um durch den Befehlsverlauf zu scrollen.</span><span class="sxs-lookup"><span data-stu-id="9a204-116">From a PowerShell prompt, use the up and down arrows on your keyboard to scroll through the command history.</span></span> <span data-ttu-id="9a204-117">Verwenden Sie, um die `PSReadLine` Konfiguration für den Befehlsverlauf anzuzeigen `Get-PSReadLineOption` .</span><span class="sxs-lookup"><span data-stu-id="9a204-117">To display the `PSReadLine` configuration for command history, use `Get-PSReadLineOption`.</span></span>
<span data-ttu-id="9a204-118">`PSReadLine` ausgeliefert mit PowerShell 5,0 und höher.</span><span class="sxs-lookup"><span data-stu-id="9a204-118">`PSReadLine` shipped with PowerShell 5.0 and above.</span></span> <span data-ttu-id="9a204-119">Weitere Informationen finden Sie unter [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).</span><span class="sxs-lookup"><span data-stu-id="9a204-119">For more information, see [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).</span></span>

## <span data-ttu-id="9a204-120">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="9a204-120">EXAMPLES</span></span>

### <span data-ttu-id="9a204-121">Beispiel 1: Löschen des Befehls Verlaufs aus einer PowerShell-Sitzung</span><span class="sxs-lookup"><span data-stu-id="9a204-121">Example 1: Delete the command history from a PowerShell session</span></span>

<span data-ttu-id="9a204-122">Dieser Befehl löscht alle Befehle aus dem Verlauf einer PowerShell-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="9a204-122">This command deletes all of the commands from a PowerShell session's history.</span></span>

```powershell
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location .\Test
   2 Update-Help
   3 Set-Location C:\Test\Logs
   4 Get-Location
```

```powershell
Clear-History
Get-History
```

```Output
  Id CommandLine
  -- -----------
   5 Clear-History
```

<span data-ttu-id="9a204-123">Das `Get-History` -Cmdlet zeigt den Verlauf der PowerShell-Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="9a204-123">The `Get-History` cmdlet displays the PowerShell session's history.</span></span> <span data-ttu-id="9a204-124">`Clear-History` Löscht den gesamten Befehlsverlauf.</span><span class="sxs-lookup"><span data-stu-id="9a204-124">`Clear-History` deletes the entire command history.</span></span> <span data-ttu-id="9a204-125">`Get-History` zeigt den aktualisierten Befehlsverlauf an und bestätigt, dass der vorherige Verlauf gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="9a204-125">`Get-History` displays the updated command history and confirms the prior history was deleted.</span></span>

### <span data-ttu-id="9a204-126">Beispiel 2: Löschen der neuesten Befehle</span><span class="sxs-lookup"><span data-stu-id="9a204-126">Example 2: Delete the newest commands</span></span>

<span data-ttu-id="9a204-127">Dieser Befehl verwendet die Parameter **count** und **Latest** , um die neuesten Befehle aus dem Verlauf einer PowerShell-Sitzung zu löschen.</span><span class="sxs-lookup"><span data-stu-id="9a204-127">This command uses the **Count** and **Newest** parameters to delete the newest commands from a PowerShell session's history.</span></span>

```powershell
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location C:\Test\
   2 Get-Command Clear-History
   3 Get-Command Clear-History -Syntax
   4 Get-Command Clear-History -ShowCommandInfo
   5 Get-Help Get-Alias
   6 Get-Command Get-ChildItem -Syntax
   7 Get-Help Clear-History
   8 Set-Location C:\Test\Logs
   9 Get-Help Get-Variable
  10 Get-Help Get-ChildItem
```

```powershell
Clear-History -Count 5 -Newest
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location C:\Test\
   2 Get-Command Clear-History
   3 Get-Command Clear-History -Syntax
   4 Get-Command Clear-History -ShowCommandInfo
   5 Get-Help Get-Alias
  11 Clear-History -Count 5 -Newest
```

<span data-ttu-id="9a204-128">Das `Get-History` -Cmdlet zeigt den Verlauf der PowerShell-Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="9a204-128">The `Get-History` cmdlet displays the PowerShell session's history.</span></span> <span data-ttu-id="9a204-129">`Clear-History` wird verwendet, um den Befehlsverlauf zu löschen.</span><span class="sxs-lookup"><span data-stu-id="9a204-129">`Clear-History` is used to delete the command history.</span></span> <span data-ttu-id="9a204-130">Der **count** -Parameter gibt die Anzahl der zu löschenden Befehle an, einschließlich der angegebenen **ID**. Der **Latest** -Parameter gibt an, dass die neuesten Befehle aus dem Verlauf gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="9a204-130">The **Count** parameter specifies the number of commands to delete, inclusive of the specified **Id**. The **Newest** parameter specifies that the newest commands are cleared from the history.</span></span> <span data-ttu-id="9a204-131">`Get-History`zeigt den aktualisierten Befehlsverlauf an und bestätigt, dass die fünf neuesten Befehle gelöscht wurden, **ID 6**  -  **ID 10**.</span><span class="sxs-lookup"><span data-stu-id="9a204-131">`Get-History` displays the updated command history and confirms that the five newest commands were deleted, **Id 6** - **Id 10**.</span></span>

### <span data-ttu-id="9a204-132">Beispiel 3: Löschen von Befehlen, die bestimmten Kriterien entsprechen</span><span class="sxs-lookup"><span data-stu-id="9a204-132">Example 3: Delete commands that match specific criteria</span></span>

<span data-ttu-id="9a204-133">Dieser Befehl löscht Befehle, die bestimmten Kriterien entsprechen, die vom **CommandLine** -Parameter definiert werden.</span><span class="sxs-lookup"><span data-stu-id="9a204-133">This command deletes commands that match specific criteria defined by the **CommandLine** parameter.</span></span>

```powershell
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location C:\Test\
   2 Get-Command Clear-History
   3 Get-Command Clear-History -Syntax
   4 Get-Command Clear-History -ShowCommandInfo
   5 Get-Help Get-Alias
   6 Get-Command Get-ChildItem -Syntax
   7 Get-Help Clear-History
```

```powershell
Clear-History -CommandLine *Help*, *Syntax
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location C:\Test\
   2 Get-Command Clear-History
   4 Get-Command Clear-History -ShowCommandInfo
   8 Clear-History -CommandLine *Help*, *Syntax
```

<span data-ttu-id="9a204-134">Das `Get-History` -Cmdlet zeigt den Verlauf der PowerShell-Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="9a204-134">The `Get-History` cmdlet displays the PowerShell session's history.</span></span> <span data-ttu-id="9a204-135">`Clear-History` Löscht den Befehlsverlauf.</span><span class="sxs-lookup"><span data-stu-id="9a204-135">`Clear-History` deletes the command history.</span></span> <span data-ttu-id="9a204-136">Der **CommandLine** -Parameter gibt Befehle an, die **Hilfe** oder Ende mit **Syntax** enthalten.</span><span class="sxs-lookup"><span data-stu-id="9a204-136">The **CommandLine** parameter specifies commands that contain **Help** or end with **Syntax**.</span></span> <span data-ttu-id="9a204-137">`Get-History` zeigt den aktualisierten Befehlsverlauf an und bestätigt, dass die Befehle **ID 3**, **ID 5**, **ID 6** und **ID 7** gelöscht wurden.</span><span class="sxs-lookup"><span data-stu-id="9a204-137">`Get-History` displays the updated command history and confirms that commands **Id 3**, **Id 5**, **Id 6**, and **Id 7** were deleted.</span></span>

### <span data-ttu-id="9a204-138">Beispiel 4: Löschen von Befehlen nach ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="9a204-138">Example 4: Delete commands by Id number</span></span>

<span data-ttu-id="9a204-139">Mit diesem Befehl werden bestimmte Verlaufs Elemente mithilfe der **ID** gelöscht. Zum Löschen mehrerer Befehle übermitteln Sie eine durch Trennzeichen getrennte Liste mit **ID** -Nummern.</span><span class="sxs-lookup"><span data-stu-id="9a204-139">This command deletes specific history items using the **Id**. To delete multiple commands, submit a comma-separated list of **Id** numbers.</span></span>

```powershell
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location C:\Test\
   2 Get-History
   3 Get-Help Get-Alias
   4 Get-Command Clear-History
   5 Get-Command Clear-History -Syntax
   6 Get-Command Clear-History -ShowCommandInfo
```

```powershell
Clear-History -Id 3, 5
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location C:\Test\
   2 Get-History
   4 Get-Command Clear-History
   6 Get-Command Clear-History -ShowCommandInfo
   7 Get-History
   8 Clear-History -Id 3, 5
```

<span data-ttu-id="9a204-140">Das `Get-History` -Cmdlet zeigt den Verlauf der PowerShell-Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="9a204-140">The `Get-History` cmdlet displays the PowerShell session's history.</span></span> <span data-ttu-id="9a204-141">`Clear-History` Löscht den Befehlsverlauf.</span><span class="sxs-lookup"><span data-stu-id="9a204-141">`Clear-History` deletes the command history.</span></span> <span data-ttu-id="9a204-142">Der **ID** -Parameter gibt an, welche Befehle gelöscht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9a204-142">The **Id** parameter specifies which commands to delete.</span></span> <span data-ttu-id="9a204-143">`Get-History` zeigt den aktualisierten Befehlsverlauf an und bestätigt, dass **ID 3** und **ID 5** gelöscht wurden.</span><span class="sxs-lookup"><span data-stu-id="9a204-143">`Get-History` displays the updated command history and confirms that **Id 3** and **Id 5** were deleted.</span></span>

### <span data-ttu-id="9a204-144">Beispiel 5: Löschen von Befehlen nach ID-Nummer und-Anzahl</span><span class="sxs-lookup"><span data-stu-id="9a204-144">Example 5: Delete commands by Id number and count</span></span>

<span data-ttu-id="9a204-145">Dieser Befehl verwendet die **ID** -und **count** -Parameter, um den Befehlsverlauf zu löschen.</span><span class="sxs-lookup"><span data-stu-id="9a204-145">This command uses the **Id** and **Count** parameters to delete command history.</span></span> <span data-ttu-id="9a204-146">Die Befehle werden aus der angegebenen **ID** in umgekehrter Reihenfolge gelöscht, von der neuesten zum ältesten.</span><span class="sxs-lookup"><span data-stu-id="9a204-146">Commands are deleted from the specified **Id** in reverse order, newest to oldest.</span></span>

```powershell
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location C:\Test\
   2 Get-Command Clear-History
   3 Get-Command Clear-History -Syntax
   4 Get-Command Clear-History -ShowCommandInfo
   5 Get-Help Get-Alias
   6 Get-Command Get-ChildItem -Syntax
   7 Get-Help Clear-History
   8 Set-Location C:\Test\Logs
   9 Get-Help Get-Variable
  10 Get-Help Get-ChildItem
```

```powershell
Clear-History -Id 7 -Count 5
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location C:\Test\
   2 Get-Command Clear-History
   8 Set-Location C:\Test\Logs
   9 Get-Help Get-Variable
  10 Get-Help Get-ChildItem
  11 Clear-History -Id 7 -Count 5
```

<span data-ttu-id="9a204-147">Das `Get-History` -Cmdlet zeigt den Verlauf der PowerShell-Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="9a204-147">The `Get-History` cmdlet displays the PowerShell session's history.</span></span> <span data-ttu-id="9a204-148">`Clear-History` Löscht den Befehlsverlauf.</span><span class="sxs-lookup"><span data-stu-id="9a204-148">`Clear-History` deletes the command history.</span></span> <span data-ttu-id="9a204-149">Der **ID** -Parameter gibt an, dass mit **ID 7** begonnen werden soll.</span><span class="sxs-lookup"><span data-stu-id="9a204-149">The **Id** parameter specifies to begin with **Id 7**.</span></span> <span data-ttu-id="9a204-150">Der **count** -Parameter gibt an, dass fünf Befehle einschließlich der angegebenen **ID** gelöscht werden sollen. `Get-History`zeigt den aktualisierten Befehlsverlauf an und bestätigt, dass fünf Befehle gelöscht wurden, **ID 3**  -  **ID 7**.</span><span class="sxs-lookup"><span data-stu-id="9a204-150">The **Count** parameter specifies to delete five commands, inclusive of the specified **Id**. `Get-History` displays the updated command history and confirms that five commands were deleted, **Id 3** - **Id 7**.</span></span>

## <span data-ttu-id="9a204-151">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9a204-151">PARAMETERS</span></span>

### <span data-ttu-id="9a204-152">-CommandLine</span><span class="sxs-lookup"><span data-stu-id="9a204-152">-CommandLine</span></span>

<span data-ttu-id="9a204-153">Löscht den Befehlsverlauf aus einer PowerShell-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="9a204-153">Deletes command history from a PowerShell session.</span></span> <span data-ttu-id="9a204-154">Die Zeichenfolge muss eine exakte Entsprechung sein oder Platzhalter verwenden, um Befehle in dem von angezeigten PowerShell-Sitzungsverlauf abzugleichen `Get-History` .</span><span class="sxs-lookup"><span data-stu-id="9a204-154">The string must be an exact match or use wildcards to match commands in the PowerShell session history displayed by `Get-History`.</span></span> <span data-ttu-id="9a204-155">Wenn Sie mehr als eine Zeichenfolge eingeben, `Clear-History` Löscht die Befehle, die mit einer der Zeichen folgen zu vergleichen sind.</span><span class="sxs-lookup"><span data-stu-id="9a204-155">If you enter more than one string, `Clear-History` deletes commands that match any of the strings.</span></span> <span data-ttu-id="9a204-156">Der **CommandLine** -Parameter kann mit **count** verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9a204-156">The **CommandLine** parameter can be used with **Count**.</span></span>

<span data-ttu-id="9a204-157">Verwenden Sie für Zeichen folgen mit einem Leerzeichen einfache Anführungszeichen.</span><span class="sxs-lookup"><span data-stu-id="9a204-157">For strings with a space, use single quotations.</span></span> <span data-ttu-id="9a204-158">Weitere Informationen finden Sie unter [about_Quoting_Rules](About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="9a204-158">For more information, see [about_Quoting_Rules](About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: CommandLineParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="9a204-159">-Anzahl</span><span class="sxs-lookup"><span data-stu-id="9a204-159">-Count</span></span>

<span data-ttu-id="9a204-160">Gibt die Anzahl von Verlaufs Einträgen an, die von `Clear-History` gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="9a204-160">Specifies the number of history entries that `Clear-History` deletes.</span></span> <span data-ttu-id="9a204-161">Befehle werden in der Reihenfolge gelöscht, beginnend mit dem ältesten Eintrag im Verlauf.</span><span class="sxs-lookup"><span data-stu-id="9a204-161">Commands are deleted in order, beginning with the oldest entry in the history.</span></span>

<span data-ttu-id="9a204-162">Die Parameter **count** und **ID** können gleichzeitig verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9a204-162">The **Count** and **Id** parameters can be used together.</span></span> <span data-ttu-id="9a204-163">Der **count** -Parameter gibt die Anzahl der zu löschenden Befehle an, einschließlich der angegebenen **ID**. Beginnend bei der angegebenen **ID** werden die Befehle in umgekehrter sequenzieller Reihenfolge gelöscht.</span><span class="sxs-lookup"><span data-stu-id="9a204-163">The **Count** parameter specifies the number of commands to delete, inclusive of the specified **Id**. Beginning at the specified **Id**, commands are deleted in reverse sequential order.</span></span> <span data-ttu-id="9a204-164">Wenn die **ID** z. b. 30 und die **Anzahl** 10 beträgt, `Clear-History` Löscht die Elemente 21 bis 30.</span><span class="sxs-lookup"><span data-stu-id="9a204-164">For example, if the **Id** is 30 and the **Count** is 10, `Clear-History` deletes items 21 through 30.</span></span>

<span data-ttu-id="9a204-165">Die Parameter **count** und **CommandLine** können gleichzeitig verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9a204-165">The **Count** and **CommandLine** parameters can be used together.</span></span> <span data-ttu-id="9a204-166">**Count** gibt die Anzahl der zu löschenden Befehle an, die dem **CommandLine** -Parameterwert entsprechen.</span><span class="sxs-lookup"><span data-stu-id="9a204-166">**Count** specifies the number of commands to delete that match **CommandLine** parameter value.</span></span> <span data-ttu-id="9a204-167">Die Befehle werden in sequenzieller Reihenfolge gelöscht.</span><span class="sxs-lookup"><span data-stu-id="9a204-167">The commands are deleted in sequential order.</span></span>

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

### <span data-ttu-id="9a204-168">-Id</span><span class="sxs-lookup"><span data-stu-id="9a204-168">-Id</span></span>

<span data-ttu-id="9a204-169">Gibt die Befehlsverlauf- **ID** an, die von `Clear-History` gelöscht wird</span><span class="sxs-lookup"><span data-stu-id="9a204-169">Specifies the command history **Id** that `Clear-History` deletes.</span></span> <span data-ttu-id="9a204-170">Verwenden Sie das-Cmdlet, um die **ID** -Nummern anzuzeigen `Get-History` .</span><span class="sxs-lookup"><span data-stu-id="9a204-170">To display **Id** numbers, use the `Get-History` cmdlet.</span></span> <span data-ttu-id="9a204-171">Die **ID** -Nummern sind sequenziell, und die Befehle behalten ihre **ID** -Nummer in einer PowerShell-Sitzung bei.</span><span class="sxs-lookup"><span data-stu-id="9a204-171">The **Id** numbers are sequential and commands keep their **Id** number throughout a PowerShell session.</span></span> <span data-ttu-id="9a204-172">Der **ID** -Parameter kann mit **count** und **Latest** verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9a204-172">The **Id** parameter can be used with **Count** and **Newest**.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: IDParameter
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9a204-173">-Latest</span><span class="sxs-lookup"><span data-stu-id="9a204-173">-Newest</span></span>

<span data-ttu-id="9a204-174">Wenn der **neueste** Parameter verwendet wird, `Clear-History` Löscht die neuesten Einträge im Verlauf.</span><span class="sxs-lookup"><span data-stu-id="9a204-174">When the **Newest** parameter is used, `Clear-History` deletes the newest entries in the history.</span></span> <span data-ttu-id="9a204-175">Standardmäßig `Clear-History` Löscht die ältesten Einträge im Verlauf.</span><span class="sxs-lookup"><span data-stu-id="9a204-175">By default, `Clear-History` deletes the oldest entries in the history.</span></span>

<span data-ttu-id="9a204-176">Der **neueste** Parameter kann mit der **ID** und der **Anzahl** verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9a204-176">The **Newest** parameter can be used with **Id** and **Count**.</span></span> <span data-ttu-id="9a204-177">Der **count** -Parameter gibt die Anzahl der zu löschenden Befehle an, einschließlich der angegebenen **ID**. Beginnend bei der angegebenen **ID** werden die Befehle in sequenzieller Reihenfolge gelöscht.</span><span class="sxs-lookup"><span data-stu-id="9a204-177">The **Count** parameter specifies the number of commands to delete, inclusive of the specified **Id**. Beginning at the specified **Id**, commands are deleted in sequential order.</span></span> <span data-ttu-id="9a204-178">Wenn die **ID** z. b. 30 und die **Anzahl** 10 beträgt, `Clear-History` Löscht die Elemente 30 bis 39.</span><span class="sxs-lookup"><span data-stu-id="9a204-178">For example, if the **Id** is 30 and the **Count** is 10, `Clear-History` deletes items 30 through 39.</span></span>

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

### <span data-ttu-id="9a204-179">-Confirm</span><span class="sxs-lookup"><span data-stu-id="9a204-179">-Confirm</span></span>

<span data-ttu-id="9a204-180">Sie werden zur Bestätigung aufgefordert, bevor Sie das `Clear-History` Cmdlet ausführen.</span><span class="sxs-lookup"><span data-stu-id="9a204-180">Prompts you for confirmation before running the `Clear-History` cmdlet.</span></span>

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

### <span data-ttu-id="9a204-181">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="9a204-181">-WhatIf</span></span>

<span data-ttu-id="9a204-182">Zeigt, was geschieht, wenn das `Clear-History` Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9a204-182">Shows what would happen if the `Clear-History` cmdlet runs.</span></span> <span data-ttu-id="9a204-183">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="9a204-183">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="9a204-184">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="9a204-184">CommonParameters</span></span>

<span data-ttu-id="9a204-185">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9a204-185">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9a204-186">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="9a204-186">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="9a204-187">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="9a204-187">INPUTS</span></span>

### <span data-ttu-id="9a204-188">Keine</span><span class="sxs-lookup"><span data-stu-id="9a204-188">None</span></span>

<span data-ttu-id="9a204-189">Objekte können nicht an übergeben werden `Clear-History` .</span><span class="sxs-lookup"><span data-stu-id="9a204-189">You cannot pipe objects to `Clear-History`.</span></span>

## <span data-ttu-id="9a204-190">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="9a204-190">OUTPUTS</span></span>

### <span data-ttu-id="9a204-191">Keine</span><span class="sxs-lookup"><span data-stu-id="9a204-191">None</span></span>

<span data-ttu-id="9a204-192">`Clear-History` generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="9a204-192">`Clear-History` does not generate any output.</span></span>

## <span data-ttu-id="9a204-193">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="9a204-193">NOTES</span></span>

<span data-ttu-id="9a204-194">Der PowerShell-Sitzungsverlauf ist eine Liste der Befehle, die während einer PowerShell-Sitzung eingegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="9a204-194">The PowerShell session history is a list of the commands entered during a PowerShell session.</span></span> <span data-ttu-id="9a204-195">Sie können den Verlauf anzeigen, Befehle hinzufügen und löschen und Befehle aus dem Verlauf ausführen.</span><span class="sxs-lookup"><span data-stu-id="9a204-195">You can view the history, add and delete commands, and run commands from the history.</span></span> <span data-ttu-id="9a204-196">Weitere Informationen finden Sie unter [about_History](About/about_History.md).</span><span class="sxs-lookup"><span data-stu-id="9a204-196">For more information, see [about_History](About/about_History.md).</span></span>

<span data-ttu-id="9a204-197">Der Sitzungsverlauf wird getrennt von dem vom **psread Line** -Modul verwalteten Verlauf verwaltet.</span><span class="sxs-lookup"><span data-stu-id="9a204-197">The session history is managed separately from the history maintained by the **PSReadLine** module.</span></span>
<span data-ttu-id="9a204-198">Beide Verläufe sind in Sitzungen verfügbar, in denen **psread Line** geladen wird.</span><span class="sxs-lookup"><span data-stu-id="9a204-198">Both histories are available in sessions where **PSReadLine** is loaded.</span></span> <span data-ttu-id="9a204-199">Dieses Cmdlet funktioniert nur mit dem Sitzungsverlauf.</span><span class="sxs-lookup"><span data-stu-id="9a204-199">This cmdlet only works with the session history.</span></span> <span data-ttu-id="9a204-200">Weitere Informationen finden Sie unter [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).</span><span class="sxs-lookup"><span data-stu-id="9a204-200">For more information see, [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).</span></span>

## <span data-ttu-id="9a204-201">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="9a204-201">RELATED LINKS</span></span>

[<span data-ttu-id="9a204-202">about_History</span><span class="sxs-lookup"><span data-stu-id="9a204-202">about_History</span></span>](About/about_History.md)

[<span data-ttu-id="9a204-203">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="9a204-203">about_PSReadLine</span></span>](../PSReadLine/About/about_PSReadLine.md)

[<span data-ttu-id="9a204-204">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="9a204-204">about_Quoting_Rules</span></span>](About/about_Quoting_Rules.md)

[<span data-ttu-id="9a204-205">Add-History</span><span class="sxs-lookup"><span data-stu-id="9a204-205">Add-History</span></span>](Add-History.md)

[<span data-ttu-id="9a204-206">Get-History</span><span class="sxs-lookup"><span data-stu-id="9a204-206">Get-History</span></span>](Get-History.md)

[<span data-ttu-id="9a204-207">Invoke-History</span><span class="sxs-lookup"><span data-stu-id="9a204-207">Invoke-History</span></span>](Invoke-History.md)

[<span data-ttu-id="9a204-208">Get-psread lineoption</span><span class="sxs-lookup"><span data-stu-id="9a204-208">Get-PSReadLineOption</span></span>](/powershell/module/psreadline/get-psreadlineoption)

[<span data-ttu-id="9a204-209">Set-psread lineoption</span><span class="sxs-lookup"><span data-stu-id="9a204-209">Set-PSReadLineOption</span></span>](/powershell/module/psreadline/set-psreadlineoption)

