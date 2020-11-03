---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/stop-service?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Service
ms.openlocfilehash: 6bffe41f1efd42c686d06f59cf86b374b596d80d
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214351"
---
# <span data-ttu-id="3a531-103">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="3a531-103">Stop-Service</span></span>

## <span data-ttu-id="3a531-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="3a531-104">SYNOPSIS</span></span>
<span data-ttu-id="3a531-105">Beendet ausgeführte Dienste.</span><span class="sxs-lookup"><span data-stu-id="3a531-105">Stops one or more running services.</span></span>

## <span data-ttu-id="3a531-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3a531-106">SYNTAX</span></span>

### <span data-ttu-id="3a531-107">Inputobject (Standard)</span><span class="sxs-lookup"><span data-stu-id="3a531-107">InputObject (Default)</span></span>

```
Stop-Service [-Force] [-NoWait] [-InputObject] <ServiceController[]> [-PassThru] [-Include <String[]>]
 [-Exclude <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="3a531-108">Standard</span><span class="sxs-lookup"><span data-stu-id="3a531-108">Default</span></span>

```
Stop-Service [-Force] [-NoWait] [-Name] <String[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="3a531-109">DisplayName</span><span class="sxs-lookup"><span data-stu-id="3a531-109">DisplayName</span></span>

```
Stop-Service [-Force] [-NoWait] [-PassThru] -DisplayName <String[]> [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="3a531-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3a531-110">DESCRIPTION</span></span>

<span data-ttu-id="3a531-111">Das Cmdlet "End **-Service** " sendet für jeden der angegebenen Dienste eine Nachricht zum Abbrechen an den Windows-Dienst Controller.</span><span class="sxs-lookup"><span data-stu-id="3a531-111">The **Stop-Service** cmdlet sends a stop message to the Windows Service Controller for each of the specified services.</span></span>
<span data-ttu-id="3a531-112">Sie können die Dienste mit ihren Dienstnamen oder anzeigen Amen angeben, oder Sie können den **Inputobject** -Parameter verwenden, um ein Dienst Objekt zu übergeben, das den Dienst darstellt, den Sie abbrechen möchten.</span><span class="sxs-lookup"><span data-stu-id="3a531-112">You can specify the services by their service names or display names, or you can use the **InputObject** parameter to pass a service object that represents the service that you want to stop.</span></span>

## <span data-ttu-id="3a531-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="3a531-113">EXAMPLES</span></span>

### <span data-ttu-id="3a531-114">Beispiel 1: beendet einen Dienst auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="3a531-114">Example 1: Stop a service on the local computer</span></span>

```
PS C:\> Stop-Service -Name "sysmonlog"
```

<span data-ttu-id="3a531-115">Mit diesem Befehl wird der Dienst für Leistungsprotokolle und -benachrichtigungen (SysmonLog) auf dem lokalen Computer beendet.</span><span class="sxs-lookup"><span data-stu-id="3a531-115">This command stops the Performance Logs and Alerts (SysmonLog) service on the local computer.</span></span>

### <span data-ttu-id="3a531-116">Beispiel 2: Beendigung eines dienstandens mit dem anzeigen Amen</span><span class="sxs-lookup"><span data-stu-id="3a531-116">Example 2: Stop a service by using the display name</span></span>

```
PS C:\> Get-Service -DisplayName "telnet" | Stop-Service
```

<span data-ttu-id="3a531-117">Mit diesem Befehl wird der Dienst %%amp;quot;Telnet%%amp;quot; auf dem lokalen Computer beendet.</span><span class="sxs-lookup"><span data-stu-id="3a531-117">This command stops the Telnet service on the local computer.</span></span>
<span data-ttu-id="3a531-118">Der Befehl verwendet **Get-Service** , um ein Objekt zu erhalten, das den Telnet-Dienst darstellt.</span><span class="sxs-lookup"><span data-stu-id="3a531-118">The command uses **Get-Service** to get an object that represents the Telnet service.</span></span>
<span data-ttu-id="3a531-119">Der Pipeline Operator (|) übergibt das Objekt an den **Stopp-Dienst** , wodurch der Dienst beendet wird.</span><span class="sxs-lookup"><span data-stu-id="3a531-119">The pipeline operator (|) pipes the object to **Stop-Service** , which stops the service.</span></span>

### <span data-ttu-id="3a531-120">Beispiel 3: beendet einen Dienst, der über abhängige Dienste verfügt.</span><span class="sxs-lookup"><span data-stu-id="3a531-120">Example 3: Stop a service that has dependent services</span></span>

```
PS C:\> Get-Service -Name "iisadmin" | Format-List -Property Name, DependentServices
PS C:\> Stop-Service -Name "iisadmin" -Force -Confirm
```

<span data-ttu-id="3a531-121">In diesem Beispiel wird der IISAdmin-Dienst auf dem lokalen Computer angehalten.</span><span class="sxs-lookup"><span data-stu-id="3a531-121">This example stops the IISAdmin service on the local computer.</span></span>
<span data-ttu-id="3a531-122">Da durch das Beenden dieses Diensts auch die Dienste angehalten werden, die vom IISAdmin-Dienst abhängen, empfiehlt es sich, dem **Stop-Service** mit einem Befehl voranzugehen, der die Dienste auflistet, die vom IISAdmin-Dienst abhängen.</span><span class="sxs-lookup"><span data-stu-id="3a531-122">Because stopping this service also stops the services that depend on the IISAdmin service, it is best to precede **Stop-Service** with a command that lists the services that depend on the IISAdmin service.</span></span>

<span data-ttu-id="3a531-123">Mit dem ersten Befehl werden die Dienste aufgelistet, die von %%amp;quot;IISAdmin%%amp;quot; abhängen.</span><span class="sxs-lookup"><span data-stu-id="3a531-123">The first command lists the services that depend on IISAdmin.</span></span>
<span data-ttu-id="3a531-124">Er verwendet **Get-Service** , um ein Objekt zu erhalten, das den IISAdmin-Dienst darstellt.</span><span class="sxs-lookup"><span data-stu-id="3a531-124">It uses **Get-Service** to get an object that represents the IISAdmin service.</span></span>
<span data-ttu-id="3a531-125">Der Pipelineoperator (|) übergibt das Ergebnis an das Cmdlet %%amp;quot;Format-List%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="3a531-125">The pipeline operator (|) passes the result to the Format-List cmdlet.</span></span>
<span data-ttu-id="3a531-126">Der Befehl verwendet den *Property* -Parameter von " **Format-List** ", um nur die Eigenschaften " **Name** " und " **DependentServices** " des Diensts aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="3a531-126">The command uses the *Property* parameter of **Format-List** to list only the **Name** and **DependentServices** properties of the service.</span></span>

<span data-ttu-id="3a531-127">Mit dem zweiten Befehl wird der IISAdmin-Dienst beendet.</span><span class="sxs-lookup"><span data-stu-id="3a531-127">The second command stops the IISAdmin service.</span></span>
<span data-ttu-id="3a531-128">Der *Force* -Parameter ist erforderlich, um einen Dienst zu unterbinden, der über abhängige Dienste verfügt.</span><span class="sxs-lookup"><span data-stu-id="3a531-128">The *Force* parameter is required to stop a service that has dependent services.</span></span>
<span data-ttu-id="3a531-129">Der Befehl verwendet den *Confirm* -Parameter, um eine Bestätigung vom Benutzer anzufordern, bevor die einzelnen Dienste beendet werden.</span><span class="sxs-lookup"><span data-stu-id="3a531-129">The command uses the *Confirm* parameter to request confirmation from the user before it stops each service.</span></span>

## <span data-ttu-id="3a531-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3a531-130">PARAMETERS</span></span>

### <span data-ttu-id="3a531-131">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="3a531-131">-DisplayName</span></span>

<span data-ttu-id="3a531-132">Gibt die anzeigen amen der zu stoppenden Dienste an.</span><span class="sxs-lookup"><span data-stu-id="3a531-132">Specifies the display names of the services to stop.</span></span>
<span data-ttu-id="3a531-133">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="3a531-133">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="3a531-134">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="3a531-134">-Exclude</span></span>

<span data-ttu-id="3a531-135">Gibt die Dienste an, die von diesem Cmdlet ausgelassen werden.</span><span class="sxs-lookup"><span data-stu-id="3a531-135">Specifies services that this cmdlet omits.</span></span>
<span data-ttu-id="3a531-136">Der Wert dieses Parameters qualifiziert den *Name* -Parameter.</span><span class="sxs-lookup"><span data-stu-id="3a531-136">The value of this parameter qualifies the *Name* parameter.</span></span>
<span data-ttu-id="3a531-137">Geben Sie ein Namenselement oder-Muster ein, z. b. s \*.</span><span class="sxs-lookup"><span data-stu-id="3a531-137">Enter a name element or pattern, such as s\*.</span></span>
<span data-ttu-id="3a531-138">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="3a531-138">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="3a531-139">-Force</span><span class="sxs-lookup"><span data-stu-id="3a531-139">-Force</span></span>

<span data-ttu-id="3a531-140">Erzwingt, dass das Cmdlet einen Dienst beendet, auch wenn dieser Dienst über abhängige Dienste verfügt.</span><span class="sxs-lookup"><span data-stu-id="3a531-140">Forces the cmdlet to stop a service even if that service has dependent services.</span></span>

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

### <span data-ttu-id="3a531-141">-Include</span><span class="sxs-lookup"><span data-stu-id="3a531-141">-Include</span></span>

<span data-ttu-id="3a531-142">Gibt die Dienste an, die von diesem Cmdlet beendet werden.</span><span class="sxs-lookup"><span data-stu-id="3a531-142">Specifies services that this cmdlet stops.</span></span>
<span data-ttu-id="3a531-143">Der Wert dieses Parameters qualifiziert den *Name* -Parameter.</span><span class="sxs-lookup"><span data-stu-id="3a531-143">The value of this parameter qualifies the *Name* parameter.</span></span>
<span data-ttu-id="3a531-144">Geben Sie ein Namenselement oder-Muster ein, z. b. s \*.</span><span class="sxs-lookup"><span data-stu-id="3a531-144">Enter a name element or pattern, such as s\*.</span></span>
<span data-ttu-id="3a531-145">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="3a531-145">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="3a531-146">-InputObject</span><span class="sxs-lookup"><span data-stu-id="3a531-146">-InputObject</span></span>

<span data-ttu-id="3a531-147">Gibt **ServiceController** -Objekte an, die die zu stoppenden Dienste darstellen.</span><span class="sxs-lookup"><span data-stu-id="3a531-147">Specifies **ServiceController** objects that represent the services to stop.</span></span>
<span data-ttu-id="3a531-148">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="3a531-148">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="3a531-149">-Name</span><span class="sxs-lookup"><span data-stu-id="3a531-149">-Name</span></span>

<span data-ttu-id="3a531-150">Gibt die Dienstnamen der zu stoppenden Dienste an.</span><span class="sxs-lookup"><span data-stu-id="3a531-150">Specifies the service names of the services to stop.</span></span>
<span data-ttu-id="3a531-151">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="3a531-151">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="3a531-152">-Nowait</span><span class="sxs-lookup"><span data-stu-id="3a531-152">-NoWait</span></span>

<span data-ttu-id="3a531-153">Gibt an, dass dieses Cmdlet die Option No Wait verwendet.</span><span class="sxs-lookup"><span data-stu-id="3a531-153">Indicates that this cmdlet uses the no wait option.</span></span>

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

### <span data-ttu-id="3a531-154">-PassThru</span><span class="sxs-lookup"><span data-stu-id="3a531-154">-PassThru</span></span>

<span data-ttu-id="3a531-155">Gibt ein Objekt zurück, das den Dienst darstellt.</span><span class="sxs-lookup"><span data-stu-id="3a531-155">Returns an object that represents the service.</span></span>
<span data-ttu-id="3a531-156">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="3a531-156">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="3a531-157">-Confirm</span><span class="sxs-lookup"><span data-stu-id="3a531-157">-Confirm</span></span>

<span data-ttu-id="3a531-158">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="3a531-158">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="3a531-159">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="3a531-159">-WhatIf</span></span>

<span data-ttu-id="3a531-160">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3a531-160">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="3a531-161">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="3a531-161">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="3a531-162">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="3a531-162">CommonParameters</span></span>

<span data-ttu-id="3a531-163">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3a531-163">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3a531-164">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="3a531-164">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3a531-165">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="3a531-165">INPUTS</span></span>

### <span data-ttu-id="3a531-166">System. ServiceProcess. ServiceController, System. String</span><span class="sxs-lookup"><span data-stu-id="3a531-166">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="3a531-167">Sie können ein Dienst Objekt oder eine Zeichenfolge, die den Namen eines diensnamens enthält, über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="3a531-167">You can pipe a service object or a string that contains the name of a service to this cmdlet.</span></span>

## <span data-ttu-id="3a531-168">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="3a531-168">OUTPUTS</span></span>

### <span data-ttu-id="3a531-169">Keine, System. ServiceProcess. ServiceController</span><span class="sxs-lookup"><span data-stu-id="3a531-169">None, System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="3a531-170">Dieses Cmdlet generiert ein **System. ServiceProcess. ServiceController** -Objekt, das den Dienst darstellt, wenn Sie den *passthru* -Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="3a531-170">This cmdlet generates a **System.ServiceProcess.ServiceController** object that represents the service, if you use the *PassThru* parameter.</span></span>
<span data-ttu-id="3a531-171">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="3a531-171">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="3a531-172">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="3a531-172">NOTES</span></span>

* <span data-ttu-id="3a531-173">Sie können auch über den integrierten Alias **spsv** auf "End **-Service** " verweisen.</span><span class="sxs-lookup"><span data-stu-id="3a531-173">You can also refer to **Stop-Service** by its built-in alias, **spsv** .</span></span> <span data-ttu-id="3a531-174">Weitere Informationen finden Sie unter %%amp;quot;about_Aliases%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="3a531-174">For more information, see about_Aliases.</span></span>

  <span data-ttu-id="3a531-175">" **Beenden": der Dienst** kann die Dienste nur steuern, wenn der aktuelle Benutzer über die entsprechende Berechtigung verfügt.</span><span class="sxs-lookup"><span data-stu-id="3a531-175">**Stop-Service** can control services only when the current user has permission to do this.</span></span>
<span data-ttu-id="3a531-176">Wenn ein Befehl nicht ordnungsgemäß verarbeitet wird, verfügen Sie u. U. nicht über die erforderlichen Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="3a531-176">If a command does not work correctly, you might not have the required permissions.</span></span>

  <span data-ttu-id="3a531-177">Geben Sie ein, um die Dienstnamen und anzeigen amen der Dienste auf dem System zu suchen `Get-Service` .</span><span class="sxs-lookup"><span data-stu-id="3a531-177">To find the service names and display names of the services on your system, type `Get-Service`.</span></span>
<span data-ttu-id="3a531-178">Die Dienstnamen werden in der Spalte " **Name** " angezeigt, und die anzeigen Amen werden in der Spalte " **Display Name** " angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3a531-178">The service names appear in the **Name** column and the display names appear in the **DisplayName** column.</span></span>

*

## <span data-ttu-id="3a531-179">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="3a531-179">RELATED LINKS</span></span>

[<span data-ttu-id="3a531-180">Get-Service</span><span class="sxs-lookup"><span data-stu-id="3a531-180">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="3a531-181">New-Service</span><span class="sxs-lookup"><span data-stu-id="3a531-181">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="3a531-182">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="3a531-182">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="3a531-183">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="3a531-183">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="3a531-184">Set-Service</span><span class="sxs-lookup"><span data-stu-id="3a531-184">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="3a531-185">Start-Service</span><span class="sxs-lookup"><span data-stu-id="3a531-185">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="3a531-186">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="3a531-186">Suspend-Service</span></span>](Suspend-Service.md)
