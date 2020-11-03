---
description: Beschreibt die Gruppenrichtlinie Einstellungen für PowerShell.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 03/25/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_group_policy_settings?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Group_Policy_Settings
ms.openlocfilehash: df2a3e9349dd3afbe621bd11b92ac5cdf552492a
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93220900"
---
# <a name="about-group-policy-settings"></a><span data-ttu-id="0691a-104">Informationen zu Gruppenrichtlinie Einstellungen</span><span class="sxs-lookup"><span data-stu-id="0691a-104">About Group Policy Settings</span></span>

## <a name="short-description"></a><span data-ttu-id="0691a-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0691a-105">Short description</span></span>
<span data-ttu-id="0691a-106">Beschreibt die Gruppenrichtlinie Einstellungen für PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0691a-106">Describes the Group Policy settings for PowerShell</span></span>

## <a name="long-description"></a><span data-ttu-id="0691a-107">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0691a-107">Long description</span></span>

<span data-ttu-id="0691a-108">PowerShell enthält Gruppenrichtlinie Einstellungen, mit deren Hilfe Sie konsistente Konfigurationswerte für Windows-Computer in einer Unternehmensumgebung definieren können.</span><span class="sxs-lookup"><span data-stu-id="0691a-108">PowerShell includes Group Policy settings to help you define consistent configuration values for Windows computers in an enterprise environment.</span></span>

<span data-ttu-id="0691a-109">Die PowerShell-Gruppenrichtlinie Einstellungen befinden sich in den folgenden Gruppenrichtlinie Pfaden:</span><span class="sxs-lookup"><span data-stu-id="0691a-109">The PowerShell Group Policy settings are in the following Group Policy paths:</span></span>

```
Computer Configuration\
  Administrative Templates\
    PowerShell Core

User Configuration\
  Administrative Templates\
    PowerShell Core
```

<span data-ttu-id="0691a-110">Die Gruppenrichtlinien Einstellungen im Benutzer Konfigurations Pfad haben Vorrang vor den Gruppenrichtlinie Einstellungen im Computer Konfigurations Pfad.</span><span class="sxs-lookup"><span data-stu-id="0691a-110">Group policy settings in the User Configuration path take precedence over Group Policy settings in the Computer Configuration path.</span></span>

<span data-ttu-id="0691a-111">PowerShell 7 bietet Gruppenrichtlinienvorlagen und in `$PSHOME` ein Installationsskript.</span><span class="sxs-lookup"><span data-stu-id="0691a-111">PowerShell 7 includes Group Policy templates and an installation script in `$PSHOME`.</span></span>

<span data-ttu-id="0691a-112">Gruppenrichtlinientools verwenden administrative Vorlagendateien (`.admx`, `.adml`), um Richtlinieneinstellungen auf der Benutzeroberfläche aufzufüllen.</span><span class="sxs-lookup"><span data-stu-id="0691a-112">Group Policy tools use administrative template files (`.admx`, `.adml`) to populate policy settings in the user interface.</span></span> <span data-ttu-id="0691a-113">Dies ermöglicht Administratoren die Verwaltung registrierungsbasierter Richtlinieneinstellungen.</span><span class="sxs-lookup"><span data-stu-id="0691a-113">This allows administrators to manage registry-based policy settings.</span></span> <span data-ttu-id="0691a-114">Das `InstallPSCorePolicyDefinitions.ps1` Skript installiert **PowerShell Core administrative Vorlagen** auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="0691a-114">The `InstallPSCorePolicyDefinitions.ps1` script installs **PowerShell Core Administrative Templates** on the local machine.</span></span>

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

<span data-ttu-id="0691a-115">Nachdem Sie die Vorlagen installiert haben, können Sie diese Einstellungen im Gruppenrichtlinie-Editor ( `gpedit.msc` ) bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="0691a-115">After installing the templates, you can edit these settings in the Group Policy editor (`gpedit.msc`).</span></span>

<span data-ttu-id="0691a-116">Die Richtlinien lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="0691a-116">The policies are as follows:</span></span>

