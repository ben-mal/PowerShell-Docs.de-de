---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/register-pssessionconfiguration?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-PSSessionConfiguration
ms.openlocfilehash: c0dd413e315d5905467d5591ed64eb971cbb0dbe
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210404"
---
# <span data-ttu-id="c6da4-103">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="c6da4-103">Register-PSSessionConfiguration</span></span>

## <span data-ttu-id="c6da4-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="c6da4-104">SYNOPSIS</span></span>
<span data-ttu-id="c6da4-105">Erstellt und registriert eine neue Sitzungskonfiguration.</span><span class="sxs-lookup"><span data-stu-id="c6da4-105">Creates and registers a new session configuration.</span></span>

## <span data-ttu-id="c6da4-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c6da4-106">SYNTAX</span></span>

### <span data-ttu-id="c6da4-107">Nameparameterset (Standard)</span><span class="sxs-lookup"><span data-stu-id="c6da4-107">NameParameterSet (Default)</span></span>

```
Register-PSSessionConfiguration [-ProcessorArchitecture <String>] [-Name] <String> [-ApplicationBase <String>]
 [-RunAsCredential <PSCredential>] [-ThreadApartmentState <ApartmentState>] [-ThreadOptions <PSThreadOptions>]
 [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess] [-StartupScript <String>]
 [-MaximumReceivedDataSizePerCommandMB <Double>] [-MaximumReceivedObjectSizeMB <Double>]
 [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI] [-Force] [-NoServiceRestart]
 [-PSVersion <Version>] [-SessionTypeOption <PSSessionTypeOption>] [-TransportOption <PSTransportOption>]
 [-ModulesToImport <Object[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="c6da4-108">Assemblynameparameterset</span><span class="sxs-lookup"><span data-stu-id="c6da4-108">AssemblyNameParameterSet</span></span>

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

### <span data-ttu-id="c6da4-109">Sessionconfigurationfile</span><span class="sxs-lookup"><span data-stu-id="c6da4-109">SessionConfigurationFile</span></span>

```
Register-PSSessionConfiguration [-ProcessorArchitecture <String>] [-Name] <String>
 [-RunAsCredential <PSCredential>] [-ThreadApartmentState <ApartmentState>] [-ThreadOptions <PSThreadOptions>]
 [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess] [-StartupScript <String>]
 [-MaximumReceivedDataSizePerCommandMB <Double>] [-MaximumReceivedObjectSizeMB <Double>]
 [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI] [-Force] [-NoServiceRestart]
 [-TransportOption <PSTransportOption>] -Path <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="c6da4-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c6da4-110">DESCRIPTION</span></span>

<span data-ttu-id="c6da4-111">Das `Register-PSSessionConfiguration` -Cmdlet erstellt und registriert eine neue Sitzungs Konfiguration auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="c6da4-111">The `Register-PSSessionConfiguration` cmdlet creates and registers a new session configuration on the local computer.</span></span> <span data-ttu-id="c6da4-112">Hierbei handelt es sich um ein erweitertes Cmdlet, das Sie zum Erstellen benutzerdefinierter Sitzungen für Remote Benutzer verwenden können.</span><span class="sxs-lookup"><span data-stu-id="c6da4-112">This is an advanced cmdlet that you can use to create custom sessions for remote users.</span></span>

<span data-ttu-id="c6da4-113">Jede PowerShell-Sitzung ( **PSSession** ) verwendet eine Sitzungs Konfiguration, auch als Endpunkt bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="c6da4-113">Every PowerShell session ( **PSSession** ) uses a session configuration, also known as an endpoint.</span></span>
<span data-ttu-id="c6da4-114">Wenn Benutzer eine Sitzung erstellen, die eine Verbindung mit dem Computer herstellt, können Sie eine Sitzungs Konfiguration auswählen oder die Standard Sitzungs Konfiguration verwenden, die beim Aktivieren von PowerShell-Remoting registriert wird.</span><span class="sxs-lookup"><span data-stu-id="c6da4-114">When users create a session that connects to the computer, they can select a session configuration or use the default session configuration that is registered when you enable PowerShell remoting.</span></span>
<span data-ttu-id="c6da4-115">Benutzer können auch die $PSSessionConfigurationName-Einstellungsvariable festlegen, die eine Standardkonfiguration für in der aktuellen Sitzung erstellte Remotesitzungen angibt.</span><span class="sxs-lookup"><span data-stu-id="c6da4-115">Users can also set the $PSSessionConfigurationName preference variable, which specifies a default configuration for remote sessions created in the current session.</span></span>

<span data-ttu-id="c6da4-116">Die Sitzungskonfiguration definiert die Umgebung für die Remotesitzung.</span><span class="sxs-lookup"><span data-stu-id="c6da4-116">The session configuration defines the environment for the remote session.</span></span> <span data-ttu-id="c6da4-117">Die Konfiguration kann festlegen, welche Befehle und Sprachelemente in der Sitzung verfügbar sind und Einstellungen zum Schutz des Computers enthalten, wie z. B. Beschränkungen der Datenmenge, die von der Sitzung remote in einem einzigen Objekt oder Befehl empfangen werden kann.</span><span class="sxs-lookup"><span data-stu-id="c6da4-117">The configuration can determine which commands and language elements are available in the session, and it can include settings that protect the computer, such as those that limit the amount of data that the session can receive remotely in a single object or command.</span></span> <span data-ttu-id="c6da4-118">Die Sicherheits Beschreibung der Sitzungs Konfiguration bestimmt, welche Benutzer über die Berechtigung zum Verwenden der Sitzungs Konfiguration verfügen.</span><span class="sxs-lookup"><span data-stu-id="c6da4-118">The security descriptor of the session configuration determines which users have permission to use the session configuration.</span></span>

<span data-ttu-id="c6da4-119">Sie können die Elemente der Konfiguration mit einer Assembly definieren, die eine neue Konfigurationsklasse implementiert, sowie mithilfe eines Skripts, das in der Sitzung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c6da4-119">You can define the elements of configuration by using an assembly that implements a new configuration class and by using a script that runs in the session.</span></span> <span data-ttu-id="c6da4-120">Ab PowerShell 3,0 können Sie auch eine Sitzungs Konfigurationsdatei verwenden, um die Sitzungs Konfiguration zu definieren.</span><span class="sxs-lookup"><span data-stu-id="c6da4-120">Beginning in PowerShell 3.0, you can also use a session configuration file to define the session configuration.</span></span>

