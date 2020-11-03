---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enable-pssessionconfiguration?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSSessionConfiguration
ms.openlocfilehash: 237fe83af05de7a97113deb95a831d8295c9f4c4
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210700"
---
# <span data-ttu-id="2e8ee-103">Enable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="2e8ee-103">Enable-PSSessionConfiguration</span></span>

## <span data-ttu-id="2e8ee-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="2e8ee-104">SYNOPSIS</span></span>
<span data-ttu-id="2e8ee-105">Aktiviert die Sitzungskonfigurationen auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="2e8ee-105">Enables the session configurations on the local computer.</span></span>

## <span data-ttu-id="2e8ee-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2e8ee-106">SYNTAX</span></span>

```
Enable-PSSessionConfiguration [[-Name] <String[]>] [-Force] [-SecurityDescriptorSddl <String>]
 [-SkipNetworkProfileCheck] [-NoServiceRestart] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="2e8ee-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2e8ee-107">DESCRIPTION</span></span>

<span data-ttu-id="2e8ee-108">Mit dem- `Enable-PSSessionConfiguration` Cmdlet werden registrierte Sitzungs Konfigurationen aktiviert, die deaktiviert wurden, wie z `Disable-PSSessionConfiguration` . b. die-oder- `Disable-PSRemoting` Cmdlets oder der **AccessMode** -Parameter von `Register-PSSessionConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="2e8ee-108">The `Enable-PSSessionConfiguration` cmdlet enables registered session configurations that have been disabled, such as by using the `Disable-PSSessionConfiguration` or `Disable-PSRemoting` cmdlets, or the **AccessMode** parameter of `Register-PSSessionConfiguration`.</span></span> <span data-ttu-id="2e8ee-109">Dies ist ein erweitertes Cmdlet für Systemadministratoren, die benutzerdefinierte Sitzungskonfigurationen für ihre Benutzer verwalten.</span><span class="sxs-lookup"><span data-stu-id="2e8ee-109">This is an advanced cmdlet that is designed to be used by system administrators to manage customized session configurations for their users.</span></span>

<span data-ttu-id="2e8ee-110">Ohne Parameter `Enable-PSSessionConfiguration` aktiviert die **Microsoft. PowerShell** -Konfiguration, bei der es sich um die Standardkonfiguration handelt, die für Sitzungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2e8ee-110">Without parameters, `Enable-PSSessionConfiguration` enables the **Microsoft.PowerShell** configuration, which is the default configuration that is used for sessions.</span></span>

<span data-ttu-id="2e8ee-111">`Enable-PSSessionConfiguration` entfernt die **Deny_All** Einstellung aus der Sicherheits Beschreibung der betroffenen Sitzungs Konfigurationen, aktiviert den Listener, der Anforderungen an eine beliebige IP-Adresse annimmt, und startet den WinRM-Dienst neu.</span><span class="sxs-lookup"><span data-stu-id="2e8ee-111">`Enable-PSSessionConfiguration` removes the **Deny_All** setting from the security descriptor of the affected session configurations, turns on the listener that accepts requests on any IP address, and restarts the WinRM service.</span></span> <span data-ttu-id="2e8ee-112">Ab PowerShell 3,0 wird `Enable-PSSessionConfiguration` auch der Wert der **aktivierten** Eigenschaft der Sitzungs Konfiguration ( `WSMan:\<computer>\PlugIn\<SessionConfigurationName>\Enabled` ) auf true festgelegt.</span><span class="sxs-lookup"><span data-stu-id="2e8ee-112">Beginning in PowerShell 3.0, `Enable-PSSessionConfiguration` also sets the value of the **Enabled** property of the session configuration (`WSMan:\<computer>\PlugIn\<SessionConfigurationName>\Enabled`) to True.</span></span> <span data-ttu-id="2e8ee-113">`Enable-PSSessionConfiguration`Die **Network_Deny_All** `AccessMode=Local` Sicherheits beschreibungeinstellung Network_Deny_All (), die nur Benutzern des lokalen Computers die Verwendung der Sitzungs Konfiguration ermöglicht, wird von jedoch nicht entfernt oder geändert.</span><span class="sxs-lookup"><span data-stu-id="2e8ee-113">However, `Enable-PSSessionConfiguration` does not remove or change the **Network_Deny_All** (`AccessMode=Local`) security descriptor setting that allows only users of the local computer to use to the session configuration.</span></span>

## <span data-ttu-id="2e8ee-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="2e8ee-114">EXAMPLES</span></span>

### <span data-ttu-id="2e8ee-115">Beispiel 1: Erneutes Aktivieren der Standard Sitzung</span><span class="sxs-lookup"><span data-stu-id="2e8ee-115">Example 1: Re-enable the default session</span></span>

