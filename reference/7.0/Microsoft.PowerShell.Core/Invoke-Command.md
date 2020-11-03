---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/invoke-command?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-Command
ms.openlocfilehash: b4e065ba0055c43a0ab4475878a049e4f9fde3e2
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218844"
---
# <span data-ttu-id="c2ed2-103">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="c2ed2-103">Invoke-Command</span></span>

## <span data-ttu-id="c2ed2-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="c2ed2-104">SYNOPSIS</span></span>
<span data-ttu-id="c2ed2-105">Führt Befehle auf lokalen Computern und Remotecomputern aus.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-105">Runs commands on local and remote computers.</span></span>

## <span data-ttu-id="c2ed2-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c2ed2-106">SYNTAX</span></span>

### <span data-ttu-id="c2ed2-107">InProcess (Standard)</span><span class="sxs-lookup"><span data-stu-id="c2ed2-107">InProcess (Default)</span></span>

```
Invoke-Command [-ScriptBlock] <ScriptBlock> [-NoNewScope] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [<CommonParameters>]
```

### <span data-ttu-id="c2ed2-108">Filepathrunspace</span><span class="sxs-lookup"><span data-stu-id="c2ed2-108">FilePathRunspace</span></span>

```
Invoke-Command [[-Session] <PSSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-HideComputerName]
 [-JobName <String>] [-FilePath] <String> [-RemoteDebug] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [<CommonParameters>]
```

### <span data-ttu-id="c2ed2-109">Sitzung</span><span class="sxs-lookup"><span data-stu-id="c2ed2-109">Session</span></span>

```
Invoke-Command [[-Session] <PSSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-HideComputerName]
 [-JobName <String>] [-ScriptBlock] <ScriptBlock> [-RemoteDebug] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [<CommonParameters>]
```

### <span data-ttu-id="c2ed2-110">Filepathcomputername</span><span class="sxs-lookup"><span data-stu-id="c2ed2-110">FilePathComputerName</span></span>

