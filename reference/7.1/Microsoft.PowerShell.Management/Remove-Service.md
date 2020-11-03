---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-service?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Service
ms.openlocfilehash: b23e263c2d6ff64ca2a799614d213f1e549cdfe3
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211543"
---
# <span data-ttu-id="a6e1f-103">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="a6e1f-103">Remove-Service</span></span>

## <span data-ttu-id="a6e1f-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="a6e1f-104">SYNOPSIS</span></span>
<span data-ttu-id="a6e1f-105">Entfernt einen Windows-Dienst.</span><span class="sxs-lookup"><span data-stu-id="a6e1f-105">Removes a Windows service.</span></span>

## <span data-ttu-id="a6e1f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a6e1f-106">SYNTAX</span></span>

### <span data-ttu-id="a6e1f-107">Name (Standard)</span><span class="sxs-lookup"><span data-stu-id="a6e1f-107">Name (Default)</span></span>

```
Remove-Service [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="a6e1f-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="a6e1f-108">InputObject</span></span>

```
Remove-Service [-InputObject <ServiceController>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="a6e1f-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a6e1f-109">DESCRIPTION</span></span>

<span data-ttu-id="a6e1f-110">Mit dem `Remove-Service` -Cmdlet wird ein Windows-Dienst in der Registrierung und in der Dienst Datenbank entfernt.</span><span class="sxs-lookup"><span data-stu-id="a6e1f-110">The `Remove-Service` cmdlet removes a Windows service in the registry and in the service database.</span></span>

<span data-ttu-id="a6e1f-111">Das `Remove-Service` Cmdlet wurde in PowerShell 6,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="a6e1f-111">The `Remove-Service` cmdlet was introduced in PowerShell 6.0.</span></span>

## <span data-ttu-id="a6e1f-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="a6e1f-112">EXAMPLES</span></span>

### <span data-ttu-id="a6e1f-113">Beispiel 1: Entfernen eines Dienstanbieter</span><span class="sxs-lookup"><span data-stu-id="a6e1f-113">Example 1: Remove a service</span></span>

<span data-ttu-id="a6e1f-114">Dadurch wird ein Dienst mit dem Namen Test Service entfernt.</span><span class="sxs-lookup"><span data-stu-id="a6e1f-114">This removes a service named TestService.</span></span>

```powershell
Remove-Service -Name "TestService"
```

### <span data-ttu-id="a6e1f-115">Beispiel 2: Entfernen eines diensnamens mit dem anzeigen Amen</span><span class="sxs-lookup"><span data-stu-id="a6e1f-115">Example 2: Remove a service using the display name</span></span>

<span data-ttu-id="a6e1f-116">In diesem Beispiel wird ein Dienst mit dem Namen Test Service entfernt.</span><span class="sxs-lookup"><span data-stu-id="a6e1f-116">This example removes a service named TestService.</span></span> <span data-ttu-id="a6e1f-117">Der Befehl verwendet `Get-Service` , um ein Objekt zu erhalten, das den Test Service-Dienst mit dem anzeigen Amen darstellt.</span><span class="sxs-lookup"><span data-stu-id="a6e1f-117">The command uses `Get-Service` to get an object that represents the TestService service using the display name.</span></span> <span data-ttu-id="a6e1f-118">Der Pipeline Operator ( `|` ) übergibt das Objekt an `Remove-Service` , wodurch der Dienst entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="a6e1f-118">The pipeline operator (`|`) pipes the object to `Remove-Service`, which removes the service.</span></span>

```powershell
Get-Service -DisplayName "Test Service" | Remove-Service
```

## <span data-ttu-id="a6e1f-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a6e1f-119">PARAMETERS</span></span>

### <span data-ttu-id="a6e1f-120">-InputObject</span><span class="sxs-lookup"><span data-stu-id="a6e1f-120">-InputObject</span></span>

<span data-ttu-id="a6e1f-121">Gibt **ServiceController** -Objekte an, die die zu entfern tenden Dienste darstellen.</span><span class="sxs-lookup"><span data-stu-id="a6e1f-121">Specifies **ServiceController** objects that represent the services to remove.</span></span> <span data-ttu-id="a6e1f-122">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="a6e1f-122">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

```yaml
Type: System.ServiceProcess.ServiceController
Parameter Sets: InputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="a6e1f-123">-Name</span><span class="sxs-lookup"><span data-stu-id="a6e1f-123">-Name</span></span>

<span data-ttu-id="a6e1f-124">Gibt die Dienstnamen der zu entfernenden Dienste an.</span><span class="sxs-lookup"><span data-stu-id="a6e1f-124">Specifies the service names of the services to remove.</span></span> <span data-ttu-id="a6e1f-125">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="a6e1f-125">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String
Parameter Sets: Name
Aliases: ServiceName, SN

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="a6e1f-126">-Confirm</span><span class="sxs-lookup"><span data-stu-id="a6e1f-126">-Confirm</span></span>

<span data-ttu-id="a6e1f-127">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="a6e1f-127">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="a6e1f-128">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="a6e1f-128">-WhatIf</span></span>

<span data-ttu-id="a6e1f-129">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a6e1f-129">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="a6e1f-130">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a6e1f-130">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="a6e1f-131">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a6e1f-131">CommonParameters</span></span>

<span data-ttu-id="a6e1f-132">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a6e1f-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a6e1f-133">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a6e1f-133">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a6e1f-134">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="a6e1f-134">INPUTS</span></span>

### <span data-ttu-id="a6e1f-135">System. ServiceProcess. ServiceController, System. String</span><span class="sxs-lookup"><span data-stu-id="a6e1f-135">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="a6e1f-136">Sie können ein Dienst Objekt oder eine Zeichenfolge, die den Namen eines diensnamens enthält, über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="a6e1f-136">You can pipe a service object or a string that contains the name of a service to this cmdlet.</span></span>

## <span data-ttu-id="a6e1f-137">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="a6e1f-137">OUTPUTS</span></span>

### <span data-ttu-id="a6e1f-138">Keine</span><span class="sxs-lookup"><span data-stu-id="a6e1f-138">None</span></span>

<span data-ttu-id="a6e1f-139">Dieses Cmdlet gibt keine Ausgabe zurück.</span><span class="sxs-lookup"><span data-stu-id="a6e1f-139">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="a6e1f-140">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="a6e1f-140">NOTES</span></span>

<span data-ttu-id="a6e1f-141">Starten Sie PowerShell mit der Option **als Administrator ausführen** , um dieses Cmdlet auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a6e1f-141">To run this cmdlet, start PowerShell by using the **Run as administrator** option.</span></span>

## <span data-ttu-id="a6e1f-142">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="a6e1f-142">RELATED LINKS</span></span>

[<span data-ttu-id="a6e1f-143">Get-Service</span><span class="sxs-lookup"><span data-stu-id="a6e1f-143">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="a6e1f-144">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="a6e1f-144">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="a6e1f-145">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="a6e1f-145">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="a6e1f-146">Set-Service</span><span class="sxs-lookup"><span data-stu-id="a6e1f-146">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="a6e1f-147">Start-Service</span><span class="sxs-lookup"><span data-stu-id="a6e1f-147">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="a6e1f-148">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="a6e1f-148">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="a6e1f-149">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="a6e1f-149">Suspend-Service</span></span>](Suspend-Service.md)

