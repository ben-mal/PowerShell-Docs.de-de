---
ms.date: 06/05/2017
keywords: powershell,cmdlet
title: Verwalten von Diensten
description: PowerShell bietet mehrere Cmdlets, die die Verwaltung von Diensten auf lokalen und Remotecomputern unterstützen.
ms.openlocfilehash: 003803cdaa37e51b3788f3f897cbec7d6e243ca8
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500350"
---
# <a name="managing-services"></a><span data-ttu-id="8e198-104">Verwalten von Diensten</span><span class="sxs-lookup"><span data-stu-id="8e198-104">Managing Services</span></span>

<span data-ttu-id="8e198-105">Es gibt acht dienstbezogene Kern-Cmdlets („Service“-Cmdlets), die für eine Vielzahl von Dienstaufgaben konzipiert sind.</span><span class="sxs-lookup"><span data-stu-id="8e198-105">There are eight core Service cmdlets, designed for a wide range of service tasks .</span></span> <span data-ttu-id="8e198-106">Hier geht es nur um das Auflisten von Diensten und das Ändern des Ausführungsstatus für Dienste. Sie können aber eine Liste der Service-Cmdlets abrufen, indem Sie `Get-Help \*-Service` verwenden, und Sie finden Informationen zu jedem Service-Cmdlet, indem Sie `Get-Help <Cmdlet-Name>` verwenden (z.B. `Get-Help New-Service`).</span><span class="sxs-lookup"><span data-stu-id="8e198-106">We will look only at listing and changing running state for services, but you can get a list of Service cmdlets by using `Get-Help \*-Service`, and you can find information about each Service cmdlet by using `Get-Help <Cmdlet-Name>`, such as `Get-Help New-Service`.</span></span>

## <a name="getting-services"></a><span data-ttu-id="8e198-107">Abrufen von Diensten</span><span class="sxs-lookup"><span data-stu-id="8e198-107">Getting Services</span></span>

<span data-ttu-id="8e198-108">Sie können die Dienste auf einem lokalen oder Remotecomputer abrufen, indem Sie das Cmdlet `Get-Service` verwenden.</span><span class="sxs-lookup"><span data-stu-id="8e198-108">You can get the services on a local or remote computer by using the `Get-Service` cmdlet.</span></span> <span data-ttu-id="8e198-109">Wie bei `Get-Process` werden bei der Verwendung des `Get-Service`-Befehls ohne Parameter alle Dienste zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8e198-109">As with `Get-Process`, using the `Get-Service` command without parameters returns all services.</span></span> <span data-ttu-id="8e198-110">Sie können nach Name filtern, und Sie können sogar ein Sternchen als Platzhalterzeichen verwenden:</span><span class="sxs-lookup"><span data-stu-id="8e198-110">You can filter by name, even using an asterisk as a wildcard:</span></span>

```powershell
PS> Get-Service -Name se*

Status   Name               DisplayName
------   ----               -----------
Running  seclogon           Secondary Logon
Running  SENS               System Event Notification
Stopped  ServiceLayer       ServiceLayer
```

<span data-ttu-id="8e198-111">Weil nicht immer offensichtlich ist, welcher Name der echte Name für einen Dienst ist, möchten Sie möglicherweise über den Anzeigenamen nach Diensten suchen.</span><span class="sxs-lookup"><span data-stu-id="8e198-111">Because it is not always obvious what the real name for the service is, you may find you need to find services by display name.</span></span> <span data-ttu-id="8e198-112">Dazu können Sie nach einem bestimmten Namen, mit Platzhaltern oder mit einer Liste von Anzeigenamen suchen:</span><span class="sxs-lookup"><span data-stu-id="8e198-112">You can do this by specific name, using wildcards, or using a list of display names:</span></span>

```powershell
PS> Get-Service -DisplayName se*

Status   Name               DisplayName
------   ----               -----------
Running  lanmanserver       Server
Running  SamSs              Security Accounts Manager
Running  seclogon           Secondary Logon
Stopped  ServiceLayer       ServiceLayer
Running  wscsvc             Security Center

PS> Get-Service -DisplayName ServiceLayer,Server

Status   Name               DisplayName
------   ----               -----------
Running  lanmanserver       Server
Stopped  ServiceLayer       ServiceLayer
```

