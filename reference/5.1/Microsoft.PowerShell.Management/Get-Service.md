---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-service?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Service
ms.openlocfilehash: 0c007f1becd7364806cfd47e18cf05995b81e0f7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215404"
---
# <span data-ttu-id="24a5b-103">Get-Service</span><span class="sxs-lookup"><span data-stu-id="24a5b-103">Get-Service</span></span>

## <span data-ttu-id="24a5b-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="24a5b-104">SYNOPSIS</span></span>
<span data-ttu-id="24a5b-105">Ruft die Dienste auf einem lokalen Computer oder einem Remotecomputer ab.</span><span class="sxs-lookup"><span data-stu-id="24a5b-105">Gets the services on a local or remote computer.</span></span>

## <span data-ttu-id="24a5b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="24a5b-106">SYNTAX</span></span>

### <span data-ttu-id="24a5b-107">Standard (Standard)</span><span class="sxs-lookup"><span data-stu-id="24a5b-107">Default (Default)</span></span>

```
Get-Service [[-Name] <String[]>] [-ComputerName <String[]>] [-DependentServices] [-RequiredServices]
 [-Include <String[]>] [-Exclude <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="24a5b-108">DisplayName</span><span class="sxs-lookup"><span data-stu-id="24a5b-108">DisplayName</span></span>

```
Get-Service [-ComputerName <String[]>] [-DependentServices] [-RequiredServices] -DisplayName <String[]>
 [-Include <String[]>] [-Exclude <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="24a5b-109">InputObject</span><span class="sxs-lookup"><span data-stu-id="24a5b-109">InputObject</span></span>

```
Get-Service [-ComputerName <String[]>] [-DependentServices] [-RequiredServices] [-Include <String[]>]
 [-Exclude <String[]>] [-InputObject <ServiceController[]>] [<CommonParameters>]
```

## <span data-ttu-id="24a5b-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="24a5b-110">DESCRIPTION</span></span>

<span data-ttu-id="24a5b-111">Mit dem " **Get-Service"-** Cmdlet werden Objekte abgerufen, die die Dienste auf einem lokalen Computer oder auf einem Remote Computer darstellen, einschließlich der Ausführung und Beendigung der Dienste.</span><span class="sxs-lookup"><span data-stu-id="24a5b-111">The **Get-Service** cmdlet gets objects that represent the services on a local computer or on a remote computer, including running and stopped services.</span></span>

<span data-ttu-id="24a5b-112">Sie können dieses Cmdlet anweisen, nur bestimmte Dienste zu erhalten, indem Sie den Dienstnamen oder anzeigen amen der Dienste angeben, oder Sie können Dienst Objekte über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="24a5b-112">You can direct this cmdlet to get only particular services by specifying the service name or the display name of the services, or you can pipe service objects to this cmdlet.</span></span>

## <span data-ttu-id="24a5b-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="24a5b-113">EXAMPLES</span></span>

### <span data-ttu-id="24a5b-114">Beispiel 1: alle Dienste auf dem Computer</span><span class="sxs-lookup"><span data-stu-id="24a5b-114">Example 1: Get all services on the computer</span></span>

```powershell
Get-Service
```

<span data-ttu-id="24a5b-115">Mit diesem Befehl werden alle Dienste auf dem Computer abgerufen.</span><span class="sxs-lookup"><span data-stu-id="24a5b-115">This command gets all of the services on the computer.</span></span>
<span data-ttu-id="24a5b-116">Dies verhält sich, als ob Sie eingegeben haben `Get-Service *` .</span><span class="sxs-lookup"><span data-stu-id="24a5b-116">It behaves as though you typed `Get-Service *`.</span></span>
<span data-ttu-id="24a5b-117">In der Standardanzeige werden der Status, der Dienstname und der Anzeigename der einzelnen Dienste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="24a5b-117">The default display shows the status, service name, and display name of each service.</span></span>

### <span data-ttu-id="24a5b-118">Beispiel 2: erhalten von Diensten, die mit einer Such Zeichenfolge beginnen</span><span class="sxs-lookup"><span data-stu-id="24a5b-118">Example 2: Get services that begin with a search string</span></span>

```powershell
Get-Service "wmi*"
```

<span data-ttu-id="24a5b-119">Mit diesem Befehl werden Dienste mit Dienstnamen abgerufen, die mit WMI beginnen (das Akronym für Windows-Verwaltungsinstrumentation).</span><span class="sxs-lookup"><span data-stu-id="24a5b-119">This command retrieves services with service names that begin with WMI (the acronym for Windows Management Instrumentation).</span></span>

### <span data-ttu-id="24a5b-120">Beispiel 3: Anzeigen von Diensten, die eine Such Zeichenfolge enthalten</span><span class="sxs-lookup"><span data-stu-id="24a5b-120">Example 3: Display services that include a search string</span></span>

```powershell
Get-Service -Displayname "*network*"
```

<span data-ttu-id="24a5b-121">Mit diesem Befehl werden Dienste angezeigt, deren Anzeige Name das Wort "Network" enthält.</span><span class="sxs-lookup"><span data-stu-id="24a5b-121">This command displays services with a display name that includes the word network.</span></span>
<span data-ttu-id="24a5b-122">Durch das Suchen des Anzeigenamens können Sie Netzwerkdienste suchen, selbst wenn der Dienstname nicht das Wort %%amp;quot;Net%%amp;quot; enthält, beispielsweise %%amp;quot;xmlprov%%amp;quot; (der Netzwerkbereitstellungsdienst).</span><span class="sxs-lookup"><span data-stu-id="24a5b-122">Searching the display name finds network-related services even when the service name does not include "Net", such as xmlprov, the Network Provisioning Service.</span></span>

### <span data-ttu-id="24a5b-123">Beispiel 4: erhalten von Diensten, die mit einer Such Zeichenfolge und einem Ausschluss beginnen</span><span class="sxs-lookup"><span data-stu-id="24a5b-123">Example 4: Get services that begin with a search string and an exclusion</span></span>

```powershell
Get-Service -Name "win*" -Exclude "WinRM"
```

<span data-ttu-id="24a5b-124">Diese Befehle erhalten nur die Dienste, deren Dienstnamen mit "Win" beginnen, mit Ausnahme des WinRM-Diensts.</span><span class="sxs-lookup"><span data-stu-id="24a5b-124">These commands get only the services with service names that begin with win, except for the WinRM service.</span></span>

### <span data-ttu-id="24a5b-125">Beispiel 5: Anzeigen von Diensten, die zurzeit aktiv sind</span><span class="sxs-lookup"><span data-stu-id="24a5b-125">Example 5: Display services that are currently active</span></span>

```powershell
Get-Service | Where-Object {$_.Status -eq "Running"}
```

<span data-ttu-id="24a5b-126">Mit diesem Befehl werden nur die Dienste angezeigt, die zurzeit aktiv sind.</span><span class="sxs-lookup"><span data-stu-id="24a5b-126">This command displays only the services that are currently active.</span></span>
<span data-ttu-id="24a5b-127">Er verwendet das **Get-Service-** Cmdlet, um alle Dienste auf dem Computer zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="24a5b-127">It uses the **Get-Service** cmdlet to get all of the services on the computer.</span></span>
<span data-ttu-id="24a5b-128">Der Pipeline Operator (|) übergibt die Ergebnisse an das Where-Object-Cmdlet, das nur die Dienste auswählt, deren Status-Eigenschaft ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="24a5b-128">The pipeline operator (|) passes the results to the Where-Object cmdlet, which selects only the services with a Status property that equals Running.</span></span>

<span data-ttu-id="24a5b-129">%%amp;quot;Status%%amp;quot; ist nur eine der Eigenschaften von Dienstobjekten.</span><span class="sxs-lookup"><span data-stu-id="24a5b-129">Status is only one property of service objects.</span></span>
<span data-ttu-id="24a5b-130">Um alle Eigenschaften anzuzeigen, geben Sie ein `Get-Service | Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="24a5b-130">To see all of the properties, type `Get-Service | Get-Member`.</span></span>

### <span data-ttu-id="24a5b-131">Beispiel 6: erhalten der Dienste auf einem Remote Computer</span><span class="sxs-lookup"><span data-stu-id="24a5b-131">Example 6: Get the services on a remote computer</span></span>

```powershell
Get-Service -ComputerName "Server02"
```

<span data-ttu-id="24a5b-132">Dieser Befehl ruft die Dienste auf dem Remotecomputer %%amp;quot;Server02%%amp;quot; ab.</span><span class="sxs-lookup"><span data-stu-id="24a5b-132">This command gets the services on the Server02 remote computer.</span></span>

<span data-ttu-id="24a5b-133">Da der Computer *Name* -Parameter von **Get-Service** nicht Windows PowerShell-Remoting verwendet, können Sie diesen Parameter auch dann verwenden, wenn der Computer nicht für Remoting in Windows PowerShell konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="24a5b-133">Because the *ComputerName* parameter of **Get-Service** does not use Windows PowerShell remoting, you can use this parameter even if the computer is not configured for remoting in Windows PowerShell.</span></span>

### <span data-ttu-id="24a5b-134">Beispiel 7: Auflisten der Dienste auf dem lokalen Computer, die über abhängige Dienste verfügen</span><span class="sxs-lookup"><span data-stu-id="24a5b-134">Example 7: List the services on the local computer that have dependent services</span></span>

```powershell
Get-Service |
  Where-Object {$_.DependentServices} |
    Format-List -Property Name, DependentServices, @{
      Label="NoOfDependentServices"; Expression={$_.dependentservices.count}
    }
```

```Output
Name                  : AudioEndpointBuilder
DependentServices     : {AudioSrv}
NoOfDependentServices : 1

Name                  : Dhcp
DependentServices     : {WinHttpAutoProxySvc}
NoOfDependentServices : 1
...
```

<span data-ttu-id="24a5b-135">Der erste Befehl verwendet das **Get-Service-** Cmdlet, um die Dienste auf dem Computer zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="24a5b-135">The first command uses the **Get-Service** cmdlet to get the services on the computer.</span></span>
<span data-ttu-id="24a5b-136">Ein Pipeline Operator (|) sendet die Dienste an das **Where-Object-** Cmdlet, das die Dienste auswählt, deren **DependentServices** -Eigenschaft nicht NULL ist.</span><span class="sxs-lookup"><span data-stu-id="24a5b-136">A pipeline operator (|) sends the services to the **Where-Object** cmdlet, which selects the services whose **DependentServices** property is not null.</span></span>

<span data-ttu-id="24a5b-137">Die Ergebnisse werden mit einem anderen Pipelineoperator an das Cmdlet %%amp;quot;Format-List%%amp;quot; gesendet.</span><span class="sxs-lookup"><span data-stu-id="24a5b-137">Another pipeline operator sends the results to the Format-List cmdlet.</span></span>
<span data-ttu-id="24a5b-138">Der Befehl verwendet den *Property* -Parameter, um den Namen des Diensts, den Namen der abhängigen Dienste und eine berechnete Eigenschaft anzuzeigen, die die Anzahl der abhängigen Dienste anzeigt, die jeder Dienst besitzt.</span><span class="sxs-lookup"><span data-stu-id="24a5b-138">The command uses its *Property* parameter to display the name of the service, the name of the dependent services, and a calculated property that displays the number of dependent services that each service has.</span></span>

### <span data-ttu-id="24a5b-139">Beispiel 8: Sortieren von Diensten nach Eigenschafts Wert</span><span class="sxs-lookup"><span data-stu-id="24a5b-139">Example 8: Sort services by property value</span></span>

```powershell
Get-Service "s*" | Sort-Object status
```

```Output
Status   Name               DisplayName
------   ----               -----------
Stopped  stisvc             Windows Image Acquisition (WIA)
Stopped  SwPrv              MS Software Shadow Copy Provider
Stopped  SysmonLog          Performance Logs and Alerts
Running  Spooler            Print Spooler
Running  srservice          System Restore Service
Running  SSDPSRV            SSDP Discovery Service
Running  ShellHWDetection   Shell Hardware Detection
Running  Schedule           Task Scheduler
Running  SCardSvr           Smart Card
Running  SamSs              Security Accounts Manager
Running  SharedAccess       Windows Firewall/Internet Connectio...
Running  SENS               System Event Notification
Running  seclogon           Secondary Logon
```

<span data-ttu-id="24a5b-140">Dieser Befehl zeigt, dass beim Sortieren von Diensten in aufsteigender Reihenfolge nach dem Wert der **Status** -Eigenschaft beendete Dienste vor dem Ausführen von Diensten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="24a5b-140">This command shows that when you sort services in ascending order by the value of their **Status** property, stopped services appear before running services.</span></span>
<span data-ttu-id="24a5b-141">Dies liegt daran, dass der Wert von "Status" eine Enumeration ist, in der "beendet" den Wert "1" aufweist und "Running" den Wert 4 aufweist.</span><span class="sxs-lookup"><span data-stu-id="24a5b-141">This happens because the value of Status is an enumeration, in which Stopped has a value of 1, and Running has a value of 4.</span></span>

<span data-ttu-id="24a5b-142">Verwenden Sie zum Auflisten der laufenden Dienste zuerst den *Absteig* enden Parameter des Sort-Object-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="24a5b-142">To list running services first, use the *Descending* parameter of the Sort-Object cmdlet.</span></span>

### <span data-ttu-id="24a5b-143">Beispiel 9: Dienste auf mehreren Computern</span><span class="sxs-lookup"><span data-stu-id="24a5b-143">Example 9: Get services on multiple computers</span></span>

```powershell
Get-Service -Name "WinRM" -ComputerName "localhost", "Server01", "Server02" |
 Format-Table -Property MachineName, Status, Name, DisplayName -auto
```

```Output
MachineName    Status  Name  DisplayName
------------   ------  ----  -----------
localhost      Running WinRM Windows Remote Management (WS-Management)
Server01       Running WinRM Windows Remote Management (WS-Management)
Server02       Running WinRM Windows Remote Management (WS-Management)
```

<span data-ttu-id="24a5b-144">Dieser Befehl verwendet das **Get-Service-** Cmdlet, um einen Get-Service WinRM-Befehl auf zwei Remote Computern und dem lokalen Computer ("localhost") auszuführen.</span><span class="sxs-lookup"><span data-stu-id="24a5b-144">This command uses the **Get-Service** cmdlet to run a Get-Service Winrm command on two remote computers and the local computer ("localhost").</span></span>

<span data-ttu-id="24a5b-145">Der Befehl wird auf den Remote Computern ausgeführt, und die Ergebnisse werden an den lokalen Computer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="24a5b-145">The command runs on the remote computers, and the results are returned to the local computer.</span></span>
<span data-ttu-id="24a5b-146">Ein Pipeline Operator (|) sendet die Ergebnisse an das **Format-Table-** Cmdlet, das die Dienste als Tabelle formatiert.</span><span class="sxs-lookup"><span data-stu-id="24a5b-146">A pipeline operator (|) sends the results to the **Format-Table** cmdlet, which formats the services as a table.</span></span>
<span data-ttu-id="24a5b-147">Der **Format-Table-** Befehl verwendet den *Property* -Parameter, um die Eigenschaften anzugeben, die in der Tabelle angezeigt werden, einschließlich der **MachineName** -Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="24a5b-147">The **Format-Table** command uses the *Property* parameter to specify the properties displayed in the table, including the **MachineName** property.</span></span>

### <span data-ttu-id="24a5b-148">Beispiel 10: erhalten der abhängigen Dienste eines Diensts</span><span class="sxs-lookup"><span data-stu-id="24a5b-148">Example 10: Get the dependent services of a service</span></span>

```powershell
Get-Service "WinRM" -RequiredServices
```

<span data-ttu-id="24a5b-149">Mit diesem Befehl werden die für den WinRM-Dienst erforderlichen Dienste abgerufen.</span><span class="sxs-lookup"><span data-stu-id="24a5b-149">This command gets the services that the WinRM service requires.</span></span>

<span data-ttu-id="24a5b-150">Der Befehl gibt den Wert der **ServicesDependedOn** -Eigenschaft des Dienstanbieter zurück.</span><span class="sxs-lookup"><span data-stu-id="24a5b-150">The command returns the value of the **ServicesDependedOn** property of the service.</span></span>

### <span data-ttu-id="24a5b-151">Beispiel 11: erhalten eines Dienstanbieter über den Pipeline-Operator</span><span class="sxs-lookup"><span data-stu-id="24a5b-151">Example 11: Get a service through the pipeline operator</span></span>

```powershell
"WinRM" | Get-Service
```

<span data-ttu-id="24a5b-152">Mit diesem Befehl wird der WinRM-Dienst auf dem lokalen Computer abgerufen.</span><span class="sxs-lookup"><span data-stu-id="24a5b-152">This command gets the WinRM service on the local computer.</span></span>
<span data-ttu-id="24a5b-153">Dieses Beispiel zeigt, dass Sie eine Dienstnamen Zeichenfolge (in Anführungszeichen eingeschlossen) über die Pipeline an **Get-Service** übergeben können.</span><span class="sxs-lookup"><span data-stu-id="24a5b-153">This example shows that you can pipe a service name string (enclosed in quotation marks) to **Get-Service** .</span></span>

## <span data-ttu-id="24a5b-154">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="24a5b-154">PARAMETERS</span></span>

### <span data-ttu-id="24a5b-155">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="24a5b-155">-ComputerName</span></span>

<span data-ttu-id="24a5b-156">Ruft die Dienste ab, die auf den angegebenen Computern ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="24a5b-156">Gets the services running on the specified computers.</span></span>
<span data-ttu-id="24a5b-157">Die Standardeinstellung ist der lokale Computer.</span><span class="sxs-lookup"><span data-stu-id="24a5b-157">The default is the local computer.</span></span>

<span data-ttu-id="24a5b-158">Geben Sie den NetBIOS-Namen, eine IP-Adresse oder einen voll qualifizierten Domänen Namen (Fully Qualified Domain Name, FQDN) eines Remote Computers ein.</span><span class="sxs-lookup"><span data-stu-id="24a5b-158">Type the NetBIOS name, an IP address, or a fully qualified domain name (FQDN) of a remote computer.</span></span>
<span data-ttu-id="24a5b-159">Geben Sie den Computernamen, einen Punkt (.) oder einen localhost ein, um den lokalen Computer anzugeben.</span><span class="sxs-lookup"><span data-stu-id="24a5b-159">To specify the local computer, type the computer name, a dot (.), or localhost.</span></span>

<span data-ttu-id="24a5b-160">Dieser Parameter beruht nicht auf Windows PowerShell-Remoting.</span><span class="sxs-lookup"><span data-stu-id="24a5b-160">This parameter does not rely on Windows PowerShell remoting.</span></span>
<span data-ttu-id="24a5b-161">Sie können den *Computername* -Parameter von **Get-Service** auch dann verwenden, wenn der Computer nicht für das Ausführen von Remote Befehlen konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="24a5b-161">You can use the *ComputerName* parameter of **Get-Service** even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="24a5b-162">-DependentServices</span><span class="sxs-lookup"><span data-stu-id="24a5b-162">-DependentServices</span></span>

<span data-ttu-id="24a5b-163">Gibt an, dass dieses Cmdlet nur die Dienste abruft, die vom angegebenen Dienst abhängen.</span><span class="sxs-lookup"><span data-stu-id="24a5b-163">Indicates that this cmdlet gets only the services that depend upon the specified service.</span></span>

<span data-ttu-id="24a5b-164">Standardmäßig ruft dieses Cmdlet alle Dienste ab.</span><span class="sxs-lookup"><span data-stu-id="24a5b-164">By default, this cmdlet gets all services.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: DS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="24a5b-165">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="24a5b-165">-DisplayName</span></span>

<span data-ttu-id="24a5b-166">Gibt die anzeigen amen der abzurufenden Dienste als Zeichen folgen Array an.</span><span class="sxs-lookup"><span data-stu-id="24a5b-166">Specifies, as a string array, the display names of services to be retrieved.</span></span>
<span data-ttu-id="24a5b-167">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="24a5b-167">Wildcards are permitted.</span></span>
<span data-ttu-id="24a5b-168">Standardmäßig ruft dieses Cmdlet alle Dienste auf dem Computer ab.</span><span class="sxs-lookup"><span data-stu-id="24a5b-168">By default, this cmdlet gets all services on the computer.</span></span>

```yaml
Type: System.String[]
Parameter Sets: DisplayName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="24a5b-169">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="24a5b-169">-Exclude</span></span>

<span data-ttu-id="24a5b-170">Gibt als Zeichen folgen Array einen Dienst oder Dienste an, die von diesem Cmdlet aus dem Vorgang ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="24a5b-170">Specifies, as a string array, a service or services that this cmdlet excludes from the operation.</span></span>
<span data-ttu-id="24a5b-171">Der Wert dieses Parameters qualifiziert den *Name* -Parameter.</span><span class="sxs-lookup"><span data-stu-id="24a5b-171">The value of this parameter qualifies the *Name* parameter.</span></span>
<span data-ttu-id="24a5b-172">Geben Sie ein Namenselement oder -muster wie %%amp;quot;s\*%%amp;quot; ein.</span><span class="sxs-lookup"><span data-stu-id="24a5b-172">Enter a name element or pattern, such as "s\*".</span></span>
<span data-ttu-id="24a5b-173">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="24a5b-173">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="24a5b-174">-Include</span><span class="sxs-lookup"><span data-stu-id="24a5b-174">-Include</span></span>

<span data-ttu-id="24a5b-175">Gibt als Zeichen folgen Array einen Dienst oder Dienste an, die dieses Cmdlet in den Vorgang einschließt.</span><span class="sxs-lookup"><span data-stu-id="24a5b-175">Specifies, as a string array, a service or services that this cmdlet includes in the operation.</span></span>
<span data-ttu-id="24a5b-176">Der Wert dieses Parameters qualifiziert den *Name* -Parameter.</span><span class="sxs-lookup"><span data-stu-id="24a5b-176">The value of this parameter qualifies the *Name* parameter.</span></span>
<span data-ttu-id="24a5b-177">Geben Sie ein Namenselement oder -muster wie %%amp;quot;s\*%%amp;quot; ein.</span><span class="sxs-lookup"><span data-stu-id="24a5b-177">Enter a name element or pattern, such as "s\*".</span></span>
<span data-ttu-id="24a5b-178">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="24a5b-178">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="24a5b-179">-InputObject</span><span class="sxs-lookup"><span data-stu-id="24a5b-179">-InputObject</span></span>

<span data-ttu-id="24a5b-180">Gibt **ServiceController** -Objekte an, die die abzurufenden Dienste darstellen.</span><span class="sxs-lookup"><span data-stu-id="24a5b-180">Specifies **ServiceController** objects representing the services to be retrieved.</span></span>
<span data-ttu-id="24a5b-181">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="24a5b-181">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>
<span data-ttu-id="24a5b-182">Sie können ein Dienst Objekt auch über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="24a5b-182">You can also pipe a service object to this cmdlet.</span></span>

```yaml
Type: System.ServiceProcess.ServiceController[]
Parameter Sets: InputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="24a5b-183">-Name</span><span class="sxs-lookup"><span data-stu-id="24a5b-183">-Name</span></span>

<span data-ttu-id="24a5b-184">Gibt die Dienstnamen der abzurufenden Dienste an.</span><span class="sxs-lookup"><span data-stu-id="24a5b-184">Specifies the service names of services to be retrieved.</span></span>
<span data-ttu-id="24a5b-185">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="24a5b-185">Wildcards are permitted.</span></span>
<span data-ttu-id="24a5b-186">Standardmäßig ruft dieses Cmdlet alle Dienste auf dem Computer ab.</span><span class="sxs-lookup"><span data-stu-id="24a5b-186">By default, this cmdlet gets all of the services on the computer.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases: ServiceName

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="24a5b-187">-Requirements dservices</span><span class="sxs-lookup"><span data-stu-id="24a5b-187">-RequiredServices</span></span>

<span data-ttu-id="24a5b-188">Gibt an, dass dieses Cmdlet nur die Dienste abruft, die dieser Dienst benötigt.</span><span class="sxs-lookup"><span data-stu-id="24a5b-188">Indicates that this cmdlet gets only the services that this service requires.</span></span>

<span data-ttu-id="24a5b-189">Dieser Parameter ruft den Wert der **ServicesDependedOn** -Eigenschaft des Dienstanbieter ab.</span><span class="sxs-lookup"><span data-stu-id="24a5b-189">This parameter gets the value of the **ServicesDependedOn** property of the service.</span></span>
<span data-ttu-id="24a5b-190">Standardmäßig ruft dieses Cmdlet alle Dienste ab.</span><span class="sxs-lookup"><span data-stu-id="24a5b-190">By default, this cmdlet gets all services.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: SDO, ServicesDependedOn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="24a5b-191">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="24a5b-191">CommonParameters</span></span>

<span data-ttu-id="24a5b-192">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="24a5b-192">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="24a5b-193">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="24a5b-193">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="24a5b-194">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="24a5b-194">INPUTS</span></span>

### <span data-ttu-id="24a5b-195">System. ServiceProcess. ServiceController, System. String</span><span class="sxs-lookup"><span data-stu-id="24a5b-195">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="24a5b-196">Sie können ein Dienst Objekt oder einen Dienstnamen über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="24a5b-196">You can pipe a service object or a service name to this cmdlet.</span></span>

## <span data-ttu-id="24a5b-197">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="24a5b-197">OUTPUTS</span></span>

### <span data-ttu-id="24a5b-198">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="24a5b-198">System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="24a5b-199">Dieses Cmdlet gibt Objekte zurück, die die Dienste auf dem Computer darstellen.</span><span class="sxs-lookup"><span data-stu-id="24a5b-199">This cmdlet returns objects that represent the services on the computer.</span></span>

## <span data-ttu-id="24a5b-200">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="24a5b-200">NOTES</span></span>

<span data-ttu-id="24a5b-201">Sie können auch über den integrierten Alias "GSV" auf " **Get-Service** " verweisen.</span><span class="sxs-lookup"><span data-stu-id="24a5b-201">You can also refer to **Get-Service** by its built-in alias, "gsv".</span></span> <span data-ttu-id="24a5b-202">Weitere Informationen finden Sie unter %%amp;quot;about_Aliases%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="24a5b-202">For more information, see about_Aliases.</span></span>

<span data-ttu-id="24a5b-203">Dieses Cmdlet kann nur dann Dienste anzeigen, wenn der aktuelle Benutzer über die Berechtigung verfügt, Sie anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="24a5b-203">This cmdlet can display services only when the current user has permission to see them.</span></span>
<span data-ttu-id="24a5b-204">Wenn dieses Cmdlet keine Dienste anzeigt, verfügen Sie möglicherweise nicht über die Berechtigung, diese anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="24a5b-204">If this cmdlet does not display services, you might not have permission to see them.</span></span>

<span data-ttu-id="24a5b-205">Geben Sie ein, um den Dienstnamen und den anzeigen amen der einzelnen Dienste auf dem System zu ermitteln `Get-Service` .</span><span class="sxs-lookup"><span data-stu-id="24a5b-205">To find the service name and display name of each service on your system, type `Get-Service`.</span></span>
<span data-ttu-id="24a5b-206">Die Dienstnamen werden in der Spalte %%amp;quot;Name%%amp;quot; und die Anzeigenamen in der Spalte %%amp;quot;DisplayName%%amp;quot; aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="24a5b-206">The service names appear in the Name column, and the display names appear in the DisplayName column.</span></span>

<span data-ttu-id="24a5b-207">Wenn Sie aufsteigend nach Statuswert sortieren, werden Dienste mit dem Status %%amp;quot;Stopped%%amp;quot; vor Diensten mit dem Status %%amp;quot;Running%%amp;quot; angezeigt.</span><span class="sxs-lookup"><span data-stu-id="24a5b-207">When you sort in ascending order by status value, "Stopped" services appear before "Running" services.</span></span>
<span data-ttu-id="24a5b-208">Die Status-Eigenschaft eines Diensts ist ein Enumerationswert, in dem die Namen der Status ganzzahlige Werte darstellen.</span><span class="sxs-lookup"><span data-stu-id="24a5b-208">The Status property of a service is an enumerated value in which the names of the statuses represent integer values.</span></span>
<span data-ttu-id="24a5b-209">Die Sortierung basiert auf dem ganzzahligen Wert, nicht dem Namen.</span><span class="sxs-lookup"><span data-stu-id="24a5b-209">The sort is based on the integer value, not the name.</span></span>
<span data-ttu-id="24a5b-210">%%amp;quot;Running%%amp;quot; wird vor %%amp;quot;Stopped%%amp;quot; angezeigt, da %%amp;quot;Stopped%%amp;quot; über den Wert %%amp;quot;1%%amp;quot; verfügt. %%amp;quot;Running%%amp;quot; verfügt über den Wert %%amp;quot;4%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="24a5b-210">"Running" appears before "Stopped" because "Stopped" has a value of "1", and "Running" has a value of "4".</span></span>

## <span data-ttu-id="24a5b-211">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="24a5b-211">RELATED LINKS</span></span>

[<span data-ttu-id="24a5b-212">New-Service</span><span class="sxs-lookup"><span data-stu-id="24a5b-212">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="24a5b-213">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="24a5b-213">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="24a5b-214">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="24a5b-214">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="24a5b-215">Set-Service</span><span class="sxs-lookup"><span data-stu-id="24a5b-215">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="24a5b-216">Start-Service</span><span class="sxs-lookup"><span data-stu-id="24a5b-216">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="24a5b-217">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="24a5b-217">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="24a5b-218">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="24a5b-218">Suspend-Service</span></span>](Suspend-Service.md)
