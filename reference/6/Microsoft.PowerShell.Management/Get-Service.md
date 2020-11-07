---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/30/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-service?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Service
ms.openlocfilehash: 425b5e56286c22b6595954916d8aa66eec807d83
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2020
ms.locfileid: "94345254"
---
# <span data-ttu-id="9cfd4-103">Get-Service</span><span class="sxs-lookup"><span data-stu-id="9cfd4-103">Get-Service</span></span>

## <span data-ttu-id="9cfd4-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="9cfd4-104">SYNOPSIS</span></span>
<span data-ttu-id="9cfd4-105">Ruft die Dienste auf dem Computer ab.</span><span class="sxs-lookup"><span data-stu-id="9cfd4-105">Gets the services on the computer.</span></span>

## <span data-ttu-id="9cfd4-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9cfd4-106">SYNTAX</span></span>

### <span data-ttu-id="9cfd4-107">Standard (Standard)</span><span class="sxs-lookup"><span data-stu-id="9cfd4-107">Default (Default)</span></span>

```
Get-Service [[-Name] <String[]>] [-DependentServices] [-RequiredServices] [-Include <String[]>]
 [-Exclude <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="9cfd4-108">DisplayName</span><span class="sxs-lookup"><span data-stu-id="9cfd4-108">DisplayName</span></span>

```
Get-Service [-DependentServices] [-RequiredServices] -DisplayName <String[]> [-Include <String[]>]
 [-Exclude <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="9cfd4-109">InputObject</span><span class="sxs-lookup"><span data-stu-id="9cfd4-109">InputObject</span></span>

```
Get-Service [-DependentServices] [-RequiredServices] [-Include <String[]>] [-Exclude <String[]>]
 [-InputObject <ServiceController[]>] [<CommonParameters>]
```

## <span data-ttu-id="9cfd4-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9cfd4-110">DESCRIPTION</span></span>

<span data-ttu-id="9cfd4-111">`Get-Service`Mit dem-Cmdlet werden Objekte abgerufen, die die Dienste auf einem Computer darstellen, einschließlich der Ausführung und Beendigung der Dienste.</span><span class="sxs-lookup"><span data-stu-id="9cfd4-111">The `Get-Service` cmdlet gets objects that represent the services on a computer, including running and stopped services.</span></span> <span data-ttu-id="9cfd4-112">Wenn `Get-Service` ohne Parameter ausgeführt wird, werden standardmäßig alle Dienste des lokalen Computers zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9cfd4-112">By default, when `Get-Service` is run without parameters, all the local computer's services are returned.</span></span>

<span data-ttu-id="9cfd4-113">Sie können dieses Cmdlet anweisen, nur bestimmte Dienste zu erhalten, indem Sie den Dienstnamen oder anzeigen amen der Dienste angeben, oder Sie können Dienst Objekte über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="9cfd4-113">You can direct this cmdlet to get only particular services by specifying the service name or the display name of the services, or you can pipe service objects to this cmdlet.</span></span>

## <span data-ttu-id="9cfd4-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="9cfd4-114">EXAMPLES</span></span>

### <span data-ttu-id="9cfd4-115">Beispiel 1: alle Dienste auf dem Computer</span><span class="sxs-lookup"><span data-stu-id="9cfd4-115">Example 1: Get all services on the computer</span></span>

<span data-ttu-id="9cfd4-116">In diesem Beispiel werden alle Dienste auf dem Computer abgerufen.</span><span class="sxs-lookup"><span data-stu-id="9cfd4-116">This example gets all of the services on the computer.</span></span> <span data-ttu-id="9cfd4-117">Dies verhält sich, als ob Sie eingegeben haben `Get-Service *` .</span><span class="sxs-lookup"><span data-stu-id="9cfd4-117">It behaves as though you typed `Get-Service *`.</span></span> <span data-ttu-id="9cfd4-118">In der Standardanzeige werden der Status, der Dienstname und der Anzeigename der einzelnen Dienste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9cfd4-118">The default display shows the status, service name, and display name of each service.</span></span>

```powershell
Get-Service
```

### <span data-ttu-id="9cfd4-119">Beispiel 2: erhalten von Diensten, die mit einer Such Zeichenfolge beginnen</span><span class="sxs-lookup"><span data-stu-id="9cfd4-119">Example 2: Get services that begin with a search string</span></span>

<span data-ttu-id="9cfd4-120">In diesem Beispiel werden Dienste mit Dienstnamen abgerufen, die mit WMI (Windows-Verwaltungsinstrumentation) beginnen.</span><span class="sxs-lookup"><span data-stu-id="9cfd4-120">This example retrieves services with service names that begin with WMI (Windows Management Instrumentation).</span></span>

```powershell
Get-Service "wmi*"
```

### <span data-ttu-id="9cfd4-121">Beispiel 3: Anzeigen von Diensten, die eine Such Zeichenfolge enthalten</span><span class="sxs-lookup"><span data-stu-id="9cfd4-121">Example 3: Display services that include a search string</span></span>

<span data-ttu-id="9cfd4-122">In diesem Beispiel werden Dienste mit einem anzeigen Amen angezeigt, der das Wort "Network" enthält.</span><span class="sxs-lookup"><span data-stu-id="9cfd4-122">This example displays services with a display name that includes the word network.</span></span> <span data-ttu-id="9cfd4-123">Durch das Durchsuchen des anzeigen Amens werden netzwerkbezogene Dienste auch dann gefunden, wenn der Dienst Name NET nicht enthält, wie z. b. xmlprov, den Netzwerk Bereitstellungs Dienst.</span><span class="sxs-lookup"><span data-stu-id="9cfd4-123">Searching the display name finds network-related services even when the service name doesn't include Net, such as xmlprov, the Network Provisioning Service.</span></span>

```powershell
Get-Service -Displayname "*network*"
```

### <span data-ttu-id="9cfd4-124">Beispiel 4: erhalten von Diensten, die mit einer Such Zeichenfolge und einem Ausschluss beginnen</span><span class="sxs-lookup"><span data-stu-id="9cfd4-124">Example 4: Get services that begin with a search string and an exclusion</span></span>

<span data-ttu-id="9cfd4-125">In diesem Beispiel werden nur die Dienste mit Dienstnamen abgerufen, die mit " **Win** " beginnen, mit Ausnahme des WinRM-Diensts.</span><span class="sxs-lookup"><span data-stu-id="9cfd4-125">This example only gets the services with service names that begin with **win** , except for the WinRM service.</span></span>

```powershell
Get-Service -Name "win*" -Exclude "WinRM"
```

### <span data-ttu-id="9cfd4-126">Beispiel 5: Anzeigen von Diensten, die zurzeit aktiv sind</span><span class="sxs-lookup"><span data-stu-id="9cfd4-126">Example 5: Display services that are currently active</span></span>

<span data-ttu-id="9cfd4-127">In diesem Beispiel werden nur die Dienste mit dem Status "wird ausgeführt" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9cfd4-127">This example displays only the services with a status of Running.</span></span>

```powershell
Get-Service | Where-Object {$_.Status -eq "Running"}
```

<span data-ttu-id="9cfd4-128">`Get-Service` Ruft alle Dienste auf dem Computer ab und sendet die Objekte in der Pipeline.</span><span class="sxs-lookup"><span data-stu-id="9cfd4-128">`Get-Service` gets all the services on the computer and sends the objects down the pipeline.</span></span> <span data-ttu-id="9cfd4-129">Mit dem- `Where-Object` Cmdlet werden nur die Dienste ausgewählt, deren **Status** -Eigenschaft ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9cfd4-129">The `Where-Object` cmdlet, selects only the services with a **Status** property that equals Running.</span></span>

<span data-ttu-id="9cfd4-130">%%amp;quot;Status%%amp;quot; ist nur eine der Eigenschaften von Dienstobjekten.</span><span class="sxs-lookup"><span data-stu-id="9cfd4-130">Status is only one property of service objects.</span></span> <span data-ttu-id="9cfd4-131">Um alle Eigenschaften anzuzeigen, geben Sie ein `Get-Service | Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="9cfd4-131">To see all of the properties, type `Get-Service | Get-Member`.</span></span>

### <span data-ttu-id="9cfd4-132">Beispiel 6: Auflisten der Dienste auf dem Computer, die über abhängige Dienste verfügen</span><span class="sxs-lookup"><span data-stu-id="9cfd4-132">Example 6: List the services on the computer that have dependent services</span></span>

<span data-ttu-id="9cfd4-133">In diesem Beispiel werden Dienste abgerufen, die über abhängige Dienste verfügen.</span><span class="sxs-lookup"><span data-stu-id="9cfd4-133">This example gets services that have dependent services.</span></span>

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

<span data-ttu-id="9cfd4-134">Das `Get-Service` Cmdlet ruft alle Dienste auf dem Computer ab und sendet die Objekte in der Pipeline.</span><span class="sxs-lookup"><span data-stu-id="9cfd4-134">The `Get-Service` cmdlet gets all the services on the computer and sends the objects down the pipeline.</span></span> <span data-ttu-id="9cfd4-135">Mit dem- `Where-Object` Cmdlet werden die Dienste ausgewählt, deren **DependentServices** -Eigenschaft nicht NULL ist.</span><span class="sxs-lookup"><span data-stu-id="9cfd4-135">The `Where-Object` cmdlet selects the services whose **DependentServices** property isn't null.</span></span>

<span data-ttu-id="9cfd4-136">Die Ergebnisse werden über die Pipeline an das `Format-List` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="9cfd4-136">The results are sent down the pipeline to the `Format-List` cmdlet.</span></span> <span data-ttu-id="9cfd4-137">Der **Property** -Parameter zeigt den Namen des Diensts, den Namen der abhängigen Dienste und eine berechnete Eigenschaft an, die die Anzahl der abhängigen Dienste für jeden Dienst anzeigt.</span><span class="sxs-lookup"><span data-stu-id="9cfd4-137">The **Property** parameter displays the name of the service, the name of the dependent services, and a calculated property that displays the number of dependent services for each service.</span></span>

### <span data-ttu-id="9cfd4-138">Beispiel 7: Sortieren von Diensten nach Eigenschafts Wert</span><span class="sxs-lookup"><span data-stu-id="9cfd4-138">Example 7: Sort services by property value</span></span>

<span data-ttu-id="9cfd4-139">Dieses Beispiel zeigt, dass beim Sortieren von Diensten in aufsteigender Reihenfolge nach dem Wert der **Status** -Eigenschaft beendete Dienste vor dem Ausführen von Diensten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="9cfd4-139">This example shows that when you sort services in ascending order by the value of their **Status** property, stopped services appear before running services.</span></span> <span data-ttu-id="9cfd4-140">Der Grund hierfür ist, dass der Wert von " **Status** " eine Enumeration ist, in der "beendet" den Wert "1" aufweist und "Running" den Wert 4 aufweist.</span><span class="sxs-lookup"><span data-stu-id="9cfd4-140">The reason is because the value of **Status** is an enumeration, in which Stopped has a value of 1, and Running has a value of 4.</span></span> <span data-ttu-id="9cfd4-141">Weitere Informationen finden Sie unter [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).</span><span class="sxs-lookup"><span data-stu-id="9cfd4-141">For more information, see [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).</span></span>

<span data-ttu-id="9cfd4-142">Verwenden Sie zum Auflisten der laufenden Dienste zuerst den **Absteig** enden Parameter des `Sort-Object` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="9cfd4-142">To list running services first, use the **Descending** parameter of the `Sort-Object` cmdlet.</span></span>

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

### <span data-ttu-id="9cfd4-143">Beispiel 8: erhalten der abhängigen Dienste eines Diensts</span><span class="sxs-lookup"><span data-stu-id="9cfd4-143">Example 8: Get the dependent services of a service</span></span>

<span data-ttu-id="9cfd4-144">In diesem Beispiel werden die Dienste abgerufen, die für den WinRM-Dienst erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="9cfd4-144">This example gets the services that the WinRM service requires.</span></span> <span data-ttu-id="9cfd4-145">Der Wert der **ServicesDependedOn** -Eigenschaft des dienstangs wird zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9cfd4-145">The value of the service's **ServicesDependedOn** property is returned.</span></span>

```powershell
Get-Service "WinRM" -RequiredServices
```

### <span data-ttu-id="9cfd4-146">Beispiel 9: erhalten eines Dienstanbieter über den Pipeline-Operator</span><span class="sxs-lookup"><span data-stu-id="9cfd4-146">Example 9: Get a service through the pipeline operator</span></span>

<span data-ttu-id="9cfd4-147">In diesem Beispiel wird der WinRM-Dienst auf dem lokalen Computer abgerufen.</span><span class="sxs-lookup"><span data-stu-id="9cfd4-147">This example gets the WinRM service on the local computer.</span></span> <span data-ttu-id="9cfd4-148">Die in Anführungszeichen eingeschlossene Dienstnamen Zeichenfolge wird von der Pipeline an gesendet `Get-Service` .</span><span class="sxs-lookup"><span data-stu-id="9cfd4-148">The service name string, enclosed in quotation marks, is sent down the pipeline to `Get-Service`.</span></span>

```powershell
"WinRM" | Get-Service
```

## <span data-ttu-id="9cfd4-149">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9cfd4-149">PARAMETERS</span></span>

### <span data-ttu-id="9cfd4-150">-DependentServices</span><span class="sxs-lookup"><span data-stu-id="9cfd4-150">-DependentServices</span></span>

<span data-ttu-id="9cfd4-151">Gibt an, dass dieses Cmdlet nur die Dienste abruft, die vom angegebenen Dienst abhängen.</span><span class="sxs-lookup"><span data-stu-id="9cfd4-151">Indicates that this cmdlet gets only the services that depend upon the specified service.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: DS

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9cfd4-152">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="9cfd4-152">-DisplayName</span></span>

<span data-ttu-id="9cfd4-153">Gibt die anzeigen amen der abzurufenden Dienste als Zeichen folgen Array an.</span><span class="sxs-lookup"><span data-stu-id="9cfd4-153">Specifies, as a string array, the display names of services to be retrieved.</span></span> <span data-ttu-id="9cfd4-154">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="9cfd4-154">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="9cfd4-155">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="9cfd4-155">-Exclude</span></span>

<span data-ttu-id="9cfd4-156">Gibt als Zeichen folgen Array einen Dienst oder Dienste an, die von diesem Cmdlet aus dem Vorgang ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="9cfd4-156">Specifies, as a string array, a service or services that this cmdlet excludes from the operation.</span></span>
<span data-ttu-id="9cfd4-157">Der Wert dieses Parameters qualifiziert den **Name** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="9cfd4-157">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="9cfd4-158">Geben Sie ein Namenselement oder-Muster ein, z `s*` . b..</span><span class="sxs-lookup"><span data-stu-id="9cfd4-158">Enter a name element or pattern, such as `s*`.</span></span> <span data-ttu-id="9cfd4-159">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="9cfd4-159">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="9cfd4-160">-Include</span><span class="sxs-lookup"><span data-stu-id="9cfd4-160">-Include</span></span>

<span data-ttu-id="9cfd4-161">Gibt als Zeichen folgen Array einen Dienst oder Dienste an, die dieses Cmdlet in den Vorgang einschließt.</span><span class="sxs-lookup"><span data-stu-id="9cfd4-161">Specifies, as a string array, a service or services that this cmdlet includes in the operation.</span></span> <span data-ttu-id="9cfd4-162">Der Wert dieses Parameters qualifiziert den **Name** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="9cfd4-162">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="9cfd4-163">Geben Sie ein Namenselement oder-Muster ein, z `s*` . b..</span><span class="sxs-lookup"><span data-stu-id="9cfd4-163">Enter a name element or pattern, such as `s*`.</span></span> <span data-ttu-id="9cfd4-164">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="9cfd4-164">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="9cfd4-165">-InputObject</span><span class="sxs-lookup"><span data-stu-id="9cfd4-165">-InputObject</span></span>

<span data-ttu-id="9cfd4-166">Gibt **ServiceController** -Objekte an, die die abzurufenden Dienste darstellen.</span><span class="sxs-lookup"><span data-stu-id="9cfd4-166">Specifies **ServiceController** objects representing the services to be retrieved.</span></span> <span data-ttu-id="9cfd4-167">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="9cfd4-167">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span> <span data-ttu-id="9cfd4-168">Sie können ein Dienst Objekt über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="9cfd4-168">You can pipe a service object to this cmdlet.</span></span>

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

### <span data-ttu-id="9cfd4-169">-Name</span><span class="sxs-lookup"><span data-stu-id="9cfd4-169">-Name</span></span>

<span data-ttu-id="9cfd4-170">Gibt die Dienstnamen der abzurufenden Dienste an.</span><span class="sxs-lookup"><span data-stu-id="9cfd4-170">Specifies the service names of services to be retrieved.</span></span> <span data-ttu-id="9cfd4-171">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="9cfd4-171">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="9cfd4-172">-Requirements dservices</span><span class="sxs-lookup"><span data-stu-id="9cfd4-172">-RequiredServices</span></span>

<span data-ttu-id="9cfd4-173">Gibt an, dass dieses Cmdlet nur die Dienste abruft, die dieser Dienst benötigt.</span><span class="sxs-lookup"><span data-stu-id="9cfd4-173">Indicates that this cmdlet gets only the services that this service requires.</span></span> <span data-ttu-id="9cfd4-174">Dieser Parameter ruft den Wert der **ServicesDependedOn** -Eigenschaft des Dienstanbieter ab.</span><span class="sxs-lookup"><span data-stu-id="9cfd4-174">This parameter gets the value of the **ServicesDependedOn** property of the service.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: SDO, ServicesDependedOn

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="9cfd4-175">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="9cfd4-175">CommonParameters</span></span>

<span data-ttu-id="9cfd4-176">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9cfd4-176">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9cfd4-177">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="9cfd4-177">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9cfd4-178">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="9cfd4-178">INPUTS</span></span>

### <span data-ttu-id="9cfd4-179">System. ServiceProcess. ServiceController, System. String</span><span class="sxs-lookup"><span data-stu-id="9cfd4-179">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="9cfd4-180">Sie können ein Dienst Objekt oder einen Dienstnamen über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="9cfd4-180">You can pipe a service object or a service name to this cmdlet.</span></span>

## <span data-ttu-id="9cfd4-181">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="9cfd4-181">OUTPUTS</span></span>

### <span data-ttu-id="9cfd4-182">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="9cfd4-182">System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="9cfd4-183">Dieses Cmdlet gibt Objekte zurück, die die Dienste auf dem Computer darstellen.</span><span class="sxs-lookup"><span data-stu-id="9cfd4-183">This cmdlet returns objects that represent the services on the computer.</span></span>

## <span data-ttu-id="9cfd4-184">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="9cfd4-184">NOTES</span></span>

<span data-ttu-id="9cfd4-185">Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9cfd4-185">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="9cfd4-186">Ab PowerShell 6,0 werden den **ServiceController** -Objekten die folgenden Eigenschaften hinzugefügt: **username** , **Description** , **delayedaudestart** , **binarypathname** und **startupType** .</span><span class="sxs-lookup"><span data-stu-id="9cfd4-186">Beginning in PowerShell 6.0, the following properties are added to the **ServiceController** objects: **UserName** , **Description** , **DelayedAutoStart** , **BinaryPathName** , and **StartupType** .</span></span>

<span data-ttu-id="9cfd4-187">Sie können auch auf den `Get-Service` integrierten Alias verweisen `gsv` .</span><span class="sxs-lookup"><span data-stu-id="9cfd4-187">You can also refer to `Get-Service` by its built-in alias, `gsv`.</span></span> <span data-ttu-id="9cfd4-188">Weitere Informationen finden Sie unter [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="9cfd4-188">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="9cfd4-189">Dieses Cmdlet kann nur dann Dienste anzeigen, wenn der aktuelle Benutzer über die Berechtigung verfügt, Sie anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="9cfd4-189">This cmdlet can display services only when the current user has permission to see them.</span></span> <span data-ttu-id="9cfd4-190">Wenn dieses Cmdlet keine Dienste anzeigt, verfügen Sie möglicherweise nicht über die Berechtigung, diese anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="9cfd4-190">If this cmdlet does not display services, you might not have permission to see them.</span></span>

<span data-ttu-id="9cfd4-191">Geben Sie ein, um den Dienstnamen und den anzeigen amen der einzelnen Dienste auf dem System zu ermitteln `Get-Service` .</span><span class="sxs-lookup"><span data-stu-id="9cfd4-191">To find the service name and display name of each service on your system, type `Get-Service`.</span></span> <span data-ttu-id="9cfd4-192">Die Dienstnamen werden in der Spalte Name angezeigt, und die anzeigen Amen werden in der Spalte **Display Name** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9cfd4-192">The service names appear in the Name column, and the display names appear in the **DisplayName** column.</span></span>

<span data-ttu-id="9cfd4-193">Wenn Sie in aufsteigender Reihenfolge nach dem Wert der **Status** Eigenschaft sortieren, werden beendete Dienste vor dem Ausführen von Diensten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9cfd4-193">When you sort in ascending order by the **Status** property's value, Stopped services appear before Running services.</span></span> <span data-ttu-id="9cfd4-194">Die **Status** -Eigenschaft des dienstangs ist ein Enumerationswert, und die Statusnamen stellen ganzzahlige Werte dar</span><span class="sxs-lookup"><span data-stu-id="9cfd4-194">The service's **Status** property is an enumerated value and the status names represent integer values.</span></span> <span data-ttu-id="9cfd4-195">Die Sortierreihenfolge basiert auf dem ganzzahligen Wert und nicht auf dem Namen.</span><span class="sxs-lookup"><span data-stu-id="9cfd4-195">The sort order is based on the integer value, not the name.</span></span> <span data-ttu-id="9cfd4-196">Beendet wird vor angezeigt, da die Ausführung von, da beendet ist, den Wert 1 hat und die Ausführung von den Wert 4 aufweist.</span><span class="sxs-lookup"><span data-stu-id="9cfd4-196">Stopped appears before because Running because Stopped has a value of 1, and Running has a value of 4.</span></span> <span data-ttu-id="9cfd4-197">Weitere Informationen finden Sie unter [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).</span><span class="sxs-lookup"><span data-stu-id="9cfd4-197">For more information, see [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).</span></span>

## <span data-ttu-id="9cfd4-198">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="9cfd4-198">RELATED LINKS</span></span>

[<span data-ttu-id="9cfd4-199">New-Service</span><span class="sxs-lookup"><span data-stu-id="9cfd4-199">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="9cfd4-200">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="9cfd4-200">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="9cfd4-201">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="9cfd4-201">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="9cfd4-202">Set-Service</span><span class="sxs-lookup"><span data-stu-id="9cfd4-202">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="9cfd4-203">Start-Service</span><span class="sxs-lookup"><span data-stu-id="9cfd4-203">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="9cfd4-204">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="9cfd4-204">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="9cfd4-205">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="9cfd4-205">Suspend-Service</span></span>](Suspend-Service.md)

[<span data-ttu-id="9cfd4-206">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="9cfd4-206">Remove-Service</span></span>](Remove-Service.md)