<span data-ttu-id="8e198-113">Sie können den „ComputerName“-Parameter des „Get-Service“-Cmdlets verwenden, um die Dienste auf Remotecomputern abzurufen.</span><span class="sxs-lookup"><span data-stu-id="8e198-113">You can use the ComputerName parameter of the Get-Service cmdlet to get the services on remote computers.</span></span> <span data-ttu-id="8e198-114">Der „ComputerName“-Parameter akzeptiert mehrere Werte sowie Platzhalterzeichen, sodass Sie die Dienste auf mehreren Computern mit einem einzigen Befehl abrufen können.</span><span class="sxs-lookup"><span data-stu-id="8e198-114">The ComputerName parameter accepts multiple values and wildcard characters, so you can get the services on multiple computers with a single command.</span></span> <span data-ttu-id="8e198-115">Beispielsweise ruft der folgende Befehl die Dienste auf dem Remotecomputer „Server01“ ab.</span><span class="sxs-lookup"><span data-stu-id="8e198-115">For example, the following command gets the services on the Server01 remote computer.</span></span>

```powershell
Get-Service -ComputerName Server01
```

## <a name="getting-required-and-dependent-services"></a><span data-ttu-id="8e198-116">Abrufen von erforderlichen und abhängigen Diensten</span><span class="sxs-lookup"><span data-stu-id="8e198-116">Getting Required and Dependent Services</span></span>

<span data-ttu-id="8e198-117">Das „Get-Service“-Cmdlet hat zwei Parameter, die bei der Verwaltung von Diensten sehr hilfreich sind.</span><span class="sxs-lookup"><span data-stu-id="8e198-117">The Get-Service cmdlet has two parameters that are very useful in service administration.</span></span> <span data-ttu-id="8e198-118">Der „DependentServices“-Parameter bewirkt, dass Dienste abgerufen werden, die vom angegebenen Dienst abhängen.</span><span class="sxs-lookup"><span data-stu-id="8e198-118">The DependentServices parameter gets services that depend on the service.</span></span> <span data-ttu-id="8e198-119">Der „RequiredServices“-Parameter bewirkt, dass Dienste abgerufen, von denen der angegebene Dienst abhängt.</span><span class="sxs-lookup"><span data-stu-id="8e198-119">The RequiredServices parameter gets services upon which this service depends.</span></span>

<span data-ttu-id="8e198-120">Diese Parameter bewirken lediglich, dass die Werte der Eigenschaften „DependentServices und „ServicesDependedOn“ (Alias = „RequiredServices“) des von „Get-Service“ zurückgegebenen „System.ServiceProcess.ServiceController“-Objekts angezeigt werden, aber sie vereinfachen Befehle und machen das Abrufen dieser Informationen viel einfacher.</span><span class="sxs-lookup"><span data-stu-id="8e198-120">These parameters just display the values of the DependentServices and ServicesDependedOn (alias=RequiredServices) properties of the System.ServiceProcess.ServiceController object that Get-Service returns, but they simplify commands and make getting this information much simpler.</span></span>

<span data-ttu-id="8e198-121">Der folgende Befehl ruft die Dienste ab, die für den „LanmanWorkstation“-Dienst erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="8e198-121">The following command gets the services that the LanmanWorkstation service requires.</span></span>

```powershell
PS> Get-Service -Name LanmanWorkstation -RequiredServices

Status   Name               DisplayName
------   ----               -----------
Running  MRxSmb20           SMB 2.0 MiniRedirector
Running  bowser             Bowser
Running  MRxSmb10           SMB 1.x MiniRedirector
Running  NSI                Network Store Interface Service
```

<span data-ttu-id="8e198-122">Der folgende Befehl ruft die Dienste ab, für die der „LanmanWorkstation“-Dienst erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="8e198-122">The following command gets the services that require the LanmanWorkstation service.</span></span>

```powershell
PS> Get-Service -Name LanmanWorkstation -DependentServices

Status   Name               DisplayName
------   ----               -----------
Running  SessionEnv         Terminal Services Configuration
Running  Netlogon           Netlogon
Stopped  Browser            Computer Browser
Running  BITS               Background Intelligent Transfer Ser...
```

