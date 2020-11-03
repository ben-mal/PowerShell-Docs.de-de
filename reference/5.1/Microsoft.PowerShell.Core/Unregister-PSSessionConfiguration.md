---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/unregister-pssessionconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-PSSessionConfiguration
ms.openlocfilehash: 5e43e9e23e52885325eaf1eb4d460a60dc110567
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218199"
---
# <span data-ttu-id="5fb80-103">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="5fb80-103">Unregister-PSSessionConfiguration</span></span>

## <span data-ttu-id="5fb80-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="5fb80-104">SYNOPSIS</span></span>
<span data-ttu-id="5fb80-105">Löscht registrierte Sitzungskonfigurationen vom Computer.</span><span class="sxs-lookup"><span data-stu-id="5fb80-105">Deletes registered session configurations from the computer.</span></span>

## <span data-ttu-id="5fb80-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5fb80-106">SYNTAX</span></span>

```
Unregister-PSSessionConfiguration [-Name] <String> [-Force] [-NoServiceRestart] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="5fb80-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5fb80-107">DESCRIPTION</span></span>

<span data-ttu-id="5fb80-108">Mit dem- `Unregister-PSSessionConfiguration` Cmdlet werden registrierte Sitzungs Konfigurationen vom Computer gelöscht.</span><span class="sxs-lookup"><span data-stu-id="5fb80-108">The `Unregister-PSSessionConfiguration` cmdlet deletes registered session configurations from the computer.</span></span> <span data-ttu-id="5fb80-109">Dieses Cmdlet wurde für Systemadministratoren entwickelt, um benutzerdefinierte Sitzungs Konfigurationen für Benutzer zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="5fb80-109">This cmdlet is designed for system administrators to manage customized session configurations for users.</span></span>

<span data-ttu-id="5fb80-110">Damit die Änderung wirksam wird, wird `Unregister-PSSessionConfiguration` der **WinRM** -Dienst neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="5fb80-110">To make the change effective, `Unregister-PSSessionConfiguration` restarts the **WinRM** service.</span></span> <span data-ttu-id="5fb80-111">Geben Sie den **noservicerestart** -Parameter an, um den Neustart zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="5fb80-111">To prevent the restart, specify the **NoServiceRestart** parameter.</span></span>

<span data-ttu-id="5fb80-112">Wenn Sie die Standard Sitzungs Konfigurationen **Microsoft. PowerShell** oder **Microsoft. PowerShell32** versehentlich löschen, verwenden Sie das `Enable-PSRemoting` Cmdlet, um Sie wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="5fb80-112">If you accidentally delete the default **Microsoft.PowerShell** or **Microsoft.PowerShell32** session configurations, use the `Enable-PSRemoting` cmdlet to restore them.</span></span> <span data-ttu-id="5fb80-113">Weitere Informationen finden Sie unter [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="5fb80-113">For more information, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

## <span data-ttu-id="5fb80-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="5fb80-114">EXAMPLES</span></span>

### <span data-ttu-id="5fb80-115">Beispiel 1: Löschen einer Sitzungs Konfiguration</span><span class="sxs-lookup"><span data-stu-id="5fb80-115">Example 1: Delete a session configuration</span></span>

<span data-ttu-id="5fb80-116">In diesem Beispiel wird die **maintenanceshell** -Sitzungs Konfiguration vom Computer gelöscht.</span><span class="sxs-lookup"><span data-stu-id="5fb80-116">This example deletes the **MaintenanceShell** session configuration from the computer.</span></span>

```powershell
Unregister-PSSessionConfiguration -Name "MaintenanceShell"
```

### <span data-ttu-id="5fb80-117">Beispiel 2: Löschen einer Sitzungs Konfiguration und Neustarten des WinRM-Dienstanbieter</span><span class="sxs-lookup"><span data-stu-id="5fb80-117">Example 2: Delete a session configuration and restart the WinRM service</span></span>

<span data-ttu-id="5fb80-118">In diesem Beispiel wird die **maintenanceshell** -Konfiguration gelöscht und der WinRM-Dienst neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="5fb80-118">In this example, we delete the **MaintenanceShell** configuration and restart the WinRM service.</span></span> <span data-ttu-id="5fb80-119">Der **Force** -Parameter unterdrückt alle Benutzer Meldungen, um den **WinRM** -Dienst ohne Aufforderung neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="5fb80-119">The **Force** parameter suppresses all user messages to restart the **WinRM** service without prompting.</span></span>

```powershell
Unregister-PSSessionConfiguration -Name MaintenanceShell -Force
```

### <span data-ttu-id="5fb80-120">Beispiel 3: Löschen aller Sitzungs Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="5fb80-120">Example 3: Delete all session configurations</span></span>

<span data-ttu-id="5fb80-121">In diesen Beispielen werden zwei Möglichkeiten veranschaulicht, um alle Sitzungs Konfigurationen auf dem Computer zu löschen.</span><span class="sxs-lookup"><span data-stu-id="5fb80-121">This examples show two ways to delete all the session configurations on the computer.</span></span> <span data-ttu-id="5fb80-122">Beide Befehle haben denselben Effekt und können austauschbar verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5fb80-122">Both commands have the same effect and can be used interchangeably.</span></span>

```
Unregister-PSSessionConfiguration -Name *
Get-PSSessionConfiguration -Name * | Unregister-PSSessionConfiguration
```

### <span data-ttu-id="5fb80-123">Beispiel 4: Aufheben der Registrierung ohne Neustart</span><span class="sxs-lookup"><span data-stu-id="5fb80-123">Example 4: Unregister without a restart</span></span>

<span data-ttu-id="5fb80-124">Dieses Beispiel zeigt die Auswirkung der Verwendung des **noservicerestart** -Parameters, um einen Dienst Neustart zu verhindern, der alle Sitzungen auf dem Computer stören würde.</span><span class="sxs-lookup"><span data-stu-id="5fb80-124">This example shows the effect of using the **NoServiceRestart** parameter to prevent a service restart that would disrupt any sessions on the computer.</span></span>

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

<span data-ttu-id="5fb80-125">Der `Unregister-PSSessionConfiguration` Löscht die **maintenanceshell** -Sitzungs Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="5fb80-125">The `Unregister-PSSessionConfiguration` deletes the **MaintenanceShell** session configuration.</span></span>
<span data-ttu-id="5fb80-126">Da der Befehl jedoch den **noservicerestart** -Parameter verwendet, wird der **WinRM** -Dienst nicht neu gestartet, und die Änderung ist noch nicht vollständig wirksam.</span><span class="sxs-lookup"><span data-stu-id="5fb80-126">However, because the command uses the **NoServiceRestart** parameter, the **WinRM** service is not restarted and the change is not yet completely effective.</span></span>

<span data-ttu-id="5fb80-127">Anschließend versucht, `Get-PSSessionConfiguration` die **maintenanceshell** -Sitzung zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="5fb80-127">Next, the `Get-PSSessionConfiguration` tries to get the **MaintenanceShell** session.</span></span> <span data-ttu-id="5fb80-128">Da die Sitzung aus der WS-Management-Ressourcen Tabelle entfernt wurde, `Get-PSSessionConfiguration` kann Sie nicht zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="5fb80-128">Because the session has been removed from the WS-Management resource table, `Get-PSSessionConfiguration` cannot return it.</span></span>

<span data-ttu-id="5fb80-129">Mit dem- `New-PSSession` Cmdlet wird eine Sitzung mithilfe der **maintenanceshell** -Konfiguration erstellt.</span><span class="sxs-lookup"><span data-stu-id="5fb80-129">The `New-PSSession` cmdlet creates a session using the **MaintenanceShell** configuration.</span></span> <span data-ttu-id="5fb80-130">Der Befehl wird erfolgreich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5fb80-130">The command succeeds.</span></span> <span data-ttu-id="5fb80-131">Als nächstes starten wir den **WinRM** -Dienst neu.</span><span class="sxs-lookup"><span data-stu-id="5fb80-131">Next, we restart the **WinRM** service.</span></span>

<span data-ttu-id="5fb80-132">Zum Schluss `New-PSSession` versucht das Cmdlet, eine Sitzung zu erstellen, die die **maintenanceshell** -Konfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="5fb80-132">Finally, the `New-PSSession` cmdlet tries to create a session that uses the **MaintenanceShell** configuration.</span></span> <span data-ttu-id="5fb80-133">Diesmal schlägt die Sitzung fehl, da die **maintenanceshell** -Konfiguration gelöscht wurde, als der WinRM-Dienst neu gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="5fb80-133">This time, the session fails because the **MaintenanceShell** configuration was deleted when the WinRM service restarted.</span></span>

## <span data-ttu-id="5fb80-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5fb80-134">PARAMETERS</span></span>

### <span data-ttu-id="5fb80-135">-Force</span><span class="sxs-lookup"><span data-stu-id="5fb80-135">-Force</span></span>

<span data-ttu-id="5fb80-136">Gibt an, dass Sie vom Cmdlet nicht zur Bestätigung aufgefordert werden, und startet den **WinRM** -Dienst ohne Aufforderung neu.</span><span class="sxs-lookup"><span data-stu-id="5fb80-136">Indicates that the cmdlet does not prompt you for confirmation, and restarts the **WinRM** service without prompting.</span></span> <span data-ttu-id="5fb80-137">Durch Neustarten des Diensts wird die Konfigurationsänderung übernommen.</span><span class="sxs-lookup"><span data-stu-id="5fb80-137">Restarting the service makes the configuration change effective.</span></span>

<span data-ttu-id="5fb80-138">Um einen Neustart zu verhindern und die Aufforderung zum Neustart zu unterdrücken, verwenden Sie den **NoServiceRestart** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="5fb80-138">To prevent a restart and suppress the restart prompt, use the **NoServiceRestart** parameter.</span></span>

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

### <span data-ttu-id="5fb80-139">-Name</span><span class="sxs-lookup"><span data-stu-id="5fb80-139">-Name</span></span>

<span data-ttu-id="5fb80-140">Gibt die Namen der zu löschenden Sitzungskonfigurationen an.</span><span class="sxs-lookup"><span data-stu-id="5fb80-140">Specifies the names of the session configurations to delete.</span></span> <span data-ttu-id="5fb80-141">Geben Sie einen Sitzungskonfigurationsnamen oder ein Konfigurationsnamensmuster ein.</span><span class="sxs-lookup"><span data-stu-id="5fb80-141">Enter one session configuration name or a configuration name pattern.</span></span> <span data-ttu-id="5fb80-142">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="5fb80-142">Wildcard characters are permitted.</span></span> <span data-ttu-id="5fb80-143">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5fb80-143">This parameter is required.</span></span>

<span data-ttu-id="5fb80-144">Sie können eine Sitzungs Konfiguration auch über die Pipeline an senden `Unregister-PSSessionConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="5fb80-144">You can also pipe a session configurations to `Unregister-PSSessionConfiguration`.</span></span>

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

