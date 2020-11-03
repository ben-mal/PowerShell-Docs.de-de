---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/invoke-command?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-Command
ms.openlocfilehash: 652ff321ea1c6507915be9748715604166207200
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218236"
---
# <span data-ttu-id="2d46f-103">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="2d46f-103">Invoke-Command</span></span>

## <span data-ttu-id="2d46f-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="2d46f-104">SYNOPSIS</span></span>
<span data-ttu-id="2d46f-105">Führt Befehle auf lokalen Computern und Remotecomputern aus.</span><span class="sxs-lookup"><span data-stu-id="2d46f-105">Runs commands on local and remote computers.</span></span>

## <span data-ttu-id="2d46f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2d46f-106">SYNTAX</span></span>

### <span data-ttu-id="2d46f-107">InProcess (Standard)</span><span class="sxs-lookup"><span data-stu-id="2d46f-107">InProcess (Default)</span></span>

```
Invoke-Command [-ScriptBlock] <ScriptBlock> [-NoNewScope] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [<CommonParameters>]
```

### <span data-ttu-id="2d46f-108">Sitzung</span><span class="sxs-lookup"><span data-stu-id="2d46f-108">Session</span></span>

```
Invoke-Command [[-Session] <PSSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-HideComputerName]
 [-JobName <String>] [-ScriptBlock] <ScriptBlock> [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [<CommonParameters>]
```

### <span data-ttu-id="2d46f-109">Filepathrunspace</span><span class="sxs-lookup"><span data-stu-id="2d46f-109">FilePathRunspace</span></span>

```
Invoke-Command [[-Session] <PSSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-HideComputerName]
 [-JobName <String>] [-FilePath] <String> [-InputObject <PSObject>] [-ArgumentList <Object[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="2d46f-110">Filepathcomputername</span><span class="sxs-lookup"><span data-stu-id="2d46f-110">FilePathComputerName</span></span>

```
Invoke-Command [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-Port <Int32>] [-UseSSL]
 [-ConfigurationName <String>] [-ApplicationName <String>] [-ThrottleLimit <Int32>] [-AsJob]
 [-InDisconnectedSession] [-SessionName <String[]>] [-HideComputerName] [-JobName <String>]
 [-FilePath] <String> [-SessionOption <PSSessionOption>] [-Authentication <AuthenticationMechanism>]
 [-EnableNetworkAccess] [-InputObject <PSObject>] [-ArgumentList <Object[]>] [<CommonParameters>]
```

### <span data-ttu-id="2d46f-111">Computername</span><span class="sxs-lookup"><span data-stu-id="2d46f-111">ComputerName</span></span>

```
Invoke-Command [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-Port <Int32>] [-UseSSL]
 [-ConfigurationName <String>] [-ApplicationName <String>] [-ThrottleLimit <Int32>] [-AsJob]
 [-InDisconnectedSession] [-SessionName <String[]>] [-HideComputerName] [-JobName <String>]
 [-ScriptBlock] <ScriptBlock> [-SessionOption <PSSessionOption>]
 [-Authentication <AuthenticationMechanism>] [-EnableNetworkAccess] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="2d46f-112">Uri</span><span class="sxs-lookup"><span data-stu-id="2d46f-112">Uri</span></span>

