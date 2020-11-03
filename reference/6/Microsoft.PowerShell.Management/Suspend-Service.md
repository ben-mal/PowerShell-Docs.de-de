---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/suspend-service?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Suspend-Service
ms.openlocfilehash: 6e9fd5dd7a5736ef95976cb5195dd1d210d81651
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212239"
---
# <span data-ttu-id="037d1-103">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="037d1-103">Suspend-Service</span></span>

## <span data-ttu-id="037d1-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="037d1-104">SYNOPSIS</span></span>
<span data-ttu-id="037d1-105">Hält ausgeführte Dienste an.</span><span class="sxs-lookup"><span data-stu-id="037d1-105">Suspends (pauses) one or more running services.</span></span>

## <span data-ttu-id="037d1-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="037d1-106">SYNTAX</span></span>

### <span data-ttu-id="037d1-107">Inputobject (Standard)</span><span class="sxs-lookup"><span data-stu-id="037d1-107">InputObject (Default)</span></span>

```
Suspend-Service [-InputObject] <ServiceController[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="037d1-108">Standard</span><span class="sxs-lookup"><span data-stu-id="037d1-108">Default</span></span>

```
Suspend-Service [-Name] <String[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="037d1-109">DisplayName</span><span class="sxs-lookup"><span data-stu-id="037d1-109">DisplayName</span></span>

```
Suspend-Service [-PassThru] -DisplayName <String[]> [-Include <String[]>] [-Exclude <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="037d1-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="037d1-110">DESCRIPTION</span></span>

<span data-ttu-id="037d1-111">Das **Suspend-Service-** Cmdlet sendet für jeden der angegebenen Dienste eine Suspend-Nachricht an den Windows-Dienst Controller.</span><span class="sxs-lookup"><span data-stu-id="037d1-111">The **Suspend-Service** cmdlet sends a suspend message to the Windows Service Controller for each of the specified services.</span></span>
<span data-ttu-id="037d1-112">Obwohl der Dienst angehalten wird, wird der Dienst weiterhin ausgeführt, die Aktion wird jedoch bis zum fortsetzen angehalten, wie z. b. durch das Resume-Service Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="037d1-112">While suspended, the service is still running, but its action is stopped until resumed, such as by usingthe Resume-Service cmdlet.</span></span>
<span data-ttu-id="037d1-113">Sie können die Dienste mit ihren Dienstnamen oder anzeigen Amen angeben, oder Sie können mit dem *Inputobject* -Parameter ein Dienst Objekt übergeben, das die anzuhaltenden Dienste darstellt.</span><span class="sxs-lookup"><span data-stu-id="037d1-113">You can specify the services by their service names or display names, or you can use the *InputObject* parameter to pass a service object that represents the services that you want to suspend.</span></span>

## <span data-ttu-id="037d1-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="037d1-114">EXAMPLES</span></span>

### <span data-ttu-id="037d1-115">Beispiel 1: aussetzen eines Dienstanbieter</span><span class="sxs-lookup"><span data-stu-id="037d1-115">Example 1: Suspend a service</span></span>

```
PS C:\> Suspend-Service -DisplayName "Telnet"
```

<span data-ttu-id="037d1-116">Mit diesem Befehl wird der Telnet-Dienst (Tlntsvr) auf dem lokalen Computer angehalten.</span><span class="sxs-lookup"><span data-stu-id="037d1-116">This command suspends the Telnet service (Tlntsvr) service on the local computer.</span></span>

### <span data-ttu-id="037d1-117">Beispiel 2: anzeigen, was passiert, wenn Sie Dienste aussetzen</span><span class="sxs-lookup"><span data-stu-id="037d1-117">Example 2: Display what would happen if you suspend services</span></span>

```
PS C:\> Suspend-Service -Name lanman* -WhatIf
```

<span data-ttu-id="037d1-118">Dieser Befehl gibt Aufschluss darüber, was passieren würde, wenn Sie die Dienste mit einem Dienstnamen angehalten haben, der mit LanMan beginnt.</span><span class="sxs-lookup"><span data-stu-id="037d1-118">This command tells what would happen if you suspended the services that have a service name that starts with lanman.</span></span>
<span data-ttu-id="037d1-119">Führen Sie den Befehl ohne den *WhatIf* -Parameter erneut aus, um die Dienste anzuhalten.</span><span class="sxs-lookup"><span data-stu-id="037d1-119">To suspend the services, rerun the command without the *WhatIf* parameter.</span></span>

### <span data-ttu-id="037d1-120">Beispiel 3: Get und Suspend a Service</span><span class="sxs-lookup"><span data-stu-id="037d1-120">Example 3: Get and suspend a service</span></span>

```
PS C:\> Get-Service schedule | Suspend-Service
```

<span data-ttu-id="037d1-121">Dieser Befehl verwendet das **Get-Service-** Cmdlet, um ein Objekt zu erhalten, das den Taskplaner (Schedule)-Dienst auf dem Computer darstellt.</span><span class="sxs-lookup"><span data-stu-id="037d1-121">This command uses the **Get-Service** cmdlet to get an object that represents the Task Scheduler (Schedule) service on the computer.</span></span>
<span data-ttu-id="037d1-122">Der Pipeline Operator (|) übergibt das Ergebnis an **Suspend-Service** , wodurch der Dienst angehalten wird.</span><span class="sxs-lookup"><span data-stu-id="037d1-122">The pipeline operator (|) passes the result to **Suspend-Service** , which suspends the service.</span></span>

### <span data-ttu-id="037d1-123">Beispiel 4: aussetzen aller Dienste, die angehalten werden können</span><span class="sxs-lookup"><span data-stu-id="037d1-123">Example 4: Suspend all services that can be suspended</span></span>

```
PS C:\> Get-Service | Where-Object {$_.CanPauseAndContinue -eq "True"} | Suspend-Service -Confirm
```

<span data-ttu-id="037d1-124">Mit diesem Befehl werden alle Dienste auf dem Computer angehalten, die angehalten werden können.</span><span class="sxs-lookup"><span data-stu-id="037d1-124">This command suspends all of the services on the computer that can be suspended.</span></span>
<span data-ttu-id="037d1-125">Er verwendet **Get-Service** , um Objekte zu erhalten, die die Dienste auf dem Computer darstellen.</span><span class="sxs-lookup"><span data-stu-id="037d1-125">It uses **Get-Service** to get objects that represent the services on the computer.</span></span>
<span data-ttu-id="037d1-126">Der Pipeline Operator übergibt die Ergebnisse an das Cmdlet "Where-Object", das nur die Dienste auswählt, die den Wert "$true" für die **canpaustiandcontinue** -Eigenschaft aufweisen.</span><span class="sxs-lookup"><span data-stu-id="037d1-126">The pipeline operator passes the results to the Where-Object cmdlet, which selects only the services that have a value of $True for the **CanPauseAndContinue** property.</span></span>
<span data-ttu-id="037d1-127">Ein weiterer Pipeline Operator übergibt die Ergebnisse an **Suspend-Service** .</span><span class="sxs-lookup"><span data-stu-id="037d1-127">Another pipeline operator passes the results to **Suspend-Service** .</span></span>
<span data-ttu-id="037d1-128">Mit dem *Confirm* -Parameter werden Sie vor dem Anhalten der einzelnen Dienste zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="037d1-128">The *Confirm* parameter prompts you for confirmation before suspending each of the services.</span></span>

## <span data-ttu-id="037d1-129">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="037d1-129">PARAMETERS</span></span>

### <span data-ttu-id="037d1-130">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="037d1-130">-DisplayName</span></span>

<span data-ttu-id="037d1-131">Gibt die Anzeigenamen der anzuhaltenden Dienste an.</span><span class="sxs-lookup"><span data-stu-id="037d1-131">Specifies the display names of the services to be suspended.</span></span>
<span data-ttu-id="037d1-132">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="037d1-132">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="037d1-133">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="037d1-133">-Exclude</span></span>

<span data-ttu-id="037d1-134">Gibt Dienste an, die aus den angegebenen Diensten ausgelassen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="037d1-134">Specifies services to omit from the specified services.</span></span>
<span data-ttu-id="037d1-135">Der Wert dieses Parameters qualifiziert den *Name* -Parameter.</span><span class="sxs-lookup"><span data-stu-id="037d1-135">The value of this parameter qualifies the *Name* parameter.</span></span>
<span data-ttu-id="037d1-136">Geben Sie ein Namenselement oder -muster wie %%amp;quot;s\*%%amp;quot; ein.</span><span class="sxs-lookup"><span data-stu-id="037d1-136">Enter a name element or pattern, such as "s\*".</span></span>
<span data-ttu-id="037d1-137">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="037d1-137">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="037d1-138">-Include</span><span class="sxs-lookup"><span data-stu-id="037d1-138">-Include</span></span>

<span data-ttu-id="037d1-139">Gibt Dienste zum Aussetzen an.</span><span class="sxs-lookup"><span data-stu-id="037d1-139">Specifies services to suspend.</span></span>
<span data-ttu-id="037d1-140">Der Wert dieses Parameters qualifiziert den *Name* -Parameter.</span><span class="sxs-lookup"><span data-stu-id="037d1-140">The value of this parameter qualifies the *Name* parameter.</span></span>
<span data-ttu-id="037d1-141">Geben Sie ein Namenselement oder -muster wie %%amp;quot;s\*%%amp;quot; ein.</span><span class="sxs-lookup"><span data-stu-id="037d1-141">Enter a name element or pattern, such as "s\*".</span></span>
<span data-ttu-id="037d1-142">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="037d1-142">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="037d1-143">-InputObject</span><span class="sxs-lookup"><span data-stu-id="037d1-143">-InputObject</span></span>

<span data-ttu-id="037d1-144">Gibt **ServiceController** -Objekte an, die die anzuhaltenden Dienste darstellen.</span><span class="sxs-lookup"><span data-stu-id="037d1-144">Specifies **ServiceController** objects that represent the services to suspend.</span></span>
<span data-ttu-id="037d1-145">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="037d1-145">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="037d1-146">-Name</span><span class="sxs-lookup"><span data-stu-id="037d1-146">-Name</span></span>

<span data-ttu-id="037d1-147">Gibt die Dienstnamen der anzuhaltenden Dienste an.</span><span class="sxs-lookup"><span data-stu-id="037d1-147">Specifies the service names of the services to suspend.</span></span>
<span data-ttu-id="037d1-148">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="037d1-148">Wildcard characters are permitted.</span></span>

<span data-ttu-id="037d1-149">Der Parametername ist optional.</span><span class="sxs-lookup"><span data-stu-id="037d1-149">The parameter name is optional.</span></span>
<span data-ttu-id="037d1-150">Sie können " *Name* " oder den zugehörigen Alias " *Service* Name" verwenden, oder Sie können den Parameternamen weglassen.</span><span class="sxs-lookup"><span data-stu-id="037d1-150">You can use *Name* or its alias, *ServiceName* , or you can omit the parameter name.</span></span>

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

### <span data-ttu-id="037d1-151">-PassThru</span><span class="sxs-lookup"><span data-stu-id="037d1-151">-PassThru</span></span>

<span data-ttu-id="037d1-152">Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="037d1-152">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="037d1-153">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="037d1-153">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="037d1-154">-Confirm</span><span class="sxs-lookup"><span data-stu-id="037d1-154">-Confirm</span></span>

<span data-ttu-id="037d1-155">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="037d1-155">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="037d1-156">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="037d1-156">-WhatIf</span></span>

<span data-ttu-id="037d1-157">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="037d1-157">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="037d1-158">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="037d1-158">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="037d1-159">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="037d1-159">CommonParameters</span></span>

<span data-ttu-id="037d1-160">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="037d1-160">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="037d1-161">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="037d1-161">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="037d1-162">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="037d1-162">INPUTS</span></span>

### <span data-ttu-id="037d1-163">System. ServiceProcess. ServiceController, System. String</span><span class="sxs-lookup"><span data-stu-id="037d1-163">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="037d1-164">Sie können ein Dienst Objekt oder eine Zeichenfolge, die einen Dienstnamen enthält, über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="037d1-164">You can pipe a service object or a string that contains a service name to this cmdlet.</span></span>

## <span data-ttu-id="037d1-165">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="037d1-165">OUTPUTS</span></span>

### <span data-ttu-id="037d1-166">Keine, System. ServiceProcess. ServiceController</span><span class="sxs-lookup"><span data-stu-id="037d1-166">None, System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="037d1-167">Dieses Cmdlet generiert ein **System. ServiceProcess. ServiceController** -Objekt, das den Dienst darstellt, wenn Sie den *passthru* -Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="037d1-167">This cmdlet generates a **System.ServiceProcess.ServiceController** object that represents the service, if you specify the *PassThru* parameter.</span></span>
<span data-ttu-id="037d1-168">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="037d1-168">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="037d1-169">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="037d1-169">NOTES</span></span>

* <span data-ttu-id="037d1-170">**Suspend-Service** kann Dienste nur steuern, wenn der aktuelle Benutzer über die entsprechende Berechtigung verfügt.</span><span class="sxs-lookup"><span data-stu-id="037d1-170">**Suspend-Service** can control services only when the current user has permission to do this.</span></span> <span data-ttu-id="037d1-171">Wenn ein Befehl nicht ordnungsgemäß verarbeitet wird, verfügen Sie u. U. nicht über die erforderlichen Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="037d1-171">If a command does not work correctly, you might not have the required permissions.</span></span>
* <span data-ttu-id="037d1-172">**Suspend-Service** kann nur Dienste aussetzen, die angehalten und fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="037d1-172">**Suspend-Service** can suspend only services that support being suspended and resumed.</span></span> <span data-ttu-id="037d1-173">Um zu ermitteln, ob ein bestimmter Dienst angehalten werden kann, verwenden Sie das Get-Service-Cmdlet mit der **canpauabandcontinue** -Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="037d1-173">To determine whether a particular service can be suspended, use the Get-Service cmdlet together with the **CanPauseAndContinue** property.</span></span> <span data-ttu-id="037d1-174">Beispiel: `Get-Service wmi | Format-List Name, CanPauseAndContinue`.</span><span class="sxs-lookup"><span data-stu-id="037d1-174">For example, `Get-Service wmi | Format-List Name, CanPauseAndContinue`.</span></span> <span data-ttu-id="037d1-175">Wenn Sie alle Dienste auf dem Computer ermitteln möchten, die angehalten werden können, geben Sie ein `Get-Service | Where-Object {$_.CanPauseAndContinue -eq $true}` .</span><span class="sxs-lookup"><span data-stu-id="037d1-175">To find all services on the computer that can be suspended, type `Get-Service | Where-Object {$_.CanPauseAndContinue -eq $true}`.</span></span>
* <span data-ttu-id="037d1-176">Geben **Sie Get-Service** ein, um die Dienstnamen und anzeigen amen der Dienste auf Ihrem System zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="037d1-176">To find the service names and display names of the services on your system, type **Get-Service** .</span></span> <span data-ttu-id="037d1-177">Die Dienstnamen werden in der Spalte **Name** angezeigt, und die anzeigen Amen werden in der Spalte **Display Name** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="037d1-177">The service names appear in the **Name** column, and the display names appear in the **DisplayName** column.</span></span>

## <span data-ttu-id="037d1-178">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="037d1-178">RELATED LINKS</span></span>

[<span data-ttu-id="037d1-179">Get-Service</span><span class="sxs-lookup"><span data-stu-id="037d1-179">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="037d1-180">New-Service</span><span class="sxs-lookup"><span data-stu-id="037d1-180">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="037d1-181">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="037d1-181">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="037d1-182">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="037d1-182">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="037d1-183">Set-Service</span><span class="sxs-lookup"><span data-stu-id="037d1-183">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="037d1-184">Start-Service</span><span class="sxs-lookup"><span data-stu-id="037d1-184">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="037d1-185">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="037d1-185">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="037d1-186">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="037d1-186">Remove-Service</span></span>](Remove-Service.md)
