---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 04/09/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/add-localgroupmember?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-LocalGroupMember
ms.openlocfilehash: 06993c8f6618472f4809e37fbf83d298d13ae515
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211927"
---
# <span data-ttu-id="65d7c-103">Add-LocalGroupMember</span><span class="sxs-lookup"><span data-stu-id="65d7c-103">Add-LocalGroupMember</span></span>

## <span data-ttu-id="65d7c-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="65d7c-104">SYNOPSIS</span></span>
<span data-ttu-id="65d7c-105">Fügt einer lokalen Gruppe Mitglieder hinzu.</span><span class="sxs-lookup"><span data-stu-id="65d7c-105">Adds members to a local group.</span></span>

## <span data-ttu-id="65d7c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="65d7c-106">SYNTAX</span></span>

### <span data-ttu-id="65d7c-107">Group</span><span class="sxs-lookup"><span data-stu-id="65d7c-107">Group</span></span>

```
Add-LocalGroupMember [-Group] <LocalGroup> [-Member] <LocalPrincipal[]> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="65d7c-108">Standard</span><span class="sxs-lookup"><span data-stu-id="65d7c-108">Default</span></span>

```
Add-LocalGroupMember [-Member] <LocalPrincipal[]> [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="65d7c-109">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="65d7c-109">SecurityIdentifier</span></span>

```
Add-LocalGroupMember [-Member] <LocalPrincipal[]> [-SID] <SecurityIdentifier> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="65d7c-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="65d7c-110">DESCRIPTION</span></span>

<span data-ttu-id="65d7c-111">Mit dem- `Add-LocalGroupMember` Cmdlet werden Benutzer oder Gruppen einer lokalen Sicherheitsgruppe hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="65d7c-111">The `Add-LocalGroupMember` cmdlet adds users or groups to a local security group.</span></span> <span data-ttu-id="65d7c-112">Alle einer Gruppe zugewiesenen Rechte und Berechtigungen werden allen Mitgliedern dieser Gruppe zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="65d7c-112">All the rights and permissions that are assigned to a group are assigned to all members of that group.</span></span>

<span data-ttu-id="65d7c-113">Mitglieder der Gruppe „Administratoren“ eines lokalen Computers haben die Berechtigung Vollzugriff auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="65d7c-113">Members of the Administrators group on a local computer have Full Control permissions on that computer.</span></span> <span data-ttu-id="65d7c-114">Einschränken der Benutzeranzahl in der Gruppe „Administratoren“.</span><span class="sxs-lookup"><span data-stu-id="65d7c-114">Limit the number of users in the Administrators group.</span></span>

<span data-ttu-id="65d7c-115">Wenn der Computer einer Domäne angehört, können Sie einer lokalen Gruppe Benutzerkonten, Computerkonten und Gruppenkonten aus dieser Domäne und aus vertrauenswürdigen Domänen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="65d7c-115">If the computer is joined to a domain, you can add user accounts, computer accounts, and group accounts from that domain and from trusted domains to a local group.</span></span>

> [!NOTE]
> <span data-ttu-id="65d7c-116">Wenn der Computer einer Domäne angehört und Sie versuchen, einen lokalen Benutzer hinzuzufügen, der denselben Namen wie ein Mitglied der Domäne hat, wird das Domänen Mitglied hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="65d7c-116">If the computer is joined to a domain and you try to add a local user that has the same name as a member of the domain it adds the domain member.</span></span>

## <span data-ttu-id="65d7c-117">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="65d7c-117">EXAMPLES</span></span>

### <span data-ttu-id="65d7c-118">Beispiel 1: Hinzufügen von Mitgliedern zur Gruppe "Administratoren"</span><span class="sxs-lookup"><span data-stu-id="65d7c-118">Example 1: Add members to the Administrators group</span></span>

<span data-ttu-id="65d7c-119">Mit diesem Befehl werden der lokalen Gruppe "Administratoren" mehrere Mitglieder hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="65d7c-119">This command adds several members to the local Administrators group.</span></span> <span data-ttu-id="65d7c-120">Zu den neuen Mitgliedern gehören ein lokales Benutzerkonto, ein Microsoft-Konto, ein Azure Active Directory Konto und eine Domänen Gruppe.</span><span class="sxs-lookup"><span data-stu-id="65d7c-120">The new members include a local user account, a Microsoft account, an Azure Active Directory account, and a domain group.</span></span> <span data-ttu-id="65d7c-121">In diesem Beispiel wird ein Platzhalter Wert für den Benutzernamen eines Kontos unter Outlook.com verwendet.</span><span class="sxs-lookup"><span data-stu-id="65d7c-121">This example uses a placeholder value for the user name of an account at Outlook.com.</span></span>

```powershell
Add-LocalGroupMember -Group "Administrators" -Member "Admin02", "MicrosoftAccount\username@Outlook.com", "AzureAD\DavidChew@contoso.com", "CONTOSO\Domain Admins"
```

## <span data-ttu-id="65d7c-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="65d7c-122">PARAMETERS</span></span>

### <span data-ttu-id="65d7c-123">-Group</span><span class="sxs-lookup"><span data-stu-id="65d7c-123">-Group</span></span>

<span data-ttu-id="65d7c-124">Gibt die Sicherheitsgruppe an, der von diesem Cmdlet Mitglieder hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="65d7c-124">Specifies the security group to which this cmdlet adds members.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.LocalGroup
Parameter Sets: Group
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="65d7c-125">-Member</span><span class="sxs-lookup"><span data-stu-id="65d7c-125">-Member</span></span>

<span data-ttu-id="65d7c-126">Gibt ein Array von Benutzern oder Gruppen an, die von diesem Cmdlet zu einer Sicherheitsgruppe hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="65d7c-126">Specifies an array of users or groups that this cmdlet adds to a security group.</span></span> <span data-ttu-id="65d7c-127">Sie können Benutzer oder Gruppen nach Name, Sicherheits-ID (SID) oder **localprincipal** -Objekten angeben.</span><span class="sxs-lookup"><span data-stu-id="65d7c-127">You can specify users or groups by name, security ID (SID), or **LocalPrincipal** objects.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.LocalPrincipal[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="65d7c-128">-Name</span><span class="sxs-lookup"><span data-stu-id="65d7c-128">-Name</span></span>

<span data-ttu-id="65d7c-129">Gibt den Namen der Sicherheitsgruppe an, der von diesem Cmdlet Mitglieder hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="65d7c-129">Specifies the name of the security group to which this cmdlet adds members.</span></span>

```yaml
Type: System.String
Parameter Sets: Default
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="65d7c-130">-SID</span><span class="sxs-lookup"><span data-stu-id="65d7c-130">-SID</span></span>

<span data-ttu-id="65d7c-131">Gibt die Sicherheits-ID der Sicherheitsgruppe an, der von diesem Cmdlet Mitglieder hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="65d7c-131">Specifies the security ID of the security group to which this cmdlet adds members.</span></span>

```yaml
Type: System.Security.Principal.SecurityIdentifier
Parameter Sets: SecurityIdentifier
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="65d7c-132">-Confirm</span><span class="sxs-lookup"><span data-stu-id="65d7c-132">-Confirm</span></span>

<span data-ttu-id="65d7c-133">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="65d7c-133">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="65d7c-134">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="65d7c-134">-WhatIf</span></span>

<span data-ttu-id="65d7c-135">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="65d7c-135">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="65d7c-136">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="65d7c-136">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="65d7c-137">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="65d7c-137">CommonParameters</span></span>

<span data-ttu-id="65d7c-138">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="65d7c-138">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="65d7c-139">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="65d7c-139">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="65d7c-140">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="65d7c-140">INPUTS</span></span>

### <span data-ttu-id="65d7c-141">System. Management. Automation. securityaccountmanager. localgroup, System. String, System. Security. Principal. SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="65d7c-141">System.Management.Automation.SecurityAccountsManager.LocalGroup, System.String, System.Security.Principal.SecurityIdentifier</span></span>

<span data-ttu-id="65d7c-142">Sie können einen lokalen Prinzipal, eine Zeichenfolge oder eine SID an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="65d7c-142">You can pipe a local principal, a string, or a SID to this cmdlet.</span></span>

## <span data-ttu-id="65d7c-143">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="65d7c-143">OUTPUTS</span></span>

### <span data-ttu-id="65d7c-144">Keine</span><span class="sxs-lookup"><span data-stu-id="65d7c-144">None</span></span>

<span data-ttu-id="65d7c-145">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="65d7c-145">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="65d7c-146">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="65d7c-146">NOTES</span></span>

<span data-ttu-id="65d7c-147">Das Microsoft. PowerShell. LocalAccounts-Modul ist in der 32-Bit-PowerShell auf einem 64-Bit-System nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="65d7c-147">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

<span data-ttu-id="65d7c-148">Die **principalsource** -Eigenschaft ist eine Eigenschaft für die Objekte " **LocalUser** ", " **localgroup** " und " **localprincipal** ", die die Quelle des Objekts beschreiben.</span><span class="sxs-lookup"><span data-stu-id="65d7c-148">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="65d7c-149">Folgende Quellen sind möglich:</span><span class="sxs-lookup"><span data-stu-id="65d7c-149">The possible sources are as follows:</span></span>

- <span data-ttu-id="65d7c-150">Lokal</span><span class="sxs-lookup"><span data-stu-id="65d7c-150">Local</span></span>
- <span data-ttu-id="65d7c-151">Active Directory</span><span class="sxs-lookup"><span data-stu-id="65d7c-151">Active Directory</span></span>
- <span data-ttu-id="65d7c-152">Azure Active Directory-Gruppe</span><span class="sxs-lookup"><span data-stu-id="65d7c-152">Azure Active Directory group</span></span>
- <span data-ttu-id="65d7c-153">Microsoft-Konto</span><span class="sxs-lookup"><span data-stu-id="65d7c-153">Microsoft Account</span></span>

<span data-ttu-id="65d7c-154">**Principalsource** wird nur von Windows 10, Windows Server 2016 und neueren Versionen des Windows-Betriebssystems unterstützt.</span><span class="sxs-lookup"><span data-stu-id="65d7c-154">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="65d7c-155">Bei früheren Versionen ist die-Eigenschaft leer.</span><span class="sxs-lookup"><span data-stu-id="65d7c-155">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="65d7c-156">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="65d7c-156">RELATED LINKS</span></span>

[<span data-ttu-id="65d7c-157">Get-LocalGroupMember</span><span class="sxs-lookup"><span data-stu-id="65d7c-157">Get-LocalGroupMember</span></span>](Get-LocalGroupMember.md)

[<span data-ttu-id="65d7c-158">New-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="65d7c-158">New-LocalGroup</span></span>](New-LocalGroup.md)

[<span data-ttu-id="65d7c-159">Remove-LocalGroupMember</span><span class="sxs-lookup"><span data-stu-id="65d7c-159">Remove-LocalGroupMember</span></span>](Remove-LocalGroupMember.md)
