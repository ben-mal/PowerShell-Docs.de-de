---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/resume-service?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Resume-Service
ms.openlocfilehash: 2d627625dec5afe6397a3fb346716adfd3fdb31c
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2020
ms.locfileid: "94342908"
---
# <span data-ttu-id="dd306-103">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="dd306-103">Resume-Service</span></span>

## <span data-ttu-id="dd306-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="dd306-104">SYNOPSIS</span></span>
<span data-ttu-id="dd306-105">Setzt angehaltene (unterbrochene) Dienste fort.</span><span class="sxs-lookup"><span data-stu-id="dd306-105">Resumes one or more suspended (paused) services.</span></span>

## <span data-ttu-id="dd306-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="dd306-106">SYNTAX</span></span>

### <span data-ttu-id="dd306-107">Inputobject (Standard)</span><span class="sxs-lookup"><span data-stu-id="dd306-107">InputObject (Default)</span></span>

```
Resume-Service [-InputObject] <ServiceController[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="dd306-108">Standard</span><span class="sxs-lookup"><span data-stu-id="dd306-108">Default</span></span>

```
Resume-Service [-Name] <String[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="dd306-109">DisplayName</span><span class="sxs-lookup"><span data-stu-id="dd306-109">DisplayName</span></span>

```
Resume-Service [-PassThru] -DisplayName <String[]> [-Include <String[]>] [-Exclude <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="dd306-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="dd306-110">DESCRIPTION</span></span>

<span data-ttu-id="dd306-111">Das- `Resume-Service` Cmdlet sendet für jeden der angegebenen Dienste eine Fortsetzungs Meldung an den Windows-Dienst Controller.</span><span class="sxs-lookup"><span data-stu-id="dd306-111">The `Resume-Service` cmdlet sends a resume message to the Windows Service Controller for each of the specified services.</span></span> <span data-ttu-id="dd306-112">Wenn ein Dienst angehalten wird, wird er fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="dd306-112">If a service is suspended, it resumes.</span></span> <span data-ttu-id="dd306-113">Wenn er gerade ausgeführt wird, wird die Meldung ignoriert.</span><span class="sxs-lookup"><span data-stu-id="dd306-113">If it is currently running, the message is ignored.</span></span> <span data-ttu-id="dd306-114">Sie können die Dienste mit ihren Dienstnamen oder anzeigen Amen angeben, oder Sie können mit dem **Inputobject** -Parameter ein Dienst Objekt übergeben, das die wiederherzustellenden Dienste darstellt.</span><span class="sxs-lookup"><span data-stu-id="dd306-114">You can specify the services by their service names or display names, or you can use the **InputObject** parameter to pass a service object that represents the services that you want to resume.</span></span>

## <span data-ttu-id="dd306-115">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="dd306-115">EXAMPLES</span></span>

### <span data-ttu-id="dd306-116">Beispiel 1: Fortsetzen eines Dienstanbieter auf dem lokalen Computer</span><span class="sxs-lookup"><span data-stu-id="dd306-116">Example 1: Resume a service on the local computer</span></span>

```
PS C:\> Resume-Service "sens"
```

<span data-ttu-id="dd306-117">Mit diesem Befehl wird der System Ereignis Benachrichtigungsdienst auf dem lokalen Computer fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="dd306-117">This command resumes the System Event Notification service on the local computer.</span></span> <span data-ttu-id="dd306-118">Der Dienst Name wird im Befehl von Sens dargestellt.</span><span class="sxs-lookup"><span data-stu-id="dd306-118">The service name is represented in the command by sens.</span></span> <span data-ttu-id="dd306-119">Der Befehl verwendet den **Name** -Parameter, um den Dienstnamen des Dienstanbieter anzugeben, aber der Befehl lässt den Parameternamen aus, da der Parameter Name optional ist.</span><span class="sxs-lookup"><span data-stu-id="dd306-119">The command uses the **Name** parameter to specify the service name of the service, but the command omits the parameter name because the parameter name is optional.</span></span>

### <span data-ttu-id="dd306-120">Beispiel 2: Fortsetzen aller angehaltenen Dienste</span><span class="sxs-lookup"><span data-stu-id="dd306-120">Example 2: Resume all suspended services</span></span>

```
PS C:\> Get-Service | Where-Object {$_.Status -eq "Paused"} | Resume-Service
```

<span data-ttu-id="dd306-121">Mit diesem Befehl werden alle angehaltenen Dienste auf dem Computer fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="dd306-121">This command resumes all of the suspended services on the computer.</span></span> <span data-ttu-id="dd306-122">Der `Get-Service` Cmdlet-Befehl ruft alle Dienste auf dem Computer ab.</span><span class="sxs-lookup"><span data-stu-id="dd306-122">The `Get-Service` cmdlet command gets all of the services on the computer.</span></span> <span data-ttu-id="dd306-123">Der Pipeline Operator ( `|` ) übergibt die Ergebnisse an das `Where-Object` Cmdlet, das die Dienste auswählt, deren **Status** -Eigenschaft angehalten ist.</span><span class="sxs-lookup"><span data-stu-id="dd306-123">The pipeline operator (`|`) passes the results to the `Where-Object` cmdlet, which selects the services that have a **Status** property of Paused.</span></span> <span data-ttu-id="dd306-124">Der nächste Pipeline Operator sendet die Ergebnisse an `Resume-Service` , wodurch die angehaltenen Dienste fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="dd306-124">The next pipeline operator sends the results to `Resume-Service`, which resumes the paused services.</span></span>

<span data-ttu-id="dd306-125">In der Praxis verwenden Sie den **WhatIf** -Parameter, um die Auswirkung des Befehls zu ermitteln, bevor Sie ihn ausführen.</span><span class="sxs-lookup"><span data-stu-id="dd306-125">In practice, you would use the **WhatIf** parameter to determine the effect of the command before you run it.</span></span>

## <span data-ttu-id="dd306-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="dd306-126">PARAMETERS</span></span>

### <span data-ttu-id="dd306-127">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="dd306-127">-DisplayName</span></span>

<span data-ttu-id="dd306-128">Gibt die Anzeigenamen der fortzusetzenden Dienste an.</span><span class="sxs-lookup"><span data-stu-id="dd306-128">Specifies the display names of the services to be resumed.</span></span>
<span data-ttu-id="dd306-129">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="dd306-129">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="dd306-130">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="dd306-130">-Exclude</span></span>

<span data-ttu-id="dd306-131">Gibt die Dienste an, die von diesem Cmdlet ausgelassen werden.</span><span class="sxs-lookup"><span data-stu-id="dd306-131">Specifies services that this cmdlet omits.</span></span> <span data-ttu-id="dd306-132">Der Wert dieses Parameters qualifiziert den **Name** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="dd306-132">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="dd306-133">Geben Sie ein Namenselement oder-Muster ein, z. b. s \*.</span><span class="sxs-lookup"><span data-stu-id="dd306-133">Enter a name element or pattern, such as s\*.</span></span> <span data-ttu-id="dd306-134">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="dd306-134">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="dd306-135">-Include</span><span class="sxs-lookup"><span data-stu-id="dd306-135">-Include</span></span>

<span data-ttu-id="dd306-136">Gibt Dienste zum Fortsetzen an.</span><span class="sxs-lookup"><span data-stu-id="dd306-136">Specifies services to resume.</span></span> <span data-ttu-id="dd306-137">Der Wert dieses Parameters qualifiziert den **Name** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="dd306-137">The value of this parameter qualifies **Name** parameter.</span></span> <span data-ttu-id="dd306-138">Geben Sie ein Namenselement oder-Muster ein, z. b. s \*.</span><span class="sxs-lookup"><span data-stu-id="dd306-138">Enter a name element or pattern, such as s\*.</span></span> <span data-ttu-id="dd306-139">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="dd306-139">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="dd306-140">-InputObject</span><span class="sxs-lookup"><span data-stu-id="dd306-140">-InputObject</span></span>

<span data-ttu-id="dd306-141">Gibt **ServiceController** -Objekte an, die die fort zusetzenden Dienste darstellen.</span><span class="sxs-lookup"><span data-stu-id="dd306-141">Specifies **ServiceController** objects that represent the services to resumed.</span></span> <span data-ttu-id="dd306-142">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="dd306-142">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="dd306-143">-Name</span><span class="sxs-lookup"><span data-stu-id="dd306-143">-Name</span></span>

<span data-ttu-id="dd306-144">Gibt die Dienstnamen der fortzusetzenden Dienste an.</span><span class="sxs-lookup"><span data-stu-id="dd306-144">Specifies the service names of the services to be resumed.</span></span>

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

### <span data-ttu-id="dd306-145">-PassThru</span><span class="sxs-lookup"><span data-stu-id="dd306-145">-PassThru</span></span>

<span data-ttu-id="dd306-146">Gibt ein Objekt zurück, das den Dienst darstellt.</span><span class="sxs-lookup"><span data-stu-id="dd306-146">Returns an object that represents the service.</span></span> <span data-ttu-id="dd306-147">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="dd306-147">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="dd306-148">-Confirm</span><span class="sxs-lookup"><span data-stu-id="dd306-148">-Confirm</span></span>

<span data-ttu-id="dd306-149">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="dd306-149">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="dd306-150">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="dd306-150">-WhatIf</span></span>

<span data-ttu-id="dd306-151">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="dd306-151">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="dd306-152">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="dd306-152">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="dd306-153">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="dd306-153">CommonParameters</span></span>

<span data-ttu-id="dd306-154">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="dd306-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="dd306-155">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="dd306-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="dd306-156">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="dd306-156">INPUTS</span></span>

### <span data-ttu-id="dd306-157">System. ServiceProcess. ServiceController, System. String</span><span class="sxs-lookup"><span data-stu-id="dd306-157">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="dd306-158">Sie können ein Dienst Objekt oder eine Zeichenfolge, die einen Dienstnamen enthält, über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="dd306-158">You can pipe a service object or a string that contains a service name to this cmdlet.</span></span>

## <span data-ttu-id="dd306-159">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="dd306-159">OUTPUTS</span></span>

### <span data-ttu-id="dd306-160">Keine, System. ServiceProcess. ServiceController</span><span class="sxs-lookup"><span data-stu-id="dd306-160">None, System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="dd306-161">Dieses Cmdlet generiert ein **System. ServiceProcess. ServiceController** -Objekt, das den fortgesetzten Dienst darstellt, wenn Sie den **passthru** -Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="dd306-161">This cmdlet generates a **System.ServiceProcess.ServiceController** object that represents the resumed service, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="dd306-162">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="dd306-162">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="dd306-163">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="dd306-163">NOTES</span></span>

<span data-ttu-id="dd306-164">Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="dd306-164">This cmdlet is only available on Windows platforms.</span></span>

- <span data-ttu-id="dd306-165">Der Status von Diensten, die angehalten wurden, wurde angehalten.</span><span class="sxs-lookup"><span data-stu-id="dd306-165">The status of services that have been suspended is Paused.</span></span> <span data-ttu-id="dd306-166">Wenn Dienste fortgesetzt werden, lautet Ihr Status wird ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="dd306-166">When services are resumed, their status is Running.</span></span>
- <span data-ttu-id="dd306-167">`Resume-Service` Dienste können nur von gesteuert werden, wenn der aktuelle Benutzer über die entsprechende Berechtigung verfügt.</span><span class="sxs-lookup"><span data-stu-id="dd306-167">`Resume-Service` can control services only when the current user has permission to do this.</span></span> <span data-ttu-id="dd306-168">Wenn ein Befehl nicht ordnungsgemäß verarbeitet wird, verfügen Sie u. U. nicht über die erforderlichen Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="dd306-168">If a command does not work correctly, you might not have the required permissions.</span></span>
- <span data-ttu-id="dd306-169">Geben Sie ein, um die Dienstnamen und anzeigen amen der Dienste auf dem System zu suchen `Get-Service` .</span><span class="sxs-lookup"><span data-stu-id="dd306-169">To find the service names and display names of the services on your system, type `Get-Service`.</span></span>
  <span data-ttu-id="dd306-170">Die Dienstnamen werden in der Spalte **Name** angezeigt, und die anzeigen Amen werden in der Spalte **Display Name** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dd306-170">The service names appear in the **Name** column, and the display names appear in the **DisplayName** column.</span></span>

## <span data-ttu-id="dd306-171">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="dd306-171">RELATED LINKS</span></span>

[<span data-ttu-id="dd306-172">Get-Service</span><span class="sxs-lookup"><span data-stu-id="dd306-172">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="dd306-173">New-Service</span><span class="sxs-lookup"><span data-stu-id="dd306-173">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="dd306-174">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="dd306-174">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="dd306-175">Set-Service</span><span class="sxs-lookup"><span data-stu-id="dd306-175">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="dd306-176">Start-Service</span><span class="sxs-lookup"><span data-stu-id="dd306-176">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="dd306-177">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="dd306-177">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="dd306-178">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="dd306-178">Suspend-Service</span></span>](Suspend-Service.md)

[<span data-ttu-id="dd306-179">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="dd306-179">Remove-Service</span></span>](Remove-Service.md)
