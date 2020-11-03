---
description: Beschreibt die Sitzungskonfigurationen, die bestimmen, welche Benutzer eine Remoteverbindung mit dem Computer herstellen können und welche Befehle ausgeführt werden können.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 12/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_session_configurations?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Session_Configurations
ms.openlocfilehash: 0956e2e96cb67d1c4b8c3ef245c6fa084b781351
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221167"
---
# <a name="about-session-configurations"></a><span data-ttu-id="73638-104">Informationen zu Sitzungs Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="73638-104">About Session Configurations</span></span>

## <a name="short-description"></a><span data-ttu-id="73638-105">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="73638-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="73638-106">Beschreibt die Sitzungskonfigurationen, die bestimmen, welche Benutzer eine Remoteverbindung mit dem Computer herstellen können und welche Befehle ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="73638-106">Describes session configurations, which determine the users who can connect to the computer remotely and the commands they can run.</span></span>

## <a name="long-description"></a><span data-ttu-id="73638-107">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="73638-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="73638-108">Eine Sitzungs Konfiguration, auch als "Endpunkt" bezeichnet, ist eine Gruppe von Einstellungen auf dem lokalen Computer, die die Umgebung für die PowerShell-Sitzungen definieren, die erstellt werden, wenn Remote-oder lokale Benutzer eine Verbindung mit PowerShell auf dem lokalen Computer herstellen.</span><span class="sxs-lookup"><span data-stu-id="73638-108">A session configuration, also known as an "endpoint" is a group of settings on the local computer that define the environment for the PowerShell sessions that are created when remote or local users connect to PowerShell on the local computer.</span></span>

<span data-ttu-id="73638-109">Administratoren des Computers können Sitzungs Konfigurationen verwenden, um den Computer zu schützen und benutzerdefinierte Umgebungen für Benutzer zu definieren, die eine Verbindung mit dem Computer herstellen.</span><span class="sxs-lookup"><span data-stu-id="73638-109">Administrators of the computer can use session configurations to protect the computer and to define custom environments for users who connect to the computer.</span></span>

<span data-ttu-id="73638-110">Administratoren können auch Sitzungs Konfigurationen verwenden, um die Berechtigungen zu bestimmen, die erforderlich sind, um eine Remote Verbindung mit dem Computer herzustellen.</span><span class="sxs-lookup"><span data-stu-id="73638-110">Administrators can also use session configurations to determine the permissions that are required to connect to the computer remotely.</span></span> <span data-ttu-id="73638-111">Standardmäßig haben nur Mitglieder der Gruppe "Administratoren" die Berechtigung, die Sitzungs Konfiguration für eine Remote Verbindung zu verwenden. Sie können jedoch die Standardeinstellungen ändern, damit alle Benutzer oder ausgewählte Benutzer eine Remote Verbindung mit dem Computer herstellen können.</span><span class="sxs-lookup"><span data-stu-id="73638-111">By default, only members of the Administrators group have permission to use the session configuration to connect remotely, but you can change the default settings to allow all users, or selected users, to connect remotely to your computer.</span></span>

<span data-ttu-id="73638-112">Ab PowerShell 3,0 können Sie eine Sitzungs Konfigurationsdatei verwenden, um die Elemente einer Sitzungs Konfiguration zu definieren.</span><span class="sxs-lookup"><span data-stu-id="73638-112">Beginning in PowerShell 3.0, you can use a session configuration file to define the elements of a session configuration.</span></span> <span data-ttu-id="73638-113">Diese Funktion erleichtert das Anpassen von Sitzungen, ohne Code zu schreiben und die Eigenschaften einer Sitzungs Konfiguration zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="73638-113">This feature makes it easy to customize sessions without writing code and to discover the properties of a session configuration.</span></span> <span data-ttu-id="73638-114">Verwenden Sie das Cmdlet "New-PSSessionConfiguration", um eine Sitzungs Konfigurationsdatei zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="73638-114">To create a session configuration file, use the New-PSSessionConfiguration cmdlet.</span></span> <span data-ttu-id="73638-115">Weitere Informationen zu Sitzungskonfigurationsdateien finden Sie unter [about_Session_Configuration_Files](about_Session_Configuration_Files.md).</span><span class="sxs-lookup"><span data-stu-id="73638-115">For more information about session configuration files, see [about_Session_Configuration_Files](about_Session_Configuration_Files.md).</span></span>

