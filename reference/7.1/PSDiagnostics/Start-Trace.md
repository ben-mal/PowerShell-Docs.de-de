---
external help file: PSDiagnostics-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/start-trace?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Trace
ms.openlocfilehash: 21fcb49200d71f451cdf5923bdd61f6daedd81b1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211692"
---
# <span data-ttu-id="78662-103">Start-Trace</span><span class="sxs-lookup"><span data-stu-id="78662-103">Start-Trace</span></span>

## <span data-ttu-id="78662-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="78662-104">SYNOPSIS</span></span>
<span data-ttu-id="78662-105">Startet eine Protokollierungs Sitzung der Ereignis Ablauf Verfolgung.</span><span class="sxs-lookup"><span data-stu-id="78662-105">Start an Event Trace logging session.</span></span>

## <span data-ttu-id="78662-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="78662-106">SYNTAX</span></span>

```
Start-Trace [-SessionName] <String> [[-OutputFilePath] <String>] [[-ProviderFilePath] <String>]
 [-ETS] [-Format <String>] [-MinBuffers <Int32>] [-MaxBuffers <Int32>]
 [-BufferSizeInKB <Int32>] [-MaxLogFileSizeInMB <Int32>] [<CommonParameters>]
```

## <span data-ttu-id="78662-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="78662-107">DESCRIPTION</span></span>
<span data-ttu-id="78662-108">Dieses Cmdlet startet eine Protokollierungs Sitzung für Windows-Ereignis Ablauf Verfolgung.</span><span class="sxs-lookup"><span data-stu-id="78662-108">This cmdlet starts a Windows Event Trace logging session.</span></span>

<span data-ttu-id="78662-109">Dieses Cmdlet wird von den folgenden Cmdlets verwendet:</span><span class="sxs-lookup"><span data-stu-id="78662-109">This cmdlet is used by the following cmdlets:</span></span>

- `Enable-PSWSManCombinedTrace`
- `Enable-WSManTrace`

<span data-ttu-id="78662-110">Sie müssen dieses Cmdlet aus einer PowerShell-Sitzung mit erhöhten Rechten ausführen.</span><span class="sxs-lookup"><span data-stu-id="78662-110">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="78662-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="78662-111">EXAMPLES</span></span>

### <span data-ttu-id="78662-112">Beispiel 1: Starten einer WSMAN-Ablauf Verfolgungs Protokollierungs Sitzung</span><span class="sxs-lookup"><span data-stu-id="78662-112">Example 1: Start a WSMan Trace logging session</span></span>

```powershell
Start-Trace -SessionName 'wsmlog' -ETS -OutputFilePath "$env:windir\system32\wsmtraces.log" -Format 'bincirc' -MinBuffers 16 -MaxBuffers 256 -BufferSizeInKb 64 -MaxLogFileSizeInMB 256 -ProviderFilePath "$env:windir\system32\wsmtraceproviders.txt"
```

## <span data-ttu-id="78662-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="78662-113">PARAMETERS</span></span>

### <span data-ttu-id="78662-114">-Buffersizeinkb</span><span class="sxs-lookup"><span data-stu-id="78662-114">-BufferSizeInKB</span></span>
<span data-ttu-id="78662-115">Puffergröße für Ereignis Ablauf Verfolgungs Sitzung in Kilobyte (KB).</span><span class="sxs-lookup"><span data-stu-id="78662-115">Event Trace Session buffer size in kilobytes (KB).</span></span>

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

### <span data-ttu-id="78662-116">-ETS</span><span class="sxs-lookup"><span data-stu-id="78662-116">-ETS</span></span>
<span data-ttu-id="78662-117">Direktes Senden von Befehlen an Ereignis Ablauf Verfolgungs Sitzungen, ohne zu speichern oder zu planen.</span><span class="sxs-lookup"><span data-stu-id="78662-117">Send commands to Event Trace Sessions directly without saving or scheduling.</span></span>

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

### <span data-ttu-id="78662-118">-Format</span><span class="sxs-lookup"><span data-stu-id="78662-118">-Format</span></span>
<span data-ttu-id="78662-119">Gibt das Protokoll Format für den Datensammler an.</span><span class="sxs-lookup"><span data-stu-id="78662-119">Specifies the log format for the data collector.</span></span> <span data-ttu-id="78662-120">Beim SQL-Datenbankformat muss die Option **outputfilepath** in der Befehlszeile mit dem Wert verwendet werden `dsn!log` .</span><span class="sxs-lookup"><span data-stu-id="78662-120">For SQL database format, you must use the **OutputFilePath** option in the command line with the `dsn!log` value.</span></span> <span data-ttu-id="78662-121">Der Standardwert ist Binary (bin).</span><span class="sxs-lookup"><span data-stu-id="78662-121">The default is binary (bin).</span></span> <span data-ttu-id="78662-122">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="78662-122">The possible values are:</span></span>

