---
description: Erläutert, wie eine Verbindung mit einer PowerShell-Sitzung (PSSession) getrennt und die Verbindung wieder hergestellt wird.
Locale: en-US
ms.date: 12/01/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_disconnected_sessions?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_Disconnected_Sessions
ms.openlocfilehash: 0756e110b1058915f6280e2ea59ee915bedb2c75
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596352"
---
# <a name="about-remote-disconnected-sessions"></a><span data-ttu-id="3f51e-103">Informationen zu getrennten Remote Sitzungen</span><span class="sxs-lookup"><span data-stu-id="3f51e-103">About Remote Disconnected Sessions</span></span>

## <a name="short-description"></a><span data-ttu-id="3f51e-104">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3f51e-104">Short description</span></span>

<span data-ttu-id="3f51e-105">Erläutert, wie eine Verbindung mit einer PowerShell-Sitzung (PSSession) getrennt und die Verbindung wieder hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="3f51e-105">Explains how to disconnect and reconnect to a PowerShell Session (PSSession).</span></span>

## <a name="long-description"></a><span data-ttu-id="3f51e-106">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3f51e-106">Long description</span></span>

<span data-ttu-id="3f51e-107">Ab PowerShell 3,0 können Sie die Verbindung mit einer PSSession trennen und die Verbindung mit der PSSession auf dem gleichen Computer oder auf einem anderen Computer wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="3f51e-107">Beginning in PowerShell 3.0, you can disconnect from a PSSession and reconnect to the PSSession on the same computer or a different computer.</span></span> <span data-ttu-id="3f51e-108">Der Sitzungszustand wird beibehalten, und Befehle in der PSSession werden weiterhin ausgeführt, während die Sitzung getrennt wird.</span><span class="sxs-lookup"><span data-stu-id="3f51e-108">The session state is maintained and commands in the PSSession continue to run while the session is disconnected.</span></span>

<span data-ttu-id="3f51e-109">Die Funktion "getrennte Sitzungen" ist nur verfügbar, wenn auf dem Remote Computer PowerShell 3,0 oder eine höhere Version ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3f51e-109">The Disconnected Sessions feature is only available when the remote computer is running PowerShell 3.0 or a later version.</span></span>

<span data-ttu-id="3f51e-110">Mit dem Feature "getrennte Sitzungen" können Sie die Sitzung schließen, in der eine PSSession erstellt wurde, und sogar PowerShell schließen und den Computer Herunterfahren, ohne die in der PSSession ausgelaufenden Befehle zu unterbrechen.</span><span class="sxs-lookup"><span data-stu-id="3f51e-110">The Disconnected Sessions feature allows you to close the session in which a PSSession was created, and even close PowerShell, and shut down the computer, without disrupting commands running in the PSSession.</span></span> <span data-ttu-id="3f51e-111">Getrennte Sitzungen sind nützlich für die Ausführung von Befehlen, die einen längeren Zeitraum benötigen, und bieten Zeit-und Geräte Flexibilität, die IT-Experten benötigen.</span><span class="sxs-lookup"><span data-stu-id="3f51e-111">Disconnected sessions are useful for running commands that take an extended time to complete, and provides the time and device flexibility that IT professionals require.</span></span>

