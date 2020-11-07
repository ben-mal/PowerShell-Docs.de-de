---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/disable-pssessionconfiguration?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSSessionConfiguration
ms.openlocfilehash: 075071f83e8443d186dcc99e13fa102504dc23af
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2020
ms.locfileid: "94345526"
---
# <span data-ttu-id="ed43b-103">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="ed43b-103">Disable-PSSessionConfiguration</span></span>

## <span data-ttu-id="ed43b-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="ed43b-104">SYNOPSIS</span></span>
<span data-ttu-id="ed43b-105">Deaktiviert die Sitzungskonfigurationen auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="ed43b-105">Disables session configurations on the local computer.</span></span>

## <span data-ttu-id="ed43b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ed43b-106">SYNTAX</span></span>

```
Disable-PSSessionConfiguration [[-Name] <String[]>] [-Force] [-NoServiceRestart] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="ed43b-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ed43b-107">DESCRIPTION</span></span>

<span data-ttu-id="ed43b-108">Das- `Disable-PSSessionConfiguration` Cmdlet deaktiviert die Sitzungs Konfigurationen auf dem lokalen Computer, wodurch verhindert wird, dass die Sitzungs Konfigurationen von allen Benutzern verwendet werden, um auf dem lokalen Computerbenutzer verwaltete Sitzungen ( **pssessions** ) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ed43b-108">The `Disable-PSSessionConfiguration` cmdlet disables session configurations on the local computer, which prevents all users from using the session configurations to create a user-managed sessions ( **PSSessions** ) on the local computer.</span></span> <span data-ttu-id="ed43b-109">Dies ist ein erweitertes Cmdlet für Systemadministratoren, die benutzerdefinierte Sitzungskonfigurationen für ihre Benutzer verwalten.</span><span class="sxs-lookup"><span data-stu-id="ed43b-109">This is an advanced cmdlet that is designed to be used by system administrators to manage customized session configurations for their users.</span></span>

<span data-ttu-id="ed43b-110">Ab PowerShell 3,0 `Disable-PSSessionConfiguration` legt das Cmdlet die **aktivierte** Einstellung der Sitzungs Konfiguration ( `WSMan:\localhost\Plugins\<SessionConfiguration>\Enabled` ) auf "false" fest.</span><span class="sxs-lookup"><span data-stu-id="ed43b-110">Starting in PowerShell 3.0, the `Disable-PSSessionConfiguration` cmdlet sets the **Enabled** setting of the session configuration (`WSMan:\localhost\Plugins\<SessionConfiguration>\Enabled`) to False.</span></span>

<span data-ttu-id="ed43b-111">In PowerShell 2,0 fügt das `Disable-PSSessionConfiguration` Cmdlet der Sicherheits Beschreibung eines oder mehrerer registrierter Sitzungs Konfigurationen einen **Deny_All** Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="ed43b-111">In PowerShell 2.0, the `Disable-PSSessionConfiguration` cmdlet adds a **Deny_All** entry to the security descriptor of one or more registered session configurations.</span></span>

<span data-ttu-id="ed43b-112">Ohne Parameter `Disable-PSSessionConfiguration` deaktiviert die **Microsoft. PowerShell** -Konfiguration, die für Sitzungen verwendete Standardkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="ed43b-112">Without parameters, `Disable-PSSessionConfiguration` disables the **Microsoft.PowerShell** configuration, the default configuration used for sessions.</span></span> <span data-ttu-id="ed43b-113">Wenn der Benutzer keine andere Konfiguration angibt, werden lokale und remote Benutzer effektiv daran gehindert, eine Sitzung zu erstellen, die eine Verbindung mit dem Computer herstellt.</span><span class="sxs-lookup"><span data-stu-id="ed43b-113">Unless the user specifies a different configuration, both local and remote users are effectively prevented from creating any sessions that connect to the computer.</span></span>

<span data-ttu-id="ed43b-114">Um alle Sitzungs Konfigurationen auf dem Computer zu deaktivieren, verwenden Sie `Disable-PSRemoting` .</span><span class="sxs-lookup"><span data-stu-id="ed43b-114">To disable all session configurations on the computer, use `Disable-PSRemoting`.</span></span>

## <span data-ttu-id="ed43b-115">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="ed43b-115">EXAMPLES</span></span>

### <span data-ttu-id="ed43b-116">Beispiel 1: Deaktivieren der Standardkonfiguration</span><span class="sxs-lookup"><span data-stu-id="ed43b-116">Example 1: Disable the default configuration</span></span>

<span data-ttu-id="ed43b-117">In diesem Beispiel wird die Microsoft. PowerShell-Sitzungs Konfiguration deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="ed43b-117">This example disables the Microsoft.PowerShell session configuration.</span></span>

```powershell
Disable-PSSessionConfiguration
```

### <span data-ttu-id="ed43b-118">Beispiel 2: Deaktivieren aller registrierten Sitzungs Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="ed43b-118">Example 2: Disable all registered session configurations</span></span>

<span data-ttu-id="ed43b-119">In diesem Beispiel werden alle registrierten Sitzungs Konfigurationen auf dem Computer deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="ed43b-119">This example disables all registered session configurations on the computer.</span></span>

```powershell
Disable-PSSessionConfiguration -Name *
```

### <span data-ttu-id="ed43b-120">Beispiel 3: Deaktivieren von Sitzungs Konfigurationen nach Namen</span><span class="sxs-lookup"><span data-stu-id="ed43b-120">Example 3: Disable session configurations by name</span></span>

<span data-ttu-id="ed43b-121">In diesem Beispiel werden alle Sitzungs Konfigurationen, deren Namen mit Microsoft beginnen, deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="ed43b-121">This example disables all session configurations that have names that begin with Microsoft.</span></span> <span data-ttu-id="ed43b-122">Mit dem **Force** -Parameter werden alle Benutzer Aufforderungen des Cmdlets unterdrückt.</span><span class="sxs-lookup"><span data-stu-id="ed43b-122">The **Force** parameter suppresses all user prompts from the cmdlet.</span></span>

```powershell
Disable-PSSessionConfiguration -Name Microsoft* -Force
```

### <span data-ttu-id="ed43b-123">Beispiel 4: Deaktivieren von Sitzungs Konfigurationen mithilfe der Pipeline</span><span class="sxs-lookup"><span data-stu-id="ed43b-123">Example 4: Disable session configurations by using the pipeline</span></span>

<span data-ttu-id="ed43b-124">In diesem Beispiel werden die Sitzungs Konfigurationen " **maintenanceshell** " und " **adminshell** " deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="ed43b-124">This example disables the **MaintenanceShell** and **AdminShell** session configurations.</span></span> <span data-ttu-id="ed43b-125">Der Pipeline Operator (|) sendet die Ergebnisse eines `Get-PSSessionConfiguration` an `Disable-PSSessionConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="ed43b-125">The pipeline operator (|) sends the results of a `Get-PSSessionConfiguration` to `Disable-PSSessionConfiguration`.</span></span>