<span data-ttu-id="73638-116">Sitzungs Konfigurationen sind eine Funktion von Web Services for Management (WS-Management)-basierten PowerShell-Remoting.</span><span class="sxs-lookup"><span data-stu-id="73638-116">Session configurations are a feature of Web Services for Management (WS-Management) based PowerShell remoting.</span></span> <span data-ttu-id="73638-117">Sie werden nur verwendet, wenn Sie die Cmdlets New-PSSession, Aufruf-Command oder Enter-PSSession zum Herstellen einer Verbindung mit einem Remote Computer verwenden.</span><span class="sxs-lookup"><span data-stu-id="73638-117">They are used only when you use the New-PSSession, Invoke-Command, or Enter-PSSession cmdlets to connect to a remote computer.</span></span>

<span data-ttu-id="73638-118">Hinweis: Starten Sie PowerShell mit der Option "als Administrator ausführen", um die Sitzungs Konfigurationen zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="73638-118">Note: To manage the session configurations, start PowerShell with the "Run as administrator" option.</span></span>

<span data-ttu-id="73638-119">Informationen zu Sitzungs Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="73638-119">About Session Configurations</span></span>

<span data-ttu-id="73638-120">Für jede PowerShell-Sitzung wird eine Sitzungs Konfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="73638-120">Every PowerShell session uses a session configuration.</span></span> <span data-ttu-id="73638-121">Dies schließt persistente Sitzungen ein, die Sie mithilfe der Cmdlets New-PSSession oder Enter-PSSession erstellen, und die temporären Sitzungen, die PowerShell erstellt, wenn Sie den Computername-Parameter eines Cmdlets verwenden, das WS-Management-basierte Remotingtechnologie verwendet, wie z. b. "Start-Command".</span><span class="sxs-lookup"><span data-stu-id="73638-121">This includes persistent sessions that you create by using the New-PSSession or Enter-PSSession cmdlets, and the temporary sessions that PowerShell creates when you use the ComputerName parameter of a cmdlet that uses WS-Management-based remoting technology, such as Invoke-Command.</span></span>

<span data-ttu-id="73638-122">Administratoren können Sitzungs Konfigurationen verwenden, um die Ressourcen des Computers zu schützen und benutzerdefinierte Umgebungen für Benutzer zu erstellen, die eine Verbindung mit dem Computer herstellen.</span><span class="sxs-lookup"><span data-stu-id="73638-122">Administrators can use session configurations to protect the resources of the computer and to create custom environments for users who connect to the computer.</span></span> <span data-ttu-id="73638-123">Beispielsweise können Sie eine Sitzungs Konfiguration verwenden, um die Größe der Objekte, die der Computer in der Sitzung empfängt, einzuschränken, den Sprachmodus der Sitzung zu definieren und die in der Sitzung verfügbaren Cmdlets, Anbieter und Funktionen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="73638-123">For example, you can use a session configuration to limit the size of objects that the computer receives in the session, to define the language mode of the session, and to specify the cmdlets, providers, and functions that are available in the session.</span></span>

<span data-ttu-id="73638-124">Durch Konfigurieren der Sicherheits Beschreibung einer Sitzungs Konfiguration legen Sie fest, wer die Sitzungs Konfiguration verwenden kann, um eine Verbindung mit dem Computer herzustellen.</span><span class="sxs-lookup"><span data-stu-id="73638-124">By configuring the security descriptor of a session configuration, you determine who can use the session configuration to connect to the computer.</span></span>
<span data-ttu-id="73638-125">Benutzer müssen über die Berechtigung Ausführen für eine Sitzungs Konfiguration verfügen, damit Sie in einer Sitzung verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="73638-125">Users must have Execute permission to a session configuration to use it in a session.</span></span> <span data-ttu-id="73638-126">Wenn ein Benutzer nicht über die erforderlichen Berechtigungen verfügt, um eine der Sitzungs Konfigurationen auf einem Computer zu verwenden, kann der Benutzer keine Remote Verbindung mit dem Computer herstellen.</span><span class="sxs-lookup"><span data-stu-id="73638-126">If a user does not have the required permissions to use any of the session configurations on a computer, the user cannot connect to the computer remotely.</span></span>

<span data-ttu-id="73638-127">Standardmäßig verfügen nur Administratoren des Computers über die Berechtigung zum Verwenden der Standard Sitzungs Konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="73638-127">By default, only Administrators of the computer have permission to use the default session configurations.</span></span> <span data-ttu-id="73638-128">Sie können jedoch die Sicherheits Deskriptoren ändern, um allen Benutzern, nicht oder nur ausgewählten Benutzern zu gestatten, die Sitzungs Konfigurationen auf dem Computer zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="73638-128">But, you can change the security descriptors to allow everyone, no one, or only selected users to use the session configurations on your computer.</span></span>

