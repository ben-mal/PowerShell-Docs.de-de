---
description: Beschreibt die Gruppenrichtlinie Einstellungen für PowerShell.
Locale: en-US
ms.date: 03/25/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_group_policy_settings?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Group_Policy_Settings
ms.openlocfilehash: 5ca13d22c69213dd8bae57a0dd08587c9c2b1541
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99595952"
---
# <a name="about-group-policy-settings"></a><span data-ttu-id="33513-103">Informationen zu Gruppenrichtlinie Einstellungen</span><span class="sxs-lookup"><span data-stu-id="33513-103">About Group Policy Settings</span></span>

## <a name="short-description"></a><span data-ttu-id="33513-104">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="33513-104">Short description</span></span>
<span data-ttu-id="33513-105">Beschreibt die Gruppenrichtlinie Einstellungen für PowerShell.</span><span class="sxs-lookup"><span data-stu-id="33513-105">Describes the Group Policy settings for PowerShell</span></span>

## <a name="long-description"></a><span data-ttu-id="33513-106">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="33513-106">Long description</span></span>

<span data-ttu-id="33513-107">PowerShell enthält Gruppenrichtlinie Einstellungen, mit deren Hilfe Sie konsistente Konfigurationswerte für Windows-Computer in einer Unternehmensumgebung definieren können.</span><span class="sxs-lookup"><span data-stu-id="33513-107">PowerShell includes Group Policy settings to help you define consistent configuration values for Windows computers in an enterprise environment.</span></span>

<span data-ttu-id="33513-108">Die PowerShell-Gruppenrichtlinie Einstellungen befinden sich in den folgenden Gruppenrichtlinie Pfaden:</span><span class="sxs-lookup"><span data-stu-id="33513-108">The PowerShell Group Policy settings are in the following Group Policy paths:</span></span>

```
Computer Configuration\
  Administrative Templates\
    PowerShell Core

User Configuration\
  Administrative Templates\
    PowerShell Core
```

<span data-ttu-id="33513-109">Die Gruppenrichtlinien Einstellungen im Benutzer Konfigurations Pfad haben Vorrang vor den Gruppenrichtlinie Einstellungen im Computer Konfigurations Pfad.</span><span class="sxs-lookup"><span data-stu-id="33513-109">Group policy settings in the User Configuration path take precedence over Group Policy settings in the Computer Configuration path.</span></span>

<span data-ttu-id="33513-110">PowerShell 7 bietet Gruppenrichtlinienvorlagen und in `$PSHOME` ein Installationsskript.</span><span class="sxs-lookup"><span data-stu-id="33513-110">PowerShell 7 includes Group Policy templates and an installation script in `$PSHOME`.</span></span>

<span data-ttu-id="33513-111">Gruppenrichtlinientools verwenden administrative Vorlagendateien (`.admx`, `.adml`), um Richtlinieneinstellungen auf der Benutzeroberfläche aufzufüllen.</span><span class="sxs-lookup"><span data-stu-id="33513-111">Group Policy tools use administrative template files (`.admx`, `.adml`) to populate policy settings in the user interface.</span></span> <span data-ttu-id="33513-112">Dies ermöglicht Administratoren die Verwaltung registrierungsbasierter Richtlinieneinstellungen.</span><span class="sxs-lookup"><span data-stu-id="33513-112">This allows administrators to manage registry-based policy settings.</span></span> <span data-ttu-id="33513-113">Das `InstallPSCorePolicyDefinitions.ps1` Skript installiert **PowerShell Core administrative Vorlagen** auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="33513-113">The `InstallPSCorePolicyDefinitions.ps1` script installs **PowerShell Core Administrative Templates** on the local machine.</span></span>

```powershell
Get-ChildItem -Path $PSHOME -Filter *Core*Policy*
```

