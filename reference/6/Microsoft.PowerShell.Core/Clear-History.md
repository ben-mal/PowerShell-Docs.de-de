---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 05/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/clear-history?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-History
ms.openlocfilehash: 859738998de9d2a61a5fb7d9f39ff6ef8b74ad4d
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215111"
---
# <span data-ttu-id="b276d-103">Clear-History</span><span class="sxs-lookup"><span data-stu-id="b276d-103">Clear-History</span></span>

## <span data-ttu-id="b276d-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="b276d-104">SYNOPSIS</span></span>
<span data-ttu-id="b276d-105">Löscht Einträge aus dem PowerShell-Sitzungs Befehlsverlauf.</span><span class="sxs-lookup"><span data-stu-id="b276d-105">Deletes entries from the PowerShell session command history.</span></span>

## <span data-ttu-id="b276d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b276d-106">SYNTAX</span></span>

### <span data-ttu-id="b276d-107">IDParameter (Standard)</span><span class="sxs-lookup"><span data-stu-id="b276d-107">IDParameter (Default)</span></span>

```
Clear-History [[-Id] <int[]>] [[-Count] <int>] [-Newest] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="b276d-108">Commandlineparameter</span><span class="sxs-lookup"><span data-stu-id="b276d-108">CommandLineParameter</span></span>

```
Clear-History [[-Count] <int>] [-CommandLine <string[]>] [-Newest] [-WhatIf] [-Confirm]
[<CommonParameters>]
```

## <span data-ttu-id="b276d-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b276d-109">DESCRIPTION</span></span>

<span data-ttu-id="b276d-110">`Clear-History` Löscht den Befehlsverlauf aus einer PowerShell-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="b276d-110">`Clear-History` deletes the command history from a PowerShell session.</span></span> <span data-ttu-id="b276d-111">Jede PowerShell-Sitzung verfügt über einen eigenen Befehlsverlauf.</span><span class="sxs-lookup"><span data-stu-id="b276d-111">Each PowerShell session has its own command history.</span></span> <span data-ttu-id="b276d-112">Verwenden Sie das-Cmdlet, um den Befehlsverlauf anzuzeigen `Get-History` .</span><span class="sxs-lookup"><span data-stu-id="b276d-112">To display the command history, use the `Get-History` cmdlet.</span></span>

<span data-ttu-id="b276d-113">Standardmäßig wird `Clear-History` der gesamte Befehlsverlauf aus einer PowerShell-Sitzung gelöscht.</span><span class="sxs-lookup"><span data-stu-id="b276d-113">By default, `Clear-History` deletes the entire command history from a PowerShell session.</span></span> <span data-ttu-id="b276d-114">Sie können Parameter mit verwenden `Clear-History` , um ausgewählte Befehle zu löschen.</span><span class="sxs-lookup"><span data-stu-id="b276d-114">You can use parameters with `Clear-History` to delete selected commands.</span></span>

<span data-ttu-id="b276d-115">`Clear-History` Löscht die Befehls Verlaufs `PSReadLine` Datei nicht.</span><span class="sxs-lookup"><span data-stu-id="b276d-115">`Clear-History` does not clear the `PSReadLine` command history file.</span></span> <span data-ttu-id="b276d-116">Das `PSReadLine` Modul speichert eine Verlaufs Datei, die jeden PowerShell-Befehl in jeder PowerShell-Sitzung enthält.</span><span class="sxs-lookup"><span data-stu-id="b276d-116">The `PSReadLine` module stores a history file that contains every PowerShell command from every PowerShell session.</span></span> <span data-ttu-id="b276d-117">Verwenden Sie an einer PowerShell-Eingabeaufforderung die Pfeile nach oben und nach unten auf der Tastatur, um durch den Befehlsverlauf zu scrollen.</span><span class="sxs-lookup"><span data-stu-id="b276d-117">From a PowerShell prompt, use the up and down arrows on your keyboard to scroll through the command history.</span></span> <span data-ttu-id="b276d-118">Verwenden Sie, um die `PSReadLine` Konfiguration für den Befehlsverlauf anzuzeigen `Get-PSReadLineOption` .</span><span class="sxs-lookup"><span data-stu-id="b276d-118">To display the `PSReadLine` configuration for command history, use `Get-PSReadLineOption`.</span></span>
<span data-ttu-id="b276d-119">`PSReadLine` ausgeliefert mit PowerShell 5,0 und höher.</span><span class="sxs-lookup"><span data-stu-id="b276d-119">`PSReadLine` shipped with PowerShell 5.0 and above.</span></span> <span data-ttu-id="b276d-120">Weitere Informationen finden Sie unter [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).</span><span class="sxs-lookup"><span data-stu-id="b276d-120">For more information, see [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).</span></span>

## <span data-ttu-id="b276d-121">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="b276d-121">EXAMPLES</span></span>

### <span data-ttu-id="b276d-122">Beispiel 1: Löschen des Befehls Verlaufs aus einer PowerShell-Sitzung</span><span class="sxs-lookup"><span data-stu-id="b276d-122">Example 1: Delete the command history from a PowerShell session</span></span>

<span data-ttu-id="b276d-123">Dieser Befehl löscht alle Befehle aus dem Verlauf einer PowerShell-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="b276d-123">This command deletes all of the commands from a PowerShell session's history.</span></span>

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

<span data-ttu-id="b276d-124">Das `Get-History` -Cmdlet zeigt den Verlauf der PowerShell-Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="b276d-124">The `Get-History` cmdlet displays the PowerShell session's history.</span></span> <span data-ttu-id="b276d-125">`Clear-History` Löscht den gesamten Befehlsverlauf.</span><span class="sxs-lookup"><span data-stu-id="b276d-125">`Clear-History` deletes the entire command history.</span></span> <span data-ttu-id="b276d-126">`Get-History` zeigt den aktualisierten Befehlsverlauf an und bestätigt, dass der vorherige Verlauf gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="b276d-126">`Get-History` displays the updated command history and confirms the prior history was deleted.</span></span>

### <span data-ttu-id="b276d-127">Beispiel 2: Löschen der neuesten Befehle</span><span class="sxs-lookup"><span data-stu-id="b276d-127">Example 2: Delete the newest commands</span></span>

<span data-ttu-id="b276d-128">Dieser Befehl verwendet die Parameter **count** und **Latest** , um die neuesten Befehle aus dem Verlauf einer PowerShell-Sitzung zu löschen.</span><span class="sxs-lookup"><span data-stu-id="b276d-128">This command uses the **Count** and **Newest** parameters to delete the newest commands from a PowerShell session's history.</span></span>

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

<span data-ttu-id="b276d-129">Das `Get-History` -Cmdlet zeigt den Verlauf der PowerShell-Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="b276d-129">The `Get-History` cmdlet displays the PowerShell session's history.</span></span> <span data-ttu-id="b276d-130">`Clear-History` wird verwendet, um den Befehlsverlauf zu löschen.</span><span class="sxs-lookup"><span data-stu-id="b276d-130">`Clear-History` is used to delete the command history.</span></span> <span data-ttu-id="b276d-131">Der **count** -Parameter gibt die Anzahl der zu löschenden Befehle an, einschließlich der angegebenen **ID** . Der **Latest** -Parameter gibt an, dass die neuesten Befehle aus dem Verlauf gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="b276d-131">The **Count** parameter specifies the number of commands to delete, inclusive of the specified **Id** . The **Newest** parameter specifies that the newest commands are cleared from the history.</span></span> <span data-ttu-id="b276d-132">`Get-History`zeigt den aktualisierten Befehlsverlauf an und bestätigt, dass die fünf neuesten Befehle gelöscht wurden, **ID 6**  -  **ID 10** .</span><span class="sxs-lookup"><span data-stu-id="b276d-132">`Get-History` displays the updated command history and confirms that the five newest commands were deleted, **Id 6** - **Id 10** .</span></span>

### <span data-ttu-id="b276d-133">Beispiel 3: Löschen von Befehlen, die bestimmten Kriterien entsprechen</span><span class="sxs-lookup"><span data-stu-id="b276d-133">Example 3: Delete commands that match specific criteria</span></span>

<span data-ttu-id="b276d-134">Dieser Befehl löscht Befehle, die bestimmten Kriterien entsprechen, die vom **CommandLine** -Parameter definiert werden.</span><span class="sxs-lookup"><span data-stu-id="b276d-134">This command deletes commands that match specific criteria defined by the **CommandLine** parameter.</span></span>

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

<span data-ttu-id="b276d-135">Das `Get-History` -Cmdlet zeigt den Verlauf der PowerShell-Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="b276d-135">The `Get-History` cmdlet displays the PowerShell session's history.</span></span> <span data-ttu-id="b276d-136">`Clear-History` Löscht den Befehlsverlauf.</span><span class="sxs-lookup"><span data-stu-id="b276d-136">`Clear-History` deletes the command history.</span></span> <span data-ttu-id="b276d-137">Der **CommandLine** -Parameter gibt Befehle an, die **Hilfe** oder Ende mit **Syntax** enthalten.</span><span class="sxs-lookup"><span data-stu-id="b276d-137">The **CommandLine** parameter specifies commands that contain **Help** or end with **Syntax** .</span></span> <span data-ttu-id="b276d-138">`Get-History` zeigt den aktualisierten Befehlsverlauf an und bestätigt, dass die Befehle **ID 3** , **ID 5** , **ID 6** und **ID 7** gelöscht wurden.</span><span class="sxs-lookup"><span data-stu-id="b276d-138">`Get-History` displays the updated command history and confirms that commands **Id 3** , **Id 5** , **Id 6** , and **Id 7** were deleted.</span></span>

### <span data-ttu-id="b276d-139">Beispiel 4: Löschen von Befehlen nach ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="b276d-139">Example 4: Delete commands by Id number</span></span>

<span data-ttu-id="b276d-140">Mit diesem Befehl werden bestimmte Verlaufs Elemente mithilfe der **ID** gelöscht. Zum Löschen mehrerer Befehle übermitteln Sie eine durch Trennzeichen getrennte Liste mit **ID** -Nummern.</span><span class="sxs-lookup"><span data-stu-id="b276d-140">This command deletes specific history items using the **Id** . To delete multiple commands, submit a comma-separated list of **Id** numbers.</span></span>

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

<span data-ttu-id="b276d-141">Das `Get-History` -Cmdlet zeigt den Verlauf der PowerShell-Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="b276d-141">The `Get-History` cmdlet displays the PowerShell session's history.</span></span> <span data-ttu-id="b276d-142">`Clear-History` Löscht den Befehlsverlauf.</span><span class="sxs-lookup"><span data-stu-id="b276d-142">`Clear-History` deletes the command history.</span></span> <span data-ttu-id="b276d-143">Der **ID** -Parameter gibt an, welche Befehle gelöscht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b276d-143">The **Id** parameter specifies which commands to delete.</span></span> <span data-ttu-id="b276d-144">`Get-History` zeigt den aktualisierten Befehlsverlauf an und bestätigt, dass **ID 3** und **ID 5** gelöscht wurden.</span><span class="sxs-lookup"><span data-stu-id="b276d-144">`Get-History` displays the updated command history and confirms that **Id 3** and **Id 5** were deleted.</span></span>

### <span data-ttu-id="b276d-145">Beispiel 5: Löschen von Befehlen nach ID-Nummer und-Anzahl</span><span class="sxs-lookup"><span data-stu-id="b276d-145">Example 5: Delete commands by Id number and count</span></span>

<span data-ttu-id="b276d-146">Dieser Befehl verwendet die **ID** -und **count** -Parameter, um den Befehlsverlauf zu löschen.</span><span class="sxs-lookup"><span data-stu-id="b276d-146">This command uses the **Id** and **Count** parameters to delete command history.</span></span> <span data-ttu-id="b276d-147">Die Befehle werden aus der angegebenen **ID** in umgekehrter Reihenfolge gelöscht, von der neuesten zum ältesten.</span><span class="sxs-lookup"><span data-stu-id="b276d-147">Commands are deleted from the specified **Id** in reverse order, newest to oldest.</span></span>

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

<span data-ttu-id="b276d-148">Das `Get-History` -Cmdlet zeigt den Verlauf der PowerShell-Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="b276d-148">The `Get-History` cmdlet displays the PowerShell session's history.</span></span> <span data-ttu-id="b276d-149">`Clear-History` Löscht den Befehlsverlauf.</span><span class="sxs-lookup"><span data-stu-id="b276d-149">`Clear-History` deletes the command history.</span></span> <span data-ttu-id="b276d-150">Der **ID** -Parameter gibt an, dass mit **ID 7** begonnen werden soll.</span><span class="sxs-lookup"><span data-stu-id="b276d-150">The **Id** parameter specifies to begin with **Id 7** .</span></span> <span data-ttu-id="b276d-151">Der **count** -Parameter gibt an, dass fünf Befehle einschließlich der angegebenen **ID** gelöscht werden sollen. `Get-History`zeigt den aktualisierten Befehlsverlauf an und bestätigt, dass fünf Befehle gelöscht wurden, **ID 3**  -  **ID 7** .</span><span class="sxs-lookup"><span data-stu-id="b276d-151">The **Count** parameter specifies to delete five commands, inclusive of the specified **Id** . `Get-History` displays the updated command history and confirms that five commands were deleted, **Id 3** - **Id 7** .</span></span>

## <span data-ttu-id="b276d-152">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b276d-152">PARAMETERS</span></span>

### <span data-ttu-id="b276d-153">-CommandLine</span><span class="sxs-lookup"><span data-stu-id="b276d-153">-CommandLine</span></span>

<span data-ttu-id="b276d-154">Löscht den Befehlsverlauf aus einer PowerShell-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="b276d-154">Deletes command history from a PowerShell session.</span></span> <span data-ttu-id="b276d-155">Die Zeichenfolge muss eine exakte Entsprechung sein oder Platzhalter verwenden, um Befehle in dem von angezeigten PowerShell-Sitzungsverlauf abzugleichen `Get-History` .</span><span class="sxs-lookup"><span data-stu-id="b276d-155">The string must be an exact match or use wildcards to match commands in the PowerShell session history displayed by `Get-History`.</span></span> <span data-ttu-id="b276d-156">Wenn Sie mehr als eine Zeichenfolge eingeben, `Clear-History` Löscht die Befehle, die mit einer der Zeichen folgen zu vergleichen sind.</span><span class="sxs-lookup"><span data-stu-id="b276d-156">If you enter more than one string, `Clear-History` deletes commands that match any of the strings.</span></span> <span data-ttu-id="b276d-157">Der **CommandLine** -Parameter kann mit **count** verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b276d-157">The **CommandLine** parameter can be used with **Count** .</span></span>

<span data-ttu-id="b276d-158">Verwenden Sie für Zeichen folgen mit einem Leerzeichen einfache Anführungszeichen.</span><span class="sxs-lookup"><span data-stu-id="b276d-158">For strings with a space, use single quotations.</span></span> <span data-ttu-id="b276d-159">Weitere Informationen finden Sie unter [about_Quoting_Rules](About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="b276d-159">For more information, see [about_Quoting_Rules](About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="b276d-160">-Anzahl</span><span class="sxs-lookup"><span data-stu-id="b276d-160">-Count</span></span>

<span data-ttu-id="b276d-161">Gibt die Anzahl von Verlaufs Einträgen an, die von `Clear-History` gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="b276d-161">Specifies the number of history entries that `Clear-History` deletes.</span></span> <span data-ttu-id="b276d-162">Befehle werden in der Reihenfolge gelöscht, beginnend mit dem ältesten Eintrag im Verlauf.</span><span class="sxs-lookup"><span data-stu-id="b276d-162">Commands are deleted in order, beginning with the oldest entry in the history.</span></span>

<span data-ttu-id="b276d-163">Die Parameter **count** und **ID** können gleichzeitig verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b276d-163">The **Count** and **Id** parameters can be used together.</span></span> <span data-ttu-id="b276d-164">Der **count** -Parameter gibt die Anzahl der zu löschenden Befehle an, einschließlich der angegebenen **ID** . Beginnend bei der angegebenen **ID** werden die Befehle in umgekehrter sequenzieller Reihenfolge gelöscht.</span><span class="sxs-lookup"><span data-stu-id="b276d-164">The **Count** parameter specifies the number of commands to delete, inclusive of the specified **Id** . Beginning at the specified **Id** , commands are deleted in reverse sequential order.</span></span> <span data-ttu-id="b276d-165">Wenn die **ID** z. b. 30 und die **Anzahl** 10 beträgt, `Clear-History` Löscht die Elemente 21 bis 30.</span><span class="sxs-lookup"><span data-stu-id="b276d-165">For example, if the **Id** is 30 and the **Count** is 10, `Clear-History` deletes items 21 through 30.</span></span>

<span data-ttu-id="b276d-166">Die Parameter **count** und **CommandLine** können gleichzeitig verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b276d-166">The **Count** and **CommandLine** parameters can be used together.</span></span> <span data-ttu-id="b276d-167">**Count** gibt die Anzahl der zu löschenden Befehle an, die dem **CommandLine** -Parameterwert entsprechen.</span><span class="sxs-lookup"><span data-stu-id="b276d-167">**Count** specifies the number of commands to delete that match **CommandLine** parameter value.</span></span> <span data-ttu-id="b276d-168">Die Befehle werden in sequenzieller Reihenfolge gelöscht.</span><span class="sxs-lookup"><span data-stu-id="b276d-168">The commands are deleted in sequential order.</span></span>

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

### <span data-ttu-id="b276d-169">-Id</span><span class="sxs-lookup"><span data-stu-id="b276d-169">-Id</span></span>

<span data-ttu-id="b276d-170">Gibt die Befehlsverlauf- **ID** an, die von `Clear-History` gelöscht wird</span><span class="sxs-lookup"><span data-stu-id="b276d-170">Specifies the command history **Id** that `Clear-History` deletes.</span></span> <span data-ttu-id="b276d-171">Verwenden Sie das-Cmdlet, um die **ID** -Nummern anzuzeigen `Get-History` .</span><span class="sxs-lookup"><span data-stu-id="b276d-171">To display **Id** numbers, use the `Get-History` cmdlet.</span></span> <span data-ttu-id="b276d-172">Die **ID** -Nummern sind sequenziell, und die Befehle behalten ihre **ID** -Nummer in einer PowerShell-Sitzung bei.</span><span class="sxs-lookup"><span data-stu-id="b276d-172">The **Id** numbers are sequential and commands keep their **Id** number throughout a PowerShell session.</span></span> <span data-ttu-id="b276d-173">Der **ID** -Parameter kann mit **count** und **Latest** verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b276d-173">The **Id** parameter can be used with **Count** and **Newest** .</span></span>

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

### <span data-ttu-id="b276d-174">-Latest</span><span class="sxs-lookup"><span data-stu-id="b276d-174">-Newest</span></span>

<span data-ttu-id="b276d-175">Wenn der **neueste** Parameter verwendet wird, `Clear-History` Löscht die neuesten Einträge im Verlauf.</span><span class="sxs-lookup"><span data-stu-id="b276d-175">When the **Newest** parameter is used, `Clear-History` deletes the newest entries in the history.</span></span> <span data-ttu-id="b276d-176">Standardmäßig `Clear-History` Löscht die ältesten Einträge im Verlauf.</span><span class="sxs-lookup"><span data-stu-id="b276d-176">By default, `Clear-History` deletes the oldest entries in the history.</span></span>

<span data-ttu-id="b276d-177">Der **neueste** Parameter kann mit der **ID** und der **Anzahl** verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b276d-177">The **Newest** parameter can be used with **Id** and **Count** .</span></span> <span data-ttu-id="b276d-178">Der **count** -Parameter gibt die Anzahl der zu löschenden Befehle an, einschließlich der angegebenen **ID** . Beginnend bei der angegebenen **ID** werden die Befehle in sequenzieller Reihenfolge gelöscht.</span><span class="sxs-lookup"><span data-stu-id="b276d-178">The **Count** parameter specifies the number of commands to delete, inclusive of the specified **Id** . Beginning at the specified **Id** , commands are deleted in sequential order.</span></span> <span data-ttu-id="b276d-179">Wenn die **ID** z. b. 30 und die **Anzahl** 10 beträgt, `Clear-History` Löscht die Elemente 30 bis 39.</span><span class="sxs-lookup"><span data-stu-id="b276d-179">For example, if the **Id** is 30 and the **Count** is 10, `Clear-History` deletes items 30 through 39.</span></span>

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

### <span data-ttu-id="b276d-180">-Confirm</span><span class="sxs-lookup"><span data-stu-id="b276d-180">-Confirm</span></span>

<span data-ttu-id="b276d-181">Sie werden zur Bestätigung aufgefordert, bevor Sie das `Clear-History` Cmdlet ausführen.</span><span class="sxs-lookup"><span data-stu-id="b276d-181">Prompts you for confirmation before running the `Clear-History` cmdlet.</span></span>

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

### <span data-ttu-id="b276d-182">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="b276d-182">-WhatIf</span></span>

<span data-ttu-id="b276d-183">Zeigt, was geschieht, wenn das `Clear-History` Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b276d-183">Shows what would happen if the `Clear-History` cmdlet runs.</span></span> <span data-ttu-id="b276d-184">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b276d-184">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="b276d-185">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b276d-185">CommonParameters</span></span>

<span data-ttu-id="b276d-186">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b276d-186">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b276d-187">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="b276d-187">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="b276d-188">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="b276d-188">INPUTS</span></span>

### <span data-ttu-id="b276d-189">Keine</span><span class="sxs-lookup"><span data-stu-id="b276d-189">None</span></span>

<span data-ttu-id="b276d-190">Objekte können nicht an übergeben werden `Clear-History` .</span><span class="sxs-lookup"><span data-stu-id="b276d-190">You cannot pipe objects to `Clear-History`.</span></span>

## <span data-ttu-id="b276d-191">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="b276d-191">OUTPUTS</span></span>

### <span data-ttu-id="b276d-192">Keine</span><span class="sxs-lookup"><span data-stu-id="b276d-192">None</span></span>

<span data-ttu-id="b276d-193">`Clear-History` generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="b276d-193">`Clear-History` does not generate any output.</span></span>

## <span data-ttu-id="b276d-194">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="b276d-194">NOTES</span></span>

<span data-ttu-id="b276d-195">Der PowerShell-Sitzungsverlauf ist eine Liste der Befehle, die während einer PowerShell-Sitzung eingegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="b276d-195">The PowerShell session history is a list of the commands entered during a PowerShell session.</span></span> <span data-ttu-id="b276d-196">Sie können den Verlauf anzeigen, Befehle hinzufügen und löschen und Befehle aus dem Verlauf ausführen.</span><span class="sxs-lookup"><span data-stu-id="b276d-196">You can view the history, add and delete commands, and run commands from the history.</span></span> <span data-ttu-id="b276d-197">Weitere Informationen finden Sie unter [about_History](About/about_History.md).</span><span class="sxs-lookup"><span data-stu-id="b276d-197">For more information, see [about_History](About/about_History.md).</span></span>

<span data-ttu-id="b276d-198">Der Sitzungsverlauf wird getrennt von dem vom **psread Line** -Modul verwalteten Verlauf verwaltet.</span><span class="sxs-lookup"><span data-stu-id="b276d-198">The session history is managed separately from the history maintained by the **PSReadLine** module.</span></span>
<span data-ttu-id="b276d-199">Beide Verläufe sind in Sitzungen verfügbar, in denen **psread Line** geladen wird.</span><span class="sxs-lookup"><span data-stu-id="b276d-199">Both histories are available in sessions where **PSReadLine** is loaded.</span></span> <span data-ttu-id="b276d-200">Dieses Cmdlet funktioniert nur mit dem Sitzungsverlauf.</span><span class="sxs-lookup"><span data-stu-id="b276d-200">This cmdlet only works with the session history.</span></span> <span data-ttu-id="b276d-201">Weitere Informationen finden Sie unter [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).</span><span class="sxs-lookup"><span data-stu-id="b276d-201">For more information see, [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).</span></span>

## <span data-ttu-id="b276d-202">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="b276d-202">RELATED LINKS</span></span>

[<span data-ttu-id="b276d-203">about_History</span><span class="sxs-lookup"><span data-stu-id="b276d-203">about_History</span></span>](About/about_History.md)

[<span data-ttu-id="b276d-204">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="b276d-204">about_PSReadLine</span></span>](../PSReadLine/About/about_PSReadLine.md)

[<span data-ttu-id="b276d-205">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="b276d-205">about_Quoting_Rules</span></span>](About/about_Quoting_Rules.md)

[<span data-ttu-id="b276d-206">Add-History</span><span class="sxs-lookup"><span data-stu-id="b276d-206">Add-History</span></span>](Add-History.md)

[<span data-ttu-id="b276d-207">Get-History</span><span class="sxs-lookup"><span data-stu-id="b276d-207">Get-History</span></span>](Get-History.md)

[<span data-ttu-id="b276d-208">Invoke-History</span><span class="sxs-lookup"><span data-stu-id="b276d-208">Invoke-History</span></span>](Invoke-History.md)

[<span data-ttu-id="b276d-209">Get-psread lineoption</span><span class="sxs-lookup"><span data-stu-id="b276d-209">Get-PSReadLineOption</span></span>](/powershell/module/psreadline/get-psreadlineoption)

[<span data-ttu-id="b276d-210">Set-psread lineoption</span><span class="sxs-lookup"><span data-stu-id="b276d-210">Set-PSReadLineOption</span></span>](/powershell/module/psreadline/set-psreadlineoption)