<span data-ttu-id="73638-129">Integrierte Sitzungs Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="73638-129">Built-in Session Configurations</span></span>

<span data-ttu-id="73638-130">PowerShell 3,0 umfasst integrierte Sitzungs Konfigurationen namens Microsoft. PowerShell und Microsoft. PowerShell. Workflow.</span><span class="sxs-lookup"><span data-stu-id="73638-130">PowerShell 3.0 includes built-in session configurations named Microsoft.PowerShell and Microsoft.PowerShell.Workflow.</span></span> <span data-ttu-id="73638-131">Auf Computern, auf denen 64-Bit-Versionen von Windows ausgeführt werden, bietet PowerShell auch Microsoft. PowerShell32, eine 32-Bit-Sitzungs Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="73638-131">On computers running 64-bit versions of Windows, PowerShell also provides Microsoft.PowerShell32, a 32-bit session configuration.</span></span>

<span data-ttu-id="73638-132">Die Microsoft. PowerShell-Sitzungs Konfiguration wird standardmäßig für Sitzungen verwendet, d. h., wenn ein Befehl zum Erstellen einer Sitzung nicht den ConfigurationName-Parameter des Cmdlets New-PSSession, Enter-PSSession oder Invoke-Command enthält.</span><span class="sxs-lookup"><span data-stu-id="73638-132">The Microsoft.PowerShell session configuration is used for sessions by default, that is, when a command to create a session does not include the ConfigurationName parameter of the New-PSSession, Enter-PSSession, or Invoke-Command cmdlet.</span></span>

<span data-ttu-id="73638-133">Die Sicherheits Deskriptoren für die Standard Sitzungs Konfigurationen ermöglichen es nur Mitgliedern der Gruppe "Administratoren" auf dem lokalen Computer, Sie zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="73638-133">The security descriptors for the default session configurations allow only members of the Administrators group on the local computer to use them.</span></span> <span data-ttu-id="73638-134">Daher können nur Mitglieder der Gruppe "Administratoren" eine Remote Verbindung mit dem Computer herstellen, es sei denn, Sie ändern die Standardeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="73638-134">As such, only members of the Administrators group can connect to the computer remotely unless you change the default settings.</span></span>

<span data-ttu-id="73638-135">Sie können die Standard Sitzungs Konfigurationen mithilfe der $PSSessionConfigurationName Preference-Variablen ändern.</span><span class="sxs-lookup"><span data-stu-id="73638-135">You can change the default session configurations by using the $PSSessionConfigurationName preference variable.</span></span> <span data-ttu-id="73638-136">Weitere Informationen finden Sie unter „about_Preference_Variables“.</span><span class="sxs-lookup"><span data-stu-id="73638-136">For more information, see about_Preference_Variables.</span></span>

<span data-ttu-id="73638-137">Anzeigen von Sitzungs Konfigurationen auf dem lokalen Computer</span><span class="sxs-lookup"><span data-stu-id="73638-137">Viewing Session Configurations on the Local Computer</span></span>

<span data-ttu-id="73638-138">Verwenden Sie das Cmdlet "Get-PSSessionConfiguration", um die Sitzungs Konfigurationen auf dem lokalen Computer zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="73638-138">To get the session configurations on your local computer, use the Get-PSSessionConfiguration cmdlet.</span></span>

<span data-ttu-id="73638-139">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="73638-139">For example, type:</span></span>

```powershell
PS C:> Get-PSSessionConfiguration | Format-List -Property Name, Permission

Name       : microsoft.powershell
Permission : BUILTIN\Administrators AccessAllowed

Name       : microsoft.powershell.workflow
Permission : BUILTIN\Administrators AccessAllowed

Name       : microsoft.powershell32
Permission : BUILTIN\Administrators AccessAllowed
```

<span data-ttu-id="73638-140">Das Sitzungs Konfigurationsobjekt wird in PowerShell 3,0 erweitert, um die Eigenschaften der Sitzungs Konfiguration anzuzeigen, die mithilfe einer Sitzungs Konfigurationsdatei konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="73638-140">The session configuration object is expanded in PowerShell 3.0 to display the properties of the session configuration that are configured by using a session configuration file.</span></span>

