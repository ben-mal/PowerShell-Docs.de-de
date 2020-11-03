---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 01/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-EventLog
ms.openlocfilehash: 61fafc0670a24fd6ca057e4cf0c7179d90446b07
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214620"
---
# <span data-ttu-id="2c4cf-103">New-EventLog</span><span class="sxs-lookup"><span data-stu-id="2c4cf-103">New-EventLog</span></span>

## <span data-ttu-id="2c4cf-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="2c4cf-104">SYNOPSIS</span></span>
<span data-ttu-id="2c4cf-105">Erstellt ein neues Ereignisprotokoll und eine neue Ereignisquelle auf einem lokalen Computer oder einem Remotecomputer.</span><span class="sxs-lookup"><span data-stu-id="2c4cf-105">Creates a new event log and a new event source on a local or remote computer.</span></span>

## <span data-ttu-id="2c4cf-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2c4cf-106">SYNTAX</span></span>

```
New-EventLog [-LogName] <string> [-Source] <string[]> [[-ComputerName] <string[]>]
  [-CategoryResourceFile <string>] [-MessageResourceFile <string>] [-ParameterResourceFile <string>]
  [<CommonParameters>]
```

## <span data-ttu-id="2c4cf-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2c4cf-107">DESCRIPTION</span></span>

<span data-ttu-id="2c4cf-108">Dieses Cmdlet erstellt ein neues klassisches Ereignisprotokoll auf einem lokalen Computer oder einem Remotecomputer.</span><span class="sxs-lookup"><span data-stu-id="2c4cf-108">This cmdlet creates a new classic event log on a local or remote computer.</span></span> <span data-ttu-id="2c4cf-109">Außerdem kann eine Ereignisquelle registriert werden, die in das neue Protokoll oder in ein vorhandenes Protokoll schreibt.</span><span class="sxs-lookup"><span data-stu-id="2c4cf-109">It can also register an event source that writes to the new log or to an existing log.</span></span>

<span data-ttu-id="2c4cf-110">Die Cmdlets, die das Substantiv %%amp;quot;EventLog%%amp;quot; enthalten (die EventLog-Cmdlets), können nur für klassische Ereignisprotokolle verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2c4cf-110">The cmdlets that contain the EventLog noun (the Event log cmdlets) work only on classic event logs.</span></span>
<span data-ttu-id="2c4cf-111">Verwenden Sie, um Ereignisse aus Protokollen zu erhalten, in denen die Windows-Ereignisprotokoll Technologie in Windows Vista und höheren Versionen von Windows verwendet wird `Get-WinEvent` .</span><span class="sxs-lookup"><span data-stu-id="2c4cf-111">To get events from logs that use the Windows Event Log technology in Windows Vista and later versions of Windows, use `Get-WinEvent`.</span></span>

## <span data-ttu-id="2c4cf-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="2c4cf-112">EXAMPLES</span></span>

### <span data-ttu-id="2c4cf-113">Beispiel 1: Erstellen eines neuen Ereignis Protokolls</span><span class="sxs-lookup"><span data-stu-id="2c4cf-113">Example 1 - create a new event log</span></span>

<span data-ttu-id="2c4cf-114">Mit diesem Befehl wird das Ereignisprotokoll %%amp;quot;TestLog%%amp;quot; auf dem lokalen Computer erstellt und eine neue Quelle dafür registriert.</span><span class="sxs-lookup"><span data-stu-id="2c4cf-114">This command creates the TestLog event log on the local computer and registers a new source for it.</span></span>

```powershell
New-EventLog -source TestApp -LogName TestLog -MessageResourceFile C:\Test\TestApp.dll
```

### <span data-ttu-id="2c4cf-115">Beispiel 2: Hinzufügen einer neuen Ereignis Quelle zu einem vorhandenen Protokoll</span><span class="sxs-lookup"><span data-stu-id="2c4cf-115">Example 2 - add a new event source to an existing log</span></span>

<span data-ttu-id="2c4cf-116">Mit diesem Befehl wird die neue Ereignisquelle %%amp;quot;NewTestApp%%amp;quot; dem Anwendungsprotokoll auf dem Remotecomputer %%amp;quot;Server01%%amp;quot; hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="2c4cf-116">This command adds a new event source, NewTestApp, to the Application log on the Server01 remote computer.</span></span>

