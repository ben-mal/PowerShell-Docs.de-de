---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 05/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/invoke-history?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-History
ms.openlocfilehash: 6745ceb3e6106bacf45d0c20fc916951316139dc
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216460"
---
# <span data-ttu-id="89204-103">Invoke-History</span><span class="sxs-lookup"><span data-stu-id="89204-103">Invoke-History</span></span>

## <span data-ttu-id="89204-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="89204-104">SYNOPSIS</span></span>
<span data-ttu-id="89204-105">Führt Befehle aus dem Sitzungsverlauf aus.</span><span class="sxs-lookup"><span data-stu-id="89204-105">Runs commands from the session history.</span></span>

## <span data-ttu-id="89204-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="89204-106">SYNTAX</span></span>

```
Invoke-History [[-Id] <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="89204-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="89204-107">DESCRIPTION</span></span>

<span data-ttu-id="89204-108">Das- `Invoke-History` Cmdlet führt Befehle aus dem Sitzungsverlauf aus.</span><span class="sxs-lookup"><span data-stu-id="89204-108">The `Invoke-History` cmdlet runs commands from the session history.</span></span> <span data-ttu-id="89204-109">Sie können Objekte, die die Befehle darstellen, von Get-History an übergeben `Invoke-History` , oder Sie können Befehle im aktuellen Verlauf mithilfe Ihrer **ID** -Nummer identifizieren.</span><span class="sxs-lookup"><span data-stu-id="89204-109">You can pass objects representing the commands from Get-History to `Invoke-History`, or you can identify commands in the current history by using their **Id** number.</span></span> <span data-ttu-id="89204-110">Verwenden Sie das-Cmdlet, um die ID eines Befehls zu ermitteln `Get-History` .</span><span class="sxs-lookup"><span data-stu-id="89204-110">To find the identification number of a command, use the `Get-History` cmdlet.</span></span>

<span data-ttu-id="89204-111">Der Sitzungsverlauf wird getrennt von dem vom **psread Line** -Modul verwalteten Verlauf verwaltet.</span><span class="sxs-lookup"><span data-stu-id="89204-111">The session history is managed separately from the history maintained by the **PSReadLine** module.</span></span>
<span data-ttu-id="89204-112">Beide Verläufe sind in Sitzungen verfügbar, in denen **psread Line** geladen wird.</span><span class="sxs-lookup"><span data-stu-id="89204-112">Both histories are available in sessions where **PSReadLine** is loaded.</span></span> <span data-ttu-id="89204-113">Dieses Cmdlet funktioniert nur mit dem Sitzungsverlauf.</span><span class="sxs-lookup"><span data-stu-id="89204-113">This cmdlet only works with the session history.</span></span> <span data-ttu-id="89204-114">Weitere Informationen finden Sie unter [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).</span><span class="sxs-lookup"><span data-stu-id="89204-114">For more information see, [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).</span></span>

## <span data-ttu-id="89204-115">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="89204-115">EXAMPLES</span></span>

### <span data-ttu-id="89204-116">Beispiel 1: Ausführen des letzten Befehls im Verlauf</span><span class="sxs-lookup"><span data-stu-id="89204-116">Example 1: Run the most recent command in the history</span></span>

<span data-ttu-id="89204-117">In diesem Beispiel wird der letzte oder neueste Befehl im Sitzungsverlauf ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="89204-117">This example runs the last, or most recent, command in the session history.</span></span> <span data-ttu-id="89204-118">Sie können diesen Befehl als `r` , den Alias für, abkürzen `Invoke-History` .</span><span class="sxs-lookup"><span data-stu-id="89204-118">You can abbreviate this command as `r`, the alias for `Invoke-History`.</span></span>

```powershell
Invoke-History
```

### <span data-ttu-id="89204-119">Beispiel 2: führen Sie den Befehl aus, der über eine angegebene ID verfügt.</span><span class="sxs-lookup"><span data-stu-id="89204-119">Example 2: Run the command that has a specified ID</span></span>

<span data-ttu-id="89204-120">Dieses Beispiel führt den Befehl im Sitzungsverlauf mit der **ID** 132 aus.</span><span class="sxs-lookup"><span data-stu-id="89204-120">This example runs the command in the session history with **Id** 132.</span></span> <span data-ttu-id="89204-121">Da der Name des **ID** -Parameters optional ist, können Sie diesen Befehl wie folgt abkürzen: `Invoke-History 132` , `ihy 132` oder `r 132` .</span><span class="sxs-lookup"><span data-stu-id="89204-121">Because the name of the **Id** parameter is optional, you can abbreviate this command as the following: `Invoke-History 132`, `ihy 132`, or `r 132`.</span></span>

```powershell
Invoke-History -Id 132
```

### <span data-ttu-id="89204-122">Beispiel 3: Ausführen des neuesten Befehls mit dem Befehls Text</span><span class="sxs-lookup"><span data-stu-id="89204-122">Example 3: Run the most recent command by using the command text</span></span>

<span data-ttu-id="89204-123">In diesem Beispiel wird der letzte `Get-Process` Befehl im Sitzungsverlauf ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="89204-123">This example runs the most recent `Get-Process` command in the session history.</span></span> <span data-ttu-id="89204-124">Wenn Sie Zeichen für den **ID** -Parameter eingeben, `Invoke-History` führt den ersten gefundenen Befehl aus, der mit dem Muster übereinstimmt, beginnend mit den neuesten Befehlen.</span><span class="sxs-lookup"><span data-stu-id="89204-124">When you type characters for the **Id** parameter, `Invoke-History` runs the first command that it finds that matches the pattern, starting with the most recent commands.</span></span>

```powershell
Invoke-History -Id get-pr
```

> [!NOTE]
> <span data-ttu-id="89204-125">Beim Musterabgleich wird die Groß-/Kleinschreibung nicht beachtet, aber das Muster entspricht dem Anfang der Zeile.</span><span class="sxs-lookup"><span data-stu-id="89204-125">Pattern matching is case-insensitive, but the pattern matches the beginning of the line.</span></span>

### <span data-ttu-id="89204-126">Beispiel 4: Ausführen einer Sequenz von Befehlen aus dem Verlauf</span><span class="sxs-lookup"><span data-stu-id="89204-126">Example 4: Run a sequence of commands from the history</span></span>

<span data-ttu-id="89204-127">Dieses Beispiel führt die Befehle 16 bis 24 aus.</span><span class="sxs-lookup"><span data-stu-id="89204-127">This example runs commands 16 through 24.</span></span> <span data-ttu-id="89204-128">Da Sie nur einen **ID** -Wert auflisten können, verwendet der Befehl das `ForEach-Object` Cmdlet, um den `Invoke-History` Befehl für jeden **ID** -Wert einmal auszuführen.</span><span class="sxs-lookup"><span data-stu-id="89204-128">Because you can list only one **Id** value, the command uses the `ForEach-Object` cmdlet to run the `Invoke-History` command one time for each **Id** value.</span></span>

```powershell
16..24 | ForEach {Invoke-History -Id $_ }
```

### <span data-ttu-id="89204-129">Beispiel 5</span><span class="sxs-lookup"><span data-stu-id="89204-129">Example 5</span></span>

<span data-ttu-id="89204-130">Dieses Beispiel führt die sieben Befehle im Verlauf aus, die mit dem Befehl 255 (249 bis 255) enden.</span><span class="sxs-lookup"><span data-stu-id="89204-130">This example runs the seven commands in the history that end with command 255 (249 through 255).</span></span> <span data-ttu-id="89204-131">Er verwendet das `Get-History` Cmdlet zum Abrufen der Befehle.</span><span class="sxs-lookup"><span data-stu-id="89204-131">It uses the `Get-History` cmdlet to retrieve the commands.</span></span> <span data-ttu-id="89204-132">Da Sie nur einen **ID** -Wert auflisten können, verwendet der Befehl das `ForEach-Object` Cmdlet, um den `Invoke-History` Befehl für jeden **ID** -Wert einmal auszuführen.</span><span class="sxs-lookup"><span data-stu-id="89204-132">Because you can list only one **Id** value, the command uses the `ForEach-Object` cmdlet to run the `Invoke-History` command once for each **Id** value.</span></span>

```powershell
Get-History -Id 255 -Count 7 | ForEach {Invoke-History -Id $_.Id}
```

## <span data-ttu-id="89204-133">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="89204-133">PARAMETERS</span></span>

### <span data-ttu-id="89204-134">-Id</span><span class="sxs-lookup"><span data-stu-id="89204-134">-Id</span></span>

<span data-ttu-id="89204-135">Gibt die **ID** eines Befehls im Verlauf an.</span><span class="sxs-lookup"><span data-stu-id="89204-135">Specifies the **Id** of a command in the history.</span></span> <span data-ttu-id="89204-136">Sie können die **ID** -Nummer des Befehls oder die ersten Zeichen des Befehls eingeben.</span><span class="sxs-lookup"><span data-stu-id="89204-136">You can type the **Id** number of the command or the first few characters of the command.</span></span>

<span data-ttu-id="89204-137">Wenn Sie Zeichen eingeben, werden `Invoke-History` zuerst die neuesten Befehle abgeglichen.</span><span class="sxs-lookup"><span data-stu-id="89204-137">If you type characters, `Invoke-History` matches the most recent commands first.</span></span> <span data-ttu-id="89204-138">Wenn Sie diesen Parameter weglassen, `Invoke-History` führt den letzten oder letzten Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="89204-138">If you omit this parameter, `Invoke-History` runs the last, or most recent, command.</span></span> <span data-ttu-id="89204-139">Verwenden Sie das-Cmdlet, um die **ID** -Nummer eines Befehls zu ermitteln `Get-History` .</span><span class="sxs-lookup"><span data-stu-id="89204-139">To find the **Id** number of a command, use the `Get-History` cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="89204-140">-Confirm</span><span class="sxs-lookup"><span data-stu-id="89204-140">-Confirm</span></span>

<span data-ttu-id="89204-141">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="89204-141">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="89204-142">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="89204-142">-WhatIf</span></span>

<span data-ttu-id="89204-143">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="89204-143">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="89204-144">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="89204-144">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="89204-145">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="89204-145">CommonParameters</span></span>

<span data-ttu-id="89204-146">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="89204-146">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="89204-147">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="89204-147">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="89204-148">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="89204-148">INPUTS</span></span>

### <span data-ttu-id="89204-149">System.String</span><span class="sxs-lookup"><span data-stu-id="89204-149">System.String</span></span>

<span data-ttu-id="89204-150">Sie können eine Verlaufs- **ID** an dieses Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="89204-150">You can pipe a history **Id** to this cmdlet.</span></span>

## <span data-ttu-id="89204-151">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="89204-151">OUTPUTS</span></span>

### <span data-ttu-id="89204-152">Keine</span><span class="sxs-lookup"><span data-stu-id="89204-152">None</span></span>

<span data-ttu-id="89204-153">Dieses Cmdlet generiert keine Ausgabe, aber die Ausgabe kann durch die Befehle generiert werden, die ausgeführt werden `Invoke-History` .</span><span class="sxs-lookup"><span data-stu-id="89204-153">This cmdlet does not generate any output, but output might be generated by the commands that `Invoke-History` runs.</span></span>

## <span data-ttu-id="89204-154">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="89204-154">NOTES</span></span>

<span data-ttu-id="89204-155">Der Sitzungsverlauf ist eine Liste der Befehle, die während der Sitzung eingegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="89204-155">The session history is a list of the commands entered during the session.</span></span> <span data-ttu-id="89204-156">Der Sitzungsverlauf stellt die Reihenfolge der Ausführung, den Status und die Start- und Endzeiten des Befehls dar.</span><span class="sxs-lookup"><span data-stu-id="89204-156">The session history represents the order of execution, the status, and the start and end times of the command.</span></span> <span data-ttu-id="89204-157">Wenn Sie jeden Befehl eingeben, wird er von PowerShell dem Verlauf hinzugefügt, damit Sie ihn wieder verwenden können.</span><span class="sxs-lookup"><span data-stu-id="89204-157">As you enter each command, PowerShell adds it to the history so that you can reuse it.</span></span> <span data-ttu-id="89204-158">Weitere Informationen zum Sitzungsverlauf finden Sie unter [about_History](About/about_History.md).</span><span class="sxs-lookup"><span data-stu-id="89204-158">For more information about the session history, see [about_History](About/about_History.md).</span></span>

<span data-ttu-id="89204-159">Weitere Informationen finden Sie auch unter `Invoke-History` den integrierten Aliasen `r` und `ihy` .</span><span class="sxs-lookup"><span data-stu-id="89204-159">You can also refer to `Invoke-History` by its built-in aliases, `r` and `ihy`.</span></span> <span data-ttu-id="89204-160">Weitere Informationen finden Sie unter [about_Aliases](About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="89204-160">For more information, see [about_Aliases](About/about_Aliases.md).</span></span>

## <span data-ttu-id="89204-161">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="89204-161">RELATED LINKS</span></span>

[<span data-ttu-id="89204-162">Add-History</span><span class="sxs-lookup"><span data-stu-id="89204-162">Add-History</span></span>](Add-History.md)

[<span data-ttu-id="89204-163">Clear-History</span><span class="sxs-lookup"><span data-stu-id="89204-163">Clear-History</span></span>](Clear-History.md)

[<span data-ttu-id="89204-164">Get-History</span><span class="sxs-lookup"><span data-stu-id="89204-164">Get-History</span></span>](Get-History.md)
