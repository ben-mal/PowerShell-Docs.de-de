---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 05/01/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-timespan?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-TimeSpan
ms.openlocfilehash: 5808685a5560d1cbf91c6705b90643c35702b28a
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599222"
---
# <span data-ttu-id="044fa-102">New-TimeSpan</span><span class="sxs-lookup"><span data-stu-id="044fa-102">New-TimeSpan</span></span>

## <span data-ttu-id="044fa-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="044fa-103">SYNOPSIS</span></span>
<span data-ttu-id="044fa-104">Erstellt ein TimeSpan-Objekt.</span><span class="sxs-lookup"><span data-stu-id="044fa-104">Creates a TimeSpan object.</span></span>

## <span data-ttu-id="044fa-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="044fa-105">SYNTAX</span></span>

### <span data-ttu-id="044fa-106">Datum (Standard)</span><span class="sxs-lookup"><span data-stu-id="044fa-106">Date (Default)</span></span>

```
New-TimeSpan [[-Start] <DateTime>] [[-End] <DateTime>] [<CommonParameters>]
```

### <span data-ttu-id="044fa-107">Time</span><span class="sxs-lookup"><span data-stu-id="044fa-107">Time</span></span>

```
New-TimeSpan [-Days <Int32>] [-Hours <Int32>] [-Minutes <Int32>] [-Seconds <Int32>] [<CommonParameters>]
```

## <span data-ttu-id="044fa-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="044fa-108">DESCRIPTION</span></span>

<span data-ttu-id="044fa-109">Das- `New-TimeSpan` Cmdlet erstellt ein **TimeSpan** -Objekt, das ein Zeitintervall darstellt.</span><span class="sxs-lookup"><span data-stu-id="044fa-109">The `New-TimeSpan` cmdlet creates a **TimeSpan** object that represents a time interval.</span></span>
<span data-ttu-id="044fa-110">Mit einem **TimeSpan** -Objekt können Sie Zeit aus **DateTime** -Objekten addieren oder subtrahieren.</span><span class="sxs-lookup"><span data-stu-id="044fa-110">You can use a **TimeSpan** object to add or subtract time from **DateTime** objects.</span></span>

<span data-ttu-id="044fa-111">Ohne Parameter gibt ein `New-TimeSpan` Befehl ein **TimeSpan** -Objekt zurück, das ein Zeitintervall von 0 (null) darstellt.</span><span class="sxs-lookup"><span data-stu-id="044fa-111">Without parameters, a `New-TimeSpan` command returns a **TimeSpan** object that represents a time interval of zero.</span></span>

## <span data-ttu-id="044fa-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="044fa-112">EXAMPLES</span></span>

### <span data-ttu-id="044fa-113">Beispiel 1: Erstellen eines TimeSpan-Objekts für eine angegebene Dauer</span><span class="sxs-lookup"><span data-stu-id="044fa-113">Example 1: Create a TimeSpan object for a specified duration</span></span>

<span data-ttu-id="044fa-114">Dieser Befehl erstellt ein **TimeSpan** -Objekt mit einer Dauer von 1 Stunde und 25 Minuten und speichert es in einer Variablen mit dem Namen `$TimeSpan` .</span><span class="sxs-lookup"><span data-stu-id="044fa-114">This command creates a **TimeSpan** object with a duration of 1 hour and 25 minutes and stores it in a variable named `$TimeSpan`.</span></span> <span data-ttu-id="044fa-115">Es zeigt eine Darstellung des **TimeSpan** -Objekts an.</span><span class="sxs-lookup"><span data-stu-id="044fa-115">It displays a representation of the **TimeSpan** object.</span></span>

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

### <span data-ttu-id="044fa-116">Beispiel 2: Erstellen eines TimeSpan-Objekts für ein Zeitintervall</span><span class="sxs-lookup"><span data-stu-id="044fa-116">Example 2: Create a TimeSpan object for a time interval</span></span>

<span data-ttu-id="044fa-117">In diesem Beispiel wird ein neues **TimeSpan** -Objekt erstellt, das das Intervall zwischen dem Zeitpunkt, zu dem der Befehl ausgeführt wird, und dem 1. Januar 2010 darstellt.</span><span class="sxs-lookup"><span data-stu-id="044fa-117">This example creates a new **TimeSpan** object that represents the interval between the time that the command is run and January 1, 2010.</span></span>

<span data-ttu-id="044fa-118">Für diesen Befehl ist der **Start** -Parameter nicht erforderlich, da der Standardwert des **Start** -Parameters das aktuelle Datum und die aktuelle Uhrzeit ist.</span><span class="sxs-lookup"><span data-stu-id="044fa-118">This command does not require the **Start** parameter, because the default value of the **Start** parameter is the current date and time.</span></span>

