---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/stop-service?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Service
ms.openlocfilehash: 77ce507d0eaf476e2c24f41e433bd69fdcb416bb
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2020
ms.locfileid: "94342568"
---
# <span data-ttu-id="01940-103">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="01940-103">Stop-Service</span></span>

## <span data-ttu-id="01940-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="01940-104">SYNOPSIS</span></span>
<span data-ttu-id="01940-105">Beendet ausgeführte Dienste.</span><span class="sxs-lookup"><span data-stu-id="01940-105">Stops one or more running services.</span></span>

## <span data-ttu-id="01940-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="01940-106">SYNTAX</span></span>

### <span data-ttu-id="01940-107">Inputobject (Standard)</span><span class="sxs-lookup"><span data-stu-id="01940-107">InputObject (Default)</span></span>

```
Stop-Service [-Force] [-NoWait] [-InputObject] <ServiceController[]> [-PassThru] [-Include <String[]>]
 [-Exclude <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="01940-108">Standard</span><span class="sxs-lookup"><span data-stu-id="01940-108">Default</span></span>

```
Stop-Service [-Force] [-NoWait] [-Name] <String[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="01940-109">DisplayName</span><span class="sxs-lookup"><span data-stu-id="01940-109">DisplayName</span></span>

```
Stop-Service [-Force] [-NoWait] [-PassThru] -DisplayName <String[]> [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="01940-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="01940-110">DESCRIPTION</span></span>

<span data-ttu-id="01940-111">Das- `Stop-Service` Cmdlet sendet für jeden der angegebenen Dienste eine Stoppmeldung an den Windows-Dienst Controller.</span><span class="sxs-lookup"><span data-stu-id="01940-111">The `Stop-Service` cmdlet sends a stop message to the Windows Service Controller for each of the specified services.</span></span> <span data-ttu-id="01940-112">Sie können die Dienste mit ihren Dienstnamen oder anzeigen Amen angeben, oder Sie können den **Inputobject** -Parameter verwenden, um ein Dienst Objekt zu übergeben, das den Dienst darstellt, den Sie abbrechen möchten.</span><span class="sxs-lookup"><span data-stu-id="01940-112">You can specify the services by their service names or display names, or you can use the **InputObject** parameter to pass a service object that represents the service that you want to stop.</span></span>

## <span data-ttu-id="01940-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="01940-113">EXAMPLES</span></span>

### <span data-ttu-id="01940-114">Beispiel 1: beendet einen Dienst auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="01940-114">Example 1: Stop a service on the local computer</span></span>

```
PS C:\> Stop-Service -Name "sysmonlog"
```

<span data-ttu-id="01940-115">Mit diesem Befehl wird der Dienst für Leistungsprotokolle und -benachrichtigungen (SysmonLog) auf dem lokalen Computer beendet.</span><span class="sxs-lookup"><span data-stu-id="01940-115">This command stops the Performance Logs and Alerts (SysmonLog) service on the local computer.</span></span>

### <span data-ttu-id="01940-116">Beispiel 2: Beendigung eines dienstandens mit dem anzeigen Amen</span><span class="sxs-lookup"><span data-stu-id="01940-116">Example 2: Stop a service by using the display name</span></span>

```
PS C:\> Get-Service -DisplayName "telnet" | Stop-Service
```

<span data-ttu-id="01940-117">Mit diesem Befehl wird der Dienst %%amp;quot;Telnet%%amp;quot; auf dem lokalen Computer beendet.</span><span class="sxs-lookup"><span data-stu-id="01940-117">This command stops the Telnet service on the local computer.</span></span> <span data-ttu-id="01940-118">Der Befehl verwendet `Get-Service` , um ein Objekt zu erhalten, das den Telnet-Dienst darstellt.</span><span class="sxs-lookup"><span data-stu-id="01940-118">The command uses `Get-Service` to get an object that represents the Telnet service.</span></span> <span data-ttu-id="01940-119">Der Pipeline Operator ( `|` ) übergibt das Objekt an `Stop-Service` , wodurch der Dienst beendet wird.</span><span class="sxs-lookup"><span data-stu-id="01940-119">The pipeline operator (`|`) pipes the object to `Stop-Service`, which stops the service.</span></span>

### <span data-ttu-id="01940-120">Beispiel 3: beendet einen Dienst, der über abhängige Dienste verfügt.</span><span class="sxs-lookup"><span data-stu-id="01940-120">Example 3: Stop a service that has dependent services</span></span>

```
PS C:\> Get-Service -Name "iisadmin" | Format-List -Property Name, DependentServices
PS C:\> Stop-Service -Name "iisadmin" -Force -Confirm
```

<span data-ttu-id="01940-121">In diesem Beispiel wird der IISAdmin-Dienst auf dem lokalen Computer angehalten.</span><span class="sxs-lookup"><span data-stu-id="01940-121">This example stops the IISAdmin service on the local computer.</span></span> <span data-ttu-id="01940-122">Da das Beenden dieses Diensts auch die Dienste stoppt, die vom IISAdmin-Dienst abhängen, empfiehlt es sich, `Stop-Service` einem Befehl, der die Dienste auflistet, die vom IISAdmin-Dienst abhängen, einen vorangestellten Befehl vorzufinden.</span><span class="sxs-lookup"><span data-stu-id="01940-122">Because stopping this service also stops the services that depend on the IISAdmin service, it is best to precede `Stop-Service` with a command that lists the services that depend on the IISAdmin service.</span></span>

<span data-ttu-id="01940-123">Mit dem ersten Befehl werden die Dienste aufgelistet, die von %%amp;quot;IISAdmin%%amp;quot; abhängen.</span><span class="sxs-lookup"><span data-stu-id="01940-123">The first command lists the services that depend on IISAdmin.</span></span> <span data-ttu-id="01940-124">Es wird verwendet `Get-Service` , um ein Objekt zu erhalten, das den IISAdmin-Dienst darstellt.</span><span class="sxs-lookup"><span data-stu-id="01940-124">It uses `Get-Service` to get an object that represents the IISAdmin service.</span></span> <span data-ttu-id="01940-125">Der Pipeline Operator ( `|` ) übergibt das Ergebnis an das `Format-List` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="01940-125">The pipeline operator (`|`) passes the result to the `Format-List` cmdlet.</span></span> <span data-ttu-id="01940-126">Der Befehl verwendet den **Property** -Parameter von `Format-List` , um nur die **Name** -Eigenschaft und die **DependentServices** -Eigenschaft des Diensts aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="01940-126">The command uses the **Property** parameter of `Format-List` to list only the **Name** and **DependentServices** properties of the service.</span></span>

<span data-ttu-id="01940-127">Mit dem zweiten Befehl wird der IISAdmin-Dienst beendet.</span><span class="sxs-lookup"><span data-stu-id="01940-127">The second command stops the IISAdmin service.</span></span> <span data-ttu-id="01940-128">Der **Force** -Parameter ist erforderlich, um einen Dienst zu unterbinden, der über abhängige Dienste verfügt.</span><span class="sxs-lookup"><span data-stu-id="01940-128">The **Force** parameter is required to stop a service that has dependent services.</span></span> <span data-ttu-id="01940-129">Der Befehl verwendet den **Confirm** -Parameter, um eine Bestätigung vom Benutzer anzufordern, bevor die einzelnen Dienste beendet werden.</span><span class="sxs-lookup"><span data-stu-id="01940-129">The command uses the **Confirm** parameter to request confirmation from the user before it stops each service.</span></span>

## <span data-ttu-id="01940-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="01940-130">PARAMETERS</span></span>

### <span data-ttu-id="01940-131">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="01940-131">-DisplayName</span></span>

<span data-ttu-id="01940-132">Gibt die anzeigen amen der zu stoppenden Dienste an.</span><span class="sxs-lookup"><span data-stu-id="01940-132">Specifies the display names of the services to stop.</span></span>
<span data-ttu-id="01940-133">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="01940-133">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="01940-134">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="01940-134">-Exclude</span></span>

<span data-ttu-id="01940-135">Gibt die Dienste an, die von diesem Cmdlet ausgelassen werden.</span><span class="sxs-lookup"><span data-stu-id="01940-135">Specifies services that this cmdlet omits.</span></span> <span data-ttu-id="01940-136">Der Wert dieses Parameters qualifiziert den **Name** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="01940-136">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="01940-137">Geben Sie ein Namenselement oder-Muster ein, z. b. s \*.</span><span class="sxs-lookup"><span data-stu-id="01940-137">Enter a name element or pattern, such as s\*.</span></span> <span data-ttu-id="01940-138">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="01940-138">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="01940-139">-Force</span><span class="sxs-lookup"><span data-stu-id="01940-139">-Force</span></span>

<span data-ttu-id="01940-140">Erzwingt, dass das Cmdlet einen Dienst beendet, auch wenn dieser Dienst über abhängige Dienste verfügt.</span><span class="sxs-lookup"><span data-stu-id="01940-140">Forces the cmdlet to stop a service even if that service has dependent services.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="01940-141">-Include</span><span class="sxs-lookup"><span data-stu-id="01940-141">-Include</span></span>

<span data-ttu-id="01940-142">Gibt die Dienste an, die von diesem Cmdlet beendet werden.</span><span class="sxs-lookup"><span data-stu-id="01940-142">Specifies services that this cmdlet stops.</span></span> <span data-ttu-id="01940-143">Der Wert dieses Parameters qualifiziert den **Name** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="01940-143">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="01940-144">Geben Sie ein Namenselement oder-Muster ein, z. b. s \*.</span><span class="sxs-lookup"><span data-stu-id="01940-144">Enter a name element or pattern, such as s\*.</span></span> <span data-ttu-id="01940-145">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="01940-145">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="01940-146">-InputObject</span><span class="sxs-lookup"><span data-stu-id="01940-146">-InputObject</span></span>

<span data-ttu-id="01940-147">Gibt **ServiceController** -Objekte an, die die zu stoppenden Dienste darstellen.</span><span class="sxs-lookup"><span data-stu-id="01940-147">Specifies **ServiceController** objects that represent the services to stop.</span></span> <span data-ttu-id="01940-148">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="01940-148">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

```yaml
Type: System.ServiceProcess.ServiceController[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="01940-149">-Name</span><span class="sxs-lookup"><span data-stu-id="01940-149">-Name</span></span>

<span data-ttu-id="01940-150">Gibt die Dienstnamen der zu stoppenden Dienste an.</span><span class="sxs-lookup"><span data-stu-id="01940-150">Specifies the service names of the services to stop.</span></span> <span data-ttu-id="01940-151">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="01940-151">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases: ServiceName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="01940-152">-Nowait</span><span class="sxs-lookup"><span data-stu-id="01940-152">-NoWait</span></span>

<span data-ttu-id="01940-153">Gibt an, dass dieses Cmdlet die Option No Wait verwendet.</span><span class="sxs-lookup"><span data-stu-id="01940-153">Indicates that this cmdlet uses the no wait option.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="01940-154">-PassThru</span><span class="sxs-lookup"><span data-stu-id="01940-154">-PassThru</span></span>

<span data-ttu-id="01940-155">Gibt ein Objekt zurück, das den Dienst darstellt.</span><span class="sxs-lookup"><span data-stu-id="01940-155">Returns an object that represents the service.</span></span> <span data-ttu-id="01940-156">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="01940-156">By default, this cmdlet does not generate any output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="01940-157">-Confirm</span><span class="sxs-lookup"><span data-stu-id="01940-157">-Confirm</span></span>

<span data-ttu-id="01940-158">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="01940-158">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="01940-159">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="01940-159">-WhatIf</span></span>

<span data-ttu-id="01940-160">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="01940-160">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="01940-161">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="01940-161">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="01940-162">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="01940-162">CommonParameters</span></span>

<span data-ttu-id="01940-163">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="01940-163">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="01940-164">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="01940-164">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="01940-165">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="01940-165">INPUTS</span></span>

### <span data-ttu-id="01940-166">System. ServiceProcess. ServiceController, System. String</span><span class="sxs-lookup"><span data-stu-id="01940-166">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="01940-167">Sie können ein Dienst Objekt oder eine Zeichenfolge, die den Namen eines diensnamens enthält, über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="01940-167">You can pipe a service object or a string that contains the name of a service to this cmdlet.</span></span>

## <span data-ttu-id="01940-168">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="01940-168">OUTPUTS</span></span>

### <span data-ttu-id="01940-169">Keine, System. ServiceProcess. ServiceController</span><span class="sxs-lookup"><span data-stu-id="01940-169">None, System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="01940-170">Dieses Cmdlet generiert ein **System. ServiceProcess. ServiceController** -Objekt, das den Dienst darstellt, wenn Sie den **passthru** -Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="01940-170">This cmdlet generates a **System.ServiceProcess.ServiceController** object that represents the service, if you use the **PassThru** parameter.</span></span> <span data-ttu-id="01940-171">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="01940-171">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="01940-172">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="01940-172">NOTES</span></span>

<span data-ttu-id="01940-173">Sie können auch über `Stop-Service` den integrierten Alias **spsv** auf verweisen.</span><span class="sxs-lookup"><span data-stu-id="01940-173">You can also refer to `Stop-Service` by its built-in alias, **spsv**.</span></span> <span data-ttu-id="01940-174">Weitere Informationen finden Sie unter %%amp;quot;about_Aliases%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="01940-174">For more information, see about_Aliases.</span></span>

<span data-ttu-id="01940-175">`Stop-Service` Dienste können nur von gesteuert werden, wenn der aktuelle Benutzer über die entsprechende Berechtigung verfügt.</span><span class="sxs-lookup"><span data-stu-id="01940-175">`Stop-Service` can control services only when the current user has permission to do this.</span></span> <span data-ttu-id="01940-176">Wenn ein Befehl nicht ordnungsgemäß verarbeitet wird, verfügen Sie u. U. nicht über die erforderlichen Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="01940-176">If a command does not work correctly, you might not have the required permissions.</span></span>

<span data-ttu-id="01940-177">Geben Sie ein, um die Dienstnamen und anzeigen amen der Dienste auf dem System zu suchen `Get-Service` .</span><span class="sxs-lookup"><span data-stu-id="01940-177">To find the service names and display names of the services on your system, type `Get-Service`.</span></span> <span data-ttu-id="01940-178">Die Dienstnamen werden in der Spalte " **Name** " angezeigt, und die anzeigen Amen werden in der Spalte " **Display Name** " angezeigt.</span><span class="sxs-lookup"><span data-stu-id="01940-178">The service names appear in the **Name** column and the display names appear in the **DisplayName** column.</span></span>

## <span data-ttu-id="01940-179">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="01940-179">RELATED LINKS</span></span>

[<span data-ttu-id="01940-180">Get-Service</span><span class="sxs-lookup"><span data-stu-id="01940-180">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="01940-181">New-Service</span><span class="sxs-lookup"><span data-stu-id="01940-181">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="01940-182">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="01940-182">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="01940-183">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="01940-183">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="01940-184">Set-Service</span><span class="sxs-lookup"><span data-stu-id="01940-184">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="01940-185">Start-Service</span><span class="sxs-lookup"><span data-stu-id="01940-185">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="01940-186">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="01940-186">Suspend-Service</span></span>](Suspend-Service.md)
