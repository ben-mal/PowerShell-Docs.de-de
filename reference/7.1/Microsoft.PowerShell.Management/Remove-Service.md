---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-service?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Service
ms.openlocfilehash: dbe084b553587ba09a2ce4b76b0c662915c59808
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2020
ms.locfileid: "94347345"
---
# <span data-ttu-id="ec135-103">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="ec135-103">Remove-Service</span></span>

## <span data-ttu-id="ec135-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="ec135-104">SYNOPSIS</span></span>
<span data-ttu-id="ec135-105">Entfernt einen Windows-Dienst.</span><span class="sxs-lookup"><span data-stu-id="ec135-105">Removes a Windows service.</span></span>

## <span data-ttu-id="ec135-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ec135-106">SYNTAX</span></span>

### <span data-ttu-id="ec135-107">Name (Standard)</span><span class="sxs-lookup"><span data-stu-id="ec135-107">Name (Default)</span></span>

```
Remove-Service [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="ec135-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="ec135-108">InputObject</span></span>

```
Remove-Service [-InputObject <ServiceController>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="ec135-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ec135-109">DESCRIPTION</span></span>

<span data-ttu-id="ec135-110">Mit dem `Remove-Service` -Cmdlet wird ein Windows-Dienst in der Registrierung und in der Dienst Datenbank entfernt.</span><span class="sxs-lookup"><span data-stu-id="ec135-110">The `Remove-Service` cmdlet removes a Windows service in the registry and in the service database.</span></span>

<span data-ttu-id="ec135-111">Das `Remove-Service` Cmdlet wurde in PowerShell 6,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ec135-111">The `Remove-Service` cmdlet was introduced in PowerShell 6.0.</span></span>

## <span data-ttu-id="ec135-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="ec135-112">EXAMPLES</span></span>

### <span data-ttu-id="ec135-113">Beispiel 1: Entfernen eines Dienstanbieter</span><span class="sxs-lookup"><span data-stu-id="ec135-113">Example 1: Remove a service</span></span>

<span data-ttu-id="ec135-114">Dadurch wird ein Dienst mit dem Namen Test Service entfernt.</span><span class="sxs-lookup"><span data-stu-id="ec135-114">This removes a service named TestService.</span></span>

```powershell
Remove-Service -Name "TestService"
```

### <span data-ttu-id="ec135-115">Beispiel 2: Entfernen eines diensnamens mit dem anzeigen Amen</span><span class="sxs-lookup"><span data-stu-id="ec135-115">Example 2: Remove a service using the display name</span></span>

<span data-ttu-id="ec135-116">In diesem Beispiel wird ein Dienst mit dem Namen Test Service entfernt.</span><span class="sxs-lookup"><span data-stu-id="ec135-116">This example removes a service named TestService.</span></span> <span data-ttu-id="ec135-117">Der Befehl verwendet `Get-Service` , um ein Objekt zu erhalten, das den Test Service-Dienst mit dem anzeigen Amen darstellt.</span><span class="sxs-lookup"><span data-stu-id="ec135-117">The command uses `Get-Service` to get an object that represents the TestService service using the display name.</span></span> <span data-ttu-id="ec135-118">Der Pipeline Operator ( `|` ) übergibt das Objekt an `Remove-Service` , wodurch der Dienst entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="ec135-118">The pipeline operator (`|`) pipes the object to `Remove-Service`, which removes the service.</span></span>

```powershell
Get-Service -DisplayName "Test Service" | Remove-Service
```

## <span data-ttu-id="ec135-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ec135-119">PARAMETERS</span></span>

### <span data-ttu-id="ec135-120">-InputObject</span><span class="sxs-lookup"><span data-stu-id="ec135-120">-InputObject</span></span>

<span data-ttu-id="ec135-121">Gibt **ServiceController** -Objekte an, die die zu entfern tenden Dienste darstellen.</span><span class="sxs-lookup"><span data-stu-id="ec135-121">Specifies **ServiceController** objects that represent the services to remove.</span></span> <span data-ttu-id="ec135-122">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="ec135-122">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="ec135-123">-Name</span><span class="sxs-lookup"><span data-stu-id="ec135-123">-Name</span></span>

<span data-ttu-id="ec135-124">Gibt die Dienstnamen der zu entfernenden Dienste an.</span><span class="sxs-lookup"><span data-stu-id="ec135-124">Specifies the service names of the services to remove.</span></span> <span data-ttu-id="ec135-125">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="ec135-125">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="ec135-126">-Confirm</span><span class="sxs-lookup"><span data-stu-id="ec135-126">-Confirm</span></span>

<span data-ttu-id="ec135-127">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="ec135-127">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="ec135-128">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="ec135-128">-WhatIf</span></span>

<span data-ttu-id="ec135-129">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ec135-129">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="ec135-130">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ec135-130">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="ec135-131">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ec135-131">CommonParameters</span></span>

<span data-ttu-id="ec135-132">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ec135-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ec135-133">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ec135-133">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ec135-134">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="ec135-134">INPUTS</span></span>

### <span data-ttu-id="ec135-135">System. ServiceProcess. ServiceController, System. String</span><span class="sxs-lookup"><span data-stu-id="ec135-135">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="ec135-136">Sie können ein Dienst Objekt oder eine Zeichenfolge, die den Namen eines diensnamens enthält, über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="ec135-136">You can pipe a service object or a string that contains the name of a service to this cmdlet.</span></span>

## <span data-ttu-id="ec135-137">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="ec135-137">OUTPUTS</span></span>

### <span data-ttu-id="ec135-138">Keine</span><span class="sxs-lookup"><span data-stu-id="ec135-138">None</span></span>

<span data-ttu-id="ec135-139">Dieses Cmdlet gibt keine Ausgabe zurück.</span><span class="sxs-lookup"><span data-stu-id="ec135-139">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="ec135-140">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="ec135-140">NOTES</span></span>

<span data-ttu-id="ec135-141">Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ec135-141">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="ec135-142">Starten Sie PowerShell mit der Option **als Administrator ausführen** , um dieses Cmdlet auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ec135-142">To run this cmdlet, start PowerShell by using the **Run as administrator** option.</span></span>

## <span data-ttu-id="ec135-143">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="ec135-143">RELATED LINKS</span></span>

[<span data-ttu-id="ec135-144">Get-Service</span><span class="sxs-lookup"><span data-stu-id="ec135-144">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="ec135-145">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="ec135-145">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="ec135-146">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="ec135-146">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="ec135-147">Set-Service</span><span class="sxs-lookup"><span data-stu-id="ec135-147">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="ec135-148">Start-Service</span><span class="sxs-lookup"><span data-stu-id="ec135-148">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="ec135-149">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="ec135-149">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="ec135-150">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="ec135-150">Suspend-Service</span></span>](Suspend-Service.md)
