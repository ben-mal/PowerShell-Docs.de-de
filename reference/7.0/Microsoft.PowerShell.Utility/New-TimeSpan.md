---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 5/1/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-timespan?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-TimeSpan
ms.openlocfilehash: 7e96437c67180eaac0e3163eaf799b34de2b903f
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210348"
---
# <span data-ttu-id="d8ae3-103">New-TimeSpan</span><span class="sxs-lookup"><span data-stu-id="d8ae3-103">New-TimeSpan</span></span>

## <span data-ttu-id="d8ae3-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="d8ae3-104">SYNOPSIS</span></span>
<span data-ttu-id="d8ae3-105">Erstellt ein TimeSpan-Objekt.</span><span class="sxs-lookup"><span data-stu-id="d8ae3-105">Creates a TimeSpan object.</span></span>

## <span data-ttu-id="d8ae3-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d8ae3-106">SYNTAX</span></span>

### <span data-ttu-id="d8ae3-107">Datum (Standard)</span><span class="sxs-lookup"><span data-stu-id="d8ae3-107">Date (Default)</span></span>

```
New-TimeSpan [[-Start] <DateTime>] [[-End] <DateTime>] [<CommonParameters>]
```

### <span data-ttu-id="d8ae3-108">Zeit</span><span class="sxs-lookup"><span data-stu-id="d8ae3-108">Time</span></span>

```
New-TimeSpan [-Days <Int32>] [-Hours <Int32>] [-Minutes <Int32>] [-Seconds <Int32>] [<CommonParameters>]
```

## <span data-ttu-id="d8ae3-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d8ae3-109">DESCRIPTION</span></span>

<span data-ttu-id="d8ae3-110">Das- `New-TimeSpan` Cmdlet erstellt ein **TimeSpan** -Objekt, das ein Zeitintervall darstellt.</span><span class="sxs-lookup"><span data-stu-id="d8ae3-110">The `New-TimeSpan` cmdlet creates a **TimeSpan** object that represents a time interval.</span></span>
<span data-ttu-id="d8ae3-111">Mit einem **TimeSpan** -Objekt können Sie Zeit aus **DateTime** -Objekten addieren oder subtrahieren.</span><span class="sxs-lookup"><span data-stu-id="d8ae3-111">You can use a **TimeSpan** object to add or subtract time from **DateTime** objects.</span></span>

<span data-ttu-id="d8ae3-112">Ohne Parameter gibt ein `New-TimeSpan` Befehl ein **TimeSpan** -Objekt zurück, das ein Zeitintervall von 0 (null) darstellt.</span><span class="sxs-lookup"><span data-stu-id="d8ae3-112">Without parameters, a `New-TimeSpan` command returns a **TimeSpan** object that represents a time interval of zero.</span></span>

## <span data-ttu-id="d8ae3-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="d8ae3-113">EXAMPLES</span></span>

### <span data-ttu-id="d8ae3-114">Beispiel 1: Erstellen eines TimeSpan-Objekts für eine angegebene Dauer</span><span class="sxs-lookup"><span data-stu-id="d8ae3-114">Example 1: Create a TimeSpan object for a specified duration</span></span>

<span data-ttu-id="d8ae3-115">Dieser Befehl erstellt ein **TimeSpan** -Objekt mit einer Dauer von 1 Stunde und 25 Minuten und speichert es in einer Variablen mit dem Namen `$TimeSpan` .</span><span class="sxs-lookup"><span data-stu-id="d8ae3-115">This command creates a **TimeSpan** object with a duration of 1 hour and 25 minutes and stores it in a variable named `$TimeSpan`.</span></span> <span data-ttu-id="d8ae3-116">Es zeigt eine Darstellung des **TimeSpan** -Objekts an.</span><span class="sxs-lookup"><span data-stu-id="d8ae3-116">It displays a representation of the **TimeSpan** object.</span></span>

```powershell
$TimeSpan = New-TimeSpan -Hours 1 -Minutes 25
$TimeSpan
```