- <span data-ttu-id="0691a-117">Konfiguration der Konsolensitzung: Legt einen Konfigurationsendpunkt fest, an dem PowerShell ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0691a-117">Console session configuration: Sets a configuration endpoint in which PowerShell is run.</span></span>
- <span data-ttu-id="0691a-118">Modul Protokollierung aktivieren: legt die **logpipelineexecutiondetails** -Eigenschaft von Modulen fest.</span><span class="sxs-lookup"><span data-stu-id="0691a-118">Turn on Module Logging: Sets the **LogPipelineExecutionDetails** property of modules.</span></span>
- <span data-ttu-id="0691a-119">Protokollierung von PowerShell-Skriptblöcken: Aktiviert die ausführliche Protokollierung aller PowerShell-Skripts.</span><span class="sxs-lookup"><span data-stu-id="0691a-119">Turn on PowerShell Script Block Logging: Enables detailed logging of all PowerShell scripts.</span></span>
- <span data-ttu-id="0691a-120">Skriptausführung aktivieren: Legt die PowerShell-Ausführungsrichtlinie fest.</span><span class="sxs-lookup"><span data-stu-id="0691a-120">Turn on Script Execution: Sets the PowerShell execution policy.</span></span>
- <span data-ttu-id="0691a-121">PowerShell-Aufzeichnung aktivieren: ermöglicht die Erfassung der Ein- und Ausgabe von PowerShell-Befehlen in textbasierten Transkripten.</span><span class="sxs-lookup"><span data-stu-id="0691a-121">Turn on PowerShell Transcription: enables capturing of input and output of PowerShell commands into text-based transcripts.</span></span>
- <span data-ttu-id="0691a-122">Legen Sie den Standard Quellpfad für fest `Update-Help` : legt die Quelle für die aktualisierbare Hilfe zu einem Verzeichnis, nicht zum Internet, fest.</span><span class="sxs-lookup"><span data-stu-id="0691a-122">Set the default source path for `Update-Help`: Sets the source for Updatable Help to a directory, not the Internet.</span></span>

<span data-ttu-id="0691a-123">Jede PowerShell-Gruppenrichtlinie Einstellung verfügt über eine Option (das Feld "Windows PowerShell-Richtlinien Einstellung verwenden"), um den Wert aus einer ähnlichen Windows PowerShell-Gruppenrichtlinie Einstellung zu verwenden, die sich in den folgenden Gruppenrichtlinie Pfaden befindet:</span><span class="sxs-lookup"><span data-stu-id="0691a-123">Each PowerShell Group Policy setting has an option ('Use Windows PowerShell Policy setting' field) to use the value from a similar Windows PowerShell Group Policy setting that is located in the following Group Policy paths:</span></span>

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
> <span data-ttu-id="0691a-124">Diese **PowerShell Core-administrative Vorlagen** enthalten keine Einstellungen für Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0691a-124">These **PowerShell Core Administrative Templates** do not include settings for Windows PowerShell.</span></span> <span data-ttu-id="0691a-125">Weitere Informationen zum Abrufen anderer Vorlagen und zum Konfigurieren der Gruppenrichtlinie finden [Sie unter Erstellen und Verwalten des zentralen Speicher für Gruppenrichtlinie administrative Vorlagen in Windows][gpstore].</span><span class="sxs-lookup"><span data-stu-id="0691a-125">For more information about acquiring other templates and configuring Group policy, see [How to create and manage the Central Store for Group Policy Administrative Templates in Windows][gpstore].</span></span>

## <a name="console-session-configuration"></a><span data-ttu-id="0691a-126">Konsolen Sitzungs Konfiguration</span><span class="sxs-lookup"><span data-stu-id="0691a-126">Console session configuration</span></span>

<span data-ttu-id="0691a-127">Die Richtlinien Einstellung **Konsolen Sitzungs Konfiguration** gibt einen Konfigurations Endpunkt an, in dem PowerShell ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0691a-127">The **Console session configuration** policy setting specifies a configuration endpoint in which PowerShell is run.</span></span> <span data-ttu-id="0691a-128">Dies kann ein beliebiger Endpunkt sein, der auf dem lokalen Computer registriert ist, einschließlich der standardmäßigen PowerShell-Remoting-Endpunkte oder ein benutzerdefinierter Endpunkt, der über bestimmte Benutzer Rollen</span><span class="sxs-lookup"><span data-stu-id="0691a-128">This can be any endpoint registered on the local machine including the default PowerShell remoting endpoints or a custom endpoint having specific user role capabilities.</span></span>

## <a name="turn-on-module-logging"></a><span data-ttu-id="0691a-129">Aktivieren der Modul Protokollierung</span><span class="sxs-lookup"><span data-stu-id="0691a-129">Turn on module logging</span></span>

