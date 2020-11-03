---
description: Beschreibt die Gruppenrichtlinie Einstellungen für PowerShell.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 11/28/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_group_policy_settings?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Group_Policy_Settings
ms.openlocfilehash: 1533908be91703efd8509653b30d30de6b7c4a84
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221575"
---
# <a name="about-group-policy-settings"></a><span data-ttu-id="506d0-104">Informationen zu Gruppenrichtlinie Einstellungen</span><span class="sxs-lookup"><span data-stu-id="506d0-104">About Group Policy Settings</span></span>

## <a name="short-description"></a><span data-ttu-id="506d0-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="506d0-105">Short description</span></span>
<span data-ttu-id="506d0-106">Beschreibt die Gruppenrichtlinie Einstellungen für PowerShell.</span><span class="sxs-lookup"><span data-stu-id="506d0-106">Describes the Group Policy settings for PowerShell</span></span>

## <a name="long-description"></a><span data-ttu-id="506d0-107">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="506d0-107">Long description</span></span>

<span data-ttu-id="506d0-108">PowerShell enthält Gruppenrichtlinie Einstellungen, mit deren Hilfe Sie konsistente Konfigurationswerte für Windows-Computer in einer Unternehmensumgebung definieren können.</span><span class="sxs-lookup"><span data-stu-id="506d0-108">PowerShell includes Group Policy settings to help you define consistent configuration values for Windows computers in an enterprise environment.</span></span>

<span data-ttu-id="506d0-109">Die PowerShell-Gruppenrichtlinie Einstellungen befinden sich in den folgenden Gruppenrichtlinie Pfaden:</span><span class="sxs-lookup"><span data-stu-id="506d0-109">The PowerShell Group Policy settings are in the following Group Policy paths:</span></span>

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

<span data-ttu-id="506d0-110">Die Gruppenrichtlinien Einstellungen im Benutzer Konfigurations Pfad haben Vorrang vor den Gruppenrichtlinie Einstellungen im Computer Konfigurations Pfad.</span><span class="sxs-lookup"><span data-stu-id="506d0-110">Group policy settings in the User Configuration path take precedence over Group Policy settings in the Computer Configuration path.</span></span>

<span data-ttu-id="506d0-111">Nachdem Sie die Vorlagen installiert haben, können Sie diese Einstellungen im Gruppenrichtlinie-Editor ( `gpedit.msc` ) bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="506d0-111">After installing the templates, you can edit these settings in the Group Policy editor (`gpedit.msc`).</span></span>

<span data-ttu-id="506d0-112">Die Richtlinien lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="506d0-112">The policies are as follows:</span></span>

- <span data-ttu-id="506d0-113">Modul Protokollierung aktivieren: legt die **logpipelineexecutiondetails** -Eigenschaft von Modulen fest.</span><span class="sxs-lookup"><span data-stu-id="506d0-113">Turn on Module Logging: Sets the **LogPipelineExecutionDetails** property of modules.</span></span>
- <span data-ttu-id="506d0-114">Protokollierung von PowerShell-Skriptblöcken: Aktiviert die ausführliche Protokollierung aller PowerShell-Skripts.</span><span class="sxs-lookup"><span data-stu-id="506d0-114">Turn on PowerShell Script Block Logging: Enables detailed logging of all PowerShell scripts.</span></span>
- <span data-ttu-id="506d0-115">Skriptausführung aktivieren: Legt die PowerShell-Ausführungsrichtlinie fest.</span><span class="sxs-lookup"><span data-stu-id="506d0-115">Turn on Script Execution: Sets the PowerShell execution policy.</span></span>
- <span data-ttu-id="506d0-116">PowerShell-Aufzeichnung aktivieren: ermöglicht die Erfassung der Ein- und Ausgabe von PowerShell-Befehlen in textbasierten Transkripten.</span><span class="sxs-lookup"><span data-stu-id="506d0-116">Turn on PowerShell Transcription: enables capturing of input and output of PowerShell commands into text-based transcripts.</span></span>
- <span data-ttu-id="506d0-117">Legen Sie den Standard Quellpfad für fest `Update-Help` : legt die Quelle für die aktualisierbare Hilfe zu einem Verzeichnis, nicht zum Internet, fest.</span><span class="sxs-lookup"><span data-stu-id="506d0-117">Set the default source path for `Update-Help`: Sets the source for Updatable Help to a directory, not the Internet.</span></span>