<span data-ttu-id="8e198-123">Sie können sogar alle Dienste abrufen, für die es Abhängigkeiten gibt.</span><span class="sxs-lookup"><span data-stu-id="8e198-123">You can even get all services that have dependencies.</span></span> <span data-ttu-id="8e198-124">Im folgenden Befehl wird genau das getan und anschließend das Cmdlet „Format-Table“ verwendet, um für die Dienste auf dem Computer die Eigenschaften „Status“, „Name“, „RequiredServices“ und „DependentServices“ anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8e198-124">The following command does just that, and then it uses the Format-Table cmdlet to display the Status, Name, RequiredServices and DependentServices properties of the services on the computer.</span></span>

```powershell
Get-Service -Name * | Where-Object {$_.RequiredServices -or $_.DependentServices} |
  Format-Table -Property Status, Name, RequiredServices, DependentServices -auto
```

## <a name="stopping-starting-suspending-and-restarting-services"></a><span data-ttu-id="8e198-125">Beenden, Starten, Anhalten und Neustarten von Diensten</span><span class="sxs-lookup"><span data-stu-id="8e198-125">Stopping, Starting, Suspending, and Restarting Services</span></span>

<span data-ttu-id="8e198-126">Die „Service“-Cmdlets die alle haben dieselbe allgemeine Form.</span><span class="sxs-lookup"><span data-stu-id="8e198-126">The Service cmdlets all have the same general form.</span></span> <span data-ttu-id="8e198-127">Dienste können als allgemeine Namen oder Anzeigenamen angegeben werden, und es können Listen sowie Platzhalter als Werte angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="8e198-127">Services can be specified by common name or display name, and take lists and wildcards as values.</span></span> <span data-ttu-id="8e198-128">Um den Druckspooler zu beenden, verwenden Sie folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="8e198-128">To stop the print spooler, use:</span></span>

```powershell
Stop-Service -Name spooler
```

<span data-ttu-id="8e198-129">Um den Druckspooler zu starten, nachdem er beendet wurde, verwenden Sie folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="8e198-129">To start the print spooler after it is stopped, use:</span></span>

```powershell
Start-Service -Name spooler
```

<span data-ttu-id="8e198-130">Um den Druckspooler anzuhalten, verwenden Sie folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="8e198-130">To suspend the print spooler, use:</span></span>

```powershell
Suspend-Service -Name spooler
```

<span data-ttu-id="8e198-131">Das `Restart-Service`-Cmdlet funktioniert in gleicher Weise wie die anderen Service-Cmdlets, aber es werden einige komplexere Beispiele für dieses Cmdlet erläutert.</span><span class="sxs-lookup"><span data-stu-id="8e198-131">The `Restart-Service` cmdlet works in the same manner as the other Service cmdlets, but we will show some more complex examples for it.</span></span> <span data-ttu-id="8e198-132">Bei der einfachsten Verwendung geben Sie den Namen des Diensts an:</span><span class="sxs-lookup"><span data-stu-id="8e198-132">In the simplest use, you specify the name of the service:</span></span>

```powershell
PS> Restart-Service -Name spooler

WARNING: Waiting for service 'Print Spooler (Spooler)' to finish starting...
WARNING: Waiting for service 'Print Spooler (Spooler)' to finish starting...
PS>
```

<span data-ttu-id="8e198-133">Sie werden feststellen, dass eine wiederholte Warnmeldung zum Startvorgang des Druckspoolers angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="8e198-133">You will notice that you get a repeated warning message about the Print Spooler starting up.</span></span> <span data-ttu-id="8e198-134">Wenn Sie einen Dienstvorgang ausführen, der einige Zeit dauert, werden Sie von Windows PowerShell benachrichtigt, dass weiterhin versucht wird, die Aufgabe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="8e198-134">When you perform a service operation that takes some time, Windows PowerShell will notify you that it is still attempting to perform the task.</span></span>

<span data-ttu-id="8e198-135">Wenn Sie mehrere Dienste neu starten möchten, können Sie eine Liste der Dienste abrufen, diese Liste filtern und dann den Neustart ausführen:</span><span class="sxs-lookup"><span data-stu-id="8e198-135">If you want to restart multiple services, you can get a list of services, filter them, and then perform the restart:</span></span>

