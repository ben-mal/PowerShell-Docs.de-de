---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 09/18/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-timezone?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-TimeZone
ms.openlocfilehash: 3acf02b567c1fecd8089b12fac7c32b42abfec77
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2020
ms.locfileid: "94343180"
---
# <span data-ttu-id="4c510-103">Set-TimeZone</span><span class="sxs-lookup"><span data-stu-id="4c510-103">Set-TimeZone</span></span>

## <span data-ttu-id="4c510-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="4c510-104">SYNOPSIS</span></span>
<span data-ttu-id="4c510-105">Legt die Zeitzone des Systems auf eine angegebene Zeitzone fest.</span><span class="sxs-lookup"><span data-stu-id="4c510-105">Sets the system time zone to a specified time zone.</span></span>

## <span data-ttu-id="4c510-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4c510-106">SYNTAX</span></span>

### <span data-ttu-id="4c510-107">Name (Standard)</span><span class="sxs-lookup"><span data-stu-id="4c510-107">Name (Default)</span></span>

```
Set-TimeZone [-Name] <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="4c510-108">Id</span><span class="sxs-lookup"><span data-stu-id="4c510-108">Id</span></span>

```
Set-TimeZone -Id <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="4c510-109">InputObject</span><span class="sxs-lookup"><span data-stu-id="4c510-109">InputObject</span></span>

```
Set-TimeZone [-InputObject] <TimeZoneInfo> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="4c510-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4c510-110">DESCRIPTION</span></span>

<span data-ttu-id="4c510-111">Mit dem- `Set-TimeZone` Cmdlet wird die Zeitzone des Systems auf eine angegebene Zeitzone festgelegt.</span><span class="sxs-lookup"><span data-stu-id="4c510-111">The `Set-TimeZone` cmdlet sets the system time zone to a specified time zone.</span></span>

## <span data-ttu-id="4c510-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="4c510-112">EXAMPLES</span></span>

### <span data-ttu-id="4c510-113">Beispiel 1: Festlegen der Zeitzone nach ID</span><span class="sxs-lookup"><span data-stu-id="4c510-113">Example 1: Set the time zone by Id</span></span>

<span data-ttu-id="4c510-114">In diesem Beispiel wird die Zeitzone auf dem lokalen Computer auf die russische Standard Zeit festgelegt.</span><span class="sxs-lookup"><span data-stu-id="4c510-114">This example sets the time zone on the local computer to Russian Standard Time.</span></span>

```powershell
Set-TimeZone -Id "Russian Standard Time" -PassThru
```

```Output
Id                         : Russian Standard Time
DisplayName                : (UTC+03:00) Moscow, St. Petersburg
StandardName               : Russia TZ 2 Standard Time
DaylightName               : Russia TZ 2 Daylight Time
BaseUtcOffset              : 03:00:00
SupportsDaylightSavingTime : True
```

### <span data-ttu-id="4c510-115">Beispiel 2: Festlegen der Zeitzone nach Name</span><span class="sxs-lookup"><span data-stu-id="4c510-115">Example 2: Set the time zone by name</span></span>

<span data-ttu-id="4c510-116">In diesem Beispiel wird die Zeitzone auf dem lokalen Computer auf die russische Standard Zeit festgelegt.</span><span class="sxs-lookup"><span data-stu-id="4c510-116">This example sets the time zone on the local computer to Russian Standard Time.</span></span>

```powershell
Set-TimeZone -Name "Russia TZ 2 Standard Time"
```

<span data-ttu-id="4c510-117">Wie wir im vorherigen Beispiel gesehen haben, stimmen die **ID** und der **Name** der Zeitzone nicht immer mit.</span><span class="sxs-lookup"><span data-stu-id="4c510-117">As we saw in the previous example, the **Id** and the **Name** of the Time Zone do not always match.</span></span>
<span data-ttu-id="4c510-118">Der **Name** -Parameter muss mit den Eigenschaften **Standardname** oder **DaylightName** des **TimeZoneInfo** -Objekts übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="4c510-118">The **Name** parameter must match the **StandardName** or **DaylightName** properties of the **TimeZoneInfo** object.</span></span>

## <span data-ttu-id="4c510-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4c510-119">PARAMETERS</span></span>

### <span data-ttu-id="4c510-120">-Id</span><span class="sxs-lookup"><span data-stu-id="4c510-120">-Id</span></span>

<span data-ttu-id="4c510-121">Gibt die ID der Zeitzone an, die von diesem Cmdlet festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="4c510-121">Specifies the ID of the time zone that this cmdlet sets.</span></span> <span data-ttu-id="4c510-122">Eine vollständige Liste der Zeit Zonen-IDs können Sie durch Ausführen des folgenden Befehls erhalten: `Get-TimeZone -ListAvailable` .</span><span class="sxs-lookup"><span data-stu-id="4c510-122">A full list of Time Zone IDs can be obtained by running the following command: `Get-TimeZone -ListAvailable`.</span></span>

```yaml
Type: System.String
Parameter Sets: Id
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4c510-123">-InputObject</span><span class="sxs-lookup"><span data-stu-id="4c510-123">-InputObject</span></span>

