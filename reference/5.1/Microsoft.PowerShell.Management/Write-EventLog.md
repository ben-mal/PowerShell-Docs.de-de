---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/write-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-EventLog
ms.openlocfilehash: 051f02b00144805569d5130686a51a0f42b64b00
ms.sourcegitcommit: f5986121386c81acddcf324eb0526d7d092bcc8f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/20/2021
ms.locfileid: "98584629"
---
# <span data-ttu-id="21b96-103">Write-EventLog</span><span class="sxs-lookup"><span data-stu-id="21b96-103">Write-EventLog</span></span>

## <span data-ttu-id="21b96-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="21b96-104">SYNOPSIS</span></span>
<span data-ttu-id="21b96-105">Schreibt ein Ereignis in ein Ereignisprotokoll.</span><span class="sxs-lookup"><span data-stu-id="21b96-105">Writes an event to an event log.</span></span>

## <span data-ttu-id="21b96-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="21b96-106">SYNTAX</span></span>

```
Write-EventLog [-LogName] <String> [-Source] <String> [[-EntryType] <EventLogEntryType>] [-Category <Int16>]
 [-EventId] <Int32> [-Message] <String> [-RawData <Byte[]>] [-ComputerName <String>] [<CommonParameters>]
```

## <span data-ttu-id="21b96-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="21b96-107">DESCRIPTION</span></span>

<span data-ttu-id="21b96-108">Mit dem- `Write-EventLog` Cmdlet wird ein Ereignis in ein Ereignisprotokoll geschrieben.</span><span class="sxs-lookup"><span data-stu-id="21b96-108">The `Write-EventLog` cmdlet writes an event to an event log.</span></span>

<span data-ttu-id="21b96-109">Damit ein Ereignis in ein Ereignisprotokoll geschrieben werden kann, muss das Ereignisprotokoll auf dem Computer vorhanden sein, und die Quelle muss für das Ereignisprotokoll registriert sein.</span><span class="sxs-lookup"><span data-stu-id="21b96-109">To write an event to an event log, the event log must exist on the computer and the source must be registered for the event log.</span></span>

<span data-ttu-id="21b96-110">Die Cmdlets, die das **EventLog** -Substantiv (die **EventLog** -Cmdlets) enthalten, funktionieren nur in klassischen Ereignisprotokollen.</span><span class="sxs-lookup"><span data-stu-id="21b96-110">The cmdlets that contain the **EventLog** noun (the **EventLog** cmdlets) work only on classic event logs.</span></span> <span data-ttu-id="21b96-111">Verwenden Sie das-Cmdlet, um Ereignisse aus Protokollen zu erhalten, in denen die Windows-Ereignisprotokoll Technologie in Windows Vista und höheren Versionen des Windows-Betriebssystems verwendet wird `Get-WinEvent` .</span><span class="sxs-lookup"><span data-stu-id="21b96-111">To get events from logs that use the Windows Event Log technology in Windows Vista and later versions of the Windows operating system, use the `Get-WinEvent` cmdlet.</span></span>

## <span data-ttu-id="21b96-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="21b96-112">EXAMPLES</span></span>

### <span data-ttu-id="21b96-113">Beispiel 1: Schreiben eines Ereignisses in das Anwendungs Ereignisprotokoll</span><span class="sxs-lookup"><span data-stu-id="21b96-113">Example 1: Write an event to the Application event log</span></span>

```
PS C:\> Write-EventLog -LogName "Application" -Source "MyApp" -EventID 3001 -EntryType Information -Message "MyApp added a user-requested feature to the display." -Category 1 -RawData 10,20
```

<span data-ttu-id="21b96-114">Dieser Befehl schreibt ein Ereignis aus der Quelle %%amp;quot;MyApp%%amp;quot; in das Anwendungsereignisprotokoll.</span><span class="sxs-lookup"><span data-stu-id="21b96-114">This command writes an event from the MyApp source to the Application event log.</span></span>

### <span data-ttu-id="21b96-115">Beispiel 2: Schreiben eines Ereignisses in das Anwendungs Ereignisprotokoll eines Remote Computers</span><span class="sxs-lookup"><span data-stu-id="21b96-115">Example 2: Write an event to the Application event log of a remote computer</span></span>

```
PS C:\> Write-EventLog -ComputerName "Server01" -LogName Application -Source "MyApp" -EventID 3001 -Message "MyApp added a user-requested feature to the display."
```

<span data-ttu-id="21b96-116">Dieser Befehl schreibt ein Ereignis aus der Quelle %%amp;quot;MyApp%%amp;quot; in das Anwendungsereignisprotokoll auf dem Remotecomputer %%amp;quot;Server01%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="21b96-116">This command writes an event from the MyApp source to the Application event log on the Server01 remote computer.</span></span>

## <span data-ttu-id="21b96-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="21b96-117">PARAMETERS</span></span>

