---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/restart-service?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Restart-Service
ms.openlocfilehash: f88e07e36ec7c6adf7f24e2c6e57ae5864eb1a60
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597379"
---
# <span data-ttu-id="f61f9-102">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="f61f9-102">Restart-Service</span></span>

## <span data-ttu-id="f61f9-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="f61f9-103">SYNOPSIS</span></span>
<span data-ttu-id="f61f9-104">Beendet Dienste und startet diese anschließend.</span><span class="sxs-lookup"><span data-stu-id="f61f9-104">Stops and then starts one or more services.</span></span>

## <span data-ttu-id="f61f9-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f61f9-105">SYNTAX</span></span>

### <span data-ttu-id="f61f9-106">Inputobject (Standard)</span><span class="sxs-lookup"><span data-stu-id="f61f9-106">InputObject (Default)</span></span>

```
Restart-Service [-Force] [-InputObject] <ServiceController[]> [-PassThru] [-Include <String[]>]
 [-Exclude <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="f61f9-107">Standard</span><span class="sxs-lookup"><span data-stu-id="f61f9-107">Default</span></span>

```
Restart-Service [-Force] [-Name] <String[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="f61f9-108">DisplayName</span><span class="sxs-lookup"><span data-stu-id="f61f9-108">DisplayName</span></span>

```
Restart-Service [-Force] [-PassThru] -DisplayName <String[]> [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="f61f9-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f61f9-109">DESCRIPTION</span></span>

<span data-ttu-id="f61f9-110">Das `Restart-Service` -Cmdlet sendet eine Nachricht zum Abbrechen und eine Start Meldung an den Windows-Dienst Controller für einen angegebenen Dienst.</span><span class="sxs-lookup"><span data-stu-id="f61f9-110">The `Restart-Service` cmdlet sends a stop message and then a start message to the Windows Service Controller for a specified service.</span></span> <span data-ttu-id="f61f9-111">Wenn ein Dienst bereits beendet wurde, wird er gestartet, ohne dass ein Fehler ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="f61f9-111">If a service was already stopped, it is started without notifying you of an error.</span></span> <span data-ttu-id="f61f9-112">Sie können die Dienste mit ihren Dienstnamen oder anzeigen Amen angeben, oder Sie können mit dem **Inputobject** -Parameter ein Objekt übergeben, das die einzelnen neu zu startenden Dienste darstellt.</span><span class="sxs-lookup"><span data-stu-id="f61f9-112">You can specify the services by their service names or display names, or you can use the **InputObject** parameter to pass an object that represents each service that you want to restart.</span></span>

## <span data-ttu-id="f61f9-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="f61f9-113">EXAMPLES</span></span>

### <span data-ttu-id="f61f9-114">Beispiel 1: Neustarten eines Dienstanbieter auf dem lokalen Computer</span><span class="sxs-lookup"><span data-stu-id="f61f9-114">Example 1: Restart a service on the local computer</span></span>

```powershell
PS C:\> Restart-Service -Name winmgmt
```

<span data-ttu-id="f61f9-115">Mit diesem Befehl wird der WMI-Dienst (WinMgmt) auf dem lokalen Computer neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="f61f9-115">This command restarts the Windows Management Instrumentation service (WinMgmt) on the local computer.</span></span>

### <span data-ttu-id="f61f9-116">Beispiel 2: Ausschließen eines Dienstanbieter</span><span class="sxs-lookup"><span data-stu-id="f61f9-116">Example 2: Exclude a service</span></span>

```powershell
PS C:\> Restart-Service -DisplayName "net*" -Exclude "net logon"
```

<span data-ttu-id="f61f9-117">Mit diesem Befehl werden die Dienste neu gestartet, deren Anzeige Name mit "NET" beginnt, mit Ausnahme des Anmelde Diensts.</span><span class="sxs-lookup"><span data-stu-id="f61f9-117">This command restarts the services that have a display name that starts with Net, except for the Net Logon service.</span></span>

### <span data-ttu-id="f61f9-118">Beispiel 3: Starten aller beendeten Netzwerkdienste</span><span class="sxs-lookup"><span data-stu-id="f61f9-118">Example 3: Start all stopped network services</span></span>

```powershell
PS C:\> Get-Service -Name "net*" | Where-Object {$_.Status -eq "Stopped"} | Restart-Service
```

<span data-ttu-id="f61f9-119">Mit diesem Befehl werden alle beendeten Netzwerkdienste auf dem Computer gestartet.</span><span class="sxs-lookup"><span data-stu-id="f61f9-119">This command starts all of the stopped network services on the computer.</span></span>

<span data-ttu-id="f61f9-120">Dieser Befehl verwendet das `Get-Service` Cmdlet, um Objekte zu erhalten, die die Dienste darstellen, deren Dienst Name mit "NET" beginnt.</span><span class="sxs-lookup"><span data-stu-id="f61f9-120">This command uses the `Get-Service` cmdlet to get objects that represent the services whose service name starts with net.</span></span> <span data-ttu-id="f61f9-121">Der Pipeline Operator ( `|` ) sendet das Dienst Objekt an das `Where-Object` Cmdlet, das nur die Dienste auswählt, die den Status "beendet" aufweisen.</span><span class="sxs-lookup"><span data-stu-id="f61f9-121">The pipeline operator (`|`) sends the services object to the `Where-Object` cmdlet, which selects only the services that have a status of stopped.</span></span> <span data-ttu-id="f61f9-122">Ein weiterer Pipeline Operator sendet die ausgewählten Dienste an `Restart-Service` .</span><span class="sxs-lookup"><span data-stu-id="f61f9-122">Another pipeline operator sends the selected services to `Restart-Service`.</span></span>

<span data-ttu-id="f61f9-123">In der Praxis verwenden Sie den **WhatIf** -Parameter, um die Auswirkung des Befehls zu ermitteln, bevor Sie ihn ausführen.</span><span class="sxs-lookup"><span data-stu-id="f61f9-123">In practice, you would use the **WhatIf** parameter to determine the effect of the command before you run it.</span></span>

## <span data-ttu-id="f61f9-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f61f9-124">PARAMETERS</span></span>

### <span data-ttu-id="f61f9-125">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="f61f9-125">-DisplayName</span></span>

<span data-ttu-id="f61f9-126">Gibt die anzeigen Amen von Diensten an, die neu gestartet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f61f9-126">Specifies the display names of services to restarted.</span></span> <span data-ttu-id="f61f9-127">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="f61f9-127">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="f61f9-128">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="f61f9-128">-Exclude</span></span>

<span data-ttu-id="f61f9-129">Gibt die Dienste an, die von diesem Cmdlet ausgelassen werden.</span><span class="sxs-lookup"><span data-stu-id="f61f9-129">Specifies services that this cmdlet omits.</span></span> <span data-ttu-id="f61f9-130">Der Wert dieses Parameters qualifiziert den **Name** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="f61f9-130">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="f61f9-131">Geben Sie ein Namenselement oder-Muster ein, z. b. s \*.</span><span class="sxs-lookup"><span data-stu-id="f61f9-131">Enter a name element or pattern, such as s\*.</span></span> <span data-ttu-id="f61f9-132">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="f61f9-132">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="f61f9-133">-Force</span><span class="sxs-lookup"><span data-stu-id="f61f9-133">-Force</span></span>

<span data-ttu-id="f61f9-134">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="f61f9-134">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="f61f9-135">-Include</span><span class="sxs-lookup"><span data-stu-id="f61f9-135">-Include</span></span>

<span data-ttu-id="f61f9-136">Gibt die Dienste an, die von diesem Cmdlet neu gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="f61f9-136">Specifies services that this cmdlet restarts.</span></span> <span data-ttu-id="f61f9-137">Der Wert dieses Parameters qualifiziert den **Name** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="f61f9-137">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="f61f9-138">Geben Sie ein Namenselement oder-Muster ein, z. b. s \*.</span><span class="sxs-lookup"><span data-stu-id="f61f9-138">Enter a name element or pattern, such as s\*.</span></span> <span data-ttu-id="f61f9-139">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="f61f9-139">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="f61f9-140">-InputObject</span><span class="sxs-lookup"><span data-stu-id="f61f9-140">-InputObject</span></span>

<span data-ttu-id="f61f9-141">Gibt **ServiceController** -Objekte an, die die neu zu Start-Dienste darstellen.</span><span class="sxs-lookup"><span data-stu-id="f61f9-141">Specifies **ServiceController** objects that represent the services to restart.</span></span> <span data-ttu-id="f61f9-142">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="f61f9-142">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="f61f9-143">-Name</span><span class="sxs-lookup"><span data-stu-id="f61f9-143">-Name</span></span>

<span data-ttu-id="f61f9-144">Gibt die Dienstnamen der neu zu startenden Dienste an.</span><span class="sxs-lookup"><span data-stu-id="f61f9-144">Specifies the service names of the services to restart.</span></span>

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

### <span data-ttu-id="f61f9-145">-PassThru</span><span class="sxs-lookup"><span data-stu-id="f61f9-145">-PassThru</span></span>

<span data-ttu-id="f61f9-146">Gibt ein Objekt zurück, das den Dienst darstellt.</span><span class="sxs-lookup"><span data-stu-id="f61f9-146">Returns an object that represents the service.</span></span> <span data-ttu-id="f61f9-147">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="f61f9-147">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="f61f9-148">-Confirm</span><span class="sxs-lookup"><span data-stu-id="f61f9-148">-Confirm</span></span>

<span data-ttu-id="f61f9-149">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="f61f9-149">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="f61f9-150">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="f61f9-150">-WhatIf</span></span>

<span data-ttu-id="f61f9-151">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f61f9-151">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="f61f9-152">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f61f9-152">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="f61f9-153">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f61f9-153">CommonParameters</span></span>

<span data-ttu-id="f61f9-154">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f61f9-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f61f9-155">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f61f9-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f61f9-156">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="f61f9-156">INPUTS</span></span>

### <span data-ttu-id="f61f9-157">System. ServiceProcess. ServiceController, System. String</span><span class="sxs-lookup"><span data-stu-id="f61f9-157">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="f61f9-158">Sie können ein Dienst Objekt oder eine Zeichenfolge, die einen Dienstnamen enthält, über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="f61f9-158">You can pipe a service object or a string that contains a service name to this cmdlet.</span></span>

## <span data-ttu-id="f61f9-159">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="f61f9-159">OUTPUTS</span></span>

### <span data-ttu-id="f61f9-160">Keine, System. ServiceProcess. ServiceController</span><span class="sxs-lookup"><span data-stu-id="f61f9-160">None, System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="f61f9-161">Dieses Cmdlet generiert ein **System. ServiceProcess. ServiceController** -Objekt, das den neu gestarteten Dienst darstellt, wenn Sie den **passthru** -Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="f61f9-161">This cmdlet generates a **System.ServiceProcess.ServiceController** object that represents the restarted service, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="f61f9-162">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="f61f9-162">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="f61f9-163">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="f61f9-163">NOTES</span></span>

<span data-ttu-id="f61f9-164">Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f61f9-164">This cmdlet is only available on Windows platforms.</span></span>

- <span data-ttu-id="f61f9-165">`Restart-Service` Dienste können nur von gesteuert werden, wenn der aktuelle Benutzer über die entsprechende Berechtigung verfügt.</span><span class="sxs-lookup"><span data-stu-id="f61f9-165">`Restart-Service` can control services only when the current user has permission to do this.</span></span> <span data-ttu-id="f61f9-166">Wenn ein Befehl nicht ordnungsgemäß verarbeitet wird, verfügen Sie u. U. nicht über die erforderlichen Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="f61f9-166">If a command does not work correctly, you might not have the required permissions.</span></span>
- <span data-ttu-id="f61f9-167">Geben Sie "ein, um die Dienstnamen und anzeigen amen der Dienste auf dem System zu suchen `Get-Service` .</span><span class="sxs-lookup"><span data-stu-id="f61f9-167">To find the service names and display names of the services on your system, type `Get-Service`".</span></span>
  <span data-ttu-id="f61f9-168">Die Dienstnamen werden in der Spalte **Name** angezeigt, und die anzeigen Amen werden in der Spalte **Display Name** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f61f9-168">The service names appear in the **Name** column, and the display names appear in the **DisplayName** column.</span></span>

## <span data-ttu-id="f61f9-169">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="f61f9-169">RELATED LINKS</span></span>

[<span data-ttu-id="f61f9-170">Get-Service</span><span class="sxs-lookup"><span data-stu-id="f61f9-170">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="f61f9-171">New-Service</span><span class="sxs-lookup"><span data-stu-id="f61f9-171">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="f61f9-172">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="f61f9-172">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="f61f9-173">Set-Service</span><span class="sxs-lookup"><span data-stu-id="f61f9-173">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="f61f9-174">Start-Service</span><span class="sxs-lookup"><span data-stu-id="f61f9-174">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="f61f9-175">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="f61f9-175">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="f61f9-176">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="f61f9-176">Suspend-Service</span></span>](Suspend-Service.md)

[<span data-ttu-id="f61f9-177">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="f61f9-177">Remove-Service</span></span>](Remove-Service.md)
