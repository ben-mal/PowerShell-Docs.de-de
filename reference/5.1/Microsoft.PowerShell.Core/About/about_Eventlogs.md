---
description: Windows PowerShell erstellt ein Windows-Ereignisprotokoll mit dem Namen "Windows PowerShell", um Windows PowerShell-Ereignisse aufzuzeichnen. Sie können dieses Protokoll in Ereignisanzeige oder mithilfe von Cmdlets anzeigen, die Ereignisse wie das `Get-EventLog` Cmdlet erhalten. Standardmäßig werden Windows PowerShell-Engine-und Anbieter Ereignisse im Ereignisprotokoll aufgezeichnet, aber Sie können die Ereignisprotokoll-Einstellungs Variablen verwenden, um das Ereignisprotokoll anzupassen. Beispielsweise können Sie Ereignisse zu Windows PowerShell-Befehlen hinzufügen.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 11/27/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_eventlogs?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Eventlogs
ms.openlocfilehash: eb92333c6a6e220e287dcbec1441d2d05aa9275b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223508"
---
# <a name="about-eventlogs"></a><span data-ttu-id="7d990-107">Informationen zu Eventlogs</span><span class="sxs-lookup"><span data-stu-id="7d990-107">About Eventlogs</span></span>

## <a name="short-description"></a><span data-ttu-id="7d990-108">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7d990-108">Short Description</span></span>

<span data-ttu-id="7d990-109">Windows PowerShell erstellt ein Windows-Ereignisprotokoll mit dem Namen "Windows PowerShell", um Windows PowerShell-Ereignisse aufzuzeichnen.</span><span class="sxs-lookup"><span data-stu-id="7d990-109">Windows PowerShell creates a Windows event log that is named "Windows PowerShell" to record Windows PowerShell events.</span></span> <span data-ttu-id="7d990-110">Sie können dieses Protokoll in Ereignisanzeige oder mithilfe von Cmdlets anzeigen, die Ereignisse wie das `Get-EventLog` Cmdlet erhalten.</span><span class="sxs-lookup"><span data-stu-id="7d990-110">You can view this log in Event Viewer or by using cmdlets that get events, such as the `Get-EventLog` cmdlet.</span></span> <span data-ttu-id="7d990-111">Standardmäßig werden Windows PowerShell-Engine-und Anbieter Ereignisse im Ereignisprotokoll aufgezeichnet, aber Sie können die Ereignisprotokoll-Einstellungs Variablen verwenden, um das Ereignisprotokoll anzupassen.</span><span class="sxs-lookup"><span data-stu-id="7d990-111">By default, Windows PowerShell engine and provider events are recorded in the event log, but you can use the event log preference variables to customize the event log.</span></span> <span data-ttu-id="7d990-112">Beispielsweise können Sie Ereignisse zu Windows PowerShell-Befehlen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="7d990-112">For example, you can add events about Windows PowerShell commands.</span></span>

## <a name="long-description"></a><span data-ttu-id="7d990-113">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7d990-113">Long Description</span></span>

<span data-ttu-id="7d990-114">Das Windows PowerShell-Ereignisprotokoll zeichnet Details zu Windows PowerShell-Vorgängen auf, z. b. das Starten und Beenden der Programm-Engine und das Starten und Beenden der Windows PowerShell-Anbieter.</span><span class="sxs-lookup"><span data-stu-id="7d990-114">The Windows PowerShell event log records details of Windows PowerShell operations, such as starting and stopping the program engine and starting and stopping the Windows PowerShell providers.</span></span> <span data-ttu-id="7d990-115">Sie können auch Details zu Windows PowerShell-Befehlen protokollieren.</span><span class="sxs-lookup"><span data-stu-id="7d990-115">You can also log details about Windows PowerShell commands.</span></span>

<span data-ttu-id="7d990-116">Das Windows PowerShell-Ereignisprotokoll befindet sich in der Gruppe Anwendungs-und Dienst Protokolle.</span><span class="sxs-lookup"><span data-stu-id="7d990-116">The Windows PowerShell event log is in the Application and Services Logs group.</span></span> <span data-ttu-id="7d990-117">Beim Windows PowerShell-Protokoll handelt es sich um ein klassisches Ereignisprotokoll, in dem die Windows Eventing-Technologie nicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7d990-117">The Windows PowerShell log is a classic event log that does not use the Windows Eventing technology.</span></span> <span data-ttu-id="7d990-118">Um das Protokoll anzuzeigen, verwenden Sie die Cmdlets, die für Klassische Ereignisprotokolle wie entwickelt wurden `Get-EventLog` .</span><span class="sxs-lookup"><span data-stu-id="7d990-118">To view the log, use the cmdlets designed for classic event logs, such as `Get-EventLog`.</span></span>