<span data-ttu-id="c6da4-121">Weitere Informationen zu Sitzungs Konfigurationen finden Sie unter [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="c6da4-121">For information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>
<span data-ttu-id="c6da4-122">Weitere Informationen zu Sitzungs Konfigurationsdateien finden Sie unter [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span><span class="sxs-lookup"><span data-stu-id="c6da4-122">For information about session configuration files, see [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span></span>

## <span data-ttu-id="c6da4-123">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="c6da4-123">EXAMPLES</span></span>

### <span data-ttu-id="c6da4-124">Beispiel 1: Registrieren einer Newshell-Sitzungs Konfiguration</span><span class="sxs-lookup"><span data-stu-id="c6da4-124">Example 1: Register a NewShell session configuration</span></span>

<span data-ttu-id="c6da4-125">In diesem Beispiel registrieren wir die **Newshell** -Sitzungs Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="c6da4-125">In this example, we register the **NewShell** session configuration.</span></span> <span data-ttu-id="c6da4-126">Die Parameter **AssemblyName** und **ApplicationBase** geben den Speicherort der **MyShell.dll** Datei an, die die Cmdlets und Anbieter in der Sitzungs Konfiguration angibt.</span><span class="sxs-lookup"><span data-stu-id="c6da4-126">The **AssemblyName** and **ApplicationBase** parameters specify the location of the **MyShell.dll** file, which specifies the cmdlets and providers in the session configuration.</span></span> <span data-ttu-id="c6da4-127">Der **configurationtypame** -Parameter gibt die Konfigurations Klasse an, die aus der Assembly verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c6da4-127">The **ConfigurationTypeName** parameter specifies the configuration class to use from the assembly.</span></span>

```powershell
$sessionConfiguration = @{
    Name='NewShell'
    ApplicationBase='c:\MyShells\'
    AssemblyName='MyShell.dll'
    ConfigurationTypeName='MyClass'
}
Register-PSSessionConfiguration @sessionConfiguration
```

<span data-ttu-id="c6da4-128">Um diese Konfiguration zu verwenden, geben Sie ein `New-PSSession -ConfigurationName newshell` .</span><span class="sxs-lookup"><span data-stu-id="c6da4-128">To use this configuration, type `New-PSSession -ConfigurationName newshell`.</span></span>

### <span data-ttu-id="c6da4-129">Beispiel 2: Registrieren einer maintenanceshell-Sitzungs Konfiguration</span><span class="sxs-lookup"><span data-stu-id="c6da4-129">Example 2: Register a MaintenanceShell session configuration</span></span>

<span data-ttu-id="c6da4-130">In diesem Beispiel wird die **maintenanceshell** -Sitzungs Konfiguration auf dem lokalen Computer registriert.</span><span class="sxs-lookup"><span data-stu-id="c6da4-130">This example registers the **MaintenanceShell** session configuration on the local computer.</span></span> <span data-ttu-id="c6da4-131">Der **startupscript** -Parameter gibt das `Maintenance.ps1` Skript an.</span><span class="sxs-lookup"><span data-stu-id="c6da4-131">The **StartupScript** parameter specifies the `Maintenance.ps1` script.</span></span>

```powershell
Register-PSSessionConfiguration -Name MaintenanceShell -StartupScript C:\ps-test\Maintenance.ps1
```

<span data-ttu-id="c6da4-132">Wenn ein Benutzer einen `New-PSSession` Befehl verwendet und die **maintenanceshell** -Konfiguration auswählt, wird das `Maintenance.ps1` Skript in der neuen Sitzung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c6da4-132">When a user uses a `New-PSSession` command and selects the **MaintenanceShell** configuration, the `Maintenance.ps1` script runs in the new session.</span></span> <span data-ttu-id="c6da4-133">Das Skript kann die Sitzung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c6da4-133">The script can configure the session.</span></span> <span data-ttu-id="c6da4-134">Dies schließt das Importieren von Modulen und das Festlegen der Ausführungs Richtlinie für die Sitzung ein.</span><span class="sxs-lookup"><span data-stu-id="c6da4-134">This includes importing modules and setting the execution policy for the session.</span></span> <span data-ttu-id="c6da4-135">Wenn das Skript Fehler generiert, einschließlich Fehler ohne Abbruch, `New-PSSession` schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="c6da4-135">If the script generates any errors, including non-terminating errors, the `New-PSSession` command fails.</span></span>

### <span data-ttu-id="c6da4-136">Beispiel 3: Registrieren einer Sitzungs Konfiguration</span><span class="sxs-lookup"><span data-stu-id="c6da4-136">Example 3: Register a session configuration</span></span>

<span data-ttu-id="c6da4-137">In diesem Beispiel wird die **adminshell** -Sitzungs Konfiguration registriert.</span><span class="sxs-lookup"><span data-stu-id="c6da4-137">This example registers the **AdminShell** session configuration.</span></span>

<span data-ttu-id="c6da4-138">Die `$sessionParams` Variable ist eine Hash Tabelle, die alle Parameterwerte enthält.</span><span class="sxs-lookup"><span data-stu-id="c6da4-138">The `$sessionParams` variable is a hashtable containing all the parameter values.</span></span> <span data-ttu-id="c6da4-139">Diese Hash Tabelle wird mithilfe von PowerShell-splatting an das Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="c6da4-139">This hashtable is passed to the cmdlet using PowerShell splatting.</span></span> <span data-ttu-id="c6da4-140">Der `Register-PSSessionConfiguration` Befehl verwendet den **securitydescritorsddl** -Parameter, um die SDDL im Wert der `$sddl` Variablen anzugeben, und den **maximumreceivedobjectsizemb** -Parameter, um das Objektgrößen Limit zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="c6da4-140">The `Register-PSSessionConfiguration` command uses the **SecurityDescritorSDDL** parameter to specify the SDDL in the value of the `$sddl` variable and the **MaximumReceivedObjectSizeMB** parameter to increase the object size limit.</span></span> <span data-ttu-id="c6da4-141">Darüber hinaus verwendet er den **StartupScript** -Parameter, um ein Skript für die Sitzungskonfiguration anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c6da4-141">It also uses the **StartupScript** parameter to specify a script that configures the session.</span></span>

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

### <span data-ttu-id="c6da4-142">Beispiel 4: Zurückgeben eines Konfigurations Container Elements</span><span class="sxs-lookup"><span data-stu-id="c6da4-142">Example 4: Return a configuration container element</span></span>

<span data-ttu-id="c6da4-143">Dieses Beispiel zeigt, wie die **maintenanceshell** -Konfiguration registriert wird.</span><span class="sxs-lookup"><span data-stu-id="c6da4-143">This example shows how to register the **MaintenanceShell** configuration.</span></span>
<span data-ttu-id="c6da4-144">`Register-PSSessionConfiguration` Gibt ein **wsmanconfigcontainerelement** -Objekt zurück, das in der Variablen gespeichert ist `$s` .</span><span class="sxs-lookup"><span data-stu-id="c6da4-144">`Register-PSSessionConfiguration` returns a **WSManConfigContainerElement** object stored in the `$s` variable.</span></span> <span data-ttu-id="c6da4-145">`Format-List` zeigt alle Eigenschaften des zurückgegebenen Objekts an.</span><span class="sxs-lookup"><span data-stu-id="c6da4-145">`Format-List` displays all the properties of the returned object.</span></span> <span data-ttu-id="c6da4-146">Die **PSPath** -Eigenschaft zeigt, dass das Objekt in einem Verzeichnis auf dem WSMan:-Laufwerk gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="c6da4-146">The **PSPath** property shows that the object is stored in a directory of the WSMan: drive.</span></span> <span data-ttu-id="c6da4-147">`Get-ChildItem` (Alias `dir` ) zeigt die Elemente im `WSMan:\LocalHost\PlugIn` Pfad an.</span><span class="sxs-lookup"><span data-stu-id="c6da4-147">`Get-ChildItem` (alias `dir`) displays the items in the `WSMan:\LocalHost\PlugIn` path.</span></span> <span data-ttu-id="c6da4-148">Hierzu gehören die neue **maintenanceshell** -Konfiguration und die beiden Standardkonfigurationen, die in PowerShell enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="c6da4-148">These include the new **MaintenanceShell** configuration and the two default configurations that come with PowerShell.</span></span>

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

### <span data-ttu-id="c6da4-149">Beispiel 5: Registrieren einer Sitzungs Konfiguration mit einem Startskript</span><span class="sxs-lookup"><span data-stu-id="c6da4-149">Example 5: Register a session configuration with a startup script</span></span>

<span data-ttu-id="c6da4-150">In diesem Beispiel erstellen und registrieren wir die **withprofile** -Sitzungs Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="c6da4-150">In this example we create and register the **WithProfile** session configuration.</span></span> <span data-ttu-id="c6da4-151">Der **startupscript** -Parameter weist PowerShell an, das angegebene Skript für jede Sitzung auszuführen, die die Sitzungs Konfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="c6da4-151">The **StartupScript** parameter directs PowerShell to run the specified script for any session that uses the session configuration.</span></span>

```powershell
Register-PSSessionConfiguration -Name WithProfile -StartupScript Add-Profile.ps1
```

<span data-ttu-id="c6da4-152">Das Skript enthält einen einzelnen Befehl, der DOT-Quellentnahme verwendet, um das **CurrentUserAllHosts** -Profil des Benutzers im aktuellen Bereich der Sitzung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c6da4-152">The script contains a single command that uses dot sourcing to run the user's **CurrentUserAllHosts** profile in the current scope of the session.</span></span>

<span data-ttu-id="c6da4-153">Weitere Informationen zu Profilen finden Sie unter [about_Profiles](./About/about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="c6da4-153">For more information about profiles, see [about_Profiles](./About/about_Profiles.md).</span></span> <span data-ttu-id="c6da4-154">Weitere Informationen zur DOT-Quellentnahme finden Sie unter [about_Scopes](./About/about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="c6da4-154">For more information about dot sourcing, see [about_Scopes](./About/about_Scopes.md).</span></span>

## <span data-ttu-id="c6da4-155">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c6da4-155">PARAMETERS</span></span>

### <span data-ttu-id="c6da4-156">-AccessMode</span><span class="sxs-lookup"><span data-stu-id="c6da4-156">-AccessMode</span></span>

<span data-ttu-id="c6da4-157">Aktiviert und deaktiviert die Sitzungskonfiguration und bestimmt, ob sie für Remote- oder lokale Sitzungen auf dem Computer verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="c6da4-157">Enables and disables the session configuration and determines whether it can be used for remote or local sessions on the computer.</span></span> <span data-ttu-id="c6da4-158">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="c6da4-158">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="c6da4-159">Deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="c6da4-159">Disabled.</span></span> <span data-ttu-id="c6da4-160">Deaktiviert die Sitzungskonfiguration.</span><span class="sxs-lookup"><span data-stu-id="c6da4-160">Disables the session configuration.</span></span> <span data-ttu-id="c6da4-161">Sie kann nicht für Remote- oder lokalen Zugriff auf den Computer verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c6da4-161">It cannot be used for remote or local access to the computer.</span></span>
- <span data-ttu-id="c6da4-162">Lokal.</span><span class="sxs-lookup"><span data-stu-id="c6da4-162">Local.</span></span> <span data-ttu-id="c6da4-163">Ermöglicht Benutzern des lokalen Computers die Verwendung der Sitzungs Konfiguration zum Erstellen einer lokalen Loopback Sitzung auf demselben Computer, verweigert aber Remote Benutzern den Zugriff.</span><span class="sxs-lookup"><span data-stu-id="c6da4-163">Allows users of the local computer to use the session configuration to create a local loopback session on the same computer, but denies access to remote users.</span></span>
- <span data-ttu-id="c6da4-164">Remote.</span><span class="sxs-lookup"><span data-stu-id="c6da4-164">Remote.</span></span> <span data-ttu-id="c6da4-165">Ermöglicht lokalen und Remotebenutzern die Verwendung der Sitzungskonfiguration zum Erstellen von Sitzungen und Ausführen von Befehlen auf diesem Computer.</span><span class="sxs-lookup"><span data-stu-id="c6da4-165">Allows local and remote users to use the session configuration to create sessions and run commands on this computer.</span></span>

<span data-ttu-id="c6da4-166">Der Standardwert ist Remote.</span><span class="sxs-lookup"><span data-stu-id="c6da4-166">The default value is Remote.</span></span>

<span data-ttu-id="c6da4-167">Andere Cmdlets können den Wert dieses Parameters später überschreiben.</span><span class="sxs-lookup"><span data-stu-id="c6da4-167">Other cmdlets can override the value of this parameter later.</span></span> <span data-ttu-id="c6da4-168">Beispielsweise ermöglicht das `Enable-PSRemoting` Cmdlet den Remote Zugriff auf alle Sitzungs Konfigurationen, das `Enable-PSSessionConfiguration` Cmdlet aktiviert Sitzungs Konfigurationen, und das `Disable-PSRemoting` Cmdlet verhindert den Remote Zugriff auf alle Sitzungs Konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="c6da4-168">For example, the `Enable-PSRemoting` cmdlet allows for remote access to all session configurations, the `Enable-PSSessionConfiguration` cmdlet enables session configurations, and the `Disable-PSRemoting` cmdlet prevents remote access to all session configurations.</span></span>

<span data-ttu-id="c6da4-169">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="c6da4-169">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="c6da4-170">-ApplicationBase</span><span class="sxs-lookup"><span data-stu-id="c6da4-170">-ApplicationBase</span></span>

<span data-ttu-id="c6da4-171">Gibt den Pfad der \* **Assemblydatei** (. dll) an, die im Wert des AssemblyName-Parameters angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="c6da4-171">Specifies the path of the assembly file (\*.dll) that is specified in the value of the **AssemblyName** parameter.</span></span> <span data-ttu-id="c6da4-172">Verwenden Sie diesen Parameter, wenn der Wert des **AssemblyName** -Parameters keinen Pfad enthält.</span><span class="sxs-lookup"><span data-stu-id="c6da4-172">Use this parameter when the value of the **AssemblyName** parameter does not include a path.</span></span> <span data-ttu-id="c6da4-173">Der Standardwert ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="c6da4-173">The default is the current directory.</span></span>

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

### <span data-ttu-id="c6da4-174">-AssemblyName</span><span class="sxs-lookup"><span data-stu-id="c6da4-174">-AssemblyName</span></span>

<span data-ttu-id="c6da4-175">Gibt den Namen einer \* Assemblydatei (. dll) an, in der der Konfigurationstyp definiert ist.</span><span class="sxs-lookup"><span data-stu-id="c6da4-175">Specifies the name of an assembly file (\*.dll) in which the configuration type is defined.</span></span> <span data-ttu-id="c6da4-176">Sie können den Pfad der DLL-Datei in diesem Parameter oder im Wert des **ApplicationBase** -Parameters angeben.</span><span class="sxs-lookup"><span data-stu-id="c6da4-176">You can specify the path of the .dll in this parameter or in the value of the **ApplicationBase** parameter.</span></span>

<span data-ttu-id="c6da4-177">Dieser Parameter ist erforderlich, wenn Sie den **configurationtypame** -Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="c6da4-177">This parameter is required when you specify the **ConfigurationTypeName** parameter.</span></span>

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

### <span data-ttu-id="c6da4-178">-Configurationtyname</span><span class="sxs-lookup"><span data-stu-id="c6da4-178">-ConfigurationTypeName</span></span>

<span data-ttu-id="c6da4-179">Gibt den vollqualifizierten Namen des Microsoft .NET Framework-Typs an, der für diese Konfiguration verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c6da4-179">Specifies the fully qualified name of the Microsoft .NET Framework type that is used for this configuration.</span></span> <span data-ttu-id="c6da4-180">Der Typ, den Sie angeben, muss die **System.Management.Automation.Remoting.PSSessionConfiguration** Klasse implementieren.</span><span class="sxs-lookup"><span data-stu-id="c6da4-180">The type that you specify must implement the **System.Management.Automation.Remoting.PSSessionConfiguration** class.</span></span>

<span data-ttu-id="c6da4-181">Um die \* **Assemblydatei** (. dll) anzugeben, die den Konfigurationstyp implementiert, geben Sie die Parameter AssemblyName und **ApplicationBase** an.</span><span class="sxs-lookup"><span data-stu-id="c6da4-181">To specify the assembly file (\*.dll) that implements the configuration type, specify the **AssemblyName** and **ApplicationBase** parameters.</span></span>

<span data-ttu-id="c6da4-182">Durch das Erstellen eines Typs können Sie weitere Aspekte der Sitzungs Konfiguration steuern, z. b. das verfügbar machen oder Ausblenden bestimmter Parameter von Cmdlets oder das Festlegen von Datengrößen-und Objektgrößen Beschränkungen, die von Benutzern nicht überschrieben werden können.</span><span class="sxs-lookup"><span data-stu-id="c6da4-182">Creating a type lets you control more aspects of the session configuration, such as exposing or hiding certain parameters of cmdlets, or setting data size and object size limits that users cannot override.</span></span>

<span data-ttu-id="c6da4-183">Wenn Sie diesen Parameter weglassen, wird die **DefaultRemotePowerShellConfiguration** -Klasse für die Sitzungskonfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="c6da4-183">If you omit this parameter, the **DefaultRemotePowerShellConfiguration** class is used for the session configuration.</span></span>

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

### <span data-ttu-id="c6da4-184">-Force</span><span class="sxs-lookup"><span data-stu-id="c6da4-184">-Force</span></span>

<span data-ttu-id="c6da4-185">Unterdrückt alle Benutzer Aufforderungen und startet den **WinRM** -Dienst ohne Aufforderung neu.</span><span class="sxs-lookup"><span data-stu-id="c6da4-185">Suppresses all user prompts and restarts the **WinRM** service without prompting.</span></span> <span data-ttu-id="c6da4-186">Durch Neustarten des Diensts wird die Konfigurationsänderung übernommen.</span><span class="sxs-lookup"><span data-stu-id="c6da4-186">Restarting the service makes the configuration change effective.</span></span>

<span data-ttu-id="c6da4-187">Um einen Neustart zu verhindern und die Aufforderung zum Neustart zu unterdrücken, geben Sie den **noservicerestart** -Parameter an.</span><span class="sxs-lookup"><span data-stu-id="c6da4-187">To prevent a restart and suppress the restart prompt, specify the **NoServiceRestart** parameter.</span></span>

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

### <span data-ttu-id="c6da4-188">-Maximumreceiveddatasizepercommandmb</span><span class="sxs-lookup"><span data-stu-id="c6da4-188">-MaximumReceivedDataSizePerCommandMB</span></span>

<span data-ttu-id="c6da4-189">Gibt einen Grenzwert für die Datenmenge an, die in jedem einzelnen Remote Befehl an diesen Computer gesendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="c6da4-189">Specifies a limit for the amount of data that can be sent to this computer in any single remote command.</span></span> <span data-ttu-id="c6da4-190">Geben Sie die Datengröße in Megabyte (MB) ein.</span><span class="sxs-lookup"><span data-stu-id="c6da4-190">Enter the data size in megabytes (MB).</span></span> <span data-ttu-id="c6da4-191">Der Standardwert ist 50 MB.</span><span class="sxs-lookup"><span data-stu-id="c6da4-191">The default is 50 MB.</span></span>

<span data-ttu-id="c6da4-192">Wenn eine Datengrößenbeschränkung im Konfigurationstyp definiert ist, der im **ConfigurationTypeName** -Parameter angegeben ist, wird die Beschränkung im Konfigurationstyp verwendet und der Wert dieses Parameters ignoriert.</span><span class="sxs-lookup"><span data-stu-id="c6da4-192">If a data size limit is defined in the configuration type that is specified in the **ConfigurationTypeName** parameter, the limit in the configuration type is used and the value of this parameter is ignored.</span></span>

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

### <span data-ttu-id="c6da4-193">-Maximumreceivedobjectsizemb</span><span class="sxs-lookup"><span data-stu-id="c6da4-193">-MaximumReceivedObjectSizeMB</span></span>

<span data-ttu-id="c6da4-194">Gibt einen Grenzwert für die Datenmenge an, die in jedem einzelnen Objekt an diesen Computer gesendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="c6da4-194">Specifies a limit for the amount of data that can be sent to this computer in any single object.</span></span>
<span data-ttu-id="c6da4-195">Geben Sie die Datengröße in Megabyte ein.</span><span class="sxs-lookup"><span data-stu-id="c6da4-195">Enter the data size in megabytes.</span></span> <span data-ttu-id="c6da4-196">Der Standardwert ist 10 MB.</span><span class="sxs-lookup"><span data-stu-id="c6da4-196">The default is 10 MB.</span></span>

<span data-ttu-id="c6da4-197">Wenn eine Objektgrößenbeschränkung im Konfigurationstyp definiert ist, der im **ConfigurationTypeName** -Parameter angegeben ist, wird die Beschränkung im Konfigurationstyp verwendet und der Wert dieses Parameters ignoriert.</span><span class="sxs-lookup"><span data-stu-id="c6da4-197">If an object size limit is defined in the configuration type that is specified in the **ConfigurationTypeName** parameter, the limit in the configuration type is used and the value of this parameter is ignored.</span></span>

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

### <span data-ttu-id="c6da4-198">-Modulestoimport</span><span class="sxs-lookup"><span data-stu-id="c6da4-198">-ModulesToImport</span></span>

<span data-ttu-id="c6da4-199">Gibt die Module an, die automatisch in Sitzungen importiert werden, die die Sitzungs Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="c6da4-199">Specifies the modules that are automatically imported into sessions that use the session configuration.</span></span>

<span data-ttu-id="c6da4-200">Standardmäßig wird nur **Microsoft. PowerShell. Core** in Sitzungen importiert.</span><span class="sxs-lookup"><span data-stu-id="c6da4-200">By default, only **Microsoft.PowerShell.Core** is imported into sessions.</span></span> <span data-ttu-id="c6da4-201">Wenn die Cmdlets nicht ausgeschlossen sind, können Sie verwenden, `Import-Module` um der Sitzung Module hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="c6da4-201">Unless the cmdlets are excluded, you can use `Import-Module` to add modules to the session.</span></span>

<span data-ttu-id="c6da4-202">Die in diesem Parameterwert angegebenen Module werden in Ergänzungen zu Modulen importiert, die durch den **SessionType** -Parameter angegeben werden, und die Module, die im Schlüssel **modulestoimport** in der Sitzungs Konfigurationsdatei () aufgelistet sind `New-PSSessionConfigurationFile` .</span><span class="sxs-lookup"><span data-stu-id="c6da4-202">The modules specified in this parameter value are imported in additions to modules that are specified by the **SessionType** parameter and those listed in the **ModulesToImport** key in the session configuration file (`New-PSSessionConfigurationFile`).</span></span> <span data-ttu-id="c6da4-203">Einstellungen in der Sitzungskonfigurationsdatei können jedoch die von Modulen exportierten Befehle ausblenden oder verhindern, dass Benutzer sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="c6da4-203">However, settings in the session configuration file can hide the commands exported by modules or prevent users from using them.</span></span>

<span data-ttu-id="c6da4-204">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="c6da4-204">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="c6da4-205">-Name</span><span class="sxs-lookup"><span data-stu-id="c6da4-205">-Name</span></span>

<span data-ttu-id="c6da4-206">Gibt einen Namen für die Sitzungskonfiguration an.</span><span class="sxs-lookup"><span data-stu-id="c6da4-206">Specifies a name for the session configuration.</span></span> <span data-ttu-id="c6da4-207">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c6da4-207">This parameter is required.</span></span>

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

### <span data-ttu-id="c6da4-208">-Noservicerestart</span><span class="sxs-lookup"><span data-stu-id="c6da4-208">-NoServiceRestart</span></span>

<span data-ttu-id="c6da4-209">Der **WinRM** -Dienst wird nicht neu gestartet, und die Aufforderung zum Neustarten des Dienstanbieter wird unterdrückt.</span><span class="sxs-lookup"><span data-stu-id="c6da4-209">Does not restart the **WinRM** service, and suppresses the prompt to restart the service.</span></span>

<span data-ttu-id="c6da4-210">Wenn Sie einen `Register-PSSessionConfiguration` Befehl ausführen, werden Sie standardmäßig aufgefordert, den **WinRM** -Dienst neu zu starten, damit die neue Sitzungs Konfiguration wirksam wird.</span><span class="sxs-lookup"><span data-stu-id="c6da4-210">By default, when you run a `Register-PSSessionConfiguration` command, you are prompted to restart the **WinRM** service to make the new session configuration effective.</span></span> <span data-ttu-id="c6da4-211">Bis der **WinRM** -Dienst neu gestartet wird, ist die neue Sitzungs Konfiguration nicht wirksam.</span><span class="sxs-lookup"><span data-stu-id="c6da4-211">Until the **WinRM** service is restarted, the new session configuration is not effective.</span></span>

<span data-ttu-id="c6da4-212">Um den **WinRM** -Dienst ohne Aufforderung neu zu starten, geben Sie den **Force** -Parameter an.</span><span class="sxs-lookup"><span data-stu-id="c6da4-212">To restart the **WinRM** service without prompting, specify the **Force** parameter.</span></span> <span data-ttu-id="c6da4-213">Verwenden Sie das-Cmdlet, um den **WinRM** -Dienst manuell neu zu starten `Restart-Service` .</span><span class="sxs-lookup"><span data-stu-id="c6da4-213">To restart the **WinRM** service manually, use the `Restart-Service` cmdlet.</span></span>

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

### <span data-ttu-id="c6da4-214">-Path</span><span class="sxs-lookup"><span data-stu-id="c6da4-214">-Path</span></span>

<span data-ttu-id="c6da4-215">Gibt den Pfad und den Dateinamen einer Sitzungs Konfigurationsdatei (. PSSC) an, z. b. eine, die von erstellt wurde `New-PSSessionConfigurationFile` .</span><span class="sxs-lookup"><span data-stu-id="c6da4-215">Specifies the path and filename of a session configuration file (.pssc), such as one created by `New-PSSessionConfigurationFile`.</span></span> <span data-ttu-id="c6da4-216">Wenn Sie den Pfad weglassen, ist die Standardeinstellung das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="c6da4-216">If you omit the path, the default is the current directory.</span></span>

<span data-ttu-id="c6da4-217">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="c6da4-217">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="c6da4-218">-ProcessorArchitecture</span><span class="sxs-lookup"><span data-stu-id="c6da4-218">-ProcessorArchitecture</span></span>

<span data-ttu-id="c6da4-219">Bestimmt, ob eine 32-Bit-oder 64-Bit-Version des PowerShell-Prozesses in Sitzungen gestartet wird, die diese Sitzungs Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="c6da4-219">Determines whether a 32-bit or 64-bit version of the PowerShell process is started in sessions that use this session configuration.</span></span> <span data-ttu-id="c6da4-220">Die zulässigen Werte für diesen Parameter sind: x86 (32-Bit) und amd64 (64-Bit).</span><span class="sxs-lookup"><span data-stu-id="c6da4-220">The acceptable values for this parameter are: x86 (32-bit) and AMD64 (64-bit).</span></span> <span data-ttu-id="c6da4-221">Der Standardwert wird von der Prozessorarchitektur des Computers bestimmt, der die Sitzungskonfiguration hostet.</span><span class="sxs-lookup"><span data-stu-id="c6da4-221">The default value is determined by the processor architecture of the computer that hosts the session configuration.</span></span>

<span data-ttu-id="c6da4-222">Sie können diesen Parameter verwenden, um eine 32-Bit-Sitzung auf einem 64-Bit-Computer zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c6da4-222">You can use this parameter to create a 32-bit session on a 64-bit computer.</span></span> <span data-ttu-id="c6da4-223">Versuche zum Erstellen eines 64-Bit-Prozesses auf einem 32-Bit-Computer schlagen fehl.</span><span class="sxs-lookup"><span data-stu-id="c6da4-223">Attempts to create a 64-bit process on a 32-bit computer fail.</span></span>

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

### <span data-ttu-id="c6da4-224">-Psversion</span><span class="sxs-lookup"><span data-stu-id="c6da4-224">-PSVersion</span></span>

<span data-ttu-id="c6da4-225">Gibt die Version von PowerShell in Sitzungen an, die diese Sitzungs Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="c6da4-225">Specifies the version of PowerShell in sessions that use this session configuration.</span></span>

<span data-ttu-id="c6da4-226">Der Wert dieses Parameters hat Vorrang vor den Wert des **PowerShellVersion** -Schlüssels in der Sitzungskonfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="c6da4-226">The value of this parameter takes precedence over the value of the **PowerShellVersion** key in the session configuration file.</span></span>

<span data-ttu-id="c6da4-227">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="c6da4-227">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="c6da4-228">-Runascredential</span><span class="sxs-lookup"><span data-stu-id="c6da4-228">-RunAsCredential</span></span>

<span data-ttu-id="c6da4-229">Gibt Anmelde Informationen für Befehle in der Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="c6da4-229">Specifies credentials for commands in the session.</span></span> <span data-ttu-id="c6da4-230">Standardmäßig werden Befehle mit den Berechtigungen des aktuellen Benutzers ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c6da4-230">By default, commands run with the permissions of the current user.</span></span>

<span data-ttu-id="c6da4-231">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="c6da4-231">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="c6da4-232">-SecurityDescriptor SDDL</span><span class="sxs-lookup"><span data-stu-id="c6da4-232">-SecurityDescriptorSddl</span></span>

<span data-ttu-id="c6da4-233">Gibt eine Zeichenfolge für die Security Descriptor Definition Language (SDDL) der Konfiguration an.</span><span class="sxs-lookup"><span data-stu-id="c6da4-233">Specifies a Security Descriptor Definition Language (SDDL) string for the configuration.</span></span>

<span data-ttu-id="c6da4-234">Diese Zeichenfolge bestimmt die Berechtigungen, die erforderlich sind, um die Konfiguration für die neue Sitzung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="c6da4-234">This string determines the permissions that are required to use the new session configuration.</span></span> <span data-ttu-id="c6da4-235">Um eine Sitzungs Konfiguration in einer Sitzung zu verwenden, müssen die Benutzer mindestens über die Berechtigung Execute (aufrufen) für die Konfiguration verfügen.</span><span class="sxs-lookup"><span data-stu-id="c6da4-235">To use a session configuration in a session, users must have at least Execute (Invoke) permission for the configuration.</span></span>

<span data-ttu-id="c6da4-236">Wenn die Sicherheitsbeschreibung komplex ist, sollten Sie den **ShowSecurityDescriptorUI** -Parameter anstelle dieses Parameters verwenden.</span><span class="sxs-lookup"><span data-stu-id="c6da4-236">If the security descriptor is complex, consider using the **ShowSecurityDescriptorUI** parameter instead of this parameter.</span></span> <span data-ttu-id="c6da4-237">Sie können nicht beide Parameter im selben Befehl verwenden.</span><span class="sxs-lookup"><span data-stu-id="c6da4-237">You cannot use both parameters in the same command.</span></span>

<span data-ttu-id="c6da4-238">Wenn Sie diesen Parameter weglassen, wird die Stamm-SDDL für den **WinRM** -Dienst für diese Konfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="c6da4-238">If you omit this parameter, the root SDDL for the **WinRM** service is used for this configuration.</span></span>
<span data-ttu-id="c6da4-239">Verwenden Sie zum Anzeigen oder Ändern der Stamm-SDDL den WSMan-Anbieter.</span><span class="sxs-lookup"><span data-stu-id="c6da4-239">To view or change the root SDDL, use the WSMan provider.</span></span> <span data-ttu-id="c6da4-240">Beispiel: `Get-Item wsman:\localhost\service\rootSDDL`.</span><span class="sxs-lookup"><span data-stu-id="c6da4-240">For example `Get-Item wsman:\localhost\service\rootSDDL`.</span></span> <span data-ttu-id="c6da4-241">Weitere Informationen zum WSMAN-Anbieter erhalten Sie, wenn Sie eingeben `Get-Help wsman` .</span><span class="sxs-lookup"><span data-stu-id="c6da4-241">For more information about the WSMan provider, type `Get-Help wsman`.</span></span>

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

### <span data-ttu-id="c6da4-242">-Sessiontypeoption</span><span class="sxs-lookup"><span data-stu-id="c6da4-242">-SessionTypeOption</span></span>

<span data-ttu-id="c6da4-243">Gibt typspezifische Optionen für die Sitzungs Konfiguration an.</span><span class="sxs-lookup"><span data-stu-id="c6da4-243">Specifies type-specific options for the session configuration.</span></span> <span data-ttu-id="c6da4-244">Geben Sie ein "Session TYPE Options"-Objekt ein, z. b. das vom Cmdlet zurückgegebene **psworkflowexecutionoption** -Objekt `New-PSWorkflowExecutionOption` .</span><span class="sxs-lookup"><span data-stu-id="c6da4-244">Enter a session type options object, such as the **PSWorkflowExecutionOption** object that the `New-PSWorkflowExecutionOption` cmdlet returns.</span></span>

<span data-ttu-id="c6da4-245">Die Optionen der Sitzungen, die die Sitzungskonfiguration verwenden, werden durch die Werte der Sitzungsoptionen und die Sitzungskonfigurationsoptionen bestimmt.</span><span class="sxs-lookup"><span data-stu-id="c6da4-245">The options of sessions that use the session configuration are determined by the values of session options and the session configuration options.</span></span> <span data-ttu-id="c6da4-246">Sofern nicht angegeben, haben in der Sitzung festgelegte Optionen, z. b. mit dem `New-PSSessionOption` Cmdlet, Vorrang vor den in der Sitzungs Konfiguration festgelegten Optionen.</span><span class="sxs-lookup"><span data-stu-id="c6da4-246">Unless specified, options set in the session, such as by using the `New-PSSessionOption` cmdlet, take precedence over options set in the session configuration.</span></span> <span data-ttu-id="c6da4-247">Die Sitzungsoptionswerte dürfen aber nicht die in der Sitzungskonfiguration festgelegten Höchstwerte überschreiten.</span><span class="sxs-lookup"><span data-stu-id="c6da4-247">However, session option values cannot exceed maximum values set in the session configuration.</span></span>

<span data-ttu-id="c6da4-248">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="c6da4-248">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="c6da4-249">-Showsecuritydescriptor UI</span><span class="sxs-lookup"><span data-stu-id="c6da4-249">-ShowSecurityDescriptorUI</span></span>

<span data-ttu-id="c6da4-250">Gibt an, dass dieses Cmdlet ein Eigenschaften Blatt anzeigt, das Ihnen hilft, die SDDL für die Sitzungs Konfiguration zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c6da4-250">Indicates that this cmdlet displays a property sheet that helps you create the SDDL for the session configuration.</span></span> <span data-ttu-id="c6da4-251">Das Eigenschaften Blatt wird angezeigt, nachdem Sie den `Register-PSSessionConfiguration` Befehl eingegeben und dann den **WinRM** -Dienst neu gestartet haben.</span><span class="sxs-lookup"><span data-stu-id="c6da4-251">The property sheet appears after you enter the `Register-PSSessionConfiguration` command and then restart the **WinRM** service.</span></span>

<span data-ttu-id="c6da4-252">Denken Sie beim Festlegen der Berechtigungen für die Konfiguration daran, dass Benutzer mindestens über die Berechtigung Execute (aufrufen) verfügen müssen, um die Sitzungs Konfiguration in einer Sitzung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="c6da4-252">When setting the permissions for the configuration, remember that users must have at least Execute (Invoke) permission to use the session configuration in a session.</span></span>

<span data-ttu-id="c6da4-253">Sie können den **SecurityDescriptorSDDL** -Parameter und diesen Parameter nicht im selben Befehl verwenden.</span><span class="sxs-lookup"><span data-stu-id="c6da4-253">You cannot use the **SecurityDescriptorSDDL** parameter and this parameter in the same command.</span></span>

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

### <span data-ttu-id="c6da4-254">-Startupscript</span><span class="sxs-lookup"><span data-stu-id="c6da4-254">-StartupScript</span></span>

<span data-ttu-id="c6da4-255">Gibt den voll qualifizierten Pfad eines PowerShell-Skripts an.</span><span class="sxs-lookup"><span data-stu-id="c6da4-255">Specifies the fully qualified path of a PowerShell script.</span></span> <span data-ttu-id="c6da4-256">Das angegebene Skript wird in der neuen Sitzung ausgeführt, die die Sitzungskonfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="c6da4-256">The specified script runs in the new session that uses the session configuration.</span></span>

<span data-ttu-id="c6da4-257">Sie können das Skript verwenden, um die Sitzung zusätzlich zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c6da4-257">You can use the script to additionally configure the session.</span></span> <span data-ttu-id="c6da4-258">Wenn das Skript einen Fehler (auch einen Fehler ohne Abbruch) generiert, wird die Sitzung nicht erstellt, und der `New-PSSession` Befehl schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="c6da4-258">If the script generates an error, even a non-terminating error, the session is not created and the `New-PSSession` command fails.</span></span>

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

### <span data-ttu-id="c6da4-259">-Threadoptions</span><span class="sxs-lookup"><span data-stu-id="c6da4-259">-ThreadOptions</span></span>

<span data-ttu-id="c6da4-260">Gibt an, wie Threads erstellt und verwendet werden, wenn ein Befehl in der Sitzung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c6da4-260">Specifies how threads are created and used when a command runs in the session.</span></span> <span data-ttu-id="c6da4-261">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="c6da4-261">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="c6da4-262">Standard</span><span class="sxs-lookup"><span data-stu-id="c6da4-262">Default</span></span>
- <span data-ttu-id="c6da4-263">Reusethread</span><span class="sxs-lookup"><span data-stu-id="c6da4-263">ReuseThread</span></span>
- <span data-ttu-id="c6da4-264">UseCurrentThread</span><span class="sxs-lookup"><span data-stu-id="c6da4-264">UseCurrentThread</span></span>
- <span data-ttu-id="c6da4-265">Usenewthread</span><span class="sxs-lookup"><span data-stu-id="c6da4-265">UseNewThread</span></span>

<span data-ttu-id="c6da4-266">Der Standardwert ist **usecurrentthread** .</span><span class="sxs-lookup"><span data-stu-id="c6da4-266">The default value is **UseCurrentThread** .</span></span>

<span data-ttu-id="c6da4-267">Weitere Informationen finden Sie unter [psthlesoptions-Enumeration](/dotnet/api/system.management.automation.runspaces.psthreadoptions?view=powershellsdk-1.1.0).</span><span class="sxs-lookup"><span data-stu-id="c6da4-267">For more information, see [PSThreadOptions Enumeration](/dotnet/api/system.management.automation.runspaces.psthreadoptions?view=powershellsdk-1.1.0).</span></span>

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

### <span data-ttu-id="c6da4-268">-Transportoption</span><span class="sxs-lookup"><span data-stu-id="c6da4-268">-TransportOption</span></span>

<span data-ttu-id="c6da4-269">Gibt die Transport Option an.</span><span class="sxs-lookup"><span data-stu-id="c6da4-269">Specifies the transport option.</span></span>

<span data-ttu-id="c6da4-270">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="c6da4-270">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="c6da4-271">--Vorgang</span><span class="sxs-lookup"><span data-stu-id="c6da4-271">-UseSharedProcess</span></span>

<span data-ttu-id="c6da4-272">Verwenden Sie nur einen Prozess, um alle Sitzungen zu hosten, die vom gleichen Benutzer gestartet wurden und die gleiche Sitzungs Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="c6da4-272">Use only one process to host all sessions that are started by the same user and use the same session configuration.</span></span> <span data-ttu-id="c6da4-273">Standardmäßig wird jede Sitzung in einem eigenen Prozess gehostet.</span><span class="sxs-lookup"><span data-stu-id="c6da4-273">By default, each session is hosted in its own process.</span></span>

<span data-ttu-id="c6da4-274">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="c6da4-274">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="c6da4-275">-Confirm</span><span class="sxs-lookup"><span data-stu-id="c6da4-275">-Confirm</span></span>

<span data-ttu-id="c6da4-276">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="c6da4-276">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="c6da4-277">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="c6da4-277">-WhatIf</span></span>

<span data-ttu-id="c6da4-278">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c6da4-278">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="c6da4-279">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c6da4-279">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="c6da4-280">-Threadapartmentstate</span><span class="sxs-lookup"><span data-stu-id="c6da4-280">-ThreadApartmentState</span></span>

<span data-ttu-id="c6da4-281">Gibt den Apartment Zustand des Threading Moduls an, das verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c6da4-281">Specifies the apartment state of the threading module to be used.</span></span> <span data-ttu-id="c6da4-282">Zulässige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="c6da4-282">Acceptable values are:</span></span>

- <span data-ttu-id="c6da4-283">Unknown</span><span class="sxs-lookup"><span data-stu-id="c6da4-283">Unknown</span></span>
- <span data-ttu-id="c6da4-284">MTA</span><span class="sxs-lookup"><span data-stu-id="c6da4-284">MTA</span></span>
- <span data-ttu-id="c6da4-285">STA</span><span class="sxs-lookup"><span data-stu-id="c6da4-285">STA</span></span>

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

### <span data-ttu-id="c6da4-286">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c6da4-286">CommonParameters</span></span>

<span data-ttu-id="c6da4-287">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c6da4-287">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c6da4-288">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c6da4-288">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c6da4-289">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="c6da4-289">INPUTS</span></span>

### <span data-ttu-id="c6da4-290">Keine</span><span class="sxs-lookup"><span data-stu-id="c6da4-290">None</span></span>

<span data-ttu-id="c6da4-291">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="c6da4-291">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="c6da4-292">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="c6da4-292">OUTPUTS</span></span>

### <span data-ttu-id="c6da4-293">Microsoft. WSMAN. Management. wsmanconfigcontainerelement</span><span class="sxs-lookup"><span data-stu-id="c6da4-293">Microsoft.WSMan.Management.WSManConfigContainerElement</span></span>

## <span data-ttu-id="c6da4-294">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="c6da4-294">NOTES</span></span>

<span data-ttu-id="c6da4-295">Zum Ausführen dieses Cmdlets müssen Sie PowerShell mit der Option **als Administrator ausführen** starten.</span><span class="sxs-lookup"><span data-stu-id="c6da4-295">To run this cmdlet you must start PowerShell by using the **Run as administrator** option.</span></span>

<span data-ttu-id="c6da4-296">Dieses Cmdlet generiert XML, das eine Plug-in-Konfiguration für Web Services for Management (WS-Management) darstellt, und sendet die XML-Datei an WS-Management, die das Plug-in auf dem lokalen Computer registriert ( `New-Item wsman:\localhost\plugin` ).</span><span class="sxs-lookup"><span data-stu-id="c6da4-296">This cmdlet generates XML that represents a Web Services for Management (WS-Management) plug-in configuration and sends the XML to WS-Management, which registers the plug-in on the local computer (`New-Item wsman:\localhost\plugin`).</span></span>

<span data-ttu-id="c6da4-297">Die Eigenschaften eines Sitzungskonfigurationsobjekts weichen hinsichtlich der für die Sitzungskonfiguration festgelegten Optionen sowie der Werte dieser Optionen ab.</span><span class="sxs-lookup"><span data-stu-id="c6da4-297">The properties of a session configuration object vary with the options set for the session configuration and the values of those options.</span></span> <span data-ttu-id="c6da4-298">Sitzungskonfigurationen, die eine Sitzungskonfigurationsdatei verwenden, haben außerdem zusätzliche Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="c6da4-298">Also, session configurations that use a session configuration file have additional properties.</span></span>

## <span data-ttu-id="c6da4-299">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="c6da4-299">RELATED LINKS</span></span>

[<span data-ttu-id="c6da4-300">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="c6da4-300">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="c6da4-301">Enable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="c6da4-301">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="c6da4-302">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="c6da4-302">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="c6da4-303">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="c6da4-303">New-PSSessionConfigurationFile</span></span>](New-PSSessionConfigurationFile.md)

[<span data-ttu-id="c6da4-304">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="c6da4-304">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="c6da4-305">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="c6da4-305">Test-PSSessionConfigurationFile</span></span>](Test-PSSessionConfigurationFile.md)

[<span data-ttu-id="c6da4-306">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="c6da4-306">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="c6da4-307">WSMan-Anbieter</span><span class="sxs-lookup"><span data-stu-id="c6da4-307">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="c6da4-308">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="c6da4-308">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)

[<span data-ttu-id="c6da4-309">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="c6da4-309">about_Session_Configuration_Files</span></span>](About/about_Session_Configuration_Files.md)
