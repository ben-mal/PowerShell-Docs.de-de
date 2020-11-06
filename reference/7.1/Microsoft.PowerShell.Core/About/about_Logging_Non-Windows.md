---
description: PowerShell protokolliert interne Vorgänge von der Engine, den Anbietern und den Cmdlets.
keywords: powershell
Locale: en-US
ms.date: 03/30/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_logging_non-windows?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Logging_Non-Windows
ms.openlocfilehash: f70e2cb2c04287e36ecdf21a97dd099fcfd23d65
ms.sourcegitcommit: 39c2a697228276d5dae39e540995fa479c2b5f39
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2020
ms.locfileid: "93355492"
---
# <a name="about-logging-non-windows"></a><span data-ttu-id="5a9c4-104">Informationen zur Protokollierung nicht-Windows</span><span class="sxs-lookup"><span data-stu-id="5a9c4-104">About Logging Non-Windows</span></span>

## <a name="short-description"></a><span data-ttu-id="5a9c4-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5a9c4-105">Short description</span></span>
<span data-ttu-id="5a9c4-106">PowerShell protokolliert interne Vorgänge von der Engine, den Anbietern und den Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-106">PowerShell logs internal operations from the engine, providers, and cmdlets.</span></span>

## <a name="long-description"></a><span data-ttu-id="5a9c4-107">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5a9c4-107">Long description</span></span>

<span data-ttu-id="5a9c4-108">PowerShell protokolliert Details von PowerShell-Vorgängen.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-108">PowerShell logs details of PowerShell operations.</span></span> <span data-ttu-id="5a9c4-109">PowerShell protokolliert z. b. Vorgänge wie das Starten und Beenden der-Engine sowie das Starten und Beenden von Anbietern.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-109">For example, PowerShell will log operations such as starting and stopping the engine and starting and stopping providers.</span></span> <span data-ttu-id="5a9c4-110">Außerdem werden Details zu PowerShell-Befehlen protokolliert.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-110">It will also log details about PowerShell commands.</span></span>

<span data-ttu-id="5a9c4-111">Der Speicherort von PowerShell-Protokollen hängt von der Zielplattform ab.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-111">The location of PowerShell logs is dependent on the target platform.</span></span> <span data-ttu-id="5a9c4-112">Unter **Linux** können PowerShell-Protokolle für **syslog** und **rsyslog. conf** verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-112">On **Linux** , PowerShell logs to **syslog** and **rsyslog.conf** can be used.</span></span> <span data-ttu-id="5a9c4-113">Weitere Informationen finden Sie auf den lokalen Seiten des Linux-Computers `man` .</span><span class="sxs-lookup"><span data-stu-id="5a9c4-113">For more information, refer to the Linux computer's local `man` pages.</span></span> <span data-ttu-id="5a9c4-114">Unter **macOS** wird das **os_log** Protokollierungs System verwendet.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-114">On **macOS** , the **os_log** logging system is used.</span></span> <span data-ttu-id="5a9c4-115">Weitere Informationen finden Sie unter [os_log Developer-Dokumentation](https://developer.apple.com/documentation/os/os_log).</span><span class="sxs-lookup"><span data-stu-id="5a9c4-115">For more information, see [os_log developer documentation](https://developer.apple.com/documentation/os/os_log).</span></span>

## <a name="viewing-powershell-log-output-on-linux"></a><span data-ttu-id="5a9c4-116">Anzeigen der PowerShell-Protokoll Ausgabe unter Linux</span><span class="sxs-lookup"><span data-stu-id="5a9c4-116">Viewing PowerShell log output on Linux</span></span>

<span data-ttu-id="5a9c4-117">PowerShell-Protokolle für **syslog** unter Linux und alle Tools, die häufig zum Anzeigen von **syslog** -Inhalten verwendet werden, können verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-117">PowerShell logs to **syslog** on Linux and any of the tools commonly used to view **syslog** contents may be used.</span></span>

<span data-ttu-id="5a9c4-118">Das Format der Protokolleinträge verwendet die folgende Vorlage:</span><span class="sxs-lookup"><span data-stu-id="5a9c4-118">The format of the log entries uses the following template:</span></span>