<span data-ttu-id="0691a-130">Mit der Richtlinien Einstellung " **Modul Protokollierung** aktivieren" wird die Protokollierung für ausgewählte PowerShell-Module aktiviert.</span><span class="sxs-lookup"><span data-stu-id="0691a-130">The **Turn on Module Logging** policy setting turns on logging for selected PowerShell modules.</span></span> <span data-ttu-id="0691a-131">Die Einstellung ist in allen Sitzungen auf allen betroffenen Computern wirksam.</span><span class="sxs-lookup"><span data-stu-id="0691a-131">The setting is effective in all sessions on all affected computers.</span></span>

<span data-ttu-id="0691a-132">Wenn Sie diese Richtlinien Einstellung aktivieren und ein oder mehrere Module angeben, werden Pipeline Ausführungs Ereignisse für die angegebenen Module im Windows PowerShell-Protokoll Ereignisanzeige aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="0691a-132">If you enable this policy setting and specify one or more modules, pipeline execution events for the specified modules are recorded in the Windows PowerShell log in Event Viewer.</span></span>

<span data-ttu-id="0691a-133">Wenn Sie diese Richtlinien Einstellung deaktivieren, wird die Protokollierung von Ausführungs Ereignissen für alle PowerShell-Module deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="0691a-133">If you disable this policy setting, logging of execution events is disabled for all PowerShell modules.</span></span>

<span data-ttu-id="0691a-134">Wenn diese Richtlinien Einstellung nicht konfiguriert ist, bestimmt die **logpipelineexecutiondetails** -Eigenschaft jedes Moduls, ob die Ausführungs Ereignisse eines Moduls protokolliert werden.</span><span class="sxs-lookup"><span data-stu-id="0691a-134">If this policy setting is not configured, the **LogPipelineExecutionDetails** property of each module determines whether the execution events of a module are logged.</span></span> <span data-ttu-id="0691a-135">Standardmäßig ist die **logpipelineexecutiondetails** -Eigenschaft aller Module auf false festgelegt.</span><span class="sxs-lookup"><span data-stu-id="0691a-135">By default, the **LogPipelineExecutionDetails** property of all modules is set to False.</span></span>

<span data-ttu-id="0691a-136">Verwenden Sie das folgende Befehls Format, um die Modul Protokollierung für ein Modul zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="0691a-136">To turn on module logging for a module, use the following command format.</span></span> <span data-ttu-id="0691a-137">Das Modul muss in die Sitzung importiert werden, und die Einstellung ist nur in der aktuellen Sitzung gültig.</span><span class="sxs-lookup"><span data-stu-id="0691a-137">The module must be imported into the session and the setting is effective only in the current session.</span></span>

```powershell
Import-Module <Module-Name>
(Get-Module <Module-Name>).LogPipelineExecutionDetails = $true
```

<span data-ttu-id="0691a-138">Fügen Sie zum Aktivieren der Modul Protokollierung für alle Sitzungen auf einem bestimmten Computer die vorherigen Befehle zum PowerShell-Profil "alle Benutzer" ( `$Profile.AllUsersAllHosts` ) hinzu.</span><span class="sxs-lookup"><span data-stu-id="0691a-138">To turn on module logging for all sessions on a particular computer, add the previous commands to the 'All Users' PowerShell profile (`$Profile.AllUsersAllHosts`).</span></span>

<span data-ttu-id="0691a-139">Weitere Informationen zur Modul Protokollierung finden Sie unter [about_Modules](about_Modules.md).</span><span class="sxs-lookup"><span data-stu-id="0691a-139">For more information about module logging, see [about_Modules](about_Modules.md).</span></span>

## <a name="turn-on-powershell-script-block-logging"></a><span data-ttu-id="0691a-140">Aktivieren der PowerShell-Skriptblock Protokollierung</span><span class="sxs-lookup"><span data-stu-id="0691a-140">Turn on PowerShell script block logging</span></span>

