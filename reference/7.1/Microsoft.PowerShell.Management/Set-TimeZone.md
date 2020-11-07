---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 09/18/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-timezone?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-TimeZone
ms.openlocfilehash: 4bade5a583533c3156fb923a5257ebb7a4453a2b
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2020
ms.locfileid: "94347532"
---
# <span data-ttu-id="a19a9-103">Set-TimeZone</span><span class="sxs-lookup"><span data-stu-id="a19a9-103">Set-TimeZone</span></span>

## <span data-ttu-id="a19a9-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="a19a9-104">SYNOPSIS</span></span>
<span data-ttu-id="a19a9-105">Legt die Zeitzone des Systems auf eine angegebene Zeitzone fest.</span><span class="sxs-lookup"><span data-stu-id="a19a9-105">Sets the system time zone to a specified time zone.</span></span>

## <span data-ttu-id="a19a9-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a19a9-106">SYNTAX</span></span>

### <span data-ttu-id="a19a9-107">Name (Standard)</span><span class="sxs-lookup"><span data-stu-id="a19a9-107">Name (Default)</span></span>

```
Set-TimeZone [-Name] <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="a19a9-108">Id</span><span class="sxs-lookup"><span data-stu-id="a19a9-108">Id</span></span>

```
Set-TimeZone -Id <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="a19a9-109">InputObject</span><span class="sxs-lookup"><span data-stu-id="a19a9-109">InputObject</span></span>

```
Set-TimeZone [-InputObject] <TimeZoneInfo> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="a19a9-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a19a9-110">DESCRIPTION</span></span>

<span data-ttu-id="a19a9-111">Mit dem- `Set-TimeZone` Cmdlet wird die Zeitzone des Systems auf eine angegebene Zeitzone festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a19a9-111">The `Set-TimeZone` cmdlet sets the system time zone to a specified time zone.</span></span>

## <span data-ttu-id="a19a9-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="a19a9-112">EXAMPLES</span></span>

### <span data-ttu-id="a19a9-113">Beispiel 1: Festlegen der Zeitzone nach ID</span><span class="sxs-lookup"><span data-stu-id="a19a9-113">Example 1: Set the time zone by Id</span></span>

<span data-ttu-id="a19a9-114">In diesem Beispiel wird die Zeitzone auf dem lokalen Computer auf die russische Standard Zeit festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a19a9-114">This example sets the time zone on the local computer to Russian Standard Time.</span></span>

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

### <span data-ttu-id="a19a9-115">Beispiel 2: Festlegen der Zeitzone nach Name</span><span class="sxs-lookup"><span data-stu-id="a19a9-115">Example 2: Set the time zone by name</span></span>

<span data-ttu-id="a19a9-116">In diesem Beispiel wird die Zeitzone auf dem lokalen Computer auf die russische Standard Zeit festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a19a9-116">This example sets the time zone on the local computer to Russian Standard Time.</span></span>

```powershell
Set-TimeZone -Name "Russia TZ 2 Standard Time"
```

<span data-ttu-id="a19a9-117">Wie wir im vorherigen Beispiel gesehen haben, stimmen die **ID** und der **Name** der Zeitzone nicht immer mit.</span><span class="sxs-lookup"><span data-stu-id="a19a9-117">As we saw in the previous example, the **Id** and the **Name** of the Time Zone do not always match.</span></span>
<span data-ttu-id="a19a9-118">Der **Name** -Parameter muss mit den Eigenschaften **Standardname** oder **DaylightName** des **TimeZoneInfo** -Objekts übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="a19a9-118">The **Name** parameter must match the **StandardName** or **DaylightName** properties of the **TimeZoneInfo** object.</span></span>

## <span data-ttu-id="a19a9-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a19a9-119">PARAMETERS</span></span>

### <span data-ttu-id="a19a9-120">-Id</span><span class="sxs-lookup"><span data-stu-id="a19a9-120">-Id</span></span>

<span data-ttu-id="a19a9-121">Gibt die ID der Zeitzone an, die von diesem Cmdlet festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="a19a9-121">Specifies the ID of the time zone that this cmdlet sets.</span></span> <span data-ttu-id="a19a9-122">Eine vollständige Liste der Zeit Zonen-IDs können Sie durch Ausführen des folgenden Befehls erhalten: `Get-TimeZone -ListAvailable` .</span><span class="sxs-lookup"><span data-stu-id="a19a9-122">A full list of Time Zone IDs can be obtained by running the following command: `Get-TimeZone -ListAvailable`.</span></span>

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

### <span data-ttu-id="a19a9-123">-InputObject</span><span class="sxs-lookup"><span data-stu-id="a19a9-123">-InputObject</span></span>

<span data-ttu-id="a19a9-124">Gibt ein **TimeZoneInfo** -Objekt an, das als Eingabe verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a19a9-124">Specifies a **TimeZoneInfo** object to use as input.</span></span>

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

### <span data-ttu-id="a19a9-125">-Name</span><span class="sxs-lookup"><span data-stu-id="a19a9-125">-Name</span></span>

<span data-ttu-id="a19a9-126">Gibt den Namen der Zeitzone an, die von diesem Cmdlet festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="a19a9-126">Specifies the name of the time zone that this cmdlet sets.</span></span> <span data-ttu-id="a19a9-127">Eine vollständige Liste der Zeit Zonen Namen können Sie durch Ausführen des folgenden Befehls erhalten: `Get-TimeZone -ListAvailable` .</span><span class="sxs-lookup"><span data-stu-id="a19a9-127">A full list of Time Zone names can be obtained by running the following command: `Get-TimeZone -ListAvailable`.</span></span>

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

### <span data-ttu-id="a19a9-128">-PassThru</span><span class="sxs-lookup"><span data-stu-id="a19a9-128">-PassThru</span></span>

<span data-ttu-id="a19a9-129">Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="a19a9-129">Returns an object representing the item with which you are working.</span></span> <span data-ttu-id="a19a9-130">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="a19a9-130">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="a19a9-131">-Confirm</span><span class="sxs-lookup"><span data-stu-id="a19a9-131">-Confirm</span></span>

<span data-ttu-id="a19a9-132">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="a19a9-132">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="a19a9-133">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="a19a9-133">-WhatIf</span></span>

<span data-ttu-id="a19a9-134">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a19a9-134">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="a19a9-135">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a19a9-135">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="a19a9-136">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a19a9-136">CommonParameters</span></span>

<span data-ttu-id="a19a9-137">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a19a9-137">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a19a9-138">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a19a9-138">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a19a9-139">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="a19a9-139">INPUTS</span></span>

### <span data-ttu-id="a19a9-140">System. String, System. timezoneingefo, System. String</span><span class="sxs-lookup"><span data-stu-id="a19a9-140">System.String, System.TimeZoneInfo, System.String</span></span>

## <span data-ttu-id="a19a9-141">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="a19a9-141">OUTPUTS</span></span>

## <span data-ttu-id="a19a9-142">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="a19a9-142">NOTES</span></span>

<span data-ttu-id="a19a9-143">Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a19a9-143">This cmdlet is only available on Windows platforms.</span></span>

## <span data-ttu-id="a19a9-144">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="a19a9-144">RELATED LINKS</span></span>

[<span data-ttu-id="a19a9-145">Get-TimeZone</span><span class="sxs-lookup"><span data-stu-id="a19a9-145">Get-TimeZone</span></span>](Get-TimeZone.md)