<span data-ttu-id="3f51e-112">Die Verbindung mit einer interaktiven Sitzung, die mithilfe des Cmdlets gestartet wurde, kann nicht getrennt werden `Enter-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="3f51e-112">You can't disconnect from an interactive session that is started by using the `Enter-PSSession` cmdlet.</span></span>

<span data-ttu-id="3f51e-113">Sie können getrennte Sitzungen zum Verwalten von pssessions verwenden, die aufgrund eines Computer-oder Netzwerkausfalls versehentlich getrennt wurden.</span><span class="sxs-lookup"><span data-stu-id="3f51e-113">You can use disconnected sessions to manage PSSessions that were disconnected unintentionally as the result of a computer or network outage.</span></span>

<span data-ttu-id="3f51e-114">In der Praxis können Sie mit der Funktion für getrennte Sitzungen beginnen, ein Problem zu lösen, ein Problem mit höherer Priorität zu lösen und die Arbeit an der Lösung fortzusetzen, selbst auf einem anderen Computer an einem anderen Standort.</span><span class="sxs-lookup"><span data-stu-id="3f51e-114">In real-world use, the Disconnected Sessions feature allows you to begin solving a problem, turn your attention to a higher priority issue, and then resume work on the solution, even on a different computer in a different location.</span></span>

## <a name="disconnected-session-cmdlets"></a><span data-ttu-id="3f51e-115">Cmdlets für getrennte Sitzungen</span><span class="sxs-lookup"><span data-stu-id="3f51e-115">Disconnected session cmdlets</span></span>

<span data-ttu-id="3f51e-116">Die folgenden Cmdlets unterstützen das Feature "getrennte Sitzungen":</span><span class="sxs-lookup"><span data-stu-id="3f51e-116">The following cmdlets support the Disconnected Sessions feature:</span></span>

- <span data-ttu-id="3f51e-117">`Connect-PSSession`: Stellt eine Verbindung mit einer getrennten PSSession her.</span><span class="sxs-lookup"><span data-stu-id="3f51e-117">`Connect-PSSession`: Connects to a disconnected PSSession.</span></span>
- <span data-ttu-id="3f51e-118">`Disconnect-PSSession`: Trennt eine PSSession.</span><span class="sxs-lookup"><span data-stu-id="3f51e-118">`Disconnect-PSSession`: Disconnects a PSSession.</span></span>
- <span data-ttu-id="3f51e-119">`Get-PSSession`: Ruft pssessions auf dem lokalen Computer oder auf Remote Computern ab.</span><span class="sxs-lookup"><span data-stu-id="3f51e-119">`Get-PSSession`: Gets PSSessions on the local computer or on remote computers.</span></span>
- <span data-ttu-id="3f51e-120">`Receive-PSSession`: Ruft die Ergebnisse von Befehlen ab, die in getrennten Sitzungen ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="3f51e-120">`Receive-PSSession`: Gets the results of commands that ran in disconnected sessions.</span></span>
- <span data-ttu-id="3f51e-121">`Invoke-Command`: Der **indisconnectedsession** -Parameter erstellt eine PSSession und trennt die Verbindung sofort.</span><span class="sxs-lookup"><span data-stu-id="3f51e-121">`Invoke-Command`: **InDisconnectedSession** parameter creates a PSSession and disconnects immediately.</span></span>

## <a name="how-the-disconnected-sessions-feature-works"></a><span data-ttu-id="3f51e-122">Funktionsweise der Funktion "getrennte Sitzungen"</span><span class="sxs-lookup"><span data-stu-id="3f51e-122">How the Disconnected Sessions feature works</span></span>

<span data-ttu-id="3f51e-123">Ab PowerShell 3,0 sind pssessions unabhängig von den Sitzungen, in denen Sie erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="3f51e-123">Beginning in PowerShell 3.0, PSSessions are independent of the sessions in which they're created.</span></span> <span data-ttu-id="3f51e-124">Aktive pssessions werden auf dem Remote Computer oder der **Serverseite** der Verbindung verwaltet, auch wenn die Sitzung, in der die PSSession erstellt wurde, geschlossen ist und der ursprüngliche Computer heruntergefahren oder vom Netzwerk getrennt wird.</span><span class="sxs-lookup"><span data-stu-id="3f51e-124">Active PSSessions are maintained on the remote computer or **server-side** of the connection, even if the session in which the PSSession was created is closed and the originating computer is shut down or disconnected from the network.</span></span>

<span data-ttu-id="3f51e-125">In PowerShell 2,0 wird die PSSession auf dem Remote Computer gelöscht, wenn Sie von der ursprünglichen Sitzung getrennt ist oder die Sitzung beendet wird, in der Sie erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="3f51e-125">In PowerShell 2.0, the PSSession is deleted from the remote computer when it's disconnected from the originating session or the session in which it was created ends.</span></span>

<span data-ttu-id="3f51e-126">Wenn Sie eine PSSession trennen, bleibt die PSSession aktiv und wird auf dem Remote Computer beibehalten.</span><span class="sxs-lookup"><span data-stu-id="3f51e-126">When you disconnect a PSSession, the PSSession remains active and is maintained on the remote computer.</span></span> <span data-ttu-id="3f51e-127">Der Sitzungs Status ändert sich von wird **ausgeführt** in **getrennt**.</span><span class="sxs-lookup"><span data-stu-id="3f51e-127">The session state changes from **Running** to **Disconnected**.</span></span> <span data-ttu-id="3f51e-128">Sie können von der aktuellen Sitzung oder einer anderen Sitzung auf demselben Computer oder von einem anderen Computer aus eine Verbindung mit einer getrennten PSSession herstellen.</span><span class="sxs-lookup"><span data-stu-id="3f51e-128">You can reconnect to a disconnected PSSession from the current session or from a different session on the same computer, or from a different computer.</span></span> <span data-ttu-id="3f51e-129">Der Remote Computer, auf dem die Sitzung verwaltet wird, muss ausgeführt werden und mit dem Netzwerk verbunden sein.</span><span class="sxs-lookup"><span data-stu-id="3f51e-129">The remote computer that maintains the session must be running and be connected to the network.</span></span>

<span data-ttu-id="3f51e-130">Befehle in einer getrennten PSSession werden auf dem Remote Computer weiterhin ununterbrochen ausgeführt, bis der Befehl abgeschlossen ist oder der Ausgabepuffer gefüllt wird.</span><span class="sxs-lookup"><span data-stu-id="3f51e-130">Commands in a disconnected PSSession continue to run uninterrupted on the remote computer until the command completes or the output buffer fills.</span></span> <span data-ttu-id="3f51e-131">Verwenden Sie den **outputbufferingmode** -Parameter der `Disconnect-PSSession` `New-PSSessionOption` Cmdlets, oder, um zu verhindern, dass ein vollständiger Ausgabepuffer einen Befehl angehalten `New-PSTransportOption` .</span><span class="sxs-lookup"><span data-stu-id="3f51e-131">To prevent a full output buffer from suspending a command, use the **OutputBufferingMode** parameter of the `Disconnect-PSSession`, `New-PSSessionOption`, or `New-PSTransportOption` cmdlets.</span></span>

<span data-ttu-id="3f51e-132">Getrennte Sitzungen werden auf dem Remote Computer im getrennten Zustand verwaltet.</span><span class="sxs-lookup"><span data-stu-id="3f51e-132">Disconnected sessions are maintained in the disconnected state on the remote computer.</span></span> <span data-ttu-id="3f51e-133">Sie können wieder hergestellt werden, bis Sie die PSSession löschen, z. b. mit dem `Remove-PSSession` Cmdlet, oder bis das Leerlauf Timeout der PSSession abläuft.</span><span class="sxs-lookup"><span data-stu-id="3f51e-133">They're available for you to reconnect, until you delete the PSSession, such as by using the `Remove-PSSession` cmdlet, or until the idle timeout of the PSSession expires.</span></span> <span data-ttu-id="3f51e-134">Sie können das Leerlauf Timeout einer PSSession anpassen, indem Sie die **idletimeoutsec** -oder **IdleTimeout** -Parameter der- `Disconnect-PSSession` ,-oder- `New-PSSessionOption` `New-PSTransportOption` Cmdlets verwenden.</span><span class="sxs-lookup"><span data-stu-id="3f51e-134">You can adjust the idle timeout of a PSSession by using the **IdleTimeoutSec** or **IdleTimeout** parameters of the `Disconnect-PSSession`, `New-PSSessionOption`, or `New-PSTransportOption` cmdlets.</span></span>

<span data-ttu-id="3f51e-135">Ein anderer Benutzer kann eine Verbindung mit pssessions herstellen, die Sie erstellt haben, aber nur, wenn Sie die Anmelde Informationen bereitstellen können, die zum Erstellen der Sitzung verwendet wurden, oder die `RunAs` Anmelde Informationen der Sitzungs Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="3f51e-135">Another user can connect to PSSessions that you created, but only if they can provide the credentials that were used to create the session, or use the `RunAs` credentials of the session configuration.</span></span>

## <a name="how-to-get-pssessions"></a><span data-ttu-id="3f51e-136">Vorgehensweise beim erhalten von pssessions</span><span class="sxs-lookup"><span data-stu-id="3f51e-136">How to get PSSessions</span></span>

<span data-ttu-id="3f51e-137">Ab PowerShell 3,0 `Get-PSSession` Ruft das Cmdlet pssessions auf dem lokalen Computer und Remote Computern ab.</span><span class="sxs-lookup"><span data-stu-id="3f51e-137">Beginning in PowerShell 3.0, the `Get-PSSession` cmdlet gets PSSessions on the local computer and remote computers.</span></span> <span data-ttu-id="3f51e-138">Sie kann auch pssessions erhalten, die in der aktuellen Sitzung erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="3f51e-138">It can also get PSSessions that were created in the current session.</span></span>

<span data-ttu-id="3f51e-139">Um pssessions auf dem lokalen Computer oder auf Remote Computern zu erhalten, verwenden Sie die Parameter **Computername** oder **ConnectionUri** .</span><span class="sxs-lookup"><span data-stu-id="3f51e-139">To get PSSessions on the local computer or remote computers, use the **ComputerName** or **ConnectionUri** parameters.</span></span> <span data-ttu-id="3f51e-140">Ohne Parameter ruft `Get-PSSession` die PSSession ab, die in der lokalen Sitzung erstellt wurde, unabhängig davon, wo Sie beendet werden.</span><span class="sxs-lookup"><span data-stu-id="3f51e-140">Without parameters, `Get-PSSession` gets PSSession that were created in the local session, regardless of where they terminate.</span></span>

<span data-ttu-id="3f51e-141">Beachten Sie beim erhalten von pssessions, dass Sie auf dem Computer, auf dem Sie gewartet haben,, d. h. auf dem Remote Computer oder dem **serverseitigen** Computer, nach diesen suchen.</span><span class="sxs-lookup"><span data-stu-id="3f51e-141">When getting PSSessions, remember to look for them on the computer on which they're maintained, that is, the remote or **server-side** computer.</span></span>

<span data-ttu-id="3f51e-142">Wenn Sie z. b. eine PSSession auf dem Server01-Computer erstellen, rufen Sie die Sitzung vom Server01-Computer ab.</span><span class="sxs-lookup"><span data-stu-id="3f51e-142">For example, if you create a PSSession to the Server01 computer, get the session from the Server01 computer.</span></span> <span data-ttu-id="3f51e-143">Wenn Sie eine PSSession von einem anderen Computer auf dem lokalen Computer erstellen, rufen Sie die Sitzung vom lokalen Computer ab.</span><span class="sxs-lookup"><span data-stu-id="3f51e-143">If you create a PSSession from another computer to the local computer, get the session from the local computer.</span></span>

<span data-ttu-id="3f51e-144">Die folgende Befehlssequenz zeigt, wie `Get-PSSession` funktioniert.</span><span class="sxs-lookup"><span data-stu-id="3f51e-144">The following command sequence shows how `Get-PSSession` works.</span></span>

<span data-ttu-id="3f51e-145">Der erste Befehl erstellt eine Sitzung für den Server01-Computer.</span><span class="sxs-lookup"><span data-stu-id="3f51e-145">The first command creates a session to the Server01 computer.</span></span> <span data-ttu-id="3f51e-146">Die Sitzung befindet sich auf dem Server01-Computer.</span><span class="sxs-lookup"><span data-stu-id="3f51e-146">The session resides on the Server01 computer.</span></span>

```powershell
New-PSSession -ComputerName Server01
```

```Output
Id Name      ComputerName  State    ConfigurationName     Availability
-- ----      ------------  -----    -----------------     ------------
 2 Session2  Server01      Opened   Microsoft.PowerShell     Available
```

<span data-ttu-id="3f51e-147">Um die Sitzung zu erhalten, verwenden Sie den **Computername** -Parameter von `Get-PSSession` mit dem Wert Server01.</span><span class="sxs-lookup"><span data-stu-id="3f51e-147">To get the session, use the **ComputerName** parameter of `Get-PSSession` with a value of Server01.</span></span>

```powershell
Get-PSSession -ComputerName Server01
```

```Output
Id Name      ComputerName  State    ConfigurationName     Availability
-- ----      ------------  -----    -----------------     ------------
 2 Session2  Server01      Opened   Microsoft.PowerShell     Available
```

<span data-ttu-id="3f51e-148">Wenn der Wert des **Computername** -Parameters von `Get-PSSession` localhost ist, ruft `Get-PSSession` pssessions ab, die bei und auf dem lokalen Computer verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="3f51e-148">If the value of the **ComputerName** parameter of `Get-PSSession` is localhost, `Get-PSSession` gets PSSessions that terminate at and are maintained on the local computer.</span></span> <span data-ttu-id="3f51e-149">Auf dem Server01-Computer werden keine pssessions angezeigt, auch wenn Sie auf dem lokalen Computer gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="3f51e-149">It doesn't get PSSessions on the Server01 computer, even if they were started on the local computer.</span></span>

```powershell
Get-PSSession -ComputerName localhost
```

<span data-ttu-id="3f51e-150">Verwenden Sie das `Get-PSSession` Cmdlet ohne Parameter, um Sitzungen zu erhalten, die in der aktuellen Sitzung erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="3f51e-150">To get sessions that were created in the current session, use the `Get-PSSession` cmdlet without parameters.</span></span> <span data-ttu-id="3f51e-151">In diesem Beispiel `Get-PSSession` wird die in der aktuellen Sitzung erstellte PSSession abgerufen und eine Verbindung mit dem Server01-Computer hergestellt.</span><span class="sxs-lookup"><span data-stu-id="3f51e-151">In this example, `Get-PSSession` gets the PSSession that was created in the current session and connects to the Server01 computer.</span></span>

```powershell
Get-PSSession
```

```Output
Id Name      ComputerName  State    ConfigurationName     Availability
-- ----      ------------  -----    -----------------     ------------
 2 Session2  Server01      Opened   Microsoft.PowerShell     Available