- <span data-ttu-id="78662-123">bin-Binary</span><span class="sxs-lookup"><span data-stu-id="78662-123">bin - binary</span></span>
- <span data-ttu-id="78662-124">bincirc-Binary mit zirkulärer Protokollierung</span><span class="sxs-lookup"><span data-stu-id="78662-124">bincirc - binary with circular logging</span></span>
- <span data-ttu-id="78662-125">CSV-durch Trennzeichen getrennte Werte</span><span class="sxs-lookup"><span data-stu-id="78662-125">csv - Comma-separated values</span></span>
- <span data-ttu-id="78662-126">TSV-durch Tabstopps getrennte Werte</span><span class="sxs-lookup"><span data-stu-id="78662-126">tsv - Tab-separated values</span></span>
- <span data-ttu-id="78662-127">SQL-SQL-Datenbank</span><span class="sxs-lookup"><span data-stu-id="78662-127">sql - SQL database</span></span>

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

### <span data-ttu-id="78662-128">-MaxBuffers</span><span class="sxs-lookup"><span data-stu-id="78662-128">-MaxBuffers</span></span>
<span data-ttu-id="78662-129">Legt die maximale Anzahl der Sitzungs Puffer für die Ereignis Ablauf Verfolgung fest.</span><span class="sxs-lookup"><span data-stu-id="78662-129">Sets the maximum number of Event Trace Session buffers.</span></span>

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

### <span data-ttu-id="78662-130">-Maxlogfilesizeinmb</span><span class="sxs-lookup"><span data-stu-id="78662-130">-MaxLogFileSizeInMB</span></span>
<span data-ttu-id="78662-131">Legt die maximale Protokolldatei Größe in Megabyte (MB) oder die Anzahl von Datensätzen für SQL-Protokolle fest.</span><span class="sxs-lookup"><span data-stu-id="78662-131">Sets the maximum log file size in megabytes (MB) or number of records for SQL logs.</span></span>

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

### <span data-ttu-id="78662-132">-Minbuffers</span><span class="sxs-lookup"><span data-stu-id="78662-132">-MinBuffers</span></span>
<span data-ttu-id="78662-133">Legt die Mindestanzahl von Sitzungs Puffern für die Ereignis Ablauf Verfolgung fest.</span><span class="sxs-lookup"><span data-stu-id="78662-133">Sets the minimum number of Event Trace Session buffers.</span></span>

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

### <span data-ttu-id="78662-134">-Outputfilepath</span><span class="sxs-lookup"><span data-stu-id="78662-134">-OutputFilePath</span></span>
<span data-ttu-id="78662-135">Der Pfad der Ausgabeprotokoll Datei oder der DSN und der Protokoll Satz Name in einer SQL-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="78662-135">Path of the output log file or the DSN and log set name in a SQL database.</span></span> <span data-ttu-id="78662-136">Der Standardpfad lautet `$env:systemdrive\PerfLogs\Admin`.</span><span class="sxs-lookup"><span data-stu-id="78662-136">The default path is `$env:systemdrive\PerfLogs\Admin`.</span></span>

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

### <span data-ttu-id="78662-137">-Providerfilepath</span><span class="sxs-lookup"><span data-stu-id="78662-137">-ProviderFilePath</span></span>
<span data-ttu-id="78662-138">Datei mit mehreren Ereignis Ablauf Verfolgungs Anbietern, die aktiviert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="78662-138">File listing multiple Event Trace providers to enable.</span></span>

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

### <span data-ttu-id="78662-139">-Sessionname</span><span class="sxs-lookup"><span data-stu-id="78662-139">-SessionName</span></span>
<span data-ttu-id="78662-140">Der Name der Ereignis Ablauf Verfolgungs Sitzung.</span><span class="sxs-lookup"><span data-stu-id="78662-140">The name of the Event Trace session.</span></span> <span data-ttu-id="78662-141">Um eine Ablauf Verfolgungs Sitzung zu verhindern, müssen Sie den Sitzungs Namen kennen.</span><span class="sxs-lookup"><span data-stu-id="78662-141">To stop a trace session you must know the session name.</span></span>

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

### <span data-ttu-id="78662-142">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="78662-142">CommonParameters</span></span>

<span data-ttu-id="78662-143">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="78662-143">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="78662-144">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="78662-144">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="78662-145">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="78662-145">INPUTS</span></span>

### <span data-ttu-id="78662-146">Keine</span><span class="sxs-lookup"><span data-stu-id="78662-146">None</span></span>

## <span data-ttu-id="78662-147">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="78662-147">OUTPUTS</span></span>

### <span data-ttu-id="78662-148">Keine</span><span class="sxs-lookup"><span data-stu-id="78662-148">None</span></span>

## <span data-ttu-id="78662-149">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="78662-149">NOTES</span></span>

## <span data-ttu-id="78662-150">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="78662-150">RELATED LINKS</span></span>

[<span data-ttu-id="78662-151">Ereignis Ablauf Verfolgung</span><span class="sxs-lookup"><span data-stu-id="78662-151">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="78662-152">Stop-Trace</span><span class="sxs-lookup"><span data-stu-id="78662-152">Stop-Trace</span></span>](stop-trace.md)

[<span data-ttu-id="78662-153">Disable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="78662-153">Disable-PSWSManCombinedTrace</span></span>](Disable-PSWSManCombinedTrace.md)

[<span data-ttu-id="78662-154">Disable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="78662-154">Disable-WSManTrace</span></span>](Disable-WSManTrace.md)

[<span data-ttu-id="78662-155">Enable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="78662-155">Enable-PSWSManCombinedTrace</span></span>](Enable-PSWSManCombinedTrace.md)

[<span data-ttu-id="78662-156">Enable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="78662-156">Enable-WSManTrace</span></span>](Enable-WSManTrace.md)