```powershell
New-TimeSpan -End (Get-Date -Year 2010 -Month 1 -Day 1)
```

### <span data-ttu-id="044fa-119">Beispiel 3: erhalten Sie das Datum 90 Tage ab dem aktuellen Datum.</span><span class="sxs-lookup"><span data-stu-id="044fa-119">Example 3: Get the date 90 days from the current date</span></span>

```powershell
$90days = New-TimeSpan -Days 90
(Get-Date) + $90days
```

<span data-ttu-id="044fa-120">Diese Befehle geben das Datum zurück, das 90 Tage nach dem aktuellen Datum liegt.</span><span class="sxs-lookup"><span data-stu-id="044fa-120">These commands return the date that is 90 days after the current date.</span></span>

### <span data-ttu-id="044fa-121">Beispiel 4: Ermitteln der Zeitspanne seit dem Aktualisieren einer Datei</span><span class="sxs-lookup"><span data-stu-id="044fa-121">Example 4: Discover the TimeSpan since a file was updated</span></span>

<span data-ttu-id="044fa-122">Dieser Befehl gibt Aufschluss darüber, wie lange es seit der letzten Aktualisierung der [About_Remote](../Microsoft.PowerShell.Core/About/about_Remote.md) Hilfedatei war.</span><span class="sxs-lookup"><span data-stu-id="044fa-122">This command tells you how long it has been since the [about_remote](../Microsoft.PowerShell.Core/About/about_Remote.md) help file was last updated.</span></span>
<span data-ttu-id="044fa-123">Sie können dieses Befehls Format für jede beliebige Datei oder ein beliebiges anderes Objekt verwenden, das über eine **LastWrite Time** -Eigenschaft verfügt.</span><span class="sxs-lookup"><span data-stu-id="044fa-123">You can use this command format on any file, or any other object that has a **LastWriteTime** property.</span></span>

<span data-ttu-id="044fa-124">Dieser Befehl funktioniert, da der **Start** -Parameter von `New-TimeSpan` einen Alias von " **lastschreitetime**" aufweist.</span><span class="sxs-lookup"><span data-stu-id="044fa-124">This command works because the **Start** parameter of `New-TimeSpan` has an alias of **LastWriteTime**.</span></span> <span data-ttu-id="044fa-125">Wenn Sie ein Objekt mit der **LastWrite-Time** -Eigenschaft an übergeben `New-TimeSpan` , verwendet PowerShell den Wert der **LastWrite-Time** -Eigenschaft als Wert des **Start** -Parameters.</span><span class="sxs-lookup"><span data-stu-id="044fa-125">When you pipe an object that has a **LastWriteTime** property to `New-TimeSpan`, PowerShell uses the value of the **LastWriteTime** property as the value of the **Start** parameter.</span></span>

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

## <span data-ttu-id="044fa-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="044fa-126">PARAMETERS</span></span>

### <span data-ttu-id="044fa-127">-Days</span><span class="sxs-lookup"><span data-stu-id="044fa-127">-Days</span></span>

<span data-ttu-id="044fa-128">Gibt die Tage in der Zeitspanne an.</span><span class="sxs-lookup"><span data-stu-id="044fa-128">Specifies the days in the time span.</span></span>
<span data-ttu-id="044fa-129">Der Standardwert ist 0.</span><span class="sxs-lookup"><span data-stu-id="044fa-129">The default value is 0.</span></span>

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

### <span data-ttu-id="044fa-130">-Ende</span><span class="sxs-lookup"><span data-stu-id="044fa-130">-End</span></span>

<span data-ttu-id="044fa-131">Gibt das Ende einer Zeitspanne an.</span><span class="sxs-lookup"><span data-stu-id="044fa-131">Specifies the end of a time span.</span></span>
<span data-ttu-id="044fa-132">Der Standardwert ist das aktuelle Datum und die aktuelle Uhrzeit.</span><span class="sxs-lookup"><span data-stu-id="044fa-132">The default value is the current date and time.</span></span>

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

### <span data-ttu-id="044fa-133">-Stunden</span><span class="sxs-lookup"><span data-stu-id="044fa-133">-Hours</span></span>

<span data-ttu-id="044fa-134">Gibt die Stunden in der Zeitspanne an.</span><span class="sxs-lookup"><span data-stu-id="044fa-134">Specifies the hours in the time span.</span></span>
<span data-ttu-id="044fa-135">Der Standardwert ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="044fa-135">The default value is zero.</span></span>

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

### <span data-ttu-id="044fa-136">-Minuten</span><span class="sxs-lookup"><span data-stu-id="044fa-136">-Minutes</span></span>