<span data-ttu-id="506d0-118">Weitere Informationen zum Abrufen anderer Vorlagen und zum Konfigurieren der Gruppenrichtlinie finden [Sie unter Erstellen und Verwalten des zentralen Speicher für Gruppenrichtlinie administrative Vorlagen in Windows][gpstore].</span><span class="sxs-lookup"><span data-stu-id="506d0-118">For more information about acquiring other templates and configuring Group policy, see [How to create and manage the Central Store for Group Policy Administrative Templates in Windows][gpstore].</span></span>

## <a name="turn-on-module-logging"></a><span data-ttu-id="506d0-119">Aktivieren der Modul Protokollierung</span><span class="sxs-lookup"><span data-stu-id="506d0-119">Turn on module logging</span></span>

<span data-ttu-id="506d0-120">Mit der Richtlinien Einstellung " **Modul Protokollierung** aktivieren" wird die Protokollierung für ausgewählte PowerShell-Module aktiviert.</span><span class="sxs-lookup"><span data-stu-id="506d0-120">The **Turn on Module Logging** policy setting turns on logging for selected PowerShell modules.</span></span> <span data-ttu-id="506d0-121">Die Einstellung ist in allen Sitzungen auf allen betroffenen Computern wirksam.</span><span class="sxs-lookup"><span data-stu-id="506d0-121">The setting is effective in all sessions on all affected computers.</span></span>

<span data-ttu-id="506d0-122">Wenn Sie diese Richtlinien Einstellung aktivieren und ein oder mehrere Module angeben, werden Pipeline Ausführungs Ereignisse für die angegebenen Module im Windows PowerShell-Protokoll Ereignisanzeige aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="506d0-122">If you enable this policy setting and specify one or more modules, pipeline execution events for the specified modules are recorded in the Windows PowerShell log in Event Viewer.</span></span>

<span data-ttu-id="506d0-123">Wenn Sie diese Richtlinien Einstellung deaktivieren, wird die Protokollierung von Ausführungs Ereignissen für alle PowerShell-Module deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="506d0-123">If you disable this policy setting, logging of execution events is disabled for all PowerShell modules.</span></span>

<span data-ttu-id="506d0-124">Wenn diese Richtlinien Einstellung nicht konfiguriert ist, bestimmt die **logpipelineexecutiondetails** -Eigenschaft jedes Moduls, ob die Ausführungs Ereignisse eines Moduls protokolliert werden.</span><span class="sxs-lookup"><span data-stu-id="506d0-124">If this policy setting is not configured, the **LogPipelineExecutionDetails** property of each module determines whether the execution events of a module are logged.</span></span> <span data-ttu-id="506d0-125">Standardmäßig ist die **logpipelineexecutiondetails** -Eigenschaft aller Module auf false festgelegt.</span><span class="sxs-lookup"><span data-stu-id="506d0-125">By default, the **LogPipelineExecutionDetails** property of all modules is set to False.</span></span>

<span data-ttu-id="506d0-126">Verwenden Sie das folgende Befehls Format, um die Modul Protokollierung für ein Modul zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="506d0-126">To turn on module logging for a module, use the following command format.</span></span> <span data-ttu-id="506d0-127">Das Modul muss in die Sitzung importiert werden, und die Einstellung ist nur in der aktuellen Sitzung gültig.</span><span class="sxs-lookup"><span data-stu-id="506d0-127">The module must be imported into the session and the setting is effective only in the current session.</span></span>

```powershell
Import-Module <Module-Name>
(Get-Module <Module-Name>).LogPipelineExecutionDetails = $true
```

<span data-ttu-id="506d0-128">Fügen Sie zum Aktivieren der Modul Protokollierung für alle Sitzungen auf einem bestimmten Computer die vorherigen Befehle zum PowerShell-Profil "alle Benutzer" ( `$Profile.AllUsersAllHosts` ) hinzu.</span><span class="sxs-lookup"><span data-stu-id="506d0-128">To turn on module logging for all sessions on a particular computer, add the previous commands to the 'All Users' PowerShell profile (`$Profile.AllUsersAllHosts`).</span></span>

<span data-ttu-id="506d0-129">Weitere Informationen zur Modul Protokollierung finden Sie unter [about_Modules](about_Modules.md).</span><span class="sxs-lookup"><span data-stu-id="506d0-129">For more information about module logging, see [about_Modules](about_Modules.md).</span></span>

## <a name="turn-on-powershell-script-block-logging"></a><span data-ttu-id="506d0-130">Aktivieren der PowerShell-Skriptblock Protokollierung</span><span class="sxs-lookup"><span data-stu-id="506d0-130">Turn on PowerShell script block logging</span></span>