```
Invoke-Command [-Credential <PSCredential>] [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [[-ConnectionUri] <Uri[]>] [-AsJob] [-InDisconnectedSession] [-HideComputerName]
 [-JobName <String>] [-ScriptBlock] <ScriptBlock> [-AllowRedirection]
 [-SessionOption <PSSessionOption>] [-Authentication <AuthenticationMechanism>]
 [-EnableNetworkAccess] [-InputObject <PSObject>] [-ArgumentList <Object[]>]
 [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="2d46f-113">Filepaar</span><span class="sxs-lookup"><span data-stu-id="2d46f-113">FilePathUri</span></span>

```
Invoke-Command [-Credential <PSCredential>] [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [[-ConnectionUri] <Uri[]>] [-AsJob] [-InDisconnectedSession] [-HideComputerName]
 [-JobName <String>] [-FilePath] <String> [-AllowRedirection] [-SessionOption <PSSessionOption>]
 [-Authentication <AuthenticationMechanism>] [-EnableNetworkAccess] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [<CommonParameters>]
```

### <span data-ttu-id="2d46f-114">VMId</span><span class="sxs-lookup"><span data-stu-id="2d46f-114">VMId</span></span>

```
Invoke-Command -Credential <PSCredential> [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [-AsJob] [-HideComputerName] [-ScriptBlock] <ScriptBlock> [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [-VMId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="2d46f-115">VMName</span><span class="sxs-lookup"><span data-stu-id="2d46f-115">VMName</span></span>

```
Invoke-Command -Credential <PSCredential> [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [-AsJob] [-HideComputerName] [-ScriptBlock] <ScriptBlock> [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] -VMName <String[]> [<CommonParameters>]
```

### <span data-ttu-id="2d46f-116">Filepathvmid</span><span class="sxs-lookup"><span data-stu-id="2d46f-116">FilePathVMId</span></span>

```
Invoke-Command -Credential <PSCredential> [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [-AsJob] [-HideComputerName] [-FilePath] <String> [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [-VMId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="2d46f-117">Filepathvmname</span><span class="sxs-lookup"><span data-stu-id="2d46f-117">FilePathVMName</span></span>

```
Invoke-Command -Credential <PSCredential> [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [-AsJob] [-HideComputerName] [-FilePath] <String> [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] -VMName <String[]> [<CommonParameters>]
```

### <span data-ttu-id="2d46f-118">ContainerId</span><span class="sxs-lookup"><span data-stu-id="2d46f-118">ContainerId</span></span>

```
Invoke-Command [-ConfigurationName <String>] [-ThrottleLimit <Int32>] [-AsJob] [-HideComputerName]
 [-JobName <String>] [-ScriptBlock] <ScriptBlock> [-RunAsAdministrator] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] -ContainerId <String[]> [<CommonParameters>]
```

### <span data-ttu-id="2d46f-119">Filepathcontainerid</span><span class="sxs-lookup"><span data-stu-id="2d46f-119">FilePathContainerId</span></span>

```
Invoke-Command [-ConfigurationName <String>] [-ThrottleLimit <Int32>] [-AsJob] [-HideComputerName]
 [-JobName <String>] [-FilePath] <String> [-RunAsAdministrator] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] -ContainerId <String[]> [<CommonParameters>]
```

## <span data-ttu-id="2d46f-120">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2d46f-120">DESCRIPTION</span></span>

<span data-ttu-id="2d46f-121">Das `Invoke-Command` -Cmdlet führt Befehle auf einem lokalen Computer oder einem Remote Computer aus und gibt alle Ausgaben der Befehle zurück, einschließlich der Fehler.</span><span class="sxs-lookup"><span data-stu-id="2d46f-121">The `Invoke-Command` cmdlet runs commands on a local or remote computer and returns all output from the commands, including errors.</span></span> <span data-ttu-id="2d46f-122">Mit einem einzigen `Invoke-Command` Befehl können Sie Befehle auf mehreren Computern ausführen.</span><span class="sxs-lookup"><span data-stu-id="2d46f-122">Using a single `Invoke-Command` command, you can run commands on multiple computers.</span></span>

<span data-ttu-id="2d46f-123">Um einen einzelnen Befehl auf einem Remotecomputer auszuführen, verwenden Sie den **ComputerName** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="2d46f-123">To run a single command on a remote computer, use the **ComputerName** parameter.</span></span> <span data-ttu-id="2d46f-124">Um eine Reihe verwandter Befehle auszuführen, die Daten gemeinsam nutzen, verwenden Sie das `New-PSSession` -Cmdlet, um eine **PSSession** (eine permanente Verbindung) auf dem Remote Computer zu erstellen, und verwenden Sie dann den **Session** -Parameter von, `Invoke-Command` um den Befehl in der **PSSession** auszuführen.</span><span class="sxs-lookup"><span data-stu-id="2d46f-124">To run a series of related commands that share data, use the `New-PSSession` cmdlet to create a **PSSession** (a persistent connection) on the remote computer, and then use the **Session** parameter of `Invoke-Command` to run the command in the **PSSession**.</span></span> <span data-ttu-id="2d46f-125">Verwenden Sie zum Ausführen eines Befehls in einer getrennten Sitzung den **InDisconnectedSession** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="2d46f-125">To run a command in a disconnected session, use the **InDisconnectedSession** parameter.</span></span> <span data-ttu-id="2d46f-126">Verwenden Sie zum Ausführen eines Befehls in einem Hintergrundauftrag den **AsJob** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="2d46f-126">To run a command in a background job, use the **AsJob** parameter.</span></span>

<span data-ttu-id="2d46f-127">Sie können auch `Invoke-Command` auf einem lokalen Computer mit einem Skriptblock als Befehl verwenden.</span><span class="sxs-lookup"><span data-stu-id="2d46f-127">You can also use `Invoke-Command` on a local computer to a script block as a command.</span></span> <span data-ttu-id="2d46f-128">PowerShell führt den Skriptblock direkt in einem untergeordneten Bereich des aktuellen Gültigkeits Bereichs aus.</span><span class="sxs-lookup"><span data-stu-id="2d46f-128">PowerShell runs the script block immediately in a child scope of the current scope.</span></span>

<span data-ttu-id="2d46f-129">`Invoke-Command`Lesen Sie vor der Verwendung von zum Ausführen von Befehlen auf einem Remote Computer [about_Remote](./About/about_Remote.md).</span><span class="sxs-lookup"><span data-stu-id="2d46f-129">Before using `Invoke-Command` to run commands on a remote computer, read [about_Remote](./About/about_Remote.md).</span></span>

<span data-ttu-id="2d46f-130">In einigen Codebeispielen wird Verteilung verwendet, um die Zeilenlänge zu verringern.</span><span class="sxs-lookup"><span data-stu-id="2d46f-130">Some code samples use splatting to reduce the line length.</span></span> <span data-ttu-id="2d46f-131">Weitere Informationen finden Sie unter [about_Splatting](./About/about_Splatting.md).</span><span class="sxs-lookup"><span data-stu-id="2d46f-131">For more information, see [about_Splatting](./About/about_Splatting.md).</span></span>

## <span data-ttu-id="2d46f-132">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="2d46f-132">EXAMPLES</span></span>

### <span data-ttu-id="2d46f-133">Beispiel 1: Ausführen eines Skripts auf einem Server</span><span class="sxs-lookup"><span data-stu-id="2d46f-133">Example 1: Run a script on a server</span></span>

<span data-ttu-id="2d46f-134">In diesem Beispiel wird das `Test.ps1` Skript auf dem Computer Server01 ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2d46f-134">This example runs the `Test.ps1` script on the Server01 computer.</span></span>

```powershell
Invoke-Command -FilePath c:\scripts\test.ps1 -ComputerName Server01
```

<span data-ttu-id="2d46f-135">Der **FilePath** -Parameter gibt ein Skript an, das sich auf dem lokalen Computer befindet.</span><span class="sxs-lookup"><span data-stu-id="2d46f-135">The **FilePath** parameter specifies a script that is located on the local computer.</span></span> <span data-ttu-id="2d46f-136">Das Skript wird auf dem Remotecomputer ausgeführt, und die Ergebnisse werden an den lokalen Computer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2d46f-136">The script runs on the remote computer and the results are returned to the local computer.</span></span>

### <span data-ttu-id="2d46f-137">Beispiel 2: Ausführen eines Befehls auf einem Remote Server</span><span class="sxs-lookup"><span data-stu-id="2d46f-137">Example 2: Run a command on a remote server</span></span>

<span data-ttu-id="2d46f-138">In diesem Beispiel wird ein `Get-Culture` Befehl auf dem Remote Computer Server01 ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2d46f-138">This example runs a `Get-Culture` command on the Server01 remote computer.</span></span>

```powershell
Invoke-Command -ComputerName Server01 -Credential Domain01\User01 -ScriptBlock { Get-Culture }
```

<span data-ttu-id="2d46f-139">Der **Computername** -Parameter gibt den Namen des Remote Computers an.</span><span class="sxs-lookup"><span data-stu-id="2d46f-139">The **ComputerName** parameter specifies the name of the remote computer.</span></span> <span data-ttu-id="2d46f-140">Der **Credential** -Parameter wird verwendet, um den Befehl im Sicherheitskontext von Domain01\User01 auszuführen, einem Benutzer, der über die Berechtigung zum Ausführen von Befehlen verfügt.</span><span class="sxs-lookup"><span data-stu-id="2d46f-140">The **Credential** parameter is used to run the command in the security context of Domain01\User01, a user who has permission to run commands.</span></span> <span data-ttu-id="2d46f-141">Der **ScriptBlock** -Parameter gibt den Befehl an, der auf dem Remote Computer ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="2d46f-141">The **ScriptBlock** parameter specifies the command to be run on the remote computer.</span></span>

<span data-ttu-id="2d46f-142">In der Antwort fordert PowerShell das Kennwort und eine Authentifizierungsmethode für das USER01-Konto an.</span><span class="sxs-lookup"><span data-stu-id="2d46f-142">In response, PowerShell requests the password and an authentication method for the User01 account.</span></span>
<span data-ttu-id="2d46f-143">Anschließend wird der Befehl auf dem Computer „Server01“ ausgeführt und das Ergebnis zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2d46f-143">It then runs the command on the Server01 computer and returns the result.</span></span>

### <span data-ttu-id="2d46f-144">Beispiel 3: Ausführen eines Befehls in einer permanenten Verbindung</span><span class="sxs-lookup"><span data-stu-id="2d46f-144">Example 3: Run a command in a persistent connection</span></span>

<span data-ttu-id="2d46f-145">In diesem Beispiel wird derselbe `Get-Culture` Befehl in einer Sitzung mit einer permanenten Verbindung auf dem Remote Computer mit dem Namen Server02 ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2d46f-145">This example runs the same `Get-Culture` command in a session, using a persistent connection, on the remote computer named Server02.</span></span>

```powershell
$s = New-PSSession -ComputerName Server02 -Credential Domain01\User01
Invoke-Command -Session $s -ScriptBlock {Get-Culture}
```

<span data-ttu-id="2d46f-146">`New-PSSession`Mit dem-Cmdlet wird eine Sitzung auf dem Remote Computer Server02 erstellt und in der `$s` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="2d46f-146">The `New-PSSession` cmdlet creates a session on the Server02 remote computer and saves it in the `$s` variable.</span></span> <span data-ttu-id="2d46f-147">In der Regel erstellen Sie eine Sitzung nur, wenn Sie eine Reihe von Befehlen auf dem Remote Computer ausführen.</span><span class="sxs-lookup"><span data-stu-id="2d46f-147">Typically, you create a session only when you run a series of commands on the remote computer.</span></span>

<span data-ttu-id="2d46f-148">Das- `Invoke-Command` Cmdlet führt den `Get-Culture` Befehl auf Server02 aus.</span><span class="sxs-lookup"><span data-stu-id="2d46f-148">The `Invoke-Command` cmdlet runs the `Get-Culture` command on Server02.</span></span> <span data-ttu-id="2d46f-149">Der **Session** -Parameter gibt die in der Variablen gespeicherte Sitzung an `$s` .</span><span class="sxs-lookup"><span data-stu-id="2d46f-149">The **Session** parameter specifies the session saved in the `$s` variable.</span></span>

<span data-ttu-id="2d46f-150">In der Antwort führt PowerShell den Befehl in der Sitzung auf dem Server02-Computer aus.</span><span class="sxs-lookup"><span data-stu-id="2d46f-150">In response, PowerShell runs the command in the session on the Server02 computer.</span></span>

### <span data-ttu-id="2d46f-151">Beispiel 4: Verwenden einer Sitzung zum Ausführen einer Reihe von Befehlen, die Daten freigeben</span><span class="sxs-lookup"><span data-stu-id="2d46f-151">Example 4: Use a session to run a series of commands that share data</span></span>

<span data-ttu-id="2d46f-152">In diesem Beispiel werden die Auswirkungen der Verwendung von **Computername** und **Sitzungs** Parametern von verglichen `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="2d46f-152">This example compares the effects of using **ComputerName** and **Session** parameters of `Invoke-Command`.</span></span> <span data-ttu-id="2d46f-153">Es veranschaulicht, wie Sie eine Sitzung verwenden können, um eine Reihe von Befehlen auszuführen, die gemeinsam die gleichen Daten nutzen.</span><span class="sxs-lookup"><span data-stu-id="2d46f-153">It shows how to use a session to run a series of commands that share the same data.</span></span>

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

<span data-ttu-id="2d46f-154">Die ersten beiden Befehle verwenden den **Computername** -Parameter von `Invoke-Command` , um Befehle auf dem Remote Computer Server02 auszuführen.</span><span class="sxs-lookup"><span data-stu-id="2d46f-154">The first two commands use the **ComputerName** parameter of `Invoke-Command` to run commands on the Server02 remote computer.</span></span> <span data-ttu-id="2d46f-155">Der erste Befehl verwendet das `Get-Process` Cmdlet, um den PowerShell-Prozess auf dem Remote Computer zu erhalten und in der `$p` Variablen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="2d46f-155">The first command uses the `Get-Process` cmdlet to get the PowerShell process on the remote computer and to save it in the `$p` variable.</span></span> <span data-ttu-id="2d46f-156">Der zweite Befehl ruft den Wert der **VirtualMemorySize** -Eigenschaft des PowerShell-Prozesses ab.</span><span class="sxs-lookup"><span data-stu-id="2d46f-156">The second command gets the value of the **VirtualMemorySize** property of the PowerShell process.</span></span>

<span data-ttu-id="2d46f-157">Wenn Sie den **Computername** -Parameter verwenden, erstellt PowerShell eine neue Sitzung, um den Befehl auszuführen.</span><span class="sxs-lookup"><span data-stu-id="2d46f-157">When you use the **ComputerName** parameter, PowerShell creates a new session to run the command.</span></span>
<span data-ttu-id="2d46f-158">Die Sitzung wird geschlossen, wenn der Befehl abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="2d46f-158">The session is closed when the command completes.</span></span> <span data-ttu-id="2d46f-159">Die `$p` Variable wurde in einer Verbindung erstellt, ist jedoch nicht in der für den zweiten Befehl erstellten Verbindung vorhanden.</span><span class="sxs-lookup"><span data-stu-id="2d46f-159">The `$p` variable was created in one connection, but it doesn't exist in the connection created for the second command.</span></span>

<span data-ttu-id="2d46f-160">Das Problem wird gelöst, indem eine persistente Sitzung auf dem Remote Computer erstellt und dann beide Befehle in der gleichen Sitzung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2d46f-160">The problem is solved by creating a persistent session on the remote computer, then running both of the commands in the same session.</span></span>

<span data-ttu-id="2d46f-161">`New-PSSession`Mit dem-Cmdlet wird eine persistente Sitzung auf dem Computer Server02 erstellt und die Sitzung in der `$s` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="2d46f-161">The `New-PSSession` cmdlet creates a persistent session on the computer Server02 and saves the session in the `$s` variable.</span></span> <span data-ttu-id="2d46f-162">`Invoke-Command`In den folgenden Zeilen wird der **Session** -Parameter verwendet, um beide Befehle in der gleichen Sitzung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="2d46f-162">The `Invoke-Command` lines that follow use the **Session** parameter to run both of the commands in the same session.</span></span> <span data-ttu-id="2d46f-163">Da beide Befehle in der gleichen Sitzung ausgeführt werden, `$p` bleibt der Wert aktiv.</span><span class="sxs-lookup"><span data-stu-id="2d46f-163">Since both commands run in the same session, the `$p` value remains active.</span></span>

### <span data-ttu-id="2d46f-164">Beispiel 5: Eingeben eines Befehls, der in einer lokalen Variablen gespeichert ist</span><span class="sxs-lookup"><span data-stu-id="2d46f-164">Example 5: Enter a command stored in a local variable</span></span>

<span data-ttu-id="2d46f-165">Dieses Beispiel zeigt, wie Sie einen Befehl erstellen, der als Skriptblock in einer lokalen Variablen gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="2d46f-165">This example shows how to create a command that is stored as a script block in a local variable.</span></span>
<span data-ttu-id="2d46f-166">Wenn der Skriptblock in einer lokalen Variablen gespeichert wird, können Sie die Variable als Wert des **ScriptBlock** -Parameters angeben.</span><span class="sxs-lookup"><span data-stu-id="2d46f-166">When the script block is saved in a local variable, you can specify the variable as the value of the **ScriptBlock** parameter.</span></span>

```powershell
$command = { Get-EventLog -LogName "Windows PowerShell" |
  Where-Object {$_.Message -like "*certificate*"} }
Invoke-Command -ComputerName S1, S2 -ScriptBlock $command
```

<span data-ttu-id="2d46f-167">Die `$command` -Variable speichert den `Get-EventLog` Befehl, der als Skriptblock formatiert ist.</span><span class="sxs-lookup"><span data-stu-id="2d46f-167">The `$command` variable stores the `Get-EventLog` command that's formatted as a script block.</span></span> <span data-ttu-id="2d46f-168">Der `Invoke-Command` führt den in gespeicherten Befehl `$command` auf den Remote Computern S1 und S2 aus.</span><span class="sxs-lookup"><span data-stu-id="2d46f-168">The `Invoke-Command` runs the command stored in `$command` on the S1 and S2 remote computers.</span></span>

### <span data-ttu-id="2d46f-169">Beispiel 6: Ausführen eines einzelnen Befehls auf mehreren Computern</span><span class="sxs-lookup"><span data-stu-id="2d46f-169">Example 6: Run a single command on several computers</span></span>

<span data-ttu-id="2d46f-170">In diesem Beispiel wird veranschaulicht, wie verwendet wird, `Invoke-Command` um einen einzelnen Befehl auf mehreren Computern auszuführen.</span><span class="sxs-lookup"><span data-stu-id="2d46f-170">This example demonstrates how to use `Invoke-Command` to run a single command on multiple computers.</span></span>

```powershell
$parameters = @{
  ComputerName = "Server01", "Server02", "TST-0143", "localhost"
  ConfigurationName = 'MySession.PowerShell'
  ScriptBlock = { Get-EventLog "Windows PowerShell" }
}
Invoke-Command @parameters
```

<span data-ttu-id="2d46f-171">Der Computer **Name** -Parameter gibt eine durch Trennzeichen getrennte Liste von Computernamen an.</span><span class="sxs-lookup"><span data-stu-id="2d46f-171">The **ComputerName** parameter specifies a comma-separated list of computer names.</span></span> <span data-ttu-id="2d46f-172">Die Liste der Computer enthält den Wert "localhost", der den lokalen Computer darstellt.</span><span class="sxs-lookup"><span data-stu-id="2d46f-172">The list of computers includes the localhost value, which represents the local computer.</span></span> <span data-ttu-id="2d46f-173">Der **ConfigurationName** -Parameter gibt eine Alternative Sitzungs Konfiguration an.</span><span class="sxs-lookup"><span data-stu-id="2d46f-173">The **ConfigurationName** parameter specifies an alternate session configuration.</span></span> <span data-ttu-id="2d46f-174">Der **ScriptBlock** -Parameter wird ausgeführt `Get-EventLog` , um die Windows PowerShell-Ereignisprotokolle von den einzelnen Computern zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="2d46f-174">The **ScriptBlock** parameter runs `Get-EventLog` to get the Windows PowerShell event logs from each computer.</span></span>

### <span data-ttu-id="2d46f-175">Beispiel 7: erhalten der Version des Host Programms auf mehreren Computern</span><span class="sxs-lookup"><span data-stu-id="2d46f-175">Example 7: Get the version of the host program on multiple computers</span></span>

<span data-ttu-id="2d46f-176">In diesem Beispiel wird die Version des PowerShell-Host Programms abgerufen, das auf 200 Remote Computern ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2d46f-176">This example gets the version of the PowerShell host program running on 200 remote computers.</span></span>

```powershell
$version = Invoke-Command -ComputerName (Get-Content Machines.txt) -ScriptBlock {(Get-Host).Version}
```

<span data-ttu-id="2d46f-177">Da nur ein Befehl ausgeführt wird, müssen Sie keine permanenten Verbindungen mit den einzelnen Computern erstellen.</span><span class="sxs-lookup"><span data-stu-id="2d46f-177">Because only one command is run, you don't have to create persistent connections to each of the computers.</span></span> <span data-ttu-id="2d46f-178">Der Befehl verwendet stattdessen den **ComputerName** -Parameter, um die Computer anzugeben.</span><span class="sxs-lookup"><span data-stu-id="2d46f-178">Instead, the command uses the **ComputerName** parameter to indicate the computers.</span></span> <span data-ttu-id="2d46f-179">Zum Angeben der Computer wird mit dem `Get-Content` Cmdlet der Inhalt der Machine.txt Datei (eine Datei mit Computernamen) erhalten.</span><span class="sxs-lookup"><span data-stu-id="2d46f-179">To specify the computers, it uses the `Get-Content` cmdlet to get the contents of the Machine.txt file, a file of computer names.</span></span>

<span data-ttu-id="2d46f-180">Das- `Invoke-Command` Cmdlet führt einen `Get-Host` Befehl auf den Remote Computern aus.</span><span class="sxs-lookup"><span data-stu-id="2d46f-180">The `Invoke-Command` cmdlet runs a `Get-Host` command on the remote computers.</span></span> <span data-ttu-id="2d46f-181">Er verwendet die Punkt Notation, um die **Versions** Eigenschaft des PowerShell-Hosts zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="2d46f-181">It uses dot notation to get the **Version** property of the PowerShell host.</span></span>

<span data-ttu-id="2d46f-182">Diese Befehle werden nacheinander ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2d46f-182">These commands run one at a time.</span></span> <span data-ttu-id="2d46f-183">Wenn die Befehle vollständig sind, wird die Ausgabe der Befehle von allen Computern in der Variablen gespeichert `$version` .</span><span class="sxs-lookup"><span data-stu-id="2d46f-183">When the commands complete, the output of the commands from all of the computers is saved in the `$version` variable.</span></span> <span data-ttu-id="2d46f-184">Die Ausgabe enthält den Namen des Computers, von dem die Daten stammen.</span><span class="sxs-lookup"><span data-stu-id="2d46f-184">The output includes the name of the computer from which the data originated.</span></span>

### <span data-ttu-id="2d46f-185">Beispiel 8: Ausführen eines Hintergrund Auftrags auf mehreren Remote Computern</span><span class="sxs-lookup"><span data-stu-id="2d46f-185">Example 8: Run a background job on several remote computers</span></span>

<span data-ttu-id="2d46f-186">In diesem Beispiel wird ein Befehl auf zwei Remote Computern ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2d46f-186">This example runs a command on two remote computers.</span></span> <span data-ttu-id="2d46f-187">Der `Invoke-Command` Befehl verwendet den **AsJob** -Parameter, sodass der Befehl als Hintergrund Auftrag ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2d46f-187">The `Invoke-Command` command uses the **AsJob** parameter so that the command runs as a background job.</span></span> <span data-ttu-id="2d46f-188">Die Befehle werden auf den Remote Computern ausgeführt, der Auftrag ist jedoch auf dem lokalen Computer vorhanden.</span><span class="sxs-lookup"><span data-stu-id="2d46f-188">The commands run on the remote computers, but the job exists on the local computer.</span></span> <span data-ttu-id="2d46f-189">Die Ergebnisse werden an den lokalen Computer übertragen.</span><span class="sxs-lookup"><span data-stu-id="2d46f-189">The results are transmitted to the local computer.</span></span>

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

<span data-ttu-id="2d46f-190">Das `New-PSSession` -Cmdlet erstellt Sitzungen auf den Remote Computern Server01 und Server02.</span><span class="sxs-lookup"><span data-stu-id="2d46f-190">The `New-PSSession` cmdlet creates sessions on the Server01 and Server02 remote computers.</span></span> <span data-ttu-id="2d46f-191">Das- `Invoke-Command` Cmdlet führt in jeder Sitzung einen Hintergrund Auftrag aus.</span><span class="sxs-lookup"><span data-stu-id="2d46f-191">The `Invoke-Command` cmdlet runs a background job in each of the sessions.</span></span> <span data-ttu-id="2d46f-192">Bei dem Befehl wird der Befehl mithilfe des **AsJob** -Parameters als Hintergrundauftrag ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2d46f-192">The command uses the **AsJob** parameter to run the command as a background job.</span></span> <span data-ttu-id="2d46f-193">Dieser Befehl gibt ein Auftragsobjekt zurück, das zwei untergeordnete Auftragsobjekte enthält, jeweils eins für die Aufträge, die auf zwei Remotecomputern ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2d46f-193">This command returns a job object that contains two child job objects, one for each of the jobs run on the two remote computers.</span></span>

<span data-ttu-id="2d46f-194">Der `Get-Job` Befehl speichert das Auftrags Objekt in der `$j` Variablen.</span><span class="sxs-lookup"><span data-stu-id="2d46f-194">The `Get-Job` command saves the job object in the `$j` variable.</span></span> <span data-ttu-id="2d46f-195">Die `$j` Variable wird dann an das `Format-List` Cmdlet weitergeleitet, um alle Eigenschaften des Auftrags Objekts in einer Liste anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2d46f-195">The `$j` variable is then piped to the `Format-List` cmdlet to display all properties of the job object in a list.</span></span> <span data-ttu-id="2d46f-196">Mit dem letzten Befehl werden die Ergebnisse der Aufträge abgerufen.</span><span class="sxs-lookup"><span data-stu-id="2d46f-196">The last command gets the results of the jobs.</span></span> <span data-ttu-id="2d46f-197">Das Auftrags Objekt wird an `$j` das `Receive-Job` Cmdlet weitergeleitet, und die Ergebnisse werden in der `$results` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="2d46f-197">It pipes the job object in `$j` to the `Receive-Job` cmdlet and stores the results in the `$results` variable.</span></span>

### <span data-ttu-id="2d46f-198">Beispiel 9: einschließen lokaler Variablen in einem Befehl, der auf einem Remote Computer ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="2d46f-198">Example 9: Include local variables in a command run on a remote computer</span></span>

<span data-ttu-id="2d46f-199">Dieses Beispiel zeigt, wie Sie die Werte von lokalen Variablen in einem Befehl einschließen können, der auf einem Remotecomputer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2d46f-199">This example shows how to include the values of local variables in a command run on a remote computer.</span></span> <span data-ttu-id="2d46f-200">Der Befehl verwendet den `Using` Scope-Modifizierer, um eine lokale Variable in einem Remote Befehl zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="2d46f-200">The command uses the `Using` scope modifier to identify a local variable in a remote command.</span></span> <span data-ttu-id="2d46f-201">Standardmäßig wird davon ausgegangen, dass alle Variablen in der Remotesitzung definiert sind.</span><span class="sxs-lookup"><span data-stu-id="2d46f-201">By default, all variables are assumed to be defined in the remote session.</span></span> <span data-ttu-id="2d46f-202">Der bereichsmodifizierer `Using` wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="2d46f-202">The `Using` scope modifier was introduced in PowerShell 3.0.</span></span> <span data-ttu-id="2d46f-203">Weitere Informationen zum bereichsmodifizierer `Using` finden Sie unter [about_Remote_Variables](./About/about_Remote_Variables.md) und [about_Scopes](./about/about_scopes.md).</span><span class="sxs-lookup"><span data-stu-id="2d46f-203">For more information about the `Using` scope modifier, see [about_Remote_Variables](./About/about_Remote_Variables.md) and [about_Scopes](./about/about_scopes.md).</span></span>

```powershell
$Log = "Windows PowerShell"
Invoke-Command -ComputerName Server01 -ScriptBlock { Get-EventLog -LogName $Using:Log -Newest 10 }
```

<span data-ttu-id="2d46f-204">Die `$Log` Variable speichert den Namen des Ereignis Protokolls, Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2d46f-204">The `$Log` variable stores the name of the event log, Windows PowerShell.</span></span> <span data-ttu-id="2d46f-205">Das- `Invoke-Command` Cmdlet wird `Get-EventLog` auf Server01 ausgeführt, um die zehn neuesten Ereignisse aus dem Ereignisprotokoll zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="2d46f-205">The `Invoke-Command` cmdlet runs `Get-EventLog` on Server01 to get the ten newest events from the event log.</span></span> <span data-ttu-id="2d46f-206">Der Wert des **logName** -Parameters ist die Variable, der der bereichsmodifizierer vorangestellt `$Log` wird, `Using` um anzugeben, dass er in der lokalen Sitzung erstellt wurde, nicht in der Remote Sitzung.</span><span class="sxs-lookup"><span data-stu-id="2d46f-206">The value of the **LogName** parameter is the `$Log` variable, which is prefixed by the `Using` scope modifier to indicate that it was created in the local session, not in the remote session.</span></span>

### <span data-ttu-id="2d46f-207">Beispiel 10: Ausblenden des Computer namens</span><span class="sxs-lookup"><span data-stu-id="2d46f-207">Example 10: Hide the computer name</span></span>

<span data-ttu-id="2d46f-208">Dieses Beispiel zeigt die Auswirkung der Verwendung des **hidecomputername** -Parameters von `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="2d46f-208">This example shows the effect of using the **HideComputerName** parameter of `Invoke-Command`.</span></span>
<span data-ttu-id="2d46f-209">**Hidecomputername** ändert nicht das Objekt, das von diesem Cmdlet zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="2d46f-209">**HideComputerName** doesn't change the object that this cmdlet returns.</span></span> <span data-ttu-id="2d46f-210">Es ändert nur die Anzeige.</span><span class="sxs-lookup"><span data-stu-id="2d46f-210">It changes only the display.</span></span> <span data-ttu-id="2d46f-211">Sie können weiterhin die **Format** -Cmdlets verwenden, um die **pscomputername** -Eigenschaft der betroffenen Objekte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2d46f-211">You can still use the **Format** cmdlets to display the **PsComputerName** property of any of the affected objects.</span></span>

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

<span data-ttu-id="2d46f-212">Die ersten beiden Befehle verwenden `Invoke-Command` , um einen `Get-Process` Befehl für den PowerShell-Prozess auszuführen.</span><span class="sxs-lookup"><span data-stu-id="2d46f-212">The first two commands use `Invoke-Command` to run a `Get-Process` command for the PowerShell process.</span></span> <span data-ttu-id="2d46f-213">Die Ausgabe des ersten Befehls enthält die **PsComputerName** -Eigenschaft, die den Namen des Computers enthält, auf dem der Befehl ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="2d46f-213">The output of the first command includes the **PsComputerName** property, which contains the name of the computer on which the command ran.</span></span> <span data-ttu-id="2d46f-214">Die Ausgabe des zweiten Befehls, der **hidecomputername** verwendet, enthält nicht die **pscomputername** -Spalte.</span><span class="sxs-lookup"><span data-stu-id="2d46f-214">The output of the second command, which uses **HideComputerName** , doesn't include the **PsComputerName** column.</span></span>

### <span data-ttu-id="2d46f-215">Beispiel 11: Verwenden des param-Schlüssel Worts in einem Skriptblock</span><span class="sxs-lookup"><span data-stu-id="2d46f-215">Example 11: Use the Param keyword in a script block</span></span>

<span data-ttu-id="2d46f-216">Das `Param` Schlüsselwort und der Argument **List** -Parameter werden verwendet, um Variablen Werte an benannte Parameter in einem Skriptblock zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="2d46f-216">The `Param` keyword and the **ArgumentList** parameter are used to pass variable values to named parameters in a script block.</span></span> <span data-ttu-id="2d46f-217">In diesem Beispiel werden Dateinamen angezeigt, die mit dem Buchstaben beginnen `a` und die `.pdf` Erweiterung aufweisen.</span><span class="sxs-lookup"><span data-stu-id="2d46f-217">This example displays filenames that begin with the letter `a` and have the `.pdf` extension.</span></span>

<span data-ttu-id="2d46f-218">Weitere Informationen zum- `Param` Schlüsselwort finden Sie unter [about_Language_Keywords](./about/about_language_keywords.md#param).</span><span class="sxs-lookup"><span data-stu-id="2d46f-218">For more information about the `Param` keyword, see [about_Language_Keywords](./about/about_language_keywords.md#param).</span></span>

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

<span data-ttu-id="2d46f-219">`Invoke-Command` verwendet den **ScriptBlock** -Parameter, der zwei Variablen definiert, `$param1` und `$param2` .</span><span class="sxs-lookup"><span data-stu-id="2d46f-219">`Invoke-Command` uses the **ScriptBlock** parameter that defines two variables, `$param1` and `$param2`.</span></span> <span data-ttu-id="2d46f-220">`Get-ChildItem` verwendet die benannten Parameter **Name** und **include** mit den Variablennamen.</span><span class="sxs-lookup"><span data-stu-id="2d46f-220">`Get-ChildItem` uses the named parameters, **Name** and **Include** with the variable names.</span></span> <span data-ttu-id="2d46f-221">Die Argument **List** übergibt die Werte an die Variablen.</span><span class="sxs-lookup"><span data-stu-id="2d46f-221">The **ArgumentList** passes the values to the variables.</span></span>

### <span data-ttu-id="2d46f-222">Beispiel 12: Verwenden der automatischen $args automatischen Variablen in einem Skriptblock</span><span class="sxs-lookup"><span data-stu-id="2d46f-222">Example 12: Use the $args automatic variable in a script block</span></span>

<span data-ttu-id="2d46f-223">Die `$args` Automatische Variable und der Argument **List** -Parameter werden verwendet, um Array Werte an Parameter Positionen in einem Skriptblock zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="2d46f-223">The `$args` automatic variable and the **ArgumentList** parameter are used to pass array values to parameter positions in a script block.</span></span> <span data-ttu-id="2d46f-224">In diesem Beispiel wird der Verzeichnis Inhalt eines Servers der- `.txt` Dateien angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2d46f-224">This example displays a server's directory contents of `.txt` files.</span></span> <span data-ttu-id="2d46f-225">Der `Get-ChildItem` **path** -Parameter ist Position 0, und der **Filter** -Parameter ist Position.</span><span class="sxs-lookup"><span data-stu-id="2d46f-225">The `Get-ChildItem` **Path** parameter is position 0 and the **Filter** parameter is position</span></span>
1.

<span data-ttu-id="2d46f-226">Weitere Informationen zur `$args` Variablen finden Sie unter [about_Automatic_Variables](./about/about_automatic_variables.md#args)</span><span class="sxs-lookup"><span data-stu-id="2d46f-226">For more information about the `$args` variable, see [about_Automatic_Variables](./about/about_automatic_variables.md#args)</span></span>

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

<span data-ttu-id="2d46f-227">`Invoke-Command` verwendet einen **ScriptBlock** -Parameter und `Get-ChildItem` gibt `$args[0]` die `$args[1]` Array Werte und an.</span><span class="sxs-lookup"><span data-stu-id="2d46f-227">`Invoke-Command` uses a **ScriptBlock** parameter and `Get-ChildItem` specifies the `$args[0]` and `$args[1]` array values.</span></span> <span data-ttu-id="2d46f-228">Die Argument **List** übergibt die `$args` Array Werte an die `Get-ChildItem` Parameter Positionen für **path** und **Filter**.</span><span class="sxs-lookup"><span data-stu-id="2d46f-228">The **ArgumentList** passes the `$args` array values to the `Get-ChildItem` parameter positions for **Path** and **Filter**.</span></span>

### <span data-ttu-id="2d46f-229">Beispiel 13: Ausführen eines Skripts auf allen in einer Textdatei aufgeführten Computern</span><span class="sxs-lookup"><span data-stu-id="2d46f-229">Example 13: Run a script on all the computers listed in a text file</span></span>

<span data-ttu-id="2d46f-230">In diesem Beispiel wird das- `Invoke-Command` Cmdlet verwendet, um das `Sample.ps1` Skript auf allen Computern auszuführen, die in der Datei aufgelistet sind `Servers.txt` .</span><span class="sxs-lookup"><span data-stu-id="2d46f-230">This example uses the `Invoke-Command` cmdlet to run the `Sample.ps1` script on all the computers listed in the `Servers.txt` file.</span></span> <span data-ttu-id="2d46f-231">Der Befehl verwendet den **FilePath** -Parameter, um die Skriptdatei anzugeben.</span><span class="sxs-lookup"><span data-stu-id="2d46f-231">The command uses the **FilePath** parameter to specify the script file.</span></span> <span data-ttu-id="2d46f-232">Mit diesem Befehl können Sie das Skript auf den Remote Computern ausführen, selbst wenn die Skriptdatei für die Remote Computer nicht zugänglich ist.</span><span class="sxs-lookup"><span data-stu-id="2d46f-232">This command lets you run the script on the remote computers, even if the script file isn't accessible to the remote computers.</span></span>

```powershell
Invoke-Command -ComputerName (Get-Content Servers.txt) -FilePath C:\Scripts\Sample.ps1 -ArgumentList Process, Service
```

<span data-ttu-id="2d46f-233">Wenn Sie den Befehl senden, wird der Inhalt der `Sample.ps1` Datei in einen Skriptblock kopiert, und der Skriptblock wird auf jedem Remote Computer ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2d46f-233">When you submit the command, the content of the `Sample.ps1` file is copied into a script block and the script block is run on each of the remote computers.</span></span> <span data-ttu-id="2d46f-234">Dieses Verfahren entspricht der Verwendung des **ScriptBlock** -Parameters, um den Inhalt des Skripts zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="2d46f-234">This procedure is equivalent to using the **ScriptBlock** parameter to submit the contents of the script.</span></span>

### <span data-ttu-id="2d46f-235">Beispiel 14: Ausführen eines Befehls auf einem Remote Computer mithilfe eines URI</span><span class="sxs-lookup"><span data-stu-id="2d46f-235">Example 14: Run a command on a remote computer using a URI</span></span>

<span data-ttu-id="2d46f-236">In diesem Beispiel wird gezeigt, wie ein Befehl auf einem Remote Computer ausgeführt wird, der durch einen Uniform Resource Identifier (URI) identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="2d46f-236">This example shows how to run a command on a remote computer that's identified by a Uniform Resource Identifier (URI).</span></span> <span data-ttu-id="2d46f-237">Dieses spezielle Beispiel führt einen `Set-Mailbox` Befehl auf einem Exchange-Remote Server aus.</span><span class="sxs-lookup"><span data-stu-id="2d46f-237">This particular example runs a `Set-Mailbox` command on a remote Exchange server.</span></span>

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

<span data-ttu-id="2d46f-238">Die erste Zeile verwendet das `Get-Credential` Cmdlet zum Speichern der Windows Live ID-Anmelde Informationen in der `$LiveCred` Variablen.</span><span class="sxs-lookup"><span data-stu-id="2d46f-238">The first line uses the `Get-Credential` cmdlet to store Windows Live ID credentials in the `$LiveCred` variable.</span></span> <span data-ttu-id="2d46f-239">PowerShell fordert den Benutzer auf, Windows Live ID-Anmelde Informationen einzugeben.</span><span class="sxs-lookup"><span data-stu-id="2d46f-239">PowerShell prompts the user to enter Windows Live ID credentials.</span></span>

<span data-ttu-id="2d46f-240">Die- `$parameters` Variable ist eine Hash Tabelle mit den Parametern, die an das `Invoke-Command` Cmdlet übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="2d46f-240">The `$parameters` variable is a hash table containing the parameters to be passed to the `Invoke-Command` cmdlet.</span></span> <span data-ttu-id="2d46f-241">Das- `Invoke-Command` Cmdlet führt einen `Set-Mailbox` Befehl mithilfe der **Microsoft. Exchange** -Sitzungs Konfiguration aus.</span><span class="sxs-lookup"><span data-stu-id="2d46f-241">The `Invoke-Command` cmdlet runs a `Set-Mailbox` command using the **Microsoft.Exchange** session configuration.</span></span> <span data-ttu-id="2d46f-242">Der **ConnectionURI** -Parameter gibt den URL des Exchange-Serverendpunkts an.</span><span class="sxs-lookup"><span data-stu-id="2d46f-242">The **ConnectionURI** parameter specifies the URL of the Exchange server endpoint.</span></span> <span data-ttu-id="2d46f-243">Der **Credential** -Parameter gibt die in der Variablen gespeicherten Anmelde Informationen an `$LiveCred` .</span><span class="sxs-lookup"><span data-stu-id="2d46f-243">The **Credential** parameter specifies the credentials stored in the `$LiveCred` variable.</span></span> <span data-ttu-id="2d46f-244">Der **AuthenticationMechanism** -Parameter gibt die Verwendung der Standardauthentifizierung an.</span><span class="sxs-lookup"><span data-stu-id="2d46f-244">The **AuthenticationMechanism** parameter specifies the use of basic authentication.</span></span> <span data-ttu-id="2d46f-245">Der **ScriptBlock** -Parameter gibt einen Skriptblock mit dem Befehl an.</span><span class="sxs-lookup"><span data-stu-id="2d46f-245">The **ScriptBlock** parameter specifies a script block that contains the command.</span></span>

### <span data-ttu-id="2d46f-246">Beispiel 15: Verwenden einer Sitzungs Option</span><span class="sxs-lookup"><span data-stu-id="2d46f-246">Example 15: Use a session option</span></span>

<span data-ttu-id="2d46f-247">Dieses Beispiel zeigt, wie Sie einen **sessionoption** -Parameter erstellen und verwenden.</span><span class="sxs-lookup"><span data-stu-id="2d46f-247">This example shows how to create and use a **SessionOption** parameter.</span></span>

```powershell
$so = New-PSSessionOption -SkipCACheck -SkipCNCheck -SkipRevocationCheck
Invoke-Command -ComputerName server01 -UseSSL -ScriptBlock { Get-HotFix } -SessionOption $so -Credential server01\user01
```

<span data-ttu-id="2d46f-248">Mit dem- `New-PSSessionOption` Cmdlet wird ein Sitzungs Options Objekt erstellt, das bewirkt, dass die Zertifizierungsstelle, der kanonische Name und die Sperr Listen beim Auswerten der eingehenden HTTPS-Verbindung vom Remote Ende nicht überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="2d46f-248">The `New-PSSessionOption` cmdlet creates a session option object that causes the remote end not to verify the Certificate Authority, Canonical Name, and Revocation Lists while evaluating the incoming HTTPS connection.</span></span> <span data-ttu-id="2d46f-249">Das **sessionoption** -Objekt wird in der `$so` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="2d46f-249">The **SessionOption** object is saved in the `$so` variable.</span></span>

> [!NOTE]
> <span data-ttu-id="2d46f-250">Die Deaktivierung dieser Überprüfungen ist praktisch für die Problembehandlung, aber offensichtlich nicht sicher.</span><span class="sxs-lookup"><span data-stu-id="2d46f-250">Disabling these checks is convenient for troubleshooting, but obviously not secure.</span></span>

<span data-ttu-id="2d46f-251">Das- `Invoke-Command` Cmdlet führt einen `Get-HotFix` Befehl Remote aus.</span><span class="sxs-lookup"><span data-stu-id="2d46f-251">The `Invoke-Command` cmdlet runs a `Get-HotFix` command remotely.</span></span> <span data-ttu-id="2d46f-252">Der **sessionoption** -Parameter wird der- `$so` Variablen zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="2d46f-252">The **SessionOption** parameter is given the `$so` variable.</span></span>

### <span data-ttu-id="2d46f-253">Beispiel 16: Verwalten der URI-Umleitung in einem Remote Befehl</span><span class="sxs-lookup"><span data-stu-id="2d46f-253">Example 16: Manage URI redirection in a remote command</span></span>

<span data-ttu-id="2d46f-254">In diesem Beispiel wird gezeigt, wie die Parameter " **Zuweisung** " und " **sessionoption** " verwendet werden, um die URI-Umleitung in einem Remote Befehl zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="2d46f-254">This example shows how to use the **AllowRedirection** and **SessionOption** parameters to manage URI redirection in a remote command.</span></span>

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

<span data-ttu-id="2d46f-255">Mit dem- `New-PSSessionOption` Cmdlet wird ein **pssessionoption** -Objekt erstellt, das in der Variablen gespeichert wird `$max` .</span><span class="sxs-lookup"><span data-stu-id="2d46f-255">The `New-PSSessionOption` cmdlet creates a **PSSessionOption** object that is saved in the `$max` variable.</span></span> <span data-ttu-id="2d46f-256">Der Befehl verwendet den **MaximumRedirection** -Parameter zum Festlegen der **MaximumConnectionRedirectionCount** -Eigenschaft des **PSSessionOption** -Objekts auf 1.</span><span class="sxs-lookup"><span data-stu-id="2d46f-256">The command uses the **MaximumRedirection** parameter to set the **MaximumConnectionRedirectionCount** property of the **PSSessionOption** object to 1.</span></span>

<span data-ttu-id="2d46f-257">Das- `Invoke-Command` Cmdlet führt einen `Get-Mailbox` Befehl auf einem Microsoft Exchange-Remote Server aus.</span><span class="sxs-lookup"><span data-stu-id="2d46f-257">The `Invoke-Command` cmdlet runs a `Get-Mailbox` command on a remote Microsoft Exchange Server.</span></span> <span data-ttu-id="2d46f-258">Der **Zustellungs Direction** -Parameter stellt explizite Berechtigungen zum Umleiten der Verbindung zu einem alternativen Endpunkt bereit.</span><span class="sxs-lookup"><span data-stu-id="2d46f-258">The **AllowRedirection** parameter provides explicit permission to redirect the connection to an alternate endpoint.</span></span> <span data-ttu-id="2d46f-259">Der **sessionoption** -Parameter verwendet das Sitzungs Objekt, das in der Variablen gespeichert ist `$max` .</span><span class="sxs-lookup"><span data-stu-id="2d46f-259">The **SessionOption** parameter uses the session object stored in the `$max` variable.</span></span>

<span data-ttu-id="2d46f-260">Wenn also der von **ConnectionUri** angegebene Remote Computer eine Umleitungs Meldung zurückgibt, leitet PowerShell die Verbindung um, aber wenn das neue Ziel eine andere Weiterleitungs Nachricht zurückgibt, wird der Umleitungs Zählerwert 1 überschritten, und es wird `Invoke-Command` ein Fehler ohne Abbruch zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2d46f-260">As a result, if the remote computer specified by **ConnectionURI** returns a redirection message, PowerShell redirects the connection, but if the new destination returns another redirection message, the redirection count value of 1 is exceeded, and `Invoke-Command` returns a non-terminating error.</span></span>

### <span data-ttu-id="2d46f-261">Beispiel 17: Zugreifen auf eine Netzwerkfreigabe in einer Remote Sitzung</span><span class="sxs-lookup"><span data-stu-id="2d46f-261">Example 17: Access a network share in a remote session</span></span>

<span data-ttu-id="2d46f-262">Dieses Beispiel zeigt, wie Sie über eine Remote Sitzung auf eine Netzwerkfreigabe zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="2d46f-262">This example shows how to access a network share from a remote session.</span></span> <span data-ttu-id="2d46f-263">Zum veranschaulichen des Beispiels werden drei Computer verwendet.</span><span class="sxs-lookup"><span data-stu-id="2d46f-263">Three computers are used to demonstrate the example.</span></span> <span data-ttu-id="2d46f-264">Server01 ist der lokale Computer, Server02 ist der Remote Computer, und Net03 enthält die Netzwerkfreigabe.</span><span class="sxs-lookup"><span data-stu-id="2d46f-264">Server01 is the local computer, Server02 is the remote computer, and Net03 contains the network share.</span></span> <span data-ttu-id="2d46f-265">Server01 stellt eine Verbindung mit Server02 her, und Server02 führt dann einen zweiten Hop zu Net03 aus, um auf die Netzwerkfreigabe zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="2d46f-265">Server01 connects to Server02, and then Server02 does a second hop to Net03 to access the network share.</span></span> <span data-ttu-id="2d46f-266">Weitere Informationen zur Unterstützung von Hops durch PowerShell-Remoting zwischen Computern finden Sie unter Ausführen [des zweiten Hops in PowerShell-Remoting](/powershell/scripting/learn/remoting/ps-remoting-second-hop).</span><span class="sxs-lookup"><span data-stu-id="2d46f-266">For more information about how PowerShell Remoting supports hops between computers, see [Making the second hop in PowerShell Remoting](/powershell/scripting/learn/remoting/ps-remoting-second-hop).</span></span>

<span data-ttu-id="2d46f-267">In den Client Einstellungen auf dem lokalen Computer und in den Dienst Einstellungen auf dem Remote Computer ist die erforderliche Credential Security Support Provider (kredssp)-Delegierung aktiviert.</span><span class="sxs-lookup"><span data-stu-id="2d46f-267">The required Credential Security Support Provider (CredSSP) delegation is enabled in the client settings on the local computer, and in the service settings on the remote computer.</span></span> <span data-ttu-id="2d46f-268">Um die Befehle in diesem Beispiel auszuführen, müssen Sie Mitglied der Gruppe " **Administratoren** " auf dem lokalen Computer und dem Remote Computer sein.</span><span class="sxs-lookup"><span data-stu-id="2d46f-268">To run the commands in this example, you must be a member of the **Administrators** group on the local computer and the remote computer.</span></span>

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

<span data-ttu-id="2d46f-269">Mit dem- `Enable-WSManCredSSP` Cmdlet kann die "Server01"-Delegierung vom lokalen Computer auf den Server02-Remote Computer aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="2d46f-269">The `Enable-WSManCredSSP` cmdlet enables CredSSP delegation from the Server01 local computer to the Server02 remote computer.</span></span> <span data-ttu-id="2d46f-270">Der **Role** -Parameter gibt den **Client** an, um die Einstellung für den Client auf dem lokalen Computer zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="2d46f-270">The **Role** parameter specifies **Client** to configure the CredSSP client setting on the local computer.</span></span>

<span data-ttu-id="2d46f-271">`New-PSSession` erstellt ein **PSSession** -Objekt für Server02 und speichert das-Objekt in der `$s` Variablen.</span><span class="sxs-lookup"><span data-stu-id="2d46f-271">`New-PSSession` creates a **PSSession** object for Server02 and stores the object in the `$s` variable.</span></span>

<span data-ttu-id="2d46f-272">Das `Invoke-Command` Cmdlet verwendet die- `$s` Variable, um eine Verbindung mit dem Remote Computer Server02 herzustellen.</span><span class="sxs-lookup"><span data-stu-id="2d46f-272">The `Invoke-Command` cmdlet uses the `$s` variable to connect to the remote computer, Server02.</span></span> <span data-ttu-id="2d46f-273">Der **ScriptBlock** -Parameter wird `Enable-WSManCredSSP` auf dem Remote Computer ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2d46f-273">The **ScriptBlock** parameter runs `Enable-WSManCredSSP` on the remote computer.</span></span> <span data-ttu-id="2d46f-274">Der **Role** -Parameter gibt den **Server** an, um die Einstellungen für den auf dem Remote Computer festgelegten Einstellungen für den ""</span><span class="sxs-lookup"><span data-stu-id="2d46f-274">The **Role** parameter specifies **Server** to configure the CredSSP server setting on the remote computer.</span></span>

<span data-ttu-id="2d46f-275">Die- `$parameters` Variable enthält die Parameterwerte zum Herstellen einer Verbindung mit der Netzwerkfreigabe.</span><span class="sxs-lookup"><span data-stu-id="2d46f-275">The `$parameters` variable contains the parameter values to connect to the network share.</span></span> <span data-ttu-id="2d46f-276">Das- `Invoke-Command` Cmdlet führt einen `Get-Item` Befehl in der Sitzung in aus `$s` .</span><span class="sxs-lookup"><span data-stu-id="2d46f-276">The `Invoke-Command` cmdlet runs a `Get-Item` command in the session in `$s`.</span></span> <span data-ttu-id="2d46f-277">Mit diesem Befehl wird ein Skript aus der `\\Net03\Scripts` Netzwerkfreigabe abgerufen.</span><span class="sxs-lookup"><span data-stu-id="2d46f-277">This command gets a script from the `\\Net03\Scripts` network share.</span></span> <span data-ttu-id="2d46f-278">Der Befehl verwendet den **Authentication** -Parameter mit dem Wert " **kredssp** " und dem **Credential** -Parameter mit dem Wert " **Domain01\Admin01** ".</span><span class="sxs-lookup"><span data-stu-id="2d46f-278">The command uses the **Authentication** parameter with a value of **CredSSP** and the **Credential** parameter with a value of **Domain01\Admin01**.</span></span>

### <span data-ttu-id="2d46f-279">Beispiel 18: Starten von Skripts auf vielen Remote Computern</span><span class="sxs-lookup"><span data-stu-id="2d46f-279">Example 18: Start scripts on many remote computers</span></span>

<span data-ttu-id="2d46f-280">In diesem Beispiel wird ein Skript auf mehr als 100 Computern ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2d46f-280">This example runs a script on more than a hundred computers.</span></span> <span data-ttu-id="2d46f-281">Zur Minimierung der Auswirkungen auf dem lokalen Computer wird eine Verbindung mit jedem Computer hergestellt, das Skript gestartet und die Verbindung dann von jedem Computer getrennt.</span><span class="sxs-lookup"><span data-stu-id="2d46f-281">To minimize the impact on the local computer, it connects to each computer, starts the script, and then disconnects from each computer.</span></span>
<span data-ttu-id="2d46f-282">Das Skript wird weiterhin in den getrennten Sitzungen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2d46f-282">The script continues to run in the disconnected sessions.</span></span>

```powershell
$parameters = @{
  ComputerName = (Get-Content -Path C:\Test\Servers.txt)
  InDisconnectedSession = $true
  FilePath = "\\Scripts\Public\ConfigInventory.ps1"
  SessionOption = @{OutputBufferingMode="Drop";IdleTimeout=43200000}
}
Invoke-Command @parameters
```

<span data-ttu-id="2d46f-283">Der Befehl verwendet `Invoke-Command` , um das Skript auszuführen.</span><span class="sxs-lookup"><span data-stu-id="2d46f-283">The command uses `Invoke-Command` to run the script.</span></span> <span data-ttu-id="2d46f-284">Der Wert des **Computername** -Parameters ist ein `Get-Content` Befehl, der die Namen der Remote Computer aus einer Textdatei abruft.</span><span class="sxs-lookup"><span data-stu-id="2d46f-284">The value of the **ComputerName** parameter is a `Get-Content` command that gets the names of the remote computers from a text file.</span></span> <span data-ttu-id="2d46f-285">Der **InDisconnectedSession** -Parameter trennt Sitzungen, sobald der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2d46f-285">The **InDisconnectedSession** parameter disconnects the sessions as soon as it starts the command.</span></span> <span data-ttu-id="2d46f-286">Der Wert des **FilePath** -Parameters ist das Skript, das `Invoke-Command` auf jedem Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2d46f-286">The value of the **FilePath** parameter is the script that `Invoke-Command` runs on each computer.</span></span>

<span data-ttu-id="2d46f-287">Der Wert von **sessionoption** ist eine Hash Tabelle.</span><span class="sxs-lookup"><span data-stu-id="2d46f-287">The value of **SessionOption** is a hash table.</span></span> <span data-ttu-id="2d46f-288">Der Wert **outputbufferingmode** ist auf **Drop** festgelegt, und der **IdleTimeout** -Wert wird auf **43,2 Millionen** Millisekunden (12 Stunden) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="2d46f-288">The **OutputBufferingMode** value is set to **Drop** and the **IdleTimeout** value is set to **43200000** milliseconds (12 hours).</span></span>

<span data-ttu-id="2d46f-289">Verwenden Sie das-Cmdlet, um die Ergebnisse von Befehlen und Skripts, die in getrennten Sitzungen ausgeführt werden, zu erhalten `Receive-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="2d46f-289">To get the results of commands and scripts that run in disconnected sessions, use the `Receive-PSSession` cmdlet.</span></span>

## <span data-ttu-id="2d46f-290">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2d46f-290">PARAMETERS</span></span>

### <span data-ttu-id="2d46f-291">-Zuweisung Richtung</span><span class="sxs-lookup"><span data-stu-id="2d46f-291">-AllowRedirection</span></span>

<span data-ttu-id="2d46f-292">Ermöglicht die Umleitung dieser Verbindung an einen alternativen URI (Uniform Resource Identifier).</span><span class="sxs-lookup"><span data-stu-id="2d46f-292">Allows redirection of this connection to an alternate Uniform Resource Identifier (URI).</span></span>

<span data-ttu-id="2d46f-293">Bei Verwendung des **ConnectionURI** -Parameters kann das Remoteziel eine Anweisung zum Umleiten an einen anderen URI zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="2d46f-293">When you use the **ConnectionURI** parameter, the remote destination can return an instruction to redirect to a different URI.</span></span> <span data-ttu-id="2d46f-294">Standardmäßig werden Verbindungen von PowerShell nicht umgeleitet, aber Sie können diesen Parameter verwenden, um die Umleitung der Verbindung zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="2d46f-294">By default, PowerShell doesn't redirect connections, but you can use this parameter to allow it to redirect the connection.</span></span>

<span data-ttu-id="2d46f-295">Sie können auch einschränken, wie oft die Verbindung umgeleitet wird, indem Sie den **MaximumConnectionRedirectionCount** -Optionswert der Sitzung ändern.</span><span class="sxs-lookup"><span data-stu-id="2d46f-295">You can also limit the number of times the connection is redirected by changing the **MaximumConnectionRedirectionCount** session option value.</span></span> <span data-ttu-id="2d46f-296">Verwenden Sie den **maximumredirect** -Parameter des `New-PSSessionOption` Cmdlets, oder legen Sie die **maximumconnectionredirectioncount** -Eigenschaft der `$PSSessionOption` Preference-Variablen fest.</span><span class="sxs-lookup"><span data-stu-id="2d46f-296">Use the **MaximumRedirection** parameter of the `New-PSSessionOption` cmdlet or set the **MaximumConnectionRedirectionCount** property of the `$PSSessionOption` preference variable.</span></span> <span data-ttu-id="2d46f-297">Der Standardwert ist 5.</span><span class="sxs-lookup"><span data-stu-id="2d46f-297">The default value is 5.</span></span>

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

### <span data-ttu-id="2d46f-298">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="2d46f-298">-ApplicationName</span></span>

<span data-ttu-id="2d46f-299">Gibt das Anwendungsnamenssegment des Verbindungs-URI an.</span><span class="sxs-lookup"><span data-stu-id="2d46f-299">Specifies the application name segment of the connection URI.</span></span> <span data-ttu-id="2d46f-300">Verwenden Sie diesen Parameter, um den Anwendungsnamen anzugeben, wenn Sie nicht den **ConnectionUri** -Parameter im Befehl verwenden.</span><span class="sxs-lookup"><span data-stu-id="2d46f-300">Use this parameter to specify the application name when you aren't using the **ConnectionURI** parameter in the command.</span></span>

<span data-ttu-id="2d46f-301">Der Standardwert ist der Wert der Einstellungs `$PSSessionApplicationName` Variablen auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="2d46f-301">The default value is the value of the `$PSSessionApplicationName` preference variable on the local computer.</span></span> <span data-ttu-id="2d46f-302">Wenn diese Einstellungs Variable nicht definiert ist, lautet der Standardwert "wsman".</span><span class="sxs-lookup"><span data-stu-id="2d46f-302">If this preference variable isn't defined, the default value is WSMAN.</span></span> <span data-ttu-id="2d46f-303">Dieser Wert ist für die meisten Verwendungsarten geeignet.</span><span class="sxs-lookup"><span data-stu-id="2d46f-303">This value is appropriate for most uses.</span></span> <span data-ttu-id="2d46f-304">Weitere Informationen finden Sie unter [about_Preference_Variables](./About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="2d46f-304">For more information, see [about_Preference_Variables](./About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="2d46f-305">Der WinRM-Dienst wählt mit dem Anwendungsnamen einen Listener für die Verbindungsanforderung aus.</span><span class="sxs-lookup"><span data-stu-id="2d46f-305">The WinRM service uses the application name to select a listener to service the connection request.</span></span>
<span data-ttu-id="2d46f-306">Der Wert dieses Parameters sollte mit dem Wert der **URLPrefix** -Eigenschaft eines Listeners auf dem Remotecomputer übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2d46f-306">The value of this parameter should match the value of the **URLPrefix** property of a listener on the remote computer.</span></span>

```yaml
Type: System.String
Parameter Sets: FilePathComputerName, ComputerName
Aliases:

Required: False
Position: Named
Default value: $PSSessionApplicationName if set on the local computer, otherwise WSMAN
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="2d46f-307">-Argumentlist</span><span class="sxs-lookup"><span data-stu-id="2d46f-307">-ArgumentList</span></span>

<span data-ttu-id="2d46f-308">Stellt die Werte von lokalen Variablen im Befehl bereit.</span><span class="sxs-lookup"><span data-stu-id="2d46f-308">Supplies the values of local variables in the command.</span></span> <span data-ttu-id="2d46f-309">Die Variablen im Befehl werden durch diese Werte ersetzt, bevor der Befehl auf dem Remotecomputer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2d46f-309">The variables in the command are replaced by these values before the command is run on the remote computer.</span></span> <span data-ttu-id="2d46f-310">Geben Sie die Werte in eine durch Kommas getrennte Liste ein.</span><span class="sxs-lookup"><span data-stu-id="2d46f-310">Enter the values in a comma-separated list.</span></span> <span data-ttu-id="2d46f-311">Werte werden Variablen in der Reihenfolge zugeordnet, in der Sie aufgelistet sind.</span><span class="sxs-lookup"><span data-stu-id="2d46f-311">Values are associated with variables in the order that they're listed.</span></span> <span data-ttu-id="2d46f-312">Der Alias für Argument **List** lautet "args".</span><span class="sxs-lookup"><span data-stu-id="2d46f-312">The alias for **ArgumentList** is Args.</span></span>

<span data-ttu-id="2d46f-313">Die Werte im Argument **List** -Parameter können tatsächliche Werte sein, z. b. 1024, oder es kann sich um Verweise auf lokale Variablen handeln, z `$max` . b..</span><span class="sxs-lookup"><span data-stu-id="2d46f-313">The values in the **ArgumentList** parameter can be actual values, such as 1024, or they can be references to local variables, such as `$max`.</span></span>

<span data-ttu-id="2d46f-314">Um lokale Variablen in einem Befehl zu verwenden, verwenden Sie das folgende Befehlsformat:</span><span class="sxs-lookup"><span data-stu-id="2d46f-314">To use local variables in a command, use the following command format:</span></span>

<span data-ttu-id="2d46f-315">`{param($<name1>[, $<name2>]...) <command-with-local-variables>} -ArgumentList <value>` - oder - `<local-variable>`</span><span class="sxs-lookup"><span data-stu-id="2d46f-315">`{param($<name1>[, $<name2>]...) <command-with-local-variables>} -ArgumentList <value>` -or- `<local-variable>`</span></span>

<span data-ttu-id="2d46f-316">Das Schlüsselwort " **param** " listet die lokalen Variablen auf, die im Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2d46f-316">The **param** keyword lists the local variables that are used in the command.</span></span> <span data-ttu-id="2d46f-317">**Argumentlist** gibt die Werte der Variablen in der Reihenfolge an, in der Sie aufgelistet sind.</span><span class="sxs-lookup"><span data-stu-id="2d46f-317">**ArgumentList** supplies the values of the variables, in the order that they're listed.</span></span> <span data-ttu-id="2d46f-318">Weitere Informationen zum Verhalten von **argumentlist** finden Sie unter [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span><span class="sxs-lookup"><span data-stu-id="2d46f-318">For more information about the behavior of **ArgumentList** , see [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span></span>

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

### <span data-ttu-id="2d46f-319">-AsJob</span><span class="sxs-lookup"><span data-stu-id="2d46f-319">-AsJob</span></span>

<span data-ttu-id="2d46f-320">Gibt an, dass dieses Cmdlet den Befehl als Hintergrund Auftrag auf einem Remote Computer ausführt.</span><span class="sxs-lookup"><span data-stu-id="2d46f-320">Indicates that this cmdlet runs the command as a background job on a remote computer.</span></span> <span data-ttu-id="2d46f-321">Verwenden Sie diesen Parameter, um Befehle auszuführen, deren Ausführung viel Zeit in Anspruch nimmt.</span><span class="sxs-lookup"><span data-stu-id="2d46f-321">Use this parameter to run commands that take an extensive time to finish.</span></span>

<span data-ttu-id="2d46f-322">Wenn Sie den **AsJob** -Parameter verwenden, gibt der Befehl ein Objekt zurück, das den Auftrag darstellt, und zeigt dann die Eingabeaufforderung an.</span><span class="sxs-lookup"><span data-stu-id="2d46f-322">When you use the **AsJob** parameter, the command returns an object that represents the job, and then displays the command prompt.</span></span> <span data-ttu-id="2d46f-323">Sie können die Sitzung weiterhin verwenden, während der Auftrag abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="2d46f-323">You can continue to work in the session while the job finishes.</span></span> <span data-ttu-id="2d46f-324">Verwenden Sie die-Cmdlets, um den Auftrag zu verwalten `*-Job` .</span><span class="sxs-lookup"><span data-stu-id="2d46f-324">To manage the job, use the `*-Job` cmdlets.</span></span> <span data-ttu-id="2d46f-325">Um die Auftragsergebnisse abzurufen, verwenden Sie das Cmdlet `Receive-Job`.</span><span class="sxs-lookup"><span data-stu-id="2d46f-325">To get the job results, use the `Receive-Job` cmdlet.</span></span>

<span data-ttu-id="2d46f-326">Der **AsJob** -Parameter ähnelt der Verwendung des `Invoke-Command` Cmdlets zum `Start-Job` Remote Ausführen eines Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="2d46f-326">The **AsJob** parameter resembles using the `Invoke-Command` cmdlet to run a `Start-Job` cmdlet remotely.</span></span> <span data-ttu-id="2d46f-327">Bei **AsJob** wird der Auftrag jedoch auf dem lokalen Computer erstellt, auch wenn der Auftrag auf einem Remote Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2d46f-327">However, with **AsJob** , the job is created on the local computer, even though the job runs on a remote computer.</span></span> <span data-ttu-id="2d46f-328">Die Ergebnisse des Remote Auftrags werden automatisch an den lokalen Computer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2d46f-328">The results of the remote job are automatically returned to the local computer.</span></span>

<span data-ttu-id="2d46f-329">Weitere Informationen zu PowerShell-Hintergrund Aufträgen finden Sie unter [about_Jobs](About/about_Jobs.md) und [about_Remote_Jobs](About/about_Remote_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="2d46f-329">For more information about PowerShell background jobs, see [about_Jobs](About/about_Jobs.md) and [about_Remote_Jobs](About/about_Remote_Jobs.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Session, FilePathRunspace, FilePathComputerName, ComputerName, Uri, FilePathUri, VMId, VMName, FilePathVMId, FilePathVMName, ContainerId, FilePathContainerId
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2d46f-330">-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="2d46f-330">-Authentication</span></span>

<span data-ttu-id="2d46f-331">Gibt den Mechanismus an, der zum Authentifizieren der Anmelde Informationen des Benutzers verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2d46f-331">Specifies the mechanism that's used to authenticate the user's credentials.</span></span> <span data-ttu-id="2d46f-332">Die kredssp-Authentifizierung ist nur in Windows Vista, Windows Server 2008 und höheren Versionen des Windows-Betriebssystems verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2d46f-332">CredSSP authentication is available only in Windows Vista, Windows Server 2008, and later versions of the Windows operating system.</span></span>

<span data-ttu-id="2d46f-333">Die zulässigen Werte für diesen Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="2d46f-333">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="2d46f-334">Standard</span><span class="sxs-lookup"><span data-stu-id="2d46f-334">Default</span></span>
- <span data-ttu-id="2d46f-335">Basic</span><span class="sxs-lookup"><span data-stu-id="2d46f-335">Basic</span></span>
- <span data-ttu-id="2d46f-336">CredSSP</span><span class="sxs-lookup"><span data-stu-id="2d46f-336">Credssp</span></span>
- <span data-ttu-id="2d46f-337">Digest</span><span class="sxs-lookup"><span data-stu-id="2d46f-337">Digest</span></span>
- <span data-ttu-id="2d46f-338">Kerberos</span><span class="sxs-lookup"><span data-stu-id="2d46f-338">Kerberos</span></span>
- <span data-ttu-id="2d46f-339">Aushandeln</span><span class="sxs-lookup"><span data-stu-id="2d46f-339">Negotiate</span></span>
- <span data-ttu-id="2d46f-340">NegotiateWithImplicitCredential</span><span class="sxs-lookup"><span data-stu-id="2d46f-340">NegotiateWithImplicitCredential</span></span>

<span data-ttu-id="2d46f-341">Der Standardwert ist Default.</span><span class="sxs-lookup"><span data-stu-id="2d46f-341">The default value is Default.</span></span>

<span data-ttu-id="2d46f-342">Weitere Informationen zu den Werten dieses Parameters finden Sie unter [authenticationmechanism-Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span><span class="sxs-lookup"><span data-stu-id="2d46f-342">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!CAUTION]
> <span data-ttu-id="2d46f-343">Die CredSSP (Credential Security Support Provider)-Authentifizierung, bei der die Anmeldeinformationen des Benutzers zur Authentifizierung an einen Remotecomputer übergeben werden, ist für Befehle konzipiert, die die Authentifizierung auf mehr als einer Ressource erfordern, z. B. beim Zugriff auf eine Remotenetzwerkfreigabe.</span><span class="sxs-lookup"><span data-stu-id="2d46f-343">Credential Security Support Provider (CredSSP) authentication, in which the user's credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="2d46f-344">Dieser Mechanismus erhöht das Sicherheitsrisiko des Remotevorgangs.</span><span class="sxs-lookup"><span data-stu-id="2d46f-344">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="2d46f-345">Wenn die Sicherheit des Remotecomputers gefährdet ist, können die an ihn übergebenen Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2d46f-345">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span> <span data-ttu-id="2d46f-346">Weitere Informationen finden Sie [unter Credential Security Support Provider](/windows/win32/secauthn/credential-security-support-provider).</span><span class="sxs-lookup"><span data-stu-id="2d46f-346">For more information, see [Credential Security Support Provider](/windows/win32/secauthn/credential-security-support-provider).</span></span>

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: FilePathComputerName, ComputerName, Uri, FilePathUri
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2d46f-347">-Certifiupethumschlag-Print</span><span class="sxs-lookup"><span data-stu-id="2d46f-347">-CertificateThumbprint</span></span>

<span data-ttu-id="2d46f-348">Gibt das digitale Zertifikat für öffentliche Schlüssel (X.509) eines Benutzerkontos mit der Berechtigung zum Herstellen einer Verbindung mit der getrennten Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="2d46f-348">Specifies the digital public key certificate (X509) of a user account that has permission to connect to the disconnected session.</span></span> <span data-ttu-id="2d46f-349">Geben Sie den Zertifikatfingerabdruck des Zertifikats ein.</span><span class="sxs-lookup"><span data-stu-id="2d46f-349">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="2d46f-350">Zertifikate werden bei der clientzertifikatbasierten Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="2d46f-350">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="2d46f-351">Sie können nur lokalen Benutzerkonten zugeordnet werden und funktionieren nicht mit Domänen Konten.</span><span class="sxs-lookup"><span data-stu-id="2d46f-351">They can be mapped only to local user accounts and they don't work with domain accounts.</span></span>

<span data-ttu-id="2d46f-352">Um einen Zertifikat Fingerabdruck abzurufen, verwenden Sie einen- `Get-Item` `Get-ChildItem` Befehl oder den-Befehl im PowerShell-Laufwerk "CERT:".</span><span class="sxs-lookup"><span data-stu-id="2d46f-352">To get a certificate thumbprint, use a `Get-Item` or `Get-ChildItem` command in the PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="2d46f-353">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="2d46f-353">-ComputerName</span></span>

<span data-ttu-id="2d46f-354">Gibt die Computer an, auf denen der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2d46f-354">Specifies the computers on which the command runs.</span></span> <span data-ttu-id="2d46f-355">Die Standardeinstellung ist der lokale Computer.</span><span class="sxs-lookup"><span data-stu-id="2d46f-355">The default is the local computer.</span></span>

<span data-ttu-id="2d46f-356">Wenn Sie den **Computername** -Parameter verwenden, erstellt PowerShell eine temporäre Verbindung, die nur zum Ausführen des angegebenen Befehls verwendet und dann geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="2d46f-356">When you use the **ComputerName** parameter, PowerShell creates a temporary connection that's used only to run the specified command and is then closed.</span></span> <span data-ttu-id="2d46f-357">Wenn Sie eine permanente Verbindung benötigen, verwenden Sie den **Session** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="2d46f-357">If you need a persistent connection, use the **Session** parameter.</span></span>

<span data-ttu-id="2d46f-358">Geben Sie den NetBIOS-Namen, die IP-Adresse oder den vollqualifizierten Domänennamen eines Computers oder mehrerer Computer in einer durch Trennzeichen getrennten Liste ein.</span><span class="sxs-lookup"><span data-stu-id="2d46f-358">Type the NETBIOS name, IP address, or fully qualified domain name of one or more computers in a comma-separated list.</span></span> <span data-ttu-id="2d46f-359">Um den lokalen Computer anzugeben, geben Sie den Computernamen, "localhost" oder einen Punkt ( `.` ) ein.</span><span class="sxs-lookup"><span data-stu-id="2d46f-359">To specify the local computer, type the computer name, localhost, or a dot (`.`).</span></span>

<span data-ttu-id="2d46f-360">Um eine IP-Adresse im Wert von **Computername** zu verwenden, muss der Befehl den **Credential** -Parameter enthalten.</span><span class="sxs-lookup"><span data-stu-id="2d46f-360">To use an IP address in the value of **ComputerName** , the command must include the **Credential** parameter.</span></span> <span data-ttu-id="2d46f-361">Der Computer muss für den HTTPS-Transport konfiguriert sein, oder die IP-Adresse des Remote Computers muss in der **WinRM-** Liste des lokalen Computers enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="2d46f-361">The computer must be configured for the HTTPS transport or the IP address of the remote computer must be included in the local computer's WinRM **TrustedHosts** list.</span></span> <span data-ttu-id="2d46f-362">Anweisungen zum Hinzufügen eines Computer namens zur Liste " **Treuhänder Hosts** " finden Sie unter [Hinzufügen eines Computers zur Liste "vertrauenswürdiger Host](./about/about_remote_troubleshooting.md#how-to-add-a-computer-to-the-trusted-hosts-list)".</span><span class="sxs-lookup"><span data-stu-id="2d46f-362">For instructions to add a computer name to the **TrustedHosts** list, see [How to Add a Computer to the Trusted Host List](./about/about_remote_troubleshooting.md#how-to-add-a-computer-to-the-trusted-hosts-list).</span></span>

<span data-ttu-id="2d46f-363">Unter Windows Vista und höheren Versionen des Windows-Betriebssystems müssen Sie PowerShell mit der Option **als Administrator ausführen** ausführen, um den lokalen Computer in den Wert von **Computername** einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="2d46f-363">On Windows Vista and later versions of the Windows operating system, to include the local computer in the value of **ComputerName** , you must run PowerShell using the **Run as administrator** option.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FilePathComputerName, ComputerName
Aliases: Cn

Required: False
Position: 0
Default value: Local computer
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2d46f-364">-ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="2d46f-364">-ConfigurationName</span></span>

<span data-ttu-id="2d46f-365">Gibt die Sitzungs Konfiguration an, die für die neue **PSSession** verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2d46f-365">Specifies the session configuration that is used for the new **PSSession**.</span></span>

<span data-ttu-id="2d46f-366">Geben Sie einen Konfigurationsnamen oder den vollqualifizierten Ressourcen-URI für eine Sitzungskonfiguration ein.</span><span class="sxs-lookup"><span data-stu-id="2d46f-366">Enter a configuration name or the fully qualified resource URI for a session configuration.</span></span> <span data-ttu-id="2d46f-367">Wenn Sie nur den Konfigurations Namen angeben, wird der folgende Schema-URI vorangestellt: `http://schemas.microsoft.com/PowerShell` .</span><span class="sxs-lookup"><span data-stu-id="2d46f-367">If you specify only the configuration name, the following schema URI is prepended: `http://schemas.microsoft.com/PowerShell`.</span></span>

<span data-ttu-id="2d46f-368">Die Sitzungskonfiguration für eine Sitzung befindet sich auf dem Remotecomputer.</span><span class="sxs-lookup"><span data-stu-id="2d46f-368">The session configuration for a session is located on the remote computer.</span></span> <span data-ttu-id="2d46f-369">Wenn die angegebene Sitzungs Konfiguration auf dem Remote Computer nicht vorhanden ist, schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="2d46f-369">If the specified session configuration doesn't exist on the remote computer, the command fails.</span></span>

<span data-ttu-id="2d46f-370">Der Standardwert ist der Wert der Einstellungs `$PSSessionConfigurationName` Variablen auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="2d46f-370">The default value is the value of the `$PSSessionConfigurationName` preference variable on the local computer.</span></span> <span data-ttu-id="2d46f-371">Wenn diese Einstellungs Variable nicht festgelegt ist, lautet der Standardwert **Microsoft. PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="2d46f-371">If this preference variable isn't set, the default is **Microsoft.PowerShell**.</span></span> <span data-ttu-id="2d46f-372">Weitere Informationen finden Sie unter [about_Preference_Variables](about/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="2d46f-372">For more information, see [about_Preference_Variables](about/about_Preference_Variables.md).</span></span>

```yaml
Type: System.String
Parameter Sets: FilePathComputerName, ComputerName, Uri, FilePathUri, VMId, VMName, FilePathVMId, FilePathVMName, ContainerId, FilePathContainerId
Aliases:

Required: False
Position: Named
Default value: $PSSessionConfigurationName if set on the local computer, otherwise Microsoft.PowerShell
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="2d46f-373">-ConnectionUri</span><span class="sxs-lookup"><span data-stu-id="2d46f-373">-ConnectionUri</span></span>

<span data-ttu-id="2d46f-374">Gibt einen URI (Uniform Resource Identifier) an, der den Verbindungsendpunkt für die Sitzung definiert.</span><span class="sxs-lookup"><span data-stu-id="2d46f-374">Specifies a Uniform Resource Identifier (URI) that defines the connection endpoint of the session.</span></span>
<span data-ttu-id="2d46f-375">Der URI muss vollqualifiziert sein.</span><span class="sxs-lookup"><span data-stu-id="2d46f-375">The URI must be fully qualified.</span></span>

<span data-ttu-id="2d46f-376">Das Format dieser Zeichenfolge lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="2d46f-376">The format of this string is as follows:</span></span>

`<Transport>://<ComputerName>:<Port>/<ApplicationName>`

<span data-ttu-id="2d46f-377">Der Standardwert lautet:</span><span class="sxs-lookup"><span data-stu-id="2d46f-377">The default value is as follows:</span></span>

`http://localhost:5985/WSMAN`

<span data-ttu-id="2d46f-378">Wenn Sie keinen Verbindungs-URI angeben, können Sie die Parameter " **US** " und " **Port** " verwenden, um die Verbindungs-URI-Werte anzugeben.</span><span class="sxs-lookup"><span data-stu-id="2d46f-378">If you don't specify a connection URI, you can use the **UseSSL** and **Port** parameters to specify the connection URI values.</span></span>

<span data-ttu-id="2d46f-379">Gültige Werte für das **Transport** -Segment des URI sind „HTTP“ und „HTTPS“.</span><span class="sxs-lookup"><span data-stu-id="2d46f-379">Valid values for the **Transport** segment of the URI are HTTP and HTTPS.</span></span> <span data-ttu-id="2d46f-380">Wenn Sie einen Verbindungs-URI mit einem Transport Segment angeben, aber keinen Port angeben, wird die Sitzung mit den Standardports erstellt: 80 für http und 443 für HTTPS.</span><span class="sxs-lookup"><span data-stu-id="2d46f-380">If you specify a connection URI with a Transport segment, but don't specify a port, the session is created with the standards ports: 80 for HTTP and 443 for HTTPS.</span></span> <span data-ttu-id="2d46f-381">Wenn Sie die Standardports für PowerShell-Remoting verwenden möchten, geben Sie Port 5985 für http oder 5986 für HTTPS an.</span><span class="sxs-lookup"><span data-stu-id="2d46f-381">To use the default ports for PowerShell remoting, specify port 5985 for HTTP or 5986 for HTTPS.</span></span>

<span data-ttu-id="2d46f-382">Wenn der Zielcomputer die Verbindung an einen anderen URI umleitet, verhindert PowerShell die Umleitung, es sei denn, Sie verwenden den Parameter " **Zuweisung** " im Befehl.</span><span class="sxs-lookup"><span data-stu-id="2d46f-382">If the destination computer redirects the connection to a different URI, PowerShell prevents the redirection unless you use the **AllowRedirection** parameter in the command.</span></span>

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

### <span data-ttu-id="2d46f-383">-Containerid</span><span class="sxs-lookup"><span data-stu-id="2d46f-383">-ContainerId</span></span>

<span data-ttu-id="2d46f-384">Gibt ein Array von Container-IDs an.</span><span class="sxs-lookup"><span data-stu-id="2d46f-384">Specifies an array of container IDs.</span></span>

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

### <span data-ttu-id="2d46f-385">-Credential</span><span class="sxs-lookup"><span data-stu-id="2d46f-385">-Credential</span></span>

<span data-ttu-id="2d46f-386">Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="2d46f-386">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="2d46f-387">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="2d46f-387">The default is the current user.</span></span>

<span data-ttu-id="2d46f-388">Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01** , oder geben Sie ein **PSCredential** -Objekt ein, das vom `Get-Credential` Cmdlet generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="2d46f-388">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="2d46f-389">Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe des Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="2d46f-389">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="2d46f-390">Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.</span><span class="sxs-lookup"><span data-stu-id="2d46f-390">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="2d46f-391">Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="2d46f-391">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="2d46f-392">-Enablenetworkaccess</span><span class="sxs-lookup"><span data-stu-id="2d46f-392">-EnableNetworkAccess</span></span>

<span data-ttu-id="2d46f-393">Gibt an, dass mit diesem Cmdlet Loopback Sitzungen ein interaktives Sicherheits Token hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="2d46f-393">Indicates that this cmdlet adds an interactive security token to loopback sessions.</span></span> <span data-ttu-id="2d46f-394">Mit dem interaktiven Token können Sie die Befehle in der Loopbacksitzung ausführen, um Daten von anderen Computern abzurufen.</span><span class="sxs-lookup"><span data-stu-id="2d46f-394">The interactive token lets you run commands in the loopback session that get data from other computers.</span></span> <span data-ttu-id="2d46f-395">Beispielsweise können Sie einen Befehl in der Sitzung ausführen, mit dem XML-Dateien von einem Remotecomputer auf den lokalen Computer kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="2d46f-395">For example, you can run a command in the session that copies XML files from a remote computer to the local computer.</span></span>

<span data-ttu-id="2d46f-396">Eine Loopback Sitzung ist eine **PSSession** , die auf demselben computerbasiert und endet.</span><span class="sxs-lookup"><span data-stu-id="2d46f-396">A loopback session is a **PSSession** that originates and ends on the same computer.</span></span> <span data-ttu-id="2d46f-397">Um eine Loopback Sitzung zu erstellen, lassen Sie den **Computername** -Parameter aus, oder legen Sie seinen Wert auf "dot ( `.` )", "localhost" oder den Namen des lokalen Computers fest.</span><span class="sxs-lookup"><span data-stu-id="2d46f-397">To create a loopback session, omit the **ComputerName** parameter or set its value to dot (`.`), localhost, or the name of the local computer.</span></span>

<span data-ttu-id="2d46f-398">Standardmäßig werden Loopback Sitzungen mit einem Netzwerk Token erstellt, das möglicherweise nicht über ausreichende Berechtigungen zum Authentifizieren bei Remote Computern verfügt.</span><span class="sxs-lookup"><span data-stu-id="2d46f-398">By default, loopback sessions are created using a network token, which might not provide sufficient permission to authenticate to remote computers.</span></span>

<span data-ttu-id="2d46f-399">Der **EnableNetworkAccess** -Parameter ist nur bei Loopbacksitzungen wirksam.</span><span class="sxs-lookup"><span data-stu-id="2d46f-399">The **EnableNetworkAccess** parameter is effective only in loopback sessions.</span></span> <span data-ttu-id="2d46f-400">Wenn Sie **enablenetworkaccess** verwenden, wenn Sie eine Sitzung auf einem Remote Computer erstellen, ist der Befehl erfolgreich, aber der-Parameter wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="2d46f-400">If you use **EnableNetworkAccess** when you create a session on a remote computer, the command succeeds, but the parameter is ignored.</span></span>

<span data-ttu-id="2d46f-401">Sie können den Remote Zugriff in einer Loopback Sitzung mithilfe des Werts " **kredssp** " des Parameters " **Authentication** " zulassen, der die Sitzungs Anmelde Informationen an andere Computer delegiert.</span><span class="sxs-lookup"><span data-stu-id="2d46f-401">You can allow remote access in a loopback session using the **CredSSP** value of the **Authentication** parameter, which delegates the session credentials to other computers.</span></span>

<span data-ttu-id="2d46f-402">Um den Computer vor böswilligem Zugriff zu schützen, können getrennte Loopback Sitzungen mit interaktiven Tokens, die mithilfe von **enablenetworkaccess** erstellt wurden, nur von dem Computer wieder hergestellt werden, auf dem die Sitzung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="2d46f-402">To protect the computer from malicious access, disconnected loopback sessions that have interactive tokens, which are those created using **EnableNetworkAccess** , can be reconnected only from the computer on which the session was created.</span></span> <span data-ttu-id="2d46f-403">Die Verbindung von getrennten Sitzungen, die die CredSSP-Authentifizierung verwenden, kann von anderen Computern wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="2d46f-403">Disconnected sessions that use CredSSP authentication can be reconnected from other computers.</span></span> <span data-ttu-id="2d46f-404">Weitere Informationen finden Sie unter `Disconnect-PSSession`.</span><span class="sxs-lookup"><span data-stu-id="2d46f-404">For more information, see `Disconnect-PSSession`.</span></span>

<span data-ttu-id="2d46f-405">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="2d46f-405">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: FilePathComputerName, ComputerName, Uri, FilePathUri
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2d46f-406">-FilePath</span><span class="sxs-lookup"><span data-stu-id="2d46f-406">-FilePath</span></span>

<span data-ttu-id="2d46f-407">Gibt ein lokales Skript an, das dieses Cmdlet auf einem oder mehreren Remote Computern ausführt.</span><span class="sxs-lookup"><span data-stu-id="2d46f-407">Specifies a local script that this cmdlet runs on one or more remote computers.</span></span> <span data-ttu-id="2d46f-408">Geben Sie den Pfad und den Dateinamen des Skripts ein, oder übergeben Sie einen Skript Pfad an `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="2d46f-408">Enter the path and filename of the script, or pipe a script path to `Invoke-Command`.</span></span> <span data-ttu-id="2d46f-409">Das Skript muss auf dem lokalen Computer oder in einem Verzeichnis vorhanden sein, auf das der lokale Computer zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="2d46f-409">The script must exist on the local computer or in a directory that the local computer can access.</span></span> <span data-ttu-id="2d46f-410">Verwenden Sie **argumentlist** , um die Werte der Parameter im Skript anzugeben.</span><span class="sxs-lookup"><span data-stu-id="2d46f-410">Use **ArgumentList** to specify the values of parameters in the script.</span></span>

<span data-ttu-id="2d46f-411">Wenn Sie diesen Parameter verwenden, konvertiert PowerShell den Inhalt der angegebenen Skriptdatei in einen Skriptblock, überträgt den Skriptblock an den Remote Computer und führt ihn auf dem Remote Computer aus.</span><span class="sxs-lookup"><span data-stu-id="2d46f-411">When you use this parameter, PowerShell converts the contents of the specified script file to a script block, transmits the script block to the remote computer, and runs it on the remote computer.</span></span>

```yaml
Type: System.String
Parameter Sets: FilePathRunspace, FilePathComputerName, FilePathUri, FilePathVMId, FilePathVMName, FilePathContainerId
Aliases: PSPath

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2d46f-412">-Hidecomputername</span><span class="sxs-lookup"><span data-stu-id="2d46f-412">-HideComputerName</span></span>

<span data-ttu-id="2d46f-413">Gibt an, dass dieses Cmdlet den Computernamen der einzelnen Objekte aus der Ausgabe Anzeige auslässt.</span><span class="sxs-lookup"><span data-stu-id="2d46f-413">Indicates that this cmdlet omits the computer name of each object from the output display.</span></span> <span data-ttu-id="2d46f-414">Standardmäßig wird der Name des Computers, der das Objekt generiert, in der Anzeige angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2d46f-414">By default, the name of the computer that generated the object appears in the display.</span></span>

<span data-ttu-id="2d46f-415">Dieser Parameter betrifft nur die Ausgabeanzeige.</span><span class="sxs-lookup"><span data-stu-id="2d46f-415">This parameter affects only the output display.</span></span> <span data-ttu-id="2d46f-416">Das Objekt wird nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="2d46f-416">It doesn't change the object.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Session, FilePathRunspace, FilePathComputerName, ComputerName, Uri, FilePathUri, VMId, VMName, FilePathVMId, FilePathVMName, ContainerId, FilePathContainerId
Aliases: HCN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2d46f-417">-Indisconnectedsession</span><span class="sxs-lookup"><span data-stu-id="2d46f-417">-InDisconnectedSession</span></span>

<span data-ttu-id="2d46f-418">Gibt an, dass dieses Cmdlet einen Befehl oder ein Skript in einer getrennten Sitzung ausführt.</span><span class="sxs-lookup"><span data-stu-id="2d46f-418">Indicates that this cmdlet runs a command or script in a disconnected session.</span></span>

<span data-ttu-id="2d46f-419">Wenn Sie den **indisconnectedsession** -Parameter verwenden, wird `Invoke-Command` auf jedem Remote Computer eine persistente Sitzung erstellt, der durch den **ScriptBlock** -Parameter oder den **FilePath** -Parameter angegebene Befehl gestartet und die Verbindung mit der Sitzung getrennt.</span><span class="sxs-lookup"><span data-stu-id="2d46f-419">When you use the **InDisconnectedSession** parameter, `Invoke-Command` creates a persistent session on each remote computer, starts the command specified by the **ScriptBlock** or **FilePath** parameter, and then disconnects from the session.</span></span> <span data-ttu-id="2d46f-420">Die Befehle werden weiterhin in den getrennten Sitzungen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2d46f-420">The commands continue to run in the disconnected sessions.</span></span> <span data-ttu-id="2d46f-421">Mit **indisconnectedsession** können Sie Befehle ausführen, ohne eine Verbindung mit den Remote Sitzungen aufrechtzuerhalten.</span><span class="sxs-lookup"><span data-stu-id="2d46f-421">**InDisconnectedSession** enables you to run commands without maintaining a connection to the remote sessions.</span></span> <span data-ttu-id="2d46f-422">Und da die Sitzung getrennt wird, bevor Ergebnisse zurückgegeben werden, stellt " **indisconnectedsession** " sicher, dass alle Befehls Ergebnisse an die erneut verbundene Sitzung zurückgegeben werden, statt zwischen Sitzungen aufgeteilt zu werden.</span><span class="sxs-lookup"><span data-stu-id="2d46f-422">And, because the session is disconnected before any results are returned, **InDisconnectedSession** makes sure that all command results are returned to the reconnected session, instead of being split between sessions.</span></span>

<span data-ttu-id="2d46f-423">Sie können " **indisconnectedsession** " nicht mit dem **Sitzungs** Parameter oder dem **AsJob** -Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="2d46f-423">You can't use **InDisconnectedSession** with the **Session** parameter or the **AsJob** parameter.</span></span>

<span data-ttu-id="2d46f-424">Befehle, die **indisconnectedsession** verwenden, geben ein **PSSession** -Objekt zurück, das die getrennte Sitzung darstellt.</span><span class="sxs-lookup"><span data-stu-id="2d46f-424">Commands that use **InDisconnectedSession** return a **PSSession** object that represents the disconnected session.</span></span> <span data-ttu-id="2d46f-425">Die Befehlsausgabe wird nicht zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2d46f-425">They don't return the command output.</span></span> <span data-ttu-id="2d46f-426">Verwenden Sie zum Herstellen einer Verbindung mit der getrennten Sitzung die `Connect-PSSession` `Receive-PSSession` Cmdlets oder.</span><span class="sxs-lookup"><span data-stu-id="2d46f-426">To connect to the disconnected session, use the `Connect-PSSession` or `Receive-PSSession` cmdlets.</span></span> <span data-ttu-id="2d46f-427">Verwenden Sie das-Cmdlet, um die Ergebnisse von Befehlen zu erhalten, die in der Sitzung ausgeführt wurden `Receive-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="2d46f-427">To get the results of commands that ran in the session, use the `Receive-PSSession` cmdlet.</span></span> <span data-ttu-id="2d46f-428">Um Befehle auszuführen, die eine Ausgabe in einer getrennten Sitzung generieren, legen Sie den Wert der **outputbufferingmode** -Sitzungs Option auf **Drop** fest.</span><span class="sxs-lookup"><span data-stu-id="2d46f-428">To run commands that generate output in a disconnected session, set the value of the **OutputBufferingMode** session option to **Drop**.</span></span> <span data-ttu-id="2d46f-429">Wenn Sie eine Verbindung mit der getrennten Sitzung herstellen möchten, legen Sie das Leerlauf Timeout in der Sitzung fest, damit Sie genügend Zeit zum Herstellen einer Verbindung haben, bevor Sie die Sitzung löschen.</span><span class="sxs-lookup"><span data-stu-id="2d46f-429">If you intend to connect to the disconnected session, set the idle time-out in the session so that it provides sufficient time for you to connect before deleting the session.</span></span>

<span data-ttu-id="2d46f-430">Sie können den Ausgabepuffer Modus und das Leerlauf Timeout im **sessionoption** -Parameter oder in der `$PSSessionOption` Preference-Variablen festlegen.</span><span class="sxs-lookup"><span data-stu-id="2d46f-430">You can set the output buffering mode and idle time-out in the **SessionOption** parameter or in the `$PSSessionOption` preference variable.</span></span> <span data-ttu-id="2d46f-431">Weitere Informationen zu Sitzungs Optionen finden Sie unter `New-PSSessionOption` und [about_Preference_Variables](./about/about_preference_variables.md).</span><span class="sxs-lookup"><span data-stu-id="2d46f-431">For more information about session options, see `New-PSSessionOption` and [about_Preference_Variables](./about/about_preference_variables.md).</span></span>

<span data-ttu-id="2d46f-432">Weitere Informationen zum Feature „Getrennte Sitzungen“ finden Sie unter [about_Remote_Disconnected_Sessions](about/about_Remote_Disconnected_Sessions.md).</span><span class="sxs-lookup"><span data-stu-id="2d46f-432">For more information about the Disconnected Sessions feature, see [about_Remote_Disconnected_Sessions](about/about_Remote_Disconnected_Sessions.md).</span></span>

<span data-ttu-id="2d46f-433">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="2d46f-433">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: FilePathComputerName, ComputerName, Uri, FilePathUri
Aliases: Disconnected

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2d46f-434">-InputObject</span><span class="sxs-lookup"><span data-stu-id="2d46f-434">-InputObject</span></span>

<span data-ttu-id="2d46f-435">Gibt die Eingabe für den Befehl an.</span><span class="sxs-lookup"><span data-stu-id="2d46f-435">Specifies input to the command.</span></span> <span data-ttu-id="2d46f-436">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, durch den die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="2d46f-436">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span>

<span data-ttu-id="2d46f-437">Wenn Sie den **Inputobject** -Parameter verwenden, verwenden `$Input` Sie die automatische Variable im Wert des **ScriptBlock** -Parameters, um die Eingabe Objekte darzustellen.</span><span class="sxs-lookup"><span data-stu-id="2d46f-437">When using the **InputObject** parameter, use the `$Input` automatic variable in the value of the **ScriptBlock** parameter to represent the input objects.</span></span>

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

### <span data-ttu-id="2d46f-438">-Jobname</span><span class="sxs-lookup"><span data-stu-id="2d46f-438">-JobName</span></span>

<span data-ttu-id="2d46f-439">Gibt einen Anzeigenamen für den Hintergrundauftrag an.</span><span class="sxs-lookup"><span data-stu-id="2d46f-439">Specifies a friendly name for the background job.</span></span> <span data-ttu-id="2d46f-440">Standardmäßig werden Aufträge benannt `Job<n>` , wobei `<n>` eine Ordinalzahl ist.</span><span class="sxs-lookup"><span data-stu-id="2d46f-440">By default, jobs are named `Job<n>`, where `<n>` is an ordinal number.</span></span>

<span data-ttu-id="2d46f-441">Wenn Sie den **Jobname** -Parameter in einem Befehl verwenden, wird der Befehl als Auftrag ausgeführt, und es wird `Invoke-Command` ein Auftrags Objekt zurückgegeben, auch wenn Sie **AsJob** nicht in den Befehl einschließen.</span><span class="sxs-lookup"><span data-stu-id="2d46f-441">If you use the **JobName** parameter in a command, the command is run as a job, and `Invoke-Command` returns a job object, even if you don't include **AsJob** in the command.</span></span>

<span data-ttu-id="2d46f-442">Weitere Informationen zu PowerShell-Hintergrund Aufträgen finden Sie unter [about_Jobs](./About/about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="2d46f-442">For more information about PowerShell background jobs, see [about_Jobs](./About/about_Jobs.md).</span></span>

```yaml
Type: System.String
Parameter Sets: Session, FilePathRunspace, FilePathComputerName, ComputerName, Uri, FilePathUri, ContainerId, FilePathContainerId
Aliases:

Required: False
Position: Named
Default value: Job<n>
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2d46f-443">-Nonewscope</span><span class="sxs-lookup"><span data-stu-id="2d46f-443">-NoNewScope</span></span>

<span data-ttu-id="2d46f-444">Gibt an, dass dieses Cmdlet den angegebenen Befehl im aktuellen Bereich ausführt.</span><span class="sxs-lookup"><span data-stu-id="2d46f-444">Indicates that this cmdlet runs the specified command in the current scope.</span></span> <span data-ttu-id="2d46f-445">Standardmäßig `Invoke-Command` führt Befehle in Ihrem eigenen Bereich aus.</span><span class="sxs-lookup"><span data-stu-id="2d46f-445">By default, `Invoke-Command` runs commands in their own scope.</span></span>

<span data-ttu-id="2d46f-446">Dieser Parameter ist nur in Befehlen gültig, die in der aktuellen Sitzung ausgeführt werden, d. h. in Befehlen, bei denen beide Parameter, **ComputerName** und **Session** , weglassen wurden.</span><span class="sxs-lookup"><span data-stu-id="2d46f-446">This parameter is valid only in commands that are run in the current session, that is, commands that omit both the **ComputerName** and **Session** parameters.</span></span>

<span data-ttu-id="2d46f-447">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="2d46f-447">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="2d46f-448">-Port</span><span class="sxs-lookup"><span data-stu-id="2d46f-448">-Port</span></span>

<span data-ttu-id="2d46f-449">Gibt den Netzwerkport auf dem Remote Computer an, der für diesen Befehl verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2d46f-449">Specifies the network port on the remote computer that is used for this command.</span></span> <span data-ttu-id="2d46f-450">Zum Herstellen einer Verbindung mit einem Remotecomputer muss der Remotecomputer den für die Verbindung verwendeten Port abhören.</span><span class="sxs-lookup"><span data-stu-id="2d46f-450">To connect to a remote computer, the remote computer must be listening on the port that the connection uses.</span></span> <span data-ttu-id="2d46f-451">Die Standardports sind 5985 (WinRM-Port für http) und 5986 (WinRM-Port für HTTPS).</span><span class="sxs-lookup"><span data-stu-id="2d46f-451">The default ports are 5985 (WinRM port for HTTP) and 5986 (WinRM port for HTTPS).</span></span>

<span data-ttu-id="2d46f-452">Konfigurieren Sie vor der Verwendung eines alternativen Ports den WinRM-Listener auf dem Remotecomputer, um diesen Port abzuhören.</span><span class="sxs-lookup"><span data-stu-id="2d46f-452">Before using an alternate port, configure the WinRM listener on the remote computer to listen at that port.</span></span> <span data-ttu-id="2d46f-453">Um den Listener zu konfigurieren, geben Sie die folgenden beiden Befehle an der PowerShell-Eingabeaufforderung ein:</span><span class="sxs-lookup"><span data-stu-id="2d46f-453">To configure the listener, type the following two commands at the PowerShell prompt:</span></span>

`Remove-Item -Path WSMan:\Localhost\listener\listener* -Recurse`

`New-Item -Path WSMan:\Localhost\listener -Transport http -Address * -Port \<port-number\>`

<span data-ttu-id="2d46f-454">Verwenden Sie den **Port** -Parameter nur, wenn dies erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="2d46f-454">Don't use the **Port** parameter unless you must.</span></span> <span data-ttu-id="2d46f-455">Der im Befehl festgelegte Port gilt für alle Computer oder Sitzungen, für die der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2d46f-455">The port that is set in the command applies to all computers or sessions on which the command runs.</span></span> <span data-ttu-id="2d46f-456">Eine alternative Porteinstellung kann verhindern, dass der Befehl auf allen Computern ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2d46f-456">An alternate port setting might prevent the command from running on all computers.</span></span>

```yaml
Type: System.Int32
Parameter Sets: FilePathComputerName, ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2d46f-457">-Runasadministrator</span><span class="sxs-lookup"><span data-stu-id="2d46f-457">-RunAsAdministrator</span></span>

<span data-ttu-id="2d46f-458">Gibt an, dass dieses Cmdlet einen Befehl als Administrator aufruft.</span><span class="sxs-lookup"><span data-stu-id="2d46f-458">Indicates that this cmdlet invokes a command as an Administrator.</span></span>

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

### <span data-ttu-id="2d46f-459">-ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="2d46f-459">-ScriptBlock</span></span>

<span data-ttu-id="2d46f-460">Gibt die auszuführenden Befehle an.</span><span class="sxs-lookup"><span data-stu-id="2d46f-460">Specifies the commands to run.</span></span> <span data-ttu-id="2d46f-461">Schließen Sie die Befehle in geschweiften Klammern `{ }` ein, um einen Skriptblock zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2d46f-461">Enclose the commands in curly braces `{ }` to create a script block.</span></span>
<span data-ttu-id="2d46f-462">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2d46f-462">This parameter is required.</span></span>

<span data-ttu-id="2d46f-463">Standardmäßig werden alle Variablen im Befehl auf dem Remotecomputer ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="2d46f-463">By default, any variables in the command are evaluated on the remote computer.</span></span> <span data-ttu-id="2d46f-464">Um lokale Variablen in den Befehl einzuschließen, verwenden Sie **argumentlist**.</span><span class="sxs-lookup"><span data-stu-id="2d46f-464">To include local variables in the command, use **ArgumentList**.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: InProcess, Session, ComputerName, Uri, VMId, VMName, ContainerId
Aliases: Command

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2d46f-465">-Sitzung</span><span class="sxs-lookup"><span data-stu-id="2d46f-465">-Session</span></span>

<span data-ttu-id="2d46f-466">Gibt ein Array von Sitzungen an, in denen dieses Cmdlet den Befehl ausführt.</span><span class="sxs-lookup"><span data-stu-id="2d46f-466">Specifies an array of sessions in which this cmdlet runs the command.</span></span> <span data-ttu-id="2d46f-467">Geben Sie eine Variable ein, die **PSSession** -Objekte enthält, oder einen Befehl, der die **PSSession** -Objekte erstellt oder abruft, z `New-PSSession` . b. den `Get-PSSession` Befehl oder.</span><span class="sxs-lookup"><span data-stu-id="2d46f-467">Enter a variable that contains **PSSession** objects or a command that creates or gets the **PSSession** objects, such as a `New-PSSession` or `Get-PSSession` command.</span></span>

<span data-ttu-id="2d46f-468">Wenn Sie eine **PSSession** erstellen, stellt PowerShell eine permanente Verbindung mit dem Remote Computer her.</span><span class="sxs-lookup"><span data-stu-id="2d46f-468">When you create a **PSSession** , PowerShell establishes a persistent connection to the remote computer.</span></span> <span data-ttu-id="2d46f-469">Verwenden Sie eine **PSSession** , um eine Reihe verwandter Befehle auszuführen, die Daten gemeinsam nutzen.</span><span class="sxs-lookup"><span data-stu-id="2d46f-469">Use a **PSSession** to run a series of related commands that share data.</span></span> <span data-ttu-id="2d46f-470">Verwenden Sie den **Computername** -Parameter, um einen einzelnen Befehl oder eine Reihe von nicht verknüpften Befehlen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="2d46f-470">To run a single command or a series of unrelated commands, use the **ComputerName** parameter.</span></span> <span data-ttu-id="2d46f-471">Weitere Informationen finden Sie unter [about_PSSessions](./About/about_PSSessions.md).</span><span class="sxs-lookup"><span data-stu-id="2d46f-471">For more information, see [about_PSSessions](./About/about_PSSessions.md).</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession[]
Parameter Sets: Session, FilePathRunspace
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2d46f-472">-Sessionname</span><span class="sxs-lookup"><span data-stu-id="2d46f-472">-SessionName</span></span>

<span data-ttu-id="2d46f-473">Gibt einen Anzeigenamen für eine getrennte Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="2d46f-473">Specifies a friendly name for a disconnected session.</span></span> <span data-ttu-id="2d46f-474">Sie können den Namen verwenden, um in nachfolgenden Befehlen auf die Sitzung zu verweisen, z. b. einen- `Get-PSSession` Befehl.</span><span class="sxs-lookup"><span data-stu-id="2d46f-474">You can use the name to refer to the session in subsequent commands, such as a `Get-PSSession` command.</span></span> <span data-ttu-id="2d46f-475">Dieser Parameter ist nur mit dem **InDisconnectedSession** -Parameter gültig.</span><span class="sxs-lookup"><span data-stu-id="2d46f-475">This parameter is valid only with the **InDisconnectedSession** parameter.</span></span>

<span data-ttu-id="2d46f-476">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="2d46f-476">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FilePathComputerName, ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2d46f-477">-Sessionoption</span><span class="sxs-lookup"><span data-stu-id="2d46f-477">-SessionOption</span></span>

<span data-ttu-id="2d46f-478">Gibt erweiterte Optionen für die Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="2d46f-478">Specifies advanced options for the session.</span></span> <span data-ttu-id="2d46f-479">Geben Sie ein **sessionoption** -Objekt ein, z. b. ein Objekt, das Sie mit dem `New-PSSessionOption` Cmdlet erstellen, oder eine Hash Tabelle, in der die Schlüssel Sitzungs Optionsnamen und die Werte Sitzungs Optionswerte sind.</span><span class="sxs-lookup"><span data-stu-id="2d46f-479">Enter a **SessionOption** object, such as one that you create using the `New-PSSessionOption` cmdlet, or a hash table in which the keys are session option names and the values are session option values.</span></span>

<span data-ttu-id="2d46f-480">Die Standardwerte für die Optionen werden durch den Wert der Einstellungs `$PSSessionOption` Variablen bestimmt, sofern festgelegt.</span><span class="sxs-lookup"><span data-stu-id="2d46f-480">The default values for the options are determined by the value of the `$PSSessionOption` preference variable, if it's set.</span></span> <span data-ttu-id="2d46f-481">Andernfalls werden die Standardwerte durch Optionen festgelegt, die in der Sitzungskonfiguration festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="2d46f-481">Otherwise, the default values are established by options set in the session configuration.</span></span>

<span data-ttu-id="2d46f-482">Die Sitzungs Optionswerte haben Vorrang vor Standardwerten für Sitzungen, die in der `$PSSessionOption` Preference-Variablen und in der Sitzungs Konfiguration festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="2d46f-482">The session option values take precedence over default values for sessions set in the `$PSSessionOption` preference variable and in the session configuration.</span></span> <span data-ttu-id="2d46f-483">Allerdings haben Sie Vorrang vor maximalen Werten, Kontingenten oder Grenzwerten, die in der Sitzungs Konfiguration festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="2d46f-483">However, they don't take precedence over maximum values, quotas, or limits set in the session configuration.</span></span>

<span data-ttu-id="2d46f-484">Eine Beschreibung der Sitzungs Optionen, die die Standardwerte enthalten, finden Sie unter `New-PSSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="2d46f-484">For a description of the session options that includes the default values, see `New-PSSessionOption`.</span></span> <span data-ttu-id="2d46f-485">Weitere Informationen zur Einstellungs `$PSSessionOption` Variablen finden Sie unter [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="2d46f-485">For information about the `$PSSessionOption` preference variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>
<span data-ttu-id="2d46f-486">Weitere Informationen zu Sitzungs Konfigurationen finden Sie unter [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="2d46f-486">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

```yaml
Type: System.Management.Automation.Remoting.PSSessionOption
Parameter Sets: FilePathComputerName, ComputerName, Uri, FilePathUri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2d46f-487">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="2d46f-487">-ThrottleLimit</span></span>

<span data-ttu-id="2d46f-488">Gibt die maximale Anzahl von gleichzeitigen Verbindungen an, die zum Ausführen dieses Befehls hergestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="2d46f-488">Specifies the maximum number of concurrent connections that can be established to run this command.</span></span>
<span data-ttu-id="2d46f-489">Wenn Sie diesen Parameter weglassen oder den Wert %%amp;quot;0%%amp;quot; eingeben, wird der Standardwert %%amp;quot;32%%amp;quot; verwendet.</span><span class="sxs-lookup"><span data-stu-id="2d46f-489">If you omit this parameter or enter a value of 0, the default value, 32, is used.</span></span>

<span data-ttu-id="2d46f-490">Die Drosselungsgrenze gilt nur für den aktuellen Befehl und nicht für die Sitzung oder den Computer.</span><span class="sxs-lookup"><span data-stu-id="2d46f-490">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

```yaml
Type: System.Int32
Parameter Sets: Session, FilePathRunspace, FilePathComputerName, ComputerName, Uri, FilePathUri, VMId, VMName, FilePathVMId, FilePathVMName, ContainerId, FilePathContainerId
Aliases:

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2d46f-491">-US-</span><span class="sxs-lookup"><span data-stu-id="2d46f-491">-UseSSL</span></span>

<span data-ttu-id="2d46f-492">Gibt an, dass dieses Cmdlet das Secure Sockets Layer (SSL)-Protokoll verwendet, um eine Verbindung mit dem Remote Computer herzustellen.</span><span class="sxs-lookup"><span data-stu-id="2d46f-492">Indicates that this cmdlet uses the Secure Sockets Layer (SSL) protocol to establish a connection to the remote computer.</span></span> <span data-ttu-id="2d46f-493">Standardmäßig wird SSL nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="2d46f-493">By default, SSL isn't used.</span></span>

<span data-ttu-id="2d46f-494">WS-Management verschlüsselt alle über das Netzwerk übertragenen PowerShell-Inhalte.</span><span class="sxs-lookup"><span data-stu-id="2d46f-494">WS-Management encrypts all PowerShell content transmitted over the network.</span></span> <span data-ttu-id="2d46f-495">Der **Parameter "** " ist ein zusätzlicher Schutz, der die Daten über eine HTTPS-anstelle von http sendet.</span><span class="sxs-lookup"><span data-stu-id="2d46f-495">The **UseSSL** parameter is an additional protection that sends the data across an HTTPS, instead of HTTP.</span></span>

<span data-ttu-id="2d46f-496">Wenn Sie diesen Parameter verwenden, aber SSL auf dem Port, der für den Befehl verwendet wird, nicht verfügbar ist, schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="2d46f-496">If you use this parameter, but SSL isn't available on the port that's used for the command, the command fails.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: FilePathComputerName, ComputerName
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2d46f-497">-VMID</span><span class="sxs-lookup"><span data-stu-id="2d46f-497">-VMId</span></span>

<span data-ttu-id="2d46f-498">Gibt ein Array von IDs von virtuellen Computern an.</span><span class="sxs-lookup"><span data-stu-id="2d46f-498">Specifies an array of IDs of virtual machines.</span></span>

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

### <span data-ttu-id="2d46f-499">-VMName</span><span class="sxs-lookup"><span data-stu-id="2d46f-499">-VMName</span></span>

<span data-ttu-id="2d46f-500">Gibt ein Array von Namen von virtuellen Computern an.</span><span class="sxs-lookup"><span data-stu-id="2d46f-500">Specifies an array of names of virtual machines.</span></span>

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

### <span data-ttu-id="2d46f-501">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="2d46f-501">CommonParameters</span></span>

<span data-ttu-id="2d46f-502">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2d46f-502">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2d46f-503">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2d46f-503">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2d46f-504">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="2d46f-504">INPUTS</span></span>

### <span data-ttu-id="2d46f-505">System. Management. Automation. ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="2d46f-505">System.Management.Automation.ScriptBlock</span></span>

<span data-ttu-id="2d46f-506">Sie können einen Befehl in einem Skriptblock an die Pipeline übergeben `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="2d46f-506">You can pipe a command in a script block to `Invoke-Command`.</span></span> <span data-ttu-id="2d46f-507">Verwenden `$Input` Sie die automatische Variable, um die Eingabe Objekte im Befehl darzustellen.</span><span class="sxs-lookup"><span data-stu-id="2d46f-507">Use the `$Input` automatic variable to represent the input objects in the command.</span></span>

## <span data-ttu-id="2d46f-508">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="2d46f-508">OUTPUTS</span></span>

### <span data-ttu-id="2d46f-509">System. Management. Automation. psremotingjob, System. Management. Automation. Runspaces. PSSession oder die Ausgabe des aufgerufenen Befehls</span><span class="sxs-lookup"><span data-stu-id="2d46f-509">System.Management.Automation.PSRemotingJob, System.Management.Automation.Runspaces.PSSession, or the output of the invoked command</span></span>

<span data-ttu-id="2d46f-510">Dieses Cmdlet gibt ein Auftrags Objekt zurück, wenn Sie den **AsJob** -Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="2d46f-510">This cmdlet returns a job object, if you use the **AsJob** parameter.</span></span> <span data-ttu-id="2d46f-511">Wenn Sie den **indisconnectedsession** -Parameter angeben, `Invoke-Command` gibt ein **PSSession** -Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="2d46f-511">If you specify the **InDisconnectedSession** parameter, `Invoke-Command` returns a **PSSession** object.</span></span> <span data-ttu-id="2d46f-512">Andernfalls wird die Ausgabe des aufgerufenen Befehls zurückgegeben, bei dem es sich um den Wert des **ScriptBlock** -Parameters handelt.</span><span class="sxs-lookup"><span data-stu-id="2d46f-512">Otherwise, it returns the output of the invoked command, which is the value of the **ScriptBlock** parameter.</span></span>

## <span data-ttu-id="2d46f-513">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="2d46f-513">NOTES</span></span>

<span data-ttu-id="2d46f-514">Wenn unter Windows Vista und höheren Versionen des Windows-Betriebssystems der **Computername** -Parameter von `Invoke-Command` zum Ausführen eines Befehls auf dem lokalen Computer verwendet werden soll, müssen Sie PowerShell mithilfe der Option **als Administrator ausführen** ausführen.</span><span class="sxs-lookup"><span data-stu-id="2d46f-514">On Windows Vista, and later versions of the Windows operating system, to use the **ComputerName** parameter of `Invoke-Command` to run a command on the local computer, you must run PowerShell using the **Run as administrator** option.</span></span>

<span data-ttu-id="2d46f-515">Wenn Sie Befehle auf mehreren Computern ausführen, stellt PowerShell eine Verbindung mit den Computern in der Reihenfolge her, in der Sie in der Liste angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="2d46f-515">When you run commands on multiple computers, PowerShell connects to the computers in the order in which they appear in the list.</span></span> <span data-ttu-id="2d46f-516">Allerdings wird die Befehlsausgabe in der Reihenfolge angezeigt, in der Sie von den Remote Computern empfangen wird, die sich möglicherweise unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="2d46f-516">However, the command output is displayed in the order that it's received from the remote computers, which might be different.</span></span>

<span data-ttu-id="2d46f-517">Fehler, die sich aus dem Befehl ergeben, der `Invoke-Command` ausführt, sind in den Befehls Ergebnissen enthalten.</span><span class="sxs-lookup"><span data-stu-id="2d46f-517">Errors that result from the command that `Invoke-Command` runs are included in the command results.</span></span>
<span data-ttu-id="2d46f-518">Fehler, die in einem lokalen Befehl Fehler mit Abbruch sein würden, werden in einem Remotebefehl als Fehler ohne Abbruch behandelt.</span><span class="sxs-lookup"><span data-stu-id="2d46f-518">Errors that would be terminating errors in a local command are treated as non-terminating errors in a remote command.</span></span> <span data-ttu-id="2d46f-519">Durch diese Strategie wird sichergestellt, dass beim Beenden von Fehlern auf einem Computer der Befehl auf allen Computern, auf denen er ausgeführt wird, nicht geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="2d46f-519">This strategy makes sure that terminating errors on one computer don't close the command on all computers on which it's run.</span></span> <span data-ttu-id="2d46f-520">Diese Vorgehensweise wird selbst dann verwendet, wenn ein Remotebefehl auf einem einzelnen Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2d46f-520">This practice is used even when a remote command is run on a single computer.</span></span>

<span data-ttu-id="2d46f-521">Wenn sich der Remote Computer nicht in einer Domäne befindet, der der lokale Computer vertraut, ist der Computer möglicherweise nicht in der Lage, die Anmelde Informationen des Benutzers zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="2d46f-521">If the remote computer isn't in a domain that the local computer trusts, the computer might not be able to authenticate the user's credentials.</span></span> <span data-ttu-id="2d46f-522">Um den Remote Computer der Liste der vertrauenswürdigen Hosts in der WS-Verwaltung hinzuzufügen, verwenden Sie den folgenden Befehl im `WSMAN` Anbieter, wobei `<Remote-Computer-Name>` der Name des Remote Computers ist:</span><span class="sxs-lookup"><span data-stu-id="2d46f-522">To add the remote computer to the list of trusted hosts in WS-Management, use the following command in the `WSMAN` provider, where `<Remote-Computer-Name>` is the name of the remote computer:</span></span>

`Set-Item -Path WSMan:\Localhost\Client\TrustedHosts -Value \<Remote-Computer-Name\>`

<span data-ttu-id="2d46f-523">Wenn Sie eine **PSSession** mit dem **indisconnectedsession** -Parameter trennen, wird der Sitzungs Status **getrennt** , und die Verfügbarkeit ist **None**.</span><span class="sxs-lookup"><span data-stu-id="2d46f-523">When you disconnect a **PSSession** using the **InDisconnectedSession** parameter, the session state is **Disconnected** and the availability is **None**.</span></span> <span data-ttu-id="2d46f-524">Der Wert der **State** Eigenschaft bezieht sich auf die aktuelle Sitzung.</span><span class="sxs-lookup"><span data-stu-id="2d46f-524">The value of the **State** property is relative to the current session.</span></span> <span data-ttu-id="2d46f-525">Der Wert " **getrennt** " bedeutet, dass die **PSSession** nicht mit der aktuellen Sitzung verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="2d46f-525">A value of **Disconnected** means that the **PSSession** isn't connected to the current session.</span></span> <span data-ttu-id="2d46f-526">Dies bedeutet jedoch nicht, dass die **PSSession** von allen Sitzungen getrennt ist.</span><span class="sxs-lookup"><span data-stu-id="2d46f-526">However, it doesn't mean that the **PSSession** is disconnected from all sessions.</span></span> <span data-ttu-id="2d46f-527">Sie kann mit einer anderen Sitzung verbunden sein.</span><span class="sxs-lookup"><span data-stu-id="2d46f-527">It might be connected to a different session.</span></span> <span data-ttu-id="2d46f-528">Um festzustellen, ob Sie eine Sitzungsverbindung herstellen bzw. wiederherstellen können, verwenden Sie die **Availability** -Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="2d46f-528">To determine whether you can connect or reconnect to the session, use the **Availability** property.</span></span>

<span data-ttu-id="2d46f-529">Ein **Availability** -Wert von **None** gibt an, dass eine Verbindung mit der Sitzung hergestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="2d46f-529">An **Availability** value of **None** indicates that you can connect to the session.</span></span> <span data-ttu-id="2d46f-530">Der Wert **ausgelastet** gibt an, dass keine Verbindung mit der **PSSession** hergestellt werden kann, da Sie mit einer anderen Sitzung verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="2d46f-530">A value of **Busy** indicates that you can't connect to the **PSSession** because it's connected to another session.</span></span> <span data-ttu-id="2d46f-531">Weitere Informationen zu den Werten der **State** -Eigenschaft von Sitzungen finden Sie unter [runspacestate](/dotnet/api/system.management.automation.runspaces.runspacestate).</span><span class="sxs-lookup"><span data-stu-id="2d46f-531">For more information about the values of the **State** property of sessions, see [RunspaceState](/dotnet/api/system.management.automation.runspaces.runspacestate).</span></span> <span data-ttu-id="2d46f-532">Weitere Informationen zu den Werten der **Availability** -Eigenschaft von Sitzungen finden Sie unter [runspaceavailability](/dotnet/api/system.management.automation.runspaces.runspaceavailability).</span><span class="sxs-lookup"><span data-stu-id="2d46f-532">For more information about the values of the **Availability** property of sessions, see [RunspaceAvailability](/dotnet/api/system.management.automation.runspaces.runspaceavailability).</span></span>

## <span data-ttu-id="2d46f-533">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="2d46f-533">RELATED LINKS</span></span>

[<span data-ttu-id="2d46f-534">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="2d46f-534">about_PSSessions</span></span>](./About/about_PSSessions.md)

[<span data-ttu-id="2d46f-535">about_Remote</span><span class="sxs-lookup"><span data-stu-id="2d46f-535">about_Remote</span></span>](./About/about_Remote.md)

[<span data-ttu-id="2d46f-536">about_Remote_Disconnected_Sessions</span><span class="sxs-lookup"><span data-stu-id="2d46f-536">about_Remote_Disconnected_Sessions</span></span>](./About/about_Remote_Disconnected_Sessions.md)

[<span data-ttu-id="2d46f-537">about_Remote_Troubleshooting</span><span class="sxs-lookup"><span data-stu-id="2d46f-537">about_Remote_Troubleshooting</span></span>](./About/about_remote_troubleshooting.md)

[<span data-ttu-id="2d46f-538">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="2d46f-538">about_Remote_Variables</span></span>](./About/about_Remote_Variables.md)

[<span data-ttu-id="2d46f-539">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="2d46f-539">about_Scopes</span></span>](./About/about_scopes.md)

[<span data-ttu-id="2d46f-540">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="2d46f-540">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="2d46f-541">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="2d46f-541">Exit-PSSession</span></span>](Exit-PSSession.md)

[<span data-ttu-id="2d46f-542">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="2d46f-542">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="2d46f-543">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="2d46f-543">Invoke-Item</span></span>](../Microsoft.PowerShell.Management/Invoke-Item.md)

[<span data-ttu-id="2d46f-544">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="2d46f-544">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="2d46f-545">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="2d46f-545">Remove-PSSession</span></span>](Remove-PSSession.md)

[<span data-ttu-id="2d46f-546">WSMan-Anbieter</span><span class="sxs-lookup"><span data-stu-id="2d46f-546">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)
