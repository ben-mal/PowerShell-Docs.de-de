---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 11/06/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/connect-pssession?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Connect-PSSession
ms.openlocfilehash: 62e5081854fbef46554cafcde0b227ee49fd273e
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94391441"
---
# <span data-ttu-id="7fd73-103">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="7fd73-103">Connect-PSSession</span></span>

## <span data-ttu-id="7fd73-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="7fd73-104">SYNOPSIS</span></span>
<span data-ttu-id="7fd73-105">Stellt die Verbindung mit getrennten Sitzungen wieder her.</span><span class="sxs-lookup"><span data-stu-id="7fd73-105">Reconnects to disconnected sessions.</span></span>

## <span data-ttu-id="7fd73-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7fd73-106">SYNTAX</span></span>

### <span data-ttu-id="7fd73-107">Name (Standard)</span><span class="sxs-lookup"><span data-stu-id="7fd73-107">Name (Default)</span></span>

```
Connect-PSSession -Name <String[]> [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="7fd73-108">Sitzung</span><span class="sxs-lookup"><span data-stu-id="7fd73-108">Session</span></span>

```
Connect-PSSession [-Session] <PSSession[]> [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="7fd73-109">Computernameguid</span><span class="sxs-lookup"><span data-stu-id="7fd73-109">ComputerNameGuid</span></span>

```
Connect-PSSession -ComputerName <String[]> [-ApplicationName <String>] [-ConfigurationName <String>]
 -InstanceId <Guid[]> [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [-Port <Int32>] [-UseSSL] [-SessionOption <PSSessionOption>]
 [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="7fd73-110">Computername</span><span class="sxs-lookup"><span data-stu-id="7fd73-110">ComputerName</span></span>

```
Connect-PSSession -ComputerName <String[]> [-ApplicationName <String>] [-ConfigurationName <String>]
 [-Name <String[]>] [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [-Port <Int32>] [-UseSSL] [-SessionOption <PSSessionOption>]
 [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="7fd73-111">Connectionuriguid</span><span class="sxs-lookup"><span data-stu-id="7fd73-111">ConnectionUriGuid</span></span>

```
Connect-PSSession [-ConfigurationName <String>] [-ConnectionUri] <Uri[]> [-AllowRedirection]
 -InstanceId <Guid[]> [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [-SessionOption <PSSessionOption>] [-ThrottleLimit <Int32>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="7fd73-112">ConnectionUri</span><span class="sxs-lookup"><span data-stu-id="7fd73-112">ConnectionUri</span></span>

```
Connect-PSSession [-ConfigurationName <String>] [-ConnectionUri] <Uri[]> [-AllowRedirection] [-Name <String[]>]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [-SessionOption <PSSessionOption>] [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="7fd73-113">InstanceId</span><span class="sxs-lookup"><span data-stu-id="7fd73-113">InstanceId</span></span>

```
Connect-PSSession -InstanceId <Guid[]> [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="7fd73-114">Id</span><span class="sxs-lookup"><span data-stu-id="7fd73-114">Id</span></span>

```
Connect-PSSession [-ThrottleLimit <Int32>] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="7fd73-115">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7fd73-115">DESCRIPTION</span></span>

<span data-ttu-id="7fd73-116">Das `Connect-PSSession` Cmdlet stellt erneut eine Verbindung mit vom Benutzer verwalteten PowerShell-Sitzungen ( **pssessions** ) her, die getrennt wurden.</span><span class="sxs-lookup"><span data-stu-id="7fd73-116">The `Connect-PSSession` cmdlet reconnects to user-managed PowerShell sessions ( **PSSessions** ) that were disconnected.</span></span> <span data-ttu-id="7fd73-117">Es funktioniert für Sitzungen, die absichtlich getrennt sind, z. b. durch Verwendung des `Disconnect-PSSession` Cmdlets oder des Parameters " **indisconnectedsession** " des `Invoke-Command` Cmdlets, und von Benutzern, die versehentlich getrennt wurden, z. b. durch einen temporären Netzwerkausfall.</span><span class="sxs-lookup"><span data-stu-id="7fd73-117">It works on sessions that are disconnected intentionally, such as by using the `Disconnect-PSSession` cmdlet or the **InDisconnectedSession** parameter of the `Invoke-Command` cmdlet, and those that were disconnected unintentionally, such as by a temporary network outage.</span></span>

<span data-ttu-id="7fd73-118">`Connect-PSSession` kann eine Verbindung mit einer getrennten Sitzung herstellen, die vom gleichen Benutzer gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="7fd73-118">`Connect-PSSession` can connect to any disconnected session that was started by the same user.</span></span> <span data-ttu-id="7fd73-119">Dazu zählen diejenigen, die von anderen Sitzungen auf anderen Computern gestartet oder getrennt wurden.</span><span class="sxs-lookup"><span data-stu-id="7fd73-119">These include those that were started by or disconnected from other sessions on other computers.</span></span>

<span data-ttu-id="7fd73-120">Allerdings `Connect-PSSession` kann keine Verbindung mit unterbrochenen oder geschlossenen Sitzungen oder interaktiven Sitzungen hergestellt werden, die mithilfe des `Enter-PSSession` Cmdlets gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="7fd73-120">However, `Connect-PSSession` cannot connect to broken or closed sessions, or interactive sessions started by using the `Enter-PSSession` cmdlet.</span></span> <span data-ttu-id="7fd73-121">Sie können auch keine Sitzungen mit Sitzungen verbinden, die von anderen Benutzern gestartet wurden, es sei denn, Sie geben die Anmeldeinformationen des Benutzers an, der die Sitzung erstellt hat.</span><span class="sxs-lookup"><span data-stu-id="7fd73-121">Also you cannot connect sessions to sessions started by other users, unless you can provide the credentials of the user who created the session.</span></span>

<span data-ttu-id="7fd73-122">Weitere Informationen zum Feature „Getrennte Sitzungen“ finden Sie unter [about_Remote_Disconnected_Sessions](about/about_Remote_Disconnected_Sessions.md).</span><span class="sxs-lookup"><span data-stu-id="7fd73-122">For more information about the Disconnected Sessions feature, see [about_Remote_Disconnected_Sessions](about/about_Remote_Disconnected_Sessions.md).</span></span>

<span data-ttu-id="7fd73-123">Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="7fd73-123">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="7fd73-124">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="7fd73-124">EXAMPLES</span></span>

### <span data-ttu-id="7fd73-125">Beispiel 1: Wiederherstellen der Verbindung mit einer Sitzung</span><span class="sxs-lookup"><span data-stu-id="7fd73-125">Example 1: Reconnect to a session</span></span>

```
PS C:\> Connect-PSSession -ComputerName Server01 -Name ITTask
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 4 ITTask          Server01        Opened        ITTasks                  Available
```

<span data-ttu-id="7fd73-126">Mit diesem Befehl wird die Verbindung mit der ITTask-Sitzung auf dem Computer Server01 wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="7fd73-126">This command reconnects to the ITTask session on the Server01 computer.</span></span>

<span data-ttu-id="7fd73-127">Die Ausgabe zeigt, dass der Befehl erfolgreich ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="7fd73-127">The output shows that the command was successful.</span></span> <span data-ttu-id="7fd73-128">Der **Status** der Sitzung wird geöffnet, und die **Verfügbarkeit** ist verfügbar. Dies bedeutet, dass Sie Befehle in der Sitzung ausführen können.</span><span class="sxs-lookup"><span data-stu-id="7fd73-128">The **State** of the session is Opened and the **Availability** is Available, which indicates that you can run commands in the session.</span></span>

### <span data-ttu-id="7fd73-129">Beispiel 2: Auswirkung der Trennung und erneuten Verbindungs Herstellung</span><span class="sxs-lookup"><span data-stu-id="7fd73-129">Example 2: Effect of disconnecting and reconnecting</span></span>

```
PS C:\> Get-PSSession

Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 Backups         Localhost       Opened        Microsoft.PowerShell     Available


PS C:\> Get-PSSession | Disconnect-PSSession

Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 Backups         Localhost       Disconnected  Microsoft.PowerShell          None


PS C:\> Get-PSSession | Connect-PSSession

Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 Backups         Localhost       Opened        Microsoft.PowerShell     Available
```

<span data-ttu-id="7fd73-130">Dieses Beispiel zeigt die Auswirkungen des Trennens und Neuverbindens einer Sitzung.</span><span class="sxs-lookup"><span data-stu-id="7fd73-130">This example shows the effect of disconnecting and then reconnecting to a session.</span></span>

<span data-ttu-id="7fd73-131">Der erste Befehl verwendet das `Get-PSSession` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7fd73-131">The first command uses the `Get-PSSession` cmdlet.</span></span> <span data-ttu-id="7fd73-132">Ohne den **ComputerName** -Parameter  ruft der Befehl nur Sitzungen ab, die in der aktuellen Sitzung erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="7fd73-132">Without the **ComputerName** parameter, the command gets only sessions that were created in the current session.</span></span>

<span data-ttu-id="7fd73-133">Die Ausgabe zeigt, dass mit dem Befehl die Sitzung „Backups“ auf dem lokalen Computer abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="7fd73-133">The output shows that the command gets the Backups session on the local computer.</span></span> <span data-ttu-id="7fd73-134">Der **Status** der Sitzung wird geöffnet, und die **Verfügbarkeit** ist verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7fd73-134">The **State** of the session is Opened and the **Availability** is Available.</span></span>

<span data-ttu-id="7fd73-135">Der zweite Befehl verwendet das `Get-PSSession` Cmdlet, um die **PSSession** -Objekte abzurufen, die in der aktuellen Sitzung erstellt wurden, und das `Disconnect-PSSession` Cmdlet zum Trennen der Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="7fd73-135">The second command uses the `Get-PSSession` cmdlet to get the **PSSession** objects that were created in the current session and the `Disconnect-PSSession` cmdlet to disconnect the sessions.</span></span> <span data-ttu-id="7fd73-136">Die Ausgabe zeigt, dass, die Sitzung „Backups“ getrennt wurde.</span><span class="sxs-lookup"><span data-stu-id="7fd73-136">The output shows that the Backups session was disconnected.</span></span> <span data-ttu-id="7fd73-137">Der **Status** der Sitzung wird getrennt, und die **Verfügbarkeit** ist "None".</span><span class="sxs-lookup"><span data-stu-id="7fd73-137">The **State** of the session is Disconnected and the **Availability** is None.</span></span>

<span data-ttu-id="7fd73-138">Der dritte Befehl verwendet das `Get-PSSession` Cmdlet, um die **PSSession** -Objekte abzurufen, die in der aktuellen Sitzung erstellt wurden, und das `Connect-PSSession` Cmdlet zum erneuten Verbinden der Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="7fd73-138">The third command uses the `Get-PSSession` cmdlet to get the **PSSession** objects that were created in the current session and the `Connect-PSSession` cmdlet to reconnect the sessions.</span></span> <span data-ttu-id="7fd73-139">Die Ausgabe zeigt, dass, die Sitzung „Backups“ neu verbunden wurde.</span><span class="sxs-lookup"><span data-stu-id="7fd73-139">The output shows that the Backups session was reconnected.</span></span> <span data-ttu-id="7fd73-140">Der **Status** der Sitzung wird geöffnet, und die **Verfügbarkeit** ist verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7fd73-140">The **State** of the session is Opened and the **Availability** is Available.</span></span>

<span data-ttu-id="7fd73-141">Wenn Sie das `Connect-PSSession` Cmdlet für eine Sitzung verwenden, die nicht getrennt ist, hat der Befehl keine Auswirkungen auf die Sitzung und generiert keine Fehler.</span><span class="sxs-lookup"><span data-stu-id="7fd73-141">If you use the `Connect-PSSession` cmdlet on a session that is not disconnected, the command does not affect the session and it does not generate any errors.</span></span>

### <span data-ttu-id="7fd73-142">Beispiel 3: Reihe von Befehlen in einem Unternehmens Szenario</span><span class="sxs-lookup"><span data-stu-id="7fd73-142">Example 3: Series of commands in an enterprise scenario</span></span>

<span data-ttu-id="7fd73-143">Diese Reihe von Befehlen zeigt, wie das `Connect-PSSession` Cmdlet in einem Unternehmens Szenario verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="7fd73-143">This series of commands shows how the `Connect-PSSession` cmdlet might be used in an enterprise scenario.</span></span> <span data-ttu-id="7fd73-144">In diesem Fall startet ein Systemadministrator einen Auftrag mit langer Ausführungszeit in einer Sitzung auf einem Remotecomputer.</span><span class="sxs-lookup"><span data-stu-id="7fd73-144">In this case, a system administrator starts a long-running job in a session on a remote computer.</span></span> <span data-ttu-id="7fd73-145">Nach dem Starten des Auftrags trennt der Administrator die Verbindung mit der Sitzung und kann nach Hause gehen.</span><span class="sxs-lookup"><span data-stu-id="7fd73-145">After starting the job, the administrator disconnects from the session and goes home.</span></span>
<span data-ttu-id="7fd73-146">Später am Abend meldet sich der Administrator bei Ihrem Heimcomputer an und überprüft, ob der Auftrag ausgeführt wird, bis er abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="7fd73-146">Later that evening, the administrator logs on to her home computer and verifies that the job ran until it is completed.</span></span>

<span data-ttu-id="7fd73-147">Der Administrator erstellt zunächst eine Sitzung auf einem Remote Computer und führt ein Skript in der Sitzung aus. Der erste Befehl verwendet das `New-PSSession` Cmdlet, um die ittask-Sitzung auf dem Remote Computer Server01 zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7fd73-147">The administrator starts by creating a sessions on a remote computer and running a script in the session.The first command uses the `New-PSSession` cmdlet to create the ITTask session on the Server01 remote computer.</span></span> <span data-ttu-id="7fd73-148">Der Befehl verwendet den **ConfigurationName** -Parameter , um die Sitzungskonfiguration von ITTasks anzugeben.</span><span class="sxs-lookup"><span data-stu-id="7fd73-148">The command uses the **ConfigurationName** parameter to specify the ITTasks session configuration.</span></span> <span data-ttu-id="7fd73-149">Der Befehl speichert die Sitzungen in der `$s` Variablen.</span><span class="sxs-lookup"><span data-stu-id="7fd73-149">The command saves the sessions in the `$s` variable.</span></span>

<span data-ttu-id="7fd73-150">Das zweite Befehls- `Invoke-Command` Cmdlet zum Starten eines Hintergrund Auftrags in der Sitzung in der `$s` Variablen.</span><span class="sxs-lookup"><span data-stu-id="7fd73-150">The second command `Invoke-Command` cmdlet to start a background job in the session in the `$s` variable.</span></span> <span data-ttu-id="7fd73-151">Er verwendet den **FilePath** -Parameter, um das Skript im Hintergrundauftrag auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7fd73-151">It uses the **FilePath** parameter to run the script in the background job.</span></span>

<span data-ttu-id="7fd73-152">Der dritte Befehl verwendet das `Disconnect-PSSession` Cmdlet, um die Verbindung mit der Sitzung in der Variablen zu trennen `$s` .</span><span class="sxs-lookup"><span data-stu-id="7fd73-152">The third command uses the `Disconnect-PSSession` cmdlet to disconnect from the session in the `$s` variable.</span></span> <span data-ttu-id="7fd73-153">Der Befehl verwendet den **OutputBufferingMode** -Parameter mit dem Wert Drop, um zu verhindern, dass das Skript blockiert wird, weil es die Ausgabe an die Sitzung liefern muss.</span><span class="sxs-lookup"><span data-stu-id="7fd73-153">The command uses the **OutputBufferingMode** parameter with a value of Drop to prevent the script from being blocked by having to deliver output to the session.</span></span> <span data-ttu-id="7fd73-154">Er verwendet den **idletimeoutsec** -Parameter, um das Sitzungs Timeout auf 15 Stunden zu verlängern.</span><span class="sxs-lookup"><span data-stu-id="7fd73-154">It uses the **IdleTimeoutSec** parameter to extend the session time-out to 15 hours.</span></span> <span data-ttu-id="7fd73-155">Wenn der Befehl abgeschlossen ist, sperrt der Administrator Ihren Computer und wechselt für den Abend zu Hause.</span><span class="sxs-lookup"><span data-stu-id="7fd73-155">When the command is completed, the administrator locks her computer and goes home for the evening.</span></span>

<span data-ttu-id="7fd73-156">Zu einem späteren Zeitpunkt startet der Administrator Ihren Heimcomputer, meldet sich beim Unternehmensnetzwerk an und startet PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7fd73-156">Later that evening, the administrator starts her home computer, logs on to the corporate network, and starts PowerShell.</span></span> <span data-ttu-id="7fd73-157">Der vierte Befehl verwendet das `Get-PSSession` Cmdlet, um die Sitzungen auf dem Server01-Computer zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="7fd73-157">The fourth command uses the `Get-PSSession` cmdlet to get the sessions on the Server01 computer.</span></span> <span data-ttu-id="7fd73-158">Der Befehl findet die ittask-Sitzung. Der fünfte Befehl verwendet das `Connect-PSSession` Cmdlet, um eine Verbindung mit der ittask-Sitzung herzustellen.</span><span class="sxs-lookup"><span data-stu-id="7fd73-158">The command finds the ITTask session.The fifth command uses the `Connect-PSSession` cmdlet to connect to the ITTask session.</span></span> <span data-ttu-id="7fd73-159">Der Befehl speichert die Sitzung in der Variablen `$s`.</span><span class="sxs-lookup"><span data-stu-id="7fd73-159">The command saves the session in the `$s` variable.</span></span>

<span data-ttu-id="7fd73-160">Der sechste Befehl verwendet das `Invoke-Command` Cmdlet, um einen `Get-Job` Befehl in der Sitzung in der `$s` Variablen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7fd73-160">The sixth command uses the `Invoke-Command` cmdlet to run a `Get-Job` command in the session in the `$s` variable.</span></span> <span data-ttu-id="7fd73-161">Die Ausgabe zeigt, dass der Auftrag erfolgreich abgeschlossen wurde. Der siebte Befehl verwendet das `Invoke-Command` Cmdlet, um einen Befehl in der Sitzung in der- `Receive-Job` `$s` Variable in der Sitzung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7fd73-161">The output shows that the job finished successfully.The seventh command uses the `Invoke-Command` cmdlet to run a `Receive-Job` command in the session in the `$s` variable in the session.</span></span> <span data-ttu-id="7fd73-162">Der Befehl speichert die Ergebnisse in der `$BackupSpecs` Variablen. Der achte Befehl verwendet das `Invoke-Command` Cmdlet zum Ausführen eines weiteren Skripts in der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="7fd73-162">The command saves the results in the `$BackupSpecs` variable.The eighth command uses the `Invoke-Command` cmdlet to runs another script in the session.</span></span> <span data-ttu-id="7fd73-163">Der Befehl verwendet den Wert der `$BackupSpecs` Variablen in der Sitzung als Eingabe für das Skript.</span><span class="sxs-lookup"><span data-stu-id="7fd73-163">The command uses the value of the `$BackupSpecs` variable in the session as input to the script.</span></span>

```
PS C:\> $s = New-PSSession -ComputerName Server01 -Name ITTask -ConfigurationName ITTasks
PS C:\> Invoke-Command -Session $s {Start-Job -FilePath \\Server30\Scripts\Backup-SQLDatabase.ps1}

Id     Name            State         HasMoreData     Location             Command
--     ----            -----         -----------     --------             -------
2      Job2            Running       True            Server01             \\Server30\Scripts\Backup...

PS C:\> Disconnect-PSSession -Session $s -OutputBufferingMode Drop -IdleTimeoutSec 60*60*15

Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Server01        Disconnected  ITTasks               None

PS C:\> Get-PSSession -ComputerName Server01 -Name ITTask

Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Server01        Disconnected  ITTasks               None


PS C:\> $s = Connect-PSSession -ComputerName Server01 -Name ITTask


Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Server01        Opened        ITTasks               Available

PS C:\> Invoke-Command -Session $s {Get-Job}

Id     Name            State         HasMoreData     Location             Command
--     ----            -----         -----------     --------             -------
2      Job2            Completed     True            Server01             \\Server30\Scripts\Backup...

PS C:\> Invoke-Command -Session $s {$BackupSpecs = Receive-Job -JobName Job2}

PS C:\> Invoke-Command -Session $s {\\Server30\Scripts\New-SQLDatabase.ps1 -InitData $BackupSpecs.Initialization}

PS C:\> Disconnect-PSSession -Session $s -OutputBufferingMode Drop -IdleTimeoutSec 60*60*15
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Server01        Disconnected  ITTasks               None
```

<span data-ttu-id="7fd73-164">Der neunte Befehl trennt die Verbindung mit der Sitzung in der `$s` Variablen. Der Administrator schließt PowerShell und schließt den Computer.</span><span class="sxs-lookup"><span data-stu-id="7fd73-164">The ninth command disconnects from the session in the `$s` variable.The administrator closes PowerShell and closes the computer.</span></span> <span data-ttu-id="7fd73-165">Am nächsten Tag kann er die Sitzung neu verbinden und den Skriptstatus auf dem Computer am Arbeitsplatz überprüfen.</span><span class="sxs-lookup"><span data-stu-id="7fd73-165">She can reconnect to the session on the next day and check the script status from her work computer.</span></span>

## <span data-ttu-id="7fd73-166">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7fd73-166">PARAMETERS</span></span>

### <span data-ttu-id="7fd73-167">-Zuweisung Richtung</span><span class="sxs-lookup"><span data-stu-id="7fd73-167">-AllowRedirection</span></span>

<span data-ttu-id="7fd73-168">Gibt an, dass dieses Cmdlet die Umleitung dieser Verbindung an einen alternativen URI zulässt.</span><span class="sxs-lookup"><span data-stu-id="7fd73-168">Indicates that this cmdlet allows redirection of this connection to an alternate URI.</span></span>

<span data-ttu-id="7fd73-169">Bei Verwendung des **ConnectionURI** -Parameters kann das Remoteziel eine Anweisung zum Umleiten an einen anderen URI zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="7fd73-169">When you use the **ConnectionURI** parameter, the remote destination can return an instruction to redirect to a different URI.</span></span> <span data-ttu-id="7fd73-170">Standardmäßig werden Verbindungen von PowerShell nicht umgeleitet, aber Sie können diesen Parameter verwenden, um die Umleitung der Verbindung zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="7fd73-170">By default, PowerShell does not redirect connections, but you can use this parameter to allow it to redirect the connection.</span></span>

<span data-ttu-id="7fd73-171">Sie können auch einschränken, wie oft die Verbindung umgeleitet wird, indem Sie den **MaximumConnectionRedirectionCount** -Optionswert der Sitzung ändern.</span><span class="sxs-lookup"><span data-stu-id="7fd73-171">You can also limit the number of times the connection is redirected by changing the **MaximumConnectionRedirectionCount** session option value.</span></span> <span data-ttu-id="7fd73-172">Verwenden Sie den **maximumredirect** -Parameter des `New-PSSessionOption` Cmdlets, oder legen Sie die **maximumconnectionredirectioncount** -Eigenschaft der **$PSSessionOption** Preference-Variablen fest.</span><span class="sxs-lookup"><span data-stu-id="7fd73-172">Use the **MaximumRedirection** parameter of the `New-PSSessionOption` cmdlet or set the **MaximumConnectionRedirectionCount** property of the **$PSSessionOption** preference variable.</span></span> <span data-ttu-id="7fd73-173">Der Standardwert ist 5.</span><span class="sxs-lookup"><span data-stu-id="7fd73-173">The default value is 5.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ConnectionUriGuid, ConnectionUri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7fd73-174">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="7fd73-174">-ApplicationName</span></span>

<span data-ttu-id="7fd73-175">Gibt den Namen einer Anwendung an.</span><span class="sxs-lookup"><span data-stu-id="7fd73-175">Specifies the name of an application.</span></span> <span data-ttu-id="7fd73-176">Dieses Cmdlet stellt nur Verbindungen mit Sitzungen her, die die angegebene Anwendung verwenden.</span><span class="sxs-lookup"><span data-stu-id="7fd73-176">This cmdlet connects only to sessions that use the specified application.</span></span>

<span data-ttu-id="7fd73-177">Geben Sie das Anwendungsnamensegment des Verbindungs-URI ein.</span><span class="sxs-lookup"><span data-stu-id="7fd73-177">Enter the application name segment of the connection URI.</span></span> <span data-ttu-id="7fd73-178">Im folgenden Verbindungs-URI lautet der Anwendungsname beispielsweise WSMAN: `http://localhost:5985/WSMAN` .</span><span class="sxs-lookup"><span data-stu-id="7fd73-178">For example, in the following connection URI, the application name is WSMan: `http://localhost:5985/WSMAN`.</span></span> <span data-ttu-id="7fd73-179">Der Anwendungsname einer Sitzung wird in der **Runspace.ConnectionInfo.AppName** -Eigenschaft der Sitzung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="7fd73-179">The application name of a session is stored in the **Runspace.ConnectionInfo.AppName** property of the session.</span></span>

<span data-ttu-id="7fd73-180">Der Wert dieses Parameters wird verwendet, um Sitzungen auszuwählen und zu filtern.</span><span class="sxs-lookup"><span data-stu-id="7fd73-180">The value of this parameter is used to select and filter sessions.</span></span> <span data-ttu-id="7fd73-181">Er ändert nicht die von der Sitzung verwendete Anwendung.</span><span class="sxs-lookup"><span data-stu-id="7fd73-181">It does not change the application that the session uses.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerNameGuid, ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="7fd73-182">-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="7fd73-182">-Authentication</span></span>

<span data-ttu-id="7fd73-183">Gibt den Mechanismus an, der zum Authentifizieren der Benutzer Anmelde Informationen im Befehl verwendet wird, um die Verbindung mit der getrennten Sitzung wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="7fd73-183">Specifies the mechanism that is used to authenticate user credentials in the command to reconnect to the disconnected session.</span></span> <span data-ttu-id="7fd73-184">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="7fd73-184">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="7fd73-185">Standard</span><span class="sxs-lookup"><span data-stu-id="7fd73-185">Default</span></span>
- <span data-ttu-id="7fd73-186">Standard</span><span class="sxs-lookup"><span data-stu-id="7fd73-186">Basic</span></span>
- <span data-ttu-id="7fd73-187">CredSSP</span><span class="sxs-lookup"><span data-stu-id="7fd73-187">Credssp</span></span>
- <span data-ttu-id="7fd73-188">Digest</span><span class="sxs-lookup"><span data-stu-id="7fd73-188">Digest</span></span>
- <span data-ttu-id="7fd73-189">Kerberos</span><span class="sxs-lookup"><span data-stu-id="7fd73-189">Kerberos</span></span>
- <span data-ttu-id="7fd73-190">Aushandeln</span><span class="sxs-lookup"><span data-stu-id="7fd73-190">Negotiate</span></span>
- <span data-ttu-id="7fd73-191">NegotiateWithImplicitCredential</span><span class="sxs-lookup"><span data-stu-id="7fd73-191">NegotiateWithImplicitCredential</span></span>

<span data-ttu-id="7fd73-192">Der Standardwert ist Default.</span><span class="sxs-lookup"><span data-stu-id="7fd73-192">The default value is Default.</span></span>

<span data-ttu-id="7fd73-193">Weitere Informationen zu den Werten dieses Parameters finden Sie unter [authenticationmechanism-Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span><span class="sxs-lookup"><span data-stu-id="7fd73-193">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!CAUTION]
> <span data-ttu-id="7fd73-194">Die CredSSP (Credential Security Support Provider)-Authentifizierung, bei der die Anmeldeinformationen des Benutzers zur Authentifizierung an einen Remotecomputer übergeben werden, ist für Befehle konzipiert, die die Authentifizierung auf mehr als einer Ressource erfordern, z. B. beim Zugriff auf eine Remotenetzwerkfreigabe.</span><span class="sxs-lookup"><span data-stu-id="7fd73-194">Credential Security Support Provider (CredSSP) authentication, in which the user's credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="7fd73-195">Dieser Mechanismus erhöht das Sicherheitsrisiko des Remotevorgangs.</span><span class="sxs-lookup"><span data-stu-id="7fd73-195">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="7fd73-196">Wenn die Sicherheit des Remotecomputers gefährdet ist, können die an ihn übergebenen Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7fd73-196">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: ComputerNameGuid, ComputerName, ConnectionUriGuid, ConnectionUri
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7fd73-197">-Certifiupethumschlag-Print</span><span class="sxs-lookup"><span data-stu-id="7fd73-197">-CertificateThumbprint</span></span>

<span data-ttu-id="7fd73-198">Gibt das digitale Zertifikat für öffentliche Schlüssel (X.509) eines Benutzerkontos mit der Berechtigung zum Herstellen einer Verbindung mit der getrennten Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="7fd73-198">Specifies the digital public key certificate (X509) of a user account that has permission to connect to the disconnected session.</span></span> <span data-ttu-id="7fd73-199">Geben Sie den Zertifikatfingerabdruck des Zertifikats ein.</span><span class="sxs-lookup"><span data-stu-id="7fd73-199">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="7fd73-200">Zertifikate werden bei der clientzertifikatbasierten Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="7fd73-200">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="7fd73-201">Sie können nur lokalen Benutzerkonten zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="7fd73-201">They can be mapped only to local user accounts.</span></span> <span data-ttu-id="7fd73-202">Sie funktionieren nicht mit Domänen Konten.</span><span class="sxs-lookup"><span data-stu-id="7fd73-202">They do not work with domain accounts.</span></span>

<span data-ttu-id="7fd73-203">Um einen Zertifikat Fingerabdruck abzurufen, verwenden Sie einen- `Get-Item` `Get-ChildItem` Befehl oder den-Befehl im PowerShell-Laufwerk "CERT:".</span><span class="sxs-lookup"><span data-stu-id="7fd73-203">To get a certificate thumbprint, use a `Get-Item` or `Get-ChildItem` command in the PowerShell Cert: drive.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerNameGuid, ComputerName, ConnectionUriGuid, ConnectionUri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7fd73-204">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="7fd73-204">-ComputerName</span></span>

<span data-ttu-id="7fd73-205">Gibt die Computer an, auf denen die Sitzungen gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="7fd73-205">Specifies the computers on which the disconnected sessions are stored.</span></span> <span data-ttu-id="7fd73-206">Sitzungen werden auf dem Server gespeichert, der sich auf dem Server oder am Ende einer Verbindung befindet.</span><span class="sxs-lookup"><span data-stu-id="7fd73-206">Sessions are stored on the computer that is at the server-side or receiving end of a connection.</span></span> <span data-ttu-id="7fd73-207">Die Standardeinstellung ist der lokale Computer.</span><span class="sxs-lookup"><span data-stu-id="7fd73-207">The default is the local computer.</span></span>

<span data-ttu-id="7fd73-208">Geben Sie den NetBIOS-Namen, eine IP-Adresse oder einen vollqualifizierten Domänennamen eines Computers ein.</span><span class="sxs-lookup"><span data-stu-id="7fd73-208">Type the NetBIOS name, an IP address, or a fully qualified domain name of one computer.</span></span> <span data-ttu-id="7fd73-209">Platzhalterzeichen sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="7fd73-209">Wildcard characters are not permitted.</span></span> <span data-ttu-id="7fd73-210">Um den lokalen Computer anzugeben, geben Sie den Computernamen, "localhost" oder einen Punkt (.) ein.</span><span class="sxs-lookup"><span data-stu-id="7fd73-210">To specify the local computer, type the computer name, localhost, or a dot (.)</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerNameGuid, ComputerName
Aliases: Cn

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7fd73-211">-ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="7fd73-211">-ConfigurationName</span></span>

<span data-ttu-id="7fd73-212">Stellt nur eine Verbindung mit Sitzungen her, die die angegebene Sitzungskonfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="7fd73-212">Connects only to sessions that use the specified session configuration.</span></span>

<span data-ttu-id="7fd73-213">Geben Sie einen Konfigurationsnamen oder den vollqualifizierten Ressourcen-URI für eine Sitzungskonfiguration ein.</span><span class="sxs-lookup"><span data-stu-id="7fd73-213">Enter a configuration name or the fully qualified resource URI for a session configuration.</span></span> <span data-ttu-id="7fd73-214">Wenn Sie nur den Konfigurations Namen angeben, wird der folgende Schema-URI vorangestellt: `http://schemas.microsoft.com/powershell` .</span><span class="sxs-lookup"><span data-stu-id="7fd73-214">If you specify only the configuration name, the following schema URI is prepended: `http://schemas.microsoft.com/powershell`.</span></span> <span data-ttu-id="7fd73-215">Der Konfigurationsname einer Sitzung befindet sich in der **ConfigurationName** -Eigenschaft der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="7fd73-215">The configuration name of a session is stored in the **ConfigurationName** property of the session.</span></span>

<span data-ttu-id="7fd73-216">Der Wert dieses Parameters wird verwendet, um Sitzungen auszuwählen und zu filtern.</span><span class="sxs-lookup"><span data-stu-id="7fd73-216">The value of this parameter is used to select and filter sessions.</span></span> <span data-ttu-id="7fd73-217">Er ändert nicht die von der Sitzung verwendete Sitzungskonfiguration.</span><span class="sxs-lookup"><span data-stu-id="7fd73-217">It does not change the session configuration that the session uses.</span></span>

<span data-ttu-id="7fd73-218">Weitere Informationen zu Sitzungs Konfigurationen finden Sie unter [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="7fd73-218">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerNameGuid, ComputerName, ConnectionUriGuid, ConnectionUri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="7fd73-219">-ConnectionUri</span><span class="sxs-lookup"><span data-stu-id="7fd73-219">-ConnectionUri</span></span>

<span data-ttu-id="7fd73-220">Gibt die URIs der Verbindungs Endpunkte für die getrennten Sitzungen an.</span><span class="sxs-lookup"><span data-stu-id="7fd73-220">Specifies the URIs of the connection endpoints for the disconnected sessions.</span></span>

<span data-ttu-id="7fd73-221">Der URI muss vollqualifiziert sein.</span><span class="sxs-lookup"><span data-stu-id="7fd73-221">The URI must be fully qualified.</span></span> <span data-ttu-id="7fd73-222">Das Format dieser Zeichenfolge lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="7fd73-222">The format of this string is as follows:</span></span>

`<Transport>://<ComputerName>:<Port>/<ApplicationName>`

<span data-ttu-id="7fd73-223">Der Standardwert lautet:</span><span class="sxs-lookup"><span data-stu-id="7fd73-223">The default value is as follows:</span></span>

`http://localhost:5985/WSMAN`

<span data-ttu-id="7fd73-224">Wenn Sie keinen Verbindungs-URI angeben, können Sie die Parameter " **US** " und " **Port** " verwenden, um die Verbindungs-URI-Werte anzugeben.</span><span class="sxs-lookup"><span data-stu-id="7fd73-224">If you do not specify a connection URI, you can use the **UseSSL** and **Port** parameters to specify the connection URI values.</span></span>

<span data-ttu-id="7fd73-225">Gültige Werte für das **Transport** -Segment des URI sind „HTTP“ und „HTTPS“.</span><span class="sxs-lookup"><span data-stu-id="7fd73-225">Valid values for the **Transport** segment of the URI are HTTP and HTTPS.</span></span> <span data-ttu-id="7fd73-226">Wenn Sie einen Verbindungs-URI mit einem Transport Segment angeben, aber keinen Port angeben, wird die Sitzung mit Standardports erstellt: 80 für http und 443 für HTTPS.</span><span class="sxs-lookup"><span data-stu-id="7fd73-226">If you specify a connection URI with a Transport segment, but do not specify a port, the session is created with standards ports: 80 for HTTP and 443 for HTTPS.</span></span> <span data-ttu-id="7fd73-227">Wenn Sie die Standardports für PowerShell-Remoting verwenden möchten, geben Sie Port 5985 für http oder 5986 für HTTPS an.</span><span class="sxs-lookup"><span data-stu-id="7fd73-227">To use the default ports for PowerShell remoting, specify port 5985 for HTTP or 5986 for HTTPS.</span></span>

<span data-ttu-id="7fd73-228">Wenn der Zielcomputer die Verbindung an einen anderen URI umleitet, verhindert PowerShell die Umleitung, es sei denn, Sie verwenden den Parameter " **Zuweisung** " im Befehl.</span><span class="sxs-lookup"><span data-stu-id="7fd73-228">If the destination computer redirects the connection to a different URI, PowerShell prevents the redirection unless you use the **AllowRedirection** parameter in the command.</span></span>

```yaml
Type: System.Uri[]
Parameter Sets: ConnectionUriGuid, ConnectionUri
Aliases: URI, CU

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="7fd73-229">-Credential</span><span class="sxs-lookup"><span data-stu-id="7fd73-229">-Credential</span></span>

<span data-ttu-id="7fd73-230">Gibt ein Benutzerkonto mit der Berechtigung zum Herstellen einer Verbindung mit der getrennten Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="7fd73-230">Specifies a user account that has permission to connect to the disconnected session.</span></span> <span data-ttu-id="7fd73-231">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="7fd73-231">The default is the current user.</span></span>

<span data-ttu-id="7fd73-232">Geben Sie einen Benutzernamen ein, z. b. `User01` oder `Domain01\User01` , oder geben Sie ein `PSCredential` vom Cmdlet generiertes-Objekt ein `Get-Credential` .</span><span class="sxs-lookup"><span data-stu-id="7fd73-232">Type a user name, such as `User01` or `Domain01\User01`, or enter a `PSCredential` object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="7fd73-233">Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe des Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="7fd73-233">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="7fd73-234">Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.</span><span class="sxs-lookup"><span data-stu-id="7fd73-234">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="7fd73-235">Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="7fd73-235">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerNameGuid, ComputerName, ConnectionUriGuid, ConnectionUri
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7fd73-236">-Id</span><span class="sxs-lookup"><span data-stu-id="7fd73-236">-Id</span></span>

<span data-ttu-id="7fd73-237">Gibt die IDs der getrennten Sitzungen an.</span><span class="sxs-lookup"><span data-stu-id="7fd73-237">Specifies the IDs of the disconnected sessions.</span></span> <span data-ttu-id="7fd73-238">Der **ID** -Parameter funktioniert nur, wenn die getrennte Sitzung zuvor mit der aktuellen Sitzung verbunden war.</span><span class="sxs-lookup"><span data-stu-id="7fd73-238">The **Id** parameter works only when the disconnected session was previously connected to the current session.</span></span>

<span data-ttu-id="7fd73-239">Dieser Parameter ist gültig, aber nicht wirksam, wenn die Sitzung auf dem lokalen Computer gespeichert ist, aber nicht mit der aktuellen Sitzung verbunden wurde.</span><span class="sxs-lookup"><span data-stu-id="7fd73-239">This parameter is valid, but not effective, when the session is stored on the local computer, but was not connected to the current session.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="7fd73-240">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="7fd73-240">-InstanceId</span></span>

<span data-ttu-id="7fd73-241">Gibt die Instanz-IDs von getrennten Sitzungen an.</span><span class="sxs-lookup"><span data-stu-id="7fd73-241">Specifies the instance IDs of the disconnected sessions.</span></span>

<span data-ttu-id="7fd73-242">Die Instanz-ID ist eine GUID, die eine **PSSession** auf einem lokalen Computer oder einem Remote Computer eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="7fd73-242">The instance ID is a GUID that uniquely identifies a **PSSession** on a local or remote computer.</span></span>

<span data-ttu-id="7fd73-243">Die Instanz-ID wird in der **InstanceId-** Eigenschaft der **PSSession** gespeichert.</span><span class="sxs-lookup"><span data-stu-id="7fd73-243">The instance ID is stored in the **InstanceID** property of the **PSSession**.</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: ComputerNameGuid, ConnectionUriGuid, InstanceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7fd73-244">-Name</span><span class="sxs-lookup"><span data-stu-id="7fd73-244">-Name</span></span>

<span data-ttu-id="7fd73-245">Gibt die Anzeigenamen von getrennten Sitzungen an.</span><span class="sxs-lookup"><span data-stu-id="7fd73-245">Specifies the friendly names of the disconnected sessions.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name, ComputerName, ConnectionUri
Aliases:

Required: True (Name), False (ComputerName, ConnectionUri)
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7fd73-246">-Port</span><span class="sxs-lookup"><span data-stu-id="7fd73-246">-Port</span></span>

<span data-ttu-id="7fd73-247">Gibt den Netzwerkport auf dem Remotecomputer an, der für die Verbindungswiederherstellung mit der Sitzung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7fd73-247">Specifies the network port on the remote computer that is used to reconnect to the session.</span></span> <span data-ttu-id="7fd73-248">Zum Herstellen einer Verbindung mit einem Remotecomputer muss der Remotecomputer den für die Verbindung verwendeten Port abhören.</span><span class="sxs-lookup"><span data-stu-id="7fd73-248">To connect to a remote computer, the remote computer must be listening on the port that the connection uses.</span></span> <span data-ttu-id="7fd73-249">Die Standardports sind 5985. Dies ist der WinRM-Port für http und 5986 (der WinRM-Port für HTTPS).</span><span class="sxs-lookup"><span data-stu-id="7fd73-249">The default ports are 5985, which is the WinRM port for HTTP, and 5986, which is the WinRM port for HTTPS.</span></span>

<span data-ttu-id="7fd73-250">Bevor ein alternativer Port verwendet werden kann, müssen Sie den WinRM-Listener auf dem Remotecomputer für das Abhören an diesen Port konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="7fd73-250">Before using an alternate port, you must configure the WinRM listener on the remote computer to listen at that port.</span></span> <span data-ttu-id="7fd73-251">Um den Listener zu konfigurieren, geben Sie die folgenden beiden Befehle an der PowerShell-Eingabeaufforderung ein:</span><span class="sxs-lookup"><span data-stu-id="7fd73-251">To configure the listener, type the following two commands at the PowerShell prompt:</span></span>

`Remove-Item -Path WSMan:\Localhost\listener\listener* -Recurse`

`New-Item -Path WSMan:\Localhost\listener -Transport http -Address * -Port \<port-number\>`

<span data-ttu-id="7fd73-252">Verwenden Sie den **Port** -Parameter nur, wenn es unbedingt notwendig ist.</span><span class="sxs-lookup"><span data-stu-id="7fd73-252">Do not use the **Port** parameter unless you must.</span></span> <span data-ttu-id="7fd73-253">Der im Befehl festgelegte Port gilt für alle Computer oder Sitzungen, für die der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7fd73-253">The port that is set in the command applies to all computers or sessions on which the command runs.</span></span> <span data-ttu-id="7fd73-254">Eine alternative Porteinstellung kann verhindern, dass der Befehl auf allen Computern ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7fd73-254">An alternate port setting might prevent the command from running on all computers.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ComputerNameGuid, ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7fd73-255">-Sitzung</span><span class="sxs-lookup"><span data-stu-id="7fd73-255">-Session</span></span>

<span data-ttu-id="7fd73-256">Gibt die getrennten Sitzungen an.</span><span class="sxs-lookup"><span data-stu-id="7fd73-256">Specifies the disconnected sessions.</span></span> <span data-ttu-id="7fd73-257">Geben Sie eine Variable ein, die die **PSSession** -Objekte enthält, oder einen Befehl, der die **PSSession** -Objekte erstellt oder abruft, z `Get-PSSession` . b. einen Befehl.</span><span class="sxs-lookup"><span data-stu-id="7fd73-257">Enter a variable that contains the **PSSession** objects or a command that creates or gets the **PSSession** objects, such as a `Get-PSSession` command.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession[]
Parameter Sets: Session
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="7fd73-258">-Sessionoption</span><span class="sxs-lookup"><span data-stu-id="7fd73-258">-SessionOption</span></span>

<span data-ttu-id="7fd73-259">Gibt erweiterte Optionen für die Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="7fd73-259">Specifies advanced options for the session.</span></span> <span data-ttu-id="7fd73-260">Geben Sie ein **sessionoption** -Objekt ein, z. b. ein Objekt, das Sie mit dem `New-PSSessionOption` Cmdlet erstellen, oder eine Hash Tabelle, in der die Schlüssel Sitzungs Optionsnamen und die Werte Sitzungs Optionswerte sind.</span><span class="sxs-lookup"><span data-stu-id="7fd73-260">Enter a **SessionOption** object, such as one that you create by using the `New-PSSessionOption` cmdlet, or a hash table in which the keys are session option names and the values are session option values.</span></span>

<span data-ttu-id="7fd73-261">Die Standardwerte für die Optionen werden durch den Wert der Einstellungs `$PSSessionOption` Variablen bestimmt, sofern festgelegt.</span><span class="sxs-lookup"><span data-stu-id="7fd73-261">The default values for the options are determined by the value of the `$PSSessionOption` preference variable, if it is set.</span></span> <span data-ttu-id="7fd73-262">Andernfalls werden die Standardwerte durch Optionen festgelegt, die in der Sitzungskonfiguration festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="7fd73-262">Otherwise, the default values are established by options set in the session configuration.</span></span>

<span data-ttu-id="7fd73-263">Die Sitzungs Optionswerte haben Vorrang vor Standardwerten für Sitzungen, die in der `$PSSessionOption` Preference-Variablen und in der Sitzungs Konfiguration festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="7fd73-263">The session option values take precedence over default values for sessions set in the `$PSSessionOption` preference variable and in the session configuration.</span></span> <span data-ttu-id="7fd73-264">Allerdings haben sie nicht Vorrang vor Höchstwerten, Kontingenten oder Grenzwerten, die in der Sitzungskonfiguration festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="7fd73-264">However, they do not take precedence over maximum values, quotas or limits set in the session configuration.</span></span>

<span data-ttu-id="7fd73-265">Eine Beschreibung der Sitzungs Optionen, die die Standardwerte enthalten, finden Sie unter `New-PSSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="7fd73-265">For a description of the session options that includes the default values, see `New-PSSessionOption`.</span></span> <span data-ttu-id="7fd73-266">Weitere Informationen zur **$PSSessionOption** Preference-Variablen finden Sie unter [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="7fd73-266">For information about the **$PSSessionOption** preference variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span> <span data-ttu-id="7fd73-267">Weitere Informationen zu Sitzungs Konfigurationen finden Sie unter [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="7fd73-267">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

```yaml
Type: System.Management.Automation.Remoting.PSSessionOption
Parameter Sets: ComputerNameGuid, ComputerName, ConnectionUriGuid, ConnectionUri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7fd73-268">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="7fd73-268">-ThrottleLimit</span></span>

<span data-ttu-id="7fd73-269">Gibt die maximale Anzahl von gleichzeitigen Verbindungen an, die zum Ausführen dieses Befehls hergestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="7fd73-269">Specifies the maximum number of concurrent connections that can be established to run this command.</span></span>
<span data-ttu-id="7fd73-270">Wenn Sie diesen Parameter weglassen oder den Wert %%amp;quot;0%%amp;quot; eingeben, wird der Standardwert %%amp;quot;32%%amp;quot; verwendet.</span><span class="sxs-lookup"><span data-stu-id="7fd73-270">If you omit this parameter or enter a value of 0, the default value, 32, is used.</span></span>

<span data-ttu-id="7fd73-271">Die Drosselungsgrenze gilt nur für den aktuellen Befehl und nicht für die Sitzung oder den Computer.</span><span class="sxs-lookup"><span data-stu-id="7fd73-271">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7fd73-272">-US-</span><span class="sxs-lookup"><span data-stu-id="7fd73-272">-UseSSL</span></span>

<span data-ttu-id="7fd73-273">Gibt an, dass dieses Cmdlet das Secure Sockets Layer (SSL)-Protokoll zum Herstellen einer Verbindung mit der getrennten Sitzung verwendet.</span><span class="sxs-lookup"><span data-stu-id="7fd73-273">Indicates that this cmdlet uses the Secure Sockets Layer (SSL) protocol to connect to the disconnected session.</span></span> <span data-ttu-id="7fd73-274">Standardmäßig wird SSL nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="7fd73-274">By default, SSL is not used.</span></span>

<span data-ttu-id="7fd73-275">WS-Management verschlüsselt alle über das Netzwerk übertragenen PowerShell-Inhalte.</span><span class="sxs-lookup"><span data-stu-id="7fd73-275">WS-Management encrypts all PowerShell content transmitted over the network.</span></span> <span data-ttu-id="7fd73-276">Der Parameter " **eessl** " ist ein zusätzlicher Schutz, der die Daten über eine HTTPS-Verbindung anstelle einer HTTP-Verbindung sendet.</span><span class="sxs-lookup"><span data-stu-id="7fd73-276">The **UseSSL** parameter is an additional protection that sends the data across an HTTPS connection instead of an HTTP connection.</span></span>

<span data-ttu-id="7fd73-277">Wenn Sie diesen Parameter verwenden, aber SSL auf dem Port, der für den Befehl verwendet wird, nicht verfügbar ist, schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="7fd73-277">If you use this parameter, but SSL is not available on the port that is used for the command, the command fails.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerNameGuid, ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7fd73-278">-Confirm</span><span class="sxs-lookup"><span data-stu-id="7fd73-278">-Confirm</span></span>

<span data-ttu-id="7fd73-279">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="7fd73-279">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="7fd73-280">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="7fd73-280">-WhatIf</span></span>

<span data-ttu-id="7fd73-281">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7fd73-281">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="7fd73-282">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7fd73-282">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="7fd73-283">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="7fd73-283">CommonParameters</span></span>

<span data-ttu-id="7fd73-284">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="7fd73-284">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7fd73-285">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="7fd73-285">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7fd73-286">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="7fd73-286">INPUTS</span></span>

### <span data-ttu-id="7fd73-287">System. Management. Automation. Runspaces. PSSession</span><span class="sxs-lookup"><span data-stu-id="7fd73-287">System.Management.Automation.Runspaces.PSSession</span></span>

<span data-ttu-id="7fd73-288">Sie können eine Sitzung ( **PSSession** ) über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="7fd73-288">You can pipe a session ( **PSSession** ) to this cmdlet.</span></span>

## <span data-ttu-id="7fd73-289">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="7fd73-289">OUTPUTS</span></span>

### <span data-ttu-id="7fd73-290">System. Management. Automation. Runspaces. PSSession</span><span class="sxs-lookup"><span data-stu-id="7fd73-290">System.Management.Automation.Runspaces.PSSession</span></span>

<span data-ttu-id="7fd73-291">Dieses Cmdlet gibt ein Objekt zurück, das die Sitzung darstellt, mit der die Verbindung wieder hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="7fd73-291">This cmdlet returns an object that represents the session to which it reconnected.</span></span>

## <span data-ttu-id="7fd73-292">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="7fd73-292">NOTES</span></span>

- <span data-ttu-id="7fd73-293">Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7fd73-293">This cmdlet is only available on Windows platforms.</span></span>

- <span data-ttu-id="7fd73-294">`Connect-PSSession` stellt nur eine Verbindung mit Sitzungen her, die getrennt sind, d. h. Sitzungen, deren Wert für die **State** -Eigenschaft getrennt ist.</span><span class="sxs-lookup"><span data-stu-id="7fd73-294">`Connect-PSSession` reconnects only to sessions that are disconnected, that is, sessions that have a value of Disconnected for the **State** property.</span></span> <span data-ttu-id="7fd73-295">Nur Sitzungen, die mit einem Computer verbunden sind, auf dem Windows PowerShell 3,0 oder höhere Versionen ausgeführt werden, können getrennt und wieder verbunden werden.</span><span class="sxs-lookup"><span data-stu-id="7fd73-295">Only sessions that are connected to, or end at, computers that run Windows PowerShell 3.0 or later versions can be disconnected and reconnected.</span></span>

- <span data-ttu-id="7fd73-296">Wenn Sie `Connect-PSSession` in einer Sitzung verwenden, die nicht getrennt ist, hat der Befehl keine Auswirkungen auf die Sitzung und generiert keine Fehler.</span><span class="sxs-lookup"><span data-stu-id="7fd73-296">If you use `Connect-PSSession` on a session that is not disconnected, the command does not affect the session and it does not generate errors.</span></span>

- <span data-ttu-id="7fd73-297">Getrennte Loopback Sitzungen mit interaktiven Tokens, die mit dem **enablenetworkaccess** -Parameter erstellt werden, können nur von dem Computer wieder hergestellt werden, auf dem die Sitzung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="7fd73-297">Disconnected loopback sessions with interactive tokens, which are created by using the **EnableNetworkAccess** parameter, can be reconnected only from the computer on which the session was created.</span></span> <span data-ttu-id="7fd73-298">Diese Einschränkung schützt den Computer vor böswilligem Zugriff.</span><span class="sxs-lookup"><span data-stu-id="7fd73-298">This restriction protects the computer from malicious access.</span></span>

- <span data-ttu-id="7fd73-299">Der Wert der **State** -Eigenschaft einer **PSSession** ist relativ zur aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="7fd73-299">The value of the **State** property of a **PSSession** is relative to the current session.</span></span>
  <span data-ttu-id="7fd73-300">Daher bedeutet der Wert " **getrennt** ", dass die **PSSession** nicht mit der aktuellen Sitzung verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="7fd73-300">Therefore, a value of **Disconnected** means that the **PSSession** is not connected to the current session.</span></span> <span data-ttu-id="7fd73-301">Dies bedeutet jedoch nicht, dass die **PSSession** von allen Sitzungen getrennt ist.</span><span class="sxs-lookup"><span data-stu-id="7fd73-301">However, it does not mean that the **PSSession** is disconnected from all sessions.</span></span> <span data-ttu-id="7fd73-302">Sie kann mit einer anderen Sitzung verbunden sein.</span><span class="sxs-lookup"><span data-stu-id="7fd73-302">It might be connected to a different session.</span></span> <span data-ttu-id="7fd73-303">Um festzustellen, ob Sie eine Sitzungsverbindung herstellen bzw. wiederherstellen können, verwenden Sie die **Availability** -Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="7fd73-303">To determine whether you can connect or reconnect to the session, use the **Availability** property.</span></span>

  <span data-ttu-id="7fd73-304">Ein **Availability** -Wert von None gibt an, dass eine Verbindung mit der Sitzung hergestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="7fd73-304">An **Availability** value of None indicates that you can connect to the session.</span></span> <span data-ttu-id="7fd73-305">Der Wert ausgelastet gibt an, dass keine Verbindung mit der **PSSession** hergestellt werden kann, da Sie mit einer anderen Sitzung verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="7fd73-305">A value of Busy indicates that you cannot connect to the **PSSession** because it is connected to another session.</span></span>

  <span data-ttu-id="7fd73-306">Weitere Informationen zu den Werten der **State** -Eigenschaft von Sitzungen finden Sie unter [runspacestate-Enumeration](/dotnet/api/system.management.automation.runspaces.runspacestate).</span><span class="sxs-lookup"><span data-stu-id="7fd73-306">For more information about the values of the **State** property of sessions, see [RunspaceState Enumeration](/dotnet/api/system.management.automation.runspaces.runspacestate).</span></span>

  <span data-ttu-id="7fd73-307">Weitere Informationen zu den Werten der **Availability** -Eigenschaft von Sitzungen finden Sie unter [runspaceavailability-Enumeration](/dotnet/api/system.management.automation.runspaces.runspaceavailability).</span><span class="sxs-lookup"><span data-stu-id="7fd73-307">For more information about the values of the **Availability** property of sessions, see [RunspaceAvailability Enumeration](/dotnet/api/system.management.automation.runspaces.runspaceavailability).</span></span>

- <span data-ttu-id="7fd73-308">Wenn Sie eine Verbindung mit der **PSSession** herstellen, können Sie den Timeout Wert für das Leerlauf einer **PSSession** nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="7fd73-308">You cannot change the idle time-out value of a **PSSession** when you connect to the **PSSession**.</span></span> <span data-ttu-id="7fd73-309">Der **sessionoption** -Parameter von verwendet `Connect-PSSession` ein **sessionoption** -Objekt, das über einen **IdleTimeout** -Wert verfügt.</span><span class="sxs-lookup"><span data-stu-id="7fd73-309">The **SessionOption** parameter of `Connect-PSSession` takes a **SessionOption** object that has an **IdleTimeout** value.</span></span> <span data-ttu-id="7fd73-310">Der **IdleTimeout** -Wert des **sessionoption** -Objekts und der **IdleTimeout** -Wert der `$PSSessionOption` Variablen werden jedoch beim Herstellen einer Verbindung mit einer **PSSession** ignoriert.</span><span class="sxs-lookup"><span data-stu-id="7fd73-310">However, the **IdleTimeout** value of the **SessionOption** object and the **IdleTimeout** value of the `$PSSessionOption` variable are ignored when connecting to a **PSSession**.</span></span>

  <span data-ttu-id="7fd73-311">Sie können das Leerlauf Timeout einer **PSSession** festlegen und ändern, wenn Sie die **PSSession** erstellen, indem Sie die- `New-PSSession` oder- `Invoke-Command` Cmdlets verwenden und die Verbindung mit der **PSSession** trennen.</span><span class="sxs-lookup"><span data-stu-id="7fd73-311">You can set and change the idle time-out of a **PSSession** when you create the **PSSession** , by using the `New-PSSession` or `Invoke-Command` cmdlets, and when you disconnect from the **PSSession**.</span></span>

  <span data-ttu-id="7fd73-312">Die **IdleTimeout** -Eigenschaft einer **PSSession** ist wichtig für getrennte Sitzungen, da Sie bestimmt, wie lange eine getrennte Sitzung auf dem Remote Computer beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="7fd73-312">The **IdleTimeout** property of a **PSSession** is critical to disconnected sessions, because it determines how long a disconnected session is maintained on the remote computer.</span></span> <span data-ttu-id="7fd73-313">Getrennte Sitzungen gelten vom Moment ihrer Trennung an als im Leerlauf, selbst wenn Befehle in der getrennten Sitzung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="7fd73-313">Disconnected sessions are considered to be idle from the moment that they are disconnected, even if commands are running in the disconnected session.</span></span>

## <span data-ttu-id="7fd73-314">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="7fd73-314">RELATED LINKS</span></span>

[<span data-ttu-id="7fd73-315">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="7fd73-315">Disconnect-PSSession</span></span>](Disconnect-PSSession.md)

[<span data-ttu-id="7fd73-316">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="7fd73-316">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="7fd73-317">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="7fd73-317">Exit-PSSession</span></span>](Exit-PSSession.md)

[<span data-ttu-id="7fd73-318">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="7fd73-318">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="7fd73-319">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="7fd73-319">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="7fd73-320">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="7fd73-320">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="7fd73-321">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="7fd73-321">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="7fd73-322">New-PSTransportOption</span><span class="sxs-lookup"><span data-stu-id="7fd73-322">New-PSTransportOption</span></span>](New-PSTransportOption.md)

[<span data-ttu-id="7fd73-323">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="7fd73-323">Receive-PSSession</span></span>](Receive-PSSession.md)

[<span data-ttu-id="7fd73-324">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="7fd73-324">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="7fd73-325">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="7fd73-325">Remove-PSSession</span></span>](Remove-PSSession.md)