```
TIMESTAMP MACHINENAME powershell[PID]: (COMMITID:TID:CID)
  [EVENTID:TASK.OPCODE.LEVEL] MESSAGE
```

|<span data-ttu-id="5a9c4-119">Feld</span><span class="sxs-lookup"><span data-stu-id="5a9c4-119">Field</span></span>        |<span data-ttu-id="5a9c4-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5a9c4-120">Description</span></span>                                             |
|-------------|--------------------------------------------------------|
|`TIMESTAMP`  |<span data-ttu-id="5a9c4-121">Ein Datum/Uhrzeit-Zeitpunkt, zu dem der Protokolleintrag erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-121">A date/time when the log entry was produced.</span></span>            |
|`MACHINENAME`|<span data-ttu-id="5a9c4-122">Der Name des Systems, auf dem das Protokoll erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-122">The name of the system where the log was produced.</span></span>      |
|`PID`        |<span data-ttu-id="5a9c4-123">Die Prozess-ID des Prozesses, der den Protokolleintrag geschrieben hat.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-123">The process ID of the process that wrote the log entry.</span></span> |
|`COMMITID`   |<span data-ttu-id="5a9c4-124">Die `git commit` ID oder das Tag, das zum Erstellen des Builds verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-124">The `git commit` ID or tag used to produce the build.</span></span>   |
|`TID`        |<span data-ttu-id="5a9c4-125">Die Thread-ID des Threads, der den Protokolleintrag geschrieben hat.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-125">The thread ID of the thread that wrote the log entry.</span></span>   |
|`CID`        |<span data-ttu-id="5a9c4-126">Der hexadezimale Kanal Bezeichner des Protokoll Eintrags.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-126">The hex channel identifier of the log entry.</span></span>            |
|             |<span data-ttu-id="5a9c4-127">10 = Operational, 11 = analytische</span><span class="sxs-lookup"><span data-stu-id="5a9c4-127">10 = Operational, 11 = Analytic</span></span>                         |
|`EVENTID`    |<span data-ttu-id="5a9c4-128">Der Ereignis Bezeichner des Protokoll Eintrags.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-128">The event identifier of the log entry.</span></span>                  |
|`TASK`       |<span data-ttu-id="5a9c4-129">Der Task Bezeichner für den Ereignis Eintrag.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-129">The task identifier for the event entry</span></span>                 |
|`OPCODE`     |<span data-ttu-id="5a9c4-130">Der Opcode für den Ereignis Eintrag.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-130">The opcode for the event entry</span></span>                          |
|`LEVEL`      |<span data-ttu-id="5a9c4-131">Die Protokollebene für den Ereignis Eintrag.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-131">The log level for the event entry</span></span>                       |
|`MESSAGE`    |<span data-ttu-id="5a9c4-132">Die Meldung, die dem Ereignis Eintrag zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-132">The message associated with the event entry</span></span>             |

> [!NOTE]
> <span data-ttu-id="5a9c4-133">`EVENTID`, `TASK` , `OPCODE` und `LEVEL` sind die gleichen Werte, die bei der Protokollierung im Windows-Ereignisprotokoll verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-133">`EVENTID`, `TASK`, `OPCODE`, and `LEVEL` are the same values as used when logging to the Windows event log.</span></span>

### <a name="filtering-powershell-log-entries-using-rsyslog"></a><span data-ttu-id="5a9c4-134">Filtern von PowerShell-Protokoll Einträgen mithilfe von rsyslog</span><span class="sxs-lookup"><span data-stu-id="5a9c4-134">Filtering PowerShell log entries using rsyslog</span></span>

<span data-ttu-id="5a9c4-135">Normalerweise werden PowerShell-Protokolleinträge in den Standardwert `location/file` für **syslog** geschrieben.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-135">Normally, PowerShell log entries are written to the default `location/file` for **syslog**.</span></span> <span data-ttu-id="5a9c4-136">Allerdings ist es möglich, die Einträge an eine benutzerdefinierte Datei umzuleiten.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-136">However, it's possible to redirect the entries to a custom file.</span></span>