```Output
    Directory: C:\Program Files\PowerShell\7

Mode       LastWriteTime         Length Name
----       -------------         ------ ----
-a---      2/27/2020 12:38 AM     15861 InstallPSCorePolicyDefinitions.ps1
-a---      2/27/2020 12:28 AM      9675 PowerShellCoreExecutionPolicy.adml
-a---      2/27/2020 12:28 AM      6201 PowerShellCoreExecutionPolicy.admx
```

<span data-ttu-id="33513-114">Nachdem Sie die Vorlagen installiert haben, können Sie diese Einstellungen im Gruppenrichtlinie-Editor ( `gpedit.msc` ) bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="33513-114">After installing the templates, you can edit these settings in the Group Policy editor (`gpedit.msc`).</span></span>

<span data-ttu-id="33513-115">Die Richtlinien lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="33513-115">The policies are as follows:</span></span>

- <span data-ttu-id="33513-116">Konfiguration der Konsolensitzung: Legt einen Konfigurationsendpunkt fest, an dem PowerShell ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="33513-116">Console session configuration: Sets a configuration endpoint in which PowerShell is run.</span></span>
- <span data-ttu-id="33513-117">Modul Protokollierung aktivieren: legt die **logpipelineexecutiondetails** -Eigenschaft von Modulen fest.</span><span class="sxs-lookup"><span data-stu-id="33513-117">Turn on Module Logging: Sets the **LogPipelineExecutionDetails** property of modules.</span></span>
- <span data-ttu-id="33513-118">Protokollierung von PowerShell-Skriptblöcken: Aktiviert die ausführliche Protokollierung aller PowerShell-Skripts.</span><span class="sxs-lookup"><span data-stu-id="33513-118">Turn on PowerShell Script Block Logging: Enables detailed logging of all PowerShell scripts.</span></span>
- <span data-ttu-id="33513-119">Skriptausführung aktivieren: Legt die PowerShell-Ausführungsrichtlinie fest.</span><span class="sxs-lookup"><span data-stu-id="33513-119">Turn on Script Execution: Sets the PowerShell execution policy.</span></span>
- <span data-ttu-id="33513-120">PowerShell-Aufzeichnung aktivieren: ermöglicht die Erfassung der Ein- und Ausgabe von PowerShell-Befehlen in textbasierten Transkripten.</span><span class="sxs-lookup"><span data-stu-id="33513-120">Turn on PowerShell Transcription: enables capturing of input and output of PowerShell commands into text-based transcripts.</span></span>
- <span data-ttu-id="33513-121">Legen Sie den Standard Quellpfad für fest `Update-Help` : legt die Quelle für die aktualisierbare Hilfe zu einem Verzeichnis, nicht zum Internet, fest.</span><span class="sxs-lookup"><span data-stu-id="33513-121">Set the default source path for `Update-Help`: Sets the source for Updatable Help to a directory, not the Internet.</span></span>

<span data-ttu-id="33513-122">Jede PowerShell-Gruppenrichtlinie Einstellung verfügt über eine Option (das Feld "Windows PowerShell-Richtlinien Einstellung verwenden"), um den Wert aus einer ähnlichen Windows PowerShell-Gruppenrichtlinie Einstellung zu verwenden, die sich in den folgenden Gruppenrichtlinie Pfaden befindet:</span><span class="sxs-lookup"><span data-stu-id="33513-122">Each PowerShell Group Policy setting has an option ('Use Windows PowerShell Policy setting' field) to use the value from a similar Windows PowerShell Group Policy setting that is located in the following Group Policy paths:</span></span>

```
Computer Configuration\
  Administrative Templates\
    Windows Components\
      Windows PowerShell

User Configuration\
  Administrative Templates\
    Windows Components\
      Windows PowerShell
```

