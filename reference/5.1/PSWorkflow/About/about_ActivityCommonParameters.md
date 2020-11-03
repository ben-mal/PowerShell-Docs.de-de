---
description: Beschreibt die Parameter, die durch den Windows PowerShell-Workflow zu Aktivitäten hinzugefügt werden.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_activitycommonparameters?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Informationen über_ActivityCommonParameters
ms.openlocfilehash: b745bf17e4ae26156042ecdc25211830177bc692
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221916"
---
# <a name="about-activitycommonparameters"></a><span data-ttu-id="ecf7d-104">Informationen zu activitycommonparameters</span><span class="sxs-lookup"><span data-stu-id="ecf7d-104">About ActivityCommonParameters</span></span>

## <a name="short-description"></a><span data-ttu-id="ecf7d-105">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ecf7d-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="ecf7d-106">Beschreibt die Parameter, die durch den Windows PowerShell-Workflow zu Aktivitäten hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-106">Describes the parameters that Windows PowerShell Workflow adds to activities.</span></span>

## <a name="long-description"></a><span data-ttu-id="ecf7d-107">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ecf7d-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="ecf7d-108">Der Windows PowerShell-Workflow fügt die allgemeinen Aktivitäts Parameter zu Aktivitäten hinzu, die von der psactivity-Basisklasse abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-108">Windows PowerShell Workflow adds the activity common parameters to activities that are derived from the PSActivity base class.</span></span> <span data-ttu-id="ecf7d-109">Diese Kategorie enthält die InlineScript-Aktivität und Windows PowerShell-Cmdlets, die als Aktivitäten implementiert sind, z. b. Get-Process und Get-WinEvent.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-109">This category includes the InlineScript activity and Windows PowerShell cmdlets that are implemented as activities, such as Get-Process and Get-WinEvent.</span></span>

<span data-ttu-id="ecf7d-110">Die allgemeinen Aktivitäts Parameter sind für die Suspend-Workflow-und Checkpoint-Workflow Aktivitäten ungültig und werden nicht zu Cmdlets oder Ausdrücken hinzugefügt, die der Windows PowerShell-Workflow automatisch in einem InlineScript-Skriptblock oder einer ähnlichen Aktivität ausführt.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-110">The activity common parameters are not valid on the Suspend-Workflow and Checkpoint-Workflow activities and they are not added to cmdlets or expressions that Windows PowerShell Workflow automatically runs in an InlineScript script block or similar activity.</span></span> <span data-ttu-id="ecf7d-111">Die allgemeinen Aktivitätsparameter sind für die Aktivität InlineScript verfügbar, nicht aber für die Befehle im Skriptblock InlineScript.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-111">The activity common parameters are available on the InlineScript activity, but not on commands in the InlineScript script block.</span></span>

<span data-ttu-id="ecf7d-112">Einige der allgemeinen Aktivitäts Parameter sind auch allgemeine Workflow Parameter oder allgemeine Windows PowerShell-Parameter.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-112">Several of the activity common parameters are also workflow common parameters or Windows PowerShell common parameters.</span></span> <span data-ttu-id="ecf7d-113">Andere allgemeine Aktivitäts Parameter sind nur für Aktivitäten spezifisch.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-113">Other activity common parameters are unique to activities.</span></span>

<span data-ttu-id="ecf7d-114">Weitere Informationen zu allgemeinen Workflowparametern finden Sie unter about_WorkflowCommonParameters.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-114">For information about the workflow common parameters, see about_WorkflowCommonParameters.</span></span> <span data-ttu-id="ecf7d-115">Informationen zu den allgemeinen Windows PowerShell-Parametern finden Sie unter about_CommonParameters.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-115">For information about the Windows PowerShell common parameters, see about_CommonParameters.</span></span>

### <a name="list-of-activity-common-parameters"></a><span data-ttu-id="ecf7d-116">Liste der allgemeinen Aktivitäts Parameter</span><span class="sxs-lookup"><span data-stu-id="ecf7d-116">LIST OF ACTIVITY COMMON PARAMETERS</span></span>

```
AppendOutput                      PSDebug
Debug                             PSDisableSerialization
DisplayName                       PSDisableSerializationPreference
ErrorAction                       PSError
Input                             PSPersist
MergeErrorToOutput                PSPort
PSActionRetryCount                PSProgress
PSActionRetryIntervalSec          PSProgressMessage
PSActionRunningTimeoutSec         PSRemotingBehavior
PSApplicationName                 PSRequiredModules
PSAuthentication                  PSSessionOption
PSCertificateThumbprint           PSUseSSL
PSComputerName                    PSVerbose
PSConfigurationName               PSWarning
PSConnectionRetryCount            Result
PSConnectionRetryIntervalSec      UseDefaultInput
PSConnectionURI                   Verbose
PSCredential                      WarningAction
```

### <a name="parameter-descriptions"></a><span data-ttu-id="ecf7d-117">Parameter Beschreibungen</span><span class="sxs-lookup"><span data-stu-id="ecf7d-117">PARAMETER DESCRIPTIONS</span></span>

<span data-ttu-id="ecf7d-118">In diesem Abschnitt werden die allgemeinen Aktivitäts Parameter beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-118">This section describes the activity common parameters.</span></span>

#### <a name="appendoutput-boolean"></a><span data-ttu-id="ecf7d-119">Appendoutput \<Boolean\></span><span class="sxs-lookup"><span data-stu-id="ecf7d-119">AppendOutput \<Boolean\></span></span>

<span data-ttu-id="ecf7d-120">Mit dem Wert wird `$True` die Ausgabe der-Aktivität dem Wert der Variablen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-120">A value of `$True` adds the output of the activity to the value of the variable.</span></span>
<span data-ttu-id="ecf7d-121">Der Wert `$False` hat keine Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-121">A value of `$False` has no effect.</span></span> <span data-ttu-id="ecf7d-122">In der Standardeinstellung ersetzt das Zuweisen eines Werts zu einer Variablen den Wert der Variablen.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-122">By default, assigning a value to a variable replaces the variable value.</span></span>

<span data-ttu-id="ecf7d-123">Die folgenden Befehle fügen z. b. dem Dienst Objekt in der Variablen ein Prozess Objekt hinzu `$x` .</span><span class="sxs-lookup"><span data-stu-id="ecf7d-123">For example, the following commands add a process object to the service object in the `$x` variable.</span></span>

```powershell
Workflow Test-Workflow
{
    $x = Get-Service
    $x = Get-Process -AppendOutput $true
}
```

<span data-ttu-id="ecf7d-124">Dieser Parameter ist für XAML-basierte Workflows konzipiert.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-124">This parameter is designed for XAML-based workflows.</span></span> <span data-ttu-id="ecf7d-125">In Skript Workflows können Sie auch den + =-Zuweisungs Operator verwenden, um eine Ausgabe zum Wert einer Variablen hinzuzufügen, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-125">In script workflows, you can also use the += assignment operator to add output to the value of a variable, as shown in the following example.</span></span>

```powershell
Workflow Test-Workflow
{
    $x = Get-Service
    $x += Get-Process
}
```

#### <a name="debug-switchparameter"></a><span data-ttu-id="ecf7d-126">Gen \<SwitchParameter\></span><span class="sxs-lookup"><span data-stu-id="ecf7d-126">Debug \<SwitchParameter\></span></span>

<span data-ttu-id="ecf7d-127">Zeigt Details zur Programmierungs Ebene zu dem vom Befehl ausgeführten Vorgang an.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-127">Displays programmer-level detail about the operation performed by the command.</span></span>
<span data-ttu-id="ecf7d-128">Der Debug-Parameter überschreibt den Wert der $debugPreference-Variablen für den aktuellen Befehl.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-128">The Debug parameter overrides the value of the $DebugPreference variable for the current command.</span></span> <span data-ttu-id="ecf7d-129">Dieser Parameter funktioniert nur, wenn der Befehl Debugmeldungen generiert.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-129">This parameter works only when the command generates debugging messages.</span></span> <span data-ttu-id="ecf7d-130">Bei diesem Parameter handelt es sich auch um einen allgemeinen Windows PowerShell-Parameter.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-130">This parameter is also a Windows PowerShell common parameter.</span></span>

#### <a name="displayname-string"></a><span data-ttu-id="ecf7d-131">Display Name \<String\></span><span class="sxs-lookup"><span data-stu-id="ecf7d-131">DisplayName \<String\></span></span>

<span data-ttu-id="ecf7d-132">Gibt einen Anzeigenamen für die Aktivität an.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-132">Specifies a friendly name for the activity.</span></span> <span data-ttu-id="ecf7d-133">Der DisplayName-Wert wird in der Statusanzeige angezeigt, während der Workflow ausgeführt wird, und im Wert der Progress-Eigenschaft des Workflow Auftrags.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-133">The DisplayName value appears in the progress bar while the workflow runs and in the value of the Progress property of the workflow job.</span></span> <span data-ttu-id="ecf7d-134">Wenn der psprogressmessage-Parameter auch im Befehl enthalten ist, wird der Inhalt der Statusanzeige \<DisplayName\> im \<PSProgressMessage\> Format angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-134">When the PSProgressMessage parameter is also included in the command, the progress bar content appears in \<DisplayName\>:\<PSProgressMessage\> format.</span></span>

