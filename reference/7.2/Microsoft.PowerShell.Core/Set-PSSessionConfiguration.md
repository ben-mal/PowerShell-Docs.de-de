---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/set-pssessionconfiguration?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSSessionConfiguration
ms.openlocfilehash: c3c3c0bbb0436ef2e6857adc35f83e627d03f4b9
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597577"
---
# <span data-ttu-id="e0ed0-102">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="e0ed0-102">Set-PSSessionConfiguration</span></span>

## <span data-ttu-id="e0ed0-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="e0ed0-103">SYNOPSIS</span></span>
<span data-ttu-id="e0ed0-104">Ändert die Eigenschaften einer registrierten Sitzungskonfiguration.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-104">Changes the properties of a registered session configuration.</span></span>

## <span data-ttu-id="e0ed0-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e0ed0-105">SYNTAX</span></span>

### <span data-ttu-id="e0ed0-106">Nameparameterset (Standard)</span><span class="sxs-lookup"><span data-stu-id="e0ed0-106">NameParameterSet (Default)</span></span>

```
Set-PSSessionConfiguration [-Name] <String> [-ApplicationBase <String>] [-RunAsCredential <PSCredential>]
 [-ThreadOptions <PSThreadOptions>] [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess]
 [-StartupScript <String>] [-MaximumReceivedDataSizePerCommandMB <Double>]
 [-MaximumReceivedObjectSizeMB <Double>] [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI]
 [-Force] [-NoServiceRestart] [-PSVersion <Version>] [-SessionTypeOption <PSSessionTypeOption>]
 [-TransportOption <PSTransportOption>] [-ModulesToImport <Object[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="e0ed0-107">Assemblynameparameterset</span><span class="sxs-lookup"><span data-stu-id="e0ed0-107">AssemblyNameParameterSet</span></span>

```
Set-PSSessionConfiguration [-Name] <String> [-AssemblyName] <String> [-ApplicationBase <String>]
 [-ConfigurationTypeName] <String> [-RunAsCredential <PSCredential>] [-ThreadOptions <PSThreadOptions>]
 [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess] [-StartupScript <String>]
 [-MaximumReceivedDataSizePerCommandMB <Double>] [-MaximumReceivedObjectSizeMB <Double>]
 [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI] [-Force] [-NoServiceRestart]
 [-PSVersion <Version>] [-SessionTypeOption <PSSessionTypeOption>] [-TransportOption <PSTransportOption>]
 [-ModulesToImport <Object[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="e0ed0-108">Sessionconfigurationfile</span><span class="sxs-lookup"><span data-stu-id="e0ed0-108">SessionConfigurationFile</span></span>

```
Set-PSSessionConfiguration [-Name] <String> [-RunAsCredential <PSCredential>]
 [-ThreadOptions <PSThreadOptions>] [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess]
 [-StartupScript <String>] [-MaximumReceivedDataSizePerCommandMB <Double>]
 [-MaximumReceivedObjectSizeMB <Double>] [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI]
 [-Force] [-NoServiceRestart] [-TransportOption <PSTransportOption>] -Path <String> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="e0ed0-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e0ed0-109">DESCRIPTION</span></span>

<span data-ttu-id="e0ed0-110">Mit dem- `Set-PSSessionConfiguration` Cmdlet werden die Eigenschaften der Sitzungs Konfigurationen auf dem lokalen Computer geändert.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-110">The `Set-PSSessionConfiguration` cmdlet changes the properties of the session configurations on the local computer.</span></span>

<span data-ttu-id="e0ed0-111">Verwenden Sie den **Name**-Parameter, um die Sitzungskonfiguration zu identifizieren, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-111">Use the **Name** parameter to identify the session configuration that you want to change.</span></span> <span data-ttu-id="e0ed0-112">Verwenden Sie die anderen Parameter, um neue Werte für die Eigenschaften der Sitzungskonfiguration anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-112">Use the other parameters to specify new values for the properties of the session configuration.</span></span> <span data-ttu-id="e0ed0-113">Um einen Eigenschafts Wert aus der Konfiguration zu löschen und den Standardwert zu verwenden, geben Sie eine leere Zeichenfolge ("") oder den Wert `$Null` für den entsprechenden Parameter ein.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-113">To delete a property value from the configuration, and use the default value, enter an empty string ("") or a value of `$Null` for the corresponding parameter.</span></span>

<span data-ttu-id="e0ed0-114">Ab PowerShell 3,0 können Sie eine Sitzungs Konfigurationsdatei verwenden, um eine Sitzungs Konfiguration zu definieren.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-114">Starting in PowerShell 3.0, you can use a session configuration file to define a session configuration.</span></span> <span data-ttu-id="e0ed0-115">Diese Funktion bietet eine einfache und sichtbare Methode für das Festlegen und Ändern der Eigenschaften von Sitzungen, die die Sitzungskonfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-115">This feature provides a simple and discoverable method for setting and changing the properties of sessions that use the session configuration.</span></span> <span data-ttu-id="e0ed0-116">Um eine Sitzungs Konfigurationsdatei anzugeben, verwenden Sie den **path** -Parameter von `Set-PSSessionConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="e0ed0-116">To specify a session configuration file, use the **Path** parameter of `Set-PSSessionConfiguration`.</span></span> <span data-ttu-id="e0ed0-117">Weitere Informationen zu Sitzungs Konfigurationsdateien finden Sie unter [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span><span class="sxs-lookup"><span data-stu-id="e0ed0-117">For information about session configuration files, see [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span></span>
<span data-ttu-id="e0ed0-118">Weitere Informationen zum Erstellen und Ändern einer Sitzungs Konfigurationsdatei finden Sie unter dem- `New-PSSessionConfigurationFile` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-118">For information about how to create and modify a session configuration file, see the `New-PSSessionConfigurationFile` cmdlet.</span></span>

<span data-ttu-id="e0ed0-119">Sitzungs Konfigurationen definieren die Umgebung von Remote Sitzungen (**pssessions**), die eine Verbindung mit dem lokalen Computer herstellen.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-119">Session configurations define the environment of remote sessions (**PSSessions**) that connect to the local computer.</span></span> <span data-ttu-id="e0ed0-120">Jede **PSSession** verwendet eine Sitzungs Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-120">Every **PSSession** uses a session configuration.</span></span> <span data-ttu-id="e0ed0-121">Die Sitzungs Konfiguration bestimmt die Funktionen der **PSSession**, wie z. b. die Module, die in der Sitzung verfügbar sind, die Cmdlets, die ausgeführt werden dürfen, den Sprachmodus, Kontingente und Timeouts.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-121">The session configuration determines the features of the **PSSession**, such as the modules that are available in the session, the cmdlets that are permitted to run, the language mode, quotas, and timeouts.</span></span> <span data-ttu-id="e0ed0-122">Die Sicherheits Beschreibung der Sitzungs Konfiguration bestimmt, wer die Sitzungs Konfiguration verwenden kann, um eine Verbindung mit dem lokalen Computer herzustellen.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-122">The security descriptor of the session configuration determines who can use the session configuration to connect to the local computer.</span></span> <span data-ttu-id="e0ed0-123">Weitere Informationen zu Sitzungs Konfigurationen finden Sie unter [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="e0ed0-123">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

<span data-ttu-id="e0ed0-124">Um die Eigenschaften einer Sitzungs Konfiguration anzuzeigen, verwenden Sie das `Get-PSSessionConfiguration` Cmdlet oder den WSMAN-Anbieter.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-124">To see the properties of a session configuration, use the `Get-PSSessionConfiguration` cmdlet or the WSMan Provider.</span></span> <span data-ttu-id="e0ed0-125">Weitere Informationen zum WSMAN-Anbieter erhalten Sie, wenn Sie eingeben `Get-Help WSMan` .</span><span class="sxs-lookup"><span data-stu-id="e0ed0-125">For more information about the WSMan Provider, type `Get-Help WSMan`.</span></span>

## <span data-ttu-id="e0ed0-126">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="e0ed0-126">EXAMPLES</span></span>

### <span data-ttu-id="e0ed0-127">Beispiel 1: Erstellen und Ändern einer Sitzungs Konfiguration</span><span class="sxs-lookup"><span data-stu-id="e0ed0-127">Example 1: Create and change a session configuration</span></span>

<span data-ttu-id="e0ed0-128">Dieses Beispiel zeigt, wie Sie ein Startskript aus einer Konfiguration hinzufügen und daraus entfernen.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-128">This example shows how to add and remove a startup script from a configuration.</span></span>

<span data-ttu-id="e0ed0-129">Mit dem ersten Befehl wird die **adminshell** -Konfiguration erstellt.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-129">The first command creates the **AdminShell** configuration.</span></span> <span data-ttu-id="e0ed0-130">Mit dem zweiten Befehl wird das Skript der Konfiguration hinzugefügt `AdminConfig.ps1` .</span><span class="sxs-lookup"><span data-stu-id="e0ed0-130">The second command adds the `AdminConfig.ps1` script to the configuration.</span></span> <span data-ttu-id="e0ed0-131">Die Änderung ist wirksam, wenn Sie **WinRM** neu starten.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-131">The change is effective when you restart **WinRM**.</span></span>
<span data-ttu-id="e0ed0-132">Der dritte Befehl entfernt das `AdminConfig.ps1` Skript aus der Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-132">The third command removes the `AdminConfig.ps1` script from the configuration.</span></span>

```powershell
Register-PSSessionConfiguration -Name "AdminShell" -AssemblyName "C:\Shells\AdminShell.dll" -ConfigurationTypeName "AdminClass"
Set-PSSessionConfiguration -Name "AdminShell" -StartupScript "AdminConfig.ps1"
Set-PSSessionConfiguration -Name "AdminShell" -StartupScript $Null
```

### <span data-ttu-id="e0ed0-133">Beispiel 2: Anzeigen von Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="e0ed0-133">Example 2: Display results</span></span>

<span data-ttu-id="e0ed0-134">In diesem Beispiel wird der Wert der **maximumreceivedobjectsizemb** -Eigenschaft auf 20 erhöht.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-134">This example increases the value of the **MaximumReceivedObjectSizeMB** property to 20.</span></span> <span data-ttu-id="e0ed0-135">Mit diesem Befehl werden Sie außerdem aufgefordert, den **WinRM** -Dienst neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-135">This command also prompts you to restart the **WinRM** service.</span></span> <span data-ttu-id="e0ed0-136">Die Änderung wird erst wirksam, wenn der **WinRM** -Dienst neu gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-136">The change is not effective until the **WinRM** service is restarted.</span></span>

```powershell
Set-PSSessionConfiguration -Name "IncObj" -MaximumReceivedObjectSizeMB 20
```

```Output
WSManConfig: Microsoft.WSMan.Management\WSMan::localhost\Plugin\IncObj\InitializationParameters

ParamName                       ParamValue
---------                       ----------
psmaximumreceivedobjectsizemb   20

"Restart WinRM service"
WinRM service need to be restarted to make the changes effective. Do you want to run the command "restart-service winrm"?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): y
```

### <span data-ttu-id="e0ed0-137">Beispiel 3: Anzeigen der Ergebnisse auf verschiedene Weise</span><span class="sxs-lookup"><span data-stu-id="e0ed0-137">Example 3: Display results in different ways</span></span>

<span data-ttu-id="e0ed0-138">In diesem Beispiel `Set-PSSessionConfiguration` ändert das Startskript in der **maintenanceshell** -Sitzungs Konfiguration in `Maintenance.ps1` .</span><span class="sxs-lookup"><span data-stu-id="e0ed0-138">In this example, `Set-PSSessionConfiguration` changes the startup script in the **MaintenanceShell** session configuration to `Maintenance.ps1`.</span></span> <span data-ttu-id="e0ed0-139">In der Ausgabe wird die Änderung angezeigt, und Sie werden aufgefordert, den **WinRM** -Dienst neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-139">The output shows the change and prompts you to restart the **WinRM** service.</span></span> <span data-ttu-id="e0ed0-140">Die Antwort ist „y“ (Ja).</span><span class="sxs-lookup"><span data-stu-id="e0ed0-140">The response is "y" (yes).</span></span>

<span data-ttu-id="e0ed0-141">`Get-PSSessionConfiguration` Ruft die **maintenanceshell** -Sitzungs Konfiguration ab.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-141">`Get-PSSessionConfiguration` gets the **MaintenanceShell** session configuration.</span></span> <span data-ttu-id="e0ed0-142">Der Pipeline Operator (|) sendet die Ergebnisse des Befehls an `Format-List` , wodurch alle Eigenschaften des Konfigurations Objekts in einer Liste angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-142">The pipeline operator (|) sends the results of the command to `Format-List`, which displays all the properties of the configuration object in a list.</span></span> <span data-ttu-id="e0ed0-143">Als Nächstes zeigen wir mithilfe des WSMAN-Anbieters die Initialisierungs Parameter für die **maintenanceshell** -Konfiguration an.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-143">Next, using the WSMan provider, we view the initialization parameters for the **MaintenanceShell** configuration.</span></span> <span data-ttu-id="e0ed0-144">`Get-ChildItem` (Alias `dir` ) Ruft die untergeordneten Elemente im **initializationparameters** -Knoten für das **maintenanceshell** -Plug-in ab.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-144">`Get-ChildItem` (alias `dir`) gets the child items in the **InitializationParameters** node for the **MaintenanceShell** plug-in.</span></span> <span data-ttu-id="e0ed0-145">Weitere Informationen zum WSMAN-Anbieter erhalten Sie, wenn Sie eingeben `Get-Help wsman` .</span><span class="sxs-lookup"><span data-stu-id="e0ed0-145">For more information about the WSMan provider, type `Get-Help wsman`.</span></span>

```powershell
Set-PSSessionConfiguration -Name "MaintenanceShell" -StartupScript "C:\ps-test\Maintenance.ps1"
```

```Output
WSManConfig: Microsoft.WSMan.Management\WSMan::localhost\Plugin\MaintenanceShell\InitializationParameters

ParamName            ParamValue
---------            ----------
startupscript        c:\ps-test\Mainte...

"Restart WinRM service"
WinRM service need to be restarted to make the changes effective. Do you want to run
the command "restart-service winrm"?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): y

```

```powershell
Get-PSSessionConfiguration MaintenanceShell | Format-List -Property *
```

```Output
xmlns            : http://schemas.microsoft.com/wbem/wsman/1/config/PluginConfiguration
Name             : MaintenanceShell
Filename         : %windir%\system32\pwrshplugin.dll
SDKVersion       : 1
XmlRenderingType : text
lang             : en-US
PSVersion        : 2.0
startupscript    : c:\ps-test\Maintenance.ps1
ResourceUri      : http://schemas.microsoft.com/powershell/MaintenanceShell
SupportsOptions  : true
ExactMatch       : true
Capability       : {Shell}
Permission       :
```

```powershell
dir WSMan:\localhost\Plugin\MaintenanceShell\InitializationParameters
```

```Output
ParamName     ParamValue
---------     ----------
PSVersion     2.0
startupscript c:\ps-test\Maintenance.ps1
```

## <span data-ttu-id="e0ed0-146">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e0ed0-146">PARAMETERS</span></span>

### <span data-ttu-id="e0ed0-147">-AccessMode</span><span class="sxs-lookup"><span data-stu-id="e0ed0-147">-AccessMode</span></span>

<span data-ttu-id="e0ed0-148">Aktiviert und deaktiviert die Sitzungskonfiguration und bestimmt, ob sie für Remote- oder lokale Sitzungen auf dem Computer verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-148">Enables and disables the session configuration and determines whether it can be used for remote or local sessions on the computer.</span></span> <span data-ttu-id="e0ed0-149">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="e0ed0-149">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="e0ed0-150">Deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-150">Disabled.</span></span> <span data-ttu-id="e0ed0-151">Deaktiviert die Sitzungskonfiguration.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-151">Disables the session configuration.</span></span> <span data-ttu-id="e0ed0-152">Sie kann nicht für Remote- oder lokalen Zugriff auf den Computer verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-152">It cannot be used for remote or local access to the computer.</span></span> <span data-ttu-id="e0ed0-153">Dieser Wert legt die **aktivierte** Eigenschaft der Sitzungs Konfiguration ( `WSMan:\<ComputerName>\PlugIn\<SessionConfigurationName>\Enabled` ) auf " **false**" fest.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-153">This value sets the **Enabled** property of the session configuration (`WSMan:\<ComputerName>\PlugIn\<SessionConfigurationName>\Enabled`) to **False**.</span></span>
- <span data-ttu-id="e0ed0-154">Lokal.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-154">Local.</span></span> <span data-ttu-id="e0ed0-155">Fügt der Sicherheitsbeschreibung der Sitzungskonfiguration einen **Network_Deny_All**-Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-155">Adds a **Network_Deny_All** entry to security descriptor of the session configuration.</span></span>
  <span data-ttu-id="e0ed0-156">Benutzer des lokalen Computers können die Sitzungs Konfiguration verwenden, um eine lokale Loopback Sitzung auf demselben Computer zu erstellen, aber Remote Benutzern wird der Zugriff verweigert.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-156">Users of the local computer can use the session configuration to create a local loopback session on the same computer, but remote users are denied access.</span></span>
- <span data-ttu-id="e0ed0-157">Remote.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-157">Remote.</span></span> <span data-ttu-id="e0ed0-158">Entfernt die Einträge **Deny_All** und **Network_Deny_All** aus den Sicherheitsbeschreibungen der Sitzungskonfiguration.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-158">Removes **Deny_All** and **Network_Deny_All** entries from the security descriptors of the session configuration.</span></span> <span data-ttu-id="e0ed0-159">Benutzer von lokalen Computern und Remotecomputern können die Sitzungskonfiguration verwenden, um Sitzungen zu erstellen und um Befehle auf diesem Computer auszuführen.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-159">Users of local and remote computers can use the session configuration to create sessions and run commands on this computer.</span></span>

<span data-ttu-id="e0ed0-160">Der Standardwert ist **Remote**.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-160">The default value is **Remote**.</span></span>

<span data-ttu-id="e0ed0-161">Andere Cmdlets können den Wert dieses Parameters später überschreiben.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-161">Other cmdlets can override the value of this parameter later.</span></span> <span data-ttu-id="e0ed0-162">Beispielsweise aktiviert das `Enable-PSRemoting` Cmdlet alle Sitzungs Konfigurationen auf dem Computer und ermöglicht den Remote Zugriff auf diese, und das `Disable-PSRemoting` Cmdlet gestattet nur den lokalen Zugriff auf alle Sitzungs Konfigurationen auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-162">For example, the `Enable-PSRemoting` cmdlet enables all session configurations on the computer and permits remote access to them, and the `Disable-PSRemoting` cmdlet permits only local access to all session configurations on the computer.</span></span>

<span data-ttu-id="e0ed0-163">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-163">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSessionConfigurationAccessMode
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, Local, Remote

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e0ed0-164">-ApplicationBase</span><span class="sxs-lookup"><span data-stu-id="e0ed0-164">-ApplicationBase</span></span>

<span data-ttu-id="e0ed0-165">Gibt den Pfad der \* **Assemblydatei** (. dll) an, die im Wert des AssemblyName-Parameters angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-165">Specifies the path of the assembly file (\*.dll) that is specified in the value of the **AssemblyName** parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: NameParameterSet, AssemblyNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e0ed0-166">-AssemblyName</span><span class="sxs-lookup"><span data-stu-id="e0ed0-166">-AssemblyName</span></span>

<span data-ttu-id="e0ed0-167">Gibt den Assemblynamen an.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-167">Specifies the assembly name.</span></span> <span data-ttu-id="e0ed0-168">Dieses Cmdlet erstellt eine Sitzungs Konfiguration basierend auf einer Klasse, die in einer Assembly definiert ist.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-168">This cmdlet creates a session configuration based on a class that is defined in an assembly.</span></span>

<span data-ttu-id="e0ed0-169">Geben Sie den Dateinamen oder den vollständigen Pfad einer Assembly. dll-Datei ein, die eine Sitzungs Konfiguration definiert.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-169">Enter the filename or full path of an assembly .dll file that defines a session configuration.</span></span> <span data-ttu-id="e0ed0-170">Wenn Sie nur den Dateinamen eingeben, können Sie den Pfad im Wert des **ApplicationBase** -Parameters eingeben.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-170">If you enter only the file name, you can enter the path in the value of the **ApplicationBase** parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: AssemblyNameParameterSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e0ed0-171">-Configurationtyname</span><span class="sxs-lookup"><span data-stu-id="e0ed0-171">-ConfigurationTypeName</span></span>

<span data-ttu-id="e0ed0-172">Gibt den Typ der Sitzungskonfiguration an, der in der Assembly im **AssemblyName**-Parameter definiert ist.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-172">Specifies the type of the session configuration that is defined in the assembly in the **AssemblyName** parameter.</span></span> <span data-ttu-id="e0ed0-173">Der Typ, den Sie angeben, muss die **System.Management.Automation.Remoting.PSSessionConfiguration** Klasse implementieren.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-173">The type that you specify must implement the **System.Management.Automation.Remoting.PSSessionConfiguration** class.</span></span>

<span data-ttu-id="e0ed0-174">Dieser Parameter ist erforderlich, wenn Sie den Namen einer Assembly angeben.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-174">This parameter is required when you specify an assembly name.</span></span>

```yaml
Type: System.String
Parameter Sets: AssemblyNameParameterSet
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e0ed0-175">-Force</span><span class="sxs-lookup"><span data-stu-id="e0ed0-175">-Force</span></span>

<span data-ttu-id="e0ed0-176">Unterdrückt alle Benutzer Aufforderungen und startet den **WinRM** -Dienst ohne Aufforderung neu.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-176">Suppresses all user prompts, and restarts the **WinRM** service without prompting.</span></span> <span data-ttu-id="e0ed0-177">Durch Neustarten des Diensts wird die Konfigurationsänderung übernommen.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-177">Restarting the service makes the configuration change effective.</span></span>

<span data-ttu-id="e0ed0-178">Um einen Neustart zu verhindern und die Aufforderung zum Neustart zu unterdrücken, verwenden Sie den **NoServiceRestart**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-178">To prevent a restart and suppress the restart prompt, use the **NoServiceRestart** parameter.</span></span>

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

### <span data-ttu-id="e0ed0-179">-Maximumreceiveddatasizepercommandmb</span><span class="sxs-lookup"><span data-stu-id="e0ed0-179">-MaximumReceivedDataSizePerCommandMB</span></span>

<span data-ttu-id="e0ed0-180">Gibt den Grenzwert für die Datenmenge an, die in jedem einzelnen Remote Befehl an diesen Computer gesendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-180">Specifies the limit on the amount of data that can be sent to this computer in any single remote command.</span></span> <span data-ttu-id="e0ed0-181">Geben Sie die Datengröße in Megabyte (MB) ein.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-181">Enter the data size in megabytes (MB).</span></span> <span data-ttu-id="e0ed0-182">Der Standardwert ist 50 MB.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-182">The default is 50 MB.</span></span>

<span data-ttu-id="e0ed0-183">Wenn eine Datengrößen Beschränkung im Konfigurationstyp definiert ist, der im **configurationtypame** -Parameter angegeben ist, wird der Grenzwert im Konfigurationstyp verwendet.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-183">If a data size limit is defined in the configuration type that is specified in the **ConfigurationTypeName** parameter, the limit in the configuration type is used.</span></span> <span data-ttu-id="e0ed0-184">Der Wert dieses Parameters wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-184">The value of this parameter is ignored.</span></span>

```yaml
Type: System.Nullable`1[System.Double]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e0ed0-185">-Maximumreceivedobjectsizemb</span><span class="sxs-lookup"><span data-stu-id="e0ed0-185">-MaximumReceivedObjectSizeMB</span></span>

<span data-ttu-id="e0ed0-186">Gibt die Grenzwerte für die Datenmenge an, die in jedem einzelnen Objekt an diesen Computer gesendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-186">Specifies the limits on the amount of data that can be sent to this computer in any single object.</span></span>
<span data-ttu-id="e0ed0-187">Geben Sie die Datengröße in Megabyte ein.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-187">Enter the data size in megabytes.</span></span> <span data-ttu-id="e0ed0-188">Der Standardwert ist 10 MB.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-188">The default is 10 MB.</span></span>

<span data-ttu-id="e0ed0-189">Wenn eine Objektgrößen Beschränkung im Konfigurationstyp definiert ist, der im **configurationtypame** -Parameter angegeben ist, wird der Grenzwert im Konfigurationstyp verwendet.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-189">If an object size limit is defined in the configuration type that is specified in the **ConfigurationTypeName** parameter, the limit in the configuration type is used.</span></span> <span data-ttu-id="e0ed0-190">Der Wert dieses Parameters wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-190">The value of this parameter is ignored.</span></span>

```yaml
Type: System.Nullable`1[System.Double]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e0ed0-191">-Modulestoimport</span><span class="sxs-lookup"><span data-stu-id="e0ed0-191">-ModulesToImport</span></span>

<span data-ttu-id="e0ed0-192">Gibt die Module und Snap-ins an, die automatisch in Sitzungen importiert werden, die die Sitzungskonfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-192">Specifies the modules and snap-ins that are automatically imported into sessions that use the session configuration.</span></span> <span data-ttu-id="e0ed0-193">Geben Sie die Namen der Module und Snap-Ins ein.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-193">Enter the module and snap-in names.</span></span>

<span data-ttu-id="e0ed0-194">Standardmäßig wird nur das **Microsoft. PowerShell. Core** -Snap-in in Sitzungen importiert, aber wenn die Cmdlets nicht ausgeschlossen sind, können Sie die `Import-Module` -und-Add-PSSnapin-Cmdlets verwenden, um der Sitzung Module und Snap-Ins hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-194">By default, only the **Microsoft.PowerShell.Core** snap-in is imported into sessions, but unless the cmdlets are excluded, you can use the `Import-Module` and Add-PSSnapin cmdlets to add modules and snap-ins to the session.</span></span>

<span data-ttu-id="e0ed0-195">Die in diesem Parameterwert angegebenen Module werden in Ergänzungen zu Modulen importiert, die in der Sitzungs Konfigurationsdatei () angegeben sind `New-PSSessionConfigurationFile` .</span><span class="sxs-lookup"><span data-stu-id="e0ed0-195">The modules specified in this parameter value are imported in additions to modules specified in the session configuration file (`New-PSSessionConfigurationFile`).</span></span> <span data-ttu-id="e0ed0-196">Einstellungen in der Sitzungskonfigurationsdatei können jedoch die von Modulen exportierten Befehle ausblenden oder verhindern, dass Benutzer sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-196">However, settings in the session configuration file can hide the commands exported by modules or prevent users from using them.</span></span>

<span data-ttu-id="e0ed0-197">Die in diesem Parameterwert angegebenen Module ersetzen die Liste der Module, die mit dem **modulestoimport** -Parameter des `Register-PSSessionConfiguration` Cmdlets angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-197">The modules specified in this parameter value replace the list of modules specified by using the **ModulesToImport** parameter of the `Register-PSSessionConfiguration` cmdlet.</span></span>

<span data-ttu-id="e0ed0-198">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-198">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: NameParameterSet, AssemblyNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e0ed0-199">-Name</span><span class="sxs-lookup"><span data-stu-id="e0ed0-199">-Name</span></span>

<span data-ttu-id="e0ed0-200">Gibt den Namen der Sitzungskonfiguration an, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-200">Specifies the name of the session configuration that you want to change.</span></span>

<span data-ttu-id="e0ed0-201">Sie können diesen Parameter verwenden, um den Namen der Sitzungskonfiguration zu ändern.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-201">You cannot use this parameter to change the name of the session configuration.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="e0ed0-202">-Noservicerestart</span><span class="sxs-lookup"><span data-stu-id="e0ed0-202">-NoServiceRestart</span></span>

<span data-ttu-id="e0ed0-203">Der **WinRM** -Dienst wird nicht neu gestartet, und die Aufforderung zum Neustarten des Dienstanbieter wird unterdrückt.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-203">Does not restart the **WinRM** service, and suppresses the prompt to restart the service.</span></span>

<span data-ttu-id="e0ed0-204">Wenn Sie Ausführen `Set-PSSessionConfiguration` , werden Sie standardmäßig aufgefordert, den **WinRM** -Dienst neu zu starten, damit die neue Sitzungs Konfiguration wirksam wird.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-204">By default, when you run `Set-PSSessionConfiguration`, you are prompted to restart the **WinRM** service to make the new session configuration effective.</span></span> <span data-ttu-id="e0ed0-205">Bis der **WinRM** -Dienst neu gestartet wird, ist die neue Sitzungs Konfiguration nicht wirksam.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-205">Until the **WinRM** service is restarted, the new session configuration is not effective.</span></span>

<span data-ttu-id="e0ed0-206">Um den **WinRM** -Dienst ohne Aufforderung neu zu starten, verwenden Sie den **Force** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-206">To restart the **WinRM** service without prompting, use the **Force** parameter.</span></span> <span data-ttu-id="e0ed0-207">Verwenden Sie das-Cmdlet, um den **WinRM** -Dienst manuell neu zu starten `Restart-Service` .</span><span class="sxs-lookup"><span data-stu-id="e0ed0-207">To restart the **WinRM** service manually, use the `Restart-Service` cmdlet.</span></span>

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

### <span data-ttu-id="e0ed0-208">-Path</span><span class="sxs-lookup"><span data-stu-id="e0ed0-208">-Path</span></span>

<span data-ttu-id="e0ed0-209">Gibt den Pfad einer Sitzungs Konfigurationsdatei (. PSSC) an, z. b. eine, die vom `New-PSSessionConfigurationFile` Cmdlet erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-209">Specifies the path of a session configuration file (.pssc), such as one created by the `New-PSSessionConfigurationFile` cmdlet.</span></span> <span data-ttu-id="e0ed0-210">Wenn Sie den Pfad weglassen, ist die Standardeinstellung das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-210">If you omit the path, the default is the current directory.</span></span>

<span data-ttu-id="e0ed0-211">Informationen dazu, wie Sie eine Sitzungs Konfigurationsdatei ändern, finden Sie im Hilfethema für das `New-PSSessionConfigurationFile` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-211">For information about how to modify a session configuration file, see the help topic for the `New-PSSessionConfigurationFile` cmdlet.</span></span>

<span data-ttu-id="e0ed0-212">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-212">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: SessionConfigurationFile
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e0ed0-213">-Psversion</span><span class="sxs-lookup"><span data-stu-id="e0ed0-213">-PSVersion</span></span>

<span data-ttu-id="e0ed0-214">Gibt die Version von PowerShell in Sitzungen an, die diese Sitzungs Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-214">Specifies the version of PowerShell in sessions that use this session configuration.</span></span>

<span data-ttu-id="e0ed0-215">Der Wert dieses Parameters hat Vorrang vor den Wert des **PowerShellVersion**-Schlüssels in der Sitzungskonfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-215">The value of this parameter takes precedence over the value of the **PowerShellVersion** key in the session configuration file.</span></span>

<span data-ttu-id="e0ed0-216">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-216">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Version
Parameter Sets: NameParameterSet, AssemblyNameParameterSet
Aliases: PowerShellVersion

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e0ed0-217">-Runascredential</span><span class="sxs-lookup"><span data-stu-id="e0ed0-217">-RunAsCredential</span></span>

<span data-ttu-id="e0ed0-218">Gibt Anmelde Informationen für Befehle in der Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-218">Specifies credentials for commands in the session.</span></span> <span data-ttu-id="e0ed0-219">Standardmäßig werden Befehle mit den Berechtigungen des aktuellen Benutzers ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-219">By default, commands run with the permissions of the current user.</span></span>

<span data-ttu-id="e0ed0-220">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-220">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e0ed0-221">-SecurityDescriptor SDDL</span><span class="sxs-lookup"><span data-stu-id="e0ed0-221">-SecurityDescriptorSddl</span></span>

<span data-ttu-id="e0ed0-222">Gibt eine andere Security Descriptor Definition Language (SDDL)-Zeichenfolge für die Konfiguration an.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-222">Specifies a different Security Descriptor Definition Language (SDDL) string for the configuration.</span></span>

<span data-ttu-id="e0ed0-223">Diese Zeichenfolge bestimmt die Berechtigungen, die erforderlich sind, um die Konfiguration für die neue Sitzung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-223">This string determines the permissions that are required to use the new session configuration.</span></span> <span data-ttu-id="e0ed0-224">Um eine Sitzungs Konfiguration in einer Sitzung zu verwenden, müssen die Benutzer mindestens über die Berechtigung Execute (aufrufen) für die Konfiguration verfügen.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-224">To use a session configuration in a session, users must have at least Execute(Invoke) permission for the configuration.</span></span>

<span data-ttu-id="e0ed0-225">Um die Standard Sicherheits Beschreibung für die Konfiguration zu verwenden, geben Sie eine leere Zeichenfolge ("") oder einen Wert von ein `$Null` .</span><span class="sxs-lookup"><span data-stu-id="e0ed0-225">To use the default security descriptor for the configuration, enter an empty string ("") or a value of `$Null`.</span></span> <span data-ttu-id="e0ed0-226">Der Standardwert ist die Stamm-SDDL im WSMan:-Laufwerk.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-226">The default is the root SDDL in the WSMan: drive.</span></span>

<span data-ttu-id="e0ed0-227">Wenn die Sicherheits Beschreibung Komplex ist, sollten Sie die Verwendung des **showsecuritydescriptorui** -Parameters anstelle dieses Parameters in Erwägung gezogen.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-227">If the security descriptor is complex, consider using the **ShowSecurityDescriptorUI** parameter instead of this one.</span></span> <span data-ttu-id="e0ed0-228">Sie können nicht beide Parameter im selben Befehl verwenden.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-228">You cannot use both parameters in the same command.</span></span>

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

### <span data-ttu-id="e0ed0-229">-Sessiontypeoption</span><span class="sxs-lookup"><span data-stu-id="e0ed0-229">-SessionTypeOption</span></span>

<span data-ttu-id="e0ed0-230">Gibt typspezifische Optionen für die Sitzungs Konfiguration an.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-230">Specifies type-specific options for the session configuration.</span></span> <span data-ttu-id="e0ed0-231">Geben Sie ein "Session TYPE Options"-Objekt ein, z. b. das vom Cmdlet zurückgegebene **psworkflowexecutionoption** -Objekt `New-PSWorkflowExecutionOption` .</span><span class="sxs-lookup"><span data-stu-id="e0ed0-231">Enter a session type options object, such as the **PSWorkflowExecutionOption** object that the `New-PSWorkflowExecutionOption` cmdlet returns.</span></span>

<span data-ttu-id="e0ed0-232">Die Optionen der Sitzungen, die die Sitzungskonfiguration verwenden, werden durch die Werte der Sitzungsoptionen und die Sitzungskonfigurationsoptionen bestimmt.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-232">The options of sessions that use the session configuration are determined by the values of session options and the session configuration options.</span></span> <span data-ttu-id="e0ed0-233">Sofern nicht angegeben, haben in der Sitzung festgelegte Optionen, z. b. mit dem `New-PSSessionOption` Cmdlet, Vorrang vor den in der Sitzungs Konfiguration festgelegten Optionen.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-233">Unless specified, options set in the session, such as by using the `New-PSSessionOption` cmdlet, take precedence over options set in the session configuration.</span></span> <span data-ttu-id="e0ed0-234">Die Sitzungsoptionswerte dürfen aber nicht die in der Sitzungskonfiguration festgelegten Höchstwerte überschreiten.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-234">However, session option values cannot exceed maximum values set in the session configuration.</span></span>

<span data-ttu-id="e0ed0-235">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-235">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSSessionTypeOption
Parameter Sets: NameParameterSet, AssemblyNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e0ed0-236">-Showsecuritydescriptor UI</span><span class="sxs-lookup"><span data-stu-id="e0ed0-236">-ShowSecurityDescriptorUI</span></span>

<span data-ttu-id="e0ed0-237">Gibt an, dass dieses Cmdlet ein Eigenschaften Blatt ist, das Ihnen hilft, eine neue SDDL für die Sitzungs Konfiguration zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-237">Indicates that this cmdlet a property sheet that helps you create a new SDDL for the session configuration.</span></span> <span data-ttu-id="e0ed0-238">Das Eigenschaften Blatt wird angezeigt, nachdem Sie den `Set-PSSessionConfiguration` Befehl ausgeführt und den **WinRM** -Dienst neu gestartet haben.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-238">The property sheet appears after you run the `Set-PSSessionConfiguration` command and then restart the **WinRM** service.</span></span>

<span data-ttu-id="e0ed0-239">Beachten Sie beim Festlegen der Berechtigungen für die Konfiguration, dass die Benutzer mindestens über die Berechtigung Ausführen (aufrufen) verfügen müssen, um die Sitzungs Konfiguration in einer Sitzung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-239">When you set permissions to the configuration, remember that users must have at least Execute(Invoke) permission to use the session configuration in a session.</span></span>

<span data-ttu-id="e0ed0-240">Sie können den **SecurityDescriptorSDDL**-Parameter und diesen Parameter nicht im selben Befehl verwenden.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-240">You cannot use the **SecurityDescriptorSDDL** parameter and this parameter in the same command.</span></span>

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

### <span data-ttu-id="e0ed0-241">-Startupscript</span><span class="sxs-lookup"><span data-stu-id="e0ed0-241">-StartupScript</span></span>

<span data-ttu-id="e0ed0-242">Gibt das Startskript für die Konfiguration an.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-242">Specifies the startup script for the configuration.</span></span> <span data-ttu-id="e0ed0-243">Geben Sie den voll qualifizierten Pfad eines PowerShell-Skripts ein.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-243">Enter the fully qualified path of a PowerShell script.</span></span> <span data-ttu-id="e0ed0-244">Das angegebene Skript wird in der neuen Sitzung ausgeführt, die die Sitzungskonfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-244">The specified script runs in the new session that uses the session configuration.</span></span>

<span data-ttu-id="e0ed0-245">Zum Löschen eines Start Skripts aus einer Sitzungs Konfiguration geben Sie eine leere Zeichenfolge ("") oder einen Wert von ein `$Null` .</span><span class="sxs-lookup"><span data-stu-id="e0ed0-245">To delete a startup script from a session configuration, enter an empty string ("") or a value of `$Null`.</span></span>

<span data-ttu-id="e0ed0-246">Zur weiteren Konfiguration der Benutzersitzung können Sie ein Startskript verwenden.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-246">You can use a startup script to further configure the user session.</span></span> <span data-ttu-id="e0ed0-247">Wenn das Skript einen Fehler (auch einen Fehler ohne Abbruch) generiert, wird die Sitzung nicht erstellt, und der `New-PSSession` Befehl schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-247">If the script generates an error, even a non-terminating error, the session is not created and the `New-PSSession` command fails.</span></span>

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

### <span data-ttu-id="e0ed0-248">-Threadoptions</span><span class="sxs-lookup"><span data-stu-id="e0ed0-248">-ThreadOptions</span></span>

<span data-ttu-id="e0ed0-249">Gibt die Thread Options Einstellung in der Konfiguration an.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-249">Specifies the thread options setting in the configuration.</span></span> <span data-ttu-id="e0ed0-250">Diese Einstellung definiert, wie Threads erstellt und verwendet werden, wenn ein Befehl in der Sitzung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-250">This setting defines how threads are created and used when a command is executed in the session.</span></span> <span data-ttu-id="e0ed0-251">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="e0ed0-251">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="e0ed0-252">Standard</span><span class="sxs-lookup"><span data-stu-id="e0ed0-252">Default</span></span>
- <span data-ttu-id="e0ed0-253">Reusethread</span><span class="sxs-lookup"><span data-stu-id="e0ed0-253">ReuseThread</span></span>
- <span data-ttu-id="e0ed0-254">UseCurrentThread</span><span class="sxs-lookup"><span data-stu-id="e0ed0-254">UseCurrentThread</span></span>
- <span data-ttu-id="e0ed0-255">Usenewthread</span><span class="sxs-lookup"><span data-stu-id="e0ed0-255">UseNewThread</span></span>

<span data-ttu-id="e0ed0-256">Der Standardwert ist **usecurrentthread**.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-256">The default value is **UseCurrentThread**.</span></span>

<span data-ttu-id="e0ed0-257">Weitere Informationen finden Sie unter [psthlesoptions-Enumeration](/dotnet/api/system.management.automation.runspaces.psthreadoptions).</span><span class="sxs-lookup"><span data-stu-id="e0ed0-257">For more information, see [PSThreadOptions Enumeration](/dotnet/api/system.management.automation.runspaces.psthreadoptions).</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSThreadOptions
Parameter Sets: (All)
Aliases:
Accepted values: Default, UseNewThread, ReuseThread, UseCurrentThread

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e0ed0-258">-Transportoption</span><span class="sxs-lookup"><span data-stu-id="e0ed0-258">-TransportOption</span></span>

<span data-ttu-id="e0ed0-259">Gibt die Transport Optionen für die Sitzungs Konfiguration an.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-259">Specifies the transport options for the session configuration.</span></span> <span data-ttu-id="e0ed0-260">Geben Sie ein Transport Options Objekt ein, z. b. das **wsmanconfigurationoption** -Objekt, das vom `New-PSTransportOption` Cmdlet zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-260">Enter a transport options object, such as the **WSManConfigurationOption** object that the `New-PSTransportOption` cmdlet returns.</span></span>

<span data-ttu-id="e0ed0-261">Die Optionen der Sitzungen, die die Sitzungskonfiguration verwenden, werden durch die Werte der Sitzungsoptionen und die Sitzungskonfigurationsoptionen bestimmt.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-261">The options of sessions that use the session configuration are determined by the values of session options and the session configuration options.</span></span> <span data-ttu-id="e0ed0-262">Sofern nicht angegeben, haben in der Sitzung festgelegte Optionen, z. b. mit dem `New-PSSessionOption` Cmdlet, Vorrang vor den in der Sitzungs Konfiguration festgelegten Optionen.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-262">Unless specified, options set in the session, such as by using the `New-PSSessionOption` cmdlet, take precedence over options set in the session configuration.</span></span> <span data-ttu-id="e0ed0-263">Die Sitzungsoptionswerte dürfen aber nicht die in der Sitzungskonfiguration festgelegten Höchstwerte überschreiten.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-263">However, session option values cannot exceed maximum values set in the session configuration.</span></span>

<span data-ttu-id="e0ed0-264">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-264">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSTransportOption
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e0ed0-265">--Vorgang</span><span class="sxs-lookup"><span data-stu-id="e0ed0-265">-UseSharedProcess</span></span>

<span data-ttu-id="e0ed0-266">Verwenden Sie nur einen Prozess, um alle Sitzungen zu hosten, die vom gleichen Benutzer gestartet wurden und die gleiche Sitzungs Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-266">Use only one process to host all sessions that are started by the same user and use the same session configuration.</span></span> <span data-ttu-id="e0ed0-267">Standardmäßig wird jede Sitzung in einem eigenen Prozess gehostet.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-267">By default, each session is hosted in its own process.</span></span>

<span data-ttu-id="e0ed0-268">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-268">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="e0ed0-269">-Confirm</span><span class="sxs-lookup"><span data-stu-id="e0ed0-269">-Confirm</span></span>

<span data-ttu-id="e0ed0-270">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-270">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="e0ed0-271">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="e0ed0-271">-WhatIf</span></span>

<span data-ttu-id="e0ed0-272">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-272">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="e0ed0-273">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-273">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="e0ed0-274">-Threadapartmentstate</span><span class="sxs-lookup"><span data-stu-id="e0ed0-274">-ThreadApartmentState</span></span>

<span data-ttu-id="e0ed0-275">Gibt den Apartment Zustand des Threading Moduls an, das verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-275">Specifies the apartment state of the threading module to be used.</span></span> <span data-ttu-id="e0ed0-276">Zulässige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="e0ed0-276">Acceptable values are:</span></span>

- <span data-ttu-id="e0ed0-277">Unbekannt</span><span class="sxs-lookup"><span data-stu-id="e0ed0-277">Unknown</span></span>
- <span data-ttu-id="e0ed0-278">MTA</span><span class="sxs-lookup"><span data-stu-id="e0ed0-278">MTA</span></span>
- <span data-ttu-id="e0ed0-279">STA</span><span class="sxs-lookup"><span data-stu-id="e0ed0-279">STA</span></span>

```yaml
Type: System.Threading.ApartmentState
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e0ed0-280">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e0ed0-280">CommonParameters</span></span>

<span data-ttu-id="e0ed0-281">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-281">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e0ed0-282">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e0ed0-282">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e0ed0-283">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="e0ed0-283">INPUTS</span></span>

### <span data-ttu-id="e0ed0-284">Keine</span><span class="sxs-lookup"><span data-stu-id="e0ed0-284">None</span></span>

<span data-ttu-id="e0ed0-285">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-285">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="e0ed0-286">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="e0ed0-286">OUTPUTS</span></span>

### <span data-ttu-id="e0ed0-287">Microsoft. WSMAN. Management. wsmanconfigleafelement</span><span class="sxs-lookup"><span data-stu-id="e0ed0-287">Microsoft.WSMan.Management.WSManConfigLeafElement</span></span>

## <span data-ttu-id="e0ed0-288">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="e0ed0-288">NOTES</span></span>

<span data-ttu-id="e0ed0-289">Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-289">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="e0ed0-290">Starten Sie PowerShell mit der Option als Administrator ausführen, um dieses Cmdlet auszuführen.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-290">To run this cmdlet, start PowerShell by using the Run as administrator option.</span></span>

<span data-ttu-id="e0ed0-291">Der `Set-PSSessionConfiguration` Konfigurations Name wird vom Cmdlet nicht geändert, und der **WSMAN** -Anbieter unterstützt das `Rename-Item` Cmdlet nicht.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-291">The `Set-PSSessionConfiguration` cmdlet does not change the configuration name and the **WSMan** provider does not support the `Rename-Item` cmdlet.</span></span> <span data-ttu-id="e0ed0-292">Um den Namen einer Sitzungs Konfiguration zu ändern, verwenden `Unregister-PSSessionConfiguration` Sie das Cmdlet, um die Konfiguration zu löschen, und verwenden Sie dann das `Register-PSSessionConfiguration` Cmdlet, um eine neue Sitzungs Konfiguration zu erstellen und zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-292">To change the name of a session configuration, use the `Unregister-PSSessionConfiguration` cmdlet to delete the configuration and then use the `Register-PSSessionConfiguration` cmdlet to create and register a new session configuration.</span></span>

<span data-ttu-id="e0ed0-293">Sie können das `Set-PSSessionConfiguration` Cmdlet verwenden, um die Standard Sitzungs Konfigurationen Microsoft. PowerShell und Microsoft. PowerShell32 zu ändern.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-293">You can use the `Set-PSSessionConfiguration` cmdlet to change the default Microsoft.PowerShell and Microsoft.PowerShell32 session configurations.</span></span> <span data-ttu-id="e0ed0-294">Sie sind nicht geschützt.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-294">They are not protected.</span></span> <span data-ttu-id="e0ed0-295">Um die ursprüngliche Version einer Standard Sitzungs Konfiguration wiederherzustellen, verwenden Sie das `Unregister-PSSessionConfiguration` Cmdlet, um die Standard Sitzungs Konfiguration zu löschen, und verwenden Sie dann das `Enable-PSRemoting` Cmdlet, um es wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-295">To revert to the original version of a default session configuration, use the `Unregister-PSSessionConfiguration` cmdlet to delete the default session configuration and then use the `Enable-PSRemoting` cmdlet to restore it.</span></span>

<span data-ttu-id="e0ed0-296">Die Eigenschaften eines Sitzungskonfigurationsobjekts weichen hinsichtlich der für die Sitzungskonfiguration festgelegten Optionen sowie der Werte dieser Optionen ab.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-296">The properties of a session configuration object vary with the options set for the session configuration and the values of those options.</span></span> <span data-ttu-id="e0ed0-297">Sitzungskonfigurationen, die eine Sitzungskonfigurationsdatei verwenden, haben außerdem zusätzliche Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-297">Also, session configurations that use a session configuration file have additional properties.</span></span>

<span data-ttu-id="e0ed0-298">Sie können Befehle im WSMan:-Laufwerk verwenden, um die Eigenschaften von Sitzungskonfigurationen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-298">You can use commands in the WSMan: drive to change the properties of session configurations.</span></span>
<span data-ttu-id="e0ed0-299">Allerdings können Sie das WSMAN:-Laufwerk in PowerShell 2,0 nicht verwenden, um Sitzungs Konfigurations Eigenschaften zu ändern, die in PowerShell 3,0 (z. b. **outputbufferingmode**) eingeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-299">However, you cannot use the WSMan: drive in PowerShell 2.0 to change session configuration properties that are introduced in PowerShell 3.0, such as **OutputBufferingMode**.</span></span> <span data-ttu-id="e0ed0-300">Windows PowerShell 2.0-Befehle generieren keine Fehler, aber sie sind wirkungslos.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-300">Windows PowerShell 2.0 commands do not generate an error, but they are ineffective.</span></span> <span data-ttu-id="e0ed0-301">Verwenden Sie das WSMAN:-Laufwerk in PowerShell 3,0, um die in PowerShell 3,0 eingeführten Eigenschaften zu ändern.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-301">To change properties introduced in PowerShell 3.0, use the WSMan: drive in PowerShell 3.0.</span></span>

## <span data-ttu-id="e0ed0-302">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="e0ed0-302">RELATED LINKS</span></span>

[<span data-ttu-id="e0ed0-303">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="e0ed0-303">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="e0ed0-304">Enable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="e0ed0-304">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="e0ed0-305">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="e0ed0-305">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="e0ed0-306">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="e0ed0-306">New-PSSessionConfigurationFile</span></span>](New-PSSessionConfigurationFile.md)

[<span data-ttu-id="e0ed0-307">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="e0ed0-307">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="e0ed0-308">New-PSTransportOption</span><span class="sxs-lookup"><span data-stu-id="e0ed0-308">New-PSTransportOption</span></span>](New-PSTransportOption.md)

[<span data-ttu-id="e0ed0-309">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="e0ed0-309">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="e0ed0-310">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="e0ed0-310">Test-PSSessionConfigurationFile</span></span>](Test-PSSessionConfigurationFile.md)

[<span data-ttu-id="e0ed0-311">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="e0ed0-311">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="e0ed0-312">WSMan-Anbieter</span><span class="sxs-lookup"><span data-stu-id="e0ed0-312">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="e0ed0-313">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="e0ed0-313">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)

[<span data-ttu-id="e0ed0-314">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="e0ed0-314">about_Session_Configuration_Files</span></span>](About/about_Session_Configuration_Files.md)
