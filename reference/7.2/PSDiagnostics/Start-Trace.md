---
external help file: PSDiagnostics-help.xml
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/start-trace?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Trace
ms.openlocfilehash: b1c6a596f3dc35028b928c3a6b5459a805bc2512
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602505"
---
# <span data-ttu-id="0b102-102">Start-Trace</span><span class="sxs-lookup"><span data-stu-id="0b102-102">Start-Trace</span></span>

## <span data-ttu-id="0b102-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="0b102-103">SYNOPSIS</span></span>
<span data-ttu-id="0b102-104">Startet eine Protokollierungs Sitzung der Ereignis Ablauf Verfolgung.</span><span class="sxs-lookup"><span data-stu-id="0b102-104">Start an Event Trace logging session.</span></span>

## <span data-ttu-id="0b102-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0b102-105">SYNTAX</span></span>

```
Start-Trace [-SessionName] <String> [[-OutputFilePath] <String>] [[-ProviderFilePath] <String>]
 [-ETS] [-Format <String>] [-MinBuffers <Int32>] [-MaxBuffers <Int32>]
 [-BufferSizeInKB <Int32>] [-MaxLogFileSizeInMB <Int32>] [<CommonParameters>]
```

## <span data-ttu-id="0b102-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0b102-106">DESCRIPTION</span></span>
<span data-ttu-id="0b102-107">Dieses Cmdlet startet eine Protokollierungs Sitzung für Windows-Ereignis Ablauf Verfolgung.</span><span class="sxs-lookup"><span data-stu-id="0b102-107">This cmdlet starts a Windows Event Trace logging session.</span></span>

<span data-ttu-id="0b102-108">Dieses Cmdlet wird von den folgenden Cmdlets verwendet:</span><span class="sxs-lookup"><span data-stu-id="0b102-108">This cmdlet is used by the following cmdlets:</span></span>

- `Enable-PSWSManCombinedTrace`
- `Enable-WSManTrace`

<span data-ttu-id="0b102-109">Sie müssen dieses Cmdlet aus einer PowerShell-Sitzung mit erhöhten Rechten ausführen.</span><span class="sxs-lookup"><span data-stu-id="0b102-109">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="0b102-110">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="0b102-110">EXAMPLES</span></span>

### <span data-ttu-id="0b102-111">Beispiel 1: Starten einer WSMAN-Ablauf Verfolgungs Protokollierungs Sitzung</span><span class="sxs-lookup"><span data-stu-id="0b102-111">Example 1: Start a WSMan Trace logging session</span></span>

```powershell
Start-Trace -SessionName 'wsmlog' -ETS -OutputFilePath "$env:windir\system32\wsmtraces.log" -Format 'bincirc' -MinBuffers 16 -MaxBuffers 256 -BufferSizeInKb 64 -MaxLogFileSizeInMB 256 -ProviderFilePath "$env:windir\system32\wsmtraceproviders.txt"
```

## <span data-ttu-id="0b102-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0b102-112">PARAMETERS</span></span>

### <span data-ttu-id="0b102-113">-Buffersizeinkb</span><span class="sxs-lookup"><span data-stu-id="0b102-113">-BufferSizeInKB</span></span>
<span data-ttu-id="0b102-114">Puffergröße für Ereignis Ablauf Verfolgungs Sitzung in Kilobyte (KB).</span><span class="sxs-lookup"><span data-stu-id="0b102-114">Event Trace Session buffer size in kilobytes (KB).</span></span>

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

### <span data-ttu-id="0b102-115">-ETS</span><span class="sxs-lookup"><span data-stu-id="0b102-115">-ETS</span></span>
<span data-ttu-id="0b102-116">Direktes Senden von Befehlen an Ereignis Ablauf Verfolgungs Sitzungen, ohne zu speichern oder zu planen.</span><span class="sxs-lookup"><span data-stu-id="0b102-116">Send commands to Event Trace Sessions directly without saving or scheduling.</span></span>

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

### <span data-ttu-id="0b102-117">-Format</span><span class="sxs-lookup"><span data-stu-id="0b102-117">-Format</span></span>
<span data-ttu-id="0b102-118">Gibt das Protokoll Format für den Datensammler an.</span><span class="sxs-lookup"><span data-stu-id="0b102-118">Specifies the log format for the data collector.</span></span> <span data-ttu-id="0b102-119">Beim SQL-Datenbankformat muss die Option **outputfilepath** in der Befehlszeile mit dem Wert verwendet werden `dsn!log` .</span><span class="sxs-lookup"><span data-stu-id="0b102-119">For SQL database format, you must use the **OutputFilePath** option in the command line with the `dsn!log` value.</span></span> <span data-ttu-id="0b102-120">Der Standardwert ist Binary (bin).</span><span class="sxs-lookup"><span data-stu-id="0b102-120">The default is binary (bin).</span></span> <span data-ttu-id="0b102-121">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="0b102-121">The possible values are:</span></span>

- <span data-ttu-id="0b102-122">bin-Binary</span><span class="sxs-lookup"><span data-stu-id="0b102-122">bin - binary</span></span>
- <span data-ttu-id="0b102-123">bincirc-Binary mit zirkulärer Protokollierung</span><span class="sxs-lookup"><span data-stu-id="0b102-123">bincirc - binary with circular logging</span></span>
- <span data-ttu-id="0b102-124">CSV-durch Trennzeichen getrennte Werte</span><span class="sxs-lookup"><span data-stu-id="0b102-124">csv - Comma-separated values</span></span>
- <span data-ttu-id="0b102-125">TSV-durch Tabstopps getrennte Werte</span><span class="sxs-lookup"><span data-stu-id="0b102-125">tsv - Tab-separated values</span></span>
- <span data-ttu-id="0b102-126">SQL-SQL-Datenbank</span><span class="sxs-lookup"><span data-stu-id="0b102-126">sql - SQL database</span></span>

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