```Output
Days              : 0
Hours             : 1
Minutes           : 25
Seconds           : 0
Milliseconds      : 0
Ticks             : 51000000000
TotalDays         : 0.0590277777777778
TotalHours        : 1.41666666666667
TotalMinutes      : 85
TotalSeconds      : 5100
TotalMilliseconds : 5100000
```

### <span data-ttu-id="d8ae3-117">Beispiel 2: Erstellen eines TimeSpan-Objekts für ein Zeitintervall</span><span class="sxs-lookup"><span data-stu-id="d8ae3-117">Example 2: Create a TimeSpan object for a time interval</span></span>

<span data-ttu-id="d8ae3-118">In diesem Beispiel wird ein neues **TimeSpan** -Objekt erstellt, das das Intervall zwischen dem Zeitpunkt, zu dem der Befehl ausgeführt wird, und dem 1. Januar 2010 darstellt.</span><span class="sxs-lookup"><span data-stu-id="d8ae3-118">This example creates a new **TimeSpan** object that represents the interval between the time that the command is run and January 1, 2010.</span></span>

<span data-ttu-id="d8ae3-119">Für diesen Befehl ist der **Start** -Parameter nicht erforderlich, da der Standardwert des **Start** -Parameters das aktuelle Datum und die aktuelle Uhrzeit ist.</span><span class="sxs-lookup"><span data-stu-id="d8ae3-119">This command does not require the **Start** parameter, because the default value of the **Start** parameter is the current date and time.</span></span>

```powershell
New-TimeSpan -End (Get-Date -Year 2010 -Month 1 -Day 1)
```

### <span data-ttu-id="d8ae3-120">Beispiel 3: erhalten Sie das Datum 90 Tage ab dem aktuellen Datum.</span><span class="sxs-lookup"><span data-stu-id="d8ae3-120">Example 3: Get the date 90 days from the current date</span></span>

```powershell
$90days = New-TimeSpan -Days 90
(Get-Date) + $90days
```

<span data-ttu-id="d8ae3-121">Diese Befehle geben das Datum zurück, das 90 Tage nach dem aktuellen Datum liegt.</span><span class="sxs-lookup"><span data-stu-id="d8ae3-121">These commands return the date that is 90 days after the current date.</span></span>

### <span data-ttu-id="d8ae3-122">Beispiel 4: Ermitteln der Zeitspanne seit dem Aktualisieren einer Datei</span><span class="sxs-lookup"><span data-stu-id="d8ae3-122">Example 4: Discover the TimeSpan since a file was updated</span></span>

<span data-ttu-id="d8ae3-123">Dieser Befehl gibt Aufschluss darüber, wie lange es seit der letzten Aktualisierung der [About_Remote](../Microsoft.PowerShell.Core/About/about_Remote.md) Hilfedatei war.</span><span class="sxs-lookup"><span data-stu-id="d8ae3-123">This command tells you how long it has been since the [about_remote](../Microsoft.PowerShell.Core/About/about_Remote.md) help file was last updated.</span></span>
<span data-ttu-id="d8ae3-124">Sie können dieses Befehls Format für jede beliebige Datei oder ein beliebiges anderes Objekt verwenden, das über eine **LastWrite Time** -Eigenschaft verfügt.</span><span class="sxs-lookup"><span data-stu-id="d8ae3-124">You can use this command format on any file, or any other object that has a **LastWriteTime** property.</span></span>

<span data-ttu-id="d8ae3-125">Dieser Befehl funktioniert, da der **Start** -Parameter von `New-TimeSpan` einen Alias von " **lastschreitetime** " aufweist.</span><span class="sxs-lookup"><span data-stu-id="d8ae3-125">This command works because the **Start** parameter of `New-TimeSpan` has an alias of **LastWriteTime** .</span></span> <span data-ttu-id="d8ae3-126">Wenn Sie ein Objekt mit der **LastWrite-Time** -Eigenschaft an übergeben `New-TimeSpan` , verwendet PowerShell den Wert der **LastWrite-Time** -Eigenschaft als Wert des **Start** -Parameters.</span><span class="sxs-lookup"><span data-stu-id="d8ae3-126">When you pipe an object that has a **LastWriteTime** property to `New-TimeSpan`, PowerShell uses the value of the **LastWriteTime** property as the value of the **Start** parameter.</span></span>