```powershell
Get-PSSessionConfiguration -Name MaintenanceShell, AdminShell | Disable-PSSessionConfiguration
```

### <span data-ttu-id="ed43b-126">Beispiel 5: Auswirkungen der Deaktivierung einer Sitzungs Konfiguration</span><span class="sxs-lookup"><span data-stu-id="ed43b-126">Example 5: Effects of disabling a session configuration</span></span>

<span data-ttu-id="ed43b-127">In diesem Beispiel werden die Berechtigungen vor und nach der Ausführung `Disable-PSSessionConfiguration` sowie die Auswirkung der Deaktivierung einer Sitzungs Konfiguration veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="ed43b-127">This example shows the permissions before and after running `Disable-PSSessionConfiguration` and the effect of disabling a session configuration.</span></span>

```
PS> Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto

Name                   Permission
----                   ----------
MaintenanceShell       BUILTIN\Administrators AccessAllowed
microsoft.powershell   BUILTIN\Administrators AccessAllowed
microsoft.powershell32 BUILTIN\Administrators AccessAllowed

PS> Disable-PSSessionConfiguration -Name MaintenanceShell -Force
PS> Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto

Name                   Permission
----                   ----------
MaintenanceShell       Everyone AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell   BUILTIN\Administrators AccessAllowed
microsoft.powershell32 BUILTIN\Administrators AccessAllowed

PS> New-PSSession -ComputerName localhost -ConfigurationName MaintenanceShell

[localhost] Connecting to remote server failed with the following error message : Access is denied.
For more information, see the about_Remote_Troubleshooting Help topic.
+ CategoryInfo          : OpenError: (System.Manageme....RemoteRunspace:RemoteRunspace) [], PSRemotingTransportException
+ FullyQualifiedErrorId : PSSessionOpenFailed
```

> [!NOTE]
> <span data-ttu-id="ed43b-128">Durch das Deaktivieren der Konfiguration wird nicht verhindert, dass Sie die Konfiguration mithilfe des `Set-PSSessionConfiguration` Cmdlets ändern.</span><span class="sxs-lookup"><span data-stu-id="ed43b-128">Disabling the configuration does not prevent you from changing the configuration using the `Set-PSSessionConfiguration` cmdlet.</span></span> <span data-ttu-id="ed43b-129">Es wird nur die Verwendung der Konfiguration verhindert.</span><span class="sxs-lookup"><span data-stu-id="ed43b-129">It only prevents use of the configuration.</span></span>

## <span data-ttu-id="ed43b-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ed43b-130">PARAMETERS</span></span>

### <span data-ttu-id="ed43b-131">-Force</span><span class="sxs-lookup"><span data-stu-id="ed43b-131">-Force</span></span>

<span data-ttu-id="ed43b-132">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="ed43b-132">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="ed43b-133">-Name</span><span class="sxs-lookup"><span data-stu-id="ed43b-133">-Name</span></span>

