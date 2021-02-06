---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/remove-cimsession?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-CimSession
ms.openlocfilehash: a3ff2132c531df1ab19bf7149a55ea0df4a787a8
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598390"
---
# <span data-ttu-id="bcb3c-102">Remove-CimSession</span><span class="sxs-lookup"><span data-stu-id="bcb3c-102">Remove-CimSession</span></span>

## <span data-ttu-id="bcb3c-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="bcb3c-103">SYNOPSIS</span></span>
<span data-ttu-id="bcb3c-104">Entfernt mindestens eine CIM-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="bcb3c-104">Removes one or more CIM sessions.</span></span>

## <span data-ttu-id="bcb3c-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="bcb3c-105">SYNTAX</span></span>

### <span data-ttu-id="bcb3c-106">Cimsessionset (Standard)</span><span class="sxs-lookup"><span data-stu-id="bcb3c-106">CimSessionSet (Default)</span></span>

```
Remove-CimSession [-CimSession] <CimSession[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="bcb3c-107">Computernameset</span><span class="sxs-lookup"><span data-stu-id="bcb3c-107">ComputerNameSet</span></span>

```
Remove-CimSession [-ComputerName] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="bcb3c-108">Sessionidset</span><span class="sxs-lookup"><span data-stu-id="bcb3c-108">SessionIdSet</span></span>

```
Remove-CimSession [-Id] <UInt32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="bcb3c-109">Instanceidset</span><span class="sxs-lookup"><span data-stu-id="bcb3c-109">InstanceIdSet</span></span>

```
Remove-CimSession -InstanceId <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="bcb3c-110">Nameset</span><span class="sxs-lookup"><span data-stu-id="bcb3c-110">NameSet</span></span>

