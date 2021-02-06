---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/register-pssessionconfiguration?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-PSSessionConfiguration
ms.openlocfilehash: 0ec31d32ef73108b53b18b529cc93aa80787fe25
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600900"
---
# <span data-ttu-id="255c5-102">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="255c5-102">Register-PSSessionConfiguration</span></span>

## <span data-ttu-id="255c5-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="255c5-103">SYNOPSIS</span></span>
<span data-ttu-id="255c5-104">Erstellt und registriert eine neue Sitzungskonfiguration.</span><span class="sxs-lookup"><span data-stu-id="255c5-104">Creates and registers a new session configuration.</span></span>

## <span data-ttu-id="255c5-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="255c5-105">SYNTAX</span></span>

### <span data-ttu-id="255c5-106">Nameparameterset (Standard)</span><span class="sxs-lookup"><span data-stu-id="255c5-106">NameParameterSet (Default)</span></span>

```
Register-PSSessionConfiguration [-ProcessorArchitecture <String>] [-Name] <String> [-ApplicationBase <String>]
 [-RunAsCredential <PSCredential>] [-ThreadApartmentState <ApartmentState>] [-ThreadOptions <PSThreadOptions>]
 [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess] [-StartupScript <String>]
 [-MaximumReceivedDataSizePerCommandMB <Double>] [-MaximumReceivedObjectSizeMB <Double>]
 [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI] [-Force] [-NoServiceRestart]
 [-PSVersion <Version>] [-SessionTypeOption <PSSessionTypeOption>] [-TransportOption <PSTransportOption>]
 [-ModulesToImport <Object[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="255c5-107">Assemblynameparameterset</span><span class="sxs-lookup"><span data-stu-id="255c5-107">AssemblyNameParameterSet</span></span>

```
Register-PSSessionConfiguration [-ProcessorArchitecture <String>] [-Name] <String> [-AssemblyName] <String>
 [-ApplicationBase <String>] [-ConfigurationTypeName] <String> [-RunAsCredential <PSCredential>]
 [-ThreadApartmentState <ApartmentState>] [-ThreadOptions <PSThreadOptions>]
 [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess] [-StartupScript <String>]
 [-MaximumReceivedDataSizePerCommandMB <Double>] [-MaximumReceivedObjectSizeMB <Double>]
 [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI] [-Force] [-NoServiceRestart]
 [-PSVersion <Version>] [-SessionTypeOption <PSSessionTypeOption>] [-TransportOption <PSTransportOption>]
 [-ModulesToImport <Object[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="255c5-108">Sessionconfigurationfile</span><span class="sxs-lookup"><span data-stu-id="255c5-108">SessionConfigurationFile</span></span>

```
Register-PSSessionConfiguration [-ProcessorArchitecture <String>] [-Name] <String>
 [-RunAsCredential <PSCredential>] [-ThreadApartmentState <ApartmentState>] [-ThreadOptions <PSThreadOptions>]
 [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess] [-StartupScript <String>]
 [-MaximumReceivedDataSizePerCommandMB <Double>] [-MaximumReceivedObjectSizeMB <Double>]
 [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI] [-Force] [-NoServiceRestart]
 [-TransportOption <PSTransportOption>] -Path <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="255c5-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="255c5-109">DESCRIPTION</span></span>

<span data-ttu-id="255c5-110">Das `Register-PSSessionConfiguration` -Cmdlet erstellt und registriert eine neue Sitzungs Konfiguration auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="255c5-110">The `Register-PSSessionConfiguration` cmdlet creates and registers a new session configuration on the local computer.</span></span> <span data-ttu-id="255c5-111">Hierbei handelt es sich um ein erweitertes Cmdlet, das Sie zum Erstellen benutzerdefinierter Sitzungen für Remote Benutzer verwenden können.</span><span class="sxs-lookup"><span data-stu-id="255c5-111">This is an advanced cmdlet that you can use to create custom sessions for remote users.</span></span>

<span data-ttu-id="255c5-112">Jede PowerShell-Sitzung (**PSSession**) verwendet eine Sitzungs Konfiguration, auch als Endpunkt bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="255c5-112">Every PowerShell session (**PSSession**) uses a session configuration, also known as an endpoint.</span></span>
<span data-ttu-id="255c5-113">Wenn Benutzer eine Sitzung erstellen, die eine Verbindung mit dem Computer herstellt, können Sie eine Sitzungs Konfiguration auswählen oder die Standard Sitzungs Konfiguration verwenden, die beim Aktivieren von PowerShell-Remoting registriert wird.</span><span class="sxs-lookup"><span data-stu-id="255c5-113">When users create a session that connects to the computer, they can select a session configuration or use the default session configuration that is registered when you enable PowerShell remoting.</span></span>
<span data-ttu-id="255c5-114">Benutzer können auch die $PSSessionConfigurationName-Einstellungsvariable festlegen, die eine Standardkonfiguration für in der aktuellen Sitzung erstellte Remotesitzungen angibt.</span><span class="sxs-lookup"><span data-stu-id="255c5-114">Users can also set the $PSSessionConfigurationName preference variable, which specifies a default configuration for remote sessions created in the current session.</span></span>

<span data-ttu-id="255c5-115">Die Sitzungskonfiguration definiert die Umgebung für die Remotesitzung.</span><span class="sxs-lookup"><span data-stu-id="255c5-115">The session configuration defines the environment for the remote session.</span></span> <span data-ttu-id="255c5-116">Die Konfiguration kann festlegen, welche Befehle und Sprachelemente in der Sitzung verfügbar sind und Einstellungen zum Schutz des Computers enthalten, wie z. B. Beschränkungen der Datenmenge, die von der Sitzung remote in einem einzigen Objekt oder Befehl empfangen werden kann.</span><span class="sxs-lookup"><span data-stu-id="255c5-116">The configuration can determine which commands and language elements are available in the session, and it can include settings that protect the computer, such as those that limit the amount of data that the session can receive remotely in a single object or command.</span></span> <span data-ttu-id="255c5-117">Die Sicherheits Beschreibung der Sitzungs Konfiguration bestimmt, welche Benutzer über die Berechtigung zum Verwenden der Sitzungs Konfiguration verfügen.</span><span class="sxs-lookup"><span data-stu-id="255c5-117">The security descriptor of the session configuration determines which users have permission to use the session configuration.</span></span>

<span data-ttu-id="255c5-118">Sie können die Elemente der Konfiguration mit einer Assembly definieren, die eine neue Konfigurationsklasse implementiert, sowie mithilfe eines Skripts, das in der Sitzung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="255c5-118">You can define the elements of configuration by using an assembly that implements a new configuration class and by using a script that runs in the session.</span></span> <span data-ttu-id="255c5-119">Ab PowerShell 3,0 können Sie auch eine Sitzungs Konfigurationsdatei verwenden, um die Sitzungs Konfiguration zu definieren.</span><span class="sxs-lookup"><span data-stu-id="255c5-119">Beginning in PowerShell 3.0, you can also use a session configuration file to define the session configuration.</span></span>

<span data-ttu-id="255c5-120">Weitere Informationen zu Sitzungs Konfigurationen finden Sie unter [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="255c5-120">For information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>
<span data-ttu-id="255c5-121">Weitere Informationen zu Sitzungs Konfigurationsdateien finden Sie unter [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span><span class="sxs-lookup"><span data-stu-id="255c5-121">For information about session configuration files, see [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span></span>

## <span data-ttu-id="255c5-122">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="255c5-122">EXAMPLES</span></span>

### <span data-ttu-id="255c5-123">Beispiel 1: Registrieren einer Newshell-Sitzungs Konfiguration</span><span class="sxs-lookup"><span data-stu-id="255c5-123">Example 1: Register a NewShell session configuration</span></span>

<span data-ttu-id="255c5-124">In diesem Beispiel registrieren wir die **Newshell** -Sitzungs Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="255c5-124">In this example, we register the **NewShell** session configuration.</span></span> <span data-ttu-id="255c5-125">Die Parameter **AssemblyName** und **ApplicationBase** geben den Speicherort der **MyShell.dll** Datei an, die die Cmdlets und Anbieter in der Sitzungs Konfiguration angibt.</span><span class="sxs-lookup"><span data-stu-id="255c5-125">The **AssemblyName** and **ApplicationBase** parameters specify the location of the **MyShell.dll** file, which specifies the cmdlets and providers in the session configuration.</span></span> <span data-ttu-id="255c5-126">Der **configurationtypame** -Parameter gibt die Konfigurations Klasse an, die aus der Assembly verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="255c5-126">The **ConfigurationTypeName** parameter specifies the configuration class to use from the assembly.</span></span>

```powershell
$sessionConfiguration = @{
    Name='NewShell'
    ApplicationBase='c:\MyShells\'
    AssemblyName='MyShell.dll'
    ConfigurationTypeName='MyClass'
}
Register-PSSessionConfiguration @sessionConfiguration
```

<span data-ttu-id="255c5-127">Um diese Konfiguration zu verwenden, geben Sie ein `New-PSSession -ConfigurationName newshell` .</span><span class="sxs-lookup"><span data-stu-id="255c5-127">To use this configuration, type `New-PSSession -ConfigurationName newshell`.</span></span>

### <span data-ttu-id="255c5-128">Beispiel 2: Registrieren einer maintenanceshell-Sitzungs Konfiguration</span><span class="sxs-lookup"><span data-stu-id="255c5-128">Example 2: Register a MaintenanceShell session configuration</span></span>

<span data-ttu-id="255c5-129">In diesem Beispiel wird die **maintenanceshell** -Sitzungs Konfiguration auf dem lokalen Computer registriert.</span><span class="sxs-lookup"><span data-stu-id="255c5-129">This example registers the **MaintenanceShell** session configuration on the local computer.</span></span> <span data-ttu-id="255c5-130">Der **startupscript** -Parameter gibt das `Maintenance.ps1` Skript an.</span><span class="sxs-lookup"><span data-stu-id="255c5-130">The **StartupScript** parameter specifies the `Maintenance.ps1` script.</span></span>

```powershell
Register-PSSessionConfiguration -Name MaintenanceShell -StartupScript C:\ps-test\Maintenance.ps1
```

<span data-ttu-id="255c5-131">Wenn ein Benutzer einen `New-PSSession` Befehl verwendet und die **maintenanceshell** -Konfiguration auswählt, wird das `Maintenance.ps1` Skript in der neuen Sitzung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="255c5-131">When a user uses a `New-PSSession` command and selects the **MaintenanceShell** configuration, the `Maintenance.ps1` script runs in the new session.</span></span> <span data-ttu-id="255c5-132">Das Skript kann die Sitzung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="255c5-132">The script can configure the session.</span></span> <span data-ttu-id="255c5-133">Dies schließt das Importieren von Modulen und das Festlegen der Ausführungs Richtlinie für die Sitzung ein.</span><span class="sxs-lookup"><span data-stu-id="255c5-133">This includes importing modules and setting the execution policy for the session.</span></span> <span data-ttu-id="255c5-134">Wenn das Skript Fehler generiert, einschließlich Fehler ohne Abbruch, `New-PSSession` schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="255c5-134">If the script generates any errors, including non-terminating errors, the `New-PSSession` command fails.</span></span>

### <span data-ttu-id="255c5-135">Beispiel 3: Registrieren einer Sitzungs Konfiguration</span><span class="sxs-lookup"><span data-stu-id="255c5-135">Example 3: Register a session configuration</span></span>

<span data-ttu-id="255c5-136">In diesem Beispiel wird die **adminshell** -Sitzungs Konfiguration registriert.</span><span class="sxs-lookup"><span data-stu-id="255c5-136">This example registers the **AdminShell** session configuration.</span></span>

<span data-ttu-id="255c5-137">Die `$sessionParams` Variable ist eine Hash Tabelle, die alle Parameterwerte enthält.</span><span class="sxs-lookup"><span data-stu-id="255c5-137">The `$sessionParams` variable is a hashtable containing all the parameter values.</span></span> <span data-ttu-id="255c5-138">Diese Hash Tabelle wird mithilfe von PowerShell-splatting an das Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="255c5-138">This hashtable is passed to the cmdlet using PowerShell splatting.</span></span> <span data-ttu-id="255c5-139">Der `Register-PSSessionConfiguration` Befehl verwendet den **securitydescritorsddl** -Parameter, um die SDDL im Wert der `$sddl` Variablen anzugeben, und den **maximumreceivedobjectsizemb** -Parameter, um das Objektgrößen Limit zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="255c5-139">The `Register-PSSessionConfiguration` command uses the **SecurityDescritorSDDL** parameter to specify the SDDL in the value of the `$sddl` variable and the **MaximumReceivedObjectSizeMB** parameter to increase the object size limit.</span></span> <span data-ttu-id="255c5-140">Darüber hinaus verwendet er den **StartupScript**-Parameter, um ein Skript für die Sitzungskonfiguration anzugeben.</span><span class="sxs-lookup"><span data-stu-id="255c5-140">It also uses the **StartupScript** parameter to specify a script that configures the session.</span></span>

```powershell
$sddl = "O:NSG:BAD:P(A;;GA;;;BA)S:P(AU;FA;GA;;;WD)(AU;FA;SA;GWGX;;WD)"
$sessionParams = @{
    Name="AdminShell"
    SecurityDescriptorSDDL=$sddl
    MaximumReceivedObjectSizeMB=20
    StartupScript="C:\scripts\AdminShell.ps1"
}
Register-PSSessionConfiguration @sessionParams
```

### <span data-ttu-id="255c5-141">Beispiel 4: Zurückgeben eines Konfigurations Container Elements</span><span class="sxs-lookup"><span data-stu-id="255c5-141">Example 4: Return a configuration container element</span></span>

<span data-ttu-id="255c5-142">Dieses Beispiel zeigt, wie die **maintenanceshell** -Konfiguration registriert wird.</span><span class="sxs-lookup"><span data-stu-id="255c5-142">This example shows how to register the **MaintenanceShell** configuration.</span></span>
<span data-ttu-id="255c5-143">`Register-PSSessionConfiguration` Gibt ein **wsmanconfigcontainerelement** -Objekt zurück, das in der Variablen gespeichert ist `$s` .</span><span class="sxs-lookup"><span data-stu-id="255c5-143">`Register-PSSessionConfiguration` returns a **WSManConfigContainerElement** object stored in the `$s` variable.</span></span> <span data-ttu-id="255c5-144">`Format-List` zeigt alle Eigenschaften des zurückgegebenen Objekts an.</span><span class="sxs-lookup"><span data-stu-id="255c5-144">`Format-List` displays all the properties of the returned object.</span></span> <span data-ttu-id="255c5-145">Die **PSPath**-Eigenschaft zeigt, dass das Objekt in einem Verzeichnis auf dem WSMan:-Laufwerk gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="255c5-145">The **PSPath** property shows that the object is stored in a directory of the WSMan: drive.</span></span> <span data-ttu-id="255c5-146">`Get-ChildItem` (Alias `dir` ) zeigt die Elemente im `WSMan:\LocalHost\PlugIn` Pfad an.</span><span class="sxs-lookup"><span data-stu-id="255c5-146">`Get-ChildItem` (alias `dir`) displays the items in the `WSMan:\LocalHost\PlugIn` path.</span></span> <span data-ttu-id="255c5-147">Hierzu gehören die neue **maintenanceshell** -Konfiguration und die beiden Standardkonfigurationen, die in PowerShell enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="255c5-147">These include the new **MaintenanceShell** configuration and the two default configurations that come with PowerShell.</span></span>

```powershell
$s = Register-PSSessionConfiguration -Name MaintenanceShell -StartupScript C:\ps-test\Maintenance.ps1
$s | Format-List -Property *
dir WSMan:\LocalHost\Plugin
```

```Output
PSPath            : Microsoft.WSMan.Management\WSMan::localhost\Plugin\MaintenanceShell
PSParentPath      : Microsoft.WSMan.Management\WSMan::localhost\Plugin
PSChildName       : MaintenanceShell
PSDrive           : WSMan
PSProvider        : Microsoft.WSMan.Management\WSMan
PSIsContainer     : True
Keys              : {Name=MaintenanceShell}
Name              : MaintenanceShell
TypeNameOfElement : Container

Name                      Type                 Keys
----                      ----                 ----
MaintenanceShell          Container            {Name=MaintenanceShell}
microsoft.powershell      Container            {Name=microsoft.powershell}
microsoft.powershell32    Container            {Name=microsoft.powershell32}
```

### <span data-ttu-id="255c5-148">Beispiel 5: Registrieren einer Sitzungs Konfiguration mit einem Startskript</span><span class="sxs-lookup"><span data-stu-id="255c5-148">Example 5: Register a session configuration with a startup script</span></span>

<span data-ttu-id="255c5-149">In diesem Beispiel erstellen und registrieren wir die **withprofile** -Sitzungs Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="255c5-149">In this example we create and register the **WithProfile** session configuration.</span></span> <span data-ttu-id="255c5-150">Der **startupscript** -Parameter weist PowerShell an, das angegebene Skript für jede Sitzung auszuführen, die die Sitzungs Konfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="255c5-150">The **StartupScript** parameter directs PowerShell to run the specified script for any session that uses the session configuration.</span></span>

```powershell
Register-PSSessionConfiguration -Name WithProfile -StartupScript Add-Profile.ps1
```

<span data-ttu-id="255c5-151">Das Skript enthält einen einzelnen Befehl, der DOT-Quellentnahme verwendet, um das **CurrentUserAllHosts**-Profil des Benutzers im aktuellen Bereich der Sitzung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="255c5-151">The script contains a single command that uses dot sourcing to run the user's **CurrentUserAllHosts** profile in the current scope of the session.</span></span>

<span data-ttu-id="255c5-152">Weitere Informationen zu Profilen finden Sie unter [about_Profiles](./About/about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="255c5-152">For more information about profiles, see [about_Profiles](./About/about_Profiles.md).</span></span> <span data-ttu-id="255c5-153">Weitere Informationen zur DOT-Quellentnahme finden Sie unter [about_Scopes](./About/about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="255c5-153">For more information about dot sourcing, see [about_Scopes](./About/about_Scopes.md).</span></span>

## <span data-ttu-id="255c5-154">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="255c5-154">PARAMETERS</span></span>

### <span data-ttu-id="255c5-155">-AccessMode</span><span class="sxs-lookup"><span data-stu-id="255c5-155">-AccessMode</span></span>

<span data-ttu-id="255c5-156">Aktiviert und deaktiviert die Sitzungskonfiguration und bestimmt, ob sie für Remote- oder lokale Sitzungen auf dem Computer verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="255c5-156">Enables and disables the session configuration and determines whether it can be used for remote or local sessions on the computer.</span></span> <span data-ttu-id="255c5-157">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="255c5-157">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="255c5-158">Deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="255c5-158">Disabled.</span></span> <span data-ttu-id="255c5-159">Deaktiviert die Sitzungskonfiguration.</span><span class="sxs-lookup"><span data-stu-id="255c5-159">Disables the session configuration.</span></span> <span data-ttu-id="255c5-160">Sie kann nicht für Remote- oder lokalen Zugriff auf den Computer verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="255c5-160">It cannot be used for remote or local access to the computer.</span></span>
- <span data-ttu-id="255c5-161">Lokal.</span><span class="sxs-lookup"><span data-stu-id="255c5-161">Local.</span></span> <span data-ttu-id="255c5-162">Ermöglicht Benutzern des lokalen Computers die Verwendung der Sitzungs Konfiguration zum Erstellen einer lokalen Loopback Sitzung auf demselben Computer, verweigert aber Remote Benutzern den Zugriff.</span><span class="sxs-lookup"><span data-stu-id="255c5-162">Allows users of the local computer to use the session configuration to create a local loopback session on the same computer, but denies access to remote users.</span></span>
- <span data-ttu-id="255c5-163">Remote.</span><span class="sxs-lookup"><span data-stu-id="255c5-163">Remote.</span></span> <span data-ttu-id="255c5-164">Ermöglicht lokalen und Remotebenutzern die Verwendung der Sitzungskonfiguration zum Erstellen von Sitzungen und Ausführen von Befehlen auf diesem Computer.</span><span class="sxs-lookup"><span data-stu-id="255c5-164">Allows local and remote users to use the session configuration to create sessions and run commands on this computer.</span></span>

<span data-ttu-id="255c5-165">Der Standardwert ist Remote.</span><span class="sxs-lookup"><span data-stu-id="255c5-165">The default value is Remote.</span></span>

<span data-ttu-id="255c5-166">Andere Cmdlets können den Wert dieses Parameters später überschreiben.</span><span class="sxs-lookup"><span data-stu-id="255c5-166">Other cmdlets can override the value of this parameter later.</span></span> <span data-ttu-id="255c5-167">Beispielsweise ermöglicht das `Enable-PSRemoting` Cmdlet den Remote Zugriff auf alle Sitzungs Konfigurationen, das `Enable-PSSessionConfiguration` Cmdlet aktiviert Sitzungs Konfigurationen, und das `Disable-PSRemoting` Cmdlet verhindert den Remote Zugriff auf alle Sitzungs Konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="255c5-167">For example, the `Enable-PSRemoting` cmdlet allows for remote access to all session configurations, the `Enable-PSSessionConfiguration` cmdlet enables session configurations, and the `Disable-PSRemoting` cmdlet prevents remote access to all session configurations.</span></span>

<span data-ttu-id="255c5-168">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="255c5-168">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="255c5-169">-ApplicationBase</span><span class="sxs-lookup"><span data-stu-id="255c5-169">-ApplicationBase</span></span>

<span data-ttu-id="255c5-170">Gibt den Pfad der \* **Assemblydatei** (. dll) an, die im Wert des AssemblyName-Parameters angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="255c5-170">Specifies the path of the assembly file (\*.dll) that is specified in the value of the **AssemblyName** parameter.</span></span> <span data-ttu-id="255c5-171">Verwenden Sie diesen Parameter, wenn der Wert des **AssemblyName**-Parameters keinen Pfad enthält.</span><span class="sxs-lookup"><span data-stu-id="255c5-171">Use this parameter when the value of the **AssemblyName** parameter does not include a path.</span></span> <span data-ttu-id="255c5-172">Der Standardwert ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="255c5-172">The default is the current directory.</span></span>

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

### <span data-ttu-id="255c5-173">-AssemblyName</span><span class="sxs-lookup"><span data-stu-id="255c5-173">-AssemblyName</span></span>

<span data-ttu-id="255c5-174">Gibt den Namen einer \* Assemblydatei (. dll) an, in der der Konfigurationstyp definiert ist.</span><span class="sxs-lookup"><span data-stu-id="255c5-174">Specifies the name of an assembly file (\*.dll) in which the configuration type is defined.</span></span> <span data-ttu-id="255c5-175">Sie können den Pfad der DLL-Datei in diesem Parameter oder im Wert des **ApplicationBase** -Parameters angeben.</span><span class="sxs-lookup"><span data-stu-id="255c5-175">You can specify the path of the .dll in this parameter or in the value of the **ApplicationBase** parameter.</span></span>

<span data-ttu-id="255c5-176">Dieser Parameter ist erforderlich, wenn Sie den **configurationtypame** -Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="255c5-176">This parameter is required when you specify the **ConfigurationTypeName** parameter.</span></span>

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

### <span data-ttu-id="255c5-177">-Configurationtyname</span><span class="sxs-lookup"><span data-stu-id="255c5-177">-ConfigurationTypeName</span></span>

<span data-ttu-id="255c5-178">Gibt den vollqualifizierten Namen des Microsoft .NET Framework-Typs an, der für diese Konfiguration verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="255c5-178">Specifies the fully qualified name of the Microsoft .NET Framework type that is used for this configuration.</span></span> <span data-ttu-id="255c5-179">Der Typ, den Sie angeben, muss die **System.Management.Automation.Remoting.PSSessionConfiguration** Klasse implementieren.</span><span class="sxs-lookup"><span data-stu-id="255c5-179">The type that you specify must implement the **System.Management.Automation.Remoting.PSSessionConfiguration** class.</span></span>

<span data-ttu-id="255c5-180">Um die \* **Assemblydatei** (. dll) anzugeben, die den Konfigurationstyp implementiert, geben Sie die Parameter AssemblyName und **ApplicationBase** an.</span><span class="sxs-lookup"><span data-stu-id="255c5-180">To specify the assembly file (\*.dll) that implements the configuration type, specify the **AssemblyName** and **ApplicationBase** parameters.</span></span>

<span data-ttu-id="255c5-181">Durch das Erstellen eines Typs können Sie weitere Aspekte der Sitzungs Konfiguration steuern, z. b. das verfügbar machen oder Ausblenden bestimmter Parameter von Cmdlets oder das Festlegen von Datengrößen-und Objektgrößen Beschränkungen, die von Benutzern nicht überschrieben werden können.</span><span class="sxs-lookup"><span data-stu-id="255c5-181">Creating a type lets you control more aspects of the session configuration, such as exposing or hiding certain parameters of cmdlets, or setting data size and object size limits that users cannot override.</span></span>

<span data-ttu-id="255c5-182">Wenn Sie diesen Parameter weglassen, wird die **DefaultRemotePowerShellConfiguration**-Klasse für die Sitzungskonfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="255c5-182">If you omit this parameter, the **DefaultRemotePowerShellConfiguration** class is used for the session configuration.</span></span>

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

### <span data-ttu-id="255c5-183">-Force</span><span class="sxs-lookup"><span data-stu-id="255c5-183">-Force</span></span>

<span data-ttu-id="255c5-184">Unterdrückt alle Benutzer Aufforderungen und startet den **WinRM** -Dienst ohne Aufforderung neu.</span><span class="sxs-lookup"><span data-stu-id="255c5-184">Suppresses all user prompts and restarts the **WinRM** service without prompting.</span></span> <span data-ttu-id="255c5-185">Durch Neustarten des Diensts wird die Konfigurationsänderung übernommen.</span><span class="sxs-lookup"><span data-stu-id="255c5-185">Restarting the service makes the configuration change effective.</span></span>

<span data-ttu-id="255c5-186">Um einen Neustart zu verhindern und die Aufforderung zum Neustart zu unterdrücken, geben Sie den **noservicerestart** -Parameter an.</span><span class="sxs-lookup"><span data-stu-id="255c5-186">To prevent a restart and suppress the restart prompt, specify the **NoServiceRestart** parameter.</span></span>

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

### <span data-ttu-id="255c5-187">-Maximumreceiveddatasizepercommandmb</span><span class="sxs-lookup"><span data-stu-id="255c5-187">-MaximumReceivedDataSizePerCommandMB</span></span>

<span data-ttu-id="255c5-188">Gibt einen Grenzwert für die Datenmenge an, die in jedem einzelnen Remote Befehl an diesen Computer gesendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="255c5-188">Specifies a limit for the amount of data that can be sent to this computer in any single remote command.</span></span> <span data-ttu-id="255c5-189">Geben Sie die Datengröße in Megabyte (MB) ein.</span><span class="sxs-lookup"><span data-stu-id="255c5-189">Enter the data size in megabytes (MB).</span></span> <span data-ttu-id="255c5-190">Der Standardwert ist 50 MB.</span><span class="sxs-lookup"><span data-stu-id="255c5-190">The default is 50 MB.</span></span>

<span data-ttu-id="255c5-191">Wenn eine Datengrößenbeschränkung im Konfigurationstyp definiert ist, der im **ConfigurationTypeName**-Parameter angegeben ist, wird die Beschränkung im Konfigurationstyp verwendet und der Wert dieses Parameters ignoriert.</span><span class="sxs-lookup"><span data-stu-id="255c5-191">If a data size limit is defined in the configuration type that is specified in the **ConfigurationTypeName** parameter, the limit in the configuration type is used and the value of this parameter is ignored.</span></span>

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

### <span data-ttu-id="255c5-192">-Maximumreceivedobjectsizemb</span><span class="sxs-lookup"><span data-stu-id="255c5-192">-MaximumReceivedObjectSizeMB</span></span>

<span data-ttu-id="255c5-193">Gibt einen Grenzwert für die Datenmenge an, die in jedem einzelnen Objekt an diesen Computer gesendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="255c5-193">Specifies a limit for the amount of data that can be sent to this computer in any single object.</span></span>
<span data-ttu-id="255c5-194">Geben Sie die Datengröße in Megabyte ein.</span><span class="sxs-lookup"><span data-stu-id="255c5-194">Enter the data size in megabytes.</span></span> <span data-ttu-id="255c5-195">Der Standardwert ist 10 MB.</span><span class="sxs-lookup"><span data-stu-id="255c5-195">The default is 10 MB.</span></span>

<span data-ttu-id="255c5-196">Wenn eine Objektgrößenbeschränkung im Konfigurationstyp definiert ist, der im **ConfigurationTypeName**-Parameter angegeben ist, wird die Beschränkung im Konfigurationstyp verwendet und der Wert dieses Parameters ignoriert.</span><span class="sxs-lookup"><span data-stu-id="255c5-196">If an object size limit is defined in the configuration type that is specified in the **ConfigurationTypeName** parameter, the limit in the configuration type is used and the value of this parameter is ignored.</span></span>

```yaml
Type: System.Nullable`1[System.Double]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 10
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="255c5-197">-Modulestoimport</span><span class="sxs-lookup"><span data-stu-id="255c5-197">-ModulesToImport</span></span>

<span data-ttu-id="255c5-198">Gibt die Module an, die automatisch in Sitzungen importiert werden, die die Sitzungs Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="255c5-198">Specifies the modules that are automatically imported into sessions that use the session configuration.</span></span>

<span data-ttu-id="255c5-199">Standardmäßig wird nur **Microsoft. PowerShell. Core** in Sitzungen importiert.</span><span class="sxs-lookup"><span data-stu-id="255c5-199">By default, only **Microsoft.PowerShell.Core** is imported into sessions.</span></span> <span data-ttu-id="255c5-200">Wenn die Cmdlets nicht ausgeschlossen sind, können Sie verwenden, `Import-Module` um der Sitzung Module hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="255c5-200">Unless the cmdlets are excluded, you can use `Import-Module` to add modules to the session.</span></span>

<span data-ttu-id="255c5-201">Die in diesem Parameterwert angegebenen Module werden in Ergänzungen zu Modulen importiert, die durch den **SessionType** -Parameter angegeben werden, und die Module, die im Schlüssel **modulestoimport** in der Sitzungs Konfigurationsdatei () aufgelistet sind `New-PSSessionConfigurationFile` .</span><span class="sxs-lookup"><span data-stu-id="255c5-201">The modules specified in this parameter value are imported in additions to modules that are specified by the **SessionType** parameter and those listed in the **ModulesToImport** key in the session configuration file (`New-PSSessionConfigurationFile`).</span></span> <span data-ttu-id="255c5-202">Einstellungen in der Sitzungskonfigurationsdatei können jedoch die von Modulen exportierten Befehle ausblenden oder verhindern, dass Benutzer sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="255c5-202">However, settings in the session configuration file can hide the commands exported by modules or prevent users from using them.</span></span>

<span data-ttu-id="255c5-203">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="255c5-203">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="255c5-204">-Name</span><span class="sxs-lookup"><span data-stu-id="255c5-204">-Name</span></span>

<span data-ttu-id="255c5-205">Gibt einen Namen für die Sitzungskonfiguration an.</span><span class="sxs-lookup"><span data-stu-id="255c5-205">Specifies a name for the session configuration.</span></span> <span data-ttu-id="255c5-206">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="255c5-206">This parameter is required.</span></span>

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

### <span data-ttu-id="255c5-207">-Noservicerestart</span><span class="sxs-lookup"><span data-stu-id="255c5-207">-NoServiceRestart</span></span>

<span data-ttu-id="255c5-208">Der **WinRM** -Dienst wird nicht neu gestartet, und die Aufforderung zum Neustarten des Dienstanbieter wird unterdrückt.</span><span class="sxs-lookup"><span data-stu-id="255c5-208">Does not restart the **WinRM** service, and suppresses the prompt to restart the service.</span></span>

<span data-ttu-id="255c5-209">Wenn Sie einen `Register-PSSessionConfiguration` Befehl ausführen, werden Sie standardmäßig aufgefordert, den **WinRM** -Dienst neu zu starten, damit die neue Sitzungs Konfiguration wirksam wird.</span><span class="sxs-lookup"><span data-stu-id="255c5-209">By default, when you run a `Register-PSSessionConfiguration` command, you are prompted to restart the **WinRM** service to make the new session configuration effective.</span></span> <span data-ttu-id="255c5-210">Bis der **WinRM** -Dienst neu gestartet wird, ist die neue Sitzungs Konfiguration nicht wirksam.</span><span class="sxs-lookup"><span data-stu-id="255c5-210">Until the **WinRM** service is restarted, the new session configuration is not effective.</span></span>

<span data-ttu-id="255c5-211">Um den **WinRM** -Dienst ohne Aufforderung neu zu starten, geben Sie den **Force** -Parameter an.</span><span class="sxs-lookup"><span data-stu-id="255c5-211">To restart the **WinRM** service without prompting, specify the **Force** parameter.</span></span> <span data-ttu-id="255c5-212">Verwenden Sie das-Cmdlet, um den **WinRM** -Dienst manuell neu zu starten `Restart-Service` .</span><span class="sxs-lookup"><span data-stu-id="255c5-212">To restart the **WinRM** service manually, use the `Restart-Service` cmdlet.</span></span>

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

### <span data-ttu-id="255c5-213">-Path</span><span class="sxs-lookup"><span data-stu-id="255c5-213">-Path</span></span>

<span data-ttu-id="255c5-214">Gibt den Pfad und den Dateinamen einer Sitzungs Konfigurationsdatei (. PSSC) an, z. b. eine, die von erstellt wurde `New-PSSessionConfigurationFile` .</span><span class="sxs-lookup"><span data-stu-id="255c5-214">Specifies the path and filename of a session configuration file (.pssc), such as one created by `New-PSSessionConfigurationFile`.</span></span> <span data-ttu-id="255c5-215">Wenn Sie den Pfad weglassen, ist die Standardeinstellung das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="255c5-215">If you omit the path, the default is the current directory.</span></span>

<span data-ttu-id="255c5-216">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="255c5-216">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="255c5-217">-ProcessorArchitecture</span><span class="sxs-lookup"><span data-stu-id="255c5-217">-ProcessorArchitecture</span></span>

<span data-ttu-id="255c5-218">Bestimmt, ob eine 32-Bit-oder 64-Bit-Version des PowerShell-Prozesses in Sitzungen gestartet wird, die diese Sitzungs Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="255c5-218">Determines whether a 32-bit or 64-bit version of the PowerShell process is started in sessions that use this session configuration.</span></span> <span data-ttu-id="255c5-219">Die zulässigen Werte für diesen Parameter sind: x86 (32-Bit) und amd64 (64-Bit).</span><span class="sxs-lookup"><span data-stu-id="255c5-219">The acceptable values for this parameter are: x86 (32-bit) and AMD64 (64-bit).</span></span> <span data-ttu-id="255c5-220">Der Standardwert wird von der Prozessorarchitektur des Computers bestimmt, der die Sitzungskonfiguration hostet.</span><span class="sxs-lookup"><span data-stu-id="255c5-220">The default value is determined by the processor architecture of the computer that hosts the session configuration.</span></span>

<span data-ttu-id="255c5-221">Sie können diesen Parameter verwenden, um eine 32-Bit-Sitzung auf einem 64-Bit-Computer zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="255c5-221">You can use this parameter to create a 32-bit session on a 64-bit computer.</span></span> <span data-ttu-id="255c5-222">Versuche zum Erstellen eines 64-Bit-Prozesses auf einem 32-Bit-Computer schlagen fehl.</span><span class="sxs-lookup"><span data-stu-id="255c5-222">Attempts to create a 64-bit process on a 32-bit computer fail.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PA
Accepted values: x86, amd64

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="255c5-223">-Psversion</span><span class="sxs-lookup"><span data-stu-id="255c5-223">-PSVersion</span></span>

<span data-ttu-id="255c5-224">Gibt die Version von PowerShell in Sitzungen an, die diese Sitzungs Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="255c5-224">Specifies the version of PowerShell in sessions that use this session configuration.</span></span>

<span data-ttu-id="255c5-225">Der Wert dieses Parameters hat Vorrang vor den Wert des **PowerShellVersion**-Schlüssels in der Sitzungskonfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="255c5-225">The value of this parameter takes precedence over the value of the **PowerShellVersion** key in the session configuration file.</span></span>

<span data-ttu-id="255c5-226">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="255c5-226">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="255c5-227">-Runascredential</span><span class="sxs-lookup"><span data-stu-id="255c5-227">-RunAsCredential</span></span>

<span data-ttu-id="255c5-228">Gibt Anmelde Informationen für Befehle in der Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="255c5-228">Specifies credentials for commands in the session.</span></span> <span data-ttu-id="255c5-229">Standardmäßig werden Befehle mit den Berechtigungen des aktuellen Benutzers ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="255c5-229">By default, commands run with the permissions of the current user.</span></span>

<span data-ttu-id="255c5-230">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="255c5-230">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="255c5-231">-SecurityDescriptor SDDL</span><span class="sxs-lookup"><span data-stu-id="255c5-231">-SecurityDescriptorSddl</span></span>

<span data-ttu-id="255c5-232">Gibt eine Zeichenfolge für die Security Descriptor Definition Language (SDDL) der Konfiguration an.</span><span class="sxs-lookup"><span data-stu-id="255c5-232">Specifies a Security Descriptor Definition Language (SDDL) string for the configuration.</span></span>

<span data-ttu-id="255c5-233">Diese Zeichenfolge bestimmt die Berechtigungen, die erforderlich sind, um die Konfiguration für die neue Sitzung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="255c5-233">This string determines the permissions that are required to use the new session configuration.</span></span> <span data-ttu-id="255c5-234">Um eine Sitzungs Konfiguration in einer Sitzung zu verwenden, müssen die Benutzer mindestens über die Berechtigung Execute (aufrufen) für die Konfiguration verfügen.</span><span class="sxs-lookup"><span data-stu-id="255c5-234">To use a session configuration in a session, users must have at least Execute (Invoke) permission for the configuration.</span></span>

<span data-ttu-id="255c5-235">Wenn die Sicherheitsbeschreibung komplex ist, sollten Sie den **ShowSecurityDescriptorUI**-Parameter anstelle dieses Parameters verwenden.</span><span class="sxs-lookup"><span data-stu-id="255c5-235">If the security descriptor is complex, consider using the **ShowSecurityDescriptorUI** parameter instead of this parameter.</span></span> <span data-ttu-id="255c5-236">Sie können nicht beide Parameter im selben Befehl verwenden.</span><span class="sxs-lookup"><span data-stu-id="255c5-236">You cannot use both parameters in the same command.</span></span>

<span data-ttu-id="255c5-237">Wenn Sie diesen Parameter weglassen, wird die Stamm-SDDL für den **WinRM** -Dienst für diese Konfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="255c5-237">If you omit this parameter, the root SDDL for the **WinRM** service is used for this configuration.</span></span>
<span data-ttu-id="255c5-238">Verwenden Sie zum Anzeigen oder Ändern der Stamm-SDDL den WSMan-Anbieter.</span><span class="sxs-lookup"><span data-stu-id="255c5-238">To view or change the root SDDL, use the WSMan provider.</span></span> <span data-ttu-id="255c5-239">Beispiel: `Get-Item wsman:\localhost\service\rootSDDL`.</span><span class="sxs-lookup"><span data-stu-id="255c5-239">For example `Get-Item wsman:\localhost\service\rootSDDL`.</span></span> <span data-ttu-id="255c5-240">Weitere Informationen zum WSMAN-Anbieter erhalten Sie, wenn Sie eingeben `Get-Help wsman` .</span><span class="sxs-lookup"><span data-stu-id="255c5-240">For more information about the WSMan provider, type `Get-Help wsman`.</span></span>

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

### <span data-ttu-id="255c5-241">-Sessiontypeoption</span><span class="sxs-lookup"><span data-stu-id="255c5-241">-SessionTypeOption</span></span>

<span data-ttu-id="255c5-242">Gibt typspezifische Optionen für die Sitzungs Konfiguration an.</span><span class="sxs-lookup"><span data-stu-id="255c5-242">Specifies type-specific options for the session configuration.</span></span> <span data-ttu-id="255c5-243">Geben Sie ein "Session TYPE Options"-Objekt ein, z. b. das vom Cmdlet zurückgegebene **psworkflowexecutionoption** -Objekt `New-PSWorkflowExecutionOption` .</span><span class="sxs-lookup"><span data-stu-id="255c5-243">Enter a session type options object, such as the **PSWorkflowExecutionOption** object that the `New-PSWorkflowExecutionOption` cmdlet returns.</span></span>

<span data-ttu-id="255c5-244">Die Optionen der Sitzungen, die die Sitzungskonfiguration verwenden, werden durch die Werte der Sitzungsoptionen und die Sitzungskonfigurationsoptionen bestimmt.</span><span class="sxs-lookup"><span data-stu-id="255c5-244">The options of sessions that use the session configuration are determined by the values of session options and the session configuration options.</span></span> <span data-ttu-id="255c5-245">Sofern nicht angegeben, haben in der Sitzung festgelegte Optionen, z. b. mit dem `New-PSSessionOption` Cmdlet, Vorrang vor den in der Sitzungs Konfiguration festgelegten Optionen.</span><span class="sxs-lookup"><span data-stu-id="255c5-245">Unless specified, options set in the session, such as by using the `New-PSSessionOption` cmdlet, take precedence over options set in the session configuration.</span></span> <span data-ttu-id="255c5-246">Die Sitzungsoptionswerte dürfen aber nicht die in der Sitzungskonfiguration festgelegten Höchstwerte überschreiten.</span><span class="sxs-lookup"><span data-stu-id="255c5-246">However, session option values cannot exceed maximum values set in the session configuration.</span></span>

<span data-ttu-id="255c5-247">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="255c5-247">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="255c5-248">-Showsecuritydescriptor UI</span><span class="sxs-lookup"><span data-stu-id="255c5-248">-ShowSecurityDescriptorUI</span></span>

<span data-ttu-id="255c5-249">Gibt an, dass dieses Cmdlet ein Eigenschaften Blatt anzeigt, das Ihnen hilft, die SDDL für die Sitzungs Konfiguration zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="255c5-249">Indicates that this cmdlet displays a property sheet that helps you create the SDDL for the session configuration.</span></span> <span data-ttu-id="255c5-250">Das Eigenschaften Blatt wird angezeigt, nachdem Sie den `Register-PSSessionConfiguration` Befehl eingegeben und dann den **WinRM** -Dienst neu gestartet haben.</span><span class="sxs-lookup"><span data-stu-id="255c5-250">The property sheet appears after you enter the `Register-PSSessionConfiguration` command and then restart the **WinRM** service.</span></span>

<span data-ttu-id="255c5-251">Denken Sie beim Festlegen der Berechtigungen für die Konfiguration daran, dass Benutzer mindestens über die Berechtigung Execute (aufrufen) verfügen müssen, um die Sitzungs Konfiguration in einer Sitzung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="255c5-251">When setting the permissions for the configuration, remember that users must have at least Execute (Invoke) permission to use the session configuration in a session.</span></span>

<span data-ttu-id="255c5-252">Sie können den **SecurityDescriptorSDDL**-Parameter und diesen Parameter nicht im selben Befehl verwenden.</span><span class="sxs-lookup"><span data-stu-id="255c5-252">You cannot use the **SecurityDescriptorSDDL** parameter and this parameter in the same command.</span></span>

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

### <span data-ttu-id="255c5-253">-Startupscript</span><span class="sxs-lookup"><span data-stu-id="255c5-253">-StartupScript</span></span>

<span data-ttu-id="255c5-254">Gibt den voll qualifizierten Pfad eines PowerShell-Skripts an.</span><span class="sxs-lookup"><span data-stu-id="255c5-254">Specifies the fully qualified path of a PowerShell script.</span></span> <span data-ttu-id="255c5-255">Das angegebene Skript wird in der neuen Sitzung ausgeführt, die die Sitzungskonfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="255c5-255">The specified script runs in the new session that uses the session configuration.</span></span>

<span data-ttu-id="255c5-256">Sie können das Skript verwenden, um die Sitzung zusätzlich zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="255c5-256">You can use the script to additionally configure the session.</span></span> <span data-ttu-id="255c5-257">Wenn das Skript einen Fehler (auch einen Fehler ohne Abbruch) generiert, wird die Sitzung nicht erstellt, und der `New-PSSession` Befehl schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="255c5-257">If the script generates an error, even a non-terminating error, the session is not created and the `New-PSSession` command fails.</span></span>

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

### <span data-ttu-id="255c5-258">-Threadoptions</span><span class="sxs-lookup"><span data-stu-id="255c5-258">-ThreadOptions</span></span>

<span data-ttu-id="255c5-259">Gibt an, wie Threads erstellt und verwendet werden, wenn ein Befehl in der Sitzung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="255c5-259">Specifies how threads are created and used when a command runs in the session.</span></span> <span data-ttu-id="255c5-260">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="255c5-260">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="255c5-261">Standard</span><span class="sxs-lookup"><span data-stu-id="255c5-261">Default</span></span>
- <span data-ttu-id="255c5-262">Reusethread</span><span class="sxs-lookup"><span data-stu-id="255c5-262">ReuseThread</span></span>
- <span data-ttu-id="255c5-263">UseCurrentThread</span><span class="sxs-lookup"><span data-stu-id="255c5-263">UseCurrentThread</span></span>
- <span data-ttu-id="255c5-264">Usenewthread</span><span class="sxs-lookup"><span data-stu-id="255c5-264">UseNewThread</span></span>

<span data-ttu-id="255c5-265">Der Standardwert ist **usecurrentthread**.</span><span class="sxs-lookup"><span data-stu-id="255c5-265">The default value is **UseCurrentThread**.</span></span>

<span data-ttu-id="255c5-266">Weitere Informationen finden Sie unter [psthlesoptions-Enumeration](/dotnet/api/system.management.automation.runspaces.psthreadoptions?view=powershellsdk-1.1.0).</span><span class="sxs-lookup"><span data-stu-id="255c5-266">For more information, see [PSThreadOptions Enumeration](/dotnet/api/system.management.automation.runspaces.psthreadoptions?view=powershellsdk-1.1.0).</span></span>

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

### <span data-ttu-id="255c5-267">-Transportoption</span><span class="sxs-lookup"><span data-stu-id="255c5-267">-TransportOption</span></span>

<span data-ttu-id="255c5-268">Gibt die Transport Option an.</span><span class="sxs-lookup"><span data-stu-id="255c5-268">Specifies the transport option.</span></span>

<span data-ttu-id="255c5-269">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="255c5-269">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="255c5-270">--Vorgang</span><span class="sxs-lookup"><span data-stu-id="255c5-270">-UseSharedProcess</span></span>

<span data-ttu-id="255c5-271">Verwenden Sie nur einen Prozess, um alle Sitzungen zu hosten, die vom gleichen Benutzer gestartet wurden und die gleiche Sitzungs Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="255c5-271">Use only one process to host all sessions that are started by the same user and use the same session configuration.</span></span> <span data-ttu-id="255c5-272">Standardmäßig wird jede Sitzung in einem eigenen Prozess gehostet.</span><span class="sxs-lookup"><span data-stu-id="255c5-272">By default, each session is hosted in its own process.</span></span>

<span data-ttu-id="255c5-273">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="255c5-273">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="255c5-274">-Confirm</span><span class="sxs-lookup"><span data-stu-id="255c5-274">-Confirm</span></span>

<span data-ttu-id="255c5-275">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="255c5-275">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="255c5-276">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="255c5-276">-WhatIf</span></span>

<span data-ttu-id="255c5-277">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="255c5-277">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="255c5-278">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="255c5-278">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="255c5-279">-Threadapartmentstate</span><span class="sxs-lookup"><span data-stu-id="255c5-279">-ThreadApartmentState</span></span>

<span data-ttu-id="255c5-280">Gibt den Apartment Zustand des Threading Moduls an, das verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="255c5-280">Specifies the apartment state of the threading module to be used.</span></span> <span data-ttu-id="255c5-281">Zulässige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="255c5-281">Acceptable values are:</span></span>

- <span data-ttu-id="255c5-282">Unbekannt</span><span class="sxs-lookup"><span data-stu-id="255c5-282">Unknown</span></span>
- <span data-ttu-id="255c5-283">MTA</span><span class="sxs-lookup"><span data-stu-id="255c5-283">MTA</span></span>
- <span data-ttu-id="255c5-284">STA</span><span class="sxs-lookup"><span data-stu-id="255c5-284">STA</span></span>

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

### <span data-ttu-id="255c5-285">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="255c5-285">CommonParameters</span></span>

<span data-ttu-id="255c5-286">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="255c5-286">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="255c5-287">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="255c5-287">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="255c5-288">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="255c5-288">INPUTS</span></span>

### <span data-ttu-id="255c5-289">Keine</span><span class="sxs-lookup"><span data-stu-id="255c5-289">None</span></span>

<span data-ttu-id="255c5-290">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="255c5-290">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="255c5-291">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="255c5-291">OUTPUTS</span></span>

### <span data-ttu-id="255c5-292">Microsoft. WSMAN. Management. wsmanconfigcontainerelement</span><span class="sxs-lookup"><span data-stu-id="255c5-292">Microsoft.WSMan.Management.WSManConfigContainerElement</span></span>

## <span data-ttu-id="255c5-293">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="255c5-293">NOTES</span></span>

<span data-ttu-id="255c5-294">Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="255c5-294">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="255c5-295">Zum Ausführen dieses Cmdlets müssen Sie PowerShell mit der Option **als Administrator ausführen** starten.</span><span class="sxs-lookup"><span data-stu-id="255c5-295">To run this cmdlet you must start PowerShell by using the **Run as administrator** option.</span></span>

<span data-ttu-id="255c5-296">Dieses Cmdlet generiert XML, das eine Plug-in-Konfiguration für Web Services for Management (WS-Management) darstellt, und sendet die XML-Datei an WS-Management, die das Plug-in auf dem lokalen Computer registriert ( `New-Item wsman:\localhost\plugin` ).</span><span class="sxs-lookup"><span data-stu-id="255c5-296">This cmdlet generates XML that represents a Web Services for Management (WS-Management) plug-in configuration and sends the XML to WS-Management, which registers the plug-in on the local computer (`New-Item wsman:\localhost\plugin`).</span></span>

<span data-ttu-id="255c5-297">Die Eigenschaften eines Sitzungskonfigurationsobjekts weichen hinsichtlich der für die Sitzungskonfiguration festgelegten Optionen sowie der Werte dieser Optionen ab.</span><span class="sxs-lookup"><span data-stu-id="255c5-297">The properties of a session configuration object vary with the options set for the session configuration and the values of those options.</span></span> <span data-ttu-id="255c5-298">Sitzungskonfigurationen, die eine Sitzungskonfigurationsdatei verwenden, haben außerdem zusätzliche Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="255c5-298">Also, session configurations that use a session configuration file have additional properties.</span></span>

## <span data-ttu-id="255c5-299">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="255c5-299">RELATED LINKS</span></span>

[<span data-ttu-id="255c5-300">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="255c5-300">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="255c5-301">Enable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="255c5-301">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="255c5-302">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="255c5-302">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="255c5-303">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="255c5-303">New-PSSessionConfigurationFile</span></span>](New-PSSessionConfigurationFile.md)

[<span data-ttu-id="255c5-304">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="255c5-304">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="255c5-305">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="255c5-305">Test-PSSessionConfigurationFile</span></span>](Test-PSSessionConfigurationFile.md)

[<span data-ttu-id="255c5-306">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="255c5-306">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="255c5-307">WSMan-Anbieter</span><span class="sxs-lookup"><span data-stu-id="255c5-307">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="255c5-308">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="255c5-308">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)

[<span data-ttu-id="255c5-309">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="255c5-309">about_Session_Configuration_Files</span></span>](About/about_Session_Configuration_Files.md)