```powershell
PS> Get-Service | Where-Object -FilterScript {$_.CanStop} | Restart-Service

WARNING: Waiting for service 'Computer Browser (Browser)' to finish stopping...
WARNING: Waiting for service 'Computer Browser (Browser)' to finish stopping...
Restart-Service : Cannot stop service 'Logical Disk Manager (dmserver)' because
 it has dependent services. It can only be stopped if the Force flag is set.
At line:1 char:57
+ Get-Service | Where-Object -FilterScript {$_.CanStop} | Restart-Service <<<<
WARNING: Waiting for service 'Print Spooler (Spooler)' to finish starting...
WARNING: Waiting for service 'Print Spooler (Spooler)' to finish starting...
```

<span data-ttu-id="8e198-136">Diese „Service“-Cmdlets haben keinen „ComputerName“-Parameter, Sie können sie aber auf einem Remotecomputer ausführen, indem Sie das „Invoke-Command“-Cmdlet verwenden.</span><span class="sxs-lookup"><span data-stu-id="8e198-136">These Service cmdlets do not have a ComputerName parameter, but you can run them on a remote computer by using the Invoke-Command cmdlet.</span></span> <span data-ttu-id="8e198-137">Beispielsweise startet der folgende Befehl den „Spooler“-Dienst auf dem Remotecomputer „Server01“ neu.</span><span class="sxs-lookup"><span data-stu-id="8e198-137">For example, the following command restarts the Spooler service on the Server01 remote computer.</span></span>

```powershell
Invoke-Command -ComputerName Server01 {Restart-Service Spooler}
```

## <a name="setting-service-properties"></a><span data-ttu-id="8e198-138">Festlegen von Diensteigenschaften</span><span class="sxs-lookup"><span data-stu-id="8e198-138">Setting Service Properties</span></span>

<span data-ttu-id="8e198-139">Das Cmdlet „`Set-Service`“ ändert die Eigenschaften eines Diensts auf einem lokalen Computer oder Remotecomputer.</span><span class="sxs-lookup"><span data-stu-id="8e198-139">The `Set-Service` cmdlet changes the properties of a service on a local or remote computer.</span></span> <span data-ttu-id="8e198-140">Weil der Dienststatus eine Eigenschaft ist, können Sie dieses Cmdlet verwenden, um einen Dienst zu starten, zu beenden und anzuhalten.</span><span class="sxs-lookup"><span data-stu-id="8e198-140">Because the service status is a property, you can use this cmdlet to start, stop, and suspend a service.</span></span>
<span data-ttu-id="8e198-141">Das Cmdlet „Set-Service“ hat außerdem einen „StartupType“-Parameter, über den Sie den Starttyp des Diensts ändern können.</span><span class="sxs-lookup"><span data-stu-id="8e198-141">The Set-Service cmdlet also has a StartupType parameter that lets you change the service startup type.</span></span>

<span data-ttu-id="8e198-142">Wenn Sie „`Set-Service`“ unter Windows Vista und höheren Versionen von Windows verwenden möchten, öffnen Sie Windows PowerShell mit der Option „Als Administrator ausführen“.</span><span class="sxs-lookup"><span data-stu-id="8e198-142">To use `Set-Service` on Windows Vista and later versions of Windows, open Windows PowerShell with the "Run as administrator" option.</span></span>

<span data-ttu-id="8e198-143">Weitere Informationen hierzu finden Sie unter [Set-Service](/powershell/module/Microsoft.PowerShell.Management/set-service).</span><span class="sxs-lookup"><span data-stu-id="8e198-143">For more information, see [Set-Service](/powershell/module/Microsoft.PowerShell.Management/set-service)</span></span>

## <a name="see-also"></a><span data-ttu-id="8e198-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8e198-144">See Also</span></span>

- [<span data-ttu-id="8e198-145">Get-Service</span><span class="sxs-lookup"><span data-stu-id="8e198-145">Get-Service</span></span>](/powershell/module/Microsoft.PowerShell.Management/get-service)
- [<span data-ttu-id="8e198-146">Set-Service</span><span class="sxs-lookup"><span data-stu-id="8e198-146">Set-Service</span></span>](/powershell/module/Microsoft.PowerShell.Management/set-service)
- [<span data-ttu-id="8e198-147">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="8e198-147">Restart-Service</span></span>](/powershell/module/Microsoft.PowerShell.Management/restart-service)
- [<span data-ttu-id="8e198-148">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="8e198-148">Suspend-Service</span></span>](/powershell/module/Microsoft.PowerShell.Management/suspend-service)
