---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enable-pssessionconfiguration?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSSessionConfiguration
ms.openlocfilehash: 86650f33f376ccb7d1428836c9d0070e749cf0ee
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599440"
---
# <span data-ttu-id="ac467-102">Enable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="ac467-102">Enable-PSSessionConfiguration</span></span>

## <span data-ttu-id="ac467-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="ac467-103">SYNOPSIS</span></span>
<span data-ttu-id="ac467-104">Aktiviert die Sitzungskonfigurationen auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="ac467-104">Enables the session configurations on the local computer.</span></span>

## <span data-ttu-id="ac467-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ac467-105">SYNTAX</span></span>

```
Enable-PSSessionConfiguration [[-Name] <String[]>] [-Force] [-SecurityDescriptorSddl <String>]
 [-SkipNetworkProfileCheck] [-NoServiceRestart] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="ac467-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ac467-106">DESCRIPTION</span></span>

<span data-ttu-id="ac467-107">Mit dem- `Enable-PSSessionConfiguration` Cmdlet werden registrierte Sitzungs Konfigurationen aktiviert, die deaktiviert wurden, wie z `Disable-PSSessionConfiguration` . b. die-oder- `Disable-PSRemoting` Cmdlets oder der **AccessMode** -Parameter von `Register-PSSessionConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="ac467-107">The `Enable-PSSessionConfiguration` cmdlet enables registered session configurations that have been disabled, such as by using the `Disable-PSSessionConfiguration` or `Disable-PSRemoting` cmdlets, or the **AccessMode** parameter of `Register-PSSessionConfiguration`.</span></span> <span data-ttu-id="ac467-108">Dies ist ein erweitertes Cmdlet für Systemadministratoren, die benutzerdefinierte Sitzungskonfigurationen für ihre Benutzer verwalten.</span><span class="sxs-lookup"><span data-stu-id="ac467-108">This is an advanced cmdlet that is designed to be used by system administrators to manage customized session configurations for their users.</span></span>

<span data-ttu-id="ac467-109">Ohne Parameter `Enable-PSSessionConfiguration` aktiviert die **Microsoft. PowerShell** -Konfiguration, bei der es sich um die Standardkonfiguration handelt, die für Sitzungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ac467-109">Without parameters, `Enable-PSSessionConfiguration` enables the **Microsoft.PowerShell** configuration, which is the default configuration that is used for sessions.</span></span>

<span data-ttu-id="ac467-110">`Enable-PSSessionConfiguration` entfernt die **Deny_All** Einstellung aus der Sicherheits Beschreibung der betroffenen Sitzungs Konfigurationen, aktiviert den Listener, der Anforderungen an eine beliebige IP-Adresse annimmt, und startet den WinRM-Dienst neu.</span><span class="sxs-lookup"><span data-stu-id="ac467-110">`Enable-PSSessionConfiguration` removes the **Deny_All** setting from the security descriptor of the affected session configurations, turns on the listener that accepts requests on any IP address, and restarts the WinRM service.</span></span> <span data-ttu-id="ac467-111">Ab PowerShell 3,0 wird `Enable-PSSessionConfiguration` auch der Wert der **aktivierten** Eigenschaft der Sitzungs Konfiguration ( `WSMan:\<computer>\PlugIn\<SessionConfigurationName>\Enabled` ) auf true festgelegt.</span><span class="sxs-lookup"><span data-stu-id="ac467-111">Beginning in PowerShell 3.0, `Enable-PSSessionConfiguration` also sets the value of the **Enabled** property of the session configuration (`WSMan:\<computer>\PlugIn\<SessionConfigurationName>\Enabled`) to True.</span></span> <span data-ttu-id="ac467-112">`Enable-PSSessionConfiguration`Die  `AccessMode=Local` Sicherheits beschreibungeinstellung Network_Deny_All (), die nur Benutzern des lokalen Computers die Verwendung der Sitzungs Konfiguration ermöglicht, wird von jedoch nicht entfernt oder geändert.</span><span class="sxs-lookup"><span data-stu-id="ac467-112">However, `Enable-PSSessionConfiguration` does not remove or change the **Network_Deny_All** (`AccessMode=Local`) security descriptor setting that allows only users of the local computer to use to the session configuration.</span></span>

## <span data-ttu-id="ac467-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="ac467-113">EXAMPLES</span></span>

### <span data-ttu-id="ac467-114">Beispiel 1: Erneutes Aktivieren der Standard Sitzung</span><span class="sxs-lookup"><span data-stu-id="ac467-114">Example 1: Re-enable the default session</span></span>

