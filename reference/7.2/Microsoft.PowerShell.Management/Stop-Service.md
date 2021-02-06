---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/stop-service?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Service
ms.openlocfilehash: 0216c7fae722121ead1c8e9ba122fbc3f1713725
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596557"
---
# <span data-ttu-id="7ba8b-102">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="7ba8b-102">Stop-Service</span></span>

## <span data-ttu-id="7ba8b-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="7ba8b-103">SYNOPSIS</span></span>
<span data-ttu-id="7ba8b-104">Beendet ausgeführte Dienste.</span><span class="sxs-lookup"><span data-stu-id="7ba8b-104">Stops one or more running services.</span></span>

## <span data-ttu-id="7ba8b-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7ba8b-105">SYNTAX</span></span>

### <span data-ttu-id="7ba8b-106">Inputobject (Standard)</span><span class="sxs-lookup"><span data-stu-id="7ba8b-106">InputObject (Default)</span></span>

```
Stop-Service [-Force] [-NoWait] [-InputObject] <ServiceController[]> [-PassThru] [-Include <String[]>]
 [-Exclude <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="7ba8b-107">Standard</span><span class="sxs-lookup"><span data-stu-id="7ba8b-107">Default</span></span>

```
Stop-Service [-Force] [-NoWait] [-Name] <String[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="7ba8b-108">DisplayName</span><span class="sxs-lookup"><span data-stu-id="7ba8b-108">DisplayName</span></span>

```
Stop-Service [-Force] [-NoWait] [-PassThru] -DisplayName <String[]> [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="7ba8b-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7ba8b-109">DESCRIPTION</span></span>

<span data-ttu-id="7ba8b-110">Das- `Stop-Service` Cmdlet sendet für jeden der angegebenen Dienste eine Stoppmeldung an den Windows-Dienst Controller.</span><span class="sxs-lookup"><span data-stu-id="7ba8b-110">The `Stop-Service` cmdlet sends a stop message to the Windows Service Controller for each of the specified services.</span></span> <span data-ttu-id="7ba8b-111">Sie können die Dienste mit ihren Dienstnamen oder anzeigen Amen angeben, oder Sie können den **Inputobject** -Parameter verwenden, um ein Dienst Objekt zu übergeben, das den Dienst darstellt, den Sie abbrechen möchten.</span><span class="sxs-lookup"><span data-stu-id="7ba8b-111">You can specify the services by their service names or display names, or you can use the **InputObject** parameter to pass a service object that represents the service that you want to stop.</span></span>

## <span data-ttu-id="7ba8b-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="7ba8b-112">EXAMPLES</span></span>

### <span data-ttu-id="7ba8b-113">Beispiel 1: beendet einen Dienst auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="7ba8b-113">Example 1: Stop a service on the local computer</span></span>

```
PS C:\> Stop-Service -Name "sysmonlog"
```

<span data-ttu-id="7ba8b-114">Mit diesem Befehl wird der Dienst für Leistungsprotokolle und -benachrichtigungen (SysmonLog) auf dem lokalen Computer beendet.</span><span class="sxs-lookup"><span data-stu-id="7ba8b-114">This command stops the Performance Logs and Alerts (SysmonLog) service on the local computer.</span></span>

### <span data-ttu-id="7ba8b-115">Beispiel 2: Beendigung eines dienstandens mit dem anzeigen Amen</span><span class="sxs-lookup"><span data-stu-id="7ba8b-115">Example 2: Stop a service by using the display name</span></span>

```
PS C:\> Get-Service -DisplayName "telnet" | Stop-Service
```

<span data-ttu-id="7ba8b-116">Mit diesem Befehl wird der Dienst %%amp;quot;Telnet%%amp;quot; auf dem lokalen Computer beendet.</span><span class="sxs-lookup"><span data-stu-id="7ba8b-116">This command stops the Telnet service on the local computer.</span></span> <span data-ttu-id="7ba8b-117">Der Befehl verwendet `Get-Service` , um ein Objekt zu erhalten, das den Telnet-Dienst darstellt.</span><span class="sxs-lookup"><span data-stu-id="7ba8b-117">The command uses `Get-Service` to get an object that represents the Telnet service.</span></span> <span data-ttu-id="7ba8b-118">Der Pipeline Operator ( `|` ) übergibt das Objekt an `Stop-Service` , wodurch der Dienst beendet wird.</span><span class="sxs-lookup"><span data-stu-id="7ba8b-118">The pipeline operator (`|`) pipes the object to `Stop-Service`, which stops the service.</span></span>

### <span data-ttu-id="7ba8b-119">Beispiel 3: beendet einen Dienst, der über abhängige Dienste verfügt.</span><span class="sxs-lookup"><span data-stu-id="7ba8b-119">Example 3: Stop a service that has dependent services</span></span>

```
PS C:\> Get-Service -Name "iisadmin" | Format-List -Property Name, DependentServices
PS C:\> Stop-Service -Name "iisadmin" -Force -Confirm
```

<span data-ttu-id="7ba8b-120">In diesem Beispiel wird der IISAdmin-Dienst auf dem lokalen Computer angehalten.</span><span class="sxs-lookup"><span data-stu-id="7ba8b-120">This example stops the IISAdmin service on the local computer.</span></span> <span data-ttu-id="7ba8b-121">Da das Beenden dieses Diensts auch die Dienste stoppt, die vom IISAdmin-Dienst abhängen, empfiehlt es sich, `Stop-Service` einem Befehl, der die Dienste auflistet, die vom IISAdmin-Dienst abhängen, einen vorangestellten Befehl vorzufinden.</span><span class="sxs-lookup"><span data-stu-id="7ba8b-121">Because stopping this service also stops the services that depend on the IISAdmin service, it is best to precede `Stop-Service` with a command that lists the services that depend on the IISAdmin service.</span></span>

<span data-ttu-id="7ba8b-122">Mit dem ersten Befehl werden die Dienste aufgelistet, die von %%amp;quot;IISAdmin%%amp;quot; abhängen.</span><span class="sxs-lookup"><span data-stu-id="7ba8b-122">The first command lists the services that depend on IISAdmin.</span></span> <span data-ttu-id="7ba8b-123">Es wird verwendet `Get-Service` , um ein Objekt zu erhalten, das den IISAdmin-Dienst darstellt.</span><span class="sxs-lookup"><span data-stu-id="7ba8b-123">It uses `Get-Service` to get an object that represents the IISAdmin service.</span></span> <span data-ttu-id="7ba8b-124">Der Pipeline Operator ( `|` ) übergibt das Ergebnis an das `Format-List` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7ba8b-124">The pipeline operator (`|`) passes the result to the `Format-List` cmdlet.</span></span> <span data-ttu-id="7ba8b-125">Der Befehl verwendet den **Property** -Parameter von `Format-List` , um nur die **Name** -Eigenschaft und die **DependentServices** -Eigenschaft des Diensts aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="7ba8b-125">The command uses the **Property** parameter of `Format-List` to list only the **Name** and **DependentServices** properties of the service.</span></span>

<span data-ttu-id="7ba8b-126">Mit dem zweiten Befehl wird der IISAdmin-Dienst beendet.</span><span class="sxs-lookup"><span data-stu-id="7ba8b-126">The second command stops the IISAdmin service.</span></span> <span data-ttu-id="7ba8b-127">Der **Force** -Parameter ist erforderlich, um einen Dienst zu unterbinden, der über abhängige Dienste verfügt.</span><span class="sxs-lookup"><span data-stu-id="7ba8b-127">The **Force** parameter is required to stop a service that has dependent services.</span></span> <span data-ttu-id="7ba8b-128">Der Befehl verwendet den **Confirm** -Parameter, um eine Bestätigung vom Benutzer anzufordern, bevor die einzelnen Dienste beendet werden.</span><span class="sxs-lookup"><span data-stu-id="7ba8b-128">The command uses the **Confirm** parameter to request confirmation from the user before it stops each service.</span></span>

## <span data-ttu-id="7ba8b-129">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7ba8b-129">PARAMETERS</span></span>

### <span data-ttu-id="7ba8b-130">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="7ba8b-130">-DisplayName</span></span>

<span data-ttu-id="7ba8b-131">Gibt die anzeigen amen der zu stoppenden Dienste an.</span><span class="sxs-lookup"><span data-stu-id="7ba8b-131">Specifies the display names of the services to stop.</span></span>
<span data-ttu-id="7ba8b-132">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="7ba8b-132">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="7ba8b-133">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="7ba8b-133">-Exclude</span></span>

<span data-ttu-id="7ba8b-134">Gibt die Dienste an, die von diesem Cmdlet ausgelassen werden.</span><span class="sxs-lookup"><span data-stu-id="7ba8b-134">Specifies services that this cmdlet omits.</span></span> <span data-ttu-id="7ba8b-135">Der Wert dieses Parameters qualifiziert den **Name** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="7ba8b-135">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="7ba8b-136">Geben Sie ein Namenselement oder-Muster ein, z. b. s \*.</span><span class="sxs-lookup"><span data-stu-id="7ba8b-136">Enter a name element or pattern, such as s\*.</span></span> <span data-ttu-id="7ba8b-137">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="7ba8b-137">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="7ba8b-138">-Force</span><span class="sxs-lookup"><span data-stu-id="7ba8b-138">-Force</span></span>

<span data-ttu-id="7ba8b-139">Erzwingt, dass das Cmdlet einen Dienst beendet, auch wenn dieser Dienst über abhängige Dienste verfügt.</span><span class="sxs-lookup"><span data-stu-id="7ba8b-139">Forces the cmdlet to stop a service even if that service has dependent services.</span></span>

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

### <span data-ttu-id="7ba8b-140">-Include</span><span class="sxs-lookup"><span data-stu-id="7ba8b-140">-Include</span></span>

<span data-ttu-id="7ba8b-141">Gibt die Dienste an, die von diesem Cmdlet beendet werden.</span><span class="sxs-lookup"><span data-stu-id="7ba8b-141">Specifies services that this cmdlet stops.</span></span> <span data-ttu-id="7ba8b-142">Der Wert dieses Parameters qualifiziert den **Name** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="7ba8b-142">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="7ba8b-143">Geben Sie ein Namenselement oder-Muster ein, z. b. s \*.</span><span class="sxs-lookup"><span data-stu-id="7ba8b-143">Enter a name element or pattern, such as s\*.</span></span> <span data-ttu-id="7ba8b-144">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="7ba8b-144">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="7ba8b-145">-InputObject</span><span class="sxs-lookup"><span data-stu-id="7ba8b-145">-InputObject</span></span>

<span data-ttu-id="7ba8b-146">Gibt **ServiceController** -Objekte an, die die zu stoppenden Dienste darstellen.</span><span class="sxs-lookup"><span data-stu-id="7ba8b-146">Specifies **ServiceController** objects that represent the services to stop.</span></span> <span data-ttu-id="7ba8b-147">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="7ba8b-147">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="7ba8b-148">-Name</span><span class="sxs-lookup"><span data-stu-id="7ba8b-148">-Name</span></span>

<span data-ttu-id="7ba8b-149">Gibt die Dienstnamen der zu stoppenden Dienste an.</span><span class="sxs-lookup"><span data-stu-id="7ba8b-149">Specifies the service names of the services to stop.</span></span> <span data-ttu-id="7ba8b-150">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="7ba8b-150">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="7ba8b-151">-Nowait</span><span class="sxs-lookup"><span data-stu-id="7ba8b-151">-NoWait</span></span>

<span data-ttu-id="7ba8b-152">Gibt an, dass dieses Cmdlet die Option No Wait verwendet.</span><span class="sxs-lookup"><span data-stu-id="7ba8b-152">Indicates that this cmdlet uses the no wait option.</span></span>

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

### <span data-ttu-id="7ba8b-153">-PassThru</span><span class="sxs-lookup"><span data-stu-id="7ba8b-153">-PassThru</span></span>

<span data-ttu-id="7ba8b-154">Gibt ein Objekt zurück, das den Dienst darstellt.</span><span class="sxs-lookup"><span data-stu-id="7ba8b-154">Returns an object that represents the service.</span></span> <span data-ttu-id="7ba8b-155">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="7ba8b-155">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="7ba8b-156">-Confirm</span><span class="sxs-lookup"><span data-stu-id="7ba8b-156">-Confirm</span></span>

<span data-ttu-id="7ba8b-157">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="7ba8b-157">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="7ba8b-158">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="7ba8b-158">-WhatIf</span></span>

<span data-ttu-id="7ba8b-159">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7ba8b-159">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="7ba8b-160">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7ba8b-160">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="7ba8b-161">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="7ba8b-161">CommonParameters</span></span>

<span data-ttu-id="7ba8b-162">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="7ba8b-162">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7ba8b-163">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="7ba8b-163">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7ba8b-164">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="7ba8b-164">INPUTS</span></span>

### <span data-ttu-id="7ba8b-165">System. ServiceProcess. ServiceController, System. String</span><span class="sxs-lookup"><span data-stu-id="7ba8b-165">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="7ba8b-166">Sie können ein Dienst Objekt oder eine Zeichenfolge, die den Namen eines diensnamens enthält, über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="7ba8b-166">You can pipe a service object or a string that contains the name of a service to this cmdlet.</span></span>

## <span data-ttu-id="7ba8b-167">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="7ba8b-167">OUTPUTS</span></span>

### <span data-ttu-id="7ba8b-168">Keine, System. ServiceProcess. ServiceController</span><span class="sxs-lookup"><span data-stu-id="7ba8b-168">None, System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="7ba8b-169">Dieses Cmdlet generiert ein **System. ServiceProcess. ServiceController** -Objekt, das den Dienst darstellt, wenn Sie den **passthru** -Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="7ba8b-169">This cmdlet generates a **System.ServiceProcess.ServiceController** object that represents the service, if you use the **PassThru** parameter.</span></span> <span data-ttu-id="7ba8b-170">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="7ba8b-170">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="7ba8b-171">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="7ba8b-171">NOTES</span></span>

<span data-ttu-id="7ba8b-172">Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7ba8b-172">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="7ba8b-173">Sie können auch über `Stop-Service` den integrierten Alias **spsv** auf verweisen.</span><span class="sxs-lookup"><span data-stu-id="7ba8b-173">You can also refer to `Stop-Service` by its built-in alias, **spsv**.</span></span> <span data-ttu-id="7ba8b-174">Weitere Informationen finden Sie unter %%amp;quot;about_Aliases%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="7ba8b-174">For more information, see about_Aliases.</span></span>

<span data-ttu-id="7ba8b-175">`Stop-Service` Dienste können nur von gesteuert werden, wenn der aktuelle Benutzer über die entsprechende Berechtigung verfügt.</span><span class="sxs-lookup"><span data-stu-id="7ba8b-175">`Stop-Service` can control services only when the current user has permission to do this.</span></span> <span data-ttu-id="7ba8b-176">Wenn ein Befehl nicht ordnungsgemäß verarbeitet wird, verfügen Sie u. U. nicht über die erforderlichen Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="7ba8b-176">If a command does not work correctly, you might not have the required permissions.</span></span>

<span data-ttu-id="7ba8b-177">Geben Sie ein, um die Dienstnamen und anzeigen amen der Dienste auf dem System zu suchen `Get-Service` .</span><span class="sxs-lookup"><span data-stu-id="7ba8b-177">To find the service names and display names of the services on your system, type `Get-Service`.</span></span> <span data-ttu-id="7ba8b-178">Die Dienstnamen werden in der Spalte " **Name** " angezeigt, und die anzeigen Amen werden in der Spalte " **Display Name** " angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7ba8b-178">The service names appear in the **Name** column and the display names appear in the **DisplayName** column.</span></span>

## <span data-ttu-id="7ba8b-179">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="7ba8b-179">RELATED LINKS</span></span>

[<span data-ttu-id="7ba8b-180">Get-Service</span><span class="sxs-lookup"><span data-stu-id="7ba8b-180">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="7ba8b-181">New-Service</span><span class="sxs-lookup"><span data-stu-id="7ba8b-181">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="7ba8b-182">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="7ba8b-182">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="7ba8b-183">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="7ba8b-183">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="7ba8b-184">Set-Service</span><span class="sxs-lookup"><span data-stu-id="7ba8b-184">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="7ba8b-185">Start-Service</span><span class="sxs-lookup"><span data-stu-id="7ba8b-185">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="7ba8b-186">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="7ba8b-186">Suspend-Service</span></span>](Suspend-Service.md)

[<span data-ttu-id="7ba8b-187">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="7ba8b-187">Remove-Service</span></span>](Remove-Service.md)