## <a name="viewing-the-windows-powershell-event-log"></a><span data-ttu-id="7d990-119">Anzeigen des Windows PowerShell-Ereignis Protokolls</span><span class="sxs-lookup"><span data-stu-id="7d990-119">Viewing the Windows PowerShell Event Log</span></span>

<span data-ttu-id="7d990-120">Sie können das Windows PowerShell-Ereignisprotokoll in Ereignisanzeige oder mithilfe der `Get-EventLog` -und- `Get-WmiObject` Cmdlets anzeigen.</span><span class="sxs-lookup"><span data-stu-id="7d990-120">You can view the Windows PowerShell event log in Event Viewer or by using the `Get-EventLog` and `Get-WmiObject` cmdlets.</span></span> <span data-ttu-id="7d990-121">Geben Sie Folgendes ein, um den Inhalt des Windows PowerShell-Protokolls anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="7d990-121">To view the contents of the Windows PowerShell log, type:</span></span>

```powershell
Get-EventLog -LogName "Windows PowerShell"
```

<span data-ttu-id="7d990-122">Verwenden Sie zum Überprüfen der Ereignisse und ihrer Eigenschaften das `Sort-Object` Cmdlet, das `Group-Object` Cmdlet und die Cmdlets, die das `Format` Verb (die `Format` Cmdlets) enthalten.</span><span class="sxs-lookup"><span data-stu-id="7d990-122">To examine the events and their properties, use the `Sort-Object` cmdlet, the `Group-Object` cmdlet, and the cmdlets that contain the `Format` verb (the `Format` cmdlets).</span></span>

<span data-ttu-id="7d990-123">Geben Sie z. b. Folgendes ein, um die Ereignisse im Protokoll nach der Ereignis-ID gruppiert anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="7d990-123">For example, to view the events in the log grouped by the event ID, type:</span></span>

```powershell
Get-EventLog "Windows PowerShell" | Format-Table -GroupBy EventID
```

<span data-ttu-id="7d990-124">Oder geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="7d990-124">Or, type:</span></span>

```powershell
Get-EventLog "Windows PowerShell" |
  Sort-Object EventID |
  Group-Object EventID
```

<span data-ttu-id="7d990-125">Wenn Sie alle klassischen Ereignisprotokolle anzeigen möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="7d990-125">To view all the classic event logs, type:</span></span>

```powershell
Get-EventLog -List
```

<span data-ttu-id="7d990-126">Sie können auch das- `Get-WmiObject` Cmdlet verwenden, um die ereignisbezogenen Windows-Verwaltungsinstrumentation (WMI)-Klassen zu verwenden, um das Ereignisprotokoll zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="7d990-126">You can also use the `Get-WmiObject` cmdlet to use the event-related Windows Management Instrumentation (WMI) classes to examine the event log.</span></span> <span data-ttu-id="7d990-127">Wenn Sie z. b. alle Eigenschaften der Ereignisprotokoll Datei anzeigen möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="7d990-127">For example, to view all the properties of the event log file, type:</span></span>

```powershell
Get-WmiObject Win32_NTEventlogFile |
  where LogFileName -EQ "Windows PowerShell" |
  Format-List -Property *
```

<span data-ttu-id="7d990-128">Geben Sie Folgendes ein, um die WMI-Klassen für Win32-Ereignisse zu finden:</span><span class="sxs-lookup"><span data-stu-id="7d990-128">To find the Win32 event-related WMI classes, type:</span></span>

```powershell
Get-WmiObject -List | where Name -Like "win32*event*"
```

<span data-ttu-id="7d990-129">Wenn Sie weitere Informationen benötigen, geben Sie "Get-Help Get-EventLog" und "Get-Help Get-WmiObject" ein.</span><span class="sxs-lookup"><span data-stu-id="7d990-129">For more information, type "Get-Help Get-EventLog" and "Get-Help Get-WmiObject".</span></span>

## <a name="selecting-events-for-the-windows-powershell-event-log"></a><span data-ttu-id="7d990-130">Auswählen von Ereignissen für das Windows PowerShell-Ereignisprotokoll</span><span class="sxs-lookup"><span data-stu-id="7d990-130">Selecting Events for the Windows PowerShell Event Log</span></span>