```

## <a name="how-to-disconnect-sessions"></a><span data-ttu-id="3f51e-152">Trennen von Sitzungen</span><span class="sxs-lookup"><span data-stu-id="3f51e-152">How to disconnect sessions</span></span>

<span data-ttu-id="3f51e-153">Um die Verbindung mit einer PSSession zu trennen, verwenden Sie das- `Disconnect-PSSession` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3f51e-153">To disconnect a PSSession, use the `Disconnect-PSSession` cmdlet.</span></span> <span data-ttu-id="3f51e-154">Um die PSSession zu identifizieren, verwenden Sie den **Session** -Parameter oder die Pipeline a PSSession aus den- `New-PSSession` oder- `Get-PSSession` Cmdlets für `Disconnect-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="3f51e-154">To identify the PSSession, use the **Session** parameter, or pipeline a PSSession from the `New-PSSession` or `Get-PSSession` cmdlets to `Disconnect-PSSession`.</span></span>

<span data-ttu-id="3f51e-155">Der folgende Befehl trennt die PSSession mit dem Server01-Computer.</span><span class="sxs-lookup"><span data-stu-id="3f51e-155">The following command disconnects the PSSession to the Server01 computer.</span></span>
<span data-ttu-id="3f51e-156">Beachten Sie, dass der Wert der **State** -Eigenschaft **getrennt** ist und die **Verfügbarkeit** **None** lautet.</span><span class="sxs-lookup"><span data-stu-id="3f51e-156">Notice that the value of the **State** property is **Disconnected** and the **Availability** is **None**.</span></span>

```powershell
Get-PSSession -ComputerName Server01 | Disconnect-PSSession
```

```Output
Id Name      ComputerName  State         ConfigurationName     Availability
-- ----      ------------  -----         -----------------     ------------
 2 Session2  Server01      Disconnected  Microsoft.PowerShell          None
```

<span data-ttu-id="3f51e-157">Um eine getrennte Sitzung zu erstellen, verwenden Sie den **indisconnectedsession** -Parameter des `Invoke-Command` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="3f51e-157">To create a disconnected session, use the **InDisconnectedSession** parameter of the `Invoke-Command` cmdlet.</span></span> <span data-ttu-id="3f51e-158">Er erstellt eine Sitzung, startet den Befehl und trennt sofort die Verbindung, bevor der Befehl eine beliebige Ausgabe zurückgeben kann.</span><span class="sxs-lookup"><span data-stu-id="3f51e-158">It creates a session, starts the command, and disconnects immediately, before the command can return any output.</span></span>

<span data-ttu-id="3f51e-159">Der folgende Befehl führt einen `Get-WinEvent` Befehl in einer getrennten Sitzung auf dem Remote Computer Server02 aus.</span><span class="sxs-lookup"><span data-stu-id="3f51e-159">The following command runs a `Get-WinEvent` command in a disconnected session on the Server02 remote computer.</span></span>

```powershell
Invoke-Command -ComputerName Server02 -InDisconnectedSession -ScriptBlock {
   Get-WinEvent -LogName "*PowerShell*" }
```

```Output
Id Name      ComputerName  State         ConfigurationName     Availability
-- ----      ------------  -----         -----------------     ------------
 4 Session3  Server02      Disconnected  Microsoft.PowerShell          None
```

## <a name="how-to-connect-to-disconnected-sessions"></a><span data-ttu-id="3f51e-160">Vorgehensweise beim Herstellen einer Verbindung mit getrennten Sitzungen</span><span class="sxs-lookup"><span data-stu-id="3f51e-160">How to connect to disconnected sessions</span></span>

<span data-ttu-id="3f51e-161">Sie können eine Verbindung mit einer beliebigen verfügbaren getrennten PSSession von der Sitzung aus herstellen, in der Sie die PSSession erstellt haben, oder aus anderen Sitzungen auf dem lokalen Computer oder auf anderen Computern.</span><span class="sxs-lookup"><span data-stu-id="3f51e-161">You can connect to any available disconnected PSSession from the session in which you created the PSSession or from other sessions on the local computer or other computers.</span></span>

<span data-ttu-id="3f51e-162">Sie können eine PSSession erstellen, Befehle in der PSSession ausführen, die Verbindung mit der PSSession trennen, PowerShell schließen und den Computer Herunterfahren.</span><span class="sxs-lookup"><span data-stu-id="3f51e-162">You can create a PSSession, run commands in the PSSession, disconnect from the PSSession, close PowerShell, and shut down the computer.</span></span> <span data-ttu-id="3f51e-163">Stunden später können Sie einen anderen Computer öffnen, die PSSession erhalten, eine Verbindung mit dem Computer herstellen und die Ergebnisse der Befehle erhalten, die in der PSSession ausgeführt wurden, während diese getrennt war.</span><span class="sxs-lookup"><span data-stu-id="3f51e-163">Hours later, you can open a different computer, get the PSSession, connect to it, and get the results of commands that ran in the PSSession while it was disconnected.</span></span> <span data-ttu-id="3f51e-164">Anschließend können Sie weitere Befehle in der Sitzung ausführen.</span><span class="sxs-lookup"><span data-stu-id="3f51e-164">Then you can run more commands in the session.</span></span>

<span data-ttu-id="3f51e-165">Verwenden Sie das-Cmdlet, um eine Verbindung mit einer getrennten PSSession herzustellen `Connect-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="3f51e-165">To connect a disconnected PSSession, use the `Connect-PSSession` cmdlet.</span></span> <span data-ttu-id="3f51e-166">Verwenden Sie die Parameter **Computername** oder **ConnectionUri** , um die PSSession oder Pipeline eine PSSession von `Get-PSSession` zu identifizieren `Connect-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="3f51e-166">Use the **ComputerName** or **ConnectionUri** parameters to identify the PSSession, or pipeline a PSSession from `Get-PSSession` to `Connect-PSSession`.</span></span>

<span data-ttu-id="3f51e-167">Mit dem folgenden Befehl werden die Sitzungen auf dem Computer Server02 abgerufen.</span><span class="sxs-lookup"><span data-stu-id="3f51e-167">The following command gets the sessions on the Server02 computer.</span></span> <span data-ttu-id="3f51e-168">Die Ausgabe enthält zwei getrennte Sitzungen, die beide verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="3f51e-168">The output includes two disconnected sessions, both of which are available.</span></span>

```powershell
Get-PSSession -ComputerName Server02
```

```Output
Id Name      ComputerName   State         ConfigurationName     Availability
-- ----      ------------   -----         -----------------     ------------
 2 Session2  juneb-srv8320  Disconnected  Microsoft.PowerShell          None
 4 Session3  juneb-srv8320  Disconnected  Microsoft.PowerShell          None
```

<span data-ttu-id="3f51e-169">Der folgende Befehl stellt eine Verbindung mit Session2 her.</span><span class="sxs-lookup"><span data-stu-id="3f51e-169">The following command connects to Session2.</span></span> <span data-ttu-id="3f51e-170">Die PSSession ist nun geöffnet und verfügbar.</span><span class="sxs-lookup"><span data-stu-id="3f51e-170">The PSSession is now open and available.</span></span>

```powershell
Connect-PSSession -ComputerName Server02 -Name Session2
```

```Output
Id Name      ComputerName    State    ConfigurationName     Availability
-- ----      ------------    -----    -----------------     ------------
 2 Session2  juneb-srv8320   Opened   Microsoft.PowerShell     Available
```

## <a name="how-to-get-the-results"></a><span data-ttu-id="3f51e-171">So erhalten Sie die Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="3f51e-171">How to get the results</span></span>

<span data-ttu-id="3f51e-172">Verwenden Sie zum erhalten der Ergebnisse von Befehlen, die in einer getrennten PSSession ausgeführt wurden, das- `Receive-PSSession` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3f51e-172">To get the results of commands that ran in a disconnected PSSession, use the `Receive-PSSession` cmdlet.</span></span>

