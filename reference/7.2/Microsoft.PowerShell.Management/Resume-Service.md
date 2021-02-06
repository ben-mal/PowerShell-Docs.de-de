---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/resume-service?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Resume-Service
ms.openlocfilehash: 8ce2182117167d93c8f7abd86eeb2c79abdf09c8
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600305"
---
# <span data-ttu-id="b38df-102">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="b38df-102">Resume-Service</span></span>

## <span data-ttu-id="b38df-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="b38df-103">SYNOPSIS</span></span>
<span data-ttu-id="b38df-104">Setzt angehaltene (unterbrochene) Dienste fort.</span><span class="sxs-lookup"><span data-stu-id="b38df-104">Resumes one or more suspended (paused) services.</span></span>

## <span data-ttu-id="b38df-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b38df-105">SYNTAX</span></span>

### <span data-ttu-id="b38df-106">Inputobject (Standard)</span><span class="sxs-lookup"><span data-stu-id="b38df-106">InputObject (Default)</span></span>

```
Resume-Service [-InputObject] <ServiceController[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="b38df-107">Standard</span><span class="sxs-lookup"><span data-stu-id="b38df-107">Default</span></span>

```
Resume-Service [-Name] <String[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="b38df-108">DisplayName</span><span class="sxs-lookup"><span data-stu-id="b38df-108">DisplayName</span></span>

```
Resume-Service [-PassThru] -DisplayName <String[]> [-Include <String[]>] [-Exclude <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="b38df-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b38df-109">DESCRIPTION</span></span>

<span data-ttu-id="b38df-110">Das- `Resume-Service` Cmdlet sendet für jeden der angegebenen Dienste eine Fortsetzungs Meldung an den Windows-Dienst Controller.</span><span class="sxs-lookup"><span data-stu-id="b38df-110">The `Resume-Service` cmdlet sends a resume message to the Windows Service Controller for each of the specified services.</span></span> <span data-ttu-id="b38df-111">Wenn ein Dienst angehalten wird, wird er fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="b38df-111">If a service is suspended, it resumes.</span></span> <span data-ttu-id="b38df-112">Wenn er gerade ausgeführt wird, wird die Meldung ignoriert.</span><span class="sxs-lookup"><span data-stu-id="b38df-112">If it is currently running, the message is ignored.</span></span> <span data-ttu-id="b38df-113">Sie können die Dienste mit ihren Dienstnamen oder anzeigen Amen angeben, oder Sie können mit dem **Inputobject** -Parameter ein Dienst Objekt übergeben, das die wiederherzustellenden Dienste darstellt.</span><span class="sxs-lookup"><span data-stu-id="b38df-113">You can specify the services by their service names or display names, or you can use the **InputObject** parameter to pass a service object that represents the services that you want to resume.</span></span>

## <span data-ttu-id="b38df-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="b38df-114">EXAMPLES</span></span>

### <span data-ttu-id="b38df-115">Beispiel 1: Fortsetzen eines Dienstanbieter auf dem lokalen Computer</span><span class="sxs-lookup"><span data-stu-id="b38df-115">Example 1: Resume a service on the local computer</span></span>

```
PS C:\> Resume-Service "sens"
```

<span data-ttu-id="b38df-116">Mit diesem Befehl wird der System Ereignis Benachrichtigungsdienst auf dem lokalen Computer fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="b38df-116">This command resumes the System Event Notification service on the local computer.</span></span> <span data-ttu-id="b38df-117">Der Dienst Name wird im Befehl von Sens dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b38df-117">The service name is represented in the command by sens.</span></span> <span data-ttu-id="b38df-118">Der Befehl verwendet den **Name** -Parameter, um den Dienstnamen des Dienstanbieter anzugeben, aber der Befehl lässt den Parameternamen aus, da der Parameter Name optional ist.</span><span class="sxs-lookup"><span data-stu-id="b38df-118">The command uses the **Name** parameter to specify the service name of the service, but the command omits the parameter name because the parameter name is optional.</span></span>

### <span data-ttu-id="b38df-119">Beispiel 2: Fortsetzen aller angehaltenen Dienste</span><span class="sxs-lookup"><span data-stu-id="b38df-119">Example 2: Resume all suspended services</span></span>

```
PS C:\> Get-Service | Where-Object {$_.Status -eq "Paused"} | Resume-Service
```

<span data-ttu-id="b38df-120">Mit diesem Befehl werden alle angehaltenen Dienste auf dem Computer fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="b38df-120">This command resumes all of the suspended services on the computer.</span></span> <span data-ttu-id="b38df-121">Der `Get-Service` Cmdlet-Befehl ruft alle Dienste auf dem Computer ab.</span><span class="sxs-lookup"><span data-stu-id="b38df-121">The `Get-Service` cmdlet command gets all of the services on the computer.</span></span> <span data-ttu-id="b38df-122">Der Pipeline Operator ( `|` ) übergibt die Ergebnisse an das `Where-Object` Cmdlet, das die Dienste auswählt, deren **Status** -Eigenschaft angehalten ist.</span><span class="sxs-lookup"><span data-stu-id="b38df-122">The pipeline operator (`|`) passes the results to the `Where-Object` cmdlet, which selects the services that have a **Status** property of Paused.</span></span> <span data-ttu-id="b38df-123">Der nächste Pipeline Operator sendet die Ergebnisse an `Resume-Service` , wodurch die angehaltenen Dienste fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="b38df-123">The next pipeline operator sends the results to `Resume-Service`, which resumes the paused services.</span></span>

<span data-ttu-id="b38df-124">In der Praxis verwenden Sie den **WhatIf** -Parameter, um die Auswirkung des Befehls zu ermitteln, bevor Sie ihn ausführen.</span><span class="sxs-lookup"><span data-stu-id="b38df-124">In practice, you would use the **WhatIf** parameter to determine the effect of the command before you run it.</span></span>

## <span data-ttu-id="b38df-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b38df-125">PARAMETERS</span></span>

### <span data-ttu-id="b38df-126">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="b38df-126">-DisplayName</span></span>

<span data-ttu-id="b38df-127">Gibt die Anzeigenamen der fortzusetzenden Dienste an.</span><span class="sxs-lookup"><span data-stu-id="b38df-127">Specifies the display names of the services to be resumed.</span></span>
<span data-ttu-id="b38df-128">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="b38df-128">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="b38df-129">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="b38df-129">-Exclude</span></span>

<span data-ttu-id="b38df-130">Gibt die Dienste an, die von diesem Cmdlet ausgelassen werden.</span><span class="sxs-lookup"><span data-stu-id="b38df-130">Specifies services that this cmdlet omits.</span></span> <span data-ttu-id="b38df-131">Der Wert dieses Parameters qualifiziert den **Name** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="b38df-131">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="b38df-132">Geben Sie ein Namenselement oder-Muster ein, z. b. s \*.</span><span class="sxs-lookup"><span data-stu-id="b38df-132">Enter a name element or pattern, such as s\*.</span></span> <span data-ttu-id="b38df-133">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="b38df-133">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="b38df-134">-Include</span><span class="sxs-lookup"><span data-stu-id="b38df-134">-Include</span></span>

<span data-ttu-id="b38df-135">Gibt Dienste zum Fortsetzen an.</span><span class="sxs-lookup"><span data-stu-id="b38df-135">Specifies services to resume.</span></span> <span data-ttu-id="b38df-136">Der Wert dieses Parameters qualifiziert den **Name** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="b38df-136">The value of this parameter qualifies **Name** parameter.</span></span> <span data-ttu-id="b38df-137">Geben Sie ein Namenselement oder-Muster ein, z. b. s \*.</span><span class="sxs-lookup"><span data-stu-id="b38df-137">Enter a name element or pattern, such as s\*.</span></span> <span data-ttu-id="b38df-138">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="b38df-138">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="b38df-139">-InputObject</span><span class="sxs-lookup"><span data-stu-id="b38df-139">-InputObject</span></span>

<span data-ttu-id="b38df-140">Gibt **ServiceController** -Objekte an, die die fort zusetzenden Dienste darstellen.</span><span class="sxs-lookup"><span data-stu-id="b38df-140">Specifies **ServiceController** objects that represent the services to resumed.</span></span> <span data-ttu-id="b38df-141">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="b38df-141">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="b38df-142">-Name</span><span class="sxs-lookup"><span data-stu-id="b38df-142">-Name</span></span>

<span data-ttu-id="b38df-143">Gibt die Dienstnamen der fortzusetzenden Dienste an.</span><span class="sxs-lookup"><span data-stu-id="b38df-143">Specifies the service names of the services to be resumed.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases: ServiceName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="b38df-144">-PassThru</span><span class="sxs-lookup"><span data-stu-id="b38df-144">-PassThru</span></span>

<span data-ttu-id="b38df-145">Gibt ein Objekt zurück, das den Dienst darstellt.</span><span class="sxs-lookup"><span data-stu-id="b38df-145">Returns an object that represents the service.</span></span> <span data-ttu-id="b38df-146">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="b38df-146">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="b38df-147">-Confirm</span><span class="sxs-lookup"><span data-stu-id="b38df-147">-Confirm</span></span>

<span data-ttu-id="b38df-148">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="b38df-148">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="b38df-149">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="b38df-149">-WhatIf</span></span>

<span data-ttu-id="b38df-150">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b38df-150">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="b38df-151">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b38df-151">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="b38df-152">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b38df-152">CommonParameters</span></span>

<span data-ttu-id="b38df-153">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b38df-153">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b38df-154">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b38df-154">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b38df-155">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="b38df-155">INPUTS</span></span>

### <span data-ttu-id="b38df-156">System. ServiceProcess. ServiceController, System. String</span><span class="sxs-lookup"><span data-stu-id="b38df-156">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="b38df-157">Sie können ein Dienst Objekt oder eine Zeichenfolge, die einen Dienstnamen enthält, über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="b38df-157">You can pipe a service object or a string that contains a service name to this cmdlet.</span></span>

## <span data-ttu-id="b38df-158">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="b38df-158">OUTPUTS</span></span>

### <span data-ttu-id="b38df-159">Keine, System. ServiceProcess. ServiceController</span><span class="sxs-lookup"><span data-stu-id="b38df-159">None, System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="b38df-160">Dieses Cmdlet generiert ein **System. ServiceProcess. ServiceController** -Objekt, das den fortgesetzten Dienst darstellt, wenn Sie den **passthru** -Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="b38df-160">This cmdlet generates a **System.ServiceProcess.ServiceController** object that represents the resumed service, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="b38df-161">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="b38df-161">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="b38df-162">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="b38df-162">NOTES</span></span>

<span data-ttu-id="b38df-163">Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b38df-163">This cmdlet is only available on Windows platforms.</span></span>

- <span data-ttu-id="b38df-164">Der Status von Diensten, die angehalten wurden, wurde angehalten.</span><span class="sxs-lookup"><span data-stu-id="b38df-164">The status of services that have been suspended is Paused.</span></span> <span data-ttu-id="b38df-165">Wenn Dienste fortgesetzt werden, lautet Ihr Status wird ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b38df-165">When services are resumed, their status is Running.</span></span>
- <span data-ttu-id="b38df-166">`Resume-Service` Dienste können nur von gesteuert werden, wenn der aktuelle Benutzer über die entsprechende Berechtigung verfügt.</span><span class="sxs-lookup"><span data-stu-id="b38df-166">`Resume-Service` can control services only when the current user has permission to do this.</span></span> <span data-ttu-id="b38df-167">Wenn ein Befehl nicht ordnungsgemäß verarbeitet wird, verfügen Sie u. U. nicht über die erforderlichen Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="b38df-167">If a command does not work correctly, you might not have the required permissions.</span></span>
- <span data-ttu-id="b38df-168">Geben Sie ein, um die Dienstnamen und anzeigen amen der Dienste auf dem System zu suchen `Get-Service` .</span><span class="sxs-lookup"><span data-stu-id="b38df-168">To find the service names and display names of the services on your system, type `Get-Service`.</span></span>
  <span data-ttu-id="b38df-169">Die Dienstnamen werden in der Spalte **Name** angezeigt, und die anzeigen Amen werden in der Spalte **Display Name** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b38df-169">The service names appear in the **Name** column, and the display names appear in the **DisplayName** column.</span></span>

## <span data-ttu-id="b38df-170">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="b38df-170">RELATED LINKS</span></span>

[<span data-ttu-id="b38df-171">Get-Service</span><span class="sxs-lookup"><span data-stu-id="b38df-171">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="b38df-172">New-Service</span><span class="sxs-lookup"><span data-stu-id="b38df-172">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="b38df-173">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="b38df-173">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="b38df-174">Set-Service</span><span class="sxs-lookup"><span data-stu-id="b38df-174">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="b38df-175">Start-Service</span><span class="sxs-lookup"><span data-stu-id="b38df-175">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="b38df-176">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="b38df-176">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="b38df-177">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="b38df-177">Suspend-Service</span></span>](Suspend-Service.md)

[<span data-ttu-id="b38df-178">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="b38df-178">Remove-Service</span></span>](Remove-Service.md)