<span data-ttu-id="044fa-137">Gibt die Minuten in der Zeitspanne an.</span><span class="sxs-lookup"><span data-stu-id="044fa-137">Specifies the minutes in the time span.</span></span>
<span data-ttu-id="044fa-138">Der Standardwert ist 0.</span><span class="sxs-lookup"><span data-stu-id="044fa-138">The default value is 0.</span></span>

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

### <span data-ttu-id="044fa-139">-Sekunden</span><span class="sxs-lookup"><span data-stu-id="044fa-139">-Seconds</span></span>

<span data-ttu-id="044fa-140">Gibt die Länge der Zeitspanne in Sekunden an.</span><span class="sxs-lookup"><span data-stu-id="044fa-140">Specifies the length of the time span in seconds.</span></span>
<span data-ttu-id="044fa-141">Der Standardwert ist 0.</span><span class="sxs-lookup"><span data-stu-id="044fa-141">The default value is 0.</span></span>

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

### <span data-ttu-id="044fa-142">-Start</span><span class="sxs-lookup"><span data-stu-id="044fa-142">-Start</span></span>

<span data-ttu-id="044fa-143">Gibt den Anfang einer Zeitspanne an.</span><span class="sxs-lookup"><span data-stu-id="044fa-143">Specifies the start of a time span.</span></span>
<span data-ttu-id="044fa-144">Geben Sie eine Zeichenfolge ein, die das Datum und die Uhrzeit darstellt, z. b. "3/15/09" oder ein **DateTime** -Objekt, z. b. eines von einem `Get-Date` Befehl.</span><span class="sxs-lookup"><span data-stu-id="044fa-144">Enter a string that represents the date and time, such as "3/15/09" or a **DateTime** object, such as one from a `Get-Date` command.</span></span> <span data-ttu-id="044fa-145">Der Standardwert ist das aktuelle Datum und die aktuelle Uhrzeit.</span><span class="sxs-lookup"><span data-stu-id="044fa-145">The default value is the current date and time.</span></span>

<span data-ttu-id="044fa-146">Sie können " **Start** " oder dessen Alias " **lastschreitetime**" verwenden.</span><span class="sxs-lookup"><span data-stu-id="044fa-146">You can use **Start** or its alias, **LastWriteTime**.</span></span>
<span data-ttu-id="044fa-147">Mit dem **LastWrite-Time** -Alias können Sie Objekte, die über eine **lastschreitetime** -Eigenschaft (z. b. Dateien im Dateisystem) verfügen, `[System.Io.FileIO]` an den **Start** -Parameter von übergeben `New-TimeSpan` .</span><span class="sxs-lookup"><span data-stu-id="044fa-147">The **LastWriteTime** alias lets you pipe objects that have a **LastWriteTime** property, such as files in the file system `[System.Io.FileIO]`, to the **Start** parameter of `New-TimeSpan`.</span></span>

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

### <span data-ttu-id="044fa-148">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="044fa-148">CommonParameters</span></span>

<span data-ttu-id="044fa-149">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="044fa-149">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="044fa-150">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="044fa-150">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="044fa-151">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="044fa-151">INPUTS</span></span>

### <span data-ttu-id="044fa-152">System.DateTime</span><span class="sxs-lookup"><span data-stu-id="044fa-152">System.DateTime</span></span>

<span data-ttu-id="044fa-153">Sie können ein **DateTime** -Objekt, das diese Startzeit darstellt, an die Pipeline übergeben `New-TimeSpan` .</span><span class="sxs-lookup"><span data-stu-id="044fa-153">You can pipe a **DateTime** object that represents that start time to `New-TimeSpan`.</span></span>

## <span data-ttu-id="044fa-154">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="044fa-154">OUTPUTS</span></span>

### <span data-ttu-id="044fa-155">System.TimeSpan</span><span class="sxs-lookup"><span data-stu-id="044fa-155">System.TimeSpan</span></span>

<span data-ttu-id="044fa-156">`New-TimeSpan` Gibt ein-Objekt zurück, das die Zeitspanne darstellt.</span><span class="sxs-lookup"><span data-stu-id="044fa-156">`New-TimeSpan` returns an object that represents the time span.</span></span>

## <span data-ttu-id="044fa-157">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="044fa-157">NOTES</span></span>

## <span data-ttu-id="044fa-158">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="044fa-158">RELATED LINKS</span></span>

[<span data-ttu-id="044fa-159">Get-Date</span><span class="sxs-lookup"><span data-stu-id="044fa-159">Get-Date</span></span>](Get-Date.md)

[<span data-ttu-id="044fa-160">Set-Date</span><span class="sxs-lookup"><span data-stu-id="044fa-160">Set-Date</span></span>](Set-Date.md)

