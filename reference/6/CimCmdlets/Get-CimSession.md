---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/get-cimsession?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-CimSession
ms.openlocfilehash: c40367d0458c3670b9d684cd0c3b4b2a3631b3e4
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215159"
---
# <span data-ttu-id="ca1c9-103">Get-CimSession</span><span class="sxs-lookup"><span data-stu-id="ca1c9-103">Get-CimSession</span></span>

## <span data-ttu-id="ca1c9-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="ca1c9-104">SYNOPSIS</span></span>
<span data-ttu-id="ca1c9-105">Ruft die CIM-Sitzungs Objekte aus der aktuellen Sitzung ab.</span><span class="sxs-lookup"><span data-stu-id="ca1c9-105">Gets the CIM session objects from the current session.</span></span>

## <span data-ttu-id="ca1c9-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ca1c9-106">SYNTAX</span></span>

### <span data-ttu-id="ca1c9-107">Computernameset (Standard)</span><span class="sxs-lookup"><span data-stu-id="ca1c9-107">ComputerNameSet (Default)</span></span>

```
Get-CimSession [[-ComputerName] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="ca1c9-108">Sessionidset</span><span class="sxs-lookup"><span data-stu-id="ca1c9-108">SessionIdSet</span></span>

```
Get-CimSession [-Id] <UInt32[]> [<CommonParameters>]
```

### <span data-ttu-id="ca1c9-109">Instanceidset</span><span class="sxs-lookup"><span data-stu-id="ca1c9-109">InstanceIdSet</span></span>

```
Get-CimSession -InstanceId <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="ca1c9-110">Nameset</span><span class="sxs-lookup"><span data-stu-id="ca1c9-110">NameSet</span></span>

```
Get-CimSession -Name <String[]> [<CommonParameters>]
```

## <span data-ttu-id="ca1c9-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ca1c9-111">DESCRIPTION</span></span>

<span data-ttu-id="ca1c9-112">Standardmäßig ruft das Cmdlet alle CIM-Sitzungen ab, die in der aktuellen PowerShell-Sitzung erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="ca1c9-112">By default, the cmdlet gets all of the CIM sessions created in the current PowerShell session.</span></span> <span data-ttu-id="ca1c9-113">Sie können die Parameter von verwenden, `Get-CimSession` um die Sitzungen für bestimmte Computer zu erhalten, oder Sie können Sitzungen anhand ihrer Namen oder anderer Bezeichner identifizieren.</span><span class="sxs-lookup"><span data-stu-id="ca1c9-113">You can use the parameters of `Get-CimSession` to get the sessions that are for particular computers, or you can identify sessions by their names or other identifiers.</span></span> <span data-ttu-id="ca1c9-114">`Get-CimSession` Ruft keine CIM-Sitzungen ab, die in anderen PowerShell-Sitzungen erstellt wurden oder auf anderen Computern erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="ca1c9-114">`Get-CimSession` does not get CIM sessions that were created in other PowerShell sessions or that were created on other computers.</span></span>