```powershell
Get-ChildItem $PSHOME\en-us\about_remote.help.txt | New-TimeSpan
```

```Output
Days              : 321
Hours             : 21
Minutes           : 59
Seconds           : 22
Milliseconds      : 312
Ticks             : 278135623127728
TotalDays         : 321.916230471907
TotalHours        : 7725.98953132578
TotalMinutes      : 463559.371879547
TotalSeconds      : 27813562.3127728
TotalMilliseconds : 27813562312.7728
```

## <span data-ttu-id="d8ae3-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d8ae3-127">PARAMETERS</span></span>

### <span data-ttu-id="d8ae3-128">-Days</span><span class="sxs-lookup"><span data-stu-id="d8ae3-128">-Days</span></span>

<span data-ttu-id="d8ae3-129">Gibt die Tage in der Zeitspanne an.</span><span class="sxs-lookup"><span data-stu-id="d8ae3-129">Specifies the days in the time span.</span></span>
<span data-ttu-id="d8ae3-130">Der Standardwert ist 0.</span><span class="sxs-lookup"><span data-stu-id="d8ae3-130">The default value is 0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: Time
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d8ae3-131">-Ende</span><span class="sxs-lookup"><span data-stu-id="d8ae3-131">-End</span></span>

<span data-ttu-id="d8ae3-132">Gibt das Ende einer Zeitspanne an.</span><span class="sxs-lookup"><span data-stu-id="d8ae3-132">Specifies the end of a time span.</span></span>
<span data-ttu-id="d8ae3-133">Der Standardwert ist das aktuelle Datum und die aktuelle Uhrzeit.</span><span class="sxs-lookup"><span data-stu-id="d8ae3-133">The default value is the current date and time.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: Date
Aliases:

Required: False
Position: 1
Default value: Current date and time
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d8ae3-134">-Stunden</span><span class="sxs-lookup"><span data-stu-id="d8ae3-134">-Hours</span></span>

<span data-ttu-id="d8ae3-135">Gibt die Stunden in der Zeitspanne an.</span><span class="sxs-lookup"><span data-stu-id="d8ae3-135">Specifies the hours in the time span.</span></span>
<span data-ttu-id="d8ae3-136">Der Standardwert ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="d8ae3-136">The default value is zero.</span></span>

