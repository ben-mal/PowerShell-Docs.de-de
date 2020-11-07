---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/set-pssessionconfiguration?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSSessionConfiguration
ms.openlocfilehash: 72ee8c7eebf7d74920fd0d39e3a508841e57b7c5
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2020
ms.locfileid: "94347498"
---
# <span data-ttu-id="65fee-103">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="65fee-103">Set-PSSessionConfiguration</span></span>

## <span data-ttu-id="65fee-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="65fee-104">SYNOPSIS</span></span>
<span data-ttu-id="65fee-105">Ändert die Eigenschaften einer registrierten Sitzungskonfiguration.</span><span class="sxs-lookup"><span data-stu-id="65fee-105">Changes the properties of a registered session configuration.</span></span>

## <span data-ttu-id="65fee-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="65fee-106">SYNTAX</span></span>

### <span data-ttu-id="65fee-107">Nameparameterset (Standard)</span><span class="sxs-lookup"><span data-stu-id="65fee-107">NameParameterSet (Default)</span></span>

```
Set-PSSessionConfiguration [-Name] <String> [-ApplicationBase <String>] [-RunAsCredential <PSCredential>]
 [-ThreadApartmentState <ApartmentState>] [-ThreadOptions <PSThreadOptions>]
 [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess] [-StartupScript <String>]
 [-MaximumReceivedDataSizePerCommandMB <Double>] [-MaximumReceivedObjectSizeMB <Double>]
 [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI] [-Force] [-NoServiceRestart]
 [-PSVersion <Version>] [-SessionTypeOption <PSSessionTypeOption>] [-TransportOption <PSTransportOption>]
 [-ModulesToImport <Object[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="65fee-108">Assemblynameparameterset</span><span class="sxs-lookup"><span data-stu-id="65fee-108">AssemblyNameParameterSet</span></span>

```
Set-PSSessionConfiguration [-Name] <String> [-AssemblyName] <String> [-ApplicationBase <String>]
 [-ConfigurationTypeName] <String> [-RunAsCredential <PSCredential>] [-ThreadApartmentState <ApartmentState>]
 [-ThreadOptions <PSThreadOptions>] [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess]
 [-StartupScript <String>] [-MaximumReceivedDataSizePerCommandMB <Double>]
 [-MaximumReceivedObjectSizeMB <Double>] [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI]
 [-Force] [-NoServiceRestart] [-PSVersion <Version>] [-SessionTypeOption <PSSessionTypeOption>]
 [-TransportOption <PSTransportOption>] [-ModulesToImport <Object[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="65fee-109">Sessionconfigurationfile</span><span class="sxs-lookup"><span data-stu-id="65fee-109">SessionConfigurationFile</span></span>

```
Set-PSSessionConfiguration [-Name] <String> [-RunAsCredential <PSCredential>]
 [-ThreadApartmentState <ApartmentState>] [-ThreadOptions <PSThreadOptions>]
 [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess] [-StartupScript <String>]
 [-MaximumReceivedDataSizePerCommandMB <Double>] [-MaximumReceivedObjectSizeMB <Double>]
 [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI] [-Force] [-NoServiceRestart]
 [-TransportOption <PSTransportOption>] -Path <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="65fee-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="65fee-110">DESCRIPTION</span></span>

<span data-ttu-id="65fee-111">Mit dem- `Set-PSSessionConfiguration` Cmdlet werden die Eigenschaften der Sitzungs Konfigurationen auf dem lokalen Computer geändert.</span><span class="sxs-lookup"><span data-stu-id="65fee-111">The `Set-PSSessionConfiguration` cmdlet changes the properties of the session configurations on the local computer.</span></span>

<span data-ttu-id="65fee-112">Verwenden Sie den **Name** -Parameter, um die Sitzungskonfiguration zu identifizieren, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="65fee-112">Use the **Name** parameter to identify the session configuration that you want to change.</span></span> <span data-ttu-id="65fee-113">Verwenden Sie die anderen Parameter, um neue Werte für die Eigenschaften der Sitzungskonfiguration anzugeben.</span><span class="sxs-lookup"><span data-stu-id="65fee-113">Use the other parameters to specify new values for the properties of the session configuration.</span></span> <span data-ttu-id="65fee-114">Um einen Eigenschafts Wert aus der Konfiguration zu löschen und den Standardwert zu verwenden, geben Sie eine leere Zeichenfolge ("") oder den Wert `$Null` für den entsprechenden Parameter ein.</span><span class="sxs-lookup"><span data-stu-id="65fee-114">To delete a property value from the configuration, and use the default value, enter an empty string ("") or a value of `$Null` for the corresponding parameter.</span></span>

<span data-ttu-id="65fee-115">Ab PowerShell 3,0 können Sie eine Sitzungs Konfigurationsdatei verwenden, um eine Sitzungs Konfiguration zu definieren.</span><span class="sxs-lookup"><span data-stu-id="65fee-115">Starting in PowerShell 3.0, you can use a session configuration file to define a session configuration.</span></span> <span data-ttu-id="65fee-116">Diese Funktion bietet eine einfache und sichtbare Methode für das Festlegen und Ändern der Eigenschaften von Sitzungen, die die Sitzungskonfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="65fee-116">This feature provides a simple and discoverable method for setting and changing the properties of sessions that use the session configuration.</span></span> <span data-ttu-id="65fee-117">Um eine Sitzungs Konfigurationsdatei anzugeben, verwenden Sie den **path** -Parameter von `Set-PSSessionConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="65fee-117">To specify a session configuration file, use the **Path** parameter of `Set-PSSessionConfiguration`.</span></span> <span data-ttu-id="65fee-118">Weitere Informationen zu Sitzungs Konfigurationsdateien finden Sie unter [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span><span class="sxs-lookup"><span data-stu-id="65fee-118">For information about session configuration files, see [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span></span>
<span data-ttu-id="65fee-119">Weitere Informationen zum Erstellen und Ändern einer Sitzungs Konfigurationsdatei finden Sie unter dem- `New-PSSessionConfigurationFile` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="65fee-119">For information about how to create and modify a session configuration file, see the `New-PSSessionConfigurationFile` cmdlet.</span></span>

<span data-ttu-id="65fee-120">Sitzungs Konfigurationen definieren die Umgebung von Remote Sitzungen ( **pssessions** ), die eine Verbindung mit dem lokalen Computer herstellen.</span><span class="sxs-lookup"><span data-stu-id="65fee-120">Session configurations define the environment of remote sessions ( **PSSessions** ) that connect to the local computer.</span></span> <span data-ttu-id="65fee-121">Jede **PSSession** verwendet eine Sitzungs Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="65fee-121">Every **PSSession** uses a session configuration.</span></span> <span data-ttu-id="65fee-122">Die Sitzungs Konfiguration bestimmt die Funktionen der **PSSession** , wie z. b. die Module, die in der Sitzung verfügbar sind, die Cmdlets, die ausgeführt werden dürfen, den Sprachmodus, Kontingente und Timeouts.</span><span class="sxs-lookup"><span data-stu-id="65fee-122">The session configuration determines the features of the **PSSession** , such as the modules that are available in the session, the cmdlets that are permitted to run, the language mode, quotas, and timeouts.</span></span> <span data-ttu-id="65fee-123">Die Sicherheits Beschreibung der Sitzungs Konfiguration bestimmt, wer die Sitzungs Konfiguration verwenden kann, um eine Verbindung mit dem lokalen Computer herzustellen.</span><span class="sxs-lookup"><span data-stu-id="65fee-123">The security descriptor of the session configuration determines who can use the session configuration to connect to the local computer.</span></span> <span data-ttu-id="65fee-124">Weitere Informationen zu Sitzungs Konfigurationen finden Sie unter [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="65fee-124">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

<span data-ttu-id="65fee-125">Um die Eigenschaften einer Sitzungs Konfiguration anzuzeigen, verwenden Sie das `Get-PSSessionConfiguration` Cmdlet oder den WSMAN-Anbieter.</span><span class="sxs-lookup"><span data-stu-id="65fee-125">To see the properties of a session configuration, use the `Get-PSSessionConfiguration` cmdlet or the WSMan Provider.</span></span> <span data-ttu-id="65fee-126">Weitere Informationen zum WSMAN-Anbieter erhalten Sie, wenn Sie eingeben `Get-Help WSMan` .</span><span class="sxs-lookup"><span data-stu-id="65fee-126">For more information about the WSMan Provider, type `Get-Help WSMan`.</span></span>

## <span data-ttu-id="65fee-127">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="65fee-127">EXAMPLES</span></span>

### <span data-ttu-id="65fee-128">Beispiel 1: Erstellen und Ändern einer Sitzungs Konfiguration</span><span class="sxs-lookup"><span data-stu-id="65fee-128">Example 1: Create and change a session configuration</span></span>

<span data-ttu-id="65fee-129">Dieses Beispiel zeigt, wie Sie ein Startskript aus einer Konfiguration hinzufügen und daraus entfernen.</span><span class="sxs-lookup"><span data-stu-id="65fee-129">This example shows how to add and remove a startup script from a configuration.</span></span>

<span data-ttu-id="65fee-130">Mit dem ersten Befehl wird die **adminshell** -Konfiguration erstellt.</span><span class="sxs-lookup"><span data-stu-id="65fee-130">The first command creates the **AdminShell** configuration.</span></span> <span data-ttu-id="65fee-131">Mit dem zweiten Befehl wird das Skript der Konfiguration hinzugefügt `AdminConfig.ps1` .</span><span class="sxs-lookup"><span data-stu-id="65fee-131">The second command adds the `AdminConfig.ps1` script to the configuration.</span></span> <span data-ttu-id="65fee-132">Die Änderung ist wirksam, wenn Sie **WinRM** neu starten.</span><span class="sxs-lookup"><span data-stu-id="65fee-132">The change is effective when you restart **WinRM**.</span></span>
<span data-ttu-id="65fee-133">Der dritte Befehl entfernt das `AdminConfig.ps1` Skript aus der Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="65fee-133">The third command removes the `AdminConfig.ps1` script from the configuration.</span></span>

```powershell
Register-PSSessionConfiguration -Name "AdminShell" -AssemblyName "C:\Shells\AdminShell.dll" -ConfigurationTypeName "AdminClass"
Set-PSSessionConfiguration -Name "AdminShell" -StartupScript "AdminConfig.ps1"
Set-PSSessionConfiguration -Name "AdminShell" -StartupScript $Null
```

### <span data-ttu-id="65fee-134">Beispiel 2: Anzeigen von Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="65fee-134">Example 2: Display results</span></span>

<span data-ttu-id="65fee-135">In diesem Beispiel wird der Wert der **maximumreceivedobjectsizemb** -Eigenschaft auf 20 erhöht.</span><span class="sxs-lookup"><span data-stu-id="65fee-135">This example increases the value of the **MaximumReceivedObjectSizeMB** property to 20.</span></span> <span data-ttu-id="65fee-136">Mit diesem Befehl werden Sie außerdem aufgefordert, den **WinRM** -Dienst neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="65fee-136">This command also prompts you to restart the **WinRM** service.</span></span> <span data-ttu-id="65fee-137">Die Änderung wird erst wirksam, wenn der **WinRM** -Dienst neu gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="65fee-137">The change is not effective until the **WinRM** service is restarted.</span></span>

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

### <span data-ttu-id="65fee-138">Beispiel 3: Anzeigen der Ergebnisse auf verschiedene Weise</span><span class="sxs-lookup"><span data-stu-id="65fee-138">Example 3: Display results in different ways</span></span>

<span data-ttu-id="65fee-139">In diesem Beispiel `Set-PSSessionConfiguration` ändert das Startskript in der **maintenanceshell** -Sitzungs Konfiguration in `Maintenance.ps1` .</span><span class="sxs-lookup"><span data-stu-id="65fee-139">In this example, `Set-PSSessionConfiguration` changes the startup script in the **MaintenanceShell** session configuration to `Maintenance.ps1`.</span></span> <span data-ttu-id="65fee-140">In der Ausgabe wird die Änderung angezeigt, und Sie werden aufgefordert, den **WinRM** -Dienst neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="65fee-140">The output shows the change and prompts you to restart the **WinRM** service.</span></span> <span data-ttu-id="65fee-141">Die Antwort ist „y“ (Ja).</span><span class="sxs-lookup"><span data-stu-id="65fee-141">The response is "y" (yes).</span></span>

<span data-ttu-id="65fee-142">`Get-PSSessionConfiguration` Ruft die **maintenanceshell** -Sitzungs Konfiguration ab.</span><span class="sxs-lookup"><span data-stu-id="65fee-142">`Get-PSSessionConfiguration` gets the **MaintenanceShell** session configuration.</span></span> <span data-ttu-id="65fee-143">Der Pipeline Operator (|) sendet die Ergebnisse des Befehls an `Format-List` , wodurch alle Eigenschaften des Konfigurations Objekts in einer Liste angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="65fee-143">The pipeline operator (|) sends the results of the command to `Format-List`, which displays all the properties of the configuration object in a list.</span></span> <span data-ttu-id="65fee-144">Als Nächstes zeigen wir mithilfe des WSMAN-Anbieters die Initialisierungs Parameter für die **maintenanceshell** -Konfiguration an.</span><span class="sxs-lookup"><span data-stu-id="65fee-144">Next, using the WSMan provider, we view the initialization parameters for the **MaintenanceShell** configuration.</span></span> <span data-ttu-id="65fee-145">`Get-ChildItem` (Alias `dir` ) Ruft die untergeordneten Elemente im **initializationparameters** -Knoten für das **maintenanceshell** -Plug-in ab.</span><span class="sxs-lookup"><span data-stu-id="65fee-145">`Get-ChildItem` (alias `dir`) gets the child items in the **InitializationParameters** node for the **MaintenanceShell** plug-in.</span></span> <span data-ttu-id="65fee-146">Weitere Informationen zum WSMAN-Anbieter erhalten Sie, wenn Sie eingeben `Get-Help wsman` .</span><span class="sxs-lookup"><span data-stu-id="65fee-146">For more information about the WSMan provider, type `Get-Help wsman`.</span></span>

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

## <span data-ttu-id="65fee-147">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="65fee-147">PARAMETERS</span></span>

### <span data-ttu-id="65fee-148">-AccessMode</span><span class="sxs-lookup"><span data-stu-id="65fee-148">-AccessMode</span></span>

<span data-ttu-id="65fee-149">Aktiviert und deaktiviert die Sitzungskonfiguration und bestimmt, ob sie für Remote- oder lokale Sitzungen auf dem Computer verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="65fee-149">Enables and disables the session configuration and determines whether it can be used for remote or local sessions on the computer.</span></span> <span data-ttu-id="65fee-150">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="65fee-150">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="65fee-151">Deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="65fee-151">Disabled.</span></span> <span data-ttu-id="65fee-152">Deaktiviert die Sitzungskonfiguration.</span><span class="sxs-lookup"><span data-stu-id="65fee-152">Disables the session configuration.</span></span> <span data-ttu-id="65fee-153">Sie kann nicht für Remote- oder lokalen Zugriff auf den Computer verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="65fee-153">It cannot be used for remote or local access to the computer.</span></span> <span data-ttu-id="65fee-154">Dieser Wert legt die **aktivierte** Eigenschaft der Sitzungs Konfiguration ( `WSMan:\<ComputerName>\PlugIn\<SessionConfigurationName>\Enabled` ) auf " **false** " fest.</span><span class="sxs-lookup"><span data-stu-id="65fee-154">This value sets the **Enabled** property of the session configuration (`WSMan:\<ComputerName>\PlugIn\<SessionConfigurationName>\Enabled`) to **False**.</span></span>
- <span data-ttu-id="65fee-155">Lokal.</span><span class="sxs-lookup"><span data-stu-id="65fee-155">Local.</span></span> <span data-ttu-id="65fee-156">Fügt der Sicherheitsbeschreibung der Sitzungskonfiguration einen **Network_Deny_All** -Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="65fee-156">Adds a **Network_Deny_All** entry to security descriptor of the session configuration.</span></span>
  <span data-ttu-id="65fee-157">Benutzer des lokalen Computers können die Sitzungs Konfiguration verwenden, um eine lokale Loopback Sitzung auf demselben Computer zu erstellen, aber Remote Benutzern wird der Zugriff verweigert.</span><span class="sxs-lookup"><span data-stu-id="65fee-157">Users of the local computer can use the session configuration to create a local loopback session on the same computer, but remote users are denied access.</span></span>
- <span data-ttu-id="65fee-158">Remote.</span><span class="sxs-lookup"><span data-stu-id="65fee-158">Remote.</span></span> <span data-ttu-id="65fee-159">Entfernt die Einträge **Deny_All** und **Network_Deny_All** aus den Sicherheitsbeschreibungen der Sitzungskonfiguration.</span><span class="sxs-lookup"><span data-stu-id="65fee-159">Removes **Deny_All** and **Network_Deny_All** entries from the security descriptors of the session configuration.</span></span> <span data-ttu-id="65fee-160">Benutzer von lokalen Computern und Remotecomputern können die Sitzungskonfiguration verwenden, um Sitzungen zu erstellen und um Befehle auf diesem Computer auszuführen.</span><span class="sxs-lookup"><span data-stu-id="65fee-160">Users of local and remote computers can use the session configuration to create sessions and run commands on this computer.</span></span>

<span data-ttu-id="65fee-161">Der Standardwert ist **Remote**.</span><span class="sxs-lookup"><span data-stu-id="65fee-161">The default value is **Remote**.</span></span>

<span data-ttu-id="65fee-162">Andere Cmdlets können den Wert dieses Parameters später überschreiben.</span><span class="sxs-lookup"><span data-stu-id="65fee-162">Other cmdlets can override the value of this parameter later.</span></span> <span data-ttu-id="65fee-163">Beispielsweise aktiviert das `Enable-PSRemoting` Cmdlet alle Sitzungs Konfigurationen auf dem Computer und ermöglicht den Remote Zugriff auf diese, und das `Disable-PSRemoting` Cmdlet gestattet nur den lokalen Zugriff auf alle Sitzungs Konfigurationen auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="65fee-163">For example, the `Enable-PSRemoting` cmdlet enables all session configurations on the computer and permits remote access to them, and the `Disable-PSRemoting` cmdlet permits only local access to all session configurations on the computer.</span></span>

<span data-ttu-id="65fee-164">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="65fee-164">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="65fee-165">-ApplicationBase</span><span class="sxs-lookup"><span data-stu-id="65fee-165">-ApplicationBase</span></span>

<span data-ttu-id="65fee-166">Gibt den Pfad der \* **Assemblydatei** (. dll) an, die im Wert des AssemblyName-Parameters angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="65fee-166">Specifies the path of the assembly file (\*.dll) that is specified in the value of the **AssemblyName** parameter.</span></span>

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

### <span data-ttu-id="65fee-167">-AssemblyName</span><span class="sxs-lookup"><span data-stu-id="65fee-167">-AssemblyName</span></span>

<span data-ttu-id="65fee-168">Gibt den Assemblynamen an.</span><span class="sxs-lookup"><span data-stu-id="65fee-168">Specifies the assembly name.</span></span> <span data-ttu-id="65fee-169">Dieses Cmdlet erstellt eine Sitzungs Konfiguration basierend auf einer Klasse, die in einer Assembly definiert ist.</span><span class="sxs-lookup"><span data-stu-id="65fee-169">This cmdlet creates a session configuration based on a class that is defined in an assembly.</span></span>

<span data-ttu-id="65fee-170">Geben Sie den Dateinamen oder den vollständigen Pfad einer Assembly. dll-Datei ein, die eine Sitzungs Konfiguration definiert.</span><span class="sxs-lookup"><span data-stu-id="65fee-170">Enter the filename or full path of an assembly .dll file that defines a session configuration.</span></span> <span data-ttu-id="65fee-171">Wenn Sie nur den Dateinamen eingeben, können Sie den Pfad im Wert des **ApplicationBase** -Parameters eingeben.</span><span class="sxs-lookup"><span data-stu-id="65fee-171">If you enter only the file name, you can enter the path in the value of the **ApplicationBase** parameter.</span></span>

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

### <span data-ttu-id="65fee-172">-Configurationtyname</span><span class="sxs-lookup"><span data-stu-id="65fee-172">-ConfigurationTypeName</span></span>

<span data-ttu-id="65fee-173">Gibt den Typ der Sitzungskonfiguration an, der in der Assembly im **AssemblyName** -Parameter definiert ist.</span><span class="sxs-lookup"><span data-stu-id="65fee-173">Specifies the type of the session configuration that is defined in the assembly in the **AssemblyName** parameter.</span></span> <span data-ttu-id="65fee-174">Der Typ, den Sie angeben, muss die **System.Management.Automation.Remoting.PSSessionConfiguration** Klasse implementieren.</span><span class="sxs-lookup"><span data-stu-id="65fee-174">The type that you specify must implement the **System.Management.Automation.Remoting.PSSessionConfiguration** class.</span></span>

<span data-ttu-id="65fee-175">Dieser Parameter ist erforderlich, wenn Sie den Namen einer Assembly angeben.</span><span class="sxs-lookup"><span data-stu-id="65fee-175">This parameter is required when you specify an assembly name.</span></span>

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

### <span data-ttu-id="65fee-176">-Force</span><span class="sxs-lookup"><span data-stu-id="65fee-176">-Force</span></span>

<span data-ttu-id="65fee-177">Unterdrückt alle Benutzer Aufforderungen und startet den **WinRM** -Dienst ohne Aufforderung neu.</span><span class="sxs-lookup"><span data-stu-id="65fee-177">Suppresses all user prompts, and restarts the **WinRM** service without prompting.</span></span> <span data-ttu-id="65fee-178">Durch Neustarten des Diensts wird die Konfigurationsänderung übernommen.</span><span class="sxs-lookup"><span data-stu-id="65fee-178">Restarting the service makes the configuration change effective.</span></span>

<span data-ttu-id="65fee-179">Um einen Neustart zu verhindern und die Aufforderung zum Neustart zu unterdrücken, verwenden Sie den **NoServiceRestart** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="65fee-179">To prevent a restart and suppress the restart prompt, use the **NoServiceRestart** parameter.</span></span>

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

### <span data-ttu-id="65fee-180">-Maximumreceiveddatasizepercommandmb</span><span class="sxs-lookup"><span data-stu-id="65fee-180">-MaximumReceivedDataSizePerCommandMB</span></span>

<span data-ttu-id="65fee-181">Gibt den Grenzwert für die Datenmenge an, die in jedem einzelnen Remote Befehl an diesen Computer gesendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="65fee-181">Specifies the limit on the amount of data that can be sent to this computer in any single remote command.</span></span> <span data-ttu-id="65fee-182">Geben Sie die Datengröße in Megabyte (MB) ein.</span><span class="sxs-lookup"><span data-stu-id="65fee-182">Enter the data size in megabytes (MB).</span></span> <span data-ttu-id="65fee-183">Der Standardwert ist 50 MB.</span><span class="sxs-lookup"><span data-stu-id="65fee-183">The default is 50 MB.</span></span>

<span data-ttu-id="65fee-184">Wenn eine Datengrößen Beschränkung im Konfigurationstyp definiert ist, der im **configurationtypame** -Parameter angegeben ist, wird der Grenzwert im Konfigurationstyp verwendet.</span><span class="sxs-lookup"><span data-stu-id="65fee-184">If a data size limit is defined in the configuration type that is specified in the **ConfigurationTypeName** parameter, the limit in the configuration type is used.</span></span> <span data-ttu-id="65fee-185">Der Wert dieses Parameters wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="65fee-185">The value of this parameter is ignored.</span></span>

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

### <span data-ttu-id="65fee-186">-Maximumreceivedobjectsizemb</span><span class="sxs-lookup"><span data-stu-id="65fee-186">-MaximumReceivedObjectSizeMB</span></span>

<span data-ttu-id="65fee-187">Gibt die Grenzwerte für die Datenmenge an, die in jedem einzelnen Objekt an diesen Computer gesendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="65fee-187">Specifies the limits on the amount of data that can be sent to this computer in any single object.</span></span>
<span data-ttu-id="65fee-188">Geben Sie die Datengröße in Megabyte ein.</span><span class="sxs-lookup"><span data-stu-id="65fee-188">Enter the data size in megabytes.</span></span> <span data-ttu-id="65fee-189">Der Standardwert ist 10 MB.</span><span class="sxs-lookup"><span data-stu-id="65fee-189">The default is 10 MB.</span></span>

<span data-ttu-id="65fee-190">Wenn eine Objektgrößen Beschränkung im Konfigurationstyp definiert ist, der im **configurationtypame** -Parameter angegeben ist, wird der Grenzwert im Konfigurationstyp verwendet.</span><span class="sxs-lookup"><span data-stu-id="65fee-190">If an object size limit is defined in the configuration type that is specified in the **ConfigurationTypeName** parameter, the limit in the configuration type is used.</span></span> <span data-ttu-id="65fee-191">Der Wert dieses Parameters wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="65fee-191">The value of this parameter is ignored.</span></span>

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

### <span data-ttu-id="65fee-192">-Modulestoimport</span><span class="sxs-lookup"><span data-stu-id="65fee-192">-ModulesToImport</span></span>

<span data-ttu-id="65fee-193">Gibt die Module und Snap-ins an, die automatisch in Sitzungen importiert werden, die die Sitzungskonfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="65fee-193">Specifies the modules and snap-ins that are automatically imported into sessions that use the session configuration.</span></span> <span data-ttu-id="65fee-194">Geben Sie die Namen der Module und Snap-Ins ein.</span><span class="sxs-lookup"><span data-stu-id="65fee-194">Enter the module and snap-in names.</span></span>

<span data-ttu-id="65fee-195">Standardmäßig wird nur das **Microsoft. PowerShell. Core** -Snap-in in Sitzungen importiert, aber wenn die Cmdlets nicht ausgeschlossen sind, können Sie die `Import-Module` -und-Add-PSSnapin-Cmdlets verwenden, um der Sitzung Module und Snap-Ins hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="65fee-195">By default, only the **Microsoft.PowerShell.Core** snap-in is imported into sessions, but unless the cmdlets are excluded, you can use the `Import-Module` and Add-PSSnapin cmdlets to add modules and snap-ins to the session.</span></span>

<span data-ttu-id="65fee-196">Die in diesem Parameterwert angegebenen Module werden in Ergänzungen zu Modulen importiert, die in der Sitzungs Konfigurationsdatei () angegeben sind `New-PSSessionConfigurationFile` .</span><span class="sxs-lookup"><span data-stu-id="65fee-196">The modules specified in this parameter value are imported in additions to modules specified in the session configuration file (`New-PSSessionConfigurationFile`).</span></span> <span data-ttu-id="65fee-197">Einstellungen in der Sitzungskonfigurationsdatei können jedoch die von Modulen exportierten Befehle ausblenden oder verhindern, dass Benutzer sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="65fee-197">However, settings in the session configuration file can hide the commands exported by modules or prevent users from using them.</span></span>

<span data-ttu-id="65fee-198">Die in diesem Parameterwert angegebenen Module ersetzen die Liste der Module, die mit dem **modulestoimport** -Parameter des `Register-PSSessionConfiguration` Cmdlets angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="65fee-198">The modules specified in this parameter value replace the list of modules specified by using the **ModulesToImport** parameter of the `Register-PSSessionConfiguration` cmdlet.</span></span>

<span data-ttu-id="65fee-199">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="65fee-199">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="65fee-200">-Name</span><span class="sxs-lookup"><span data-stu-id="65fee-200">-Name</span></span>

<span data-ttu-id="65fee-201">Gibt den Namen der Sitzungskonfiguration an, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="65fee-201">Specifies the name of the session configuration that you want to change.</span></span>

<span data-ttu-id="65fee-202">Sie können diesen Parameter verwenden, um den Namen der Sitzungskonfiguration zu ändern.</span><span class="sxs-lookup"><span data-stu-id="65fee-202">You cannot use this parameter to change the name of the session configuration.</span></span>

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

### <span data-ttu-id="65fee-203">-Noservicerestart</span><span class="sxs-lookup"><span data-stu-id="65fee-203">-NoServiceRestart</span></span>

<span data-ttu-id="65fee-204">Der **WinRM** -Dienst wird nicht neu gestartet, und die Aufforderung zum Neustarten des Dienstanbieter wird unterdrückt.</span><span class="sxs-lookup"><span data-stu-id="65fee-204">Does not restart the **WinRM** service, and suppresses the prompt to restart the service.</span></span>

<span data-ttu-id="65fee-205">Wenn Sie Ausführen `Set-PSSessionConfiguration` , werden Sie standardmäßig aufgefordert, den **WinRM** -Dienst neu zu starten, damit die neue Sitzungs Konfiguration wirksam wird.</span><span class="sxs-lookup"><span data-stu-id="65fee-205">By default, when you run `Set-PSSessionConfiguration`, you are prompted to restart the **WinRM** service to make the new session configuration effective.</span></span> <span data-ttu-id="65fee-206">Bis der **WinRM** -Dienst neu gestartet wird, ist die neue Sitzungs Konfiguration nicht wirksam.</span><span class="sxs-lookup"><span data-stu-id="65fee-206">Until the **WinRM** service is restarted, the new session configuration is not effective.</span></span>

<span data-ttu-id="65fee-207">Um den **WinRM** -Dienst ohne Aufforderung neu zu starten, verwenden Sie den **Force** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="65fee-207">To restart the **WinRM** service without prompting, use the **Force** parameter.</span></span> <span data-ttu-id="65fee-208">Verwenden Sie das-Cmdlet, um den **WinRM** -Dienst manuell neu zu starten `Restart-Service` .</span><span class="sxs-lookup"><span data-stu-id="65fee-208">To restart the **WinRM** service manually, use the `Restart-Service` cmdlet.</span></span>

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

### <span data-ttu-id="65fee-209">-Path</span><span class="sxs-lookup"><span data-stu-id="65fee-209">-Path</span></span>

<span data-ttu-id="65fee-210">Gibt den Pfad einer Sitzungs Konfigurationsdatei (. PSSC) an, z. b. eine, die vom `New-PSSessionConfigurationFile` Cmdlet erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="65fee-210">Specifies the path of a session configuration file (.pssc), such as one created by the `New-PSSessionConfigurationFile` cmdlet.</span></span> <span data-ttu-id="65fee-211">Wenn Sie den Pfad weglassen, ist die Standardeinstellung das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="65fee-211">If you omit the path, the default is the current directory.</span></span>

<span data-ttu-id="65fee-212">Informationen dazu, wie Sie eine Sitzungs Konfigurationsdatei ändern, finden Sie im Hilfethema für das `New-PSSessionConfigurationFile` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="65fee-212">For information about how to modify a session configuration file, see the help topic for the `New-PSSessionConfigurationFile` cmdlet.</span></span>

<span data-ttu-id="65fee-213">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="65fee-213">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="65fee-214">-Psversion</span><span class="sxs-lookup"><span data-stu-id="65fee-214">-PSVersion</span></span>

<span data-ttu-id="65fee-215">Gibt die Version von PowerShell in Sitzungen an, die diese Sitzungs Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="65fee-215">Specifies the version of PowerShell in sessions that use this session configuration.</span></span>

<span data-ttu-id="65fee-216">Der Wert dieses Parameters hat Vorrang vor den Wert des **PowerShellVersion** -Schlüssels in der Sitzungskonfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="65fee-216">The value of this parameter takes precedence over the value of the **PowerShellVersion** key in the session configuration file.</span></span>

<span data-ttu-id="65fee-217">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="65fee-217">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="65fee-218">-Runascredential</span><span class="sxs-lookup"><span data-stu-id="65fee-218">-RunAsCredential</span></span>

<span data-ttu-id="65fee-219">Gibt Anmelde Informationen für Befehle in der Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="65fee-219">Specifies credentials for commands in the session.</span></span> <span data-ttu-id="65fee-220">Standardmäßig werden Befehle mit den Berechtigungen des aktuellen Benutzers ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="65fee-220">By default, commands run with the permissions of the current user.</span></span>

<span data-ttu-id="65fee-221">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="65fee-221">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="65fee-222">-SecurityDescriptor SDDL</span><span class="sxs-lookup"><span data-stu-id="65fee-222">-SecurityDescriptorSddl</span></span>

<span data-ttu-id="65fee-223">Gibt eine andere Security Descriptor Definition Language (SDDL)-Zeichenfolge für die Konfiguration an.</span><span class="sxs-lookup"><span data-stu-id="65fee-223">Specifies a different Security Descriptor Definition Language (SDDL) string for the configuration.</span></span>

<span data-ttu-id="65fee-224">Diese Zeichenfolge bestimmt die Berechtigungen, die erforderlich sind, um die Konfiguration für die neue Sitzung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="65fee-224">This string determines the permissions that are required to use the new session configuration.</span></span> <span data-ttu-id="65fee-225">Um eine Sitzungs Konfiguration in einer Sitzung zu verwenden, müssen die Benutzer mindestens über die Berechtigung Execute (aufrufen) für die Konfiguration verfügen.</span><span class="sxs-lookup"><span data-stu-id="65fee-225">To use a session configuration in a session, users must have at least Execute(Invoke) permission for the configuration.</span></span>

<span data-ttu-id="65fee-226">Um die Standard Sicherheits Beschreibung für die Konfiguration zu verwenden, geben Sie eine leere Zeichenfolge ("") oder einen Wert von ein `$Null` .</span><span class="sxs-lookup"><span data-stu-id="65fee-226">To use the default security descriptor for the configuration, enter an empty string ("") or a value of `$Null`.</span></span> <span data-ttu-id="65fee-227">Der Standardwert ist die Stamm-SDDL im WSMan:-Laufwerk.</span><span class="sxs-lookup"><span data-stu-id="65fee-227">The default is the root SDDL in the WSMan: drive.</span></span>

<span data-ttu-id="65fee-228">Wenn die Sicherheits Beschreibung Komplex ist, sollten Sie die Verwendung des **showsecuritydescriptorui** -Parameters anstelle dieses Parameters in Erwägung gezogen.</span><span class="sxs-lookup"><span data-stu-id="65fee-228">If the security descriptor is complex, consider using the **ShowSecurityDescriptorUI** parameter instead of this one.</span></span> <span data-ttu-id="65fee-229">Sie können nicht beide Parameter im selben Befehl verwenden.</span><span class="sxs-lookup"><span data-stu-id="65fee-229">You cannot use both parameters in the same command.</span></span>

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

### <span data-ttu-id="65fee-230">-Sessiontypeoption</span><span class="sxs-lookup"><span data-stu-id="65fee-230">-SessionTypeOption</span></span>

<span data-ttu-id="65fee-231">Gibt typspezifische Optionen für die Sitzungs Konfiguration an.</span><span class="sxs-lookup"><span data-stu-id="65fee-231">Specifies type-specific options for the session configuration.</span></span> <span data-ttu-id="65fee-232">Geben Sie ein "Session TYPE Options"-Objekt ein, z. b. das vom Cmdlet zurückgegebene **psworkflowexecutionoption** -Objekt `New-PSWorkflowExecutionOption` .</span><span class="sxs-lookup"><span data-stu-id="65fee-232">Enter a session type options object, such as the **PSWorkflowExecutionOption** object that the `New-PSWorkflowExecutionOption` cmdlet returns.</span></span>

<span data-ttu-id="65fee-233">Die Optionen der Sitzungen, die die Sitzungskonfiguration verwenden, werden durch die Werte der Sitzungsoptionen und die Sitzungskonfigurationsoptionen bestimmt.</span><span class="sxs-lookup"><span data-stu-id="65fee-233">The options of sessions that use the session configuration are determined by the values of session options and the session configuration options.</span></span> <span data-ttu-id="65fee-234">Sofern nicht angegeben, haben in der Sitzung festgelegte Optionen, z. b. mit dem `New-PSSessionOption` Cmdlet, Vorrang vor den in der Sitzungs Konfiguration festgelegten Optionen.</span><span class="sxs-lookup"><span data-stu-id="65fee-234">Unless specified, options set in the session, such as by using the `New-PSSessionOption` cmdlet, take precedence over options set in the session configuration.</span></span> <span data-ttu-id="65fee-235">Die Sitzungsoptionswerte dürfen aber nicht die in der Sitzungskonfiguration festgelegten Höchstwerte überschreiten.</span><span class="sxs-lookup"><span data-stu-id="65fee-235">However, session option values cannot exceed maximum values set in the session configuration.</span></span>

<span data-ttu-id="65fee-236">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="65fee-236">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="65fee-237">-Showsecuritydescriptor UI</span><span class="sxs-lookup"><span data-stu-id="65fee-237">-ShowSecurityDescriptorUI</span></span>

<span data-ttu-id="65fee-238">Gibt an, dass dieses Cmdlet ein Eigenschaften Blatt ist, das Ihnen hilft, eine neue SDDL für die Sitzungs Konfiguration zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="65fee-238">Indicates that this cmdlet a property sheet that helps you create a new SDDL for the session configuration.</span></span> <span data-ttu-id="65fee-239">Das Eigenschaften Blatt wird angezeigt, nachdem Sie den `Set-PSSessionConfiguration` Befehl ausgeführt und den **WinRM** -Dienst neu gestartet haben.</span><span class="sxs-lookup"><span data-stu-id="65fee-239">The property sheet appears after you run the `Set-PSSessionConfiguration` command and then restart the **WinRM** service.</span></span>

<span data-ttu-id="65fee-240">Beachten Sie beim Festlegen der Berechtigungen für die Konfiguration, dass die Benutzer mindestens über die Berechtigung Ausführen (aufrufen) verfügen müssen, um die Sitzungs Konfiguration in einer Sitzung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="65fee-240">When you set permissions to the configuration, remember that users must have at least Execute(Invoke) permission to use the session configuration in a session.</span></span>

<span data-ttu-id="65fee-241">Sie können den **SecurityDescriptorSDDL** -Parameter und diesen Parameter nicht im selben Befehl verwenden.</span><span class="sxs-lookup"><span data-stu-id="65fee-241">You cannot use the **SecurityDescriptorSDDL** parameter and this parameter in the same command.</span></span>

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

### <span data-ttu-id="65fee-242">-Startupscript</span><span class="sxs-lookup"><span data-stu-id="65fee-242">-StartupScript</span></span>

<span data-ttu-id="65fee-243">Gibt das Startskript für die Konfiguration an.</span><span class="sxs-lookup"><span data-stu-id="65fee-243">Specifies the startup script for the configuration.</span></span> <span data-ttu-id="65fee-244">Geben Sie den voll qualifizierten Pfad eines PowerShell-Skripts ein.</span><span class="sxs-lookup"><span data-stu-id="65fee-244">Enter the fully qualified path of a PowerShell script.</span></span> <span data-ttu-id="65fee-245">Das angegebene Skript wird in der neuen Sitzung ausgeführt, die die Sitzungskonfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="65fee-245">The specified script runs in the new session that uses the session configuration.</span></span>

<span data-ttu-id="65fee-246">Zum Löschen eines Start Skripts aus einer Sitzungs Konfiguration geben Sie eine leere Zeichenfolge ("") oder einen Wert von ein `$Null` .</span><span class="sxs-lookup"><span data-stu-id="65fee-246">To delete a startup script from a session configuration, enter an empty string ("") or a value of `$Null`.</span></span>

<span data-ttu-id="65fee-247">Zur weiteren Konfiguration der Benutzersitzung können Sie ein Startskript verwenden.</span><span class="sxs-lookup"><span data-stu-id="65fee-247">You can use a startup script to further configure the user session.</span></span> <span data-ttu-id="65fee-248">Wenn das Skript einen Fehler (auch einen Fehler ohne Abbruch) generiert, wird die Sitzung nicht erstellt, und der `New-PSSession` Befehl schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="65fee-248">If the script generates an error, even a non-terminating error, the session is not created and the `New-PSSession` command fails.</span></span>

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

### <span data-ttu-id="65fee-249">-Threadoptions</span><span class="sxs-lookup"><span data-stu-id="65fee-249">-ThreadOptions</span></span>

<span data-ttu-id="65fee-250">Gibt die Thread Options Einstellung in der Konfiguration an.</span><span class="sxs-lookup"><span data-stu-id="65fee-250">Specifies the thread options setting in the configuration.</span></span> <span data-ttu-id="65fee-251">Diese Einstellung definiert, wie Threads erstellt und verwendet werden, wenn ein Befehl in der Sitzung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="65fee-251">This setting defines how threads are created and used when a command is executed in the session.</span></span> <span data-ttu-id="65fee-252">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="65fee-252">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="65fee-253">Standard</span><span class="sxs-lookup"><span data-stu-id="65fee-253">Default</span></span>
- <span data-ttu-id="65fee-254">Reusethread</span><span class="sxs-lookup"><span data-stu-id="65fee-254">ReuseThread</span></span>
- <span data-ttu-id="65fee-255">UseCurrentThread</span><span class="sxs-lookup"><span data-stu-id="65fee-255">UseCurrentThread</span></span>
- <span data-ttu-id="65fee-256">Usenewthread</span><span class="sxs-lookup"><span data-stu-id="65fee-256">UseNewThread</span></span>

<span data-ttu-id="65fee-257">Der Standardwert ist **usecurrentthread**.</span><span class="sxs-lookup"><span data-stu-id="65fee-257">The default value is **UseCurrentThread**.</span></span>

<span data-ttu-id="65fee-258">Weitere Informationen finden Sie unter [psthlesoptions-Enumeration](/dotnet/api/system.management.automation.runspaces.psthreadoptions).</span><span class="sxs-lookup"><span data-stu-id="65fee-258">For more information, see [PSThreadOptions Enumeration](/dotnet/api/system.management.automation.runspaces.psthreadoptions).</span></span>

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

### <span data-ttu-id="65fee-259">-Transportoption</span><span class="sxs-lookup"><span data-stu-id="65fee-259">-TransportOption</span></span>

<span data-ttu-id="65fee-260">Gibt die Transport Optionen für die Sitzungs Konfiguration an.</span><span class="sxs-lookup"><span data-stu-id="65fee-260">Specifies the transport options for the session configuration.</span></span> <span data-ttu-id="65fee-261">Geben Sie ein Transport Options Objekt ein, z. b. das **wsmanconfigurationoption** -Objekt, das vom `New-PSTransportOption` Cmdlet zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="65fee-261">Enter a transport options object, such as the **WSManConfigurationOption** object that the `New-PSTransportOption` cmdlet returns.</span></span>

<span data-ttu-id="65fee-262">Die Optionen der Sitzungen, die die Sitzungskonfiguration verwenden, werden durch die Werte der Sitzungsoptionen und die Sitzungskonfigurationsoptionen bestimmt.</span><span class="sxs-lookup"><span data-stu-id="65fee-262">The options of sessions that use the session configuration are determined by the values of session options and the session configuration options.</span></span> <span data-ttu-id="65fee-263">Sofern nicht angegeben, haben in der Sitzung festgelegte Optionen, z. b. mit dem `New-PSSessionOption` Cmdlet, Vorrang vor den in der Sitzungs Konfiguration festgelegten Optionen.</span><span class="sxs-lookup"><span data-stu-id="65fee-263">Unless specified, options set in the session, such as by using the `New-PSSessionOption` cmdlet, take precedence over options set in the session configuration.</span></span> <span data-ttu-id="65fee-264">Die Sitzungsoptionswerte dürfen aber nicht die in der Sitzungskonfiguration festgelegten Höchstwerte überschreiten.</span><span class="sxs-lookup"><span data-stu-id="65fee-264">However, session option values cannot exceed maximum values set in the session configuration.</span></span>

<span data-ttu-id="65fee-265">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="65fee-265">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="65fee-266">--Vorgang</span><span class="sxs-lookup"><span data-stu-id="65fee-266">-UseSharedProcess</span></span>

<span data-ttu-id="65fee-267">Verwenden Sie nur einen Prozess, um alle Sitzungen zu hosten, die vom gleichen Benutzer gestartet wurden und die gleiche Sitzungs Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="65fee-267">Use only one process to host all sessions that are started by the same user and use the same session configuration.</span></span> <span data-ttu-id="65fee-268">Standardmäßig wird jede Sitzung in einem eigenen Prozess gehostet.</span><span class="sxs-lookup"><span data-stu-id="65fee-268">By default, each session is hosted in its own process.</span></span>

<span data-ttu-id="65fee-269">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="65fee-269">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="65fee-270">-Confirm</span><span class="sxs-lookup"><span data-stu-id="65fee-270">-Confirm</span></span>

<span data-ttu-id="65fee-271">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="65fee-271">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="65fee-272">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="65fee-272">-WhatIf</span></span>

<span data-ttu-id="65fee-273">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="65fee-273">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="65fee-274">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="65fee-274">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="65fee-275">-Threadapartmentstate</span><span class="sxs-lookup"><span data-stu-id="65fee-275">-ThreadApartmentState</span></span>

<span data-ttu-id="65fee-276">Gibt den Apartment Zustand des Threading Moduls an, das verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="65fee-276">Specifies the apartment state of the threading module to be used.</span></span> <span data-ttu-id="65fee-277">Zulässige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="65fee-277">Acceptable values are:</span></span>

- <span data-ttu-id="65fee-278">Unknown</span><span class="sxs-lookup"><span data-stu-id="65fee-278">Unknown</span></span>
- <span data-ttu-id="65fee-279">MTA</span><span class="sxs-lookup"><span data-stu-id="65fee-279">MTA</span></span>
- <span data-ttu-id="65fee-280">STA</span><span class="sxs-lookup"><span data-stu-id="65fee-280">STA</span></span>

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

### <span data-ttu-id="65fee-281">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="65fee-281">CommonParameters</span></span>

<span data-ttu-id="65fee-282">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="65fee-282">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="65fee-283">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="65fee-283">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="65fee-284">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="65fee-284">INPUTS</span></span>

### <span data-ttu-id="65fee-285">Keine</span><span class="sxs-lookup"><span data-stu-id="65fee-285">None</span></span>

<span data-ttu-id="65fee-286">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="65fee-286">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="65fee-287">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="65fee-287">OUTPUTS</span></span>

### <span data-ttu-id="65fee-288">Microsoft. WSMAN. Management. wsmanconfigleafelement</span><span class="sxs-lookup"><span data-stu-id="65fee-288">Microsoft.WSMan.Management.WSManConfigLeafElement</span></span>

## <span data-ttu-id="65fee-289">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="65fee-289">NOTES</span></span>

<span data-ttu-id="65fee-290">Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="65fee-290">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="65fee-291">Starten Sie PowerShell mit der Option als Administrator ausführen, um dieses Cmdlet auszuführen.</span><span class="sxs-lookup"><span data-stu-id="65fee-291">To run this cmdlet, start PowerShell by using the Run as administrator option.</span></span>

<span data-ttu-id="65fee-292">Der `Set-PSSessionConfiguration` Konfigurations Name wird vom Cmdlet nicht geändert, und der **WSMAN** -Anbieter unterstützt das `Rename-Item` Cmdlet nicht.</span><span class="sxs-lookup"><span data-stu-id="65fee-292">The `Set-PSSessionConfiguration` cmdlet does not change the configuration name and the **WSMan** provider does not support the `Rename-Item` cmdlet.</span></span> <span data-ttu-id="65fee-293">Um den Namen einer Sitzungs Konfiguration zu ändern, verwenden `Unregister-PSSessionConfiguration` Sie das Cmdlet, um die Konfiguration zu löschen, und verwenden Sie dann das `Register-PSSessionConfiguration` Cmdlet, um eine neue Sitzungs Konfiguration zu erstellen und zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="65fee-293">To change the name of a session configuration, use the `Unregister-PSSessionConfiguration` cmdlet to delete the configuration and then use the `Register-PSSessionConfiguration` cmdlet to create and register a new session configuration.</span></span>

<span data-ttu-id="65fee-294">Sie können das `Set-PSSessionConfiguration` Cmdlet verwenden, um die Standard Sitzungs Konfigurationen Microsoft. PowerShell und Microsoft. PowerShell32 zu ändern.</span><span class="sxs-lookup"><span data-stu-id="65fee-294">You can use the `Set-PSSessionConfiguration` cmdlet to change the default Microsoft.PowerShell and Microsoft.PowerShell32 session configurations.</span></span> <span data-ttu-id="65fee-295">Sie sind nicht geschützt.</span><span class="sxs-lookup"><span data-stu-id="65fee-295">They are not protected.</span></span> <span data-ttu-id="65fee-296">Um die ursprüngliche Version einer Standard Sitzungs Konfiguration wiederherzustellen, verwenden Sie das `Unregister-PSSessionConfiguration` Cmdlet, um die Standard Sitzungs Konfiguration zu löschen, und verwenden Sie dann das `Enable-PSRemoting` Cmdlet, um es wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="65fee-296">To revert to the original version of a default session configuration, use the `Unregister-PSSessionConfiguration` cmdlet to delete the default session configuration and then use the `Enable-PSRemoting` cmdlet to restore it.</span></span>

<span data-ttu-id="65fee-297">Die Eigenschaften eines Sitzungskonfigurationsobjekts weichen hinsichtlich der für die Sitzungskonfiguration festgelegten Optionen sowie der Werte dieser Optionen ab.</span><span class="sxs-lookup"><span data-stu-id="65fee-297">The properties of a session configuration object vary with the options set for the session configuration and the values of those options.</span></span> <span data-ttu-id="65fee-298">Sitzungskonfigurationen, die eine Sitzungskonfigurationsdatei verwenden, haben außerdem zusätzliche Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="65fee-298">Also, session configurations that use a session configuration file have additional properties.</span></span>

<span data-ttu-id="65fee-299">Sie können Befehle im WSMan:-Laufwerk verwenden, um die Eigenschaften von Sitzungskonfigurationen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="65fee-299">You can use commands in the WSMan: drive to change the properties of session configurations.</span></span>
<span data-ttu-id="65fee-300">Allerdings können Sie das WSMAN:-Laufwerk in PowerShell 2,0 nicht verwenden, um Sitzungs Konfigurations Eigenschaften zu ändern, die in PowerShell 3,0 (z. b. **outputbufferingmode** ) eingeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="65fee-300">However, you cannot use the WSMan: drive in PowerShell 2.0 to change session configuration properties that are introduced in PowerShell 3.0, such as **OutputBufferingMode**.</span></span> <span data-ttu-id="65fee-301">Windows PowerShell 2.0-Befehle generieren keine Fehler, aber sie sind wirkungslos.</span><span class="sxs-lookup"><span data-stu-id="65fee-301">Windows PowerShell 2.0 commands do not generate an error, but they are ineffective.</span></span> <span data-ttu-id="65fee-302">Verwenden Sie das WSMAN:-Laufwerk in PowerShell 3,0, um die in PowerShell 3,0 eingeführten Eigenschaften zu ändern.</span><span class="sxs-lookup"><span data-stu-id="65fee-302">To change properties introduced in PowerShell 3.0, use the WSMan: drive in PowerShell 3.0.</span></span>

## <span data-ttu-id="65fee-303">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="65fee-303">RELATED LINKS</span></span>

[<span data-ttu-id="65fee-304">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="65fee-304">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="65fee-305">Enable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="65fee-305">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="65fee-306">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="65fee-306">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="65fee-307">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="65fee-307">New-PSSessionConfigurationFile</span></span>](New-PSSessionConfigurationFile.md)

[<span data-ttu-id="65fee-308">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="65fee-308">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="65fee-309">New-PSTransportOption</span><span class="sxs-lookup"><span data-stu-id="65fee-309">New-PSTransportOption</span></span>](New-PSTransportOption.md)

[<span data-ttu-id="65fee-310">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="65fee-310">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="65fee-311">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="65fee-311">Test-PSSessionConfigurationFile</span></span>](Test-PSSessionConfigurationFile.md)

[<span data-ttu-id="65fee-312">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="65fee-312">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="65fee-313">WSMan-Anbieter</span><span class="sxs-lookup"><span data-stu-id="65fee-313">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="65fee-314">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="65fee-314">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)

[<span data-ttu-id="65fee-315">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="65fee-315">about_Session_Configuration_Files</span></span>](About/about_Session_Configuration_Files.md)
