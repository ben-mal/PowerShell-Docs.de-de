---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 5/15/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-pssession?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSSession
ms.openlocfilehash: 2f233dad23a8dead5e6fe0d072d71f0e2528551d
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218692"
---
# <span data-ttu-id="f40c5-103">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="f40c5-103">Get-PSSession</span></span>

## <span data-ttu-id="f40c5-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="f40c5-104">SYNOPSIS</span></span>
<span data-ttu-id="f40c5-105">Ruft die PowerShell-Sitzungen auf lokalen Computern und Remote Computern ab.</span><span class="sxs-lookup"><span data-stu-id="f40c5-105">Gets the PowerShell sessions on local and remote computers.</span></span>

## <span data-ttu-id="f40c5-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f40c5-106">SYNTAX</span></span>

### <span data-ttu-id="f40c5-107">Name (Standard)</span><span class="sxs-lookup"><span data-stu-id="f40c5-107">Name (Default)</span></span>

```
Get-PSSession [-Name <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="f40c5-108">Computername</span><span class="sxs-lookup"><span data-stu-id="f40c5-108">ComputerName</span></span>

```
Get-PSSession [-ComputerName] <String[]> [-ApplicationName <String>] [-ConfigurationName <String>]
 [-Name <String[]>] [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [-Port <Int32>] [-UseSSL] [-ThrottleLimit <Int32>]
 [-State <SessionFilterState>] [-SessionOption <PSSessionOption>] [<CommonParameters>]
```

### <span data-ttu-id="f40c5-109">Computerinstanceid</span><span class="sxs-lookup"><span data-stu-id="f40c5-109">ComputerInstanceId</span></span>

```
Get-PSSession [-ComputerName] <String[]> [-ApplicationName <String>] [-ConfigurationName <String>]
 -InstanceId <Guid[]> [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [-Port <Int32>] [-UseSSL] [-ThrottleLimit <Int32>]
 [-State <SessionFilterState>] [-SessionOption <PSSessionOption>] [<CommonParameters>]
```

### <span data-ttu-id="f40c5-110">ConnectionUri</span><span class="sxs-lookup"><span data-stu-id="f40c5-110">ConnectionUri</span></span>

```
Get-PSSession [-ConnectionUri] <Uri[]> [-ConfigurationName <String>] [-AllowRedirection] [-Name <String[]>]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [-ThrottleLimit <Int32>] [-State <SessionFilterState>] [-SessionOption <PSSessionOption>] [<CommonParameters>]
```

### <span data-ttu-id="f40c5-111">Connectionuriinstanceid</span><span class="sxs-lookup"><span data-stu-id="f40c5-111">ConnectionUriInstanceId</span></span>

```
Get-PSSession [-ConnectionUri] <Uri[]> [-ConfigurationName <String>] [-AllowRedirection] -InstanceId <Guid[]>
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [-ThrottleLimit <Int32>] [-State <SessionFilterState>] [-SessionOption <PSSessionOption>] [<CommonParameters>]
```

### <span data-ttu-id="f40c5-112">Vmnameingestanceid</span><span class="sxs-lookup"><span data-stu-id="f40c5-112">VMNameInstanceId</span></span>

```
Get-PSSession [-ConfigurationName <String>] -InstanceId <Guid[]> [-State <SessionFilterState>]
 -VMName <String[]> [<CommonParameters>]
```

### <span data-ttu-id="f40c5-113">ContainerId</span><span class="sxs-lookup"><span data-stu-id="f40c5-113">ContainerId</span></span>

```
Get-PSSession [-ConfigurationName <String>] [-Name <String[]>] [-State <SessionFilterState>]
 -ContainerId <String[]> [<CommonParameters>]
```

### <span data-ttu-id="f40c5-114">Containeridinstanceid</span><span class="sxs-lookup"><span data-stu-id="f40c5-114">ContainerIdInstanceId</span></span>

```
Get-PSSession [-ConfigurationName <String>] -InstanceId <Guid[]> [-State <SessionFilterState>]
 -ContainerId <String[]> [<CommonParameters>]
```

### <span data-ttu-id="f40c5-115">VMId</span><span class="sxs-lookup"><span data-stu-id="f40c5-115">VMId</span></span>

```
Get-PSSession [-ConfigurationName <String>] [-Name <String[]>] [-State <SessionFilterState>] -VMId <Guid[]>
 [<CommonParameters>]
```

### <span data-ttu-id="f40c5-116">Vmidinstanceid</span><span class="sxs-lookup"><span data-stu-id="f40c5-116">VMIdInstanceId</span></span>

```
Get-PSSession [-ConfigurationName <String>] -InstanceId <Guid[]> [-State <SessionFilterState>] -VMId <Guid[]>
 [<CommonParameters>]
```

### <span data-ttu-id="f40c5-117">VMName</span><span class="sxs-lookup"><span data-stu-id="f40c5-117">VMName</span></span>

```
Get-PSSession [-ConfigurationName <String>] [-Name <String[]>] [-State <SessionFilterState>] -VMName <String[]>
 [<CommonParameters>]
```

### <span data-ttu-id="f40c5-118">InstanceId</span><span class="sxs-lookup"><span data-stu-id="f40c5-118">InstanceId</span></span>

```
Get-PSSession [-InstanceId <Guid[]>] [<CommonParameters>]
```

### <span data-ttu-id="f40c5-119">Id</span><span class="sxs-lookup"><span data-stu-id="f40c5-119">Id</span></span>

```
Get-PSSession [-Id] <Int32[]> [<CommonParameters>]
```

## <span data-ttu-id="f40c5-120">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f40c5-120">DESCRIPTION</span></span>

<span data-ttu-id="f40c5-121">`Get-PSSession`Mit dem-Cmdlet werden die vom Benutzer verwalteten PowerShell-Sitzungen ( **pssessions** ) auf lokalen Computern und Remote Computern abgerufen.</span><span class="sxs-lookup"><span data-stu-id="f40c5-121">The `Get-PSSession` cmdlet gets the user-managed PowerShell sessions ( **PSSessions** ) on local and remote computers.</span></span>

<span data-ttu-id="f40c5-122">Ab Windows PowerShell 3,0 werden Sitzungen auf den Computern am Remote Ende jeder Verbindung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f40c5-122">Starting in Windows PowerShell 3.0, sessions are stored on the computers at the remote end of each connection.</span></span> <span data-ttu-id="f40c5-123">Sie können die Parameter **Computername** oder **ConnectionUri** von verwenden, `Get-PSSession` um die Sitzungen zu erhalten, die eine Verbindung mit dem lokalen Computer oder Remote Computern herstellen, auch wenn Sie nicht in der aktuellen Sitzung erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="f40c5-123">You can use the **ComputerName** or **ConnectionUri** parameters of `Get-PSSession` to get the sessions that connect to the local computer or remote computers, even if they were not created in the current session.</span></span>

<span data-ttu-id="f40c5-124">Ohne Parameter ruft `Get-PSSession` alle Sitzungen ab, die in der aktuellen Sitzung erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="f40c5-124">Without parameters, `Get-PSSession` gets all sessions that were created in the current session.</span></span>

<span data-ttu-id="f40c5-125">Verwenden Sie die Filter Parameter, einschließlich **Name** , **ID** , **InstanceId** , **State** , **ApplicationName** und **ConfigurationName** , um eine Auswahl aus den zurückgegebenen Sitzungen zu treffen `Get-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="f40c5-125">Use the filtering parameters, including **Name** , **ID** , **InstanceID** , **State** , **ApplicationName** , and **ConfigurationName** to select from among the sessions that `Get-PSSession` returns.</span></span>

<span data-ttu-id="f40c5-126">Verwenden Sie die verbleibenden Parameter, um die temporäre Verbindung zu konfigurieren, in der der Befehl ausgeführt wird, `Get-PSSession` Wenn Sie die Parameter **Computername** oder **ConnectionUri** verwenden.</span><span class="sxs-lookup"><span data-stu-id="f40c5-126">Use the remaining parameters to configure the temporary connection in which the `Get-PSSession` command runs when you use the **ComputerName** or **ConnectionUri** parameters.</span></span>

<span data-ttu-id="f40c5-127">Hinweis: Ruft in Windows PowerShell 2,0 ohne Parameter `Get-PSSession` alle Sitzungen ab, die in der aktuellen Sitzung erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="f40c5-127">NOTE: In Windows PowerShell 2.0, without parameters, `Get-PSSession` gets all sessions that were created in the current session.</span></span> <span data-ttu-id="f40c5-128">Der **Computername** -Parameter ruft die Sitzungen ab, die in der aktuellen Sitzung erstellt wurden, und eine Verbindung mit dem angegebenen Computer.</span><span class="sxs-lookup"><span data-stu-id="f40c5-128">The **ComputerName** parameter gets sessions that were created in the current session and connect to the specified computer.</span></span>

<span data-ttu-id="f40c5-129">Weitere Informationen zu PowerShell-Sitzungen finden Sie unter [about_PSSessions](about/about_PSSessions.md).</span><span class="sxs-lookup"><span data-stu-id="f40c5-129">For more information about PowerShell sessions, see [about_PSSessions](about/about_PSSessions.md).</span></span>

## <span data-ttu-id="f40c5-130">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="f40c5-130">EXAMPLES</span></span>

### <span data-ttu-id="f40c5-131">Beispiel 1: Get-Sitzungen, die in der aktuellen Sitzung erstellt wurden</span><span class="sxs-lookup"><span data-stu-id="f40c5-131">Example 1: Get sessions created in the current session</span></span>

```powershell
Get-PSSession
```

<span data-ttu-id="f40c5-132">Dieser Befehl ruft alle **pssessions** ab, die in der aktuellen Sitzung erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="f40c5-132">This command gets all of the **PSSessions** that were created in the current session.</span></span> <span data-ttu-id="f40c5-133">Er ruft keine **pssessions** ab, die in anderen Sitzungen oder auf anderen Computern erstellt wurden, auch wenn Sie eine Verbindung mit diesem Computer herstellen.</span><span class="sxs-lookup"><span data-stu-id="f40c5-133">It does not get **PSSessions** that were created in other sessions or on other computers, even if they connect to this computer.</span></span>

### <span data-ttu-id="f40c5-134">Beispiel 2: Get-Sitzungen, die mit dem lokalen Computer verbunden sind</span><span class="sxs-lookup"><span data-stu-id="f40c5-134">Example 2: Get sessions connected to the local computer</span></span>

```powershell
Get-PSSession -ComputerName "localhost"
```

<span data-ttu-id="f40c5-135">Dieser Befehl ruft die **pssessions** ab, die mit dem lokalen Computer verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="f40c5-135">This command gets the **PSSessions** that are connected to the local computer.</span></span> <span data-ttu-id="f40c5-136">Um den lokalen Computer anzugeben, geben Sie den Computernamen, "localhost" oder einen Punkt (.) ein.</span><span class="sxs-lookup"><span data-stu-id="f40c5-136">To indicate the local computer, type the computer name, localhost, or a dot (.)</span></span>

<span data-ttu-id="f40c5-137">Der Befehl gibt alle Sitzungen auf dem lokalen Computer zurück, auch wenn sie in anderen Sitzungen oder auf anderen Computern erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="f40c5-137">The command returns all of the sessions on the local computer, even if they were created in different sessions or on different computers.</span></span>

### <span data-ttu-id="f40c5-138">Beispiel 3: erhalten von Sitzungen, die mit einem Computer verbunden sind</span><span class="sxs-lookup"><span data-stu-id="f40c5-138">Example 3: Get sessions connected to a computer</span></span>

```powershell
Get-PSSession -ComputerName "Server02"
```

```Output
 Id Name            ComputerName    State         ConfigurationName     Availability
 -- ----            ------------    -----         -----------------     ------------
  2 Session3        Server02       Disconnected  ITTasks                       Busy
  1 ScheduledJobs   Server02       Opened        Microsoft.PowerShell     Available
  3 Test            Server02       Disconnected  Microsoft.PowerShell          Busy
```

<span data-ttu-id="f40c5-139">Dieser Befehl ruft die **pssessions** ab, die mit dem Server02-Computer verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="f40c5-139">This command gets the **PSSessions** that are connected to the Server02 computer.</span></span>

<span data-ttu-id="f40c5-140">Der Befehl gibt alle Sitzungen auf dem Computer „Server02“ zurück, auch wenn sie in anderen Sitzungen oder auf anderen Computern erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="f40c5-140">The command returns all of the sessions on Server02, even if they were created in different sessions or on different computers.</span></span>

<span data-ttu-id="f40c5-141">Die Ausgabe zeigt, dass zwei Sitzungen den Status „Getrennt“ und die Verfügbarkeit „Ausgelastet“ haben.</span><span class="sxs-lookup"><span data-stu-id="f40c5-141">The output shows that two of the sessions have a Disconnected state and a Busy availability.</span></span> <span data-ttu-id="f40c5-142">Sie wurden in verschiedenen Sitzungen erstellt und werden derzeit verwendet.</span><span class="sxs-lookup"><span data-stu-id="f40c5-142">They were created in different sessions and are currently in use.</span></span> <span data-ttu-id="f40c5-143">Die scheduledjobs-Sitzung, die geöffnet und verfügbar ist, wurde in der aktuellen Sitzung erstellt.</span><span class="sxs-lookup"><span data-stu-id="f40c5-143">The ScheduledJobs session, which is Opened and Available, was created in the current session.</span></span>

### <span data-ttu-id="f40c5-144">Beispiel 4: Speichern der Ergebnisse dieses Befehls</span><span class="sxs-lookup"><span data-stu-id="f40c5-144">Example 4: Save results of this command</span></span>

```powershell
New-PSSession -ComputerName Server01, Server02, Server03
$s1, $s2, $s3 = Get-PSSession
```

<span data-ttu-id="f40c5-145">Dieses Beispiel zeigt, wie die Ergebnisse eines `Get-PSSession` Befehls in mehreren Variablen gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="f40c5-145">This example shows how to save the results of a `Get-PSSession` command in multiple variables.</span></span>

<span data-ttu-id="f40c5-146">Der erste Befehl verwendet das `New-PSSession` Cmdlet, um **pssessions** auf drei Remote Computern zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f40c5-146">The first command uses the `New-PSSession` cmdlet to create **PSSessions** on three remote computers.</span></span>

<span data-ttu-id="f40c5-147">Der zweite Befehl verwendet ein `Get-PSSession` Cmdlet, um die drei **pssessions** zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="f40c5-147">The second command uses a `Get-PSSession` cmdlet to get the three **PSSessions**.</span></span> <span data-ttu-id="f40c5-148">Anschließend werden alle **pssessions** in einer separaten Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f40c5-148">It then saves each of the **PSSessions** in a separate variable.</span></span>

<span data-ttu-id="f40c5-149">Wenn PowerShell ein Array von Objekten einem Array von Variablen zuweist, wird das erste Objekt der ersten Variablen, das zweite Objekt der zweiten Variablen usw. zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="f40c5-149">When PowerShell assigns an array of objects to an array of variables, it assigns the first object to the first variable, the second object to the second variable, and so on.</span></span> <span data-ttu-id="f40c5-150">Wenn es mehr Objekte als Variablen gibt, werden alle verbleibenden Objekte der letzten Variablen im Array zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="f40c5-150">If there are more objects than variables, it assigns all remaining objects to the last variable in the array.</span></span> <span data-ttu-id="f40c5-151">Wenn es mehr Variablen als Objekte gibt, werden die zusätzlichen Variablen nicht genutzt.</span><span class="sxs-lookup"><span data-stu-id="f40c5-151">If there are more variables than objects, the extra variables are not used.</span></span>

### <span data-ttu-id="f40c5-152">Beispiel 5: Löschen einer Sitzung mit einer Instanz-ID</span><span class="sxs-lookup"><span data-stu-id="f40c5-152">Example 5: Delete a session by using an instance ID</span></span>

```powershell
Get-PSSession | Format-Table -Property ComputerName, InstanceID
$s = Get-PSSession -InstanceID a786be29-a6bb-40da-80fb-782c67f7db0f
Remove-PSSession -Session $s
```

<span data-ttu-id="f40c5-153">Dieses Beispiel zeigt, wie Sie eine **PSSession** mit der Instanz-ID erhalten und dann die **PSSession** löschen.</span><span class="sxs-lookup"><span data-stu-id="f40c5-153">This example shows how to get a **PSSession** by using its instance ID, and then to delete the **PSSession**.</span></span>

<span data-ttu-id="f40c5-154">Der erste Befehl ruft alle **pssessions** ab, die in der aktuellen Sitzung erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="f40c5-154">The first command gets all of the **PSSessions** that were created in the current session.</span></span> <span data-ttu-id="f40c5-155">Die **pssessions** werden an das Format-Table-Cmdlet gesendet, das die **Computername** -und **InstanceId-** Eigenschaften der einzelnen **PSSession** anzeigt.</span><span class="sxs-lookup"><span data-stu-id="f40c5-155">It sends the **PSSessions** to the Format-Table cmdlet, which displays the **ComputerName** and **InstanceID** properties of each **PSSession**.</span></span>

<span data-ttu-id="f40c5-156">Der zweite Befehl verwendet das `Get-PSSession` Cmdlet, um eine bestimmte **PSSession** abzurufen und in der Variablen zu speichern `$s` .</span><span class="sxs-lookup"><span data-stu-id="f40c5-156">The second command uses the `Get-PSSession` cmdlet to get a particular **PSSession** and to save it in the `$s` variable.</span></span> <span data-ttu-id="f40c5-157">Der Befehl verwendet den **InstanceId-** Parameter, um die **PSSession** zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="f40c5-157">The command uses the **InstanceID** parameter to identify the **PSSession**.</span></span>

<span data-ttu-id="f40c5-158">Der dritte Befehl verwendet das Cmdlet "Remove-PSSession", um die **PSSession** in der Variablen zu löschen `$s` .</span><span class="sxs-lookup"><span data-stu-id="f40c5-158">The third command uses the Remove-PSSession cmdlet to delete the **PSSession** in the `$s` variable.</span></span>

### <span data-ttu-id="f40c5-159">Beispiel 6: erhalten einer Sitzung mit einem bestimmten Namen</span><span class="sxs-lookup"><span data-stu-id="f40c5-159">Example 6: Get a session that has a particular name</span></span>

<span data-ttu-id="f40c5-160">Mit den Befehlen in diesem Beispiel finden Sie eine Sitzung, die über ein bestimmtes Namensformat verfügt und eine bestimmte Sitzungskonfiguration verwendet, und stellen dann eine Verbindung zur Sitzung her.</span><span class="sxs-lookup"><span data-stu-id="f40c5-160">The commands in this example find a session that has a particular name format and uses a particular session configuration and then connect to the session.</span></span> <span data-ttu-id="f40c5-161">Sie können einen Befehl wie diesen dazu verwenden, eine Sitzung zu suchen, in der ein Kollege eine Aufgabe gestartet hat, und eine Verbindung herstellen, um die Aufgabe abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="f40c5-161">You can use a command like this one to find a session in which a colleague started a task and connect to finish the task.</span></span>

```powershell
Get-PSSession -ComputerName Server02, Server12 -Name BackupJob* -ConfigurationName ITTasks -SessionOption @{OperationTimeout=240000}
```

```Output
 Id Name            ComputerName    State         ConfigurationName     Availability
 -- ----            ------------    -----         -----------------     ------------
  3 BackupJob04     Server02        Disconnected        ITTasks                  None
```

```powershell
$s = Get-PSSession -ComputerName Server02 -Name BackupJob04 -ConfigurationName ITTasks | Connect-PSSession
$s
```

```Output
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 5 BackupJob04     Server02        Opened        ITTasks                  Available
```

<span data-ttu-id="f40c5-162">Der erste Befehl ruft die Sitzungen auf den Remote Computern Server02 und Server12 ab, deren Namen mit backupjob beginnen und die ittasks-Sitzungs Konfiguration verwenden. Der Befehl verwendet den **Name** -Parameter, um das Namensmuster anzugeben, und den **ConfigurationName** -Parameter, um die Sitzungs Konfiguration anzugeben.</span><span class="sxs-lookup"><span data-stu-id="f40c5-162">The first command gets sessions on the Server02 and Server12 remote computers that have names that begin with BackupJob and use the ITTasks session configuration.The command uses the **Name** parameter to specify the name pattern and the **ConfigurationName** parameter to specify the session configuration.</span></span> <span data-ttu-id="f40c5-163">Der Wert des **SessionOption** -Parameters ist eine Hashtabelle, die den **OperationTimeout** -Wert auf 240000 Millisekunden (4 Minuten) festlegt.</span><span class="sxs-lookup"><span data-stu-id="f40c5-163">The value of the **SessionOption** parameter is a hash table that sets the value of the **OperationTimeout** to 240000 milliseconds (4 minutes).</span></span> <span data-ttu-id="f40c5-164">Diese Einstellung gibt dem Befehl mehr Zeit für den Abschluss. Der **ConfigurationName** -Parameter und der **sessionoption** -Parameter werden verwendet, um die temporären Sitzungen zu konfigurieren, in denen das `Get-PSSession` Cmdlet auf jedem Computer ausgeführt wird. Die Ausgabe zeigt, dass der Befehl die BackupJob04-Sitzung zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="f40c5-164">This setting gives the command more time to complete.The **ConfigurationName** and **SessionOption** parameters are used to configure the temporary sessions in which the `Get-PSSession` cmdlet runs on each computer.The output shows that the command returns the BackupJob04 session.</span></span> <span data-ttu-id="f40c5-165">Die Sitzung wird getrennt, und die **Verfügbarkeit** ist None. Dies bedeutet, dass Sie nicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f40c5-165">The session is disconnected and the **Availability** is None, which indicates that it is not in use.</span></span>

<span data-ttu-id="f40c5-166">Der zweite Befehl verwendet das `Get-PSSession` Cmdlet, um die BackupJob04-Sitzung zu erhalten, und das Cmdlet "Connect-PSSession", um eine Verbindung mit der Sitzung herzustellen.</span><span class="sxs-lookup"><span data-stu-id="f40c5-166">The second command uses the `Get-PSSession` cmdlet to get to the BackupJob04 session and the Connect-PSSession cmdlet to connect to the session.</span></span> <span data-ttu-id="f40c5-167">Der Befehl speichert die Sitzung in der $s-Variablen.</span><span class="sxs-lookup"><span data-stu-id="f40c5-167">The command saves the session in the $s variable.</span></span>

<span data-ttu-id="f40c5-168">Der dritte Befehl ruft die Sitzung in der Variablen „$s“ ab.</span><span class="sxs-lookup"><span data-stu-id="f40c5-168">The third command gets the session in the $s variable.</span></span> <span data-ttu-id="f40c5-169">Die Ausgabe zeigt, dass der `Connect-PSSession` Befehl erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="f40c5-169">The output shows that the `Connect-PSSession` command was successful.</span></span> <span data-ttu-id="f40c5-170">Die Sitzung hat den Status **Opened** und steht zur Verwendung zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="f40c5-170">The session is in the **Opened** state and is available for use.</span></span>

### <span data-ttu-id="f40c5-171">Beispiel 7: eine Sitzung mithilfe ihrer ID erhalten</span><span class="sxs-lookup"><span data-stu-id="f40c5-171">Example 7: Get a session by using its ID</span></span>

```powershell
Get-PSSession -Id 2
```

<span data-ttu-id="f40c5-172">Mit diesem Befehl wird die **PSSession** mit der ID 2 abgerufen.</span><span class="sxs-lookup"><span data-stu-id="f40c5-172">This command gets the **PSSession** with ID 2.</span></span> <span data-ttu-id="f40c5-173">Da der Wert der **ID** -Eigenschaft nur in der aktuellen Sitzung eindeutig ist, ist der **ID** -Parameter nur für lokale Befehle gültig.</span><span class="sxs-lookup"><span data-stu-id="f40c5-173">Because the value of the **ID** property is unique only in the current session, the **Id** parameter is valid only for local commands.</span></span>

## <span data-ttu-id="f40c5-174">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f40c5-174">PARAMETERS</span></span>

### <span data-ttu-id="f40c5-175">-Zuweisung Richtung</span><span class="sxs-lookup"><span data-stu-id="f40c5-175">-AllowRedirection</span></span>

<span data-ttu-id="f40c5-176">Gibt an, dass dieses Cmdlet die Umleitung dieser Verbindung an eine Alternative Uniform Resource Identifier (URI) zulässt.</span><span class="sxs-lookup"><span data-stu-id="f40c5-176">Indicates that this cmdlet allows redirection of this connection to an alternate Uniform Resource Identifier (URI).</span></span> <span data-ttu-id="f40c5-177">Standardmäßig leitet PowerShell Verbindungen nicht um.</span><span class="sxs-lookup"><span data-stu-id="f40c5-177">By default, PowerShell does not redirect connections.</span></span>

<span data-ttu-id="f40c5-178">Dieser Parameter konfiguriert die temporäre Verbindung, die erstellt wird, um einen `Get-PSSession` Befehl mit dem **ConnectionUri** -Parameter auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f40c5-178">This parameter configures the temporary connection that is created to run a `Get-PSSession` command with the **ConnectionUri** parameter.</span></span>

<span data-ttu-id="f40c5-179">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="f40c5-179">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ConnectionUriInstanceId, ConnectionUri
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f40c5-180">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="f40c5-180">-ApplicationName</span></span>

<span data-ttu-id="f40c5-181">Gibt den Namen einer Anwendung an.</span><span class="sxs-lookup"><span data-stu-id="f40c5-181">Specifies the name of an application.</span></span> <span data-ttu-id="f40c5-182">Dieses Cmdlet stellt nur Verbindungen mit Sitzungen her, die die angegebene Anwendung verwenden.</span><span class="sxs-lookup"><span data-stu-id="f40c5-182">This cmdlet connects only to sessions that use the specified application.</span></span>

<span data-ttu-id="f40c5-183">Geben Sie das Anwendungsnamensegment des Verbindungs-URI ein.</span><span class="sxs-lookup"><span data-stu-id="f40c5-183">Enter the application name segment of the connection URI.</span></span> <span data-ttu-id="f40c5-184">Im folgenden Verbindungs-URI lautet der Anwendungsname beispielsweise WSMAN: `http://localhost:5985/WSMAN` .</span><span class="sxs-lookup"><span data-stu-id="f40c5-184">For example, in the following connection URI, the application name is WSMan: `http://localhost:5985/WSMAN`.</span></span> <span data-ttu-id="f40c5-185">Der Anwendungsname einer Sitzung wird in der **Runspace.ConnectionInfo.AppName** -Eigenschaft der Sitzung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f40c5-185">The application name of a session is stored in the **Runspace.ConnectionInfo.AppName** property of the session.</span></span>

<span data-ttu-id="f40c5-186">Der Wert dieses Parameters wird verwendet, um Sitzungen auszuwählen und zu filtern.</span><span class="sxs-lookup"><span data-stu-id="f40c5-186">The value of this parameter is used to select and filter sessions.</span></span> <span data-ttu-id="f40c5-187">Er ändert nicht die von der Sitzung verwendete Anwendung.</span><span class="sxs-lookup"><span data-stu-id="f40c5-187">It does not change the application that the session uses.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerInstanceId, ComputerName
Aliases:

Required: False
Position: Named
Default value: All sessions
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="f40c5-188">-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="f40c5-188">-Authentication</span></span>

<span data-ttu-id="f40c5-189">Gibt den Mechanismus an, der zum Authentifizieren der Anmelde Informationen für die Sitzung verwendet wird, in der der Befehl ausgeführt wird `Get-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="f40c5-189">Specifies the mechanism that is used to authenticate credentials for the session in which the `Get-PSSession` command runs.</span></span>

<span data-ttu-id="f40c5-190">Dieser Parameter konfiguriert die temporäre Verbindung, die erstellt wird, um einen `Get-PSSession` Befehl mit dem Parameter **Computername** oder **ConnectionUri** auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f40c5-190">This parameter configures the temporary connection that is created to run a `Get-PSSession` command with the **ComputerName** or **ConnectionUri** parameter.</span></span>

<span data-ttu-id="f40c5-191">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="f40c5-191">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="f40c5-192">Standard</span><span class="sxs-lookup"><span data-stu-id="f40c5-192">Default</span></span>
- <span data-ttu-id="f40c5-193">Basic</span><span class="sxs-lookup"><span data-stu-id="f40c5-193">Basic</span></span>
- <span data-ttu-id="f40c5-194">CredSSP</span><span class="sxs-lookup"><span data-stu-id="f40c5-194">Credssp</span></span>
- <span data-ttu-id="f40c5-195">Digest</span><span class="sxs-lookup"><span data-stu-id="f40c5-195">Digest</span></span>
- <span data-ttu-id="f40c5-196">Kerberos</span><span class="sxs-lookup"><span data-stu-id="f40c5-196">Kerberos</span></span>
- <span data-ttu-id="f40c5-197">Aushandeln</span><span class="sxs-lookup"><span data-stu-id="f40c5-197">Negotiate</span></span>
- <span data-ttu-id="f40c5-198">NegotiateWithImplicitCredential.</span><span class="sxs-lookup"><span data-stu-id="f40c5-198">NegotiateWithImplicitCredential.</span></span>

<span data-ttu-id="f40c5-199">Der Standardwert ist Default.</span><span class="sxs-lookup"><span data-stu-id="f40c5-199">The default value is Default.</span></span>

<span data-ttu-id="f40c5-200">Weitere Informationen zu den Werten dieses Parameters finden Sie unter [authenticationmechanism-Enumeration](https://msdn.microsoft.com/library/system.management.automation.runspaces.authenticationmechanism) in der MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="f40c5-200">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](https://msdn.microsoft.com/library/system.management.automation.runspaces.authenticationmechanism) in the MSDN library.</span></span>

<span data-ttu-id="f40c5-201">Vorsicht: die Authentifizierung der Credential Security Support Provider (kredssp), bei der die Anmelde Informationen des Benutzers an einen Remote Computer übergeben werden, der authentifiziert werden soll, wurde für Befehle entworfen, die eine Authentifizierung auf mehr als einer Ressource erfordern, z. b. den Zugriff auf eine Remote Netzwerkfreigabe.</span><span class="sxs-lookup"><span data-stu-id="f40c5-201">CAUTION: Credential Security Support Provider (CredSSP) authentication, in which the user's credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="f40c5-202">Dieser Mechanismus erhöht das Sicherheitsrisiko des Remotevorgangs.</span><span class="sxs-lookup"><span data-stu-id="f40c5-202">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="f40c5-203">Wenn die Sicherheit des Remotecomputers gefährdet ist, können die an ihn übergebenen Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f40c5-203">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

<span data-ttu-id="f40c5-204">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="f40c5-204">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: ComputerInstanceId, ComputerName, ConnectionUriInstanceId, ConnectionUri
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f40c5-205">-Certifiupethumschlag-Print</span><span class="sxs-lookup"><span data-stu-id="f40c5-205">-CertificateThumbprint</span></span>

<span data-ttu-id="f40c5-206">Gibt das digitale Zertifikat für öffentliche Schlüssel (X509) eines Benutzerkontos an, das über die Berechtigung zum Erstellen der Sitzung verfügt, in der der Befehl ausgeführt wird `Get-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="f40c5-206">Specifies the digital public key certificate (X509) of a user account that has permission to create the session in which the `Get-PSSession` command runs.</span></span> <span data-ttu-id="f40c5-207">Geben Sie den Zertifikatfingerabdruck des Zertifikats ein.</span><span class="sxs-lookup"><span data-stu-id="f40c5-207">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="f40c5-208">Dieser Parameter konfiguriert die temporäre Verbindung, die erstellt wird, um einen `Get-PSSession` Befehl mit dem Parameter **Computername** oder **ConnectionUri** auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f40c5-208">This parameter configures the temporary connection that is created to run a `Get-PSSession` command with the **ComputerName** or **ConnectionUri** parameter.</span></span>

<span data-ttu-id="f40c5-209">Zertifikate werden bei der clientzertifikatbasierten Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="f40c5-209">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="f40c5-210">Sie können nur lokalen Benutzerkonten zugeordnet werden und funktionieren nicht mit Domänenkonten.</span><span class="sxs-lookup"><span data-stu-id="f40c5-210">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="f40c5-211">Um einen Zertifikat Fingerabdruck abzurufen, verwenden Sie im PowerShell-Laufwerk "CERT:" einen Get-Item oder Get-ChildItem Befehl.</span><span class="sxs-lookup"><span data-stu-id="f40c5-211">To get a certificate thumbprint, use a Get-Item or Get-ChildItem command in the PowerShell Cert: drive.</span></span>

<span data-ttu-id="f40c5-212">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="f40c5-212">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerInstanceId, ComputerName, ConnectionUriInstanceId, ConnectionUri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f40c5-213">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="f40c5-213">-ComputerName</span></span>

<span data-ttu-id="f40c5-214">Gibt ein Array von Namen von Computern an.</span><span class="sxs-lookup"><span data-stu-id="f40c5-214">Specifies an array of names of computers.</span></span> <span data-ttu-id="f40c5-215">Ruft die Sitzungen ab, die eine Verbindung zu den angegebenen Computern herstellen.</span><span class="sxs-lookup"><span data-stu-id="f40c5-215">Gets the sessions that connect to the specified computers.</span></span>
<span data-ttu-id="f40c5-216">Platzhalterzeichen sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="f40c5-216">Wildcard characters are not permitted.</span></span> <span data-ttu-id="f40c5-217">Es gibt keinen Standardwert.</span><span class="sxs-lookup"><span data-stu-id="f40c5-217">There is no default value.</span></span>

<span data-ttu-id="f40c5-218">Ab Windows PowerShell 3,0 werden **PSSession** -Objekte auf den Computern am Remote Ende jeder Verbindung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f40c5-218">Beginning in Windows PowerShell 3.0, **PSSession** objects are stored on the computers at the remote end of each connection.</span></span> <span data-ttu-id="f40c5-219">Um die Sitzungen auf den angegebenen Computern zu erhalten, erstellt PowerShell eine temporäre Verbindung mit den einzelnen Computern und führt einen `Get-PSSession` Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="f40c5-219">To get the sessions on the specified computers, PowerShell creates a temporary connection to each computer and runs a `Get-PSSession` command.</span></span>

<span data-ttu-id="f40c5-220">Geben Sie den NetBIOS-Namen, eine IP-Adresse oder einen vollqualifizierten Domänennamen mindestens eines Computers ein.</span><span class="sxs-lookup"><span data-stu-id="f40c5-220">Type the NetBIOS name, an IP address, or a fully-qualified domain name of one or more computers.</span></span> <span data-ttu-id="f40c5-221">Um den lokalen Computer anzugeben, geben Sie den Computernamen, "localhost" oder einen Punkt (.) ein.</span><span class="sxs-lookup"><span data-stu-id="f40c5-221">To specify the local computer, type the computer name, localhost, or a dot (.).</span></span>

<span data-ttu-id="f40c5-222">Hinweis: dieser Parameter ruft nur Sitzungen von Computern ab, auf denen Windows PowerShell 3,0 oder eine höhere Version von PowerShell ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f40c5-222">Note: This parameter gets sessions only from computers that run Windows PowerShell 3.0 or later versions of PowerShell.</span></span> <span data-ttu-id="f40c5-223">In früheren Versionen werden keine Sitzungen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f40c5-223">Earlier versions do not store sessions.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerInstanceId, ComputerName
Aliases: Cn

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="f40c5-224">-ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="f40c5-224">-ConfigurationName</span></span>

<span data-ttu-id="f40c5-225">Gibt den Namen einer Konfiguration an.</span><span class="sxs-lookup"><span data-stu-id="f40c5-225">Specifies the name of a configuration.</span></span> <span data-ttu-id="f40c5-226">Dieses Cmdlet bezieht sich nur auf Sitzungen, die die angegebene Sitzungs Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="f40c5-226">This cmdlet gets only to sessions that use the specified session configuration.</span></span>

<span data-ttu-id="f40c5-227">Geben Sie einen Konfigurationsnamen oder den vollqualifizierten Ressourcen-URI für eine Sitzungskonfiguration ein.</span><span class="sxs-lookup"><span data-stu-id="f40c5-227">Enter a configuration name or the fully qualified resource URI for a session configuration.</span></span> <span data-ttu-id="f40c5-228">Wenn Sie nur den Konfigurations Namen angeben, wird der folgende Schema-URI vorangestellt: `http://schemas.microsoft.com/powershell` .</span><span class="sxs-lookup"><span data-stu-id="f40c5-228">If you specify only the configuration name, the following schema URI is prepended: `http://schemas.microsoft.com/powershell`.</span></span> <span data-ttu-id="f40c5-229">Der Konfigurationsname einer Sitzung befindet sich in der **ConfigurationName** -Eigenschaft der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="f40c5-229">The configuration name of a session is stored in the **ConfigurationName** property of the session.</span></span>

<span data-ttu-id="f40c5-230">Der Wert dieses Parameters wird verwendet, um Sitzungen auszuwählen und zu filtern.</span><span class="sxs-lookup"><span data-stu-id="f40c5-230">The value of this parameter is used to select and filter sessions.</span></span> <span data-ttu-id="f40c5-231">Er ändert nicht die von der Sitzung verwendete Sitzungskonfiguration.</span><span class="sxs-lookup"><span data-stu-id="f40c5-231">It does not change the session configuration that the session uses.</span></span>

<span data-ttu-id="f40c5-232">Weitere Informationen zu Sitzungs Konfigurationen finden Sie unter [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="f40c5-232">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerInstanceId, ComputerName, ConnectionUriInstanceId, ConnectionUri, VMNameInstanceId, ContainerId, ContainerIdInstanceId, VMId, VMIdInstanceId, VMName
Aliases:

Required: False
Position: Named
Default value: All sessions
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="f40c5-233">-ConnectionUri</span><span class="sxs-lookup"><span data-stu-id="f40c5-233">-ConnectionUri</span></span>

<span data-ttu-id="f40c5-234">Gibt einen URI an, der den Verbindungs Endpunkt für die temporäre Sitzung definiert, in der der Befehl ausgeführt wird `Get-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="f40c5-234">Specifies a URI that defines the connection endpoint for the temporary session in which the `Get-PSSession` command runs.</span></span> <span data-ttu-id="f40c5-235">Der URI muss vollqualifiziert sein.</span><span class="sxs-lookup"><span data-stu-id="f40c5-235">The URI must be fully qualified.</span></span>

<span data-ttu-id="f40c5-236">Dieser Parameter konfiguriert die temporäre Verbindung, die erstellt wird, um einen `Get-PSSession` Befehl mit dem **ConnectionUri** -Parameter auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f40c5-236">This parameter configures the temporary connection that is created to run a `Get-PSSession` command with the **ConnectionUri** parameter.</span></span>

<span data-ttu-id="f40c5-237">Das Format dieser Zeichenfolge lautet:</span><span class="sxs-lookup"><span data-stu-id="f40c5-237">The format of this string is:</span></span>

`<Transport>://<ComputerName>:<Port\>/<ApplicationName>`

<span data-ttu-id="f40c5-238">Standardwert: `http://localhost:5985/WSMAN`.</span><span class="sxs-lookup"><span data-stu-id="f40c5-238">The default value is: `http://localhost:5985/WSMAN`.</span></span>

<span data-ttu-id="f40c5-239">Wenn Sie keinen **ConnectionUri** angeben, können Sie die **ConnectionUri** -Werte mit den Parametern " **US** ", " **Computername** ", " **Port** " und " **ApplicationName** " angeben.</span><span class="sxs-lookup"><span data-stu-id="f40c5-239">If you do not specify a **ConnectionUri** , you can use the **UseSSL** , **ComputerName** , **Port** , and **ApplicationName** parameters to specify the **ConnectionURI** values.</span></span> <span data-ttu-id="f40c5-240">Gültige Werte für das Transport-Segment des URI sind „HTTP“ und „HTTPS“.</span><span class="sxs-lookup"><span data-stu-id="f40c5-240">Valid values for the Transport segment of the URI are HTTP and HTTPS.</span></span> <span data-ttu-id="f40c5-241">Wenn Sie einen Verbindungs-URI mit einem Transport Segment angeben, aber keinen Port angeben, wird die Sitzung mit Standardports erstellt: 80 für http und 443 für HTTPS.</span><span class="sxs-lookup"><span data-stu-id="f40c5-241">If you specify a connection URI with a Transport segment, but do not specify a port, the session is created with standards ports: 80 for HTTP and 443 for HTTPS.</span></span> <span data-ttu-id="f40c5-242">Wenn Sie die Standardports für PowerShell-Remoting verwenden möchten, geben Sie Port 5985 für http oder 5986 für HTTPS an.</span><span class="sxs-lookup"><span data-stu-id="f40c5-242">To use the default ports for PowerShell remoting, specify port 5985 for HTTP or 5986 for HTTPS.</span></span>

<span data-ttu-id="f40c5-243">Wenn der Zielcomputer die Verbindung an einen anderen URI umleitet, verhindert PowerShell die Umleitung, es sei denn, Sie verwenden den Parameter " **Zuweisung** " im Befehl.</span><span class="sxs-lookup"><span data-stu-id="f40c5-243">If the destination computer redirects the connection to a different URI, PowerShell prevents the redirection unless you use the **AllowRedirection** parameter in the command.</span></span>

<span data-ttu-id="f40c5-244">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="f40c5-244">This parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="f40c5-245">Dieser Parameter ruft nur Sitzungen von Computern ab, auf denen Windows PowerShell 3,0 oder höhere Versionen von Windows PowerShell ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f40c5-245">This parameter gets sessions only from computers that run Windows PowerShell 3.0 or later versions of Windows PowerShell.</span></span> <span data-ttu-id="f40c5-246">In früheren Versionen werden keine Sitzungen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f40c5-246">Earlier versions do not store sessions.</span></span>

```yaml
Type: System.Uri[]
Parameter Sets: ConnectionUriInstanceId, ConnectionUri
Aliases: URI, CU

Required: True
Position: 0
Default value: Http://localhost:5985/WSMAN
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="f40c5-247">-Containerid</span><span class="sxs-lookup"><span data-stu-id="f40c5-247">-ContainerId</span></span>

<span data-ttu-id="f40c5-248">Gibt ein Array von IDs von Containern an.</span><span class="sxs-lookup"><span data-stu-id="f40c5-248">Specifies an array of IDs of containers.</span></span> <span data-ttu-id="f40c5-249">Mit diesem Cmdlet wird eine interaktive Sitzung mit jedem der angegebenen Container gestartet.</span><span class="sxs-lookup"><span data-stu-id="f40c5-249">This cmdlet starts an interactive session with each of the specified containers.</span></span> <span data-ttu-id="f40c5-250">Verwenden Sie den `docker ps` Befehl, um eine Liste der Container-IDs abzurufen.</span><span class="sxs-lookup"><span data-stu-id="f40c5-250">Use the `docker ps` command to get a list of container IDs.</span></span> <span data-ttu-id="f40c5-251">Weitere Informationen finden Sie in der Hilfe zum [docker PS](https://docs.docker.com/engine/reference/commandline/ps/) -Befehl.</span><span class="sxs-lookup"><span data-stu-id="f40c5-251">For more information, see the help for the [docker ps](https://docs.docker.com/engine/reference/commandline/ps/) command.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ContainerId, ContainerIdInstanceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="f40c5-252">-Credential</span><span class="sxs-lookup"><span data-stu-id="f40c5-252">-Credential</span></span>

<span data-ttu-id="f40c5-253">Gibt Benutzer Anmelde Informationen an.</span><span class="sxs-lookup"><span data-stu-id="f40c5-253">Specifies a user credential.</span></span> <span data-ttu-id="f40c5-254">Dieses Cmdlet führt den Befehl mit den Berechtigungen des angegebenen Benutzers aus.</span><span class="sxs-lookup"><span data-stu-id="f40c5-254">This cmdlet runs the command with the permissions of the specified user.</span></span> <span data-ttu-id="f40c5-255">Geben Sie ein Benutzerkonto an, das über die Berechtigung zum Herstellen einer Verbindung mit dem Remote Computer und Ausführen eines `Get-PSSession` Befehls verfügt.</span><span class="sxs-lookup"><span data-stu-id="f40c5-255">Specify a user account that has permission to connect to the remote computer and run a `Get-PSSession` command.</span></span> <span data-ttu-id="f40c5-256">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="f40c5-256">The default is the current user.</span></span>

<span data-ttu-id="f40c5-257">Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01** , oder geben Sie ein **PSCredential** -Objekt ein, das vom `Get-Credential` Cmdlet generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="f40c5-257">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="f40c5-258">Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe des Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="f40c5-258">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="f40c5-259">Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f40c5-259">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="f40c5-260">Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="f40c5-260">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

<span data-ttu-id="f40c5-261">Dieser Parameter konfiguriert die temporäre Verbindung, die erstellt wird, um einen `Get-PSSession` Befehl mit dem Parameter **Computername** oder **ConnectionUri** auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f40c5-261">This parameter configures to the temporary connection that is created to run a `Get-PSSession` command with the **ComputerName** or **ConnectionUri** parameter.</span></span>

<span data-ttu-id="f40c5-262">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="f40c5-262">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerInstanceId, ComputerName, ConnectionUriInstanceId, ConnectionUri
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f40c5-263">-Id</span><span class="sxs-lookup"><span data-stu-id="f40c5-263">-Id</span></span>

<span data-ttu-id="f40c5-264">Gibt ein Array von Sitzungs-IDs an.</span><span class="sxs-lookup"><span data-stu-id="f40c5-264">Specifies an array of session IDs.</span></span> <span data-ttu-id="f40c5-265">Dieses Cmdlet ruft nur die Sitzungen mit den angegebenen IDs ab.</span><span class="sxs-lookup"><span data-stu-id="f40c5-265">This cmdlet gets only the sessions with the specified IDs.</span></span> <span data-ttu-id="f40c5-266">Geben Sie eine oder mehrere IDs ein, die durch Kommas getrennt sind, oder verwenden Sie den Bereichs Operator (..), um einen Bereich von IDs anzugeben.</span><span class="sxs-lookup"><span data-stu-id="f40c5-266">Type one or more IDs, separated by commas, or use the range operator (..) to specify a range of IDs.</span></span> <span data-ttu-id="f40c5-267">Der ID-Parameter kann nicht in Verbindung mit dem **Computername** -Parameter verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f40c5-267">You cannot use the ID parameter together with the **ComputerName** parameter.</span></span>

<span data-ttu-id="f40c5-268">Eine ID ist eine Ganzzahl, die die vom Benutzer verwalteten Sitzungen in der aktuellen Sitzung eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="f40c5-268">An ID is an integer that uniquely identifies the user-managed sessions in the current session.</span></span> <span data-ttu-id="f40c5-269">Es ist einfacher zu merken und einzugeben als die **InstanceId** , aber nur innerhalb der aktuellen Sitzung eindeutig.</span><span class="sxs-lookup"><span data-stu-id="f40c5-269">It is easier to remember and type than the **InstanceId** , but it is unique only within the current session.</span></span> <span data-ttu-id="f40c5-270">Die ID einer Sitzung wird in der ID-Eigenschaft der Sitzung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f40c5-270">The ID of a session is stored in the ID property of the session.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: All sessions
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="f40c5-271">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="f40c5-271">-InstanceId</span></span>

<span data-ttu-id="f40c5-272">Gibt ein Array von Instanz-IDs von Sitzungen an.</span><span class="sxs-lookup"><span data-stu-id="f40c5-272">Specifies an array of instance IDs of sessions.</span></span> <span data-ttu-id="f40c5-273">Dieses Cmdlet ruft nur die Sitzungen mit den angegebenen Instanz-IDs ab.</span><span class="sxs-lookup"><span data-stu-id="f40c5-273">This cmdlet gets only the sessions with the specified instance IDs.</span></span>

<span data-ttu-id="f40c5-274">Die Instanz-ID ist eine GUID, die eine Sitzung auf einem lokalen oder Remotecomputer eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="f40c5-274">The instance ID is a GUID that uniquely identifies a session on a local or remote computer.</span></span> <span data-ttu-id="f40c5-275">Die **InstanceId** ist eindeutig, auch wenn mehrere Sitzungen in PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f40c5-275">The **InstanceID** is unique, even when you have multiple sessions running in PowerShell.</span></span>

<span data-ttu-id="f40c5-276">Die Instanz-ID einer Sitzung wird in der **InstanceID** -Eigenschaft der Sitzung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f40c5-276">The instance ID of a session is stored in the **InstanceID** property of the session.</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: ComputerInstanceId, ConnectionUriInstanceId, VMNameInstanceId, ContainerIdInstanceId, VMIdInstanceId
Aliases:

Required: True (ComputerInstanceId, ConnectionUriInstanceId, ContainerIdInstanceId, VMIdInstanceId, VMNameInstanceId), False (InstanceId)
Position: Named
Default value: All sessions
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f40c5-277">-Name</span><span class="sxs-lookup"><span data-stu-id="f40c5-277">-Name</span></span>

<span data-ttu-id="f40c5-278">Gibt ein Array von Sitzungs Namen an.</span><span class="sxs-lookup"><span data-stu-id="f40c5-278">Specifies an array of session names.</span></span> <span data-ttu-id="f40c5-279">Dieses Cmdlet ruft nur die Sitzungen mit den angegebenen anzeigen Amen ab.</span><span class="sxs-lookup"><span data-stu-id="f40c5-279">This cmdlet gets only the sessions that have the specified friendly names.</span></span> <span data-ttu-id="f40c5-280">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="f40c5-280">Wildcard characters are permitted.</span></span>

<span data-ttu-id="f40c5-281">Der Anzeigename einer Sitzung wird in der **Name** -Eigenschaft der Sitzung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f40c5-281">The friendly name of a session is stored in the **Name** property of the session.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name, ComputerName, ConnectionUri, ContainerId, VMId, VMName
Aliases:

Required: False
Position: Named
Default value: All sessions
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="f40c5-282">-Port</span><span class="sxs-lookup"><span data-stu-id="f40c5-282">-Port</span></span>

<span data-ttu-id="f40c5-283">Gibt den angegebenen Netzwerkport an, der für die temporäre Verbindung verwendet wird, in der der Befehl ausgeführt wird `Get-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="f40c5-283">Specifies the specified network port that is used for the temporary connection in which the `Get-PSSession` command runs.</span></span> <span data-ttu-id="f40c5-284">Zum Herstellen einer Verbindung mit einem Remotecomputer muss der Remotecomputer den für die Verbindung verwendeten Port abhören.</span><span class="sxs-lookup"><span data-stu-id="f40c5-284">To connect to a remote computer, the remote computer must be listening on the port that the connection uses.</span></span> <span data-ttu-id="f40c5-285">Die Standardports sind 5985. Dies ist der WinRM-Port für http und 5986 (der WinRM-Port für HTTPS).</span><span class="sxs-lookup"><span data-stu-id="f40c5-285">The default ports are 5985, which is the WinRM port for HTTP, and 5986, which is the WinRM port for HTTPS.</span></span>

<span data-ttu-id="f40c5-286">Bevor ein alternativer Port verwendet werden kann, müssen Sie den WinRM-Listener auf dem Remotecomputer für das Abhören an diesen Port konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f40c5-286">Before using an alternate port, you must configure the WinRM listener on the remote computer to listen at that port.</span></span> <span data-ttu-id="f40c5-287">Um den Listener zu konfigurieren, geben Sie die folgenden beiden Befehle an der PowerShell-Eingabeaufforderung ein:</span><span class="sxs-lookup"><span data-stu-id="f40c5-287">To configure the listener, type the following two commands at the PowerShell prompt:</span></span>

`Remove-Item -Path WSMan:\Localhost\listener\listener* -Recurse`

`New-Item -Path WSMan:\Localhost\listener -Transport http -Address * -Port \<port-number\>`

<span data-ttu-id="f40c5-288">Dieser Parameter konfiguriert die temporäre Verbindung, die erstellt wird, um einen `Get-PSSession` Befehl mit dem Parameter **Computername** oder **ConnectionUri** auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f40c5-288">This parameter configures to the temporary connection that is created to run a `Get-PSSession` command with the **ComputerName** or **ConnectionUri** parameter.</span></span>

<span data-ttu-id="f40c5-289">Verwenden Sie den **Port** -Parameter nur, wenn es unbedingt notwendig ist.</span><span class="sxs-lookup"><span data-stu-id="f40c5-289">Do not use the **Port** parameter unless you must.</span></span> <span data-ttu-id="f40c5-290">Der im Befehl festgelegte **Port** gilt für alle Computer oder Sitzungen, für die der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f40c5-290">The **Port** set in the command applies to all computers or sessions on which the command runs.</span></span> <span data-ttu-id="f40c5-291">Eine alternative Porteinstellung kann verhindern, dass der Befehl auf allen Computern ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f40c5-291">An alternate port setting might prevent the command from running on all computers.</span></span>

<span data-ttu-id="f40c5-292">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="f40c5-292">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ComputerInstanceId, ComputerName
Aliases:

Required: False
Position: Named
Default value: 5985, 5986
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f40c5-293">-Sessionoption</span><span class="sxs-lookup"><span data-stu-id="f40c5-293">-SessionOption</span></span>

<span data-ttu-id="f40c5-294">Gibt erweiterte Optionen für die Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="f40c5-294">Specifies advanced options for the session.</span></span> <span data-ttu-id="f40c5-295">Geben Sie ein **sessionoption** -Objekt ein, z. b. ein Objekt, das Sie mit dem Cmdlet "New-PSSessionOption" erstellen, oder eine Hash Tabelle, in der die Schlüssel Sitzungs Optionsnamen und die Werte Sitzungs Optionswerte sind.</span><span class="sxs-lookup"><span data-stu-id="f40c5-295">Enter a **SessionOption** object, such as one that you create by using the New-PSSessionOption cmdlet, or a hash table in which the keys are session option names and the values are session option values.</span></span>

<span data-ttu-id="f40c5-296">Die Standardwerte für die Optionen werden durch den Wert der $PSSessionOption-Einstellungsvariablen bestimmt, sofern festgelegt.</span><span class="sxs-lookup"><span data-stu-id="f40c5-296">The default values for the options are determined by the value of the $PSSessionOption preference variable, if it is set.</span></span> <span data-ttu-id="f40c5-297">Andernfalls werden die Standardwerte durch Optionen festgelegt, die in der Sitzungskonfiguration festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="f40c5-297">Otherwise, the default values are established by options set in the session configuration.</span></span>

<span data-ttu-id="f40c5-298">Die Sitzungsoptionswerte haben Vorrang vor Standardwerten für Sitzungen, die in der $PSSessionOption-Einstellungsvariablen und in der Sitzungskonfiguration festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="f40c5-298">The session option values take precedence over default values for sessions set in the $PSSessionOption preference variable and in the session configuration.</span></span> <span data-ttu-id="f40c5-299">Allerdings haben sie nicht Vorrang vor Höchstwerten, Kontingenten oder Grenzwerten, die in der Sitzungskonfiguration festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="f40c5-299">However, they do not take precedence over maximum values, quotas or limits set in the session configuration.</span></span>

<span data-ttu-id="f40c5-300">Eine Beschreibung der Sitzungs Optionen, einschließlich der Standardwerte, finden Sie unter `New-PSSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="f40c5-300">For a description of the session options, including the default values, see `New-PSSessionOption`.</span></span>
<span data-ttu-id="f40c5-301">Weitere Informationen zur Einstellungs `$PSSessionOption` Variablen finden Sie unter [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="f40c5-301">For information about the `$PSSessionOption` preference variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span> <span data-ttu-id="f40c5-302">Weitere Informationen zu Sitzungs Konfigurationen finden Sie unter [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="f40c5-302">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

```yaml
Type: System.Management.Automation.Remoting.PSSessionOption
Parameter Sets: ComputerInstanceId, ComputerName, ConnectionUriInstanceId, ConnectionUri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f40c5-303">-State</span><span class="sxs-lookup"><span data-stu-id="f40c5-303">-State</span></span>

<span data-ttu-id="f40c5-304">Gibt einen Sitzungszustand an.</span><span class="sxs-lookup"><span data-stu-id="f40c5-304">Specifies a session state.</span></span> <span data-ttu-id="f40c5-305">Dieses Cmdlet ruft nur Sitzungen im angegebenen Zustand ab.</span><span class="sxs-lookup"><span data-stu-id="f40c5-305">This cmdlet gets only sessions in the specified state.</span></span> <span data-ttu-id="f40c5-306">Die zulässigen Werte für diesen Parameter sind: alle, geöffnet, getrennt, geschlossen und beschädigt.</span><span class="sxs-lookup"><span data-stu-id="f40c5-306">The acceptable values for this parameter are: All, Opened, Disconnected, Closed, and Broken.</span></span> <span data-ttu-id="f40c5-307">Der Standardwert ist „Alle“.</span><span class="sxs-lookup"><span data-stu-id="f40c5-307">The default value is All.</span></span>

<span data-ttu-id="f40c5-308">Der Sitzungsstatuswert ist relativ zu aktuellen Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="f40c5-308">The session state value is relative to the current sessions.</span></span> <span data-ttu-id="f40c5-309">Sitzungen, die nicht in den aktuellen Sitzungen erstellt wurden und nicht mit der aktuellen Sitzung verbunden sind, haben den Status Disconnected, auch wenn sie mit einer anderen Sitzung verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="f40c5-309">Sessions that were not created in the current sessions and are not connected to the current session have a state of Disconnected even when they are connected to a different session.</span></span>

<span data-ttu-id="f40c5-310">Der Status einer Sitzung wird in der **State** -Eigenschaft der Sitzung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f40c5-310">The state of a session is stored in the **State** property of the session.</span></span>

<span data-ttu-id="f40c5-311">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="f40c5-311">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.SessionFilterState
Parameter Sets: ComputerInstanceId, ComputerName, ConnectionUriInstanceId, ConnectionUri, VMNameInstanceId, ContainerId, ContainerIdInstanceId, VMId, VMIdInstanceId, VMName
Aliases:
Accepted values: All, Opened, Disconnected, Closed, Broken

Required: False
Position: Named
Default value: All
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f40c5-312">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="f40c5-312">-ThrottleLimit</span></span>

<span data-ttu-id="f40c5-313">Gibt die maximale Anzahl gleichzeitiger Verbindungen an, die zum Ausführen des Befehls hergestellt werden können `Get-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="f40c5-313">Specifies the maximum number of concurrent connections that can be established to run the `Get-PSSession` command.</span></span> <span data-ttu-id="f40c5-314">Wenn Sie diesen Parameter weglassen oder den Wert „0“ (Null) eingeben, wird der Standardwert „32“ verwendet.</span><span class="sxs-lookup"><span data-stu-id="f40c5-314">If you omit this parameter or enter a value of 0 (zero), the default value, 32, is used.</span></span> <span data-ttu-id="f40c5-315">Die Drosselungsgrenze gilt nur für den aktuellen Befehl und nicht für die Sitzung oder den Computer.</span><span class="sxs-lookup"><span data-stu-id="f40c5-315">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

<span data-ttu-id="f40c5-316">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="f40c5-316">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ComputerInstanceId, ComputerName, ConnectionUriInstanceId, ConnectionUri
Aliases:

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f40c5-317">-US-</span><span class="sxs-lookup"><span data-stu-id="f40c5-317">-UseSSL</span></span>

<span data-ttu-id="f40c5-318">Gibt an, dass dieses Cmdlet das Secure Sockets Layer (SSL)-Protokoll verwendet, um die Verbindung herzustellen, in der der Befehl ausgeführt wird `Get-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="f40c5-318">Indicates that this cmdlet uses the Secure Sockets Layer (SSL) protocol to establish the connection in which the `Get-PSSession` command runs.</span></span> <span data-ttu-id="f40c5-319">Standardmäßig wird SSL nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="f40c5-319">By default, SSL is not used.</span></span> <span data-ttu-id="f40c5-320">Wenn Sie diesen Parameter verwenden, aber SSL auf dem Port für den Befehl nicht verfügbar ist, tritt ein Fehler beim Befehl auf.</span><span class="sxs-lookup"><span data-stu-id="f40c5-320">If you use this parameter, but SSL is not available on the port used for the command, the command fails.</span></span>

<span data-ttu-id="f40c5-321">Dieser Parameter konfiguriert die temporäre Verbindung, die erstellt wird, um einen `Get-PSSession` Befehl mit dem **Computername** -Parameter auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f40c5-321">This parameter configures the temporary connection that is created to run a `Get-PSSession` command with the **ComputerName** parameter.</span></span>

<span data-ttu-id="f40c5-322">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="f40c5-322">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerInstanceId, ComputerName
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f40c5-323">-VMID</span><span class="sxs-lookup"><span data-stu-id="f40c5-323">-VMId</span></span>

<span data-ttu-id="f40c5-324">Gibt ein Array mit der ID der virtuellen Computer an.</span><span class="sxs-lookup"><span data-stu-id="f40c5-324">Specifies an array of ID of virtual machines.</span></span> <span data-ttu-id="f40c5-325">Dieses Cmdlet startet eine interaktive Sitzung mit jedem der angegebenen virtuellen Computer.</span><span class="sxs-lookup"><span data-stu-id="f40c5-325">This cmdlet starts an interactive session with each of the specified virtual machines.</span></span> <span data-ttu-id="f40c5-326">Verwenden Sie den folgenden Befehl, um die verfügbaren virtuellen Computer anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="f40c5-326">To see the virtual machines that are available to you, use the following command:</span></span>

`Get-VM | Select-Object -Property Name, ID`

```yaml
Type: System.Guid[]
Parameter Sets: VMId, VMIdInstanceId
Aliases: VMGuid

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="f40c5-327">-VMName</span><span class="sxs-lookup"><span data-stu-id="f40c5-327">-VMName</span></span>

<span data-ttu-id="f40c5-328">Gibt ein Array von Namen von virtuellen Computern an.</span><span class="sxs-lookup"><span data-stu-id="f40c5-328">Specifies an array of names of virtual machines.</span></span> <span data-ttu-id="f40c5-329">Dieses Cmdlet startet eine interaktive Sitzung mit jedem der angegebenen virtuellen Computer.</span><span class="sxs-lookup"><span data-stu-id="f40c5-329">This cmdlet starts an interactive session with each of the specified virtual machines.</span></span> <span data-ttu-id="f40c5-330">Verwenden Sie das-Cmdlet, um die für Sie verfügbaren virtuellen Maschinen anzuzeigen `Get-VM` .</span><span class="sxs-lookup"><span data-stu-id="f40c5-330">To see the virtual machines that are available to you, use the `Get-VM` cmdlet.</span></span>

```yaml
Type: System.String[]
Parameter Sets: VMNameInstanceId, VMName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="f40c5-331">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f40c5-331">CommonParameters</span></span>

<span data-ttu-id="f40c5-332">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f40c5-332">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f40c5-333">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f40c5-333">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f40c5-334">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="f40c5-334">INPUTS</span></span>

### <span data-ttu-id="f40c5-335">Keine</span><span class="sxs-lookup"><span data-stu-id="f40c5-335">None</span></span>

<span data-ttu-id="f40c5-336">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="f40c5-336">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="f40c5-337">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="f40c5-337">OUTPUTS</span></span>

### <span data-ttu-id="f40c5-338">System. Management. Automation. Runspaces. PSSession</span><span class="sxs-lookup"><span data-stu-id="f40c5-338">System.Management.Automation.Runspaces.PSSession</span></span>

## <span data-ttu-id="f40c5-339">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="f40c5-339">NOTES</span></span>

- <span data-ttu-id="f40c5-340">Mit diesem Cmdlet werden von Benutzern verwaltete Sitzungen **PSSession** -Objekte abgerufen, z. b. solche, die mit den Cmdlets New-PSSession, `Enter-PSSession` und Invoke-Command erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="f40c5-340">This cmdlet gets user-managed sessions **PSSession** objects" such as those that are created by using the New-PSSession, `Enter-PSSession`, and Invoke-Command cmdlets.</span></span> <span data-ttu-id="f40c5-341">Sie ruft nicht die vom System verwaltete Sitzung ab, die beim Starten von PowerShell erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="f40c5-341">It does not get the system-managed session that is created when you start PowerShell.</span></span>
- <span data-ttu-id="f40c5-342">Ab Windows PowerShell 3,0 werden **PSSession** -Objekte auf dem Server gespeichert, der sich auf dem Server oder am Ende einer Verbindung befindet.</span><span class="sxs-lookup"><span data-stu-id="f40c5-342">Starting in Windows PowerShell 3.0, **PSSession** objects are stored on the computer that is at the server-side or receiving end of a connection.</span></span> <span data-ttu-id="f40c5-343">Um die Sitzungen zu erhalten, die auf dem lokalen Computer oder einem Remote Computer gespeichert sind, stellt PowerShell eine temporäre Sitzung mit dem angegebenen Computer her und führt Abfrage Befehle in der Sitzung aus.</span><span class="sxs-lookup"><span data-stu-id="f40c5-343">To get the sessions that are stored on the local computer or a remote computer, PowerShell establishes a temporary session to the specified computer and runs query commands in the session.</span></span>
- <span data-ttu-id="f40c5-344">Verwenden Sie zum Abrufen von Sitzungen, die eine Verbindung zu einem Remotecomputer herstellen, den Parameter **ComputerName** oder **ConnectionUri** , um den Remotecomputer anzugeben.</span><span class="sxs-lookup"><span data-stu-id="f40c5-344">To get sessions that connect to a remote computer, use the **ComputerName** or **ConnectionUri** parameters to specify the remote computer.</span></span> <span data-ttu-id="f40c5-345">Um die Sitzungen zu filtern `Get-PSSession` , die abrufen, verwenden Sie die Parameter **Name** , **ID** , **InstanceId** und **State** .</span><span class="sxs-lookup"><span data-stu-id="f40c5-345">To filter the sessions that `Get-PSSession` gets, use the **Name** , **ID** , **InstanceID** , and **State** parameters.</span></span> <span data-ttu-id="f40c5-346">Verwenden Sie die restlichen Parameter, um die temporäre Sitzung zu konfigurieren, die von `Get-PSSession` verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f40c5-346">Use the remaining parameters to configure the temporary session that `Get-PSSession` uses.</span></span>
- <span data-ttu-id="f40c5-347">Wenn Sie die Parameter **Computername** oder **ConnectionUri** verwenden, ruft `Get-PSSession` nur Sitzungen von Computern ab, auf denen Windows PowerShell 3,0 und höhere Versionen von PowerShell ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f40c5-347">When you use the **ComputerName** or **ConnectionUri** parameters, `Get-PSSession` gets only sessions from computers running Windows PowerShell 3.0 and later versions of PowerShell.</span></span>
- <span data-ttu-id="f40c5-348">Der Wert der **State** -Eigenschaft einer **PSSession** ist relativ zur aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="f40c5-348">The value of the **State** property of a **PSSession** is relative to the current session.</span></span>
  <span data-ttu-id="f40c5-349">Daher bedeutet der Wert " **getrennt** ", dass die **PSSession** nicht mit der aktuellen Sitzung verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="f40c5-349">Therefore, a value of **Disconnected** means that the **PSSession** is not connected to the current session.</span></span> <span data-ttu-id="f40c5-350">Dies bedeutet jedoch nicht, dass die **PSSession** von allen Sitzungen getrennt ist.</span><span class="sxs-lookup"><span data-stu-id="f40c5-350">However, it does not mean that the **PSSession** is disconnected from all sessions.</span></span> <span data-ttu-id="f40c5-351">Sie kann mit einer anderen Sitzung verbunden sein.</span><span class="sxs-lookup"><span data-stu-id="f40c5-351">It might be connected to a different session.</span></span> <span data-ttu-id="f40c5-352">Verwenden Sie die **Availability** -Eigenschaft, um zu bestimmen, ob Sie die **PSSession** in der aktuellen Sitzung verbinden oder wiederherstellen können.</span><span class="sxs-lookup"><span data-stu-id="f40c5-352">To determine whether you can connect or reconnect to the **PSSession** from the current session, use the **Availability** property.</span></span>

<span data-ttu-id="f40c5-353">Ein **Availability** -Wert von **None** gibt an, dass eine Verbindung mit der Sitzung hergestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="f40c5-353">An **Availability** value of **None** indicates that you can connect to the session.</span></span> <span data-ttu-id="f40c5-354">Der Wert **ausgelastet** gibt an, dass keine Verbindung mit der **PSSession** hergestellt werden kann, da Sie mit einer anderen Sitzung verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="f40c5-354">A value of **Busy** indicates that you cannot connect to the **PSSession** because it is connected to another session.</span></span>

<span data-ttu-id="f40c5-355">Weitere Informationen zu den Werten der **State** -Eigenschaft von Sitzungen finden Sie unter [runspacestate-Enumeration](https://msdn.microsoft.com/library/system.management.automation.runspaces.runspacestate).</span><span class="sxs-lookup"><span data-stu-id="f40c5-355">For more information about the values of the **State** property of sessions, see [RunspaceState Enumeration](https://msdn.microsoft.com/library/system.management.automation.runspaces.runspacestate).</span></span>

<span data-ttu-id="f40c5-356">Weitere Informationen zu den Werten der **Availability** -Eigenschaft von Sitzungen finden Sie unter [runspaceavailability-Enumeration](https://msdn.microsoft.com/library/system.management.automation.runspaces.runspaceavailability).</span><span class="sxs-lookup"><span data-stu-id="f40c5-356">For more information about the values of the **Availability** property of sessions, see [RunspaceAvailability Enumeration](https://msdn.microsoft.com/library/system.management.automation.runspaces.runspaceavailability).</span></span>

## <span data-ttu-id="f40c5-357">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="f40c5-357">RELATED LINKS</span></span>

[<span data-ttu-id="f40c5-358">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="f40c5-358">Connect-PSSession</span></span>](Connect-PSSession.md)

[<span data-ttu-id="f40c5-359">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="f40c5-359">Disconnect-PSSession</span></span>](Disconnect-PSSession.md)

[<span data-ttu-id="f40c5-360">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="f40c5-360">Receive-PSSession</span></span>](Receive-PSSession.md)

[<span data-ttu-id="f40c5-361">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="f40c5-361">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="f40c5-362">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="f40c5-362">Exit-PSSession</span></span>](Exit-PSSession.md)

[<span data-ttu-id="f40c5-363">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="f40c5-363">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="f40c5-364">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="f40c5-364">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="f40c5-365">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="f40c5-365">Remove-PSSession</span></span>](Remove-PSSession.md)

[<span data-ttu-id="f40c5-366">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="f40c5-366">about_PSSessions</span></span>](About/about_PSSessions.md)

[<span data-ttu-id="f40c5-367">about_Remote</span><span class="sxs-lookup"><span data-stu-id="f40c5-367">about_Remote</span></span>](About/about_Remote.md)
