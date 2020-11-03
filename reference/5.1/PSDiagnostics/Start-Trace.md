---
external help file: PSDiagnostics-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/start-trace?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Trace
ms.openlocfilehash: cbdb40edf85dd4645552f6e096a99384532b4443
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213516"
---
# <span data-ttu-id="c600f-103">Start-Trace</span><span class="sxs-lookup"><span data-stu-id="c600f-103">Start-Trace</span></span>

## <span data-ttu-id="c600f-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="c600f-104">SYNOPSIS</span></span>
<span data-ttu-id="c600f-105">Startet eine Protokollierungs Sitzung der Ereignis Ablauf Verfolgung.</span><span class="sxs-lookup"><span data-stu-id="c600f-105">Start an Event Trace logging session.</span></span>

## <span data-ttu-id="c600f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c600f-106">SYNTAX</span></span>

```
Start-Trace [-SessionName] <String> [[-OutputFilePath] <String>] [[-ProviderFilePath] <String>]
 [-ETS] [-Format <String>] [-MinBuffers <Int32>] [-MaxBuffers <Int32>]
 [-BufferSizeInKB <Int32>] [-MaxLogFileSizeInMB <Int32>] [<CommonParameters>]
```

## <span data-ttu-id="c600f-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c600f-107">DESCRIPTION</span></span>
<span data-ttu-id="c600f-108">Dieses Cmdlet startet eine Protokollierungs Sitzung für Windows-Ereignis Ablauf Verfolgung.</span><span class="sxs-lookup"><span data-stu-id="c600f-108">This cmdlet starts a Windows Event Trace logging session.</span></span>

<span data-ttu-id="c600f-109">Dieses Cmdlet wird von den folgenden Cmdlets verwendet:</span><span class="sxs-lookup"><span data-stu-id="c600f-109">This cmdlet is used by the following cmdlets:</span></span>

- `Enable-PSWSManCombinedTrace`
- `Enable-WSManTrace`

<span data-ttu-id="c600f-110">Sie müssen dieses Cmdlet aus einer PowerShell-Sitzung mit erhöhten Rechten ausführen.</span><span class="sxs-lookup"><span data-stu-id="c600f-110">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="c600f-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="c600f-111">EXAMPLES</span></span>

### <span data-ttu-id="c600f-112">Beispiel 1: Starten einer WSMAN-Ablauf Verfolgungs Protokollierungs Sitzung</span><span class="sxs-lookup"><span data-stu-id="c600f-112">Example 1: Start a WSMan Trace logging session</span></span>

```powershell
Start-Trace -SessionName 'wsmlog' -ETS -OutputFilePath "$env:windir\system32\wsmtraces.log" -Format 'bincirc' -MinBuffers 16 -MaxBuffers 256 -BufferSizeInKb 64 -MaxLogFileSizeInMB 256 -ProviderFilePath "$env:windir\system32\wsmtraceproviders.txt"
```

## <span data-ttu-id="c600f-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c600f-113">PARAMETERS</span></span>

### <span data-ttu-id="c600f-114">-Buffersizeinkb</span><span class="sxs-lookup"><span data-stu-id="c600f-114">-BufferSizeInKB</span></span>
<span data-ttu-id="c600f-115">Puffergröße für Ereignis Ablauf Verfolgungs Sitzung in Kilobyte (KB).</span><span class="sxs-lookup"><span data-stu-id="c600f-115">Event Trace Session buffer size in kilobytes (KB).</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c600f-116">-ETS</span><span class="sxs-lookup"><span data-stu-id="c600f-116">-ETS</span></span>
<span data-ttu-id="c600f-117">Direktes Senden von Befehlen an Ereignis Ablauf Verfolgungs Sitzungen, ohne zu speichern oder zu planen.</span><span class="sxs-lookup"><span data-stu-id="c600f-117">Send commands to Event Trace Sessions directly without saving or scheduling.</span></span>

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

### <span data-ttu-id="c600f-118">-Format</span><span class="sxs-lookup"><span data-stu-id="c600f-118">-Format</span></span>
<span data-ttu-id="c600f-119">Gibt das Protokoll Format für den Datensammler an.</span><span class="sxs-lookup"><span data-stu-id="c600f-119">Specifies the log format for the data collector.</span></span> <span data-ttu-id="c600f-120">Beim SQL-Datenbankformat muss die Option **outputfilepath** in der Befehlszeile mit dem Wert verwendet werden `dsn!log` .</span><span class="sxs-lookup"><span data-stu-id="c600f-120">For SQL database format, you must use the **OutputFilePath** option in the command line with the `dsn!log` value.</span></span> <span data-ttu-id="c600f-121">Der Standardwert ist Binary (bin).</span><span class="sxs-lookup"><span data-stu-id="c600f-121">The default is binary (bin).</span></span> <span data-ttu-id="c600f-122">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="c600f-122">The possible values are:</span></span>