<span data-ttu-id="506d0-131">Die Richtlinien Einstellung **PowerShell-Skript Block Protokollierung aktivieren** ermöglicht das Protokollieren aller PowerShell-Skript Eingaben im Ereignisprotokoll Microsoft-Windows-PowerShell/Operational.</span><span class="sxs-lookup"><span data-stu-id="506d0-131">The **Turn on PowerShell Script Block Logging** policy setting enables logging of all PowerShell script input to the Microsoft-Windows-PowerShell/Operational event log.</span></span> <span data-ttu-id="506d0-132">Wenn Sie diese Richtlinien Einstellung aktivieren, protokolliert PowerShell Core die Verarbeitung von Befehlen, Skript Blöcken, Funktionen und Skripts, unabhängig davon, ob Sie interaktiv aufgerufen werden, oder durch Automatisierung.</span><span class="sxs-lookup"><span data-stu-id="506d0-132">If you enable this policy setting, PowerShell Core will log the processing of commands, script blocks, functions, and scripts - whether invoked interactively, or through automation.</span></span>

<span data-ttu-id="506d0-133">Wenn Sie diese Richtlinieneinstellung deaktivieren, ist das Protokollieren von PowerShell-Skript-Eingaben deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="506d0-133">If you disable this policy setting, logging of PowerShell script input is disabled.</span></span> <span data-ttu-id="506d0-134">Wenn Sie die Protokollierung von Skriptblockaufrufen aktivieren, protokolliert PowerShell zusätzlich Protokollereignisse, wenn ein Befehl, ein Skriptblock, eine Funktion oder Skriptstarts oder -stops aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="506d0-134">If you enable the Script Block Invocation Logging, PowerShell additionally logs events when invocation of a command, script block, function, or script starts or stops.</span></span> <span data-ttu-id="506d0-135">Das Aktivieren der Protokollierung von Aufrufen führt zu einer großen Anzahl von Ereignisprotokollen.</span><span class="sxs-lookup"><span data-stu-id="506d0-135">Enabling Invocation Logging generates a high volume of event logs.</span></span>

## <a name="turn-on-script-execution"></a><span data-ttu-id="506d0-136">Skriptausführung aktivieren</span><span class="sxs-lookup"><span data-stu-id="506d0-136">Turn on script execution</span></span>

<span data-ttu-id="506d0-137">Mit der Richtlinien Einstellung **Skriptausführung aktivieren** wird die Ausführungs Richtlinie für Computer und Benutzer festgelegt, die bestimmt, welche Skripts ausgeführt werden dürfen.</span><span class="sxs-lookup"><span data-stu-id="506d0-137">The **Turn on Script Execution** policy setting sets the execution policy for computers and users, which determines which scripts are permitted to run.</span></span>

<span data-ttu-id="506d0-138">Wenn Sie die Richtlinien Einstellung aktivieren, können Sie zwischen den folgenden Richtlinien Einstellungen wählen.</span><span class="sxs-lookup"><span data-stu-id="506d0-138">If you enable the policy setting, you can select from among the following policy settings.</span></span>

- <span data-ttu-id="506d0-139">**Nur signierte Skripts zulassen** : Skripts können nur ausgeführt werden, wenn Sie von einem vertrauenswürdigen Herausgeber signiert wurden.</span><span class="sxs-lookup"><span data-stu-id="506d0-139">**Allow only signed scripts** allows scripts to execute only if they are signed by a trusted publisher.</span></span> <span data-ttu-id="506d0-140">Diese Richtlinien Einstellung entspricht der AllSigned-Ausführungs Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="506d0-140">This policy setting is equivalent to the AllSigned execution policy.</span></span>

- <span data-ttu-id="506d0-141">**Lokale Skripts und Remote signierte Skripts zulassen** ermöglicht das Ausführen aller lokalen Skripts.</span><span class="sxs-lookup"><span data-stu-id="506d0-141">**Allow local scripts and remote signed scripts** allows all local scripts to run.</span></span> <span data-ttu-id="506d0-142">Skripts, die aus dem Internet stammen, müssen von einem vertrauenswürdigen Herausgeber signiert werden.</span><span class="sxs-lookup"><span data-stu-id="506d0-142">Scripts that originate from the Internet must be signed by a trusted publisher.</span></span> <span data-ttu-id="506d0-143">Diese Richtlinien Einstellung entspricht der RemoteSigned-Ausführungs Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="506d0-143">This policy setting is equivalent to the RemoteSigned execution policy.</span></span>