### <span data-ttu-id="21b96-118">-Kategorie</span><span class="sxs-lookup"><span data-stu-id="21b96-118">-Category</span></span>

<span data-ttu-id="21b96-119">Gibt eine Aufgabenkategorie für das Ereignis an.</span><span class="sxs-lookup"><span data-stu-id="21b96-119">Specifies a task category for the event.</span></span> <span data-ttu-id="21b96-120">Geben Sie eine ganze Zahl ein, die den Zeichenfolgen in der Kategoriemeldungsdatei für das Ereignisprotokoll zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="21b96-120">Enter an integer that is associated with the strings in the category message file for the event log.</span></span>

```yaml
Type: System.Int16
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="21b96-121">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="21b96-121">-ComputerName</span></span>

<span data-ttu-id="21b96-122">Gibt einen Remotecomputer an.</span><span class="sxs-lookup"><span data-stu-id="21b96-122">Specifies a remote computer.</span></span> <span data-ttu-id="21b96-123">Die Standardeinstellung ist der lokale Computer.</span><span class="sxs-lookup"><span data-stu-id="21b96-123">The default is the local computer.</span></span>

<span data-ttu-id="21b96-124">Geben Sie den NetBIOS-Namen, eine IP-Adresse oder den vollqualifizierten Domänennamen eines Remotecomputers ein.</span><span class="sxs-lookup"><span data-stu-id="21b96-124">Type the NetBIOS name, an IP address, or a fully qualified domain name of a remote computer.</span></span>

<span data-ttu-id="21b96-125">Dieser Parameter beruht nicht auf Windows PowerShell-Remoting.</span><span class="sxs-lookup"><span data-stu-id="21b96-125">This parameter does not rely on Windows PowerShell remoting.</span></span> <span data-ttu-id="21b96-126">Sie können den Computer **Name** -Parameter des `Get-EventLog` Cmdlets auch dann verwenden, wenn der Computer nicht für das Ausführen von Remote Befehlen konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="21b96-126">You can use the **ComputerName** parameter of the `Get-EventLog` cmdlet even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: CN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="21b96-127">-EntryType</span><span class="sxs-lookup"><span data-stu-id="21b96-127">-EntryType</span></span>

<span data-ttu-id="21b96-128">Gibt den Eintragstyp des Ereignisses an.</span><span class="sxs-lookup"><span data-stu-id="21b96-128">Specifies the entry type of the event.</span></span> <span data-ttu-id="21b96-129">Die zulässigen Werte für diesen Parameter sind: Error, Warning, Information, Success Audit und FAILUREAUDIT.</span><span class="sxs-lookup"><span data-stu-id="21b96-129">The acceptable values for this parameter are: Error, Warning, Information, SuccessAudit, and FailureAudit.</span></span> <span data-ttu-id="21b96-130">Der Standardwert ist %%amp;quot;Information%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="21b96-130">The default value is Information.</span></span>

<span data-ttu-id="21b96-131">Eine Beschreibung der Werte finden Sie unter [EventLogEntryType-Enumeration](/dotnet/api/system.diagnostics.eventlogentrytype).</span><span class="sxs-lookup"><span data-stu-id="21b96-131">For a description of the values, see [EventLogEntryType Enumeration](/dotnet/api/system.diagnostics.eventlogentrytype).</span></span>

```yaml
Type: System.Diagnostics.EventLogEntryType
Parameter Sets: (All)
Aliases: ET
Accepted values: Error, Information, FailureAudit, SuccessAudit, Warning

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="21b96-132">-EventID</span><span class="sxs-lookup"><span data-stu-id="21b96-132">-EventId</span></span>

<span data-ttu-id="21b96-133">Gibt den Ereignisbezeichner an.</span><span class="sxs-lookup"><span data-stu-id="21b96-133">Specifies the event identifier.</span></span> <span data-ttu-id="21b96-134">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="21b96-134">This parameter is required.</span></span> <span data-ttu-id="21b96-135">Der maximale Wert für den **EventID-** Parameter ist 65535.</span><span class="sxs-lookup"><span data-stu-id="21b96-135">The maximum value for the **EventId** parameter is 65535.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: ID, EID

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="21b96-136">-LogName</span><span class="sxs-lookup"><span data-stu-id="21b96-136">-LogName</span></span>

<span data-ttu-id="21b96-137">Gibt den Namen des Protokolls an, in das das Ereignis geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="21b96-137">Specifies the name of the log to which the event is written.</span></span> <span data-ttu-id="21b96-138">Geben Sie den Protokollnamen ein.</span><span class="sxs-lookup"><span data-stu-id="21b96-138">Enter the log name.</span></span> <span data-ttu-id="21b96-139">Der Protokoll Name ist der Wert der **Log** -Eigenschaft, nicht der **LogDisplayName**.</span><span class="sxs-lookup"><span data-stu-id="21b96-139">The log name is the value of the **Log** property, not the **LogDisplayName**.</span></span> <span data-ttu-id="21b96-140">Platzhalterzeichen sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="21b96-140">Wildcard characters are not permitted.</span></span>
<span data-ttu-id="21b96-141">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="21b96-141">This parameter is required.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: LN

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="21b96-142">-Meldung</span><span class="sxs-lookup"><span data-stu-id="21b96-142">-Message</span></span>