1. <span data-ttu-id="5a9c4-137">Erstellen Sie eine conf für die PowerShell-Protokoll Konfiguration, und geben Sie eine Zahl an, die kleiner als 50 (für `50-default.conf` ) ist, z `40-powershell.conf` . b..</span><span class="sxs-lookup"><span data-stu-id="5a9c4-137">Create a conf for PowerShell log configuration and provide a number that's less than 50 (for `50-default.conf`), such as `40-powershell.conf`.</span></span> <span data-ttu-id="5a9c4-138">Die Datei sollte unter platziert werden `/etc/rsyslog.d` .</span><span class="sxs-lookup"><span data-stu-id="5a9c4-138">The file should be placed under `/etc/rsyslog.d`.</span></span>

1. <span data-ttu-id="5a9c4-139">Fügen Sie der Datei den folgenden Eintrag hinzu:</span><span class="sxs-lookup"><span data-stu-id="5a9c4-139">Add the following entry to the file:</span></span>

   ```
   :syslogtag, contains, "powershell[" /var/log/powershell.log
   & stop
   ```

1. <span data-ttu-id="5a9c4-140">Stellen Sie sicher, dass `/etc/rsyslog.conf` die neue Datei enthält.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-140">Make sure `/etc/rsyslog.conf` includes the new file.</span></span> <span data-ttu-id="5a9c4-141">Häufig wird eine generische include-Anweisung verwendet, die wie folgt aussieht:</span><span class="sxs-lookup"><span data-stu-id="5a9c4-141">Often, it will have a generic include statement that looks like following configuration:</span></span>

   `$IncludeConfig /etc/rsyslog.d/*.conf`

   <span data-ttu-id="5a9c4-142">Wenn dies nicht der Fall ist, müssen Sie eine include-Anweisung manuell hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-142">If it doesn't, you'll need to add an include statement manually.</span></span>

1. <span data-ttu-id="5a9c4-143">Stellen Sie sicher, dass Attribute und Berechtigungen entsprechend festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-143">Make sure attributes and permissions are set appropriately.</span></span>

   ```
   -rw-r--r-- 1 root root   67 Nov 28 12:51 40-powershell.conf
   ```

1. <span data-ttu-id="5a9c4-144">Legen Sie Ownership auf **root** fest.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-144">Set ownership to **root**.</span></span>

   ```
   chown root:root /etc/rsyslog.d/40-powershell.conf
   ```

1. <span data-ttu-id="5a9c4-145">Zugriffsberechtigungen festlegen: **root** hat Lese-/Schreibzugriff, **Benutzer** haben Lesezugriff.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-145">Set access permissions: **root** has read/write, **users** have read.</span></span>

   ```
   chmod 644 /etc/rsyslog.d/40-powershell.conf
   ```

## <a name="viewing-powershell-log-output-on-macos"></a><span data-ttu-id="5a9c4-146">Anzeigen der PowerShell-Protokoll Ausgabe unter macOS</span><span class="sxs-lookup"><span data-stu-id="5a9c4-146">Viewing PowerShell log output on macOS</span></span>

<span data-ttu-id="5a9c4-147">Die einfachste Methode zum Anzeigen der PowerShell-Protokoll Ausgabe unter macOS ist die Verwendung der **Konsolen** Anwendung.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-147">The easiest method for viewing PowerShell log output on macOS is using the **Console** application.</span></span>

1. <span data-ttu-id="5a9c4-148">Suchen Sie nach der **Konsolen** Anwendung, und starten Sie Sie.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-148">Search for the **Console** application and launch it.</span></span>
1. <span data-ttu-id="5a9c4-149">Wählen Sie unter **Geräte** den Computernamen aus.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-149">Select the Machine name under **Devices**.</span></span>
1. <span data-ttu-id="5a9c4-150">Geben Sie im **Suchfeld als Suchbegriff** `pwsh` für die Haupt-Binärdatei von PowerShell ein.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-150">In the **Search** field, enter `pwsh` for the PowerShell main binary.</span></span>
1. <span data-ttu-id="5a9c4-151">Ändern Sie den Suchfilter von `Any` in `Process` .</span><span class="sxs-lookup"><span data-stu-id="5a9c4-151">Change the search filter from `Any` to `Process`.</span></span>
1. <span data-ttu-id="5a9c4-152">Führen Sie die Vorgänge aus.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-152">Perform the operations.</span></span>
1. <span data-ttu-id="5a9c4-153">Optional können Sie die Suche für die spätere Verwendung speichern.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-153">Optionally, save the search for future use.</span></span>