<span data-ttu-id="73638-141">Wenn Sie z. b. alle Eigenschaften eines Sitzungs Konfigurations Objekts anzeigen möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="73638-141">For example, to see all of the properties of a session configuration object, type:</span></span>

```powershell
PS C:> Get-PSSessionConfiguration | Format-List -Property *
```

<span data-ttu-id="73638-142">Sie können auch den WSMAN-Anbieter in PowerShell verwenden, um Sitzungs Konfigurationen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="73638-142">You can also use the WSMan provider in PowerShell to view session configurations.</span></span> <span data-ttu-id="73638-143">Der WSMAN-Anbieter erstellt ein WSMAN:-Laufwerk in der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="73638-143">The WSMan provider creates a WSMAN: drive in your session.</span></span>

<span data-ttu-id="73638-144">Im WSMAN:-Laufwerk befinden sich Sitzungs Konfigurationen im Plug-in-Knoten.</span><span class="sxs-lookup"><span data-stu-id="73638-144">In the WSMAN: drive, session configurations are in the Plugin node.</span></span> <span data-ttu-id="73638-145">(Alle Sitzungs Konfigurationen befinden sich im Plug-in-Knoten, es sind jedoch Elemente im Plug-in-Knoten vorhanden, die keine Sitzungs Konfigurationen sind.)</span><span class="sxs-lookup"><span data-stu-id="73638-145">(All session configurations are in the Plugin node, but there are items in the Plugin node that are not session configurations.)</span></span>

<span data-ttu-id="73638-146">Wenn Sie z. b. die Sitzungs Konfigurationen auf dem lokalen Computer anzeigen möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="73638-146">For example, to view the session configurations on the local computer, type:</span></span>

```powershell
PS C:> dir wsman:\localhost\plugin\microsoft*

WSManConfig: Microsoft.WSMan.Management\WSMan::localhost\Plugin

Type       Keys                              Name
----       ----                              ----
Container  {Name=microsoft.powershell}       microsoft.powershell
Container  {Name=microsoft.powershell.wor... microsoft.powershell.workflow
Container  {Name=microsoft.powershell32}     microsoft.powershell32
```

<span data-ttu-id="73638-147">Anzeigen von Sitzungs Konfigurationen auf einem Remote Computer</span><span class="sxs-lookup"><span data-stu-id="73638-147">Viewing Session Configurations on a Remote Computer</span></span>

<span data-ttu-id="73638-148">Um die Sitzungs Konfigurationen auf einem Remote Computer anzuzeigen, verwenden Sie das Cmdlet "Connect-WSMan", um dem WSMAN:-Laufwerk auf dem lokalen Computer einen Hinweis für den Remote Computer hinzuzufügen, und verwenden Sie dann das WSMAN:-Laufwerk, um die Sitzungs Konfigurationen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="73638-148">To view the session configurations on a remote computer, use the Connect-WSMan cmdlet to add a note for the remote computer to the WSMAN: drive on your local computer, and then use the WSMAN: drive to view the session configurations.</span></span>

<span data-ttu-id="73638-149">Beispielsweise wird mit dem folgenden Befehl dem WSMAN:-Laufwerk auf dem lokalen Computer ein Knoten für den Remote Computer Server01 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="73638-149">For example, the following command adds a node for the Server01 remote computer to the WSMAN: drive on the local computer.</span></span>

```powershell
PS C:> Connect-WSMan server01.corp.fabrikam.com
```

<span data-ttu-id="73638-150">Wenn der Befehl fertiggestellt ist, können Sie zum Knoten für den Server01-Computer navigieren, um die Sitzungs Konfigurationen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="73638-150">When the command is complete, you can navigate to the node for the Server01 computer to view the session configurations.</span></span>

<span data-ttu-id="73638-151">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="73638-151">For example:</span></span>

```powershell
PS C:> cd wsman:

PS WSMan:> dir

ComputerName                                  Type
------------                                  ----
localhost                                     Container
server01.corp.fabrikam.com                    Container

PS WSMan:> dir server01\plugin\

WSManConfig: Microsoft.WSMan.Management\WSMan::server01.corp.fabrikam.com\Pl
ugin

Type       Keys                              Name
----       ----                              ----
Container  {Name=microsoft.powershell}       microsoft.powershell
Container  {Name=microsoft.powershell.wor... microsoft.powershell.workflow
Container  {Name=microsoft.powershell32}     microsoft.powershell32
```