<span data-ttu-id="21b96-143">Gibt die Ereignismeldung an.</span><span class="sxs-lookup"><span data-stu-id="21b96-143">Specifies the event message.</span></span> <span data-ttu-id="21b96-144">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="21b96-144">This parameter is required.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: MSG

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="21b96-145">-RawData</span><span class="sxs-lookup"><span data-stu-id="21b96-145">-RawData</span></span>

<span data-ttu-id="21b96-146">Gibt die dem Ereignis zugeordneten Binärdaten in Bytes an.</span><span class="sxs-lookup"><span data-stu-id="21b96-146">Specifies the binary data that is associated with the event, in bytes.</span></span>

```yaml
Type: System.Byte[]
Parameter Sets: (All)
Aliases: RD

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="21b96-147">-Source</span><span class="sxs-lookup"><span data-stu-id="21b96-147">-Source</span></span>

<span data-ttu-id="21b96-148">Gibt die Ereignisquelle an. Dabei handelt es sich normalerweise um den Namen der Anwendung, die das Ereignis in das Protokoll schreibt.</span><span class="sxs-lookup"><span data-stu-id="21b96-148">Specifies the event source, which is typically the name of the application that is writing the event to the log.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: SRC

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="21b96-149">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="21b96-149">CommonParameters</span></span>

<span data-ttu-id="21b96-150">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="21b96-150">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="21b96-151">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="21b96-151">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="21b96-152">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="21b96-152">INPUTS</span></span>

### <span data-ttu-id="21b96-153">Keine</span><span class="sxs-lookup"><span data-stu-id="21b96-153">None</span></span>

<span data-ttu-id="21b96-154">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="21b96-154">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="21b96-155">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="21b96-155">OUTPUTS</span></span>

### <span data-ttu-id="21b96-156">System. Diagnostics. EventLogEntry</span><span class="sxs-lookup"><span data-stu-id="21b96-156">System.Diagnostics.EventLogEntry</span></span>

<span data-ttu-id="21b96-157">Dieses Cmdlet gibt Objekte zurück, die die Ereignisse in den Protokollen darstellen.</span><span class="sxs-lookup"><span data-stu-id="21b96-157">This cmdlet returns objects that represents the events in the logs.</span></span>

## <span data-ttu-id="21b96-158">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="21b96-158">NOTES</span></span>

<span data-ttu-id="21b96-159">Für einige Windows-Ereignisprotokolle sind für das Schreiben von Ereignissen Administratorrechte erforderlich.</span><span class="sxs-lookup"><span data-stu-id="21b96-159">For some Windows event logs, writing events requires administrator rights.</span></span> <span data-ttu-id="21b96-160">Sie müssen PowerShell mit der Option **als Administrator ausführen** starten.</span><span class="sxs-lookup"><span data-stu-id="21b96-160">You must start PowerShell using the **Run as Administrator** option.</span></span>

## <span data-ttu-id="21b96-161">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="21b96-161">RELATED LINKS</span></span>

[<span data-ttu-id="21b96-162">Clear-EventLog</span><span class="sxs-lookup"><span data-stu-id="21b96-162">Clear-EventLog</span></span>](Clear-EventLog.md)

[<span data-ttu-id="21b96-163">Get-EventLog</span><span class="sxs-lookup"><span data-stu-id="21b96-163">Get-EventLog</span></span>](Get-EventLog.md)

[<span data-ttu-id="21b96-164">Limit-EventLog</span><span class="sxs-lookup"><span data-stu-id="21b96-164">Limit-EventLog</span></span>](Limit-EventLog.md)

[<span data-ttu-id="21b96-165">New-EventLog</span><span class="sxs-lookup"><span data-stu-id="21b96-165">New-EventLog</span></span>](New-EventLog.md)

[<span data-ttu-id="21b96-166">Remove-EventLog</span><span class="sxs-lookup"><span data-stu-id="21b96-166">Remove-EventLog</span></span>](Remove-EventLog.md)

[<span data-ttu-id="21b96-167">Show-EventLog</span><span class="sxs-lookup"><span data-stu-id="21b96-167">Show-EventLog</span></span>](Show-EventLog.md)

[<span data-ttu-id="21b96-168">Write-EventLog</span><span class="sxs-lookup"><span data-stu-id="21b96-168">Write-EventLog</span></span>](Write-EventLog.md)
