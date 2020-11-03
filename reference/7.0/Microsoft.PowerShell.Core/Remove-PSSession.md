---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/remove-pssession?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PSSession
ms.openlocfilehash: aa6965b3a21c145ecccb284d43c6d0913bb31027
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93209879"
---
# <span data-ttu-id="33f55-103">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="33f55-103">Remove-PSSession</span></span>

## <span data-ttu-id="33f55-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="33f55-104">SYNOPSIS</span></span>
<span data-ttu-id="33f55-105">Schließt mindestens eine PowerShell-Sitzung (pssessions).</span><span class="sxs-lookup"><span data-stu-id="33f55-105">Closes one or more PowerShell sessions (PSSessions).</span></span>

## <span data-ttu-id="33f55-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="33f55-106">SYNTAX</span></span>

### <span data-ttu-id="33f55-107">ID (Standard)</span><span class="sxs-lookup"><span data-stu-id="33f55-107">Id (Default)</span></span>

```
Remove-PSSession [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="33f55-108">Sitzung</span><span class="sxs-lookup"><span data-stu-id="33f55-108">Session</span></span>

```
Remove-PSSession [-Session] <PSSession[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="33f55-109">ContainerId</span><span class="sxs-lookup"><span data-stu-id="33f55-109">ContainerId</span></span>

```
Remove-PSSession -ContainerId <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="33f55-110">VMId</span><span class="sxs-lookup"><span data-stu-id="33f55-110">VMId</span></span>

```
Remove-PSSession -VMId <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="33f55-111">VMName</span><span class="sxs-lookup"><span data-stu-id="33f55-111">VMName</span></span>

```
Remove-PSSession -VMName <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="33f55-112">InstanceId</span><span class="sxs-lookup"><span data-stu-id="33f55-112">InstanceId</span></span>

```
Remove-PSSession -InstanceId <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="33f55-113">Name</span><span class="sxs-lookup"><span data-stu-id="33f55-113">Name</span></span>

```
Remove-PSSession -Name <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="33f55-114">Computername</span><span class="sxs-lookup"><span data-stu-id="33f55-114">ComputerName</span></span>

```
Remove-PSSession [-ComputerName] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="33f55-115">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="33f55-115">DESCRIPTION</span></span>

<span data-ttu-id="33f55-116">Das **Remove-PSSession-** Cmdlet schließt PowerShell-Sitzungen ( **pssessions** ) in der aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="33f55-116">The **Remove-PSSession** cmdlet closes PowerShell sessions ( **PSSessions** ) in the current session.</span></span>
<span data-ttu-id="33f55-117">Es beendet alle Befehle, die in den **pssessions** ausgeführt werden, beendet die **PSSession** und gibt die Ressourcen frei, die von der **PSSession** verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="33f55-117">It stops any commands that are running in the **PSSessions** , ends the **PSSession** , and releases the resources that the **PSSession** was using.</span></span>
<span data-ttu-id="33f55-118">Wenn die **PSSession** mit einem Remote Computer verbunden ist, schließt dieses Cmdlet auch die Verbindung zwischen dem lokalen Computer und dem Remote Computer.</span><span class="sxs-lookup"><span data-stu-id="33f55-118">If the **PSSession** is connected to a remote computer, this cmdlet also closes the connection between the local and remote computers.</span></span>

<span data-ttu-id="33f55-119">Um eine **PSSession** zu entfernen, geben Sie *Name* , *Computer Name* , *ID* oder *InstanceId* der Sitzung ein.</span><span class="sxs-lookup"><span data-stu-id="33f55-119">To remove a **PSSession** , enter the *Name* , *ComputerName* , *ID* , or *InstanceID* of the session.</span></span>

<span data-ttu-id="33f55-120">Wenn Sie die *PSSession* in einer Variablen gespeichert haben, bleibt das Sitzungs Objekt in der Variablen, der Status der *PSSession* ist jedoch geschlossen.</span><span class="sxs-lookup"><span data-stu-id="33f55-120">If you have saved the *PSSession* in a variable, the session object remains in the variable, but the state of the *PSSession* is Closed.</span></span>

## <span data-ttu-id="33f55-121">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="33f55-121">EXAMPLES</span></span>

### <span data-ttu-id="33f55-122">Beispiel 1: Entfernen von Sitzungen mithilfe von IDs</span><span class="sxs-lookup"><span data-stu-id="33f55-122">Example 1: Remove sessions by using IDs</span></span>

```powershell
Remove-PSSession -Id 1, 2
```

<span data-ttu-id="33f55-123">Mit diesem Befehl werden die **pssessions** mit den IDs 1 und 2 entfernt.</span><span class="sxs-lookup"><span data-stu-id="33f55-123">This command removes the **PSSessions** that have IDs 1 and 2.</span></span>

### <span data-ttu-id="33f55-124">Beispiel 2: Entfernen aller Sitzungen in der aktuellen Sitzung</span><span class="sxs-lookup"><span data-stu-id="33f55-124">Example 2: Remove all the sessions in the current session</span></span>

```powershell
Get-PSSession | Remove-PSSession
Remove-PSSession -Session (Get-PSSession)
$s = Get-PSSession
Remove-PSSession -Session $s
```

<span data-ttu-id="33f55-125">Diese Befehle entfernen alle **pssessions** in der aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="33f55-125">These commands remove all of the **PSSessions** in the current session.</span></span>
<span data-ttu-id="33f55-126">Obwohl die drei Befehlsformate anders aussehen, haben sie die gleiche Wirkung.</span><span class="sxs-lookup"><span data-stu-id="33f55-126">Although the three command formats look different, they have the same effect.</span></span>

### <span data-ttu-id="33f55-127">Beispiel 3: Schließen von Sitzungen mithilfe von Namen</span><span class="sxs-lookup"><span data-stu-id="33f55-127">Example 3: Close sessions by using names</span></span>

```powershell
$r = Get-PSSession -ComputerName Serv*
$r | Remove-PSSession
```

<span data-ttu-id="33f55-128">Diese Befehle schließen die **pssessions** , die mit Computern verbunden sind, deren Namen mit "Serv" beginnen.</span><span class="sxs-lookup"><span data-stu-id="33f55-128">These commands close the **PSSessions** that are connected to computers that have names that begin with Serv.</span></span>

### <span data-ttu-id="33f55-129">Beispiel 4: Schließen von Sitzungen, die mit einem Port verbunden sind</span><span class="sxs-lookup"><span data-stu-id="33f55-129">Example 4: Close sessions connected to a port</span></span>

```powershell
Get-PSSession | where {$_.port -eq 90} | Remove-PSSession
```

<span data-ttu-id="33f55-130">Dieser Befehl schließt die **pssessions** , die mit Port 90 verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="33f55-130">This command closes the **PSSessions** that are connected to port 90.</span></span>
<span data-ttu-id="33f55-131">Sie können dieses Befehls Format verwenden, um **pssessions** nach anderen Eigenschaften als *Computer Name* , *Name* , *InstanceId* und *ID* zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="33f55-131">You can use this command format to identify **PSSessions** by properties other than *ComputerName* , *Name* , *InstanceID* , and *ID* .</span></span>

### <span data-ttu-id="33f55-132">Beispiel 5: Schließen einer Sitzung basierend auf der Instanz-ID</span><span class="sxs-lookup"><span data-stu-id="33f55-132">Example 5: Close a session based on instance ID</span></span>

```powershell
Get-PSSession | Format-Table ComputerName, InstanceID  -AutoSize
```

```Output
ComputerName InstanceId
------------ ----------------
Server01     875d231b-2788-4f36-9f67-2e50d63bb82a
localhost    c065ffa0-02c4-406e-84a3-dacb0d677868
Server02     4699cdbc-61d5-4e0d-b916-84f82ebede1f
Server03     4e5a3245-4c63-43e4-88d0-a7798bfc2414
TX-TEST-01   fc4e9dfa-f246-452d-9fa3-1adbdd64ae85 PS C:\> Remove-PSSession -InstanceID fc4e9dfa-f246-452d-9fa3-1adbdd64ae85
```

<span data-ttu-id="33f55-133">Diese Befehle zeigen, wie eine **PSSession** auf Grundlage Ihrer Instanz-ID oder **remoterunspaceid** geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="33f55-133">These commands show how to close a **PSSession** based on its instance ID, or **RemoteRunspaceID** .</span></span>

<span data-ttu-id="33f55-134">Der erste Befehl verwendet das **Get-PSSession** -Cmdlet, um die **pssessions** in der aktuellen Sitzung abzurufen.</span><span class="sxs-lookup"><span data-stu-id="33f55-134">The first command uses the **Get-PSSession** cmdlet to get the **PSSessions** in the current session.</span></span>
<span data-ttu-id="33f55-135">Er verwendet einen Pipeline Operator (|), um die **pssessions** an das Format-Table-Cmdlet zu senden, das die **Computername** -und **InstanceId-** Eigenschaften in einer Tabelle formatiert.</span><span class="sxs-lookup"><span data-stu-id="33f55-135">It uses a pipeline operator (|) to send the **PSSessions** to the Format-Table cmdlet, which formats their **ComputerName** and **InstanceID** properties in a table.</span></span>
<span data-ttu-id="33f55-136">Der *AutoSize* -Parameter komprimiert die Spalten für die Anzeige.</span><span class="sxs-lookup"><span data-stu-id="33f55-136">The *AutoSize* parameter compresses the columns for display.</span></span>

<span data-ttu-id="33f55-137">In der resultierenden Anzeige können Sie die zu schließende **PSSession** identifizieren und die *InstanceId* dieser **PSSession** kopieren und in den zweiten Befehl einfügen.</span><span class="sxs-lookup"><span data-stu-id="33f55-137">From the resulting display, you can identify the **PSSession** to be closed, and copy and paste the *InstanceID* of that **PSSession** into the second command.</span></span>

<span data-ttu-id="33f55-138">Der zweite Befehl verwendet das **Remove-PSSession-** Cmdlet, um die *PSSession* mit der angegebenen Instanz-ID zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="33f55-138">The second command uses the **Remove-PSSession** cmdlet to remove the *PSSession* with the specified instance ID.</span></span>

### <span data-ttu-id="33f55-139">Beispiel 6: Erstellen einer Funktion, die alle Sitzungen in der aktuellen Sitzung löscht</span><span class="sxs-lookup"><span data-stu-id="33f55-139">Example 6: Create a function that deletes all sessions in the current session</span></span>

```powershell
Function EndPSS { Get-PSSession | Remove-PSSession }
```

<span data-ttu-id="33f55-140">Diese Funktion löscht alle **pssessions** in der aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="33f55-140">This function deletes all of the **PSSessions** in the current session.</span></span>
<span data-ttu-id="33f55-141">Nachdem Sie diese Funktion dem PowerShell-Profil hinzugefügt haben, geben Sie ein, um alle Sitzungen zu löschen `EndPSS` .</span><span class="sxs-lookup"><span data-stu-id="33f55-141">After you add this function to your PowerShell profile, to delete all sessions, type `EndPSS`.</span></span>

## <span data-ttu-id="33f55-142">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="33f55-142">PARAMETERS</span></span>

### <span data-ttu-id="33f55-143">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="33f55-143">-ComputerName</span></span>

<span data-ttu-id="33f55-144">Gibt ein Array von Namen von Computern an.</span><span class="sxs-lookup"><span data-stu-id="33f55-144">Specifies an array of names of computers.</span></span>
<span data-ttu-id="33f55-145">Dieses Cmdlet schließt die **pssessions** , die mit den angegebenen Computern verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="33f55-145">This cmdlet closes the **PSSessions** that are connected to the specified computers.</span></span>
<span data-ttu-id="33f55-146">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="33f55-146">Wildcard characters are permitted.</span></span>

<span data-ttu-id="33f55-147">Geben Sie den NetBIOS-Namen, eine IP-Adresse oder den vollqualifizierten Domänennamen mindestens eines Computers ein.</span><span class="sxs-lookup"><span data-stu-id="33f55-147">Type the NetBIOS name, an IP address, or a fully qualified domain name of one or more remote computers.</span></span>
<span data-ttu-id="33f55-148">Um den lokalen Computer anzugeben, geben Sie den Computernamen, "localhost" oder einen Punkt (.) ein.</span><span class="sxs-lookup"><span data-stu-id="33f55-148">To specify the local computer, type the computer name, localhost, or a dot (.).</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerName
Aliases: Cn

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="33f55-149">-Containerid</span><span class="sxs-lookup"><span data-stu-id="33f55-149">-ContainerId</span></span>

<span data-ttu-id="33f55-150">Gibt ein Array von IDs von Containern an.</span><span class="sxs-lookup"><span data-stu-id="33f55-150">Specifies an array of IDs of containers.</span></span> <span data-ttu-id="33f55-151">Mit diesem Cmdlet werden Sitzungen für jeden der angegebenen Container entfernt.</span><span class="sxs-lookup"><span data-stu-id="33f55-151">This cmdlet removes sessions for each of the specified containers.</span></span> <span data-ttu-id="33f55-152">Verwenden Sie den `docker ps` Befehl, um eine Liste der Container-IDs abzurufen.</span><span class="sxs-lookup"><span data-stu-id="33f55-152">Use the `docker ps` command to get a list of container IDs.</span></span> <span data-ttu-id="33f55-153">Weitere Informationen finden Sie in der Hilfe zum [docker PS](https://docs.docker.com/engine/reference/commandline/ps/) -Befehl.</span><span class="sxs-lookup"><span data-stu-id="33f55-153">For more information, see the help for the [docker ps](https://docs.docker.com/engine/reference/commandline/ps/) command.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ContainerId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="33f55-154">-Id</span><span class="sxs-lookup"><span data-stu-id="33f55-154">-Id</span></span>

<span data-ttu-id="33f55-155">Gibt ein Array von IDs von Sitzungen an.</span><span class="sxs-lookup"><span data-stu-id="33f55-155">Specifies an array of IDs of sessions.</span></span>
<span data-ttu-id="33f55-156">Dieses Cmdlet schließt die *pssessions* mit den angegebenen IDs.</span><span class="sxs-lookup"><span data-stu-id="33f55-156">This cmdlet closes the *PSSessions* with the specified IDs.</span></span>
<span data-ttu-id="33f55-157">Geben Sie eine oder mehrere IDs ein, die durch Kommas getrennt sind, oder verwenden Sie den Bereichs Operator (..), um einen Bereich von IDs anzugeben.</span><span class="sxs-lookup"><span data-stu-id="33f55-157">Type one or more IDs, separated by commas, or use the range operator (..) to specify a range of IDs.</span></span>

<span data-ttu-id="33f55-158">Eine ID ist eine Ganzzahl, die die **PSSession** in der aktuellen Sitzung eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="33f55-158">An ID is an integer that uniquely identifies the **PSSession** in the current session.</span></span>
<span data-ttu-id="33f55-159">Es ist einfacher zu merken und einzugeben als die *InstanceId* , aber Sie ist nur in der aktuellen Sitzung eindeutig.</span><span class="sxs-lookup"><span data-stu-id="33f55-159">It is easier to remember and type than the *InstanceId* , but it is unique only in the current session.</span></span>
<span data-ttu-id="33f55-160">Um die ID einer **PSSession** zu ermitteln, führen Sie das Get-PSSession-Cmdlet ohne Parameter aus.</span><span class="sxs-lookup"><span data-stu-id="33f55-160">To find the ID of a **PSSession** , run the Get-PSSession cmdlet without parameters.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="33f55-161">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="33f55-161">-InstanceId</span></span>

<span data-ttu-id="33f55-162">Gibt ein Array von Instanz-IDs an.</span><span class="sxs-lookup"><span data-stu-id="33f55-162">Specifies an array of instance IDs.</span></span>
<span data-ttu-id="33f55-163">Dieses Cmdlet schließt die **pssessions** mit den angegebenen Instanz-IDs.</span><span class="sxs-lookup"><span data-stu-id="33f55-163">This cmdlet closes the **PSSessions** that have the specified instance IDs.</span></span>

<span data-ttu-id="33f55-164">Die Instanz-ID ist eine GUID, die eine **PSSession** in der aktuellen Sitzung eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="33f55-164">The instance ID is a GUID that uniquely identifies a **PSSession** in the current session.</span></span>
<span data-ttu-id="33f55-165">Die Instanz-ID ist eindeutig, auch wenn mehrere Sitzungen auf einem einzelnen Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="33f55-165">The instance ID is unique, even when you have multiple sessions running on a single computer.</span></span>

<span data-ttu-id="33f55-166">Die Instanz-ID wird in der **InstanceId-** Eigenschaft des Objekts gespeichert, das eine **PSSession** darstellt.</span><span class="sxs-lookup"><span data-stu-id="33f55-166">The instance ID is stored in the **InstanceID** property of the object that represents a **PSSession** .</span></span>
<span data-ttu-id="33f55-167">Um die **InstanceId** der **pssessions** in der aktuellen Sitzung zu suchen, geben Sie ein `Get-PSSession | Format-Table Name, ComputerName, InstanceId` .</span><span class="sxs-lookup"><span data-stu-id="33f55-167">To find the **InstanceID** of the **PSSessions** in the current session, type `Get-PSSession | Format-Table Name, ComputerName, InstanceId`.</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: InstanceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="33f55-168">-Name</span><span class="sxs-lookup"><span data-stu-id="33f55-168">-Name</span></span>

<span data-ttu-id="33f55-169">Gibt ein Array von anzeigen Amen von Sitzungen an.</span><span class="sxs-lookup"><span data-stu-id="33f55-169">Specifies an array of friendly names of sessions.</span></span>
<span data-ttu-id="33f55-170">Dieses Cmdlet schließt die **pssessions** mit den angegebenen anzeigen Amen.</span><span class="sxs-lookup"><span data-stu-id="33f55-170">This cmdlet closes the **PSSessions** that have the specified friendly names.</span></span>
<span data-ttu-id="33f55-171">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="33f55-171">Wildcard characters are permitted.</span></span>

<span data-ttu-id="33f55-172">Da der Anzeige Name einer **PSSession** möglicherweise nicht eindeutig ist, sollten Sie bei Verwendung des *Name* -Parameters auch den *WhatIf* -Parameter oder den *Confirm* -Parameter im **Remove-PSSession-** Befehl verwenden.</span><span class="sxs-lookup"><span data-stu-id="33f55-172">Because the friendly name of a **PSSession** might not be unique, when you use the *Name* parameter, consider also using the *WhatIf* or *Confirm* parameter in the **Remove-PSSession** command.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="33f55-173">-Sitzung</span><span class="sxs-lookup"><span data-stu-id="33f55-173">-Session</span></span>

<span data-ttu-id="33f55-174">Gibt die Sitzungs Objekte der zu schließenden **pssessions** an.</span><span class="sxs-lookup"><span data-stu-id="33f55-174">Specifies the session objects of the **PSSessions** to close.</span></span>
<span data-ttu-id="33f55-175">Geben Sie eine Variable ein, die die **pssessions** oder einen Befehl enthält, der die **pssessions** erstellt oder abruft, z. b. einen New-PSSession-oder **Get-PSSession** -Befehl.</span><span class="sxs-lookup"><span data-stu-id="33f55-175">Enter a variable that contains the **PSSessions** or a command that creates or gets the **PSSessions** , such as a New-PSSession or **Get-PSSession** command.</span></span>
<span data-ttu-id="33f55-176">Sie können ein oder mehrere Sitzungs Objekte auch über die Pipeline an **Remove-PSSession** übergeben.</span><span class="sxs-lookup"><span data-stu-id="33f55-176">You can also pipe one or more session objects to **Remove-PSSession** .</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession[]
Parameter Sets: Session
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="33f55-177">-VMID</span><span class="sxs-lookup"><span data-stu-id="33f55-177">-VMId</span></span>

<span data-ttu-id="33f55-178">Gibt ein Array mit der ID der virtuellen Computer an.</span><span class="sxs-lookup"><span data-stu-id="33f55-178">Specifies an array of ID of virtual machines.</span></span>
<span data-ttu-id="33f55-179">Dieses Cmdlet startet eine interaktive Sitzung mit jedem der angegebenen virtuellen Computer.</span><span class="sxs-lookup"><span data-stu-id="33f55-179">This cmdlet starts an interactive session with each of the specified virtual machines.</span></span>
<span data-ttu-id="33f55-180">Verwenden Sie den folgenden Befehl, um die verfügbaren virtuellen Computer anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="33f55-180">To see the virtual machines that are available to you, use the following command:</span></span>

`Get-VM | Select-Object -Property Name, ID`

```yaml
Type: System.Guid[]
Parameter Sets: VMId
Aliases: VMGuid

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="33f55-181">-VMName</span><span class="sxs-lookup"><span data-stu-id="33f55-181">-VMName</span></span>

<span data-ttu-id="33f55-182">Gibt ein Array von Namen von virtuellen Computern an.</span><span class="sxs-lookup"><span data-stu-id="33f55-182">Specifies an array of names of virtual machines.</span></span>
<span data-ttu-id="33f55-183">Dieses Cmdlet startet eine interaktive Sitzung mit jedem der angegebenen virtuellen Computer.</span><span class="sxs-lookup"><span data-stu-id="33f55-183">This cmdlet starts an interactive session with each of the specified virtual machines.</span></span>
<span data-ttu-id="33f55-184">Verwenden Sie das Cmdlet **Get-VM** , um die für Sie verfügbaren virtuellen Computer anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="33f55-184">To see the virtual machines that are available to you, use the **Get-VM** cmdlet.</span></span>

```yaml
Type: System.String[]
Parameter Sets: VMName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="33f55-185">-Confirm</span><span class="sxs-lookup"><span data-stu-id="33f55-185">-Confirm</span></span>

<span data-ttu-id="33f55-186">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="33f55-186">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="33f55-187">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="33f55-187">-WhatIf</span></span>

<span data-ttu-id="33f55-188">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="33f55-188">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="33f55-189">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="33f55-189">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="33f55-190">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="33f55-190">CommonParameters</span></span>

<span data-ttu-id="33f55-191">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="33f55-191">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="33f55-192">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="33f55-192">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="33f55-193">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="33f55-193">INPUTS</span></span>

### <span data-ttu-id="33f55-194">System. Management. Automation. Runspaces. PSSession</span><span class="sxs-lookup"><span data-stu-id="33f55-194">System.Management.Automation.Runspaces.PSSession</span></span>

<span data-ttu-id="33f55-195">Sie können ein Sitzungs Objekt über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="33f55-195">You can pipe a session object to this cmdlet.</span></span>

## <span data-ttu-id="33f55-196">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="33f55-196">OUTPUTS</span></span>

### <span data-ttu-id="33f55-197">Keine</span><span class="sxs-lookup"><span data-stu-id="33f55-197">None</span></span>

<span data-ttu-id="33f55-198">Dieses Cmdlet gibt keine Objekte zurück.</span><span class="sxs-lookup"><span data-stu-id="33f55-198">This cmdlet does not return any objects.</span></span>

## <span data-ttu-id="33f55-199">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="33f55-199">NOTES</span></span>

* <span data-ttu-id="33f55-200">Der *ID* -Parameter ist obligatorisch.</span><span class="sxs-lookup"><span data-stu-id="33f55-200">The *Id* parameter is mandatory.</span></span> <span data-ttu-id="33f55-201">Um alle **pssessions** in der aktuellen Sitzung zu löschen, geben Sie ein `Get-PSSession | Remove-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="33f55-201">To delete all the **PSSessions** in the current session, type `Get-PSSession | Remove-PSSession`.</span></span>
* <span data-ttu-id="33f55-202">Eine **PSSession** verwendet eine permanente Verbindung mit einem Remote Computer.</span><span class="sxs-lookup"><span data-stu-id="33f55-202">A **PSSession** uses a persistent connection to a remote computer.</span></span> <span data-ttu-id="33f55-203">Erstellen Sie eine **PSSession** , um eine Reihe von Befehlen auszuführen, die Daten gemeinsam nutzen.</span><span class="sxs-lookup"><span data-stu-id="33f55-203">Create a **PSSession** to run a series of commands that share data.</span></span> <span data-ttu-id="33f55-204">Geben Sie Folgendes ein, um weitere Informationen zu erhalten: `Get-Help about_PSSessions`.</span><span class="sxs-lookup"><span data-stu-id="33f55-204">For more information, type `Get-Help about_PSSessions`.</span></span>
* <span data-ttu-id="33f55-205">**Pssessions** sind spezifisch für die aktuelle Sitzung.</span><span class="sxs-lookup"><span data-stu-id="33f55-205">**PSSessions** are specific to the current session.</span></span> <span data-ttu-id="33f55-206">Wenn Sie eine Sitzung beenden, werden die **pssessions** , die Sie in dieser Sitzung erstellt haben, zwangsweise geschlossen.</span><span class="sxs-lookup"><span data-stu-id="33f55-206">When you end a session, the **PSSessions** that you created in that session are forcibly closed.</span></span>

## <span data-ttu-id="33f55-207">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="33f55-207">RELATED LINKS</span></span>

[<span data-ttu-id="33f55-208">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="33f55-208">Connect-PSSession</span></span>](Connect-PSSession.md)

[<span data-ttu-id="33f55-209">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="33f55-209">Disconnect-PSSession</span></span>](Disconnect-PSSession.md)

[<span data-ttu-id="33f55-210">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="33f55-210">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="33f55-211">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="33f55-211">Exit-PSSession</span></span>](Exit-PSSession.md)

[<span data-ttu-id="33f55-212">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="33f55-212">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="33f55-213">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="33f55-213">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="33f55-214">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="33f55-214">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="33f55-215">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="33f55-215">Receive-PSSession</span></span>](Receive-PSSession.md)

[<span data-ttu-id="33f55-216">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="33f55-216">about_PSSessions</span></span>](About/about_PSSessions.md)

[<span data-ttu-id="33f55-217">about_Remote</span><span class="sxs-lookup"><span data-stu-id="33f55-217">about_Remote</span></span>](About/about_Remote.md)