<span data-ttu-id="2e8ee-116">In diesem Beispiel wird die **Microsoft. PowerShell** -Standard Sitzungs Konfiguration auf dem Computer erneut aktiviert.</span><span class="sxs-lookup"><span data-stu-id="2e8ee-116">This example re-enables the **Microsoft.PowerShell** default session configuration on the computer.</span></span>

```powershell
Enable-PSSessionConfiguration
```

### <span data-ttu-id="2e8ee-117">Beispiel 2: Erneutes Aktivieren der angegebenen Sitzungen</span><span class="sxs-lookup"><span data-stu-id="2e8ee-117">Example 2: Re-enable specified sessions</span></span>

<span data-ttu-id="2e8ee-118">In diesem Beispiel werden die **maintenanceshell** -und **adminshell** -Sitzungs Konfigurationen auf dem Computer erneut aktiviert.</span><span class="sxs-lookup"><span data-stu-id="2e8ee-118">This example re-enables the **MaintenanceShell** and **AdminShell** session configurations on the computer.</span></span>

```powershell
Enable-PSSessionConfiguration -Name MaintenanceShell, AdminShell
```

### <span data-ttu-id="2e8ee-119">Beispiel 3: Erneutes Aktivieren der gesamten Sitzungen</span><span class="sxs-lookup"><span data-stu-id="2e8ee-119">Example 3: Re-enable the all sessions</span></span>

<span data-ttu-id="2e8ee-120">In diesem Beispiel werden alle Sitzungs Konfigurationen auf dem Computer erneut aktiviert.</span><span class="sxs-lookup"><span data-stu-id="2e8ee-120">This example re-enables all session configurations on the computer.</span></span> <span data-ttu-id="2e8ee-121">Diese Befehle sind gleichwertig.</span><span class="sxs-lookup"><span data-stu-id="2e8ee-121">These commands are equivalent.</span></span>
<span data-ttu-id="2e8ee-122">Daher können Sie beide verwenden.</span><span class="sxs-lookup"><span data-stu-id="2e8ee-122">Therefore, you can use either.</span></span>

```powershell
Enable-PSSessionConfiguration -Name *
Get-PSSessionConfiguration | Enable-PSSessionConfiguration
```

<span data-ttu-id="2e8ee-123">`Enable-PSSessionConfiguration` generiert keine Fehler, wenn Sie eine bereits aktivierte Sitzungs Konfiguration aktivieren.</span><span class="sxs-lookup"><span data-stu-id="2e8ee-123">`Enable-PSSessionConfiguration` does not generate an error if you enable a session configuration that is already enabled.</span></span>

### <span data-ttu-id="2e8ee-124">Beispiel 4: Erneutes Aktivieren einer Sitzung und Angeben einer neuen Sicherheits Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2e8ee-124">Example 4: Re-enable a session and specify a new security descriptor</span></span>

<span data-ttu-id="2e8ee-125">In diesem Beispiel wird die **maintenanceshell** -Sitzungs Konfiguration erneut aktiviert und eine neue Sicherheits Beschreibung für die Konfiguration angegeben.</span><span class="sxs-lookup"><span data-stu-id="2e8ee-125">This example re-enables the **MaintenanceShell** session configuration and specifies a new security descriptor for the configuration.</span></span>

```powershell
$sddl = "O:NSG:BAD:P(A;;GXGWGR;;;BA)(A;;GAGR;;;S-1-5-21-123456789-188441444-3100496)S:P"
Enable-PSSessionConfiguration -Name MaintenanceShell -SecurityDescriptorSDDL $sddl
```

## <span data-ttu-id="2e8ee-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2e8ee-126">PARAMETERS</span></span>

### <span data-ttu-id="2e8ee-127">-Force</span><span class="sxs-lookup"><span data-stu-id="2e8ee-127">-Force</span></span>

<span data-ttu-id="2e8ee-128">Gibt an, dass Sie vom Cmdlet nicht zur Bestätigung aufgefordert werden, und startet den WinRM-Dienst ohne Aufforderung neu.</span><span class="sxs-lookup"><span data-stu-id="2e8ee-128">Indicates that the cmdlet does not prompt you for confirmation, and restarts the WinRM service without prompting.</span></span> <span data-ttu-id="2e8ee-129">Durch Neustarten des Diensts wird die Konfigurationsänderung übernommen.</span><span class="sxs-lookup"><span data-stu-id="2e8ee-129">Restarting the service makes the configuration change effective.</span></span>

<span data-ttu-id="2e8ee-130">Um einen Neustart zu verhindern und die Aufforderung zum Neustart zu unterdrücken, verwenden Sie den **NoServiceRestart** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="2e8ee-130">To prevent a restart and suppress the restart prompt, use the **NoServiceRestart** parameter.</span></span>

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