<span data-ttu-id="ed43b-134">Gibt ein Array von Namen der zu deaktivierenden Sitzungs Konfigurationen an.</span><span class="sxs-lookup"><span data-stu-id="ed43b-134">Specifies an array of names of session configurations to disable.</span></span> <span data-ttu-id="ed43b-135">Geben Sie einen oder mehrere Konfigurationsnamen ein.</span><span class="sxs-lookup"><span data-stu-id="ed43b-135">Enter one or more configuration names.</span></span> <span data-ttu-id="ed43b-136">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="ed43b-136">Wildcard characters are permitted.</span></span> <span data-ttu-id="ed43b-137">Sie können eine Zeichenfolge, die einen Konfigurations Namen oder ein Sitzungs Konfigurationsobjekt enthält, auch über die Pipeline an übergeben `Disable-PSSessionConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="ed43b-137">You can also pipe a string that contains a configuration name or a session configuration object to `Disable-PSSessionConfiguration`.</span></span>

<span data-ttu-id="ed43b-138">Wenn Sie diesen Parameter weglassen, wird `Disable-PSSessionConfiguration` die Microsoft. PowerShell-Sitzungs Konfiguration von deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="ed43b-138">If you omit this parameter, `Disable-PSSessionConfiguration` disables the Microsoft.PowerShell session configuration.</span></span>

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

### <span data-ttu-id="ed43b-139">-Noservicerestart</span><span class="sxs-lookup"><span data-stu-id="ed43b-139">-NoServiceRestart</span></span>

<span data-ttu-id="ed43b-140">Wird verwendet, um den Neustart des WSMAN-Dienstanbieter zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="ed43b-140">Used to prevent the restart of the WSMan service.</span></span> <span data-ttu-id="ed43b-141">Es ist nicht erforderlich, den Dienst neu zu starten, um die Konfiguration zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="ed43b-141">It is not necessary to restart the service to disable the configuration.</span></span>

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

### <span data-ttu-id="ed43b-142">-Confirm</span><span class="sxs-lookup"><span data-stu-id="ed43b-142">-Confirm</span></span>

<span data-ttu-id="ed43b-143">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="ed43b-143">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="ed43b-144">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="ed43b-144">-WhatIf</span></span>

<span data-ttu-id="ed43b-145">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ed43b-145">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="ed43b-146">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ed43b-146">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="ed43b-147">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ed43b-147">CommonParameters</span></span>

<span data-ttu-id="ed43b-148">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ed43b-148">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ed43b-149">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ed43b-149">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ed43b-150">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="ed43b-150">INPUTS</span></span>

### <span data-ttu-id="ed43b-151">Microsoft. PowerShell. Commands. pssessionconfigurationcommands # pssessionconfiguration, System. String</span><span class="sxs-lookup"><span data-stu-id="ed43b-151">Microsoft.PowerShell.Commands.PSSessionConfigurationCommands#PSSessionConfiguration, System.String</span></span>

<span data-ttu-id="ed43b-152">Sie können ein Sitzungs Konfigurationsobjekt oder eine Zeichenfolge, die den Namen einer Sitzungs Konfiguration enthält, über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="ed43b-152">You can pipe a session configuration object or a string that contains the name of a session configuration to this cmdlet.</span></span>

## <span data-ttu-id="ed43b-153">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="ed43b-153">OUTPUTS</span></span>

### <span data-ttu-id="ed43b-154">Keine</span><span class="sxs-lookup"><span data-stu-id="ed43b-154">None</span></span>

<span data-ttu-id="ed43b-155">Dieses Cmdlet gibt keine Objekte zurück.</span><span class="sxs-lookup"><span data-stu-id="ed43b-155">This cmdlet does not return any objects.</span></span>

## <span data-ttu-id="ed43b-156">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="ed43b-156">NOTES</span></span>

<span data-ttu-id="ed43b-157">Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ed43b-157">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="ed43b-158">Zum Ausführen dieses Cmdlets müssen Sie PowerShell mit der Option **als Administrator ausführen** starten.</span><span class="sxs-lookup"><span data-stu-id="ed43b-158">To run this cmdlet you must start PowerShell by using the **Run as administrator** option.</span></span>

## <span data-ttu-id="ed43b-159">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="ed43b-159">RELATED LINKS</span></span>

[<span data-ttu-id="ed43b-160">Enable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="ed43b-160">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="ed43b-161">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="ed43b-161">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="ed43b-162">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="ed43b-162">New-PSSessionConfigurationFile</span></span>](New-PSSessionConfigurationFile.md)

[<span data-ttu-id="ed43b-163">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="ed43b-163">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="ed43b-164">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="ed43b-164">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="ed43b-165">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="ed43b-165">Test-PSSessionConfigurationFile</span></span>](Test-PSSessionConfigurationFile.md)

[<span data-ttu-id="ed43b-166">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="ed43b-166">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="ed43b-167">WSMan-Anbieter</span><span class="sxs-lookup"><span data-stu-id="ed43b-167">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="ed43b-168">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="ed43b-168">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)

[<span data-ttu-id="ed43b-169">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="ed43b-169">about_Session_Configuration_Files</span></span>](About/about_Session_Configuration_Files.md)
