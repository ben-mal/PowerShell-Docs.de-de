---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/30/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-service?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Service
ms.openlocfilehash: c27dac11cdd8ebbf1705ac3bba0c0aa5147d4fa8
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599189"
---
# <span data-ttu-id="bb0cc-102">Get-Service</span><span class="sxs-lookup"><span data-stu-id="bb0cc-102">Get-Service</span></span>

## <span data-ttu-id="bb0cc-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="bb0cc-103">SYNOPSIS</span></span>
<span data-ttu-id="bb0cc-104">Ruft die Dienste auf dem Computer ab.</span><span class="sxs-lookup"><span data-stu-id="bb0cc-104">Gets the services on the computer.</span></span>

## <span data-ttu-id="bb0cc-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="bb0cc-105">SYNTAX</span></span>

### <span data-ttu-id="bb0cc-106">Standard (Standard)</span><span class="sxs-lookup"><span data-stu-id="bb0cc-106">Default (Default)</span></span>

```
Get-Service [[-Name] <String[]>] [-DependentServices] [-RequiredServices] [-Include <String[]>]
 [-Exclude <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="bb0cc-107">DisplayName</span><span class="sxs-lookup"><span data-stu-id="bb0cc-107">DisplayName</span></span>

```
Get-Service [-DependentServices] [-RequiredServices] -DisplayName <String[]> [-Include <String[]>]
 [-Exclude <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="bb0cc-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="bb0cc-108">InputObject</span></span>

```
Get-Service [-DependentServices] [-RequiredServices] [-Include <String[]>] [-Exclude <String[]>]
 [-InputObject <ServiceController[]>] [<CommonParameters>]
```

## <span data-ttu-id="bb0cc-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bb0cc-109">DESCRIPTION</span></span>

<span data-ttu-id="bb0cc-110">`Get-Service`Mit dem-Cmdlet werden Objekte abgerufen, die die Dienste auf einem Computer darstellen, einschließlich der Ausführung und Beendigung der Dienste.</span><span class="sxs-lookup"><span data-stu-id="bb0cc-110">The `Get-Service` cmdlet gets objects that represent the services on a computer, including running and stopped services.</span></span> <span data-ttu-id="bb0cc-111">Wenn `Get-Service` ohne Parameter ausgeführt wird, werden standardmäßig alle Dienste des lokalen Computers zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="bb0cc-111">By default, when `Get-Service` is run without parameters, all the local computer's services are returned.</span></span>

<span data-ttu-id="bb0cc-112">Sie können dieses Cmdlet anweisen, nur bestimmte Dienste zu erhalten, indem Sie den Dienstnamen oder anzeigen amen der Dienste angeben, oder Sie können Dienst Objekte über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="bb0cc-112">You can direct this cmdlet to get only particular services by specifying the service name or the display name of the services, or you can pipe service objects to this cmdlet.</span></span>

## <span data-ttu-id="bb0cc-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="bb0cc-113">EXAMPLES</span></span>

### <span data-ttu-id="bb0cc-114">Beispiel 1: alle Dienste auf dem Computer</span><span class="sxs-lookup"><span data-stu-id="bb0cc-114">Example 1: Get all services on the computer</span></span>

<span data-ttu-id="bb0cc-115">In diesem Beispiel werden alle Dienste auf dem Computer abgerufen.</span><span class="sxs-lookup"><span data-stu-id="bb0cc-115">This example gets all of the services on the computer.</span></span> <span data-ttu-id="bb0cc-116">Dies verhält sich, als ob Sie eingegeben haben `Get-Service *` .</span><span class="sxs-lookup"><span data-stu-id="bb0cc-116">It behaves as though you typed `Get-Service *`.</span></span> <span data-ttu-id="bb0cc-117">In der Standardanzeige werden der Status, der Dienstname und der Anzeigename der einzelnen Dienste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bb0cc-117">The default display shows the status, service name, and display name of each service.</span></span>

```powershell
Get-Service
```

### <span data-ttu-id="bb0cc-118">Beispiel 2: erhalten von Diensten, die mit einer Such Zeichenfolge beginnen</span><span class="sxs-lookup"><span data-stu-id="bb0cc-118">Example 2: Get services that begin with a search string</span></span>

<span data-ttu-id="bb0cc-119">In diesem Beispiel werden Dienste mit Dienstnamen abgerufen, die mit WMI (Windows-Verwaltungsinstrumentation) beginnen.</span><span class="sxs-lookup"><span data-stu-id="bb0cc-119">This example retrieves services with service names that begin with WMI (Windows Management Instrumentation).</span></span>

```powershell
Get-Service "wmi*"
```

### <span data-ttu-id="bb0cc-120">Beispiel 3: Anzeigen von Diensten, die eine Such Zeichenfolge enthalten</span><span class="sxs-lookup"><span data-stu-id="bb0cc-120">Example 3: Display services that include a search string</span></span>

<span data-ttu-id="bb0cc-121">In diesem Beispiel werden Dienste mit einem anzeigen Amen angezeigt, der das Wort "Network" enthält.</span><span class="sxs-lookup"><span data-stu-id="bb0cc-121">This example displays services with a display name that includes the word network.</span></span> <span data-ttu-id="bb0cc-122">Durch das Durchsuchen des anzeigen Amens werden netzwerkbezogene Dienste auch dann gefunden, wenn der Dienst Name NET nicht enthält, wie z. b. xmlprov, den Netzwerk Bereitstellungs Dienst.</span><span class="sxs-lookup"><span data-stu-id="bb0cc-122">Searching the display name finds network-related services even when the service name doesn't include Net, such as xmlprov, the Network Provisioning Service.</span></span>

```powershell
Get-Service -Displayname "*network*"
```

### <span data-ttu-id="bb0cc-123">Beispiel 4: erhalten von Diensten, die mit einer Such Zeichenfolge und einem Ausschluss beginnen</span><span class="sxs-lookup"><span data-stu-id="bb0cc-123">Example 4: Get services that begin with a search string and an exclusion</span></span>

<span data-ttu-id="bb0cc-124">In diesem Beispiel werden nur die Dienste mit Dienstnamen abgerufen, die mit " **Win**" beginnen, mit Ausnahme des WinRM-Diensts.</span><span class="sxs-lookup"><span data-stu-id="bb0cc-124">This example only gets the services with service names that begin with **win**, except for the WinRM service.</span></span>

```powershell
Get-Service -Name "win*" -Exclude "WinRM"
```

### <span data-ttu-id="bb0cc-125">Beispiel 5: Anzeigen von Diensten, die zurzeit aktiv sind</span><span class="sxs-lookup"><span data-stu-id="bb0cc-125">Example 5: Display services that are currently active</span></span>

<span data-ttu-id="bb0cc-126">In diesem Beispiel werden nur die Dienste mit dem Status "wird ausgeführt" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bb0cc-126">This example displays only the services with a status of Running.</span></span>

```powershell
Get-Service | Where-Object {$_.Status -eq "Running"}
```

<span data-ttu-id="bb0cc-127">`Get-Service` Ruft alle Dienste auf dem Computer ab und sendet die Objekte in der Pipeline.</span><span class="sxs-lookup"><span data-stu-id="bb0cc-127">`Get-Service` gets all the services on the computer and sends the objects down the pipeline.</span></span> <span data-ttu-id="bb0cc-128">Mit dem- `Where-Object` Cmdlet werden nur die Dienste ausgewählt, deren **Status** -Eigenschaft ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="bb0cc-128">The `Where-Object` cmdlet, selects only the services with a **Status** property that equals Running.</span></span>

<span data-ttu-id="bb0cc-129">%%amp;quot;Status%%amp;quot; ist nur eine der Eigenschaften von Dienstobjekten.</span><span class="sxs-lookup"><span data-stu-id="bb0cc-129">Status is only one property of service objects.</span></span> <span data-ttu-id="bb0cc-130">Um alle Eigenschaften anzuzeigen, geben Sie ein `Get-Service | Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="bb0cc-130">To see all of the properties, type `Get-Service | Get-Member`.</span></span>

### <span data-ttu-id="bb0cc-131">Beispiel 6: Auflisten der Dienste auf dem Computer, die über abhängige Dienste verfügen</span><span class="sxs-lookup"><span data-stu-id="bb0cc-131">Example 6: List the services on the computer that have dependent services</span></span>

<span data-ttu-id="bb0cc-132">In diesem Beispiel werden Dienste abgerufen, die über abhängige Dienste verfügen.</span><span class="sxs-lookup"><span data-stu-id="bb0cc-132">This example gets services that have dependent services.</span></span>

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

<span data-ttu-id="bb0cc-133">Das `Get-Service` Cmdlet ruft alle Dienste auf dem Computer ab und sendet die Objekte in der Pipeline.</span><span class="sxs-lookup"><span data-stu-id="bb0cc-133">The `Get-Service` cmdlet gets all the services on the computer and sends the objects down the pipeline.</span></span> <span data-ttu-id="bb0cc-134">Mit dem- `Where-Object` Cmdlet werden die Dienste ausgewählt, deren **DependentServices** -Eigenschaft nicht NULL ist.</span><span class="sxs-lookup"><span data-stu-id="bb0cc-134">The `Where-Object` cmdlet selects the services whose **DependentServices** property isn't null.</span></span>

<span data-ttu-id="bb0cc-135">Die Ergebnisse werden über die Pipeline an das `Format-List` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="bb0cc-135">The results are sent down the pipeline to the `Format-List` cmdlet.</span></span> <span data-ttu-id="bb0cc-136">Der **Property** -Parameter zeigt den Namen des Diensts, den Namen der abhängigen Dienste und eine berechnete Eigenschaft an, die die Anzahl der abhängigen Dienste für jeden Dienst anzeigt.</span><span class="sxs-lookup"><span data-stu-id="bb0cc-136">The **Property** parameter displays the name of the service, the name of the dependent services, and a calculated property that displays the number of dependent services for each service.</span></span>

### <span data-ttu-id="bb0cc-137">Beispiel 7: Sortieren von Diensten nach Eigenschafts Wert</span><span class="sxs-lookup"><span data-stu-id="bb0cc-137">Example 7: Sort services by property value</span></span>

<span data-ttu-id="bb0cc-138">Dieses Beispiel zeigt, dass beim Sortieren von Diensten in aufsteigender Reihenfolge nach dem Wert der **Status** -Eigenschaft beendete Dienste vor dem Ausführen von Diensten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="bb0cc-138">This example shows that when you sort services in ascending order by the value of their **Status** property, stopped services appear before running services.</span></span> <span data-ttu-id="bb0cc-139">Der Grund hierfür ist, dass der Wert von " **Status** " eine Enumeration ist, in der "beendet" den Wert "1" aufweist und "Running" den Wert 4 aufweist.</span><span class="sxs-lookup"><span data-stu-id="bb0cc-139">The reason is because the value of **Status** is an enumeration, in which Stopped has a value of 1, and Running has a value of 4.</span></span> <span data-ttu-id="bb0cc-140">Weitere Informationen finden Sie unter [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).</span><span class="sxs-lookup"><span data-stu-id="bb0cc-140">For more information, see [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).</span></span>

<span data-ttu-id="bb0cc-141">Verwenden Sie zum Auflisten der laufenden Dienste zuerst den **Absteig** enden Parameter des `Sort-Object` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="bb0cc-141">To list running services first, use the **Descending** parameter of the `Sort-Object` cmdlet.</span></span>

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

### <span data-ttu-id="bb0cc-142">Beispiel 8: erhalten der abhängigen Dienste eines Diensts</span><span class="sxs-lookup"><span data-stu-id="bb0cc-142">Example 8: Get the dependent services of a service</span></span>

<span data-ttu-id="bb0cc-143">In diesem Beispiel werden die Dienste abgerufen, die für den WinRM-Dienst erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="bb0cc-143">This example gets the services that the WinRM service requires.</span></span> <span data-ttu-id="bb0cc-144">Der Wert der **ServicesDependedOn** -Eigenschaft des dienstangs wird zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="bb0cc-144">The value of the service's **ServicesDependedOn** property is returned.</span></span>

```powershell
Get-Service "WinRM" -RequiredServices
```

### <span data-ttu-id="bb0cc-145">Beispiel 9: erhalten eines Dienstanbieter über den Pipeline-Operator</span><span class="sxs-lookup"><span data-stu-id="bb0cc-145">Example 9: Get a service through the pipeline operator</span></span>

<span data-ttu-id="bb0cc-146">In diesem Beispiel wird der WinRM-Dienst auf dem lokalen Computer abgerufen.</span><span class="sxs-lookup"><span data-stu-id="bb0cc-146">This example gets the WinRM service on the local computer.</span></span> <span data-ttu-id="bb0cc-147">Die in Anführungszeichen eingeschlossene Dienstnamen Zeichenfolge wird von der Pipeline an gesendet `Get-Service` .</span><span class="sxs-lookup"><span data-stu-id="bb0cc-147">The service name string, enclosed in quotation marks, is sent down the pipeline to `Get-Service`.</span></span>

```powershell
"WinRM" | Get-Service
```

## <span data-ttu-id="bb0cc-148">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bb0cc-148">PARAMETERS</span></span>

### <span data-ttu-id="bb0cc-149">-DependentServices</span><span class="sxs-lookup"><span data-stu-id="bb0cc-149">-DependentServices</span></span>

<span data-ttu-id="bb0cc-150">Gibt an, dass dieses Cmdlet nur die Dienste abruft, die vom angegebenen Dienst abhängen.</span><span class="sxs-lookup"><span data-stu-id="bb0cc-150">Indicates that this cmdlet gets only the services that depend upon the specified service.</span></span>

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

### <span data-ttu-id="bb0cc-151">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="bb0cc-151">-DisplayName</span></span>

<span data-ttu-id="bb0cc-152">Gibt die anzeigen amen der abzurufenden Dienste als Zeichen folgen Array an.</span><span class="sxs-lookup"><span data-stu-id="bb0cc-152">Specifies, as a string array, the display names of services to be retrieved.</span></span> <span data-ttu-id="bb0cc-153">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="bb0cc-153">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="bb0cc-154">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="bb0cc-154">-Exclude</span></span>

<span data-ttu-id="bb0cc-155">Gibt als Zeichen folgen Array einen Dienst oder Dienste an, die von diesem Cmdlet aus dem Vorgang ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="bb0cc-155">Specifies, as a string array, a service or services that this cmdlet excludes from the operation.</span></span>
<span data-ttu-id="bb0cc-156">Der Wert dieses Parameters qualifiziert den **Name** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="bb0cc-156">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="bb0cc-157">Geben Sie ein Namenselement oder-Muster ein, z `s*` . b..</span><span class="sxs-lookup"><span data-stu-id="bb0cc-157">Enter a name element or pattern, such as `s*`.</span></span> <span data-ttu-id="bb0cc-158">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="bb0cc-158">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="bb0cc-159">-Include</span><span class="sxs-lookup"><span data-stu-id="bb0cc-159">-Include</span></span>

<span data-ttu-id="bb0cc-160">Gibt als Zeichen folgen Array einen Dienst oder Dienste an, die dieses Cmdlet in den Vorgang einschließt.</span><span class="sxs-lookup"><span data-stu-id="bb0cc-160">Specifies, as a string array, a service or services that this cmdlet includes in the operation.</span></span> <span data-ttu-id="bb0cc-161">Der Wert dieses Parameters qualifiziert den **Name** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="bb0cc-161">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="bb0cc-162">Geben Sie ein Namenselement oder-Muster ein, z `s*` . b..</span><span class="sxs-lookup"><span data-stu-id="bb0cc-162">Enter a name element or pattern, such as `s*`.</span></span> <span data-ttu-id="bb0cc-163">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="bb0cc-163">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="bb0cc-164">-InputObject</span><span class="sxs-lookup"><span data-stu-id="bb0cc-164">-InputObject</span></span>

<span data-ttu-id="bb0cc-165">Gibt **ServiceController** -Objekte an, die die abzurufenden Dienste darstellen.</span><span class="sxs-lookup"><span data-stu-id="bb0cc-165">Specifies **ServiceController** objects representing the services to be retrieved.</span></span> <span data-ttu-id="bb0cc-166">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="bb0cc-166">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span> <span data-ttu-id="bb0cc-167">Sie können ein Dienst Objekt über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="bb0cc-167">You can pipe a service object to this cmdlet.</span></span>

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

### <span data-ttu-id="bb0cc-168">-Name</span><span class="sxs-lookup"><span data-stu-id="bb0cc-168">-Name</span></span>

<span data-ttu-id="bb0cc-169">Gibt die Dienstnamen der abzurufenden Dienste an.</span><span class="sxs-lookup"><span data-stu-id="bb0cc-169">Specifies the service names of services to be retrieved.</span></span> <span data-ttu-id="bb0cc-170">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="bb0cc-170">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="bb0cc-171">-Requirements dservices</span><span class="sxs-lookup"><span data-stu-id="bb0cc-171">-RequiredServices</span></span>

<span data-ttu-id="bb0cc-172">Gibt an, dass dieses Cmdlet nur die Dienste abruft, die dieser Dienst benötigt.</span><span class="sxs-lookup"><span data-stu-id="bb0cc-172">Indicates that this cmdlet gets only the services that this service requires.</span></span> <span data-ttu-id="bb0cc-173">Dieser Parameter ruft den Wert der **ServicesDependedOn** -Eigenschaft des Dienstanbieter ab.</span><span class="sxs-lookup"><span data-stu-id="bb0cc-173">This parameter gets the value of the **ServicesDependedOn** property of the service.</span></span>

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

### <span data-ttu-id="bb0cc-174">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="bb0cc-174">CommonParameters</span></span>

<span data-ttu-id="bb0cc-175">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="bb0cc-175">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="bb0cc-176">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="bb0cc-176">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="bb0cc-177">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="bb0cc-177">INPUTS</span></span>

### <span data-ttu-id="bb0cc-178">System. ServiceProcess. ServiceController, System. String</span><span class="sxs-lookup"><span data-stu-id="bb0cc-178">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="bb0cc-179">Sie können ein Dienst Objekt oder einen Dienstnamen über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="bb0cc-179">You can pipe a service object or a service name to this cmdlet.</span></span>

## <span data-ttu-id="bb0cc-180">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="bb0cc-180">OUTPUTS</span></span>

### <span data-ttu-id="bb0cc-181">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="bb0cc-181">System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="bb0cc-182">Dieses Cmdlet gibt Objekte zurück, die die Dienste auf dem Computer darstellen.</span><span class="sxs-lookup"><span data-stu-id="bb0cc-182">This cmdlet returns objects that represent the services on the computer.</span></span>

## <span data-ttu-id="bb0cc-183">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="bb0cc-183">NOTES</span></span>

<span data-ttu-id="bb0cc-184">Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="bb0cc-184">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="bb0cc-185">Ab PowerShell 6,0 werden den **ServiceController** -Objekten die folgenden Eigenschaften hinzugefügt: **username**, **Description**, **delayedaudestart**, **binarypathname** und **startupType** .</span><span class="sxs-lookup"><span data-stu-id="bb0cc-185">Beginning in PowerShell 6.0, the following properties are added to the **ServiceController** objects: **UserName**, **Description**, **DelayedAutoStart**, **BinaryPathName**, and **StartupType** .</span></span>

<span data-ttu-id="bb0cc-186">Sie können auch auf den `Get-Service` integrierten Alias verweisen `gsv` .</span><span class="sxs-lookup"><span data-stu-id="bb0cc-186">You can also refer to `Get-Service` by its built-in alias, `gsv`.</span></span> <span data-ttu-id="bb0cc-187">Weitere Informationen finden Sie unter [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="bb0cc-187">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="bb0cc-188">Dieses Cmdlet kann nur dann Dienste anzeigen, wenn der aktuelle Benutzer über die Berechtigung verfügt, Sie anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="bb0cc-188">This cmdlet can display services only when the current user has permission to see them.</span></span> <span data-ttu-id="bb0cc-189">Wenn dieses Cmdlet keine Dienste anzeigt, verfügen Sie möglicherweise nicht über die Berechtigung, diese anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="bb0cc-189">If this cmdlet does not display services, you might not have permission to see them.</span></span>

<span data-ttu-id="bb0cc-190">Geben Sie ein, um den Dienstnamen und den anzeigen amen der einzelnen Dienste auf dem System zu ermitteln `Get-Service` .</span><span class="sxs-lookup"><span data-stu-id="bb0cc-190">To find the service name and display name of each service on your system, type `Get-Service`.</span></span> <span data-ttu-id="bb0cc-191">Die Dienstnamen werden in der Spalte Name angezeigt, und die anzeigen Amen werden in der Spalte **Display Name** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bb0cc-191">The service names appear in the Name column, and the display names appear in the **DisplayName** column.</span></span>

<span data-ttu-id="bb0cc-192">Wenn Sie in aufsteigender Reihenfolge nach dem Wert der **Status** Eigenschaft sortieren, werden beendete Dienste vor dem Ausführen von Diensten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bb0cc-192">When you sort in ascending order by the **Status** property's value, Stopped services appear before Running services.</span></span> <span data-ttu-id="bb0cc-193">Die **Status** -Eigenschaft des dienstangs ist ein Enumerationswert, und die Statusnamen stellen ganzzahlige Werte dar</span><span class="sxs-lookup"><span data-stu-id="bb0cc-193">The service's **Status** property is an enumerated value and the status names represent integer values.</span></span> <span data-ttu-id="bb0cc-194">Die Sortierreihenfolge basiert auf dem ganzzahligen Wert und nicht auf dem Namen.</span><span class="sxs-lookup"><span data-stu-id="bb0cc-194">The sort order is based on the integer value, not the name.</span></span> <span data-ttu-id="bb0cc-195">Beendet wird vor angezeigt, da die Ausführung von, da beendet ist, den Wert 1 hat und die Ausführung von den Wert 4 aufweist.</span><span class="sxs-lookup"><span data-stu-id="bb0cc-195">Stopped appears before because Running because Stopped has a value of 1, and Running has a value of 4.</span></span> <span data-ttu-id="bb0cc-196">Weitere Informationen finden Sie unter [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).</span><span class="sxs-lookup"><span data-stu-id="bb0cc-196">For more information, see [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).</span></span>

## <span data-ttu-id="bb0cc-197">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="bb0cc-197">RELATED LINKS</span></span>

[<span data-ttu-id="bb0cc-198">New-Service</span><span class="sxs-lookup"><span data-stu-id="bb0cc-198">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="bb0cc-199">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="bb0cc-199">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="bb0cc-200">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="bb0cc-200">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="bb0cc-201">Set-Service</span><span class="sxs-lookup"><span data-stu-id="bb0cc-201">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="bb0cc-202">Start-Service</span><span class="sxs-lookup"><span data-stu-id="bb0cc-202">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="bb0cc-203">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="bb0cc-203">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="bb0cc-204">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="bb0cc-204">Suspend-Service</span></span>](Suspend-Service.md)

[<span data-ttu-id="bb0cc-205">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="bb0cc-205">Remove-Service</span></span>](Remove-Service.md)
