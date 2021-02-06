---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-pssessionconfiguration?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSSessionConfiguration
ms.openlocfilehash: a5aa70521841b3b05d34623ff92ebbf9e3471fd1
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603723"
---
# <span data-ttu-id="14595-102">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="14595-102">Get-PSSessionConfiguration</span></span>

## <span data-ttu-id="14595-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="14595-103">SYNOPSIS</span></span>
<span data-ttu-id="14595-104">Ruft die registrierten Sitzungskonfigurationen auf dem Computer ab.</span><span class="sxs-lookup"><span data-stu-id="14595-104">Gets the registered session configurations on the computer.</span></span>

## <span data-ttu-id="14595-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="14595-105">SYNTAX</span></span>

```
Get-PSSessionConfiguration [[-Name] <String[]>] [-Force] [<CommonParameters>]
```

## <span data-ttu-id="14595-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="14595-106">DESCRIPTION</span></span>

<span data-ttu-id="14595-107">Mit dem- `Get-PSSessionConfiguration` Cmdlet werden die Sitzungs Konfigurationen abgerufen, die auf dem lokalen Computer registriert wurden.</span><span class="sxs-lookup"><span data-stu-id="14595-107">The `Get-PSSessionConfiguration` cmdlet gets the session configurations that have been registered on the local computer.</span></span> <span data-ttu-id="14595-108">Dies ist ein erweitertes Cmdlet für Systemadministratoren, die benutzerdefinierte Sitzungskonfigurationen für ihre Benutzer verwalten.</span><span class="sxs-lookup"><span data-stu-id="14595-108">This is an advanced cmdlet that is designed to be used by system administrators to manage customized session configurations for their users.</span></span>