- <span data-ttu-id="506d0-144">**Alle Skripts zulassen** ermöglicht das Ausführen aller Skripts.</span><span class="sxs-lookup"><span data-stu-id="506d0-144">**Allow all scripts** allows all scripts to run.</span></span> <span data-ttu-id="506d0-145">Diese Richtlinien Einstellung entspricht der uneingeschränkten Ausführungs Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="506d0-145">This policy setting is equivalent to the Unrestricted execution policy.</span></span>

<span data-ttu-id="506d0-146">Wenn Sie diese Richtlinien Einstellung deaktivieren, dürfen keine Skripts ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="506d0-146">If you disable this policy setting, no scripts are allowed to run.</span></span> <span data-ttu-id="506d0-147">Diese Richtlinien Einstellung entspricht der eingeschränkten Ausführungs Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="506d0-147">This policy setting is equivalent to the Restricted execution policy.</span></span>

<span data-ttu-id="506d0-148">Wenn Sie diese Richtlinien Einstellung deaktivieren oder nicht konfigurieren, bestimmt die Ausführungs Richtlinie, die vom Cmdlet für den Computer oder Benutzer festgelegt wird, `Set-ExecutionPolicy` ob Skripts ausgeführt werden dürfen.</span><span class="sxs-lookup"><span data-stu-id="506d0-148">If you disable or do not configure this policy setting, the execution policy that is set for the computer or user by the `Set-ExecutionPolicy` cmdlet determines whether scripts are permitted to run.</span></span> <span data-ttu-id="506d0-149">Der Standardwert ist "Restricted".</span><span class="sxs-lookup"><span data-stu-id="506d0-149">The default value is Restricted.</span></span>