### <span data-ttu-id="5fb80-145">-Noservicerestart</span><span class="sxs-lookup"><span data-stu-id="5fb80-145">-NoServiceRestart</span></span>

<span data-ttu-id="5fb80-146">Gibt an, dass dieses Cmdlet den **WinRM** -Dienst nicht neu startet, und unterdrückt die Eingabeaufforderung, um den Dienst neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="5fb80-146">Indicates that this cmdlet does not restart the **WinRM** service, and suppresses the prompt to restart the service.</span></span>

<span data-ttu-id="5fb80-147">Wenn Sie einen `Unregister-PSSessionConfiguration` Befehl ausführen, werden Sie standardmäßig aufgefordert, den **WinRM** -Dienst neu zu starten, damit die Änderung wirksam wird.</span><span class="sxs-lookup"><span data-stu-id="5fb80-147">By default, when you run an `Unregister-PSSessionConfiguration` command, you are prompted to restart the **WinRM** service to make the change effective.</span></span> <span data-ttu-id="5fb80-148">Bis der **WinRM** -Dienst neu gestartet wird, können Benutzer die nicht registrierte Sitzungs Konfiguration weiterhin verwenden, obwohl `Get-PSSessionConfiguration` Sie nicht gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="5fb80-148">Until the **WinRM** service is restarted, users can still use the unregistered session configuration, even though `Get-PSSessionConfiguration` does not find it.</span></span>

