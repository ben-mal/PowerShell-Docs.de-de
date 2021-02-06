---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/30/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/set-date?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Date
ms.openlocfilehash: 0f35eea0dfca76b535aad3bdb663d55c224a11d2
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603690"
---
# <span data-ttu-id="8304a-102">Set-Date</span><span class="sxs-lookup"><span data-stu-id="8304a-102">Set-Date</span></span>

## <span data-ttu-id="8304a-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="8304a-103">SYNOPSIS</span></span>
<span data-ttu-id="8304a-104">Ändert die Systemzeit auf dem Computer in eine von Ihnen angegebene Uhrzeit.</span><span class="sxs-lookup"><span data-stu-id="8304a-104">Changes the system time on the computer to a time that you specify.</span></span>

## <span data-ttu-id="8304a-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8304a-105">SYNTAX</span></span>

### <span data-ttu-id="8304a-106">Datum (Standard)</span><span class="sxs-lookup"><span data-stu-id="8304a-106">Date (Default)</span></span>

```
Set-Date [-Date] <DateTime> [-DisplayHint <DisplayHintType>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="8304a-107">Anpassen</span><span class="sxs-lookup"><span data-stu-id="8304a-107">Adjust</span></span>

```
Set-Date [-Adjust] <TimeSpan> [-DisplayHint <DisplayHintType>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="8304a-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8304a-108">DESCRIPTION</span></span>

<span data-ttu-id="8304a-109">Das- `Set-Date` Cmdlet ändert das Systemdatum und die Uhrzeit auf dem Computer in eine von Ihnen angegebene Datums-und uhrzeitanzeit.</span><span class="sxs-lookup"><span data-stu-id="8304a-109">The `Set-Date` cmdlet changes the system date and time on the computer to a date and time that you specify.</span></span>
<span data-ttu-id="8304a-110">Sie können ein neues Datum und/oder eine Uhrzeit angeben, indem Sie eine Zeichenfolge eingeben oder ein **DateTime** -oder **TimeSpan** -Objekt an übergeben `Set-Date` .</span><span class="sxs-lookup"><span data-stu-id="8304a-110">You can specify a new date and/or time by typing a string or by passing a **DateTime** or **TimeSpan** object to `Set-Date`.</span></span> <span data-ttu-id="8304a-111">Um ein neues Datum oder eine Uhrzeit anzugeben, verwenden Sie den **Date** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="8304a-111">To specify a new date or time, use the **Date** parameter.</span></span>
<span data-ttu-id="8304a-112">Verwenden Sie den Parameter " **Anpassen** ", um ein Änderungs Intervall anzugeben.</span><span class="sxs-lookup"><span data-stu-id="8304a-112">To specify a change interval, use the **Adjust** parameter.</span></span>

## <span data-ttu-id="8304a-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="8304a-113">EXAMPLES</span></span>

### <span data-ttu-id="8304a-114">Beispiel 1: Hinzufügen von drei Tagen zum Systemdatum</span><span class="sxs-lookup"><span data-stu-id="8304a-114">Example 1: Add three days to the system date</span></span>

<span data-ttu-id="8304a-115">Mit diesem Befehl werden dem aktuellen Datum drei Tage hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="8304a-115">This command adds three days to the current system date.</span></span>
<span data-ttu-id="8304a-116">Er wirkt sich nicht auf die Uhrzeit aus.</span><span class="sxs-lookup"><span data-stu-id="8304a-116">It does not affect the time.</span></span>
<span data-ttu-id="8304a-117">Der Befehl verwendet den **Date** -Parameter, um das Datum anzugeben.</span><span class="sxs-lookup"><span data-stu-id="8304a-117">The command uses the **Date** parameter to specify the date.</span></span>

<span data-ttu-id="8304a-118">Mit dem- `Get-Date` Cmdlet wird das aktuelle Datum als **DateTime** -Objekt zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8304a-118">The `Get-Date` cmdlet returns the current date as a **DateTime** object.</span></span> <span data-ttu-id="8304a-119">Die **addDays** -Methode des **DateTime** -Objekts fügt dem aktuellen **DateTime** -Objekt eine angegebene Anzahl von Tagen (3) hinzu.</span><span class="sxs-lookup"><span data-stu-id="8304a-119">The **DateTime** object's **AddDays** method adds a specified number of days (3) to the current **DateTime** object.</span></span>

```powershell
Set-Date -Date (Get-Date).AddDays(3)
```

### <span data-ttu-id="8304a-120">Beispiel 2: Festlegen der Systemuhr auf 10 Minuten</span><span class="sxs-lookup"><span data-stu-id="8304a-120">Example 2: Set the system clock back 10 minutes</span></span>

<span data-ttu-id="8304a-121">In diesem Beispiel wird die aktuelle Systemzeit um 10 Minuten zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="8304a-121">This example sets the current system time back by 10 minutes.</span></span>

<span data-ttu-id="8304a-122">Mit dem Parameter " **Anpassen** " können Sie ein Änderungs Intervall (abzüglich zehn Minuten) im Standardzeit Format für das Gebiets Schema angeben.</span><span class="sxs-lookup"><span data-stu-id="8304a-122">The **Adjust** parameter allows you to specify an interval of change (minus ten minutes) in the standard time format for the locale.</span></span>

<span data-ttu-id="8304a-123">Der **displayhint** -Parameter weist PowerShell an, nur die Uhrzeit anzuzeigen, wirkt sich jedoch nicht auf das **DateTime** -Objekt aus, das `Set-Date` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="8304a-123">The **DisplayHint** parameter tells PowerShell to display only the time, but it does not affect the **DateTime** object that `Set-Date` returns.</span></span>

```powershell
Set-Date -Adjust -0:10:0 -DisplayHint Time
```

### <span data-ttu-id="8304a-124">Beispiel 3: Festlegen des Datums und der Uhrzeit auf einen variablen Wert</span><span class="sxs-lookup"><span data-stu-id="8304a-124">Example 3: Set the date and time to a variable value</span></span>

<span data-ttu-id="8304a-125">Diese Befehle ändern das Systemdatum und die Uhrzeit auf dem lokalen Computer in das Datum und die Uhrzeit, die in der Variablen gespeichert sind `$T` .</span><span class="sxs-lookup"><span data-stu-id="8304a-125">These commands change the system date and time on local computer to the date and time saved in the variable `$T`.</span></span> <span data-ttu-id="8304a-126">Der erste Befehl ruft das Datum ab und speichert es in `$T` .</span><span class="sxs-lookup"><span data-stu-id="8304a-126">The first command gets the date and stores it in `$T`.</span></span>

<span data-ttu-id="8304a-127">Der zweite Befehl verwendet den **Date** -Parameter, um das **DateTime** -Objekt in an `$T` das `Set-Date` Cmdlet zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="8304a-127">The second command uses the **Date** parameter to pass the **DateTime** object in `$T` to the `Set-Date` cmdlet.</span></span>

```powershell
$T = Get-Date
Set-Date -Date $T
```

### <span data-ttu-id="8304a-128">Beispiel 4: Hinzufügen von 90 Minuten zur Systemuhr</span><span class="sxs-lookup"><span data-stu-id="8304a-128">Example 4: Add 90 minutes to the system clock</span></span>

<span data-ttu-id="8304a-129">Diese Befehle stellen die Systemzeit auf dem lokalen Computer um 90 Minuten vor.</span><span class="sxs-lookup"><span data-stu-id="8304a-129">These commands advance the system time on the local computer by 90 minutes.</span></span>

<span data-ttu-id="8304a-130">Der erste Befehl verwendet das `New-TimeSpan` Cmdlet, um ein **TimeSpan** -Objekt mit einem Intervall von 90 Minuten zu erstellen, und speichert es in der `$90mins` Variablen.</span><span class="sxs-lookup"><span data-stu-id="8304a-130">The first command uses the `New-TimeSpan` cmdlet to create a **TimeSpan** object with a 90-minute interval, and saves it in the `$90mins` variable.</span></span>

<span data-ttu-id="8304a-131">Der zweite Befehl verwendet den **Adjust** -Parameter von `Set-Date` , um das Datum mit dem Wert des **TimeSpan** -Objekts in der `$90mins` Variablen anzupassen.</span><span class="sxs-lookup"><span data-stu-id="8304a-131">The second command uses the **Adjust** parameter of `Set-Date` to adjust the date by the value of the **TimeSpan** object in the `$90mins` variable.</span></span>

```powershell
$90mins = New-TimeSpan -Minutes 90
Set-Date -Adjust $90mins
```

## <span data-ttu-id="8304a-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8304a-132">PARAMETERS</span></span>

### <span data-ttu-id="8304a-133">-Anpassen</span><span class="sxs-lookup"><span data-stu-id="8304a-133">-Adjust</span></span>

<span data-ttu-id="8304a-134">Gibt den Wert an, den dieses Cmdlet dem aktuellen Datum und der aktuellen Uhrzeit hinzufügt oder von diesem subtrahiert.</span><span class="sxs-lookup"><span data-stu-id="8304a-134">Specifies the value for which this cmdlet adds or subtracts from the current date and time.</span></span>
<span data-ttu-id="8304a-135">kann eine Anpassung im Standard Datums-und-Uhrzeit Format für Ihr Gebiets Schema eingeben, oder verwenden Sie den **Adjust** -Parameter, um ein **TimeSpan** -Objekt von `New-TimeSpan` an zu übergeben `Set-Date` .</span><span class="sxs-lookup"><span data-stu-id="8304a-135">can type an adjustment in standard date and time format for your locale or use the **Adjust** parameter to pass a **TimeSpan** object from `New-TimeSpan` to `Set-Date`.</span></span>

```yaml
Type: System.TimeSpan
Parameter Sets: Adjust
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8304a-136">-Datum</span><span class="sxs-lookup"><span data-stu-id="8304a-136">-Date</span></span>

<span data-ttu-id="8304a-137">Ändert das Datum und die Uhrzeit in die angegebenen Werte.</span><span class="sxs-lookup"><span data-stu-id="8304a-137">Changes the date and time to the specified values.</span></span>
<span data-ttu-id="8304a-138">Sie können ein neues Datum im kurzen Datumsformat und eine Uhrzeit im Standardzeitformat für Ihr Gebietsschema eingeben.</span><span class="sxs-lookup"><span data-stu-id="8304a-138">You can type a new date in the short date format and a time in the standard time format for your locale.</span></span> <span data-ttu-id="8304a-139">Oder Sie können ein **DateTime** -Objekt von übergeben `Get-Date` .</span><span class="sxs-lookup"><span data-stu-id="8304a-139">Or, you can pass a **DateTime** object from `Get-Date`.</span></span>

<span data-ttu-id="8304a-140">Wenn Sie ein Datum, aber keine Uhrzeit angeben, wird `Set-Date` die Uhrzeit am angegebenen Datum auf Mitternacht geändert.</span><span class="sxs-lookup"><span data-stu-id="8304a-140">If you specify a date, but not a time, `Set-Date` changes the time to midnight on the specified date.</span></span> <span data-ttu-id="8304a-141">Wenn Sie nur eine Uhrzeit angeben, wird das Datum nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="8304a-141">If you specify only a time, it does not change the date.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: Date
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="8304a-142">-Displayhint</span><span class="sxs-lookup"><span data-stu-id="8304a-142">-DisplayHint</span></span>

<span data-ttu-id="8304a-143">Gibt an, welche Elemente von Datum und Uhrzeit angezeigt werden. Die zulässigen Werte für diesen Parameter sind:</span><span class="sxs-lookup"><span data-stu-id="8304a-143">Specifies which elements of the date and time are displayed.The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="8304a-144">**Date** : zeigt nur das Datum an.</span><span class="sxs-lookup"><span data-stu-id="8304a-144">**Date** - displays only the date.</span></span>
- <span data-ttu-id="8304a-145">**Zeit** : zeigt nur die Uhrzeit an.</span><span class="sxs-lookup"><span data-stu-id="8304a-145">**Time** - displays only the time.</span></span>
- <span data-ttu-id="8304a-146">**DateTime** : zeigt das Datum und die Uhrzeit an.</span><span class="sxs-lookup"><span data-stu-id="8304a-146">**DateTime** - displays the date and time.</span></span>

<span data-ttu-id="8304a-147">Dieser Parameter betrifft nur die Anzeige.</span><span class="sxs-lookup"><span data-stu-id="8304a-147">This parameter affects only the display.</span></span>
<span data-ttu-id="8304a-148">Dies wirkt sich nicht auf das **DateTime** -Objekt aus, das `Get-Date` abruft.</span><span class="sxs-lookup"><span data-stu-id="8304a-148">It does not affect the **DateTime** object that `Get-Date` retrieves.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.DisplayHintType
Parameter Sets: (All)
Aliases:
Accepted values: Date, Time, DateTime

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8304a-149">-Confirm</span><span class="sxs-lookup"><span data-stu-id="8304a-149">-Confirm</span></span>

<span data-ttu-id="8304a-150">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="8304a-150">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8304a-151">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="8304a-151">-WhatIf</span></span>

<span data-ttu-id="8304a-152">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8304a-152">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="8304a-153">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="8304a-153">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8304a-154">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="8304a-154">CommonParameters</span></span>

<span data-ttu-id="8304a-155">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="8304a-155">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8304a-156">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="8304a-156">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="8304a-157">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="8304a-157">INPUTS</span></span>

### <span data-ttu-id="8304a-158">System.DateTime</span><span class="sxs-lookup"><span data-stu-id="8304a-158">System.DateTime</span></span>

<span data-ttu-id="8304a-159">Sie können ein Datum an die Pipeline übergeben `Set-Date` .</span><span class="sxs-lookup"><span data-stu-id="8304a-159">You can pipe a date to `Set-Date`.</span></span>

## <span data-ttu-id="8304a-160">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="8304a-160">OUTPUTS</span></span>

### <span data-ttu-id="8304a-161">System.DateTime</span><span class="sxs-lookup"><span data-stu-id="8304a-161">System.DateTime</span></span>

<span data-ttu-id="8304a-162">`Set-Date` Gibt ein-Objekt zurück, das das von ihm festgelegte Datum darstellt.</span><span class="sxs-lookup"><span data-stu-id="8304a-162">`Set-Date` returns an object that represents the date that it set.</span></span>

## <span data-ttu-id="8304a-163">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="8304a-163">NOTES</span></span>

- <span data-ttu-id="8304a-164">Verwenden Sie dieses Cmdlet vorsichtig, wenn Sie das Datum und die Uhrzeit auf dem Computer ändern.</span><span class="sxs-lookup"><span data-stu-id="8304a-164">Use this cmdlet cautiously when changing the date and time on the computer.</span></span> <span data-ttu-id="8304a-165">Die Änderung kann möglicherweise verhindern, dass der Computer systemweite Ereignisse und Updates erhält, die durch einen Datums- oder Uhrzeitwert ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="8304a-165">The change might prevent the computer from receiving system-wide events and updates that are triggered by a date or time.</span></span> <span data-ttu-id="8304a-166">Verwenden Sie die Parameter **WhatIf** und **Confirm** , um Fehler zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="8304a-166">Use the **WhatIf** and **Confirm** parameters to avoid errors.</span></span>
- <span data-ttu-id="8304a-167">Sie können .net-Standardmethoden mit den **DateTime** -und **TimeSpan** -Objekten verwenden, die mit verwendet werden `Set-Date` , z. b. **addDays**, **addmonate** und **FromFileTime**.</span><span class="sxs-lookup"><span data-stu-id="8304a-167">You can use standard .NET methods with the **DateTime** and **TimeSpan** objects used with `Set-Date`, such as **AddDays**, **AddMonths**, and **FromFileTime**.</span></span> <span data-ttu-id="8304a-168">Weitere Informationen finden Sie unter [DateTime-Methoden](/dotnet/api/system.datetime) und</span><span class="sxs-lookup"><span data-stu-id="8304a-168">For more information, see [DateTime Methods](/dotnet/api/system.datetime) and</span></span>

  <span data-ttu-id="8304a-169">[TimeSpan-Methoden](/dotnet/api/system.timespan) im .NET SDK.</span><span class="sxs-lookup"><span data-stu-id="8304a-169">[TimeSpan Methods](/dotnet/api/system.timespan) in the .NET SDK.</span></span>

## <span data-ttu-id="8304a-170">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="8304a-170">RELATED LINKS</span></span>

[<span data-ttu-id="8304a-171">Get-Date</span><span class="sxs-lookup"><span data-stu-id="8304a-171">Get-Date</span></span>](Get-Date.md)

[<span data-ttu-id="8304a-172">New-TimeSpan</span><span class="sxs-lookup"><span data-stu-id="8304a-172">New-TimeSpan</span></span>](New-TimeSpan.md)
