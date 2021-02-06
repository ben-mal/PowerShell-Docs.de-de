---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/unregister-pssessionconfiguration?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-PSSessionConfiguration
ms.openlocfilehash: 4ac7605ada0fdb682e9df31c2422d368d6e64f57
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600286"
---
# <span data-ttu-id="f12a8-102">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="f12a8-102">Unregister-PSSessionConfiguration</span></span>

## <span data-ttu-id="f12a8-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="f12a8-103">SYNOPSIS</span></span>
<span data-ttu-id="f12a8-104">Löscht registrierte Sitzungskonfigurationen vom Computer.</span><span class="sxs-lookup"><span data-stu-id="f12a8-104">Deletes registered session configurations from the computer.</span></span>

## <span data-ttu-id="f12a8-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f12a8-105">SYNTAX</span></span>

```
Unregister-PSSessionConfiguration [-Name] <String> [-Force] [-NoServiceRestart] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="f12a8-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f12a8-106">DESCRIPTION</span></span>

<span data-ttu-id="f12a8-107">Mit dem- `Unregister-PSSessionConfiguration` Cmdlet werden registrierte Sitzungs Konfigurationen vom Computer gelöscht.</span><span class="sxs-lookup"><span data-stu-id="f12a8-107">The `Unregister-PSSessionConfiguration` cmdlet deletes registered session configurations from the computer.</span></span> <span data-ttu-id="f12a8-108">Dieses Cmdlet wurde für Systemadministratoren entwickelt, um benutzerdefinierte Sitzungs Konfigurationen für Benutzer zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="f12a8-108">This cmdlet is designed for system administrators to manage customized session configurations for users.</span></span>

<span data-ttu-id="f12a8-109">Damit die Änderung wirksam wird, wird `Unregister-PSSessionConfiguration` der **WinRM** -Dienst neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="f12a8-109">To make the change effective, `Unregister-PSSessionConfiguration` restarts the **WinRM** service.</span></span> <span data-ttu-id="f12a8-110">Geben Sie den **noservicerestart** -Parameter an, um den Neustart zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="f12a8-110">To prevent the restart, specify the **NoServiceRestart** parameter.</span></span>

<span data-ttu-id="f12a8-111">Wenn Sie die Standard Sitzungs Konfigurationen **Microsoft. PowerShell** oder **Microsoft. PowerShell32** versehentlich löschen, verwenden Sie das `Enable-PSRemoting` Cmdlet, um Sie wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="f12a8-111">If you accidentally delete the default **Microsoft.PowerShell** or **Microsoft.PowerShell32** session configurations, use the `Enable-PSRemoting` cmdlet to restore them.</span></span> <span data-ttu-id="f12a8-112">Weitere Informationen finden Sie unter [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="f12a8-112">For more information, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

## <span data-ttu-id="f12a8-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="f12a8-113">EXAMPLES</span></span>

### <span data-ttu-id="f12a8-114">Beispiel 1: Löschen einer Sitzungs Konfiguration</span><span class="sxs-lookup"><span data-stu-id="f12a8-114">Example 1: Delete a session configuration</span></span>

<span data-ttu-id="f12a8-115">In diesem Beispiel wird die **maintenanceshell** -Sitzungs Konfiguration vom Computer gelöscht.</span><span class="sxs-lookup"><span data-stu-id="f12a8-115">This example deletes the **MaintenanceShell** session configuration from the computer.</span></span>

```powershell
Unregister-PSSessionConfiguration -Name "MaintenanceShell"
```

### <span data-ttu-id="f12a8-116">Beispiel 2: Löschen einer Sitzungs Konfiguration und Neustarten des WinRM-Dienstanbieter</span><span class="sxs-lookup"><span data-stu-id="f12a8-116">Example 2: Delete a session configuration and restart the WinRM service</span></span>

<span data-ttu-id="f12a8-117">In diesem Beispiel wird die **maintenanceshell** -Konfiguration gelöscht und der WinRM-Dienst neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="f12a8-117">In this example, we delete the **MaintenanceShell** configuration and restart the WinRM service.</span></span> <span data-ttu-id="f12a8-118">Der **Force** -Parameter unterdrückt alle Benutzer Meldungen, um den **WinRM** -Dienst ohne Aufforderung neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="f12a8-118">The **Force** parameter suppresses all user messages to restart the **WinRM** service without prompting.</span></span>

```powershell
Unregister-PSSessionConfiguration -Name MaintenanceShell -Force
```

### <span data-ttu-id="f12a8-119">Beispiel 3: Löschen aller Sitzungs Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="f12a8-119">Example 3: Delete all session configurations</span></span>

<span data-ttu-id="f12a8-120">In diesen Beispielen werden zwei Möglichkeiten veranschaulicht, um alle Sitzungs Konfigurationen auf dem Computer zu löschen.</span><span class="sxs-lookup"><span data-stu-id="f12a8-120">This examples show two ways to delete all the session configurations on the computer.</span></span> <span data-ttu-id="f12a8-121">Beide Befehle haben denselben Effekt und können austauschbar verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f12a8-121">Both commands have the same effect and can be used interchangeably.</span></span>

```
Unregister-PSSessionConfiguration -Name *
Get-PSSessionConfiguration -Name * | Unregister-PSSessionConfiguration
```

### <span data-ttu-id="f12a8-122">Beispiel 4: Aufheben der Registrierung ohne Neustart</span><span class="sxs-lookup"><span data-stu-id="f12a8-122">Example 4: Unregister without a restart</span></span>

<span data-ttu-id="f12a8-123">Dieses Beispiel zeigt die Auswirkung der Verwendung des **noservicerestart** -Parameters, um einen Dienst Neustart zu verhindern, der alle Sitzungen auf dem Computer stören würde.</span><span class="sxs-lookup"><span data-stu-id="f12a8-123">This example shows the effect of using the **NoServiceRestart** parameter to prevent a service restart that would disrupt any sessions on the computer.</span></span>

```
PS> Unregister-PSSessionConfiguration -Name "MaintenanceShell" -NoServiceRestart
PS> Get-PSSessionConfiguration -Name "MaintenanceShell"