<span data-ttu-id="14595-109">Ab PowerShell 3,0 können Sie die Eigenschaften einer Sitzungs Konfiguration mit einer Sitzungs Konfigurationsdatei (. PSSC) definieren.</span><span class="sxs-lookup"><span data-stu-id="14595-109">Beginning in PowerShell 3.0, you can define the properties of a session configuration by using a session configuration (.pssc) file.</span></span> <span data-ttu-id="14595-110">Mit dieser Funktion können Sie angepasste und eingeschränkte Sitzungen erstellen, ohne ein Programm zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="14595-110">This feature lets you create customized and restricted sessions without writing a computer program.</span></span> <span data-ttu-id="14595-111">Weitere Informationen zu Sitzungskonfigurationsdateien finden Sie unter [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span><span class="sxs-lookup"><span data-stu-id="14595-111">For more information about session configuration files, see [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span></span>

<span data-ttu-id="14595-112">Außerdem wurden ab PowerShell 3,0 neue Hinweis Eigenschaften zum Sitzungs Konfigurationsobjekt hinzugefügt, das `Get-PSSessionConfiguration` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="14595-112">Also, beginning in PowerShell 3.0, new note properties have been added to the session configuration object that `Get-PSSessionConfiguration` returns.</span></span> <span data-ttu-id="14595-113">Diese Eigenschaften erleichtern Benutzern und Erstellern von Sitzungskonfigurationen die Überprüfung und den Vergleich von Sitzungskonfigurationen.</span><span class="sxs-lookup"><span data-stu-id="14595-113">These properties make it easier for users and session configuration authors to examine and compare session configurations.</span></span>

<span data-ttu-id="14595-114">Verwenden Sie das-Cmdlet, um eine Sitzungs Konfiguration zu erstellen und zu registrieren `Register-PSSessionConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="14595-114">To create and register a session configuration, use the `Register-PSSessionConfiguration` cmdlet.</span></span>
<span data-ttu-id="14595-115">Weitere Informationen zu Sitzungs Konfigurationen finden Sie unter [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="14595-115">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

## <span data-ttu-id="14595-116">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="14595-116">EXAMPLES</span></span>

### <span data-ttu-id="14595-117">Beispiel 1: erhalten von Sitzungs Konfigurationen auf dem lokalen Computer</span><span class="sxs-lookup"><span data-stu-id="14595-117">Example 1 - Get session configurations on the local computer</span></span>

```powershell
Get-PSSessionConfiguration
```

### <span data-ttu-id="14595-118">Beispiel 2: Holen Sie sich die beiden Standard Sitzungs Konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="14595-118">Example 2 - Get the two default session configurations</span></span>

<span data-ttu-id="14595-119">Der Befehl verwendet den **Name** -Parameter von `Get-PSSessionConfiguration` , um nur die Sitzungs Konfigurationen zu erhalten, deren Namen mit "Microsoft" beginnen.</span><span class="sxs-lookup"><span data-stu-id="14595-119">The command uses the **Name** parameter of `Get-PSSessionConfiguration` to get only the session configurations with names that begin with "Microsoft".</span></span>

```powershell
Get-PSSessionConfiguration -Name Microsoft*
```

```Output
Name                      PSVersion  StartupScript        Permission
----                      ---------  -------------        ----------
microsoft.powershell      5.1                             BUILTIN\Administrators AccessAll...
microsoft.powershell32    5.1                             BUILTIN\Administrators AccessAll...
```

### <span data-ttu-id="14595-120">Beispiel 3: erhalten der Eigenschaften und Werte einer Sitzungs Konfiguration</span><span class="sxs-lookup"><span data-stu-id="14595-120">Example 3 - Get the properties and values of a session configuration</span></span>

<span data-ttu-id="14595-121">Dieses Beispiel zeigt die Eigenschaften und Eigenschaftswerte einer Sitzungskonfiguration, die mithilfe einer Sitzungskonfigurationsdatei erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="14595-121">This example shows the properties and property values of a session configuration that was created by using a session configuration file.</span></span>

```powershell
Get-PSSessionConfiguration -Name Full  | Format-List -Property *
```

```Output
Copyright                     : (c) 2011 User01. All rights reserved.
AliasDefinitions              : {System.Collections.Hashtable}
SessionType                   : Default
CompanyName                   : Unknown
GUID                          : 1e9cb265-dae0-4bd3-89a9-8338a47698a1
Author                        : User01
ExecutionPolicy               : Restricted
SchemaVersion                 : 1.0.0.0
LanguageMode                  : FullLanguage
Architecture                  : 64
Filename                      : %windir%\system32\pwrshplugin.dll
ResourceUri                   : http://schemas.microsoft.com/powershell/Full
MaxConcurrentCommandsPerShell : 1500
UseSharedProcess              : false
ProcessIdleTimeoutSec         : 0
xmlns                         : http://schemas.microsoft.com/wbem/wsman/1/config/PluginConfiguration
MaxConcurrentUsers            : 10
lang                          : en-US
SupportsOptions               : true
ExactMatch                    : true
configfilepath                : C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\Full_1e9cb265-dae0-4bd3-89a9-8338a47698a1.pssc
RunAsUser                     :
IdleTimeoutms                 : 7200000
PSVersion                     : 3.0
OutputBufferingMode           : Block
AutoRestart                   : false
MaxShells                     : 300
MaxMemoryPerShellMB           : 1024
MaxIdleTimeoutms              : 43200000
SDKVersion                    : 1
Name                          : Full
XmlRenderingType              : text
Capability                    : {Shell}
RunAsPassword                 :
MaxProcessesPerShell          : 25
Enabled                       : True
MaxShellsPerUser              : 30
Permission                    :
```

<span data-ttu-id="14595-122">Im Beispiel wird das- `Get-PSSessionConfiguration` Cmdlet verwendet, um die vollständige Sitzungs Konfiguration zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="14595-122">The example uses the `Get-PSSessionConfiguration` cmdlet to get the full session configuration.</span></span> <span data-ttu-id="14595-123">Ein Pipeline Operator sendet die vollständige Sitzungs Konfiguration an das `Format-List` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="14595-123">A pipeline operator sends the Full session configuration to the `Format-List` cmdlet.</span></span> <span data-ttu-id="14595-124">Der **Property** -Parameter mit dem Wert `*` (All) leitet `Format-List` , um alle Eigenschaften und Werte des Objekts in einer Liste anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="14595-124">The **Property** parameter with a value of `*` (all) directs `Format-List` to display all the properties and values of the object in a list.</span></span>

<span data-ttu-id="14595-125">Die Ausgabe enthält nützliche Informationen, darunter den Autor der Sitzungs Konfiguration, den Sitzungstyp, den Sprachmodus und die Ausführungs Richtlinie von Sitzungen, die mit dieser Sitzungs Konfiguration, Sitzungs Kontingente und dem vollständigen Pfad zur Sitzungs Konfigurationsdatei erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="14595-125">The output includes useful information, including the author of the session configuration, the session type, language mode, and execution policy of sessions that are created with this session configuration, session quotas, and the full path to the session configuration file.</span></span>

<span data-ttu-id="14595-126">Diese Ansicht einer Sitzungskonfiguration wird für Sitzungen verwendet, die eine Sitzungskonfigurationsdatei enthalten.</span><span class="sxs-lookup"><span data-stu-id="14595-126">This view of a session configuration is used for sessions that include a session configuration file.</span></span>
<span data-ttu-id="14595-127">Weitere Informationen zu Sitzungskonfigurationsdateien finden Sie unter [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span><span class="sxs-lookup"><span data-stu-id="14595-127">For more information about session configuration files, see [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span></span>

### <span data-ttu-id="14595-128">Beispiel 4: eine weitere Möglichkeit zum Überprüfen der Sitzungs Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="14595-128">Example 4 - Another way to look at the session configurations</span></span>

<span data-ttu-id="14595-129">In diesem Beispiel wird das- `Get-ChildItem` Cmdlet (Alias `dir` ) im WSMAN: Provider-Laufwerk verwendet, um den Inhalt des Plug-in-Knotens anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="14595-129">This example uses the `Get-ChildItem` cmdlet (alias `dir`) in the WSMan: provider drive to look at the content of the Plugin node.</span></span> <span data-ttu-id="14595-130">Dies ist eine weitere Möglichkeit, um die Sitzungskonfigurationen auf dem Computer anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="14595-130">This is another way to look at the session configurations on the computer.</span></span>

```powershell
dir wsman:\localhost\plugin
```

```Output
Type            Keys                                Name
----            ----                                ----
Container       {Name=Event Forwarding Plugin}      Event Forwarding Plugin
Container       {Name=Full}                         Full
Container       {Name=microsoft.powershell}         microsoft.powershell
Container       {Name=microsoft.powershell.workf... microsoft.powershell.workflow
Container       {Name=microsoft.powershell32}       microsoft.powershell32
Container       {Name=microsoft.ServerManager}      microsoft.ServerManager
Container       {Name=WMI Provider}                 WMI Provider
```

<span data-ttu-id="14595-131">Der **Plug** -in-Knoten enthält **Containerelement** -Objekte (Microsoft. WSMAN. Management. wsmanconfigcontainerelement), die die registrierten PowerShell-Sitzungs Konfigurationen zusammen mit anderen Plug-Ins für die WS-Verwaltung darstellen.</span><span class="sxs-lookup"><span data-stu-id="14595-131">The **PlugIn** node contains **ContainerElement** objects (Microsoft.WSMan.Management.WSManConfigContainerElement) that represent the registered PowerShell session configurations, along with other plug-ins for WS-Management.</span></span>

### <span data-ttu-id="14595-132">Beispiel 6: Anzeigen von Sitzungs Konfigurationen auf einem Remote Computer</span><span class="sxs-lookup"><span data-stu-id="14595-132">Example 6 - View session configurations on a remote computer</span></span>

<span data-ttu-id="14595-133">Dieses Beispiel zeigt, wie Sie den WSMan-Anbieter verwenden können, um die Sitzungskonfigurationen auf einem Remotecomputer anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="14595-133">This example shows how to use the WSMan provider to view the session configurations on a remote computer.</span></span> <span data-ttu-id="14595-134">Diese Methode bietet nicht so viele Informationen wie ein `Get-PSSessionConfiguration` Befehl, aber der Benutzer muss nicht Mitglied der Gruppe "Administratoren" sein, um dieses Cmdlet ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="14595-134">This method does not provide as much information as a `Get-PSSessionConfiguration` command, but the user does not need to be a member of the Administrators group to run this cmdlet.</span></span>

```powershell
Connect-WSMan -ComputerName Server01
dir WSMan:\Server01\Plugin
```

```Output
   WSManConfig: Microsoft.WSMan.Management\WSMan::localhost\Plugin

Type            Keys                                Name
----            ----                                ----
Container       {Name=Empty}                        Empty
Container       {Name=Event Forwarding Plugin}      Event Forwarding Plugin
Container       {Name=Full}                         Full
Container       {Name=microsoft.powershell}         microsoft.powershell
Container       {Name=microsoft.powershell.workf... microsoft.powershell.workflow
Container       {Name=microsoft.powershell32}       microsoft.powershell32
Container       {Name=microsoft.ServerManager}      microsoft.ServerManager
Container       {Name=NoLanguage}                   NoLanguage
Container       {Name=RestrictedLang}               RestrictedLang
Container       {Name=RRS}                          RRS
Container       {Name=SEL Plugin}                   SEL Plugin
Container       {Name=WithProfile}                  WithProfile
Container       {Name=WMI Provider}                 WMI Provider
```

<span data-ttu-id="14595-135">Das- `Connect-WSMan` Cmdlet stellt eine Verbindung mit dem WinRM-Dienst auf dem Remote Computer Server01 her.</span><span class="sxs-lookup"><span data-stu-id="14595-135">The `Connect-WSMan` cmdlet connects to the WinRM service on the Server01 remote computer.</span></span> <span data-ttu-id="14595-136">Mit dem- `Get-ChildItem` Cmdlet (Alias `dir` ) des WSMAN:-Laufwerks werden die Elemente im **Server01\Plugin** -Pfad abgerufen.</span><span class="sxs-lookup"><span data-stu-id="14595-136">The `Get-ChildItem` cmdlet (alias `dir`) of the WSMan: drive gets the items in the **Server01\Plugin** path.</span></span> <span data-ttu-id="14595-137">Die Ausgabe zeigt die Elemente im Plugin-Verzeichnis auf dem Computer „Server01“.</span><span class="sxs-lookup"><span data-stu-id="14595-137">The output shows the items in the Plugin directory on the Server01 computer.</span></span> <span data-ttu-id="14595-138">Die Elemente enthalten die Sitzungskonfigurationen, die eine Art von WSMan-Plug-In sind, sowie andere Arten von Plug-Ins auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="14595-138">The items include the session configurations, which are a type of WSMan plug-in, along with other types of plug-ins on the computer.</span></span>

### <span data-ttu-id="14595-139">Beispiel 7: erhalten von detaillierten Sitzungs Konfigurationen von einem Remote Computer</span><span class="sxs-lookup"><span data-stu-id="14595-139">Example 7 - Get detailed session configurations from a remote computer</span></span>

<span data-ttu-id="14595-140">In diesem Beispiel wird gezeigt, wie ein `Get-PSSessionConfiguration` Befehl auf einem Remote Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="14595-140">This example shows how to run a `Get-PSSessionConfiguration` command on a remote computer.</span></span> <span data-ttu-id="14595-141">Der Befehl erfordert, dass die CredSSP-Delegierung in den Clienteinstellungen auf dem lokalen Computer und in den Diensteinstellungen auf dem Remotecomputer aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="14595-141">The command requires that CredSSP delegation be enabled in the client settings on the local computer and in the service settings on the remote computer.</span></span>

<span data-ttu-id="14595-142">Um die Befehle in diesem Beispiel auszuführen, müssen Sie Mitglied der Gruppe "Administratoren" auf dem lokalen Computer und dem Remote Computer sein, und Sie müssen PowerShell mit der Option " **als Administrator ausführen** " starten.</span><span class="sxs-lookup"><span data-stu-id="14595-142">To run the commands in this example, you must be a member of the Administrators group on the local and remote computers and you must start PowerShell with the **Run as administrator** option.</span></span>

```powershell
Enable-WSManCredSSP -Delegate Server02
Connect-WSMan Server02
Set-Item WSMan:\Server02*\Service\Auth\CredSSP -Value $true
Invoke-Command -ScriptBlock {Get-PSSessionConfiguration} -ComputerName Server02 -Authentication CredSSP -Credential Domain01\Admin01
```

```Output
Name                      PSVersion  StartupScript        Permission                          PSComputerName
----                      ---------  -------------        ----------                          --------------
microsoft.powershell      5.1                             BUILTIN\Administrators AccessAll... server02.corp.fabrikam.com
microsoft.powershell32    5.1                             BUILTIN\Administrators AccessAll... server02.corp.fabrikam.com
MyX86Shell                5.1        c:\test\x86Shell.ps1 BUILTIN\Administrators AccessAll... server02.corp.fabrikam.com
```

<span data-ttu-id="14595-143">Mit dem- `Enable-WSManCredSSP` Cmdlet wird die Server01-Delegierung auf dem lokalen Computer aktiviert. </span><span class="sxs-lookup"><span data-stu-id="14595-143">The `Enable-WSManCredSSP` cmdlet enables **CredSSP** delegation on Server01, the local computer.</span></span> <span data-ttu-id="14595-144">Das- `Connect-WSMan` Cmdlet stellt eine Verbindung mit Server02 Computer her.</span><span class="sxs-lookup"><span data-stu-id="14595-144">The `Connect-WSMan` cmdlet connects to Server02 computer.</span></span> <span data-ttu-id="14595-145">Durch diese Aktion wird dem WSMAN:-Laufwerk auf dem lokalen Computer ein Knoten für Server02 hinzugefügt, sodass Sie die WS-Management Einstellungen auf dem Server02-Computer anzeigen und ändern können.</span><span class="sxs-lookup"><span data-stu-id="14595-145">This action adds a node for Server02 to the WSMan: drive on the local computer, allowing you to view and change the WS-Management settings on the Server02 computer.</span></span> <span data-ttu-id="14595-146">Das- `Set-Item` Cmdlet ändert den Wert des Elements " **kredssp** " im Knoten "Dienst" des Server02-Computers in " **true**".</span><span class="sxs-lookup"><span data-stu-id="14595-146">The `Set-Item` cmdlet changes the value of the **CredSSP** item in the Service node of the Server02 computer to **True**.</span></span> <span data-ttu-id="14595-147">Dadurch werden die Diensteinstellungen auf dem Remotecomputer konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="14595-147">This configures the service settings on the remote computer.</span></span> <span data-ttu-id="14595-148">Das- `Invoke-Command` Cmdlet führt den `Get-PSSessionConfiguration` Befehl auf dem Server02-Computer aus.</span><span class="sxs-lookup"><span data-stu-id="14595-148">The `Invoke-Command` cmdlet runs the`Get-PSSessionConfiguration` command on the Server02 computer.</span></span> <span data-ttu-id="14595-149">Der Befehl verwendet den **Credential**-Parameter und den **Authentication**-Parameter mit dem Wert **CredSSP**.</span><span class="sxs-lookup"><span data-stu-id="14595-149">The command uses the **Credential** parameter, and it uses the **Authentication** parameter with a value of **CredSSP**.</span></span> <span data-ttu-id="14595-150">Die Ausgabe zeigt die Sitzungskonfigurationen auf dem Remotecomputer „Server02“.</span><span class="sxs-lookup"><span data-stu-id="14595-150">The output shows the session configurations on the Server02 remote computer.</span></span>

### <span data-ttu-id="14595-151">Beispiel 8: Ressourcen-URI einer Sitzungs Konfiguration</span><span class="sxs-lookup"><span data-stu-id="14595-151">Example 8 - Get the resource URI of a session configuration</span></span>

<span data-ttu-id="14595-152">Dieses Beispiel ist hilfreich beim Festlegen des Werts der `$PSSessionConfigurationName` Preference-Variablen, die einen Ressourcen-URI annimmt.</span><span class="sxs-lookup"><span data-stu-id="14595-152">This example is useful for setting the value of the `$PSSessionConfigurationName` preference variable, which takes a resource URI.</span></span>

```powershell
(Get-PSSessionConfiguration -Name CustomShell).resourceURI
```

```Output
http://schemas.microsoft.com/powershell/microsoft.CustomShell
```

<span data-ttu-id="14595-153">Die- `$PSSessionConfigurationName` Variable gibt die Standardkonfiguration an, die beim Erstellen einer Sitzung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="14595-153">The `$PSSessionConfigurationName` variable specifies the default configuration that is used when you create a session.</span></span> <span data-ttu-id="14595-154">Diese Variable wird auf dem lokalen Computer festgelegt, aber sie gibt eine Konfiguration auf dem Remotecomputer an.</span><span class="sxs-lookup"><span data-stu-id="14595-154">This variable is set on the local computer, but it specifies a configuration on the remote computer.</span></span> <span data-ttu-id="14595-155">Weitere Informationen zur- `$PSSessionConfiguration` Variablen finden Sie unter [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="14595-155">For more information about the `$PSSessionConfiguration` variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

## <span data-ttu-id="14595-156">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="14595-156">PARAMETERS</span></span>

### <span data-ttu-id="14595-157">-Force</span><span class="sxs-lookup"><span data-stu-id="14595-157">-Force</span></span>

<span data-ttu-id="14595-158">Unterdrückt die Eingabeaufforderung zum Neustart des WinRM-Diensts, wenn der Dienst noch nicht ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="14595-158">Suppresses the prompt to restart the WinRM service, if the service is not already running.</span></span>

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

### <span data-ttu-id="14595-159">-Name</span><span class="sxs-lookup"><span data-stu-id="14595-159">-Name</span></span>

<span data-ttu-id="14595-160">Ruft nur die Sitzungskonfigurationen mit dem angegebenen Namen oder Namensmuster ab.</span><span class="sxs-lookup"><span data-stu-id="14595-160">Gets only the session configurations with the specified name or name pattern.</span></span> <span data-ttu-id="14595-161">Geben Sie mindestens einen Konfigurationsnamen ein.</span><span class="sxs-lookup"><span data-stu-id="14595-161">Enter one or more session configuration names.</span></span> <span data-ttu-id="14595-162">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="14595-162">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: All session configurations on the local computer
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="14595-163">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="14595-163">CommonParameters</span></span>

<span data-ttu-id="14595-164">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="14595-164">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="14595-165">Weitere Informationen findest du unter [about_CommonParameters](./About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="14595-165">For more information, see [about_CommonParameters](./About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="14595-166">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="14595-166">INPUTS</span></span>

### <span data-ttu-id="14595-167">Keine</span><span class="sxs-lookup"><span data-stu-id="14595-167">None</span></span>

<span data-ttu-id="14595-168">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="14595-168">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="14595-169">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="14595-169">OUTPUTS</span></span>

### <span data-ttu-id="14595-170">Microsoft. PowerShell. Commands. pssessionconfigurationcommands # pssessionconfiguration</span><span class="sxs-lookup"><span data-stu-id="14595-170">Microsoft.PowerShell.Commands.PSSessionConfigurationCommands#PSSessionConfiguration</span></span>

## <span data-ttu-id="14595-171">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="14595-171">NOTES</span></span>

- <span data-ttu-id="14595-172">Starten Sie PowerShell mit der Option **als Administrator ausführen** , um dieses Cmdlet auszuführen.</span><span class="sxs-lookup"><span data-stu-id="14595-172">To run this cmdlet, start PowerShell with the **Run as administrator** option.</span></span>

- <span data-ttu-id="14595-173">Zur Anzeige der Sitzungskonfigurationen auf dem Computer müssen Sie Mitglied der Gruppe „Administratoren“ auf dem Computer sein.</span><span class="sxs-lookup"><span data-stu-id="14595-173">To view the session configurations on the computer, you must be a member of the Administrators group on the computer.</span></span>

- <span data-ttu-id="14595-174">Wenn Sie einen `Get-PSSessionConfiguration` Befehl auf einem Remote Computer ausführen möchten, müssen Sie in den Client Einstellungen auf dem lokalen Computer (mithilfe des `Enable-WSManCredSSP` Cmdlets) und in den Dienst Einstellungen auf dem Remote Computer aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="14595-174">To run a `Get-PSSessionConfiguration` command on a remote computer, Credential Security Service Provider (CredSSP) authentication must be enabled in the client settings on the local computer (by using the `Enable-WSManCredSSP` cmdlet) and in the service settings on the remote computer.</span></span> <span data-ttu-id="14595-175">Sie müssen auch den Wert " **kredssp** " des Parameters " **Authentication** " verwenden, wenn Sie die Remote Sitzung einrichten.</span><span class="sxs-lookup"><span data-stu-id="14595-175">Also, you must use the **CredSSP** value of the **Authentication** parameter when establishing the remote session.</span></span> <span data-ttu-id="14595-176">Andernfalls wird der Zugriff verweigert.</span><span class="sxs-lookup"><span data-stu-id="14595-176">Otherwise, access is denied.</span></span>

- <span data-ttu-id="14595-177">Die Hinweis Eigenschaften des-Objekts, das `Get-PSSessionConfiguration` zurückgibt, werden nur für das-Objekt angezeigt, wenn Sie über einen Wert verfügen.</span><span class="sxs-lookup"><span data-stu-id="14595-177">The note properties of the object that `Get-PSSessionConfiguration` returns appear on the object only when they have a value.</span></span> <span data-ttu-id="14595-178">Nur Sitzungs Konfigurationen, die mithilfe einer Sitzungs Konfigurationsdatei erstellt wurden, verfügen über alle definierten Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="14595-178">Only session configurations that were created by using a session configuration file have all the defined properties.</span></span>

- <span data-ttu-id="14595-179">Die Eigenschaften eines Sitzungskonfigurationsobjekts weichen hinsichtlich der für die Sitzungskonfiguration festgelegten Optionen sowie der Werte dieser Optionen ab.</span><span class="sxs-lookup"><span data-stu-id="14595-179">The properties of a session configuration object vary with the options set for the session configuration and the values of those options.</span></span> <span data-ttu-id="14595-180">Sitzungskonfigurationen, die eine Sitzungskonfigurationsdatei verwenden, haben außerdem zusätzliche Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="14595-180">Also, session configurations that use a session configuration file have additional properties.</span></span>

- <span data-ttu-id="14595-181">Sie können Befehle im WSMan:-Laufwerk verwenden, um die Eigenschaften von Sitzungskonfigurationen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="14595-181">You can use commands in the WSMan: drive to change the properties of session configurations.</span></span>
  <span data-ttu-id="14595-182">Allerdings können Sie das WSMAN:-Laufwerk in PowerShell 2,0 nicht verwenden, um Sitzungs Konfigurations Eigenschaften zu ändern, die in PowerShell 3,0 (z. b. **outputbufferingmode**) eingeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="14595-182">However, you cannot use the WSMan: drive in PowerShell 2.0 to change session configuration properties that are introduced in PowerShell 3.0, such as **OutputBufferingMode**.</span></span> <span data-ttu-id="14595-183">PowerShell 2,0-Befehle generieren keine Fehler, aber Sie sind wirkungslos.</span><span class="sxs-lookup"><span data-stu-id="14595-183">PowerShell 2.0 commands do not generate an error, but they are ineffective.</span></span> <span data-ttu-id="14595-184">Verwenden Sie das WSMAN:-Laufwerk in PowerShell 3,0, um die in PowerShell 3,0 eingeführten Eigenschaften zu ändern.</span><span class="sxs-lookup"><span data-stu-id="14595-184">To change properties introduced in PowerShell 3.0, use the WSMan: drive in PowerShell 3.0.</span></span>

## <span data-ttu-id="14595-185">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="14595-185">RELATED LINKS</span></span>

[<span data-ttu-id="14595-186">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="14595-186">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="14595-187">Enable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="14595-187">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="14595-188">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="14595-188">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="14595-189">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="14595-189">New-PSSessionConfigurationFile</span></span>](New-PSSessionConfigurationFile.md)

[<span data-ttu-id="14595-190">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="14595-190">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="14595-191">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="14595-191">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="14595-192">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="14595-192">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="14595-193">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="14595-193">Test-PSSessionConfigurationFile</span></span>](Test-PSSessionConfigurationFile.md)

[<span data-ttu-id="14595-194">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="14595-194">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="14595-195">WSMan-Anbieter</span><span class="sxs-lookup"><span data-stu-id="14595-195">WSMan Provider</span></span>](../microsoft.wsman.management/about/about_WSMan_Provider.md)

[<span data-ttu-id="14595-196">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="14595-196">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)

[<span data-ttu-id="14595-197">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="14595-197">about_Session_Configuration_Files</span></span>](About/about_Session_Configuration_Files.md)

