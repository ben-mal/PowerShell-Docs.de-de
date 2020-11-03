---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/remove-pssnapin?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PSSnapin
ms.openlocfilehash: e74aff3e52c61f41a54664efbab9c0f195b0d409
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212780"
---
# <span data-ttu-id="24134-103">Remove-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="24134-103">Remove-PSSnapin</span></span>

## <span data-ttu-id="24134-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="24134-104">SYNOPSIS</span></span>
<span data-ttu-id="24134-105">Entfernt Windows PowerShell-Snap-Ins aus der aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="24134-105">Removes Windows PowerShell snap-ins from the current session.</span></span>

## <span data-ttu-id="24134-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="24134-106">SYNTAX</span></span>

```
Remove-PSSnapin [-Name] <String[]> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="24134-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="24134-107">DESCRIPTION</span></span>
<span data-ttu-id="24134-108">Mit dem Cmdlet " **Remove-PSSnapIn** " wird ein Windows PowerShell-Snap-in aus der aktuellen Sitzung entfernt.</span><span class="sxs-lookup"><span data-stu-id="24134-108">The **Remove-PSSnapin** cmdlet removes a Windows PowerShell snap-in from the current session.</span></span>
<span data-ttu-id="24134-109">Sie können es zum Entfernen von Snap-Ins verwenden, die Sie Windows PowerShell hinzugefügt haben. Sie können dieses Cmdlet nicht verwenden, um die mit Windows PowerShell installierten Snap-Ins zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="24134-109">You can use it to remove snap-ins that you have added to Windows PowerShell You cannot use this cmdlet to remove the snap-ins that are installed with Windows PowerShell.</span></span>

<span data-ttu-id="24134-110">Nachdem Sie ein Snap-in aus der aktuellen Sitzung entfernt haben, wird das Snap-in noch geladen, aber die Cmdlets und Anbieter im Snap-in sind in der Sitzung nicht mehr verfügbar.</span><span class="sxs-lookup"><span data-stu-id="24134-110">After you remove a snap-in from the current session, the snap-in is still loaded, but the cmdlets and providers in the snap-in are no longer available in the session.</span></span>

## <span data-ttu-id="24134-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="24134-111">EXAMPLES</span></span>

### <span data-ttu-id="24134-112">Beispiel 1: Entfernen eines Snap-Ins</span><span class="sxs-lookup"><span data-stu-id="24134-112">Example 1: Remove a snap-in</span></span>

```
PS C:\> remove-pssnapin -Name Microsoft.Exchange
```

<span data-ttu-id="24134-113">Mit diesem Befehl wird das **Microsoft. Exchange** -Snap-in aus der aktuellen Sitzung entfernt.</span><span class="sxs-lookup"><span data-stu-id="24134-113">This command removes the **Microsoft.Exchange** snap-in from the current session.</span></span>
<span data-ttu-id="24134-114">Wenn der Befehl abgeschlossen ist, sind die von dem Snap-In unterstützten Cmdlets und Anbieter in der Sitzung nicht mehr verfügbar.</span><span class="sxs-lookup"><span data-stu-id="24134-114">When the command is complete, the cmdlets and providers that the snap-in supported are not available in the session.</span></span>

### <span data-ttu-id="24134-115">Beispiel 2: Entfernen von Snap-Ins mithilfe von Namen mit der Pipeline</span><span class="sxs-lookup"><span data-stu-id="24134-115">Example 2: Remove snap-ins by using names with the pipeline</span></span>

```
PS C:\> Get-PSSnapIn smp* | Remove-PSSnapIn
```

<span data-ttu-id="24134-116">Dieser Befehl entfernt die Windows PowerShell-Snap-Ins, deren Namen mit "SMP" beginnen, aus der aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="24134-116">This command removes the Windows PowerShell snap-ins that have names that start with smp from the current session.</span></span>

<span data-ttu-id="24134-117">Der Befehl verwendet das **Get-PSSnapin-** Cmdlet, um Objekte zu erhalten, die die Snap-Ins darstellen. Der Pipeline Operator (|) sendet die Ergebnisse an das **Remove-PSSnapIn** -Cmdlet, das Sie aus der Sitzung entfernt.</span><span class="sxs-lookup"><span data-stu-id="24134-117">The command uses the **Get-PSSnapin** cmdlet to get objects that represent the snap-ins. The pipeline operator (|) sends the results to the **Remove-PSSnapin** cmdlet, which removes them from the session.</span></span>
<span data-ttu-id="24134-118">Die von diesem Snap-In unterstützten Anbieter und Cmdlets sind in der Sitzung nicht mehr verfügbar.</span><span class="sxs-lookup"><span data-stu-id="24134-118">The providers and cmdlets that this snap-in supports are no longer available in the session.</span></span>

<span data-ttu-id="24134-119">Wenn Sie Objekte über die Pipeline an **Remove-PSSnapIn** übergeben, werden die Namen der Objekte dem *Name* -Parameter zugeordnet, der Objekte aus der Pipeline annimmt, die über eine **Name** -Eigenschaft verfügen.</span><span class="sxs-lookup"><span data-stu-id="24134-119">When you pipe objects to **Remove-PSSnapin** , the names of the objects are associated with the *Name* parameter, which accepts objects from the pipeline that have a **Name** property.</span></span>

### <span data-ttu-id="24134-120">Beispiel 3: Entfernen von Snap-Ins mithilfe von Namen</span><span class="sxs-lookup"><span data-stu-id="24134-120">Example 3: Remove snap-ins by using names</span></span>

```
PS C:\> Remove-PSSnapin -Name *event*
```

<span data-ttu-id="24134-121">Dieser Befehl entfernt alle Windows PowerShell-Snap-Ins, deren Namen das Ereignis enthalten.</span><span class="sxs-lookup"><span data-stu-id="24134-121">This command removes all Windows PowerShell snap-ins that have names that include event.</span></span>

## <span data-ttu-id="24134-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="24134-122">PARAMETERS</span></span>

### <span data-ttu-id="24134-123">-Name</span><span class="sxs-lookup"><span data-stu-id="24134-123">-Name</span></span>
<span data-ttu-id="24134-124">Gibt die Namen der Windows PowerShell-Snap-Ins an, die aus der aktuellen Sitzung entfernt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="24134-124">Specifies the names of Windows PowerShell snap-ins to remove from the current session.</span></span>
<span data-ttu-id="24134-125">Platzhalterzeichen (\*) sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="24134-125">Wildcard characters (\*) are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="24134-126">-PassThru</span><span class="sxs-lookup"><span data-stu-id="24134-126">-PassThru</span></span>
<span data-ttu-id="24134-127">Gibt ein Objekt zurück, das das Snap-in darstellt.</span><span class="sxs-lookup"><span data-stu-id="24134-127">Returns an object that represents the snap-in.</span></span>
<span data-ttu-id="24134-128">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="24134-128">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="24134-129">-Confirm</span><span class="sxs-lookup"><span data-stu-id="24134-129">-Confirm</span></span>
<span data-ttu-id="24134-130">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="24134-130">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="24134-131">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="24134-131">-WhatIf</span></span>
<span data-ttu-id="24134-132">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="24134-132">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="24134-133">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="24134-133">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="24134-134">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="24134-134">CommonParameters</span></span>
<span data-ttu-id="24134-135">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="24134-135">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="24134-136">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="24134-136">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="24134-137">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="24134-137">INPUTS</span></span>

### <span data-ttu-id="24134-138">System. Management. Automation. pssnapininfo</span><span class="sxs-lookup"><span data-stu-id="24134-138">System.Management.Automation.PSSnapInInfo</span></span>
<span data-ttu-id="24134-139">Sie können ein Snap-in-Objekt über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="24134-139">You can pipe a snap-in object to this cmdlet.</span></span>

## <span data-ttu-id="24134-140">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="24134-140">OUTPUTS</span></span>

### <span data-ttu-id="24134-141">Keine, System. Management. Automation. pssnapininfo</span><span class="sxs-lookup"><span data-stu-id="24134-141">None, System.Management.Automation.PSSnapInInfo</span></span>
<span data-ttu-id="24134-142">Dieses Cmdlet generiert ein **System. Management. Automation. pssnapininfo** -Objekt, das das Snap-in darstellt, wenn Sie den *passthru* -Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="24134-142">This cmdlet generates a **System.Management.Automation.PSSnapInInfo** object that represents the snap-in, if you specify the *PassThru* parameter.</span></span>
<span data-ttu-id="24134-143">Standardmäßig generiert **Remove-PSSnapIn** keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="24134-143">By default, **Remove-PSSnapin** does not generate any output.</span></span>

## <span data-ttu-id="24134-144">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="24134-144">NOTES</span></span>

* <span data-ttu-id="24134-145">**Remove-PSSnapIn** überprüft die Version von Windows PowerShell nicht, bevor ein Snap-in aus der Sitzung entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="24134-145">**Remove-PSSnapin** does not check the version of Windows PowerShell before removing a snap-in from the session.</span></span> <span data-ttu-id="24134-146">Wenn ein Snap-In nicht entfernt werden kann, wird eine Warnung angezeigt und der Befehl führt zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="24134-146">If a snap-in cannot be removed, a warning appears and the command fails.</span></span>
* <span data-ttu-id="24134-147">**Remove-PSSnapIn** wirkt sich nur auf die aktuelle Sitzung aus.</span><span class="sxs-lookup"><span data-stu-id="24134-147">**Remove-PSSnapin** affects only the current session.</span></span> <span data-ttu-id="24134-148">Wenn Sie einen Add-PSSnapin-Befehl zu Ihrem Windows PowerShell-Profil hinzugefügt haben, sollten Sie den Befehl löschen, um das Snap-In aus zukünftigen Sitzungen zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="24134-148">If you have added an Add-PSSnapin command to your Windows PowerShell profile, you should delete the command to remove the snap-in from future sessions.</span></span> <span data-ttu-id="24134-149">Anweisungen erhalten Sie, wenn Sie eingeben `Get-Help about_Profiles` .</span><span class="sxs-lookup"><span data-stu-id="24134-149">For instructions, type `Get-Help about_Profiles`.</span></span>

## <span data-ttu-id="24134-150">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="24134-150">RELATED LINKS</span></span>

[<span data-ttu-id="24134-151">Add-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="24134-151">Add-PSSnapin</span></span>](Add-PSSnapin.md)

[<span data-ttu-id="24134-152">Get-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="24134-152">Get-PSSnapin</span></span>](Get-PSSnapin.md)