<span data-ttu-id="7d990-131">Sie können die Einstellungs Variablen für das Ereignisprotokoll verwenden, um zu bestimmen, welche Ereignisse im Windows PowerShell-Ereignisprotokoll aufgezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="7d990-131">You can use the event log preference variables to determine which events are recorded in the Windows PowerShell event log.</span></span>

<span data-ttu-id="7d990-132">Es gibt sechs Ereignisprotokoll-Einstellungs Variablen: zwei Variablen für jede der drei Protokollierungs Komponenten: die-Engine (das Windows PowerShell-Programm), die-Anbieter und die-Befehle.</span><span class="sxs-lookup"><span data-stu-id="7d990-132">There are six event log preference variables; two variables for each of the three logging components: the engine (the Windows PowerShell program), the providers, and the commands.</span></span> <span data-ttu-id="7d990-133">Die lifecycleevent-Variablen protokollieren normale Start-und Stop-Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="7d990-133">The LifeCycleEvent variables log normal starting and stopping events.</span></span> <span data-ttu-id="7d990-134">Die Integritäts Variablen protokollieren Fehlerereignisse.</span><span class="sxs-lookup"><span data-stu-id="7d990-134">The Health variables log error events.</span></span>

<span data-ttu-id="7d990-135">In der folgenden Tabelle sind die Einstellungs Variablen für das Ereignisprotokoll aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="7d990-135">The following table lists the event log preference variables.</span></span>

|<span data-ttu-id="7d990-136">Variable</span><span class="sxs-lookup"><span data-stu-id="7d990-136">Variable</span></span>                  |<span data-ttu-id="7d990-137">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7d990-137">Description</span></span>                                    |
|--------------------------|-----------------------------------------------|
|<span data-ttu-id="7d990-138">$LogEngineLifeCycleEvent</span><span class="sxs-lookup"><span data-stu-id="7d990-138">$LogEngineLifeCycleEvent</span></span>  |<span data-ttu-id="7d990-139">Protokolliert den Start und das Ende von PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7d990-139">Logs the start and stop of PowerShell</span></span>          |
|<span data-ttu-id="7d990-140">$LogEngineHealthEvent</span><span class="sxs-lookup"><span data-stu-id="7d990-140">$LogEngineHealthEvent</span></span>     |<span data-ttu-id="7d990-141">Protokolliert PowerShell-Programmfehler.</span><span class="sxs-lookup"><span data-stu-id="7d990-141">Logs PowerShell program errors</span></span>                 |
|<span data-ttu-id="7d990-142">$LogProviderLifeCycleEvent</span><span class="sxs-lookup"><span data-stu-id="7d990-142">$LogProviderLifeCycleEvent</span></span>|<span data-ttu-id="7d990-143">Protokolliert den Start und das Ende von PowerShell-Anbietern.</span><span class="sxs-lookup"><span data-stu-id="7d990-143">Logs the start and stop of PowerShell providers</span></span>|
|<span data-ttu-id="7d990-144">$LogProviderHealthEvent</span><span class="sxs-lookup"><span data-stu-id="7d990-144">$LogProviderHealthEvent</span></span>   |<span data-ttu-id="7d990-145">Protokolliert Fehler des PowerShell-Anbieters.</span><span class="sxs-lookup"><span data-stu-id="7d990-145">Logs PowerShell provider errors</span></span>                |
|<span data-ttu-id="7d990-146">$LogCommandLifeCycleEvent</span><span class="sxs-lookup"><span data-stu-id="7d990-146">$LogCommandLifeCycleEvent</span></span> |<span data-ttu-id="7d990-147">Protokolliert den Start und den Abschluss von Befehlen.</span><span class="sxs-lookup"><span data-stu-id="7d990-147">Logs the starting and completion of commands</span></span>   |
|<span data-ttu-id="7d990-148">$LogCommandHealthEvent</span><span class="sxs-lookup"><span data-stu-id="7d990-148">$LogCommandHealthEvent</span></span>    |<span data-ttu-id="7d990-149">Protokolliert Befehls Fehler.</span><span class="sxs-lookup"><span data-stu-id="7d990-149">Logs command errors</span></span>                            |

<span data-ttu-id="7d990-150">(Informationen zu Windows PowerShell-Anbietern finden Sie unter [about_Providers](about_Providers.md).)</span><span class="sxs-lookup"><span data-stu-id="7d990-150">(For information about Windows PowerShell providers, see [about_Providers](about_Providers.md).)</span></span>

