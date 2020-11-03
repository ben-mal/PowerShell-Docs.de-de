---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/remove-localgroupmember?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-LocalGroupMember
ms.openlocfilehash: 6e6264a65c343657c2f2f87384d76cc3f1554d3d
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214679"
---
# <span data-ttu-id="bb81f-103">Remove-LocalGroupMember</span><span class="sxs-lookup"><span data-stu-id="bb81f-103">Remove-LocalGroupMember</span></span>

## <span data-ttu-id="bb81f-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="bb81f-104">SYNOPSIS</span></span>
<span data-ttu-id="bb81f-105">Entfernt Mitglieder aus einer lokalen Gruppe.</span><span class="sxs-lookup"><span data-stu-id="bb81f-105">Removes members from a local group.</span></span>

## <span data-ttu-id="bb81f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="bb81f-106">SYNTAX</span></span>

### <span data-ttu-id="bb81f-107">Group</span><span class="sxs-lookup"><span data-stu-id="bb81f-107">Group</span></span>

```
Remove-LocalGroupMember [-Group] <LocalGroup> [-Member] <LocalPrincipal[]> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="bb81f-108">Standard</span><span class="sxs-lookup"><span data-stu-id="bb81f-108">Default</span></span>

```
Remove-LocalGroupMember [-Member] <LocalPrincipal[]> [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="bb81f-109">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="bb81f-109">SecurityIdentifier</span></span>

```
Remove-LocalGroupMember [-Member] <LocalPrincipal[]> [-SID] <SecurityIdentifier> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="bb81f-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bb81f-110">DESCRIPTION</span></span>
<span data-ttu-id="bb81f-111">Das **Remove-localgroupmember** -Cmdlet entfernt Benutzer oder Gruppen aus einer lokalen Gruppe.</span><span class="sxs-lookup"><span data-stu-id="bb81f-111">The **Remove-LocalGroupMember** cmdlet removes users or groups from a local group.</span></span>

> [!NOTE]
> <span data-ttu-id="bb81f-112">Das Microsoft. PowerShell. LocalAccounts-Modul ist in der 32-Bit-PowerShell auf einem 64-Bit-System nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="bb81f-112">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="bb81f-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="bb81f-113">EXAMPLES</span></span>

### <span data-ttu-id="bb81f-114">Beispiel 1: Entfernen von Mitgliedern aus der Gruppe "Administratoren"</span><span class="sxs-lookup"><span data-stu-id="bb81f-114">Example 1: Remove members from the Administrators group</span></span>

```
PS C:\> Remove-LocalGroupMember -Group "Administrators" -Member "Admin02", "MicrosoftAccount\username@Outlook.com", "AzureAD\DavidChew@contoso.com", "CONTOSO\Domain Admins"
```

<span data-ttu-id="bb81f-115">Mit diesem Befehl werden mehrere Mitglieder aus der lokalen Administrator Gruppe entfernt.</span><span class="sxs-lookup"><span data-stu-id="bb81f-115">This command removes several members from the local Administrators group.</span></span>
<span data-ttu-id="bb81f-116">Zu den Membern, die dieses Cmdlet entfernt, gehören ein lokales Benutzerkonto, ein Microsoft-Konto, ein Azure Active Directory Konto und eine Domänen Gruppe.</span><span class="sxs-lookup"><span data-stu-id="bb81f-116">The members that this cmdlet removes include a local user account, a Microsoft account, an Azure Active Directory account, and a domain group.</span></span>
<span data-ttu-id="bb81f-117">In diesem Beispiel wird ein Platzhalter Wert für den Benutzernamen eines Kontos unter Outlook.com verwendet.</span><span class="sxs-lookup"><span data-stu-id="bb81f-117">This example uses a placeholder value for the user name of an account at Outlook.com.</span></span>

## <span data-ttu-id="bb81f-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bb81f-118">PARAMETERS</span></span>

### <span data-ttu-id="bb81f-119">-Group</span><span class="sxs-lookup"><span data-stu-id="bb81f-119">-Group</span></span>
<span data-ttu-id="bb81f-120">Gibt die Sicherheitsgruppe an, aus der das Cmdlet Mitglieder entfernt.</span><span class="sxs-lookup"><span data-stu-id="bb81f-120">Specifies the security group from which this cmdlet removes members.</span></span>

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

### <span data-ttu-id="bb81f-121">-Member</span><span class="sxs-lookup"><span data-stu-id="bb81f-121">-Member</span></span>
<span data-ttu-id="bb81f-122">Gibt ein Array von Benutzern oder Gruppen an, die von diesem Cmdlet aus einer Sicherheitsgruppe entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="bb81f-122">Specifies an array of users or groups that this cmdlet removes from a security group.</span></span>
<span data-ttu-id="bb81f-123">Sie können Benutzer oder Gruppen nach Name, Sicherheits-ID (SID) oder **localprincipal** -Objekten angeben.</span><span class="sxs-lookup"><span data-stu-id="bb81f-123">You can specify users or groups by name, security ID (SID), or **LocalPrincipal** objects.</span></span>
<span data-ttu-id="bb81f-124">Geben Sie sid-Zeichen folgen in s-R-I-s-s an.</span><span class="sxs-lookup"><span data-stu-id="bb81f-124">Specify SID strings in S-R-I-S-S .</span></span>
<span data-ttu-id="bb81f-125">.</span><span class="sxs-lookup"><span data-stu-id="bb81f-125">.</span></span> <span data-ttu-id="bb81f-126">.</span><span class="sxs-lookup"><span data-stu-id="bb81f-126">.</span></span>
<span data-ttu-id="bb81f-127">akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="bb81f-127">format.</span></span>

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

### <span data-ttu-id="bb81f-128">-Name</span><span class="sxs-lookup"><span data-stu-id="bb81f-128">-Name</span></span>
<span data-ttu-id="bb81f-129">Gibt den Namen der Sicherheitsgruppe an, von der das Cmdlet Mitglieder entfernt.</span><span class="sxs-lookup"><span data-stu-id="bb81f-129">Specifies the name of the security group from which this cmdlet removes members.</span></span>

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

### <span data-ttu-id="bb81f-130">-SID</span><span class="sxs-lookup"><span data-stu-id="bb81f-130">-SID</span></span>
<span data-ttu-id="bb81f-131">Gibt die Sicherheits-ID der Sicherheitsgruppe an, von der das Cmdlet Mitglieder entfernt.</span><span class="sxs-lookup"><span data-stu-id="bb81f-131">Specifies the security ID of the security group from which this cmdlet removes members.</span></span>

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

### <span data-ttu-id="bb81f-132">-Confirm</span><span class="sxs-lookup"><span data-stu-id="bb81f-132">-Confirm</span></span>
<span data-ttu-id="bb81f-133">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="bb81f-133">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="bb81f-134">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="bb81f-134">-WhatIf</span></span>
<span data-ttu-id="bb81f-135">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="bb81f-135">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="bb81f-136">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="bb81f-136">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="bb81f-137">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="bb81f-137">CommonParameters</span></span>
<span data-ttu-id="bb81f-138">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="bb81f-138">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="bb81f-139">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="bb81f-139">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="bb81f-140">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="bb81f-140">INPUTS</span></span>

### <span data-ttu-id="bb81f-141">System. Management. Automation. securityaccountmanager. localprincipal, System. String, System. Security. Principal. SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="bb81f-141">System.Management.Automation.SecurityAccountsManager.LocalPrincipal, System.String, System.Security.Principal.SecurityIdentifier</span></span>
<span data-ttu-id="bb81f-142">Sie können einen lokalen Prinzipal, eine Zeichenfolge oder eine SID an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="bb81f-142">You can pipe a local principal, a string, or a SID to this cmdlet.</span></span>

## <span data-ttu-id="bb81f-143">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="bb81f-143">OUTPUTS</span></span>

### <span data-ttu-id="bb81f-144">Keine</span><span class="sxs-lookup"><span data-stu-id="bb81f-144">None</span></span>
<span data-ttu-id="bb81f-145">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="bb81f-145">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="bb81f-146">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="bb81f-146">NOTES</span></span>

* <span data-ttu-id="bb81f-147">Die **principalsource** -Eigenschaft ist eine Eigenschaft für die Objekte " **LocalUser** ", " **localgroup** " und " **localprincipal** ", die die Quelle des Objekts beschreiben.</span><span class="sxs-lookup"><span data-stu-id="bb81f-147">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="bb81f-148">Folgende Quellen sind möglich:</span><span class="sxs-lookup"><span data-stu-id="bb81f-148">The possible sources are as follows:</span></span>

- <span data-ttu-id="bb81f-149">Lokal</span><span class="sxs-lookup"><span data-stu-id="bb81f-149">Local</span></span>
- <span data-ttu-id="bb81f-150">Active Directory</span><span class="sxs-lookup"><span data-stu-id="bb81f-150">Active Directory</span></span>
- <span data-ttu-id="bb81f-151">Azure Active Directory-Gruppe</span><span class="sxs-lookup"><span data-stu-id="bb81f-151">Azure Active Directory group</span></span>
- <span data-ttu-id="bb81f-152">Microsoft-Konto</span><span class="sxs-lookup"><span data-stu-id="bb81f-152">Microsoft Account</span></span>

<span data-ttu-id="bb81f-153">**Principalsource** wird nur von Windows 10, Windows Server 2016 und neueren Versionen des Windows-Betriebssystems unterstützt.</span><span class="sxs-lookup"><span data-stu-id="bb81f-153">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="bb81f-154">Bei früheren Versionen ist die-Eigenschaft leer.</span><span class="sxs-lookup"><span data-stu-id="bb81f-154">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="bb81f-155">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="bb81f-155">RELATED LINKS</span></span>

[<span data-ttu-id="bb81f-156">Add-LocalGroupMember</span><span class="sxs-lookup"><span data-stu-id="bb81f-156">Add-LocalGroupMember</span></span>](Add-LocalGroupMember.md)

[<span data-ttu-id="bb81f-157">Get-LocalGroupMember</span><span class="sxs-lookup"><span data-stu-id="bb81f-157">Get-LocalGroupMember</span></span>](Get-LocalGroupMember.md)

[<span data-ttu-id="bb81f-158">New-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="bb81f-158">New-LocalGroup</span></span>](New-LocalGroup.md)