<span data-ttu-id="5a9c4-154">Um eine bestimmte Prozess Instanz von PowerShell in der- **Konsole** zu filtern, enthält die Variable `$pid` die Prozess-ID.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-154">To filter on a specific process instance of PowerShell in the **Console** , the variable `$pid` contains the process ID.</span></span>

1. <span data-ttu-id="5a9c4-155">Geben Sie die **PID** (Prozess-ID) in das **Suchfeld** ein.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-155">Enter the **pid** (Process ID) in the **Search** field.</span></span>
1. <span data-ttu-id="5a9c4-156">Ändern Sie den Suchfilter in `PID` .</span><span class="sxs-lookup"><span data-stu-id="5a9c4-156">Change the search filter to `PID`.</span></span>
1. <span data-ttu-id="5a9c4-157">Führen Sie die Vorgänge aus.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-157">Perform the operations.</span></span>

### <a name="viewing-powershell-log-output-from-a-command-line"></a><span data-ttu-id="5a9c4-158">Anzeigen der PowerShell-Protokoll Ausgabe von einer Befehlszeile aus</span><span class="sxs-lookup"><span data-stu-id="5a9c4-158">Viewing PowerShell log output from a command line</span></span>

<span data-ttu-id="5a9c4-159">Der `log` Befehl kann verwendet werden, um PowerShell-Protokolleinträge von der Befehlszeile aus anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-159">The `log` command can be used to view PowerShell log entries from the command line.</span></span>

```
sudo log stream --predicate 'process == "pwsh"' --info
```

### <a name="persisting-powershell-log-output"></a><span data-ttu-id="5a9c4-160">Beibehalten der PowerShell-Protokoll Ausgabe</span><span class="sxs-lookup"><span data-stu-id="5a9c4-160">Persisting PowerShell log output</span></span>

<span data-ttu-id="5a9c4-161">Standardmäßig verwendet PowerShell die standardmäßige reine Speicher Protokollierung unter macOS.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-161">By default, PowerShell uses the default memory-only logging on macOS.</span></span> <span data-ttu-id="5a9c4-162">Dieses Verhalten kann geändert werden, um die Persistenz mithilfe des Befehls zu aktivieren `log config` .</span><span class="sxs-lookup"><span data-stu-id="5a9c4-162">This behavior can be changed to enable persistence using the `log config` command.</span></span>

<span data-ttu-id="5a9c4-163">Das folgende Skript aktiviert die Protokollierung und Persistenz auf infoebene:</span><span class="sxs-lookup"><span data-stu-id="5a9c4-163">The following script enables info level logging and persistence:</span></span>

```
log config --subsystem com.microsoft.powershell --mode=persist:info,level:info
```

<span data-ttu-id="5a9c4-164">Mit dem folgenden Befehl wird die PowerShell-Protokollierung auf den Standardzustand zurückgesetzt:</span><span class="sxs-lookup"><span data-stu-id="5a9c4-164">The following command reverts PowerShell logging to the default state:</span></span>

```
log config --subsystem com.microsoft.powershell --mode=persist:default,level:default
```

<span data-ttu-id="5a9c4-165">Nachdem die Persistenz aktiviert wurde, `log show` kann der Befehl zum Exportieren von Protokoll Elementen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-165">After persistence is enabled, the `log show` command can be used to export log items.</span></span> <span data-ttu-id="5a9c4-166">Der-Befehl stellt Optionen zum Exportieren der letzten N Elemente, Elemente seit einer bestimmten Zeit oder Elemente innerhalb einer bestimmten Zeitspanne bereit.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-166">The command provides options for exporting the last N items, items since a given time, or items within a given time span.</span></span>

<span data-ttu-id="5a9c4-167">Beispielsweise exportiert der folgende Befehl Elemente seit `9am on April 5 of 2018` :</span><span class="sxs-lookup"><span data-stu-id="5a9c4-167">For example, the following command exports items since `9am on April 5 of 2018`:</span></span>