#### <a name="erroraction-actionpreference"></a><span data-ttu-id="ecf7d-135">ErrorAction \<ActionPreference\></span><span class="sxs-lookup"><span data-stu-id="ecf7d-135">ErrorAction \<ActionPreference\></span></span>

<span data-ttu-id="ecf7d-136">Bestimmt, wie die Aktivität auf einen Fehler ohne Abbruch vom Befehl antwortet.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-136">Determines how the activity responds to a non-terminating error from the command.</span></span> <span data-ttu-id="ecf7d-137">Dies hat keine Auswirkung auf Abbruch Fehler.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-137">It has no effect on termination errors.</span></span> <span data-ttu-id="ecf7d-138">Dieser Parameter funktioniert nur, wenn der Befehl einen Fehler ohne Abbruch generiert, z. b. die des Write-Error-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-138">This parameter works only when the command generates a non-terminating error, such as those from the Write-Error cmdlet.</span></span> <span data-ttu-id="ecf7d-139">Der ErrorAction-Parameter überschreibt den Wert der $ErrorActionPreference-Variablen für den aktuellen Befehl.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-139">The ErrorAction parameter overrides the value of the $ErrorActionPreference variable for the current command.</span></span> <span data-ttu-id="ecf7d-140">Bei diesem Parameter handelt es sich auch um einen allgemeinen Windows PowerShell-Parameter.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-140">This parameter is also a Windows PowerShell common parameter.</span></span>

<span data-ttu-id="ecf7d-141">Gültige Werte:</span><span class="sxs-lookup"><span data-stu-id="ecf7d-141">Valid values:</span></span>

- <span data-ttu-id="ecf7d-142">Auch.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-142">Continue.</span></span> <span data-ttu-id="ecf7d-143">Zeigt die Fehlermeldung an und setzt die Ausführung des Befehls fort.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-143">Displays the error message and continues executing the command.</span></span> <span data-ttu-id="ecf7d-144">"Continue" ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-144">"Continue" is the default value.</span></span>

- <span data-ttu-id="ecf7d-145">Ignorieren.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-145">Ignore.</span></span> <span data-ttu-id="ecf7d-146">Unterdrückt die Fehlermeldung und setzt die Ausführung des Befehls fort.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-146">Suppresses the error message and continues executing the command.</span></span>
  <span data-ttu-id="ecf7d-147">Anders als SilentlyContinue wird die Fehlermeldung von IGNORE nicht der automatischen $Error-Variablen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-147">Unlike SilentlyContinue, Ignore does not add the error message to the $Error automatic variable.</span></span> <span data-ttu-id="ecf7d-148">Der Wert Ignore wird in Windows PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-148">The Ignore value is introduced in Windows PowerShell 3.0.</span></span>

- <span data-ttu-id="ecf7d-149">Digte.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-149">Inquire.</span></span> <span data-ttu-id="ecf7d-150">Zeigt die Fehlermeldung an und fordert Sie zur Bestätigung auf, bevor die Ausführung fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-150">Displays the error message and prompts you for confirmation before continuing execution.</span></span> <span data-ttu-id="ecf7d-151">Dieser Wert wird nur selten verwendet.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-151">This value is rarely used.</span></span>

- <span data-ttu-id="ecf7d-152">Anhalten.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-152">Suspend.</span></span> <span data-ttu-id="ecf7d-153">Hält einen Workflow Auftrag automatisch an, um weitere Untersuchungen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-153">Automatically suspends a workflow job to allow for further investigation.</span></span> <span data-ttu-id="ecf7d-154">Nach der Untersuchung kann der Workflow fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-154">After investigation, the workflow can be resumed.</span></span>

- <span data-ttu-id="ecf7d-155">SilentlyContinue.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-155">SilentlyContinue.</span></span> <span data-ttu-id="ecf7d-156">Unterdrückt die Fehlermeldung und setzt die Ausführung des Befehls fort.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-156">Suppresses the error message and continues executing the command.</span></span>

- <span data-ttu-id="ecf7d-157">Beenden</span><span class="sxs-lookup"><span data-stu-id="ecf7d-157">Stop.</span></span> <span data-ttu-id="ecf7d-158">Zeigt die Fehlermeldung an und beendet die Ausführung des Befehls.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-158">Displays the error message and stops executing the command.</span></span>

#### <a name="input-object"></a><span data-ttu-id="ecf7d-159">Der \<Object[]\></span><span class="sxs-lookup"><span data-stu-id="ecf7d-159">Input \<Object[]\></span></span>

<span data-ttu-id="ecf7d-160">Übermittelt eine Auflistung von Objekten an eine Aktivität.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-160">Submits a collection of objects to an activity.</span></span> <span data-ttu-id="ecf7d-161">Dies stellt eine Alternative zum einzelnen Weiterleiten von Objekten an die Aktivität dar.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-161">This is an alternative to piping objects to the activity one at a time.</span></span>

#### <a name="mergeerrortooutput-boolean"></a><span data-ttu-id="ecf7d-162">Mergeerrordeoutput \<Boolean\></span><span class="sxs-lookup"><span data-stu-id="ecf7d-162">MergeErrorToOutput \<Boolean\></span></span>

<span data-ttu-id="ecf7d-163">`$True`Der Wert fügt dem Ausgabestream Fehler hinzu.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-163">A value of `$True` adds errors to the output stream.</span></span> <span data-ttu-id="ecf7d-164">Der Wert `$False` hat keine Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-164">A value of `$False` has not effect.</span></span> <span data-ttu-id="ecf7d-165">Verwenden Sie diesen Parameter mit den parallelen `ForEach -Parallel` Schlüsselwörtern und, um Fehler und Ausgaben mehrerer paralleler Befehle in einer einzelnen Auflistung zu erfassen.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-165">Use this parameter with the Parallel and `ForEach -Parallel` keywords to collect errors and output from multiple parallel commands in a single collection.</span></span>

#### <a name="psactionretrycount-int32"></a><span data-ttu-id="ecf7d-166">Psactionretrycount \<Int32\></span><span class="sxs-lookup"><span data-stu-id="ecf7d-166">PSActionRetryCount \<Int32\></span></span>

<span data-ttu-id="ecf7d-167">Versucht wiederholt, die Aktivität auszuführen, wenn der erste Versuch fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-167">Tries repeatedly to run the activity if the first attempt fails.</span></span> <span data-ttu-id="ecf7d-168">Beim Standardwert 0 wird keine Wiederholung durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-168">The default value, 0, does not retry.</span></span>

#### <a name="psactionretryintervalsec-int32"></a><span data-ttu-id="ecf7d-169">Psactionretryintervalsec \<Int32\></span><span class="sxs-lookup"><span data-stu-id="ecf7d-169">PSActionRetryIntervalSec \<Int32\></span></span>

<span data-ttu-id="ecf7d-170">Legt das Intervall zwischen Wiederholungsversuchen der Aktion in Sekunden fest.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-170">Determines the interval between action retries in seconds.</span></span> <span data-ttu-id="ecf7d-171">Beim Standardwert 0 wird die Aktion sofort wiederholt.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-171">The default value, 0, retries the action immediately.</span></span> <span data-ttu-id="ecf7d-172">Dieser Parameter ist nur gültig, wenn der psactionretrycount-Parameter auch im Befehl verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-172">This parameter is valid only when the PSActionRetryCount parameter is also used in the command.</span></span>

#### <a name="psactionrunningtimeoutsec-int32"></a><span data-ttu-id="ecf7d-173">Psactionrunningtimeoutsec \<Int32\></span><span class="sxs-lookup"><span data-stu-id="ecf7d-173">PSActionRunningTimeoutSec \<Int32\></span></span>

<span data-ttu-id="ecf7d-174">Legt fest, wie lange die Aktivität auf jedem Zielcomputer ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-174">Determines how long the activity can run on each target computer.</span></span> <span data-ttu-id="ecf7d-175">Wenn die Aktivität vor Ablauf des Timeouts nicht beendet wird, generiert der Windows PowerShell-Workflow einen Fehler mit Abbruch und beendet die Verarbeitung des Workflows auf dem betroffenen Zielcomputer.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-175">If the activity does not complete before the timeout expires, Windows PowerShell Workflow generates a terminating error and stops processing the workflow on the affected target computer.</span></span>

#### <a name="psallowredirection-boolean"></a><span data-ttu-id="ecf7d-176">Psallowredirection \<Boolean\></span><span class="sxs-lookup"><span data-stu-id="ecf7d-176">PSAllowRedirection \<Boolean\></span></span>