<span data-ttu-id="506d0-150">Weitere Informationen finden Sie unter [about_Execution_Policies](about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="506d0-150">For more information, see [about_Execution_Policies](about_Execution_Policies.md).</span></span>

## <a name="turn-on-powershell-transcription"></a><span data-ttu-id="506d0-151">Aktivieren der PowerShell-Aufzeichnung</span><span class="sxs-lookup"><span data-stu-id="506d0-151">Turn on powershell transcription</span></span>

<span data-ttu-id="506d0-152">Mithilfe der Richtlinien Einstellung **PowerShell** -Aufzeichnung aktivieren können Sie die Eingabe und die Ausgabe von PowerShell Core-Befehlen in textbasierte Transkriptionen aufzeichnen.</span><span class="sxs-lookup"><span data-stu-id="506d0-152">The **Turn on PowerShell Transcription** policy setting lets you capture the input and output of PowerShell Core commands into text-based transcripts.</span></span> <span data-ttu-id="506d0-153">Wenn Sie diese Richtlinien Einstellung aktivieren, aktiviert PowerShell Core die Protokollierungs Protokollierung für PowerShell Core und alle anderen Anwendungen, die die PowerShell-Kern-Engine nutzen.</span><span class="sxs-lookup"><span data-stu-id="506d0-153">If you enable this policy setting, PowerShell Core will enable transcription logging for PowerShell Core and any other applications that leverage the PowerShell Core engine.</span></span> <span data-ttu-id="506d0-154">Standardmäßig zeichnet PowerShell Core die Transkriptions Ausgabe im Verzeichnis "eigene Dateien" der einzelnen Benutzer auf, wobei der Dateiname "PowerShell_transcript" sowie der Computername und die Startzeit enthalten.</span><span class="sxs-lookup"><span data-stu-id="506d0-154">By default, PowerShell Core will record transcript output to each users' My Documents directory, with a file name that includes 'PowerShell_transcript', along with the computer name and time started.</span></span>
<span data-ttu-id="506d0-155">Die Aktivierung dieser Richtlinie entspricht dem Aufrufen des Start-Transcript Cmdlets für jede PowerShell-Kern Sitzung.</span><span class="sxs-lookup"><span data-stu-id="506d0-155">Enabling this policy is equivalent to calling the Start-Transcript cmdlet on each PowerShell Core session.</span></span>

<span data-ttu-id="506d0-156">Wenn Sie diese Richtlinien Einstellung deaktivieren, ist die Protokollierungs Protokollierung von PowerShell-basierten Anwendungen standardmäßig deaktiviert, obwohl das transkripting weiterhin über das Cmdlet "Start-Transcript" aktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="506d0-156">If you disable this policy setting, transcription logging of PowerShell-based applications is disabled by default, although transcripting can still be enabled through the Start-Transcript cmdlet.</span></span>

<span data-ttu-id="506d0-157">Wenn Sie die Einstellung OutputDirectory verwenden, um die Protokollierungs Protokollierung an einem freigegebenen Speicherort zu aktivieren, achten Sie darauf, den Zugriff auf dieses Verzeichnis einzuschränken, um zu verhindern, dass Benutzer die Protokolle anderer Benutzer oder Computer anzeigen.</span><span class="sxs-lookup"><span data-stu-id="506d0-157">If you use the OutputDirectory setting to enable transcription logging to a shared location, be sure to limit access to that directory to prevent users from viewing the transcripts of other users or computers.</span></span>

## <a name="set-the-default-source-path-for-update-help"></a><span data-ttu-id="506d0-158">Standard Quellpfad für Update-Help festlegen</span><span class="sxs-lookup"><span data-stu-id="506d0-158">Set the default source path for Update-Help</span></span>

<span data-ttu-id="506d0-159">Die Richtlinien Einstellung **Standard Quellpfad für Update-Hilfe festlegen** legt einen Standardwert für den **SourcePath** -Parameter des `Update-Help` Cmdlets fest.</span><span class="sxs-lookup"><span data-stu-id="506d0-159">The **Set the Default Source Path for Update-Help** policy setting sets a default value for the **SourcePath** parameter of the `Update-Help` cmdlet.</span></span>
<span data-ttu-id="506d0-160">Diese Einstellung verhindert, dass Benutzer das `Update-Help` Cmdlet zum Herunterladen der Hilfedateien aus dem Internet verwenden.</span><span class="sxs-lookup"><span data-stu-id="506d0-160">This setting prevents users from using the `Update-Help` cmdlet to download help files from the Internet.</span></span>

> [!NOTE]
> <span data-ttu-id="506d0-161">Diese Gruppenrichtlinie Einstellung wird unter **Computer Konfiguration** und **Benutzerkonfiguration** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="506d0-161">This Group Policy setting appears under **Computer Configuration** and **User Configuration**.</span></span> <span data-ttu-id="506d0-162">Allerdings ist nur die Einstellung Gruppenrichtlinie unter **Computer Konfiguration** wirksam.</span><span class="sxs-lookup"><span data-stu-id="506d0-162">However, only the Group Policy setting under **Computer Configuration** is effective.</span></span> <span data-ttu-id="506d0-163">Die Gruppenrichtlinie Einstellung unter **Benutzerkonfiguration** wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="506d0-163">The Group Policy setting under **User Configuration** is ignored.</span></span>

<span data-ttu-id="506d0-164">Mit dem- `Update-Help` Cmdlet werden die neuesten Hilfedateien für PowerShell-Module heruntergeladen und installiert und auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="506d0-164">The `Update-Help` cmdlet downloads and installs the newest help files for PowerShell modules and installs them on the computer.</span></span> <span data-ttu-id="506d0-165">Standardmäßig `Update-Help` lädt neue Hilfedateien von einem durch das Modul angegebenen Internet Speicherort herunter.</span><span class="sxs-lookup"><span data-stu-id="506d0-165">By default, `Update-Help` downloads new help files from an Internet location specified by the module.</span></span>

<span data-ttu-id="506d0-166">Sie können das `Save-Help` Cmdlet jedoch verwenden, um die neuesten Hilfedateien an einen Dateisystem Speicherort (z. b. eine Netzwerkfreigabe) herunterzuladen. verwenden Sie dann das `Update-Help` Cmdlet, um die Hilfedateien vom Dateisystem Speicherort zu erhalten und auf dem Computer zu installieren.</span><span class="sxs-lookup"><span data-stu-id="506d0-166">However, you can use the `Save-Help` cmdlet to download the newest help files to a file system location, such as a network share, and then use the `Update-Help` cmdlet to get the help files from the file system location and install them on the computer.</span></span> <span data-ttu-id="506d0-167">Der **SourcePath** -Parameter des `Update-Help` Cmdlets gibt den Speicherort des Dateisystems an.</span><span class="sxs-lookup"><span data-stu-id="506d0-167">The **SourcePath** parameter of the `Update-Help` cmdlet specifies the file system location.</span></span>

<span data-ttu-id="506d0-168">Durch die Angabe eines Standardwerts für den **SourcePath** -Parameter fügt diese Gruppenrichtlinie Einstellung allen Befehlen implizit den **SourcePath** -Parameter hinzu `Update-Help` .</span><span class="sxs-lookup"><span data-stu-id="506d0-168">By providing a default value for the **SourcePath** parameter, this Group Policy setting implicitly adds the **SourcePath** parameter to all `Update-Help` commands.</span></span> <span data-ttu-id="506d0-169">Benutzer können den angegebenen Dateisystem Speicherort, der als Standardwert angegeben ist, überschreiben, indem Sie einen anderen Dateisystem Speicherort eingeben.</span><span class="sxs-lookup"><span data-stu-id="506d0-169">Users can override the particular file system location specified as the default value by entering a different file system location.</span></span>
<span data-ttu-id="506d0-170">Der **SourcePath** -Parameter kann jedoch nicht aus dem `Update-Help` Befehl entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="506d0-170">But they cannot remove the **SourcePath** parameter from the `Update-Help` command.</span></span>

<span data-ttu-id="506d0-171">Wenn Sie diese Richtlinien Einstellung aktivieren, können Sie einen Standardwert für den **SourcePath** -Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="506d0-171">If you enable this policy setting, you can specify a default value for the **SourcePath** parameter.</span></span> <span data-ttu-id="506d0-172">Geben Sie einen Dateisystem Speicherort ein.</span><span class="sxs-lookup"><span data-stu-id="506d0-172">Enter a file system location.</span></span>

<span data-ttu-id="506d0-173">Wenn diese Richtlinien Einstellung deaktiviert oder nicht konfiguriert ist, gibt es keinen Standardwert für den **SourcePath** -Parameter des `Update-Help` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="506d0-173">If this policy setting is disabled or not configured, there is no default value for the **SourcePath** parameter of the `Update-Help` cmdlet.</span></span> <span data-ttu-id="506d0-174">Benutzer können die Hilfe aus dem Internet oder von einem beliebigen Dateisystem Speicherort herunterladen.</span><span class="sxs-lookup"><span data-stu-id="506d0-174">Users can download help from the Internet or from any file system location.</span></span>

<span data-ttu-id="506d0-175">Weitere Informationen hierzu finden Sie unter [about_Updatable_Help](about_Updatable_Help.md).</span><span class="sxs-lookup"><span data-stu-id="506d0-175">For more information, see [about_Updatable_Help](about_Updatable_Help.md).</span></span>

## <a name="keywords"></a><span data-ttu-id="506d0-176">Keywords</span><span class="sxs-lookup"><span data-stu-id="506d0-176">Keywords</span></span>

<span data-ttu-id="506d0-177">about_Group_Policies about_GroupPolicy</span><span class="sxs-lookup"><span data-stu-id="506d0-177">about_Group_Policies about_GroupPolicy</span></span>

## <a name="see-also"></a><span data-ttu-id="506d0-178">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="506d0-178">See also</span></span>

[<span data-ttu-id="506d0-179">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="506d0-179">about_Execution_Policies</span></span>](about_Execution_Policies.md)

[<span data-ttu-id="506d0-180">about_Modules</span><span class="sxs-lookup"><span data-stu-id="506d0-180">about_Modules</span></span>](about_Modules.md)

[<span data-ttu-id="506d0-181">about_Updatable_Help</span><span class="sxs-lookup"><span data-stu-id="506d0-181">about_Updatable_Help</span></span>](about_Updatable_Help.md)

[<span data-ttu-id="506d0-182">Get-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="506d0-182">Get-ExecutionPolicy</span></span>](xref:Microsoft.PowerShell.Security.Get-ExecutionPolicy)

[<span data-ttu-id="506d0-183">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="506d0-183">Set-ExecutionPolicy</span></span>](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy)

[<span data-ttu-id="506d0-184">Get-Module</span><span class="sxs-lookup"><span data-stu-id="506d0-184">Get-Module</span></span>](xref:Microsoft.PowerShell.Core.Get-Module)

[<span data-ttu-id="506d0-185">Update-Help</span><span class="sxs-lookup"><span data-stu-id="506d0-185">Update-Help</span></span>](xref:Microsoft.PowerShell.Core.Update-Help)

[<span data-ttu-id="506d0-186">Save-Help</span><span class="sxs-lookup"><span data-stu-id="506d0-186">Save-Help</span></span>](xref:Microsoft.PowerShell.Core.Save-Help)

<!-- link references -->
[gpstore]: https://support.microsoft.com/help/3087759