```
Remove-CimSession -Name <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="bcb3c-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bcb3c-111">DESCRIPTION</span></span>

<span data-ttu-id="bcb3c-112">Mit dem- `Remove-CimSession` Cmdlet werden ein oder mehrere CIM-Sitzungs Objekte aus der lokalen PowerShell-Sitzung entfernt.</span><span class="sxs-lookup"><span data-stu-id="bcb3c-112">The `Remove-CimSession` cmdlet removes one or more CIM session objects from the local PowerShell session.</span></span>

## <span data-ttu-id="bcb3c-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="bcb3c-113">EXAMPLES</span></span>

### <span data-ttu-id="bcb3c-114">Beispiel 1: Entfernen aller CIM-Sitzungen</span><span class="sxs-lookup"><span data-stu-id="bcb3c-114">Example 1: Remove all the CIM sessions</span></span>

<span data-ttu-id="bcb3c-115">In diesem Beispiel werden alle verfügbaren CIM-Sitzungen auf dem lokalen Computer mithilfe des Cmdlets [Get-cimsession](Get-CimSession.md) abgerufen und dann mithilfe von entfernt `Remove-CimSession` .</span><span class="sxs-lookup"><span data-stu-id="bcb3c-115">This example retrieves all the available CIM sessions on the local computer using the [Get-CimSession](Get-CimSession.md) cmdlet, and then removes them using the `Remove-CimSession`.</span></span>

```powershell
Get-CimSession | Remove-CimSession
```

### <span data-ttu-id="bcb3c-116">Beispiel 2: Entfernen einer bestimmten CIM-Sitzung</span><span class="sxs-lookup"><span data-stu-id="bcb3c-116">Example 2: Remove a specific CIM session</span></span>

<span data-ttu-id="bcb3c-117">In diesem Beispiel wird die CIM-Sitzung mit dem **ID** -Wert 5 entfernt.</span><span class="sxs-lookup"><span data-stu-id="bcb3c-117">This example removes the CIM session that has an **Id** value of 5.</span></span>

```powershell
Remove-CimSession -Id 5
```

### <span data-ttu-id="bcb3c-118">Beispiel 3: Anzeigen der Liste der zu entfernenden CIM-Sitzungen mit dem WhatIf-Parameter</span><span class="sxs-lookup"><span data-stu-id="bcb3c-118">Example 3: Show the list of CIM sessions to remove by using the WhatIf parameter</span></span>

<span data-ttu-id="bcb3c-119">In diesem Beispiel wird der allgemeine Parameter **WhatIf** verwendet, um anzugeben, dass die Deinstallation nicht ausgeführt werden soll, sondern nur, was geschehen würde, wenn Sie ausgeführt würde.</span><span class="sxs-lookup"><span data-stu-id="bcb3c-119">This example uses the common parameter **WhatIf** to specify that the removal should not be done, but only output what would happen if it were done.</span></span>

```powershell
Remove-CimSession -Name a* -WhatIf
```

## <span data-ttu-id="bcb3c-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bcb3c-120">PARAMETERS</span></span>

### <span data-ttu-id="bcb3c-121">-CimSession</span><span class="sxs-lookup"><span data-stu-id="bcb3c-121">-CimSession</span></span>

<span data-ttu-id="bcb3c-122">Gibt die Sitzungs Objekte der zu schließenden CIM-Sitzungen an.</span><span class="sxs-lookup"><span data-stu-id="bcb3c-122">Specifies the session objects of the CIM sessions to close.</span></span>

<span data-ttu-id="bcb3c-123">Geben Sie eine Variable ein, die die CIM-Sitzung enthält, oder einen Befehl, mit dem die CIM-Sitzung erstellt oder abgerufen wird, z [`New-CimSession`](New-CimSession.md) [`Get-CimSession`](Get-CimSession.md) . b. die Cmdlets oder.</span><span class="sxs-lookup"><span data-stu-id="bcb3c-123">Enter a variable that contains the CIM session, or a command that creates or gets the CIM session, such as the [`New-CimSession`](New-CimSession.md) or [`Get-CimSession`](Get-CimSession.md) cmdlets.</span></span>
<span data-ttu-id="bcb3c-124">Weitere Informationen finden Sie unter [about_CimSessions](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span><span class="sxs-lookup"><span data-stu-id="bcb3c-124">For more information, see [about_CimSessions](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: CimSessionSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="bcb3c-125">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="bcb3c-125">-ComputerName</span></span>

<span data-ttu-id="bcb3c-126">Gibt ein Array von Namen von Computern an.</span><span class="sxs-lookup"><span data-stu-id="bcb3c-126">Specifies an array of names of computers.</span></span> <span data-ttu-id="bcb3c-127">Entfernt die Sitzungen, die eine Verbindung zu den angegebenen Computern herstellen.</span><span class="sxs-lookup"><span data-stu-id="bcb3c-127">Removes the sessions that connect to the specified computers.</span></span> <span data-ttu-id="bcb3c-128">Sie können einen voll qualifizierten Domänen Namen (Fully Qualified Domain Name, FQDN) oder einen NetBIOS-Namen angeben.</span><span class="sxs-lookup"><span data-stu-id="bcb3c-128">You can specify a fully qualified domain name (FQDN) or a NetBIOS name.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerNameSet
Aliases: CN, ServerName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="bcb3c-129">-Id</span><span class="sxs-lookup"><span data-stu-id="bcb3c-129">-Id</span></span>

<span data-ttu-id="bcb3c-130">Gibt die ID der zu entfernenden CIM-Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="bcb3c-130">Specifies the ID of the CIM session to remove.</span></span> <span data-ttu-id="bcb3c-131">Geben Sie mindestens eine durch Kommas getrennte ID an, oder verwenden Sie den Bereichs Operator ( `..` ), um einen Bereich von IDs anzugeben.</span><span class="sxs-lookup"><span data-stu-id="bcb3c-131">Specify one or more IDs separated by commas, or use the range operator (`..`) to specify a range of IDs.</span></span> <span data-ttu-id="bcb3c-132">Eine **ID** ist eine Ganzzahl, die die CIM-Sitzung in der aktuellen PowerShell-Sitzung eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="bcb3c-132">An **Id** is an integer that uniquely identifies the CIM session in the current PowerShell session.</span></span>

<span data-ttu-id="bcb3c-133">Weitere Informationen zum Bereichs Operator finden Sie unter [about_Operators](../Microsoft.PowerShell.Core/About/about_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="bcb3c-133">For more information about the range operator, see [about_Operators](../Microsoft.PowerShell.Core/About/about_Operators.md).</span></span>

```yaml
Type: System.UInt32[]
Parameter Sets: SessionIdSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="bcb3c-134">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="bcb3c-134">-InstanceId</span></span>