<span data-ttu-id="ecf7d-177">Der Wert $true ermöglicht die Umleitung der Verbindung zu den Ziel Computern.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-177">A value of $True allows redirection of the connection to the target computers.</span></span>
<span data-ttu-id="ecf7d-178">Der Wert $false hat keine Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-178">A value of $False has no effect.</span></span> <span data-ttu-id="ecf7d-179">Dieser allgemeine Aktivitäts Parameter ist auch ein allgemeiner Workflow Parameter.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-179">This activity common parameter is also a workflow common parameter.</span></span>

<span data-ttu-id="ecf7d-180">Wenn Sie den psconnectionuri-Parameter verwenden, kann das Remote Ziel eine Anweisung zum Umleiten an einen anderen URI zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-180">When you use the PSConnectionURI parameter, the remote destination can return an instruction to redirect to a different URI.</span></span> <span data-ttu-id="ecf7d-181">Standardmäßig umleitet Windows PowerShell Verbindungen nicht, Sie können jedoch den Parameter "psallowredirection" mit dem Wert "$true" verwenden, um die Umleitung der Verbindung zum Zielcomputer zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-181">By default, Windows PowerShell does not redirect connections, but you can use the PSAllowRedirection parameter with a value of $True to allow redirection of the connection to the target computer.</span></span>

<span data-ttu-id="ecf7d-182">Sie können auch einschränken, wie oft die Verbindung umgeleitet wird, indem Sie die maximumconnectionredirectioncount-Eigenschaft der `$PSSessionOption` Preference-Variablen festlegen oder die maximumconnectionredirectioncount-Eigenschaft des Werts des ssessionoption-Parameters von Cmdlets, die eine Sitzung erstellen.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-182">You can also limit the number of times that the connection is redirected by setting the MaximumConnectionRedirectionCount property of the `$PSSessionOption` preference variable, or the MaximumConnectionRedirectionCount property of the value of the SSessionOption parameter of cmdlets that create a session.</span></span> <span data-ttu-id="ecf7d-183">Der Standardwert ist 5.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-183">The default value is 5.</span></span>

#### <a name="psapplicationname-string"></a><span data-ttu-id="ecf7d-184">Psapplicationname \<String\></span><span class="sxs-lookup"><span data-stu-id="ecf7d-184">PSApplicationName \<String\></span></span>

<span data-ttu-id="ecf7d-185">Gibt das Anwendungs namens Segment des Verbindungs-URI an, der zum Herstellen der Verbindung mit den Ziel Computern verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-185">Specifies the application name segment of the connection URI that is used to connect to the target computers.</span></span> <span data-ttu-id="ecf7d-186">Verwenden Sie diesen Parameter, um den Anwendungsnamen anzugeben, wenn Sie nicht den ConnectionURI-Parameter im Befehl verwenden.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-186">Use this parameter to specify the application name when you are not using the ConnectionURI parameter in the command.</span></span> <span data-ttu-id="ecf7d-187">Dieser allgemeine Aktivitäts Parameter ist auch ein allgemeiner Workflow Parameter.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-187">This activity common parameter is also a workflow common parameter.</span></span>

<span data-ttu-id="ecf7d-188">Der Standardwert ist der Wert der Einstellungs `$PSSessionApplicationName` Variablen auf dem Zielcomputer.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-188">The default value is the value of the `$PSSessionApplicationName` preference variable on the target computer.</span></span> <span data-ttu-id="ecf7d-189">Wenn diese Einstellungsvariable nicht definiert ist, ist der Standardwert „WSMan“.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-189">If this preference variable is not defined, the default value is WSMAN.</span></span> <span data-ttu-id="ecf7d-190">Dieser Wert ist für die meisten Verwendungsarten geeignet.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-190">This value is appropriate for most uses.</span></span> <span data-ttu-id="ecf7d-191">Weitere Informationen finden Sie unter [about_Preference_Variables](../../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="ecf7d-191">For more information, see [about_Preference_Variables](../../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="ecf7d-192">Der WinRM-Dienst wählt mit dem Anwendungsnamen einen Listener für die Verbindungsanforderung aus.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-192">The WinRM service uses the application name to select a listener to service the connection request.</span></span> <span data-ttu-id="ecf7d-193">Der Wert dieses Parameters sollte mit dem Wert der URLPrefix-Eigenschaft eines Listeners auf dem Remotecomputer übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-193">The value of this parameter should match the value of the URLPrefix property of a listener on the remote computer.</span></span>

#### <a name="psauthentication-authenticationmechanism"></a><span data-ttu-id="ecf7d-194">Psauthentication \<AuthenticationMechanism\></span><span class="sxs-lookup"><span data-stu-id="ecf7d-194">PSAuthentication \<AuthenticationMechanism\></span></span>

<span data-ttu-id="ecf7d-195">Gibt den Mechanismus an, der zum Authentifizieren der Anmelde Informationen des Benutzers beim Herstellen einer Verbindung mit den Ziel Computern verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-195">Specifies the mechanism that is used to authenticate the user's credentials when connecting to the target computers.</span></span> <span data-ttu-id="ecf7d-196">Zu den gültigen Werten gehören Default, Basic, Credssp, Digest, Kerberos, Negotiate und NegotiateWithImplicitCredential.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-196">Valid values are Default, Basic, Credssp, Digest, Kerberos, Negotiate, and NegotiateWithImplicitCredential.</span></span> <span data-ttu-id="ecf7d-197">Der Standardwert ist Default.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-197">The default value is Default.</span></span> <span data-ttu-id="ecf7d-198">Dieser allgemeine Aktivitäts Parameter ist auch ein allgemeiner Workflow Parameter.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-198">This activity common parameter is also a workflow common parameter.</span></span>

<span data-ttu-id="ecf7d-199">Informationen zu den Werten dieses Parameters finden Sie unter der Beschreibung der **System.Management.Automation.Runspaces.AuthenticationMechanism** -Enumeration in MSDN.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-199">For information about the values of this parameter, see the description of the **System.Management.Automation.Runspaces.AuthenticationMechanism** enumeration in MSDN.</span></span>

> [!WARNING]
> <span data-ttu-id="ecf7d-200">Die Credential Security Support Provider (CredSSP)-Authentifizierung, in der die Anmeldeinformationen des Benutzers zur Authentifizierung an einen Remotecomputer übergeben werden, ist für Befehle gedacht, die Authentifizierung bei mehr als einer Ressource erfordern, z. B. beim Zugriff auf eine Remote-Netzwerkfreigabe.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-200">Credential Security Service Provider (CredSSP) authentication, in which the user's credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="ecf7d-201">Dieser Mechanismus erhöht das Sicherheitsrisiko des Remotevorgangs.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-201">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="ecf7d-202">Wenn die Sicherheit des Remotecomputers gefährdet ist, können die an ihn übergebenen Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-202">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

#### <a name="pscertificatethumbprint-string"></a><span data-ttu-id="ecf7d-203">Pscertifipethumbprint \<String\></span><span class="sxs-lookup"><span data-stu-id="ecf7d-203">PSCertificateThumbprint \<String\></span></span>

<span data-ttu-id="ecf7d-204">Gibt das digitale Zertifikat für öffentliche Schlüssel (X509) eines Benutzerkontos an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-204">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span> <span data-ttu-id="ecf7d-205">Geben Sie den Zertifikatfingerabdruck des Zertifikats ein.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-205">Enter the certificate thumbprint of the certificate.</span></span> <span data-ttu-id="ecf7d-206">Dieser allgemeine Aktivitäts Parameter ist auch ein allgemeiner Workflow Parameter.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-206">This activity common parameter is also a workflow common parameter.</span></span>

<span data-ttu-id="ecf7d-207">Zertifikate werden bei der clientzertifikatbasierten Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-207">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="ecf7d-208">Sie können nur lokalen Benutzerkonten zugeordnet werden und funktionieren nicht mit Domänenkonten.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-208">They can only be mapped to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="ecf7d-209">Um ein Zertifikat abzurufen, verwenden Sie die Cmdlets " [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item) " oder " [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem) " im Windows PowerShell-Laufwerk "CERT:".</span><span class="sxs-lookup"><span data-stu-id="ecf7d-209">To get a certificate, use the [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item) or [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem) cmdlets in the Windows PowerShell Cert: drive.</span></span>

#### <a name="pscomputername-string"></a><span data-ttu-id="ecf7d-210">PSComputerName \<String[]\></span><span class="sxs-lookup"><span data-stu-id="ecf7d-210">PSComputerName \<String[]\></span></span>

<span data-ttu-id="ecf7d-211">Gibt die Zielcomputer an, auf denen die Aktivität ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-211">Specifies the target computers on which the activity run.</span></span> <span data-ttu-id="ecf7d-212">Die Standardeinstellung ist der lokale Computer.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-212">The default is the local computer.</span></span> <span data-ttu-id="ecf7d-213">Dieser allgemeine Aktivitäts Parameter ist auch ein allgemeiner Workflow Parameter.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-213">This activity common parameter is also a workflow common parameter.</span></span>

