---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unblock-File
ms.openlocfilehash: 47d69cbe8d8542b5954d3e4a585735f7d0050715
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2020
ms.locfileid: "94347719"
---
# <span data-ttu-id="33b66-103">Unblock-File</span><span class="sxs-lookup"><span data-stu-id="33b66-103">Unblock-File</span></span>

## <span data-ttu-id="33b66-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="33b66-104">SYNOPSIS</span></span>
<span data-ttu-id="33b66-105">Hebt die Blockierung von Dateien auf, die aus dem Internet heruntergeladen wurden.</span><span class="sxs-lookup"><span data-stu-id="33b66-105">Unblocks files that were downloaded from the Internet.</span></span>

## <span data-ttu-id="33b66-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="33b66-106">SYNTAX</span></span>

### <span data-ttu-id="33b66-107">Bypath (Standard)</span><span class="sxs-lookup"><span data-stu-id="33b66-107">ByPath (Default)</span></span>

```
Unblock-File [-Path] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="33b66-108">Byliteralpath</span><span class="sxs-lookup"><span data-stu-id="33b66-108">ByLiteralPath</span></span>

```
Unblock-File -LiteralPath <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="33b66-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="33b66-109">DESCRIPTION</span></span>

<span data-ttu-id="33b66-110">Mit dem- `Unblock-File` Cmdlet können Sie Dateien öffnen, die aus dem Internet heruntergeladen wurden.</span><span class="sxs-lookup"><span data-stu-id="33b66-110">The `Unblock-File` cmdlet lets you open files that were downloaded from the Internet.</span></span> <span data-ttu-id="33b66-111">Die Blockierung von PowerShell-Skriptdateien, die aus dem Internet heruntergeladen wurden, wird aufgehoben, sodass Sie Sie ausführen können, auch wenn die PowerShell-Ausführungs Richtlinie **RemoteSigned** ist.</span><span class="sxs-lookup"><span data-stu-id="33b66-111">It unblocks PowerShell script files that were downloaded from the Internet so you can run them, even when the PowerShell execution policy is **RemoteSigned**.</span></span> <span data-ttu-id="33b66-112">Standardmäßig werden diese Dateien blockiert, um den Computer vor nicht vertrauenswürdigen Dateien zu schützen.</span><span class="sxs-lookup"><span data-stu-id="33b66-112">By default, these files are blocked to protect the computer from untrusted files.</span></span>

<span data-ttu-id="33b66-113">Bevor Sie das `Unblock-File` Cmdlet verwenden, überprüfen Sie die Datei und ihre Quelle, und vergewissern Sie sich, dass Sie sicher geöffnet werden kann.</span><span class="sxs-lookup"><span data-stu-id="33b66-113">Before using the `Unblock-File` cmdlet, review the file and its source and verify that it is safe to open.</span></span>

<span data-ttu-id="33b66-114">Intern entfernt das `Unblock-File` Cmdlet den alternativen Datenstrom "Zone. Identifier" mit dem Wert "3", um anzugeben, dass er aus dem Internet heruntergeladen wurde.</span><span class="sxs-lookup"><span data-stu-id="33b66-114">Internally, the `Unblock-File` cmdlet removes the Zone.Identifier alternate data stream, which has a value of "3" to indicate that it was downloaded from the Internet.</span></span>