```
log show --info --start "2018-04-05 09:00:00" --predicate "process = 'pwsh'"
```

<span data-ttu-id="5a9c4-168">`log`Weitere Informationen finden Sie unter `log show --help` .</span><span class="sxs-lookup"><span data-stu-id="5a9c4-168">You can get help for `log` by running `log show --help` for additional details.</span></span>

> [!TIP]
> <span data-ttu-id="5a9c4-169">Wenn Sie einen der Protokoll Befehle von einer PowerShell-Eingabeaufforderung oder einem Skript ausführen, verwenden Sie doppelte Anführungszeichen um die gesamte Prädikat Zeichenfolge und einfache Anführungszeichen innerhalb von.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-169">When executing any of the log commands from a PowerShell prompt or script, use double quotes around the entire predicate string and single quotes within.</span></span> <span data-ttu-id="5a9c4-170">Dadurch entfällt die Notwendigkeit, doppelte Anführungszeichen in der Prädikat Zeichenfolge zu schließen.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-170">This avoids the need to escape double quote characters within the predicate string.</span></span>

<span data-ttu-id="5a9c4-171">Möglicherweise möchten Sie auch die Ereignisprotokolle an einem sichereren Speicherort speichern, z. b. in einem zentralen Ereignisprotokoll Sammler oder [Siem][] -Aggregator.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-171">You may also want to consider saving the event logs to a more secure location such as a central event log collector, or [SIEM][] aggregator.</span></span> <span data-ttu-id="5a9c4-172">Sie können Siem in Azure einrichten.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-172">You can set up SIEM in Azure.</span></span> <span data-ttu-id="5a9c4-173">Weitere Informationen finden Sie unter [generische Siem-Integration](/cloud-app-security/siem).</span><span class="sxs-lookup"><span data-stu-id="5a9c4-173">For more information, see [Generic SIEM integration](/cloud-app-security/siem).</span></span>

## <a name="configuring-logging-on-a-non-windows-system"></a><span data-ttu-id="5a9c4-174">Konfigurieren der Protokollierung auf einem nicht-Windows-System</span><span class="sxs-lookup"><span data-stu-id="5a9c4-174">Configuring logging on a non-Windows system</span></span>

<span data-ttu-id="5a9c4-175">Unter Windows wird die Protokollierung durch Erstellen von etw-Ablaufverfolgungslistenern oder mithilfe der Ereignisanzeige zum Aktivieren der analytischen Protokollierung konfiguriert</span><span class="sxs-lookup"><span data-stu-id="5a9c4-175">On Windows, logging is configured by creating ETW trace listeners or by using the Event Viewer to enable Analytic logging.</span></span> <span data-ttu-id="5a9c4-176">Unter Linux und macOS wird die Protokollierung mithilfe der-Datei konfiguriert `powershell.config.json` .</span><span class="sxs-lookup"><span data-stu-id="5a9c4-176">On Linux and macOS, logging is configured using the file `powershell.config.json`.</span></span> <span data-ttu-id="5a9c4-177">Im restlichen Teil dieses Abschnitts wird die Konfiguration der PowerShell-Protokollierung auf einem nicht-Windows-System erläutert.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-177">The rest of this section will discuss configuring PowerShell logging on a non-Windows system.</span></span>

<span data-ttu-id="5a9c4-178">PowerShell ermöglicht standardmäßig eine Informations Protokollierung im Betriebskanal.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-178">By default, PowerShell enables informational logging to the operational channel.</span></span> <span data-ttu-id="5a9c4-179">Dies bedeutet, dass jede von PowerShell erzeugte Protokoll Ausgabe, die als betriebsbereit markiert ist, und eine Protokollebene (Ablauf Verfolgungs Ebene) vorhanden ist, die größer als die Information ist, protokolliert wird.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-179">What this means is any log output produced by PowerShell that is marked as operational and has a log (trace) level greater than informational will be logged.</span></span> <span data-ttu-id="5a9c4-180">Gelegentlich kann es vorkommen, dass Diagnosen eine zusätzliche Protokoll Ausgabe erfordern, z. b. eine ausführliche Protokoll Ausgabe oder die Aktivierung der analytischen Protokoll Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-180">Occasionally, diagnoses may require additional log output, such as verbose log output or enabling analytic log output.</span></span>