<span data-ttu-id="ecf7d-214">Geben Sie den NetBIOS-Namen, die IP-Adresse oder den vollqualifizierten Domänennamen von mindestens einem Computer in eine durch Kommas getrennte Liste ein.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-214">Type the NETBIOS name, IP address, or fully-qualified domain name of one or more computers in a comma-separated list.</span></span> <span data-ttu-id="ecf7d-215">Um den lokalen Computer anzugeben, geben Sie den Computernamen, „localhost“ oder einen Punkt (.) ein.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-215">To specify the local computer, type the computer name, "localhost", or a dot (.).</span></span>

<span data-ttu-id="ecf7d-216">Um den lokalen Computer in den Wert des pscomputername-Parameters einzuschließen, öffnen Sie Windows PowerShell mit der Option "als Administrator ausführen".</span><span class="sxs-lookup"><span data-stu-id="ecf7d-216">To include the local computer in the value of the PSComputerName parameter, open Windows PowerShell with the "Run as administrator" option.</span></span>

<span data-ttu-id="ecf7d-217">Wenn dieser Parameter im Befehl weggelassen wird, oder wenn der Wert $NULL oder eine leere Zeichenfolge ist, ist das Workflow Ziel der lokale Computer, und Windows PowerShell-Remoting wird nicht verwendet, um den Befehl auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-217">If this parameter is omitted from the command, or it value is $null or an empty string, the workflow target is the local computer and Windows PowerShell remoting is not used to run the command.</span></span>