```
Invoke-Command [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-Port <Int32>] [-UseSSL]
 [-ConfigurationName <String>] [-ApplicationName <String>] [-ThrottleLimit <Int32>] [-AsJob]
 [-InDisconnectedSession] [-SessionName <String[]>] [-HideComputerName] [-JobName <String>]
 [-FilePath] <String> [-SessionOption <PSSessionOption>] [-Authentication <AuthenticationMechanism>]
 [-EnableNetworkAccess] [-RemoteDebug] [-InputObject <PSObject>] [-ArgumentList <Object[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="c2ed2-111">Computername</span><span class="sxs-lookup"><span data-stu-id="c2ed2-111">ComputerName</span></span>

```
Invoke-Command [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-Port <Int32>] [-UseSSL]
 [-ConfigurationName <String>] [-ApplicationName <String>] [-ThrottleLimit <Int32>] [-AsJob]
 [-InDisconnectedSession] [-SessionName <String[]>] [-HideComputerName] [-JobName <String>]
 [-ScriptBlock] <ScriptBlock> [-SessionOption <PSSessionOption>]
 [-Authentication <AuthenticationMechanism>] [-EnableNetworkAccess] [-RemoteDebug]
 [-InputObject <PSObject>] [-ArgumentList <Object[]>] [-CertificateThumbprint <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="c2ed2-112">Uri</span><span class="sxs-lookup"><span data-stu-id="c2ed2-112">Uri</span></span>

```
Invoke-Command [-Credential <PSCredential>] [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [[-ConnectionUri] <Uri[]>] [-AsJob] [-InDisconnectedSession] [-HideComputerName]
 [-JobName <String>] [-ScriptBlock] <ScriptBlock> [-AllowRedirection]
 [-SessionOption <PSSessionOption>] [-Authentication <AuthenticationMechanism>]
 [-EnableNetworkAccess] [-RemoteDebug] [-InputObject <PSObject>] [-ArgumentList <Object[]>]
 [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="c2ed2-113">Filepaar</span><span class="sxs-lookup"><span data-stu-id="c2ed2-113">FilePathUri</span></span>

```
Invoke-Command [-Credential <PSCredential>] [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [[-ConnectionUri] <Uri[]>] [-AsJob] [-InDisconnectedSession] [-HideComputerName]
 [-JobName <String>] [-FilePath] <String> [-AllowRedirection] [-SessionOption <PSSessionOption>]
 [-Authentication <AuthenticationMechanism>] [-EnableNetworkAccess] [-RemoteDebug]
 [-InputObject <PSObject>] [-ArgumentList <Object[]>] [<CommonParameters>]
```

### <span data-ttu-id="c2ed2-114">VMId</span><span class="sxs-lookup"><span data-stu-id="c2ed2-114">VMId</span></span>

```
Invoke-Command -Credential <PSCredential> [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [-AsJob] [-HideComputerName] [-ScriptBlock] <ScriptBlock> [-RemoteDebug] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [-VMId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="c2ed2-115">VMName</span><span class="sxs-lookup"><span data-stu-id="c2ed2-115">VMName</span></span>

```
Invoke-Command -Credential <PSCredential> [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [-AsJob] [-HideComputerName] [-ScriptBlock] <ScriptBlock> [-RemoteDebug] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] -VMName <String[]> [<CommonParameters>]
```

### <span data-ttu-id="c2ed2-116">Filepathvmid</span><span class="sxs-lookup"><span data-stu-id="c2ed2-116">FilePathVMId</span></span>

```
Invoke-Command -Credential <PSCredential> [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [-AsJob] [-HideComputerName] [-FilePath] <String> [-RemoteDebug] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [-VMId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="c2ed2-117">Filepathvmname</span><span class="sxs-lookup"><span data-stu-id="c2ed2-117">FilePathVMName</span></span>

```
Invoke-Command -Credential <PSCredential> [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [-AsJob] [-HideComputerName] [-FilePath] <String> [-RemoteDebug] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] -VMName <String[]> [<CommonParameters>]
```

### <span data-ttu-id="c2ed2-118">Sshhost</span><span class="sxs-lookup"><span data-stu-id="c2ed2-118">SSHHost</span></span>

```
Invoke-Command [-Port <Int32>] [-AsJob] [-HideComputerName] [-JobName <String>]
 [-ScriptBlock] <ScriptBlock> -HostName <String[]> [-UserName <String>] [-KeyFilePath <String>]
 [-SSHTransport] [-RemoteDebug] [-InputObject <PSObject>] [-ArgumentList <Object[]>]
 [-Subsystem <String>] [<CommonParameters>]
```

### <span data-ttu-id="c2ed2-119">ContainerId</span><span class="sxs-lookup"><span data-stu-id="c2ed2-119">ContainerId</span></span>

```
Invoke-Command [-ConfigurationName <String>] [-ThrottleLimit <Int32>] [-AsJob] [-HideComputerName]
 [-JobName <String>] [-ScriptBlock] <ScriptBlock> [-RunAsAdministrator] [-RemoteDebug]
 [-InputObject <PSObject>] [-ArgumentList <Object[]>] -ContainerId <String[]> [<CommonParameters>]
```

### <span data-ttu-id="c2ed2-120">Filepathcontainerid</span><span class="sxs-lookup"><span data-stu-id="c2ed2-120">FilePathContainerId</span></span>

```
Invoke-Command [-ConfigurationName <String>] [-ThrottleLimit <Int32>] [-AsJob] [-HideComputerName]
 [-JobName <String>] [-FilePath] <String> [-RunAsAdministrator] [-RemoteDebug]
 [-InputObject <PSObject>] [-ArgumentList <Object[]>] -ContainerId <String[]> [<CommonParameters>]
```

### <span data-ttu-id="c2ed2-121">Sshhusthashparam</span><span class="sxs-lookup"><span data-stu-id="c2ed2-121">SSHHostHashParam</span></span>

```
Invoke-Command [-AsJob] [-HideComputerName] [-JobName <String>] [-ScriptBlock] <ScriptBlock>
 -SSHConnection <Hashtable[]> [-RemoteDebug] [-InputObject <PSObject>] [-ArgumentList <Object[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="c2ed2-122">Filepathsshhost</span><span class="sxs-lookup"><span data-stu-id="c2ed2-122">FilePathSSHHost</span></span>

```
Invoke-Command [-AsJob] [-HideComputerName] -FilePath <String> -HostName <String[]>
 [-UserName <String>] [-KeyFilePath <String>] [-SSHTransport] [-RemoteDebug]
 [-InputObject <PSObject>] [-ArgumentList <Object[]>] [<CommonParameters>]
```

### <span data-ttu-id="c2ed2-123">Filepathsshhusthash</span><span class="sxs-lookup"><span data-stu-id="c2ed2-123">FilePathSSHHostHash</span></span>

```
Invoke-Command [-AsJob] [-HideComputerName] -FilePath <String> -SSHConnection <Hashtable[]>
 [-RemoteDebug] [-InputObject <PSObject>] [-ArgumentList <Object[]>] [<CommonParameters>]
```

## <span data-ttu-id="c2ed2-124">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c2ed2-124">DESCRIPTION</span></span>

<span data-ttu-id="c2ed2-125">Das `Invoke-Command` -Cmdlet führt Befehle auf einem lokalen Computer oder einem Remote Computer aus und gibt alle Ausgaben der Befehle zurück, einschließlich der Fehler.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-125">The `Invoke-Command` cmdlet runs commands on a local or remote computer and returns all output from the commands, including errors.</span></span> <span data-ttu-id="c2ed2-126">Mit einem einzigen `Invoke-Command` Befehl können Sie Befehle auf mehreren Computern ausführen.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-126">Using a single `Invoke-Command` command, you can run commands on multiple computers.</span></span>

<span data-ttu-id="c2ed2-127">Um einen einzelnen Befehl auf einem Remotecomputer auszuführen, verwenden Sie den **ComputerName** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-127">To run a single command on a remote computer, use the **ComputerName** parameter.</span></span> <span data-ttu-id="c2ed2-128">Um eine Reihe verwandter Befehle auszuführen, die Daten gemeinsam nutzen, verwenden Sie das `New-PSSession` -Cmdlet, um eine **PSSession** (eine permanente Verbindung) auf dem Remote Computer zu erstellen, und verwenden Sie dann den **Session** -Parameter von, `Invoke-Command` um den Befehl in der **PSSession** auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-128">To run a series of related commands that share data, use the `New-PSSession` cmdlet to create a **PSSession** (a persistent connection) on the remote computer, and then use the **Session** parameter of `Invoke-Command` to run the command in the **PSSession**.</span></span> <span data-ttu-id="c2ed2-129">Verwenden Sie zum Ausführen eines Befehls in einer getrennten Sitzung den **InDisconnectedSession** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-129">To run a command in a disconnected session, use the **InDisconnectedSession** parameter.</span></span> <span data-ttu-id="c2ed2-130">Verwenden Sie zum Ausführen eines Befehls in einem Hintergrundauftrag den **AsJob** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-130">To run a command in a background job, use the **AsJob** parameter.</span></span>

<span data-ttu-id="c2ed2-131">Sie können auch `Invoke-Command` auf einem lokalen Computer mit einem Skriptblock als Befehl verwenden.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-131">You can also use `Invoke-Command` on a local computer to a script block as a command.</span></span> <span data-ttu-id="c2ed2-132">PowerShell führt den Skriptblock direkt in einem untergeordneten Bereich des aktuellen Gültigkeits Bereichs aus.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-132">PowerShell runs the script block immediately in a child scope of the current scope.</span></span>

<span data-ttu-id="c2ed2-133">`Invoke-Command`Lesen Sie vor der Verwendung von zum Ausführen von Befehlen auf einem Remote Computer [about_Remote](./About/about_Remote.md).</span><span class="sxs-lookup"><span data-stu-id="c2ed2-133">Before using `Invoke-Command` to run commands on a remote computer, read [about_Remote](./About/about_Remote.md).</span></span>

<span data-ttu-id="c2ed2-134">Ab PowerShell 6,0 können Sie Secure Shell (SSH) verwenden, um eine Verbindung mit herzustellen und Befehle auf Remote Computern aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-134">Starting with PowerShell 6.0 you can use Secure Shell (SSH) to establish a connection to and invoke commands on remote computers.</span></span> <span data-ttu-id="c2ed2-135">SSH muss auf dem lokalen Computer installiert sein, und der Remote Computer muss mit einem PowerShell-SSH-Endpunkt konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-135">SSH must be installed on the local computer and the remote computer must be configured with a PowerShell SSH endpoint.</span></span> <span data-ttu-id="c2ed2-136">Der Vorteil einer SSH-basierten PowerShell-Remote Sitzung besteht darin, dass Sie auf mehreren Plattformen (Windows, Linux, macOS) funktioniert.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-136">The benefit of an SSH based PowerShell remote session is that it works across multiple platforms (Windows, Linux, macOS).</span></span> <span data-ttu-id="c2ed2-137">Bei einer SSH-basierten Sitzung verwenden Sie die Parameter " **Hostname** " oder " **SshConnection** ", um den Remote Computer und relevante Verbindungsinformationen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-137">For SSH based session you use the **HostName** or **SSHConnection** parameters to specify the remote computer and relevant connection information.</span></span> <span data-ttu-id="c2ed2-138">Weitere Informationen zum Einrichten von PowerShell-SSH-Remoting finden Sie unter [PowerShell-Remoting über SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span><span class="sxs-lookup"><span data-stu-id="c2ed2-138">For more information about how to set up PowerShell SSH remoting, see [PowerShell Remoting Over SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span></span>

<span data-ttu-id="c2ed2-139">In einigen Codebeispielen wird Verteilung verwendet, um die Zeilenlänge zu verringern.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-139">Some code samples use splatting to reduce the line length.</span></span> <span data-ttu-id="c2ed2-140">Weitere Informationen finden Sie unter [about_Splatting](./About/about_Splatting.md).</span><span class="sxs-lookup"><span data-stu-id="c2ed2-140">For more information, see [about_Splatting](./About/about_Splatting.md).</span></span>

## <span data-ttu-id="c2ed2-141">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="c2ed2-141">EXAMPLES</span></span>

### <span data-ttu-id="c2ed2-142">Beispiel 1: Ausführen eines Skripts auf einem Server</span><span class="sxs-lookup"><span data-stu-id="c2ed2-142">Example 1: Run a script on a server</span></span>

<span data-ttu-id="c2ed2-143">In diesem Beispiel wird das `Test.ps1` Skript auf dem Computer Server01 ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-143">This example runs the `Test.ps1` script on the Server01 computer.</span></span>

```powershell
Invoke-Command -FilePath c:\scripts\test.ps1 -ComputerName Server01
```

<span data-ttu-id="c2ed2-144">Der **FilePath** -Parameter gibt ein Skript an, das sich auf dem lokalen Computer befindet.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-144">The **FilePath** parameter specifies a script that is located on the local computer.</span></span> <span data-ttu-id="c2ed2-145">Das Skript wird auf dem Remotecomputer ausgeführt, und die Ergebnisse werden an den lokalen Computer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-145">The script runs on the remote computer and the results are returned to the local computer.</span></span>

### <span data-ttu-id="c2ed2-146">Beispiel 2: Ausführen eines Befehls auf einem Remote Server</span><span class="sxs-lookup"><span data-stu-id="c2ed2-146">Example 2: Run a command on a remote server</span></span>

<span data-ttu-id="c2ed2-147">In diesem Beispiel wird ein `Get-Culture` Befehl auf dem Remote Computer Server01 ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-147">This example runs a `Get-Culture` command on the Server01 remote computer.</span></span>

```powershell
Invoke-Command -ComputerName Server01 -Credential Domain01\User01 -ScriptBlock { Get-Culture }
```

<span data-ttu-id="c2ed2-148">Der **Computername** -Parameter gibt den Namen des Remote Computers an.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-148">The **ComputerName** parameter specifies the name of the remote computer.</span></span> <span data-ttu-id="c2ed2-149">Der **Credential** -Parameter wird verwendet, um den Befehl im Sicherheitskontext von Domain01\User01 auszuführen, einem Benutzer, der über die Berechtigung zum Ausführen von Befehlen verfügt.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-149">The **Credential** parameter is used to run the command in the security context of Domain01\User01, a user who has permission to run commands.</span></span> <span data-ttu-id="c2ed2-150">Der **ScriptBlock** -Parameter gibt den Befehl an, der auf dem Remote Computer ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-150">The **ScriptBlock** parameter specifies the command to be run on the remote computer.</span></span>

<span data-ttu-id="c2ed2-151">In der Antwort fordert PowerShell das Kennwort und eine Authentifizierungsmethode für das USER01-Konto an.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-151">In response, PowerShell requests the password and an authentication method for the User01 account.</span></span>
<span data-ttu-id="c2ed2-152">Anschließend wird der Befehl auf dem Computer „Server01“ ausgeführt und das Ergebnis zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-152">It then runs the command on the Server01 computer and returns the result.</span></span>

### <span data-ttu-id="c2ed2-153">Beispiel 3: Ausführen eines Befehls in einer permanenten Verbindung</span><span class="sxs-lookup"><span data-stu-id="c2ed2-153">Example 3: Run a command in a persistent connection</span></span>

<span data-ttu-id="c2ed2-154">In diesem Beispiel wird derselbe `Get-Culture` Befehl in einer Sitzung mit einer permanenten Verbindung auf dem Remote Computer mit dem Namen Server02 ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-154">This example runs the same `Get-Culture` command in a session, using a persistent connection, on the remote computer named Server02.</span></span>

```powershell
$s = New-PSSession -ComputerName Server02 -Credential Domain01\User01
Invoke-Command -Session $s -ScriptBlock {Get-Culture}
```

<span data-ttu-id="c2ed2-155">`New-PSSession`Mit dem-Cmdlet wird eine Sitzung auf dem Remote Computer Server02 erstellt und in der `$s` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-155">The `New-PSSession` cmdlet creates a session on the Server02 remote computer and saves it in the `$s` variable.</span></span> <span data-ttu-id="c2ed2-156">In der Regel erstellen Sie eine Sitzung nur, wenn Sie eine Reihe von Befehlen auf dem Remote Computer ausführen.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-156">Typically, you create a session only when you run a series of commands on the remote computer.</span></span>

<span data-ttu-id="c2ed2-157">Das- `Invoke-Command` Cmdlet führt den `Get-Culture` Befehl auf Server02 aus.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-157">The `Invoke-Command` cmdlet runs the `Get-Culture` command on Server02.</span></span> <span data-ttu-id="c2ed2-158">Der **Session** -Parameter gibt die in der Variablen gespeicherte Sitzung an `$s` .</span><span class="sxs-lookup"><span data-stu-id="c2ed2-158">The **Session** parameter specifies the session saved in the `$s` variable.</span></span>

<span data-ttu-id="c2ed2-159">In der Antwort führt PowerShell den Befehl in der Sitzung auf dem Server02-Computer aus.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-159">In response, PowerShell runs the command in the session on the Server02 computer.</span></span>

### <span data-ttu-id="c2ed2-160">Beispiel 4: Verwenden einer Sitzung zum Ausführen einer Reihe von Befehlen, die Daten freigeben</span><span class="sxs-lookup"><span data-stu-id="c2ed2-160">Example 4: Use a session to run a series of commands that share data</span></span>

<span data-ttu-id="c2ed2-161">In diesem Beispiel werden die Auswirkungen der Verwendung von **Computername** und **Sitzungs** Parametern von verglichen `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="c2ed2-161">This example compares the effects of using **ComputerName** and **Session** parameters of `Invoke-Command`.</span></span> <span data-ttu-id="c2ed2-162">Es veranschaulicht, wie Sie eine Sitzung verwenden können, um eine Reihe von Befehlen auszuführen, die gemeinsam die gleichen Daten nutzen.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-162">It shows how to use a session to run a series of commands that share the same data.</span></span>

```powershell
Invoke-Command -ComputerName Server02 -ScriptBlock {$p = Get-Process PowerShell}
Invoke-Command -ComputerName Server02 -ScriptBlock {$p.VirtualMemorySize}
$s = New-PSSession -ComputerName Server02
Invoke-Command -Session $s -ScriptBlock {$p = Get-Process PowerShell}
Invoke-Command -Session $s -ScriptBlock {$p.VirtualMemorySize}
```

```Output
17930240
```

<span data-ttu-id="c2ed2-163">Die ersten beiden Befehle verwenden den **Computername** -Parameter von `Invoke-Command` , um Befehle auf dem Remote Computer Server02 auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-163">The first two commands use the **ComputerName** parameter of `Invoke-Command` to run commands on the Server02 remote computer.</span></span> <span data-ttu-id="c2ed2-164">Der erste Befehl verwendet das `Get-Process` Cmdlet, um den PowerShell-Prozess auf dem Remote Computer zu erhalten und in der `$p` Variablen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-164">The first command uses the `Get-Process` cmdlet to get the PowerShell process on the remote computer and to save it in the `$p` variable.</span></span> <span data-ttu-id="c2ed2-165">Der zweite Befehl ruft den Wert der **VirtualMemorySize** -Eigenschaft des PowerShell-Prozesses ab.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-165">The second command gets the value of the **VirtualMemorySize** property of the PowerShell process.</span></span>

<span data-ttu-id="c2ed2-166">Wenn Sie den **Computername** -Parameter verwenden, erstellt PowerShell eine neue Sitzung, um den Befehl auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-166">When you use the **ComputerName** parameter, PowerShell creates a new session to run the command.</span></span>
<span data-ttu-id="c2ed2-167">Die Sitzung wird geschlossen, wenn der Befehl abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-167">The session is closed when the command completes.</span></span> <span data-ttu-id="c2ed2-168">Die `$p` Variable wurde in einer Verbindung erstellt, ist jedoch nicht in der für den zweiten Befehl erstellten Verbindung vorhanden.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-168">The `$p` variable was created in one connection, but it doesn't exist in the connection created for the second command.</span></span>

<span data-ttu-id="c2ed2-169">Das Problem wird gelöst, indem eine persistente Sitzung auf dem Remote Computer erstellt und dann beide Befehle in der gleichen Sitzung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-169">The problem is solved by creating a persistent session on the remote computer, then running both of the commands in the same session.</span></span>

<span data-ttu-id="c2ed2-170">`New-PSSession`Mit dem-Cmdlet wird eine persistente Sitzung auf dem Computer Server02 erstellt und die Sitzung in der `$s` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-170">The `New-PSSession` cmdlet creates a persistent session on the computer Server02 and saves the session in the `$s` variable.</span></span> <span data-ttu-id="c2ed2-171">`Invoke-Command`In den folgenden Zeilen wird der **Session** -Parameter verwendet, um beide Befehle in der gleichen Sitzung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-171">The `Invoke-Command` lines that follow use the **Session** parameter to run both of the commands in the same session.</span></span> <span data-ttu-id="c2ed2-172">Da beide Befehle in der gleichen Sitzung ausgeführt werden, `$p` bleibt der Wert aktiv.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-172">Since both commands run in the same session, the `$p` value remains active.</span></span>

### <span data-ttu-id="c2ed2-173">Beispiel 5: Eingeben eines Befehls, der in einer lokalen Variablen gespeichert ist</span><span class="sxs-lookup"><span data-stu-id="c2ed2-173">Example 5: Enter a command stored in a local variable</span></span>

<span data-ttu-id="c2ed2-174">Dieses Beispiel zeigt, wie Sie einen Befehl erstellen, der als Skriptblock in einer lokalen Variablen gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-174">This example shows how to create a command that is stored as a script block in a local variable.</span></span>
<span data-ttu-id="c2ed2-175">Wenn der Skriptblock in einer lokalen Variablen gespeichert wird, können Sie die Variable als Wert des **ScriptBlock** -Parameters angeben.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-175">When the script block is saved in a local variable, you can specify the variable as the value of the **ScriptBlock** parameter.</span></span>

```powershell
$command = { Get-WinEvent -LogName PowerShellCore/Operational |
  Where-Object {$_.Message -like "*certificate*"} }
Invoke-Command -ComputerName S1, S2 -ScriptBlock $command
```

<span data-ttu-id="c2ed2-176">Die `$command` -Variable speichert den `Get-WinEvent` Befehl, der als Skriptblock formatiert ist.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-176">The `$command` variable stores the `Get-WinEvent` command that's formatted as a script block.</span></span> <span data-ttu-id="c2ed2-177">Der `Invoke-Command` führt den in gespeicherten Befehl `$command` auf den Remote Computern S1 und S2 aus.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-177">The `Invoke-Command` runs the command stored in `$command` on the S1 and S2 remote computers.</span></span>

### <span data-ttu-id="c2ed2-178">Beispiel 6: Ausführen eines einzelnen Befehls auf mehreren Computern</span><span class="sxs-lookup"><span data-stu-id="c2ed2-178">Example 6: Run a single command on several computers</span></span>

<span data-ttu-id="c2ed2-179">In diesem Beispiel wird veranschaulicht, wie verwendet wird, `Invoke-Command` um einen einzelnen Befehl auf mehreren Computern auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-179">This example demonstrates how to use `Invoke-Command` to run a single command on multiple computers.</span></span>

```powershell
$parameters = @{
  ComputerName = "Server01", "Server02", "TST-0143", "localhost"
  ConfigurationName = 'MySession.PowerShell'
  ScriptBlock = { Get-WinEvent -LogName PowerShellCore/Operational }
}
Invoke-Command @parameters
```

<span data-ttu-id="c2ed2-180">Der Computer **Name** -Parameter gibt eine durch Trennzeichen getrennte Liste von Computernamen an.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-180">The **ComputerName** parameter specifies a comma-separated list of computer names.</span></span> <span data-ttu-id="c2ed2-181">Die Liste der Computer enthält den Wert "localhost", der den lokalen Computer darstellt.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-181">The list of computers includes the localhost value, which represents the local computer.</span></span> <span data-ttu-id="c2ed2-182">Der **ConfigurationName** -Parameter gibt eine Alternative Sitzungs Konfiguration an.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-182">The **ConfigurationName** parameter specifies an alternate session configuration.</span></span> <span data-ttu-id="c2ed2-183">Der **ScriptBlock** -Parameter wird ausgeführt `Get-WinEvent` , um die powershellcore-/Operational-Ereignisprotokolle von den einzelnen Computern zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-183">The **ScriptBlock** parameter runs `Get-WinEvent` to get the PowerShellCore/Operational event logs from each computer.</span></span>

### <span data-ttu-id="c2ed2-184">Beispiel 7: erhalten der Version des Host Programms auf mehreren Computern</span><span class="sxs-lookup"><span data-stu-id="c2ed2-184">Example 7: Get the version of the host program on multiple computers</span></span>

<span data-ttu-id="c2ed2-185">In diesem Beispiel wird die Version des PowerShell-Host Programms abgerufen, das auf 200 Remote Computern ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-185">This example gets the version of the PowerShell host program running on 200 remote computers.</span></span>

```powershell
$version = Invoke-Command -ComputerName (Get-Content Machines.txt) -ScriptBlock {(Get-Host).Version}
```

<span data-ttu-id="c2ed2-186">Da nur ein Befehl ausgeführt wird, müssen Sie keine permanenten Verbindungen mit den einzelnen Computern erstellen.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-186">Because only one command is run, you don't have to create persistent connections to each of the computers.</span></span> <span data-ttu-id="c2ed2-187">Der Befehl verwendet stattdessen den **ComputerName** -Parameter, um die Computer anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-187">Instead, the command uses the **ComputerName** parameter to indicate the computers.</span></span> <span data-ttu-id="c2ed2-188">Zum Angeben der Computer wird mit dem `Get-Content` Cmdlet der Inhalt der Machine.txt Datei (eine Datei mit Computernamen) erhalten.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-188">To specify the computers, it uses the `Get-Content` cmdlet to get the contents of the Machine.txt file, a file of computer names.</span></span>

<span data-ttu-id="c2ed2-189">Das- `Invoke-Command` Cmdlet führt einen `Get-Host` Befehl auf den Remote Computern aus.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-189">The `Invoke-Command` cmdlet runs a `Get-Host` command on the remote computers.</span></span> <span data-ttu-id="c2ed2-190">Er verwendet die Punkt Notation, um die **Versions** Eigenschaft des PowerShell-Hosts zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-190">It uses dot notation to get the **Version** property of the PowerShell host.</span></span>

<span data-ttu-id="c2ed2-191">Diese Befehle werden nacheinander ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-191">These commands run one at a time.</span></span> <span data-ttu-id="c2ed2-192">Wenn die Befehle vollständig sind, wird die Ausgabe der Befehle von allen Computern in der Variablen gespeichert `$version` .</span><span class="sxs-lookup"><span data-stu-id="c2ed2-192">When the commands complete, the output of the commands from all of the computers is saved in the `$version` variable.</span></span> <span data-ttu-id="c2ed2-193">Die Ausgabe enthält den Namen des Computers, von dem die Daten stammen.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-193">The output includes the name of the computer from which the data originated.</span></span>

### <span data-ttu-id="c2ed2-194">Beispiel 8: Ausführen eines Hintergrund Auftrags auf mehreren Remote Computern</span><span class="sxs-lookup"><span data-stu-id="c2ed2-194">Example 8: Run a background job on several remote computers</span></span>

<span data-ttu-id="c2ed2-195">In diesem Beispiel wird ein Befehl auf zwei Remote Computern ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-195">This example runs a command on two remote computers.</span></span> <span data-ttu-id="c2ed2-196">Der `Invoke-Command` Befehl verwendet den **AsJob** -Parameter, sodass der Befehl als Hintergrund Auftrag ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-196">The `Invoke-Command` command uses the **AsJob** parameter so that the command runs as a background job.</span></span> <span data-ttu-id="c2ed2-197">Die Befehle werden auf den Remote Computern ausgeführt, der Auftrag ist jedoch auf dem lokalen Computer vorhanden.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-197">The commands run on the remote computers, but the job exists on the local computer.</span></span> <span data-ttu-id="c2ed2-198">Die Ergebnisse werden an den lokalen Computer übertragen.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-198">The results are transmitted to the local computer.</span></span>

```powershell
$s = New-PSSession -ComputerName Server01, Server02
Invoke-Command -Session $s -ScriptBlock {Get-EventLog system} -AsJob
```

```Output
Id   Name    State      HasMoreData   Location           Command
---  ----    -----      -----         -----------        ---------------
1    Job1    Running    True          Server01,Server02  Get-EventLog system
```

```powershell
$j = Get-Job
$j | Format-List -Property *
```

```Output
HasMoreData   : True
StatusMessage :
Location      : Server01,Server02
Command       : Get-EventLog system
JobStateInfo  : Running
Finished      : System.Threading.ManualResetEvent
InstanceId    : e124bb59-8cb2-498b-a0d2-2e07d4e030ca
Id            : 1
Name          : Job1
ChildJobs     : {Job2, Job3}
Output        : {}
Error         : {}
Progress      : {}
Verbose       : {}
Debug         : {}
Warning       : {}
StateChanged  :
```

```powershell
$results = $j | Receive-Job
```

<span data-ttu-id="c2ed2-199">Das `New-PSSession` -Cmdlet erstellt Sitzungen auf den Remote Computern Server01 und Server02.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-199">The `New-PSSession` cmdlet creates sessions on the Server01 and Server02 remote computers.</span></span> <span data-ttu-id="c2ed2-200">Das- `Invoke-Command` Cmdlet führt in jeder Sitzung einen Hintergrund Auftrag aus.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-200">The `Invoke-Command` cmdlet runs a background job in each of the sessions.</span></span> <span data-ttu-id="c2ed2-201">Bei dem Befehl wird der Befehl mithilfe des **AsJob** -Parameters als Hintergrundauftrag ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-201">The command uses the **AsJob** parameter to run the command as a background job.</span></span> <span data-ttu-id="c2ed2-202">Dieser Befehl gibt ein Auftragsobjekt zurück, das zwei untergeordnete Auftragsobjekte enthält, jeweils eins für die Aufträge, die auf zwei Remotecomputern ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-202">This command returns a job object that contains two child job objects, one for each of the jobs run on the two remote computers.</span></span>

<span data-ttu-id="c2ed2-203">Der `Get-Job` Befehl speichert das Auftrags Objekt in der `$j` Variablen.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-203">The `Get-Job` command saves the job object in the `$j` variable.</span></span> <span data-ttu-id="c2ed2-204">Die `$j` Variable wird dann an das `Format-List` Cmdlet weitergeleitet, um alle Eigenschaften des Auftrags Objekts in einer Liste anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-204">The `$j` variable is then piped to the `Format-List` cmdlet to display all properties of the job object in a list.</span></span> <span data-ttu-id="c2ed2-205">Mit dem letzten Befehl werden die Ergebnisse der Aufträge abgerufen.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-205">The last command gets the results of the jobs.</span></span> <span data-ttu-id="c2ed2-206">Das Auftrags Objekt wird an `$j` das `Receive-Job` Cmdlet weitergeleitet, und die Ergebnisse werden in der `$results` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-206">It pipes the job object in `$j` to the `Receive-Job` cmdlet and stores the results in the `$results` variable.</span></span>

### <span data-ttu-id="c2ed2-207">Beispiel 9: einschließen lokaler Variablen in einem Befehl, der auf einem Remote Computer ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="c2ed2-207">Example 9: Include local variables in a command run on a remote computer</span></span>

<span data-ttu-id="c2ed2-208">Dieses Beispiel zeigt, wie Sie die Werte von lokalen Variablen in einem Befehl einschließen können, der auf einem Remotecomputer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-208">This example shows how to include the values of local variables in a command run on a remote computer.</span></span> <span data-ttu-id="c2ed2-209">Der Befehl verwendet den `Using` Scope-Modifizierer, um eine lokale Variable in einem Remote Befehl zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-209">The command uses the `Using` scope modifier to identify a local variable in a remote command.</span></span> <span data-ttu-id="c2ed2-210">Standardmäßig wird davon ausgegangen, dass alle Variablen in der Remotesitzung definiert sind.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-210">By default, all variables are assumed to be defined in the remote session.</span></span> <span data-ttu-id="c2ed2-211">Der bereichsmodifizierer `Using` wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-211">The `Using` scope modifier was introduced in PowerShell 3.0.</span></span> <span data-ttu-id="c2ed2-212">Weitere Informationen zum bereichsmodifizierer `Using` finden Sie unter [about_Remote_Variables](./About/about_Remote_Variables.md) und [about_Scopes](./about/about_scopes.md).</span><span class="sxs-lookup"><span data-stu-id="c2ed2-212">For more information about the `Using` scope modifier, see [about_Remote_Variables](./About/about_Remote_Variables.md) and [about_Scopes](./about/about_scopes.md).</span></span>

```powershell
$Log = "PowerShellCore/Operational"
Invoke-Command -ComputerName Server01 -ScriptBlock {Get-WinEvent -LogName $Using:Log -MaxEvents 10}
```

<span data-ttu-id="c2ed2-213">Die `$Log` Variable speichert den Namen des Ereignis Protokolls, powershellcore/Operational.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-213">The `$Log` variable stores the name of the event log, PowerShellCore/Operational.</span></span> <span data-ttu-id="c2ed2-214">Das- `Invoke-Command` Cmdlet wird `Get-WinEvent` auf Server01 ausgeführt, um die zehn neuesten Ereignisse aus dem Ereignisprotokoll zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-214">The `Invoke-Command` cmdlet runs `Get-WinEvent` on Server01 to get the ten newest events from the event log.</span></span> <span data-ttu-id="c2ed2-215">Der Wert des **logName** -Parameters ist die Variable, der der bereichsmodifizierer `$Log` vorangestellt wird, `Using` um anzugeben, dass er in der lokalen Sitzung erstellt wurde, nicht in der Remote Sitzung.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-215">The value of the **LogName** parameter is the `$Log` variable that is prefixed by the `Using` scope modifier to indicate that it was created in the local session, not in the remote session.</span></span>

### <span data-ttu-id="c2ed2-216">Beispiel 10: Ausblenden des Computer namens</span><span class="sxs-lookup"><span data-stu-id="c2ed2-216">Example 10: Hide the computer name</span></span>

<span data-ttu-id="c2ed2-217">Dieses Beispiel zeigt die Auswirkung der Verwendung des **hidecomputername** -Parameters von `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="c2ed2-217">This example shows the effect of using the **HideComputerName** parameter of `Invoke-Command`.</span></span>
<span data-ttu-id="c2ed2-218">**Hidecomputername** ändert nicht das Objekt, das von diesem Cmdlet zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-218">**HideComputerName** doesn't change the object that this cmdlet returns.</span></span> <span data-ttu-id="c2ed2-219">Es ändert nur die Anzeige.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-219">It changes only the display.</span></span> <span data-ttu-id="c2ed2-220">Sie können weiterhin die **Format** -Cmdlets verwenden, um die **pscomputername** -Eigenschaft der betroffenen Objekte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-220">You can still use the **Format** cmdlets to display the **PsComputerName** property of any of the affected objects.</span></span>

```powershell
Invoke-Command -ComputerName S1, S2 -ScriptBlock {Get-Process PowerShell}
```

```Output
PSComputerName    Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id   ProcessName
--------------    -------  ------    -----      ----- -----   ------     --   -----------
S1                575      15        45100      40988   200     4.68     1392 PowerShell
S2                777      14        35100      30988   150     3.68     67   PowerShell
```

```powershell
Invoke-Command -ComputerName S1, S2 -ScriptBlock {Get-Process PowerShell} -HideComputerName
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id   ProcessName
-------  ------    -----      ----- -----   ------     --   -----------
575      15        45100      40988   200     4.68     1392 PowerShell
777      14        35100      30988   150     3.68     67   PowerShell
```

<span data-ttu-id="c2ed2-221">Die ersten beiden Befehle verwenden `Invoke-Command` , um einen `Get-Process` Befehl für den PowerShell-Prozess auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-221">The first two commands use `Invoke-Command` to run a `Get-Process` command for the PowerShell process.</span></span> <span data-ttu-id="c2ed2-222">Die Ausgabe des ersten Befehls enthält die **PsComputerName** -Eigenschaft, die den Namen des Computers enthält, auf dem der Befehl ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-222">The output of the first command includes the **PsComputerName** property, which contains the name of the computer on which the command ran.</span></span> <span data-ttu-id="c2ed2-223">Die Ausgabe des zweiten Befehls, der **hidecomputername** verwendet, enthält nicht die **pscomputername** -Spalte.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-223">The output of the second command, which uses **HideComputerName** , doesn't include the **PsComputerName** column.</span></span>

### <span data-ttu-id="c2ed2-224">Beispiel 11: Verwenden des param-Schlüssel Worts in einem Skriptblock</span><span class="sxs-lookup"><span data-stu-id="c2ed2-224">Example 11: Use the Param keyword in a script block</span></span>

<span data-ttu-id="c2ed2-225">Das `Param` Schlüsselwort und der Argument **List** -Parameter werden verwendet, um Variablen Werte an benannte Parameter in einem Skriptblock zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-225">The `Param` keyword and the **ArgumentList** parameter are used to pass variable values to named parameters in a script block.</span></span> <span data-ttu-id="c2ed2-226">In diesem Beispiel werden Dateinamen angezeigt, die mit dem Buchstaben beginnen `a` und die `.pdf` Erweiterung aufweisen.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-226">This example displays filenames that begin with the letter `a` and have the `.pdf` extension.</span></span>

<span data-ttu-id="c2ed2-227">Weitere Informationen zum- `Param` Schlüsselwort finden Sie unter [about_Language_Keywords](./about/about_language_keywords.md#param).</span><span class="sxs-lookup"><span data-stu-id="c2ed2-227">For more information about the `Param` keyword, see [about_Language_Keywords](./about/about_language_keywords.md#param).</span></span>

```powershell
$parameters = @{
    ComputerName = "Server01"
    ScriptBlock = { Param ($param1,$param2) Get-ChildItem -Name $param1 -Include $param2 }
    ArgumentList = "a*", "*.pdf"
}
Invoke-Command @parameters
```

```Output
aa.pdf
ab.pdf
ac.pdf
az.pdf
```

<span data-ttu-id="c2ed2-228">`Invoke-Command` verwendet den **ScriptBlock** -Parameter, der zwei Variablen definiert, `$param1` und `$param2` .</span><span class="sxs-lookup"><span data-stu-id="c2ed2-228">`Invoke-Command` uses the **ScriptBlock** parameter that defines two variables, `$param1` and `$param2`.</span></span> <span data-ttu-id="c2ed2-229">`Get-ChildItem` verwendet die benannten Parameter **Name** und **include** mit den Variablennamen.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-229">`Get-ChildItem` uses the named parameters, **Name** and **Include** with the variable names.</span></span> <span data-ttu-id="c2ed2-230">Die Argument **List** übergibt die Werte an die Variablen.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-230">The **ArgumentList** passes the values to the variables.</span></span>

### <span data-ttu-id="c2ed2-231">Beispiel 12: Verwenden der automatischen $args automatischen Variablen in einem Skriptblock</span><span class="sxs-lookup"><span data-stu-id="c2ed2-231">Example 12: Use the $args automatic variable in a script block</span></span>

<span data-ttu-id="c2ed2-232">Die `$args` Automatische Variable und der Argument **List** -Parameter werden verwendet, um Array Werte an Parameter Positionen in einem Skriptblock zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-232">The `$args` automatic variable and the **ArgumentList** parameter are used to pass array values to parameter positions in a script block.</span></span> <span data-ttu-id="c2ed2-233">In diesem Beispiel wird der Verzeichnis Inhalt eines Servers der- `.txt` Dateien angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-233">This example displays a server's directory contents of `.txt` files.</span></span> <span data-ttu-id="c2ed2-234">Der `Get-ChildItem` **path** -Parameter ist Position 0, und der **Filter** -Parameter ist Position.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-234">The `Get-ChildItem` **Path** parameter is position 0 and the **Filter** parameter is position</span></span>
1.

<span data-ttu-id="c2ed2-235">Weitere Informationen zur `$args` Variablen finden Sie unter [about_Automatic_Variables](./about/about_automatic_variables.md#args)</span><span class="sxs-lookup"><span data-stu-id="c2ed2-235">For more information about the `$args` variable, see [about_Automatic_Variables](./about/about_automatic_variables.md#args)</span></span>

```powershell
$parameters = @{
    ComputerName = "Server01"
    ScriptBlock = { Get-ChildItem $args[0] $args[1] }
    ArgumentList = "C:\Test", "*.txt*"
}
Invoke-Command @parameters
```

```Output
    Directory: C:\Test

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           6/12/2019    15:15            128 alog.txt
-a---           7/27/2019    15:16            256 blog.txt
-a---           9/28/2019    17:10             64 zlog.txt
```

<span data-ttu-id="c2ed2-236">`Invoke-Command` verwendet einen **ScriptBlock** -Parameter und `Get-ChildItem` gibt `$args[0]` die `$args[1]` Array Werte und an.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-236">`Invoke-Command` uses a **ScriptBlock** parameter and `Get-ChildItem` specifies the `$args[0]` and `$args[1]` array values.</span></span> <span data-ttu-id="c2ed2-237">Die Argument **List** übergibt die `$args` Array Werte an die `Get-ChildItem` Parameter Positionen für **path** und **Filter**.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-237">The **ArgumentList** passes the `$args` array values to the `Get-ChildItem` parameter positions for **Path** and **Filter**.</span></span>

### <span data-ttu-id="c2ed2-238">Beispiel 13: Ausführen eines Skripts auf allen in einer Textdatei aufgeführten Computern</span><span class="sxs-lookup"><span data-stu-id="c2ed2-238">Example 13: Run a script on all the computers listed in a text file</span></span>

<span data-ttu-id="c2ed2-239">In diesem Beispiel wird das- `Invoke-Command` Cmdlet verwendet, um das `Sample.ps1` Skript auf allen Computern auszuführen, die in der Datei aufgelistet sind `Servers.txt` .</span><span class="sxs-lookup"><span data-stu-id="c2ed2-239">This example uses the `Invoke-Command` cmdlet to run the `Sample.ps1` script on all the computers listed in the `Servers.txt` file.</span></span> <span data-ttu-id="c2ed2-240">Der Befehl verwendet den **FilePath** -Parameter, um die Skriptdatei anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-240">The command uses the **FilePath** parameter to specify the script file.</span></span> <span data-ttu-id="c2ed2-241">Mit diesem Befehl können Sie das Skript auf den Remote Computern ausführen, selbst wenn die Skriptdatei für die Remote Computer nicht zugänglich ist.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-241">This command lets you run the script on the remote computers, even if the script file isn't accessible to the remote computers.</span></span>

```powershell
Invoke-Command -ComputerName (Get-Content Servers.txt) -FilePath C:\Scripts\Sample.ps1 -ArgumentList Process, Service
```

<span data-ttu-id="c2ed2-242">Wenn Sie den Befehl senden, wird der Inhalt der `Sample.ps1` Datei in einen Skriptblock kopiert, und der Skriptblock wird auf jedem Remote Computer ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-242">When you submit the command, the content of the `Sample.ps1` file is copied into a script block and the script block is run on each of the remote computers.</span></span> <span data-ttu-id="c2ed2-243">Dieses Verfahren entspricht der Verwendung des **ScriptBlock** -Parameters, um den Inhalt des Skripts zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-243">This procedure is equivalent to using the **ScriptBlock** parameter to submit the contents of the script.</span></span>

### <span data-ttu-id="c2ed2-244">Beispiel 14: Ausführen eines Befehls auf einem Remote Computer mithilfe eines URI</span><span class="sxs-lookup"><span data-stu-id="c2ed2-244">Example 14: Run a command on a remote computer using a URI</span></span>

<span data-ttu-id="c2ed2-245">In diesem Beispiel wird gezeigt, wie ein Befehl auf einem Remote Computer ausgeführt wird, der durch einen Uniform Resource Identifier (URI) identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-245">This example shows how to run a command on a remote computer that's identified by a Uniform Resource Identifier (URI).</span></span> <span data-ttu-id="c2ed2-246">Dieses spezielle Beispiel führt einen `Set-Mailbox` Befehl auf einem Exchange-Remote Server aus.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-246">This particular example runs a `Set-Mailbox` command on a remote Exchange server.</span></span>

```powershell
$LiveCred = Get-Credential
$parameters = @{
  ConfigurationName = 'Microsoft.Exchange'
  ConnectionUri = 'https://ps.exchangelabs.com/PowerShell'
  Credential = $LiveCred
  Authentication = 'Basic'
  ScriptBlock = {Set-Mailbox Dan -DisplayName "Dan Park"}
}
Invoke-Command @parameters
```

<span data-ttu-id="c2ed2-247">Die erste Zeile verwendet das `Get-Credential` Cmdlet zum Speichern der Windows Live ID-Anmelde Informationen in der `$LiveCred` Variablen.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-247">The first line uses the `Get-Credential` cmdlet to store Windows Live ID credentials in the `$LiveCred` variable.</span></span> <span data-ttu-id="c2ed2-248">PowerShell fordert den Benutzer auf, Windows Live ID-Anmelde Informationen einzugeben.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-248">PowerShell prompts the user to enter Windows Live ID credentials.</span></span>

<span data-ttu-id="c2ed2-249">Die- `$parameters` Variable ist eine Hash Tabelle mit den Parametern, die an das `Invoke-Command` Cmdlet übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-249">The `$parameters` variable is a hash table containing the parameters to be passed to the `Invoke-Command` cmdlet.</span></span> <span data-ttu-id="c2ed2-250">Das- `Invoke-Command` Cmdlet führt einen `Set-Mailbox` Befehl mithilfe der **Microsoft. Exchange** -Sitzungs Konfiguration aus.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-250">The `Invoke-Command` cmdlet runs a `Set-Mailbox` command using the **Microsoft.Exchange** session configuration.</span></span> <span data-ttu-id="c2ed2-251">Der **ConnectionURI** -Parameter gibt den URL des Exchange-Serverendpunkts an.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-251">The **ConnectionURI** parameter specifies the URL of the Exchange server endpoint.</span></span> <span data-ttu-id="c2ed2-252">Der **Credential** -Parameter gibt die in der Variablen gespeicherten Anmelde Informationen an `$LiveCred` .</span><span class="sxs-lookup"><span data-stu-id="c2ed2-252">The **Credential** parameter specifies the credentials stored in the `$LiveCred` variable.</span></span> <span data-ttu-id="c2ed2-253">Der **AuthenticationMechanism** -Parameter gibt die Verwendung der Standardauthentifizierung an.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-253">The **AuthenticationMechanism** parameter specifies the use of basic authentication.</span></span> <span data-ttu-id="c2ed2-254">Der **ScriptBlock** -Parameter gibt einen Skriptblock mit dem Befehl an.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-254">The **ScriptBlock** parameter specifies a script block that contains the command.</span></span>

### <span data-ttu-id="c2ed2-255">Beispiel 15: Verwenden einer Sitzungs Option</span><span class="sxs-lookup"><span data-stu-id="c2ed2-255">Example 15: Use a session option</span></span>

<span data-ttu-id="c2ed2-256">Dieses Beispiel zeigt, wie Sie einen **sessionoption** -Parameter erstellen und verwenden.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-256">This example shows how to create and use a **SessionOption** parameter.</span></span>

```powershell
$so = New-PSSessionOption -SkipCACheck -SkipCNCheck -SkipRevocationCheck
Invoke-Command -ComputerName server01 -UseSSL -ScriptBlock { Get-HotFix } -SessionOption $so -Credential server01\user01
```

<span data-ttu-id="c2ed2-257">Mit dem- `New-PSSessionOption` Cmdlet wird ein Sitzungs Options Objekt erstellt, das bewirkt, dass die Zertifizierungsstelle, der kanonische Name und die Sperr Listen beim Auswerten der eingehenden HTTPS-Verbindung vom Remote Ende nicht überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-257">The `New-PSSessionOption` cmdlet creates a session option object that causes the remote end not to verify the Certificate Authority, Canonical Name, and Revocation Lists while evaluating the incoming HTTPS connection.</span></span> <span data-ttu-id="c2ed2-258">Das **sessionoption** -Objekt wird in der `$so` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-258">The **SessionOption** object is saved in the `$so` variable.</span></span>

> [!NOTE]
> <span data-ttu-id="c2ed2-259">Die Deaktivierung dieser Überprüfungen ist praktisch für die Problembehandlung, aber offensichtlich nicht sicher.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-259">Disabling these checks is convenient for troubleshooting, but obviously not secure.</span></span>

<span data-ttu-id="c2ed2-260">Das- `Invoke-Command` Cmdlet führt einen `Get-HotFix` Befehl Remote aus.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-260">The `Invoke-Command` cmdlet runs a `Get-HotFix` command remotely.</span></span> <span data-ttu-id="c2ed2-261">Der **sessionoption** -Parameter wird der- `$so` Variablen zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-261">The **SessionOption** parameter is given the `$so` variable.</span></span>

### <span data-ttu-id="c2ed2-262">Beispiel 16: Verwalten der URI-Umleitung in einem Remote Befehl</span><span class="sxs-lookup"><span data-stu-id="c2ed2-262">Example 16: Manage URI redirection in a remote command</span></span>

<span data-ttu-id="c2ed2-263">In diesem Beispiel wird gezeigt, wie die Parameter " **Zuweisung** " und " **sessionoption** " verwendet werden, um die URI-Umleitung in einem Remote Befehl zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-263">This example shows how to use the **AllowRedirection** and **SessionOption** parameters to manage URI redirection in a remote command.</span></span>

```powershell
$max = New-PSSessionOption -MaximumRedirection 1
$parameters = @{
  ConnectionUri = "https://ps.exchangelabs.com/PowerShell"
  ScriptBlock = { Get-Mailbox dan }
  AllowRedirection = $true
  SessionOption = $max
}
Invoke-Command @parameters
```

<span data-ttu-id="c2ed2-264">Mit dem- `New-PSSessionOption` Cmdlet wird ein **pssessionoption** -Objekt erstellt, das in der Variablen gespeichert wird `$max` .</span><span class="sxs-lookup"><span data-stu-id="c2ed2-264">The `New-PSSessionOption` cmdlet creates a **PSSessionOption** object that is saved in the `$max` variable.</span></span> <span data-ttu-id="c2ed2-265">Der Befehl verwendet den **MaximumRedirection** -Parameter zum Festlegen der **MaximumConnectionRedirectionCount** -Eigenschaft des **PSSessionOption** -Objekts auf 1.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-265">The command uses the **MaximumRedirection** parameter to set the **MaximumConnectionRedirectionCount** property of the **PSSessionOption** object to 1.</span></span>

<span data-ttu-id="c2ed2-266">Das- `Invoke-Command` Cmdlet führt einen `Get-Mailbox` Befehl auf einem Microsoft Exchange-Remote Server aus.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-266">The `Invoke-Command` cmdlet runs a `Get-Mailbox` command on a remote Microsoft Exchange Server.</span></span> <span data-ttu-id="c2ed2-267">Der **Zustellungs Direction** -Parameter stellt explizite Berechtigungen zum Umleiten der Verbindung zu einem alternativen Endpunkt bereit.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-267">The **AllowRedirection** parameter provides explicit permission to redirect the connection to an alternate endpoint.</span></span> <span data-ttu-id="c2ed2-268">Der **sessionoption** -Parameter verwendet das Sitzungs Objekt, das in der Variablen gespeichert ist `$max` .</span><span class="sxs-lookup"><span data-stu-id="c2ed2-268">The **SessionOption** parameter uses the session object stored in the `$max` variable.</span></span>

<span data-ttu-id="c2ed2-269">Wenn also der von **ConnectionUri** angegebene Remote Computer eine Umleitungs Meldung zurückgibt, leitet PowerShell die Verbindung um, aber wenn das neue Ziel eine andere Weiterleitungs Nachricht zurückgibt, wird der Umleitungs Zählerwert 1 überschritten, und es wird `Invoke-Command` ein Fehler ohne Abbruch zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-269">As a result, if the remote computer specified by **ConnectionURI** returns a redirection message, PowerShell redirects the connection, but if the new destination returns another redirection message, the redirection count value of 1 is exceeded, and `Invoke-Command` returns a non-terminating error.</span></span>

### <span data-ttu-id="c2ed2-270">Beispiel 17: Zugreifen auf eine Netzwerkfreigabe in einer Remote Sitzung</span><span class="sxs-lookup"><span data-stu-id="c2ed2-270">Example 17: Access a network share in a remote session</span></span>

<span data-ttu-id="c2ed2-271">Dieses Beispiel zeigt, wie Sie über eine Remote Sitzung auf eine Netzwerkfreigabe zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-271">This example shows how to access a network share from a remote session.</span></span> <span data-ttu-id="c2ed2-272">Zum veranschaulichen des Beispiels werden drei Computer verwendet.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-272">Three computers are used to demonstrate the example.</span></span> <span data-ttu-id="c2ed2-273">Server01 ist der lokale Computer, Server02 ist der Remote Computer, und Net03 enthält die Netzwerkfreigabe.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-273">Server01 is the local computer, Server02 is the remote computer, and Net03 contains the network share.</span></span> <span data-ttu-id="c2ed2-274">Server01 stellt eine Verbindung mit Server02 her, und Server02 führt dann einen zweiten Hop zu Net03 aus, um auf die Netzwerkfreigabe zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-274">Server01 connects to Server02, and then Server02 does a second hop to Net03 to access the network share.</span></span> <span data-ttu-id="c2ed2-275">Weitere Informationen zur Unterstützung von Hops durch PowerShell-Remoting zwischen Computern finden Sie unter Ausführen [des zweiten Hops in PowerShell-Remoting](/powershell/scripting/learn/remoting/ps-remoting-second-hop).</span><span class="sxs-lookup"><span data-stu-id="c2ed2-275">For more information about how PowerShell Remoting supports hops between computers, see [Making the second hop in PowerShell Remoting](/powershell/scripting/learn/remoting/ps-remoting-second-hop).</span></span>

<span data-ttu-id="c2ed2-276">In den Client Einstellungen auf dem lokalen Computer und in den Dienst Einstellungen auf dem Remote Computer ist die erforderliche Credential Security Support Provider (kredssp)-Delegierung aktiviert.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-276">The required Credential Security Support Provider (CredSSP) delegation is enabled in the client settings on the local computer, and in the service settings on the remote computer.</span></span> <span data-ttu-id="c2ed2-277">Um die Befehle in diesem Beispiel auszuführen, müssen Sie Mitglied der Gruppe " **Administratoren** " auf dem lokalen Computer und dem Remote Computer sein.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-277">To run the commands in this example, you must be a member of the **Administrators** group on the local computer and the remote computer.</span></span>

```powershell
Enable-WSManCredSSP -Role Client -DelegateComputer Server02
$s = New-PSSession Server02
Invoke-Command -Session $s -ScriptBlock {Enable-WSManCredSSP -Role Server -Force}
$parameters = @{
  Session = $s
  ScriptBlock = { Get-Item \\Net03\Scripts\LogFiles.ps1 }
  Authentication = "CredSSP"
  Credential = "Domain01\Admin01"
}
Invoke-Command @parameters
```

<span data-ttu-id="c2ed2-278">Mit dem- `Enable-WSManCredSSP` Cmdlet kann die "Server01"-Delegierung vom lokalen Computer auf den Server02-Remote Computer aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-278">The `Enable-WSManCredSSP` cmdlet enables CredSSP delegation from the Server01 local computer to the Server02 remote computer.</span></span> <span data-ttu-id="c2ed2-279">Der **Role** -Parameter gibt den **Client** an, um die Einstellung für den Client auf dem lokalen Computer zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-279">The **Role** parameter specifies **Client** to configure the CredSSP client setting on the local computer.</span></span>

<span data-ttu-id="c2ed2-280">`New-PSSession` erstellt ein **PSSession** -Objekt für Server02 und speichert das-Objekt in der `$s` Variablen.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-280">`New-PSSession` creates a **PSSession** object for Server02 and stores the object in the `$s` variable.</span></span>

<span data-ttu-id="c2ed2-281">Das `Invoke-Command` Cmdlet verwendet die- `$s` Variable, um eine Verbindung mit dem Remote Computer Server02 herzustellen.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-281">The `Invoke-Command` cmdlet uses the `$s` variable to connect to the remote computer, Server02.</span></span> <span data-ttu-id="c2ed2-282">Der **ScriptBlock** -Parameter wird `Enable-WSManCredSSP` auf dem Remote Computer ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-282">The **ScriptBlock** parameter runs `Enable-WSManCredSSP` on the remote computer.</span></span> <span data-ttu-id="c2ed2-283">Der **Role** -Parameter gibt den **Server** an, um die Einstellungen für den auf dem Remote Computer festgelegten Einstellungen für den ""</span><span class="sxs-lookup"><span data-stu-id="c2ed2-283">The **Role** parameter specifies **Server** to configure the CredSSP server setting on the remote computer.</span></span>

<span data-ttu-id="c2ed2-284">Die- `$parameters` Variable enthält die Parameterwerte zum Herstellen einer Verbindung mit der Netzwerkfreigabe.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-284">The `$parameters` variable contains the parameter values to connect to the network share.</span></span> <span data-ttu-id="c2ed2-285">Das- `Invoke-Command` Cmdlet führt einen `Get-Item` Befehl in der Sitzung in aus `$s` .</span><span class="sxs-lookup"><span data-stu-id="c2ed2-285">The `Invoke-Command` cmdlet runs a `Get-Item` command in the session in `$s`.</span></span> <span data-ttu-id="c2ed2-286">Mit diesem Befehl wird ein Skript aus der `\\Net03\Scripts` Netzwerkfreigabe abgerufen.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-286">This command gets a script from the `\\Net03\Scripts` network share.</span></span> <span data-ttu-id="c2ed2-287">Der Befehl verwendet den **Authentication** -Parameter mit dem Wert " **kredssp** " und dem **Credential** -Parameter mit dem Wert " **Domain01\Admin01** ".</span><span class="sxs-lookup"><span data-stu-id="c2ed2-287">The command uses the **Authentication** parameter with a value of **CredSSP** and the **Credential** parameter with a value of **Domain01\Admin01**.</span></span>

### <span data-ttu-id="c2ed2-288">Beispiel 18: Starten von Skripts auf vielen Remote Computern</span><span class="sxs-lookup"><span data-stu-id="c2ed2-288">Example 18: Start scripts on many remote computers</span></span>

<span data-ttu-id="c2ed2-289">In diesem Beispiel wird ein Skript auf mehr als 100 Computern ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-289">This example runs a script on more than a hundred computers.</span></span> <span data-ttu-id="c2ed2-290">Zur Minimierung der Auswirkungen auf dem lokalen Computer wird eine Verbindung mit jedem Computer hergestellt, das Skript gestartet und die Verbindung dann von jedem Computer getrennt.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-290">To minimize the impact on the local computer, it connects to each computer, starts the script, and then disconnects from each computer.</span></span>
<span data-ttu-id="c2ed2-291">Das Skript wird weiterhin in den getrennten Sitzungen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-291">The script continues to run in the disconnected sessions.</span></span>

```powershell
$parameters = @{
  ComputerName = (Get-Content -Path C:\Test\Servers.txt)
  InDisconnectedSession = $true
  FilePath = "\\Scripts\Public\ConfigInventory.ps1"
  SessionOption = @{OutputBufferingMode="Drop";IdleTimeout=43200000}
}
Invoke-Command @parameters
```

<span data-ttu-id="c2ed2-292">Der Befehl verwendet `Invoke-Command` , um das Skript auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-292">The command uses `Invoke-Command` to run the script.</span></span> <span data-ttu-id="c2ed2-293">Der Wert des **Computername** -Parameters ist ein `Get-Content` Befehl, der die Namen der Remote Computer aus einer Textdatei abruft.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-293">The value of the **ComputerName** parameter is a `Get-Content` command that gets the names of the remote computers from a text file.</span></span> <span data-ttu-id="c2ed2-294">Der **InDisconnectedSession** -Parameter trennt Sitzungen, sobald der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-294">The **InDisconnectedSession** parameter disconnects the sessions as soon as it starts the command.</span></span> <span data-ttu-id="c2ed2-295">Der Wert des **FilePath** -Parameters ist das Skript, das `Invoke-Command` auf jedem Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-295">The value of the **FilePath** parameter is the script that `Invoke-Command` runs on each computer.</span></span>

<span data-ttu-id="c2ed2-296">Der Wert von **sessionoption** ist eine Hash Tabelle.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-296">The value of **SessionOption** is a hash table.</span></span> <span data-ttu-id="c2ed2-297">Der Wert **outputbufferingmode** ist auf **Drop** festgelegt, und der **IdleTimeout** -Wert wird auf **43,2 Millionen** Millisekunden (12 Stunden) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-297">The **OutputBufferingMode** value is set to **Drop** and the **IdleTimeout** value is set to **43200000** milliseconds (12 hours).</span></span>

<span data-ttu-id="c2ed2-298">Verwenden Sie das-Cmdlet, um die Ergebnisse von Befehlen und Skripts, die in getrennten Sitzungen ausgeführt werden, zu erhalten `Receive-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="c2ed2-298">To get the results of commands and scripts that run in disconnected sessions, use the `Receive-PSSession` cmdlet.</span></span>

### <span data-ttu-id="c2ed2-299">Beispiel 19: Ausführen eines Befehls auf einem Remote Computer mithilfe von SSH</span><span class="sxs-lookup"><span data-stu-id="c2ed2-299">Example 19: Run a command on a remote computer using SSH</span></span>

<span data-ttu-id="c2ed2-300">In diesem Beispiel wird gezeigt, wie ein Befehl auf einem Remote Computer mithilfe von Secure Shell (SSH) ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-300">This example shows how to run a command on a remote computer using Secure Shell (SSH).</span></span> <span data-ttu-id="c2ed2-301">Wenn SSH auf dem Remote Computer für die Eingabe von Kenn Wörtern konfiguriert ist, erhalten Sie eine Kenn Wort Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-301">If SSH is configured on the remote computer to prompt for passwords, then you'll get a password prompt.</span></span>
<span data-ttu-id="c2ed2-302">Andernfalls müssen Sie die SSH-Schlüssel basierte Benutzerauthentifizierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-302">Otherwise, you'll have to use SSH key-based user authentication.</span></span>

```powershell
Invoke-Command -HostName UserA@LinuxServer01 -ScriptBlock { Get-MailBox * }
```

### <span data-ttu-id="c2ed2-303">Beispiel 20: Ausführen eines Befehls auf einem Remote Computer mithilfe von SSH und Angeben eines Benutzer Authentifizierungs Schlüssels</span><span class="sxs-lookup"><span data-stu-id="c2ed2-303">Example 20: Run a command on a remote computer using SSH and specify a user authentication key</span></span>

<span data-ttu-id="c2ed2-304">Dieses Beispiel zeigt, wie Sie einen Befehl auf einem Remote Computer mithilfe von SSH ausführen und eine Schlüsseldatei für die Benutzerauthentifizierung angeben.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-304">This example shows how to run a command on a remote computer using SSH and specifying a key file for user authentication.</span></span> <span data-ttu-id="c2ed2-305">Sie werden nicht zur Eingabe eines Kennworts aufgefordert, es sei denn, bei der Schlüssel Authentifizierung tritt ein Fehler auf, und der Remote Computer ist so konfiguriert, dass die</span><span class="sxs-lookup"><span data-stu-id="c2ed2-305">You won't be prompted for a password unless the key authentication fails and the remote computer is configured to allow basic password authentication.</span></span>

```powershell
Invoke-Command -HostName UserA@LinuxServer01 -ScriptBlock { Get-MailBox * } -KeyFilePath /UserA/UserAKey_rsa
```

### <span data-ttu-id="c2ed2-306">Beispiel 21: Ausführen einer Skriptdatei auf mehreren Remote Computern mithilfe von SSH als Auftrag</span><span class="sxs-lookup"><span data-stu-id="c2ed2-306">Example 21: Run a script file on multiple remote computers using SSH as a job</span></span>

<span data-ttu-id="c2ed2-307">In diesem Beispiel wird gezeigt, wie eine Skriptdatei auf mehreren Remote Computern mithilfe von SSH und dem **SshConnection** -Parametersatz ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-307">This example shows how to run a script file on multiple remote computers using SSH and the **SSHConnection** parameter set.</span></span> <span data-ttu-id="c2ed2-308">Der **SshConnection** -Parameter nimmt ein Array von Hash Tabellen an, die Verbindungsinformationen für jeden Computer enthalten.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-308">The **SSHConnection** parameter takes an array of hash tables that contain connection information for each computer.</span></span> <span data-ttu-id="c2ed2-309">Für dieses Beispiel ist es erforderlich, dass für die Ziel Remote Computer SSH konfiguriert ist, um die Schlüssel basierte Benutzerauthentifizierung zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-309">This example requires that the target remote computers have SSH configured to support key-based user authentication.</span></span>

```powershell
$sshConnections =
@{ HostName="WinServer1"; UserName="Domain\UserA"; KeyFilePath="C:\Users\UserA\id_rsa" },
@{ HostName="UserB@LinuxServer5"; KeyFilePath="/Users/UserB/id_rsa" }
$results = Invoke-Command -FilePath c:\Scripts\CollectEvents.ps1 -SSHConnection $sshConnections
```

## <span data-ttu-id="c2ed2-310">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c2ed2-310">PARAMETERS</span></span>

### <span data-ttu-id="c2ed2-311">-Zuweisung Richtung</span><span class="sxs-lookup"><span data-stu-id="c2ed2-311">-AllowRedirection</span></span>

<span data-ttu-id="c2ed2-312">Ermöglicht die Umleitung dieser Verbindung an einen alternativen URI (Uniform Resource Identifier).</span><span class="sxs-lookup"><span data-stu-id="c2ed2-312">Allows redirection of this connection to an alternate Uniform Resource Identifier (URI).</span></span>

<span data-ttu-id="c2ed2-313">Bei Verwendung des **ConnectionURI** -Parameters kann das Remoteziel eine Anweisung zum Umleiten an einen anderen URI zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-313">When you use the **ConnectionURI** parameter, the remote destination can return an instruction to redirect to a different URI.</span></span> <span data-ttu-id="c2ed2-314">Standardmäßig werden Verbindungen von PowerShell nicht umgeleitet, aber Sie können diesen Parameter verwenden, um die Umleitung der Verbindung zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-314">By default, PowerShell doesn't redirect connections, but you can use this parameter to allow it to redirect the connection.</span></span>

<span data-ttu-id="c2ed2-315">Sie können auch einschränken, wie oft die Verbindung umgeleitet wird, indem Sie den **MaximumConnectionRedirectionCount** -Optionswert der Sitzung ändern.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-315">You can also limit the number of times the connection is redirected by changing the **MaximumConnectionRedirectionCount** session option value.</span></span> <span data-ttu-id="c2ed2-316">Verwenden Sie den **maximumredirect** -Parameter des `New-PSSessionOption` Cmdlets, oder legen Sie die **maximumconnectionredirectioncount** -Eigenschaft der `$PSSessionOption` Preference-Variablen fest.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-316">Use the **MaximumRedirection** parameter of the `New-PSSessionOption` cmdlet or set the **MaximumConnectionRedirectionCount** property of the `$PSSessionOption` preference variable.</span></span> <span data-ttu-id="c2ed2-317">Der Standardwert ist 5.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-317">The default value is 5.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Uri, FilePathUri
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c2ed2-318">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="c2ed2-318">-ApplicationName</span></span>

<span data-ttu-id="c2ed2-319">Gibt das Anwendungsnamenssegment des Verbindungs-URI an.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-319">Specifies the application name segment of the connection URI.</span></span> <span data-ttu-id="c2ed2-320">Verwenden Sie diesen Parameter, um den Anwendungsnamen anzugeben, wenn Sie nicht den **ConnectionUri** -Parameter im Befehl verwenden.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-320">Use this parameter to specify the application name when you aren't using the **ConnectionURI** parameter in the command.</span></span>

<span data-ttu-id="c2ed2-321">Der Standardwert ist der Wert der Einstellungs `$PSSessionApplicationName` Variablen auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-321">The default value is the value of the `$PSSessionApplicationName` preference variable on the local computer.</span></span> <span data-ttu-id="c2ed2-322">Wenn diese Einstellungs Variable nicht definiert ist, lautet der Standardwert "wsman".</span><span class="sxs-lookup"><span data-stu-id="c2ed2-322">If this preference variable isn't defined, the default value is WSMAN.</span></span> <span data-ttu-id="c2ed2-323">Dieser Wert ist für die meisten Verwendungsarten geeignet.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-323">This value is appropriate for most uses.</span></span> <span data-ttu-id="c2ed2-324">Weitere Informationen finden Sie unter [about_Preference_Variables](./About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="c2ed2-324">For more information, see [about_Preference_Variables](./About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="c2ed2-325">Der WinRM-Dienst wählt mit dem Anwendungsnamen einen Listener für die Verbindungsanforderung aus.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-325">The WinRM service uses the application name to select a listener to service the connection request.</span></span>
<span data-ttu-id="c2ed2-326">Der Wert dieses Parameters sollte mit dem Wert der **URLPrefix** -Eigenschaft eines Listeners auf dem Remotecomputer übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-326">The value of this parameter should match the value of the **URLPrefix** property of a listener on the remote computer.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName, FilePathComputerName
Aliases:

Required: False
Position: Named
Default value: $PSSessionApplicationName if set on the local computer, otherwise WSMAN
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c2ed2-327">-Argumentlist</span><span class="sxs-lookup"><span data-stu-id="c2ed2-327">-ArgumentList</span></span>

<span data-ttu-id="c2ed2-328">Stellt die Werte von lokalen Variablen im Befehl bereit.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-328">Supplies the values of local variables in the command.</span></span> <span data-ttu-id="c2ed2-329">Die Variablen im Befehl werden durch diese Werte ersetzt, bevor der Befehl auf dem Remotecomputer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-329">The variables in the command are replaced by these values before the command is run on the remote computer.</span></span> <span data-ttu-id="c2ed2-330">Geben Sie die Werte in eine durch Kommas getrennte Liste ein.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-330">Enter the values in a comma-separated list.</span></span> <span data-ttu-id="c2ed2-331">Werte werden Variablen in der Reihenfolge zugeordnet, in der Sie aufgelistet sind.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-331">Values are associated with variables in the order that they're listed.</span></span> <span data-ttu-id="c2ed2-332">Der Alias für Argument **List** lautet "args".</span><span class="sxs-lookup"><span data-stu-id="c2ed2-332">The alias for **ArgumentList** is Args.</span></span>

<span data-ttu-id="c2ed2-333">Die Werte im Argument **List** -Parameter können tatsächliche Werte sein, z. b. 1024, oder es kann sich um Verweise auf lokale Variablen handeln, z `$max` . b..</span><span class="sxs-lookup"><span data-stu-id="c2ed2-333">The values in the **ArgumentList** parameter can be actual values, such as 1024, or they can be references to local variables, such as `$max`.</span></span>

<span data-ttu-id="c2ed2-334">Um lokale Variablen in einem Befehl zu verwenden, verwenden Sie das folgende Befehlsformat:</span><span class="sxs-lookup"><span data-stu-id="c2ed2-334">To use local variables in a command, use the following command format:</span></span>

<span data-ttu-id="c2ed2-335">`{param($<name1>[, $<name2>]...) <command-with-local-variables>} -ArgumentList <value>` - oder - `<local-variable>`</span><span class="sxs-lookup"><span data-stu-id="c2ed2-335">`{param($<name1>[, $<name2>]...) <command-with-local-variables>} -ArgumentList <value>` -or- `<local-variable>`</span></span>

<span data-ttu-id="c2ed2-336">Das Schlüsselwort " **param** " listet die lokalen Variablen auf, die im Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-336">The **param** keyword lists the local variables that are used in the command.</span></span> <span data-ttu-id="c2ed2-337">**Argumentlist** gibt die Werte der Variablen in der Reihenfolge an, in der Sie aufgelistet sind.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-337">**ArgumentList** supplies the values of the variables, in the order that they're listed.</span></span> <span data-ttu-id="c2ed2-338">Weitere Informationen zum Verhalten von **argumentlist** finden Sie unter [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span><span class="sxs-lookup"><span data-stu-id="c2ed2-338">For more information about the behavior of **ArgumentList** , see [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c2ed2-339">-AsJob</span><span class="sxs-lookup"><span data-stu-id="c2ed2-339">-AsJob</span></span>

<span data-ttu-id="c2ed2-340">Gibt an, dass dieses Cmdlet den Befehl als Hintergrund Auftrag auf einem Remote Computer ausführt.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-340">Indicates that this cmdlet runs the command as a background job on a remote computer.</span></span> <span data-ttu-id="c2ed2-341">Verwenden Sie diesen Parameter, um Befehle auszuführen, deren Ausführung viel Zeit in Anspruch nimmt.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-341">Use this parameter to run commands that take an extensive time to finish.</span></span>

<span data-ttu-id="c2ed2-342">Wenn Sie den **AsJob** -Parameter verwenden, gibt der Befehl ein Objekt zurück, das den Auftrag darstellt, und zeigt dann die Eingabeaufforderung an.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-342">When you use the **AsJob** parameter, the command returns an object that represents the job, and then displays the command prompt.</span></span> <span data-ttu-id="c2ed2-343">Sie können die Sitzung weiterhin verwenden, während der Auftrag abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-343">You can continue to work in the session while the job finishes.</span></span> <span data-ttu-id="c2ed2-344">Verwenden Sie die-Cmdlets, um den Auftrag zu verwalten `*-Job` .</span><span class="sxs-lookup"><span data-stu-id="c2ed2-344">To manage the job, use the `*-Job` cmdlets.</span></span> <span data-ttu-id="c2ed2-345">Um die Auftragsergebnisse abzurufen, verwenden Sie das Cmdlet `Receive-Job`.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-345">To get the job results, use the `Receive-Job` cmdlet.</span></span>

<span data-ttu-id="c2ed2-346">Der **AsJob** -Parameter ähnelt der Verwendung des `Invoke-Command` Cmdlets zum `Start-Job` Remote Ausführen eines Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-346">The **AsJob** parameter resembles using the `Invoke-Command` cmdlet to run a `Start-Job` cmdlet remotely.</span></span> <span data-ttu-id="c2ed2-347">Bei **AsJob** wird der Auftrag jedoch auf dem lokalen Computer erstellt, auch wenn der Auftrag auf einem Remote Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-347">However, with **AsJob** , the job is created on the local computer, even though the job runs on a remote computer.</span></span> <span data-ttu-id="c2ed2-348">Die Ergebnisse des Remote Auftrags werden automatisch an den lokalen Computer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-348">The results of the remote job are automatically returned to the local computer.</span></span>

<span data-ttu-id="c2ed2-349">Weitere Informationen zu PowerShell-Hintergrund Aufträgen finden Sie unter [about_Jobs](About/about_Jobs.md) und [about_Remote_Jobs](About/about_Remote_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="c2ed2-349">For more information about PowerShell background jobs, see [about_Jobs](About/about_Jobs.md) and [about_Remote_Jobs](About/about_Remote_Jobs.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: FilePathRunspace, Session, ComputerName, FilePathComputerName, Uri, FilePathUri, VMId, VMName, FilePathVMId, FilePathVMName, SSHHost, ContainerId, FilePathContainerId, SSHHostHashParam, FilePathSSHHost, FilePathSSHHostHash
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c2ed2-350">-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="c2ed2-350">-Authentication</span></span>

<span data-ttu-id="c2ed2-351">Gibt den Mechanismus an, der zum Authentifizieren der Anmelde Informationen des Benutzers verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-351">Specifies the mechanism that's used to authenticate the user's credentials.</span></span> <span data-ttu-id="c2ed2-352">Die kredssp-Authentifizierung ist nur in Windows Vista, Windows Server 2008 und höheren Versionen des Windows-Betriebssystems verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-352">CredSSP authentication is available only in Windows Vista, Windows Server 2008, and later versions of the Windows operating system.</span></span>

<span data-ttu-id="c2ed2-353">Die zulässigen Werte für diesen Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="c2ed2-353">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="c2ed2-354">Standard</span><span class="sxs-lookup"><span data-stu-id="c2ed2-354">Default</span></span>
- <span data-ttu-id="c2ed2-355">Basic</span><span class="sxs-lookup"><span data-stu-id="c2ed2-355">Basic</span></span>
- <span data-ttu-id="c2ed2-356">CredSSP</span><span class="sxs-lookup"><span data-stu-id="c2ed2-356">Credssp</span></span>
- <span data-ttu-id="c2ed2-357">Digest</span><span class="sxs-lookup"><span data-stu-id="c2ed2-357">Digest</span></span>
- <span data-ttu-id="c2ed2-358">Kerberos</span><span class="sxs-lookup"><span data-stu-id="c2ed2-358">Kerberos</span></span>
- <span data-ttu-id="c2ed2-359">Aushandeln</span><span class="sxs-lookup"><span data-stu-id="c2ed2-359">Negotiate</span></span>
- <span data-ttu-id="c2ed2-360">NegotiateWithImplicitCredential</span><span class="sxs-lookup"><span data-stu-id="c2ed2-360">NegotiateWithImplicitCredential</span></span>

<span data-ttu-id="c2ed2-361">Der Standardwert ist Default.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-361">The default value is Default.</span></span>

<span data-ttu-id="c2ed2-362">Weitere Informationen zu den Werten dieses Parameters finden Sie unter [authenticationmechanism-Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span><span class="sxs-lookup"><span data-stu-id="c2ed2-362">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!CAUTION]
> <span data-ttu-id="c2ed2-363">Die CredSSP (Credential Security Support Provider)-Authentifizierung, bei der die Anmeldeinformationen des Benutzers zur Authentifizierung an einen Remotecomputer übergeben werden, ist für Befehle konzipiert, die die Authentifizierung auf mehr als einer Ressource erfordern, z. B. beim Zugriff auf eine Remotenetzwerkfreigabe.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-363">Credential Security Support Provider (CredSSP) authentication, in which the user's credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="c2ed2-364">Dieser Mechanismus erhöht das Sicherheitsrisiko des Remotevorgangs.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-364">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="c2ed2-365">Wenn die Sicherheit des Remotecomputers gefährdet ist, können die an ihn übergebenen Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-365">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span> <span data-ttu-id="c2ed2-366">Weitere Informationen finden Sie [unter Credential Security Support Provider](/windows/win32/secauthn/credential-security-support-provider).</span><span class="sxs-lookup"><span data-stu-id="c2ed2-366">For more information, see [Credential Security Support Provider](/windows/win32/secauthn/credential-security-support-provider).</span></span>

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: ComputerName, FilePathComputerName, Uri, FilePathUri
Aliases:
Accepted values: Basic, Default, Credssp, Digest, Kerberos, Negotiate, NegotiateWithImplicitCredential

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c2ed2-367">-Certifiupethumschlag-Print</span><span class="sxs-lookup"><span data-stu-id="c2ed2-367">-CertificateThumbprint</span></span>

<span data-ttu-id="c2ed2-368">Gibt das digitale Zertifikat für öffentliche Schlüssel (X.509) eines Benutzerkontos mit der Berechtigung zum Herstellen einer Verbindung mit der getrennten Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-368">Specifies the digital public key certificate (X509) of a user account that has permission to connect to the disconnected session.</span></span> <span data-ttu-id="c2ed2-369">Geben Sie den Zertifikatfingerabdruck des Zertifikats ein.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-369">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="c2ed2-370">Zertifikate werden bei der clientzertifikatbasierten Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-370">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="c2ed2-371">Sie können nur lokalen Benutzerkonten zugeordnet werden und funktionieren nicht mit Domänen Konten.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-371">They can be mapped only to local user accounts and they don't work with domain accounts.</span></span>

<span data-ttu-id="c2ed2-372">Um einen Zertifikat Fingerabdruck abzurufen, verwenden Sie einen- `Get-Item` `Get-ChildItem` Befehl oder den-Befehl im PowerShell-Laufwerk "CERT:".</span><span class="sxs-lookup"><span data-stu-id="c2ed2-372">To get a certificate thumbprint, use a `Get-Item` or `Get-ChildItem` command in the PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="c2ed2-373">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="c2ed2-373">-ComputerName</span></span>

<span data-ttu-id="c2ed2-374">Gibt die Computer an, auf denen der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-374">Specifies the computers on which the command runs.</span></span> <span data-ttu-id="c2ed2-375">Die Standardeinstellung ist der lokale Computer.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-375">The default is the local computer.</span></span>

<span data-ttu-id="c2ed2-376">Wenn Sie den **Computername** -Parameter verwenden, erstellt PowerShell eine temporäre Verbindung, die nur zum Ausführen des angegebenen Befehls verwendet und dann geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-376">When you use the **ComputerName** parameter, PowerShell creates a temporary connection that's used only to run the specified command and is then closed.</span></span> <span data-ttu-id="c2ed2-377">Wenn Sie eine permanente Verbindung benötigen, verwenden Sie den **Session** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-377">If you need a persistent connection, use the **Session** parameter.</span></span>

<span data-ttu-id="c2ed2-378">Geben Sie den NetBIOS-Namen, die IP-Adresse oder den vollqualifizierten Domänennamen eines Computers oder mehrerer Computer in einer durch Trennzeichen getrennten Liste ein.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-378">Type the NETBIOS name, IP address, or fully qualified domain name of one or more computers in a comma-separated list.</span></span> <span data-ttu-id="c2ed2-379">Um den lokalen Computer anzugeben, geben Sie den Computernamen, "localhost" oder einen Punkt ( `.` ) ein.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-379">To specify the local computer, type the computer name, localhost, or a dot (`.`).</span></span>

<span data-ttu-id="c2ed2-380">Um eine IP-Adresse im Wert von **Computername** zu verwenden, muss der Befehl den **Credential** -Parameter enthalten.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-380">To use an IP address in the value of **ComputerName** , the command must include the **Credential** parameter.</span></span> <span data-ttu-id="c2ed2-381">Der Computer muss für den HTTPS-Transport konfiguriert sein, oder die IP-Adresse des Remote Computers muss in der **WinRM-** Liste des lokalen Computers enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-381">The computer must be configured for the HTTPS transport or the IP address of the remote computer must be included in the local computer's WinRM **TrustedHosts** list.</span></span> <span data-ttu-id="c2ed2-382">Anweisungen zum Hinzufügen eines Computer namens zur Liste " **Treuhänder Hosts** " finden Sie unter [Hinzufügen eines Computers zur Liste "vertrauenswürdiger Host](./about/about_remote_troubleshooting.md#how-to-add-a-computer-to-the-trusted-hosts-list)".</span><span class="sxs-lookup"><span data-stu-id="c2ed2-382">For instructions to add a computer name to the **TrustedHosts** list, see [How to Add a Computer to the Trusted Host List](./about/about_remote_troubleshooting.md#how-to-add-a-computer-to-the-trusted-hosts-list).</span></span>

<span data-ttu-id="c2ed2-383">Unter Windows Vista und höheren Versionen des Windows-Betriebssystems müssen Sie PowerShell mit der Option **als Administrator ausführen** ausführen, um den lokalen Computer in den Wert von **Computername** einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-383">On Windows Vista and later versions of the Windows operating system, to include the local computer in the value of **ComputerName** , you must run PowerShell using the **Run as administrator** option.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerName, FilePathComputerName
Aliases: Cn

Required: False
Position: 0
Default value: Local computer
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c2ed2-384">-ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="c2ed2-384">-ConfigurationName</span></span>

<span data-ttu-id="c2ed2-385">Gibt die Sitzungs Konfiguration an, die für die neue **PSSession** verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-385">Specifies the session configuration that is used for the new **PSSession**.</span></span>

<span data-ttu-id="c2ed2-386">Geben Sie einen Konfigurationsnamen oder den vollqualifizierten Ressourcen-URI für eine Sitzungskonfiguration ein.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-386">Enter a configuration name or the fully qualified resource URI for a session configuration.</span></span> <span data-ttu-id="c2ed2-387">Wenn Sie nur den Konfigurations Namen angeben, wird der folgende Schema-URI vorangestellt: `http://schemas.microsoft.com/PowerShell` .</span><span class="sxs-lookup"><span data-stu-id="c2ed2-387">If you specify only the configuration name, the following schema URI is prepended: `http://schemas.microsoft.com/PowerShell`.</span></span>

<span data-ttu-id="c2ed2-388">Bei Verwendung mit SSH gibt dieser Parameter das Subsystem an, das auf dem Ziel verwendet werden soll, wie in definiert `sshd_config` .</span><span class="sxs-lookup"><span data-stu-id="c2ed2-388">When used with SSH, this parameter specifies the subsystem to use on the target as defined in `sshd_config`.</span></span> <span data-ttu-id="c2ed2-389">Der Standardwert für SSH ist das `powershell` Subsystem.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-389">The default value for SSH is the `powershell` subsystem.</span></span>

<span data-ttu-id="c2ed2-390">Die Sitzungskonfiguration für eine Sitzung befindet sich auf dem Remotecomputer.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-390">The session configuration for a session is located on the remote computer.</span></span> <span data-ttu-id="c2ed2-391">Wenn die angegebene Sitzungs Konfiguration auf dem Remote Computer nicht vorhanden ist, schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-391">If the specified session configuration doesn't exist on the remote computer, the command fails.</span></span>

<span data-ttu-id="c2ed2-392">Der Standardwert ist der Wert der Einstellungs `$PSSessionConfigurationName` Variablen auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-392">The default value is the value of the `$PSSessionConfigurationName` preference variable on the local computer.</span></span> <span data-ttu-id="c2ed2-393">Wenn diese Einstellungs Variable nicht festgelegt ist, lautet der Standardwert **Microsoft. PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-393">If this preference variable isn't set, the default is **Microsoft.PowerShell**.</span></span> <span data-ttu-id="c2ed2-394">Weitere Informationen finden Sie unter [about_Preference_Variables](about/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="c2ed2-394">For more information, see [about_Preference_Variables](about/about_Preference_Variables.md).</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName, FilePathComputerName, Uri, FilePathUri, VMId, VMName, FilePathVMId, FilePathVMName, ContainerId, FilePathContainerId
Aliases:

Required: False
Position: Named
Default value: $PSSessionConfigurationName if set on the local computer, otherwise Microsoft.PowerShell
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c2ed2-395">-ConnectionUri</span><span class="sxs-lookup"><span data-stu-id="c2ed2-395">-ConnectionUri</span></span>

<span data-ttu-id="c2ed2-396">Gibt einen URI (Uniform Resource Identifier) an, der den Verbindungsendpunkt für die Sitzung definiert.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-396">Specifies a Uniform Resource Identifier (URI) that defines the connection endpoint of the session.</span></span>
<span data-ttu-id="c2ed2-397">Der URI muss vollqualifiziert sein.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-397">The URI must be fully qualified.</span></span>

<span data-ttu-id="c2ed2-398">Das Format dieser Zeichenfolge lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="c2ed2-398">The format of this string is as follows:</span></span>

`<Transport>://<ComputerName>:<Port>/<ApplicationName>`

<span data-ttu-id="c2ed2-399">Der Standardwert lautet:</span><span class="sxs-lookup"><span data-stu-id="c2ed2-399">The default value is as follows:</span></span>

`http://localhost:5985/WSMAN`

<span data-ttu-id="c2ed2-400">Wenn Sie keinen Verbindungs-URI angeben, können Sie die Parameter " **US** " und " **Port** " verwenden, um die Verbindungs-URI-Werte anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-400">If you don't specify a connection URI, you can use the **UseSSL** and **Port** parameters to specify the connection URI values.</span></span>

<span data-ttu-id="c2ed2-401">Gültige Werte für das **Transport** -Segment des URI sind „HTTP“ und „HTTPS“.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-401">Valid values for the **Transport** segment of the URI are HTTP and HTTPS.</span></span> <span data-ttu-id="c2ed2-402">Wenn Sie einen Verbindungs-URI mit einem Transport Segment angeben, aber keinen Port angeben, wird die Sitzung mit den Standardports erstellt: 80 für http und 443 für HTTPS.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-402">If you specify a connection URI with a Transport segment, but don't specify a port, the session is created with the standards ports: 80 for HTTP and 443 for HTTPS.</span></span> <span data-ttu-id="c2ed2-403">Wenn Sie die Standardports für PowerShell-Remoting verwenden möchten, geben Sie Port 5985 für http oder 5986 für HTTPS an.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-403">To use the default ports for PowerShell remoting, specify port 5985 for HTTP or 5986 for HTTPS.</span></span>

<span data-ttu-id="c2ed2-404">Wenn der Zielcomputer die Verbindung an einen anderen URI umleitet, verhindert PowerShell die Umleitung, es sei denn, Sie verwenden den Parameter " **Zuweisung** " im Befehl.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-404">If the destination computer redirects the connection to a different URI, PowerShell prevents the redirection unless you use the **AllowRedirection** parameter in the command.</span></span>

```yaml
Type: System.Uri[]
Parameter Sets: Uri, FilePathUri
Aliases: URI, CU

Required: False
Position: 0
Default value: http://localhost:5985/WSMAN
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c2ed2-405">-Containerid</span><span class="sxs-lookup"><span data-stu-id="c2ed2-405">-ContainerId</span></span>

<span data-ttu-id="c2ed2-406">Gibt ein Array von Container-IDs an.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-406">Specifies an array of container IDs.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ContainerId, FilePathContainerId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c2ed2-407">-Credential</span><span class="sxs-lookup"><span data-stu-id="c2ed2-407">-Credential</span></span>

<span data-ttu-id="c2ed2-408">Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-408">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="c2ed2-409">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-409">The default is the current user.</span></span>

<span data-ttu-id="c2ed2-410">Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01** , oder geben Sie ein **PSCredential** -Objekt ein, das vom `Get-Credential` Cmdlet generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-410">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="c2ed2-411">Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe des Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-411">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="c2ed2-412">Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-412">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="c2ed2-413">Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="c2ed2-413">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerName, FilePathComputerName, Uri, FilePathUri, VMId, VMName, FilePathVMId, FilePathVMName
Aliases:

Required: True (VMId, VMName, FilePathVMId, FilePathVMName), False (ComputerName, FilePathComputerName, Uri, FilePathUri)
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c2ed2-414">-Enablenetworkaccess</span><span class="sxs-lookup"><span data-stu-id="c2ed2-414">-EnableNetworkAccess</span></span>

<span data-ttu-id="c2ed2-415">Gibt an, dass mit diesem Cmdlet Loopback Sitzungen ein interaktives Sicherheits Token hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-415">Indicates that this cmdlet adds an interactive security token to loopback sessions.</span></span> <span data-ttu-id="c2ed2-416">Mit dem interaktiven Token können Sie die Befehle in der Loopbacksitzung ausführen, um Daten von anderen Computern abzurufen.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-416">The interactive token lets you run commands in the loopback session that get data from other computers.</span></span> <span data-ttu-id="c2ed2-417">Beispielsweise können Sie einen Befehl in der Sitzung ausführen, mit dem XML-Dateien von einem Remotecomputer auf den lokalen Computer kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-417">For example, you can run a command in the session that copies XML files from a remote computer to the local computer.</span></span>

<span data-ttu-id="c2ed2-418">Eine Loopback Sitzung ist eine **PSSession** , die auf demselben computerbasiert und endet.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-418">A loopback session is a **PSSession** that originates and ends on the same computer.</span></span> <span data-ttu-id="c2ed2-419">Um eine Loopback Sitzung zu erstellen, lassen Sie den **Computername** -Parameter aus, oder legen Sie seinen Wert auf "dot ( `.` )", "localhost" oder den Namen des lokalen Computers fest.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-419">To create a loopback session, omit the **ComputerName** parameter or set its value to dot (`.`), localhost, or the name of the local computer.</span></span>

<span data-ttu-id="c2ed2-420">Standardmäßig werden Loopback Sitzungen mit einem Netzwerk Token erstellt, das möglicherweise nicht über ausreichende Berechtigungen zum Authentifizieren bei Remote Computern verfügt.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-420">By default, loopback sessions are created using a network token, which might not provide sufficient permission to authenticate to remote computers.</span></span>

<span data-ttu-id="c2ed2-421">Der **EnableNetworkAccess** -Parameter ist nur bei Loopbacksitzungen wirksam.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-421">The **EnableNetworkAccess** parameter is effective only in loopback sessions.</span></span> <span data-ttu-id="c2ed2-422">Wenn Sie **enablenetworkaccess** verwenden, wenn Sie eine Sitzung auf einem Remote Computer erstellen, ist der Befehl erfolgreich, aber der-Parameter wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-422">If you use **EnableNetworkAccess** when you create a session on a remote computer, the command succeeds, but the parameter is ignored.</span></span>

<span data-ttu-id="c2ed2-423">Sie können den Remote Zugriff in einer Loopback Sitzung mithilfe des Werts " **kredssp** " des Parameters " **Authentication** " zulassen, der die Sitzungs Anmelde Informationen an andere Computer delegiert.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-423">You can allow remote access in a loopback session using the **CredSSP** value of the **Authentication** parameter, which delegates the session credentials to other computers.</span></span>

<span data-ttu-id="c2ed2-424">Um den Computer vor böswilligem Zugriff zu schützen, können getrennte Loopback Sitzungen mit interaktiven Tokens, die mithilfe von **enablenetworkaccess** erstellt wurden, nur von dem Computer wieder hergestellt werden, auf dem die Sitzung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-424">To protect the computer from malicious access, disconnected loopback sessions that have interactive tokens, which are those created using **EnableNetworkAccess** , can be reconnected only from the computer on which the session was created.</span></span> <span data-ttu-id="c2ed2-425">Die Verbindung von getrennten Sitzungen, die die CredSSP-Authentifizierung verwenden, kann von anderen Computern wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-425">Disconnected sessions that use CredSSP authentication can be reconnected from other computers.</span></span> <span data-ttu-id="c2ed2-426">Weitere Informationen finden Sie unter `Disconnect-PSSession`.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-426">For more information, see `Disconnect-PSSession`.</span></span>

<span data-ttu-id="c2ed2-427">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-427">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName, FilePathComputerName, Uri, FilePathUri
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c2ed2-428">-FilePath</span><span class="sxs-lookup"><span data-stu-id="c2ed2-428">-FilePath</span></span>

<span data-ttu-id="c2ed2-429">Gibt ein lokales Skript an, das dieses Cmdlet auf einem oder mehreren Remote Computern ausführt.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-429">Specifies a local script that this cmdlet runs on one or more remote computers.</span></span> <span data-ttu-id="c2ed2-430">Geben Sie den Pfad und den Dateinamen des Skripts ein, oder übergeben Sie einen Skript Pfad an `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="c2ed2-430">Enter the path and filename of the script, or pipe a script path to `Invoke-Command`.</span></span> <span data-ttu-id="c2ed2-431">Das Skript muss auf dem lokalen Computer oder in einem Verzeichnis vorhanden sein, auf das der lokale Computer zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-431">The script must exist on the local computer or in a directory that the local computer can access.</span></span> <span data-ttu-id="c2ed2-432">Verwenden Sie **argumentlist** , um die Werte der Parameter im Skript anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-432">Use **ArgumentList** to specify the values of parameters in the script.</span></span>

<span data-ttu-id="c2ed2-433">Wenn Sie diesen Parameter verwenden, konvertiert PowerShell den Inhalt der angegebenen Skriptdatei in einen Skriptblock, überträgt den Skriptblock an den Remote Computer und führt ihn auf dem Remote Computer aus.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-433">When you use this parameter, PowerShell converts the contents of the specified script file to a script block, transmits the script block to the remote computer, and runs it on the remote computer.</span></span>

```yaml
Type: System.String
Parameter Sets: FilePathRunspace, FilePathComputerName, FilePathUri, FilePathVMId, FilePathVMName, FilePathContainerId, FilePathSSHHost, FilePathSSHHostHash
Aliases: PSPath

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c2ed2-434">-Hidecomputername</span><span class="sxs-lookup"><span data-stu-id="c2ed2-434">-HideComputerName</span></span>

<span data-ttu-id="c2ed2-435">Gibt an, dass dieses Cmdlet den Computernamen der einzelnen Objekte aus der Ausgabe Anzeige auslässt.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-435">Indicates that this cmdlet omits the computer name of each object from the output display.</span></span> <span data-ttu-id="c2ed2-436">Standardmäßig wird der Name des Computers, der das Objekt generiert, in der Anzeige angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-436">By default, the name of the computer that generated the object appears in the display.</span></span>

<span data-ttu-id="c2ed2-437">Dieser Parameter betrifft nur die Ausgabeanzeige.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-437">This parameter affects only the output display.</span></span> <span data-ttu-id="c2ed2-438">Das Objekt wird nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-438">It doesn't change the object.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: FilePathRunspace, Session, ComputerName, FilePathComputerName, Uri, FilePathUri, VMId, VMName, FilePathVMId, FilePathVMName, SSHHost, ContainerId, FilePathContainerId, SSHHostHashParam, FilePathSSHHost, FilePathSSHHostHash
Aliases: HCN

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c2ed2-439">-HostName</span><span class="sxs-lookup"><span data-stu-id="c2ed2-439">-HostName</span></span>

<span data-ttu-id="c2ed2-440">Gibt ein Array von Computernamen für eine Secure Shell (SSH)-basierte Verbindung an.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-440">Specifies an array of computer names for a Secure Shell (SSH) based connection.</span></span> <span data-ttu-id="c2ed2-441">Dies ähnelt dem **Computername** -Parameter, mit dem Unterschied, dass die Verbindung mit dem Remote Computer anstelle von Windows WinRM über SSH hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-441">This is similar to the **ComputerName** parameter except that the connection to the remote computer is made using SSH rather than Windows WinRM.</span></span>

<span data-ttu-id="c2ed2-442">Dieser Parameter wurde in PowerShell 6,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-442">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.String[]
Parameter Sets: SSHHost, FilePathSSHHost
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c2ed2-443">-Indisconnectedsession</span><span class="sxs-lookup"><span data-stu-id="c2ed2-443">-InDisconnectedSession</span></span>

<span data-ttu-id="c2ed2-444">Gibt an, dass dieses Cmdlet einen Befehl oder ein Skript in einer getrennten Sitzung ausführt.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-444">Indicates that this cmdlet runs a command or script in a disconnected session.</span></span>

<span data-ttu-id="c2ed2-445">Wenn Sie den **indisconnectedsession** -Parameter verwenden, wird `Invoke-Command` auf jedem Remote Computer eine persistente Sitzung erstellt, der durch den **ScriptBlock** -Parameter oder den **FilePath** -Parameter angegebene Befehl gestartet und die Verbindung mit der Sitzung getrennt.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-445">When you use the **InDisconnectedSession** parameter, `Invoke-Command` creates a persistent session on each remote computer, starts the command specified by the **ScriptBlock** or **FilePath** parameter, and then disconnects from the session.</span></span> <span data-ttu-id="c2ed2-446">Die Befehle werden weiterhin in den getrennten Sitzungen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-446">The commands continue to run in the disconnected sessions.</span></span> <span data-ttu-id="c2ed2-447">Mit **indisconnectedsession** können Sie Befehle ausführen, ohne eine Verbindung mit den Remote Sitzungen aufrechtzuerhalten.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-447">**InDisconnectedSession** enables you to run commands without maintaining a connection to the remote sessions.</span></span> <span data-ttu-id="c2ed2-448">Und da die Sitzung getrennt wird, bevor Ergebnisse zurückgegeben werden, stellt " **indisconnectedsession** " sicher, dass alle Befehls Ergebnisse an die erneut verbundene Sitzung zurückgegeben werden, statt zwischen Sitzungen aufgeteilt zu werden.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-448">And, because the session is disconnected before any results are returned, **InDisconnectedSession** makes sure that all command results are returned to the reconnected session, instead of being split between sessions.</span></span>

<span data-ttu-id="c2ed2-449">Sie können " **indisconnectedsession** " nicht mit dem **Sitzungs** Parameter oder dem **AsJob** -Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-449">You can't use **InDisconnectedSession** with the **Session** parameter or the **AsJob** parameter.</span></span>

<span data-ttu-id="c2ed2-450">Befehle, die **indisconnectedsession** verwenden, geben ein **PSSession** -Objekt zurück, das die getrennte Sitzung darstellt.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-450">Commands that use **InDisconnectedSession** return a **PSSession** object that represents the disconnected session.</span></span> <span data-ttu-id="c2ed2-451">Die Befehlsausgabe wird nicht zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-451">They don't return the command output.</span></span> <span data-ttu-id="c2ed2-452">Verwenden Sie zum Herstellen einer Verbindung mit der getrennten Sitzung die `Connect-PSSession` `Receive-PSSession` Cmdlets oder.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-452">To connect to the disconnected session, use the `Connect-PSSession` or `Receive-PSSession` cmdlets.</span></span> <span data-ttu-id="c2ed2-453">Verwenden Sie das-Cmdlet, um die Ergebnisse von Befehlen zu erhalten, die in der Sitzung ausgeführt wurden `Receive-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="c2ed2-453">To get the results of commands that ran in the session, use the `Receive-PSSession` cmdlet.</span></span> <span data-ttu-id="c2ed2-454">Um Befehle auszuführen, die eine Ausgabe in einer getrennten Sitzung generieren, legen Sie den Wert der **outputbufferingmode** -Sitzungs Option auf **Drop** fest.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-454">To run commands that generate output in a disconnected session, set the value of the **OutputBufferingMode** session option to **Drop**.</span></span> <span data-ttu-id="c2ed2-455">Wenn Sie eine Verbindung mit der getrennten Sitzung herstellen möchten, legen Sie das Leerlauf Timeout in der Sitzung fest, damit Sie genügend Zeit zum Herstellen einer Verbindung haben, bevor Sie die Sitzung löschen.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-455">If you intend to connect to the disconnected session, set the idle time-out in the session so that it provides sufficient time for you to connect before deleting the session.</span></span>

<span data-ttu-id="c2ed2-456">Sie können den Ausgabepuffer Modus und das Leerlauf Timeout im **sessionoption** -Parameter oder in der `$PSSessionOption` Preference-Variablen festlegen.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-456">You can set the output buffering mode and idle time-out in the **SessionOption** parameter or in the `$PSSessionOption` preference variable.</span></span> <span data-ttu-id="c2ed2-457">Weitere Informationen zu Sitzungs Optionen finden Sie unter `New-PSSessionOption` und [about_Preference_Variables](./about/about_preference_variables.md).</span><span class="sxs-lookup"><span data-stu-id="c2ed2-457">For more information about session options, see `New-PSSessionOption` and [about_Preference_Variables](./about/about_preference_variables.md).</span></span>

<span data-ttu-id="c2ed2-458">Weitere Informationen zum Feature „Getrennte Sitzungen“ finden Sie unter [about_Remote_Disconnected_Sessions](about/about_Remote_Disconnected_Sessions.md).</span><span class="sxs-lookup"><span data-stu-id="c2ed2-458">For more information about the Disconnected Sessions feature, see [about_Remote_Disconnected_Sessions](about/about_Remote_Disconnected_Sessions.md).</span></span>

<span data-ttu-id="c2ed2-459">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-459">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName, FilePathComputerName, Uri, FilePathUri
Aliases: Disconnected

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c2ed2-460">-InputObject</span><span class="sxs-lookup"><span data-stu-id="c2ed2-460">-InputObject</span></span>

<span data-ttu-id="c2ed2-461">Gibt die Eingabe für den Befehl an.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-461">Specifies input to the command.</span></span> <span data-ttu-id="c2ed2-462">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, durch den die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-462">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span>

<span data-ttu-id="c2ed2-463">Wenn Sie den **Inputobject** -Parameter verwenden, verwenden `$Input` Sie die automatische Variable im Wert des **ScriptBlock** -Parameters, um die Eingabe Objekte darzustellen.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-463">When using the **InputObject** parameter, use the `$Input` automatic variable in the value of the **ScriptBlock** parameter to represent the input objects.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="c2ed2-464">-Jobname</span><span class="sxs-lookup"><span data-stu-id="c2ed2-464">-JobName</span></span>

<span data-ttu-id="c2ed2-465">Gibt einen Anzeigenamen für den Hintergrundauftrag an.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-465">Specifies a friendly name for the background job.</span></span> <span data-ttu-id="c2ed2-466">Standardmäßig werden Aufträge benannt `Job<n>` , wobei `<n>` eine Ordinalzahl ist.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-466">By default, jobs are named `Job<n>`, where `<n>` is an ordinal number.</span></span>

<span data-ttu-id="c2ed2-467">Wenn Sie den **Jobname** -Parameter in einem Befehl verwenden, wird der Befehl als Auftrag ausgeführt, und es wird `Invoke-Command` ein Auftrags Objekt zurückgegeben, auch wenn Sie **AsJob** nicht in den Befehl einschließen.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-467">If you use the **JobName** parameter in a command, the command is run as a job, and `Invoke-Command` returns a job object, even if you don't include **AsJob** in the command.</span></span>

<span data-ttu-id="c2ed2-468">Weitere Informationen zu PowerShell-Hintergrund Aufträgen finden Sie unter [about_Jobs](./About/about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="c2ed2-468">For more information about PowerShell background jobs, see [about_Jobs](./About/about_Jobs.md).</span></span>

```yaml
Type: System.String
Parameter Sets: FilePathRunspace, Session, ComputerName, FilePathComputerName, Uri, FilePathUri, SSHHost, ContainerId, FilePathContainerId, SSHHostHashParam
Aliases:

Required: False
Position: Named
Default value: Job<n>
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c2ed2-469">-KeyFilePath</span><span class="sxs-lookup"><span data-stu-id="c2ed2-469">-KeyFilePath</span></span>

<span data-ttu-id="c2ed2-470">Gibt einen Schlüssel Dateipfad an, der von Secure Shell (SSH) zum Authentifizieren eines Benutzers auf einem Remote Computer verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-470">Specifies a key file path used by Secure Shell (SSH) to authenticate a user on a remote computer.</span></span>

<span data-ttu-id="c2ed2-471">SSH ermöglicht die Ausführung der Benutzerauthentifizierung über private und öffentliche Schlüssel als Alternative zur grundlegenden Kenn Wort Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-471">SSH allows user authentication to be performed via private and public keys as an alternative to basic password authentication.</span></span> <span data-ttu-id="c2ed2-472">Wenn der Remote Computer für die Schlüssel Authentifizierung konfiguriert ist, kann dieser Parameter verwendet werden, um den Schlüssel zur Identifizierung des Benutzers bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-472">If the remote computer is configured for key authentication, then this parameter can be used to provide the key that identifies the user.</span></span>

<span data-ttu-id="c2ed2-473">Dieser Parameter wurde in PowerShell 6,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-473">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.String
Parameter Sets: SSHHost, FilePathSSHHost
Aliases: IdentityFilePath

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c2ed2-474">-Nonewscope</span><span class="sxs-lookup"><span data-stu-id="c2ed2-474">-NoNewScope</span></span>

<span data-ttu-id="c2ed2-475">Gibt an, dass dieses Cmdlet den angegebenen Befehl im aktuellen Bereich ausführt.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-475">Indicates that this cmdlet runs the specified command in the current scope.</span></span> <span data-ttu-id="c2ed2-476">Standardmäßig `Invoke-Command` führt Befehle in Ihrem eigenen Bereich aus.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-476">By default, `Invoke-Command` runs commands in their own scope.</span></span>

<span data-ttu-id="c2ed2-477">Dieser Parameter ist nur in Befehlen gültig, die in der aktuellen Sitzung ausgeführt werden, d. h. in Befehlen, bei denen beide Parameter, **ComputerName** und **Session** , weglassen wurden.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-477">This parameter is valid only in commands that are run in the current session, that is, commands that omit both the **ComputerName** and **Session** parameters.</span></span>

<span data-ttu-id="c2ed2-478">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-478">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: InProcess
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c2ed2-479">-Port</span><span class="sxs-lookup"><span data-stu-id="c2ed2-479">-Port</span></span>

<span data-ttu-id="c2ed2-480">Gibt den Netzwerkport auf dem Remote Computer an, der für diesen Befehl verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-480">Specifies the network port on the remote computer that is used for this command.</span></span> <span data-ttu-id="c2ed2-481">Zum Herstellen einer Verbindung mit einem Remotecomputer muss der Remotecomputer den für die Verbindung verwendeten Port abhören.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-481">To connect to a remote computer, the remote computer must be listening on the port that the connection uses.</span></span> <span data-ttu-id="c2ed2-482">Die Standardports sind 5985 (WinRM-Port für http) und 5986 (WinRM-Port für HTTPS).</span><span class="sxs-lookup"><span data-stu-id="c2ed2-482">The default ports are 5985 (WinRM port for HTTP) and 5986 (WinRM port for HTTPS).</span></span>

<span data-ttu-id="c2ed2-483">Konfigurieren Sie vor der Verwendung eines alternativen Ports den WinRM-Listener auf dem Remotecomputer, um diesen Port abzuhören.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-483">Before using an alternate port, configure the WinRM listener on the remote computer to listen at that port.</span></span> <span data-ttu-id="c2ed2-484">Um den Listener zu konfigurieren, geben Sie die folgenden beiden Befehle an der PowerShell-Eingabeaufforderung ein:</span><span class="sxs-lookup"><span data-stu-id="c2ed2-484">To configure the listener, type the following two commands at the PowerShell prompt:</span></span>

`Remove-Item -Path WSMan:\Localhost\listener\listener* -Recurse`

`New-Item -Path WSMan:\Localhost\listener -Transport http -Address * -Port \<port-number\>`

<span data-ttu-id="c2ed2-485">Verwenden Sie den **Port** -Parameter nur, wenn dies erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-485">Don't use the **Port** parameter unless you must.</span></span> <span data-ttu-id="c2ed2-486">Der im Befehl festgelegte Port gilt für alle Computer oder Sitzungen, für die der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-486">The port that is set in the command applies to all computers or sessions on which the command runs.</span></span> <span data-ttu-id="c2ed2-487">Eine alternative Porteinstellung kann verhindern, dass der Befehl auf allen Computern ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-487">An alternate port setting might prevent the command from running on all computers.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ComputerName, FilePathComputerName, SSHHost
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c2ed2-488">-Remotedebug</span><span class="sxs-lookup"><span data-stu-id="c2ed2-488">-RemoteDebug</span></span>

<span data-ttu-id="c2ed2-489">Wird verwendet, um den aufgerufenen Befehl im Debugmodus in der PowerShell-Remote Sitzung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-489">Used to run the invoked command in debug mode in the remote PowerShell session.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: FilePathRunspace, Session, ComputerName, FilePathComputerName, Uri, FilePathUri, VMId, VMName, FilePathVMId, FilePathVMName, SSHHost, ContainerId, FilePathContainerId, SSHHostHashParam, FilePathSSHHost, FilePathSSHHostHash
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c2ed2-490">-Runasadministrator</span><span class="sxs-lookup"><span data-stu-id="c2ed2-490">-RunAsAdministrator</span></span>

<span data-ttu-id="c2ed2-491">Gibt an, dass dieses Cmdlet einen Befehl als Administrator aufruft.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-491">Indicates that this cmdlet invokes a command as an Administrator.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ContainerId, FilePathContainerId
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c2ed2-492">-ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="c2ed2-492">-ScriptBlock</span></span>

<span data-ttu-id="c2ed2-493">Gibt die auszuführenden Befehle an.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-493">Specifies the commands to run.</span></span> <span data-ttu-id="c2ed2-494">Schließen Sie die Befehle in geschweiften Klammern `{ }` ein, um einen Skriptblock zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-494">Enclose the commands in curly braces `{ }` to create a script block.</span></span>
<span data-ttu-id="c2ed2-495">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-495">This parameter is required.</span></span>

<span data-ttu-id="c2ed2-496">Standardmäßig werden alle Variablen im Befehl auf dem Remotecomputer ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-496">By default, any variables in the command are evaluated on the remote computer.</span></span> <span data-ttu-id="c2ed2-497">Um lokale Variablen in den Befehl einzuschließen, verwenden Sie **argumentlist**.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-497">To include local variables in the command, use **ArgumentList**.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: InProcess, Session, ComputerName, Uri, VMId, VMName, SSHHost, ContainerId, SSHHostHashParam
Aliases: Command

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c2ed2-498">-Sitzung</span><span class="sxs-lookup"><span data-stu-id="c2ed2-498">-Session</span></span>

<span data-ttu-id="c2ed2-499">Gibt ein Array von Sitzungen an, in denen dieses Cmdlet den Befehl ausführt.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-499">Specifies an array of sessions in which this cmdlet runs the command.</span></span> <span data-ttu-id="c2ed2-500">Geben Sie eine Variable ein, die **PSSession** -Objekte enthält, oder einen Befehl, der die **PSSession** -Objekte erstellt oder abruft, z `New-PSSession` . b. den `Get-PSSession` Befehl oder.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-500">Enter a variable that contains **PSSession** objects or a command that creates or gets the **PSSession** objects, such as a `New-PSSession` or `Get-PSSession` command.</span></span>

<span data-ttu-id="c2ed2-501">Wenn Sie eine **PSSession** erstellen, stellt PowerShell eine permanente Verbindung mit dem Remote Computer her.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-501">When you create a **PSSession** , PowerShell establishes a persistent connection to the remote computer.</span></span> <span data-ttu-id="c2ed2-502">Verwenden Sie eine **PSSession** , um eine Reihe verwandter Befehle auszuführen, die Daten gemeinsam nutzen.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-502">Use a **PSSession** to run a series of related commands that share data.</span></span> <span data-ttu-id="c2ed2-503">Verwenden Sie den **Computername** -Parameter, um einen einzelnen Befehl oder eine Reihe von nicht verknüpften Befehlen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-503">To run a single command or a series of unrelated commands, use the **ComputerName** parameter.</span></span> <span data-ttu-id="c2ed2-504">Weitere Informationen finden Sie unter [about_PSSessions](./About/about_PSSessions.md).</span><span class="sxs-lookup"><span data-stu-id="c2ed2-504">For more information, see [about_PSSessions](./About/about_PSSessions.md).</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession[]
Parameter Sets: FilePathRunspace, Session
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c2ed2-505">-Sessionname</span><span class="sxs-lookup"><span data-stu-id="c2ed2-505">-SessionName</span></span>

<span data-ttu-id="c2ed2-506">Gibt einen Anzeigenamen für eine getrennte Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-506">Specifies a friendly name for a disconnected session.</span></span> <span data-ttu-id="c2ed2-507">Sie können den Namen verwenden, um in nachfolgenden Befehlen auf die Sitzung zu verweisen, z. b. einen- `Get-PSSession` Befehl.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-507">You can use the name to refer to the session in subsequent commands, such as a `Get-PSSession` command.</span></span> <span data-ttu-id="c2ed2-508">Dieser Parameter ist nur mit dem **InDisconnectedSession** -Parameter gültig.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-508">This parameter is valid only with the **InDisconnectedSession** parameter.</span></span>

<span data-ttu-id="c2ed2-509">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-509">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerName, FilePathComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c2ed2-510">-Sessionoption</span><span class="sxs-lookup"><span data-stu-id="c2ed2-510">-SessionOption</span></span>

<span data-ttu-id="c2ed2-511">Gibt erweiterte Optionen für die Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-511">Specifies advanced options for the session.</span></span> <span data-ttu-id="c2ed2-512">Geben Sie ein **sessionoption** -Objekt ein, z. b. ein Objekt, das Sie mit dem `New-PSSessionOption` Cmdlet erstellen, oder eine Hash Tabelle, in der die Schlüssel Sitzungs Optionsnamen und die Werte Sitzungs Optionswerte sind.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-512">Enter a **SessionOption** object, such as one that you create using the `New-PSSessionOption` cmdlet, or a hash table in which the keys are session option names and the values are session option values.</span></span>

<span data-ttu-id="c2ed2-513">Die Standardwerte für die Optionen werden durch den Wert der Einstellungs `$PSSessionOption` Variablen bestimmt, sofern festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-513">The default values for the options are determined by the value of the `$PSSessionOption` preference variable, if it's set.</span></span> <span data-ttu-id="c2ed2-514">Andernfalls werden die Standardwerte durch Optionen festgelegt, die in der Sitzungskonfiguration festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-514">Otherwise, the default values are established by options set in the session configuration.</span></span>

<span data-ttu-id="c2ed2-515">Die Sitzungs Optionswerte haben Vorrang vor Standardwerten für Sitzungen, die in der `$PSSessionOption` Preference-Variablen und in der Sitzungs Konfiguration festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-515">The session option values take precedence over default values for sessions set in the `$PSSessionOption` preference variable and in the session configuration.</span></span> <span data-ttu-id="c2ed2-516">Allerdings haben Sie Vorrang vor maximalen Werten, Kontingenten oder Grenzwerten, die in der Sitzungs Konfiguration festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-516">However, they don't take precedence over maximum values, quotas, or limits set in the session configuration.</span></span>

<span data-ttu-id="c2ed2-517">Eine Beschreibung der Sitzungs Optionen, die die Standardwerte enthalten, finden Sie unter `New-PSSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="c2ed2-517">For a description of the session options that includes the default values, see `New-PSSessionOption`.</span></span> <span data-ttu-id="c2ed2-518">Weitere Informationen zur Einstellungs `$PSSessionOption` Variablen finden Sie unter [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="c2ed2-518">For information about the `$PSSessionOption` preference variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>
<span data-ttu-id="c2ed2-519">Weitere Informationen zu Sitzungs Konfigurationen finden Sie unter [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="c2ed2-519">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

```yaml
Type: System.Management.Automation.Remoting.PSSessionOption
Parameter Sets: ComputerName, FilePathComputerName, Uri, FilePathUri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c2ed2-520">-SshConnection</span><span class="sxs-lookup"><span data-stu-id="c2ed2-520">-SSHConnection</span></span>

<span data-ttu-id="c2ed2-521">Dieser Parameter nimmt ein Array von Hash Tabellen an, in denen jede Hash Tabelle einen oder mehrere Verbindungsparameter enthält, die zum Herstellen einer Secure Shell (SSH)-Verbindung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-521">This parameter takes an array of hash tables where each hash table contains one or more connection parameters needed to establish a Secure Shell (SSH) connection.</span></span> <span data-ttu-id="c2ed2-522">Der **SshConnection** -Parameter ist nützlich zum Erstellen mehrerer Sitzungen, in denen jede Sitzung andere Verbindungsinformationen erfordert.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-522">The **SSHConnection** parameter is useful for creating multiple sessions where each session requires different connection information.</span></span>

<span data-ttu-id="c2ed2-523">Die Hash Tabelle verfügt über die folgenden Member:</span><span class="sxs-lookup"><span data-stu-id="c2ed2-523">The hashtable has the following members:</span></span>

- <span data-ttu-id="c2ed2-524">**Computername** (oder **Hostname** )</span><span class="sxs-lookup"><span data-stu-id="c2ed2-524">**ComputerName** (or **HostName** )</span></span>
- <span data-ttu-id="c2ed2-525">**Port**</span><span class="sxs-lookup"><span data-stu-id="c2ed2-525">**Port**</span></span>
- <span data-ttu-id="c2ed2-526">**UserName**</span><span class="sxs-lookup"><span data-stu-id="c2ed2-526">**UserName**</span></span>
- <span data-ttu-id="c2ed2-527">**KeyFilePath** (oder **identityfilepath** )</span><span class="sxs-lookup"><span data-stu-id="c2ed2-527">**KeyFilePath** (or **IdentityFilePath** )</span></span>

<span data-ttu-id="c2ed2-528">**Computername** (oder **Hostname** ) ist das einzige erforderliche Schlüssel-Wert-Paar.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-528">**ComputerName** (or **HostName** ) is the only key-value pair that is required.</span></span>

<span data-ttu-id="c2ed2-529">Dieser Parameter wurde in PowerShell 6,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-529">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Collections.Hashtable[]
Parameter Sets: SSHHostHashParam, FilePathSSHHostHash
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c2ed2-530">-Sshtransport</span><span class="sxs-lookup"><span data-stu-id="c2ed2-530">-SSHTransport</span></span>

<span data-ttu-id="c2ed2-531">Gibt an, dass die Remote Verbindung mithilfe von Secure Shell (SSH) hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-531">Indicates that the remote connection is established using Secure Shell (SSH).</span></span>

<span data-ttu-id="c2ed2-532">Standardmäßig verwendet PowerShell Windows WinRM, um eine Verbindung mit einem Remote Computer herzustellen.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-532">By default PowerShell uses Windows WinRM to connect to a remote computer.</span></span> <span data-ttu-id="c2ed2-533">Dieser Switch erzwingt, dass PowerShell den **Hostname** -Parameter zum Einrichten einer SSH-basierten Remote Verbindung verwendet.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-533">This switch forces PowerShell to use the **HostName** parameter for establishing an SSH based remote connection.</span></span>

<span data-ttu-id="c2ed2-534">Dieser Parameter wurde in PowerShell 6,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-534">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SSHHost, FilePathSSHHost
Aliases:
Accepted values: true

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c2ed2-535">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="c2ed2-535">-ThrottleLimit</span></span>

<span data-ttu-id="c2ed2-536">Gibt die maximale Anzahl von gleichzeitigen Verbindungen an, die zum Ausführen dieses Befehls hergestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-536">Specifies the maximum number of concurrent connections that can be established to run this command.</span></span>
<span data-ttu-id="c2ed2-537">Wenn Sie diesen Parameter weglassen oder den Wert %%amp;quot;0%%amp;quot; eingeben, wird der Standardwert %%amp;quot;32%%amp;quot; verwendet.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-537">If you omit this parameter or enter a value of 0, the default value, 32, is used.</span></span>

<span data-ttu-id="c2ed2-538">Die Drosselungsgrenze gilt nur für den aktuellen Befehl und nicht für die Sitzung oder den Computer.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-538">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

```yaml
Type: System.Int32
Parameter Sets: FilePathRunspace, Session, ComputerName, FilePathComputerName, Uri, FilePathUri, VMId, VMName, FilePathVMId, FilePathVMName, ContainerId, FilePathContainerId
Aliases:

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c2ed2-539">-UserName</span><span class="sxs-lookup"><span data-stu-id="c2ed2-539">-UserName</span></span>

<span data-ttu-id="c2ed2-540">Gibt den Benutzernamen für das Konto an, das zum Ausführen eines Befehls auf dem Remote Computer verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-540">Specifies the username for the account used to run a command on the remote computer.</span></span> <span data-ttu-id="c2ed2-541">Die Benutzer Authentifizierungsmethode hängt davon ab, wie Secure Shell (SSH) auf dem Remote Computer konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-541">The user authentication method depends on how Secure Shell (SSH) is configured on the remote computer.</span></span>

<span data-ttu-id="c2ed2-542">Wenn SSH für die einfache Kenn Wort Authentifizierung konfiguriert ist, werden Sie zur Eingabe des Benutzer Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-542">If SSH is configured for basic password authentication, then you'll be prompted for the user password.</span></span>

<span data-ttu-id="c2ed2-543">Wenn SSH für die Schlüssel basierte Benutzerauthentifizierung konfiguriert ist, kann ein Schlüssel Dateipfad über den Schlüssel **FilePath** -Parameter bereitgestellt werden, und es erfolgt keine Kenn Wort Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-543">If SSH is configured for key-based user authentication then a key file path can be provided via the **KeyFilePath** parameter and no password prompt occurs.</span></span> <span data-ttu-id="c2ed2-544">Wenn sich die Client Benutzer Schlüsseldatei an einem bekannten SSH-Speicherort befindet, ist der **keyFilePath** -Parameter für die Schlüssel basierte Authentifizierung nicht erforderlich, und die Benutzerauthentifizierung erfolgt automatisch basierend auf dem Benutzernamen.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-544">If the client user key file is located in an SSH known location, then the **KeyFilePath** parameter isn't needed for key-based authentication, and user authentication occurs automatically based on the username.</span></span> <span data-ttu-id="c2ed2-545">Weitere Informationen finden Sie in der SSH-Dokumentation Ihrer Plattform zur Schlüssel basierten Benutzerauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-545">For more information, see your platform's SSH documentation about key-based user authentication.</span></span>

<span data-ttu-id="c2ed2-546">Dies ist kein erforderlicher Parameter.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-546">This isn't a required parameter.</span></span> <span data-ttu-id="c2ed2-547">Wenn der **username** -Parameter nicht angegeben wird, wird der aktuell angemeldete Benutzername für die Verbindung verwendet.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-547">If the **UserName** parameter isn't specified, then the current logged on username is used for the connection.</span></span>

<span data-ttu-id="c2ed2-548">Dieser Parameter wurde in PowerShell 6,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-548">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.String
Parameter Sets: SSHHost, FilePathSSHHost
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c2ed2-549">-US-</span><span class="sxs-lookup"><span data-stu-id="c2ed2-549">-UseSSL</span></span>

<span data-ttu-id="c2ed2-550">Gibt an, dass dieses Cmdlet das Secure Sockets Layer (SSL)-Protokoll verwendet, um eine Verbindung mit dem Remote Computer herzustellen.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-550">Indicates that this cmdlet uses the Secure Sockets Layer (SSL) protocol to establish a connection to the remote computer.</span></span> <span data-ttu-id="c2ed2-551">Standardmäßig wird SSL nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-551">By default, SSL isn't used.</span></span>

<span data-ttu-id="c2ed2-552">WS-Management verschlüsselt alle über das Netzwerk übertragenen PowerShell-Inhalte.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-552">WS-Management encrypts all PowerShell content transmitted over the network.</span></span> <span data-ttu-id="c2ed2-553">Der **Parameter "** " ist ein zusätzlicher Schutz, der die Daten über eine HTTPS-anstelle von http sendet.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-553">The **UseSSL** parameter is an additional protection that sends the data across an HTTPS, instead of HTTP.</span></span>

<span data-ttu-id="c2ed2-554">Wenn Sie diesen Parameter verwenden, aber SSL auf dem Port, der für den Befehl verwendet wird, nicht verfügbar ist, schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-554">If you use this parameter, but SSL isn't available on the port that's used for the command, the command fails.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName, FilePathComputerName
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c2ed2-555">-VMID</span><span class="sxs-lookup"><span data-stu-id="c2ed2-555">-VMId</span></span>

<span data-ttu-id="c2ed2-556">Gibt ein Array von IDs von virtuellen Computern an.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-556">Specifies an array of IDs of virtual machines.</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: VMId, FilePathVMId
Aliases: VMGuid

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c2ed2-557">-VMName</span><span class="sxs-lookup"><span data-stu-id="c2ed2-557">-VMName</span></span>

<span data-ttu-id="c2ed2-558">Gibt ein Array von Namen von virtuellen Computern an.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-558">Specifies an array of names of virtual machines.</span></span>

```yaml
Type: System.String[]
Parameter Sets: VMName, FilePathVMName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c2ed2-559">-Subsystem</span><span class="sxs-lookup"><span data-stu-id="c2ed2-559">-Subsystem</span></span>

<span data-ttu-id="c2ed2-560">Gibt das SSH-Subsystem an, das für die neue **PSSession** verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-560">Specifies the SSH subsystem used for the new **PSSession**.</span></span>

<span data-ttu-id="c2ed2-561">Gibt das Subsystem an, das auf dem Ziel verwendet werden soll, wie in sshd_config definiert.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-561">This specifies the subsystem to use on the target as defined in sshd_config.</span></span>
<span data-ttu-id="c2ed2-562">Das Subsystem startet eine bestimmte Version von PowerShell mit vordefinierten Parametern.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-562">The subsystem starts a specific version of PowerShell with predefined parameters.</span></span>
<span data-ttu-id="c2ed2-563">Wenn das angegebene Subsystem auf dem Remote Computer nicht vorhanden ist, schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-563">If the specified subsystem does not exist on the remote computer, the command fails.</span></span>

<span data-ttu-id="c2ed2-564">Wenn dieser Parameter nicht verwendet wird, ist der Standardwert das "PowerShell"-Subsystem.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-564">If this parameter is not used, the default is the 'powershell' subsystem.</span></span>

```yaml
Type: System.String
Parameter Sets: SSHHost
Aliases:

Required: False
Position: Named
Default value: powershell
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c2ed2-565">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c2ed2-565">CommonParameters</span></span>

<span data-ttu-id="c2ed2-566">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-566">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c2ed2-567">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c2ed2-567">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c2ed2-568">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="c2ed2-568">INPUTS</span></span>

### <span data-ttu-id="c2ed2-569">System. Management. Automation. ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="c2ed2-569">System.Management.Automation.ScriptBlock</span></span>

<span data-ttu-id="c2ed2-570">Sie können einen Befehl in einem Skriptblock an die Pipeline übergeben `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="c2ed2-570">You can pipe a command in a script block to `Invoke-Command`.</span></span> <span data-ttu-id="c2ed2-571">Verwenden `$Input` Sie die automatische Variable, um die Eingabe Objekte im Befehl darzustellen.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-571">Use the `$Input` automatic variable to represent the input objects in the command.</span></span>

## <span data-ttu-id="c2ed2-572">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="c2ed2-572">OUTPUTS</span></span>

### <span data-ttu-id="c2ed2-573">System. Management. Automation. psremotingjob, System. Management. Automation. Runspaces. PSSession oder die Ausgabe des aufgerufenen Befehls</span><span class="sxs-lookup"><span data-stu-id="c2ed2-573">System.Management.Automation.PSRemotingJob, System.Management.Automation.Runspaces.PSSession, or the output of the invoked command</span></span>

<span data-ttu-id="c2ed2-574">Dieses Cmdlet gibt ein Auftrags Objekt zurück, wenn Sie den **AsJob** -Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-574">This cmdlet returns a job object, if you use the **AsJob** parameter.</span></span> <span data-ttu-id="c2ed2-575">Wenn Sie den **indisconnectedsession** -Parameter angeben, `Invoke-Command` gibt ein **PSSession** -Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-575">If you specify the **InDisconnectedSession** parameter, `Invoke-Command` returns a **PSSession** object.</span></span> <span data-ttu-id="c2ed2-576">Andernfalls wird die Ausgabe des aufgerufenen Befehls zurückgegeben, bei dem es sich um den Wert des **ScriptBlock** -Parameters handelt.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-576">Otherwise, it returns the output of the invoked command, which is the value of the **ScriptBlock** parameter.</span></span>

## <span data-ttu-id="c2ed2-577">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="c2ed2-577">NOTES</span></span>

<span data-ttu-id="c2ed2-578">Wenn unter Windows Vista und höheren Versionen des Windows-Betriebssystems der **Computername** -Parameter von `Invoke-Command` zum Ausführen eines Befehls auf dem lokalen Computer verwendet werden soll, müssen Sie PowerShell mithilfe der Option **als Administrator ausführen** ausführen.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-578">On Windows Vista, and later versions of the Windows operating system, to use the **ComputerName** parameter of `Invoke-Command` to run a command on the local computer, you must run PowerShell using the **Run as administrator** option.</span></span>

<span data-ttu-id="c2ed2-579">Wenn Sie Befehle auf mehreren Computern ausführen, stellt PowerShell eine Verbindung mit den Computern in der Reihenfolge her, in der Sie in der Liste angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-579">When you run commands on multiple computers, PowerShell connects to the computers in the order in which they appear in the list.</span></span> <span data-ttu-id="c2ed2-580">Allerdings wird die Befehlsausgabe in der Reihenfolge angezeigt, in der Sie von den Remote Computern empfangen wird, die sich möglicherweise unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-580">However, the command output is displayed in the order that it's received from the remote computers, which might be different.</span></span>

<span data-ttu-id="c2ed2-581">Fehler, die sich aus dem Befehl ergeben, der `Invoke-Command` ausführt, sind in den Befehls Ergebnissen enthalten.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-581">Errors that result from the command that `Invoke-Command` runs are included in the command results.</span></span>
<span data-ttu-id="c2ed2-582">Fehler, die in einem lokalen Befehl Fehler mit Abbruch sein würden, werden in einem Remotebefehl als Fehler ohne Abbruch behandelt.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-582">Errors that would be terminating errors in a local command are treated as non-terminating errors in a remote command.</span></span> <span data-ttu-id="c2ed2-583">Durch diese Strategie wird sichergestellt, dass beim Beenden von Fehlern auf einem Computer der Befehl auf allen Computern, auf denen er ausgeführt wird, nicht geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-583">This strategy makes sure that terminating errors on one computer don't close the command on all computers on which it's run.</span></span> <span data-ttu-id="c2ed2-584">Diese Vorgehensweise wird selbst dann verwendet, wenn ein Remotebefehl auf einem einzelnen Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-584">This practice is used even when a remote command is run on a single computer.</span></span>

<span data-ttu-id="c2ed2-585">Wenn sich der Remote Computer nicht in einer Domäne befindet, der der lokale Computer vertraut, ist der Computer möglicherweise nicht in der Lage, die Anmelde Informationen des Benutzers zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-585">If the remote computer isn't in a domain that the local computer trusts, the computer might not be able to authenticate the user's credentials.</span></span> <span data-ttu-id="c2ed2-586">Um den Remote Computer der Liste der vertrauenswürdigen Hosts in der WS-Verwaltung hinzuzufügen, verwenden Sie den folgenden Befehl im `WSMAN` Anbieter, wobei `<Remote-Computer-Name>` der Name des Remote Computers ist:</span><span class="sxs-lookup"><span data-stu-id="c2ed2-586">To add the remote computer to the list of trusted hosts in WS-Management, use the following command in the `WSMAN` provider, where `<Remote-Computer-Name>` is the name of the remote computer:</span></span>

`Set-Item -Path WSMan:\Localhost\Client\TrustedHosts -Value \<Remote-Computer-Name\>`

<span data-ttu-id="c2ed2-587">Wenn Sie eine **PSSession** mit dem **indisconnectedsession** -Parameter trennen, wird der Sitzungs Status **getrennt** , und die Verfügbarkeit ist **None**.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-587">When you disconnect a **PSSession** using the **InDisconnectedSession** parameter, the session state is **Disconnected** and the availability is **None**.</span></span> <span data-ttu-id="c2ed2-588">Der Wert der **State** Eigenschaft bezieht sich auf die aktuelle Sitzung.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-588">The value of the **State** property is relative to the current session.</span></span> <span data-ttu-id="c2ed2-589">Der Wert " **getrennt** " bedeutet, dass die **PSSession** nicht mit der aktuellen Sitzung verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-589">A value of **Disconnected** means that the **PSSession** isn't connected to the current session.</span></span> <span data-ttu-id="c2ed2-590">Dies bedeutet jedoch nicht, dass die **PSSession** von allen Sitzungen getrennt ist.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-590">However, it doesn't mean that the **PSSession** is disconnected from all sessions.</span></span> <span data-ttu-id="c2ed2-591">Sie kann mit einer anderen Sitzung verbunden sein.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-591">It might be connected to a different session.</span></span> <span data-ttu-id="c2ed2-592">Um festzustellen, ob Sie eine Sitzungsverbindung herstellen bzw. wiederherstellen können, verwenden Sie die **Availability** -Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-592">To determine whether you can connect or reconnect to the session, use the **Availability** property.</span></span>

<span data-ttu-id="c2ed2-593">Ein **Availability** -Wert von **None** gibt an, dass eine Verbindung mit der Sitzung hergestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-593">An **Availability** value of **None** indicates that you can connect to the session.</span></span> <span data-ttu-id="c2ed2-594">Der Wert **ausgelastet** gibt an, dass keine Verbindung mit der **PSSession** hergestellt werden kann, da Sie mit einer anderen Sitzung verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-594">A value of **Busy** indicates that you can't connect to the **PSSession** because it's connected to another session.</span></span> <span data-ttu-id="c2ed2-595">Weitere Informationen zu den Werten der **State** -Eigenschaft von Sitzungen finden Sie unter [runspacestate](/dotnet/api/system.management.automation.runspaces.runspacestate).</span><span class="sxs-lookup"><span data-stu-id="c2ed2-595">For more information about the values of the **State** property of sessions, see [RunspaceState](/dotnet/api/system.management.automation.runspaces.runspacestate).</span></span> <span data-ttu-id="c2ed2-596">Weitere Informationen zu den Werten der **Availability** -Eigenschaft von Sitzungen finden Sie unter [runspaceavailability](/dotnet/api/system.management.automation.runspaces.runspaceavailability).</span><span class="sxs-lookup"><span data-stu-id="c2ed2-596">For more information about the values of the **Availability** property of sessions, see [RunspaceAvailability](/dotnet/api/system.management.automation.runspaces.runspaceavailability).</span></span>

<span data-ttu-id="c2ed2-597">Die Parameter " **Hostname** " und " **SshConnection** " wurden ab PowerShell 6,0 eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-597">The **HostName** and **SSHConnection** parameters were included starting with PowerShell 6.0.</span></span> <span data-ttu-id="c2ed2-598">Sie wurden hinzugefügt, um PowerShell-Remoting basierend auf Secure Shell (SSH) bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-598">They were added to provide PowerShell remoting based on Secure Shell (SSH).</span></span> <span data-ttu-id="c2ed2-599">PowerShell und SSH werden auf mehreren Plattformen (Windows, Linux, macOS) unterstützt, und PowerShell-Remoting funktioniert auf diesen Plattformen, auf denen PowerShell und SSH installiert und konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-599">PowerShell and SSH are supported on multiple platforms (Windows, Linux, macOS) and PowerShell remoting works over these platforms where PowerShell and SSH are installed and configured.</span></span> <span data-ttu-id="c2ed2-600">Dies ist unabhängig vom vorherigen Windows-Remoting, das auf WinRM basiert, und viele der WinRM-spezifischen Features und Einschränkungen gelten nicht.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-600">This is separate from the previous Windows only remoting that is based on WinRM and many of the WinRM specific features and limitations don't apply.</span></span> <span data-ttu-id="c2ed2-601">Beispielsweise werden auf WinRM basierende Kontingente, Sitzungs Optionen, benutzerdefinierte Endpunkt Konfiguration und Features zum Trennen und Wiederherstellen von Verbindungen derzeit nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c2ed2-601">For example WinRM based quotas, session options, custom endpoint configuration, and disconnect/reconnect features are currently not supported.</span></span> <span data-ttu-id="c2ed2-602">Weitere Informationen zum Einrichten von PowerShell-SSH-Remoting finden Sie unter [PowerShell-Remoting über SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span><span class="sxs-lookup"><span data-stu-id="c2ed2-602">For more information about how to set up PowerShell SSH remoting, see [PowerShell Remoting Over SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span></span>

## <span data-ttu-id="c2ed2-603">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="c2ed2-603">RELATED LINKS</span></span>

[<span data-ttu-id="c2ed2-604">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="c2ed2-604">about_PSSessions</span></span>](./About/about_PSSessions.md)

[<span data-ttu-id="c2ed2-605">about_Remote</span><span class="sxs-lookup"><span data-stu-id="c2ed2-605">about_Remote</span></span>](./About/about_Remote.md)

[<span data-ttu-id="c2ed2-606">about_Remote_Disconnected_Sessions</span><span class="sxs-lookup"><span data-stu-id="c2ed2-606">about_Remote_Disconnected_Sessions</span></span>](./About/about_Remote_Disconnected_Sessions.md)

[<span data-ttu-id="c2ed2-607">about_Remote_Troubleshooting</span><span class="sxs-lookup"><span data-stu-id="c2ed2-607">about_Remote_Troubleshooting</span></span>](./About/about_remote_troubleshooting.md)

[<span data-ttu-id="c2ed2-608">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="c2ed2-608">about_Remote_Variables</span></span>](./About/about_Remote_Variables.md)

[<span data-ttu-id="c2ed2-609">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="c2ed2-609">about_Scopes</span></span>](./About/about_scopes.md)

[<span data-ttu-id="c2ed2-610">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="c2ed2-610">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="c2ed2-611">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="c2ed2-611">Exit-PSSession</span></span>](Exit-PSSession.md)

[<span data-ttu-id="c2ed2-612">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="c2ed2-612">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="c2ed2-613">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="c2ed2-613">Invoke-Item</span></span>](../Microsoft.PowerShell.Management/Invoke-Item.md)

[<span data-ttu-id="c2ed2-614">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="c2ed2-614">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="c2ed2-615">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="c2ed2-615">Remove-PSSession</span></span>](Remove-PSSession.md)

[<span data-ttu-id="c2ed2-616">WSMan-Anbieter</span><span class="sxs-lookup"><span data-stu-id="c2ed2-616">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)