<span data-ttu-id="5a9c4-181">Die Datei `powershell.config.json` ist eine **JSON** -formatierte Datei, die sich im PowerShell- `$PSHOME` Verzeichnis befindet.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-181">The file `powershell.config.json` is a **JSON** formatted file residing in the PowerShell `$PSHOME` directory.</span></span> <span data-ttu-id="5a9c4-182">Jede Installation von PowerShell verwendet eine eigene Kopie dieser Datei.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-182">Each installation of PowerShell uses its own copy of this file.</span></span> <span data-ttu-id="5a9c4-183">Für den normalen Betrieb bleibt diese Datei unverändert.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-183">For normal operation, this file is left unchanged.</span></span> <span data-ttu-id="5a9c4-184">Dies kann nützlich sein, um einige der Einstellungen in der Datei zu ändern, um die Diagnose zu ändern oder um zwischen mehreren PowerShell-Versionen im selben System oder sogar mit mehreren Kopien derselben Version zu unterscheiden (siehe `LogIdentity` in der Tabelle unten).</span><span class="sxs-lookup"><span data-stu-id="5a9c4-184">Although it can be useful, to change some of the settings in the file, for diagnosis or for distinguishing between multiple PowerShell versions on the same system or even multiple copies of the same version (See `LogIdentity` in the table below).</span></span>

<span data-ttu-id="5a9c4-185">Der folgende Code ist eine Beispielkonfiguration:</span><span class="sxs-lookup"><span data-stu-id="5a9c4-185">The following code is an example configuration:</span></span>

```json
{
  "Microsoft.PowerShell:ExecutionPolicy": "RemoteSigned",
  "PowerShellPolicies": {
    "ScriptExecution": {
      "ExecutionPolicy": "RemoteSigned",
      "EnableScripts": true
    },
    "ScriptBlockLogging": {
      "EnableScriptBlockInvocationLogging": true,
      "EnableScriptBlockLogging": true
    },
    "ModuleLogging": {
      "EnableModuleLogging": false,
      "ModuleNames": [
        "PSReadline",
        "PowerShellGet"
      ]
    },
    "ProtectedEventLogging": {
      "EnableProtectedEventLogging": false,
      "EncryptionCertificate": [
        "Joe"
      ]
    },
    "Transcription": {
      "EnableTranscripting": true,
      "EnableInvocationHeader": true,
      "OutputDirectory": "F:\\tmp\\new"
    },
    "UpdatableHelp": {
      "DefaultSourcePath": "f:\\temp"
    },
    "ConsoleSessionConfiguration": {
      "EnableConsoleSessionConfiguration": false,
      "ConsoleSessionConfigurationName": "name"
    }
  },
  "LogLevel": "verbose"
}
```

<span data-ttu-id="5a9c4-186">Die Eigenschaften zum Konfigurieren der PowerShell-Protokollierung sind in der folgenden Tabelle aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-186">The properties for configuring PowerShell logging are listed in the following table.</span></span> <span data-ttu-id="5a9c4-187">Werte, die mit einem Sternchen gekennzeichnet sind (z. b.), `Operational*` geben den Standardwert an, wenn kein Wert in der Datei angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-187">Values marked with an asterisk, such as `Operational*`, indicate the default value when no value is provided in the file.</span></span>