<span data-ttu-id="ca1c9-115">Weitere Informationen zu CIM-Sitzungen finden Sie unter [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span><span class="sxs-lookup"><span data-stu-id="ca1c9-115">For more information about CIM sessions, see [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span></span>

## <span data-ttu-id="ca1c9-116">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="ca1c9-116">EXAMPLES</span></span>

### <span data-ttu-id="ca1c9-117">Beispiel 1: erhalten von CIM-Sitzungen aus der aktuellen PowerShell-Sitzung</span><span class="sxs-lookup"><span data-stu-id="ca1c9-117">Example 1: Get CIM sessions from the current PowerShell session</span></span>

<span data-ttu-id="ca1c9-118">In diesem Beispiel werden CIM-Sitzungen mithilfe von " [New-cimsession](New-CimSession.md)" erstellt, und anschließend werden die CIM-Sitzungen mit abgerufen `Get-CimSession` .</span><span class="sxs-lookup"><span data-stu-id="ca1c9-118">This example creates CIM sessions using [New-CimSession](New-CimSession.md), and then gets the CIM sessions using `Get-CimSession`.</span></span>

```powershell
New-CimSession -ComputerName Server01,Server02
Get-CimSession
```

```Output
Id           : 1
Name         : CimSession1
InstanceId   : d1413bc3-162a-4cb8-9aec-4d2c61253d59
ComputerName : Server01
Protocol     : WSMAN

Id           : 2
Name         : CimSession2
InstanceId   : c0095981-52c5-4e7f-a5bb-c4c680541710
ComputerName : Server02
Protocol     : WSMAN
```

### <span data-ttu-id="ca1c9-119">Beispiel 2: beziehen der CIM-Sitzungen auf einem bestimmten Computer</span><span class="sxs-lookup"><span data-stu-id="ca1c9-119">Example 2: Get the CIM sessions to a specific computer</span></span>

<span data-ttu-id="ca1c9-120">In diesem Beispiel werden die CIM-Sitzungen abgerufen, die mit dem Computer namens **Server02** verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="ca1c9-120">This example gets the CIM sessions that are connected to the computer named **Server02** .</span></span>

```powershell
Get-CimSession -ComputerName Server02
```

```Output
Id           : 2
Name         : CimSession2
InstanceId   : c0095981-52c5-4e7f-a5bb-c4c680541710
ComputerName : Server02
Protocol     : WSMAN
```

### <span data-ttu-id="ca1c9-121">Beispiel 3: erhalten Sie eine Liste mit CIM-Sitzungen, und formatieren Sie dann die Liste.</span><span class="sxs-lookup"><span data-stu-id="ca1c9-121">Example 3: Get a list of CIM sessions and then format the list</span></span>

<span data-ttu-id="ca1c9-122">In diesem Beispiel werden alle CIM-Sitzungen in der aktuellen PowerShell-Sitzung abgerufen, und es wird eine Tabelle mit nur den Eigenschaften **Computername** und **InstanceId** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ca1c9-122">This example gets all CIM sessions in the current PowerShell session and displays a table containing only the **ComputerName** and **InstanceID** properties.</span></span>

```powershell
Get-CimSession | Format-Table -Property ComputerName,InstanceId
```

```Output
ComputerName InstanceId
------------ ----------
Server01     d1413bc3-162a-4cb8-9aec-4d2c61253d59
Server02     c0095981-52c5-4e7f-a5bb-c4c680541710
```

### <span data-ttu-id="ca1c9-123">Beispiel 4: alle CIM-Sitzungen mit bestimmten Namen</span><span class="sxs-lookup"><span data-stu-id="ca1c9-123">Example 4: Get all the CIM sessions that have specific names</span></span>

<span data-ttu-id="ca1c9-124">In diesem Beispiel werden alle CIM-Sitzungen abgerufen, deren Namen mit " **Serv** " beginnen.</span><span class="sxs-lookup"><span data-stu-id="ca1c9-124">This example gets all CIM sessions that have names that begin with **serv** .</span></span>

```powershell
Get-CimSession -ComputerName Serv*
```

```Output
Id           : 1
Name         : CimSession1
InstanceId   : d1413bc-162a-4cb8-9aec-4d2c61253d59
ComputerName : Server01
Protocol     : WSMAN

Id           : 2
Name         : CimSession2
InstanceId   : c0095981-52c5-4e7f-a5bb-c4c680541710
ComputerName : Server02
Protocol     : WSMAN
```

### <span data-ttu-id="ca1c9-125">Beispiel 5: beziehen einer bestimmten CIM-Sitzung</span><span class="sxs-lookup"><span data-stu-id="ca1c9-125">Example 5: Get a specific CIM session</span></span>

<span data-ttu-id="ca1c9-126">In diesem Beispiel wird die CIM-Sitzung mit der **ID** 2 abgerufen.</span><span class="sxs-lookup"><span data-stu-id="ca1c9-126">This example gets the CIM session that has an **Id** of 2.</span></span>

```powershell
Get-CimSession -ID 2
```

```Output
Id           : 2
Name         : CimSession2
InstanceId   : c0095981-52c5-4e7f-a5bb-c4c680541710
ComputerName : Server02
Protocol     : WSMAN
```

## <span data-ttu-id="ca1c9-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ca1c9-127">PARAMETERS</span></span>

### <span data-ttu-id="ca1c9-128">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="ca1c9-128">-ComputerName</span></span>

<span data-ttu-id="ca1c9-129">Gibt den Namen des Computers an, mit dem CIM-Sitzungen verbunden werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ca1c9-129">Specifies the name of the computer to get CIM sessions connected to.</span></span> <span data-ttu-id="ca1c9-130">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="ca1c9-130">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerNameSet
Aliases: CN, ServerName

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="ca1c9-131">-Id</span><span class="sxs-lookup"><span data-stu-id="ca1c9-131">-Id</span></span>

<span data-ttu-id="ca1c9-132">Gibt den Bezeichner der zu erzurufenden CIM-Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="ca1c9-132">Specifies the identifier of the CIM session to get.</span></span> <span data-ttu-id="ca1c9-133">Verwenden Sie für mehrere IDs Kommas, um die IDs zu trennen, oder verwenden Sie den Bereichs Operator ( `..` ), um einen Bereich von IDs anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ca1c9-133">For multiple IDs, use commas to separate the IDs or use the range operator (`..`) to specify a range of IDs.</span></span> <span data-ttu-id="ca1c9-134">Eine **ID** ist eine Ganzzahl, die die CIM-Sitzung innerhalb der aktuellen PowerShell-Sitzung eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="ca1c9-134">An **Id** is an integer that uniquely identifies the CIM session within the current PowerShell session.</span></span>

<span data-ttu-id="ca1c9-135">Weitere Informationen zum Bereichs Operator finden Sie unter [about_Operators](../Microsoft.PowerShell.Core/About/about_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="ca1c9-135">For more information about the range operator, see [about_Operators](../Microsoft.PowerShell.Core/About/about_Operators.md).</span></span>

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

### <span data-ttu-id="ca1c9-136">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="ca1c9-136">-InstanceId</span></span>

<span data-ttu-id="ca1c9-137">Gibt die Instanz-IDs der zu erzurufenden CIM-Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="ca1c9-137">Specifies the instance IDs of the CIM session to get.</span></span>

<span data-ttu-id="ca1c9-138">**InstanceId** ist ein global eindeutiger Bezeichner (GUID), der eine CIM-Sitzung eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="ca1c9-138">**InstanceId** is a globally-unique identifier (GUID) that uniquely identifies a CIM session.</span></span> <span data-ttu-id="ca1c9-139">Die **InstanceId** ist eindeutig, auch wenn mehrere Sitzungen in PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ca1c9-139">The **InstanceId** is unique, even when you have multiple sessions running in PowerShell.</span></span>

<span data-ttu-id="ca1c9-140">Die **InstanceId** wird in der **InstanceId-** Eigenschaft des Objekts gespeichert, das eine CIM-Sitzung darstellt.</span><span class="sxs-lookup"><span data-stu-id="ca1c9-140">The **InstanceId** is stored in the **InstanceId** property of the object that represents a CIM session.</span></span>

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

### <span data-ttu-id="ca1c9-141">-Name</span><span class="sxs-lookup"><span data-stu-id="ca1c9-141">-Name</span></span>

<span data-ttu-id="ca1c9-142">Ruft eine oder mehrere CIM-Sitzungen ab, die die angegebenen anzeigen Amen enthalten.</span><span class="sxs-lookup"><span data-stu-id="ca1c9-142">Gets one or more CIM sessions which contain the specified friendly names.</span></span> <span data-ttu-id="ca1c9-143">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="ca1c9-143">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="ca1c9-144">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ca1c9-144">CommonParameters</span></span>
<span data-ttu-id="ca1c9-145">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ca1c9-145">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ca1c9-146">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ca1c9-146">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ca1c9-147">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="ca1c9-147">INPUTS</span></span>

### <span data-ttu-id="ca1c9-148">Keine</span><span class="sxs-lookup"><span data-stu-id="ca1c9-148">None</span></span>

## <span data-ttu-id="ca1c9-149">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="ca1c9-149">OUTPUTS</span></span>

### <span data-ttu-id="ca1c9-150">Microsoft.Management.Infrastructure.CimSession</span><span class="sxs-lookup"><span data-stu-id="ca1c9-150">Microsoft.Management.Infrastructure.CimSession</span></span>

## <span data-ttu-id="ca1c9-151">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="ca1c9-151">NOTES</span></span>

## <span data-ttu-id="ca1c9-152">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="ca1c9-152">RELATED LINKS</span></span>

[<span data-ttu-id="ca1c9-153">Format-Table</span><span class="sxs-lookup"><span data-stu-id="ca1c9-153">Format-Table</span></span>](../microsoft.powershell.utility/format-table.md)

[<span data-ttu-id="ca1c9-154">New-CimSession</span><span class="sxs-lookup"><span data-stu-id="ca1c9-154">New-CimSession</span></span>](New-CimSession.md)

[<span data-ttu-id="ca1c9-155">Remove-CimSession</span><span class="sxs-lookup"><span data-stu-id="ca1c9-155">Remove-CimSession</span></span>](remove-cimsession.md)

[<span data-ttu-id="ca1c9-156">about_CimSession</span><span class="sxs-lookup"><span data-stu-id="ca1c9-156">about_CimSession</span></span>](../Microsoft.PowerShell.Core/About/about_CimSession.md)