<span data-ttu-id="3f51e-173">Sie können `Receive-PSSession` anstelle des- `Connect-PSSession` Cmdlets verwenden.</span><span class="sxs-lookup"><span data-stu-id="3f51e-173">You can use `Receive-PSSession` rather than using the `Connect-PSSession` cmdlet.</span></span> <span data-ttu-id="3f51e-174">Wenn die Sitzung bereits wieder verbunden ist, ruft `Receive-PSSession` die Ergebnisse von Befehlen ab, die beim Trennen der Sitzung ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="3f51e-174">If the session is already reconnected, `Receive-PSSession` gets the results of commands that ran when the session was disconnected.</span></span> <span data-ttu-id="3f51e-175">Wenn die PSSession weiterhin getrennt ist, stellt eine Verbindung mit der PSSession her `Receive-PSSession` und ruft dann die Ergebnisse von Befehlen ab, die während der Verbindungs Herstellung ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="3f51e-175">If the PSSession is still disconnected, `Receive-PSSession` connects to it and then gets the results of commands that ran while it was disconnected.</span></span>

<span data-ttu-id="3f51e-176">`Receive-PSSession` kann die Ergebnisse in einem Auftrag (asynchron) oder an das Host Programm (synchron) zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="3f51e-176">`Receive-PSSession` can return the results in a job (asynchronously) or to the host program (synchronously).</span></span> <span data-ttu-id="3f51e-177">Verwenden Sie den **outtarget** -Parameter, um den **Auftrag** oder den **Host** auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="3f51e-177">Use the **OutTarget** parameter to select **Job** or **Host**.</span></span> <span data-ttu-id="3f51e-178">Der Standardwert ist **Host**.</span><span class="sxs-lookup"><span data-stu-id="3f51e-178">The default value is **Host**.</span></span> <span data-ttu-id="3f51e-179">Wenn der empfangene Befehl jedoch in der aktuellen Sitzung als **Auftrag** gestartet wurde, wird er standardmäßig als **Auftrag** zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3f51e-179">However, if the command that's being received was started in the current session as a **Job**, it's returned as a **Job** by default.</span></span>

<span data-ttu-id="3f51e-180">Der folgende Befehl verwendet das `Receive-PSSession` Cmdlet, um eine Verbindung mit der PSSession auf dem Server02-Computer herzustellen und die Ergebnisse des `Get-WinEvent` Befehls abzurufen, der in der Session3-Sitzung ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="3f51e-180">The following command uses the `Receive-PSSession` cmdlet to connect to the PSSession on the Server02 computer and get the results of the `Get-WinEvent` command that ran in the Session3 session.</span></span> <span data-ttu-id="3f51e-181">Der Befehl verwendet den **outtarget** -Parameter, um die Ergebnisse in einem **Auftrag** zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="3f51e-181">The command uses the **OutTarget** parameter to get the results in a **Job**.</span></span>

```powershell
Receive-PSSession -ComputerName Server02 -Name Session3 -OutTarget Job
```

```Output
Id   Name   PSJobTypeName   State         HasMoreData     Location
--   ----   -------------   -----         -----------     --------
 3   Job3   RemoteJob       Running       True            Server02
```

<span data-ttu-id="3f51e-182">Verwenden Sie das-Cmdlet, um die Ergebnisse des Auftrags zu erhalten `Receive-Job` .</span><span class="sxs-lookup"><span data-stu-id="3f51e-182">To get the job's results, use the `Receive-Job` cmdlet.</span></span>

```powershell
Get-Job | Receive-Job -Keep
```

```Output
ProviderName: PowerShell

TimeCreated             Id LevelDisplayName Message     PSComputerName
-----------             -- ---------------- -------     --------------
5/14/2012 7:26:04 PM   400 Information      Engine stat Server02
5/14/2012 7:26:03 PM   600 Information      Provider "W Server02
5/14/2012 7:26:03 PM   600 Information      Provider "C Server02
5/14/2012 7:26:03 PM   600 Information      Provider "V Server02
```

## <a name="state-and-availability-properties"></a><span data-ttu-id="3f51e-183">Status-und Verfügbarkeits Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="3f51e-183">State and Availability properties</span></span>

<span data-ttu-id="3f51e-184">Die **Status** -und **Verfügbarkeits** Eigenschaften einer getrennten PSSession geben Aufschluss darüber, ob die Sitzung verfügbar ist, damit Sie erneut eine Verbindung herstellen können.</span><span class="sxs-lookup"><span data-stu-id="3f51e-184">The **State** and **Availability** properties of a disconnected PSSession tell you whether the session is available for you to reconnect to it.</span></span>

<span data-ttu-id="3f51e-185">Wenn eine PSSession mit der aktuellen Sitzung verbunden ist, wird Ihr Zustand **geöffnet** , und die Verfügbarkeit ist **verfügbar**.</span><span class="sxs-lookup"><span data-stu-id="3f51e-185">When a PSSession is connected to the current session, its state is **Opened** and its availability is **Available**.</span></span> <span data-ttu-id="3f51e-186">Wenn Sie die Verbindung mit der PSSession trennen, wird der PSSession-Status **getrennt** , und die Verfügbarkeit ist **None**.</span><span class="sxs-lookup"><span data-stu-id="3f51e-186">When you disconnect from the PSSession, the PSSession state is **Disconnected** and its availability is **None**.</span></span>

<span data-ttu-id="3f51e-187">Der Wert der **State** Eigenschaft bezieht sich auf die aktuelle Sitzung.</span><span class="sxs-lookup"><span data-stu-id="3f51e-187">The value of the **State** property is relative to the current session.</span></span> <span data-ttu-id="3f51e-188">Der Wert " **getrennt** " bedeutet, dass die PSSession nicht mit der aktuellen Sitzung verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="3f51e-188">A value of **Disconnected** means that the PSSession isn't connected to the current session.</span></span> <span data-ttu-id="3f51e-189">Dies bedeutet jedoch nicht, dass die PSSession von allen Sitzungen getrennt ist.</span><span class="sxs-lookup"><span data-stu-id="3f51e-189">But, it doesn't mean that the PSSession is disconnected from all sessions.</span></span> <span data-ttu-id="3f51e-190">Sie kann mit einer anderen Sitzung verbunden sein.</span><span class="sxs-lookup"><span data-stu-id="3f51e-190">It might be connected to a different session.</span></span>

<span data-ttu-id="3f51e-191">Verwenden Sie die **Availability** -Eigenschaft, um zu bestimmen, ob Sie eine Verbindung mit der PSSession herstellen oder eine Verbindung herstellen können.</span><span class="sxs-lookup"><span data-stu-id="3f51e-191">To determine whether you can connect or reconnect to the PSSession, use the **Availability** property.</span></span> <span data-ttu-id="3f51e-192">Der Wert **None** gibt an, dass Sie eine Verbindung mit der Sitzung herstellen können.</span><span class="sxs-lookup"><span data-stu-id="3f51e-192">A value of **None** indicates that you can connect to the session.</span></span> <span data-ttu-id="3f51e-193">Der Wert **ausgelastet** gibt an, dass keine Verbindung mit der PSSession hergestellt werden kann, da Sie mit einer anderen Sitzung verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="3f51e-193">A value of **Busy** indicates that you can't connect to the PSSession because it's connected to another session.</span></span>

<span data-ttu-id="3f51e-194">Das folgende Beispiel wird in zwei PowerShell-Sitzungen auf dem gleichen Computer ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="3f51e-194">The following example is run in two PowerShell sessions on the same computer.</span></span>
<span data-ttu-id="3f51e-195">Beachten Sie die geänderten Werte der **Zustands** -und **Verfügbarkeits** Eigenschaften in jeder Sitzung, wenn die PSSession getrennt und erneut verbunden wird.</span><span class="sxs-lookup"><span data-stu-id="3f51e-195">Note the changing values of the **State** and **Availability** properties in each session as the PSSession is disconnected and reconnected.</span></span>

```powershell
# Session 1
New-PSSession -ComputerName Server30 -Name Test
```

```Output
Id Name   ComputerName    State         ConfigurationName     Availability
-- ----   ------------    -----         -----------------     ------------
1  Test   Server30        Opened        Microsoft.PowerShell     Available
```

```powershell
# Session 2
Get-PSSession -ComputerName Server30 -Name Test
```

```Output
Id Name   ComputerName    State         ConfigurationName     Availability
-- ----   ------------    -----         -----------------     ------------
1 Test    Server30        Disconnected  Microsoft.PowerShell          Busy
```

```powershell
# Session 1
Get-PSSession -ComputerName Server30 -Name Test | Disconnect-PSSession
```

```Output
Id Name   ComputerName    State         ConfigurationName     Availability
-- ----   ------------    -----         -----------------     ------------
1 Test    Server30        Disconnected  Microsoft.PowerShell          None
```

```powershell
# Session 2
Get-PSSession -ComputerName Server30
```

```Output
Id Name   ComputerName    State         ConfigurationName     Availability
-- ----   ------------    -----         -----------------     ------------
1 Test    Server30        Disconnected  Microsoft.PowerShell          None
```