<span data-ttu-id="5fb80-149">Um den **WinRM** -Dienst ohne Aufforderung neu zu starten, geben Sie den **Force** -Parameter an.</span><span class="sxs-lookup"><span data-stu-id="5fb80-149">To restart the **WinRM** service without prompting, specify the **Force** parameter.</span></span> <span data-ttu-id="5fb80-150">Verwenden Sie das-Cmdlet, um den **WinRM** -Dienst manuell neu zu starten `Restart-Service` .</span><span class="sxs-lookup"><span data-stu-id="5fb80-150">To restart the **WinRM** service manually, use the `Restart-Service` cmdlet.</span></span>

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

### <span data-ttu-id="5fb80-151">-Confirm</span><span class="sxs-lookup"><span data-stu-id="5fb80-151">-Confirm</span></span>

<span data-ttu-id="5fb80-152">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="5fb80-152">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="5fb80-153">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="5fb80-153">-WhatIf</span></span>

<span data-ttu-id="5fb80-154">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5fb80-154">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="5fb80-155">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5fb80-155">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="5fb80-156">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="5fb80-156">CommonParameters</span></span>

<span data-ttu-id="5fb80-157">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5fb80-157">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5fb80-158">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="5fb80-158">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5fb80-159">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="5fb80-159">INPUTS</span></span>

