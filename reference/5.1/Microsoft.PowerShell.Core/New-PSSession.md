---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 12/20/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/new-pssession?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSSession
ms.openlocfilehash: 1835d0bd4294161f83728a63e8da8fc64c2bf9e0
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218191"
---
# <span data-ttu-id="0d23d-103">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="0d23d-103">New-PSSession</span></span>

## <span data-ttu-id="0d23d-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="0d23d-104">SYNOPSIS</span></span>
<span data-ttu-id="0d23d-105">Erstellt eine permanente Verbindung mit einem lokalen Computer oder Remotecomputer.</span><span class="sxs-lookup"><span data-stu-id="0d23d-105">Creates a persistent connection to a local or remote computer.</span></span>

## <span data-ttu-id="0d23d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0d23d-106">SYNTAX</span></span>

### <span data-ttu-id="0d23d-107">Computername (Standard)</span><span class="sxs-lookup"><span data-stu-id="0d23d-107">ComputerName (Default)</span></span>

```
New-PSSession [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-Name <String[]>]
 [-EnableNetworkAccess] [-ConfigurationName <String>] [-Port <Int32>] [-UseSSL]
 [-ApplicationName <String>] [-ThrottleLimit <Int32>] [-SessionOption <PSSessionOption>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="0d23d-108">Uri</span><span class="sxs-lookup"><span data-stu-id="0d23d-108">Uri</span></span>

```
New-PSSession [-Credential <PSCredential>] [-Name <String[]>] [-EnableNetworkAccess]
 [-ConfigurationName <String>] [-ThrottleLimit <Int32>] [-ConnectionUri] <Uri[]> [-AllowRedirection]
 [-SessionOption <PSSessionOption>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="0d23d-109">VMId</span><span class="sxs-lookup"><span data-stu-id="0d23d-109">VMId</span></span>

```
New-PSSession -Credential <PSCredential> [-Name <String[]>] [-ConfigurationName <String>]
 [-VMId] <Guid[]> [-ThrottleLimit <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="0d23d-110">VMName</span><span class="sxs-lookup"><span data-stu-id="0d23d-110">VMName</span></span>

```
New-PSSession -Credential <PSCredential> [-Name <String[]>] [-ConfigurationName <String>]
 -VMName <String[]> [-ThrottleLimit <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="0d23d-111">Sitzung</span><span class="sxs-lookup"><span data-stu-id="0d23d-111">Session</span></span>

```
New-PSSession [[-Session] <PSSession[]>] [-Name <String[]>] [-EnableNetworkAccess]
 [-ThrottleLimit <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="0d23d-112">ContainerId</span><span class="sxs-lookup"><span data-stu-id="0d23d-112">ContainerId</span></span>

```
New-PSSession [-Name <String[]>] [-ConfigurationName <String>] -ContainerId <String[]>
 [-RunAsAdministrator] [-ThrottleLimit <Int32>] [<CommonParameters>]
```

## <span data-ttu-id="0d23d-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0d23d-113">DESCRIPTION</span></span>

<span data-ttu-id="0d23d-114">Mit dem- `New-PSSession` Cmdlet wird eine PowerShell-Sitzung ( **PSSession** ) auf einem lokalen Computer oder einem Remote Computer erstellt.</span><span class="sxs-lookup"><span data-stu-id="0d23d-114">The `New-PSSession` cmdlet creates a PowerShell session ( **PSSession** ) on a local or remote computer.</span></span> <span data-ttu-id="0d23d-115">Wenn Sie eine **PSSession** erstellen, stellt PowerShell eine permanente Verbindung mit dem Remote Computer her.</span><span class="sxs-lookup"><span data-stu-id="0d23d-115">When you create a **PSSession** , PowerShell establishes a persistent connection to the remote computer.</span></span>

<span data-ttu-id="0d23d-116">Verwenden Sie eine **PSSession** , um mehrere Befehle auszuführen, die Daten gemeinsam verwenden, z. b. eine Funktion oder den Wert einer Variablen.</span><span class="sxs-lookup"><span data-stu-id="0d23d-116">Use a **PSSession** to run multiple commands that share data, such as a function or the value of a variable.</span></span> <span data-ttu-id="0d23d-117">Verwenden Sie das-Cmdlet, um Befehle in einer **PSSession** auszuführen `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="0d23d-117">To run commands in a **PSSession** , use the `Invoke-Command` cmdlet.</span></span> <span data-ttu-id="0d23d-118">Verwenden Sie das-Cmdlet, um die **PSSession** direkt mit einem Remote Computer zu interagieren `Enter-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="0d23d-118">To use the **PSSession** to interact directly with a remote computer, use the `Enter-PSSession` cmdlet.</span></span> <span data-ttu-id="0d23d-119">Weitere Informationen finden Sie unter [about_PSSessions](about/about_PSSessions.md).</span><span class="sxs-lookup"><span data-stu-id="0d23d-119">For more information, see [about_PSSessions](about/about_PSSessions.md).</span></span>

<span data-ttu-id="0d23d-120">Sie können Befehle auf einem Remote Computer ausführen, ohne eine **PSSession** zu erstellen, indem Sie die **Computername** -Parameter von `Enter-PSSession` oder verwenden `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="0d23d-120">You can run commands on a remote computer without creating a **PSSession** by using the **ComputerName** parameters of `Enter-PSSession` or `Invoke-Command`.</span></span> <span data-ttu-id="0d23d-121">Wenn Sie den **Computername** -Parameter verwenden, erstellt PowerShell eine temporäre Verbindung, die für den Befehl verwendet und dann geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="0d23d-121">When you use the **ComputerName** parameter, PowerShell creates a temporary connection that is used for the command and is then closed.</span></span>

## <span data-ttu-id="0d23d-122">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="0d23d-122">EXAMPLES</span></span>

### <span data-ttu-id="0d23d-123">Beispiel 1: Erstellen einer Sitzung auf dem lokalen Computer</span><span class="sxs-lookup"><span data-stu-id="0d23d-123">Example 1: Create a session on the local computer</span></span>

```powershell
$s = New-PSSession
```

<span data-ttu-id="0d23d-124">Dieser Befehl erstellt eine neue **PSSession** auf dem lokalen Computer und speichert die **PSSession** in der `$s` Variablen.</span><span class="sxs-lookup"><span data-stu-id="0d23d-124">This command creates a new **PSSession** on the local computer and saves the **PSSession** in the `$s` variable.</span></span>

<span data-ttu-id="0d23d-125">Sie können diese **PSSession** jetzt verwenden, um Befehle auf dem lokalen Computer auszuführen.</span><span class="sxs-lookup"><span data-stu-id="0d23d-125">You can now use this **PSSession** to run commands on the local computer.</span></span>

### <span data-ttu-id="0d23d-126">Beispiel 2: Erstellen einer Sitzung auf einem Remote Computer</span><span class="sxs-lookup"><span data-stu-id="0d23d-126">Example 2: Create a session on a remote computer</span></span>

```powershell
$Server01 = New-PSSession -ComputerName Server01
```

<span data-ttu-id="0d23d-127">Dieser Befehl erstellt eine neue **PSSession** auf dem Server01-Computer und speichert Sie in der `$Server01` Variablen.</span><span class="sxs-lookup"><span data-stu-id="0d23d-127">This command creates a new **PSSession** on the Server01 computer and saves it in the `$Server01` variable.</span></span>

<span data-ttu-id="0d23d-128">Wenn Sie mehrere **PSSession** -Objekte erstellen, weisen Sie Sie Variablen mit nützlichen Namen zu.</span><span class="sxs-lookup"><span data-stu-id="0d23d-128">When creating multiple **PSSession** objects, assign them to variables with useful names.</span></span> <span data-ttu-id="0d23d-129">Dies unterstützt Sie bei der Verwaltung der **PSSession** -Objekte in nachfolgenden Befehlen.</span><span class="sxs-lookup"><span data-stu-id="0d23d-129">This will help you manage the **PSSession** objects in subsequent commands.</span></span>

### <span data-ttu-id="0d23d-130">Beispiel 3: Erstellen von Sitzungen auf mehreren Computern</span><span class="sxs-lookup"><span data-stu-id="0d23d-130">Example 3: Create sessions on multiple computers</span></span>

```powershell
$s1, $s2, $s3 = New-PSSession -ComputerName Server01,Server02,Server03
```

<span data-ttu-id="0d23d-131">Dieser Befehl erstellt drei **PSSession** -Objekte, eine auf jedem der Computer, die durch den **Computername** -Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="0d23d-131">This command creates three **PSSession** objects, one on each of the computers specified by the **ComputerName** parameter.</span></span>

<span data-ttu-id="0d23d-132">Der Befehl verwendet den Zuweisungs Operator (=), um die neuen **PSSession** -Objekte Variablen zuzuweisen: `$s1` , `$s2` , `$s3` .</span><span class="sxs-lookup"><span data-stu-id="0d23d-132">The command uses the assignment operator (=) to assign the new **PSSession** objects to variables: `$s1`, `$s2`, `$s3`.</span></span> <span data-ttu-id="0d23d-133">Dabei werden die Server01 **PSSession** `$s1` , die Server02 **PSSession** `$s2` und die Server03 **PSSession** zu zugewiesen `$s3` .</span><span class="sxs-lookup"><span data-stu-id="0d23d-133">It assigns the Server01 **PSSession** to `$s1`, the Server02 **PSSession** to `$s2`, and the Server03 **PSSession** to `$s3`.</span></span>

<span data-ttu-id="0d23d-134">Wenn Sie mehreren Objekten eine Reihe von Variablen zuweisen, weist PowerShell jedes Objekt einer Variablen in der Reihe zu.</span><span class="sxs-lookup"><span data-stu-id="0d23d-134">When you assign multiple objects to a series of variables, PowerShell assigns each object to a variable in the series respectively.</span></span> <span data-ttu-id="0d23d-135">Wenn es mehr Objekte als Variablen gibt, werden alle verbleibenden Objekte der letzten Variablen zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="0d23d-135">If there are more objects than variables, all remaining objects are assigned to the last variable.</span></span> <span data-ttu-id="0d23d-136">Wenn es mehr Variablen als Objekte gibt, sind die verbleibenden Variablen leer (null).</span><span class="sxs-lookup"><span data-stu-id="0d23d-136">If there are more variables than objects, the remaining variables are empty (null).</span></span>

### <span data-ttu-id="0d23d-137">Beispiel 4: Erstellen einer Sitzung mit einem angegebenen Port</span><span class="sxs-lookup"><span data-stu-id="0d23d-137">Example 4: Create a session with a specified port</span></span>

```powershell
New-PSSession -ComputerName Server01 -Port 8081 -UseSSL -ConfigurationName E12
```

<span data-ttu-id="0d23d-138">Dieser Befehl erstellt eine neue **PSSession** auf dem Server01-Computer, die eine Verbindung mit dem Serverport 8081 herstellt und das SSL-Protokoll verwendet.</span><span class="sxs-lookup"><span data-stu-id="0d23d-138">This command creates a new **PSSession** on the Server01 computer that connects to server port 8081 and uses the SSL protocol.</span></span> <span data-ttu-id="0d23d-139">Die neue **PSSession** verwendet eine Alternative Sitzungs Konfiguration mit dem Namen E12.</span><span class="sxs-lookup"><span data-stu-id="0d23d-139">The new **PSSession** uses an alternative session configuration called E12.</span></span>

<span data-ttu-id="0d23d-140">Bevor Sie den Port festlegen, müssen Sie den WinRM-Listener auf dem Remotecomputer zum Abhören von Port 8081 konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="0d23d-140">Before setting the port, you must configure the WinRM listener on the remote computer to listen on port 8081.</span></span> <span data-ttu-id="0d23d-141">Weitere Informationen finden Sie unter der Beschreibung des **Port** -Parameters.</span><span class="sxs-lookup"><span data-stu-id="0d23d-141">For more information, see the description of the **Port** parameter.</span></span>

### <span data-ttu-id="0d23d-142">Beispiel 5: Erstellen einer Sitzung basierend auf einer vorhandenen Sitzung</span><span class="sxs-lookup"><span data-stu-id="0d23d-142">Example 5: Create a session based on an existing session</span></span>

```powershell
New-PSSession -Session $s -Credential Domain01\User01
```

<span data-ttu-id="0d23d-143">Dieser Befehl erstellt eine **PSSession** mit denselben Eigenschaften wie eine vorhandene **PSSession**.</span><span class="sxs-lookup"><span data-stu-id="0d23d-143">This command creates a **PSSession** with the same properties as an existing **PSSession**.</span></span> <span data-ttu-id="0d23d-144">Sie können dieses Befehls Format verwenden, wenn die Ressourcen einer vorhandenen **PSSession** erschöpft sind und eine neue **PSSession** erforderlich ist, um einen Teil der Anforderung auszulagern.</span><span class="sxs-lookup"><span data-stu-id="0d23d-144">You can use this command format when the resources of an existing **PSSession** are exhausted and a new **PSSession** is needed to offload some of the demand.</span></span>

<span data-ttu-id="0d23d-145">Der Befehl verwendet den **Session** -Parameter von `New-PSSession` , um die in der Variablen gespeicherte **PSSession** anzugeben `$s` .</span><span class="sxs-lookup"><span data-stu-id="0d23d-145">The command uses the **Session** parameter of `New-PSSession` to specify the **PSSession** saved in the `$s` variable.</span></span> <span data-ttu-id="0d23d-146">Er verwendet die Anmeldeinformationen des Benutzers „Domain1\Admin01“, um den Befehl auszuführen.</span><span class="sxs-lookup"><span data-stu-id="0d23d-146">It uses the credentials of the Domain1\Admin01 user to complete the command.</span></span>

### <span data-ttu-id="0d23d-147">Beispiel 6: Erstellen einer Sitzung mit einem globalen Gültigkeitsbereich in einer anderen Domäne</span><span class="sxs-lookup"><span data-stu-id="0d23d-147">Example 6: Create a session with a global scope in a different domain</span></span>

```powershell
$global:s = New-PSSession -ComputerName Server1.Domain44.Corpnet.Fabrikam.com -Credential Domain01\Admin01
```

<span data-ttu-id="0d23d-148">Dieses Beispiel zeigt, wie Sie eine **PSSession** mit einem globalen Bereich auf einem Computer in einer anderen Domäne erstellen.</span><span class="sxs-lookup"><span data-stu-id="0d23d-148">This example shows how to create a **PSSession** with a global scope on a computer in a different domain.</span></span>

<span data-ttu-id="0d23d-149">**PSSession** -Objekte, die in der Befehlszeile erstellt werden, werden standardmäßig mit lokalem Gültigkeitsbereich erstellt, und die in einem Skript erstellten **PSSession** -Objekte verfügen über einen Skript</span><span class="sxs-lookup"><span data-stu-id="0d23d-149">By default, **PSSession** objects created at the command line are created with local scope and **PSSession** objects created in a script have script scope.</span></span>

<span data-ttu-id="0d23d-150">Um eine **PSSession** mit globalem Gültigkeitsbereich zu erstellen, erstellen Sie eine neue **PSSession** und speichern die **PSSession** in einer Variablen, die in einen globalen Gültigkeitsbereich umgewandelt wird.</span><span class="sxs-lookup"><span data-stu-id="0d23d-150">To create a **PSSession** with global scope, create a new **PSSession** and then store the **PSSession** in a variable that is cast to a global scope.</span></span> <span data-ttu-id="0d23d-151">In diesem Fall wird die `$s` Variable in einen globalen Gültigkeitsbereich umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="0d23d-151">In this case, the `$s` variable is cast to a global scope.</span></span>

<span data-ttu-id="0d23d-152">Der Befehl verwendet den **ComputerName** -Parameter, um den Remotecomputer anzugeben.</span><span class="sxs-lookup"><span data-stu-id="0d23d-152">The command uses the **ComputerName** parameter to specify the remote computer.</span></span> <span data-ttu-id="0d23d-153">Da sich der Computer in einer anderen Domäne als das Benutzerkonto befindet, wird der vollständige Name des Computers mit den Anmelde Informationen des Benutzers angegeben.</span><span class="sxs-lookup"><span data-stu-id="0d23d-153">Because the computer is in a different domain than the user account, the full name of the computer is specified together with the credentials of the user.</span></span>

### <span data-ttu-id="0d23d-154">Beispiel 7: Erstellen von Sitzungen für viele Computer</span><span class="sxs-lookup"><span data-stu-id="0d23d-154">Example 7: Create sessions for many computers</span></span>

```powershell
$rs = Get-Content C:\Test\Servers.txt | New-PSSession -ThrottleLimit 50
```

<span data-ttu-id="0d23d-155">Dieser Befehl erstellt eine **PSSession** auf jedem der 200-Computer, die in der Servers.txt-Datei aufgelistet sind, und speichert die resultierende **PSSession** in der `$rs` Variablen.</span><span class="sxs-lookup"><span data-stu-id="0d23d-155">This command creates a **PSSession** on each of the 200 computers listed in the Servers.txt file and it stores the resulting **PSSession** in the `$rs` variable.</span></span> <span data-ttu-id="0d23d-156">Die **PSSession** -Objekte haben eine Drosselungs Grenze von 50.</span><span class="sxs-lookup"><span data-stu-id="0d23d-156">The **PSSession** objects have a throttle limit of 50.</span></span>

<span data-ttu-id="0d23d-157">Sie können dieses Befehlsformat verwenden, wenn die Namen von Computern in einer Datenbank, einer Kalkulationstabelle, einer Textdatei oder in einem anderen in Text konvertierbaren Format gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="0d23d-157">You can use this command format when the names of computers are stored in a database, spreadsheet, text file, or other text-convertible format.</span></span>

### <span data-ttu-id="0d23d-158">Beispiel 8: Erstellen einer Sitzung mithilfe eines URI</span><span class="sxs-lookup"><span data-stu-id="0d23d-158">Example 8: Create a session by using a URI</span></span>

```powershell
$s = New-PSSession -URI http://Server01:91/NewSession -Credential Domain01\User01
```

<span data-ttu-id="0d23d-159">Dieser Befehl erstellt eine **PSSession** auf dem Server01-Computer und speichert Sie in der `$s` Variablen.</span><span class="sxs-lookup"><span data-stu-id="0d23d-159">This command creates a **PSSession** on the Server01 computer and stores it in the `$s` variable.</span></span> <span data-ttu-id="0d23d-160">Er verwendet den **URI** -Parameter, um das Transportprotokoll, den Remote Computer, den Port und eine Alternative Sitzungs Konfiguration anzugeben.</span><span class="sxs-lookup"><span data-stu-id="0d23d-160">It uses the **URI** parameter to specify the transport protocol, the remote computer, the port, and an alternate session configuration.</span></span> <span data-ttu-id="0d23d-161">Außerdem wird der **Credential** -Parameter verwendet, um ein Benutzerkonto anzugeben, das über die Berechtigung zum Erstellen einer Sitzung auf dem Remote Computer verfügt.</span><span class="sxs-lookup"><span data-stu-id="0d23d-161">It also uses the **Credential** parameter to specify a user account that has permission to create a session on the remote computer.</span></span>

### <span data-ttu-id="0d23d-162">Beispiel 9: Ausführen eines Hintergrund Auftrags in einer Gruppe von Sitzungen</span><span class="sxs-lookup"><span data-stu-id="0d23d-162">Example 9: Run a background job in a set of sessions</span></span>

```powershell
$s = New-PSSession -ComputerName (Get-Content Servers.txt) -Credential Domain01\Admin01 -ThrottleLimit 16
Invoke-Command -Session $s -ScriptBlock {Get-Process PowerShell} -AsJob
```

<span data-ttu-id="0d23d-163">Diese Befehle erstellen einen Satz von **PSSession** -Objekten und führen dann einen Hintergrund Auftrag in jedem der **PSSession** -Objekte aus.</span><span class="sxs-lookup"><span data-stu-id="0d23d-163">These commands create a set of **PSSession** objects and then run a background job in each of the **PSSession** objects.</span></span>

<span data-ttu-id="0d23d-164">Der erste Befehl erstellt eine neue **PSSession** auf jedem der Computer, die in der Servers.txt-Datei aufgelistet sind.</span><span class="sxs-lookup"><span data-stu-id="0d23d-164">The first command creates a new **PSSession** on each of the computers listed in the Servers.txt file.</span></span> <span data-ttu-id="0d23d-165">Er verwendet das `New-PSSession` Cmdlet, um die **PSSession** zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0d23d-165">It uses the `New-PSSession` cmdlet to create the **PSSession**.</span></span> <span data-ttu-id="0d23d-166">Der Wert des **Computername** -Parameters ist ein Befehl, der das `Get-Content` Cmdlet verwendet, um die Liste der Computernamen der Servers.txt Datei zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="0d23d-166">The value of the **ComputerName** parameter is a command that uses the `Get-Content` cmdlet to get the list of computer names the Servers.txt file.</span></span>

<span data-ttu-id="0d23d-167">Der Befehl verwendet den **Credential** -Parameter, um die **PSSession** -Objekte zu erstellen, die über die Berechtigung eines Domänen Administrators verfügen, und verwendet den **throttlelimit** -Parameter, um den Befehl auf 16 gleichzeitige Verbindungen zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="0d23d-167">The command uses the **Credential** parameter to create the **PSSession** objects that have the permission of a domain administrator, and it uses the **ThrottleLimit** parameter to limit the command to 16 concurrent connections.</span></span> <span data-ttu-id="0d23d-168">Der Befehl speichert die **PSSession** -Objekte in der `$s` Variablen.</span><span class="sxs-lookup"><span data-stu-id="0d23d-168">The command saves the **PSSession** objects in the `$s` variable.</span></span>

<span data-ttu-id="0d23d-169">Der zweite Befehl verwendet den **AsJob** -Parameter des `Invoke-Command` Cmdlets, um einen Hintergrund Auftrag zu starten, der einen `Get-Process PowerShell` Befehl in jedem der **PSSession** -Objekte in ausführt `$s` .</span><span class="sxs-lookup"><span data-stu-id="0d23d-169">The second command uses the **AsJob** parameter of the `Invoke-Command` cmdlet to start a background job that runs a `Get-Process PowerShell` command in each of the **PSSession** objects in `$s`.</span></span>

<span data-ttu-id="0d23d-170">Weitere Informationen zu PowerShell-Hintergrund Aufträgen finden Sie unter [about_Jobs](About/about_Jobs.md) und [about_Remote_Jobs](About/about_Remote_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="0d23d-170">For more information about PowerShell background jobs, see [about_Jobs](About/about_Jobs.md) and [about_Remote_Jobs](About/about_Remote_Jobs.md).</span></span>

### <span data-ttu-id="0d23d-171">Beispiel 10: Erstellen einer Sitzung für einen Computer mithilfe seines URI</span><span class="sxs-lookup"><span data-stu-id="0d23d-171">Example 10: Create a session for a computer by using its URI</span></span>

```powershell
New-PSSession -ConnectionURI https://management.exchangelabs.com/Management
```

<span data-ttu-id="0d23d-172">Mit diesem Befehl werden **PSSession** -Objekte erstellt, die eine Verbindung mit einem Computer herstellen, der durch einen URI anstelle eines Computer namens angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="0d23d-172">This command creates a **PSSession** objects that connects to a computer that is specified by a URI instead of a computer name.</span></span>

### <span data-ttu-id="0d23d-173">Beispiel 11: Erstellen einer Sitzungs Option</span><span class="sxs-lookup"><span data-stu-id="0d23d-173">Example 11: Create a session option</span></span>

```powershell
$so = New-PSSessionOption -SkipCACheck
New-PSSession -ConnectionUri https://management.exchangelabs.com/Management -SessionOption $so -Credential Server01\Admin01
```

<span data-ttu-id="0d23d-174">Dieses Beispiel zeigt, wie ein Sitzungs Options Objekt erstellt und der **sessionoption** -Parameter verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0d23d-174">This example shows how to create a session option object and use the **SessionOption** parameter.</span></span>

<span data-ttu-id="0d23d-175">Der erste Befehl verwendet das `New-PSSessionOption` Cmdlet zum Erstellen einer Sitzungs Option.</span><span class="sxs-lookup"><span data-stu-id="0d23d-175">The first command uses the `New-PSSessionOption` cmdlet to create a session option.</span></span> <span data-ttu-id="0d23d-176">Das resultierende **sessionoption** -Objekt wird in der `$so` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="0d23d-176">It saves the resulting **SessionOption** object in the `$so` variable.</span></span>

<span data-ttu-id="0d23d-177">Der zweite Befehl verwendet die Option in einer neuen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="0d23d-177">The second command uses the option in a new session.</span></span> <span data-ttu-id="0d23d-178">Der Befehl verwendet das `New-PSSession` Cmdlet, um eine neue Sitzung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0d23d-178">The command uses the `New-PSSession` cmdlet to create a new session.</span></span> <span data-ttu-id="0d23d-179">Der Wert des sessionoption-Parameters ist das **sessionoption** -Objekt in der `$so` Variablen.</span><span class="sxs-lookup"><span data-stu-id="0d23d-179">The value of the SessionOption parameter is the **SessionOption** object in the `$so` variable.</span></span>

## <span data-ttu-id="0d23d-180">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0d23d-180">PARAMETERS</span></span>

### <span data-ttu-id="0d23d-181">-Zuweisung Richtung</span><span class="sxs-lookup"><span data-stu-id="0d23d-181">-AllowRedirection</span></span>

<span data-ttu-id="0d23d-182">Gibt an, dass dieses Cmdlet die Umleitung dieser Verbindung an eine Alternative Uniform Resource Identifier (URI) zulässt.</span><span class="sxs-lookup"><span data-stu-id="0d23d-182">Indicates that this cmdlet allows redirection of this connection to an alternate Uniform Resource Identifier (URI).</span></span>

<span data-ttu-id="0d23d-183">Bei Verwendung des **ConnectionURI** -Parameters kann das Remoteziel eine Anweisung zum Umleiten an einen anderen URI zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="0d23d-183">When you use the **ConnectionURI** parameter, the remote destination can return an instruction to redirect to a different URI.</span></span> <span data-ttu-id="0d23d-184">Standardmäßig werden Verbindungen von PowerShell nicht umgeleitet, aber Sie können diesen Parameter verwenden, um eine Umleitung der Verbindung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="0d23d-184">By default, PowerShell does not redirect connections, but you can use this parameter to enable it to redirect the connection.</span></span>

<span data-ttu-id="0d23d-185">Sie können auch einschränken, wie oft die Verbindung umgeleitet wird, indem Sie den **MaximumConnectionRedirectionCount** -Optionswert der Sitzung ändern.</span><span class="sxs-lookup"><span data-stu-id="0d23d-185">You can also limit the number of times the connection is redirected by changing the **MaximumConnectionRedirectionCount** session option value.</span></span> <span data-ttu-id="0d23d-186">Verwenden Sie den **maximumredirect** -Parameter des `New-PSSessionOption` Cmdlets, oder legen Sie die **maximumconnectionredirectioncount** -Eigenschaft der **$PSSessionOption** Preference-Variablen fest.</span><span class="sxs-lookup"><span data-stu-id="0d23d-186">Use the **MaximumRedirection** parameter of the `New-PSSessionOption` cmdlet or set the **MaximumConnectionRedirectionCount** property of the **$PSSessionOption** preference variable.</span></span> <span data-ttu-id="0d23d-187">Der Standardwert ist 5.</span><span class="sxs-lookup"><span data-stu-id="0d23d-187">The default value is 5.</span></span>

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

### <span data-ttu-id="0d23d-188">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="0d23d-188">-ApplicationName</span></span>

<span data-ttu-id="0d23d-189">Gibt das Anwendungsnamenssegment des Verbindungs-URI an.</span><span class="sxs-lookup"><span data-stu-id="0d23d-189">Specifies the application name segment of the connection URI.</span></span> <span data-ttu-id="0d23d-190">Mit diesem Parameter können Sie den Anwendungsnamen angeben, wenn Sie den **ConnectionURI** -Parameter im Befehl nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="0d23d-190">Use this parameter to specify the application name when you are not using the **ConnectionURI** parameter in the command.</span></span>

<span data-ttu-id="0d23d-191">Der Standardwert ist der Wert der Einstellungs `$PSSessionApplicationName` Variablen auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="0d23d-191">The default value is the value of the `$PSSessionApplicationName` preference variable on the local computer.</span></span> <span data-ttu-id="0d23d-192">Wenn diese Einstellungsvariable nicht definiert ist, ist der Standardwert „WSMan“.</span><span class="sxs-lookup"><span data-stu-id="0d23d-192">If this preference variable is not defined, the default value is WSMAN.</span></span> <span data-ttu-id="0d23d-193">Dieser Wert ist für die meisten Verwendungsarten geeignet.</span><span class="sxs-lookup"><span data-stu-id="0d23d-193">This value is appropriate for most uses.</span></span> <span data-ttu-id="0d23d-194">Weitere Informationen finden Sie unter [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="0d23d-194">For more information, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="0d23d-195">Der WinRM-Dienst wählt mit dem Anwendungsnamen einen Listener für die Verbindungsanforderung aus.</span><span class="sxs-lookup"><span data-stu-id="0d23d-195">The WinRM service uses the application name to select a listener to service the connection request.</span></span>
<span data-ttu-id="0d23d-196">Der Wert dieses Parameters sollte mit dem Wert der **URLPrefix** -Eigenschaft eines Listeners auf dem Remotecomputer übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="0d23d-196">The value of this parameter should match the value of the **URLPrefix** property of a listener on the remote computer.</span></span>

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

### <span data-ttu-id="0d23d-197">-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="0d23d-197">-Authentication</span></span>

<span data-ttu-id="0d23d-198">Gibt den Mechanismus an, der zum Authentifizieren der Anmeldeinformationen des Benutzers verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0d23d-198">Specifies the mechanism that is used to authenticate the user's credentials.</span></span>
<span data-ttu-id="0d23d-199">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="0d23d-199">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="0d23d-200">Standard</span><span class="sxs-lookup"><span data-stu-id="0d23d-200">Default</span></span>
- <span data-ttu-id="0d23d-201">Basic</span><span class="sxs-lookup"><span data-stu-id="0d23d-201">Basic</span></span>
- <span data-ttu-id="0d23d-202">CredSSP</span><span class="sxs-lookup"><span data-stu-id="0d23d-202">Credssp</span></span>
- <span data-ttu-id="0d23d-203">Digest</span><span class="sxs-lookup"><span data-stu-id="0d23d-203">Digest</span></span>
- <span data-ttu-id="0d23d-204">Kerberos</span><span class="sxs-lookup"><span data-stu-id="0d23d-204">Kerberos</span></span>
- <span data-ttu-id="0d23d-205">Aushandeln</span><span class="sxs-lookup"><span data-stu-id="0d23d-205">Negotiate</span></span>
- <span data-ttu-id="0d23d-206">NegotiateWithImplicitCredential</span><span class="sxs-lookup"><span data-stu-id="0d23d-206">NegotiateWithImplicitCredential</span></span>

<span data-ttu-id="0d23d-207">Der Standardwert ist Default.</span><span class="sxs-lookup"><span data-stu-id="0d23d-207">The default value is Default.</span></span>

<span data-ttu-id="0d23d-208">Weitere Informationen zu den Werten dieses Parameters finden Sie unter [authenticationmechanism-Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span><span class="sxs-lookup"><span data-stu-id="0d23d-208">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!CAUTION]
> <span data-ttu-id="0d23d-209">Die Authentifizierung der Credential Security Support Provider (kredssp), bei der die Anmelde Informationen des Benutzers an einen Remote Computer übergeben werden, der authentifiziert werden soll, wurde für Befehle entworfen, die eine Authentifizierung auf mehr als einer Ressource erfordern, z. b. den Zugriff auf eine Remote Netzwerkfreigabe.</span><span class="sxs-lookup"><span data-stu-id="0d23d-209">Credential Security Support Provider (CredSSP) authentication, in which the user credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="0d23d-210">Dieser Mechanismus erhöht das Sicherheitsrisiko des Remotevorgangs.</span><span class="sxs-lookup"><span data-stu-id="0d23d-210">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="0d23d-211">Wenn die Sicherheit des Remotecomputers gefährdet ist, können die an ihn übergebenen Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0d23d-211">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

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

### <span data-ttu-id="0d23d-212">-Certifiupethumschlag-Print</span><span class="sxs-lookup"><span data-stu-id="0d23d-212">-CertificateThumbprint</span></span>

<span data-ttu-id="0d23d-213">Gibt das digitale Zertifikat für öffentliche Schlüssel (X509) eines Benutzerkontos an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="0d23d-213">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span> <span data-ttu-id="0d23d-214">Geben Sie den Zertifikatfingerabdruck des Zertifikats ein.</span><span class="sxs-lookup"><span data-stu-id="0d23d-214">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="0d23d-215">Zertifikate werden bei der clientzertifikatbasierten Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="0d23d-215">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="0d23d-216">Sie können nur lokalen Benutzerkonten zugeordnet werden und funktionieren nicht mit Domänenkonten.</span><span class="sxs-lookup"><span data-stu-id="0d23d-216">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="0d23d-217">Um ein Zertifikat zu erhalten, verwenden Sie den `Get-Item` `Get-ChildItem` Befehl oder im PowerShell-Laufwerk "CERT:".</span><span class="sxs-lookup"><span data-stu-id="0d23d-217">To get a certificate, use the `Get-Item` or `Get-ChildItem` command in the PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="0d23d-218">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="0d23d-218">-ComputerName</span></span>

<span data-ttu-id="0d23d-219">Gibt ein Array von Namen von Computern an.</span><span class="sxs-lookup"><span data-stu-id="0d23d-219">Specifies an array of names of computers.</span></span> <span data-ttu-id="0d23d-220">Dieses Cmdlet erstellt eine permanente Verbindung ( **PSSession** ) mit dem angegebenen Computer.</span><span class="sxs-lookup"><span data-stu-id="0d23d-220">This cmdlet creates a persistent connection ( **PSSession** ) to the specified computer.</span></span> <span data-ttu-id="0d23d-221">Wenn Sie mehrere Computernamen eingeben, `New-PSSession` erstellt mehrere **PSSession** -Objekte, eine für jeden Computer.</span><span class="sxs-lookup"><span data-stu-id="0d23d-221">If you enter multiple computer names, `New-PSSession` creates multiple **PSSession** objects, one for each computer.</span></span> <span data-ttu-id="0d23d-222">Die Standardeinstellung ist der lokale Computer.</span><span class="sxs-lookup"><span data-stu-id="0d23d-222">The default is the local computer.</span></span>

<span data-ttu-id="0d23d-223">Geben Sie den NetBIOS-Namen, eine IP-Adresse oder den vollqualifizierten Domänennamen mindestens eines Computers ein.</span><span class="sxs-lookup"><span data-stu-id="0d23d-223">Type the NetBIOS name, an IP address, or a fully qualified domain name of one or more remote computers.</span></span> <span data-ttu-id="0d23d-224">Um den lokalen Computer anzugeben, geben Sie den Computernamen, "localhost" oder einen Punkt (.) ein.</span><span class="sxs-lookup"><span data-stu-id="0d23d-224">To specify the local computer, type the computer name, localhost, or a dot (.).</span></span> <span data-ttu-id="0d23d-225">Wenn sich der Remotecomputer in einer anderen Domäne als der Benutzer befindet, ist der vollqualifizierte Domänenname erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0d23d-225">When the computer is in a different domain than the user, the fully qualified domain name is required.</span></span> <span data-ttu-id="0d23d-226">Sie können einen Computernamen (in Anführungszeichen) auch über die Pipeline an übergeben `New-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="0d23d-226">You can also pipe a computer name, in quotation marks, to `New-PSSession`.</span></span>

<span data-ttu-id="0d23d-227">Um eine IP-Adresse im Wert des **Computername** -Parameters zu verwenden, muss der Befehl den **Credential** -Parameter enthalten.</span><span class="sxs-lookup"><span data-stu-id="0d23d-227">To use an IP address in the value of the **ComputerName** parameter, the command must include the **Credential** parameter.</span></span> <span data-ttu-id="0d23d-228">Außerdem muss der Computer für den HTTPS-Transport konfiguriert sein, oder die IP-Adresse des Remotecomputers muss in der WinRM TrustedHosts-Liste auf dem lokalen Computer enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="0d23d-228">Also, the computer must be configured for HTTPS transport or the IP address of the remote computer must be included in the WinRM TrustedHosts list on the local computer.</span></span> <span data-ttu-id="0d23d-229">Anweisungen zum Hinzufügen eines Computer namens zur Liste "Treuhänder Hosts" finden Sie unter "Vorgehensweise beim Hinzufügen eines Computers zur Liste vertrauenswürdiger Hosts" in [about_Remote_Troubleshooting](about/about_Remote_Troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="0d23d-229">For instructions for adding a computer name to the TrustedHosts list, see "How to Add a Computer to the Trusted Host List" in [about_Remote_Troubleshooting](about/about_Remote_Troubleshooting.md).</span></span>

<span data-ttu-id="0d23d-230">Um den lokalen Computer in den Wert des **Computername** -Parameters einzuschließen, starten Sie Windows PowerShell mit der Option als Administrator ausführen.</span><span class="sxs-lookup"><span data-stu-id="0d23d-230">To include the local computer in the value of the **ComputerName** parameter, start Windows PowerShell by using the Run as administrator option.</span></span>

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

### <span data-ttu-id="0d23d-231">-ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="0d23d-231">-ConfigurationName</span></span>

<span data-ttu-id="0d23d-232">Gibt die Sitzungs Konfiguration an, die für die neue **PSSession** verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0d23d-232">Specifies the session configuration that is used for the new **PSSession**.</span></span>

<span data-ttu-id="0d23d-233">Geben Sie einen Konfigurationsnamen oder den vollqualifizierten Ressourcen-URI für eine Sitzungskonfiguration ein.</span><span class="sxs-lookup"><span data-stu-id="0d23d-233">Enter a configuration name or the fully qualified resource URI for a session configuration.</span></span> <span data-ttu-id="0d23d-234">Wenn Sie nur den Konfigurations Namen angeben, wird der folgende Schema-URI vorangestellt: `http://schemas.microsoft.com/PowerShell` .</span><span class="sxs-lookup"><span data-stu-id="0d23d-234">If you specify only the configuration name, the following schema URI is prepended: `http://schemas.microsoft.com/PowerShell`.</span></span>

<span data-ttu-id="0d23d-235">Die Sitzungskonfiguration für eine Sitzung befindet sich auf dem Remotecomputer.</span><span class="sxs-lookup"><span data-stu-id="0d23d-235">The session configuration for a session is located on the remote computer.</span></span> <span data-ttu-id="0d23d-236">Wenn die angegebene Sitzungskonfiguration auf dem Remotecomputer nicht vorhanden ist, führt der Befehl zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="0d23d-236">If the specified session configuration does not exist on the remote computer, the command fails.</span></span>

<span data-ttu-id="0d23d-237">Der Standardwert ist der Wert der Einstellungs `$PSSessionConfigurationName` Variablen auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="0d23d-237">The default value is the value of the `$PSSessionConfigurationName` preference variable on the local computer.</span></span> <span data-ttu-id="0d23d-238">Wenn diese Einstellungsvariable nicht festgelegt ist, ist die Standardeinstellung „Microsoft.PowerShell“.</span><span class="sxs-lookup"><span data-stu-id="0d23d-238">If this preference variable is not set, the default is Microsoft.PowerShell.</span></span> <span data-ttu-id="0d23d-239">Weitere Informationen finden Sie unter [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="0d23d-239">For more information, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

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

### <span data-ttu-id="0d23d-240">-ConnectionUri</span><span class="sxs-lookup"><span data-stu-id="0d23d-240">-ConnectionUri</span></span>

<span data-ttu-id="0d23d-241">Gibt einen URI an, der den Verbindungs Endpunkt für die Sitzung definiert.</span><span class="sxs-lookup"><span data-stu-id="0d23d-241">Specifies a URI that defines the connection endpoint for the session.</span></span> <span data-ttu-id="0d23d-242">Der URI muss vollqualifiziert sein.</span><span class="sxs-lookup"><span data-stu-id="0d23d-242">The URI must be fully qualified.</span></span> <span data-ttu-id="0d23d-243">Das Format dieser Zeichenfolge lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="0d23d-243">The format of this string is as follows:</span></span>

`<Transport>://<ComputerName>:<Port>/<ApplicationName>`

<span data-ttu-id="0d23d-244">Der Standardwert lautet:</span><span class="sxs-lookup"><span data-stu-id="0d23d-244">The default value is as follows:</span></span>

`http://localhost:5985/WSMAN`

<span data-ttu-id="0d23d-245">Wenn Sie keinen **ConnectionURI** angeben, können Sie die Parameter **UseSSL** , **ComputerName** , **Port** und **ApplicationName** zur Angabe der **ConnectionURI** -Werte verwenden.</span><span class="sxs-lookup"><span data-stu-id="0d23d-245">If you do not specify a **ConnectionURI** , you can use the **UseSSL** , **ComputerName** , **Port** , and **ApplicationName** parameters to specify the **ConnectionURI** values.</span></span>

<span data-ttu-id="0d23d-246">Gültige Werte für das Transport-Segment des URI sind „HTTP“ und „HTTPS“.</span><span class="sxs-lookup"><span data-stu-id="0d23d-246">Valid values for the Transport segment of the URI are HTTP and HTTPS.</span></span> <span data-ttu-id="0d23d-247">Wenn Sie einen Verbindungs-URI mit einem Transport Segment angeben, aber keinen Port angeben, wird die Sitzung mit Standardports erstellt: 80 für http und 443 für HTTPS.</span><span class="sxs-lookup"><span data-stu-id="0d23d-247">If you specify a connection URI with a Transport segment, but do not specify a port, the session is created with standards ports: 80 for HTTP and 443 for HTTPS.</span></span> <span data-ttu-id="0d23d-248">Wenn Sie die Standardports für PowerShell-Remoting verwenden möchten, geben Sie Port 5985 für http oder 5986 für HTTPS an.</span><span class="sxs-lookup"><span data-stu-id="0d23d-248">To use the default ports for PowerShell remoting, specify port 5985 for HTTP or 5986 for HTTPS.</span></span>

<span data-ttu-id="0d23d-249">Wenn der Zielcomputer die Verbindung an einen anderen URI umleitet, verhindert PowerShell die Umleitung, es sei denn, Sie verwenden den Parameter " **Zuweisung** " im Befehl.</span><span class="sxs-lookup"><span data-stu-id="0d23d-249">If the destination computer redirects the connection to a different URI, PowerShell prevents the redirection unless you use the **AllowRedirection** parameter in the command.</span></span>

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

### <span data-ttu-id="0d23d-250">-Containerid</span><span class="sxs-lookup"><span data-stu-id="0d23d-250">-ContainerId</span></span>

<span data-ttu-id="0d23d-251">Gibt ein Array von IDs von Containern an.</span><span class="sxs-lookup"><span data-stu-id="0d23d-251">Specifies an array of IDs of containers.</span></span> <span data-ttu-id="0d23d-252">Mit diesem Cmdlet wird eine interaktive Sitzung mit jedem der angegebenen Container gestartet.</span><span class="sxs-lookup"><span data-stu-id="0d23d-252">This cmdlet starts an interactive session with each of the specified containers.</span></span> <span data-ttu-id="0d23d-253">Verwenden Sie den `docker ps` Befehl, um eine Liste der Container-IDs abzurufen.</span><span class="sxs-lookup"><span data-stu-id="0d23d-253">Use the `docker ps` command to get a list of container IDs.</span></span> <span data-ttu-id="0d23d-254">Weitere Informationen finden Sie in der Hilfe zum [docker PS](https://docs.docker.com/engine/reference/commandline/ps/) -Befehl.</span><span class="sxs-lookup"><span data-stu-id="0d23d-254">For more information, see the help for the [docker ps](https://docs.docker.com/engine/reference/commandline/ps/) command.</span></span>

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

### <span data-ttu-id="0d23d-255">-Credential</span><span class="sxs-lookup"><span data-stu-id="0d23d-255">-Credential</span></span>

<span data-ttu-id="0d23d-256">Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="0d23d-256">Specifies a user account that has permission to do this action.</span></span> <span data-ttu-id="0d23d-257">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="0d23d-257">The default is the current user.</span></span>

<span data-ttu-id="0d23d-258">Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01** , oder geben Sie ein **PSCredential** -Objekt ein, das vom `Get-Credential` Cmdlet generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="0d23d-258">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="0d23d-259">Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe des Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="0d23d-259">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="0d23d-260">Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.</span><span class="sxs-lookup"><span data-stu-id="0d23d-260">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="0d23d-261">Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="0d23d-261">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="0d23d-262">-Enablenetworkaccess</span><span class="sxs-lookup"><span data-stu-id="0d23d-262">-EnableNetworkAccess</span></span>

<span data-ttu-id="0d23d-263">Gibt an, dass mit diesem Cmdlet Loopback Sitzungen ein interaktives Sicherheits Token hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="0d23d-263">Indicates that this cmdlet adds an interactive security token to loopback sessions.</span></span> <span data-ttu-id="0d23d-264">Mit dem interaktiven Token können Sie die Befehle in der Loopbacksitzung ausführen, um Daten von anderen Computern abzurufen.</span><span class="sxs-lookup"><span data-stu-id="0d23d-264">The interactive token lets you run commands in the loopback session that get data from other computers.</span></span> <span data-ttu-id="0d23d-265">Beispielsweise können Sie einen Befehl in der Sitzung ausführen, mit dem XML-Dateien von einem Remotecomputer auf den lokalen Computer kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="0d23d-265">For example, you can run a command in the session that copies XML files from a remote computer to the local computer.</span></span>

<span data-ttu-id="0d23d-266">Eine Loopback Sitzung ist eine **PSSession** , die auf demselben computerbasiert und endet.</span><span class="sxs-lookup"><span data-stu-id="0d23d-266">A loopback session is a **PSSession** that originates and ends on the same computer.</span></span> <span data-ttu-id="0d23d-267">Um eine Loopback Sitzung zu erstellen, lassen Sie den **Computername** -Parameter aus, oder legen Sie seinen Wert auf "dot (.)", "localhost" oder den Namen des lokalen Computers fest.</span><span class="sxs-lookup"><span data-stu-id="0d23d-267">To create a loopback session, omit the **ComputerName** parameter or set its value to dot (.), localhost, or the name of the local computer.</span></span>

<span data-ttu-id="0d23d-268">Standardmäßig erstellt dieses Cmdlet Loopback Sitzungen mithilfe eines Netzwerk Tokens, das möglicherweise nicht über ausreichende Berechtigungen zum Authentifizieren bei Remote Computern verfügt.</span><span class="sxs-lookup"><span data-stu-id="0d23d-268">By default, this cmdlet creates loopback sessions by using a network token, which might not provide sufficient permission to authenticate to remote computers.</span></span>

<span data-ttu-id="0d23d-269">Der **EnableNetworkAccess** -Parameter ist nur bei Loopbacksitzungen wirksam.</span><span class="sxs-lookup"><span data-stu-id="0d23d-269">The **EnableNetworkAccess** parameter is effective only in loopback sessions.</span></span> <span data-ttu-id="0d23d-270">Wenn Sie **enablenetworkaccess** verwenden, wenn Sie eine Sitzung auf einem Remote Computer erstellen, ist der Befehl erfolgreich, aber der-Parameter wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="0d23d-270">If you use **EnableNetworkAccess** when you create a session on a remote computer, the command succeeds, but the parameter is ignored.</span></span>

<span data-ttu-id="0d23d-271">Sie können den Remote Zugriff auch in einer Loopback Sitzung aktivieren, indem Sie den Wert "kredssp" des Parameters " **Authentication** " verwenden, der die Sitzungs Anmelde Informationen an andere Computer delegiert.</span><span class="sxs-lookup"><span data-stu-id="0d23d-271">You can also enable remote access in a loopback session by using the CredSSP value of the **Authentication** parameter, which delegates the session credentials to other computers.</span></span>

<span data-ttu-id="0d23d-272">Um den Computer vor böswilligem Zugriff zu schützen, können getrennte Loopback Sitzungen mit interaktiven Tokens, die mit dem **enablenetworkaccess** -Parameter erstellt werden, nur von dem Computer wieder hergestellt werden, auf dem die Sitzung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="0d23d-272">To protect the computer from malicious access, disconnected loopback sessions that have interactive tokens, which are those created by using the **EnableNetworkAccess** parameter, can be reconnected only from the computer on which the session was created.</span></span> <span data-ttu-id="0d23d-273">Die Verbindung von getrennten Sitzungen, die die CredSSP-Authentifizierung verwenden, kann von anderen Computern wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="0d23d-273">Disconnected sessions that use CredSSP authentication can be reconnected from other computers.</span></span> <span data-ttu-id="0d23d-274">Weitere Informationen finden Sie unter `Disconnect-PSSession`.</span><span class="sxs-lookup"><span data-stu-id="0d23d-274">For more information, see `Disconnect-PSSession`.</span></span>

<span data-ttu-id="0d23d-275">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="0d23d-275">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="0d23d-276">-Name</span><span class="sxs-lookup"><span data-stu-id="0d23d-276">-Name</span></span>

<span data-ttu-id="0d23d-277">Gibt einen anzeigen Amen für die **PSSession** an.</span><span class="sxs-lookup"><span data-stu-id="0d23d-277">Specifies a friendly name for the **PSSession**.</span></span>

<span data-ttu-id="0d23d-278">Sie können den Namen verwenden, um auf die **PSSession** zu verweisen, wenn Sie andere Cmdlets verwenden, z `Get-PSSession` `Enter-PSSession` . b. und.</span><span class="sxs-lookup"><span data-stu-id="0d23d-278">You can use the name to refer to the **PSSession** when you use other cmdlets, such as `Get-PSSession` and `Enter-PSSession`.</span></span> <span data-ttu-id="0d23d-279">Der Name muss für den Computer oder die aktuelle Sitzung nicht eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="0d23d-279">The name is not required to be unique to the computer or the current session.</span></span>

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

### <span data-ttu-id="0d23d-280">-Port</span><span class="sxs-lookup"><span data-stu-id="0d23d-280">-Port</span></span>

<span data-ttu-id="0d23d-281">Gibt den Netzwerkport an dem für diese Verbindung verwendeten Remotecomputer an.</span><span class="sxs-lookup"><span data-stu-id="0d23d-281">Specifies the network port on the remote computer that is used for this connection.</span></span> <span data-ttu-id="0d23d-282">Zum Herstellen einer Verbindung mit einem Remotecomputer muss der Remotecomputer den für die Verbindung verwendeten Port abhören.</span><span class="sxs-lookup"><span data-stu-id="0d23d-282">To connect to a remote computer, the remote computer must be listening on the port that the connection uses.</span></span> <span data-ttu-id="0d23d-283">Die Standardports sind 5985. Dies ist der WinRM-Port für http und 5986 (der WinRM-Port für HTTPS).</span><span class="sxs-lookup"><span data-stu-id="0d23d-283">The default ports are 5985, which is the WinRM port for HTTP, and 5986, which is the WinRM port for HTTPS.</span></span>

<span data-ttu-id="0d23d-284">Bevor Sie einen anderen Port verwenden, müssen Sie den WinRM-Listener auf dem Remote Computer so konfigurieren, dass er an diesem Port lauscht.</span><span class="sxs-lookup"><span data-stu-id="0d23d-284">Before using another port, you must configure the WinRM listener on the remote computer to listen at that port.</span></span> <span data-ttu-id="0d23d-285">Verwenden Sie die folgenden Befehle, um den Listener zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="0d23d-285">Use the following commands to configure the listener:</span></span>

1. `winrm delete winrm/config/listener?Address=*+Transport=HTTP`
2. `winrm create winrm/config/listener?Address=*+Transport=HTTP @{Port="\<port-number\>"}`

<span data-ttu-id="0d23d-286">Verwenden Sie den **Port** -Parameter nur, wenn es unbedingt notwendig ist.</span><span class="sxs-lookup"><span data-stu-id="0d23d-286">Do not use the **Port** parameter unless you must.</span></span> <span data-ttu-id="0d23d-287">Die Porteinstellung im Befehl gilt für alle Computer oder Sitzungen, für die der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0d23d-287">The port setting in the command applies to all computers or sessions on which the command runs.</span></span> <span data-ttu-id="0d23d-288">Eine alternative Porteinstellung kann verhindern, dass der Befehl auf allen Computern ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0d23d-288">An alternate port setting might prevent the command from running on all computers.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0d23d-289">-Runasadministrator</span><span class="sxs-lookup"><span data-stu-id="0d23d-289">-RunAsAdministrator</span></span>

<span data-ttu-id="0d23d-290">Gibt an, dass die **PSSession** als Administrator ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0d23d-290">Indicates that the **PSSession** runs as administrator.</span></span>

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

### <span data-ttu-id="0d23d-291">-Sitzung</span><span class="sxs-lookup"><span data-stu-id="0d23d-291">-Session</span></span>

<span data-ttu-id="0d23d-292">Gibt ein Array von **PSSession** -Objekten an, die von diesem Cmdlet als Modell für die neue **PSSession** verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0d23d-292">Specifies an array of **PSSession** objects that this cmdlet uses as a model for the new **PSSession**.</span></span> <span data-ttu-id="0d23d-293">Dieser Parameter erstellt neue **PSSession** -Objekte, die über die gleichen Eigenschaften wie die angegebenen **PSSession** -Objekte verfügen.</span><span class="sxs-lookup"><span data-stu-id="0d23d-293">This parameter creates new **PSSession** objects that have the same properties as the specified **PSSession** objects.</span></span>

<span data-ttu-id="0d23d-294">Geben Sie eine Variable ein, die die **PSSession** -Objekte enthält, oder einen Befehl, der die **PSSession** -Objekte erstellt oder abruft, z `New-PSSession` . b. den `Get-PSSession` Befehl oder.</span><span class="sxs-lookup"><span data-stu-id="0d23d-294">Enter a variable that contains the **PSSession** objects or a command that creates or gets the **PSSession** objects, such as a `New-PSSession` or `Get-PSSession` command.</span></span>

<span data-ttu-id="0d23d-295">Die resultierenden **PSSession** -Objekte haben den gleichen Computernamen, Anwendungsnamen, Verbindungs-URI, Port, Konfigurations Namen, Drosselungs Grenzwert und Secure Sockets Layer (SSL)-Wert wie die originale, aber Sie haben einen anderen anzeigen Amen, eine andere ID und Instanz-ID (GUID).</span><span class="sxs-lookup"><span data-stu-id="0d23d-295">The resulting **PSSession** objects have the same computer name, application name, connection URI, port, configuration name, throttle limit, and Secure Sockets Layer (SSL) value as the originals, but they have a different display name, ID, and instance ID (GUID).</span></span>

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

### <span data-ttu-id="0d23d-296">-Sessionoption</span><span class="sxs-lookup"><span data-stu-id="0d23d-296">-SessionOption</span></span>

<span data-ttu-id="0d23d-297">Gibt erweiterte Optionen für die Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="0d23d-297">Specifies advanced options for the session.</span></span> <span data-ttu-id="0d23d-298">Geben Sie ein **sessionoption** -Objekt ein, z. b. ein Objekt, das Sie mit dem `New-PSSessionOption` Cmdlet erstellen, oder eine Hash Tabelle, in der die Schlüssel Sitzungs Optionsnamen und die Werte Sitzungs Optionswerte sind.</span><span class="sxs-lookup"><span data-stu-id="0d23d-298">Enter a **SessionOption** object, such as one that you create by using the `New-PSSessionOption` cmdlet, or a hash table in which the keys are session option names and the values are session option values.</span></span>

<span data-ttu-id="0d23d-299">Die Standardwerte für die Optionen werden durch den Wert der Einstellungs `$PSSessionOption` Variablen bestimmt, sofern festgelegt.</span><span class="sxs-lookup"><span data-stu-id="0d23d-299">The default values for the options are determined by the value of the `$PSSessionOption` preference variable, if it is set.</span></span> <span data-ttu-id="0d23d-300">Andernfalls werden die Standardwerte durch Optionen festgelegt, die in der Sitzungskonfiguration festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="0d23d-300">Otherwise, the default values are established by options set in the session configuration.</span></span>

<span data-ttu-id="0d23d-301">Die Sitzungs Optionswerte haben Vorrang vor Standardwerten für Sitzungen, die in der `$PSSessionOption` Preference-Variablen und in der Sitzungs Konfiguration festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="0d23d-301">The session option values take precedence over default values for sessions set in the `$PSSessionOption` preference variable and in the session configuration.</span></span> <span data-ttu-id="0d23d-302">Allerdings haben sie nicht Vorrang vor Höchstwerten, Kontingenten oder Grenzwerten, die in der Sitzungskonfiguration festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="0d23d-302">However, they do not take precedence over maximum values, quotas or limits set in the session configuration.</span></span>

<span data-ttu-id="0d23d-303">Eine Beschreibung der Sitzungs Optionen, die die Standardwerte enthalten, finden Sie unter `New-PSSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="0d23d-303">For a description of the session options that includes the default values, see `New-PSSessionOption`.</span></span> <span data-ttu-id="0d23d-304">Weitere Informationen zur Einstellungs `$PSSessionOption` Variablen finden Sie unter [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="0d23d-304">For information about the `$PSSessionOption` preference variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span> <span data-ttu-id="0d23d-305">Weitere Informationen zu Sitzungs Konfigurationen finden Sie unter [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="0d23d-305">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

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

### <span data-ttu-id="0d23d-306">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="0d23d-306">-ThrottleLimit</span></span>

<span data-ttu-id="0d23d-307">Gibt die maximale Anzahl von gleichzeitigen Verbindungen an, die zum Ausführen dieses Befehls hergestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="0d23d-307">Specifies the maximum number of concurrent connections that can be established to run this command.</span></span>
<span data-ttu-id="0d23d-308">Wenn Sie diesen Parameter weglassen oder den Wert „0“ (Null) eingeben, wird der Standardwert „32“ verwendet.</span><span class="sxs-lookup"><span data-stu-id="0d23d-308">If you omit this parameter or enter a value of 0 (zero), the default value, 32, is used.</span></span>

<span data-ttu-id="0d23d-309">Die Drosselungsgrenze gilt nur für den aktuellen Befehl und nicht für die Sitzung oder den Computer.</span><span class="sxs-lookup"><span data-stu-id="0d23d-309">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="0d23d-310">-US-</span><span class="sxs-lookup"><span data-stu-id="0d23d-310">-UseSSL</span></span>

<span data-ttu-id="0d23d-311">Gibt an, dass dieses Cmdlet das SSL-Protokoll verwendet, um eine Verbindung mit dem Remote Computer herzustellen.</span><span class="sxs-lookup"><span data-stu-id="0d23d-311">Indicates that this cmdlet uses the SSL protocol to establish a connection to the remote computer.</span></span>
<span data-ttu-id="0d23d-312">Standardmäßig wird SSL nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="0d23d-312">By default, SSL is not used.</span></span>

<span data-ttu-id="0d23d-313">WS-Management verschlüsselt alle über das Netzwerk übertragenen PowerShell-Inhalte.</span><span class="sxs-lookup"><span data-stu-id="0d23d-313">WS-Management encrypts all PowerShell content transmitted over the network.</span></span> <span data-ttu-id="0d23d-314">Der Parameter " **eessl** " bietet einen zusätzlichen Schutz, der die Daten über eine HTTPS-Verbindung statt über eine HTTP-Verbindung sendet.</span><span class="sxs-lookup"><span data-stu-id="0d23d-314">The **UseSSL** parameter offers an additional protection that sends the data across an HTTPS connection instead of an HTTP connection.</span></span>

<span data-ttu-id="0d23d-315">Wenn Sie diesen Parameter verwenden, aber SSL auf dem Port, der für den Befehl verwendet wird, nicht verfügbar ist, schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="0d23d-315">If you use this parameter, but SSL is not available on the port that is used for the command, the command fails.</span></span>

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

### <span data-ttu-id="0d23d-316">-VMID</span><span class="sxs-lookup"><span data-stu-id="0d23d-316">-VMId</span></span>

<span data-ttu-id="0d23d-317">Gibt ein Array mit der ID der virtuellen Computer an.</span><span class="sxs-lookup"><span data-stu-id="0d23d-317">Specifies an array of ID of virtual machines.</span></span> <span data-ttu-id="0d23d-318">Dieses Cmdlet startet eine interaktive Sitzung mit jedem der angegebenen virtuellen Computer.</span><span class="sxs-lookup"><span data-stu-id="0d23d-318">This cmdlet starts an interactive session with each of the specified virtual machines.</span></span> <span data-ttu-id="0d23d-319">Verwenden Sie den folgenden Befehl, um die verfügbaren virtuellen Computer anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="0d23d-319">To see the virtual machines that are available to you, use the following command:</span></span>

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

### <span data-ttu-id="0d23d-320">-VMName</span><span class="sxs-lookup"><span data-stu-id="0d23d-320">-VMName</span></span>

<span data-ttu-id="0d23d-321">Gibt ein Array von Namen von virtuellen Computern an.</span><span class="sxs-lookup"><span data-stu-id="0d23d-321">Specifies an array of names of virtual machines.</span></span> <span data-ttu-id="0d23d-322">Dieses Cmdlet startet eine interaktive Sitzung mit jedem der angegebenen virtuellen Computer.</span><span class="sxs-lookup"><span data-stu-id="0d23d-322">This cmdlet starts an interactive session with each of the specified virtual machines.</span></span> <span data-ttu-id="0d23d-323">Verwenden Sie das-Cmdlet, um die für Sie verfügbaren virtuellen Maschinen anzuzeigen `Get-VM` .</span><span class="sxs-lookup"><span data-stu-id="0d23d-323">To see the virtual machines that are available to you, use the `Get-VM` cmdlet.</span></span>

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

### <span data-ttu-id="0d23d-324">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0d23d-324">CommonParameters</span></span>

<span data-ttu-id="0d23d-325">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0d23d-325">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0d23d-326">Weitere Informationen finden Sie unter "about_CommonParameters" (https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0d23d-326">For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0d23d-327">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="0d23d-327">INPUTS</span></span>

### <span data-ttu-id="0d23d-328">System. String, System. Uri, System. Management. Automation. Runspaces. PSSession</span><span class="sxs-lookup"><span data-stu-id="0d23d-328">System.String, System.URI, System.Management.Automation.Runspaces.PSSession</span></span>

<span data-ttu-id="0d23d-329">Sie können eine Zeichenfolge, einen URI oder ein Sitzungs Objekt über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="0d23d-329">You can pipe a string, URI, or session object to this cmdlet.</span></span>

## <span data-ttu-id="0d23d-330">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="0d23d-330">OUTPUTS</span></span>

### <span data-ttu-id="0d23d-331">System. Management. Automation. Runspaces. PSSession</span><span class="sxs-lookup"><span data-stu-id="0d23d-331">System.Management.Automation.Runspaces.PSSession</span></span>

## <span data-ttu-id="0d23d-332">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="0d23d-332">NOTES</span></span>

- <span data-ttu-id="0d23d-333">Dieses Cmdlet verwendet die PowerShell-Remoting-Infrastruktur.</span><span class="sxs-lookup"><span data-stu-id="0d23d-333">This cmdlet uses the PowerShell remoting infrastructure.</span></span> <span data-ttu-id="0d23d-334">Um dieses Cmdlet verwenden zu können, müssen der lokale Computer und alle Remote Computer für PowerShell-Remoting konfiguriert sein.</span><span class="sxs-lookup"><span data-stu-id="0d23d-334">To use this cmdlet, the local computer and any remote computers must be configured for PowerShell remoting.</span></span> <span data-ttu-id="0d23d-335">Weitere Informationen finden Sie unter [about_Remote_Requirements](About/about_Remote_Requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d23d-335">For more information, see [about_Remote_Requirements](About/about_Remote_Requirements.md).</span></span>
- <span data-ttu-id="0d23d-336">Starten Sie PowerShell mit der Option als Administrator ausführen, um eine **PSSession** auf dem lokalen Computer zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0d23d-336">To create a **PSSession** on the local computer, start PowerShell with the Run as administrator option.</span></span>
- <span data-ttu-id="0d23d-337">Wenn Sie mit der **PSSession** fertig sind, verwenden Sie das `Remove-PSSession` Cmdlet, um die **PSSession** zu löschen und deren Ressourcen freizugeben.</span><span class="sxs-lookup"><span data-stu-id="0d23d-337">When you are finished with the **PSSession** , use the `Remove-PSSession` cmdlet to delete the **PSSession** and release its resources.</span></span>

## <span data-ttu-id="0d23d-338">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="0d23d-338">RELATED LINKS</span></span>

[<span data-ttu-id="0d23d-339">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="0d23d-339">Connect-PSSession</span></span>](Connect-PSSession.md)

[<span data-ttu-id="0d23d-340">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="0d23d-340">Disconnect-PSSession</span></span>](Disconnect-PSSession.md)

[<span data-ttu-id="0d23d-341">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="0d23d-341">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="0d23d-342">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="0d23d-342">Exit-PSSession</span></span>](Exit-PSSession.md)

[<span data-ttu-id="0d23d-343">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="0d23d-343">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="0d23d-344">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="0d23d-344">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="0d23d-345">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="0d23d-345">Receive-PSSession</span></span>](Receive-PSSession.md)

[<span data-ttu-id="0d23d-346">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="0d23d-346">Remove-PSSession</span></span>](Remove-PSSession.md)