```powershell
# Session 2
Connect-PSSession -ComputerName Server30 -Name Test
```

```Output
Id Name   ComputerName    State         ConfigurationName     Availability
-- ----   ------------    -----         -----------------     ------------
3 Test    Server30        Opened        Microsoft.PowerShell     Available
```

```powershell
# Session 1
Get-PSSession -ComputerName Server30
```

```Output
Id Name   ComputerName    State         ConfigurationName     Availability
-- ----   ------------    -----         -----------------     ------------
1 Test    Server30        Disconnected  Microsoft.PowerShell          Busy
```

```Output
# Idle Timeout
```

<span data-ttu-id="3f51e-196">Getrennte Sitzungen werden auf dem Remote Computer beibehalten, bis Sie Sie löschen, z. b. mit dem `Remove-PSSession` Cmdlet, oder ein Timeout. Die **IdleTimeout** -Eigenschaft einer PSSession bestimmt, wie lange eine getrennte Sitzung beibehalten wird, bevor Sie gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="3f51e-196">Disconnected sessions are maintained on the remote computer until you delete them, such as by using the `Remove-PSSession` cmdlet, or they time out. The **IdleTimeout** property of a PSSession determines how long a disconnected session is maintained before it's deleted.</span></span>

<span data-ttu-id="3f51e-197">Pssessions befinden sich im Leerlauf, wenn der Takt **Thread** keine Antwort erhält.</span><span class="sxs-lookup"><span data-stu-id="3f51e-197">PSSessions are idle when the **heartbeat thread** receives no response.</span></span>
<span data-ttu-id="3f51e-198">Wenn eine Sitzung getrennt wird, wird Sie in den Leerlauf versetzt und die **IdleTimeout** -Uhr gestartet, auch wenn Befehle weiterhin in der getrennten Sitzung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="3f51e-198">Disconnecting a session makes it idle and starts the **IdleTimeout** clock, even if commands are still running in the disconnected session.</span></span> <span data-ttu-id="3f51e-199">PowerShell berücksichtigt, dass getrennte Sitzungen aktiv sind, aber im Leerlauf sind.</span><span class="sxs-lookup"><span data-stu-id="3f51e-199">PowerShell considers disconnected sessions to be active, but idle.</span></span>

<span data-ttu-id="3f51e-200">Vergewissern Sie sich beim Erstellen und trennen von Sitzungen, dass das Leerlauf Timeout in der PSSession lang genug ist, um die Sitzung für Ihre Anforderungen beizubehalten, aber nicht so lange, dass auf dem Remote Computer unnötige Ressourcen verbraucht werden.</span><span class="sxs-lookup"><span data-stu-id="3f51e-200">When creating and disconnecting sessions, verify that the idle timeout in the PSSession is long enough to maintain the session for your needs, but not so long that it consumes unnecessary resources on the remote computer.</span></span>

<span data-ttu-id="3f51e-201">Die **idletimeoutms** -Eigenschaft der Sitzungs Konfiguration bestimmt das standardmäßige Leerlauf Timeout von Sitzungen, die die Sitzungs Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="3f51e-201">The **IdleTimeoutMs** property of the session configuration determines the default idle timeout of sessions that use the session configuration.</span></span> <span data-ttu-id="3f51e-202">Sie können den Standardwert überschreiben, aber der Wert, den Sie verwenden, darf die **maxidletimeoutms** -Eigenschaft der Sitzungs Konfiguration nicht überschreiten.</span><span class="sxs-lookup"><span data-stu-id="3f51e-202">You can override the default value, but the value that you use can't exceed the **MaxIdleTimeoutMs** property of the session configuration.</span></span>

<span data-ttu-id="3f51e-203">Verwenden Sie das folgende Befehls Format, um den Wert der **idletimeoutms** -und **maxidletimeoutms** -Werte einer Sitzungs Konfiguration zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="3f51e-203">To find the value of the **IdleTimeoutMs** and **MaxIdleTimeoutMs** values of a session configuration, use the following command format.</span></span>

```powershell
Get-PSSessionConfiguration |
  Format-Table Name, IdleTimeoutMs, MaxIdleTimeoutMs
```

<span data-ttu-id="3f51e-204">Sie können den Standardwert in der Sitzungs Konfiguration überschreiben und das Leerlauf Timeout einer PSSession festlegen, wenn Sie eine PSSession erstellen, und wenn Sie die Verbindung trennen.</span><span class="sxs-lookup"><span data-stu-id="3f51e-204">You can override the default value in the session configuration and set the idle timeout of a PSSession when you create a PSSession and when you disconnect.</span></span>

<span data-ttu-id="3f51e-205">Wenn Sie Mitglied der Gruppe "Administratoren" auf dem Remote Computer sind, können Sie die **idletimeoutms** -Eigenschaft und die **maxidletimeoutms** -Eigenschaft der Sitzungs Konfigurationen erstellen und ändern.</span><span class="sxs-lookup"><span data-stu-id="3f51e-205">If you're a member of the Administrators group on the remote computer, you can create and change the **IdleTimeoutMs** and **MaxIdleTimeoutMs** properties of session configurations.</span></span>

## <a name="idle-timeout-values"></a><span data-ttu-id="3f51e-206">Leerlauf Timeout Werte</span><span class="sxs-lookup"><span data-stu-id="3f51e-206">Idle timeout values</span></span>

<span data-ttu-id="3f51e-207">Der Wert für das Leerlauf Timeout von Sitzungs Konfigurationen und Sitzungs Optionen beträgt Millisekunden.</span><span class="sxs-lookup"><span data-stu-id="3f51e-207">The idle timeout value of session configurations and session options is in milliseconds.</span></span> <span data-ttu-id="3f51e-208">Der Timeout Wert für die Leerlaufzeit von Sitzungen und Sitzungs Konfigurationsoptionen beträgt Sekunden.</span><span class="sxs-lookup"><span data-stu-id="3f51e-208">The idle timeout value of sessions and session configuration options is in seconds.</span></span>

<span data-ttu-id="3f51e-209">Sie können das Leerlauf Timeout einer PSSession festlegen, wenn Sie die PSSession (,) erstellen und die Verbindung mit der PSSession `New-PSSession` `Invoke-Command` trennen ( `Disconnect-PSSession` ).</span><span class="sxs-lookup"><span data-stu-id="3f51e-209">You can set the idle timeout of a PSSession when you create the PSSession (`New-PSSession`, `Invoke-Command`) and when you disconnect from it (`Disconnect-PSSession`).</span></span> <span data-ttu-id="3f51e-210">Sie können den **IdleTimeout** -Wert jedoch nicht ändern, wenn Sie eine Verbindung mit der PSSession ( `Connect-PSSession` ) herstellen oder Ergebnisse ( `Receive-PSSession` ) erhalten.</span><span class="sxs-lookup"><span data-stu-id="3f51e-210">However, you can't change the **IdleTimeout** value when you connect to the PSSession (`Connect-PSSession`) or get results (`Receive-PSSession`).</span></span>

<span data-ttu-id="3f51e-211">Die `Connect-PSSession` -und- `Receive-PSSession` Cmdlets verfügen über einen **sessionoption** -Parameter, der ein **sessionoption** -Objekt annimmt, z. b. ein vom `New-PSSessionOption` Cmdlet zurück gegebenes.</span><span class="sxs-lookup"><span data-stu-id="3f51e-211">The `Connect-PSSession` and `Receive-PSSession` cmdlets have a **SessionOption** parameter that takes a **SessionOption** object, such as one returned by the `New-PSSessionOption` cmdlet.</span></span> <span data-ttu-id="3f51e-212">Der **IdleTimeout** -Wert des **sessionoption** -Objekts und der **IdleTimeout** -Wert in der `$PSSessionOption` Preference-Variablen ändern nicht den Wert des **IdleTimeout** -Werts der PSSession in einem- `Connect-PSSession` oder- `Receive-PSSession` Befehl.</span><span class="sxs-lookup"><span data-stu-id="3f51e-212">The **IdleTimeout** value in **SessionOption** object and the **IdleTimeout** value in the `$PSSessionOption` preference variable don't change the value of the **IdleTimeout** of the PSSession in a `Connect-PSSession` or `Receive-PSSession` command.</span></span>