> [!NOTE]
> <span data-ttu-id="33513-123">Diese **PowerShell Core-administrative Vorlagen** enthalten keine Einstellungen für Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="33513-123">These **PowerShell Core Administrative Templates** do not include settings for Windows PowerShell.</span></span> <span data-ttu-id="33513-124">Weitere Informationen zum Abrufen anderer Vorlagen und zum Konfigurieren der Gruppenrichtlinie finden [Sie unter Erstellen und Verwalten des zentralen Speicher für Gruppenrichtlinie administrative Vorlagen in Windows][gpstore].</span><span class="sxs-lookup"><span data-stu-id="33513-124">For more information about acquiring other templates and configuring Group policy, see [How to create and manage the Central Store for Group Policy Administrative Templates in Windows][gpstore].</span></span>

## <a name="console-session-configuration"></a><span data-ttu-id="33513-125">Konsolen Sitzungs Konfiguration</span><span class="sxs-lookup"><span data-stu-id="33513-125">Console session configuration</span></span>

<span data-ttu-id="33513-126">Die Richtlinien Einstellung **Konsolen Sitzungs Konfiguration** gibt einen Konfigurations Endpunkt an, in dem PowerShell ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="33513-126">The **Console session configuration** policy setting specifies a configuration endpoint in which PowerShell is run.</span></span> <span data-ttu-id="33513-127">Dies kann ein beliebiger Endpunkt sein, der auf dem lokalen Computer registriert ist, einschließlich der standardmäßigen PowerShell-Remoting-Endpunkte oder ein benutzerdefinierter Endpunkt, der über bestimmte Benutzer Rollen</span><span class="sxs-lookup"><span data-stu-id="33513-127">This can be any endpoint registered on the local machine including the default PowerShell remoting endpoints or a custom endpoint having specific user role capabilities.</span></span>

## <a name="turn-on-module-logging"></a><span data-ttu-id="33513-128">Aktivieren der Modul Protokollierung</span><span class="sxs-lookup"><span data-stu-id="33513-128">Turn on module logging</span></span>

<span data-ttu-id="33513-129">Mit der Richtlinien Einstellung " **Modul Protokollierung** aktivieren" wird die Protokollierung für ausgewählte PowerShell-Module aktiviert.</span><span class="sxs-lookup"><span data-stu-id="33513-129">The **Turn on Module Logging** policy setting turns on logging for selected PowerShell modules.</span></span> <span data-ttu-id="33513-130">Die Einstellung ist in allen Sitzungen auf allen betroffenen Computern wirksam.</span><span class="sxs-lookup"><span data-stu-id="33513-130">The setting is effective in all sessions on all affected computers.</span></span>

<span data-ttu-id="33513-131">Wenn Sie diese Richtlinien Einstellung aktivieren und ein oder mehrere Module angeben, werden Pipeline Ausführungs Ereignisse für die angegebenen Module im Windows PowerShell-Protokoll Ereignisanzeige aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="33513-131">If you enable this policy setting and specify one or more modules, pipeline execution events for the specified modules are recorded in the Windows PowerShell log in Event Viewer.</span></span>

<span data-ttu-id="33513-132">Wenn Sie diese Richtlinien Einstellung deaktivieren, wird die Protokollierung von Ausführungs Ereignissen für alle PowerShell-Module deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="33513-132">If you disable this policy setting, logging of execution events is disabled for all PowerShell modules.</span></span>

<span data-ttu-id="33513-133">Wenn diese Richtlinien Einstellung nicht konfiguriert ist, bestimmt die **logpipelineexecutiondetails** -Eigenschaft jedes Moduls, ob die Ausführungs Ereignisse eines Moduls protokolliert werden.</span><span class="sxs-lookup"><span data-stu-id="33513-133">If this policy setting is not configured, the **LogPipelineExecutionDetails** property of each module determines whether the execution events of a module are logged.</span></span> <span data-ttu-id="33513-134">Standardmäßig ist die **logpipelineexecutiondetails** -Eigenschaft aller Module auf false festgelegt.</span><span class="sxs-lookup"><span data-stu-id="33513-134">By default, the **LogPipelineExecutionDetails** property of all modules is set to False.</span></span>

