---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 12/20/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/new-pssession?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSSession
ms.openlocfilehash: fca93f99a27bbec0c652690142cee0ebb2e56fa6
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218831"
---
# <span data-ttu-id="4b063-103">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="4b063-103">New-PSSession</span></span>

## <span data-ttu-id="4b063-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="4b063-104">SYNOPSIS</span></span>
<span data-ttu-id="4b063-105">Erstellt eine permanente Verbindung mit einem lokalen Computer oder Remotecomputer.</span><span class="sxs-lookup"><span data-stu-id="4b063-105">Creates a persistent connection to a local or remote computer.</span></span>

## <span data-ttu-id="4b063-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4b063-106">SYNTAX</span></span>

### <span data-ttu-id="4b063-107">Computername (Standard)</span><span class="sxs-lookup"><span data-stu-id="4b063-107">ComputerName (Default)</span></span>

```
New-PSSession [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-Name <String[]>]
 [-EnableNetworkAccess] [-ConfigurationName <String>] [-Port <Int32>] [-UseSSL]
 [-ApplicationName <String>] [-ThrottleLimit <Int32>] [-SessionOption <PSSessionOption>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="4b063-108">VMId</span><span class="sxs-lookup"><span data-stu-id="4b063-108">VMId</span></span>

```
New-PSSession -Credential <PSCredential> [-Name <String[]>] [-ConfigurationName <String>]
 [-VMId] <Guid[]> [-ThrottleLimit <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="4b063-109">Uri</span><span class="sxs-lookup"><span data-stu-id="4b063-109">Uri</span></span>

```
New-PSSession [-Credential <PSCredential>] [-Name <String[]>] [-EnableNetworkAccess]
 [-ConfigurationName <String>] [-ThrottleLimit <Int32>] [-ConnectionUri] <Uri[]> [-AllowRedirection]
 [-SessionOption <PSSessionOption>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="4b063-110">VMName</span><span class="sxs-lookup"><span data-stu-id="4b063-110">VMName</span></span>

```
New-PSSession -Credential <PSCredential> [-Name <String[]>] [-ConfigurationName <String>]
 -VMName <String[]> [-ThrottleLimit <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="4b063-111">Sitzung</span><span class="sxs-lookup"><span data-stu-id="4b063-111">Session</span></span>

```
New-PSSession [[-Session] <PSSession[]>] [-Name <String[]>] [-EnableNetworkAccess]
 [-ThrottleLimit <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="4b063-112">ContainerId</span><span class="sxs-lookup"><span data-stu-id="4b063-112">ContainerId</span></span>

```
New-PSSession [-Name <String[]>] [-ConfigurationName <String>] -ContainerId <String[]>
 [-RunAsAdministrator] [-ThrottleLimit <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="4b063-113">Usewindowspowershellparameterset</span><span class="sxs-lookup"><span data-stu-id="4b063-113">UseWindowsPowerShellParameterSet</span></span>

```
New-PSSession [-Name <String[]>] -UseWindowsPowerShell [<CommonParameters>]
```

### <span data-ttu-id="4b063-114">Sshhost</span><span class="sxs-lookup"><span data-stu-id="4b063-114">SSHHost</span></span>

```
New-PSSession [-Name <String[]>] [-Port <Int32>] [-HostName] <String[]> [-UserName <String>]
 [-KeyFilePath <String>] [-SSHTransport] [-Subsystem <String>] [<CommonParameters>]
```

### <span data-ttu-id="4b063-115">Sshhusthashparam</span><span class="sxs-lookup"><span data-stu-id="4b063-115">SSHHostHashParam</span></span>

```
New-PSSession [-Name <String[]>] -SSHConnection <Hashtable[]> [<CommonParameters>]
```

## <span data-ttu-id="4b063-116">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4b063-116">DESCRIPTION</span></span>

<span data-ttu-id="4b063-117">Mit dem- `New-PSSession` Cmdlet wird eine PowerShell-Sitzung ( **PSSession** ) auf einem lokalen Computer oder einem Remote Computer erstellt.</span><span class="sxs-lookup"><span data-stu-id="4b063-117">The `New-PSSession` cmdlet creates a PowerShell session ( **PSSession** ) on a local or remote computer.</span></span> <span data-ttu-id="4b063-118">Wenn Sie eine **PSSession** erstellen, stellt PowerShell eine permanente Verbindung mit dem Remote Computer her.</span><span class="sxs-lookup"><span data-stu-id="4b063-118">When you create a **PSSession** , PowerShell establishes a persistent connection to the remote computer.</span></span>

<span data-ttu-id="4b063-119">Verwenden Sie eine **PSSession** , um mehrere Befehle auszuführen, die Daten gemeinsam verwenden, z. b. eine Funktion oder den Wert einer Variablen.</span><span class="sxs-lookup"><span data-stu-id="4b063-119">Use a **PSSession** to run multiple commands that share data, such as a function or the value of a variable.</span></span> <span data-ttu-id="4b063-120">Verwenden Sie das-Cmdlet, um Befehle in einer **PSSession** auszuführen `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="4b063-120">To run commands in a **PSSession** , use the `Invoke-Command` cmdlet.</span></span> <span data-ttu-id="4b063-121">Verwenden Sie das-Cmdlet, um die **PSSession** direkt mit einem Remote Computer zu interagieren `Enter-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="4b063-121">To use the **PSSession** to interact directly with a remote computer, use the `Enter-PSSession` cmdlet.</span></span> <span data-ttu-id="4b063-122">Weitere Informationen finden Sie unter [about_PSSessions](about/about_PSSessions.md).</span><span class="sxs-lookup"><span data-stu-id="4b063-122">For more information, see [about_PSSessions](about/about_PSSessions.md).</span></span>

<span data-ttu-id="4b063-123">Sie können Befehle auf einem Remote Computer ausführen, ohne eine **PSSession** zu erstellen, indem Sie die **Computername** -Parameter von `Enter-PSSession` oder verwenden `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="4b063-123">You can run commands on a remote computer without creating a **PSSession** by using the **ComputerName** parameters of `Enter-PSSession` or `Invoke-Command`.</span></span> <span data-ttu-id="4b063-124">Wenn Sie den **Computername** -Parameter verwenden, erstellt PowerShell eine temporäre Verbindung, die für den Befehl verwendet und dann geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="4b063-124">When you use the **ComputerName** parameter, PowerShell creates a temporary connection that is used for the command and is then closed.</span></span>

<span data-ttu-id="4b063-125">Ab PowerShell 6,0 können Sie Secure Shell (SSH) verwenden, um eine Verbindung mit herzustellen und eine Sitzung auf einem Remote Computer zu erstellen, wenn ssh auf dem lokalen Computer verfügbar ist und der Remote Computer mit einem PowerShell-SSH-Endpunkt konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="4b063-125">Starting with PowerShell 6.0 you can use Secure Shell (SSH) to establish a connection to and create a session on a remote computer, if SSH is available on the local computer and the remote computer is configured with a PowerShell SSH endpoint.</span></span> <span data-ttu-id="4b063-126">Der Vorteil einer SSH-basierten PowerShell-Remote Sitzung besteht darin, dass Sie auf mehreren Plattformen (Windows, Linux, macOS) funktionieren kann.</span><span class="sxs-lookup"><span data-stu-id="4b063-126">The benefit of an SSH based PowerShell remote session is that it can work across multiple platforms (Windows, Linux, macOS).</span></span> <span data-ttu-id="4b063-127">Bei SSH-basierten Sitzungen verwenden Sie den Parameter " **Hostname** " oder " **SshConnection** ", um den Remote Computer und relevante Verbindungsinformationen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="4b063-127">For SSH based sessions you use the **HostName** or **SSHConnection** parameter set to specify the remote computer and relevant connection information.</span></span> <span data-ttu-id="4b063-128">Weitere Informationen zum Einrichten von PowerShell-SSH-Remoting finden Sie unter [PowerShell-Remoting über SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span><span class="sxs-lookup"><span data-stu-id="4b063-128">For more information about how to set up PowerShell SSH remoting, see [PowerShell Remoting Over SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span></span>

> [!NOTE]
> <span data-ttu-id="4b063-129">Bei Verwendung von WSMAN-Remoting von einem Linux-oder macOS-Client mit einem HTTPS-Endpunkt, bei dem das Serverzertifikat nicht vertrauenswürdig ist (z. b. ein selbst signiertes Zertifikat).</span><span class="sxs-lookup"><span data-stu-id="4b063-129">When using WSMan remoting from a Linux or macOS client with a HTTPS endpoint where the server certificate is not trusted (e.g., a self-signed certificate).</span></span> <span data-ttu-id="4b063-130">Sie müssen eine bereitstellen `PSSessionOption` , die `-SkipCACheck` und enthält `-SkipCNCheck` , um die Verbindung erfolgreich herzustellen.</span><span class="sxs-lookup"><span data-stu-id="4b063-130">You must provide a `PSSessionOption` that includes `-SkipCACheck` and `-SkipCNCheck` to successfully establish the connection.</span></span> <span data-ttu-id="4b063-131">Dies ist nur der Fall, wenn Sie sich in einer Umgebung befinden, in der Sie das Serverzertifikat und die Netzwerkverbindung mit dem Zielsystem sicherstellen können.</span><span class="sxs-lookup"><span data-stu-id="4b063-131">Only do this if you are in an environment where you can be certain of the server certificate and the network connection to the target system.</span></span>

## <span data-ttu-id="4b063-132">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="4b063-132">EXAMPLES</span></span>

### <span data-ttu-id="4b063-133">Beispiel 1: Erstellen einer Sitzung auf dem lokalen Computer</span><span class="sxs-lookup"><span data-stu-id="4b063-133">Example 1: Create a session on the local computer</span></span>

```powershell
$s = New-PSSession
```

<span data-ttu-id="4b063-134">Dieser Befehl erstellt eine neue **PSSession** auf dem lokalen Computer und speichert die **PSSession** in der `$s` Variablen.</span><span class="sxs-lookup"><span data-stu-id="4b063-134">This command creates a new **PSSession** on the local computer and saves the **PSSession** in the `$s` variable.</span></span>

<span data-ttu-id="4b063-135">Sie können diese **PSSession** jetzt verwenden, um Befehle auf dem lokalen Computer auszuführen.</span><span class="sxs-lookup"><span data-stu-id="4b063-135">You can now use this **PSSession** to run commands on the local computer.</span></span>

### <span data-ttu-id="4b063-136">Beispiel 2: Erstellen einer Sitzung auf einem Remote Computer</span><span class="sxs-lookup"><span data-stu-id="4b063-136">Example 2: Create a session on a remote computer</span></span>

```powershell
$Server01 = New-PSSession -ComputerName Server01
```

<span data-ttu-id="4b063-137">Dieser Befehl erstellt eine neue **PSSession** auf dem Server01-Computer und speichert Sie in der `$Server01` Variablen.</span><span class="sxs-lookup"><span data-stu-id="4b063-137">This command creates a new **PSSession** on the Server01 computer and saves it in the `$Server01` variable.</span></span>

<span data-ttu-id="4b063-138">Wenn Sie mehrere **PSSession** -Objekte erstellen, weisen Sie Sie Variablen mit nützlichen Namen zu.</span><span class="sxs-lookup"><span data-stu-id="4b063-138">When creating multiple **PSSession** objects, assign them to variables with useful names.</span></span> <span data-ttu-id="4b063-139">Dies unterstützt Sie bei der Verwaltung der **PSSession** -Objekte in nachfolgenden Befehlen.</span><span class="sxs-lookup"><span data-stu-id="4b063-139">This will help you manage the **PSSession** objects in subsequent commands.</span></span>

### <span data-ttu-id="4b063-140">Beispiel 3: Erstellen von Sitzungen auf mehreren Computern</span><span class="sxs-lookup"><span data-stu-id="4b063-140">Example 3: Create sessions on multiple computers</span></span>

```powershell
$s1, $s2, $s3 = New-PSSession -ComputerName Server01,Server02,Server03
```

<span data-ttu-id="4b063-141">Dieser Befehl erstellt drei **PSSession** -Objekte, eine auf jedem der Computer, die durch den **Computername** -Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="4b063-141">This command creates three **PSSession** objects, one on each of the computers specified by the **ComputerName** parameter.</span></span>

<span data-ttu-id="4b063-142">Der Befehl verwendet den Zuweisungs Operator (=), um die neuen **PSSession** -Objekte Variablen zuzuweisen: `$s1` , `$s2` , `$s3` .</span><span class="sxs-lookup"><span data-stu-id="4b063-142">The command uses the assignment operator (=) to assign the new **PSSession** objects to variables: `$s1`, `$s2`, `$s3`.</span></span> <span data-ttu-id="4b063-143">Dabei werden die Server01 **PSSession** `$s1` , die Server02 **PSSession** `$s2` und die Server03 **PSSession** zu zugewiesen `$s3` .</span><span class="sxs-lookup"><span data-stu-id="4b063-143">It assigns the Server01 **PSSession** to `$s1`, the Server02 **PSSession** to `$s2`, and the Server03 **PSSession** to `$s3`.</span></span>

<span data-ttu-id="4b063-144">Wenn Sie mehreren Objekten eine Reihe von Variablen zuweisen, weist PowerShell jedes Objekt einer Variablen in der Reihe zu.</span><span class="sxs-lookup"><span data-stu-id="4b063-144">When you assign multiple objects to a series of variables, PowerShell assigns each object to a variable in the series respectively.</span></span> <span data-ttu-id="4b063-145">Wenn es mehr Objekte als Variablen gibt, werden alle verbleibenden Objekte der letzten Variablen zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="4b063-145">If there are more objects than variables, all remaining objects are assigned to the last variable.</span></span> <span data-ttu-id="4b063-146">Wenn es mehr Variablen als Objekte gibt, sind die verbleibenden Variablen leer (null).</span><span class="sxs-lookup"><span data-stu-id="4b063-146">If there are more variables than objects, the remaining variables are empty (null).</span></span>

### <span data-ttu-id="4b063-147">Beispiel 4: Erstellen einer Sitzung mit einem angegebenen Port</span><span class="sxs-lookup"><span data-stu-id="4b063-147">Example 4: Create a session with a specified port</span></span>

```powershell
New-PSSession -ComputerName Server01 -Port 8081 -UseSSL -ConfigurationName E12
```

<span data-ttu-id="4b063-148">Dieser Befehl erstellt eine neue **PSSession** auf dem Server01-Computer, die eine Verbindung mit dem Serverport 8081 herstellt und das SSL-Protokoll verwendet.</span><span class="sxs-lookup"><span data-stu-id="4b063-148">This command creates a new **PSSession** on the Server01 computer that connects to server port 8081 and uses the SSL protocol.</span></span> <span data-ttu-id="4b063-149">Die neue **PSSession** verwendet eine Alternative Sitzungs Konfiguration mit dem Namen E12.</span><span class="sxs-lookup"><span data-stu-id="4b063-149">The new **PSSession** uses an alternative session configuration called E12.</span></span>

<span data-ttu-id="4b063-150">Bevor Sie den Port festlegen, müssen Sie den WinRM-Listener auf dem Remotecomputer zum Abhören von Port 8081 konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="4b063-150">Before setting the port, you must configure the WinRM listener on the remote computer to listen on port 8081.</span></span> <span data-ttu-id="4b063-151">Weitere Informationen finden Sie unter der Beschreibung des **Port** -Parameters.</span><span class="sxs-lookup"><span data-stu-id="4b063-151">For more information, see the description of the **Port** parameter.</span></span>

### <span data-ttu-id="4b063-152">Beispiel 5: Erstellen einer Sitzung basierend auf einer vorhandenen Sitzung</span><span class="sxs-lookup"><span data-stu-id="4b063-152">Example 5: Create a session based on an existing session</span></span>

```powershell
New-PSSession -Session $s -Credential Domain01\User01
```

<span data-ttu-id="4b063-153">Dieser Befehl erstellt eine **PSSession** mit denselben Eigenschaften wie eine vorhandene **PSSession**.</span><span class="sxs-lookup"><span data-stu-id="4b063-153">This command creates a **PSSession** with the same properties as an existing **PSSession**.</span></span> <span data-ttu-id="4b063-154">Sie können dieses Befehls Format verwenden, wenn die Ressourcen einer vorhandenen **PSSession** erschöpft sind und eine neue **PSSession** erforderlich ist, um einen Teil der Anforderung auszulagern.</span><span class="sxs-lookup"><span data-stu-id="4b063-154">You can use this command format when the resources of an existing **PSSession** are exhausted and a new **PSSession** is needed to offload some of the demand.</span></span>

<span data-ttu-id="4b063-155">Der Befehl verwendet den **Session** -Parameter von `New-PSSession` , um die in der Variablen gespeicherte **PSSession** anzugeben `$s` .</span><span class="sxs-lookup"><span data-stu-id="4b063-155">The command uses the **Session** parameter of `New-PSSession` to specify the **PSSession** saved in the `$s` variable.</span></span> <span data-ttu-id="4b063-156">Er verwendet die Anmeldeinformationen des Benutzers „Domain1\Admin01“, um den Befehl auszuführen.</span><span class="sxs-lookup"><span data-stu-id="4b063-156">It uses the credentials of the Domain1\Admin01 user to complete the command.</span></span>

### <span data-ttu-id="4b063-157">Beispiel 6: Erstellen einer Sitzung mit einem globalen Gültigkeitsbereich in einer anderen Domäne</span><span class="sxs-lookup"><span data-stu-id="4b063-157">Example 6: Create a session with a global scope in a different domain</span></span>

```powershell
$global:s = New-PSSession -ComputerName Server1.Domain44.Corpnet.Fabrikam.com -Credential Domain01\Admin01
```

<span data-ttu-id="4b063-158">Dieses Beispiel zeigt, wie Sie eine **PSSession** mit einem globalen Bereich auf einem Computer in einer anderen Domäne erstellen.</span><span class="sxs-lookup"><span data-stu-id="4b063-158">This example shows how to create a **PSSession** with a global scope on a computer in a different domain.</span></span>

<span data-ttu-id="4b063-159">**PSSession** -Objekte, die in der Befehlszeile erstellt werden, werden standardmäßig mit lokalem Gültigkeitsbereich erstellt, und die in einem Skript erstellten **PSSession** -Objekte verfügen über einen Skript</span><span class="sxs-lookup"><span data-stu-id="4b063-159">By default, **PSSession** objects created at the command line are created with local scope and **PSSession** objects created in a script have script scope.</span></span>

<span data-ttu-id="4b063-160">Um eine **PSSession** mit globalem Gültigkeitsbereich zu erstellen, erstellen Sie eine neue **PSSession** und speichern die **PSSession** in einer Variablen, die in einen globalen Gültigkeitsbereich umgewandelt wird.</span><span class="sxs-lookup"><span data-stu-id="4b063-160">To create a **PSSession** with global scope, create a new **PSSession** and then store the **PSSession** in a variable that is cast to a global scope.</span></span> <span data-ttu-id="4b063-161">In diesem Fall wird die `$s` Variable in einen globalen Gültigkeitsbereich umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="4b063-161">In this case, the `$s` variable is cast to a global scope.</span></span>

<span data-ttu-id="4b063-162">Der Befehl verwendet den **ComputerName** -Parameter, um den Remotecomputer anzugeben.</span><span class="sxs-lookup"><span data-stu-id="4b063-162">The command uses the **ComputerName** parameter to specify the remote computer.</span></span> <span data-ttu-id="4b063-163">Da sich der Computer in einer anderen Domäne als das Benutzerkonto befindet, wird der vollständige Name des Computers mit den Anmelde Informationen des Benutzers angegeben.</span><span class="sxs-lookup"><span data-stu-id="4b063-163">Because the computer is in a different domain than the user account, the full name of the computer is specified together with the credentials of the user.</span></span>

### <span data-ttu-id="4b063-164">Beispiel 7: Erstellen von Sitzungen für viele Computer</span><span class="sxs-lookup"><span data-stu-id="4b063-164">Example 7: Create sessions for many computers</span></span>

```powershell
$rs = Get-Content C:\Test\Servers.txt | New-PSSession -ThrottleLimit 50
```

<span data-ttu-id="4b063-165">Dieser Befehl erstellt eine **PSSession** auf jedem der 200-Computer, die in der Servers.txt-Datei aufgelistet sind, und speichert die resultierende **PSSession** in der `$rs` Variablen.</span><span class="sxs-lookup"><span data-stu-id="4b063-165">This command creates a **PSSession** on each of the 200 computers listed in the Servers.txt file and it stores the resulting **PSSession** in the `$rs` variable.</span></span> <span data-ttu-id="4b063-166">Die **PSSession** -Objekte haben eine Drosselungs Grenze von 50.</span><span class="sxs-lookup"><span data-stu-id="4b063-166">The **PSSession** objects have a throttle limit of 50.</span></span>

<span data-ttu-id="4b063-167">Sie können dieses Befehlsformat verwenden, wenn die Namen von Computern in einer Datenbank, einer Kalkulationstabelle, einer Textdatei oder in einem anderen in Text konvertierbaren Format gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="4b063-167">You can use this command format when the names of computers are stored in a database, spreadsheet, text file, or other text-convertible format.</span></span>

### <span data-ttu-id="4b063-168">Beispiel 8: Erstellen einer Sitzung mithilfe eines URI</span><span class="sxs-lookup"><span data-stu-id="4b063-168">Example 8: Create a session by using a URI</span></span>

```powershell
$s = New-PSSession -URI http://Server01:91/NewSession -Credential Domain01\User01
```

<span data-ttu-id="4b063-169">Dieser Befehl erstellt eine **PSSession** auf dem Server01-Computer und speichert Sie in der `$s` Variablen.</span><span class="sxs-lookup"><span data-stu-id="4b063-169">This command creates a **PSSession** on the Server01 computer and stores it in the `$s` variable.</span></span> <span data-ttu-id="4b063-170">Er verwendet den **URI** -Parameter, um das Transportprotokoll, den Remote Computer, den Port und eine Alternative Sitzungs Konfiguration anzugeben.</span><span class="sxs-lookup"><span data-stu-id="4b063-170">It uses the **URI** parameter to specify the transport protocol, the remote computer, the port, and an alternate session configuration.</span></span> <span data-ttu-id="4b063-171">Außerdem wird der **Credential** -Parameter verwendet, um ein Benutzerkonto anzugeben, das über die Berechtigung zum Erstellen einer Sitzung auf dem Remote Computer verfügt.</span><span class="sxs-lookup"><span data-stu-id="4b063-171">It also uses the **Credential** parameter to specify a user account that has permission to create a session on the remote computer.</span></span>

### <span data-ttu-id="4b063-172">Beispiel 9: Ausführen eines Hintergrund Auftrags in einer Gruppe von Sitzungen</span><span class="sxs-lookup"><span data-stu-id="4b063-172">Example 9: Run a background job in a set of sessions</span></span>

```powershell
$s = New-PSSession -ComputerName (Get-Content Servers.txt) -Credential Domain01\Admin01 -ThrottleLimit 16
Invoke-Command -Session $s -ScriptBlock {Get-Process PowerShell} -AsJob
```

<span data-ttu-id="4b063-173">Diese Befehle erstellen einen Satz von **PSSession** -Objekten und führen dann einen Hintergrund Auftrag in jedem der **PSSession** -Objekte aus.</span><span class="sxs-lookup"><span data-stu-id="4b063-173">These commands create a set of **PSSession** objects and then run a background job in each of the **PSSession** objects.</span></span>

<span data-ttu-id="4b063-174">Der erste Befehl erstellt eine neue **PSSession** auf jedem der Computer, die in der Servers.txt-Datei aufgelistet sind.</span><span class="sxs-lookup"><span data-stu-id="4b063-174">The first command creates a new **PSSession** on each of the computers listed in the Servers.txt file.</span></span> <span data-ttu-id="4b063-175">Er verwendet das `New-PSSession` Cmdlet, um die **PSSession** zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4b063-175">It uses the `New-PSSession` cmdlet to create the **PSSession**.</span></span> <span data-ttu-id="4b063-176">Der Wert des **Computername** -Parameters ist ein Befehl, der das `Get-Content` Cmdlet verwendet, um die Liste der Computernamen der Servers.txt Datei zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="4b063-176">The value of the **ComputerName** parameter is a command that uses the `Get-Content` cmdlet to get the list of computer names the Servers.txt file.</span></span>

<span data-ttu-id="4b063-177">Der Befehl verwendet den **Credential** -Parameter, um die **PSSession** -Objekte zu erstellen, die über die Berechtigung eines Domänen Administrators verfügen, und verwendet den **throttlelimit** -Parameter, um den Befehl auf 16 gleichzeitige Verbindungen zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="4b063-177">The command uses the **Credential** parameter to create the **PSSession** objects that have the permission of a domain administrator, and it uses the **ThrottleLimit** parameter to limit the command to 16 concurrent connections.</span></span> <span data-ttu-id="4b063-178">Der Befehl speichert die **PSSession** -Objekte in der `$s` Variablen.</span><span class="sxs-lookup"><span data-stu-id="4b063-178">The command saves the **PSSession** objects in the `$s` variable.</span></span>

<span data-ttu-id="4b063-179">Der zweite Befehl verwendet den **AsJob** -Parameter des `Invoke-Command` Cmdlets, um einen Hintergrund Auftrag zu starten, der einen `Get-Process PowerShell` Befehl in jedem der **PSSession** -Objekte in ausführt `$s` .</span><span class="sxs-lookup"><span data-stu-id="4b063-179">The second command uses the **AsJob** parameter of the `Invoke-Command` cmdlet to start a background job that runs a `Get-Process PowerShell` command in each of the **PSSession** objects in `$s`.</span></span>

<span data-ttu-id="4b063-180">Weitere Informationen zu PowerShell-Hintergrund Aufträgen finden Sie unter [about_Jobs](About/about_Jobs.md) und [about_Remote_Jobs](About/about_Remote_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="4b063-180">For more information about PowerShell background jobs, see [about_Jobs](About/about_Jobs.md) and [about_Remote_Jobs](About/about_Remote_Jobs.md).</span></span>

### <span data-ttu-id="4b063-181">Beispiel 10: Erstellen einer Sitzung für einen Computer mithilfe seines URI</span><span class="sxs-lookup"><span data-stu-id="4b063-181">Example 10: Create a session for a computer by using its URI</span></span>

```powershell
New-PSSession -ConnectionURI https://management.exchangelabs.com/Management
```

<span data-ttu-id="4b063-182">Mit diesem Befehl werden **PSSession** -Objekte erstellt, die eine Verbindung mit einem Computer herstellen, der durch einen URI anstelle eines Computer namens angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="4b063-182">This command creates a **PSSession** objects that connects to a computer that is specified by a URI instead of a computer name.</span></span>

### <span data-ttu-id="4b063-183">Beispiel 11: Erstellen einer Sitzungs Option</span><span class="sxs-lookup"><span data-stu-id="4b063-183">Example 11: Create a session option</span></span>

```powershell
$so = New-PSSessionOption -SkipCACheck
New-PSSession -ConnectionUri https://management.exchangelabs.com/Management -SessionOption $so -Credential Server01\Admin01
```

<span data-ttu-id="4b063-184">Dieses Beispiel zeigt, wie ein Sitzungs Options Objekt erstellt und der **sessionoption** -Parameter verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4b063-184">This example shows how to create a session option object and use the **SessionOption** parameter.</span></span>

<span data-ttu-id="4b063-185">Der erste Befehl verwendet das `New-PSSessionOption` Cmdlet zum Erstellen einer Sitzungs Option.</span><span class="sxs-lookup"><span data-stu-id="4b063-185">The first command uses the `New-PSSessionOption` cmdlet to create a session option.</span></span> <span data-ttu-id="4b063-186">Das resultierende **sessionoption** -Objekt wird in der `$so` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="4b063-186">It saves the resulting **SessionOption** object in the `$so` variable.</span></span>

<span data-ttu-id="4b063-187">Der zweite Befehl verwendet die Option in einer neuen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="4b063-187">The second command uses the option in a new session.</span></span> <span data-ttu-id="4b063-188">Der Befehl verwendet das `New-PSSession` Cmdlet, um eine neue Sitzung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4b063-188">The command uses the `New-PSSession` cmdlet to create a new session.</span></span> <span data-ttu-id="4b063-189">Der Wert des sessionoption-Parameters ist das **sessionoption** -Objekt in der `$so` Variablen.</span><span class="sxs-lookup"><span data-stu-id="4b063-189">The value of the SessionOption parameter is the **SessionOption** object in the `$so` variable.</span></span>

### <span data-ttu-id="4b063-190">Beispiel 12: Erstellen einer Sitzung mithilfe von SSH</span><span class="sxs-lookup"><span data-stu-id="4b063-190">Example 12: Create a session using SSH</span></span>

```powershell
New-PSSession -HostName UserA@LinuxServer01
```

<span data-ttu-id="4b063-191">Dieses Beispiel zeigt, wie eine neue **PSSession** mithilfe von Secure Shell (SSH) erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="4b063-191">This example shows how to create a new **PSSession** using Secure Shell (SSH).</span></span> <span data-ttu-id="4b063-192">Wenn SSH auf dem Remote Computer für die Eingabe von Kenn Wörtern konfiguriert ist, erhalten Sie eine Kenn Wort Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="4b063-192">If SSH is configured on the remote computer to prompt for passwords then you will get a password prompt.</span></span> <span data-ttu-id="4b063-193">Andernfalls müssen Sie die SSH-Schlüssel basierte Benutzerauthentifizierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="4b063-193">Otherwise you will have to use SSH key based user authentication.</span></span>

### <span data-ttu-id="4b063-194">Beispiel 13: Erstellen einer Sitzung mithilfe von SSH und angeben des Ports und des Benutzer Authentifizierungs Schlüssels</span><span class="sxs-lookup"><span data-stu-id="4b063-194">Example 13: Create a session using SSH and specify the port and user authentication key</span></span>

```powershell
New-PSSession -HostName UserA@LinuxServer01:22 -KeyFilePath c:\<path>\userAKey_rsa
```

<span data-ttu-id="4b063-195">In diesem Beispiel wird gezeigt, wie eine **PSSession** mithilfe von Secure Shell (SSH) erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="4b063-195">This example shows how to create a **PSSession** using Secure Shell (SSH).</span></span> <span data-ttu-id="4b063-196">Er verwendet den **Port** -Parameter, um den zu verwendenden Port anzugeben, und den **keyFilePath** -Parameter, um einen RSA-Schlüssel anzugeben, der zum Identifizieren und Authentifizieren des Benutzers auf dem Remote Computer verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4b063-196">It uses the **Port** parameter to specify the port to use and the **KeyFilePath** parameter to specify an RSA key used to identify and authenticate the user on the remote computer.</span></span>

### <span data-ttu-id="4b063-197">Beispiel 14: Erstellen mehrerer Sitzungen mithilfe von SSH</span><span class="sxs-lookup"><span data-stu-id="4b063-197">Example 14: Create multiple sessions using SSH</span></span>

```powershell
$sshConnections = @{ HostName="WinServer1"; UserName="domain\userA"; KeyFilePath="c:\users\UserA\id_rsa" }, @{ HostName="UserB@LinuxServer5"; KeyFilePath="c:\UserB\<path>\id_rsa" }
New-PSSession -SSHConnection $sshConnections
```

<span data-ttu-id="4b063-198">Dieses Beispiel zeigt, wie mehrere Sitzungen mit Secure Shell (SSH) und dem **SshConnection** -Parametersatz erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="4b063-198">This example shows how to create multiple sessions using Secure Shell (SSH) and the **SSHConnection** parameter set.</span></span> <span data-ttu-id="4b063-199">Der **SshConnection** -Parameter nimmt ein Array von Hash Tabellen an, die Verbindungsinformationen für jede Sitzung enthalten.</span><span class="sxs-lookup"><span data-stu-id="4b063-199">The **SSHConnection** parameter takes an array of hash tables that contain connection information for each session.</span></span> <span data-ttu-id="4b063-200">Beachten Sie, dass dieses Beispiel erfordert, dass für die Ziel Remote Computer SSH konfiguriert ist, um die Schlüssel basierte Benutzerauthentifizierung zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="4b063-200">Note that this example requires that the target remote computers have SSH configured to support key based user authentication.</span></span>

## <span data-ttu-id="4b063-201">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4b063-201">PARAMETERS</span></span>

### <span data-ttu-id="4b063-202">-Zuweisung Richtung</span><span class="sxs-lookup"><span data-stu-id="4b063-202">-AllowRedirection</span></span>

<span data-ttu-id="4b063-203">Gibt an, dass dieses Cmdlet die Umleitung dieser Verbindung an eine Alternative Uniform Resource Identifier (URI) zulässt.</span><span class="sxs-lookup"><span data-stu-id="4b063-203">Indicates that this cmdlet allows redirection of this connection to an alternate Uniform Resource Identifier (URI).</span></span>

<span data-ttu-id="4b063-204">Bei Verwendung des **ConnectionURI** -Parameters kann das Remoteziel eine Anweisung zum Umleiten an einen anderen URI zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="4b063-204">When you use the **ConnectionURI** parameter, the remote destination can return an instruction to redirect to a different URI.</span></span> <span data-ttu-id="4b063-205">Standardmäßig werden Verbindungen von PowerShell nicht umgeleitet, aber Sie können diesen Parameter verwenden, um eine Umleitung der Verbindung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="4b063-205">By default, PowerShell does not redirect connections, but you can use this parameter to enable it to redirect the connection.</span></span>

<span data-ttu-id="4b063-206">Sie können auch einschränken, wie oft die Verbindung umgeleitet wird, indem Sie den **MaximumConnectionRedirectionCount** -Optionswert der Sitzung ändern.</span><span class="sxs-lookup"><span data-stu-id="4b063-206">You can also limit the number of times the connection is redirected by changing the **MaximumConnectionRedirectionCount** session option value.</span></span> <span data-ttu-id="4b063-207">Verwenden Sie den **maximumredirect** -Parameter des `New-PSSessionOption` Cmdlets, oder legen Sie die **maximumconnectionredirectioncount** -Eigenschaft der **$PSSessionOption** Preference-Variablen fest.</span><span class="sxs-lookup"><span data-stu-id="4b063-207">Use the **MaximumRedirection** parameter of the `New-PSSessionOption` cmdlet or set the **MaximumConnectionRedirectionCount** property of the **$PSSessionOption** preference variable.</span></span> <span data-ttu-id="4b063-208">Der Standardwert ist 5.</span><span class="sxs-lookup"><span data-stu-id="4b063-208">The default value is 5.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Uri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4b063-209">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="4b063-209">-ApplicationName</span></span>

<span data-ttu-id="4b063-210">Gibt das Anwendungsnamenssegment des Verbindungs-URI an.</span><span class="sxs-lookup"><span data-stu-id="4b063-210">Specifies the application name segment of the connection URI.</span></span> <span data-ttu-id="4b063-211">Mit diesem Parameter können Sie den Anwendungsnamen angeben, wenn Sie den **ConnectionURI** -Parameter im Befehl nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="4b063-211">Use this parameter to specify the application name when you are not using the **ConnectionURI** parameter in the command.</span></span>

<span data-ttu-id="4b063-212">Der Standardwert ist der Wert der Einstellungs `$PSSessionApplicationName` Variablen auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="4b063-212">The default value is the value of the `$PSSessionApplicationName` preference variable on the local computer.</span></span> <span data-ttu-id="4b063-213">Wenn diese Einstellungsvariable nicht definiert ist, ist der Standardwert „WSMan“.</span><span class="sxs-lookup"><span data-stu-id="4b063-213">If this preference variable is not defined, the default value is WSMAN.</span></span> <span data-ttu-id="4b063-214">Dieser Wert ist für die meisten Verwendungsarten geeignet.</span><span class="sxs-lookup"><span data-stu-id="4b063-214">This value is appropriate for most uses.</span></span> <span data-ttu-id="4b063-215">Weitere Informationen finden Sie unter [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="4b063-215">For more information, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="4b063-216">Der WinRM-Dienst wählt mit dem Anwendungsnamen einen Listener für die Verbindungsanforderung aus.</span><span class="sxs-lookup"><span data-stu-id="4b063-216">The WinRM service uses the application name to select a listener to service the connection request.</span></span>
<span data-ttu-id="4b063-217">Der Wert dieses Parameters sollte mit dem Wert der **URLPrefix** -Eigenschaft eines Listeners auf dem Remotecomputer übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="4b063-217">The value of this parameter should match the value of the **URLPrefix** property of a listener on the remote computer.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4b063-218">-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="4b063-218">-Authentication</span></span>

<span data-ttu-id="4b063-219">Gibt den Mechanismus an, der zum Authentifizieren der Anmeldeinformationen des Benutzers verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4b063-219">Specifies the mechanism that is used to authenticate the user's credentials.</span></span>
<span data-ttu-id="4b063-220">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="4b063-220">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="4b063-221">Standard</span><span class="sxs-lookup"><span data-stu-id="4b063-221">Default</span></span>
- <span data-ttu-id="4b063-222">Basic</span><span class="sxs-lookup"><span data-stu-id="4b063-222">Basic</span></span>
- <span data-ttu-id="4b063-223">CredSSP</span><span class="sxs-lookup"><span data-stu-id="4b063-223">Credssp</span></span>
- <span data-ttu-id="4b063-224">Digest</span><span class="sxs-lookup"><span data-stu-id="4b063-224">Digest</span></span>
- <span data-ttu-id="4b063-225">Kerberos</span><span class="sxs-lookup"><span data-stu-id="4b063-225">Kerberos</span></span>
- <span data-ttu-id="4b063-226">Aushandeln</span><span class="sxs-lookup"><span data-stu-id="4b063-226">Negotiate</span></span>
- <span data-ttu-id="4b063-227">NegotiateWithImplicitCredential</span><span class="sxs-lookup"><span data-stu-id="4b063-227">NegotiateWithImplicitCredential</span></span>

<span data-ttu-id="4b063-228">Der Standardwert ist Default.</span><span class="sxs-lookup"><span data-stu-id="4b063-228">The default value is Default.</span></span>

<span data-ttu-id="4b063-229">Weitere Informationen zu den Werten dieses Parameters finden Sie unter [authenticationmechanism-Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span><span class="sxs-lookup"><span data-stu-id="4b063-229">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!CAUTION]
> <span data-ttu-id="4b063-230">Die Authentifizierung der Credential Security Support Provider (kredssp), bei der die Anmelde Informationen des Benutzers an einen Remote Computer übergeben werden, der authentifiziert werden soll, wurde für Befehle entworfen, die eine Authentifizierung auf mehr als einer Ressource erfordern, z. b. den Zugriff auf eine Remote Netzwerkfreigabe.</span><span class="sxs-lookup"><span data-stu-id="4b063-230">Credential Security Support Provider (CredSSP) authentication, in which the user credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="4b063-231">Dieser Mechanismus erhöht das Sicherheitsrisiko des Remotevorgangs.</span><span class="sxs-lookup"><span data-stu-id="4b063-231">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="4b063-232">Wenn die Sicherheit des Remotecomputers gefährdet ist, können die an ihn übergebenen Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4b063-232">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: ComputerName, Uri
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4b063-233">-Certifiupethumschlag-Print</span><span class="sxs-lookup"><span data-stu-id="4b063-233">-CertificateThumbprint</span></span>

<span data-ttu-id="4b063-234">Gibt das digitale Zertifikat für öffentliche Schlüssel (X509) eines Benutzerkontos an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="4b063-234">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span> <span data-ttu-id="4b063-235">Geben Sie den Zertifikatfingerabdruck des Zertifikats ein.</span><span class="sxs-lookup"><span data-stu-id="4b063-235">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="4b063-236">Zertifikate werden bei der clientzertifikatbasierten Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="4b063-236">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="4b063-237">Sie können nur lokalen Benutzerkonten zugeordnet werden und funktionieren nicht mit Domänenkonten.</span><span class="sxs-lookup"><span data-stu-id="4b063-237">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="4b063-238">Um ein Zertifikat zu erhalten, verwenden Sie den `Get-Item` `Get-ChildItem` Befehl oder im PowerShell-Laufwerk "CERT:".</span><span class="sxs-lookup"><span data-stu-id="4b063-238">To get a certificate, use the `Get-Item` or `Get-ChildItem` command in the PowerShell Cert: drive.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName, Uri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4b063-239">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="4b063-239">-ComputerName</span></span>

<span data-ttu-id="4b063-240">Gibt ein Array von Namen von Computern an.</span><span class="sxs-lookup"><span data-stu-id="4b063-240">Specifies an array of names of computers.</span></span> <span data-ttu-id="4b063-241">Dieses Cmdlet erstellt eine permanente Verbindung ( **PSSession** ) mit dem angegebenen Computer.</span><span class="sxs-lookup"><span data-stu-id="4b063-241">This cmdlet creates a persistent connection ( **PSSession** ) to the specified computer.</span></span> <span data-ttu-id="4b063-242">Wenn Sie mehrere Computernamen eingeben, `New-PSSession` erstellt mehrere **PSSession** -Objekte, eine für jeden Computer.</span><span class="sxs-lookup"><span data-stu-id="4b063-242">If you enter multiple computer names, `New-PSSession` creates multiple **PSSession** objects, one for each computer.</span></span> <span data-ttu-id="4b063-243">Die Standardeinstellung ist der lokale Computer.</span><span class="sxs-lookup"><span data-stu-id="4b063-243">The default is the local computer.</span></span>

<span data-ttu-id="4b063-244">Geben Sie den NetBIOS-Namen, eine IP-Adresse oder den vollqualifizierten Domänennamen mindestens eines Computers ein.</span><span class="sxs-lookup"><span data-stu-id="4b063-244">Type the NetBIOS name, an IP address, or a fully qualified domain name of one or more remote computers.</span></span> <span data-ttu-id="4b063-245">Um den lokalen Computer anzugeben, geben Sie den Computernamen, "localhost" oder einen Punkt (.) ein.</span><span class="sxs-lookup"><span data-stu-id="4b063-245">To specify the local computer, type the computer name, localhost, or a dot (.).</span></span> <span data-ttu-id="4b063-246">Wenn sich der Remotecomputer in einer anderen Domäne als der Benutzer befindet, ist der vollqualifizierte Domänenname erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4b063-246">When the computer is in a different domain than the user, the fully qualified domain name is required.</span></span> <span data-ttu-id="4b063-247">Sie können einen Computernamen (in Anführungszeichen) auch über die Pipeline an übergeben `New-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="4b063-247">You can also pipe a computer name, in quotation marks, to `New-PSSession`.</span></span>

<span data-ttu-id="4b063-248">Um eine IP-Adresse im Wert des **Computername** -Parameters zu verwenden, muss der Befehl den **Credential** -Parameter enthalten.</span><span class="sxs-lookup"><span data-stu-id="4b063-248">To use an IP address in the value of the **ComputerName** parameter, the command must include the **Credential** parameter.</span></span> <span data-ttu-id="4b063-249">Außerdem muss der Computer für den HTTPS-Transport konfiguriert sein, oder die IP-Adresse des Remotecomputers muss in der WinRM TrustedHosts-Liste auf dem lokalen Computer enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="4b063-249">Also, the computer must be configured for HTTPS transport or the IP address of the remote computer must be included in the WinRM TrustedHosts list on the local computer.</span></span> <span data-ttu-id="4b063-250">Anweisungen zum Hinzufügen eines Computer namens zur Liste "Treuhänder Hosts" finden Sie unter "Vorgehensweise beim Hinzufügen eines Computers zur Liste vertrauenswürdiger Hosts" in [about_Remote_Troubleshooting](about/about_Remote_Troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="4b063-250">For instructions for adding a computer name to the TrustedHosts list, see "How to Add a Computer to the Trusted Host List" in [about_Remote_Troubleshooting](about/about_Remote_Troubleshooting.md).</span></span>

<span data-ttu-id="4b063-251">Um den lokalen Computer in den Wert des **Computername** -Parameters einzuschließen, starten Sie Windows PowerShell mit der Option als Administrator ausführen.</span><span class="sxs-lookup"><span data-stu-id="4b063-251">To include the local computer in the value of the **ComputerName** parameter, start Windows PowerShell by using the Run as administrator option.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerName
Aliases: Cn

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="4b063-252">-ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="4b063-252">-ConfigurationName</span></span>

<span data-ttu-id="4b063-253">Gibt die Sitzungs Konfiguration an, die für die neue **PSSession** verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4b063-253">Specifies the session configuration that is used for the new **PSSession**.</span></span>

<span data-ttu-id="4b063-254">Geben Sie einen Konfigurationsnamen oder den vollqualifizierten Ressourcen-URI für eine Sitzungskonfiguration ein.</span><span class="sxs-lookup"><span data-stu-id="4b063-254">Enter a configuration name or the fully qualified resource URI for a session configuration.</span></span> <span data-ttu-id="4b063-255">Wenn Sie nur den Konfigurations Namen angeben, wird der folgende Schema-URI vorangestellt: `http://schemas.microsoft.com/PowerShell` .</span><span class="sxs-lookup"><span data-stu-id="4b063-255">If you specify only the configuration name, the following schema URI is prepended: `http://schemas.microsoft.com/PowerShell`.</span></span>

<span data-ttu-id="4b063-256">Die Sitzungskonfiguration für eine Sitzung befindet sich auf dem Remotecomputer.</span><span class="sxs-lookup"><span data-stu-id="4b063-256">The session configuration for a session is located on the remote computer.</span></span> <span data-ttu-id="4b063-257">Wenn die angegebene Sitzungskonfiguration auf dem Remotecomputer nicht vorhanden ist, führt der Befehl zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="4b063-257">If the specified session configuration does not exist on the remote computer, the command fails.</span></span>

<span data-ttu-id="4b063-258">Der Standardwert ist der Wert der Einstellungs `$PSSessionConfigurationName` Variablen auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="4b063-258">The default value is the value of the `$PSSessionConfigurationName` preference variable on the local computer.</span></span> <span data-ttu-id="4b063-259">Wenn diese Einstellungsvariable nicht festgelegt ist, ist die Standardeinstellung „Microsoft.PowerShell“.</span><span class="sxs-lookup"><span data-stu-id="4b063-259">If this preference variable is not set, the default is Microsoft.PowerShell.</span></span> <span data-ttu-id="4b063-260">Weitere Informationen finden Sie unter [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="4b063-260">For more information, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName, Uri, VMId, VMName, ContainerId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4b063-261">-ConnectionUri</span><span class="sxs-lookup"><span data-stu-id="4b063-261">-ConnectionUri</span></span>

<span data-ttu-id="4b063-262">Gibt einen URI an, der den Verbindungs Endpunkt für die Sitzung definiert.</span><span class="sxs-lookup"><span data-stu-id="4b063-262">Specifies a URI that defines the connection endpoint for the session.</span></span> <span data-ttu-id="4b063-263">Der URI muss vollqualifiziert sein.</span><span class="sxs-lookup"><span data-stu-id="4b063-263">The URI must be fully qualified.</span></span> <span data-ttu-id="4b063-264">Das Format dieser Zeichenfolge lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="4b063-264">The format of this string is as follows:</span></span>

`<Transport>://<ComputerName>:<Port>/<ApplicationName>`

<span data-ttu-id="4b063-265">Der Standardwert lautet:</span><span class="sxs-lookup"><span data-stu-id="4b063-265">The default value is as follows:</span></span>

`http://localhost:5985/WSMAN`

<span data-ttu-id="4b063-266">Wenn Sie keinen **ConnectionURI** angeben, können Sie die Parameter **UseSSL** , **ComputerName** , **Port** und **ApplicationName** zur Angabe der **ConnectionURI** -Werte verwenden.</span><span class="sxs-lookup"><span data-stu-id="4b063-266">If you do not specify a **ConnectionURI** , you can use the **UseSSL** , **ComputerName** , **Port** , and **ApplicationName** parameters to specify the **ConnectionURI** values.</span></span>

<span data-ttu-id="4b063-267">Gültige Werte für das Transport-Segment des URI sind „HTTP“ und „HTTPS“.</span><span class="sxs-lookup"><span data-stu-id="4b063-267">Valid values for the Transport segment of the URI are HTTP and HTTPS.</span></span> <span data-ttu-id="4b063-268">Wenn Sie einen Verbindungs-URI mit einem Transport Segment angeben, aber keinen Port angeben, wird die Sitzung mit Standardports erstellt: 80 für http und 443 für HTTPS.</span><span class="sxs-lookup"><span data-stu-id="4b063-268">If you specify a connection URI with a Transport segment, but do not specify a port, the session is created with standards ports: 80 for HTTP and 443 for HTTPS.</span></span> <span data-ttu-id="4b063-269">Wenn Sie die Standardports für PowerShell-Remoting verwenden möchten, geben Sie Port 5985 für http oder 5986 für HTTPS an.</span><span class="sxs-lookup"><span data-stu-id="4b063-269">To use the default ports for PowerShell remoting, specify port 5985 for HTTP or 5986 for HTTPS.</span></span>

<span data-ttu-id="4b063-270">Wenn der Zielcomputer die Verbindung an einen anderen URI umleitet, verhindert PowerShell die Umleitung, es sei denn, Sie verwenden den Parameter " **Zuweisung** " im Befehl.</span><span class="sxs-lookup"><span data-stu-id="4b063-270">If the destination computer redirects the connection to a different URI, PowerShell prevents the redirection unless you use the **AllowRedirection** parameter in the command.</span></span>

```yaml
Type: System.Uri[]
Parameter Sets: Uri
Aliases: URI, CU

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4b063-271">-Containerid</span><span class="sxs-lookup"><span data-stu-id="4b063-271">-ContainerId</span></span>

<span data-ttu-id="4b063-272">Gibt ein Array von IDs von Containern an.</span><span class="sxs-lookup"><span data-stu-id="4b063-272">Specifies an array of IDs of containers.</span></span> <span data-ttu-id="4b063-273">Mit diesem Cmdlet wird eine interaktive Sitzung mit jedem der angegebenen Container gestartet.</span><span class="sxs-lookup"><span data-stu-id="4b063-273">This cmdlet starts an interactive session with each of the specified containers.</span></span> <span data-ttu-id="4b063-274">Verwenden Sie den `docker ps` Befehl, um eine Liste der Container-IDs abzurufen.</span><span class="sxs-lookup"><span data-stu-id="4b063-274">Use the `docker ps` command to get a list of container IDs.</span></span> <span data-ttu-id="4b063-275">Weitere Informationen finden Sie in der Hilfe zum [docker PS](https://docs.docker.com/engine/reference/commandline/ps/) -Befehl.</span><span class="sxs-lookup"><span data-stu-id="4b063-275">For more information, see the help for the [docker ps](https://docs.docker.com/engine/reference/commandline/ps/) command.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ContainerId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4b063-276">-Credential</span><span class="sxs-lookup"><span data-stu-id="4b063-276">-Credential</span></span>

<span data-ttu-id="4b063-277">Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="4b063-277">Specifies a user account that has permission to do this action.</span></span> <span data-ttu-id="4b063-278">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="4b063-278">The default is the current user.</span></span>

<span data-ttu-id="4b063-279">Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01** , oder geben Sie ein **PSCredential** -Objekt ein, das vom `Get-Credential` Cmdlet generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="4b063-279">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="4b063-280">Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe des Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="4b063-280">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="4b063-281">Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.</span><span class="sxs-lookup"><span data-stu-id="4b063-281">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="4b063-282">Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="4b063-282">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerName, Uri, VMId, VMName
Aliases:

Required: True (VMId, VMName), False (ComputerName, Uri)
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4b063-283">-Enablenetworkaccess</span><span class="sxs-lookup"><span data-stu-id="4b063-283">-EnableNetworkAccess</span></span>

<span data-ttu-id="4b063-284">Gibt an, dass mit diesem Cmdlet Loopback Sitzungen ein interaktives Sicherheits Token hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="4b063-284">Indicates that this cmdlet adds an interactive security token to loopback sessions.</span></span> <span data-ttu-id="4b063-285">Mit dem interaktiven Token können Sie die Befehle in der Loopbacksitzung ausführen, um Daten von anderen Computern abzurufen.</span><span class="sxs-lookup"><span data-stu-id="4b063-285">The interactive token lets you run commands in the loopback session that get data from other computers.</span></span> <span data-ttu-id="4b063-286">Beispielsweise können Sie einen Befehl in der Sitzung ausführen, mit dem XML-Dateien von einem Remotecomputer auf den lokalen Computer kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="4b063-286">For example, you can run a command in the session that copies XML files from a remote computer to the local computer.</span></span>

<span data-ttu-id="4b063-287">Eine Loopback Sitzung ist eine **PSSession** , die auf demselben computerbasiert und endet.</span><span class="sxs-lookup"><span data-stu-id="4b063-287">A loopback session is a **PSSession** that originates and ends on the same computer.</span></span> <span data-ttu-id="4b063-288">Um eine Loopback Sitzung zu erstellen, lassen Sie den **Computername** -Parameter aus, oder legen Sie seinen Wert auf "dot (.)", "localhost" oder den Namen des lokalen Computers fest.</span><span class="sxs-lookup"><span data-stu-id="4b063-288">To create a loopback session, omit the **ComputerName** parameter or set its value to dot (.), localhost, or the name of the local computer.</span></span>

<span data-ttu-id="4b063-289">Standardmäßig erstellt dieses Cmdlet Loopback Sitzungen mithilfe eines Netzwerk Tokens, das möglicherweise nicht über ausreichende Berechtigungen zum Authentifizieren bei Remote Computern verfügt.</span><span class="sxs-lookup"><span data-stu-id="4b063-289">By default, this cmdlet creates loopback sessions by using a network token, which might not provide sufficient permission to authenticate to remote computers.</span></span>

<span data-ttu-id="4b063-290">Der **EnableNetworkAccess** -Parameter ist nur bei Loopbacksitzungen wirksam.</span><span class="sxs-lookup"><span data-stu-id="4b063-290">The **EnableNetworkAccess** parameter is effective only in loopback sessions.</span></span> <span data-ttu-id="4b063-291">Wenn Sie **enablenetworkaccess** verwenden, wenn Sie eine Sitzung auf einem Remote Computer erstellen, ist der Befehl erfolgreich, aber der-Parameter wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="4b063-291">If you use **EnableNetworkAccess** when you create a session on a remote computer, the command succeeds, but the parameter is ignored.</span></span>

<span data-ttu-id="4b063-292">Sie können den Remote Zugriff auch in einer Loopback Sitzung aktivieren, indem Sie den Wert "kredssp" des Parameters " **Authentication** " verwenden, der die Sitzungs Anmelde Informationen an andere Computer delegiert.</span><span class="sxs-lookup"><span data-stu-id="4b063-292">You can also enable remote access in a loopback session by using the CredSSP value of the **Authentication** parameter, which delegates the session credentials to other computers.</span></span>

<span data-ttu-id="4b063-293">Um den Computer vor böswilligem Zugriff zu schützen, können getrennte Loopback Sitzungen mit interaktiven Tokens, die mit dem **enablenetworkaccess** -Parameter erstellt werden, nur von dem Computer wieder hergestellt werden, auf dem die Sitzung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="4b063-293">To protect the computer from malicious access, disconnected loopback sessions that have interactive tokens, which are those created by using the **EnableNetworkAccess** parameter, can be reconnected only from the computer on which the session was created.</span></span> <span data-ttu-id="4b063-294">Die Verbindung von getrennten Sitzungen, die die CredSSP-Authentifizierung verwenden, kann von anderen Computern wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="4b063-294">Disconnected sessions that use CredSSP authentication can be reconnected from other computers.</span></span> <span data-ttu-id="4b063-295">Weitere Informationen finden Sie unter `Disconnect-PSSession`.</span><span class="sxs-lookup"><span data-stu-id="4b063-295">For more information, see `Disconnect-PSSession`.</span></span>

<span data-ttu-id="4b063-296">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="4b063-296">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName, Uri, Session
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4b063-297">-HostName</span><span class="sxs-lookup"><span data-stu-id="4b063-297">-HostName</span></span>

<span data-ttu-id="4b063-298">Gibt ein Array von Computernamen für eine Secure Shell (SSH)-basierte Verbindung an.</span><span class="sxs-lookup"><span data-stu-id="4b063-298">Specifies an array of computer names for a Secure Shell (SSH) based connection.</span></span> <span data-ttu-id="4b063-299">Dies ähnelt dem Computername-Parameter, mit dem Unterschied, dass die Verbindung mit dem Remote Computer anstelle von Windows WinRM über SSH hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="4b063-299">This is similar to the ComputerName parameter except that the connection to the remote computer is made using SSH rather than Windows WinRM.</span></span>

<span data-ttu-id="4b063-300">Dieser Parameter wurde in PowerShell 6,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="4b063-300">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.String[]
Parameter Sets: SSHHost
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4b063-301">-KeyFilePath</span><span class="sxs-lookup"><span data-stu-id="4b063-301">-KeyFilePath</span></span>

<span data-ttu-id="4b063-302">Gibt einen Schlüssel Dateipfad an, der von Secure Shell (SSH) zum Authentifizieren eines Benutzers auf einem Remote Computer verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4b063-302">Specifies a key file path used by Secure Shell (SSH) to authenticate a user on a remote computer.</span></span>

<span data-ttu-id="4b063-303">SSH ermöglicht die Durchführung der Benutzerauthentifizierung über private/öffentliche Schlüssel als Alternative zur grundlegenden Kenn Wort Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="4b063-303">SSH allows user authentication to be performed via private/public keys as an alternative to basic password authentication.</span></span> <span data-ttu-id="4b063-304">Wenn der Remote Computer für die Schlüssel Authentifizierung konfiguriert ist, kann dieser Parameter verwendet werden, um den Schlüssel zur Identifizierung des Benutzers bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="4b063-304">If the remote computer is configured for key authentication then this parameter can be used to provide the key that identifies the user.</span></span>

<span data-ttu-id="4b063-305">Dieser Parameter wurde in PowerShell 6,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="4b063-305">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.String
Parameter Sets: SSHHost
Aliases: IdentityFilePath

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4b063-306">-Name</span><span class="sxs-lookup"><span data-stu-id="4b063-306">-Name</span></span>

<span data-ttu-id="4b063-307">Gibt einen anzeigen Amen für die **PSSession** an.</span><span class="sxs-lookup"><span data-stu-id="4b063-307">Specifies a friendly name for the **PSSession**.</span></span>

<span data-ttu-id="4b063-308">Sie können den Namen verwenden, um auf die **PSSession** zu verweisen, wenn Sie andere Cmdlets verwenden, z `Get-PSSession` `Enter-PSSession` . b. und.</span><span class="sxs-lookup"><span data-stu-id="4b063-308">You can use the name to refer to the **PSSession** when you use other cmdlets, such as `Get-PSSession` and `Enter-PSSession`.</span></span> <span data-ttu-id="4b063-309">Der Name muss für den Computer oder die aktuelle Sitzung nicht eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="4b063-309">The name is not required to be unique to the computer or the current session.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4b063-310">-Port</span><span class="sxs-lookup"><span data-stu-id="4b063-310">-Port</span></span>

<span data-ttu-id="4b063-311">Gibt den Netzwerkport an dem für diese Verbindung verwendeten Remotecomputer an.</span><span class="sxs-lookup"><span data-stu-id="4b063-311">Specifies the network port on the remote computer that is used for this connection.</span></span> <span data-ttu-id="4b063-312">Zum Herstellen einer Verbindung mit einem Remotecomputer muss der Remotecomputer den für die Verbindung verwendeten Port abhören.</span><span class="sxs-lookup"><span data-stu-id="4b063-312">To connect to a remote computer, the remote computer must be listening on the port that the connection uses.</span></span> <span data-ttu-id="4b063-313">Die Standardports sind 5985. Dies ist der WinRM-Port für http und 5986 (der WinRM-Port für HTTPS).</span><span class="sxs-lookup"><span data-stu-id="4b063-313">The default ports are 5985, which is the WinRM port for HTTP, and 5986, which is the WinRM port for HTTPS.</span></span>

<span data-ttu-id="4b063-314">Bevor Sie einen anderen Port verwenden, müssen Sie den WinRM-Listener auf dem Remote Computer so konfigurieren, dass er an diesem Port lauscht.</span><span class="sxs-lookup"><span data-stu-id="4b063-314">Before using another port, you must configure the WinRM listener on the remote computer to listen at that port.</span></span> <span data-ttu-id="4b063-315">Verwenden Sie die folgenden Befehle, um den Listener zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="4b063-315">Use the following commands to configure the listener:</span></span>

1. `winrm delete winrm/config/listener?Address=*+Transport=HTTP`
2. `winrm create winrm/config/listener?Address=*+Transport=HTTP @{Port="\<port-number\>"}`

<span data-ttu-id="4b063-316">Verwenden Sie den **Port** -Parameter nur, wenn es unbedingt notwendig ist.</span><span class="sxs-lookup"><span data-stu-id="4b063-316">Do not use the **Port** parameter unless you must.</span></span> <span data-ttu-id="4b063-317">Die Porteinstellung im Befehl gilt für alle Computer oder Sitzungen, für die der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4b063-317">The port setting in the command applies to all computers or sessions on which the command runs.</span></span> <span data-ttu-id="4b063-318">Eine alternative Porteinstellung kann verhindern, dass der Befehl auf allen Computern ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4b063-318">An alternate port setting might prevent the command from running on all computers.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ComputerName, SSHHost
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4b063-319">-Runasadministrator</span><span class="sxs-lookup"><span data-stu-id="4b063-319">-RunAsAdministrator</span></span>

<span data-ttu-id="4b063-320">Gibt an, dass die **PSSession** als Administrator ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4b063-320">Indicates that the **PSSession** runs as administrator.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ContainerId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4b063-321">-Sitzung</span><span class="sxs-lookup"><span data-stu-id="4b063-321">-Session</span></span>

<span data-ttu-id="4b063-322">Gibt ein Array von **PSSession** -Objekten an, die von diesem Cmdlet als Modell für die neue **PSSession** verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4b063-322">Specifies an array of **PSSession** objects that this cmdlet uses as a model for the new **PSSession**.</span></span> <span data-ttu-id="4b063-323">Dieser Parameter erstellt neue **PSSession** -Objekte, die über die gleichen Eigenschaften wie die angegebenen **PSSession** -Objekte verfügen.</span><span class="sxs-lookup"><span data-stu-id="4b063-323">This parameter creates new **PSSession** objects that have the same properties as the specified **PSSession** objects.</span></span>

<span data-ttu-id="4b063-324">Geben Sie eine Variable ein, die die **PSSession** -Objekte enthält, oder einen Befehl, der die **PSSession** -Objekte erstellt oder abruft, z `New-PSSession` . b. den `Get-PSSession` Befehl oder.</span><span class="sxs-lookup"><span data-stu-id="4b063-324">Enter a variable that contains the **PSSession** objects or a command that creates or gets the **PSSession** objects, such as a `New-PSSession` or `Get-PSSession` command.</span></span>

<span data-ttu-id="4b063-325">Die resultierenden **PSSession** -Objekte haben den gleichen Computernamen, Anwendungsnamen, Verbindungs-URI, Port, Konfigurations Namen, Drosselungs Grenzwert und Secure Sockets Layer (SSL)-Wert wie die originale, aber Sie haben einen anderen anzeigen Amen, eine andere ID und Instanz-ID (GUID).</span><span class="sxs-lookup"><span data-stu-id="4b063-325">The resulting **PSSession** objects have the same computer name, application name, connection URI, port, configuration name, throttle limit, and Secure Sockets Layer (SSL) value as the originals, but they have a different display name, ID, and instance ID (GUID).</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession[]
Parameter Sets: Session
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="4b063-326">-Sessionoption</span><span class="sxs-lookup"><span data-stu-id="4b063-326">-SessionOption</span></span>

<span data-ttu-id="4b063-327">Gibt erweiterte Optionen für die Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="4b063-327">Specifies advanced options for the session.</span></span> <span data-ttu-id="4b063-328">Geben Sie ein **sessionoption** -Objekt ein, z. b. ein Objekt, das Sie mit dem `New-PSSessionOption` Cmdlet erstellen, oder eine Hash Tabelle, in der die Schlüssel Sitzungs Optionsnamen und die Werte Sitzungs Optionswerte sind.</span><span class="sxs-lookup"><span data-stu-id="4b063-328">Enter a **SessionOption** object, such as one that you create by using the `New-PSSessionOption` cmdlet, or a hash table in which the keys are session option names and the values are session option values.</span></span>

<span data-ttu-id="4b063-329">Die Standardwerte für die Optionen werden durch den Wert der Einstellungs `$PSSessionOption` Variablen bestimmt, sofern festgelegt.</span><span class="sxs-lookup"><span data-stu-id="4b063-329">The default values for the options are determined by the value of the `$PSSessionOption` preference variable, if it is set.</span></span> <span data-ttu-id="4b063-330">Andernfalls werden die Standardwerte durch Optionen festgelegt, die in der Sitzungskonfiguration festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="4b063-330">Otherwise, the default values are established by options set in the session configuration.</span></span>

<span data-ttu-id="4b063-331">Die Sitzungs Optionswerte haben Vorrang vor Standardwerten für Sitzungen, die in der `$PSSessionOption` Preference-Variablen und in der Sitzungs Konfiguration festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="4b063-331">The session option values take precedence over default values for sessions set in the `$PSSessionOption` preference variable and in the session configuration.</span></span> <span data-ttu-id="4b063-332">Allerdings haben sie nicht Vorrang vor Höchstwerten, Kontingenten oder Grenzwerten, die in der Sitzungskonfiguration festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="4b063-332">However, they do not take precedence over maximum values, quotas or limits set in the session configuration.</span></span>

<span data-ttu-id="4b063-333">Eine Beschreibung der Sitzungs Optionen, die die Standardwerte enthalten, finden Sie unter `New-PSSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="4b063-333">For a description of the session options that includes the default values, see `New-PSSessionOption`.</span></span> <span data-ttu-id="4b063-334">Weitere Informationen zur Einstellungs `$PSSessionOption` Variablen finden Sie unter [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="4b063-334">For information about the `$PSSessionOption` preference variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span> <span data-ttu-id="4b063-335">Weitere Informationen zu Sitzungs Konfigurationen finden Sie unter [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="4b063-335">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

```yaml
Type: System.Management.Automation.Remoting.PSSessionOption
Parameter Sets: ComputerName, Uri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4b063-336">-SshConnection</span><span class="sxs-lookup"><span data-stu-id="4b063-336">-SSHConnection</span></span>

<span data-ttu-id="4b063-337">Dieser Parameter nimmt ein Array von Hash Tabellen an, in denen jede Hash Tabelle einen oder mehrere Verbindungsparameter enthält, die zum Herstellen einer Secure Shell (SSH)-Verbindung (Hostname, Port, Benutzername, keyFilePath) erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="4b063-337">This parameter takes an array of hashtables where each hashtable contains one or more connection parameters needed to establish a Secure Shell (SSH) connection (HostName, Port, UserName, KeyFilePath).</span></span>

<span data-ttu-id="4b063-338">Die Hash Tabellen-Verbindungsparameter entsprechen den Parametern, die für den Parametersatz " **Hostname** " definiert sind.</span><span class="sxs-lookup"><span data-stu-id="4b063-338">The hashtable connection parameters are the same as defined for the **HostName** parameter set.</span></span>

<span data-ttu-id="4b063-339">Der **SshConnection** -Parameter ist nützlich zum Erstellen mehrerer Sitzungen, in denen jede Sitzung andere Verbindungsinformationen erfordert.</span><span class="sxs-lookup"><span data-stu-id="4b063-339">The **SSHConnection** parameter is useful for creating multiple sessions where each session requires different connection information.</span></span>

<span data-ttu-id="4b063-340">Dieser Parameter wurde in PowerShell 6,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="4b063-340">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Collections.Hashtable[]
Parameter Sets: SSHHostHashParam
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4b063-341">-Sshtransport</span><span class="sxs-lookup"><span data-stu-id="4b063-341">-SSHTransport</span></span>

<span data-ttu-id="4b063-342">Gibt an, dass die Remote Verbindung mithilfe von Secure Shell (SSH) hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="4b063-342">Indicates that the remote connection is established using Secure Shell (SSH).</span></span>

<span data-ttu-id="4b063-343">Standardmäßig verwendet PowerShell Windows WinRM, um eine Verbindung mit einem Remote Computer herzustellen.</span><span class="sxs-lookup"><span data-stu-id="4b063-343">By default PowerShell uses Windows WinRM to connect to a remote computer.</span></span> <span data-ttu-id="4b063-344">Dieser Schalter zwingt PowerShell, den Hostname-Parametersatz zum Einrichten einer SSH-basierten Remote Verbindung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="4b063-344">This switch forces PowerShell to use the HostName parameter set for establishing an SSH based remote connection.</span></span>

<span data-ttu-id="4b063-345">Dieser Parameter wurde in PowerShell 6,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="4b063-345">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SSHHost
Aliases:
Accepted values: true

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4b063-346">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="4b063-346">-ThrottleLimit</span></span>

<span data-ttu-id="4b063-347">Gibt die maximale Anzahl von gleichzeitigen Verbindungen an, die zum Ausführen dieses Befehls hergestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="4b063-347">Specifies the maximum number of concurrent connections that can be established to run this command.</span></span>
<span data-ttu-id="4b063-348">Wenn Sie diesen Parameter weglassen oder den Wert „0“ (Null) eingeben, wird der Standardwert „32“ verwendet.</span><span class="sxs-lookup"><span data-stu-id="4b063-348">If you omit this parameter or enter a value of 0 (zero), the default value, 32, is used.</span></span>

<span data-ttu-id="4b063-349">Die Drosselungsgrenze gilt nur für den aktuellen Befehl und nicht für die Sitzung oder den Computer.</span><span class="sxs-lookup"><span data-stu-id="4b063-349">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ComputerName, Uri, VMId, VMName, Session, ContainerId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4b063-350">-UserName</span><span class="sxs-lookup"><span data-stu-id="4b063-350">-UserName</span></span>

<span data-ttu-id="4b063-351">Gibt den Benutzernamen für das Konto an, das verwendet wird, um eine Sitzung auf dem Remote Computer zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4b063-351">Specifies the user name for the account used to create a session on the remote computer.</span></span> <span data-ttu-id="4b063-352">Die Benutzer Authentifizierungsmethode hängt davon ab, wie Secure Shell (SSH) auf dem Remote Computer konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="4b063-352">User authentication method will depend on how Secure Shell (SSH) is configured on the remote computer.</span></span>

<span data-ttu-id="4b063-353">Wenn SSH für die einfache Kenn Wort Authentifizierung konfiguriert ist, werden Sie zur Eingabe des Benutzer Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="4b063-353">If SSH is configured for basic password authentication then you will be prompted for the user password.</span></span>

<span data-ttu-id="4b063-354">Wenn SSH für die Schlüssel basierte Benutzerauthentifizierung konfiguriert ist, kann ein Schlüssel Dateipfad über den keyFilePath-Parameter bereitgestellt werden, und es wird keine Kenn Wort Eingabeaufforderung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4b063-354">If SSH is configured for key based user authentication then a key file path can be provided via the KeyFilePath parameter and no password prompt will occur.</span></span> <span data-ttu-id="4b063-355">Beachten Sie, dass der Schlüssel filePath-Parameter für die Schlüssel basierte Authentifizierung nicht benötigt wird, wenn sich die Client Benutzer Schlüsseldatei an einem bekannten SSH-Speicherort befindet. die Benutzerauthentifizierung erfolgt automatisch basierend auf dem Benutzernamen.</span><span class="sxs-lookup"><span data-stu-id="4b063-355">Note that if the client user key file is located in an SSH known location then the KeyFilePath parameter is not needed for key based authentication, and user authentication will occur automatically based on the user name.</span></span> <span data-ttu-id="4b063-356">Weitere Informationen finden Sie in der SSH-Dokumentation zur Schlüssel basierten Benutzerauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="4b063-356">See SSH documentation about key based user authentication for more information.</span></span>

<span data-ttu-id="4b063-357">Dies ist kein erforderlicher Parameter.</span><span class="sxs-lookup"><span data-stu-id="4b063-357">This is not a required parameter.</span></span> <span data-ttu-id="4b063-358">Wenn kein username-Parameter angegeben wird, wird der aktuelle Anmelde Name des Benutzers für die Verbindung verwendet.</span><span class="sxs-lookup"><span data-stu-id="4b063-358">If no UserName parameter is specified then the current log on user name is used for the connection.</span></span>

<span data-ttu-id="4b063-359">Dieser Parameter wurde in PowerShell 6,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="4b063-359">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.String
Parameter Sets: SSHHost
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4b063-360">-US-</span><span class="sxs-lookup"><span data-stu-id="4b063-360">-UseSSL</span></span>

<span data-ttu-id="4b063-361">Gibt an, dass dieses Cmdlet das SSL-Protokoll verwendet, um eine Verbindung mit dem Remote Computer herzustellen.</span><span class="sxs-lookup"><span data-stu-id="4b063-361">Indicates that this cmdlet uses the SSL protocol to establish a connection to the remote computer.</span></span>
<span data-ttu-id="4b063-362">Standardmäßig wird SSL nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="4b063-362">By default, SSL is not used.</span></span>

<span data-ttu-id="4b063-363">WS-Management verschlüsselt alle über das Netzwerk übertragenen PowerShell-Inhalte.</span><span class="sxs-lookup"><span data-stu-id="4b063-363">WS-Management encrypts all PowerShell content transmitted over the network.</span></span> <span data-ttu-id="4b063-364">Der Parameter " **eessl** " bietet einen zusätzlichen Schutz, der die Daten über eine HTTPS-Verbindung statt über eine HTTP-Verbindung sendet.</span><span class="sxs-lookup"><span data-stu-id="4b063-364">The **UseSSL** parameter offers an additional protection that sends the data across an HTTPS connection instead of an HTTP connection.</span></span>

<span data-ttu-id="4b063-365">Wenn Sie diesen Parameter verwenden, aber SSL auf dem Port, der für den Befehl verwendet wird, nicht verfügbar ist, schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="4b063-365">If you use this parameter, but SSL is not available on the port that is used for the command, the command fails.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4b063-366">-VMID</span><span class="sxs-lookup"><span data-stu-id="4b063-366">-VMId</span></span>

<span data-ttu-id="4b063-367">Gibt ein Array mit der ID der virtuellen Computer an.</span><span class="sxs-lookup"><span data-stu-id="4b063-367">Specifies an array of ID of virtual machines.</span></span> <span data-ttu-id="4b063-368">Dieses Cmdlet startet eine interaktive Sitzung mit jedem der angegebenen virtuellen Computer.</span><span class="sxs-lookup"><span data-stu-id="4b063-368">This cmdlet starts an interactive session with each of the specified virtual machines.</span></span> <span data-ttu-id="4b063-369">Verwenden Sie den folgenden Befehl, um die verfügbaren virtuellen Computer anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="4b063-369">To see the virtual machines that are available to you, use the following command:</span></span>

`Get-VM | Select-Object -Property Name, ID`

```yaml
Type: System.Guid[]
Parameter Sets: VMId
Aliases: VMGuid

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4b063-370">-VMName</span><span class="sxs-lookup"><span data-stu-id="4b063-370">-VMName</span></span>

<span data-ttu-id="4b063-371">Gibt ein Array von Namen von virtuellen Computern an.</span><span class="sxs-lookup"><span data-stu-id="4b063-371">Specifies an array of names of virtual machines.</span></span> <span data-ttu-id="4b063-372">Dieses Cmdlet startet eine interaktive Sitzung mit jedem der angegebenen virtuellen Computer.</span><span class="sxs-lookup"><span data-stu-id="4b063-372">This cmdlet starts an interactive session with each of the specified virtual machines.</span></span> <span data-ttu-id="4b063-373">Verwenden Sie das-Cmdlet, um die für Sie verfügbaren virtuellen Maschinen anzuzeigen `Get-VM` .</span><span class="sxs-lookup"><span data-stu-id="4b063-373">To see the virtual machines that are available to you, use the `Get-VM` cmdlet.</span></span>

```yaml
Type: System.String[]
Parameter Sets: VMName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4b063-374">-HostName</span><span class="sxs-lookup"><span data-stu-id="4b063-374">-HostName</span></span>

<span data-ttu-id="4b063-375">Gibt ein Array von Computernamen für eine Secure Shell (SSH)-basierte Verbindung an.</span><span class="sxs-lookup"><span data-stu-id="4b063-375">Specifies an array of computer names for a Secure Shell (SSH) based connection.</span></span> <span data-ttu-id="4b063-376">Dies ähnelt dem Computername-Parameter, mit dem Unterschied, dass die Verbindung mit dem Remote Computer anstelle von Windows WinRM über SSH hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="4b063-376">This is similar to the ComputerName parameter except that the connection to the remote computer is made using SSH rather than Windows WinRM.</span></span>
<span data-ttu-id="4b063-377">Dieser Parameter unterstützt die Angabe des Benutzernamens und/oder Ports als Teil des Hostname-Parameter Werts unter Verwendung des Formulars `user@hostname:port` .</span><span class="sxs-lookup"><span data-stu-id="4b063-377">This parameter supports specifying the user name and/or port as part of the host name parameter value using the form `user@hostname:port`.</span></span>
<span data-ttu-id="4b063-378">Der als Teil des Host namens angegebene Benutzername und/oder Port `-UserName` `-Port` hat Vorrang vor den Parametern und.</span><span class="sxs-lookup"><span data-stu-id="4b063-378">The user name and/or port specified as part of the host name takes precedence over the `-UserName` and `-Port` parameters, if specified.</span></span>
<span data-ttu-id="4b063-379">Dadurch können mehrere Computernamen an diesen Parameter übergeben werden, bei denen einige bestimmte Benutzernamen und/oder Ports aufweisen, während andere Benutzer den Benutzernamen und/oder den Port aus den `-UserName` `-Port` Parametern und verwenden.</span><span class="sxs-lookup"><span data-stu-id="4b063-379">This allows passing multiple computer names to this parameter where some have specific user names and/or ports, while others use the user name and/or port from the `-UserName` and `-Port` parameters.</span></span>

<span data-ttu-id="4b063-380">Dieser Parameter wurde in PowerShell 6,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="4b063-380">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.String[]
Parameter Sets: HostName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4b063-381">-KeyFilePath</span><span class="sxs-lookup"><span data-stu-id="4b063-381">-KeyFilePath</span></span>

<span data-ttu-id="4b063-382">Gibt einen Schlüssel Dateipfad an, der von Secure Shell (SSH) zum Authentifizieren eines Benutzers auf einem Remote Computer verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4b063-382">Specifies a key file path used by Secure Shell (SSH) to authenticate a user on a remote computer.</span></span>

<span data-ttu-id="4b063-383">SSH ermöglicht die Durchführung der Benutzerauthentifizierung über private/öffentliche Schlüssel als Alternative zur grundlegenden Kenn Wort Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="4b063-383">SSH allows user authentication to be performed via private/public keys as an alternative to basic password authentication.</span></span> <span data-ttu-id="4b063-384">Wenn der Remote Computer für die Schlüssel Authentifizierung konfiguriert ist, kann dieser Parameter verwendet werden, um den Schlüssel zur Identifizierung des Benutzers bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="4b063-384">If the remote computer is configured for key authentication then this parameter can be used to provide the key that identifies the user.</span></span>

<span data-ttu-id="4b063-385">Dieser Parameter wurde in PowerShell 6,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="4b063-385">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.String
Parameter Sets: HostName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4b063-386">-Sshtransport</span><span class="sxs-lookup"><span data-stu-id="4b063-386">-SSHTransport</span></span>

<span data-ttu-id="4b063-387">Gibt an, dass die Remote Verbindung mithilfe von Secure Shell (SSH) hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="4b063-387">Indicates that the remote connection is established using Secure Shell (SSH).</span></span>

<span data-ttu-id="4b063-388">Standardmäßig verwendet PowerShell Windows WinRM, um eine Verbindung mit einem Remote Computer herzustellen.</span><span class="sxs-lookup"><span data-stu-id="4b063-388">By default PowerShell uses Windows WinRM to connect to a remote computer.</span></span> <span data-ttu-id="4b063-389">Dieser Schalter zwingt PowerShell, den Hostname-Parametersatz zum Einrichten einer SSH-basierten Remote Verbindung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="4b063-389">This switch forces PowerShell to use the HostName parameter set for establishing an SSH based remote connection.</span></span>

<span data-ttu-id="4b063-390">Dieser Parameter wurde in PowerShell 6,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="4b063-390">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: HostName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4b063-391">-UserName</span><span class="sxs-lookup"><span data-stu-id="4b063-391">-UserName</span></span>

<span data-ttu-id="4b063-392">Gibt den Benutzernamen für das Konto an, das verwendet wird, um eine Sitzung auf dem Remote Computer zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4b063-392">Specifies the user name for the account used to create a session on the remote computer.</span></span> <span data-ttu-id="4b063-393">Die Benutzer Authentifizierungsmethode hängt davon ab, wie Secure Shell (SSH) auf dem Remote Computer konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="4b063-393">User authentication method will depend on how Secure Shell (SSH) is configured on the remote computer.</span></span>

<span data-ttu-id="4b063-394">Wenn SSH für die einfache Kenn Wort Authentifizierung konfiguriert ist, werden Sie zur Eingabe des Benutzer Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="4b063-394">If SSH is configured for basic password authentication then you will be prompted for the user password.</span></span>

<span data-ttu-id="4b063-395">Wenn SSH für die Schlüssel basierte Benutzerauthentifizierung konfiguriert ist, kann ein Schlüssel Dateipfad über den keyFilePath-Parameter bereitgestellt werden, und es wird keine Kenn Wort Eingabeaufforderung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4b063-395">If SSH is configured for key based user authentication then a key file path can be provided via the KeyFilePath parameter and no password prompt will occur.</span></span> <span data-ttu-id="4b063-396">Beachten Sie, dass der Schlüssel filePath-Parameter für die Schlüssel basierte Authentifizierung nicht benötigt wird, wenn sich die Client Benutzer Schlüsseldatei an einem bekannten SSH-Speicherort befindet. die Benutzerauthentifizierung erfolgt automatisch basierend auf dem Benutzernamen.</span><span class="sxs-lookup"><span data-stu-id="4b063-396">Note that if the client user key file is located in an SSH known location then the KeyFilePath parameter is not needed for key based authentication, and user authentication will occur automatically based on the user name.</span></span> <span data-ttu-id="4b063-397">Weitere Informationen finden Sie in der SSH-Dokumentation zur Schlüssel basierten Benutzerauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="4b063-397">See SSH documentation about key based user authentication for more information.</span></span>

<span data-ttu-id="4b063-398">Dies ist kein erforderlicher Parameter.</span><span class="sxs-lookup"><span data-stu-id="4b063-398">This is not a required parameter.</span></span> <span data-ttu-id="4b063-399">Wenn kein username-Parameter angegeben wird, wird der aktuelle Anmelde Name des Benutzers für die Verbindung verwendet.</span><span class="sxs-lookup"><span data-stu-id="4b063-399">If no UserName parameter is specified then the current log on user name is used for the connection.</span></span>

<span data-ttu-id="4b063-400">Dieser Parameter wurde in PowerShell 6,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="4b063-400">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.String
Parameter Sets: HostName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4b063-401">-SshConnection</span><span class="sxs-lookup"><span data-stu-id="4b063-401">-SSHConnection</span></span>

<span data-ttu-id="4b063-402">Dieser Parameter nimmt ein Array von Hash Tabellen an, in denen jede Hash Tabelle einen oder mehrere Verbindungsparameter enthält, die zum Herstellen einer Secure Shell (SSH)-Verbindung (Hostname, Port, Benutzername, keyFilePath, Subsystem) erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="4b063-402">This parameter takes an array of hashtables where each hashtable contains one or more connection parameters needed to establish a Secure Shell (SSH) connection (HostName, Port, UserName, KeyFilePath, Subsystem).</span></span>

<span data-ttu-id="4b063-403">Die Hash Tabellen-Verbindungsparameter entsprechen den Parametern, die für den Parametersatz " **Hostname** " definiert sind.</span><span class="sxs-lookup"><span data-stu-id="4b063-403">The hashtable connection parameters are the same as defined for the **HostName** parameter set.</span></span>
<span data-ttu-id="4b063-404">Beachten Sie, dass die Reihenfolge der Schlüssel in der Hash Tabelle dazu führt, dass der Benutzername und der Port für die Verbindung verwendet werden, in der der letzte angegebene verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4b063-404">Note that the order of the keys in the hashtable result in user name and port being used for the connection where the last one specified is used.</span></span>  <span data-ttu-id="4b063-405">Wenn Sie z `@{UserName="first";HostName="second@host"}` . b. verwenden, wird der Benutzername `second` verwendet.</span><span class="sxs-lookup"><span data-stu-id="4b063-405">For example, if you use `@{UserName="first";HostName="second@host"}`, then the user name `second` will be used.</span></span>  <span data-ttu-id="4b063-406">Wenn Sie jedoch verwenden `@{HostName="second@host:22";Port=23}` , wird Port 23 verwendet.</span><span class="sxs-lookup"><span data-stu-id="4b063-406">However, if you use `@{HostName="second@host:22";Port=23}`, then port 23 will be used.</span></span>

<span data-ttu-id="4b063-407">Dieser Parameter wurde in PowerShell 6,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="4b063-407">This parameter was introduced in PowerShell 6.0.</span></span>

<span data-ttu-id="4b063-408">Der **SshConnection** -Parameter ist nützlich zum Erstellen mehrerer Sitzungen, in denen jede Sitzung andere Verbindungsinformationen erfordert.</span><span class="sxs-lookup"><span data-stu-id="4b063-408">The **SSHConnection** parameter is useful for creating multiple sessions where each session requires different connection information.</span></span>

```yaml
Type: hashtable
Parameter Sets: SSHConnection
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4b063-409">-Subsystem</span><span class="sxs-lookup"><span data-stu-id="4b063-409">-Subsystem</span></span>

<span data-ttu-id="4b063-410">Gibt das SSH-Subsystem an, das für die neue **PSSession** verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4b063-410">Specifies the SSH subsystem used for the new **PSSession**.</span></span>

<span data-ttu-id="4b063-411">Gibt das Subsystem an, das auf dem Ziel verwendet werden soll, wie in sshd_config definiert.</span><span class="sxs-lookup"><span data-stu-id="4b063-411">This specifies the subsystem to use on the target as defined in sshd_config.</span></span>
<span data-ttu-id="4b063-412">Das Subsystem startet eine bestimmte Version von PowerShell mit vordefinierten Parametern.</span><span class="sxs-lookup"><span data-stu-id="4b063-412">The subsystem starts a specific version of PowerShell with predefined parameters.</span></span>
<span data-ttu-id="4b063-413">Wenn das angegebene Subsystem auf dem Remote Computer nicht vorhanden ist, schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="4b063-413">If the specified subsystem does not exist on the remote computer, the command fails.</span></span>

<span data-ttu-id="4b063-414">Wenn dieser Parameter nicht verwendet wird, ist der Standardwert das "PowerShell"-Subsystem.</span><span class="sxs-lookup"><span data-stu-id="4b063-414">If this parameter is not used, the default is the 'powershell' subsystem.</span></span>

```yaml
Type: System.String
Parameter Sets: HostName
Aliases:

Required: False
Position: Named
Default value: powershell
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4b063-415">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="4b063-415">CommonParameters</span></span>

<span data-ttu-id="4b063-416">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4b063-416">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4b063-417">Weitere Informationen finden Sie unter "about_CommonParameters" (https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4b063-417">For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4b063-418">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="4b063-418">INPUTS</span></span>

### <span data-ttu-id="4b063-419">System. String, System. Uri, System. Management. Automation. Runspaces. PSSession</span><span class="sxs-lookup"><span data-stu-id="4b063-419">System.String, System.URI, System.Management.Automation.Runspaces.PSSession</span></span>

<span data-ttu-id="4b063-420">Sie können eine Zeichenfolge, einen URI oder ein Sitzungs Objekt über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="4b063-420">You can pipe a string, URI, or session object to this cmdlet.</span></span>

## <span data-ttu-id="4b063-421">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="4b063-421">OUTPUTS</span></span>

### <span data-ttu-id="4b063-422">System. Management. Automation. Runspaces. PSSession</span><span class="sxs-lookup"><span data-stu-id="4b063-422">System.Management.Automation.Runspaces.PSSession</span></span>

## <span data-ttu-id="4b063-423">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="4b063-423">NOTES</span></span>

- <span data-ttu-id="4b063-424">Dieses Cmdlet verwendet die PowerShell-Remoting-Infrastruktur.</span><span class="sxs-lookup"><span data-stu-id="4b063-424">This cmdlet uses the PowerShell remoting infrastructure.</span></span> <span data-ttu-id="4b063-425">Um dieses Cmdlet verwenden zu können, müssen der lokale Computer und alle Remote Computer für PowerShell-Remoting konfiguriert sein.</span><span class="sxs-lookup"><span data-stu-id="4b063-425">To use this cmdlet, the local computer and any remote computers must be configured for PowerShell remoting.</span></span> <span data-ttu-id="4b063-426">Weitere Informationen finden Sie unter [about_Remote_Requirements](About/about_Remote_Requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b063-426">For more information, see [about_Remote_Requirements](About/about_Remote_Requirements.md).</span></span>
- <span data-ttu-id="4b063-427">Starten Sie PowerShell mit der Option als Administrator ausführen, um eine **PSSession** auf dem lokalen Computer zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4b063-427">To create a **PSSession** on the local computer, start PowerShell with the Run as administrator option.</span></span>
- <span data-ttu-id="4b063-428">Wenn Sie mit der **PSSession** fertig sind, verwenden Sie das `Remove-PSSession` Cmdlet, um die **PSSession** zu löschen und deren Ressourcen freizugeben.</span><span class="sxs-lookup"><span data-stu-id="4b063-428">When you are finished with the **PSSession** , use the `Remove-PSSession` cmdlet to delete the **PSSession** and release its resources.</span></span>
- <span data-ttu-id="4b063-429">Die Parametersätze " **Hostname** " und " **SshConnection** " wurden ab PowerShell 6,0 eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="4b063-429">The **HostName** and **SSHConnection** parameter sets were included starting with PowerShell 6.0.</span></span>
  <span data-ttu-id="4b063-430">Sie wurden hinzugefügt, um PowerShell-Remoting basierend auf Secure Shell (SSH) bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="4b063-430">They were added to provide PowerShell remoting based on Secure Shell (SSH).</span></span> <span data-ttu-id="4b063-431">Sowohl SSH als auch PowerShell werden auf mehreren Plattformen (Windows, Linux, macOS) unterstützt, und PowerShell-Remoting funktioniert auf diesen Plattformen, auf denen PowerShell und SSH installiert und konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="4b063-431">Both SSH and PowerShell are supported on multiple platforms (Windows, Linux, macOS) and PowerShell remoting will work over these platforms where PowerShell and SSH are installed and configured.</span></span> <span data-ttu-id="4b063-432">Dies ist vom vorherigen Windows-Remoting getrennt, das auf WinRM basiert, und ein Großteil der speziellen Features und Einschränkungen von WinRM ist nicht anwendbar.</span><span class="sxs-lookup"><span data-stu-id="4b063-432">This is separate from the previous Windows only remoting that is based on WinRM and much of the WinRM specific features and limitations do not apply.</span></span> <span data-ttu-id="4b063-433">Beispielsweise werden auf WinRM basierende Kontingente, Sitzungs Optionen, benutzerdefinierte Endpunkt Konfiguration und Features zum Trennen und Wiederherstellen von Verbindungen derzeit nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4b063-433">For example WinRM based quotas, session options, custom endpoint configuration, and disconnect/reconnect features are currently not supported.</span></span> <span data-ttu-id="4b063-434">Weitere Informationen zum Einrichten von PowerShell-SSH-Remoting finden Sie unter [PowerShell-Remoting über SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span><span class="sxs-lookup"><span data-stu-id="4b063-434">For more information about how to set up PowerShell SSH remoting, see [PowerShell Remoting Over SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span></span>

## <span data-ttu-id="4b063-435">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="4b063-435">RELATED LINKS</span></span>

[<span data-ttu-id="4b063-436">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="4b063-436">Connect-PSSession</span></span>](Connect-PSSession.md)

[<span data-ttu-id="4b063-437">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="4b063-437">Disconnect-PSSession</span></span>](Disconnect-PSSession.md)

[<span data-ttu-id="4b063-438">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="4b063-438">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="4b063-439">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="4b063-439">Exit-PSSession</span></span>](Exit-PSSession.md)

[<span data-ttu-id="4b063-440">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="4b063-440">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="4b063-441">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="4b063-441">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="4b063-442">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="4b063-442">Receive-PSSession</span></span>](Receive-PSSession.md)

[<span data-ttu-id="4b063-443">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="4b063-443">Remove-PSSession</span></span>](Remove-PSSession.md)