<span data-ttu-id="3f51e-213">Erstellen Sie eine Einstellungs Variable, um eine PSSession mit einem bestimmten Leerlauf Timeout Wert zu erstellen `$PSSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="3f51e-213">To create a PSSession with a particular idle timeout value, create a `$PSSessionOption` preference variable.</span></span> <span data-ttu-id="3f51e-214">Legen Sie den Wert der **IdleTimeout** -Eigenschaft auf den gewünschten Wert (in Millisekunden) fest.</span><span class="sxs-lookup"><span data-stu-id="3f51e-214">Set the value of the **IdleTimeout** property to the desired value (in milliseconds).</span></span>

<span data-ttu-id="3f51e-215">Beim Erstellen von pssessions haben die Werte in der `$PSSessionOption` Variablen Vorrang vor den Werten in der Sitzungs Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="3f51e-215">When you create PSSessions, the values in `$PSSessionOption` variable take precedence over the values in the session configuration.</span></span>

<span data-ttu-id="3f51e-216">Der folgende Befehl legt z. b. ein Leerlauf Timeout von 48 Stunden fest:</span><span class="sxs-lookup"><span data-stu-id="3f51e-216">For example, the following command sets an idle timeout of 48 hours:</span></span>

```powershell
$PSSessionOption = New-PSSessionOption -IdleTimeoutMSec 172800000
```

<span data-ttu-id="3f51e-217">Verwenden Sie den **idletimeoutmsec** -Parameter des Cmdlets, um eine PSSession mit einem bestimmten Leerlauf Timeout Wert zu erstellen `New-PSSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="3f51e-217">To create a PSSession with a particular idle timeout value, use the **IdleTimeoutMSec** parameter of the `New-PSSessionOption` cmdlet.</span></span> <span data-ttu-id="3f51e-218">Verwenden Sie dann die Session-Option im Wert des **sessionoption** -Parameters des `New-PSSession` - `Invoke-Command` Cmdlets oder des-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="3f51e-218">Then, use the session option in the value of the **SessionOption** parameter of the `New-PSSession` or `Invoke-Command` cmdlets.</span></span>

<span data-ttu-id="3f51e-219">Die beim Erstellen der Sitzung festgelegten Werte haben Vorrang vor den Werten, die in der `$PSSessionOption` Einstellungs Variablen und der Sitzungs Konfiguration festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="3f51e-219">The values set when creating the session take precedence over the values set in the `$PSSessionOption` preference variable and the session configuration.</span></span>

<span data-ttu-id="3f51e-220">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3f51e-220">For example:</span></span>

```powershell
$o = New-PSSessionOption -IdleTimeoutMSec 172800000
New-PSSession -SessionOption $o
```

<span data-ttu-id="3f51e-221">Verwenden Sie den **idletimeoutsec** -Parameter des Cmdlets, um das Leerlauf Timeout einer PSSession zu ändern, wenn die Verbindung getrennt wird `Disconnect-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="3f51e-221">To change the idle timeout of a PSSession when disconnecting, use the **IdleTimeoutSec** parameter of the `Disconnect-PSSession` cmdlet.</span></span>

<span data-ttu-id="3f51e-222">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3f51e-222">For example:</span></span>

```powershell
Disconnect-PSSession -IdleTimeoutSec 172800
```

<span data-ttu-id="3f51e-223">Zum Erstellen einer Sitzungs Konfiguration mit einem bestimmten Leerlauf Timeout und maximalem Leerlauf Timeout verwenden Sie die **idletimeoutsec** -Parameter und die **maxidletimeoutsec** -Parameter des `New-PSTransportOption` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="3f51e-223">To create a session configuration with a particular idle timeout and maximum idle timeout, use the **IdleTimeoutSec** and **MaxIdleTimeoutSec** parameters of the `New-PSTransportOption` cmdlet.</span></span> <span data-ttu-id="3f51e-224">Verwenden Sie dann die Option Transport im Wert des **Transportoption** -Parameters von `Register-PSSessionConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="3f51e-224">Then, use the transport option in the value of the **TransportOption** parameter of `Register-PSSessionConfiguration`.</span></span>

<span data-ttu-id="3f51e-225">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3f51e-225">For example:</span></span>

```powershell
$o = New-PSTransportOption -IdleTimeoutSec 172800 -MaxIdleTimeoutSec 259200
Register-PSSessionConfiguration -Name Test -TransportOption $o
```

<span data-ttu-id="3f51e-226">Verwenden Sie die **idletimeoutsec** -Parameter und die **maxidletimeoutsec** -Parameter des Cmdlets, um das standardmäßige Leerlauf Timeout und das maximale Leerlauf Timeout einer Sitzungs Konfiguration zu ändern `New-PSTransportOption` .</span><span class="sxs-lookup"><span data-stu-id="3f51e-226">To change the default idle timeout and maximum idle timeout of a session configuration, use the **IdleTimeoutSec** and **MaxIdleTimeoutSec** parameters of the `New-PSTransportOption` cmdlet.</span></span> <span data-ttu-id="3f51e-227">Verwenden Sie dann die Option Transport im Wert des **Transportoption** -Parameters von `Set-PSSessionConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="3f51e-227">Then, use the transport option in the value of the **TransportOption** parameter of `Set-PSSessionConfiguration`.</span></span>

<span data-ttu-id="3f51e-228">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3f51e-228">For example:</span></span>

```powershell
$o = New-PSTransportOption -IdleTimeoutSec 172800 -MaxIdleTimeoutSec 259200
Set-PSSessionConfiguration -Name Test -TransportOption $o
```

## <a name="output-buffering-mode"></a><span data-ttu-id="3f51e-229">Ausgabepuffer Modus</span><span class="sxs-lookup"><span data-stu-id="3f51e-229">Output buffering mode</span></span>

<span data-ttu-id="3f51e-230">Der Ausgabepuffer Modus einer PSSession bestimmt, wie die Befehlsausgabe verwaltet wird, wenn der Ausgabepuffer der PSSession voll ist.</span><span class="sxs-lookup"><span data-stu-id="3f51e-230">The output buffering mode of a PSSession determines how command output is managed when the output buffer of the PSSession is full.</span></span>

<span data-ttu-id="3f51e-231">In einer getrennten Sitzung bestimmt der Ausgabepuffer Modus effektiv, ob der Befehl weiter ausgeführt wird, während die Sitzung getrennt wird.</span><span class="sxs-lookup"><span data-stu-id="3f51e-231">In a disconnected session, the output buffering mode effectively determines whether the command continues to run while the session is disconnected.</span></span>

<span data-ttu-id="3f51e-232">Die gültigen Werte lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="3f51e-232">The valid values as follows:</span></span>

- <span data-ttu-id="3f51e-233">**Blockierung**:</span><span class="sxs-lookup"><span data-stu-id="3f51e-233">**Block**.</span></span> <span data-ttu-id="3f51e-234">Wenn der Ausgabepuffer voll ist, wird die Ausführung unterbrochen, bis der Puffer leer ist.</span><span class="sxs-lookup"><span data-stu-id="3f51e-234">When the output buffer is full, execution is suspended until the buffer is clear.</span></span> <span data-ttu-id="3f51e-235">Der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="3f51e-235">The default value.</span></span>
- <span data-ttu-id="3f51e-236">**Drop**.</span><span class="sxs-lookup"><span data-stu-id="3f51e-236">**Drop**.</span></span> <span data-ttu-id="3f51e-237">Wenn der Ausgabepuffer voll ist, wird die Ausführung fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="3f51e-237">When the output buffer is full, execution continues.</span></span> <span data-ttu-id="3f51e-238">Wenn eine neue Ausgabe generiert wird, wird die älteste Ausgabe verworfen.</span><span class="sxs-lookup"><span data-stu-id="3f51e-238">As new output is generated, the oldest output is discarded.</span></span>

<span data-ttu-id="3f51e-239">**Block** behält Daten bei, unterbricht jedoch möglicherweise den Befehl.</span><span class="sxs-lookup"><span data-stu-id="3f51e-239">**Block** preserves data, but might interrupt the command.</span></span> <span data-ttu-id="3f51e-240">Beim Wert **Drop** kann der Befehl abgeschlossen werden, obwohl Daten verloren gehen können.</span><span class="sxs-lookup"><span data-stu-id="3f51e-240">A value of **Drop** allows the command to complete, although data might be lost.</span></span> <span data-ttu-id="3f51e-241">Bei Verwendung des **Drop**-Werts wird die Befehlsausgabe an eine Datei auf dem Datenträger umgeleitet.</span><span class="sxs-lookup"><span data-stu-id="3f51e-241">When using the **Drop** value, redirect the command output to a file on disk.</span></span> <span data-ttu-id="3f51e-242">Dieser Wert wird für getrennte Sitzungen empfohlen.</span><span class="sxs-lookup"><span data-stu-id="3f51e-242">This value is recommended for disconnected sessions.</span></span>

<span data-ttu-id="3f51e-243">Die **outputbufferingmode** -Eigenschaft der Sitzungs Konfiguration bestimmt den Standardmodus für die Ausgabepufferung von Sitzungen, die die Sitzungs Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="3f51e-243">The **OutputBufferingMode** property of the session configuration determines the default output buffering mode of sessions that use the session configuration.</span></span>

<span data-ttu-id="3f51e-244">Um den Wert der Sitzungs Konfiguration für **outputbufferingmode** zu ermitteln, können Sie eines der folgenden Befehls Formate verwenden:</span><span class="sxs-lookup"><span data-stu-id="3f51e-244">To find a session configuration's value of the **OutputBufferingMode**, you can use either of the following command formats:</span></span>

```powershell
(Get-PSSessionConfiguration <ConfigurationName>).OutputBufferingMode
```

```powershell
Get-PSSessionConfiguration | Format-Table Name, OutputBufferingMode
```

<span data-ttu-id="3f51e-245">Sie können den Standardwert in der Sitzungs Konfiguration überschreiben und den Ausgabepuffer Modus einer PSSession festlegen, wenn Sie eine PSSession erstellen, wenn Sie die Verbindung trennen und wenn Sie die Verbindung wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="3f51e-245">You can override the default value in the session configuration and set the output buffering mode of a PSSession when you create a PSSession, when you disconnect, and when you reconnect.</span></span>

<span data-ttu-id="3f51e-246">Wenn Sie Mitglied der Gruppe "Administratoren" auf dem Remote Computer sind, können Sie den Modus für die Ausgabepufferung von Sitzungs Konfigurationen erstellen und ändern.</span><span class="sxs-lookup"><span data-stu-id="3f51e-246">If you're a member of the Administrators group on the remote computer, you can create and change the output buffering mode of session configurations.</span></span>

<span data-ttu-id="3f51e-247">Erstellen Sie eine Einstellungs Variable, in der  `$PSSessionOption` der Wert der **outputbufferingmode** -Eigenschaft **Drop** lautet, um eine PSSession mit dem Ausgabepuffer Modus "Drop" zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3f51e-247">To create a PSSession with an output buffering mode of **Drop**, create a `$PSSessionOption` preference variable in which the value of the **OutputBufferingMode** property is **Drop**.</span></span>

<span data-ttu-id="3f51e-248">Beim Erstellen von pssessions haben die Werte in der `$PSSessionOption` Variablen Vorrang vor den Werten in der Sitzungs Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="3f51e-248">When you create PSSessions, the values in `$PSSessionOption` variable take precedence over the values in the session configuration.</span></span>

<span data-ttu-id="3f51e-249">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3f51e-249">For example:</span></span>

```powershell
$PSSessionOption = New-PSSessionOption -OutputBufferingMode Drop
```

<span data-ttu-id="3f51e-250">Verwenden Sie zum Erstellen einer PSSession mit dem Ausgabepuffer Modus **Drop** den **outputbufferingmode** -Parameter des `New-PSSessionOption` Cmdlets, um eine Sitzungs Option mit dem Wert **Drop** zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3f51e-250">To create a PSSession with an output buffering mode of **Drop**, use the **OutputBufferingMode** parameter of the `New-PSSessionOption` cmdlet to create a session option with a value of **Drop**.</span></span> <span data-ttu-id="3f51e-251">Verwenden Sie dann die Session-Option im Wert des **sessionoption** -Parameters des `New-PSSession` - `Invoke-Command` Cmdlets oder des-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="3f51e-251">Then, use the session option in the value of the **SessionOption** parameter of the `New-PSSession` or `Invoke-Command` cmdlets.</span></span>

<span data-ttu-id="3f51e-252">Die beim Erstellen der Sitzung festgelegten Werte haben Vorrang vor den Werten, die in der `$PSSessionOption` Einstellungs Variablen und der Sitzungs Konfiguration festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="3f51e-252">The values set when creating the session take precedence over the values set in the `$PSSessionOption` preference variable and the session configuration.</span></span>

<span data-ttu-id="3f51e-253">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3f51e-253">For example:</span></span>

```powershell
$o = New-PSSessionOption -OutputBufferingMode Drop
New-PSSession -SessionOption $o
```

<span data-ttu-id="3f51e-254">Verwenden Sie den **outputbufferingmode** -Parameter des Cmdlets, um beim Trennen der Verbindung den Ausgabepuffer Modus einer PSSession zu ändern `Disconnect-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="3f51e-254">To change the output buffering mode of a PSSession when disconnecting, use the **OutputBufferingMode** parameter of the `Disconnect-PSSession` cmdlet.</span></span>