### <span data-ttu-id="2e8ee-131">-Name</span><span class="sxs-lookup"><span data-stu-id="2e8ee-131">-Name</span></span>

<span data-ttu-id="2e8ee-132">Gibt die Namen der zu aktivierenden Sitzungskonfigurationen an.</span><span class="sxs-lookup"><span data-stu-id="2e8ee-132">Specifies the names of session configurations to enable.</span></span> <span data-ttu-id="2e8ee-133">Geben Sie einen oder mehrere Konfigurationsnamen ein.</span><span class="sxs-lookup"><span data-stu-id="2e8ee-133">Enter one or more configuration names.</span></span>
<span data-ttu-id="2e8ee-134">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="2e8ee-134">Wildcard characters are permitted.</span></span>

<span data-ttu-id="2e8ee-135">Sie können eine Zeichenfolge, die einen Konfigurations Namen oder ein Sitzungs Konfigurationsobjekt enthält, auch über die Pipeline an übergeben `Enable-PSSessionConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="2e8ee-135">You can also pipe a string that contains a configuration name or a session configuration object to `Enable-PSSessionConfiguration`.</span></span>

<span data-ttu-id="2e8ee-136">Wenn Sie diesen Parameter weglassen, `Enable-PSSessionConfiguration` aktiviert die **Microsoft. PowerShell** -Sitzungs Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="2e8ee-136">If you omit this parameter, `Enable-PSSessionConfiguration` enables the **Microsoft.PowerShell** session configuration.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="2e8ee-137">-Noservicerestart</span><span class="sxs-lookup"><span data-stu-id="2e8ee-137">-NoServiceRestart</span></span>

<span data-ttu-id="2e8ee-138">Gibt an, dass das Cmdlet den Dienst nicht neu startet.</span><span class="sxs-lookup"><span data-stu-id="2e8ee-138">Indicates that the cmdlet does not restart the service.</span></span>

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

### <span data-ttu-id="2e8ee-139">-SecurityDescriptor SDDL</span><span class="sxs-lookup"><span data-stu-id="2e8ee-139">-SecurityDescriptorSddl</span></span>

<span data-ttu-id="2e8ee-140">Gibt eine Sicherheits Beschreibung an, mit der dieses Cmdlet die Sicherheits Beschreibung für die Sitzungs Konfiguration ersetzt.</span><span class="sxs-lookup"><span data-stu-id="2e8ee-140">Specifies a security descriptor with which this cmdlet replaces the security descriptor on the session configuration.</span></span>

<span data-ttu-id="2e8ee-141">Wenn Sie diesen Parameter weglassen, `Enable-PSSessionConfiguration` Löscht nur das deny all-Element aus der Sicherheits Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="2e8ee-141">If you omit this parameter, `Enable-PSSessionConfiguration` only deletes the deny all item from the security descriptor.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2e8ee-142">-Skipnetworkprofilecheck</span><span class="sxs-lookup"><span data-stu-id="2e8ee-142">-SkipNetworkProfileCheck</span></span>

<span data-ttu-id="2e8ee-143">Gibt an, dass dieses Cmdlet die Sitzungs Konfiguration aktiviert, wenn sich der Computer in einem öffentlichen Netzwerk befindet.</span><span class="sxs-lookup"><span data-stu-id="2e8ee-143">Indicates that this cmdlet enables the session configuration when the computer is on a public network.</span></span> <span data-ttu-id="2e8ee-144">Dieser Parameter aktiviert eine Firewallregel für öffentliche Netzwerke, die den Remotezugriff nur von Computern im selben lokalen Subnetz zulässt.</span><span class="sxs-lookup"><span data-stu-id="2e8ee-144">This parameter enables a firewall rule for public networks that allows remote access only from computers in the same local subnet.</span></span> <span data-ttu-id="2e8ee-145">Standardmäßig `Enable-PSSessionConfiguration` schlägt in einem öffentlichen Netzwerk fehl.</span><span class="sxs-lookup"><span data-stu-id="2e8ee-145">By default, `Enable-PSSessionConfiguration` fails on a public network.</span></span>

<span data-ttu-id="2e8ee-146">Dieser Parameter ist für Client Versionen des Windows-Betriebssystems vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="2e8ee-146">This parameter is designed for client versions of the Windows operating system.</span></span> <span data-ttu-id="2e8ee-147">Server Versionen des Windows-Betriebssystems verfügen über eine lokale subnetzfirewallregel für öffentliche Netzwerke.</span><span class="sxs-lookup"><span data-stu-id="2e8ee-147">Server versions of the Windows operating system have a local subnet firewall rule for public networks.</span></span> <span data-ttu-id="2e8ee-148">Wenn die Firewallregel für das lokale Subnetz jedoch auf einer Server Version des Windows-Betriebssystems deaktiviert ist, wird Sie durch diesen Parameter erneut aktiviert.</span><span class="sxs-lookup"><span data-stu-id="2e8ee-148">However, if the local subnet firewall rule is disabled on a server version of the Windows operating system, this parameter re-enables it.</span></span>

<span data-ttu-id="2e8ee-149">Verwenden Sie das `Set-NetFirewallRule` Cmdlet im Netsecurity-Modul, um die Einschränkung für das lokale Subnetz zu entfernen und den Remote Zugriff von allen Standorten in öffentlichen Netzwerken aus zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="2e8ee-149">To remove the local subnet restriction and enable remote access from all locations on public networks, use the `Set-NetFirewallRule` cmdlet in the NetSecurity module.</span></span> <span data-ttu-id="2e8ee-150">Weitere Informationen finden Sie unter `Enable-PSRemoting`.</span><span class="sxs-lookup"><span data-stu-id="2e8ee-150">For more information, see `Enable-PSRemoting`.</span></span>

<span data-ttu-id="2e8ee-151">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="2e8ee-151">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="2e8ee-152">-Confirm</span><span class="sxs-lookup"><span data-stu-id="2e8ee-152">-Confirm</span></span>

<span data-ttu-id="2e8ee-153">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="2e8ee-153">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="2e8ee-154">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="2e8ee-154">-WhatIf</span></span>

<span data-ttu-id="2e8ee-155">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2e8ee-155">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="2e8ee-156">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2e8ee-156">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="2e8ee-157">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="2e8ee-157">CommonParameters</span></span>

<span data-ttu-id="2e8ee-158">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2e8ee-158">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2e8ee-159">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2e8ee-159">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2e8ee-160">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="2e8ee-160">INPUTS</span></span>

### <span data-ttu-id="2e8ee-161">Microsoft. PowerShell. Commands. pssessionconfigurationcommands # pssessionconfiguration, System. String</span><span class="sxs-lookup"><span data-stu-id="2e8ee-161">Microsoft.PowerShell.Commands.PSSessionConfigurationCommands#PSSessionConfiguration, System.String</span></span>

<span data-ttu-id="2e8ee-162">Sie können ein Sitzungs Konfigurationsobjekt oder eine Zeichenfolge, die den Namen einer Sitzungs Konfiguration enthält, über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="2e8ee-162">You can pipe a session configuration object or a string that contains the name of a session configuration to this cmdlet.</span></span>

## <span data-ttu-id="2e8ee-163">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="2e8ee-163">OUTPUTS</span></span>

### <span data-ttu-id="2e8ee-164">Keine</span><span class="sxs-lookup"><span data-stu-id="2e8ee-164">None</span></span>

<span data-ttu-id="2e8ee-165">Dieses Cmdlet gibt keine Objekte zurück.</span><span class="sxs-lookup"><span data-stu-id="2e8ee-165">This cmdlet does not return any objects.</span></span>

## <span data-ttu-id="2e8ee-166">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="2e8ee-166">NOTES</span></span>

<span data-ttu-id="2e8ee-167">Um dieses Cmdlet verwenden zu können, müssen Sie PowerShell mit der Option **als Administrator ausführen** starten.</span><span class="sxs-lookup"><span data-stu-id="2e8ee-167">To use this cmdlet, you must start PowerShell by using the **Run as administrator** option.</span></span>

## <span data-ttu-id="2e8ee-168">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="2e8ee-168">RELATED LINKS</span></span>

[<span data-ttu-id="2e8ee-169">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="2e8ee-169">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="2e8ee-170">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="2e8ee-170">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="2e8ee-171">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="2e8ee-171">New-PSSessionConfigurationFile</span></span>](New-PSSessionConfigurationFile.md)

[<span data-ttu-id="2e8ee-172">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="2e8ee-172">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="2e8ee-173">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="2e8ee-173">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="2e8ee-174">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="2e8ee-174">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="2e8ee-175">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="2e8ee-175">Test-PSSessionConfigurationFile</span></span>](Test-PSSessionConfigurationFile.md)

[<span data-ttu-id="2e8ee-176">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="2e8ee-176">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="2e8ee-177">WSMan-Anbieter</span><span class="sxs-lookup"><span data-stu-id="2e8ee-177">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="2e8ee-178">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="2e8ee-178">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)

[<span data-ttu-id="2e8ee-179">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="2e8ee-179">about_Session_Configuration_Files</span></span>](About/about_Session_Configuration_Files.md)