<span data-ttu-id="0691a-141">Die Richtlinien Einstellung **PowerShell-Skript Block Protokollierung aktivieren** ermöglicht das Protokollieren aller PowerShell-Skript Eingaben im Ereignisprotokoll Microsoft-Windows-PowerShell/Operational.</span><span class="sxs-lookup"><span data-stu-id="0691a-141">The **Turn on PowerShell Script Block Logging** policy setting enables logging of all PowerShell script input to the Microsoft-Windows-PowerShell/Operational event log.</span></span> <span data-ttu-id="0691a-142">Wenn Sie diese Richtlinien Einstellung aktivieren, protokolliert PowerShell Core die Verarbeitung von Befehlen, Skript Blöcken, Funktionen und Skripts, unabhängig davon, ob Sie interaktiv aufgerufen werden, oder durch Automatisierung.</span><span class="sxs-lookup"><span data-stu-id="0691a-142">If you enable this policy setting, PowerShell Core will log the processing of commands, script blocks, functions, and scripts - whether invoked interactively, or through automation.</span></span>

<span data-ttu-id="0691a-143">Wenn Sie diese Richtlinieneinstellung deaktivieren, ist das Protokollieren von PowerShell-Skript-Eingaben deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="0691a-143">If you disable this policy setting, logging of PowerShell script input is disabled.</span></span> <span data-ttu-id="0691a-144">Wenn Sie die Protokollierung von Skriptblockaufrufen aktivieren, protokolliert PowerShell zusätzlich Protokollereignisse, wenn ein Befehl, ein Skriptblock, eine Funktion oder Skriptstarts oder -stops aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="0691a-144">If you enable the Script Block Invocation Logging, PowerShell additionally logs events when invocation of a command, script block, function, or script starts or stops.</span></span> <span data-ttu-id="0691a-145">Das Aktivieren der Protokollierung von Aufrufen führt zu einer großen Anzahl von Ereignisprotokollen.</span><span class="sxs-lookup"><span data-stu-id="0691a-145">Enabling Invocation Logging generates a high volume of event logs.</span></span>

## <a name="turn-on-script-execution"></a><span data-ttu-id="0691a-146">Skriptausführung aktivieren</span><span class="sxs-lookup"><span data-stu-id="0691a-146">Turn on script execution</span></span>

<span data-ttu-id="0691a-147">Mit der Richtlinien Einstellung **Skriptausführung aktivieren** wird die Ausführungs Richtlinie für Computer und Benutzer festgelegt, die bestimmt, welche Skripts ausgeführt werden dürfen.</span><span class="sxs-lookup"><span data-stu-id="0691a-147">The **Turn on Script Execution** policy setting sets the execution policy for computers and users, which determines which scripts are permitted to run.</span></span>

<span data-ttu-id="0691a-148">Wenn Sie die Richtlinien Einstellung aktivieren, können Sie zwischen den folgenden Richtlinien Einstellungen wählen.</span><span class="sxs-lookup"><span data-stu-id="0691a-148">If you enable the policy setting, you can select from among the following policy settings.</span></span>

- <span data-ttu-id="0691a-149">**Nur signierte Skripts zulassen** : Skripts können nur ausgeführt werden, wenn Sie von einem vertrauenswürdigen Herausgeber signiert wurden.</span><span class="sxs-lookup"><span data-stu-id="0691a-149">**Allow only signed scripts** allows scripts to execute only if they are signed by a trusted publisher.</span></span> <span data-ttu-id="0691a-150">Diese Richtlinien Einstellung entspricht der AllSigned-Ausführungs Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="0691a-150">This policy setting is equivalent to the AllSigned execution policy.</span></span>

- <span data-ttu-id="0691a-151">**Lokale Skripts und Remote signierte Skripts zulassen** ermöglicht das Ausführen aller lokalen Skripts.</span><span class="sxs-lookup"><span data-stu-id="0691a-151">**Allow local scripts and remote signed scripts** allows all local scripts to run.</span></span> <span data-ttu-id="0691a-152">Skripts, die aus dem Internet stammen, müssen von einem vertrauenswürdigen Herausgeber signiert werden.</span><span class="sxs-lookup"><span data-stu-id="0691a-152">Scripts that originate from the Internet must be signed by a trusted publisher.</span></span> <span data-ttu-id="0691a-153">Diese Richtlinien Einstellung entspricht der RemoteSigned-Ausführungs Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="0691a-153">This policy setting is equivalent to the RemoteSigned execution policy.</span></span>

- <span data-ttu-id="0691a-154">**Alle Skripts zulassen** ermöglicht das Ausführen aller Skripts.</span><span class="sxs-lookup"><span data-stu-id="0691a-154">**Allow all scripts** allows all scripts to run.</span></span> <span data-ttu-id="0691a-155">Diese Richtlinien Einstellung entspricht der uneingeschränkten Ausführungs Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="0691a-155">This policy setting is equivalent to the Unrestricted execution policy.</span></span>

