---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 12/11/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/receive-pssession?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Receive-PSSession
ms.openlocfilehash: 3572d95724158b0ad4462d76d8d2aceb75d2fa18
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94387276"
---
# <span data-ttu-id="26e54-103">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="26e54-103">Receive-PSSession</span></span>

## <span data-ttu-id="26e54-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="26e54-104">SYNOPSIS</span></span>

<span data-ttu-id="26e54-105">Ruft die Ergebnisse von Befehlen in getrennten Sitzungen ab.</span><span class="sxs-lookup"><span data-stu-id="26e54-105">Gets results of commands in disconnected sessions</span></span>

## <span data-ttu-id="26e54-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="26e54-106">SYNTAX</span></span>

### <span data-ttu-id="26e54-107">Sitzung (Standard)</span><span class="sxs-lookup"><span data-stu-id="26e54-107">Session (Default)</span></span>

```
Receive-PSSession [-Session] <PSSession> [-OutTarget <OutTarget>] [-JobName <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="26e54-108">Id</span><span class="sxs-lookup"><span data-stu-id="26e54-108">Id</span></span>

```
Receive-PSSession [-Id] <Int32> [-OutTarget <OutTarget>] [-JobName <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="26e54-109">Computer Sitzungsname</span><span class="sxs-lookup"><span data-stu-id="26e54-109">ComputerSessionName</span></span>

```
Receive-PSSession [-ComputerName] <String> [-ApplicationName <String>] [-ConfigurationName <String>]
 -Name <String> [-OutTarget <OutTarget>] [-JobName <String>] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [-Port <Int32>]
 [-UseSSL] [-SessionOption <PSSessionOption>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="26e54-110">Computerinstanceid</span><span class="sxs-lookup"><span data-stu-id="26e54-110">ComputerInstanceId</span></span>

```
Receive-PSSession [-ComputerName] <String> [-ApplicationName <String>] [-ConfigurationName <String>]
 -InstanceId <Guid> [-OutTarget <OutTarget>] [-JobName <String>] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [-Port <Int32>]
 [-UseSSL] [-SessionOption <PSSessionOption>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="26e54-111">Connectionurisessionname</span><span class="sxs-lookup"><span data-stu-id="26e54-111">ConnectionUriSessionName</span></span>

```
Receive-PSSession [-ConfigurationName <String>] [-ConnectionUri] <Uri> [-AllowRedirection]
 -Name <String> [-OutTarget <OutTarget>] [-JobName <String>] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [-SessionOption <PSSessionOption>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="26e54-112">Connectionuriinstanceid</span><span class="sxs-lookup"><span data-stu-id="26e54-112">ConnectionUriInstanceId</span></span>

```
Receive-PSSession [-ConfigurationName <String>] [-ConnectionUri] <Uri> [-AllowRedirection]
 -InstanceId <Guid> [-OutTarget <OutTarget>] [-JobName <String>] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [-SessionOption <PSSessionOption>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="26e54-113">InstanceId</span><span class="sxs-lookup"><span data-stu-id="26e54-113">InstanceId</span></span>

```
Receive-PSSession [-InstanceId] <Guid> [-OutTarget <OutTarget>] [-JobName <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="26e54-114">Sessionname</span><span class="sxs-lookup"><span data-stu-id="26e54-114">SessionName</span></span>

```
Receive-PSSession [-Name] <String> [-OutTarget <OutTarget>] [-JobName <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="26e54-115">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="26e54-115">DESCRIPTION</span></span>

<span data-ttu-id="26e54-116">Das- `Receive-PSSession` Cmdlet ruft die Ergebnisse von Befehlen ab, die in PowerShell-Sitzungen ( **PSSession** ) ausgeführt werden, die getrennt wurden.</span><span class="sxs-lookup"><span data-stu-id="26e54-116">The `Receive-PSSession` cmdlet gets the results of commands running in PowerShell sessions ( **PSSession** ) that were disconnected.</span></span> <span data-ttu-id="26e54-117">Wenn die Sitzung zurzeit verbunden ist, ruft `Receive-PSSession` die Ergebnisse von Befehlen ab, die beim Trennen der Sitzung ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="26e54-117">If the session is currently connected, `Receive-PSSession` gets the results of commands that were running when the session was disconnected.</span></span> <span data-ttu-id="26e54-118">Wenn die Sitzung weiterhin getrennt ist, stellt `Receive-PSSession` eine Verbindung mit der Sitzung her, setzt alle angehaltenen Befehle fort und ruft die Ergebnisse der Befehle ab, die in der Sitzung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="26e54-118">If the session is still disconnected, `Receive-PSSession` connects to the session, resumes any commands that were suspended, and gets the results of commands running in the session.</span></span>

<span data-ttu-id="26e54-119">Dieses Cmdlet wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="26e54-119">This cmdlet was introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="26e54-120">Sie können einen `Receive-PSSession` zusätzlich zu oder anstelle eines `Connect-PSSession` Befehls verwenden.</span><span class="sxs-lookup"><span data-stu-id="26e54-120">You can use a `Receive-PSSession` in addition to or instead of a `Connect-PSSession` command.</span></span>
<span data-ttu-id="26e54-121">`Receive-PSSession` kann eine Verbindung mit einer getrennten oder wieder verbundenen Sitzung herstellen, die in anderen Sitzungen oder auf anderen Computern gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="26e54-121">`Receive-PSSession` can connect to any disconnected or reconnected session that was started in other sessions or on other computers.</span></span>

<span data-ttu-id="26e54-122">`Receive-PSSession` funktioniert bei **pssessions** , die mithilfe des- `Disconnect-PSSession` Cmdlets oder des `Invoke-Command` **indisconnectedsession** -Parameters absichtlich getrennt wurden.</span><span class="sxs-lookup"><span data-stu-id="26e54-122">`Receive-PSSession` works on **PSSessions** that were disconnected intentionally using the `Disconnect-PSSession` cmdlet or the `Invoke-Command` **InDisconnectedSession** parameter.</span></span> <span data-ttu-id="26e54-123">Oder nicht versehentlich durch eine Netzwerk Unterbrechung getrennt.</span><span class="sxs-lookup"><span data-stu-id="26e54-123">Or disconnected unintentionally by a network interruption.</span></span>

<span data-ttu-id="26e54-124">Wenn Sie mit dem `Receive-PSSession` Cmdlet eine Verbindung mit einer Sitzung herstellen, in der keine Befehle ausgeführt oder angehalten werden, wird eine Verbindung `Receive-PSSession` mit der Sitzung hergestellt, es werden jedoch keine Ausgaben oder Fehler zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="26e54-124">If you use the `Receive-PSSession` cmdlet to connect to a session in which no commands are running or suspended, `Receive-PSSession` connects to the session, but returns no output or errors.</span></span>

<span data-ttu-id="26e54-125">Weitere Informationen zum Feature „Getrennte Sitzungen“ finden Sie unter [about_Remote_Disconnected_Sessions](./About/about_Remote_Disconnected_Sessions.md).</span><span class="sxs-lookup"><span data-stu-id="26e54-125">For more information about the Disconnected Sessions feature, see [about_Remote_Disconnected_Sessions](./About/about_Remote_Disconnected_Sessions.md).</span></span>

<span data-ttu-id="26e54-126">In einigen Beispielen werden Verteilung verwendet, um die Zeilenlänge zu verringern und die Lesbarkeit zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="26e54-126">Some examples use splatting to reduce the line length and improve readability.</span></span> <span data-ttu-id="26e54-127">Weitere Informationen finden Sie unter [about_Splatting](./About/about_Splatting.md).</span><span class="sxs-lookup"><span data-stu-id="26e54-127">For more information, see [about_Splatting](./About/about_Splatting.md).</span></span>

## <span data-ttu-id="26e54-128">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="26e54-128">EXAMPLES</span></span>

### <span data-ttu-id="26e54-129">Beispiel 1: Herstellen einer Verbindung mit einer PSSession</span><span class="sxs-lookup"><span data-stu-id="26e54-129">Example 1: Connect to a PSSession</span></span>

<span data-ttu-id="26e54-130">In diesem Beispiel wird eine Verbindung mit einer Sitzung auf einem Remote Computer hergestellt, und die Ergebnisse von Befehlen, die in einer Sitzung ausgeführt werden, werden abgerufen.</span><span class="sxs-lookup"><span data-stu-id="26e54-130">This example connects to a session on a remote computer and gets the results of commands that are running in a session.</span></span>

```powershell
Receive-PSSession -ComputerName Server01 -Name ITTask
```

<span data-ttu-id="26e54-131">Der `Receive-PSSession` gibt den Remote Computer mit dem **Computername** -Parameter an.</span><span class="sxs-lookup"><span data-stu-id="26e54-131">The `Receive-PSSession` specifies the remote computer with the **ComputerName** parameter.</span></span> <span data-ttu-id="26e54-132">Der **Name** -Parameter identifiziert die ittask-Sitzung auf dem Server01-Computer.</span><span class="sxs-lookup"><span data-stu-id="26e54-132">The **Name** parameter identifies the ITTask session on the Server01 computer.</span></span> <span data-ttu-id="26e54-133">Das Beispiel ruft die Ergebnisse der Befehle ab, die in der ittask-Sitzung ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="26e54-133">The example gets the results of commands that were running in the ITTask session.</span></span>

<span data-ttu-id="26e54-134">Da der Befehl den **outtarget** -Parameter nicht verwendet, werden die Ergebnisse in der Befehlszeile angezeigt.</span><span class="sxs-lookup"><span data-stu-id="26e54-134">Because the command doesn't use the **OutTarget** parameter, the results appear on the command line.</span></span>

### <span data-ttu-id="26e54-135">Beispiel 2: erhalten der Ergebnisse aller Befehle für getrennte Sitzungen</span><span class="sxs-lookup"><span data-stu-id="26e54-135">Example 2: Get results of all commands on disconnected sessions</span></span>

<span data-ttu-id="26e54-136">In diesem Beispiel werden die Ergebnisse aller Befehle abgerufen, die in allen getrennten Sitzungen auf zwei Remote Computern ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="26e54-136">This example gets the results of all commands running in all disconnected sessions on two remote computers.</span></span>

<span data-ttu-id="26e54-137">Wenn eine Sitzung nicht getrennt wurde oder Befehle nicht ausgeführt werden, wird von keine `Receive-PSSession` Verbindung mit der Sitzung hergestellt, und es werden keine Ausgaben oder Fehler zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="26e54-137">If any session wasn't disconnected or isn't running commands, `Receive-PSSession` doesn't connect to the session and doesn't return any output or errors.</span></span>

```powershell
Get-PSSession -ComputerName Server01, Server02 | Receive-PSSession
```

<span data-ttu-id="26e54-138">`Get-PSSession` verwendet den **Computername** -Parameter, um die Remote Computer anzugeben.</span><span class="sxs-lookup"><span data-stu-id="26e54-138">`Get-PSSession` uses the **ComputerName** parameter to specify the remote computers.</span></span> <span data-ttu-id="26e54-139">Die Objekte werden über die Pipeline an gesendet `Receive-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="26e54-139">The objects are sent down the pipeline to `Receive-PSSession`.</span></span>

### <span data-ttu-id="26e54-140">Beispiel 3: erhalten der Ergebnisse eines Skripts, das in einer Sitzung ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="26e54-140">Example 3: Get the results of a script running in a session</span></span>

<span data-ttu-id="26e54-141">In diesem Beispiel wird das- `Receive-PSSession` Cmdlet verwendet, um die Ergebnisse eines Skripts zu erhalten, das in einer Remote Computersitzung ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="26e54-141">This example uses the `Receive-PSSession` cmdlet to get the results of a script that was running in a remote computer's session.</span></span>

```powershell
$parms = @{
  ComputerName = "Server01"
  Name = "ITTask"
  OutTarget = "Job"
  JobName = "ITTaskJob01"
  Credential = "Domain01\Admin01"
}
Receive-PSSession @parms
```

```Output
Id     Name            State         HasMoreData     Location
--     ----            -----         -----------     --------
16     ITTaskJob01     Running       True            Server01
```

<span data-ttu-id="26e54-142">Der Befehl verwendet die Parameter **ComputerName** und **Name** , um die getrennte Sitzung zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="26e54-142">The command uses the **ComputerName** and **Name** parameters to identify the disconnected session.</span></span>
<span data-ttu-id="26e54-143">Er verwendet den **outtarget** -Parameter mit einem Wert von Job, um `Receive-PSSession` die Ergebnisse als Auftrag zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="26e54-143">It uses the **OutTarget** parameter with a value of Job to direct `Receive-PSSession` to return the results as a job.</span></span> <span data-ttu-id="26e54-144">Der **Jobname** -Parameter gibt einen Namen für den Auftrag in der wieder verbundenen Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="26e54-144">The **JobName** parameter specifies a name for the job in the reconnected session.</span></span>
<span data-ttu-id="26e54-145">Der Parameter **Credential** führt den `Receive-PSSession` Befehl mit den Berechtigungen eines Domänen Administrators aus.</span><span class="sxs-lookup"><span data-stu-id="26e54-145">The **Credential** parameter runs the `Receive-PSSession` command using the permissions of a domain administrator.</span></span>

<span data-ttu-id="26e54-146">Die Ausgabe zeigt, dass `Receive-PSSession` die Ergebnisse als Auftrag in der aktuellen Sitzung zurückgegeben hat.</span><span class="sxs-lookup"><span data-stu-id="26e54-146">The output shows that `Receive-PSSession` returned the results as a job in the current session.</span></span> <span data-ttu-id="26e54-147">Um die Auftrags Ergebnisse zu erhalten, verwenden Sie einen `Receive-Job` Befehl.</span><span class="sxs-lookup"><span data-stu-id="26e54-147">To get the job results, use a `Receive-Job` command</span></span>

### <span data-ttu-id="26e54-148">Beispiel 4: Ergebnisse nach einem Netzwerkausfall erhalten</span><span class="sxs-lookup"><span data-stu-id="26e54-148">Example 4: Get results after a network outage</span></span>

<span data-ttu-id="26e54-149">In diesem Beispiel wird das- `Receive-PSSession` Cmdlet verwendet, um die Ergebnisse eines Auftrags zu erhalten, nachdem ein Netzwerkausfall eine Sitzungs Verbindung unterbrochen hat.</span><span class="sxs-lookup"><span data-stu-id="26e54-149">This example uses the `Receive-PSSession` cmdlet to get the results of a job after a network outage disrupts a session connection.</span></span> <span data-ttu-id="26e54-150">PowerShell versucht automatisch, die Sitzung einmal pro Sekunde in den nächsten vier Minuten erneut zu verbinden, und bricht den Aufwand nur ab, wenn alle Versuche im vierminütigen Intervall fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="26e54-150">PowerShell automatically attempts to reconnect the session once per second for the next four minutes and abandons the effort only if all attempts in the four-minute interval fail.</span></span>

```
PS> $s = New-PSSession -ComputerName Server01 -Name AD -ConfigurationName ADEndpoint
PS> $s

Id  Name   ComputerName    State        ConfigurationName     Availability
--  ----   ------------    -----        -----------------     ------------
8   AD      Server01       Opened       ADEndpoint               Available


PS> Invoke-Command -Session $s -FilePath \\Server12\Scripts\SharedScripts\New-ADResolve.ps1

Running "New-ADResolve.ps1"

# Network outage
# Restart local computer
# Network access is not re-established within 4 minutes


PS> Get-PSSession -ComputerName Server01

Id  Name   ComputerName    State          ConfigurationName      Availability
--  ----   ------------    -----          -----------------      ------------
1  Backup  Server01        Disconnected   Microsoft.PowerShell           None
8  AD      Server01        Disconnected   ADEndpoint                     None


PS> Receive-PSSession -ComputerName Server01 -Name AD -OutTarget Job -JobName AD

Job Id   Name      State         HasMoreData     Location
--       ----      -----         -----------     --------
16       ADJob     Running       True            Server01


PS> Get-PSSession -ComputerName Server01

Id  Name    ComputerName    State         ConfigurationName     Availability
--  ----    ------------    -----         -----------------     ------------
1  Backup   Server01        Disconnected  Microsoft.PowerShell          Busy
8  AD       Server01        Opened        ADEndpoint               Available
```

<span data-ttu-id="26e54-151">Das `New-PSSession` -Cmdlet erstellt eine Sitzung auf dem Server01-Computer und speichert die Sitzung in der `$s` Variablen.</span><span class="sxs-lookup"><span data-stu-id="26e54-151">The `New-PSSession` cmdlet creates a session on the Server01 computer and saves the session in the `$s` variable.</span></span> <span data-ttu-id="26e54-152">Die `$s` -Variable zeigt an, dass der **Status** geöffnet und die **Verfügbarkeit** verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="26e54-152">The `$s` variable displays that the **State** is Opened and the **Availability** is Available.</span></span> <span data-ttu-id="26e54-153">Diese Werte geben an, dass Sie mit der Sitzung verbunden sind und Befehle in der Sitzung ausführen können.</span><span class="sxs-lookup"><span data-stu-id="26e54-153">These values indicate that you're connected to the session and can run commands in the session.</span></span>

<span data-ttu-id="26e54-154">Das- `Invoke-Command` Cmdlet führt ein Skript in der-Sitzung in der- `$s` Variable aus.</span><span class="sxs-lookup"><span data-stu-id="26e54-154">The `Invoke-Command` cmdlet runs a script in the session in the `$s` variable.</span></span> <span data-ttu-id="26e54-155">Die Skriptausführung beginnt, und es werden Daten zurückgegeben, aber die Sitzung wird durch einen Netzwerkausfall unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="26e54-155">The script begins to run and return data, but a network outage occurs that interrupts the session.</span></span> <span data-ttu-id="26e54-156">Der Benutzer muss die Sitzung beenden und den lokalen Computer neu starten.</span><span class="sxs-lookup"><span data-stu-id="26e54-156">The user has to exit the session and restart the local computer.</span></span>

<span data-ttu-id="26e54-157">Wenn der Computer neu gestartet wird, startet der Benutzer PowerShell und führt einen `Get-PSSession` Befehl aus, um Sitzungen auf dem Server01-Computer zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="26e54-157">When the computer restarts, the user starts PowerShell and runs a `Get-PSSession` command to get sessions on the Server01 computer.</span></span> <span data-ttu-id="26e54-158">Die Ausgabe zeigt, dass die **AD** -Sitzung auf dem Server01-Computer weiterhin vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="26e54-158">The output shows that the **AD** session still exists on the Server01 computer.</span></span> <span data-ttu-id="26e54-159">Der **Status** gibt an, dass die **AD** -Sitzung getrennt ist.</span><span class="sxs-lookup"><span data-stu-id="26e54-159">The **State** indicates that the **AD** session is disconnected.</span></span> <span data-ttu-id="26e54-160">Der **Verfügbarkeits** Wert None gibt an, dass die Sitzung nicht mit Client Sitzungen verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="26e54-160">The **Availability** value of None, indicates that the session isn't connected to any client sessions.</span></span>

<span data-ttu-id="26e54-161">Das `Receive-PSSession` Cmdlet stellt erneut eine Verbindung mit der **AD** -Sitzung her und ruft die Ergebnisse des Skripts ab, das in der Sitzung ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="26e54-161">The `Receive-PSSession` cmdlet reconnects to the **AD** session and gets the results of the script that ran in the session.</span></span> <span data-ttu-id="26e54-162">Der Befehl verwendet den **outtarget** -Parameter, um die Ergebnisse in einem Auftrag mit dem Namen " **ADJob** " anzufordern.</span><span class="sxs-lookup"><span data-stu-id="26e54-162">The command uses the **OutTarget** parameter to request the results in a job named **ADJob**.</span></span> <span data-ttu-id="26e54-163">Der Befehl gibt ein Auftrags Objekt zurück, und die Ausgabe gibt an, dass das Skript noch ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="26e54-163">The command returns a job object and the output indicates that the script is still running.</span></span>

<span data-ttu-id="26e54-164">Das- `Get-PSSession` Cmdlet wird verwendet, um den Auftragsstatus zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="26e54-164">The `Get-PSSession` cmdlet is used to check the job state.</span></span> <span data-ttu-id="26e54-165">Die Ausgabe bestätigt, dass das `Receive-PSSession` Cmdlet erneut eine Verbindung mit der **AD** -Sitzung hergestellt hat, die nun geöffnet ist und für Befehle verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="26e54-165">The output confirms that the `Receive-PSSession` cmdlet reconnected to the **AD** session, which is now open and available for commands.</span></span> <span data-ttu-id="26e54-166">Und das Skript wird die Ausführung fortgesetzt, und die Skript Ergebnisse werden erhalten.</span><span class="sxs-lookup"><span data-stu-id="26e54-166">And, the script resumed execution and is getting the script results.</span></span>

### <span data-ttu-id="26e54-167">Beispiel 5: Wiederherstellen der Verbindung mit getrennten Sitzungen</span><span class="sxs-lookup"><span data-stu-id="26e54-167">Example 5: Reconnect to disconnected sessions</span></span>

<span data-ttu-id="26e54-168">In diesem Beispiel wird das `Receive-PSSession` -Cmdlet zum erneuten Verbinden mit Sitzungen verwendet, die absichtlich getrennt wurden, und die Ergebnisse von Aufträgen, die in den Sitzungen ausgeführt wurden, erhalten.</span><span class="sxs-lookup"><span data-stu-id="26e54-168">This example uses the `Receive-PSSession` cmdlet to reconnect to sessions that were intentionally disconnected and get the results of jobs that were running in the sessions.</span></span>

```
PS> $parms = @{
      InDisconnectedSession = $True
      ComputerName = "Server01", "Server02", "Server30"
      FilePath = "\\Server12\Scripts\SharedScripts\Get-BugStatus.ps1"
      Name = "BugStatus"
      SessionOption = @{IdleTimeout = 86400000}
      ConfigurationName = "ITTasks"
    }
PS> Invoke-Command @parms
PS> Exit


PS> $s = Get-PSSession -ComputerName Server01, Server02, Server30 -Name BugStatus
PS> $s

Id  Name   ComputerName    State         ConfigurationName     Availability
--  ----   ------------    -----         -----------------     ------------
1  ITTask  Server01        Disconnected  ITTasks                       None
8  ITTask  Server02        Disconnected  ITTasks                       None
2  ITTask  Server30        Disconnected  ITTasks                       None


PS> $Results = Receive-PSSession -Session $s
PS> $s

Id  Name   ComputerName    State         ConfigurationName     Availability
--  ----   ------------    -----         -----------------     ------------
1  ITTask  Server01        Opened        ITTasks                  Available
8  ITTask  Server02        Opened        ITTasks                  Available
2  ITTask  Server30        Opened        ITTasks                  Available


PS> $Results

Bug Report - Domain 01
----------------------
ComputerName          BugCount          LastUpdated
--------------        ---------         ------------
Server01              121               Friday, December 30, 2011 5:03:34 PM
```

<span data-ttu-id="26e54-169">Mit dem- `Invoke-Command` Cmdlet wird ein Skript auf drei Remote Computern ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="26e54-169">The `Invoke-Command` cmdlet runs a script on three remote computers.</span></span> <span data-ttu-id="26e54-170">Da das Skript Daten aus mehreren Datenbanken sammelt und zusammenfasst, nimmt es häufig eine längere Zeit an, bis das Skript abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="26e54-170">Because the script gathers and summarizes data from multiple databases, it often takes the script an extended time to finish.</span></span> <span data-ttu-id="26e54-171">Der Befehl verwendet den **indisconnectedsession** -Parameter, der die Skripts startet und die Sitzungen dann sofort trennt.</span><span class="sxs-lookup"><span data-stu-id="26e54-171">The command uses the **InDisconnectedSession** parameter that starts the scripts and then immediately disconnects the sessions.</span></span> <span data-ttu-id="26e54-172">Der **sessionoption** -Parameter erweitert den **IdleTimeout** -Wert der getrennten Sitzung.</span><span class="sxs-lookup"><span data-stu-id="26e54-172">The **SessionOption** parameter extends the **IdleTimeout** value of the disconnected session.</span></span> <span data-ttu-id="26e54-173">Getrennte Sitzungen gelten ab dem Zeitpunkt, an dem Sie getrennt sind, als Leerlauf.</span><span class="sxs-lookup"><span data-stu-id="26e54-173">Disconnected sessions are considered idle from the moment they're disconnected.</span></span> <span data-ttu-id="26e54-174">Es ist wichtig, das Leerlauf Timeout für lange genug festzulegen, damit die Befehle ausgeführt werden können, und Sie können erneut eine Verbindung mit der Sitzung herstellen.</span><span class="sxs-lookup"><span data-stu-id="26e54-174">It's important to set the idle time-out for long enough so that the commands can complete and you can reconnect to the session.</span></span> <span data-ttu-id="26e54-175">Sie können " **IdleTimeout** " nur festlegen, wenn Sie die PSSession erstellen, und diese nur ändern, wenn Sie die Verbindung mit der **PSSession** trennen.</span><span class="sxs-lookup"><span data-stu-id="26e54-175">You can set the **IdleTimeout** only when you create the **PSSession** and change it only when you disconnect from it.</span></span> <span data-ttu-id="26e54-176">Sie können den **IdleTimeout** -Wert nicht ändern, wenn Sie eine Verbindung mit einer **PSSession** herstellen oder Ergebnisse empfangen.</span><span class="sxs-lookup"><span data-stu-id="26e54-176">You can't change the **IdleTimeout** value when you connect to a **PSSession** or receiving its results.</span></span> <span data-ttu-id="26e54-177">Nachdem der Befehl ausgeführt wurde, beendet der Benutzer PowerShell und schließt den Computer.</span><span class="sxs-lookup"><span data-stu-id="26e54-177">After running the command, the user exits PowerShell and closes the computer.</span></span>

<span data-ttu-id="26e54-178">Am nächsten Tag nimmt der Benutzer Windows an, startet PowerShell und verwendet `Get-PSSession` , um die Sitzungen zu erhalten, in denen die Skripts ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="26e54-178">The next day, the user resumes Windows, starts PowerShell, and uses `Get-PSSession` to get the sessions in which the scripts were running.</span></span> <span data-ttu-id="26e54-179">Der Befehl identifiziert die Sitzungen nach Computername, Sitzungsname und Name der Sitzungs Konfiguration und speichert die Sitzungen in der `$s` Variablen.</span><span class="sxs-lookup"><span data-stu-id="26e54-179">The command identifies the sessions by the computer name, session name, and the name of the session configuration and saves the sessions in the `$s` variable.</span></span> <span data-ttu-id="26e54-180">Der Wert der `$s` Variablen wird angezeigt und zeigt an, dass die Sitzungen getrennt sind, aber nicht ausgelastet sind.</span><span class="sxs-lookup"><span data-stu-id="26e54-180">The value of the `$s` variable is displayed and shows that the sessions are disconnected, but aren't busy.</span></span>

<span data-ttu-id="26e54-181">`Receive-PSSession`Mit dem-Cmdlet wird eine Verbindung mit den Sitzungen in der Variablen hergestellt, und die Ergebnisse werden abgerufen `$s` .</span><span class="sxs-lookup"><span data-stu-id="26e54-181">The `Receive-PSSession` cmdlet connects to the sessions in the `$s` variable and gets their results.</span></span>
<span data-ttu-id="26e54-182">Der Befehl speichert die Ergebnisse in der `$Results` Variablen.</span><span class="sxs-lookup"><span data-stu-id="26e54-182">The command saves the results in the `$Results` variable.</span></span> <span data-ttu-id="26e54-183">Die `$s` Variable wird angezeigt und zeigt, dass die Sitzungen verbunden sind und für Befehle verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="26e54-183">The `$s` variable is displayed and shows that the sessions are connected and available for commands.</span></span>

<span data-ttu-id="26e54-184">Das Skript führt dazu, dass die `$Results` Variable in der PowerShell-Konsole angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="26e54-184">The script results in the `$Results` variable are displayed in the PowerShell console.</span></span> <span data-ttu-id="26e54-185">Wenn eines der Ergebnisse unerwartet ist, kann der Benutzer Befehle in den Sitzungen ausführen, um die Ursache zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="26e54-185">If any of the results are unexpected, the user can run commands in the sessions to investigate the root cause.</span></span>

### <span data-ttu-id="26e54-186">Beispiel 6: Ausführen eines Auftrags in einer getrennten Sitzung</span><span class="sxs-lookup"><span data-stu-id="26e54-186">Example 6: Running a job in a disconnected session</span></span>

<span data-ttu-id="26e54-187">Dieses Beispiel zeigt, was mit einem Auftrag geschieht, der in einer getrennten Sitzung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="26e54-187">This example shows what happens to a job that's running in a disconnected session.</span></span>

```
PS> $s = New-PSSession -ComputerName Server01 -Name Test
PS> $j = Invoke-Command -Session $s { 1..1500 | Foreach-Object {"Return $_"; sleep 30}} -AsJob
PS> $j

Id     Name           State         HasMoreData     Location
--     ----           -----         -----------     --------
16     Job1           Running       True            Server01


PS> $s | Disconnect-PSSession

Id Name   ComputerName    State         ConfigurationName     Availability
-- ----   ------------    -----         -----------------     ------------
1  Test   Server01        Disconnected  Microsoft.PowerShell          None


PS> $j

Id     Name           State         HasMoreData     Location
--     ----           -----         -----------     --------
16     Job1           Disconnected  True            Server01


PS> Receive-Job $j -Keep

Return 1
Return 2


PS> $s2 = Connect-PSSession -ComputerName Server01 -Name Test
PS> $j2 = Receive-PSSession -ComputerName Server01 -Name Test
PS> Receive-Job $j

Return 3
Return 4
```

<span data-ttu-id="26e54-188">Mit dem- `New-PSSession` Cmdlet wird die Test Sitzung auf dem Server01-Computer erstellt.</span><span class="sxs-lookup"><span data-stu-id="26e54-188">The `New-PSSession` cmdlet creates the Test session on the Server01 computer.</span></span> <span data-ttu-id="26e54-189">Der Befehl speichert die Sitzung in der Variablen `$s`.</span><span class="sxs-lookup"><span data-stu-id="26e54-189">The command saves the session in the `$s` variable.</span></span>

<span data-ttu-id="26e54-190">Das- `Invoke-Command` Cmdlet führt einen Befehl in der Sitzung in der `$s` Variablen aus.</span><span class="sxs-lookup"><span data-stu-id="26e54-190">The `Invoke-Command` cmdlet runs a command in the session in the `$s` variable.</span></span> <span data-ttu-id="26e54-191">Der Befehl verwendet den **AsJob** -Parameter, um den Befehl als Auftrag auszuführen, und erstellt das Auftrags Objekt in der aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="26e54-191">The command uses the **AsJob** parameter to run the command as a job and creates the job object in the current session.</span></span>
<span data-ttu-id="26e54-192">Der Befehl gibt ein Auftrags Objekt zurück, das in der `$j` Variablen gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="26e54-192">The command returns a job object that's saved in the `$j` variable.</span></span> <span data-ttu-id="26e54-193">Die- `$j` Variable zeigt das Auftrags Objekt an.</span><span class="sxs-lookup"><span data-stu-id="26e54-193">The `$j` variable displays the job object.</span></span>

<span data-ttu-id="26e54-194">Das Sitzungs Objekt in der `$s` Variablen wird an die Pipeline gesendet, `Disconnect-PSSession` und die Sitzung wird getrennt.</span><span class="sxs-lookup"><span data-stu-id="26e54-194">The session object in the `$s` variable is sent down the pipeline to `Disconnect-PSSession` and the session is disconnected.</span></span>

<span data-ttu-id="26e54-195">Die `$j` Variable wird angezeigt und zeigt die Auswirkung der Trennung des Auftrags Objekts in der `$j` Variablen an.</span><span class="sxs-lookup"><span data-stu-id="26e54-195">The `$j` variable is displayed and shows the effect of disconnecting the job object in the `$j` variable.</span></span> <span data-ttu-id="26e54-196">Der Status des Auftrags ist nun „Getrennt“.</span><span class="sxs-lookup"><span data-stu-id="26e54-196">The job state is now Disconnected.</span></span>

<span data-ttu-id="26e54-197">Der `Receive-Job` wird für den Auftrag in der `$j` Variablen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="26e54-197">The `Receive-Job` is run on the job in the `$j` variable.</span></span> <span data-ttu-id="26e54-198">Die Ausgabe zeigt, dass der Auftrag mit der Rückgabe der Ausgabe vor der Sitzung begonnen hat und der Auftrag getrennt wurde.</span><span class="sxs-lookup"><span data-stu-id="26e54-198">The output shows that the job began to return output before the session and the job were disconnected.</span></span>

<span data-ttu-id="26e54-199">Das- `Connect-PSSession` Cmdlet wird in derselben Client Sitzung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="26e54-199">The `Connect-PSSession` cmdlet is run in the same client session.</span></span> <span data-ttu-id="26e54-200">Der Befehl stellt erneut eine Verbindung mit der Test Sitzung auf dem Computer Server01 her und speichert die Sitzung in der `$s2` Variablen.</span><span class="sxs-lookup"><span data-stu-id="26e54-200">The command reconnects to the Test session on the Server01 computer and saves the session in the `$s2` variable.</span></span>

<span data-ttu-id="26e54-201">Mit dem- `Receive-PSSession` Cmdlet werden die Ergebnisse des Auftrags abgerufen, der in der Sitzung ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="26e54-201">The `Receive-PSSession` cmdlet gets the results of the job that was running in the session.</span></span> <span data-ttu-id="26e54-202">Da der Befehl in derselben Sitzung ausgeführt wird, werden `Receive-PSSession` die Ergebnisse standardmäßig als Auftrag zurückgegeben, und das gleiche Auftrags Objekt wird erneut verwendet.</span><span class="sxs-lookup"><span data-stu-id="26e54-202">Because the command is run in the same session, `Receive-PSSession` returns the results as a job by default and reuses the same job object.</span></span> <span data-ttu-id="26e54-203">Der Befehl speichert den Auftrag in der `$j2` Variablen.</span><span class="sxs-lookup"><span data-stu-id="26e54-203">The command saves the job in the `$j2` variable.</span></span> <span data-ttu-id="26e54-204">Das- `Receive-Job` Cmdlet ruft die Ergebnisse des Auftrags in der `$j` Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="26e54-204">The `Receive-Job` cmdlet gets the results of the job in the `$j` variable.</span></span>

## <span data-ttu-id="26e54-205">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="26e54-205">PARAMETERS</span></span>

### <span data-ttu-id="26e54-206">-Zuweisung Richtung</span><span class="sxs-lookup"><span data-stu-id="26e54-206">-AllowRedirection</span></span>

<span data-ttu-id="26e54-207">Gibt an, dass dieses Cmdlet die Umleitung dieser Verbindung an eine Alternative Uniform Resource Identifier (URI) zulässt.</span><span class="sxs-lookup"><span data-stu-id="26e54-207">Indicates that this cmdlet allows redirection of this connection to an alternate Uniform Resource Identifier (URI).</span></span>

<span data-ttu-id="26e54-208">Bei Verwendung des **ConnectionURI** -Parameters kann das Remoteziel eine Anweisung zum Umleiten an einen anderen URI zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="26e54-208">When you use the **ConnectionURI** parameter, the remote destination can return an instruction to redirect to a different URI.</span></span> <span data-ttu-id="26e54-209">Standardmäßig werden Verbindungen von PowerShell nicht umgeleitet, aber Sie können diesen Parameter verwenden, um eine Umleitung der Verbindung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="26e54-209">By default, PowerShell doesn't redirect connections, but you can use this parameter to enable it to redirect the connection.</span></span>

<span data-ttu-id="26e54-210">Sie können auch einschränken, wie oft die Verbindung umgeleitet wird, indem Sie den **MaximumConnectionRedirectionCount** -Optionswert der Sitzung ändern.</span><span class="sxs-lookup"><span data-stu-id="26e54-210">You can also limit the number of times the connection is redirected by changing the **MaximumConnectionRedirectionCount** session option value.</span></span> <span data-ttu-id="26e54-211">Verwenden Sie den **maximumredirect** -Parameter des `New-PSSessionOption` Cmdlets, oder legen Sie die **maximumconnectionredirectioncount** -Eigenschaft der `$PSSessionOption` Preference-Variablen fest.</span><span class="sxs-lookup"><span data-stu-id="26e54-211">Use the **MaximumRedirection** parameter of the `New-PSSessionOption` cmdlet or set the **MaximumConnectionRedirectionCount** property of the `$PSSessionOption` preference variable.</span></span> <span data-ttu-id="26e54-212">Der Standardwert ist 5.</span><span class="sxs-lookup"><span data-stu-id="26e54-212">The default value is 5.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ConnectionUriSessionName, ConnectionUriInstanceId
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="26e54-213">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="26e54-213">-ApplicationName</span></span>

<span data-ttu-id="26e54-214">Gibt eine Anwendung an.</span><span class="sxs-lookup"><span data-stu-id="26e54-214">Specifies an application.</span></span> <span data-ttu-id="26e54-215">Dieses Cmdlet stellt nur Verbindungen mit Sitzungen her, die die angegebene Anwendung verwenden.</span><span class="sxs-lookup"><span data-stu-id="26e54-215">This cmdlet connects only to sessions that use the specified application.</span></span>

<span data-ttu-id="26e54-216">Geben Sie das Anwendungsnamensegment des Verbindungs-URI ein.</span><span class="sxs-lookup"><span data-stu-id="26e54-216">Enter the application name segment of the connection URI.</span></span> <span data-ttu-id="26e54-217">Im folgenden Verbindungs-URI ist WSMAN z. b. der Anwendungsname: `http://localhost:5985/WSMAN` .</span><span class="sxs-lookup"><span data-stu-id="26e54-217">For example, in the following connection URI, WSMan is the application name: `http://localhost:5985/WSMAN`.</span></span>

<span data-ttu-id="26e54-218">Der Anwendungsname einer Sitzung wird in der **Runspace.ConnectionInfo.AppName** -Eigenschaft der Sitzung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="26e54-218">The application name of a session is stored in the **Runspace.ConnectionInfo.AppName** property of the session.</span></span>

<span data-ttu-id="26e54-219">Der Wert des Parameters wird verwendet, um Sitzungen auszuwählen und zu filtern.</span><span class="sxs-lookup"><span data-stu-id="26e54-219">The parameter's value is used to select and filter sessions.</span></span> <span data-ttu-id="26e54-220">Die von der Sitzung verwendete Anwendung wird nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="26e54-220">It doesn't change the application that the session uses.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerSessionName, ComputerInstanceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="26e54-221">-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="26e54-221">-Authentication</span></span>

<span data-ttu-id="26e54-222">Gibt den Mechanismus an, der zum Authentifizieren der Benutzer Anmelde Informationen im Befehl verwendet wird, um die Verbindung mit einer getrennten Sitzung wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="26e54-222">Specifies the mechanism that's used to authenticate the user credentials in the command to reconnect to a disconnected session.</span></span> <span data-ttu-id="26e54-223">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="26e54-223">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="26e54-224">Standard</span><span class="sxs-lookup"><span data-stu-id="26e54-224">Default</span></span>
- <span data-ttu-id="26e54-225">Standard</span><span class="sxs-lookup"><span data-stu-id="26e54-225">Basic</span></span>
- <span data-ttu-id="26e54-226">CredSSP</span><span class="sxs-lookup"><span data-stu-id="26e54-226">Credssp</span></span>
- <span data-ttu-id="26e54-227">Digest</span><span class="sxs-lookup"><span data-stu-id="26e54-227">Digest</span></span>
- <span data-ttu-id="26e54-228">Kerberos</span><span class="sxs-lookup"><span data-stu-id="26e54-228">Kerberos</span></span>
- <span data-ttu-id="26e54-229">Aushandeln</span><span class="sxs-lookup"><span data-stu-id="26e54-229">Negotiate</span></span>
- <span data-ttu-id="26e54-230">NegotiateWithImplicitCredential</span><span class="sxs-lookup"><span data-stu-id="26e54-230">NegotiateWithImplicitCredential</span></span>

<span data-ttu-id="26e54-231">Der Standardwert ist Default.</span><span class="sxs-lookup"><span data-stu-id="26e54-231">The default value is Default.</span></span>

<span data-ttu-id="26e54-232">Weitere Informationen zu den Werten dieses Parameters finden Sie unter [authenticationmechanism-Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span><span class="sxs-lookup"><span data-stu-id="26e54-232">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!CAUTION]
> <span data-ttu-id="26e54-233">Die Authentifizierung der Credential Security Support Provider (kredssp), bei der die Anmelde Informationen des Benutzers an einen Remote Computer übergeben werden, der authentifiziert werden soll, wurde für Befehle entworfen, die eine Authentifizierung auf mehr als einer Ressource erfordern, z. b. den Zugriff auf eine Remote Netzwerkfreigabe.</span><span class="sxs-lookup"><span data-stu-id="26e54-233">Credential Security Support Provider (CredSSP) authentication, in which the user credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="26e54-234">Dieser Mechanismus erhöht das Sicherheitsrisiko des Remotevorgangs.</span><span class="sxs-lookup"><span data-stu-id="26e54-234">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="26e54-235">Wenn die Sicherheit des Remotecomputers gefährdet ist, können die an ihn übergebenen Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="26e54-235">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: ComputerSessionName, ComputerInstanceId, ConnectionUriSessionName, ConnectionUriInstanceId
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="26e54-236">-Certifiupethumschlag-Print</span><span class="sxs-lookup"><span data-stu-id="26e54-236">-CertificateThumbprint</span></span>

<span data-ttu-id="26e54-237">Gibt das digitale Zertifikat für öffentliche Schlüssel (X.509) eines Benutzerkontos mit der Berechtigung zum Herstellen einer Verbindung mit der getrennten Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="26e54-237">Specifies the digital public key certificate (X509) of a user account that has permission to connect to the disconnected session.</span></span> <span data-ttu-id="26e54-238">Geben Sie den Zertifikatfingerabdruck des Zertifikats ein.</span><span class="sxs-lookup"><span data-stu-id="26e54-238">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="26e54-239">Zertifikate werden bei der clientzertifikatbasierten Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="26e54-239">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="26e54-240">Zertifikate können nur lokalen Benutzerkonten zugeordnet werden und funktionieren nicht mit Domänen Konten.</span><span class="sxs-lookup"><span data-stu-id="26e54-240">Certificates can be mapped only to local user accounts, and don't work with domain accounts.</span></span>

<span data-ttu-id="26e54-241">Um einen Zertifikat Fingerabdruck abzurufen, verwenden Sie einen- `Get-Item` `Get-ChildItem` Befehl oder den-Befehl im PowerShell- `Cert:` Laufwerk.</span><span class="sxs-lookup"><span data-stu-id="26e54-241">To get a certificate thumbprint, use a `Get-Item` or `Get-ChildItem` command in the PowerShell `Cert:` drive.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerSessionName, ComputerInstanceId, ConnectionUriSessionName, ConnectionUriInstanceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="26e54-242">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="26e54-242">-ComputerName</span></span>

<span data-ttu-id="26e54-243">Gibt den Computer an, auf dem die getrennte Sitzung gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="26e54-243">Specifies the computer on which the disconnected session is stored.</span></span> <span data-ttu-id="26e54-244">Sitzungen werden auf dem Server, der sich auf dem Server befindet, oder am Ende einer Verbindung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="26e54-244">Sessions are stored on the computer that's at the server-side, or receiving end of a connection.</span></span> <span data-ttu-id="26e54-245">Die Standardeinstellung ist der lokale Computer.</span><span class="sxs-lookup"><span data-stu-id="26e54-245">The default is the local computer.</span></span>

<span data-ttu-id="26e54-246">Geben Sie den NetBIOS-Namen, eine IP-Adresse oder einen voll qualifizierten Domänen Namen (Fully Qualified Domain Name, FQDN) eines Computers ein.</span><span class="sxs-lookup"><span data-stu-id="26e54-246">Type the NetBIOS name, an IP address, or a fully qualified domain name (FQDN) of one computer.</span></span>
<span data-ttu-id="26e54-247">Platzhalter Zeichen sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="26e54-247">Wildcard characters aren't permitted.</span></span> <span data-ttu-id="26e54-248">Um den lokalen Computer anzugeben, geben Sie den Computernamen, einen Punkt ( `.` ), `$env:COMPUTERNAME` oder einen localhost ein.</span><span class="sxs-lookup"><span data-stu-id="26e54-248">To specify the local computer, type the computer name, a dot (`.`), `$env:COMPUTERNAME`, or localhost.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerSessionName, ComputerInstanceId
Aliases: Cn

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="26e54-249">-ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="26e54-249">-ConfigurationName</span></span>

<span data-ttu-id="26e54-250">Gibt den Namen einer Sitzungs Konfiguration an.</span><span class="sxs-lookup"><span data-stu-id="26e54-250">Specifies the name of a session configuration.</span></span> <span data-ttu-id="26e54-251">Dieses Cmdlet stellt nur Verbindungen mit Sitzungen her, die die angegebene Sitzungs Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="26e54-251">This cmdlet connects only to sessions that use the specified session configuration.</span></span>

<span data-ttu-id="26e54-252">Geben Sie einen Konfigurationsnamen oder den vollqualifizierten Ressourcen-URI für eine Sitzungskonfiguration ein.</span><span class="sxs-lookup"><span data-stu-id="26e54-252">Enter a configuration name or the fully qualified resource URI for a session configuration.</span></span> <span data-ttu-id="26e54-253">Wenn Sie nur den Konfigurationsnamen angeben, wird der folgende Schema-URI vorangestellt:</span><span class="sxs-lookup"><span data-stu-id="26e54-253">If you specify only the configuration name, the following schema URI is prepended:</span></span>

<span data-ttu-id="26e54-254">`http://schemas.microsoft.com/powershell`.</span><span class="sxs-lookup"><span data-stu-id="26e54-254">`http://schemas.microsoft.com/powershell`.</span></span>

<span data-ttu-id="26e54-255">Der Konfigurationsname einer Sitzung befindet sich in der **ConfigurationName** -Eigenschaft der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="26e54-255">The configuration name of a session is stored in the **ConfigurationName** property of the session.</span></span>

<span data-ttu-id="26e54-256">Der Wert des Parameters wird verwendet, um Sitzungen auszuwählen und zu filtern.</span><span class="sxs-lookup"><span data-stu-id="26e54-256">The parameter's value is used to select and filter sessions.</span></span> <span data-ttu-id="26e54-257">Die Sitzungs Konfiguration, die von der Sitzung verwendet wird, wird nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="26e54-257">It doesn't change the session configuration that the session uses.</span></span>

<span data-ttu-id="26e54-258">Weitere Informationen zu Sitzungs Konfigurationen finden Sie unter [about_Session_Configurations](./About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="26e54-258">For more information about session configurations, see [about_Session_Configurations](./About/about_Session_Configurations.md).</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerSessionName, ComputerInstanceId, ConnectionUriSessionName, ConnectionUriInstanceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="26e54-259">-ConnectionUri</span><span class="sxs-lookup"><span data-stu-id="26e54-259">-ConnectionUri</span></span>

<span data-ttu-id="26e54-260">Gibt einen URI an, der den Verbindungs Endpunkt definiert, der zum erneuten Herstellen der Verbindung mit der getrennten Sitzung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="26e54-260">Specifies a URI that defines the connection endpoint that is used to reconnect to the disconnected session.</span></span>

<span data-ttu-id="26e54-261">Der URI muss vollqualifiziert sein.</span><span class="sxs-lookup"><span data-stu-id="26e54-261">The URI must be fully qualified.</span></span> <span data-ttu-id="26e54-262">Das Zeichen folgen Format lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="26e54-262">The string's format is as follows:</span></span>

`<Transport>://<ComputerName>:<Port>/<ApplicationName>`

<span data-ttu-id="26e54-263">Der Standardwert lautet:</span><span class="sxs-lookup"><span data-stu-id="26e54-263">The default value is as follows:</span></span>

`http://localhost:5985/WSMAN`

<span data-ttu-id="26e54-264">Wenn Sie keinen Verbindungs-URI angeben, können Sie die Parameter " **US** ", " **Computername** ", " **Port** " und " **ApplicationName** " verwenden, um die Verbindungs-URI-Werte anzugeben.</span><span class="sxs-lookup"><span data-stu-id="26e54-264">If you don't specify a connection URI, you can use the **UseSSL** , **ComputerName** , **Port** , and **ApplicationName** parameters to specify the connection URI values.</span></span>

<span data-ttu-id="26e54-265">Gültige Werte für das **Transport** -Segment des URI sind „HTTP“ und „HTTPS“.</span><span class="sxs-lookup"><span data-stu-id="26e54-265">Valid values for the **Transport** segment of the URI are HTTP and HTTPS.</span></span> <span data-ttu-id="26e54-266">Wenn Sie einen Verbindungs-URI mit einem Transport Segment angeben, aber keinen Port angeben, wird die Sitzung mit Standardports erstellt: 80 für http und 443 für HTTPS.</span><span class="sxs-lookup"><span data-stu-id="26e54-266">If you specify a connection URI with a Transport segment, but don't specify a port, the session is created with standard ports: 80 for HTTP and 443 for HTTPS.</span></span> <span data-ttu-id="26e54-267">Wenn Sie die Standardports für PowerShell-Remoting verwenden möchten, geben Sie Port 5985 für http oder 5986 für HTTPS an.</span><span class="sxs-lookup"><span data-stu-id="26e54-267">To use the default ports for PowerShell remoting, specify port 5985 for HTTP or 5986 for HTTPS.</span></span>

<span data-ttu-id="26e54-268">Wenn der Zielcomputer die Verbindung an einen anderen URI umleitet, verhindert PowerShell die Umleitung, es sei denn, Sie verwenden den Parameter " **Zuweisung** " im Befehl.</span><span class="sxs-lookup"><span data-stu-id="26e54-268">If the destination computer redirects the connection to a different URI, PowerShell prevents the redirection unless you use the **AllowRedirection** parameter in the command.</span></span>

```yaml
Type: System.Uri
Parameter Sets: ConnectionUriSessionName, ConnectionUriInstanceId
Aliases: URI, CU

Required: True
Position: 0
Default value: http://localhost:5985/WSMAN
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="26e54-269">-Credential</span><span class="sxs-lookup"><span data-stu-id="26e54-269">-Credential</span></span>

<span data-ttu-id="26e54-270">Gibt ein Benutzerkonto mit der Berechtigung zum Herstellen einer Verbindung mit der getrennten Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="26e54-270">Specifies a user account that has permission to connect to the disconnected session.</span></span> <span data-ttu-id="26e54-271">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="26e54-271">The default is the current user.</span></span>

<span data-ttu-id="26e54-272">Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01** , oder geben Sie ein **PSCredential** -Objekt ein, das vom `Get-Credential` Cmdlet generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="26e54-272">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="26e54-273">Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe des Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="26e54-273">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="26e54-274">Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.</span><span class="sxs-lookup"><span data-stu-id="26e54-274">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="26e54-275">Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="26e54-275">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerSessionName, ComputerInstanceId, ConnectionUriSessionName, ConnectionUriInstanceId
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="26e54-276">-Id</span><span class="sxs-lookup"><span data-stu-id="26e54-276">-Id</span></span>

<span data-ttu-id="26e54-277">Gibt die ID einer getrennten Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="26e54-277">Specifies the ID of a disconnected session.</span></span> <span data-ttu-id="26e54-278">Der **ID** -Parameter funktioniert nur, wenn die getrennte Sitzung zuvor mit der aktuellen Sitzung verbunden war.</span><span class="sxs-lookup"><span data-stu-id="26e54-278">The **Id** parameter works only when the disconnected session was previously connected to the current session.</span></span>

<span data-ttu-id="26e54-279">Dieser Parameter ist gültig, aber nicht wirksam, wenn die Sitzung auf dem lokalen Computer gespeichert, aber nicht mit der aktuellen Sitzung verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="26e54-279">This parameter is valid, but not effective, when the session is stored on the local computer, but wasn't connected to the current session.</span></span>

```yaml
Type: System.Int32
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="26e54-280">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="26e54-280">-InstanceId</span></span>

<span data-ttu-id="26e54-281">Gibt die Instanz-ID der getrennten Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="26e54-281">Specifies the instance ID of the disconnected session.</span></span> <span data-ttu-id="26e54-282">Die Instanz-ID ist eine GUID, die eine **PSSession** auf einem lokalen Computer oder einem Remote Computer eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="26e54-282">The instance ID is a GUID that uniquely identifies a **PSSession** on a local or remote computer.</span></span> <span data-ttu-id="26e54-283">Die Instanz-ID wird in der **InstanceId-** Eigenschaft der **PSSession** gespeichert.</span><span class="sxs-lookup"><span data-stu-id="26e54-283">The instance ID is stored in the **InstanceID** property of the **PSSession**.</span></span>

```yaml
Type: System.Guid
Parameter Sets: ComputerInstanceId, ConnectionUriInstanceId, InstanceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="26e54-284">-Jobname</span><span class="sxs-lookup"><span data-stu-id="26e54-284">-JobName</span></span>

<span data-ttu-id="26e54-285">Gibt einen anzeigen Amen für den Auftrag an, der `Receive-PSSession` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="26e54-285">Specifies a friendly name for the job that `Receive-PSSession` returns.</span></span>

<span data-ttu-id="26e54-286">`Receive-PSSession` Gibt einen Auftrag zurück, wenn der Wert des **outtarget** -Parameters "Job" ist oder der Auftrag, der in der getrennten Sitzung ausgeführt wird, in der aktuellen Sitzung gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="26e54-286">`Receive-PSSession` returns a job when the value of the **OutTarget** parameter is Job or the job that's running in the disconnected session was started in the current session.</span></span>

<span data-ttu-id="26e54-287">Wenn der Auftrag, der in der getrennten Sitzung ausgeführt wird, in der aktuellen Sitzung gestartet wurde, verwendet PowerShell das ursprüngliche Auftrags Objekt in der Sitzung erneut und ignoriert den Wert des **Jobname** -Parameters.</span><span class="sxs-lookup"><span data-stu-id="26e54-287">If the job that's running in the disconnected session was started in the current session, PowerShell reuses the original job object in the session and ignores the value of the **JobName** parameter.</span></span>

<span data-ttu-id="26e54-288">Wenn der Auftrag, der in der getrennten Sitzung ausgeführt wird, in einer anderen Sitzung gestartet wurde, erstellt PowerShell ein neues Auftrags Objekt.</span><span class="sxs-lookup"><span data-stu-id="26e54-288">If the job that's running in the disconnected session was started in a different session, PowerShell creates a new job object.</span></span> <span data-ttu-id="26e54-289">Es wird ein Standardname verwendet, aber Sie können diesen Parameter verwenden, um den Namen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="26e54-289">It uses a default name, but you can use this parameter to change the name.</span></span>

<span data-ttu-id="26e54-290">Wenn der Standardwert oder der explizite Wert des **outtarget** -Parameters nicht "Job" ist, ist der Befehl erfolgreich, aber der **Jobname** -Parameter hat keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="26e54-290">If the default value or explicit value of the **OutTarget** parameter isn't Job, the command succeeds, but the **JobName** parameter has no effect.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="26e54-291">-Name</span><span class="sxs-lookup"><span data-stu-id="26e54-291">-Name</span></span>

<span data-ttu-id="26e54-292">Gibt den Anzeigenamen der getrennten Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="26e54-292">Specifies the friendly name of the disconnected session.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerSessionName, ConnectionUriSessionName, SessionName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="26e54-293">-Outtarget</span><span class="sxs-lookup"><span data-stu-id="26e54-293">-OutTarget</span></span>

<span data-ttu-id="26e54-294">Bestimmt, wie die Sitzungsergebnisse zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="26e54-294">Determines how the session results are returned.</span></span> <span data-ttu-id="26e54-295">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="26e54-295">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="26e54-296">**Auftrag**.</span><span class="sxs-lookup"><span data-stu-id="26e54-296">**Job**.</span></span> <span data-ttu-id="26e54-297">Gibt die Ergebnisse asynchron in ein Auftragsobjekt zurück.</span><span class="sxs-lookup"><span data-stu-id="26e54-297">Returns the results asynchronously in a job object.</span></span> <span data-ttu-id="26e54-298">Sie können den **JobName** -Parameter verwenden, um einen Namen oder einen neuen Namen für den Auftrag festzulegen.</span><span class="sxs-lookup"><span data-stu-id="26e54-298">You can use the **JobName** parameter to specify a name or new name for the job.</span></span>
- <span data-ttu-id="26e54-299">**Host**.</span><span class="sxs-lookup"><span data-stu-id="26e54-299">**Host**.</span></span> <span data-ttu-id="26e54-300">Gibt die Ergebnisse (synchron) an die Befehlszeile zurück.</span><span class="sxs-lookup"><span data-stu-id="26e54-300">Returns the results to the command line (synchronously).</span></span> <span data-ttu-id="26e54-301">Wenn der Befehl fortgesetzt wird oder die Ergebnisse aus einer großen Anzahl von Objekten bestehen, kann die Antwort verzögert werden.</span><span class="sxs-lookup"><span data-stu-id="26e54-301">If the command is being resumed or the results consist of a large number of objects, the response might be delayed.</span></span>

<span data-ttu-id="26e54-302">Der Standardwert des **outtarget** -Parameters ist Host.</span><span class="sxs-lookup"><span data-stu-id="26e54-302">The default value of the **OutTarget** parameter is Host.</span></span> <span data-ttu-id="26e54-303">Wenn der Befehl, der in einer getrennten Sitzung empfangen wird, in der aktuellen Sitzung gestartet wurde, ist der Standardwert des **outtarget** -Parameters das Formular, in dem der Befehl gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="26e54-303">If the command that's being received in a disconnected session was started in the current session, the default value of the **OutTarget** parameter is the form in which the command was started.</span></span> <span data-ttu-id="26e54-304">Wenn der Befehl als Auftrag gestartet wurde, wird er standardmäßig als Auftrag zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="26e54-304">If the command was started as a job, by default, it's returned as a job.</span></span> <span data-ttu-id="26e54-305">Andernfalls wird Sie standardmäßig an das Host Programm zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="26e54-305">Otherwise, it's returned to the host program by default.</span></span>

<span data-ttu-id="26e54-306">In der Regel zeigt das Hostprogramm die zurückgegebenen Objekte ohne Verzögerung in der Befehlszeile an, dieses Verhalten kann jedoch variieren.</span><span class="sxs-lookup"><span data-stu-id="26e54-306">Typically, the host program displays returned objects at the command line without delay, but this behavior can vary.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.OutTarget
Parameter Sets: (All)
Aliases:
Accepted values: Default, Host, Job

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="26e54-307">-Port</span><span class="sxs-lookup"><span data-stu-id="26e54-307">-Port</span></span>

<span data-ttu-id="26e54-308">Gibt den Netzwerkport des Remote Computers an, der zum erneuten Herstellen der Verbindung mit der Sitzung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="26e54-308">Specifies the remote computer's network port that's used to reconnect to the session.</span></span> <span data-ttu-id="26e54-309">Zum Herstellen einer Verbindung mit einem Remote Computer muss der Port, der von der Verbindung verwendet wird, überwacht werden.</span><span class="sxs-lookup"><span data-stu-id="26e54-309">To connect to a remote computer, it must be listening on the port that the connection uses.</span></span> <span data-ttu-id="26e54-310">Die Standardports sind 5985. Dies ist der WinRM-Port für http und 5986 (der WinRM-Port für HTTPS).</span><span class="sxs-lookup"><span data-stu-id="26e54-310">The default ports are 5985, which is the WinRM port for HTTP, and 5986, which is the WinRM port for HTTPS.</span></span>

<span data-ttu-id="26e54-311">Vor der Verwendung eines alternativen Ports müssen Sie den WinRM-Listener auf dem Remote Computer so konfigurieren, dass er an diesem Port lauscht.</span><span class="sxs-lookup"><span data-stu-id="26e54-311">Before using an alternate port, you must configure the WinRM listener on the remote computer to listen on that port.</span></span> <span data-ttu-id="26e54-312">Um den Listener zu konfigurieren, geben Sie die folgenden beiden Befehle an der PowerShell-Eingabeaufforderung ein:</span><span class="sxs-lookup"><span data-stu-id="26e54-312">To configure the listener, type the following two commands at the PowerShell prompt:</span></span>

`Remove-Item -Path WSMan:\Localhost\listener\listener* -Recurse`

`New-Item -Path WSMan:\Localhost\listener -Transport http -Address * -Port \<port-number\>`

<span data-ttu-id="26e54-313">Verwenden Sie den **Port** -Parameter nur, wenn dies erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="26e54-313">Don't use the **Port** parameter unless it's necessary.</span></span> <span data-ttu-id="26e54-314">Der im Befehl festgelegte Port gilt für alle Computer oder Sitzungen, für die der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="26e54-314">The port that's set in the command applies to all computers or sessions on which the command runs.</span></span> <span data-ttu-id="26e54-315">Eine alternative Porteinstellung kann verhindern, dass der Befehl auf allen Computern ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="26e54-315">An alternate port setting might prevent the command from running on all computers.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ComputerSessionName, ComputerInstanceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="26e54-316">-Sitzung</span><span class="sxs-lookup"><span data-stu-id="26e54-316">-Session</span></span>

<span data-ttu-id="26e54-317">Gibt die getrennte Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="26e54-317">Specifies the disconnected session.</span></span> <span data-ttu-id="26e54-318">Geben Sie eine Variable ein, die die **PSSession** oder einen Befehl enthält, der die **PSSession** erstellt oder abruft, z. b. einen- `Get-PSSession` Befehl.</span><span class="sxs-lookup"><span data-stu-id="26e54-318">Enter a variable that contains the **PSSession** or a command that creates or gets the **PSSession** , such as a `Get-PSSession` command.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession
Parameter Sets: Session
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="26e54-319">-Sessionoption</span><span class="sxs-lookup"><span data-stu-id="26e54-319">-SessionOption</span></span>

<span data-ttu-id="26e54-320">Gibt erweiterte Optionen für die Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="26e54-320">Specifies advanced options for the session.</span></span> <span data-ttu-id="26e54-321">Geben Sie ein **sessionoption** -Objekt ein, z. b. ein Objekt, das Sie mit dem `New-PSSessionOption` Cmdlet erstellen, oder eine Hash Tabelle, in der die Schlüssel Sitzungs Optionsnamen und die Werte Sitzungs Optionswerte sind.</span><span class="sxs-lookup"><span data-stu-id="26e54-321">Enter a **SessionOption** object, such as one that you create by using the `New-PSSessionOption` cmdlet, or a hash table in which the keys are session option names and the values are session option values.</span></span>

<span data-ttu-id="26e54-322">Die Standardwerte für die Optionen werden durch den Wert der Einstellungs `$PSSessionOption` Variablen bestimmt, sofern festgelegt.</span><span class="sxs-lookup"><span data-stu-id="26e54-322">The default values for the options are determined by the value of the `$PSSessionOption` preference variable, if it's set.</span></span> <span data-ttu-id="26e54-323">Andernfalls werden die Standardwerte durch Optionen festgelegt, die in der Sitzungskonfiguration festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="26e54-323">Otherwise, the default values are established by options set in the session configuration.</span></span>

<span data-ttu-id="26e54-324">Die Sitzungs Optionswerte haben Vorrang vor Standardwerten für Sitzungen, die in der `$PSSessionOption` Preference-Variablen und in der Sitzungs Konfiguration festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="26e54-324">The session option values take precedence over default values for sessions set in the `$PSSessionOption` preference variable and in the session configuration.</span></span> <span data-ttu-id="26e54-325">Allerdings haben Sie Vorrang vor maximalen Werten, Kontingenten oder Grenzwerten, die in der Sitzungs Konfiguration festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="26e54-325">However, they don't take precedence over maximum values, quotas, or limits set in the session configuration.</span></span>

<span data-ttu-id="26e54-326">Eine Beschreibung der Sitzungs Optionen, die die Standardwerte enthalten, finden Sie unter `New-PSSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="26e54-326">For a description of the session options that includes the default values, see `New-PSSessionOption`.</span></span> <span data-ttu-id="26e54-327">Weitere Informationen zur **$PSSessionOption** Preference-Variablen finden Sie unter [about_Preference_Variables](./About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="26e54-327">For information about the **$PSSessionOption** preference variable, see [about_Preference_Variables](./About/about_Preference_Variables.md).</span></span> <span data-ttu-id="26e54-328">Weitere Informationen zu Sitzungs Konfigurationen finden Sie unter [about_Session_Configurations](./About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="26e54-328">For more information about session configurations, see [about_Session_Configurations](./About/about_Session_Configurations.md).</span></span>

```yaml
Type: System.Management.Automation.Remoting.PSSessionOption
Parameter Sets: ComputerSessionName, ComputerInstanceId, ConnectionUriSessionName, ConnectionUriInstanceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="26e54-329">-US-</span><span class="sxs-lookup"><span data-stu-id="26e54-329">-UseSSL</span></span>

<span data-ttu-id="26e54-330">Gibt an, dass dieses Cmdlet das Secure Sockets Layer (SSL)-Protokoll zum Herstellen einer Verbindung mit der getrennten Sitzung verwendet.</span><span class="sxs-lookup"><span data-stu-id="26e54-330">Indicates that this cmdlet uses the Secure Sockets Layer (SSL) protocol to connect to the disconnected session.</span></span> <span data-ttu-id="26e54-331">Standardmäßig wird SSL nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="26e54-331">By default, SSL isn't used.</span></span>

<span data-ttu-id="26e54-332">WS-Management verschlüsselt alle über das Netzwerk übertragenen PowerShell-Inhalte.</span><span class="sxs-lookup"><span data-stu-id="26e54-332">WS-Management encrypts all PowerShell content transmitted over the network.</span></span> <span data-ttu-id="26e54-333">**UseSSL** ist ein zusätzlicher Schutz, der die Daten über eine HTTPS-Verbindung anstatt über eine HTTP-Verbindung sendet.</span><span class="sxs-lookup"><span data-stu-id="26e54-333">**UseSSL** is an additional protection that sends the data across an HTTPS connection instead of an HTTP connection.</span></span>

<span data-ttu-id="26e54-334">Wenn Sie diesen Parameter verwenden und SSL nicht an dem Port verfügbar ist, der für den Befehl verwendet wird, schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="26e54-334">If you use this parameter and SSL isn't available on the port that's used for the command, the command fails.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerSessionName, ComputerInstanceId
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="26e54-335">-Confirm</span><span class="sxs-lookup"><span data-stu-id="26e54-335">-Confirm</span></span>

<span data-ttu-id="26e54-336">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="26e54-336">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="26e54-337">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="26e54-337">-WhatIf</span></span>

<span data-ttu-id="26e54-338">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="26e54-338">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="26e54-339">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="26e54-339">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="26e54-340">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="26e54-340">CommonParameters</span></span>

<span data-ttu-id="26e54-341">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="26e54-341">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="26e54-342">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="26e54-342">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="26e54-343">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="26e54-343">INPUTS</span></span>

### <span data-ttu-id="26e54-344">System. Management. Automation. Runspaces. PSSession</span><span class="sxs-lookup"><span data-stu-id="26e54-344">System.Management.Automation.Runspaces.PSSession</span></span>

<span data-ttu-id="26e54-345">Sie können Sitzungs Objekte über die Pipeline an dieses Cmdlet übergeben, z. b `Get-PSSession` . die vom Cmdlet zurückgegebenen Objekte.</span><span class="sxs-lookup"><span data-stu-id="26e54-345">You can pipe session objects to this cmdlet, such as objects returned by the `Get-PSSession` cmdlet.</span></span>

### <span data-ttu-id="26e54-346">System.Int32</span><span class="sxs-lookup"><span data-stu-id="26e54-346">System.Int32</span></span>

<span data-ttu-id="26e54-347">Sie können Sitzungs-IDs an dieses Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="26e54-347">You can pipe session Ids to this cmdlet.</span></span>

### <span data-ttu-id="26e54-348">System.Guid</span><span class="sxs-lookup"><span data-stu-id="26e54-348">System.Guid</span></span>

<span data-ttu-id="26e54-349">Sie können die Instanz-IDs von Sitzungen dieses Cmdlets über die Pipeline übergeben.</span><span class="sxs-lookup"><span data-stu-id="26e54-349">You can pipe the instance Ids of sessions this cmdlet.</span></span>

### <span data-ttu-id="26e54-350">System.String</span><span class="sxs-lookup"><span data-stu-id="26e54-350">System.String</span></span>

<span data-ttu-id="26e54-351">Sie können Sitzungs Namen an dieses Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="26e54-351">You can pipe session names to this cmdlet.</span></span>

## <span data-ttu-id="26e54-352">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="26e54-352">OUTPUTS</span></span>

### <span data-ttu-id="26e54-353">System. Management. Automation. Job oder psobject</span><span class="sxs-lookup"><span data-stu-id="26e54-353">System.Management.Automation.Job or PSObject</span></span>

<span data-ttu-id="26e54-354">Mit diesem Cmdlet werden die Ergebnisse von Befehlen zurückgegeben, die ggf. in der getrennten Sitzung ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="26e54-354">This cmdlet returns the results of commands that ran in the disconnected session, if any.</span></span> <span data-ttu-id="26e54-355">Wenn der Wert oder der Standardwert des **outtarget** -Parameters "Job" ist, wird `Receive-PSSession` ein Auftrags Objekt zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="26e54-355">If the value or default value of the **OutTarget** parameter is Job, `Receive-PSSession` returns a job object.</span></span> <span data-ttu-id="26e54-356">Andernfalls werden Objekte zurückgeben, die diese Befehlsergebnisse darstellen.</span><span class="sxs-lookup"><span data-stu-id="26e54-356">Otherwise, it returns objects that represent that command results.</span></span>

## <span data-ttu-id="26e54-357">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="26e54-357">NOTES</span></span>

<span data-ttu-id="26e54-358">Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="26e54-358">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="26e54-359">`Receive-PSSession` Ruft Ergebnisse nur aus Sitzungen ab, die getrennt wurden.</span><span class="sxs-lookup"><span data-stu-id="26e54-359">`Receive-PSSession` gets results only from sessions that were disconnected.</span></span> <span data-ttu-id="26e54-360">Nur Sitzungen, die mit einem Computer verbunden sind, auf dem PowerShell 3,0 oder höhere Versionen ausgeführt werden, können getrennt und erneut verbunden werden.</span><span class="sxs-lookup"><span data-stu-id="26e54-360">Only sessions that are connected to, or terminate at, computers that run PowerShell 3.0 or later versions can be disconnected and reconnected.</span></span>

<span data-ttu-id="26e54-361">Wenn die Befehle, die in der getrennten Sitzung ausgeführt wurden, keine Ergebnisse generiert haben oder die Ergebnisse bereits an eine andere Sitzung zurückgegeben wurden, `Receive-PSSession` generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="26e54-361">If the commands that were running in the disconnected session didn't generate results or if the results were already returned to another session, `Receive-PSSession` doesn't generate any output.</span></span>

<span data-ttu-id="26e54-362">Der Ausgabepuffer Modus einer Sitzung bestimmt, wie die Befehle in der Sitzung die Ausgabe verwalten, wenn die Sitzung getrennt wird.</span><span class="sxs-lookup"><span data-stu-id="26e54-362">A session's output buffering mode determines how commands in the session manage output when the session is disconnected.</span></span> <span data-ttu-id="26e54-363">Wenn der Wert der **outputbufferingmode** -Option der Sitzung Drop und der Ausgabepuffer voll ist, beginnt der Befehl mit dem Löschen der Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="26e54-363">When the value of the **OutputBufferingMode** option of the session is Drop and the output buffer is full, the command starts to delete output.</span></span> <span data-ttu-id="26e54-364">`Receive-PSSession` Diese Ausgabe kann nicht wieder hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="26e54-364">`Receive-PSSession` can't recover this output.</span></span> <span data-ttu-id="26e54-365">Weitere Informationen zur Option "Output bufferingmode" finden Sie in den Hilfe Artikeln für die Cmdlets " [New-pssessionoption](New-PSSessionOption.md) " und " [New-pstransportoption](New-PSTransportOption.md) ".</span><span class="sxs-lookup"><span data-stu-id="26e54-365">For more information about the output buffering mode option, see the help articles for the [New-PSSessionOption](New-PSSessionOption.md) and [New-PSTransportOption](New-PSTransportOption.md) cmdlets.</span></span>

<span data-ttu-id="26e54-366">Sie können den Leerlauf Timeout Wert einer **PSSession** nicht ändern, wenn Sie eine Verbindung mit der **PSSession** herstellen oder Ergebnisse empfangen.</span><span class="sxs-lookup"><span data-stu-id="26e54-366">You can't change the idle time-out value of a **PSSession** when you connect to the **PSSession** or receive results.</span></span> <span data-ttu-id="26e54-367">Der **sessionoption** -Parameter von verwendet `Receive-PSSession` ein **sessionoption** -Objekt, das über einen **IdleTimeout** -Wert verfügt.</span><span class="sxs-lookup"><span data-stu-id="26e54-367">The **SessionOption** parameter of `Receive-PSSession` takes a **SessionOption** object that has an **IdleTimeout** value.</span></span> <span data-ttu-id="26e54-368">Der **IdleTimeout** -Wert des **sessionoption** -Objekts und der **IdleTimeout** -Wert der `$PSSessionOption` Variablen werden jedoch ignoriert, wenn eine Verbindung mit einer **PSSession** hergestellt oder Ergebnisse empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="26e54-368">However, the **IdleTimeout** value of the **SessionOption** object and the **IdleTimeout** value of the `$PSSessionOption` variable are ignored when it connects to a **PSSession** or receiving results.</span></span>

- <span data-ttu-id="26e54-369">Sie können das Leerlauf Timeout einer **PSSession** festlegen und ändern, wenn Sie die **PSSession** erstellen, indem Sie die- `New-PSSession` oder- `Invoke-Command` Cmdlets verwenden und die Verbindung mit der **PSSession** trennen.</span><span class="sxs-lookup"><span data-stu-id="26e54-369">You can set and change the idle time-out of a **PSSession** when you create the **PSSession** , by using the `New-PSSession` or `Invoke-Command` cmdlets, and when you disconnect from the **PSSession**.</span></span>
- <span data-ttu-id="26e54-370">Die **IdleTimeout** -Eigenschaft einer **PSSession** ist wichtig für getrennte Sitzungen, da Sie bestimmt, wie lange eine getrennte Sitzung auf dem Remote Computer beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="26e54-370">The **IdleTimeout** property of a **PSSession** is critical to disconnected sessions because it determines how long a disconnected session is maintained on the remote computer.</span></span> <span data-ttu-id="26e54-371">Getrennte Sitzungen gelten vom Moment ihrer Trennung an als im Leerlauf, selbst wenn Befehle in der getrennten Sitzung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="26e54-371">Disconnected sessions are considered to be idle from the moment that they are disconnected, even if commands are running in the disconnected session.</span></span>

<span data-ttu-id="26e54-372">Wenn Sie einen Auftrag in einer Remote Sitzung starten, indem Sie den **AsJob** -Parameter des `Invoke-Command` Cmdlets verwenden, wird das Auftrags Objekt in der aktuellen Sitzung erstellt, auch wenn der Auftrag in der Remote Sitzung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="26e54-372">If you start a start a job in a remote session by using the **AsJob** parameter of the `Invoke-Command` cmdlet, the job object is created in the current session, even though the job runs in the remote session.</span></span> <span data-ttu-id="26e54-373">Wenn Sie die Remote Sitzung trennen, wird das Auftrags Objekt in der aktuellen Sitzung vom Auftrag getrennt.</span><span class="sxs-lookup"><span data-stu-id="26e54-373">If you disconnect the remote session, the job object in the current session is disconnected from the job.</span></span> <span data-ttu-id="26e54-374">Das Auftrags Objekt enthält alle Ergebnisse, die an es zurückgegeben wurden, empfängt aber keine neuen Ergebnisse aus dem Auftrag in der getrennten Sitzung.</span><span class="sxs-lookup"><span data-stu-id="26e54-374">The job object contains any results that were returned to it, but doesn't receive new results from the job in the disconnected session.</span></span>

<span data-ttu-id="26e54-375">Wenn ein anderer Client eine Verbindung mit der Sitzung herstellt, die den laufenden Auftrag enthält, sind die Ergebnisse, die an das ursprüngliche Auftrags Objekt in der ursprünglichen Sitzung übermittelt wurden, in der neu verbundenen Sitzung nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="26e54-375">If a different client connects to the session that contains the running job, the results that were delivered to the original job object in the original session aren't available in the newly connected session.</span></span> <span data-ttu-id="26e54-376">Nur Ergebnisse, die nicht an das ursprüngliche Auftragsobjekt übermittelt wurden, sind in der neu verbundenen Sitzung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="26e54-376">Only results that were not delivered to the original job object are available in the reconnected session.</span></span>

<span data-ttu-id="26e54-377">Wenn Sie ein Skript in einer Sitzung starten und dann die Verbindung mit der Sitzung trennen, sind alle Ergebnisse, die das Skript vor der Trennung an die Sitzung übergibt, nicht für einen anderen Client verfügbar, der eine Verbindung mit der Sitzung herstellt.</span><span class="sxs-lookup"><span data-stu-id="26e54-377">Similarly, if you start a script in a session and then disconnect from the session, any results that the script delivers to the session before disconnecting aren't available to another client that connects to the session.</span></span>

<span data-ttu-id="26e54-378">Verwenden Sie den **indisconnectedsession** -Parameter des Cmdlets, um Datenverluste in Sitzungen zu vermeiden, die Sie trennen möchten `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="26e54-378">To prevent data loss in sessions that you intend to disconnect, use the **InDisconnectedSession** parameter of the `Invoke-Command` cmdlet.</span></span> <span data-ttu-id="26e54-379">Da dieser Parameter verhindert, dass Ergebnisse an die aktuelle Sitzung zurückgegeben werden, sind alle Ergebnisse verfügbar, wenn die Verbindung mit der Sitzung wiederhergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="26e54-379">Because this parameter prevents results from being returned to the current session, all results are available when the session is reconnected.</span></span>

<span data-ttu-id="26e54-380">Sie können auch Datenverlust verhindern, indem Sie mit dem- `Invoke-Command` Cmdlet einen `Start-Job` Befehl in der Remote Sitzung ausführen.</span><span class="sxs-lookup"><span data-stu-id="26e54-380">You can also prevent data loss by using the `Invoke-Command` cmdlet to run a `Start-Job` command in the remote session.</span></span> <span data-ttu-id="26e54-381">In diesem Fall wird das Auftragsobjekt in der Remotesitzung erstellt.</span><span class="sxs-lookup"><span data-stu-id="26e54-381">In this case, the job object is created in the remote session.</span></span> <span data-ttu-id="26e54-382">Sie können das `Receive-PSSession` Cmdlet nicht verwenden, um die Auftrags Ergebnisse zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="26e54-382">You can't use the `Receive-PSSession` cmdlet to get the job results.</span></span> <span data-ttu-id="26e54-383">Verwenden Sie stattdessen das `Connect-PSSession` Cmdlet, um eine Verbindung mit der Sitzung herzustellen, und verwenden Sie dann das `Invoke-Command` Cmdlet, um einen `Receive-Job` Befehl in der Sitzung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="26e54-383">Instead, use the `Connect-PSSession` cmdlet to connect to the session and then use the `Invoke-Command` cmdlet to run a `Receive-Job` command in the session.</span></span>

<span data-ttu-id="26e54-384">Wenn eine Sitzung, die einen laufenden Auftrag enthält, getrennt und die Verbindung wieder hergestellt wird, wird das ursprüngliche Auftrags Objekt nur dann wieder verwendet, wenn der Auftrag getrennt und wieder mit der gleichen Sitzung verbunden wird und der Befehl zum Wiederherstellen der Verbindung keinen neuen Auftrags Namen angibt.</span><span class="sxs-lookup"><span data-stu-id="26e54-384">When a session that contains a running job is disconnected and then reconnected, the original job object is reused only if the job is disconnected and reconnected to the same session, and the command to reconnect doesn't specify a new job name.</span></span> <span data-ttu-id="26e54-385">Wenn die Sitzung erneut mit einer anderen Client Sitzung verbunden ist oder ein neuer Auftrags Name angegeben wird, erstellt PowerShell ein neues Auftrags Objekt für die neue Sitzung.</span><span class="sxs-lookup"><span data-stu-id="26e54-385">If the session is reconnected to a different client session or a new job name is specified, PowerShell creates a new job object for the new session.</span></span>

<span data-ttu-id="26e54-386">Wenn Sie eine **PSSession** trennen, wird der Sitzungs Status getrennt, und die Verfügbarkeit ist None.</span><span class="sxs-lookup"><span data-stu-id="26e54-386">When you disconnect a **PSSession** , the session state is Disconnected and the availability is None.</span></span>

- <span data-ttu-id="26e54-387">Der Wert der **State** Eigenschaft bezieht sich auf die aktuelle Sitzung.</span><span class="sxs-lookup"><span data-stu-id="26e54-387">The value of the **State** property is relative to the current session.</span></span> <span data-ttu-id="26e54-388">Der Wert "getrennt" bedeutet, dass die **PSSession** nicht mit der aktuellen Sitzung verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="26e54-388">A value of Disconnected means that the **PSSession** isn't connected to the current session.</span></span> <span data-ttu-id="26e54-389">Dies bedeutet jedoch nicht, dass die **PSSession** von allen Sitzungen getrennt ist.</span><span class="sxs-lookup"><span data-stu-id="26e54-389">However, it doesn't mean that the **PSSession** is disconnected from all sessions.</span></span> <span data-ttu-id="26e54-390">Sie kann mit einer anderen Sitzung verbunden sein.</span><span class="sxs-lookup"><span data-stu-id="26e54-390">It might be connected to a different session.</span></span>
  <span data-ttu-id="26e54-391">Um festzustellen, ob Sie eine Sitzungsverbindung herstellen bzw. wiederherstellen können, verwenden Sie die **Availability** -Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="26e54-391">To determine whether you can connect or reconnect to the session, use the **Availability** property.</span></span>
- <span data-ttu-id="26e54-392">Ein **Availability** -Wert von None gibt an, dass eine Verbindung mit der Sitzung hergestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="26e54-392">An **Availability** value of None indicates that you can connect to the session.</span></span> <span data-ttu-id="26e54-393">Der Wert ausgelastet gibt an, dass keine Verbindung mit der **PSSession** hergestellt werden kann, da Sie mit einer anderen Sitzung verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="26e54-393">A value of Busy indicates that you can't connect to the **PSSession** because it's connected to another session.</span></span>
- <span data-ttu-id="26e54-394">Weitere Informationen zu den Werten der **State** -Eigenschaft von Sitzungen finden Sie unter [runspacestate](/dotnet/api/system.management.automation.runspaces.runspacestate).</span><span class="sxs-lookup"><span data-stu-id="26e54-394">For more information about the values of the **State** property of sessions, see [RunspaceState](/dotnet/api/system.management.automation.runspaces.runspacestate).</span></span>
- <span data-ttu-id="26e54-395">Weitere Informationen zu den Werten der **Availability** -Eigenschaft von Sitzungen finden Sie unter [runspaceavailability](/dotnet/api/system.management.automation.runspaces.runspaceavailability).</span><span class="sxs-lookup"><span data-stu-id="26e54-395">For more information about the values of the **Availability** property of sessions, see [RunspaceAvailability](/dotnet/api/system.management.automation.runspaces.runspaceavailability).</span></span>

## <span data-ttu-id="26e54-396">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="26e54-396">RELATED LINKS</span></span>

[<span data-ttu-id="26e54-397">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="26e54-397">about_PSSessions</span></span>](./About/about_PSSessions.md)

[<span data-ttu-id="26e54-398">about_Remote</span><span class="sxs-lookup"><span data-stu-id="26e54-398">about_Remote</span></span>](./About/about_Remote.md)

[<span data-ttu-id="26e54-399">about_Remote_Disconnected_Sessions</span><span class="sxs-lookup"><span data-stu-id="26e54-399">about_Remote_Disconnected_Sessions</span></span>](./About/about_Remote_Disconnected_Sessions.md)

[<span data-ttu-id="26e54-400">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="26e54-400">about_Session_Configurations</span></span>](./About/about_Session_Configurations.md)

[<span data-ttu-id="26e54-401">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="26e54-401">Connect-PSSession</span></span>](Connect-PSSession.md)

[<span data-ttu-id="26e54-402">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="26e54-402">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="26e54-403">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="26e54-403">Exit-PSSession</span></span>](Exit-PSSession.md)

[<span data-ttu-id="26e54-404">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="26e54-404">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="26e54-405">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="26e54-405">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="26e54-406">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="26e54-406">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="26e54-407">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="26e54-407">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="26e54-408">New-PSTransportOption</span><span class="sxs-lookup"><span data-stu-id="26e54-408">New-PSTransportOption</span></span>](New-PSTransportOption.md)

[<span data-ttu-id="26e54-409">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="26e54-409">Remove-PSSession</span></span>](Remove-PSSession.md)