Get-PSSessionConfiguration -Name MaintenanceShell : No Session Configuration matches criteria "MaintenanceShell".
+ CategoryInfo          : NotSpecified: (:) [Write-Error], WriteErrorException
+ FullyQualifiedErrorId : Microsoft.PowerShell.Commands.WriteErrorException

PS> New-PSSession -ConfigurationName "MaintenanceShell"

Id Name      ComputerName    State    Configuration         Availability
-- ----      ------------    -----    -------------         ------------
1 Session1  localhost       Opened   MaintenanceShell      Available

PS> Restart-Service winrm
PS> New-PSSession -ConfigurationName MaintenanceShell

[localhost] Connecting to remote server failed with the following error message :
 The WS-Management service cannot process the request.
 The resource URI (http://schemas.microsoft.com/powershell/MaintenanceShell) was not found in the WS-Management catalog.
 The catalog contains the metadata that describes resources, or logical endpoints.
 For more information, see the about_Remote_Troubleshooting Help topic.
 + CategoryInfo          : OpenError: (System.Manageme....RemoteRunspace:RemoteRunspace) [], PSRemotingTransportException
 + FullyQualifiedErrorId : PSSessionOpenFailed
```

<span data-ttu-id="f12a8-124">Der `Unregister-PSSessionConfiguration` Löscht die **maintenanceshell** -Sitzungs Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="f12a8-124">The `Unregister-PSSessionConfiguration` deletes the **MaintenanceShell** session configuration.</span></span>
<span data-ttu-id="f12a8-125">Da der Befehl jedoch den **noservicerestart** -Parameter verwendet, wird der **WinRM** -Dienst nicht neu gestartet, und die Änderung ist noch nicht vollständig wirksam.</span><span class="sxs-lookup"><span data-stu-id="f12a8-125">However, because the command uses the **NoServiceRestart** parameter, the **WinRM** service is not restarted and the change is not yet completely effective.</span></span>

<span data-ttu-id="f12a8-126">Anschließend versucht, `Get-PSSessionConfiguration` die **maintenanceshell** -Sitzung zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="f12a8-126">Next, the `Get-PSSessionConfiguration` tries to get the **MaintenanceShell** session.</span></span> <span data-ttu-id="f12a8-127">Da die Sitzung aus der WS-Management-Ressourcen Tabelle entfernt wurde, `Get-PSSessionConfiguration` kann Sie nicht zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f12a8-127">Because the session has been removed from the WS-Management resource table, `Get-PSSessionConfiguration` cannot return it.</span></span>

<span data-ttu-id="f12a8-128">Mit dem- `New-PSSession` Cmdlet wird eine Sitzung mithilfe der **maintenanceshell** -Konfiguration erstellt.</span><span class="sxs-lookup"><span data-stu-id="f12a8-128">The `New-PSSession` cmdlet creates a session using the **MaintenanceShell** configuration.</span></span> <span data-ttu-id="f12a8-129">Der Befehl wird erfolgreich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f12a8-129">The command succeeds.</span></span> <span data-ttu-id="f12a8-130">Als nächstes starten wir den **WinRM** -Dienst neu.</span><span class="sxs-lookup"><span data-stu-id="f12a8-130">Next, we restart the **WinRM** service.</span></span>

<span data-ttu-id="f12a8-131">Zum Schluss `New-PSSession` versucht das Cmdlet, eine Sitzung zu erstellen, die die **maintenanceshell** -Konfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="f12a8-131">Finally, the `New-PSSession` cmdlet tries to create a session that uses the **MaintenanceShell** configuration.</span></span> <span data-ttu-id="f12a8-132">Diesmal schlägt die Sitzung fehl, da die **maintenanceshell** -Konfiguration gelöscht wurde, als der WinRM-Dienst neu gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="f12a8-132">This time, the session fails because the **MaintenanceShell** configuration was deleted when the WinRM service restarted.</span></span>

## <span data-ttu-id="f12a8-133">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f12a8-133">PARAMETERS</span></span>

### <span data-ttu-id="f12a8-134">-Force</span><span class="sxs-lookup"><span data-stu-id="f12a8-134">-Force</span></span>

<span data-ttu-id="f12a8-135">Gibt an, dass Sie vom Cmdlet nicht zur Bestätigung aufgefordert werden, und startet den **WinRM** -Dienst ohne Aufforderung neu.</span><span class="sxs-lookup"><span data-stu-id="f12a8-135">Indicates that the cmdlet does not prompt you for confirmation, and restarts the **WinRM** service without prompting.</span></span> <span data-ttu-id="f12a8-136">Durch Neustarten des Diensts wird die Konfigurationsänderung übernommen.</span><span class="sxs-lookup"><span data-stu-id="f12a8-136">Restarting the service makes the configuration change effective.</span></span>

<span data-ttu-id="f12a8-137">Um einen Neustart zu verhindern und die Aufforderung zum Neustart zu unterdrücken, verwenden Sie den **NoServiceRestart**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="f12a8-137">To prevent a restart and suppress the restart prompt, use the **NoServiceRestart** parameter.</span></span>

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

### <span data-ttu-id="f12a8-138">-Name</span><span class="sxs-lookup"><span data-stu-id="f12a8-138">-Name</span></span>

<span data-ttu-id="f12a8-139">Gibt die Namen der zu löschenden Sitzungskonfigurationen an.</span><span class="sxs-lookup"><span data-stu-id="f12a8-139">Specifies the names of the session configurations to delete.</span></span> <span data-ttu-id="f12a8-140">Geben Sie einen Sitzungskonfigurationsnamen oder ein Konfigurationsnamensmuster ein.</span><span class="sxs-lookup"><span data-stu-id="f12a8-140">Enter one session configuration name or a configuration name pattern.</span></span> <span data-ttu-id="f12a8-141">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="f12a8-141">Wildcard characters are permitted.</span></span> <span data-ttu-id="f12a8-142">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f12a8-142">This parameter is required.</span></span>

<span data-ttu-id="f12a8-143">Sie können eine Sitzungs Konfiguration auch über die Pipeline an senden `Unregister-PSSessionConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="f12a8-143">You can also pipe a session configurations to `Unregister-PSSessionConfiguration`.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="f12a8-144">-Noservicerestart</span><span class="sxs-lookup"><span data-stu-id="f12a8-144">-NoServiceRestart</span></span>

<span data-ttu-id="f12a8-145">Gibt an, dass dieses Cmdlet den **WinRM** -Dienst nicht neu startet, und unterdrückt die Eingabeaufforderung, um den Dienst neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="f12a8-145">Indicates that this cmdlet does not restart the **WinRM** service, and suppresses the prompt to restart the service.</span></span>

<span data-ttu-id="f12a8-146">Wenn Sie einen `Unregister-PSSessionConfiguration` Befehl ausführen, werden Sie standardmäßig aufgefordert, den **WinRM** -Dienst neu zu starten, damit die Änderung wirksam wird.</span><span class="sxs-lookup"><span data-stu-id="f12a8-146">By default, when you run an `Unregister-PSSessionConfiguration` command, you are prompted to restart the **WinRM** service to make the change effective.</span></span> <span data-ttu-id="f12a8-147">Bis der **WinRM** -Dienst neu gestartet wird, können Benutzer die nicht registrierte Sitzungs Konfiguration weiterhin verwenden, obwohl `Get-PSSessionConfiguration` Sie nicht gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="f12a8-147">Until the **WinRM** service is restarted, users can still use the unregistered session configuration, even though `Get-PSSessionConfiguration` does not find it.</span></span>

<span data-ttu-id="f12a8-148">Um den **WinRM** -Dienst ohne Aufforderung neu zu starten, geben Sie den **Force** -Parameter an.</span><span class="sxs-lookup"><span data-stu-id="f12a8-148">To restart the **WinRM** service without prompting, specify the **Force** parameter.</span></span> <span data-ttu-id="f12a8-149">Verwenden Sie das-Cmdlet, um den **WinRM** -Dienst manuell neu zu starten `Restart-Service` .</span><span class="sxs-lookup"><span data-stu-id="f12a8-149">To restart the **WinRM** service manually, use the `Restart-Service` cmdlet.</span></span>

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

### <span data-ttu-id="f12a8-150">-Confirm</span><span class="sxs-lookup"><span data-stu-id="f12a8-150">-Confirm</span></span>

<span data-ttu-id="f12a8-151">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="f12a8-151">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="f12a8-152">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="f12a8-152">-WhatIf</span></span>

<span data-ttu-id="f12a8-153">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f12a8-153">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="f12a8-154">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f12a8-154">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="f12a8-155">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f12a8-155">CommonParameters</span></span>

<span data-ttu-id="f12a8-156">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f12a8-156">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f12a8-157">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f12a8-157">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f12a8-158">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="f12a8-158">INPUTS</span></span>

### <span data-ttu-id="f12a8-159">Microsoft. PowerShell. Commands. pssessionconfigurationcommands # pssessionconfiguration</span><span class="sxs-lookup"><span data-stu-id="f12a8-159">Microsoft.PowerShell.Commands.PSSessionConfigurationCommands#PSSessionConfiguration</span></span>

<span data-ttu-id="f12a8-160">Sie können ein Sitzungs Konfigurationsobjekt von `Get-PSSessionConfiguration` über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="f12a8-160">You can pipe a session configuration object from `Get-PSSessionConfiguration` to this cmdlet.</span></span>

## <span data-ttu-id="f12a8-161">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="f12a8-161">OUTPUTS</span></span>

### <span data-ttu-id="f12a8-162">Keine</span><span class="sxs-lookup"><span data-stu-id="f12a8-162">None</span></span>

<span data-ttu-id="f12a8-163">Dieses Cmdlet gibt keine Objekte zurück.</span><span class="sxs-lookup"><span data-stu-id="f12a8-163">This cmdlet does not return any objects.</span></span>

## <span data-ttu-id="f12a8-164">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="f12a8-164">NOTES</span></span>

<span data-ttu-id="f12a8-165">Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f12a8-165">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="f12a8-166">Zum Ausführen dieses Cmdlets müssen Sie PowerShell mit der Option **als Administrator ausführen** starten.</span><span class="sxs-lookup"><span data-stu-id="f12a8-166">To run this cmdlet you must start PowerShell by using the **Run as administrator** option.</span></span>

## <span data-ttu-id="f12a8-167">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="f12a8-167">RELATED LINKS</span></span>

[<span data-ttu-id="f12a8-168">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="f12a8-168">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="f12a8-169">Enable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="f12a8-169">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="f12a8-170">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="f12a8-170">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="f12a8-171">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="f12a8-171">New-PSSessionConfigurationFile</span></span>](New-PSSessionConfigurationFile.md)

[<span data-ttu-id="f12a8-172">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="f12a8-172">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="f12a8-173">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="f12a8-173">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="f12a8-174">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="f12a8-174">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="f12a8-175">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="f12a8-175">Test-PSSessionConfigurationFile</span></span>](Test-PSSessionConfigurationFile.md)

[<span data-ttu-id="f12a8-176">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="f12a8-176">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="f12a8-177">WSMan-Anbieter</span><span class="sxs-lookup"><span data-stu-id="f12a8-177">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="f12a8-178">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="f12a8-178">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)

[<span data-ttu-id="f12a8-179">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="f12a8-179">about_Session_Configuration_Files</span></span>](About/about_Session_Configuration_Files.md)
