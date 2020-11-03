---
description: Beschreibt das Ausführen von Remote Befehlen in PowerShell.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote
ms.openlocfilehash: 04c297f849a30ddabecec98a5a2250b8d9b3fbfa
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221295"
---
# <a name="about-remote"></a><span data-ttu-id="e7e45-104">Informationen über Remote</span><span class="sxs-lookup"><span data-stu-id="e7e45-104">About Remote</span></span>

## <a name="short-description"></a><span data-ttu-id="e7e45-105">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e7e45-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="e7e45-106">Beschreibt das Ausführen von Remote Befehlen in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e7e45-106">Describes how to run remote commands in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="e7e45-107">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e7e45-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="e7e45-108">Sie können Remote Befehle auf einem einzelnen Computer oder auf mehreren Computern mithilfe einer temporären oder permanenten Verbindung ausführen.</span><span class="sxs-lookup"><span data-stu-id="e7e45-108">You can run remote commands on a single computer or on multiple computers by using a temporary or persistent connection.</span></span> <span data-ttu-id="e7e45-109">Sie können auch eine interaktive Sitzung mit einem einzelnen Remote Computer starten.</span><span class="sxs-lookup"><span data-stu-id="e7e45-109">You can also start an interactive session with a single remote computer.</span></span>

<span data-ttu-id="e7e45-110">Dieses Thema enthält eine Reihe von Beispielen, die Ihnen zeigen, wie verschiedene Arten von Remote Befehlen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e7e45-110">This topic provides a series of examples to show you how to run different types of remote command.</span></span> <span data-ttu-id="e7e45-111">Nachdem Sie diese grundlegenden Befehle ausprobiert haben, lesen Sie die Hilfe Themen, in denen die einzelnen Cmdlets beschrieben werden, die in diesen Befehlen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e7e45-111">After you try these basic commands, read the Help topics that describe each cmdlet that is used in these commands.</span></span> <span data-ttu-id="e7e45-112">In den Themen werden die Details erläutert und erläutert, wie Sie die Befehle entsprechend Ihren Anforderungen ändern können.</span><span class="sxs-lookup"><span data-stu-id="e7e45-112">The topics provide the details and explain how you can modify the commands to meet your needs.</span></span>

