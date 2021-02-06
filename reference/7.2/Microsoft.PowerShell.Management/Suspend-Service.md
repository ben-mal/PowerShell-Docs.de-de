---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/suspend-service?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Suspend-Service
ms.openlocfilehash: 9515f524df38813817b3fefd1437a3e2df296392
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601314"
---
# <span data-ttu-id="7e29d-102">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="7e29d-102">Suspend-Service</span></span>

## <span data-ttu-id="7e29d-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="7e29d-103">SYNOPSIS</span></span>
<span data-ttu-id="7e29d-104">Hält ausgeführte Dienste an.</span><span class="sxs-lookup"><span data-stu-id="7e29d-104">Suspends (pauses) one or more running services.</span></span>

## <span data-ttu-id="7e29d-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7e29d-105">SYNTAX</span></span>

### <span data-ttu-id="7e29d-106">Inputobject (Standard)</span><span class="sxs-lookup"><span data-stu-id="7e29d-106">InputObject (Default)</span></span>

```
Suspend-Service [-InputObject] <ServiceController[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="7e29d-107">Standard</span><span class="sxs-lookup"><span data-stu-id="7e29d-107">Default</span></span>

```
Suspend-Service [-Name] <String[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="7e29d-108">DisplayName</span><span class="sxs-lookup"><span data-stu-id="7e29d-108">DisplayName</span></span>

```
Suspend-Service [-PassThru] -DisplayName <String[]> [-Include <String[]>] [-Exclude <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="7e29d-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7e29d-109">DESCRIPTION</span></span>

<span data-ttu-id="7e29d-110">Das- `Suspend-Service` Cmdlet sendet eine Suspend-Nachricht für jeden der angegebenen Dienste an den Windows-Dienst Controller.</span><span class="sxs-lookup"><span data-stu-id="7e29d-110">The `Suspend-Service` cmdlet sends a suspend message to the Windows Service Controller for each of the specified services.</span></span> <span data-ttu-id="7e29d-111">Obwohl der Dienst angehalten wird, wird er weiterhin ausgeführt, die Aktion wird jedoch bis zum fortsetzen angehalten, wie z. b. durch das `Resume-Service` Verwenden des Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="7e29d-111">While suspended, the service is still running, but its action is stopped until resumed, such as by usingthe `Resume-Service` cmdlet.</span></span> <span data-ttu-id="7e29d-112">Sie können die Dienste mit ihren Dienstnamen oder anzeigen Amen angeben, oder Sie können mit dem **Inputobject** -Parameter ein Dienst Objekt übergeben, das die anzuhaltenden Dienste darstellt.</span><span class="sxs-lookup"><span data-stu-id="7e29d-112">You can specify the services by their service names or display names, or you can use the **InputObject** parameter to pass a service object that represents the services that you want to suspend.</span></span>

## <span data-ttu-id="7e29d-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="7e29d-113">EXAMPLES</span></span>

### <span data-ttu-id="7e29d-114">Beispiel 1: aussetzen eines Dienstanbieter</span><span class="sxs-lookup"><span data-stu-id="7e29d-114">Example 1: Suspend a service</span></span>

```
PS C:\> Suspend-Service -DisplayName "Telnet"
```

<span data-ttu-id="7e29d-115">Mit diesem Befehl wird der Telnet-Dienst (Tlntsvr) auf dem lokalen Computer angehalten.</span><span class="sxs-lookup"><span data-stu-id="7e29d-115">This command suspends the Telnet service (Tlntsvr) service on the local computer.</span></span>

### <span data-ttu-id="7e29d-116">Beispiel 2: anzeigen, was passiert, wenn Sie Dienste aussetzen</span><span class="sxs-lookup"><span data-stu-id="7e29d-116">Example 2: Display what would happen if you suspend services</span></span>

```
PS C:\> Suspend-Service -Name lanman* -WhatIf
```

<span data-ttu-id="7e29d-117">Dieser Befehl gibt Aufschluss darüber, was passieren würde, wenn Sie die Dienste mit einem Dienstnamen angehalten haben, der mit LanMan beginnt.</span><span class="sxs-lookup"><span data-stu-id="7e29d-117">This command tells what would happen if you suspended the services that have a service name that starts with lanman.</span></span> <span data-ttu-id="7e29d-118">Führen Sie den Befehl ohne den **WhatIf** -Parameter erneut aus, um die Dienste anzuhalten.</span><span class="sxs-lookup"><span data-stu-id="7e29d-118">To suspend the services, rerun the command without the **WhatIf** parameter.</span></span>

### <span data-ttu-id="7e29d-119">Beispiel 3: Get und Suspend a Service</span><span class="sxs-lookup"><span data-stu-id="7e29d-119">Example 3: Get and suspend a service</span></span>

```
PS C:\> Get-Service schedule | Suspend-Service
```

<span data-ttu-id="7e29d-120">Dieser Befehl verwendet das `Get-Service` Cmdlet, um ein Objekt zu erhalten, das den Taskplaner (Schedule)-Dienst auf dem Computer darstellt.</span><span class="sxs-lookup"><span data-stu-id="7e29d-120">This command uses the `Get-Service` cmdlet to get an object that represents the Task Scheduler (Schedule) service on the computer.</span></span> <span data-ttu-id="7e29d-121">Der Pipeline Operator ( `|` ) übergibt das Ergebnis an `Suspend-Service` , wodurch der Dienst angehalten wird.</span><span class="sxs-lookup"><span data-stu-id="7e29d-121">The pipeline operator (`|`) passes the result to `Suspend-Service`, which suspends the service.</span></span>

### <span data-ttu-id="7e29d-122">Beispiel 4: aussetzen aller Dienste, die angehalten werden können</span><span class="sxs-lookup"><span data-stu-id="7e29d-122">Example 4: Suspend all services that can be suspended</span></span>

```
PS C:\> Get-Service | Where-Object {$_.CanPauseAndContinue -eq "True"} | Suspend-Service -Confirm
```

<span data-ttu-id="7e29d-123">Mit diesem Befehl werden alle Dienste auf dem Computer angehalten, die angehalten werden können.</span><span class="sxs-lookup"><span data-stu-id="7e29d-123">This command suspends all of the services on the computer that can be suspended.</span></span> <span data-ttu-id="7e29d-124">Es verwendet `Get-Service` , um Objekte zu erhalten, die die Dienste auf dem Computer darstellen.</span><span class="sxs-lookup"><span data-stu-id="7e29d-124">It uses `Get-Service` to get objects that represent the services on the computer.</span></span> <span data-ttu-id="7e29d-125">Der Pipeline Operator übergibt die Ergebnisse an das `Where-Object` Cmdlet, das nur die Dienste auswählt, die den Wert `$True` für die **canpaustiandcontinue** -Eigenschaft aufweisen.</span><span class="sxs-lookup"><span data-stu-id="7e29d-125">The pipeline operator passes the results to the `Where-Object` cmdlet, which selects only the services that have a value of `$True` for the **CanPauseAndContinue** property.</span></span> <span data-ttu-id="7e29d-126">Ein weiterer Pipeline Operator übergibt die Ergebnisse an `Suspend-Service` .</span><span class="sxs-lookup"><span data-stu-id="7e29d-126">Another pipeline operator passes the results to `Suspend-Service`.</span></span> <span data-ttu-id="7e29d-127">Mit dem **Confirm** -Parameter werden Sie vor dem Anhalten der einzelnen Dienste zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="7e29d-127">The **Confirm** parameter prompts you for confirmation before suspending each of the services.</span></span>

## <span data-ttu-id="7e29d-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7e29d-128">PARAMETERS</span></span>

### <span data-ttu-id="7e29d-129">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="7e29d-129">-DisplayName</span></span>

<span data-ttu-id="7e29d-130">Gibt die Anzeigenamen der anzuhaltenden Dienste an.</span><span class="sxs-lookup"><span data-stu-id="7e29d-130">Specifies the display names of the services to be suspended.</span></span> <span data-ttu-id="7e29d-131">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="7e29d-131">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="7e29d-132">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="7e29d-132">-Exclude</span></span>

<span data-ttu-id="7e29d-133">Gibt Dienste an, die aus den angegebenen Diensten ausgelassen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="7e29d-133">Specifies services to omit from the specified services.</span></span> <span data-ttu-id="7e29d-134">Der Wert dieses Parameters qualifiziert den **Name** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="7e29d-134">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="7e29d-135">Geben Sie ein Namenselement oder -muster wie %%amp;quot;s\*%%amp;quot; ein.</span><span class="sxs-lookup"><span data-stu-id="7e29d-135">Enter a name element or pattern, such as "s\*".</span></span> <span data-ttu-id="7e29d-136">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="7e29d-136">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="7e29d-137">-Include</span><span class="sxs-lookup"><span data-stu-id="7e29d-137">-Include</span></span>

<span data-ttu-id="7e29d-138">Gibt Dienste zum Aussetzen an.</span><span class="sxs-lookup"><span data-stu-id="7e29d-138">Specifies services to suspend.</span></span> <span data-ttu-id="7e29d-139">Der Wert dieses Parameters qualifiziert den **Name** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="7e29d-139">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="7e29d-140">Geben Sie ein Namenselement oder -muster wie %%amp;quot;s\*%%amp;quot; ein.</span><span class="sxs-lookup"><span data-stu-id="7e29d-140">Enter a name element or pattern, such as "s\*".</span></span> <span data-ttu-id="7e29d-141">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="7e29d-141">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="7e29d-142">-InputObject</span><span class="sxs-lookup"><span data-stu-id="7e29d-142">-InputObject</span></span>

<span data-ttu-id="7e29d-143">Gibt **ServiceController** -Objekte an, die die anzuhaltenden Dienste darstellen.</span><span class="sxs-lookup"><span data-stu-id="7e29d-143">Specifies **ServiceController** objects that represent the services to suspend.</span></span> <span data-ttu-id="7e29d-144">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="7e29d-144">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="7e29d-145">-Name</span><span class="sxs-lookup"><span data-stu-id="7e29d-145">-Name</span></span>

<span data-ttu-id="7e29d-146">Gibt die Dienstnamen der anzuhaltenden Dienste an.</span><span class="sxs-lookup"><span data-stu-id="7e29d-146">Specifies the service names of the services to suspend.</span></span> <span data-ttu-id="7e29d-147">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="7e29d-147">Wildcard characters are permitted.</span></span>

<span data-ttu-id="7e29d-148">Der Parametername ist optional.</span><span class="sxs-lookup"><span data-stu-id="7e29d-148">The parameter name is optional.</span></span> <span data-ttu-id="7e29d-149">Sie können " **Name** " oder den zugehörigen Alias " **Service** Name" verwenden, oder Sie können den Parameternamen weglassen.</span><span class="sxs-lookup"><span data-stu-id="7e29d-149">You can use **Name** or its alias, **ServiceName**, or you can omit the parameter name.</span></span>

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

### <span data-ttu-id="7e29d-150">-PassThru</span><span class="sxs-lookup"><span data-stu-id="7e29d-150">-PassThru</span></span>

<span data-ttu-id="7e29d-151">Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="7e29d-151">Returns an object representing the item with which you are working.</span></span> <span data-ttu-id="7e29d-152">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="7e29d-152">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="7e29d-153">-Confirm</span><span class="sxs-lookup"><span data-stu-id="7e29d-153">-Confirm</span></span>

<span data-ttu-id="7e29d-154">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="7e29d-154">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="7e29d-155">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="7e29d-155">-WhatIf</span></span>

<span data-ttu-id="7e29d-156">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7e29d-156">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="7e29d-157">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7e29d-157">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="7e29d-158">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="7e29d-158">CommonParameters</span></span>

<span data-ttu-id="7e29d-159">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="7e29d-159">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7e29d-160">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="7e29d-160">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7e29d-161">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="7e29d-161">INPUTS</span></span>

### <span data-ttu-id="7e29d-162">System. ServiceProcess. ServiceController, System. String</span><span class="sxs-lookup"><span data-stu-id="7e29d-162">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="7e29d-163">Sie können ein Dienst Objekt oder eine Zeichenfolge, die einen Dienstnamen enthält, über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="7e29d-163">You can pipe a service object or a string that contains a service name to this cmdlet.</span></span>

## <span data-ttu-id="7e29d-164">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="7e29d-164">OUTPUTS</span></span>

### <span data-ttu-id="7e29d-165">Keine, System. ServiceProcess. ServiceController</span><span class="sxs-lookup"><span data-stu-id="7e29d-165">None, System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="7e29d-166">Dieses Cmdlet generiert ein **System. ServiceProcess. ServiceController** -Objekt, das den Dienst darstellt, wenn Sie den **passthru** -Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="7e29d-166">This cmdlet generates a **System.ServiceProcess.ServiceController** object that represents the service, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="7e29d-167">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="7e29d-167">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="7e29d-168">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="7e29d-168">NOTES</span></span>

<span data-ttu-id="7e29d-169">Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7e29d-169">This cmdlet is only available on Windows platforms.</span></span>

- <span data-ttu-id="7e29d-170">`Suspend-Service` Dienste können nur von gesteuert werden, wenn der aktuelle Benutzer über die entsprechende Berechtigung verfügt.</span><span class="sxs-lookup"><span data-stu-id="7e29d-170">`Suspend-Service` can control services only when the current user has permission to do this.</span></span> <span data-ttu-id="7e29d-171">Wenn ein Befehl nicht ordnungsgemäß verarbeitet wird, verfügen Sie u. U. nicht über die erforderlichen Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="7e29d-171">If a command does not work correctly, you might not have the required permissions.</span></span>
- <span data-ttu-id="7e29d-172">`Suspend-Service` von können nur Dienste angehalten werden, deren Unterstützung angehalten und fortgesetzt</span><span class="sxs-lookup"><span data-stu-id="7e29d-172">`Suspend-Service` can suspend only services that support being suspended and resumed.</span></span> <span data-ttu-id="7e29d-173">Um zu ermitteln, ob ein bestimmter Dienst angehalten werden kann, verwenden Sie das `Get-Service` Cmdlet in Verbindung mit der **canpaumenandcontinue** -Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="7e29d-173">To determine whether a particular service can be suspended, use the `Get-Service` cmdlet together with the **CanPauseAndContinue** property.</span></span> <span data-ttu-id="7e29d-174">Beispiel: `Get-Service wmi | Format-List Name, CanPauseAndContinue`.</span><span class="sxs-lookup"><span data-stu-id="7e29d-174">For example, `Get-Service wmi | Format-List Name, CanPauseAndContinue`.</span></span> <span data-ttu-id="7e29d-175">Wenn Sie alle Dienste auf dem Computer ermitteln möchten, die angehalten werden können, geben Sie ein `Get-Service | Where-Object {$_.CanPauseAndContinue -eq $true}` .</span><span class="sxs-lookup"><span data-stu-id="7e29d-175">To find all services on the computer that can be suspended, type `Get-Service | Where-Object {$_.CanPauseAndContinue -eq $true}`.</span></span>
- <span data-ttu-id="7e29d-176">Geben Sie ein, um die Dienstnamen und anzeigen amen der Dienste auf dem System zu suchen `Get-Service` .</span><span class="sxs-lookup"><span data-stu-id="7e29d-176">To find the service names and display names of the services on your system, type `Get-Service`.</span></span>
  <span data-ttu-id="7e29d-177">Die Dienstnamen werden in der Spalte **Name** angezeigt, und die anzeigen Amen werden in der Spalte **Display Name** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7e29d-177">The service names appear in the **Name** column, and the display names appear in the **DisplayName** column.</span></span>

## <span data-ttu-id="7e29d-178">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="7e29d-178">RELATED LINKS</span></span>

[<span data-ttu-id="7e29d-179">Get-Service</span><span class="sxs-lookup"><span data-stu-id="7e29d-179">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="7e29d-180">New-Service</span><span class="sxs-lookup"><span data-stu-id="7e29d-180">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="7e29d-181">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="7e29d-181">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="7e29d-182">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="7e29d-182">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="7e29d-183">Set-Service</span><span class="sxs-lookup"><span data-stu-id="7e29d-183">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="7e29d-184">Start-Service</span><span class="sxs-lookup"><span data-stu-id="7e29d-184">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="7e29d-185">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="7e29d-185">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="7e29d-186">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="7e29d-186">Remove-Service</span></span>](Remove-Service.md)