```powershell
$file = "C:\Program Files\TestApps\NewTestApp.dll"
New-EventLog -ComputerName Server01 -Source NewTestApp -LogName Application -MessageResourceFile $file -CategoryResourceFile $file
```

<span data-ttu-id="2c4cf-117">Für diesen Befehl muss sich die Datei %%amp;quot;NewTestApp.dll%%amp;quot; auf dem Computer %%amp;quot;Server01%%amp;quot; befinden.</span><span class="sxs-lookup"><span data-stu-id="2c4cf-117">The command requires that the NewTestApp.dll file is located on the Server01 computer.</span></span>

## <span data-ttu-id="2c4cf-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2c4cf-118">PARAMETERS</span></span>

### <span data-ttu-id="2c4cf-119">-CategoryResourceFile</span><span class="sxs-lookup"><span data-stu-id="2c4cf-119">-CategoryResourceFile</span></span>

<span data-ttu-id="2c4cf-120">Gibt den Pfad zu der Datei an, die Kategoriezeichenfolgen für die Quellereignisse enthält.</span><span class="sxs-lookup"><span data-stu-id="2c4cf-120">Specifies the path to the file that contains category strings for the source events.</span></span> <span data-ttu-id="2c4cf-121">Diese Datei wird auch als Kategoriemeldungsdatei bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="2c4cf-121">This file is also known as the Category Message File.</span></span>

<span data-ttu-id="2c4cf-122">Die Datei muss auf dem Computer vorhanden sein, auf dem das Ereignisprotokoll erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="2c4cf-122">The file must be present on the computer on which the event log is being created.</span></span> <span data-ttu-id="2c4cf-123">Dieser Parameter erstellt und verschiebt keine Dateien.</span><span class="sxs-lookup"><span data-stu-id="2c4cf-123">This parameter does not create or move files.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: CRF

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2c4cf-124">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="2c4cf-124">-ComputerName</span></span>

<span data-ttu-id="2c4cf-125">Erstellt die neuen Ereignisprotokolle auf den angegebenen Computern.</span><span class="sxs-lookup"><span data-stu-id="2c4cf-125">Creates the new event logs on the specified computers.</span></span> <span data-ttu-id="2c4cf-126">Die Standardeinstellung ist der lokale Computer.</span><span class="sxs-lookup"><span data-stu-id="2c4cf-126">The default is the local computer.</span></span>

<span data-ttu-id="2c4cf-127">Den NetBIOS-Namen, die IP-Adresse oder den voll qualifizierten Domänen Namen eines Remote Computers.</span><span class="sxs-lookup"><span data-stu-id="2c4cf-127">The NetBIOS name, IP address, or fully qualified domain name of a remote computer.</span></span>
<span data-ttu-id="2c4cf-128">Um den lokalen Computer anzugeben, geben Sie den Computernamen, einen Punkt (.) oder %%amp;quot;localhost%%amp;quot; ein.</span><span class="sxs-lookup"><span data-stu-id="2c4cf-128">To specify the local computer, type the computer name, a dot (.), or "localhost".</span></span>

<span data-ttu-id="2c4cf-129">Dieser Parameter beruht nicht auf PowerShell-Remoting.</span><span class="sxs-lookup"><span data-stu-id="2c4cf-129">This parameter does not rely on PowerShell remoting.</span></span> <span data-ttu-id="2c4cf-130">Sie können den **Computername** -Parameter `Get-EventLog` auch dann verwenden, wenn der Computer nicht für das Ausführen von Remote Befehlen konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="2c4cf-130">You can use the **ComputerName** parameter of `Get-EventLog` even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN

Required: False
Position: 3
Default value: Local computer
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2c4cf-131">-LogName</span><span class="sxs-lookup"><span data-stu-id="2c4cf-131">-LogName</span></span>

<span data-ttu-id="2c4cf-132">Gibt den Namen des Ereignisprotokolls an.</span><span class="sxs-lookup"><span data-stu-id="2c4cf-132">Specifies the name of the event log.</span></span>