<span data-ttu-id="e7e45-113">Hinweis: für die Verwendung von PowerShell-Remoting müssen lokale Computer und Remote Computer für Remoting konfiguriert sein.</span><span class="sxs-lookup"><span data-stu-id="e7e45-113">Note: To use PowerShell remoting, the local and remote computers must be configured for remoting.</span></span> <span data-ttu-id="e7e45-114">Weitere Informationen finden Sie unter [about_Remote_Requirements](about_Remote_Requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7e45-114">For more information, see [about_Remote_Requirements](about_Remote_Requirements.md).</span></span>

## <a name="how-to-start-an-interactive-session-enter-pssession"></a><span data-ttu-id="e7e45-115">Starten einer interaktiven Sitzung (Enter-PSSession)</span><span class="sxs-lookup"><span data-stu-id="e7e45-115">HOW TO START AN INTERACTIVE SESSION (ENTER-PSSESSION)</span></span>

<span data-ttu-id="e7e45-116">Die einfachste Möglichkeit zum Ausführen von Remote Befehlen besteht darin, eine interaktive Sitzung mit einem Remote Computer zu starten.</span><span class="sxs-lookup"><span data-stu-id="e7e45-116">The easiest way to run remote commands is to start an interactive session with a remote computer.</span></span>

<span data-ttu-id="e7e45-117">Wenn die Sitzung gestartet wird, werden die Befehle, die Sie eingeben, auf dem Remote Computer ausgeführt, so als würden Sie Sie direkt auf dem Remote Computer eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="e7e45-117">When the session starts, the commands that you type run on the remote computer, just as though you typed them directly on the remote computer.</span></span> <span data-ttu-id="e7e45-118">Sie können in jeder interaktiven Sitzung nur eine Verbindung mit einem Computer herstellen.</span><span class="sxs-lookup"><span data-stu-id="e7e45-118">You can connect to only one computer in each interactive session.</span></span>

<span data-ttu-id="e7e45-119">Verwenden Sie das Cmdlet "Enter-PSSession", um eine interaktive Sitzung zu starten.</span><span class="sxs-lookup"><span data-stu-id="e7e45-119">To start an interactive session, use the Enter-PSSession cmdlet.</span></span> <span data-ttu-id="e7e45-120">Der folgende Befehl startet eine interaktive Sitzung mit dem Computer Server01:</span><span class="sxs-lookup"><span data-stu-id="e7e45-120">The following command starts an interactive session with the Server01 computer:</span></span>

```powershell
Enter-PSSession Server01
```

<span data-ttu-id="e7e45-121">Die Eingabeaufforderung ändert sich, um anzugeben, dass Sie mit dem Server01-Computer verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="e7e45-121">The command prompt changes to indicate that you are connected to the Server01 computer.</span></span>

```
Server01\PS>
```

<span data-ttu-id="e7e45-122">Nun können Sie Befehle auf dem Server01-Computer eingeben.</span><span class="sxs-lookup"><span data-stu-id="e7e45-122">Now, you can type commands on the Server01 computer.</span></span>

<span data-ttu-id="e7e45-123">Um die interaktive Sitzung zu beenden, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="e7e45-123">To end the interactive session, type:</span></span>

```powershell
Exit-PSSession
```

<span data-ttu-id="e7e45-124">Weitere Informationen finden Sie unter Enter-PSSession.</span><span class="sxs-lookup"><span data-stu-id="e7e45-124">For more information, see Enter-PSSession.</span></span>

## <a name="how-to-use-cmdlets-that-have-a-computername-parameter-to-get-remote-data"></a><span data-ttu-id="e7e45-125">Verwenden von Cmdlets, die über einen Computername-Parameter verfügen, um Remote Daten zu erhalten</span><span class="sxs-lookup"><span data-stu-id="e7e45-125">HOW TO USE CMDLETS THAT HAVE A COMPUTERNAME PARAMETER TO GET REMOTE DATA</span></span>

<span data-ttu-id="e7e45-126">Mehrere Cmdlets verfügen über einen Computername-Parameter, mit dem Sie Objekte von Remote Computern erhalten können.</span><span class="sxs-lookup"><span data-stu-id="e7e45-126">Several cmdlets have a ComputerName parameter that lets you get objects from remote computers.</span></span>

<span data-ttu-id="e7e45-127">Da diese Cmdlets keine WS-Management-basierten PowerShell-Remoting verwenden, können Sie den Computername-Parameter dieser Cmdlets auf allen Computern verwenden, auf denen PowerShell ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e7e45-127">Because these cmdlets do not use WS-Management-based PowerShell remoting, you can use the ComputerName parameter of these cmdlets on any computer that is running PowerShell.</span></span> <span data-ttu-id="e7e45-128">Die Computer müssen nicht für PowerShell-Remoting konfiguriert werden, und die Computer müssen die Systemanforderungen für Remoting nicht erfüllen.</span><span class="sxs-lookup"><span data-stu-id="e7e45-128">The computers do not have to be configured for PowerShell remoting, and the computers do not have to meet the system requirements for remoting.</span></span>

<span data-ttu-id="e7e45-129">Die folgenden Cmdlets verfügen über einen Computername-Parameter:</span><span class="sxs-lookup"><span data-stu-id="e7e45-129">The following cmdlets have a ComputerName parameter:</span></span>

```
Clear-EventLog    Limit-EventLog
Get-Counter       New-EventLog
Get-EventLog      Remove-EventLog
Get-HotFix        Restart-Computer
Get-Process       Show-EventLog
Get-Service       Stop-Computer
Get-WinEvent      Test-Connection
Get-WmiObject     Write-EventLog
```

<span data-ttu-id="e7e45-130">Mit dem folgenden Befehl werden z. b. die Dienste auf dem Remote Computer Server01 abgerufen:</span><span class="sxs-lookup"><span data-stu-id="e7e45-130">For example, the following command gets the services on the Server01 remote computer:</span></span>

```powershell
Get-Service -ComputerName Server01
```

<span data-ttu-id="e7e45-131">Cmdlets, die Remoting ohne besondere Konfiguration unterstützen, verfügen in der Regel über einen **Computername** -Parameter und verfügen nicht über einen **Session** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="e7e45-131">Typically, cmdlets that support remoting without special configuration have a **ComputerName** parameter and do not have a **Session** parameter.</span></span> <span data-ttu-id="e7e45-132">Um diese Cmdlets in Ihrer Sitzung zu finden, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="e7e45-132">To find these cmdlets in your session, type:</span></span>

```powershell
Get-Command | Where-Object {
  $_.Parameters.Keys -contains 'ComputerName' -and
  $_.Parameters.Keys -notcontains 'Session'
}
```

## <a name="how-to-run-a-remote-command"></a><span data-ttu-id="e7e45-133">Ausführen eines Remote Befehls</span><span class="sxs-lookup"><span data-stu-id="e7e45-133">HOW TO RUN A REMOTE COMMAND</span></span>

<span data-ttu-id="e7e45-134">Verwenden Sie das Cmdlet "Invoke-Command", um andere Befehle auf Remote Computern auszuführen.</span><span class="sxs-lookup"><span data-stu-id="e7e45-134">To run other commands on remote computers, use the Invoke-Command cmdlet.</span></span>

<span data-ttu-id="e7e45-135">Um einen einzelnen Befehl oder einige nicht verknüpfte Befehle auszuführen, verwenden Sie den Computername-Parameter von Invoke-Command, um die Remote Computer anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e7e45-135">To run a single command or a few unrelated commands, use the ComputerName parameter of Invoke-Command to specify the remote computers.</span></span> <span data-ttu-id="e7e45-136">Verwenden Sie den ScriptBlock-Parameter, um den Befehl anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e7e45-136">Use the ScriptBlock parameter to specify the command.</span></span>

<span data-ttu-id="e7e45-137">Der folgende Befehl führt z. b. einen Get-Culture Befehl auf dem Server01-Computer aus.</span><span class="sxs-lookup"><span data-stu-id="e7e45-137">For example, the following command runs a Get-Culture command on the Server01 computer.</span></span>

```powershell
Invoke-Command -ComputerName Server01 -ScriptBlock {Get-Culture}
```

<span data-ttu-id="e7e45-138">Der Computername-Parameter ist für Situationen vorgesehen, in denen Sie einen einzelnen Befehl oder mehrere nicht verknüpfte Befehle auf einem oder mehreren Computern ausführen.</span><span class="sxs-lookup"><span data-stu-id="e7e45-138">The ComputerName parameter is designed for situation in which you run a single command or several unrelated commands on one or many computers.</span></span> <span data-ttu-id="e7e45-139">Verwenden Sie den Session-Parameter, um eine permanente Verbindung mit einem Remote Computer herzustellen.</span><span class="sxs-lookup"><span data-stu-id="e7e45-139">To establish a persistent connection to a remote computer, use the Session parameter.</span></span>

## <a name="how-to-create-a-persistent-connection-pssession"></a><span data-ttu-id="e7e45-140">Erstellen einer permanenten Verbindung (PSSession)</span><span class="sxs-lookup"><span data-stu-id="e7e45-140">HOW TO CREATE A PERSISTENT CONNECTION (PSSESSION)</span></span>

<span data-ttu-id="e7e45-141">Wenn Sie den Computername-Parameter des Cmdlets "Invoke-Command" verwenden, stellt Windows PowerShell eine Verbindung nur für den Befehl her.</span><span class="sxs-lookup"><span data-stu-id="e7e45-141">When you use the ComputerName parameter of the Invoke-Command cmdlet, Windows PowerShell establishes a connection just for the command.</span></span> <span data-ttu-id="e7e45-142">Anschließend wird die Verbindung nach Abschluss des Befehls geschlossen.</span><span class="sxs-lookup"><span data-stu-id="e7e45-142">Then, it closes the connection when the command is complete.</span></span> <span data-ttu-id="e7e45-143">Alle Variablen oder Funktionen, die im Befehl definiert sind, gehen verloren.</span><span class="sxs-lookup"><span data-stu-id="e7e45-143">Any variables or functions that are defined in the command are lost.</span></span>

<span data-ttu-id="e7e45-144">Verwenden Sie das Cmdlet "New-PSSession", um eine permanente Verbindung mit einem Remote Computer herzustellen.</span><span class="sxs-lookup"><span data-stu-id="e7e45-144">To create a persistent connection to a remote computer, use the New-PSSession cmdlet.</span></span> <span data-ttu-id="e7e45-145">Beispielsweise werden mit dem folgenden Befehl pssessions auf den Computern Server01 und Server02 erstellt und dann die pssessions in der $s Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="e7e45-145">For example, the following command creates PSSessions on the Server01 and Server02 computers and then saves the PSSessions in the $s variable.</span></span>

```powershell
$s = New-PSSession -ComputerName Server01, Server02
```

## <a name="how-to-run-commands-in-a-pssession"></a><span data-ttu-id="e7e45-146">Ausführen von Befehlen in einer PSSession</span><span class="sxs-lookup"><span data-stu-id="e7e45-146">HOW TO RUN COMMANDS IN A PSSESSION</span></span>

<span data-ttu-id="e7e45-147">Mit einer PSSession können Sie eine Reihe von Remote Befehlen ausführen, die Daten gemeinsam nutzen, wie z. b. Funktionen, Aliase und die Werte von Variablen.</span><span class="sxs-lookup"><span data-stu-id="e7e45-147">With a PSSession, you can run a series of remote commands that share data, like functions, aliases, and the values of variables.</span></span> <span data-ttu-id="e7e45-148">Verwenden Sie zum Ausführen von Befehlen in einer PSSession den Session-Parameter des Cmdlets "Invoke-Command".</span><span class="sxs-lookup"><span data-stu-id="e7e45-148">To run commands in a PSSession, use the Session parameter of the Invoke-Command cmdlet.</span></span>

<span data-ttu-id="e7e45-149">Der folgende Befehl verwendet z. b. das Invoke-Command-Cmdlet, um einen Get-Process-Befehl in den pssessions auf den Computern Server01 und Server02 auszuführen.</span><span class="sxs-lookup"><span data-stu-id="e7e45-149">For example, the following command uses the Invoke-Command cmdlet to run a Get-Process command in the PSSessions on the Server01 and Server02 computers.</span></span>
<span data-ttu-id="e7e45-150">Der Befehl speichert die Prozesse in einer $p Variablen in jeder PSSession.</span><span class="sxs-lookup"><span data-stu-id="e7e45-150">The command saves the processes in a $p variable in each PSSession.</span></span>

```powershell
Invoke-Command -Session $s -ScriptBlock {$p = Get-Process}
```

<span data-ttu-id="e7e45-151">Da die PSSession eine persistente Verbindung verwendet, können Sie einen anderen Befehl in derselben PSSession ausführen, in der die $p Variable verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e7e45-151">Because the PSSession uses a persistent connection, you can run another command in the same PSSession that uses the $p variable.</span></span> <span data-ttu-id="e7e45-152">Mit dem folgenden Befehl wird die Anzahl der in $p gespeicherten Prozesse gezählt.</span><span class="sxs-lookup"><span data-stu-id="e7e45-152">The following command counts the number of processes saved in $p.</span></span>

```powershell
Invoke-Command -Session $s -ScriptBlock {$p.count}
```

## <a name="how-to-run-a-remote-command-on-multiple-computers"></a><span data-ttu-id="e7e45-153">Ausführen eines Remote Befehls auf mehreren Computern</span><span class="sxs-lookup"><span data-stu-id="e7e45-153">HOW TO RUN A REMOTE COMMAND ON MULTIPLE COMPUTERS</span></span>

<span data-ttu-id="e7e45-154">Wenn Sie einen Remote Befehl auf mehreren Computern ausführen möchten, geben Sie alle Computernamen in den Wert des Computername-Parameters von "Aufruf-Command" ein.</span><span class="sxs-lookup"><span data-stu-id="e7e45-154">To run a remote command on multiple computers, type all of the computer names in the value of the ComputerName parameter of Invoke-Command.</span></span> <span data-ttu-id="e7e45-155">Trennen Sie die Namen durch Kommas.</span><span class="sxs-lookup"><span data-stu-id="e7e45-155">Separate the names with commas.</span></span>

<span data-ttu-id="e7e45-156">Der folgende Befehl führt z. b. einen Get-Culture Befehl auf drei Computern aus:</span><span class="sxs-lookup"><span data-stu-id="e7e45-156">For example, the following command runs a Get-Culture command on three computers:</span></span>

```powershell
Invoke-Command -ComputerName S1, S2, S3 -ScriptBlock {Get-Culture}
```

<span data-ttu-id="e7e45-157">Sie können auch einen Befehl in mehreren pssessions ausführen.</span><span class="sxs-lookup"><span data-stu-id="e7e45-157">You can also run a command in multiple PSSessions.</span></span> <span data-ttu-id="e7e45-158">Mit den folgenden Befehlen werden pssessions auf den Computern Server01, Server02 und Server03 erstellt und dann in jeder der pssessions ein Get-Culture Befehl ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e7e45-158">The following commands create PSSessions on the Server01, Server02, and Server03 computers and then run a Get-Culture command in each of the PSSessions.</span></span>

```powershell
$s = New-PSSession -ComputerName S1, S2, S3
Invoke-Command -Session $s -ScriptBlock {Get-Culture}
```

<span data-ttu-id="e7e45-159">Geben Sie den Namen des lokalen Computers ein, geben Sie einen Punkt (.) ein, oder geben Sie "localhost" ein, um die Liste der Computer mit dem lokalen Computer einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="e7e45-159">To include the local computer list of computers, type the name of the local computer, type a dot (.), or type  "localhost".</span></span>

```powershell
Invoke-Command -ComputerName S1, S2, S3, localhost -ScriptBlock {Get-Culture}
```

## <a name="how-to-run-a-script-on-remote-computers"></a><span data-ttu-id="e7e45-160">Ausführen eines Skripts auf Remote Computern</span><span class="sxs-lookup"><span data-stu-id="e7e45-160">HOW TO RUN A SCRIPT ON REMOTE COMPUTERS</span></span>

<span data-ttu-id="e7e45-161">Verwenden Sie zum Ausführen eines lokalen Skripts auf Remote Computern den filePath-Parameter von "Aufruf-Command".</span><span class="sxs-lookup"><span data-stu-id="e7e45-161">To run a local script on remote computers, use the FilePath parameter of Invoke-Command.</span></span>

<span data-ttu-id="e7e45-162">Der folgende Befehl führt z. b. das Sample.ps1 Skript auf den Computern S1 und S2 aus:</span><span class="sxs-lookup"><span data-stu-id="e7e45-162">For example, the following command runs the Sample.ps1 script on the S1 and S2 computers:</span></span>

```powershell
Invoke-Command -ComputerName S1, S2 -FilePath C:\Test\Sample.ps1
```

<span data-ttu-id="e7e45-163">Die Ergebnisse des Skripts werden an den lokalen Computer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e7e45-163">The results of the script are returned to the local computer.</span></span> <span data-ttu-id="e7e45-164">Sie müssen keine Dateien kopieren.</span><span class="sxs-lookup"><span data-stu-id="e7e45-164">You do not need to copy any files.</span></span>

## <a name="how-to-stop-a-remote-command"></a><span data-ttu-id="e7e45-165">Vorgehensweise beim Abbrechen eines Remote Befehls</span><span class="sxs-lookup"><span data-stu-id="e7e45-165">HOW TO STOP A REMOTE COMMAND</span></span>

<span data-ttu-id="e7e45-166">Um einen Befehl zu unterbrechen, drücken Sie STRG + C.</span><span class="sxs-lookup"><span data-stu-id="e7e45-166">To interrupt a command, press CTRL+C.</span></span> <span data-ttu-id="e7e45-167">Die Interruptanforderung wird an den Remote Computer weitergeleitet, auf dem der Remote Befehl beendet wird.</span><span class="sxs-lookup"><span data-stu-id="e7e45-167">The interrupt request is passed to the remote computer where it terminates the remote command.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="e7e45-168">WEITERE INFORMATIONEN</span><span class="sxs-lookup"><span data-stu-id="e7e45-168">FOR MORE INFORMATION</span></span>

- <span data-ttu-id="e7e45-169">Informationen zu den Systemanforderungen für Remoting finden Sie unter [about_Remote_Requirements](about_Remote_Requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7e45-169">For information about the system requirements for remoting, see [about_Remote_Requirements](about_Remote_Requirements.md).</span></span>

- <span data-ttu-id="e7e45-170">Hilfe zum Formatieren der Remote Ausgabe finden Sie unter [about_Remote_Output](about_Remote_Output.md).</span><span class="sxs-lookup"><span data-stu-id="e7e45-170">For help in formatting remote output, see [about_Remote_Output](about_Remote_Output.md).</span></span>

- <span data-ttu-id="e7e45-171">Informationen zur Funktionsweise von Remoting, zum Verwalten von Remote Daten, speziellen Konfigurationen, Sicherheitsproblemen und anderen häufig gestellten Fragen finden Sie unter [about_Remote_FAQ](about_Remote_FAQ.md).</span><span class="sxs-lookup"><span data-stu-id="e7e45-171">For information about how remoting works, how to manage remote data, special configurations, security issues, and other frequently asked questions, see [about_Remote_FAQ](about_Remote_FAQ.md).</span></span>

- <span data-ttu-id="e7e45-172">Hilfe zum Beheben von Remoting-Fehlern finden Sie unter about_Remote_Troubleshooting.</span><span class="sxs-lookup"><span data-stu-id="e7e45-172">For help in resolving remoting errors, see about_Remote_Troubleshooting.</span></span>

- <span data-ttu-id="e7e45-173">Weitere Informationen zu pssessions und permanenten Verbindungen finden Sie unter [about_PSSessions](about_PSSessions.md).</span><span class="sxs-lookup"><span data-stu-id="e7e45-173">For information about PSSessions and persistent connections, see [about_PSSessions](about_PSSessions.md).</span></span>

- <span data-ttu-id="e7e45-174">Weitere Informationen zu PowerShell-Hintergrund Aufträgen finden Sie unter [about_Jobs](about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="e7e45-174">For information about PowerShell background jobs, see [about_Jobs](about_Jobs.md).</span></span>

## <a name="keywords"></a><span data-ttu-id="e7e45-175">Keywords</span><span class="sxs-lookup"><span data-stu-id="e7e45-175">KEYWORDS</span></span>

<span data-ttu-id="e7e45-176">about_Remoting</span><span class="sxs-lookup"><span data-stu-id="e7e45-176">about_Remoting</span></span>

## <a name="see-also"></a><span data-ttu-id="e7e45-177">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="e7e45-177">SEE ALSO</span></span>

[<span data-ttu-id="e7e45-178">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="e7e45-178">about_PSSessions</span></span>](about_PSSessions.md)

[<span data-ttu-id="e7e45-179">about_Remote_Disconnected_Sessions</span><span class="sxs-lookup"><span data-stu-id="e7e45-179">about_Remote_Disconnected_Sessions</span></span>](about_Remote_Disconnected_Sessions.md)

[<span data-ttu-id="e7e45-180">about_Remote_Requirements</span><span class="sxs-lookup"><span data-stu-id="e7e45-180">about_Remote_Requirements</span></span>](about_Remote_Requirements.md)

[<span data-ttu-id="e7e45-181">about_Remote_FAQ</span><span class="sxs-lookup"><span data-stu-id="e7e45-181">about_Remote_FAQ</span></span>](about_Remote_FAQ.md)

[<span data-ttu-id="e7e45-182">about_Remote_TroubleShooting</span><span class="sxs-lookup"><span data-stu-id="e7e45-182">about_Remote_TroubleShooting</span></span>](about_Remote_TroubleShooting.md)

[<span data-ttu-id="e7e45-183">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="e7e45-183">about_Remote_Variables</span></span>](about_Remote_Variables.md)

[<span data-ttu-id="e7e45-184">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="e7e45-184">Enter-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Enter-PSSession)

[<span data-ttu-id="e7e45-185">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="e7e45-185">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)

[<span data-ttu-id="e7e45-186">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="e7e45-186">New-PSSession</span></span>](xref:Microsoft.PowerShell.Core.New-PSSession)