<span data-ttu-id="33513-135">Verwenden Sie das folgende Befehls Format, um die Modul Protokollierung für ein Modul zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="33513-135">To turn on module logging for a module, use the following command format.</span></span> <span data-ttu-id="33513-136">Das Modul muss in die Sitzung importiert werden, und die Einstellung ist nur in der aktuellen Sitzung gültig.</span><span class="sxs-lookup"><span data-stu-id="33513-136">The module must be imported into the session and the setting is effective only in the current session.</span></span>

```powershell
Import-Module <Module-Name>
(Get-Module <Module-Name>).LogPipelineExecutionDetails = $true
```

<span data-ttu-id="33513-137">Fügen Sie zum Aktivieren der Modul Protokollierung für alle Sitzungen auf einem bestimmten Computer die vorherigen Befehle zum PowerShell-Profil "alle Benutzer" ( `$Profile.AllUsersAllHosts` ) hinzu.</span><span class="sxs-lookup"><span data-stu-id="33513-137">To turn on module logging for all sessions on a particular computer, add the previous commands to the 'All Users' PowerShell profile (`$Profile.AllUsersAllHosts`).</span></span>

<span data-ttu-id="33513-138">Weitere Informationen zur Modul Protokollierung finden Sie unter [about_Modules](about_Modules.md).</span><span class="sxs-lookup"><span data-stu-id="33513-138">For more information about module logging, see [about_Modules](about_Modules.md).</span></span>

## <a name="turn-on-powershell-script-block-logging"></a><span data-ttu-id="33513-139">Aktivieren der PowerShell-Skriptblock Protokollierung</span><span class="sxs-lookup"><span data-stu-id="33513-139">Turn on PowerShell script block logging</span></span>

<span data-ttu-id="33513-140">Die Richtlinien Einstellung **PowerShell-Skript Block Protokollierung aktivieren** ermöglicht das Protokollieren aller PowerShell-Skript Eingaben im Ereignisprotokoll Microsoft-Windows-PowerShell/Operational.</span><span class="sxs-lookup"><span data-stu-id="33513-140">The **Turn on PowerShell Script Block Logging** policy setting enables logging of all PowerShell script input to the Microsoft-Windows-PowerShell/Operational event log.</span></span> <span data-ttu-id="33513-141">Wenn Sie diese Richtlinien Einstellung aktivieren, protokolliert PowerShell Core die Verarbeitung von Befehlen, Skript Blöcken, Funktionen und Skripts, unabhängig davon, ob Sie interaktiv aufgerufen werden, oder durch Automatisierung.</span><span class="sxs-lookup"><span data-stu-id="33513-141">If you enable this policy setting, PowerShell Core will log the processing of commands, script blocks, functions, and scripts - whether invoked interactively, or through automation.</span></span>

<span data-ttu-id="33513-142">Wenn Sie diese Richtlinieneinstellung deaktivieren, ist das Protokollieren von PowerShell-Skript-Eingaben deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="33513-142">If you disable this policy setting, logging of PowerShell script input is disabled.</span></span> <span data-ttu-id="33513-143">Wenn Sie die Protokollierung von Skriptblockaufrufen aktivieren, protokolliert PowerShell zusätzlich Protokollereignisse, wenn ein Befehl, ein Skriptblock, eine Funktion oder Skriptstarts oder -stops aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="33513-143">If you enable the Script Block Invocation Logging, PowerShell additionally logs events when invocation of a command, script block, function, or script starts or stops.</span></span> <span data-ttu-id="33513-144">Das Aktivieren der Protokollierung von Aufrufen führt zu einer großen Anzahl von Ereignisprotokollen.</span><span class="sxs-lookup"><span data-stu-id="33513-144">Enabling Invocation Logging generates a high volume of event logs.</span></span>

## <a name="turn-on-script-execution"></a><span data-ttu-id="33513-145">Skriptausführung aktivieren</span><span class="sxs-lookup"><span data-stu-id="33513-145">Turn on script execution</span></span>