<span data-ttu-id="ac467-115">In diesem Beispiel wird die **Microsoft. PowerShell** -Standard Sitzungs Konfiguration auf dem Computer erneut aktiviert.</span><span class="sxs-lookup"><span data-stu-id="ac467-115">This example re-enables the **Microsoft.PowerShell** default session configuration on the computer.</span></span>

```powershell
Enable-PSSessionConfiguration
```

### <span data-ttu-id="ac467-116">Beispiel 2: Erneutes Aktivieren der angegebenen Sitzungen</span><span class="sxs-lookup"><span data-stu-id="ac467-116">Example 2: Re-enable specified sessions</span></span>

<span data-ttu-id="ac467-117">In diesem Beispiel werden die **maintenanceshell** -und **adminshell** -Sitzungs Konfigurationen auf dem Computer erneut aktiviert.</span><span class="sxs-lookup"><span data-stu-id="ac467-117">This example re-enables the **MaintenanceShell** and **AdminShell** session configurations on the computer.</span></span>

```powershell
Enable-PSSessionConfiguration -Name MaintenanceShell, AdminShell
```

### <span data-ttu-id="ac467-118">Beispiel 3: Erneutes Aktivieren der gesamten Sitzungen</span><span class="sxs-lookup"><span data-stu-id="ac467-118">Example 3: Re-enable the all sessions</span></span>

<span data-ttu-id="ac467-119">In diesem Beispiel werden alle Sitzungs Konfigurationen auf dem Computer erneut aktiviert.</span><span class="sxs-lookup"><span data-stu-id="ac467-119">This example re-enables all session configurations on the computer.</span></span> <span data-ttu-id="ac467-120">Diese Befehle sind gleichwertig.</span><span class="sxs-lookup"><span data-stu-id="ac467-120">These commands are equivalent.</span></span>
<span data-ttu-id="ac467-121">Daher können Sie beide verwenden.</span><span class="sxs-lookup"><span data-stu-id="ac467-121">Therefore, you can use either.</span></span>

```powershell
Enable-PSSessionConfiguration -Name *
Get-PSSessionConfiguration | Enable-PSSessionConfiguration
```

<span data-ttu-id="ac467-122">`Enable-PSSessionConfiguration` generiert keine Fehler, wenn Sie eine bereits aktivierte Sitzungs Konfiguration aktivieren.</span><span class="sxs-lookup"><span data-stu-id="ac467-122">`Enable-PSSessionConfiguration` does not generate an error if you enable a session configuration that is already enabled.</span></span>

### <span data-ttu-id="ac467-123">Beispiel 4: Erneutes Aktivieren einer Sitzung und Angeben einer neuen Sicherheits Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ac467-123">Example 4: Re-enable a session and specify a new security descriptor</span></span>

<span data-ttu-id="ac467-124">In diesem Beispiel wird die **maintenanceshell** -Sitzungs Konfiguration erneut aktiviert und eine neue Sicherheits Beschreibung für die Konfiguration angegeben.</span><span class="sxs-lookup"><span data-stu-id="ac467-124">This example re-enables the **MaintenanceShell** session configuration and specifies a new security descriptor for the configuration.</span></span>

```powershell
$sddl = "O:NSG:BAD:P(A;;GXGWGR;;;BA)(A;;GAGR;;;S-1-5-21-123456789-188441444-3100496)S:P"
Enable-PSSessionConfiguration -Name MaintenanceShell -SecurityDescriptorSDDL $sddl
```

## <span data-ttu-id="ac467-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ac467-125">PARAMETERS</span></span>

### <span data-ttu-id="ac467-126">-Force</span><span class="sxs-lookup"><span data-stu-id="ac467-126">-Force</span></span>

<span data-ttu-id="ac467-127">Gibt an, dass Sie vom Cmdlet nicht zur Bestätigung aufgefordert werden, und startet den WinRM-Dienst ohne Aufforderung neu.</span><span class="sxs-lookup"><span data-stu-id="ac467-127">Indicates that the cmdlet does not prompt you for confirmation, and restarts the WinRM service without prompting.</span></span> <span data-ttu-id="ac467-128">Durch Neustarten des Diensts wird die Konfigurationsänderung übernommen.</span><span class="sxs-lookup"><span data-stu-id="ac467-128">Restarting the service makes the configuration change effective.</span></span>

