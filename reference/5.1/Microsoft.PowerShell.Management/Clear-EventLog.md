---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/clear-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-EventLog
ms.openlocfilehash: 695a13d4fbbf60caadeed994c1aa9c36432be917
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215564"
---
# <span data-ttu-id="32d4b-103">Clear-EventLog</span><span class="sxs-lookup"><span data-stu-id="32d4b-103">Clear-EventLog</span></span>

## <span data-ttu-id="32d4b-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="32d4b-104">SYNOPSIS</span></span>
<span data-ttu-id="32d4b-105">Löscht alle Einträge aus den angegebenen Ereignisprotokollen auf den lokalen Computern oder Remote Computern.</span><span class="sxs-lookup"><span data-stu-id="32d4b-105">Clears all entries from specified event logs on the local or remote computers.</span></span>

## <span data-ttu-id="32d4b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="32d4b-106">SYNTAX</span></span>

```
Clear-EventLog [-LogName] <String[]> [[-ComputerName] <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="32d4b-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="32d4b-107">DESCRIPTION</span></span>

<span data-ttu-id="32d4b-108">Mit dem- `Clear-EventLog` Cmdlet werden alle Einträge aus den angegebenen Ereignisprotokollen auf dem lokalen Computer oder auf Remote Computern gelöscht.</span><span class="sxs-lookup"><span data-stu-id="32d4b-108">The `Clear-EventLog` cmdlet deletes all of the entries from the specified event logs on the local computer or on remote computers.</span></span>
<span data-ttu-id="32d4b-109">Zum verwenden `Clear-EventLog` von müssen Sie Mitglied der Gruppe "Administratoren" auf dem betroffenen Computer sein.</span><span class="sxs-lookup"><span data-stu-id="32d4b-109">To use `Clear-EventLog`, you must be a member of the Administrators group on the affected computer.</span></span>

<span data-ttu-id="32d4b-110">Die Cmdlets, die das **EventLog** -Substantiv (die EventLog-Cmdlets) enthalten, funktionieren nur in klassischen Ereignisprotokollen.</span><span class="sxs-lookup"><span data-stu-id="32d4b-110">The cmdlets that contain the **EventLog** noun (the EventLog cmdlets) work only on classic event logs.</span></span>
<span data-ttu-id="32d4b-111">Verwenden Sie das Cmdlet "Get-WinEvent", um Ereignisse aus Protokollen zu erhalten, die die Windows-Ereignisprotokoll Technologie in Windows Vista und höheren Versionen von Windows verwenden.</span><span class="sxs-lookup"><span data-stu-id="32d4b-111">To get events from logs that use the Windows Event Log technology in Windows Vista and later versions of Windows, use the Get-WinEvent cmdlet.</span></span>

## <span data-ttu-id="32d4b-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="32d4b-112">EXAMPLES</span></span>

### <span data-ttu-id="32d4b-113">Beispiel 1: Löschen bestimmter Ereignisprotokoll Typen vom lokalen Computer</span><span class="sxs-lookup"><span data-stu-id="32d4b-113">Example 1: Clear specific event log types from the local computer</span></span>

```powershell
Clear-EventLog "Windows PowerShell"
```

<span data-ttu-id="32d4b-114">Dieser Befehl löscht die Einträge aus dem Windows PowerShell-Ereignisprotokoll auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="32d4b-114">This command clears the entries from the Windows PowerShell event log on the local computer.</span></span>

### <span data-ttu-id="32d4b-115">Beispiel 2: Löschen bestimmter mehrerer Protokolltypen von lokalen Computern und Remote Computern</span><span class="sxs-lookup"><span data-stu-id="32d4b-115">Example 2: Clear specific multiple log types from the local and remote computers</span></span>

```powershell
Clear-EventLog -LogName ODiag, OSession -ComputerName localhost, Server02
```

<span data-ttu-id="32d4b-116">Mit diesem Befehl werden alle Einträge in den Protokollen Microsoft Office Diagnostics (odiag) und Microsoft Office Sitzungen (osession) auf dem lokalen Computer und auf dem Remote Computer Server02 gelöscht.</span><span class="sxs-lookup"><span data-stu-id="32d4b-116">This command clears all of the entries in the Microsoft Office Diagnostics (ODiag) and Microsoft Office Sessions (OSession) logs on the local computer and the Server02 remote computer.</span></span>

### <span data-ttu-id="32d4b-117">Beispiel 3: Löschen aller Protokolle auf den angegebenen Computern und Anzeigen der Ereignisprotokoll Liste</span><span class="sxs-lookup"><span data-stu-id="32d4b-117">Example 3: Clear all logs on the specified computers then display the event log list</span></span>

```powershell
Clear-EventLog -LogName application, system -confirm
```

<span data-ttu-id="32d4b-118">Mit diesem Befehl werden Sie zur Bestätigung aufgefordert, bevor die Einträge in den angegebenen Ereignisprotokollen gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="32d4b-118">This command prompts you for confirmation before deleting the entries in the specified event logs.</span></span>

### <span data-ttu-id="32d4b-119">Beispiel 4: Löschen aller Protokolle auf den angegebenen Computern und Anzeigen der Ereignisprotokoll Liste</span><span class="sxs-lookup"><span data-stu-id="32d4b-119">Example 4: Clear all logs on the specified computers then display the event log list</span></span>

```powershell
function clear-all-event-logs ($computerName="localhost")
{
   $logs = Get-EventLog -ComputerName $computername -List | ForEach-Object {$_.Log}
   $logs | ForEach-Object {Clear-EventLog -ComputerName $computername -LogName $_ }
   Get-EventLog -ComputerName $computername -list
}