<span data-ttu-id="7d990-151">Standardmäßig sind nur die folgenden Ereignis Typen aktiviert:</span><span class="sxs-lookup"><span data-stu-id="7d990-151">By default, only the following event types are enabled:</span></span>

* <span data-ttu-id="7d990-152">$LogEngineLifeCycleEvent</span><span class="sxs-lookup"><span data-stu-id="7d990-152">$LogEngineLifeCycleEvent</span></span>
* <span data-ttu-id="7d990-153">$LogEngineHealthEvent</span><span class="sxs-lookup"><span data-stu-id="7d990-153">$LogEngineHealthEvent</span></span>
* <span data-ttu-id="7d990-154">$LogProviderLifeCycleEvent</span><span class="sxs-lookup"><span data-stu-id="7d990-154">$LogProviderLifeCycleEvent</span></span>
* <span data-ttu-id="7d990-155">$LogProviderHealthEvent</span><span class="sxs-lookup"><span data-stu-id="7d990-155">$LogProviderHealthEvent</span></span>

<span data-ttu-id="7d990-156">Legen Sie zum Aktivieren eines Ereignis Typs die Preference-Variable für diesen Ereignistyp auf $true fest.</span><span class="sxs-lookup"><span data-stu-id="7d990-156">To enable an event type, set the preference variable for that event type to $true.</span></span> <span data-ttu-id="7d990-157">Wenn Sie z. b. Befehls Lebenszyklus-Ereignisse aktivieren möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="7d990-157">For example, to enable command life-cycle events, type:</span></span>

```powershell
$LogCommandLifeCycleEvent
```

<span data-ttu-id="7d990-158">Oder geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="7d990-158">Or, type:</span></span>

```powershell
$LogCommandLifeCycleEvent = $true
```

<span data-ttu-id="7d990-159">Wenn Sie einen Ereignistyp deaktivieren möchten, legen Sie die Preference-Variable für diesen Ereignistyp auf $false fest.</span><span class="sxs-lookup"><span data-stu-id="7d990-159">To disable an event type, set the preference variable for that event type to $false.</span></span> <span data-ttu-id="7d990-160">Geben Sie z. b. Folgendes ein, um die Lebenszyklus Ereignisse von Befehlen zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="7d990-160">For example, to disable command life-cycle events, type:</span></span>

```powershell
$LogProviderLifeCycleEvent = $false
```

<span data-ttu-id="7d990-161">Sie können jedes Ereignis deaktivieren, außer den Ereignissen, die angeben, dass die Windows PowerShell-Engine und die Kern Anbieter gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="7d990-161">You can disable any event, except for the events that indicate that the Windows PowerShell engine and the core providers are started.</span></span> <span data-ttu-id="7d990-162">Diese Ereignisse werden generiert, bevor die Windows PowerShell-profile ausgeführt werden und bevor das Host Programm Befehle annehmen kann.</span><span class="sxs-lookup"><span data-stu-id="7d990-162">These events are generated before the Windows PowerShell profiles are run and before the host program is ready to accept commands.</span></span>

<span data-ttu-id="7d990-163">Die Variablen Einstellungen gelten nur für die aktuelle Windows PowerShell-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="7d990-163">The variable settings apply only for the current Windows PowerShell session.</span></span>
<span data-ttu-id="7d990-164">Wenn Sie Sie auf alle Windows PowerShell-Sitzungen anwenden möchten, fügen Sie Sie Ihrem Windows PowerShell-Profil hinzu.</span><span class="sxs-lookup"><span data-stu-id="7d990-164">To apply them to all Windows PowerShell sessions, add them to your Windows PowerShell profile.</span></span>

## <a name="logging-module-events"></a><span data-ttu-id="7d990-165">Protokollieren von Modul Ereignissen</span><span class="sxs-lookup"><span data-stu-id="7d990-165">Logging Module Events</span></span>

<span data-ttu-id="7d990-166">Ab Windows PowerShell 3,0 können Sie Ausführungs Ereignisse für die Cmdlets und Funktionen in Windows PowerShell-Modulen und-Snap-Ins aufzeichnen, indem Sie die logpipelineexecutiondetails-Eigenschaft von Modulen und Snap-Ins auf "true" festlegen.</span><span class="sxs-lookup"><span data-stu-id="7d990-166">Beginning in Windows PowerShell 3.0, you can record execution events for the cmdlets and functions in Windows PowerShell modules and snap-ins by setting the LogPipelineExecutionDetails property of modules and snap-ins to TRUE.</span></span> <span data-ttu-id="7d990-167">In Windows PowerShell 2,0 ist dieses Feature nur für Snap-Ins verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7d990-167">In Windows PowerShell 2.0, this feature is available only for snap-ins.</span></span>

