---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/remove-cimsession?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-CimSession
ms.openlocfilehash: 729b0d1c860d29190ab4b87b818dd7b89018bfd7
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210052"
---
# <span data-ttu-id="f1b31-103">Remove-CimSession</span><span class="sxs-lookup"><span data-stu-id="f1b31-103">Remove-CimSession</span></span>

## <span data-ttu-id="f1b31-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="f1b31-104">SYNOPSIS</span></span>
<span data-ttu-id="f1b31-105">Entfernt mindestens eine CIM-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="f1b31-105">Removes one or more CIM sessions.</span></span>

## <span data-ttu-id="f1b31-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f1b31-106">SYNTAX</span></span>

### <span data-ttu-id="f1b31-107">Cimsessionset (Standard)</span><span class="sxs-lookup"><span data-stu-id="f1b31-107">CimSessionSet (Default)</span></span>

```
Remove-CimSession [-CimSession] <CimSession[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="f1b31-108">Computernameset</span><span class="sxs-lookup"><span data-stu-id="f1b31-108">ComputerNameSet</span></span>

```
Remove-CimSession [-ComputerName] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="f1b31-109">Sessionidset</span><span class="sxs-lookup"><span data-stu-id="f1b31-109">SessionIdSet</span></span>

```
Remove-CimSession [-Id] <UInt32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="f1b31-110">Instanceidset</span><span class="sxs-lookup"><span data-stu-id="f1b31-110">InstanceIdSet</span></span>

```
Remove-CimSession -InstanceId <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="f1b31-111">Nameset</span><span class="sxs-lookup"><span data-stu-id="f1b31-111">NameSet</span></span>