<span data-ttu-id="4c510-124">Gibt ein **TimeZoneInfo** -Objekt an, das als Eingabe verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4c510-124">Specifies a **TimeZoneInfo** object to use as input.</span></span>

```yaml
Type: System.TimeZoneInfo
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="4c510-125">-Name</span><span class="sxs-lookup"><span data-stu-id="4c510-125">-Name</span></span>

<span data-ttu-id="4c510-126">Gibt den Namen der Zeitzone an, die von diesem Cmdlet festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="4c510-126">Specifies the name of the time zone that this cmdlet sets.</span></span> <span data-ttu-id="4c510-127">Eine vollständige Liste der Zeit Zonen Namen können Sie durch Ausführen des folgenden Befehls erhalten: `Get-TimeZone -ListAvailable` .</span><span class="sxs-lookup"><span data-stu-id="4c510-127">A full list of Time Zone names can be obtained by running the following command: `Get-TimeZone -ListAvailable`.</span></span>

```yaml
Type: System.String
Parameter Sets: Name
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4c510-128">-PassThru</span><span class="sxs-lookup"><span data-stu-id="4c510-128">-PassThru</span></span>

<span data-ttu-id="4c510-129">Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="4c510-129">Returns an object representing the item with which you are working.</span></span> <span data-ttu-id="4c510-130">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="4c510-130">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="4c510-131">-Confirm</span><span class="sxs-lookup"><span data-stu-id="4c510-131">-Confirm</span></span>

<span data-ttu-id="4c510-132">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="4c510-132">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="4c510-133">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="4c510-133">-WhatIf</span></span>

<span data-ttu-id="4c510-134">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4c510-134">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="4c510-135">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4c510-135">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="4c510-136">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="4c510-136">CommonParameters</span></span>

<span data-ttu-id="4c510-137">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4c510-137">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4c510-138">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4c510-138">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4c510-139">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="4c510-139">INPUTS</span></span>

### <span data-ttu-id="4c510-140">System. String, System. timezoneingefo, System. String</span><span class="sxs-lookup"><span data-stu-id="4c510-140">System.String, System.TimeZoneInfo, System.String</span></span>

## <span data-ttu-id="4c510-141">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="4c510-141">OUTPUTS</span></span>

## <span data-ttu-id="4c510-142">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="4c510-142">NOTES</span></span>

## <span data-ttu-id="4c510-143">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="4c510-143">RELATED LINKS</span></span>

[<span data-ttu-id="4c510-144">Get-TimeZone</span><span class="sxs-lookup"><span data-stu-id="4c510-144">Get-TimeZone</span></span>](Get-TimeZone.md)