<span data-ttu-id="ecf7d-218">Um eine IP-Adresse im Wert des Computername-Parameters zu verwenden, muss der Befehl den PSCredential-Parameter enthalten.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-218">To use an IP address in the value of the ComputerName parameter, the command must include the PSCredential parameter.</span></span> <span data-ttu-id="ecf7d-219">Außerdem muss der Computer für den HTTPS-Transport konfiguriert sein, oder die IP-Adresse des Remotecomputers muss in der WinRM TrustedHosts-Liste auf dem lokalen Computer enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-219">Also, the computer must be configured for HTTPS transport or the IP address of the remote computer must be included in the WinRM TrustedHosts list on the local computer.</span></span> <span data-ttu-id="ecf7d-220">Anweisungen zum Hinzufügen eines Computer namens zur Liste "Treuhänder Hosts" finden Sie unter "Vorgehensweise beim Hinzufügen eines Computers zur Liste vertrauenswürdiger Hosts" in [about_Remote_Troubleshooting](../../Microsoft.PowerShell.Core/About/about_Remote_Troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="ecf7d-220">For instructions for adding a computer name to the TrustedHosts list, see "How to Add a Computer to the Trusted Host List" in [about_Remote_Troubleshooting](../../Microsoft.PowerShell.Core/About/about_Remote_Troubleshooting.md).</span></span>

#### <a name="psconfigurationname-string"></a><span data-ttu-id="ecf7d-221">PSConfigurationName \<String\></span><span class="sxs-lookup"><span data-stu-id="ecf7d-221">PSConfigurationName \<String\></span></span>

<span data-ttu-id="ecf7d-222">Gibt die Sitzungs Konfigurationen an, die zum Erstellen von Sitzungen auf den Ziel Computern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-222">Specifies the session configurations that are used to create sessions on the target computers.</span></span> <span data-ttu-id="ecf7d-223">Geben Sie den Namen einer Sitzungs Konfiguration auf den Ziel Computern ein (nicht auf dem Computer, auf dem der Workflow ausgeführt wird).</span><span class="sxs-lookup"><span data-stu-id="ecf7d-223">Enter the name of a session configuration on the target computers (not on the computer that is running the workflow.</span></span> <span data-ttu-id="ecf7d-224">Der Standardwert ist Microsoft. PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-224">The default is Microsoft.PowerShell.</span></span> <span data-ttu-id="ecf7d-225">Dieser allgemeine Aktivitäts Parameter ist auch ein allgemeiner Workflow Parameter.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-225">This activity common parameter is also a workflow common parameter.</span></span>

#### <a name="psconnectionretrycount-uint"></a><span data-ttu-id="ecf7d-226">PSConnectionRetryCount \<UInt\></span><span class="sxs-lookup"><span data-stu-id="ecf7d-226">PSConnectionRetryCount \<UInt\></span></span>

<span data-ttu-id="ecf7d-227">Gibt die maximale Anzahl von versuchen an, eine Verbindung mit den einzelnen Ziel Computern herzustellen, wenn beim ersten Verbindungsversuch ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-227">Specifies the maximum number of attempts to connect to each target computer if the first connection attempt fails.</span></span> <span data-ttu-id="ecf7d-228">Geben Sie eine Zahl zwischen 1 und 4.294.967.295 (uint. MaxValue) ein.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-228">Enter a number between 1 and 4,294,967,295 (UInt.MaxValue).</span></span> <span data-ttu-id="ecf7d-229">Der Standardwert 0 (null) stellt keine Wiederholungs Versuche dar.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-229">The default value, zero (0), represents no retry attempts.</span></span>
<span data-ttu-id="ecf7d-230">Dieser allgemeine Aktivitäts Parameter ist auch ein allgemeiner Workflow Parameter.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-230">This activity common parameter is also a workflow common parameter.</span></span>

#### <a name="psconnectionretryintervalsec-uint"></a><span data-ttu-id="ecf7d-231">Psconnectionretryintervalsec \<UInt\></span><span class="sxs-lookup"><span data-stu-id="ecf7d-231">PSConnectionRetryIntervalSec \<UInt\></span></span>

<span data-ttu-id="ecf7d-232">Gibt die Verzögerung zwischen Verbindungs Wiederholungs versuchen in Sekunden an.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-232">Specifies the delay between connection retry attempts in seconds.</span></span> <span data-ttu-id="ecf7d-233">Der Standardwert ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="ecf7d-233">The default value is zero (0).</span></span> <span data-ttu-id="ecf7d-234">Dieser Parameter ist nur gültig, wenn der Wert von psconnectionretrycount mindestens 1 ist.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-234">This parameter is valid only when the value of PSConnectionRetryCount is at least 1.</span></span> <span data-ttu-id="ecf7d-235">Dieser allgemeine Aktivitäts Parameter ist auch ein allgemeiner Workflow Parameter.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-235">This activity common parameter is also a workflow common parameter.</span></span>

#### <a name="psconnectionuri-systemuri"></a><span data-ttu-id="ecf7d-236">Psconnectionuri \<System.Uri\></span><span class="sxs-lookup"><span data-stu-id="ecf7d-236">PSConnectionURI \<System.Uri\></span></span>

<span data-ttu-id="ecf7d-237">Gibt einen Uniform Resource Identifier (URI) an, der den Verbindungs Endpunkt für die Aktivität auf dem Bereitstellungs Zielcomputer definiert.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-237">Specifies a Uniform Resource Identifier (URI) that defines the connection endpoint for the activity on the target computer.</span></span> <span data-ttu-id="ecf7d-238">Der URI muss vollqualifiziert sein.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-238">The URI must be fully qualified.</span></span> <span data-ttu-id="ecf7d-239">Dieser allgemeine Aktivitäts Parameter ist auch ein allgemeiner Workflow Parameter.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-239">This activity common parameter is also a workflow common parameter.</span></span>

<span data-ttu-id="ecf7d-240">Das Format dieser Zeichenfolge lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ecf7d-240">The format of this string is as follows:</span></span>

```
<Transport>://<ComputerName>:<Port>/<ApplicationName>
```

<span data-ttu-id="ecf7d-241">Der Standardwert ist `http://localhost:5985/WSMAN`.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-241">The default value is `http://localhost:5985/WSMAN`.</span></span>

<span data-ttu-id="ecf7d-242">Wenn Sie keinen psconnectionuri angeben, können Sie die Parameter psusessl, pscomputername, psport und psapplicationname verwenden, um die psconnectionuri-Werte anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-242">If you do not specify a PSConnectionURI, you can use the PSUseSSL, PSComputerName, PSPort, and PSApplicationName parameters to specify the PSConnectionURI values.</span></span>

<span data-ttu-id="ecf7d-243">Gültige Werte für das Transport-Segment des URI sind „HTTP“ und „HTTPS“.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-243">Valid values for the Transport segment of the URI are HTTP and HTTPS.</span></span> <span data-ttu-id="ecf7d-244">Wenn Sie einen Verbindungs-URI mit einem Transport Segment angeben, aber keinen Port angeben, wird die Sitzung mit Standardports erstellt: 80 für http und 443 für HTTPS.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-244">If you specify a connection URI with a Transport segment, but do not specify a port, the session is created with standards ports: 80 for HTTP and 443 for HTTPS.</span></span> <span data-ttu-id="ecf7d-245">Um die Standardports für Windows PowerShell-Remoting zu verwenden, geben Sie Port 5985 für HTTP bzw. 5986 für HTTPS an.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-245">To use the default ports for Windows PowerShell remoting, specify port 5985 for HTTP or 5986 for HTTPS.</span></span>

#### <a name="pscredential-pscredential"></a><span data-ttu-id="ecf7d-246">PSCredential \<PSCredential\></span><span class="sxs-lookup"><span data-stu-id="ecf7d-246">PSCredential \<PSCredential\></span></span>

<span data-ttu-id="ecf7d-247">Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen der Aktivität auf dem Zielcomputer verfügt.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-247">Specifies a user account that has permission to run the activity on the target computer.</span></span> <span data-ttu-id="ecf7d-248">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-248">The default is the current user.</span></span> <span data-ttu-id="ecf7d-249">Dieser Parameter ist nur gültig, wenn der pscomputername-Parameter im Befehl enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-249">This parameter is valid only when the PSComputerName parameter is included in the command.</span></span> <span data-ttu-id="ecf7d-250">Dieser allgemeine Aktivitäts Parameter ist auch ein allgemeiner Workflow Parameter.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-250">This activity common parameter is also a workflow common parameter.</span></span>

<span data-ttu-id="ecf7d-251">Geben Sie einen Benutzernamen ein, z. b. "USER01" oder "Domain01\User01", oder geben Sie eine Variable ein, die ein PSCredential-Objekt enthält, wie z. b. das Get-Credential Cmdlet zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-251">Type a user name, such as "User01" or "Domain01\User01", or enter a variable that contains a PSCredential object, such as one that the Get-Credential cmdlet returns.</span></span> <span data-ttu-id="ecf7d-252">Wenn Sie nur einen Benutzernamen eingeben, werden Sie zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-252">If you enter only a user name, you will be prompted for a password.</span></span>

#### <a name="psdebug-psdatacollectiondebugrecord"></a><span data-ttu-id="ecf7d-253">PSDebug \<PSDataCollection[DebugRecord]\></span><span class="sxs-lookup"><span data-stu-id="ecf7d-253">PSDebug \<PSDataCollection[DebugRecord]\></span></span>

<span data-ttu-id="ecf7d-254">Fügt Debugmeldungen aus der Aktivität der angegebenen Auflistung von debugdatensätzen hinzu, anstatt die Debugmeldungen in die Konsole oder den Wert der Debug-Eigenschaft des Workflow Auftrags zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-254">Adds debug messages from the activity to the specified debug record collection, instead of writing the debug messages to the console or to the value of the Debug property of the workflow job.</span></span> <span data-ttu-id="ecf7d-255">Sie können Debugmeldungen aus mehreren Aktivitäten demselben Auflistungsobjekt mit Debugdatensätzen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-255">You can add debug messages from multiple activities to the same debug record collection object.</span></span>

<span data-ttu-id="ecf7d-256">Um diesen allgemeinen Aktivitäts Parameter zu verwenden, verwenden Sie das Cmdlet "New-Object", um ein psdatacollection-Objekt mit dem Typ "debugrecord" zu erstellen und das Objekt in einer Variablen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-256">To use this activity common parameter, use the New-Object cmdlet to create a PSDataCollection object with a type of DebugRecord and save the object in a variable.</span></span> <span data-ttu-id="ecf7d-257">Verwenden Sie dann die Variable als Wert des Parameters PSDebug einer oder mehrerer Aktivitäten, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-257">Then, use the variable as the value of the PSDebug parameter of one or more activities, as shown in the following example.</span></span>

```powershell
Workflow Test-Workflow
{
    $debugCollection = New-Object -Type `
    System.Management.Automation.PSDataCollection[System.Management.Automation.DebugRecord]
    InlineScript {\Server01\Share01\Get-AssetData.ps1} -PSDebug $debugCollection -Debug $True
    InlineScript {\Server01\Share01\Set-AssetData.ps1} -PSDebug $debugCollection -Debug $True
    if ($debugCollection -like "Missing") { ...}
}
```

#### <a name="psdisableserialization-boolean"></a><span data-ttu-id="ecf7d-258">Psdisableserialization \<Boolean\></span><span class="sxs-lookup"><span data-stu-id="ecf7d-258">PSDisableSerialization \<Boolean\></span></span>

<span data-ttu-id="ecf7d-259">Weist die Aktivität an, „Live“-Objekte (nicht serialisierte Objekte) an den Workflow zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-259">Directs the activity to return "live" (not serialized) objects to the workflow.</span></span>
<span data-ttu-id="ecf7d-260">Die resultierenden Objekte besitzen Methoden und Eigenschaften, aber sie können nicht gespeichert werden, wenn ein Prüfpunkt angenommen wird.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-260">The resulting objects have methods, as well as properties, but they cannot be saved when a checkpoint is taken.</span></span>

#### <a name="psdisableserializationpreference-boolean"></a><span data-ttu-id="ecf7d-261">PSDisableSerializationPreference \<Boolean\></span><span class="sxs-lookup"><span data-stu-id="ecf7d-261">PSDisableSerializationPreference \<Boolean\></span></span>

<span data-ttu-id="ecf7d-262">Wendet die Entsprechung des psdisableserialization-Parameters auf den gesamten Workflow an, nicht nur auf die-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-262">Applies the equivalent of the PSDisableSerialization parameter to the entire workflow, not just the activity.</span></span> <span data-ttu-id="ecf7d-263">Das Hinzufügen dieses Parameters wird in der Regel nicht empfohlen, da ein Workflow, der seine Objekte nicht serialisiert, nicht fortgesetzt oder beibehalten werden kann.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-263">Adding this parameter is generally not recommended, because a workflow that doesn't serialize its objects cannot be resumed or persisted.</span></span>

<span data-ttu-id="ecf7d-264">Gültige Werte:</span><span class="sxs-lookup"><span data-stu-id="ecf7d-264">Valid values:</span></span>

- <span data-ttu-id="ecf7d-265">Vorgegebene Wenn der Parameter nicht angegeben wird und Sie den psdisableserialization-Parameter nicht zu einer Aktivität hinzugefügt haben, werden Objekte serialisiert.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-265">(Default) If omitted, and you have also not added the PSDisableSerialization parameter to an activity, objects are serialized.</span></span>

- <span data-ttu-id="ecf7d-266">`$True`.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-266">`$True`.</span></span> <span data-ttu-id="ecf7d-267">Leitet alle Aktivitäten in einem Workflow an, (nicht serialisierte) „Live“-Objekte zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-267">Directs all activities within a workflow to return "live" (not serialized) objects.</span></span> <span data-ttu-id="ecf7d-268">Die resultierenden Objekte besitzen Methoden und Eigenschaften, aber sie können nicht gespeichert werden, wenn ein Prüfpunkt angenommen wird.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-268">The resulting objects have methods, as well as properties, but they cannot be saved when a checkpoint is taken.</span></span>
- <span data-ttu-id="ecf7d-269">`$False`.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-269">`$False`.</span></span> <span data-ttu-id="ecf7d-270">Workflow-Objekte werden serialisiert.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-270">Workflow objects are serialized.</span></span>

#### <a name="pserror-psdatacollectionerrorrecord"></a><span data-ttu-id="ecf7d-271">Pserror \<PSDataCollection[ErrorRecord]\></span><span class="sxs-lookup"><span data-stu-id="ecf7d-271">PSError \<PSDataCollection[ErrorRecord]\></span></span>

<span data-ttu-id="ecf7d-272">Fügt der angegebenen Auflistung von Fehler Datensätzen Fehlermeldungen aus der-Aktivität hinzu, statt die Fehlermeldungen in die Konsole oder den Wert der Error-Eigenschaft des Workflow Auftrags zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-272">Adds error messages from the activity to the specified error record collection, instead of writing the error messages to the console or to the value of the Error property of the workflow job.</span></span> <span data-ttu-id="ecf7d-273">Sie können Fehlermeldungen aus mehreren Aktivitäten demselben Auflistungsobjekt mit Fehlerdatensätzen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-273">You can add error messages from multiple activities to the same error record collection object.</span></span>

<span data-ttu-id="ecf7d-274">Um diesen allgemeinen Aktivitäts Parameter zu verwenden, verwenden `New-Object` Sie das Cmdlet, um ein psdatacollection-Objekt mit dem Typ ErrorRecord zu erstellen und das Objekt in einer Variablen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-274">To use this activity common parameter, use the `New-Object` cmdlet to create a PSDataCollection object with a type of ErrorRecord and save the object in a variable.</span></span> <span data-ttu-id="ecf7d-275">Verwenden Sie dann die Variable als Wert des Parameters pserror einer oder mehrerer Aktivitäten, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-275">Then, use the variable as the value of the PSError parameter of one or more activities, as shown in the following example.</span></span>

```powershell
Workflow Test-Workflow
{
   $typeName = "System.Management.Automation.PSDataCollection"
   $typeName += '[System.Management.Automation.ErrorRecord]'
   $ec = New-Object $typeName
   InlineScript {\Server01\Share01\Get-AssetData.ps1} -PSError $ec
   InlineScript {\Server01\Share01\Set-AssetData.ps1} -PSError $ec
   if ($ec.Count -gt 2)
   {
      # Do Some Work.
   }
}
```

#### <a name="pspersist-boolean"></a><span data-ttu-id="ecf7d-276">PSPersist \<Boolean\></span><span class="sxs-lookup"><span data-stu-id="ecf7d-276">PSPersist \<Boolean\></span></span>

<span data-ttu-id="ecf7d-277">Nimmt einen Prüfpunkt nach der-Aktivität an.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-277">Takes a checkpoint after the activity.</span></span> <span data-ttu-id="ecf7d-278">Dieser Prüfpunkt gilt zusätzlich zu allen Prüfpunkten, die im Workflow angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-278">This checkpoint is in addition to any checkpoints that are specified in the workflow.</span></span> <span data-ttu-id="ecf7d-279">Dieser allgemeine Aktivitäts Parameter ist auch ein allgemeiner Workflow Parameter.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-279">This activity common parameter is also a workflow common parameter.</span></span>

<span data-ttu-id="ecf7d-280">Ein "Prüfpunkt" oder "Persistenzpunkt" ist eine Momentaufnahme des Workflow Status und der Daten, die erfasst werden, während der Workflow ausgeführt wird und in einem persistenten Speicher auf dem Datenträger gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-280">A "checkpoint" or "persistence point" is a snapshot of the workflow state and data that is captured while the workflow runs and is saved to a persistence store on disk.</span></span> <span data-ttu-id="ecf7d-281">Der Windows PowerShell-Workflow verwendet die gespeicherten Daten, um einen angehaltenen oder unterbrochenen Workflow vom letzten Persistenzpunkt wieder aufzunehmen, anstatt den Workflow neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-281">Windows PowerShell Workflow uses the saved data to resume a suspended or interrupted workflow from the last persistence point, rather than to restart the workflow.</span></span>

<span data-ttu-id="ecf7d-282">Gültige Werte:</span><span class="sxs-lookup"><span data-stu-id="ecf7d-282">Valid values:</span></span>

- <span data-ttu-id="ecf7d-283">Vorgegebene Wenn Sie diesen Parameter weglassen, werden keine Prüfpunkte hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-283">(Default) If you omit this parameter, no checkpoints are added.</span></span> <span data-ttu-id="ecf7d-284">Prüfpunkte werden basierend auf den Einstellungen für den Workflow übernommen.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-284">Checkpoints are taken based on the settings for the workflow.</span></span>

- <span data-ttu-id="ecf7d-285">`$True`.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-285">`$True`.</span></span> <span data-ttu-id="ecf7d-286">Zeichnet einen Prüfpunkt auf, nachdem die Aktivität abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-286">Takes a checkpoint after the activity completes.</span></span>
  <span data-ttu-id="ecf7d-287">Dieser Prüfpunkt gilt zusätzlich zu allen Prüfpunkten, die im Workflow angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-287">This checkpoint is in addition to any checkpoints that are specified in the workflow.</span></span>

- <span data-ttu-id="ecf7d-288">`$False`.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-288">`$False`.</span></span> <span data-ttu-id="ecf7d-289">Es werden keine Prüfpunkte hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-289">No checkpoints are added.</span></span> <span data-ttu-id="ecf7d-290">Prüfpunkte werden nur dann übernommen, wenn Sie im Workflow angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-290">Checkpoints are taken only when specified in the workflow.</span></span>

#### <a name="psport-int32"></a><span data-ttu-id="ecf7d-291">Psport \<Int32\></span><span class="sxs-lookup"><span data-stu-id="ecf7d-291">PSPort \<Int32\></span></span>

<span data-ttu-id="ecf7d-292">Gibt den Netzwerkport auf den Ziel Computern an.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-292">Specifies the network port on the target computers.</span></span> <span data-ttu-id="ecf7d-293">Die Standardports sind 5985 (der WinRM-Port für HTTP) und 5986 (der WinRM-Port für HTTPS).</span><span class="sxs-lookup"><span data-stu-id="ecf7d-293">The default ports are 5985 (the WinRM port for HTTP) and 5986 (the WinRM port for HTTPS).</span></span> <span data-ttu-id="ecf7d-294">Dieser allgemeine Aktivitäts Parameter ist auch ein allgemeiner Workflow Parameter.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-294">This activity common parameter is also a workflow common parameter.</span></span>

<span data-ttu-id="ecf7d-295">Verwenden Sie den psport-Parameter nur, wenn dies erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-295">Do not use the PSPort parameter unless you must.</span></span> <span data-ttu-id="ecf7d-296">Der im Befehl festgelegte Port gilt für alle Computer oder Sitzungen, für die der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-296">The port set in the command applies to all computers or sessions on which the command runs.</span></span> <span data-ttu-id="ecf7d-297">Eine alternative Porteinstellung kann verhindern, dass der Befehl auf allen Computern ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-297">An alternate port setting might prevent the command from running on all computers.</span></span> <span data-ttu-id="ecf7d-298">Bevor ein alternativer Port verwendet werden kann, müssen Sie den WinRM-Listener auf dem Remotecomputer für das Abhören an diesen Port konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-298">Before using an alternate port, you must configure the WinRM listener on the remote computer to listen at that port.</span></span>

#### <a name="psprogress-psdatacollectionprogressrecord"></a><span data-ttu-id="ecf7d-299">Psprogress \<PSDataCollection[ProgressRecord]\></span><span class="sxs-lookup"><span data-stu-id="ecf7d-299">PSProgress \<PSDataCollection[ProgressRecord]\></span></span>

<span data-ttu-id="ecf7d-300">Fügt der angegebenen Auflistung von Statusdaten Sätzen Statusmeldungen aus der Aktivität hinzu, anstatt die Statusmeldungen in die Konsole oder den Wert der Status-Eigenschaft des Workflow Auftrags zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-300">Adds progress messages from the activity to the specified progress record collection, instead of writing the progress messages to the console or to the value of the Progress property of the workflow job.</span></span> <span data-ttu-id="ecf7d-301">Sie können Statusmeldungen aus mehreren Aktivitäten demselben Auflistungsobjekt mit Statusdatensätzen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-301">You can add progress messages from multiple activities to the same progress record collection object.</span></span>

#### <a name="psprogressmessage-string"></a><span data-ttu-id="ecf7d-302">Psprogressmessage \<String\></span><span class="sxs-lookup"><span data-stu-id="ecf7d-302">PSProgressMessage \<String\></span></span>

<span data-ttu-id="ecf7d-303">Gibt eine Beschreibung der Aktivität an.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-303">Specifies a friendly description of the activity.</span></span> <span data-ttu-id="ecf7d-304">Der Wert psprogressmessage wird in der Statusanzeige angezeigt, während der Workflow ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-304">The PSProgressMessage value appears in the progress bar while the workflow runs.</span></span> <span data-ttu-id="ecf7d-305">Wenn Display Name auch im Befehl enthalten ist, wird der Inhalt der Statusanzeige im Format angezeigt \<DisplayName\> \<PSProgressMessage\> .</span><span class="sxs-lookup"><span data-stu-id="ecf7d-305">When the DisplayName is also included in the command, the progress bar content appears in \<DisplayName\>:\<PSProgressMessage\> format.</span></span>

<span data-ttu-id="ecf7d-306">Dieser Parameter ist besonders nützlich zum Identifizieren von Aktivitäten in einem Foreach-parallel-Skriptblock.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-306">This parameter is particularly useful for identifying activities in a ForEach -Parallel script block.</span></span> <span data-ttu-id="ecf7d-307">Ohne diese Nachricht werden Aktivitäten in allen parallelen Teilstrukturen mit demselben Namen identifiziert.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-307">Without this message, activities in all parallel branches are identified by the same name.</span></span>

#### <a name="psremotingbehavior-remotingbehavior"></a><span data-ttu-id="ecf7d-308">Psremotingbehavior \<RemotingBehavior\></span><span class="sxs-lookup"><span data-stu-id="ecf7d-308">PSRemotingBehavior \<RemotingBehavior\></span></span>

<span data-ttu-id="ecf7d-309">Gibt an, wie das Remoting verwaltet wird, wenn die Aktivität auf Zielcomputern ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-309">Specifies how remoting is managed when the activity is run on target computers.</span></span>
<span data-ttu-id="ecf7d-310">PowerShell ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-310">PowerShell is the default.</span></span>

<span data-ttu-id="ecf7d-311">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="ecf7d-311">Valid values are:</span></span>

- <span data-ttu-id="ecf7d-312">Keine: die Aktivität wird nicht auf Remote Computern ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-312">None: The activity is not run on remote computers.</span></span>

- <span data-ttu-id="ecf7d-313">PowerShell: Windows PowerShell-Remoting wird zum Ausführen der Aktivität auf Ziel Computern verwendet.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-313">PowerShell: Windows PowerShell remoting is used to run the activity on target computers.</span></span>

- <span data-ttu-id="ecf7d-314">Custom: die-Aktivität unterstützt den eigenen Remoting-Typ.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-314">Custom: The activity supports its own type of remoting.</span></span> <span data-ttu-id="ecf7d-315">Dieser Wert ist gültig, wenn das Cmdlet, das als Aktivität implementiert wird, den Wert des remotingcapability-Attributs auf supportedbycommand festlegt und der Befehl den Computername-Parameter enthält.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-315">This value is valid when the cmdlet that is being implemented as an activity sets the value of the RemotingCapability attribute to SupportedByCommand and the command includes the ComputerName parameter.</span></span>

#### <a name="psrequiredmodules-string"></a><span data-ttu-id="ecf7d-316">PSRequiredModules \<String[]\></span><span class="sxs-lookup"><span data-stu-id="ecf7d-316">PSRequiredModules \<String[]\></span></span>

<span data-ttu-id="ecf7d-317">Importiert die angegebenen Module vor dem Ausführen des Befehls.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-317">Imports the specified modules before running the command.</span></span> <span data-ttu-id="ecf7d-318">Geben Sie die Modulnamen ein.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-318">Enter the module names.</span></span> <span data-ttu-id="ecf7d-319">Die Module müssen auf dem Bereitstellungs Zielcomputer installiert sein.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-319">The modules must be installed on the target computer.</span></span>

<span data-ttu-id="ecf7d-320">Module, die in einem in der psmodulepath-Umgebungsvariablen angegebenen Pfad installiert werden, werden automatisch bei der ersten Verwendung eines beliebigen Befehls im Modul importiert.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-320">Modules that are installed in a path specified in the PSModulePath environment variable are automatically imported on first use of any command in the module.</span></span>
<span data-ttu-id="ecf7d-321">Verwenden Sie diesen Parameter, um Module zu importieren, die sich nicht an einem psmodulepath-Speicherort befinden.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-321">Use this parameter to import modules that are not in a PSModulePath location.</span></span>

<span data-ttu-id="ecf7d-322">Da jede Aktivität in einem Workflow in einer eigenen Sitzung ausgeführt wird, importiert ein Import-Module-Befehl nur ein Modul in der Sitzung, in der er ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-322">Because each activity in a workflow runs in its own session, an Import-Module command imports a module only into the session in which it runs.</span></span> <span data-ttu-id="ecf7d-323">Er importiert das Modul nicht in Sitzungen, in denen andere Aktivitäten ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-323">It does not import the module into sessions in which other activities run.</span></span>

#### <a name="pssessionoption-pssessionoption"></a><span data-ttu-id="ecf7d-324">PSSessionOption \<PSSessionOption\></span><span class="sxs-lookup"><span data-stu-id="ecf7d-324">PSSessionOption \<PSSessionOption\></span></span>

<span data-ttu-id="ecf7d-325">Legt Erweiterte Optionen für die Sitzungen auf den Ziel Computern fest.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-325">Sets advanced options for the sessions to the target computers.</span></span> <span data-ttu-id="ecf7d-326">Geben Sie ein pssessionoption-Objekt ein, z. b. ein Objekt, das Sie mit dem Cmdlet "New-PSSessionOption" erstellen.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-326">Enter a PSSessionOption object, such as one that you create by using the New-PSSessionOption cmdlet.</span></span> <span data-ttu-id="ecf7d-327">Dieser allgemeine Aktivitäts Parameter ist auch ein allgemeiner Workflow Parameter.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-327">This activity common parameter is also a workflow common parameter.</span></span>

<span data-ttu-id="ecf7d-328">Die Standardwerte für die Sitzungs Optionen werden durch den Wert der Einstellungs `$PSSessionOption` Variablen bestimmt, sofern festgelegt.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-328">The default values for the session options are determined by the value of the `$PSSessionOption` preference variable, if it is set.</span></span> <span data-ttu-id="ecf7d-329">Andernfalls verwendet die Sitzung die Werte, die in der Sitzungs Konfiguration angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-329">Otherwise, the session uses the values specified in the session configuration.</span></span>

<span data-ttu-id="ecf7d-330">Eine Beschreibung der Sitzungs Optionen, einschließlich der Standardwerte, finden Sie im Hilfethema für das New-PSSessionOption Cmdlet " [New-pssessionoption](xref:Microsoft.PowerShell.Core.New-PSSessionOption)".</span><span class="sxs-lookup"><span data-stu-id="ecf7d-330">For a description of the session options, including the default values, see the help topic for the New-PSSessionOption cmdlet [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).</span></span>

<span data-ttu-id="ecf7d-331">Weitere Informationen zur $PSSessionOption Preference-Variablen finden Sie unter [about_Preference_Variables](../../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="ecf7d-331">For more information about the $PSSessionOption preference variable, see [about_Preference_Variables](../../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

#### <a name="psusessl-boolean"></a><span data-ttu-id="ecf7d-332">Psusessl \<Boolean\></span><span class="sxs-lookup"><span data-stu-id="ecf7d-332">PSUseSSL \<Boolean\></span></span>

<span data-ttu-id="ecf7d-333">Der Wert $true verwendet das Secure Sockets Layer (SSL)-Protokoll, um eine Verbindung mit dem Zielcomputer herzustellen.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-333">A value of $True uses the Secure Sockets Layer (SSL) protocol to establish a connection to the target computer.</span></span> <span data-ttu-id="ecf7d-334">Standardmäßig wird SSL nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-334">By default, SSL is not used.</span></span> <span data-ttu-id="ecf7d-335">Der Wert $false hat keine Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-335">A value of $False has no effect.</span></span> <span data-ttu-id="ecf7d-336">Dieser allgemeine Aktivitäts Parameter ist auch ein allgemeiner Workflow Parameter.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-336">This activity common parameter is also a workflow common parameter.</span></span>

<span data-ttu-id="ecf7d-337">WS-Management verschlüsselt alle Windows PowerShell-Inhalte, die über das Netzwerk übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-337">WS-Management encrypts all Windows PowerShell content transmitted over the network.</span></span> <span data-ttu-id="ecf7d-338">UseSSL bietet zusätzlichen Schutz, indem die Daten über HTTPS, anstelle von HTTP gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-338">UseSSL is an additional protection that sends the data across an HTTPS, instead of HTTP.</span></span> <span data-ttu-id="ecf7d-339">Wenn Sie diesen Parameter verwenden, aber SSL auf dem Port für den Befehl nicht verfügbar ist, tritt ein Fehler beim Befehl auf.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-339">If you use this parameter, but SSL is not available on the port used for the command, the command fails.</span></span>

#### <a name="psverbose-psdatacollectionverboserecord"></a><span data-ttu-id="ecf7d-340">Psverbose \<PSDataCollection[VerboseRecord]\></span><span class="sxs-lookup"><span data-stu-id="ecf7d-340">PSVerbose \<PSDataCollection[VerboseRecord]\></span></span>

<span data-ttu-id="ecf7d-341">Fügt der angegebenen ausführlichen Daten Satz Auflistung ausführliche Meldungen aus der-Aktivität hinzu, anstatt die ausführlichen Meldungen in die Konsole oder den Wert der ausführliche-Eigenschaft des Workflow Auftrags zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-341">Adds verbose messages from the activity to the specified verbose record collection, instead of writing the verbose messages to the console or to the value of the Verbose property of the workflow job.</span></span> <span data-ttu-id="ecf7d-342">Sie können ausführliche Meldungen aus mehreren Aktivitäten demselben Auflistungsobjekt mit ausführlichen Datensätzen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-342">You can add verbose messages from multiple activities to the same verbose record collection object.</span></span>

#### <a name="pswarning-psdatacollectionwarningrecord"></a><span data-ttu-id="ecf7d-343">Pswarning \<PSDataCollection[WarningRecord]\></span><span class="sxs-lookup"><span data-stu-id="ecf7d-343">PSWarning \<PSDataCollection[WarningRecord]\></span></span>

<span data-ttu-id="ecf7d-344">Fügt der angegebenen Auflistung von Warnungs Datensätzen Warnmeldungen aus der-Aktivität hinzu, anstatt die Warnmeldungen in die Konsole oder den Wert der Warning-Eigenschaft des Workflow Auftrags zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-344">Adds warning messages from the activity to the specified warning record collection, instead of writing the warning messages to the console or to the value of the Warning property of the workflow job.</span></span> <span data-ttu-id="ecf7d-345">Sie können Warnungen aus mehreren Aktivitäten demselben Auflistungsobjekt mit Warnungsdatensätzen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-345">You can add warning messages from multiple activities to the same warning record collection object.</span></span>

#### <a name="result"></a><span data-ttu-id="ecf7d-346">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="ecf7d-346">Result</span></span>

<span data-ttu-id="ecf7d-347">Dieser Parameter ist nur in XAML-Workflows gültig.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-347">This parameter is valid only in XAML workflows.</span></span>

#### <a name="usedefaultinput-boolean"></a><span data-ttu-id="ecf7d-348">Allgemeine usedefaultinput \<Boolean\></span><span class="sxs-lookup"><span data-stu-id="ecf7d-348">UseDefaultInput \<Boolean\></span></span>

<span data-ttu-id="ecf7d-349">Akzeptiert alle Workfloweingaben als Eingabe für die Aktivität nach Wert.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-349">Accepts all workflow input as input to the activity by value.</span></span>

<span data-ttu-id="ecf7d-350">Beispielsweise verwendet die Get-Process-Aktivität im folgenden Beispielworkflow den allgemeine UseDefaultInput-Aktivitätsparameter als Eingabe, die an den Workflow übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-350">For example, the Get-Process activity in the following sample workflow uses the UseDefaultInput activity common parameter to get input that is passed to the workflow.</span></span> <span data-ttu-id="ecf7d-351">Beim Ausführen des Workflows mit der Eingabe wird die Eingabe von der Aktivität verwendet.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-351">When you run the workflow with input, that input is used by the activity.</span></span>

```powershell
workflow Test-Workflow
{
    Get-Service -UseDefaultInput $True
}