<span data-ttu-id="0691a-156">Wenn Sie diese Richtlinien Einstellung deaktivieren, dürfen keine Skripts ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="0691a-156">If you disable this policy setting, no scripts are allowed to run.</span></span> <span data-ttu-id="0691a-157">Diese Richtlinien Einstellung entspricht der eingeschränkten Ausführungs Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="0691a-157">This policy setting is equivalent to the Restricted execution policy.</span></span>

<span data-ttu-id="0691a-158">Wenn Sie diese Richtlinien Einstellung deaktivieren oder nicht konfigurieren, bestimmt die Ausführungs Richtlinie, die vom Cmdlet für den Computer oder Benutzer festgelegt wird, `Set-ExecutionPolicy` ob Skripts ausgeführt werden dürfen.</span><span class="sxs-lookup"><span data-stu-id="0691a-158">If you disable or do not configure this policy setting, the execution policy that is set for the computer or user by the `Set-ExecutionPolicy` cmdlet determines whether scripts are permitted to run.</span></span> <span data-ttu-id="0691a-159">Der Standardwert ist "Restricted".</span><span class="sxs-lookup"><span data-stu-id="0691a-159">The default value is Restricted.</span></span>

<span data-ttu-id="0691a-160">Weitere Informationen finden Sie unter [about_Execution_Policies](about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="0691a-160">For more information, see [about_Execution_Policies](about_Execution_Policies.md).</span></span>

## <a name="turn-on-powershell-transcription"></a><span data-ttu-id="0691a-161">Aktivieren der PowerShell-Aufzeichnung</span><span class="sxs-lookup"><span data-stu-id="0691a-161">Turn on powershell transcription</span></span>

<span data-ttu-id="0691a-162">Mithilfe der Richtlinien Einstellung **PowerShell** -Aufzeichnung aktivieren können Sie die Eingabe und die Ausgabe von PowerShell Core-Befehlen in textbasierte Transkriptionen aufzeichnen.</span><span class="sxs-lookup"><span data-stu-id="0691a-162">The **Turn on PowerShell Transcription** policy setting lets you capture the input and output of PowerShell Core commands into text-based transcripts.</span></span> <span data-ttu-id="0691a-163">Wenn Sie diese Richtlinien Einstellung aktivieren, aktiviert PowerShell Core die Protokollierungs Protokollierung für PowerShell Core und alle anderen Anwendungen, die die PowerShell-Kern-Engine nutzen.</span><span class="sxs-lookup"><span data-stu-id="0691a-163">If you enable this policy setting, PowerShell Core will enable transcription logging for PowerShell Core and any other applications that leverage the PowerShell Core engine.</span></span> <span data-ttu-id="0691a-164">Standardmäßig zeichnet PowerShell Core die Transkriptions Ausgabe im Verzeichnis "eigene Dateien" der einzelnen Benutzer auf, wobei der Dateiname "PowerShell_transcript" sowie der Computername und die Startzeit enthalten.</span><span class="sxs-lookup"><span data-stu-id="0691a-164">By default, PowerShell Core will record transcript output to each users' My Documents directory, with a file name that includes 'PowerShell_transcript', along with the computer name and time started.</span></span>
<span data-ttu-id="0691a-165">Die Aktivierung dieser Richtlinie entspricht dem Aufrufen des Start-Transcript Cmdlets für jede PowerShell-Kern Sitzung.</span><span class="sxs-lookup"><span data-stu-id="0691a-165">Enabling this policy is equivalent to calling the Start-Transcript cmdlet on each PowerShell Core session.</span></span>

<span data-ttu-id="0691a-166">Wenn Sie diese Richtlinien Einstellung deaktivieren, ist die Protokollierungs Protokollierung von PowerShell-basierten Anwendungen standardmäßig deaktiviert, obwohl das transkripting weiterhin über das Cmdlet "Start-Transcript" aktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="0691a-166">If you disable this policy setting, transcription logging of PowerShell-based applications is disabled by default, although transcripting can still be enabled through the Start-Transcript cmdlet.</span></span>

<span data-ttu-id="0691a-167">Wenn Sie die Einstellung OutputDirectory verwenden, um die Protokollierungs Protokollierung an einem freigegebenen Speicherort zu aktivieren, achten Sie darauf, den Zugriff auf dieses Verzeichnis einzuschränken, um zu verhindern, dass Benutzer die Protokolle anderer Benutzer oder Computer anzeigen.</span><span class="sxs-lookup"><span data-stu-id="0691a-167">If you use the OutputDirectory setting to enable transcription logging to a shared location, be sure to limit access to that directory to prevent users from viewing the transcripts of other users or computers.</span></span>

## <a name="set-the-default-source-path-for-update-help"></a><span data-ttu-id="0691a-168">Standard Quellpfad für Update-Help festlegen</span><span class="sxs-lookup"><span data-stu-id="0691a-168">Set the default source path for Update-Help</span></span>

<span data-ttu-id="0691a-169">Die Richtlinien Einstellung **Standard Quellpfad für Update-Hilfe festlegen** legt einen Standardwert für den **SourcePath** -Parameter des `Update-Help` Cmdlets fest.</span><span class="sxs-lookup"><span data-stu-id="0691a-169">The **Set the Default Source Path for Update-Help** policy setting sets a default value for the **SourcePath** parameter of the `Update-Help` cmdlet.</span></span>
<span data-ttu-id="0691a-170">Diese Einstellung verhindert, dass Benutzer das `Update-Help` Cmdlet zum Herunterladen der Hilfedateien aus dem Internet verwenden.</span><span class="sxs-lookup"><span data-stu-id="0691a-170">This setting prevents users from using the `Update-Help` cmdlet to download help files from the Internet.</span></span>

> [!NOTE]
> <span data-ttu-id="0691a-171">Diese Gruppenrichtlinie Einstellung wird unter **Computer Konfiguration** und **Benutzerkonfiguration** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0691a-171">This Group Policy setting appears under **Computer Configuration** and **User Configuration**.</span></span> <span data-ttu-id="0691a-172">Allerdings ist nur die Einstellung Gruppenrichtlinie unter **Computer Konfiguration** wirksam.</span><span class="sxs-lookup"><span data-stu-id="0691a-172">However, only the Group Policy setting under **Computer Configuration** is effective.</span></span> <span data-ttu-id="0691a-173">Die Gruppenrichtlinie Einstellung unter **Benutzerkonfiguration** wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="0691a-173">The Group Policy setting under **User Configuration** is ignored.</span></span>

<span data-ttu-id="0691a-174">Mit dem- `Update-Help` Cmdlet werden die neuesten Hilfedateien für PowerShell-Module heruntergeladen und installiert und auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="0691a-174">The `Update-Help` cmdlet downloads and installs the newest help files for PowerShell modules and installs them on the computer.</span></span> <span data-ttu-id="0691a-175">Standardmäßig `Update-Help` lädt neue Hilfedateien von einem durch das Modul angegebenen Internet Speicherort herunter.</span><span class="sxs-lookup"><span data-stu-id="0691a-175">By default, `Update-Help` downloads new help files from an Internet location specified by the module.</span></span>

<span data-ttu-id="0691a-176">Sie können das `Save-Help` Cmdlet jedoch verwenden, um die neuesten Hilfedateien an einen Dateisystem Speicherort (z. b. eine Netzwerkfreigabe) herunterzuladen. verwenden Sie dann das `Update-Help` Cmdlet, um die Hilfedateien vom Dateisystem Speicherort zu erhalten und auf dem Computer zu installieren.</span><span class="sxs-lookup"><span data-stu-id="0691a-176">However, you can use the `Save-Help` cmdlet to download the newest help files to a file system location, such as a network share, and then use the `Update-Help` cmdlet to get the help files from the file system location and install them on the computer.</span></span> <span data-ttu-id="0691a-177">Der **SourcePath** -Parameter des `Update-Help` Cmdlets gibt den Speicherort des Dateisystems an.</span><span class="sxs-lookup"><span data-stu-id="0691a-177">The **SourcePath** parameter of the `Update-Help` cmdlet specifies the file system location.</span></span>

<span data-ttu-id="0691a-178">Durch die Angabe eines Standardwerts für den **SourcePath** -Parameter fügt diese Gruppenrichtlinie Einstellung allen Befehlen implizit den **SourcePath** -Parameter hinzu `Update-Help` .</span><span class="sxs-lookup"><span data-stu-id="0691a-178">By providing a default value for the **SourcePath** parameter, this Group Policy setting implicitly adds the **SourcePath** parameter to all `Update-Help` commands.</span></span> <span data-ttu-id="0691a-179">Benutzer können den angegebenen Dateisystem Speicherort, der als Standardwert angegeben ist, überschreiben, indem Sie einen anderen Dateisystem Speicherort eingeben.</span><span class="sxs-lookup"><span data-stu-id="0691a-179">Users can override the particular file system location specified as the default value by entering a different file system location.</span></span>
<span data-ttu-id="0691a-180">Der **SourcePath** -Parameter kann jedoch nicht aus dem `Update-Help` Befehl entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="0691a-180">But they cannot remove the **SourcePath** parameter from the `Update-Help` command.</span></span>

<span data-ttu-id="0691a-181">Wenn Sie diese Richtlinien Einstellung aktivieren, können Sie einen Standardwert für den **SourcePath** -Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="0691a-181">If you enable this policy setting, you can specify a default value for the **SourcePath** parameter.</span></span> <span data-ttu-id="0691a-182">Geben Sie einen Dateisystem Speicherort ein.</span><span class="sxs-lookup"><span data-stu-id="0691a-182">Enter a file system location.</span></span>

<span data-ttu-id="0691a-183">Wenn diese Richtlinien Einstellung deaktiviert oder nicht konfiguriert ist, gibt es keinen Standardwert für den **SourcePath** -Parameter des `Update-Help` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="0691a-183">If this policy setting is disabled or not configured, there is no default value for the **SourcePath** parameter of the `Update-Help` cmdlet.</span></span> <span data-ttu-id="0691a-184">Benutzer können die Hilfe aus dem Internet oder von einem beliebigen Dateisystem Speicherort herunterladen.</span><span class="sxs-lookup"><span data-stu-id="0691a-184">Users can download help from the Internet or from any file system location.</span></span>

<span data-ttu-id="0691a-185">Weitere Informationen hierzu finden Sie unter [about_Updatable_Help](about_Updatable_Help.md).</span><span class="sxs-lookup"><span data-stu-id="0691a-185">For more information, see [about_Updatable_Help](about_Updatable_Help.md).</span></span>

## <a name="keywords"></a><span data-ttu-id="0691a-186">Keywords</span><span class="sxs-lookup"><span data-stu-id="0691a-186">Keywords</span></span>

<span data-ttu-id="0691a-187">about_Group_Policies about_GroupPolicy</span><span class="sxs-lookup"><span data-stu-id="0691a-187">about_Group_Policies about_GroupPolicy</span></span>

## <a name="see-also"></a><span data-ttu-id="0691a-188">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="0691a-188">See also</span></span>

[<span data-ttu-id="0691a-189">PowerShell-Kern Richtlinie RFC</span><span class="sxs-lookup"><span data-stu-id="0691a-189">PowerShell Core Policy RFC</span></span>](https://github.com/PowerShell/PowerShell-RFC/blob/master/4-Experimental-Accepted/RFC0041-Policy.md)

[<span data-ttu-id="0691a-190">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="0691a-190">about_Execution_Policies</span></span>](about_Execution_Policies.md)

[<span data-ttu-id="0691a-191">about_Modules</span><span class="sxs-lookup"><span data-stu-id="0691a-191">about_Modules</span></span>](about_Modules.md)

[<span data-ttu-id="0691a-192">about_Updatable_Help</span><span class="sxs-lookup"><span data-stu-id="0691a-192">about_Updatable_Help</span></span>](about_Updatable_Help.md)

[<span data-ttu-id="0691a-193">Get-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="0691a-193">Get-ExecutionPolicy</span></span>](xref:Microsoft.PowerShell.Security.Get-ExecutionPolicy)

[<span data-ttu-id="0691a-194">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="0691a-194">Set-ExecutionPolicy</span></span>](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy)

[<span data-ttu-id="0691a-195">Get-Module</span><span class="sxs-lookup"><span data-stu-id="0691a-195">Get-Module</span></span>](xref:Microsoft.PowerShell.Core.Get-Module)

[<span data-ttu-id="0691a-196">Update-Help</span><span class="sxs-lookup"><span data-stu-id="0691a-196">Update-Help</span></span>](xref:Microsoft.PowerShell.Core.Update-Help)

[<span data-ttu-id="0691a-197">Save-Help</span><span class="sxs-lookup"><span data-stu-id="0691a-197">Save-Help</span></span>](xref:Microsoft.PowerShell.Core.Save-Help)

<!-- link references -->
[gpstore]: https://support.microsoft.com/help/3087759