<span data-ttu-id="bcb3c-135">Gibt die Instanz-ID der zu entfernenden CIM-Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="bcb3c-135">Specifies the instance ID of the CIM session to remove.</span></span> <span data-ttu-id="bcb3c-136">**InstanceId** ist eine GUID (Global Unique Identifier), die eine CIM-Sitzung eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="bcb3c-136">**InstanceId** is a Globally Unique Identifier (GUID) that uniquely identifies a CIM session.</span></span> <span data-ttu-id="bcb3c-137">Die **InstanceId** ist eindeutig, auch wenn mehrere Sitzungen in PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="bcb3c-137">The **InstanceId** is unique, even when you have multiple sessions running in PowerShell.</span></span>

<span data-ttu-id="bcb3c-138">Die **InstanceId** wird in der **InstanceId-** Eigenschaft des Objekts gespeichert, das eine CIM-Sitzung darstellt.</span><span class="sxs-lookup"><span data-stu-id="bcb3c-138">The **InstanceId** is stored in the **InstanceId** property of the object that represents a CIM session.</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: InstanceIdSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="bcb3c-139">-Name</span><span class="sxs-lookup"><span data-stu-id="bcb3c-139">-Name</span></span>

<span data-ttu-id="bcb3c-140">Gibt den anzeigen amen der zu entfernenden CIM-Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="bcb3c-140">Specifies the friendly name of the CIM session to remove.</span></span> <span data-ttu-id="bcb3c-141">Mit diesem Parameter können Sie Platzhalter Zeichen verwenden.</span><span class="sxs-lookup"><span data-stu-id="bcb3c-141">You can use wildcard characters with this parameter.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="bcb3c-142">-Confirm</span><span class="sxs-lookup"><span data-stu-id="bcb3c-142">-Confirm</span></span>

<span data-ttu-id="bcb3c-143">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="bcb3c-143">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="bcb3c-144">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="bcb3c-144">-WhatIf</span></span>

<span data-ttu-id="bcb3c-145">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="bcb3c-145">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="bcb3c-146">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="bcb3c-146">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="bcb3c-147">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="bcb3c-147">CommonParameters</span></span>

<span data-ttu-id="bcb3c-148">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="bcb3c-148">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="bcb3c-149">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="bcb3c-149">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="bcb3c-150">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="bcb3c-150">INPUTS</span></span>

### <span data-ttu-id="bcb3c-151">Keine</span><span class="sxs-lookup"><span data-stu-id="bcb3c-151">None</span></span>

<span data-ttu-id="bcb3c-152">Dieses Cmdlet akzeptiert keine Eingabe Objekte.</span><span class="sxs-lookup"><span data-stu-id="bcb3c-152">This cmdlet accepts no input objects.</span></span>

## <span data-ttu-id="bcb3c-153">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="bcb3c-153">OUTPUTS</span></span>

### <span data-ttu-id="bcb3c-154">System.Object</span><span class="sxs-lookup"><span data-stu-id="bcb3c-154">System.Object</span></span>

<span data-ttu-id="bcb3c-155">Dieses Cmdlet gibt ein Objekt zurück, das CIM-Sitzungsinformationen enthält.</span><span class="sxs-lookup"><span data-stu-id="bcb3c-155">This cmdlet returns an object that contains CIM session information.</span></span>

## <span data-ttu-id="bcb3c-156">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="bcb3c-156">NOTES</span></span>

## <span data-ttu-id="bcb3c-157">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="bcb3c-157">RELATED LINKS</span></span>

[<span data-ttu-id="bcb3c-158">Get-CimSession</span><span class="sxs-lookup"><span data-stu-id="bcb3c-158">Get-CimSession</span></span>](Get-CimSession.md)

[<span data-ttu-id="bcb3c-159">New-CimSession</span><span class="sxs-lookup"><span data-stu-id="bcb3c-159">New-CimSession</span></span>](New-CimSession.md)

[<span data-ttu-id="bcb3c-160">about_CimSession</span><span class="sxs-lookup"><span data-stu-id="bcb3c-160">about_CimSession</span></span>](../Microsoft.PowerShell.Core/About/about_CimSession.md)