<span data-ttu-id="2c4cf-133">Wenn das Protokoll nicht vorhanden ist, `New-EventLog` erstellt das Protokoll und verwendet diesen Wert für die Eigenschaften " **Log** " und " **LogDisplayName** " des neuen Ereignis Protokolls.</span><span class="sxs-lookup"><span data-stu-id="2c4cf-133">If the log does not exist, `New-EventLog` creates the log and uses this value for the **Log** and **LogDisplayName** properties of the new event log.</span></span> <span data-ttu-id="2c4cf-134">Wenn das Protokoll vorhanden ist, `New-EventLog` registriert eine neue Quelle für das Ereignisprotokoll.</span><span class="sxs-lookup"><span data-stu-id="2c4cf-134">If the log exists, `New-EventLog` registers a new source for the event log.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: LN

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2c4cf-135">-MessageResourceFile</span><span class="sxs-lookup"><span data-stu-id="2c4cf-135">-MessageResourceFile</span></span>

<span data-ttu-id="2c4cf-136">Gibt den Pfad zu der Datei an, die Formatzeichenfolgen für Nachrichten für die Quellereignisse enthält.</span><span class="sxs-lookup"><span data-stu-id="2c4cf-136">Specifies the path to the file that contains message formatting strings for the source events.</span></span>
<span data-ttu-id="2c4cf-137">Diese Datei wird auch als Ereignismeldungsdatei bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="2c4cf-137">This file is also known as the Event Message File.</span></span>

<span data-ttu-id="2c4cf-138">Die Datei muss auf dem Computer vorhanden sein, auf dem das Ereignisprotokoll erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="2c4cf-138">The file must be present on the computer on which the event log is being created.</span></span>
<span data-ttu-id="2c4cf-139">Dieser Parameter erstellt und verschiebt keine Dateien.</span><span class="sxs-lookup"><span data-stu-id="2c4cf-139">This parameter does not create or move files.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: MRF

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2c4cf-140">-ParameterResourceFile</span><span class="sxs-lookup"><span data-stu-id="2c4cf-140">-ParameterResourceFile</span></span>

<span data-ttu-id="2c4cf-141">Gibt an den Pfad zu der Datei mit Zeichenfolgen an, die für die Parameterersetzungen in Ereignisbeschreibungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2c4cf-141">Specifies the path to the file that contains strings used for parameter substitutions in event descriptions.</span></span> <span data-ttu-id="2c4cf-142">Diese Datei wird auch als Parametermeldungsdatei bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="2c4cf-142">This file is also known as the Parameter Message File.</span></span>

<span data-ttu-id="2c4cf-143">Die Datei muss auf dem Computer vorhanden sein, auf dem das Ereignisprotokoll erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="2c4cf-143">The file must be present on the computer on which the event log is being created.</span></span>
<span data-ttu-id="2c4cf-144">Dieser Parameter erstellt und verschiebt keine Dateien.</span><span class="sxs-lookup"><span data-stu-id="2c4cf-144">This parameter does not create or move files.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PRF

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2c4cf-145">-Source</span><span class="sxs-lookup"><span data-stu-id="2c4cf-145">-Source</span></span>

<span data-ttu-id="2c4cf-146">Gibt die Namen der Ereignisprotokollquellen an, z. B. Anwendungen, die in das Ereignisprotokoll schreiben.</span><span class="sxs-lookup"><span data-stu-id="2c4cf-146">Specifies the names of the event log sources, such as application programs that write to the event log.</span></span> <span data-ttu-id="2c4cf-147">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2c4cf-147">This parameter is required.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: SRC

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2c4cf-148">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="2c4cf-148">CommonParameters</span></span>

<span data-ttu-id="2c4cf-149">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2c4cf-149">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2c4cf-150">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2c4cf-150">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2c4cf-151">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="2c4cf-151">INPUTS</span></span>

### <span data-ttu-id="2c4cf-152">Keine</span><span class="sxs-lookup"><span data-stu-id="2c4cf-152">None</span></span>

<span data-ttu-id="2c4cf-153">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="2c4cf-153">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="2c4cf-154">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="2c4cf-154">OUTPUTS</span></span>

### <span data-ttu-id="2c4cf-155">System. Diagnostics. EventLogEntry</span><span class="sxs-lookup"><span data-stu-id="2c4cf-155">System.Diagnostics.EventLogEntry</span></span>