```
Remove-CimSession -Name <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="f1b31-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f1b31-112">DESCRIPTION</span></span>

<span data-ttu-id="f1b31-113">Mit dem- `Remove-CimSession` Cmdlet werden ein oder mehrere CIM-Sitzungs Objekte aus der lokalen PowerShell-Sitzung entfernt.</span><span class="sxs-lookup"><span data-stu-id="f1b31-113">The `Remove-CimSession` cmdlet removes one or more CIM session objects from the local PowerShell session.</span></span>

## <span data-ttu-id="f1b31-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="f1b31-114">EXAMPLES</span></span>

### <span data-ttu-id="f1b31-115">Beispiel 1: Entfernen aller CIM-Sitzungen</span><span class="sxs-lookup"><span data-stu-id="f1b31-115">Example 1: Remove all the CIM sessions</span></span>

<span data-ttu-id="f1b31-116">In diesem Beispiel werden alle verfügbaren CIM-Sitzungen auf dem lokalen Computer mithilfe des Cmdlets [Get-cimsession](Get-CimSession.md) abgerufen und dann mithilfe von entfernt `Remove-CimSession` .</span><span class="sxs-lookup"><span data-stu-id="f1b31-116">This example retrieves all the available CIM sessions on the local computer using the [Get-CimSession](Get-CimSession.md) cmdlet, and then removes them using the `Remove-CimSession`.</span></span>

```powershell
Get-CimSession | Remove-CimSession
```

### <span data-ttu-id="f1b31-117">Beispiel 2: Entfernen einer bestimmten CIM-Sitzung</span><span class="sxs-lookup"><span data-stu-id="f1b31-117">Example 2: Remove a specific CIM session</span></span>

<span data-ttu-id="f1b31-118">In diesem Beispiel wird die CIM-Sitzung mit dem **ID** -Wert 5 entfernt.</span><span class="sxs-lookup"><span data-stu-id="f1b31-118">This example removes the CIM session that has an **Id** value of 5.</span></span>

```powershell
Remove-CimSession -Id 5
```

### <span data-ttu-id="f1b31-119">Beispiel 3: Anzeigen der Liste der zu entfernenden CIM-Sitzungen mit dem WhatIf-Parameter</span><span class="sxs-lookup"><span data-stu-id="f1b31-119">Example 3: Show the list of CIM sessions to remove by using the WhatIf parameter</span></span>

<span data-ttu-id="f1b31-120">In diesem Beispiel wird der allgemeine Parameter **WhatIf** verwendet, um anzugeben, dass die Deinstallation nicht ausgeführt werden soll, sondern nur, was geschehen würde, wenn Sie ausgeführt würde.</span><span class="sxs-lookup"><span data-stu-id="f1b31-120">This example uses the common parameter **WhatIf** to specify that the removal should not be done, but only output what would happen if it were done.</span></span>

```powershell
Remove-CimSession -Name a* -WhatIf
```

## <span data-ttu-id="f1b31-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f1b31-121">PARAMETERS</span></span>

### <span data-ttu-id="f1b31-122">-CimSession</span><span class="sxs-lookup"><span data-stu-id="f1b31-122">-CimSession</span></span>

<span data-ttu-id="f1b31-123">Gibt die Sitzungs Objekte der zu schließenden CIM-Sitzungen an.</span><span class="sxs-lookup"><span data-stu-id="f1b31-123">Specifies the session objects of the CIM sessions to close.</span></span>

<span data-ttu-id="f1b31-124">Geben Sie eine Variable ein, die die CIM-Sitzung enthält, oder einen Befehl, mit dem die CIM-Sitzung erstellt oder abgerufen wird, z [`New-CimSession`](New-CimSession.md) [`Get-CimSession`](Get-CimSession.md) . b. die Cmdlets oder.</span><span class="sxs-lookup"><span data-stu-id="f1b31-124">Enter a variable that contains the CIM session, or a command that creates or gets the CIM session, such as the [`New-CimSession`](New-CimSession.md) or [`Get-CimSession`](Get-CimSession.md) cmdlets.</span></span>
<span data-ttu-id="f1b31-125">Weitere Informationen finden Sie unter [about_CimSessions](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span><span class="sxs-lookup"><span data-stu-id="f1b31-125">For more information, see [about_CimSessions](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span></span>

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

### <span data-ttu-id="f1b31-126">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="f1b31-126">-ComputerName</span></span>

<span data-ttu-id="f1b31-127">Gibt ein Array von Namen von Computern an.</span><span class="sxs-lookup"><span data-stu-id="f1b31-127">Specifies an array of names of computers.</span></span> <span data-ttu-id="f1b31-128">Entfernt die Sitzungen, die eine Verbindung zu den angegebenen Computern herstellen.</span><span class="sxs-lookup"><span data-stu-id="f1b31-128">Removes the sessions that connect to the specified computers.</span></span> <span data-ttu-id="f1b31-129">Sie können einen voll qualifizierten Domänen Namen (Fully Qualified Domain Name, FQDN) oder einen NetBIOS-Namen angeben.</span><span class="sxs-lookup"><span data-stu-id="f1b31-129">You can specify a fully qualified domain name (FQDN) or a NetBIOS name.</span></span>

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

### <span data-ttu-id="f1b31-130">-Id</span><span class="sxs-lookup"><span data-stu-id="f1b31-130">-Id</span></span>

<span data-ttu-id="f1b31-131">Gibt die ID der zu entfernenden CIM-Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="f1b31-131">Specifies the ID of the CIM session to remove.</span></span> <span data-ttu-id="f1b31-132">Geben Sie mindestens eine durch Kommas getrennte ID an, oder verwenden Sie den Bereichs Operator ( `..` ), um einen Bereich von IDs anzugeben.</span><span class="sxs-lookup"><span data-stu-id="f1b31-132">Specify one or more IDs separated by commas, or use the range operator (`..`) to specify a range of IDs.</span></span> <span data-ttu-id="f1b31-133">Eine **ID** ist eine Ganzzahl, die die CIM-Sitzung in der aktuellen PowerShell-Sitzung eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="f1b31-133">An **Id** is an integer that uniquely identifies the CIM session in the current PowerShell session.</span></span>

<span data-ttu-id="f1b31-134">Weitere Informationen zum Bereichs Operator finden Sie unter [about_Operators](../Microsoft.PowerShell.Core/About/about_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="f1b31-134">For more information about the range operator, see [about_Operators](../Microsoft.PowerShell.Core/About/about_Operators.md).</span></span>

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

### <span data-ttu-id="f1b31-135">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="f1b31-135">-InstanceId</span></span>

<span data-ttu-id="f1b31-136">Gibt die Instanz-ID der zu entfernenden CIM-Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="f1b31-136">Specifies the instance ID of the CIM session to remove.</span></span> <span data-ttu-id="f1b31-137">**InstanceId** ist eine GUID (Global Unique Identifier), die eine CIM-Sitzung eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="f1b31-137">**InstanceId** is a Globally Unique Identifier (GUID) that uniquely identifies a CIM session.</span></span> <span data-ttu-id="f1b31-138">Die **InstanceId** ist eindeutig, auch wenn mehrere Sitzungen in PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f1b31-138">The **InstanceId** is unique, even when you have multiple sessions running in PowerShell.</span></span>

<span data-ttu-id="f1b31-139">Die **InstanceId** wird in der **InstanceId-** Eigenschaft des Objekts gespeichert, das eine CIM-Sitzung darstellt.</span><span class="sxs-lookup"><span data-stu-id="f1b31-139">The **InstanceId** is stored in the **InstanceId** property of the object that represents a CIM session.</span></span>

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

### <span data-ttu-id="f1b31-140">-Name</span><span class="sxs-lookup"><span data-stu-id="f1b31-140">-Name</span></span>

<span data-ttu-id="f1b31-141">Gibt den anzeigen amen der zu entfernenden CIM-Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="f1b31-141">Specifies the friendly name of the CIM session to remove.</span></span> <span data-ttu-id="f1b31-142">Mit diesem Parameter können Sie Platzhalter Zeichen verwenden.</span><span class="sxs-lookup"><span data-stu-id="f1b31-142">You can use wildcard characters with this parameter.</span></span>

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

### <span data-ttu-id="f1b31-143">-Confirm</span><span class="sxs-lookup"><span data-stu-id="f1b31-143">-Confirm</span></span>

<span data-ttu-id="f1b31-144">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="f1b31-144">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="f1b31-145">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="f1b31-145">-WhatIf</span></span>

<span data-ttu-id="f1b31-146">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f1b31-146">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="f1b31-147">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f1b31-147">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="f1b31-148">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f1b31-148">CommonParameters</span></span>

<span data-ttu-id="f1b31-149">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f1b31-149">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f1b31-150">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f1b31-150">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f1b31-151">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="f1b31-151">INPUTS</span></span>

### <span data-ttu-id="f1b31-152">Keine</span><span class="sxs-lookup"><span data-stu-id="f1b31-152">None</span></span>

<span data-ttu-id="f1b31-153">Dieses Cmdlet akzeptiert keine Eingabe Objekte.</span><span class="sxs-lookup"><span data-stu-id="f1b31-153">This cmdlet accepts no input objects.</span></span>

## <span data-ttu-id="f1b31-154">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="f1b31-154">OUTPUTS</span></span>

### <span data-ttu-id="f1b31-155">System.Object</span><span class="sxs-lookup"><span data-stu-id="f1b31-155">System.Object</span></span>

<span data-ttu-id="f1b31-156">Dieses Cmdlet gibt ein Objekt zurück, das CIM-Sitzungsinformationen enthält.</span><span class="sxs-lookup"><span data-stu-id="f1b31-156">This cmdlet returns an object that contains CIM session information.</span></span>

## <span data-ttu-id="f1b31-157">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="f1b31-157">NOTES</span></span>

## <span data-ttu-id="f1b31-158">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="f1b31-158">RELATED LINKS</span></span>

[<span data-ttu-id="f1b31-159">Get-CimSession</span><span class="sxs-lookup"><span data-stu-id="f1b31-159">Get-CimSession</span></span>](Get-CimSession.md)

[<span data-ttu-id="f1b31-160">New-CimSession</span><span class="sxs-lookup"><span data-stu-id="f1b31-160">New-CimSession</span></span>](New-CimSession.md)

[<span data-ttu-id="f1b31-161">about_CimSession</span><span class="sxs-lookup"><span data-stu-id="f1b31-161">about_CimSession</span></span>](../Microsoft.PowerShell.Core/About/about_CimSession.md)
