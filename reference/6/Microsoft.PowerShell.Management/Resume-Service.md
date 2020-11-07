---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/resume-service?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Resume-Service
ms.openlocfilehash: ee44a29c4b657828accc2d8b5e5773b5c1ea6086
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2020
ms.locfileid: "94345152"
---
# <span data-ttu-id="091a1-103">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="091a1-103">Resume-Service</span></span>

## <span data-ttu-id="091a1-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="091a1-104">SYNOPSIS</span></span>
<span data-ttu-id="091a1-105">Setzt angehaltene (unterbrochene) Dienste fort.</span><span class="sxs-lookup"><span data-stu-id="091a1-105">Resumes one or more suspended (paused) services.</span></span>

## <span data-ttu-id="091a1-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="091a1-106">SYNTAX</span></span>

### <span data-ttu-id="091a1-107">Inputobject (Standard)</span><span class="sxs-lookup"><span data-stu-id="091a1-107">InputObject (Default)</span></span>

```
Resume-Service [-InputObject] <ServiceController[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="091a1-108">Standard</span><span class="sxs-lookup"><span data-stu-id="091a1-108">Default</span></span>

```
Resume-Service [-Name] <String[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="091a1-109">DisplayName</span><span class="sxs-lookup"><span data-stu-id="091a1-109">DisplayName</span></span>

```
Resume-Service [-PassThru] -DisplayName <String[]> [-Include <String[]>] [-Exclude <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="091a1-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="091a1-110">DESCRIPTION</span></span>

<span data-ttu-id="091a1-111">Das- `Resume-Service` Cmdlet sendet für jeden der angegebenen Dienste eine Fortsetzungs Meldung an den Windows-Dienst Controller.</span><span class="sxs-lookup"><span data-stu-id="091a1-111">The `Resume-Service` cmdlet sends a resume message to the Windows Service Controller for each of the specified services.</span></span> <span data-ttu-id="091a1-112">Wenn ein Dienst angehalten wird, wird er fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="091a1-112">If a service is suspended, it resumes.</span></span> <span data-ttu-id="091a1-113">Wenn er gerade ausgeführt wird, wird die Meldung ignoriert.</span><span class="sxs-lookup"><span data-stu-id="091a1-113">If it is currently running, the message is ignored.</span></span> <span data-ttu-id="091a1-114">Sie können die Dienste mit ihren Dienstnamen oder anzeigen Amen angeben, oder Sie können mit dem **Inputobject** -Parameter ein Dienst Objekt übergeben, das die wiederherzustellenden Dienste darstellt.</span><span class="sxs-lookup"><span data-stu-id="091a1-114">You can specify the services by their service names or display names, or you can use the **InputObject** parameter to pass a service object that represents the services that you want to resume.</span></span>

## <span data-ttu-id="091a1-115">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="091a1-115">EXAMPLES</span></span>

### <span data-ttu-id="091a1-116">Beispiel 1: Fortsetzen eines Dienstanbieter auf dem lokalen Computer</span><span class="sxs-lookup"><span data-stu-id="091a1-116">Example 1: Resume a service on the local computer</span></span>

```
PS C:\> Resume-Service "sens"
```

<span data-ttu-id="091a1-117">Mit diesem Befehl wird der System Ereignis Benachrichtigungsdienst auf dem lokalen Computer fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="091a1-117">This command resumes the System Event Notification service on the local computer.</span></span> <span data-ttu-id="091a1-118">Der Dienst Name wird im Befehl von Sens dargestellt.</span><span class="sxs-lookup"><span data-stu-id="091a1-118">The service name is represented in the command by sens.</span></span> <span data-ttu-id="091a1-119">Der Befehl verwendet den **Name** -Parameter, um den Dienstnamen des Dienstanbieter anzugeben, aber der Befehl lässt den Parameternamen aus, da der Parameter Name optional ist.</span><span class="sxs-lookup"><span data-stu-id="091a1-119">The command uses the **Name** parameter to specify the service name of the service, but the command omits the parameter name because the parameter name is optional.</span></span>

### <span data-ttu-id="091a1-120">Beispiel 2: Fortsetzen aller angehaltenen Dienste</span><span class="sxs-lookup"><span data-stu-id="091a1-120">Example 2: Resume all suspended services</span></span>

```
PS C:\> Get-Service | Where-Object {$_.Status -eq "Paused"} | Resume-Service
```

<span data-ttu-id="091a1-121">Mit diesem Befehl werden alle angehaltenen Dienste auf dem Computer fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="091a1-121">This command resumes all of the suspended services on the computer.</span></span> <span data-ttu-id="091a1-122">Der `Get-Service` Cmdlet-Befehl ruft alle Dienste auf dem Computer ab.</span><span class="sxs-lookup"><span data-stu-id="091a1-122">The `Get-Service` cmdlet command gets all of the services on the computer.</span></span> <span data-ttu-id="091a1-123">Der Pipeline Operator ( `|` ) übergibt die Ergebnisse an das `Where-Object` Cmdlet, das die Dienste auswählt, deren **Status** -Eigenschaft angehalten ist.</span><span class="sxs-lookup"><span data-stu-id="091a1-123">The pipeline operator (`|`) passes the results to the `Where-Object` cmdlet, which selects the services that have a **Status** property of Paused.</span></span> <span data-ttu-id="091a1-124">Der nächste Pipeline Operator sendet die Ergebnisse an `Resume-Service` , wodurch die angehaltenen Dienste fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="091a1-124">The next pipeline operator sends the results to `Resume-Service`, which resumes the paused services.</span></span>

<span data-ttu-id="091a1-125">In der Praxis verwenden Sie den **WhatIf** -Parameter, um die Auswirkung des Befehls zu ermitteln, bevor Sie ihn ausführen.</span><span class="sxs-lookup"><span data-stu-id="091a1-125">In practice, you would use the **WhatIf** parameter to determine the effect of the command before you run it.</span></span>

## <span data-ttu-id="091a1-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="091a1-126">PARAMETERS</span></span>

### <span data-ttu-id="091a1-127">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="091a1-127">-DisplayName</span></span>

<span data-ttu-id="091a1-128">Gibt die Anzeigenamen der fortzusetzenden Dienste an.</span><span class="sxs-lookup"><span data-stu-id="091a1-128">Specifies the display names of the services to be resumed.</span></span>
<span data-ttu-id="091a1-129">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="091a1-129">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="091a1-130">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="091a1-130">-Exclude</span></span>

<span data-ttu-id="091a1-131">Gibt die Dienste an, die von diesem Cmdlet ausgelassen werden.</span><span class="sxs-lookup"><span data-stu-id="091a1-131">Specifies services that this cmdlet omits.</span></span> <span data-ttu-id="091a1-132">Der Wert dieses Parameters qualifiziert den **Name** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="091a1-132">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="091a1-133">Geben Sie ein Namenselement oder-Muster ein, z. b. s \*.</span><span class="sxs-lookup"><span data-stu-id="091a1-133">Enter a name element or pattern, such as s\*.</span></span> <span data-ttu-id="091a1-134">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="091a1-134">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="091a1-135">-Include</span><span class="sxs-lookup"><span data-stu-id="091a1-135">-Include</span></span>

<span data-ttu-id="091a1-136">Gibt Dienste zum Fortsetzen an.</span><span class="sxs-lookup"><span data-stu-id="091a1-136">Specifies services to resume.</span></span> <span data-ttu-id="091a1-137">Der Wert dieses Parameters qualifiziert den **Name** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="091a1-137">The value of this parameter qualifies **Name** parameter.</span></span> <span data-ttu-id="091a1-138">Geben Sie ein Namenselement oder-Muster ein, z. b. s \*.</span><span class="sxs-lookup"><span data-stu-id="091a1-138">Enter a name element or pattern, such as s\*.</span></span> <span data-ttu-id="091a1-139">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="091a1-139">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="091a1-140">-InputObject</span><span class="sxs-lookup"><span data-stu-id="091a1-140">-InputObject</span></span>

<span data-ttu-id="091a1-141">Gibt **ServiceController** -Objekte an, die die fort zusetzenden Dienste darstellen.</span><span class="sxs-lookup"><span data-stu-id="091a1-141">Specifies **ServiceController** objects that represent the services to resumed.</span></span> <span data-ttu-id="091a1-142">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="091a1-142">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="091a1-143">-Name</span><span class="sxs-lookup"><span data-stu-id="091a1-143">-Name</span></span>

<span data-ttu-id="091a1-144">Gibt die Dienstnamen der fortzusetzenden Dienste an.</span><span class="sxs-lookup"><span data-stu-id="091a1-144">Specifies the service names of the services to be resumed.</span></span>

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

### <span data-ttu-id="091a1-145">-PassThru</span><span class="sxs-lookup"><span data-stu-id="091a1-145">-PassThru</span></span>

<span data-ttu-id="091a1-146">Gibt ein Objekt zurück, das den Dienst darstellt.</span><span class="sxs-lookup"><span data-stu-id="091a1-146">Returns an object that represents the service.</span></span> <span data-ttu-id="091a1-147">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="091a1-147">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="091a1-148">-Confirm</span><span class="sxs-lookup"><span data-stu-id="091a1-148">-Confirm</span></span>

<span data-ttu-id="091a1-149">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="091a1-149">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="091a1-150">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="091a1-150">-WhatIf</span></span>

<span data-ttu-id="091a1-151">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="091a1-151">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="091a1-152">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="091a1-152">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="091a1-153">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="091a1-153">CommonParameters</span></span>

<span data-ttu-id="091a1-154">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="091a1-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="091a1-155">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="091a1-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="091a1-156">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="091a1-156">INPUTS</span></span>

### <span data-ttu-id="091a1-157">System. ServiceProcess. ServiceController, System. String</span><span class="sxs-lookup"><span data-stu-id="091a1-157">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="091a1-158">Sie können ein Dienst Objekt oder eine Zeichenfolge, die einen Dienstnamen enthält, über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="091a1-158">You can pipe a service object or a string that contains a service name to this cmdlet.</span></span>

## <span data-ttu-id="091a1-159">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="091a1-159">OUTPUTS</span></span>

### <span data-ttu-id="091a1-160">Keine, System. ServiceProcess. ServiceController</span><span class="sxs-lookup"><span data-stu-id="091a1-160">None, System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="091a1-161">Dieses Cmdlet generiert ein **System. ServiceProcess. ServiceController** -Objekt, das den fortgesetzten Dienst darstellt, wenn Sie den **passthru** -Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="091a1-161">This cmdlet generates a **System.ServiceProcess.ServiceController** object that represents the resumed service, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="091a1-162">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="091a1-162">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="091a1-163">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="091a1-163">NOTES</span></span>

<span data-ttu-id="091a1-164">Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="091a1-164">This cmdlet is only available on Windows platforms.</span></span>

- <span data-ttu-id="091a1-165">Der Status von Diensten, die angehalten wurden, wurde angehalten.</span><span class="sxs-lookup"><span data-stu-id="091a1-165">The status of services that have been suspended is Paused.</span></span> <span data-ttu-id="091a1-166">Wenn Dienste fortgesetzt werden, lautet Ihr Status wird ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="091a1-166">When services are resumed, their status is Running.</span></span>
- <span data-ttu-id="091a1-167">`Resume-Service` Dienste können nur von gesteuert werden, wenn der aktuelle Benutzer über die entsprechende Berechtigung verfügt.</span><span class="sxs-lookup"><span data-stu-id="091a1-167">`Resume-Service` can control services only when the current user has permission to do this.</span></span> <span data-ttu-id="091a1-168">Wenn ein Befehl nicht ordnungsgemäß verarbeitet wird, verfügen Sie u. U. nicht über die erforderlichen Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="091a1-168">If a command does not work correctly, you might not have the required permissions.</span></span>
- <span data-ttu-id="091a1-169">Geben Sie ein, um die Dienstnamen und anzeigen amen der Dienste auf dem System zu suchen `Get-Service` .</span><span class="sxs-lookup"><span data-stu-id="091a1-169">To find the service names and display names of the services on your system, type `Get-Service`.</span></span>
  <span data-ttu-id="091a1-170">Die Dienstnamen werden in der Spalte **Name** angezeigt, und die anzeigen Amen werden in der Spalte **Display Name** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="091a1-170">The service names appear in the **Name** column, and the display names appear in the **DisplayName** column.</span></span>

## <span data-ttu-id="091a1-171">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="091a1-171">RELATED LINKS</span></span>

[<span data-ttu-id="091a1-172">Get-Service</span><span class="sxs-lookup"><span data-stu-id="091a1-172">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="091a1-173">New-Service</span><span class="sxs-lookup"><span data-stu-id="091a1-173">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="091a1-174">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="091a1-174">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="091a1-175">Set-Service</span><span class="sxs-lookup"><span data-stu-id="091a1-175">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="091a1-176">Start-Service</span><span class="sxs-lookup"><span data-stu-id="091a1-176">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="091a1-177">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="091a1-177">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="091a1-178">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="091a1-178">Suspend-Service</span></span>](Suspend-Service.md)

[<span data-ttu-id="091a1-179">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="091a1-179">Remove-Service</span></span>](Remove-Service.md)