|<span data-ttu-id="5a9c4-188">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="5a9c4-188">Property</span></span>   |<span data-ttu-id="5a9c4-189">Werte</span><span class="sxs-lookup"><span data-stu-id="5a9c4-189">Values</span></span>        |<span data-ttu-id="5a9c4-190">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5a9c4-190">Description</span></span>                                  |
|-----------|--------------|---------------------------------------------|
|`LogIdentity`|<span data-ttu-id="5a9c4-191">(Zeichen folgen Name)</span><span class="sxs-lookup"><span data-stu-id="5a9c4-191">(string name)</span></span> |<span data-ttu-id="5a9c4-192">Der Name, der bei der Protokollierung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-192">The name to use when logging.</span></span> <span data-ttu-id="5a9c4-193">Standardmäßig wird von</span><span class="sxs-lookup"><span data-stu-id="5a9c4-193">By default,</span></span>  |
|           |<span data-ttu-id="5a9c4-194">PowerShell</span><span class="sxs-lookup"><span data-stu-id="5a9c4-194">powershell\*</span></span>   |<span data-ttu-id="5a9c4-195">PowerShell ist die Identität.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-195">powershell is the identity.</span></span> <span data-ttu-id="5a9c4-196">Dieser Wert kann</span><span class="sxs-lookup"><span data-stu-id="5a9c4-196">This value can be</span></span>|
|           |              |<span data-ttu-id="5a9c4-197">wird verwendet, um den Unterschied zwischen zwei</span><span class="sxs-lookup"><span data-stu-id="5a9c4-197">used to tell the difference between two</span></span>      |
|           |              |<span data-ttu-id="5a9c4-198">Instanzen einer PowerShell-Installation, z. b.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-198">instances of a PowerShell installation, such</span></span> |
|           |              |<span data-ttu-id="5a9c4-199">als Release-und Beta Version.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-199">as a release and beta version.</span></span> <span data-ttu-id="5a9c4-200">Dieser Wert ist</span><span class="sxs-lookup"><span data-stu-id="5a9c4-200">This value is</span></span> |
|           |              |<span data-ttu-id="5a9c4-201">wird auch zum Umleiten der Protokoll Ausgabe an einen verwendet.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-201">also used to redirect log output to a</span></span>        |
|           |              |<span data-ttu-id="5a9c4-202">separate Datei unter Linux.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-202">separate file on Linux.</span></span> <span data-ttu-id="5a9c4-203">Weitere Informationen finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="5a9c4-203">See the discussion of</span></span>|
|           |              |<span data-ttu-id="5a9c4-204">**rsyslog** oben.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-204">**rsyslog** above.</span></span>                           |
|`LogChannels`|<span data-ttu-id="5a9c4-205">Betriebs</span><span class="sxs-lookup"><span data-stu-id="5a9c4-205">Operational\*</span></span>  |<span data-ttu-id="5a9c4-206">Die Kanäle, die aktiviert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-206">The channels to enable.</span></span> <span data-ttu-id="5a9c4-207">Werte trennen</span><span class="sxs-lookup"><span data-stu-id="5a9c4-207">Separate the values</span></span>|
|           |<span data-ttu-id="5a9c4-208">Analytic</span><span class="sxs-lookup"><span data-stu-id="5a9c4-208">Analytic</span></span>      |<span data-ttu-id="5a9c4-209">mit einem Komma, wenn mehr als eins angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-209">with a comma when specifying more than one.</span></span>  |
|`LogLevel`   |<span data-ttu-id="5a9c4-210">Always</span><span class="sxs-lookup"><span data-stu-id="5a9c4-210">Always</span></span>        |<span data-ttu-id="5a9c4-211">Geben Sie einen einzelnen Wert an.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-211">Specify a single value.</span></span> <span data-ttu-id="5a9c4-212">Der Wert aktiviert</span><span class="sxs-lookup"><span data-stu-id="5a9c4-212">The value enables</span></span>  |
|           |<span data-ttu-id="5a9c4-213">Kritisch</span><span class="sxs-lookup"><span data-stu-id="5a9c4-213">Critical</span></span>      |<span data-ttu-id="5a9c4-214">selbst und alle obigen Werte in der</span><span class="sxs-lookup"><span data-stu-id="5a9c4-214">itself and all values above it in the</span></span>        |
|           |<span data-ttu-id="5a9c4-215">Fehler</span><span class="sxs-lookup"><span data-stu-id="5a9c4-215">Error</span></span>         |<span data-ttu-id="5a9c4-216">nach Links auflisten.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-216">list to the left.</span></span>                            |
|           |<span data-ttu-id="5a9c4-217">Warnung</span><span class="sxs-lookup"><span data-stu-id="5a9c4-217">Warning</span></span>       |                                             |
|           |<span data-ttu-id="5a9c4-218">Ellen</span><span class="sxs-lookup"><span data-stu-id="5a9c4-218">Informational\*</span></span>|                                             |
|           |<span data-ttu-id="5a9c4-219">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="5a9c4-219">Verbose</span></span>       |                                             |
|           |<span data-ttu-id="5a9c4-220">Debuggen</span><span class="sxs-lookup"><span data-stu-id="5a9c4-220">Debug</span></span>         |                                             |
|`LogKeywords`|<span data-ttu-id="5a9c4-221">Runspace</span><span class="sxs-lookup"><span data-stu-id="5a9c4-221">Runspace</span></span>      |<span data-ttu-id="5a9c4-222">Schlüsselwörter bieten die Möglichkeit, die Protokollierung einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-222">Keywords provide the ability to limit logging</span></span>|
|           |<span data-ttu-id="5a9c4-223">Pipeline</span><span class="sxs-lookup"><span data-stu-id="5a9c4-223">Pipeline</span></span>      |<span data-ttu-id="5a9c4-224">für bestimmte Komponenten in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-224">to specific components within PowerShell.</span></span> <span data-ttu-id="5a9c4-225">nach</span><span class="sxs-lookup"><span data-stu-id="5a9c4-225">By</span></span> |
|           |<span data-ttu-id="5a9c4-226">Protocol</span><span class="sxs-lookup"><span data-stu-id="5a9c4-226">Protocol</span></span>      |<span data-ttu-id="5a9c4-227">Standardmäßig sind alle Schlüsselwörter aktiviert und werden geändert.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-227">default, all keywords are enabled and change</span></span> |
|           |<span data-ttu-id="5a9c4-228">Transport</span><span class="sxs-lookup"><span data-stu-id="5a9c4-228">Transport</span></span>     |<span data-ttu-id="5a9c4-229">Dieser Wert ist nur für sehr nützlich.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-229">this value is only useful for very</span></span>           |
|           |<span data-ttu-id="5a9c4-230">Host</span><span class="sxs-lookup"><span data-stu-id="5a9c4-230">Host</span></span>          |<span data-ttu-id="5a9c4-231">spezialisierte Problembehandlung.</span><span class="sxs-lookup"><span data-stu-id="5a9c4-231">specialized troubleshooting.</span></span>                |
|           |<span data-ttu-id="5a9c4-232">Cmdlets</span><span class="sxs-lookup"><span data-stu-id="5a9c4-232">Cmdlets</span></span>       |                                             |
|           |<span data-ttu-id="5a9c4-233">serializer</span><span class="sxs-lookup"><span data-stu-id="5a9c4-233">Serializer</span></span>    |                                             |
|           |<span data-ttu-id="5a9c4-234">Sitzung</span><span class="sxs-lookup"><span data-stu-id="5a9c4-234">Session</span></span>       |                                             |
|           |<span data-ttu-id="5a9c4-235">Managedplugin</span><span class="sxs-lookup"><span data-stu-id="5a9c4-235">ManagedPlugin</span></span> |                                             |