<span data-ttu-id="ac467-129">Um einen Neustart zu verhindern und die Aufforderung zum Neustart zu unterdrücken, verwenden Sie den **NoServiceRestart**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="ac467-129">To prevent a restart and suppress the restart prompt, use the **NoServiceRestart** parameter.</span></span>

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

### <span data-ttu-id="ac467-130">-Name</span><span class="sxs-lookup"><span data-stu-id="ac467-130">-Name</span></span>

<span data-ttu-id="ac467-131">Gibt die Namen der zu aktivierenden Sitzungskonfigurationen an.</span><span class="sxs-lookup"><span data-stu-id="ac467-131">Specifies the names of session configurations to enable.</span></span> <span data-ttu-id="ac467-132">Geben Sie einen oder mehrere Konfigurationsnamen ein.</span><span class="sxs-lookup"><span data-stu-id="ac467-132">Enter one or more configuration names.</span></span>
<span data-ttu-id="ac467-133">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="ac467-133">Wildcard characters are permitted.</span></span>

<span data-ttu-id="ac467-134">Sie können eine Zeichenfolge, die einen Konfigurations Namen oder ein Sitzungs Konfigurationsobjekt enthält, auch über die Pipeline an übergeben `Enable-PSSessionConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="ac467-134">You can also pipe a string that contains a configuration name or a session configuration object to `Enable-PSSessionConfiguration`.</span></span>

<span data-ttu-id="ac467-135">Wenn Sie diesen Parameter weglassen, `Enable-PSSessionConfiguration` aktiviert die **Microsoft. PowerShell** -Sitzungs Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="ac467-135">If you omit this parameter, `Enable-PSSessionConfiguration` enables the **Microsoft.PowerShell** session configuration.</span></span>

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

### <span data-ttu-id="ac467-136">-Noservicerestart</span><span class="sxs-lookup"><span data-stu-id="ac467-136">-NoServiceRestart</span></span>

<span data-ttu-id="ac467-137">Gibt an, dass das Cmdlet den Dienst nicht neu startet.</span><span class="sxs-lookup"><span data-stu-id="ac467-137">Indicates that the cmdlet does not restart the service.</span></span>

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

### <span data-ttu-id="ac467-138">-SecurityDescriptor SDDL</span><span class="sxs-lookup"><span data-stu-id="ac467-138">-SecurityDescriptorSddl</span></span>

<span data-ttu-id="ac467-139">Gibt eine Sicherheits Beschreibung an, mit der dieses Cmdlet die Sicherheits Beschreibung für die Sitzungs Konfiguration ersetzt.</span><span class="sxs-lookup"><span data-stu-id="ac467-139">Specifies a security descriptor with which this cmdlet replaces the security descriptor on the session configuration.</span></span>

<span data-ttu-id="ac467-140">Wenn Sie diesen Parameter weglassen, `Enable-PSSessionConfiguration` Löscht nur das deny all-Element aus der Sicherheits Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="ac467-140">If you omit this parameter, `Enable-PSSessionConfiguration` only deletes the deny all item from the security descriptor.</span></span>

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

### <span data-ttu-id="ac467-141">-Skipnetworkprofilecheck</span><span class="sxs-lookup"><span data-stu-id="ac467-141">-SkipNetworkProfileCheck</span></span>

<span data-ttu-id="ac467-142">Gibt an, dass dieses Cmdlet die Sitzungs Konfiguration aktiviert, wenn sich der Computer in einem öffentlichen Netzwerk befindet.</span><span class="sxs-lookup"><span data-stu-id="ac467-142">Indicates that this cmdlet enables the session configuration when the computer is on a public network.</span></span> <span data-ttu-id="ac467-143">Dieser Parameter aktiviert eine Firewallregel für öffentliche Netzwerke, die den Remotezugriff nur von Computern im selben lokalen Subnetz zulässt.</span><span class="sxs-lookup"><span data-stu-id="ac467-143">This parameter enables a firewall rule for public networks that allows remote access only from computers in the same local subnet.</span></span> <span data-ttu-id="ac467-144">Standardmäßig `Enable-PSSessionConfiguration` schlägt in einem öffentlichen Netzwerk fehl.</span><span class="sxs-lookup"><span data-stu-id="ac467-144">By default, `Enable-PSSessionConfiguration` fails on a public network.</span></span>

<span data-ttu-id="ac467-145">Dieser Parameter ist für Client Versionen des Windows-Betriebssystems vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="ac467-145">This parameter is designed for client versions of the Windows operating system.</span></span> <span data-ttu-id="ac467-146">Server Versionen des Windows-Betriebssystems verfügen über eine lokale subnetzfirewallregel für öffentliche Netzwerke.</span><span class="sxs-lookup"><span data-stu-id="ac467-146">Server versions of the Windows operating system have a local subnet firewall rule for public networks.</span></span> <span data-ttu-id="ac467-147">Wenn die Firewallregel für das lokale Subnetz jedoch auf einer Server Version des Windows-Betriebssystems deaktiviert ist, wird Sie durch diesen Parameter erneut aktiviert.</span><span class="sxs-lookup"><span data-stu-id="ac467-147">However, if the local subnet firewall rule is disabled on a server version of the Windows operating system, this parameter re-enables it.</span></span>

<span data-ttu-id="ac467-148">Verwenden Sie das `Set-NetFirewallRule` Cmdlet im Netsecurity-Modul, um die Einschränkung für das lokale Subnetz zu entfernen und den Remote Zugriff von allen Standorten in öffentlichen Netzwerken aus zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="ac467-148">To remove the local subnet restriction and enable remote access from all locations on public networks, use the `Set-NetFirewallRule` cmdlet in the NetSecurity module.</span></span> <span data-ttu-id="ac467-149">Weitere Informationen finden Sie unter `Enable-PSRemoting`.</span><span class="sxs-lookup"><span data-stu-id="ac467-149">For more information, see `Enable-PSRemoting`.</span></span>

<span data-ttu-id="ac467-150">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ac467-150">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="ac467-151">-Confirm</span><span class="sxs-lookup"><span data-stu-id="ac467-151">-Confirm</span></span>

<span data-ttu-id="ac467-152">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="ac467-152">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="ac467-153">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="ac467-153">-WhatIf</span></span>

<span data-ttu-id="ac467-154">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ac467-154">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="ac467-155">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ac467-155">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="ac467-156">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ac467-156">CommonParameters</span></span>

<span data-ttu-id="ac467-157">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ac467-157">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ac467-158">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ac467-158">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ac467-159">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="ac467-159">INPUTS</span></span>

### <span data-ttu-id="ac467-160">Microsoft. PowerShell. Commands. pssessionconfigurationcommands # pssessionconfiguration, System. String</span><span class="sxs-lookup"><span data-stu-id="ac467-160">Microsoft.PowerShell.Commands.PSSessionConfigurationCommands#PSSessionConfiguration, System.String</span></span>

<span data-ttu-id="ac467-161">Sie können ein Sitzungs Konfigurationsobjekt oder eine Zeichenfolge, die den Namen einer Sitzungs Konfiguration enthält, über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="ac467-161">You can pipe a session configuration object or a string that contains the name of a session configuration to this cmdlet.</span></span>

## <span data-ttu-id="ac467-162">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="ac467-162">OUTPUTS</span></span>

### <span data-ttu-id="ac467-163">Keine</span><span class="sxs-lookup"><span data-stu-id="ac467-163">None</span></span>

<span data-ttu-id="ac467-164">Dieses Cmdlet gibt keine Objekte zurück.</span><span class="sxs-lookup"><span data-stu-id="ac467-164">This cmdlet does not return any objects.</span></span>

## <span data-ttu-id="ac467-165">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="ac467-165">NOTES</span></span>

<span data-ttu-id="ac467-166">Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ac467-166">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="ac467-167">Um dieses Cmdlet verwenden zu können, müssen Sie PowerShell mit der Option **als Administrator ausführen** starten.</span><span class="sxs-lookup"><span data-stu-id="ac467-167">To use this cmdlet, you must start PowerShell by using the **Run as administrator** option.</span></span>

## <span data-ttu-id="ac467-168">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="ac467-168">RELATED LINKS</span></span>

[<span data-ttu-id="ac467-169">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="ac467-169">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="ac467-170">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="ac467-170">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="ac467-171">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="ac467-171">New-PSSessionConfigurationFile</span></span>](New-PSSessionConfigurationFile.md)

[<span data-ttu-id="ac467-172">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="ac467-172">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="ac467-173">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="ac467-173">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="ac467-174">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="ac467-174">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="ac467-175">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="ac467-175">Test-PSSessionConfigurationFile</span></span>](Test-PSSessionConfigurationFile.md)

[<span data-ttu-id="ac467-176">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="ac467-176">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="ac467-177">WSMan-Anbieter</span><span class="sxs-lookup"><span data-stu-id="ac467-177">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="ac467-178">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="ac467-178">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)

[<span data-ttu-id="ac467-179">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="ac467-179">about_Session_Configuration_Files</span></span>](About/about_Session_Configuration_Files.md)