<span data-ttu-id="33513-146">Mit der Richtlinien Einstellung **Skriptausführung aktivieren** wird die Ausführungs Richtlinie für Computer und Benutzer festgelegt, die bestimmt, welche Skripts ausgeführt werden dürfen.</span><span class="sxs-lookup"><span data-stu-id="33513-146">The **Turn on Script Execution** policy setting sets the execution policy for computers and users, which determines which scripts are permitted to run.</span></span>

<span data-ttu-id="33513-147">Wenn Sie die Richtlinien Einstellung aktivieren, können Sie zwischen den folgenden Richtlinien Einstellungen wählen.</span><span class="sxs-lookup"><span data-stu-id="33513-147">If you enable the policy setting, you can select from among the following policy settings.</span></span>

- <span data-ttu-id="33513-148">**Nur signierte Skripts zulassen** : Skripts können nur ausgeführt werden, wenn Sie von einem vertrauenswürdigen Herausgeber signiert wurden.</span><span class="sxs-lookup"><span data-stu-id="33513-148">**Allow only signed scripts** allows scripts to execute only if they are signed by a trusted publisher.</span></span> <span data-ttu-id="33513-149">Diese Richtlinien Einstellung entspricht der AllSigned-Ausführungs Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="33513-149">This policy setting is equivalent to the AllSigned execution policy.</span></span>

- <span data-ttu-id="33513-150">**Lokale Skripts und Remote signierte Skripts zulassen** ermöglicht das Ausführen aller lokalen Skripts.</span><span class="sxs-lookup"><span data-stu-id="33513-150">**Allow local scripts and remote signed scripts** allows all local scripts to run.</span></span> <span data-ttu-id="33513-151">Skripts, die aus dem Internet stammen, müssen von einem vertrauenswürdigen Herausgeber signiert werden.</span><span class="sxs-lookup"><span data-stu-id="33513-151">Scripts that originate from the Internet must be signed by a trusted publisher.</span></span> <span data-ttu-id="33513-152">Diese Richtlinien Einstellung entspricht der RemoteSigned-Ausführungs Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="33513-152">This policy setting is equivalent to the RemoteSigned execution policy.</span></span>

- <span data-ttu-id="33513-153">**Alle Skripts zulassen** ermöglicht das Ausführen aller Skripts.</span><span class="sxs-lookup"><span data-stu-id="33513-153">**Allow all scripts** allows all scripts to run.</span></span> <span data-ttu-id="33513-154">Diese Richtlinien Einstellung entspricht der uneingeschränkten Ausführungs Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="33513-154">This policy setting is equivalent to the Unrestricted execution policy.</span></span>

<span data-ttu-id="33513-155">Wenn Sie diese Richtlinien Einstellung deaktivieren, dürfen keine Skripts ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="33513-155">If you disable this policy setting, no scripts are allowed to run.</span></span> <span data-ttu-id="33513-156">Diese Richtlinien Einstellung entspricht der eingeschränkten Ausführungs Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="33513-156">This policy setting is equivalent to the Restricted execution policy.</span></span>

<span data-ttu-id="33513-157">Wenn Sie diese Richtlinien Einstellung deaktivieren oder nicht konfigurieren, bestimmt die Ausführungs Richtlinie, die vom Cmdlet für den Computer oder Benutzer festgelegt wird, `Set-ExecutionPolicy` ob Skripts ausgeführt werden dürfen.</span><span class="sxs-lookup"><span data-stu-id="33513-157">If you disable or do not configure this policy setting, the execution policy that is set for the computer or user by the `Set-ExecutionPolicy` cmdlet determines whether scripts are permitted to run.</span></span> <span data-ttu-id="33513-158">Der Standardwert ist "Restricted".</span><span class="sxs-lookup"><span data-stu-id="33513-158">The default value is Restricted.</span></span>