<span data-ttu-id="73638-152">Ändern der Sicherheits Beschreibung einer Sitzungs Konfiguration</span><span class="sxs-lookup"><span data-stu-id="73638-152">Changing the Security Descriptor of a Session Configuration</span></span>

<span data-ttu-id="73638-153">In Windows Server 2012 und neueren Versionen von Windows Server sind die integrierten Sitzungs Konfigurationen standardmäßig für Remote Benutzer aktiviert.</span><span class="sxs-lookup"><span data-stu-id="73638-153">In Windows Server 2012 and newer releases of Windows Server, the built-in session configurations are enabled for remote users by default.</span></span> <span data-ttu-id="73638-154">In anderen unterstützten Versionen von Windows müssen Sie die Sicherheits Deskriptoren der Sitzungs Konfigurationen ändern, um den Remote Zugriff zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="73638-154">In other supported versions of Windows, you must change the security descriptors of the session configurations to allow remote access.</span></span>

<span data-ttu-id="73638-155">Verwenden Sie das Cmdlet "Enable-PSRemoting", um den Remote Zugriff auf die Sitzungs Konfigurationen auf dem Computer zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="73638-155">To enable remote access to the session configurations on the computer, use the Enable-PSRemoting cmdlet.</span></span> <span data-ttu-id="73638-156">Dieses Cmdlet erstellt zwei Sitzungs Konfigurationen:</span><span class="sxs-lookup"><span data-stu-id="73638-156">This cmdlet creates two session configurations:</span></span>

- <span data-ttu-id="73638-157">mit dem definierten Namen "PowerShell".</span><span class="sxs-lookup"><span data-stu-id="73638-157">with the name defined as: "PowerShell."</span></span> <span data-ttu-id="73638-158">+ "aktuelle PowerShell-Version"</span><span class="sxs-lookup"><span data-stu-id="73638-158">+ "current PowerShell version"</span></span>
- <span data-ttu-id="73638-159">mit dem Namen "PowerShell. 6", nicht an eine bestimmte PowerShell-Version gebunden.</span><span class="sxs-lookup"><span data-stu-id="73638-159">with name "PowerShell.6", untied to any specific PowerShell version.</span></span>

<span data-ttu-id="73638-160">Außerdem verfügen standardmäßig nur Mitglieder der Gruppe "Administratoren" auf dem Computer über die Berechtigung "ausführen" für die Standard Sitzungs Konfigurationen, aber Sie können die Sicherheits Beschreibungen in den Standard Sitzungs Konfigurationen und in den von Ihnen erstellten Sitzungs Konfigurationen ändern.</span><span class="sxs-lookup"><span data-stu-id="73638-160">Also, by default, only members of the Administrators group on the computer have Execute permission to the default session configurations, but you can change the security descriptors on the default session configurations and on any session configurations that you create.</span></span>

<span data-ttu-id="73638-161">Um anderen Benutzern die Berechtigung zu erteilen, eine Remote Verbindung mit dem Computer herzustellen, verwenden Sie das Cmdlet "Set-PSSessionConfiguration", um den Sicherheits Beschreibungen der Sitzungs Konfigurationen Microsoft. PowerShell und Microsoft. PowerShell32 Berechtigungen für diese Benutzer hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="73638-161">To give other users permission to connect to the computer remotely, use the Set-PSSessionConfiguration cmdlet to add "Execute" permissions for those users to the security descriptors of the Microsoft.PowerShell and Microsoft.PowerShell32 session configurations.</span></span>

<span data-ttu-id="73638-162">Beispielsweise wird mit dem folgenden Befehl eine Eigenschaften Seite geöffnet, auf der Sie die Sicherheits Beschreibung für die Standard Sitzungs Konfiguration von Microsoft. PowerShell ändern können.</span><span class="sxs-lookup"><span data-stu-id="73638-162">For example, the following command opens a property page that lets you change the security descriptor for the Microsoft.PowerShell default session configuration.</span></span>

```powershell
Set-PSSessionConfiguration -name Microsoft.PowerShell `
  -ShowSecurityDescriptorUI