## <span data-ttu-id="2c4cf-156">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="2c4cf-156">NOTES</span></span>

<span data-ttu-id="2c4cf-157">Wenn Sie unter `New-EventLog` Windows Vista und höheren Versionen von Windows verwenden möchten, öffnen Sie PowerShell mit der Option "als Administrator ausführen".</span><span class="sxs-lookup"><span data-stu-id="2c4cf-157">To use `New-EventLog` on Windows Vista and later versions of Windows, open PowerShell with the "Run as administrator" option.</span></span>

<span data-ttu-id="2c4cf-158">Zum Erstellen einer Ereignisquelle in Windows Vista, Windows XP Professional oder Windows Server 2003 müssen Sie Mitglied der Gruppe %%amp;quot;Administratoren%%amp;quot; auf dem Computer sein.</span><span class="sxs-lookup"><span data-stu-id="2c4cf-158">To create an event source in Windows Vista, Windows XP Professional, or Windows Server 2003, you must be a member of the Administrators group on the computer.</span></span>

<span data-ttu-id="2c4cf-159">Wenn Sie ein neues Ereignisprotokoll und eine neue Ereignisquelle erstellen, registriert das System die neue Quelle für das neue Protokoll, das Protokoll wird jedoch erst erstellt, wenn der erste Eintrag darin geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="2c4cf-159">When you create a new event log and a new event source, the system registers the new source for the new log, but the log is not created until the first entry is written to it.</span></span>

<span data-ttu-id="2c4cf-160">Das Betriebssystem speichert Ereignisprotokolle als Dateien.</span><span class="sxs-lookup"><span data-stu-id="2c4cf-160">The operating system stores event logs as files.</span></span>

<span data-ttu-id="2c4cf-161">Wenn Sie ein neues Ereignisprotokoll erstellen, wird die zugehörige Datei im `$env:SystemRoot\System32\Config` Verzeichnis auf dem angegebenen Computer gespeichert.</span><span class="sxs-lookup"><span data-stu-id="2c4cf-161">When you create a new event log, the associated file is stored in the `$env:SystemRoot\System32\Config` directory on the specified computer.</span></span>

<span data-ttu-id="2c4cf-162">Der Dateiname ist die ersten acht Zeichen der **Log** -Eigenschaft mit der Dateinamenerweiterung ". evt".</span><span class="sxs-lookup"><span data-stu-id="2c4cf-162">The file name is the first eight characters of the **Log** property with an .evt file name extension.</span></span>

## <span data-ttu-id="2c4cf-163">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="2c4cf-163">RELATED LINKS</span></span>

[<span data-ttu-id="2c4cf-164">Clear-EventLog</span><span class="sxs-lookup"><span data-stu-id="2c4cf-164">Clear-EventLog</span></span>](Clear-EventLog.md)

[<span data-ttu-id="2c4cf-165">Get-EventLog</span><span class="sxs-lookup"><span data-stu-id="2c4cf-165">Get-EventLog</span></span>](Get-EventLog.md)

[<span data-ttu-id="2c4cf-166">Get-WinEvent</span><span class="sxs-lookup"><span data-stu-id="2c4cf-166">Get-WinEvent</span></span>](../Microsoft.PowerShell.Diagnostics/Get-WinEvent.md)

[<span data-ttu-id="2c4cf-167">Limit-EventLog</span><span class="sxs-lookup"><span data-stu-id="2c4cf-167">Limit-EventLog</span></span>](Limit-EventLog.md)

[<span data-ttu-id="2c4cf-168">New-EventLog</span><span class="sxs-lookup"><span data-stu-id="2c4cf-168">New-EventLog</span></span>](New-EventLog.md)

[<span data-ttu-id="2c4cf-169">Remove-EventLog</span><span class="sxs-lookup"><span data-stu-id="2c4cf-169">Remove-EventLog</span></span>](Remove-EventLog.md)

[<span data-ttu-id="2c4cf-170">Show-EventLog</span><span class="sxs-lookup"><span data-stu-id="2c4cf-170">Show-EventLog</span></span>](Show-EventLog.md)

[<span data-ttu-id="2c4cf-171">Write-EventLog</span><span class="sxs-lookup"><span data-stu-id="2c4cf-171">Write-EventLog</span></span>](Write-EventLog.md)