<span data-ttu-id="7d990-168">Wenn der logpipelineexecutiondetails-Eigenschafts Wert "true ()" lautet `$true` , schreibt Windows PowerShell Cmdlet-und Funktions Ausführungs Ereignisse in der Sitzung in das Windows PowerShell-Protokoll in Ereignisanzeige.</span><span class="sxs-lookup"><span data-stu-id="7d990-168">When the LogPipelineExecutionDetails property value is TRUE (`$true`), Windows PowerShell writes cmdlet and function execution events in the session to the Windows PowerShell log in Event Viewer.</span></span> <span data-ttu-id="7d990-169">Die Einstellung ist nur in der aktuellen Sitzung gültig.</span><span class="sxs-lookup"><span data-stu-id="7d990-169">The setting is effective only in the current session.</span></span>

<span data-ttu-id="7d990-170">Verwenden Sie die folgende Befehlssequenz, um die Protokollierung von Ausführungs Ereignissen von Cmdlets und Funktionen in einem Modul zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="7d990-170">To enable logging of execution events of cmdlets and functions in a module, use the following command sequence.</span></span>

```powershell
Import-Module <ModuleName>
$m = Get-Module <ModuleName>
$m.LogPipelineExecutionDetails = $true
```

<span data-ttu-id="7d990-171">Verwenden Sie die folgende Befehlssequenz, um die Protokollierung von Ausführungs Ereignissen von Cmdlets in einem Snap-in zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="7d990-171">To enable logging of execution events of cmdlets in a snap-in, use the following command sequence.</span></span>

```powershell
$m = Get-PSSnapin <SnapInName> [-Registered]
$m.LogPipelineExecutionDetails = $True
```

<span data-ttu-id="7d990-172">Wenn Sie die Protokollierung deaktivieren möchten, verwenden Sie dieselbe Befehlssequenz, um den Eigenschafts Wert auf false () festzulegen `$false` .</span><span class="sxs-lookup"><span data-stu-id="7d990-172">To disable logging, use the same command sequence to set the property value to FALSE (`$false`).</span></span>

<span data-ttu-id="7d990-173">Sie können auch die Gruppenrichtlinie Einstellung "Modul Protokollierung aktivieren" verwenden, um die Modul-und Snap-in-Protokollierung zu aktivieren und zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="7d990-173">You can also use the "Turn on Module Logging" Group Policy setting to enable and disable module and snap-in logging.</span></span> <span data-ttu-id="7d990-174">Der Richtlinien Wert enthält eine Liste der Namen von Modulen und Snap-Ins.</span><span class="sxs-lookup"><span data-stu-id="7d990-174">The policy value includes a list of module and snap-in names.</span></span> <span data-ttu-id="7d990-175">Platzhalter werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7d990-175">Wildcards are supported.</span></span>

<span data-ttu-id="7d990-176">Wenn "Modul Protokollierung aktivieren" für ein Modul festgelegt ist, ist der Wert der logpipelineexecutiondetails-Eigenschaft des Moduls in allen Sitzungen "true" und kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="7d990-176">When "Turn on Module Logging" is set for a module, the value of the LogPipelineExecutionDetails property of the module is TRUE in all sessions and it cannot be changed.</span></span>

<span data-ttu-id="7d990-177">Die Gruppenrichtlinien Einstellung "Modul Protokollierung aktivieren" befindet sich in den folgenden Gruppenrichtlinie Pfaden:</span><span class="sxs-lookup"><span data-stu-id="7d990-177">The Turn On Module Logging group policy setting is located in the following Group Policy paths:</span></span>

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

<span data-ttu-id="7d990-178">Die Richtlinie für die Benutzerkonfiguration hat Vorrang vor der Computer Konfigurationsrichtlinie, und beide Richtlinien haben Vorrang vor dem Wert der logpipelineexecutiondetails-Eigenschaft von Modulen und Snap-Ins.</span><span class="sxs-lookup"><span data-stu-id="7d990-178">The User Configuration policy takes precedence over the Computer Configuration policy, and both policies take preference over the value of the LogPipelineExecutionDetails property of modules and snap-ins.</span></span>