```

<span data-ttu-id="73638-163">Verwenden Sie das Cmdlet "Disable-PSSessionConfiguration", um allen Sitzungs Konfigurationen auf dem Computer alle Berechtigungen zu verweigern.</span><span class="sxs-lookup"><span data-stu-id="73638-163">To deny everyone permission to all the session configurations on the computer, use the Disable-PSSessionConfiguration cmdlet.</span></span> <span data-ttu-id="73638-164">Der folgende Befehl deaktiviert z. b. die Standard Sitzungs Konfigurationen auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="73638-164">For example, the following command disables the default session configurations on the computer.</span></span>

```powershell
PS C:> Disable-PSSessionConfiguration -Name Microsoft.PowerShell
```

<span data-ttu-id="73638-165">Verwenden Sie das Cmdlet "Disable-PSRemoting", um zu verhindern, dass Remote Benutzer eine Verbindung mit dem Computer herstellen, aber die Verbindung zwischen lokalen Benutzern herstellen können.</span><span class="sxs-lookup"><span data-stu-id="73638-165">To prevent remote users from connecting to the computer, but allow local users to connect, use the Disable-PSRemoting cmdlet.</span></span> <span data-ttu-id="73638-166">Disable-PSRemoting fügt allen Sitzungs Konfigurationen auf dem Computer einen "Network_Deny_All"-Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="73638-166">Disable-PSRemoting adds a "Network_Deny_All" entry to all session configurations on the computer.</span></span>

```powershell
PS C:> Disable-PSRemoting
```

<span data-ttu-id="73638-167">Verwenden Sie das Cmdlet Enable-PSRemoting oder Enable-PSSessionConfiguration, damit Remote Benutzer alle Sitzungs Konfigurationen auf dem Computer verwenden können.</span><span class="sxs-lookup"><span data-stu-id="73638-167">To allow remote users to use all session configurations on the computer, use the Enable-PSRemoting or Enable-PSSessionConfiguration cmdlet.</span></span> <span data-ttu-id="73638-168">Der folgende Befehl aktiviert z. b. den Remote Zugriff auf die integrierten Sitzungs Konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="73638-168">For example, the following command enables remote access to the built-in session configurations.</span></span>

```powershell
PS C:> Enable-PSSessionConfiguration -name Microsoft.Power*
```

<span data-ttu-id="73638-169">Wenn Sie andere Änderungen an der Sicherheits Beschreibung einer Sitzungs Konfiguration vornehmen möchten, verwenden Sie das Cmdlet "Set-PSSessionConfiguration".</span><span class="sxs-lookup"><span data-stu-id="73638-169">To make other changes to the security descriptor of a session configuration, use the Set-PSSessionConfiguration cmdlet.</span></span> <span data-ttu-id="73638-170">Verwenden Sie den securitydescriptorsddl-Parameter, um einen SDDL-Zeichen folgen Wert zu senden.</span><span class="sxs-lookup"><span data-stu-id="73638-170">Use the SecurityDescriptorSDDL parameter to submit an SDDL string value.</span></span> <span data-ttu-id="73638-171">Verwenden Sie den showsecuritydescriptorui-Parameter, um ein Eigenschaften Blatt für die Benutzeroberfläche anzuzeigen, das Ihnen beim Erstellen einer neuen SDDL hilft.</span><span class="sxs-lookup"><span data-stu-id="73638-171">Use the ShowSecurityDescriptorUI parameter to display a user interface property sheet that helps you to create a new SDDL.</span></span>

<span data-ttu-id="73638-172">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="73638-172">For example:</span></span>

```powershell
Set-PSSessionConfiguration -Name Microsoft.PowerShell `
  -ShowSecurityDescriptorUI
```

<span data-ttu-id="73638-173">Erstellen einer neuen Sitzungs Konfiguration</span><span class="sxs-lookup"><span data-stu-id="73638-173">Creating a New Session Configuration</span></span>

<span data-ttu-id="73638-174">Verwenden Sie das Cmdlet "Register-PSSessionConfiguration", um eine neue Sitzungs Konfiguration auf dem lokalen Computer zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="73638-174">To create a new session configuration on the local computer, use the Register-PSSessionConfiguration cmdlet.</span></span> <span data-ttu-id="73638-175">Zum Definieren der neuen Sitzungs Konfiguration können Sie eine c#-Assembly, ein PowerShell-Skript und die Parameter des Register-PSSessionConfiguration-Cmdlets verwenden.</span><span class="sxs-lookup"><span data-stu-id="73638-175">To define the new session configuration, you can use a C# assembly, a PowerShell script, and the parameters of the Register-PSSessionConfiguration cmdlet.</span></span>