<span data-ttu-id="33513-159">Weitere Informationen finden Sie unter [about_Execution_Policies](about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="33513-159">For more information, see [about_Execution_Policies](about_Execution_Policies.md).</span></span>

## <a name="turn-on-powershell-transcription"></a><span data-ttu-id="33513-160">Aktivieren der PowerShell-Aufzeichnung</span><span class="sxs-lookup"><span data-stu-id="33513-160">Turn on powershell transcription</span></span>

<span data-ttu-id="33513-161">Mithilfe der Richtlinien Einstellung **PowerShell** -Aufzeichnung aktivieren können Sie die Eingabe und die Ausgabe von PowerShell Core-Befehlen in textbasierte Transkriptionen aufzeichnen.</span><span class="sxs-lookup"><span data-stu-id="33513-161">The **Turn on PowerShell Transcription** policy setting lets you capture the input and output of PowerShell Core commands into text-based transcripts.</span></span> <span data-ttu-id="33513-162">Wenn Sie diese Richtlinien Einstellung aktivieren, aktiviert PowerShell Core die Protokollierungs Protokollierung für PowerShell Core und alle anderen Anwendungen, die die PowerShell-Kern-Engine nutzen.</span><span class="sxs-lookup"><span data-stu-id="33513-162">If you enable this policy setting, PowerShell Core will enable transcription logging for PowerShell Core and any other applications that leverage the PowerShell Core engine.</span></span> <span data-ttu-id="33513-163">Standardmäßig zeichnet PowerShell Core die Transkriptions Ausgabe im Verzeichnis "eigene Dateien" der einzelnen Benutzer auf, wobei der Dateiname "PowerShell_transcript" sowie der Computername und die Startzeit enthalten.</span><span class="sxs-lookup"><span data-stu-id="33513-163">By default, PowerShell Core will record transcript output to each users' My Documents directory, with a file name that includes 'PowerShell_transcript', along with the computer name and time started.</span></span>
<span data-ttu-id="33513-164">Die Aktivierung dieser Richtlinie entspricht dem Aufrufen des Start-Transcript Cmdlets für jede PowerShell-Kern Sitzung.</span><span class="sxs-lookup"><span data-stu-id="33513-164">Enabling this policy is equivalent to calling the Start-Transcript cmdlet on each PowerShell Core session.</span></span>

<span data-ttu-id="33513-165">Wenn Sie diese Richtlinien Einstellung deaktivieren, ist die Protokollierungs Protokollierung von PowerShell-basierten Anwendungen standardmäßig deaktiviert, obwohl das transkripting weiterhin über das Cmdlet "Start-Transcript" aktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="33513-165">If you disable this policy setting, transcription logging of PowerShell-based applications is disabled by default, although transcripting can still be enabled through the Start-Transcript cmdlet.</span></span>

<span data-ttu-id="33513-166">Wenn Sie die Einstellung OutputDirectory verwenden, um die Protokollierungs Protokollierung an einem freigegebenen Speicherort zu aktivieren, achten Sie darauf, den Zugriff auf dieses Verzeichnis einzuschränken, um zu verhindern, dass Benutzer die Protokolle anderer Benutzer oder Computer anzeigen.</span><span class="sxs-lookup"><span data-stu-id="33513-166">If you use the OutputDirectory setting to enable transcription logging to a shared location, be sure to limit access to that directory to prevent users from viewing the transcripts of other users or computers.</span></span>

## <a name="set-the-default-source-path-for-update-help"></a><span data-ttu-id="33513-167">Standard Quellpfad für Update-Help festlegen</span><span class="sxs-lookup"><span data-stu-id="33513-167">Set the default source path for Update-Help</span></span>

<span data-ttu-id="33513-168">Die Richtlinien Einstellung **Standard Quellpfad für Update-Hilfe festlegen** legt einen Standardwert für den **SourcePath** -Parameter des `Update-Help` Cmdlets fest.</span><span class="sxs-lookup"><span data-stu-id="33513-168">The **Set the Default Source Path for Update-Help** policy setting sets a default value for the **SourcePath** parameter of the `Update-Help` cmdlet.</span></span>
<span data-ttu-id="33513-169">Diese Einstellung verhindert, dass Benutzer das `Update-Help` Cmdlet zum Herunterladen der Hilfedateien aus dem Internet verwenden.</span><span class="sxs-lookup"><span data-stu-id="33513-169">This setting prevents users from using the `Update-Help` cmdlet to download help files from the Internet.</span></span>

> [!NOTE]
> <span data-ttu-id="33513-170">Diese Gruppenrichtlinie Einstellung wird unter **Computer Konfiguration** und **Benutzerkonfiguration** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="33513-170">This Group Policy setting appears under **Computer Configuration** and **User Configuration**.</span></span> <span data-ttu-id="33513-171">Allerdings ist nur die Einstellung Gruppenrichtlinie unter **Computer Konfiguration** wirksam.</span><span class="sxs-lookup"><span data-stu-id="33513-171">However, only the Group Policy setting under **Computer Configuration** is effective.</span></span> <span data-ttu-id="33513-172">Die Gruppenrichtlinie Einstellung unter **Benutzerkonfiguration** wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="33513-172">The Group Policy setting under **User Configuration** is ignored.</span></span>

<span data-ttu-id="33513-173">Mit dem- `Update-Help` Cmdlet werden die neuesten Hilfedateien für PowerShell-Module heruntergeladen und installiert und auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="33513-173">The `Update-Help` cmdlet downloads and installs the newest help files for PowerShell modules and installs them on the computer.</span></span> <span data-ttu-id="33513-174">Standardmäßig `Update-Help` lädt neue Hilfedateien von einem durch das Modul angegebenen Internet Speicherort herunter.</span><span class="sxs-lookup"><span data-stu-id="33513-174">By default, `Update-Help` downloads new help files from an Internet location specified by the module.</span></span>

<span data-ttu-id="33513-175">Sie können das `Save-Help` Cmdlet jedoch verwenden, um die neuesten Hilfedateien an einen Dateisystem Speicherort (z. b. eine Netzwerkfreigabe) herunterzuladen. verwenden Sie dann das `Update-Help` Cmdlet, um die Hilfedateien vom Dateisystem Speicherort zu erhalten und auf dem Computer zu installieren.</span><span class="sxs-lookup"><span data-stu-id="33513-175">However, you can use the `Save-Help` cmdlet to download the newest help files to a file system location, such as a network share, and then use the `Update-Help` cmdlet to get the help files from the file system location and install them on the computer.</span></span> <span data-ttu-id="33513-176">Der **SourcePath** -Parameter des `Update-Help` Cmdlets gibt den Speicherort des Dateisystems an.</span><span class="sxs-lookup"><span data-stu-id="33513-176">The **SourcePath** parameter of the `Update-Help` cmdlet specifies the file system location.</span></span>

<span data-ttu-id="33513-177">Durch die Angabe eines Standardwerts für den **SourcePath** -Parameter fügt diese Gruppenrichtlinie Einstellung allen Befehlen implizit den **SourcePath** -Parameter hinzu `Update-Help` .</span><span class="sxs-lookup"><span data-stu-id="33513-177">By providing a default value for the **SourcePath** parameter, this Group Policy setting implicitly adds the **SourcePath** parameter to all `Update-Help` commands.</span></span> <span data-ttu-id="33513-178">Benutzer können den angegebenen Dateisystem Speicherort, der als Standardwert angegeben ist, überschreiben, indem Sie einen anderen Dateisystem Speicherort eingeben.</span><span class="sxs-lookup"><span data-stu-id="33513-178">Users can override the particular file system location specified as the default value by entering a different file system location.</span></span>
<span data-ttu-id="33513-179">Der **SourcePath** -Parameter kann jedoch nicht aus dem `Update-Help` Befehl entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="33513-179">But they cannot remove the **SourcePath** parameter from the `Update-Help` command.</span></span>

<span data-ttu-id="33513-180">Wenn Sie diese Richtlinien Einstellung aktivieren, können Sie einen Standardwert für den **SourcePath** -Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="33513-180">If you enable this policy setting, you can specify a default value for the **SourcePath** parameter.</span></span> <span data-ttu-id="33513-181">Geben Sie einen Dateisystem Speicherort ein.</span><span class="sxs-lookup"><span data-stu-id="33513-181">Enter a file system location.</span></span>

<span data-ttu-id="33513-182">Wenn diese Richtlinien Einstellung deaktiviert oder nicht konfiguriert ist, gibt es keinen Standardwert für den **SourcePath** -Parameter des `Update-Help` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="33513-182">If this policy setting is disabled or not configured, there is no default value for the **SourcePath** parameter of the `Update-Help` cmdlet.</span></span> <span data-ttu-id="33513-183">Benutzer können die Hilfe aus dem Internet oder von einem beliebigen Dateisystem Speicherort herunterladen.</span><span class="sxs-lookup"><span data-stu-id="33513-183">Users can download help from the Internet or from any file system location.</span></span>

<span data-ttu-id="33513-184">Weitere Informationen hierzu finden Sie unter [about_Updatable_Help](about_Updatable_Help.md).</span><span class="sxs-lookup"><span data-stu-id="33513-184">For more information, see [about_Updatable_Help](about_Updatable_Help.md).</span></span>

## <a name="keywords"></a><span data-ttu-id="33513-185">Keywords</span><span class="sxs-lookup"><span data-stu-id="33513-185">Keywords</span></span>

<span data-ttu-id="33513-186">about_Group_Policies about_GroupPolicy</span><span class="sxs-lookup"><span data-stu-id="33513-186">about_Group_Policies about_GroupPolicy</span></span>

## <a name="see-also"></a><span data-ttu-id="33513-187">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="33513-187">See also</span></span>

[<span data-ttu-id="33513-188">PowerShell-Kern Richtlinie RFC</span><span class="sxs-lookup"><span data-stu-id="33513-188">PowerShell Core Policy RFC</span></span>](https://github.com/PowerShell/PowerShell-RFC/blob/master/4-Experimental-Accepted/RFC0041-Policy.md)

[<span data-ttu-id="33513-189">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="33513-189">about_Execution_Policies</span></span>](about_Execution_Policies.md)

[<span data-ttu-id="33513-190">about_Modules</span><span class="sxs-lookup"><span data-stu-id="33513-190">about_Modules</span></span>](about_Modules.md)

[<span data-ttu-id="33513-191">about_Updatable_Help</span><span class="sxs-lookup"><span data-stu-id="33513-191">about_Updatable_Help</span></span>](about_Updatable_Help.md)

[<span data-ttu-id="33513-192">Get-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="33513-192">Get-ExecutionPolicy</span></span>](xref:Microsoft.PowerShell.Security.Get-ExecutionPolicy)

[<span data-ttu-id="33513-193">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="33513-193">Set-ExecutionPolicy</span></span>](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy)

[<span data-ttu-id="33513-194">Get-Module</span><span class="sxs-lookup"><span data-stu-id="33513-194">Get-Module</span></span>](xref:Microsoft.PowerShell.Core.Get-Module)

[<span data-ttu-id="33513-195">Update-Help</span><span class="sxs-lookup"><span data-stu-id="33513-195">Update-Help</span></span>](xref:Microsoft.PowerShell.Core.Update-Help)

[<span data-ttu-id="33513-196">Save-Help</span><span class="sxs-lookup"><span data-stu-id="33513-196">Save-Help</span></span>](xref:Microsoft.PowerShell.Core.Save-Help)

<!-- link references -->
[gpstore]: https://support.microsoft.com/help/3087759