```yaml
Type: System.Int32
Parameter Sets: Time
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d8ae3-137">-Minuten</span><span class="sxs-lookup"><span data-stu-id="d8ae3-137">-Minutes</span></span>

<span data-ttu-id="d8ae3-138">Gibt die Minuten in der Zeitspanne an.</span><span class="sxs-lookup"><span data-stu-id="d8ae3-138">Specifies the minutes in the time span.</span></span>
<span data-ttu-id="d8ae3-139">Der Standardwert ist 0.</span><span class="sxs-lookup"><span data-stu-id="d8ae3-139">The default value is 0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: Time
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d8ae3-140">-Sekunden</span><span class="sxs-lookup"><span data-stu-id="d8ae3-140">-Seconds</span></span>

<span data-ttu-id="d8ae3-141">Gibt die Länge der Zeitspanne in Sekunden an.</span><span class="sxs-lookup"><span data-stu-id="d8ae3-141">Specifies the length of the time span in seconds.</span></span>
<span data-ttu-id="d8ae3-142">Der Standardwert ist 0.</span><span class="sxs-lookup"><span data-stu-id="d8ae3-142">The default value is 0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: Time
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d8ae3-143">-Starten</span><span class="sxs-lookup"><span data-stu-id="d8ae3-143">-Start</span></span>

<span data-ttu-id="d8ae3-144">Gibt den Anfang einer Zeitspanne an.</span><span class="sxs-lookup"><span data-stu-id="d8ae3-144">Specifies the start of a time span.</span></span>
<span data-ttu-id="d8ae3-145">Geben Sie eine Zeichenfolge ein, die das Datum und die Uhrzeit darstellt, z. b. "3/15/09" oder ein **DateTime** -Objekt, z. b. eines von einem `Get-Date` Befehl.</span><span class="sxs-lookup"><span data-stu-id="d8ae3-145">Enter a string that represents the date and time, such as "3/15/09" or a **DateTime** object, such as one from a `Get-Date` command.</span></span> <span data-ttu-id="d8ae3-146">Der Standardwert ist das aktuelle Datum und die aktuelle Uhrzeit.</span><span class="sxs-lookup"><span data-stu-id="d8ae3-146">The default value is the current date and time.</span></span>

<span data-ttu-id="d8ae3-147">Sie können " **Start** " oder dessen Alias " **lastschreitetime** " verwenden.</span><span class="sxs-lookup"><span data-stu-id="d8ae3-147">You can use **Start** or its alias, **LastWriteTime** .</span></span>
<span data-ttu-id="d8ae3-148">Mit dem **LastWrite-Time** -Alias können Sie Objekte, die über eine **lastschreitetime** -Eigenschaft (z. b. Dateien im Dateisystem) verfügen, `[System.Io.FileIO]` an den **Start** -Parameter von übergeben `New-TimeSpan` .</span><span class="sxs-lookup"><span data-stu-id="d8ae3-148">The **LastWriteTime** alias lets you pipe objects that have a **LastWriteTime** property, such as files in the file system `[System.Io.FileIO]`, to the **Start** parameter of `New-TimeSpan`.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: Date
Aliases: LastWriteTime

Required: False
Position: 0
Default value: Current date and time
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="d8ae3-149">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d8ae3-149">CommonParameters</span></span>

<span data-ttu-id="d8ae3-150">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d8ae3-150">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d8ae3-151">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="d8ae3-151">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="d8ae3-152">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="d8ae3-152">INPUTS</span></span>

### <span data-ttu-id="d8ae3-153">System.DateTime</span><span class="sxs-lookup"><span data-stu-id="d8ae3-153">System.DateTime</span></span>

<span data-ttu-id="d8ae3-154">Sie können ein **DateTime** -Objekt, das diese Startzeit darstellt, an die Pipeline übergeben `New-TimeSpan` .</span><span class="sxs-lookup"><span data-stu-id="d8ae3-154">You can pipe a **DateTime** object that represents that start time to `New-TimeSpan`.</span></span>

## <span data-ttu-id="d8ae3-155">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="d8ae3-155">OUTPUTS</span></span>

### <span data-ttu-id="d8ae3-156">System.TimeSpan</span><span class="sxs-lookup"><span data-stu-id="d8ae3-156">System.TimeSpan</span></span>

<span data-ttu-id="d8ae3-157">`New-TimeSpan` Gibt ein-Objekt zurück, das die Zeitspanne darstellt.</span><span class="sxs-lookup"><span data-stu-id="d8ae3-157">`New-TimeSpan` returns an object that represents the time span.</span></span>

## <span data-ttu-id="d8ae3-158">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="d8ae3-158">NOTES</span></span>

## <span data-ttu-id="d8ae3-159">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="d8ae3-159">RELATED LINKS</span></span>

[<span data-ttu-id="d8ae3-160">Get-Date</span><span class="sxs-lookup"><span data-stu-id="d8ae3-160">Get-Date</span></span>](Get-Date.md)

[<span data-ttu-id="d8ae3-161">Set-Date</span><span class="sxs-lookup"><span data-stu-id="d8ae3-161">Set-Date</span></span>](Set-Date.md)