<span data-ttu-id="3f51e-255">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3f51e-255">For example:</span></span>

```powershell
Disconnect-PSSession -OutputBufferingMode Drop
```

<span data-ttu-id="3f51e-256">Verwenden Sie den **outputbufferingmode** -Parameter des `New-PSSessionOption` Cmdlets, um beim erneuten Herstellen der Verbindung den Ausgabepuffer Modus einer PSSession zu ändern. </span><span class="sxs-lookup"><span data-stu-id="3f51e-256">To change the output buffering mode of a PSSession when reconnecting, use the **OutputBufferingMode** parameter of the `New-PSSessionOption` cmdlet to create a session option with a value of **Drop**.</span></span> <span data-ttu-id="3f51e-257">Verwenden Sie dann die Session-Option im Wert des **sessionoption** -Parameters `Connect-PSSession` von `Receive-PSSession` oder.</span><span class="sxs-lookup"><span data-stu-id="3f51e-257">Then, use the session option in the value of the **SessionOption** parameter of `Connect-PSSession` or `Receive-PSSession`.</span></span>

<span data-ttu-id="3f51e-258">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3f51e-258">For example:</span></span>

```powershell
$o = New-PSSessionOption -OutputBufferingMode Drop
Connect-PSSession -ComputerName Server01 -Name Test -SessionOption $o
```

<span data-ttu-id="3f51e-259">Zum Erstellen einer Sitzungs Konfiguration mit einem standardmäßigen Ausgabepuffer Modus von **Drop** verwenden Sie den **outputbufferingmode** -Parameter des `New-PSTransportOption` Cmdlets, um ein Transport Options Objekt mit dem Wert **Drop** zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3f51e-259">To create a session configuration with a default output buffering mode of **Drop**, use the **OutputBufferingMode** parameter of the `New-PSTransportOption` cmdlet to create a transport option object with a value of **Drop**.</span></span> <span data-ttu-id="3f51e-260">Verwenden Sie dann die Option Transport im Wert des **Transportoption** -Parameters von `Register-PSSessionConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="3f51e-260">Then, use the transport option in the value of the **TransportOption** parameter of `Register-PSSessionConfiguration`.</span></span>

<span data-ttu-id="3f51e-261">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3f51e-261">For example:</span></span>

```powershell
$o = New-PSTransportOption -OutputBufferingMode Drop
Register-PSSessionConfiguration -Name Test -TransportOption $o
```

<span data-ttu-id="3f51e-262">Um den standardmäßigen Ausgabepuffer Modus einer Sitzungs Konfiguration zu ändern, verwenden Sie den **outputbufferingmode** -Parameter des `New-PSTransportOption` Cmdlets, um eine Transport Option mit dem Wert " **Drop**" zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3f51e-262">To change the default output buffering mode of a session configuration, use the **OutputBufferingMode** parameter of the `New-PSTransportOption` cmdlet to create a transport option with a value of **Drop**.</span></span> <span data-ttu-id="3f51e-263">Verwenden Sie dann die Option Transport im Wert des **sessionoption** -Parameters von `Set-PSSessionConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="3f51e-263">Then, use the Transport option in the value of the **SessionOption** parameter of `Set-PSSessionConfiguration`.</span></span>

<span data-ttu-id="3f51e-264">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3f51e-264">For example:</span></span>

```powershell
$o = New-PSTransportOption -OutputBufferingMode Drop
Set-PSSessionConfiguration -Name Test -TransportOption $o
```

## <a name="disconnecting-loopback-sessions"></a><span data-ttu-id="3f51e-265">Trennen von Loopback Sitzungen</span><span class="sxs-lookup"><span data-stu-id="3f51e-265">Disconnecting loopback sessions</span></span>

<span data-ttu-id="3f51e-266">Loopback Sitzungen oder lokale Sitzungen sind pssessions, die auf demselben Computer gestartet und beendet werden.</span><span class="sxs-lookup"><span data-stu-id="3f51e-266">Loopback sessions, or local sessions, are PSSessions that originate and terminate on the same computer.</span></span> <span data-ttu-id="3f51e-267">Wie andere pssessions werden aktive Loopback Sitzungen auf dem Computer am Remote Ende der Verbindung (dem lokalen Computer) beibehalten, sodass Sie die Verbindung mit Loopback Sitzungen trennen und wiederherstellen können.</span><span class="sxs-lookup"><span data-stu-id="3f51e-267">Like other PSSessions, active loopback sessions are maintained on the computer on the remote end of the connection (the local computer), so you can disconnect from and reconnect to loopback sessions.</span></span>

