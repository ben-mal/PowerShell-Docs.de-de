---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/remove-localgroup?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-LocalGroup
ms.openlocfilehash: 6a2f921972fef1794581b301df6e7439e56c7f47
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214676"
---
# <span data-ttu-id="36eee-103">Remove-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="36eee-103">Remove-LocalGroup</span></span>

## <span data-ttu-id="36eee-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="36eee-104">SYNOPSIS</span></span>
<span data-ttu-id="36eee-105">Löscht lokale Sicherheitsgruppen.</span><span class="sxs-lookup"><span data-stu-id="36eee-105">Deletes local security groups.</span></span>

## <span data-ttu-id="36eee-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="36eee-106">SYNTAX</span></span>

### <span data-ttu-id="36eee-107">InputObject</span><span class="sxs-lookup"><span data-stu-id="36eee-107">InputObject</span></span>

```
Remove-LocalGroup [-InputObject] <LocalGroup[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="36eee-108">Standard</span><span class="sxs-lookup"><span data-stu-id="36eee-108">Default</span></span>

```
Remove-LocalGroup [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="36eee-109">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="36eee-109">SecurityIdentifier</span></span>

```
Remove-LocalGroup [-SID] <SecurityIdentifier[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="36eee-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="36eee-110">DESCRIPTION</span></span>
<span data-ttu-id="36eee-111">Mit dem " **Remove-localgroup"-** Cmdlet werden lokale Sicherheitsgruppen gelöscht.</span><span class="sxs-lookup"><span data-stu-id="36eee-111">The **Remove-LocalGroup** cmdlet deletes local security groups.</span></span>
<span data-ttu-id="36eee-112">Mit diesem Cmdlet wird nur eine lokale Gruppe gelöscht.</span><span class="sxs-lookup"><span data-stu-id="36eee-112">This cmdlet deletes only a local group.</span></span>
<span data-ttu-id="36eee-113">Die Benutzerkonten, Computer Konten oder Gruppenkonten, die zu dieser Gruppe gehören, werden nicht gelöscht.</span><span class="sxs-lookup"><span data-stu-id="36eee-113">It does not delete the user accounts, computer accounts, or group accounts that belong to that group.</span></span>
<span data-ttu-id="36eee-114">Eine gelöschte Gruppe kann nicht wieder hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="36eee-114">You cannot recover a deleted group.</span></span>

<span data-ttu-id="36eee-115">Wenn Sie eine Gruppe löschen und dann eine andere Gruppe mit demselben Gruppennamen erstellen, müssen Sie neue Berechtigungen für die neue Gruppe festlegen.</span><span class="sxs-lookup"><span data-stu-id="36eee-115">If you delete a group and then create another group that has the same group name, you must set new permissions for the new group.</span></span>
<span data-ttu-id="36eee-116">Die neue Gruppe erbt nicht die Berechtigungen, die der Gruppe zugewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="36eee-116">The new group does not inherit the permissions that were assigned to the group.</span></span>

> [!NOTE]
> <span data-ttu-id="36eee-117">Das Microsoft. PowerShell. LocalAccounts-Modul ist in der 32-Bit-PowerShell auf einem 64-Bit-System nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="36eee-117">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="36eee-118">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="36eee-118">EXAMPLES</span></span>

### <span data-ttu-id="36eee-119">Beispiel 1: Löschen einer Sicherheitsgruppe</span><span class="sxs-lookup"><span data-stu-id="36eee-119">Example 1: Delete a security group</span></span>

```
PS C:\> Remove-LocalGroup -Name "SecurityGroup04"
```

<span data-ttu-id="36eee-120">Dieser Befehl löscht die Gruppe mit dem Namen SecurityGroup04.</span><span class="sxs-lookup"><span data-stu-id="36eee-120">This command deletes the group named SecurityGroup04.</span></span>

## <span data-ttu-id="36eee-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="36eee-121">PARAMETERS</span></span>

### <span data-ttu-id="36eee-122">-InputObject</span><span class="sxs-lookup"><span data-stu-id="36eee-122">-InputObject</span></span>
<span data-ttu-id="36eee-123">Gibt ein Array von Sicherheitsgruppen an, die von diesem Cmdlet gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="36eee-123">Specifies an array of security groups that this cmdlet deletes.</span></span>
<span data-ttu-id="36eee-124">Verwenden Sie das Cmdlet "Get-LocalGroup", um Gruppen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="36eee-124">To obtain groups, use the Get-LocalGroup cmdlet.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.LocalGroup[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="36eee-125">-Name</span><span class="sxs-lookup"><span data-stu-id="36eee-125">-Name</span></span>
<span data-ttu-id="36eee-126">Gibt ein Array von Namen der Sicherheitsgruppen an, die von diesem Cmdlet gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="36eee-126">Specifies an array of names of the security groups that this cmdlet deletes.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="36eee-127">-SID</span><span class="sxs-lookup"><span data-stu-id="36eee-127">-SID</span></span>
<span data-ttu-id="36eee-128">Gibt ein Array von Sicherheits-IDs (SIDs) von Sicherheitsgruppen an, die von diesem Cmdlet gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="36eee-128">Specifies an array of security IDs (SIDs) of security groups that this cmdlet deletes.</span></span>

```yaml
Type: System.Security.Principal.SecurityIdentifier[]
Parameter Sets: SecurityIdentifier
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="36eee-129">-Confirm</span><span class="sxs-lookup"><span data-stu-id="36eee-129">-Confirm</span></span>
<span data-ttu-id="36eee-130">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="36eee-130">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="36eee-131">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="36eee-131">-WhatIf</span></span>
<span data-ttu-id="36eee-132">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="36eee-132">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="36eee-133">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="36eee-133">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="36eee-134">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="36eee-134">CommonParameters</span></span>
<span data-ttu-id="36eee-135">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="36eee-135">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="36eee-136">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="36eee-136">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="36eee-137">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="36eee-137">INPUTS</span></span>

### <span data-ttu-id="36eee-138">System. Management. Automation. securityaccountmanager. localgroup, System. String, System. Security. Principal. SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="36eee-138">System.Management.Automation.SecurityAccountsManager.LocalGroup, System.String, System.Security.Principal.SecurityIdentifier</span></span>
<span data-ttu-id="36eee-139">Sie können eine Sicherheitsgruppe, eine Zeichenfolge oder eine SID an dieses Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="36eee-139">You can pipe a security group, a string, or a SID to this cmdlet.</span></span>

## <span data-ttu-id="36eee-140">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="36eee-140">OUTPUTS</span></span>

### <span data-ttu-id="36eee-141">Keine</span><span class="sxs-lookup"><span data-stu-id="36eee-141">None</span></span>
<span data-ttu-id="36eee-142">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="36eee-142">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="36eee-143">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="36eee-143">NOTES</span></span>

* <span data-ttu-id="36eee-144">Mit diesem Cmdlet können die folgenden Standard Gruppen nicht gelöscht werden:</span><span class="sxs-lookup"><span data-stu-id="36eee-144">This cmdlet cannot delete the following default groups:</span></span>

- <span data-ttu-id="36eee-145">Administratoren</span><span class="sxs-lookup"><span data-stu-id="36eee-145">Administrators</span></span>
- <span data-ttu-id="36eee-146">Sicherungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="36eee-146">Backup Operators</span></span>
- <span data-ttu-id="36eee-147">Kryptografie-Operatoren</span><span class="sxs-lookup"><span data-stu-id="36eee-147">Cryptographic Operators</span></span>
- <span data-ttu-id="36eee-148">Distributed COM-Benutzer</span><span class="sxs-lookup"><span data-stu-id="36eee-148">Distributed COM Users</span></span>
- <span data-ttu-id="36eee-149">Event Log Readers</span><span class="sxs-lookup"><span data-stu-id="36eee-149">Event Log Readers</span></span>
- <span data-ttu-id="36eee-150">Gäste</span><span class="sxs-lookup"><span data-stu-id="36eee-150">Guests</span></span>
- <span data-ttu-id="36eee-151">Hyper-V-Administratoren</span><span class="sxs-lookup"><span data-stu-id="36eee-151">Hyper-V Administrators</span></span>
- <span data-ttu-id="36eee-152">IIS_IUSRS</span><span class="sxs-lookup"><span data-stu-id="36eee-152">IIS_IUSRS</span></span>
- <span data-ttu-id="36eee-153">Netzwerkkonfigurations-Operatoren</span><span class="sxs-lookup"><span data-stu-id="36eee-153">Network Configuration Operators</span></span>
- <span data-ttu-id="36eee-154">Leistungsprotokollbenutzer</span><span class="sxs-lookup"><span data-stu-id="36eee-154">Performance Log Users</span></span>
- <span data-ttu-id="36eee-155">Systemmonitorbenutzer</span><span class="sxs-lookup"><span data-stu-id="36eee-155">Performance Monitor Users</span></span>
- <span data-ttu-id="36eee-156">Powerusers</span><span class="sxs-lookup"><span data-stu-id="36eee-156">Power Users</span></span>
- <span data-ttu-id="36eee-157">Remotedesktopbenutzer</span><span class="sxs-lookup"><span data-stu-id="36eee-157">Remote Desktop Users</span></span>
- <span data-ttu-id="36eee-158">Remoteverwaltungsbenutzer</span><span class="sxs-lookup"><span data-stu-id="36eee-158">Remote Management Users</span></span>
- <span data-ttu-id="36eee-159">Replicator</span><span class="sxs-lookup"><span data-stu-id="36eee-159">Replicator</span></span>
- <span data-ttu-id="36eee-160">Benutzer</span><span class="sxs-lookup"><span data-stu-id="36eee-160">Users</span></span>
- <span data-ttu-id="36eee-161">WinRMRemoteWMIUsers__</span><span class="sxs-lookup"><span data-stu-id="36eee-161">WinRMRemoteWMIUsers__</span></span>

* <span data-ttu-id="36eee-162">Die **principalsource** -Eigenschaft ist eine Eigenschaft für die Objekte " **LocalUser** ", " **localgroup** " und " **localprincipal** ", die die Quelle des Objekts beschreiben.</span><span class="sxs-lookup"><span data-stu-id="36eee-162">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="36eee-163">Folgende Quellen sind möglich:</span><span class="sxs-lookup"><span data-stu-id="36eee-163">The possible sources are as follows:</span></span>

- <span data-ttu-id="36eee-164">Lokal</span><span class="sxs-lookup"><span data-stu-id="36eee-164">Local</span></span>
- <span data-ttu-id="36eee-165">Active Directory</span><span class="sxs-lookup"><span data-stu-id="36eee-165">Active Directory</span></span>
- <span data-ttu-id="36eee-166">Azure Active Directory-Gruppe</span><span class="sxs-lookup"><span data-stu-id="36eee-166">Azure Active Directory group</span></span>
- <span data-ttu-id="36eee-167">Microsoft-Konto</span><span class="sxs-lookup"><span data-stu-id="36eee-167">Microsoft Account</span></span>

<span data-ttu-id="36eee-168">**Principalsource** wird nur von Windows 10, Windows Server 2016 und neueren Versionen des Windows-Betriebssystems unterstützt.</span><span class="sxs-lookup"><span data-stu-id="36eee-168">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="36eee-169">Bei früheren Versionen ist die-Eigenschaft leer.</span><span class="sxs-lookup"><span data-stu-id="36eee-169">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="36eee-170">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="36eee-170">RELATED LINKS</span></span>

[<span data-ttu-id="36eee-171">Get-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="36eee-171">Get-LocalGroup</span></span>](Get-LocalGroup.md)

[<span data-ttu-id="36eee-172">New-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="36eee-172">New-LocalGroup</span></span>](New-LocalGroup.md)

[<span data-ttu-id="36eee-173">Rename-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="36eee-173">Rename-LocalGroup</span></span>](Rename-LocalGroup.md)

[<span data-ttu-id="36eee-174">Set-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="36eee-174">Set-LocalGroup</span></span>](Set-LocalGroup.md)