clear-all-event-logs -ComputerName Server01
```

```Output
Max(K) Retain OverflowAction        Entries Log
------ ------ --------------        ------- ---
15,168      0 OverwriteAsNeeded           0 Application
15,168      0 OverwriteAsNeeded           0 DFS Replication
512         7 OverwriteOlder              0 DxStudio
20,480      0 OverwriteAsNeeded           0 Hardware Events
512         7 OverwriteOlder              0 Internet Explorer
20,480      0 OverwriteAsNeeded           0 Key Management Service
16,384      0 OverwriteAsNeeded           0 Microsoft Office Diagnostics
16,384      0 OverwriteAsNeeded           0 Microsoft Office Sessions
30,016      0 OverwriteAsNeeded           1 Security
15,168      0 OverwriteAsNeeded           2 System
15,360      0 OverwriteAsNeeded           0 Windows PowerShell
```

<span data-ttu-id="32d4b-120">Diese Funktion löscht alle Ereignisprotokolle auf den angegebenen Computern und zeigt dann die resultierende Ereignisprotokollliste an.</span><span class="sxs-lookup"><span data-stu-id="32d4b-120">This function clears all event logs on the specified computers and then displays the resulting event log list.</span></span>

<span data-ttu-id="32d4b-121">Beachten Sie, dass den System- und Sicherheitsprotokollen einige Einträge nach dem Löschen, aber vor dem Anzeigen der Protokolle hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="32d4b-121">Notice that a few entries were added to the System and Security logs after the logs were cleared but before they were displayed.</span></span>

## <span data-ttu-id="32d4b-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="32d4b-122">PARAMETERS</span></span>

### <span data-ttu-id="32d4b-123">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="32d4b-123">-ComputerName</span></span>

<span data-ttu-id="32d4b-124">Gibt einen Remotecomputer an.</span><span class="sxs-lookup"><span data-stu-id="32d4b-124">Specifies a remote computer.</span></span>
<span data-ttu-id="32d4b-125">Die Standardeinstellung ist der lokale Computer.</span><span class="sxs-lookup"><span data-stu-id="32d4b-125">The default is the local computer.</span></span>

<span data-ttu-id="32d4b-126">Geben Sie den NetBIOS-Namen, eine IP-Adresse oder den vollqualifizierten Domänennamen eines Remotecomputers ein.</span><span class="sxs-lookup"><span data-stu-id="32d4b-126">Type the NetBIOS name, an Internet Protocol (IP) address, or a fully qualified domain name of a remote computer.</span></span>
<span data-ttu-id="32d4b-127">Um den lokalen Computer anzugeben, geben Sie den Computernamen, einen Punkt (.) oder %%amp;quot;localhost%%amp;quot; ein.</span><span class="sxs-lookup"><span data-stu-id="32d4b-127">To specify the local computer, type the computer name, a dot (.), or "localhost".</span></span>

<span data-ttu-id="32d4b-128">Dieser Parameter beruht nicht auf Windows PowerShell-Remoting.</span><span class="sxs-lookup"><span data-stu-id="32d4b-128">This parameter does not rely on Windows PowerShell remoting.</span></span>
<span data-ttu-id="32d4b-129">Sie können den **Computername** -Parameter `Get-EventLog` auch dann verwenden, wenn der Computer nicht für das Ausführen von Remote Befehlen konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="32d4b-129">You can use the **ComputerName** parameter of `Get-EventLog` even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: 1
Default value: Local computer
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="32d4b-130">-LogName</span><span class="sxs-lookup"><span data-stu-id="32d4b-130">-LogName</span></span>

<span data-ttu-id="32d4b-131">Gibt die Ereignisprotokolle an.</span><span class="sxs-lookup"><span data-stu-id="32d4b-131">Specifies the event logs.</span></span>
<span data-ttu-id="32d4b-132">Geben Sie den Protokollnamen (den Wert der Log-Eigenschaft, nicht %%amp;quot;LogDisplayName%%amp;quot;) von Ereignisprotokollen durch Kommas getrennt ein.</span><span class="sxs-lookup"><span data-stu-id="32d4b-132">Enter the log name (the value of the Log property; not the LogDisplayName) of one or more event logs, separated by commas.</span></span>
<span data-ttu-id="32d4b-133">Platzhalterzeichen sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="32d4b-133">Wildcard characters are not permitted.</span></span>
<span data-ttu-id="32d4b-134">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="32d4b-134">This parameter is required.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: LN

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="32d4b-135">-Confirm</span><span class="sxs-lookup"><span data-stu-id="32d4b-135">-Confirm</span></span>

<span data-ttu-id="32d4b-136">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="32d4b-136">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="32d4b-137">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="32d4b-137">-WhatIf</span></span>

<span data-ttu-id="32d4b-138">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="32d4b-138">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="32d4b-139">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="32d4b-139">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="32d4b-140">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="32d4b-140">CommonParameters</span></span>

<span data-ttu-id="32d4b-141">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="32d4b-141">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="32d4b-142">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="32d4b-142">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="32d4b-143">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="32d4b-143">INPUTS</span></span>

### <span data-ttu-id="32d4b-144">Keine</span><span class="sxs-lookup"><span data-stu-id="32d4b-144">None</span></span>

<span data-ttu-id="32d4b-145">Objekte können nicht an übergeben werden `Clear-EventLog` .</span><span class="sxs-lookup"><span data-stu-id="32d4b-145">You cannot pipe objects to `Clear-EventLog`.</span></span>

## <span data-ttu-id="32d4b-146">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="32d4b-146">OUTPUTS</span></span>

### <span data-ttu-id="32d4b-147">Keine</span><span class="sxs-lookup"><span data-stu-id="32d4b-147">None</span></span>

<span data-ttu-id="32d4b-148">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="32d4b-148">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="32d4b-149">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="32d4b-149">NOTES</span></span>

- <span data-ttu-id="32d4b-150">Wenn Sie unter `Clear-EventLog` Windows Vista und höheren Versionen von Windows verwenden möchten, starten Sie Windows PowerShell mit der Option "als Administrator ausführen".</span><span class="sxs-lookup"><span data-stu-id="32d4b-150">To use `Clear-EventLog` on Windows Vista and later versions of Windows, start Windows PowerShell with the "Run as administrator" option.</span></span>

## <span data-ttu-id="32d4b-151">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="32d4b-151">RELATED LINKS</span></span>

[<span data-ttu-id="32d4b-152">Get-EventLog</span><span class="sxs-lookup"><span data-stu-id="32d4b-152">Get-EventLog</span></span>](Get-EventLog.md)

[<span data-ttu-id="32d4b-153">Limit-EventLog</span><span class="sxs-lookup"><span data-stu-id="32d4b-153">Limit-EventLog</span></span>](Limit-EventLog.md)

[<span data-ttu-id="32d4b-154">New-EventLog</span><span class="sxs-lookup"><span data-stu-id="32d4b-154">New-EventLog</span></span>](New-EventLog.md)

[<span data-ttu-id="32d4b-155">Remove-EventLog</span><span class="sxs-lookup"><span data-stu-id="32d4b-155">Remove-EventLog</span></span>](Remove-EventLog.md)

[<span data-ttu-id="32d4b-156">Show-EventLog</span><span class="sxs-lookup"><span data-stu-id="32d4b-156">Show-EventLog</span></span>](Show-EventLog.md)

[<span data-ttu-id="32d4b-157">Write-EventLog</span><span class="sxs-lookup"><span data-stu-id="32d4b-157">Write-EventLog</span></span>](Write-EventLog.md)