<span data-ttu-id="33b66-115">Weitere Informationen zu PowerShell-Ausführungsrichtlinien finden Sie unter [about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="33b66-115">For more information about PowerShell execution policies, see [about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md).</span></span>

<span data-ttu-id="33b66-116">Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="33b66-116">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="33b66-117">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="33b66-117">EXAMPLES</span></span>

### <span data-ttu-id="33b66-118">Beispiel 1: Entsperren einer Datei</span><span class="sxs-lookup"><span data-stu-id="33b66-118">Example 1: Unblock a file</span></span>

<span data-ttu-id="33b66-119">Dieser Befehl hebt die Blockierung der Datei „PowerShellTips.chm“ auf.</span><span class="sxs-lookup"><span data-stu-id="33b66-119">This command unblocks the PowerShellTips.chm file.</span></span>

```
PS C:\> Unblock-File -Path C:\Users\User01\Documents\Downloads\PowerShellTips.chm
```

### <span data-ttu-id="33b66-120">Beispiel 2: entsperren mehrerer Dateien</span><span class="sxs-lookup"><span data-stu-id="33b66-120">Example 2: Unblock multiple files</span></span>

<span data-ttu-id="33b66-121">Dieser Befehl hebt die Blockierung aller Dateien im Verzeichnis auf, `C:\Downloads` deren Namen "PowerShell" enthalten.</span><span class="sxs-lookup"><span data-stu-id="33b66-121">This command unblocks all of the files in the `C:\Downloads` directory whose names include "PowerShell".</span></span> <span data-ttu-id="33b66-122">Führen Sie keinen Befehl wie diesen aus, bis Sie sichergestellt haben, dass alle Dateien sicher sind.</span><span class="sxs-lookup"><span data-stu-id="33b66-122">Do not run a command like this one until you have verified that all files are safe.</span></span>

```
PS C:\> dir C:\Downloads\*PowerShell* | Unblock-File
```

### <span data-ttu-id="33b66-123">Beispiel 3: Suchen und Entsperren von Skripts</span><span class="sxs-lookup"><span data-stu-id="33b66-123">Example 3: Find and unblock scripts</span></span>

<span data-ttu-id="33b66-124">Dieser Befehl zeigt, wie Sie PowerShell-Skripts suchen und deren Blockierung entsperren.</span><span class="sxs-lookup"><span data-stu-id="33b66-124">This command shows how to find and unblock PowerShell scripts.</span></span>

<span data-ttu-id="33b66-125">Der erste Befehl verwendet den **Stream** -Parameter des *Get-Item-* Cmdlets zum Aufrufen von Dateien mit dem "Zone. Identifier"-Stream.</span><span class="sxs-lookup"><span data-stu-id="33b66-125">The first command uses the **Stream** parameter of the *Get-Item* cmdlet get files with the Zone.Identifier stream.</span></span>

<span data-ttu-id="33b66-126">Der zweite Befehl zeigt, was geschieht, wenn Sie ein blockiertes Skript in einer PowerShell-Sitzung ausführen, in der die Ausführungs Richtlinie **RemoteSigned** ist.</span><span class="sxs-lookup"><span data-stu-id="33b66-126">The second command shows what happens when you run a blocked script in a PowerShell session in which the execution policy is **RemoteSigned**.</span></span> <span data-ttu-id="33b66-127">Die RemoteSigned-Richtlinie verhindert die Ausführung von Skripts, die aus dem Internet heruntergeladen werden, es sei denn, sie sind digital signiert.</span><span class="sxs-lookup"><span data-stu-id="33b66-127">The RemoteSigned policy prevents you from running scripts that are downloaded from the Internet unless they are digitally signed.</span></span>

<span data-ttu-id="33b66-128">Der dritte Befehl verwendet das `Unblock-File` Cmdlet, um die Blockierung des Skripts zu entsperren, sodass es in der Sitzung ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="33b66-128">The third command uses the `Unblock-File` cmdlet to unblock the script so it can run in the session.</span></span>

```
PS C:\> Get-Item * -Stream "Zone.Identifier" -ErrorAction SilentlyContinue
   FileName: C:\ps-test\Start-ActivityTracker.ps1

Stream                   Length
------                   ------
Zone.Identifier              26

PS C:\> C:\ps-test\Start-ActivityTracker.ps1
c:\ps-test\Start-ActivityTracker.ps1 : File c:\ps-test\Start-ActivityTracker.ps1 cannot
be loaded. The file c:\ps-test\Start-ActivityTracker.ps1 is not digitally signed. The script
will not execute on the system. For more information, see about_Execution_Policies.

At line:1 char:1
+ c:\ps-test\Start-ActivityTracker.ps1
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : SecurityError: (:) [], PSSecurityException
    + FullyQualifiedErrorId : UnauthorizedAccess

PS C:\> Get-Item C:\ps-test\Start-ActivityTracker.ps1 | Unblock-File
```

## <span data-ttu-id="33b66-129">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="33b66-129">PARAMETERS</span></span>

### <span data-ttu-id="33b66-130">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="33b66-130">-LiteralPath</span></span>

<span data-ttu-id="33b66-131">Gibt die Dateien an, deren Blockierung aufgehoben werden soll.</span><span class="sxs-lookup"><span data-stu-id="33b66-131">Specifies the files to unblock.</span></span> <span data-ttu-id="33b66-132">Im Gegensatz zu **Path** wird der Wert des **LiteralPath** -Parameters genauso verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="33b66-132">Unlike **Path** , the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="33b66-133">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="33b66-133">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="33b66-134">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="33b66-134">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="33b66-135">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="33b66-135">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="33b66-136">-Path</span><span class="sxs-lookup"><span data-stu-id="33b66-136">-Path</span></span>

<span data-ttu-id="33b66-137">Gibt die Dateien an, deren Blockierung aufgehoben werden soll.</span><span class="sxs-lookup"><span data-stu-id="33b66-137">Specifies the files to unblock.</span></span> <span data-ttu-id="33b66-138">Platzhalterzeichen werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="33b66-138">Wildcard characters are supported.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="33b66-139">-Confirm</span><span class="sxs-lookup"><span data-stu-id="33b66-139">-Confirm</span></span>

<span data-ttu-id="33b66-140">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="33b66-140">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="33b66-141">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="33b66-141">-WhatIf</span></span>

<span data-ttu-id="33b66-142">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="33b66-142">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="33b66-143">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="33b66-143">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="33b66-144">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="33b66-144">CommonParameters</span></span>

<span data-ttu-id="33b66-145">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="33b66-145">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="33b66-146">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="33b66-146">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="33b66-147">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="33b66-147">INPUTS</span></span>

### <span data-ttu-id="33b66-148">System.String</span><span class="sxs-lookup"><span data-stu-id="33b66-148">System.String</span></span>

<span data-ttu-id="33b66-149">Sie können einen Dateipfad an die Pipeline übergeben `Unblock-File` .</span><span class="sxs-lookup"><span data-stu-id="33b66-149">You can pipe a file path to `Unblock-File`.</span></span>

## <span data-ttu-id="33b66-150">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="33b66-150">OUTPUTS</span></span>

### <span data-ttu-id="33b66-151">Keine</span><span class="sxs-lookup"><span data-stu-id="33b66-151">None</span></span>

<span data-ttu-id="33b66-152">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="33b66-152">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="33b66-153">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="33b66-153">NOTES</span></span>

- <span data-ttu-id="33b66-154">Unterstützung für macOS wurde in PowerShell 7 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="33b66-154">Support for macOS was added in PowerShell 7.</span></span>
- <span data-ttu-id="33b66-155">Das- `Unblock-File` Cmdlet funktioniert nur in Dateisystem Laufwerken.</span><span class="sxs-lookup"><span data-stu-id="33b66-155">The `Unblock-File` cmdlet works only in file system drives.</span></span>
- <span data-ttu-id="33b66-156">`Unblock-File` führt den gleichen Vorgang wie die **Schaltfläche "entsperren"** im Dialogfeld " **Eigenschaften** " im Datei-Explorer aus.</span><span class="sxs-lookup"><span data-stu-id="33b66-156">`Unblock-File` performs the same operation as the **Unblock** button on the **Properties** dialog box in File Explorer.</span></span>
- <span data-ttu-id="33b66-157">Wenn Sie das `Unblock-File` Cmdlet für eine Datei verwenden, die nicht blockiert ist, hat der Befehl keine Auswirkungen auf die nicht blockierte Datei, und das Cmdlet generiert keine Fehler.</span><span class="sxs-lookup"><span data-stu-id="33b66-157">If you use the `Unblock-File` cmdlet on a file that is not blocked, the command has no effect on the unblocked file and the cmdlet does not generate errors.</span></span>

## <span data-ttu-id="33b66-158">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="33b66-158">RELATED LINKS</span></span>

[<span data-ttu-id="33b66-159">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="33b66-159">about_Execution_Policies</span></span>](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md)

[<span data-ttu-id="33b66-160">Get-Item</span><span class="sxs-lookup"><span data-stu-id="33b66-160">Get-Item</span></span>](../Microsoft.PowerShell.Management/Get-Item.md)

[<span data-ttu-id="33b66-161">Out-File</span><span class="sxs-lookup"><span data-stu-id="33b66-161">Out-File</span></span>](Out-File.md)

[<span data-ttu-id="33b66-162">FileSystem-Anbieter</span><span class="sxs-lookup"><span data-stu-id="33b66-162">FileSystem Provider</span></span>](../Microsoft.PowerShell.Core/about/about_FileSystem_Provider.md)