## <a name="see-also"></a><span data-ttu-id="5a9c4-236">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5a9c4-236">See also</span></span>

<span data-ttu-id="5a9c4-237">Informationen zu Linux- **syslog** -und **rsyslog. conf** -Informationen finden Sie auf den lokalen Seiten des Linux-Computers `man` .</span><span class="sxs-lookup"><span data-stu-id="5a9c4-237">For Linux **syslog** and **rsyslog.conf** information, refer to the Linux computer's local `man` pages.</span></span>

<span data-ttu-id="5a9c4-238">Informationen zu macOS- **os_log** finden Sie in [os_log Entwicklerdokumentation](https://developer.apple.com/documentation/os/os_log).</span><span class="sxs-lookup"><span data-stu-id="5a9c4-238">For macOS **os_log** information, see [os_log developer documentation](https://developer.apple.com/documentation/os/os_log).</span></span>

[<span data-ttu-id="5a9c4-239">about_Logging_Windows</span><span class="sxs-lookup"><span data-stu-id="5a9c4-239">about_Logging_Windows</span></span>](about_Logging_Windows.md)

[<span data-ttu-id="5a9c4-240">Generische SIEM-Integration</span><span class="sxs-lookup"><span data-stu-id="5a9c4-240">Generic SIEM integration</span></span>](/cloud-app-security/siem)

<!-- link references -->
[SIEM]: https://wikipedia.org/wiki/Security_information_and_event_management