<span data-ttu-id="3f51e-268">Standardmäßig werden Loopback Sitzungen mit einem Netzwerk Sicherheits Token erstellt, das nicht zulässt, dass Befehle, die in der Sitzung ausgeführt werden, auf andere Computer zugreifen.</span><span class="sxs-lookup"><span data-stu-id="3f51e-268">By default, loopback sessions are created with a network security token that doesn't permit commands run in the session to access other computers.</span></span> <span data-ttu-id="3f51e-269">Sie können erneut eine Verbindung mit Loopback Sitzungen herstellen, die über ein Netzwerk Sicherheits Token aus einer beliebigen Sitzung auf dem lokalen Computer oder einem Remote Computer verfügen.</span><span class="sxs-lookup"><span data-stu-id="3f51e-269">You can reconnect to loopback sessions that have a network security token from any session on the local computer or a remote computer.</span></span>

<span data-ttu-id="3f51e-270">Wenn Sie jedoch den **enablenetworkaccess** -Parameter des `New-PSSession` `Enter-PSSession` `Invoke-Command` Cmdlets, oder verwenden, wird die Loopback Sitzung mit einem interaktiven Sicherheits Token erstellt.</span><span class="sxs-lookup"><span data-stu-id="3f51e-270">However, if you use the **EnableNetworkAccess** parameter of the `New-PSSession`, `Enter-PSSession`, or `Invoke-Command` cmdlet, the loopback session is created with an interactive security token.</span></span> <span data-ttu-id="3f51e-271">Mit dem interaktiven Token können Befehle, die in der Loopback Sitzung ausgeführt werden, Daten von anderen Computern erhalten.</span><span class="sxs-lookup"><span data-stu-id="3f51e-271">The interactive token enables commands that run in the loopback session to get data from other computers.</span></span>

<span data-ttu-id="3f51e-272">Sie können Loopback Sitzungen mit interaktiven Token trennen und dann aus derselben Sitzung oder einer anderen Sitzung auf demselben Computer erneut eine Verbindung mit Ihnen herstellen.</span><span class="sxs-lookup"><span data-stu-id="3f51e-272">You can disconnect loopback sessions with interactive tokens and then reconnect to them from the same session or a different session on the same computer.</span></span>
<span data-ttu-id="3f51e-273">Um böswilligen Zugriff zu verhindern, können Sie jedoch nur über den Computer, auf dem Sie erstellt wurden, eine erneute Verbindung mit Loopback Sitzungen mit interaktiven Tokens herstellen.</span><span class="sxs-lookup"><span data-stu-id="3f51e-273">However, to prevent malicious access, you can reconnect to loopback sessions with interactive tokens only from the computer on which they were created.</span></span>

## <a name="waiting-for-jobs-in-disconnected-sessions"></a><span data-ttu-id="3f51e-274">Warten auf Aufträge in getrennten Sitzungen</span><span class="sxs-lookup"><span data-stu-id="3f51e-274">Waiting for jobs in disconnected sessions</span></span>

<span data-ttu-id="3f51e-275">Das `Wait-Job` -Cmdlet wartet, bis ein Auftrag abgeschlossen ist, und kehrt dann zur Eingabeaufforderung oder zum nächsten Befehl zurück.</span><span class="sxs-lookup"><span data-stu-id="3f51e-275">The `Wait-Job` cmdlet waits until a job completes and then returns to the command prompt or the next command.</span></span> <span data-ttu-id="3f51e-276">Standardmäßig wird von zurückgegeben, `Wait-Job` Wenn die Sitzung, in der ein Auftrag ausgeführt wird, getrennt ist.</span><span class="sxs-lookup"><span data-stu-id="3f51e-276">By default, `Wait-Job` returns if the session in which a job is running is disconnected.</span></span> <span data-ttu-id="3f51e-277">Verwenden Sie den Force-Parameter, um das `Wait-Job` Cmdlet zu warten, bis die Verbindung wieder hergestellt wird, und verwenden Sie den **Force** -Parameter im **geöffneten** Zustand.</span><span class="sxs-lookup"><span data-stu-id="3f51e-277">To direct the `Wait-Job` cmdlet to wait until the session is reconnected, in the **Opened** state, use the **Force** parameter.</span></span> <span data-ttu-id="3f51e-278">Weitere Informationen finden Sie unter [Wait-Job](xref:Microsoft.PowerShell.Core.Wait-Job).</span><span class="sxs-lookup"><span data-stu-id="3f51e-278">For more information, see [Wait-Job](xref:Microsoft.PowerShell.Core.Wait-Job).</span></span>

## <a name="robust-sessions-and-unintentional-disconnection"></a><span data-ttu-id="3f51e-279">Robuste Sitzungen und unbeabsichtigte Trennung</span><span class="sxs-lookup"><span data-stu-id="3f51e-279">Robust sessions and unintentional disconnection</span></span>

<span data-ttu-id="3f51e-280">Eine PSSession kann aufgrund eines Computerfehlers oder Netzwerkausfalls versehentlich getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="3f51e-280">A PSSession might be unintentionally disconnected because of a computer failure or network outage.</span></span> <span data-ttu-id="3f51e-281">PowerShell versucht, die PSSession wiederherzustellen, der Erfolg hängt jedoch vom Schweregrad und der Dauer der Ursache ab.</span><span class="sxs-lookup"><span data-stu-id="3f51e-281">PowerShell attempts to recover the PSSession, but its success depends upon the severity and duration of the cause.</span></span>

<span data-ttu-id="3f51e-282">Der Status einer versehentlich getrennten PSSession ist möglicherweise **beschädigt** oder **geschlossen**, aber Sie kann auch **getrennt** werden.</span><span class="sxs-lookup"><span data-stu-id="3f51e-282">The state of an unintentionally disconnected PSSession might be **Broken** or **Closed**, but it might also be **Disconnected**.</span></span> <span data-ttu-id="3f51e-283">Wenn der Wert des **Zustands** **getrennt** ist, können Sie die gleichen Verfahren zum Verwalten der PSSession verwenden, wie dies bei einer absichtlichen Trennung der Sitzung der Fall wäre.</span><span class="sxs-lookup"><span data-stu-id="3f51e-283">If the value of **State** is **Disconnected**, you can use the same techniques to manage the PSSession as you would if the session were disconnected intentionally.</span></span> <span data-ttu-id="3f51e-284">Beispielsweise können Sie mit dem `Connect-PSSession` Cmdlet erneut eine Verbindung mit der Sitzung herstellen und das `Receive-PSSession` Cmdlet zum erhalten der Ergebnisse von Befehlen, die während der Verbindungs Trennung der Sitzung ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="3f51e-284">For example, you can use the `Connect-PSSession` cmdlet to reconnect to the session and the `Receive-PSSession` cmdlet to get results of commands that ran while the session was disconnected.</span></span>

<span data-ttu-id="3f51e-285">Wenn Sie die Sitzung schließen (Beenden), in der eine PSSession erstellt wurde, während Befehle in der PSSession ausgeführt werden, verwaltet PowerShell die PSSession auf dem Remote Computer im **getrennten** Zustand.</span><span class="sxs-lookup"><span data-stu-id="3f51e-285">If you close (exit) the session in which a PSSession was created while commands are running in the PSSession, PowerShell maintains the PSSession in the **Disconnected** state on the remote computer.</span></span> <span data-ttu-id="3f51e-286">Wenn Sie die Sitzung schließen (Beenden), in der eine PSSession erstellt wurde, aber keine Befehle in der PSSession ausgeführt werden, versucht PowerShell nicht, die PSSession beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="3f51e-286">If you close (exit) the session in which a PSSession was created, but no commands are running in the PSSession, PowerShell doesn't attempt to maintain the PSSession.</span></span>

## <a name="see-also"></a><span data-ttu-id="3f51e-287">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3f51e-287">See also</span></span>

[<span data-ttu-id="3f51e-288">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="3f51e-288">about_Jobs</span></span>](about_Jobs.md)

[<span data-ttu-id="3f51e-289">about_Remote</span><span class="sxs-lookup"><span data-stu-id="3f51e-289">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="3f51e-290">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="3f51e-290">about_Remote_Variables</span></span>](about_Remote_Variables.md)

[<span data-ttu-id="3f51e-291">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="3f51e-291">about_PSSessions</span></span>](about_PSSessions.md)

[<span data-ttu-id="3f51e-292">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="3f51e-292">about_Session_Configurations</span></span>](about_Session_Configurations.md)

[<span data-ttu-id="3f51e-293">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="3f51e-293">Connect-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Connect-PSSession)

[<span data-ttu-id="3f51e-294">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="3f51e-294">Disconnect-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Disconnect-PSSession)

[<span data-ttu-id="3f51e-295">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="3f51e-295">Get-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Get-PSSession)

[<span data-ttu-id="3f51e-296">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="3f51e-296">Receive-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Receive-PSSession)

[<span data-ttu-id="3f51e-297">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="3f51e-297">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)

