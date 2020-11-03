---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/30/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-service?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Service
ms.openlocfilehash: ce91313d1b581e3d666c131caaa1cf7ecad0c04f
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210551"
---
# <span data-ttu-id="bee62-103">Get-Service</span><span class="sxs-lookup"><span data-stu-id="bee62-103">Get-Service</span></span>

## <span data-ttu-id="bee62-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="bee62-104">SYNOPSIS</span></span>
<span data-ttu-id="bee62-105">Ruft die Dienste auf dem Computer ab.</span><span class="sxs-lookup"><span data-stu-id="bee62-105">Gets the services on the computer.</span></span>

## <span data-ttu-id="bee62-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="bee62-106">SYNTAX</span></span>

### <span data-ttu-id="bee62-107">Standard (Standard)</span><span class="sxs-lookup"><span data-stu-id="bee62-107">Default (Default)</span></span>

```
Get-Service [[-Name] <String[]>] [-DependentServices] [-RequiredServices] [-Include <String[]>]
 [-Exclude <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="bee62-108">DisplayName</span><span class="sxs-lookup"><span data-stu-id="bee62-108">DisplayName</span></span>

```
Get-Service [-DependentServices] [-RequiredServices] -DisplayName <String[]> [-Include <String[]>]
 [-Exclude <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="bee62-109">InputObject</span><span class="sxs-lookup"><span data-stu-id="bee62-109">InputObject</span></span>

```
Get-Service [-DependentServices] [-RequiredServices] [-Include <String[]>] [-Exclude <String[]>]
 [-InputObject <ServiceController[]>] [<CommonParameters>]
```

## <span data-ttu-id="bee62-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bee62-110">DESCRIPTION</span></span>

<span data-ttu-id="bee62-111">`Get-Service`Mit dem-Cmdlet werden Objekte abgerufen, die die Dienste auf einem Computer darstellen, einschließlich der Ausführung und Beendigung der Dienste.</span><span class="sxs-lookup"><span data-stu-id="bee62-111">The `Get-Service` cmdlet gets objects that represent the services on a computer, including running and stopped services.</span></span> <span data-ttu-id="bee62-112">Wenn `Get-Service` ohne Parameter ausgeführt wird, werden standardmäßig alle Dienste des lokalen Computers zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="bee62-112">By default, when `Get-Service` is run without parameters, all the local computer's services are returned.</span></span>

<span data-ttu-id="bee62-113">Sie können dieses Cmdlet anweisen, nur bestimmte Dienste zu erhalten, indem Sie den Dienstnamen oder anzeigen amen der Dienste angeben, oder Sie können Dienst Objekte über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="bee62-113">You can direct this cmdlet to get only particular services by specifying the service name or the display name of the services, or you can pipe service objects to this cmdlet.</span></span>

## <span data-ttu-id="bee62-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="bee62-114">EXAMPLES</span></span>

### <span data-ttu-id="bee62-115">Beispiel 1: alle Dienste auf dem Computer</span><span class="sxs-lookup"><span data-stu-id="bee62-115">Example 1: Get all services on the computer</span></span>

<span data-ttu-id="bee62-116">In diesem Beispiel werden alle Dienste auf dem Computer abgerufen.</span><span class="sxs-lookup"><span data-stu-id="bee62-116">This example gets all of the services on the computer.</span></span> <span data-ttu-id="bee62-117">Dies verhält sich, als ob Sie eingegeben haben `Get-Service *` .</span><span class="sxs-lookup"><span data-stu-id="bee62-117">It behaves as though you typed `Get-Service *`.</span></span> <span data-ttu-id="bee62-118">In der Standardanzeige werden der Status, der Dienstname und der Anzeigename der einzelnen Dienste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bee62-118">The default display shows the status, service name, and display name of each service.</span></span>

```powershell
Get-Service
```

### <span data-ttu-id="bee62-119">Beispiel 2: erhalten von Diensten, die mit einer Such Zeichenfolge beginnen</span><span class="sxs-lookup"><span data-stu-id="bee62-119">Example 2: Get services that begin with a search string</span></span>

<span data-ttu-id="bee62-120">In diesem Beispiel werden Dienste mit Dienstnamen abgerufen, die mit WMI (Windows-Verwaltungsinstrumentation) beginnen.</span><span class="sxs-lookup"><span data-stu-id="bee62-120">This example retrieves services with service names that begin with WMI (Windows Management Instrumentation).</span></span>

```powershell
Get-Service "wmi*"
```

### <span data-ttu-id="bee62-121">Beispiel 3: Anzeigen von Diensten, die eine Such Zeichenfolge enthalten</span><span class="sxs-lookup"><span data-stu-id="bee62-121">Example 3: Display services that include a search string</span></span>

<span data-ttu-id="bee62-122">In diesem Beispiel werden Dienste mit einem anzeigen Amen angezeigt, der das Wort "Network" enthält.</span><span class="sxs-lookup"><span data-stu-id="bee62-122">This example displays services with a display name that includes the word network.</span></span> <span data-ttu-id="bee62-123">Durch das Durchsuchen des anzeigen Amens werden netzwerkbezogene Dienste auch dann gefunden, wenn der Dienst Name NET nicht enthält, wie z. b. xmlprov, den Netzwerk Bereitstellungs Dienst.</span><span class="sxs-lookup"><span data-stu-id="bee62-123">Searching the display name finds network-related services even when the service name doesn't include Net, such as xmlprov, the Network Provisioning Service.</span></span>

```powershell
Get-Service -Displayname "*network*"
```

### <span data-ttu-id="bee62-124">Beispiel 4: erhalten von Diensten, die mit einer Such Zeichenfolge und einem Ausschluss beginnen</span><span class="sxs-lookup"><span data-stu-id="bee62-124">Example 4: Get services that begin with a search string and an exclusion</span></span>

<span data-ttu-id="bee62-125">In diesem Beispiel werden nur die Dienste mit Dienstnamen abgerufen, die mit " **Win** " beginnen, mit Ausnahme des WinRM-Diensts.</span><span class="sxs-lookup"><span data-stu-id="bee62-125">This example only gets the services with service names that begin with **win** , except for the WinRM service.</span></span>

```powershell
Get-Service -Name "win*" -Exclude "WinRM"
```

### <span data-ttu-id="bee62-126">Beispiel 5: Anzeigen von Diensten, die zurzeit aktiv sind</span><span class="sxs-lookup"><span data-stu-id="bee62-126">Example 5: Display services that are currently active</span></span>

<span data-ttu-id="bee62-127">In diesem Beispiel werden nur die Dienste mit dem Status "wird ausgeführt" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bee62-127">This example displays only the services with a status of Running.</span></span>

```powershell
Get-Service | Where-Object {$_.Status -eq "Running"}
```

<span data-ttu-id="bee62-128">`Get-Service` Ruft alle Dienste auf dem Computer ab und sendet die Objekte in der Pipeline.</span><span class="sxs-lookup"><span data-stu-id="bee62-128">`Get-Service` gets all the services on the computer and sends the objects down the pipeline.</span></span> <span data-ttu-id="bee62-129">Mit dem- `Where-Object` Cmdlet werden nur die Dienste ausgewählt, deren **Status** -Eigenschaft ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="bee62-129">The `Where-Object` cmdlet, selects only the services with a **Status** property that equals Running.</span></span>

<span data-ttu-id="bee62-130">%%amp;quot;Status%%amp;quot; ist nur eine der Eigenschaften von Dienstobjekten.</span><span class="sxs-lookup"><span data-stu-id="bee62-130">Status is only one property of service objects.</span></span> <span data-ttu-id="bee62-131">Um alle Eigenschaften anzuzeigen, geben Sie ein `Get-Service | Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="bee62-131">To see all of the properties, type `Get-Service | Get-Member`.</span></span>

### <span data-ttu-id="bee62-132">Beispiel 6: Auflisten der Dienste auf dem Computer, die über abhängige Dienste verfügen</span><span class="sxs-lookup"><span data-stu-id="bee62-132">Example 6: List the services on the computer that have dependent services</span></span>

<span data-ttu-id="bee62-133">In diesem Beispiel werden Dienste abgerufen, die über abhängige Dienste verfügen.</span><span class="sxs-lookup"><span data-stu-id="bee62-133">This example gets services that have dependent services.</span></span>

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

<span data-ttu-id="bee62-134">Das `Get-Service` Cmdlet ruft alle Dienste auf dem Computer ab und sendet die Objekte in der Pipeline.</span><span class="sxs-lookup"><span data-stu-id="bee62-134">The `Get-Service` cmdlet gets all the services on the computer and sends the objects down the pipeline.</span></span> <span data-ttu-id="bee62-135">Mit dem- `Where-Object` Cmdlet werden die Dienste ausgewählt, deren **DependentServices** -Eigenschaft nicht NULL ist.</span><span class="sxs-lookup"><span data-stu-id="bee62-135">The `Where-Object` cmdlet selects the services whose **DependentServices** property isn't null.</span></span>

<span data-ttu-id="bee62-136">Die Ergebnisse werden über die Pipeline an das `Format-List` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="bee62-136">The results are sent down the pipeline to the `Format-List` cmdlet.</span></span> <span data-ttu-id="bee62-137">Der **Property** -Parameter zeigt den Namen des Diensts, den Namen der abhängigen Dienste und eine berechnete Eigenschaft an, die die Anzahl der abhängigen Dienste für jeden Dienst anzeigt.</span><span class="sxs-lookup"><span data-stu-id="bee62-137">The **Property** parameter displays the name of the service, the name of the dependent services, and a calculated property that displays the number of dependent services for each service.</span></span>

### <span data-ttu-id="bee62-138">Beispiel 7: Sortieren von Diensten nach Eigenschafts Wert</span><span class="sxs-lookup"><span data-stu-id="bee62-138">Example 7: Sort services by property value</span></span>

<span data-ttu-id="bee62-139">Dieses Beispiel zeigt, dass beim Sortieren von Diensten in aufsteigender Reihenfolge nach dem Wert der **Status** -Eigenschaft beendete Dienste vor dem Ausführen von Diensten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="bee62-139">This example shows that when you sort services in ascending order by the value of their **Status** property, stopped services appear before running services.</span></span> <span data-ttu-id="bee62-140">Der Grund hierfür ist, dass der Wert von " **Status** " eine Enumeration ist, in der "beendet" den Wert "1" aufweist und "Running" den Wert 4 aufweist.</span><span class="sxs-lookup"><span data-stu-id="bee62-140">The reason is because the value of **Status** is an enumeration, in which Stopped has a value of 1, and Running has a value of 4.</span></span> <span data-ttu-id="bee62-141">Weitere Informationen finden Sie unter [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).</span><span class="sxs-lookup"><span data-stu-id="bee62-141">For more information, see [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).</span></span>

<span data-ttu-id="bee62-142">Verwenden Sie zum Auflisten der laufenden Dienste zuerst den **Absteig** enden Parameter des `Sort-Object` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="bee62-142">To list running services first, use the **Descending** parameter of the `Sort-Object` cmdlet.</span></span>

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

### <span data-ttu-id="bee62-143">Beispiel 8: erhalten der abhängigen Dienste eines Diensts</span><span class="sxs-lookup"><span data-stu-id="bee62-143">Example 8: Get the dependent services of a service</span></span>

<span data-ttu-id="bee62-144">In diesem Beispiel werden die Dienste abgerufen, die für den WinRM-Dienst erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="bee62-144">This example gets the services that the WinRM service requires.</span></span> <span data-ttu-id="bee62-145">Der Wert der **ServicesDependedOn** -Eigenschaft des dienstangs wird zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="bee62-145">The value of the service's **ServicesDependedOn** property is returned.</span></span>

```powershell
Get-Service "WinRM" -RequiredServices
```

### <span data-ttu-id="bee62-146">Beispiel 9: erhalten eines Dienstanbieter über den Pipeline-Operator</span><span class="sxs-lookup"><span data-stu-id="bee62-146">Example 9: Get a service through the pipeline operator</span></span>

<span data-ttu-id="bee62-147">In diesem Beispiel wird der WinRM-Dienst auf dem lokalen Computer abgerufen.</span><span class="sxs-lookup"><span data-stu-id="bee62-147">This example gets the WinRM service on the local computer.</span></span> <span data-ttu-id="bee62-148">Die in Anführungszeichen eingeschlossene Dienstnamen Zeichenfolge wird von der Pipeline an gesendet `Get-Service` .</span><span class="sxs-lookup"><span data-stu-id="bee62-148">The service name string, enclosed in quotation marks, is sent down the pipeline to `Get-Service`.</span></span>

```powershell
"WinRM" | Get-Service
```

## <span data-ttu-id="bee62-149">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bee62-149">PARAMETERS</span></span>

### <span data-ttu-id="bee62-150">-DependentServices</span><span class="sxs-lookup"><span data-stu-id="bee62-150">-DependentServices</span></span>

<span data-ttu-id="bee62-151">Gibt an, dass dieses Cmdlet nur die Dienste abruft, die vom angegebenen Dienst abhängen.</span><span class="sxs-lookup"><span data-stu-id="bee62-151">Indicates that this cmdlet gets only the services that depend upon the specified service.</span></span>

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

### <span data-ttu-id="bee62-152">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="bee62-152">-DisplayName</span></span>

<span data-ttu-id="bee62-153">Gibt die anzeigen amen der abzurufenden Dienste als Zeichen folgen Array an.</span><span class="sxs-lookup"><span data-stu-id="bee62-153">Specifies, as a string array, the display names of services to be retrieved.</span></span> <span data-ttu-id="bee62-154">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="bee62-154">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="bee62-155">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="bee62-155">-Exclude</span></span>

<span data-ttu-id="bee62-156">Gibt als Zeichen folgen Array einen Dienst oder Dienste an, die von diesem Cmdlet aus dem Vorgang ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="bee62-156">Specifies, as a string array, a service or services that this cmdlet excludes from the operation.</span></span>
<span data-ttu-id="bee62-157">Der Wert dieses Parameters qualifiziert den **Name** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="bee62-157">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="bee62-158">Geben Sie ein Namenselement oder-Muster ein, z `s*` . b..</span><span class="sxs-lookup"><span data-stu-id="bee62-158">Enter a name element or pattern, such as `s*`.</span></span> <span data-ttu-id="bee62-159">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="bee62-159">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="bee62-160">-Include</span><span class="sxs-lookup"><span data-stu-id="bee62-160">-Include</span></span>

<span data-ttu-id="bee62-161">Gibt als Zeichen folgen Array einen Dienst oder Dienste an, die dieses Cmdlet in den Vorgang einschließt.</span><span class="sxs-lookup"><span data-stu-id="bee62-161">Specifies, as a string array, a service or services that this cmdlet includes in the operation.</span></span> <span data-ttu-id="bee62-162">Der Wert dieses Parameters qualifiziert den **Name** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="bee62-162">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="bee62-163">Geben Sie ein Namenselement oder-Muster ein, z `s*` . b..</span><span class="sxs-lookup"><span data-stu-id="bee62-163">Enter a name element or pattern, such as `s*`.</span></span> <span data-ttu-id="bee62-164">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="bee62-164">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="bee62-165">-InputObject</span><span class="sxs-lookup"><span data-stu-id="bee62-165">-InputObject</span></span>

<span data-ttu-id="bee62-166">Gibt **ServiceController** -Objekte an, die die abzurufenden Dienste darstellen.</span><span class="sxs-lookup"><span data-stu-id="bee62-166">Specifies **ServiceController** objects representing the services to be retrieved.</span></span> <span data-ttu-id="bee62-167">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="bee62-167">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span> <span data-ttu-id="bee62-168">Sie können ein Dienst Objekt über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="bee62-168">You can pipe a service object to this cmdlet.</span></span>

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

### <span data-ttu-id="bee62-169">-Name</span><span class="sxs-lookup"><span data-stu-id="bee62-169">-Name</span></span>

<span data-ttu-id="bee62-170">Gibt die Dienstnamen der abzurufenden Dienste an.</span><span class="sxs-lookup"><span data-stu-id="bee62-170">Specifies the service names of services to be retrieved.</span></span> <span data-ttu-id="bee62-171">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="bee62-171">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="bee62-172">-Requirements dservices</span><span class="sxs-lookup"><span data-stu-id="bee62-172">-RequiredServices</span></span>

<span data-ttu-id="bee62-173">Gibt an, dass dieses Cmdlet nur die Dienste abruft, die dieser Dienst benötigt.</span><span class="sxs-lookup"><span data-stu-id="bee62-173">Indicates that this cmdlet gets only the services that this service requires.</span></span> <span data-ttu-id="bee62-174">Dieser Parameter ruft den Wert der **ServicesDependedOn** -Eigenschaft des Dienstanbieter ab.</span><span class="sxs-lookup"><span data-stu-id="bee62-174">This parameter gets the value of the **ServicesDependedOn** property of the service.</span></span>

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

### <span data-ttu-id="bee62-175">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="bee62-175">CommonParameters</span></span>

<span data-ttu-id="bee62-176">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="bee62-176">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="bee62-177">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="bee62-177">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="bee62-178">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="bee62-178">INPUTS</span></span>

### <span data-ttu-id="bee62-179">System. ServiceProcess. ServiceController, System. String</span><span class="sxs-lookup"><span data-stu-id="bee62-179">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="bee62-180">Sie können ein Dienst Objekt oder einen Dienstnamen über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="bee62-180">You can pipe a service object or a service name to this cmdlet.</span></span>

## <span data-ttu-id="bee62-181">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="bee62-181">OUTPUTS</span></span>

### <span data-ttu-id="bee62-182">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="bee62-182">System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="bee62-183">Dieses Cmdlet gibt Objekte zurück, die die Dienste auf dem Computer darstellen.</span><span class="sxs-lookup"><span data-stu-id="bee62-183">This cmdlet returns objects that represent the services on the computer.</span></span>

## <span data-ttu-id="bee62-184">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="bee62-184">NOTES</span></span>

<span data-ttu-id="bee62-185">Ab PowerShell 6,0 werden den **ServiceController** -Objekten die folgenden Eigenschaften hinzugefügt: **username** , **Description** , **delayedaudestart** , **binarypathname** und **startupType** .</span><span class="sxs-lookup"><span data-stu-id="bee62-185">Beginning in PowerShell 6.0, the following properties are added to the **ServiceController** objects: **UserName** , **Description** , **DelayedAutoStart** , **BinaryPathName** , and **StartupType** .</span></span>

<span data-ttu-id="bee62-186">Sie können auch auf den `Get-Service` integrierten Alias verweisen `gsv` .</span><span class="sxs-lookup"><span data-stu-id="bee62-186">You can also refer to `Get-Service` by its built-in alias, `gsv`.</span></span> <span data-ttu-id="bee62-187">Weitere Informationen finden Sie unter [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="bee62-187">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="bee62-188">Dieses Cmdlet kann nur dann Dienste anzeigen, wenn der aktuelle Benutzer über die Berechtigung verfügt, Sie anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="bee62-188">This cmdlet can display services only when the current user has permission to see them.</span></span> <span data-ttu-id="bee62-189">Wenn dieses Cmdlet keine Dienste anzeigt, verfügen Sie möglicherweise nicht über die Berechtigung, diese anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="bee62-189">If this cmdlet does not display services, you might not have permission to see them.</span></span>

<span data-ttu-id="bee62-190">Geben Sie ein, um den Dienstnamen und den anzeigen amen der einzelnen Dienste auf dem System zu ermitteln `Get-Service` .</span><span class="sxs-lookup"><span data-stu-id="bee62-190">To find the service name and display name of each service on your system, type `Get-Service`.</span></span> <span data-ttu-id="bee62-191">Die Dienstnamen werden in der Spalte Name angezeigt, und die anzeigen Amen werden in der Spalte **Display Name** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bee62-191">The service names appear in the Name column, and the display names appear in the **DisplayName** column.</span></span>

<span data-ttu-id="bee62-192">Wenn Sie in aufsteigender Reihenfolge nach dem Wert der **Status** Eigenschaft sortieren, werden beendete Dienste vor dem Ausführen von Diensten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bee62-192">When you sort in ascending order by the **Status** property's value, Stopped services appear before Running services.</span></span> <span data-ttu-id="bee62-193">Die **Status** -Eigenschaft des dienstangs ist ein Enumerationswert, und die Statusnamen stellen ganzzahlige Werte dar</span><span class="sxs-lookup"><span data-stu-id="bee62-193">The service's **Status** property is an enumerated value and the status names represent integer values.</span></span> <span data-ttu-id="bee62-194">Die Sortierreihenfolge basiert auf dem ganzzahligen Wert und nicht auf dem Namen.</span><span class="sxs-lookup"><span data-stu-id="bee62-194">The sort order is based on the integer value, not the name.</span></span> <span data-ttu-id="bee62-195">Beendet wird vor angezeigt, da die Ausführung von, da beendet ist, den Wert 1 hat und die Ausführung von den Wert 4 aufweist.</span><span class="sxs-lookup"><span data-stu-id="bee62-195">Stopped appears before because Running because Stopped has a value of 1, and Running has a value of 4.</span></span> <span data-ttu-id="bee62-196">Weitere Informationen finden Sie unter [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).</span><span class="sxs-lookup"><span data-stu-id="bee62-196">For more information, see [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).</span></span>

## <span data-ttu-id="bee62-197">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="bee62-197">RELATED LINKS</span></span>

[<span data-ttu-id="bee62-198">New-Service</span><span class="sxs-lookup"><span data-stu-id="bee62-198">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="bee62-199">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="bee62-199">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="bee62-200">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="bee62-200">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="bee62-201">Set-Service</span><span class="sxs-lookup"><span data-stu-id="bee62-201">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="bee62-202">Start-Service</span><span class="sxs-lookup"><span data-stu-id="bee62-202">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="bee62-203">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="bee62-203">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="bee62-204">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="bee62-204">Suspend-Service</span></span>](Suspend-Service.md)

[<span data-ttu-id="bee62-205">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="bee62-205">Remove-Service</span></span>](Remove-Service.md)