### <span data-ttu-id="0b102-127">-MaxBuffers</span><span class="sxs-lookup"><span data-stu-id="0b102-127">-MaxBuffers</span></span>
<span data-ttu-id="0b102-128">Legt die maximale Anzahl der Sitzungs Puffer für die Ereignis Ablauf Verfolgung fest.</span><span class="sxs-lookup"><span data-stu-id="0b102-128">Sets the maximum number of Event Trace Session buffers.</span></span>

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

### <span data-ttu-id="0b102-129">-Maxlogfilesizeinmb</span><span class="sxs-lookup"><span data-stu-id="0b102-129">-MaxLogFileSizeInMB</span></span>
<span data-ttu-id="0b102-130">Legt die maximale Protokolldatei Größe in Megabyte (MB) oder die Anzahl von Datensätzen für SQL-Protokolle fest.</span><span class="sxs-lookup"><span data-stu-id="0b102-130">Sets the maximum log file size in megabytes (MB) or number of records for SQL logs.</span></span>

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

### <span data-ttu-id="0b102-131">-Minbuffers</span><span class="sxs-lookup"><span data-stu-id="0b102-131">-MinBuffers</span></span>
<span data-ttu-id="0b102-132">Legt die Mindestanzahl von Sitzungs Puffern für die Ereignis Ablauf Verfolgung fest.</span><span class="sxs-lookup"><span data-stu-id="0b102-132">Sets the minimum number of Event Trace Session buffers.</span></span>

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

### <span data-ttu-id="0b102-133">-Outputfilepath</span><span class="sxs-lookup"><span data-stu-id="0b102-133">-OutputFilePath</span></span>
<span data-ttu-id="0b102-134">Der Pfad der Ausgabeprotokoll Datei oder der DSN und der Protokoll Satz Name in einer SQL-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="0b102-134">Path of the output log file or the DSN and log set name in a SQL database.</span></span> <span data-ttu-id="0b102-135">Der Standardpfad lautet `$env:systemdrive\PerfLogs\Admin`.</span><span class="sxs-lookup"><span data-stu-id="0b102-135">The default path is `$env:systemdrive\PerfLogs\Admin`.</span></span>

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

### <span data-ttu-id="0b102-136">-Providerfilepath</span><span class="sxs-lookup"><span data-stu-id="0b102-136">-ProviderFilePath</span></span>
<span data-ttu-id="0b102-137">Datei mit mehreren Ereignis Ablauf Verfolgungs Anbietern, die aktiviert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0b102-137">File listing multiple Event Trace providers to enable.</span></span>

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

### <span data-ttu-id="0b102-138">-Sessionname</span><span class="sxs-lookup"><span data-stu-id="0b102-138">-SessionName</span></span>
<span data-ttu-id="0b102-139">Der Name der Ereignis Ablauf Verfolgungs Sitzung.</span><span class="sxs-lookup"><span data-stu-id="0b102-139">The name of the Event Trace session.</span></span> <span data-ttu-id="0b102-140">Um eine Ablauf Verfolgungs Sitzung zu verhindern, müssen Sie den Sitzungs Namen kennen.</span><span class="sxs-lookup"><span data-stu-id="0b102-140">To stop a trace session you must know the session name.</span></span>

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

### <span data-ttu-id="0b102-141">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0b102-141">CommonParameters</span></span>

<span data-ttu-id="0b102-142">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0b102-142">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0b102-143">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0b102-143">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0b102-144">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="0b102-144">INPUTS</span></span>

### <span data-ttu-id="0b102-145">Keine</span><span class="sxs-lookup"><span data-stu-id="0b102-145">None</span></span>

## <span data-ttu-id="0b102-146">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="0b102-146">OUTPUTS</span></span>

### <span data-ttu-id="0b102-147">Keine</span><span class="sxs-lookup"><span data-stu-id="0b102-147">None</span></span>

## <span data-ttu-id="0b102-148">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="0b102-148">NOTES</span></span>

## <span data-ttu-id="0b102-149">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="0b102-149">RELATED LINKS</span></span>

[<span data-ttu-id="0b102-150">Ereignis Ablauf Verfolgung</span><span class="sxs-lookup"><span data-stu-id="0b102-150">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="0b102-151">Stop-Trace</span><span class="sxs-lookup"><span data-stu-id="0b102-151">Stop-Trace</span></span>](stop-trace.md)

[<span data-ttu-id="0b102-152">Disable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="0b102-152">Disable-PSWSManCombinedTrace</span></span>](Disable-PSWSManCombinedTrace.md)

[<span data-ttu-id="0b102-153">Disable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="0b102-153">Disable-WSManTrace</span></span>](Disable-WSManTrace.md)

[<span data-ttu-id="0b102-154">Enable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="0b102-154">Enable-PSWSManCombinedTrace</span></span>](Enable-PSWSManCombinedTrace.md)

[<span data-ttu-id="0b102-155">Enable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="0b102-155">Enable-WSManTrace</span></span>](Enable-WSManTrace.md)