### <span data-ttu-id="5fb80-160">Microsoft. PowerShell. Commands. pssessionconfigurationcommands # pssessionconfiguration</span><span class="sxs-lookup"><span data-stu-id="5fb80-160">Microsoft.PowerShell.Commands.PSSessionConfigurationCommands#PSSessionConfiguration</span></span>

<span data-ttu-id="5fb80-161">Sie können ein Sitzungs Konfigurationsobjekt von `Get-PSSessionConfiguration` über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="5fb80-161">You can pipe a session configuration object from `Get-PSSessionConfiguration` to this cmdlet.</span></span>

## <span data-ttu-id="5fb80-162">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="5fb80-162">OUTPUTS</span></span>

### <span data-ttu-id="5fb80-163">Keine</span><span class="sxs-lookup"><span data-stu-id="5fb80-163">None</span></span>

<span data-ttu-id="5fb80-164">Dieses Cmdlet gibt keine Objekte zurück.</span><span class="sxs-lookup"><span data-stu-id="5fb80-164">This cmdlet does not return any objects.</span></span>

## <span data-ttu-id="5fb80-165">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="5fb80-165">NOTES</span></span>

<span data-ttu-id="5fb80-166">Zum Ausführen dieses Cmdlets müssen Sie PowerShell mit der Option **als Administrator ausführen** starten.</span><span class="sxs-lookup"><span data-stu-id="5fb80-166">To run this cmdlet you must start PowerShell by using the **Run as administrator** option.</span></span>

## <span data-ttu-id="5fb80-167">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="5fb80-167">RELATED LINKS</span></span>

[<span data-ttu-id="5fb80-168">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="5fb80-168">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="5fb80-169">Enable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="5fb80-169">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="5fb80-170">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="5fb80-170">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="5fb80-171">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="5fb80-171">New-PSSessionConfigurationFile</span></span>](New-PSSessionConfigurationFile.md)

[<span data-ttu-id="5fb80-172">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="5fb80-172">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="5fb80-173">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="5fb80-173">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="5fb80-174">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="5fb80-174">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="5fb80-175">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="5fb80-175">Test-PSSessionConfigurationFile</span></span>](Test-PSSessionConfigurationFile.md)

[<span data-ttu-id="5fb80-176">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="5fb80-176">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="5fb80-177">WSMan-Anbieter</span><span class="sxs-lookup"><span data-stu-id="5fb80-177">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="5fb80-178">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="5fb80-178">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)

[<span data-ttu-id="5fb80-179">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="5fb80-179">about_Session_Configuration_Files</span></span>](About/about_Session_Configuration_Files.md)