<span data-ttu-id="73638-176">Der folgende Befehl erstellt z. b. eine Sitzungs Konfiguration, die mit der Microsoft. PowerShell-Sitzungs Konfiguration identisch ist, mit dem Unterschied, dass die von einem Remote Befehl empfangenen Daten auf 20 Megabyte (MB) begrenzt werden.</span><span class="sxs-lookup"><span data-stu-id="73638-176">For example, the following command creates a session configuration that is identical the Microsoft.PowerShell session configuration, except that it limits the data received from a remote command to 20 megabytes (MB).</span></span> <span data-ttu-id="73638-177">(Der Standardwert ist 50 MB).</span><span class="sxs-lookup"><span data-stu-id="73638-177">(The default is 50 MB).</span></span>

```powershell
Register-PSSessionConfiguration -Name NewConfig `
  -MaximumReceivedDataSizePerCommandMB 20
```

<span data-ttu-id="73638-178">Wenn Sie eine Sitzungs Konfiguration erstellen, können Sie Sie mit den anderen Cmdlets für die Sitzungs Konfiguration verwalten, die auf dem WSMAN:-Laufwerk angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="73638-178">When you create a session configuration, you can manage it by using the other session configuration cmdlets, and it appears in the WSMAN: drive.</span></span>

<span data-ttu-id="73638-179">Weitere Informationen finden Sie unter Register-pssessionconfiguration.</span><span class="sxs-lookup"><span data-stu-id="73638-179">For more information, see Register-PSSessionConfiguration.</span></span>

<span data-ttu-id="73638-180">Entfernen einer Sitzungs Konfiguration</span><span class="sxs-lookup"><span data-stu-id="73638-180">Removing a Session Configuration</span></span>

<span data-ttu-id="73638-181">Verwenden Sie das Cmdlet "Unregister-PSSessionConfiguration", um eine Sitzungs Konfiguration vom lokalen Computer zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="73638-181">To remove a session configuration from the local computer, use the Unregister-PSSessionConfiguration cmdlet.</span></span> <span data-ttu-id="73638-182">Mit dem folgenden Befehl wird beispielsweise die Konfiguration der Neukonfigurations Sitzung vom Computer entfernt.</span><span class="sxs-lookup"><span data-stu-id="73638-182">For example, the following command removes the NewConfig session configuration from the computer.</span></span>

```powershell
PS C:> Unregister-PSSessionConfiguration -Name NewConfig
```

<span data-ttu-id="73638-183">Weitere Informationen finden Sie unter Unregister-pssessionconfiguration.</span><span class="sxs-lookup"><span data-stu-id="73638-183">For more information, see Unregister-PSSessionConfiguration.</span></span>

<span data-ttu-id="73638-184">Wiederherstellen einer Sitzungs Konfiguration</span><span class="sxs-lookup"><span data-stu-id="73638-184">Restoring a Session Configuration</span></span>

<span data-ttu-id="73638-185">Verwenden Sie das Cmdlet "Enable-PSRemoting", um eine standardmäßige Sitzungs Konfiguration, die versehentlich gelöscht wurde (ohne Registrierung), wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="73638-185">To restore a default session configuration that was deleted (unregistered) accidentally, use the Enable-PSRemoting cmdlet.</span></span>

<span data-ttu-id="73638-186">Mit dem Cmdlet "Enable-PSRemoting" werden alle Standard Sitzungs Konfigurationen neu erstellt, die auf dem Computer nicht vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="73638-186">The Enable-PSRemoting cmdlet recreates all default sessions configurations that do not exist on the computer.</span></span> <span data-ttu-id="73638-187">Die Eigenschaftswerte vorhandener Sitzungs Konfigurationen werden nicht überschrieben oder geändert.</span><span class="sxs-lookup"><span data-stu-id="73638-187">It does not overwrite or change the property values of existing session configurations.</span></span>

<span data-ttu-id="73638-188">Um die ursprünglichen Eigenschaftswerte einer Standard Sitzungs Konfiguration wiederherzustellen, verwenden Sie die Unregister-PSSessionConfiguration, um die Sitzungs Konfiguration zu löschen, und verwenden Sie dann das Enable-PSRemoting-Cmdlet, um Sie neu zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="73638-188">To restore the original property values of a default session configuration, use the Unregister-PSSessionConfiguration to delete the session configuration and then use the Enable-PSRemoting cmdlet to recreate it.</span></span>

<span data-ttu-id="73638-189">Auswählen einer Sitzungs Konfiguration</span><span class="sxs-lookup"><span data-stu-id="73638-189">Selecting a Session Configuration</span></span>

<span data-ttu-id="73638-190">Um eine bestimmte Sitzungs Konfiguration für eine Sitzung auszuwählen, verwenden Sie den ConfigurationName-Parameter von New-PSSession, Enter-PSSession oder aufrufen-Command.</span><span class="sxs-lookup"><span data-stu-id="73638-190">To select a particular session configuration for a session, use the ConfigurationName parameter of New-PSSession, Enter-PSSession, or Invoke-Command.</span></span>

<span data-ttu-id="73638-191">Dieser Befehl verwendet z. b. das New-PSSession-Cmdlet, um eine PSSession auf dem Server01-Computer zu starten.</span><span class="sxs-lookup"><span data-stu-id="73638-191">For example, this command uses the New-PSSession cmdlet to start a PSSession on the Server01 computer.</span></span> <span data-ttu-id="73638-192">Der Befehl verwendet den ConfigurationName-Parameter, um die withprofile-Konfiguration auf dem Server01-Computer auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="73638-192">The command uses the ConfigurationName parameter to select the WithProfile configuration on the Server01 computer.</span></span>

```powershell
PS C:> New-PSSession -ComputerName Server01 -ConfigurationName WithProfile
```

<span data-ttu-id="73638-193">Dieser Befehl ist nur erfolgreich, wenn der aktuelle Benutzer über die Berechtigung zum Verwenden der withprofile-Sitzungs Konfiguration verfügt oder die Anmelde Informationen eines Benutzers bereitstellen kann, der über die erforderlichen Berechtigungen verfügt.</span><span class="sxs-lookup"><span data-stu-id="73638-193">This command will succeed only if the current user has permission to use the WithProfile session configuration or can supply the credentials of a user who has the required permissions.</span></span>

<span data-ttu-id="73638-194">Sie können auch die $PSSessionConfigurationName Preference-Variable verwenden, um die Standard Sitzungs Konfiguration auf dem Computer zu ändern.</span><span class="sxs-lookup"><span data-stu-id="73638-194">You can also use the $PSSessionConfigurationName preference variable to change the default session configuration on the computer.</span></span> <span data-ttu-id="73638-195">Weitere Informationen zur $PSSessionConfigurationName Preference-Variablen finden Sie unter about_Preference_Variables.</span><span class="sxs-lookup"><span data-stu-id="73638-195">For more information about the $PSSessionConfigurationName preference variable, see about_Preference_Variables.</span></span>

## <a name="keywords"></a><span data-ttu-id="73638-196">Keywords</span><span class="sxs-lookup"><span data-stu-id="73638-196">KEYWORDS</span></span>

<span data-ttu-id="73638-197">about_Endpoints about_SessionConfigurations</span><span class="sxs-lookup"><span data-stu-id="73638-197">about_Endpoints about_SessionConfigurations</span></span>

## <a name="see-also"></a><span data-ttu-id="73638-198">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="73638-198">SEE ALSO</span></span>

[<span data-ttu-id="73638-199">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="73638-199">about_Preference_Variables</span></span>](about_Preference_Variables.md)

[<span data-ttu-id="73638-200">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="73638-200">about_PSSessions</span></span>](about_PSSessions.md)

[<span data-ttu-id="73638-201">about_Remote</span><span class="sxs-lookup"><span data-stu-id="73638-201">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="73638-202">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="73638-202">about_Session_Configuration_Files</span></span>](about_Session_Configuration_Files.md)

[<span data-ttu-id="73638-203">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="73638-203">New-PSSession</span></span>](xref:Microsoft.PowerShell.Core.New-PSSession)

[<span data-ttu-id="73638-204">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="73638-204">Disable-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Disable-PSSessionConfiguration)

[<span data-ttu-id="73638-205">Enable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="73638-205">Enable-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Enable-PSSessionConfiguration)

[<span data-ttu-id="73638-206">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="73638-206">Get-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Get-PSSessionConfiguration)

[<span data-ttu-id="73638-207">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="73638-207">New-PSSessionConfigurationFile</span></span>](xref:Microsoft.PowerShell.Core.New-PSSessionConfigurationFile)

[<span data-ttu-id="73638-208">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="73638-208">Register-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Register-PSSessionConfiguration)

[<span data-ttu-id="73638-209">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="73638-209">Set-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Set-PSSessionConfiguration)

[<span data-ttu-id="73638-210">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="73638-210">Test-PSSessionConfigurationFile</span></span>](xref:Microsoft.PowerShell.Core.Test-PSSessionConfigurationFile)

[<span data-ttu-id="73638-211">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="73638-211">Unregister-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Unregister-PSSessionConfiguration)