PS C:> Test-Workflow -InputObject WinRm
```

```output
Status   Name        DisplayName                            PSComputerName
------   ----        -----------                            --------------
Running  winrm       Windows Remote Management (WS-Manag... localhost
```

#### <a name="verbose-switchparameter"></a><span data-ttu-id="ecf7d-352">Ausführliche \<SwitchParameter\></span><span class="sxs-lookup"><span data-stu-id="ecf7d-352">Verbose \<SwitchParameter\></span></span>

<span data-ttu-id="ecf7d-353">Zeigt ausführliche Informationen zu dem vom Befehl ausgeführten Vorgang an.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-353">Displays detailed information about the operation performed by the command.</span></span>
<span data-ttu-id="ecf7d-354">Diese Informationen ähneln den Informationen in einer Ablauf Verfolgung oder einem Transaktionsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-354">This information resembles the information in a trace or in a transaction log.</span></span>
<span data-ttu-id="ecf7d-355">Der Verbose-Parameter überschreibt den Wert der $VerbosePreference-Variablen für den aktuellen Befehl.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-355">The Verbose parameter overrides the value of the $VerbosePreference variable for the current command.</span></span> <span data-ttu-id="ecf7d-356">Dieser Parameter funktioniert nur, wenn der Befehl eine ausführliche Nachricht generiert.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-356">This parameter works only when the command generates a verbose message.</span></span> <span data-ttu-id="ecf7d-357">Bei diesem Parameter handelt es sich auch um einen allgemeinen Windows PowerShell-Parameter.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-357">This parameter is also a Windows PowerShell common parameter.</span></span>

#### <a name="warningaction-actionpreference"></a><span data-ttu-id="ecf7d-358">Allgemeinen WarningAction \<ActionPreference\></span><span class="sxs-lookup"><span data-stu-id="ecf7d-358">WarningAction \<ActionPreference\></span></span>

<span data-ttu-id="ecf7d-359">Bestimmt, wie die Aktivität auf eine Warnung antwortet.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-359">Determines how the activity responds to a warning.</span></span> <span data-ttu-id="ecf7d-360">"Continue" ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-360">"Continue" is the default value.</span></span> <span data-ttu-id="ecf7d-361">Der WarningAction-Parameter überschreibt den Wert der $WarningPreference-Variablen für den aktuellen Befehl.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-361">The WarningAction parameter overrides the value of the $WarningPreference variable for the current command.</span></span> <span data-ttu-id="ecf7d-362">Dieser Parameter funktioniert nur, wenn der Befehl eine Warnmeldung generiert.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-362">This parameter works only when the command generates a warning message.</span></span> <span data-ttu-id="ecf7d-363">Bei diesem Parameter handelt es sich auch um einen allgemeinen Windows PowerShell-Parameter.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-363">This parameter is also a Windows PowerShell common parameter.</span></span>

<span data-ttu-id="ecf7d-364">Gültige Werte:</span><span class="sxs-lookup"><span data-stu-id="ecf7d-364">Valid Values:</span></span>

- <span data-ttu-id="ecf7d-365">SilentlyContinue.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-365">SilentlyContinue.</span></span> <span data-ttu-id="ecf7d-366">Unterdrückt die Warnmeldung und setzt die Ausführung des Befehls fort.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-366">Suppresses the warning message and continues executing the command.</span></span>

- <span data-ttu-id="ecf7d-367">Auch.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-367">Continue.</span></span> <span data-ttu-id="ecf7d-368">Zeigt die Warnmeldung an und setzt die Ausführung des Befehls fort.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-368">Displays the warning message and continues executing the command.</span></span>
  <span data-ttu-id="ecf7d-369">"Continue" ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-369">"Continue" is the default value.</span></span>

- <span data-ttu-id="ecf7d-370">Digte.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-370">Inquire.</span></span> <span data-ttu-id="ecf7d-371">Zeigt die Warnmeldung an und fordert Sie zur Bestätigung auf, bevor die Ausführung fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-371">Displays the warning message and prompts you for confirmation before continuing execution.</span></span> <span data-ttu-id="ecf7d-372">Dieser Wert wird nur selten verwendet.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-372">This value is rarely used.</span></span>

- <span data-ttu-id="ecf7d-373">Beenden</span><span class="sxs-lookup"><span data-stu-id="ecf7d-373">Stop.</span></span> <span data-ttu-id="ecf7d-374">Zeigt die Warnmeldung an und beendet die Ausführung des Befehls.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-374">Displays the warning message and stops executing the command.</span></span>

> [!NOTE]
> <span data-ttu-id="ecf7d-375">Der WarningAction-Parameter überschreibt den Wert der $WarningAction Preference-Variablen nicht, wenn der-Parameter in einem Befehl zum Ausführen eines Skripts oder einer Funktion verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-375">The WarningAction parameter does not override the value of the $WarningAction preference variable when the parameter is used in a command to run a script or function.</span></span>

### <a name="examples"></a><span data-ttu-id="ecf7d-376">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="ecf7d-376">EXAMPLES</span></span>

<span data-ttu-id="ecf7d-377">Die allgemeinen Aktivitätsparameter sind äußerst nützlich.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-377">The activity common parameters are extremely useful.</span></span> <span data-ttu-id="ecf7d-378">Beispielsweise können Sie den pscomputername-Parameter verwenden, um bestimmte Aktivitäten nur für eine Teilmenge der Zielcomputer auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-378">For example, you can use the PSComputerName parameter to run particular activities on only a subset of the target computers.</span></span>

<span data-ttu-id="ecf7d-379">Sie können auch die Parameter psconnectionretrycount und psconnectionretryintervalsec verwenden, um die Wiederholungswerte für bestimmte Aktivitäten anzupassen.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-379">Or, you might use the PSConnectionRetryCount and PSConnectionRetryIntervalSec parameters to adjust the retry values for particular activities.</span></span>

<span data-ttu-id="ecf7d-380">Im folgenden Beispiel wird gezeigt, wie die allgemeinen Parameter der pscomputername-Aktivität verwendet werden, um eine Get-EventLog Aktivität nur auf Computern auszuführen, die eine bestimmte Domäne haben.</span><span class="sxs-lookup"><span data-stu-id="ecf7d-380">The following example shows how to use the PSComputerName activity common parameters to run a Get-EventLog activity only on computers it a particular domain.</span></span>

```powershell
Workflow Test-Workflow
{
    $UserDomain = Get-Content -Path '.\UserComputers.txt'
    $Log = (Get-EventLog -LogName "Windows PowerShell" `
      -PSComputerName $UserDomain)

    if ($Log)
    {
        # Do Work Here.
    }
}
```

<!--
# KEYWORDS
[about_Activity_Common_Parameters](about_Activity_Common_Parameters.md)
[about_Activity_Parameters](about_Activity_Parameters.md)
[about_ActivityParameters]()about_ActivityParameters.md) -->

## <a name="see-also"></a><span data-ttu-id="ecf7d-381">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="ecf7d-381">SEE ALSO</span></span>

<span data-ttu-id="ecf7d-382">[about_Workflows](about_workflows.md) 
 [about_WorkflowCommonParameters](about_WorkflowCommonParameters.md)</span><span class="sxs-lookup"><span data-stu-id="ecf7d-382">[about_Workflows](about_workflows.md)
[about_WorkflowCommonParameters](about_WorkflowCommonParameters.md)</span></span>