<span data-ttu-id="7d990-179">Weitere Informationen zu dieser Gruppenrichtlinie Einstellung finden Sie unter [about_Group_Policy_Settings](about_Group_Policy_Settings.md).</span><span class="sxs-lookup"><span data-stu-id="7d990-179">For more information about this Group Policy setting, see [about_Group_Policy_Settings](about_Group_Policy_Settings.md).</span></span>

## <a name="security-and-auditing"></a><span data-ttu-id="7d990-180">Sicherheit und Überwachung</span><span class="sxs-lookup"><span data-stu-id="7d990-180">Security and Auditing</span></span>

<span data-ttu-id="7d990-181">Das Windows PowerShell-Ereignisprotokoll dient zum Angeben von Aktivitäten und zum Bereitstellen von Betriebs Details zur Problembehandlung.</span><span class="sxs-lookup"><span data-stu-id="7d990-181">The Windows PowerShell event log is designed to indicate activity and to provide operational details for troubleshooting.</span></span>

<span data-ttu-id="7d990-182">Wie bei den meisten Windows-basierten Anwendungs Ereignisprotokollen ist das Windows PowerShell-Ereignisprotokoll jedoch nicht als sicher konzipiert.</span><span class="sxs-lookup"><span data-stu-id="7d990-182">However, like most Windows-based application event logs, the Windows PowerShell event log is not designed to be secure.</span></span> <span data-ttu-id="7d990-183">Sie sollte nicht verwendet werden, um die Sicherheit zu überwachen oder vertrauliche oder proprietäre Informationen aufzuzeichnen.</span><span class="sxs-lookup"><span data-stu-id="7d990-183">It should not be used to audit security or to record confidential or proprietary information.</span></span>

<span data-ttu-id="7d990-184">Ereignisprotokolle sind so konzipiert, dass Sie von Benutzern gelesen und verstanden werden können.</span><span class="sxs-lookup"><span data-stu-id="7d990-184">Event logs are designed to be read and understood by users.</span></span> <span data-ttu-id="7d990-185">Benutzer können aus dem Protokoll lesen und in das Protokoll schreiben.</span><span class="sxs-lookup"><span data-stu-id="7d990-185">Users can read from and write to the log.</span></span> <span data-ttu-id="7d990-186">Ein böswilliger Benutzer könnte ein Ereignisprotokoll auf einem lokalen Computer oder einem Remote Computer lesen, falsche Daten aufzeichnen und die Protokollierung ihrer Aktivitäten verhindern.</span><span class="sxs-lookup"><span data-stu-id="7d990-186">A malicious user could read an event log on a local or remote computer, record false data, and then prevent the logging of their activities.</span></span>

## <a name="notes"></a><span data-ttu-id="7d990-187">Notizen</span><span class="sxs-lookup"><span data-stu-id="7d990-187">Notes</span></span>

<span data-ttu-id="7d990-188">Autoren von Modul Autoren können ihren Modulen Protokollierungsfunktionen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="7d990-188">Authors of module authors can add logging features to their modules.</span></span> <span data-ttu-id="7d990-189">Weitere Informationen finden Sie unter [Schreiben eines Windows PowerShell-Moduls](/powershell/scripting/developer/module/writing-a-windows-powershell-module).</span><span class="sxs-lookup"><span data-stu-id="7d990-189">For more information, see [Writing a Windows PowerShell Module](/powershell/scripting/developer/module/writing-a-windows-powershell-module).</span></span>

## <a name="see-also"></a><span data-ttu-id="7d990-190">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7d990-190">See Also</span></span>

[<span data-ttu-id="7d990-191">Get-EventLog</span><span class="sxs-lookup"><span data-stu-id="7d990-191">Get-EventLog</span></span>](xref:Microsoft.PowerShell.Management.Get-EventLog)

[<span data-ttu-id="7d990-192">Get-WmiObject</span><span class="sxs-lookup"><span data-stu-id="7d990-192">Get-WmiObject</span></span>](xref:Microsoft.PowerShell.Management.Get-WmiObject)

[<span data-ttu-id="7d990-193">about_Group_Policy_Settings</span><span class="sxs-lookup"><span data-stu-id="7d990-193">about_Group_Policy_Settings</span></span>](about_Group_Policy_Settings.md)

[<span data-ttu-id="7d990-194">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="7d990-194">about_Preference_Variables</span></span>](about_Preference_Variables.md)