- <span data-ttu-id="c600f-123">bin-Binary</span><span class="sxs-lookup"><span data-stu-id="c600f-123">bin - binary</span></span>
- <span data-ttu-id="c600f-124">bincirc-Binary mit zirkulärer Protokollierung</span><span class="sxs-lookup"><span data-stu-id="c600f-124">bincirc - binary with circular logging</span></span>
- <span data-ttu-id="c600f-125">CSV-durch Trennzeichen getrennte Werte</span><span class="sxs-lookup"><span data-stu-id="c600f-125">csv - Comma-separated values</span></span>
- <span data-ttu-id="c600f-126">TSV-durch Tabstopps getrennte Werte</span><span class="sxs-lookup"><span data-stu-id="c600f-126">tsv - Tab-separated values</span></span>
- <span data-ttu-id="c600f-127">SQL-SQL-Datenbank</span><span class="sxs-lookup"><span data-stu-id="c600f-127">sql - SQL database</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:
Accepted values: bin, bincirc, csv, tsv, sql

Required: False
Position: Named
Default value: bin
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c600f-128">-MaxBuffers</span><span class="sxs-lookup"><span data-stu-id="c600f-128">-MaxBuffers</span></span>
<span data-ttu-id="c600f-129">Legt die maximale Anzahl der Sitzungs Puffer für die Ereignis Ablauf Verfolgung fest.</span><span class="sxs-lookup"><span data-stu-id="c600f-129">Sets the maximum number of Event Trace Session buffers.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 256
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c600f-130">-Maxlogfilesizeinmb</span><span class="sxs-lookup"><span data-stu-id="c600f-130">-MaxLogFileSizeInMB</span></span>
<span data-ttu-id="c600f-131">Legt die maximale Protokolldatei Größe in Megabyte (MB) oder die Anzahl von Datensätzen für SQL-Protokolle fest.</span><span class="sxs-lookup"><span data-stu-id="c600f-131">Sets the maximum log file size in megabytes (MB) or number of records for SQL logs.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0 (no limit)
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c600f-132">-Minbuffers</span><span class="sxs-lookup"><span data-stu-id="c600f-132">-MinBuffers</span></span>
<span data-ttu-id="c600f-133">Legt die Mindestanzahl von Sitzungs Puffern für die Ereignis Ablauf Verfolgung fest.</span><span class="sxs-lookup"><span data-stu-id="c600f-133">Sets the minimum number of Event Trace Session buffers.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c600f-134">-Outputfilepath</span><span class="sxs-lookup"><span data-stu-id="c600f-134">-OutputFilePath</span></span>
<span data-ttu-id="c600f-135">Der Pfad der Ausgabeprotokoll Datei oder der DSN und der Protokoll Satz Name in einer SQL-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="c600f-135">Path of the output log file or the DSN and log set name in a SQL database.</span></span> <span data-ttu-id="c600f-136">Der Standardpfad lautet `$env:systemdrive\PerfLogs\Admin`.</span><span class="sxs-lookup"><span data-stu-id="c600f-136">The default path is `$env:systemdrive\PerfLogs\Admin`.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: $env:systemdrive\PerfLogs\Admin
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c600f-137">-Providerfilepath</span><span class="sxs-lookup"><span data-stu-id="c600f-137">-ProviderFilePath</span></span>
<span data-ttu-id="c600f-138">Datei mit mehreren Ereignis Ablauf Verfolgungs Anbietern, die aktiviert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c600f-138">File listing multiple Event Trace providers to enable.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c600f-139">-Sessionname</span><span class="sxs-lookup"><span data-stu-id="c600f-139">-SessionName</span></span>
<span data-ttu-id="c600f-140">Der Name der Ereignis Ablauf Verfolgungs Sitzung.</span><span class="sxs-lookup"><span data-stu-id="c600f-140">The name of the Event Trace session.</span></span> <span data-ttu-id="c600f-141">Um eine Ablauf Verfolgungs Sitzung zu verhindern, müssen Sie den Sitzungs Namen kennen.</span><span class="sxs-lookup"><span data-stu-id="c600f-141">To stop a trace session you must know the session name.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c600f-142">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c600f-142">CommonParameters</span></span>

<span data-ttu-id="c600f-143">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c600f-143">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c600f-144">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c600f-144">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c600f-145">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="c600f-145">INPUTS</span></span>

### <span data-ttu-id="c600f-146">Keine</span><span class="sxs-lookup"><span data-stu-id="c600f-146">None</span></span>

## <span data-ttu-id="c600f-147">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="c600f-147">OUTPUTS</span></span>

### <span data-ttu-id="c600f-148">System.Object</span><span class="sxs-lookup"><span data-stu-id="c600f-148">System.Object</span></span>

## <span data-ttu-id="c600f-149">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="c600f-149">NOTES</span></span>

## <span data-ttu-id="c600f-150">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="c600f-150">RELATED LINKS</span></span>

[<span data-ttu-id="c600f-151">Ereignis Ablauf Verfolgung</span><span class="sxs-lookup"><span data-stu-id="c600f-151">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="c600f-152">Stop-Trace</span><span class="sxs-lookup"><span data-stu-id="c600f-152">Stop-Trace</span></span>](stop-trace.md)

[<span data-ttu-id="c600f-153">Disable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="c600f-153">Disable-PSWSManCombinedTrace</span></span>](Disable-PSWSManCombinedTrace.md)

[<span data-ttu-id="c600f-154">Disable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="c600f-154">Disable-WSManTrace</span></span>](Disable-WSManTrace.md)

[<span data-ttu-id="c600f-155">Enable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="c600f-155">Enable-PSWSManCombinedTrace</span></span>](Enable-PSWSManCombinedTrace.md)

[<span data-ttu-id="c600f-156">Enable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="c600f-156">Enable-WSManTrace</span></span>](Enable-WSManTrace.md)
