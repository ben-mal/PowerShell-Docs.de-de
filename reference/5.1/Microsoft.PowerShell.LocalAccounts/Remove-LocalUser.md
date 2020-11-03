---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/remove-localuser?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-LocalUser
ms.openlocfilehash: de1054971dab19f8cfae654208488ca9ce5e17e4
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215636"
---
# <span data-ttu-id="c00c3-103">Remove-LocalUser</span><span class="sxs-lookup"><span data-stu-id="c00c3-103">Remove-LocalUser</span></span>

## <span data-ttu-id="c00c3-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="c00c3-104">SYNOPSIS</span></span>
<span data-ttu-id="c00c3-105">Löscht lokale Benutzerkonten.</span><span class="sxs-lookup"><span data-stu-id="c00c3-105">Deletes local user accounts.</span></span>

## <span data-ttu-id="c00c3-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c00c3-106">SYNTAX</span></span>

### <span data-ttu-id="c00c3-107">InputObject</span><span class="sxs-lookup"><span data-stu-id="c00c3-107">InputObject</span></span>

```
Remove-LocalUser [-InputObject] <LocalUser[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="c00c3-108">Standard</span><span class="sxs-lookup"><span data-stu-id="c00c3-108">Default</span></span>

```
Remove-LocalUser [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="c00c3-109">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="c00c3-109">SecurityIdentifier</span></span>

```
Remove-LocalUser [-SID] <SecurityIdentifier[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="c00c3-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c00c3-110">DESCRIPTION</span></span>
<span data-ttu-id="c00c3-111">Das **Remove-LocalUser-** Cmdlet löscht lokale Benutzerkonten.</span><span class="sxs-lookup"><span data-stu-id="c00c3-111">The **Remove-LocalUser** cmdlet deletes local user accounts.</span></span>

## <span data-ttu-id="c00c3-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="c00c3-112">EXAMPLES</span></span>

### <span data-ttu-id="c00c3-113">Beispiel 1: Löschen eines Benutzerkontos</span><span class="sxs-lookup"><span data-stu-id="c00c3-113">Example 1: Delete a user account</span></span>

```
PS C:\> Remove-LocalUser -Name "AdminContoso02"
```

<span data-ttu-id="c00c3-114">Mit diesem Befehl wird das Benutzerkonto mit dem Namen AdminContoso02 gelöscht.</span><span class="sxs-lookup"><span data-stu-id="c00c3-114">This command deletes the user account named AdminContoso02.</span></span>

> [!NOTE]
> <span data-ttu-id="c00c3-115">Das Microsoft. PowerShell. LocalAccounts-Modul ist in der 32-Bit-PowerShell auf einem 64-Bit-System nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c00c3-115">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="c00c3-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c00c3-116">PARAMETERS</span></span>

### <span data-ttu-id="c00c3-117">-InputObject</span><span class="sxs-lookup"><span data-stu-id="c00c3-117">-InputObject</span></span>
<span data-ttu-id="c00c3-118">Gibt ein Array von Benutzerkonten an, die von diesem Cmdlet gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="c00c3-118">Specifies an array of user accounts that this cmdlet deletes.</span></span>
<span data-ttu-id="c00c3-119">Verwenden Sie das Cmdlet "Get-LocalUser", um ein Benutzerkonto zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="c00c3-119">To obtain a user account, use the Get-LocalUser cmdlet.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.LocalUser[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="c00c3-120">-Name</span><span class="sxs-lookup"><span data-stu-id="c00c3-120">-Name</span></span>
<span data-ttu-id="c00c3-121">Gibt ein Array von Namen der Benutzerkonten an, die von diesem Cmdlet gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="c00c3-121">Specifies an array of names of the user accounts that this cmdlet deletes.</span></span>

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

### <span data-ttu-id="c00c3-122">-SID</span><span class="sxs-lookup"><span data-stu-id="c00c3-122">-SID</span></span>
<span data-ttu-id="c00c3-123">Gibt ein Array von Sicherheits-IDs (SIDs) von Benutzerkonten an, die von diesem Cmdlet gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="c00c3-123">Specifies an array of security IDs (SIDs) of user accounts that this cmdlet deletes.</span></span>

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

### <span data-ttu-id="c00c3-124">-Confirm</span><span class="sxs-lookup"><span data-stu-id="c00c3-124">-Confirm</span></span>
<span data-ttu-id="c00c3-125">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="c00c3-125">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="c00c3-126">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="c00c3-126">-WhatIf</span></span>
<span data-ttu-id="c00c3-127">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c00c3-127">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="c00c3-128">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c00c3-128">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="c00c3-129">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c00c3-129">CommonParameters</span></span>
<span data-ttu-id="c00c3-130">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c00c3-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c00c3-131">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c00c3-131">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c00c3-132">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="c00c3-132">INPUTS</span></span>

### <span data-ttu-id="c00c3-133">System. Management. Automation. securityaccountmanager. LocalUser, System. String, System. Security. Principal. SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="c00c3-133">System.Management.Automation.SecurityAccountsManager.LocalUser, System.String, System.Security.Principal.SecurityIdentifier</span></span>
<span data-ttu-id="c00c3-134">Sie können einen lokalen Benutzer, eine Zeichenfolge oder eine SID an dieses Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="c00c3-134">You can pipe a local user, a string, or a SID to this cmdlet.</span></span>

## <span data-ttu-id="c00c3-135">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="c00c3-135">OUTPUTS</span></span>

### <span data-ttu-id="c00c3-136">Keine</span><span class="sxs-lookup"><span data-stu-id="c00c3-136">None</span></span>
<span data-ttu-id="c00c3-137">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="c00c3-137">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="c00c3-138">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="c00c3-138">NOTES</span></span>

* <span data-ttu-id="c00c3-139">Die **principalsource** -Eigenschaft ist eine Eigenschaft für die Objekte " **LocalUser** ", " **localgroup** " und " **localprincipal** ", die die Quelle des Objekts beschreiben.</span><span class="sxs-lookup"><span data-stu-id="c00c3-139">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="c00c3-140">Folgende Quellen sind möglich:</span><span class="sxs-lookup"><span data-stu-id="c00c3-140">The possible sources are as follows:</span></span>

- <span data-ttu-id="c00c3-141">Lokal</span><span class="sxs-lookup"><span data-stu-id="c00c3-141">Local</span></span>
- <span data-ttu-id="c00c3-142">Active Directory</span><span class="sxs-lookup"><span data-stu-id="c00c3-142">Active Directory</span></span>
- <span data-ttu-id="c00c3-143">Azure Active Directory-Gruppe</span><span class="sxs-lookup"><span data-stu-id="c00c3-143">Azure Active Directory group</span></span>
- <span data-ttu-id="c00c3-144">Microsoft-Konto</span><span class="sxs-lookup"><span data-stu-id="c00c3-144">Microsoft Account</span></span>

<span data-ttu-id="c00c3-145">**Principalsource** wird nur von Windows 10, Windows Server 2016 und neueren Versionen des Windows-Betriebssystems unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c00c3-145">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="c00c3-146">Bei früheren Versionen ist die-Eigenschaft leer.</span><span class="sxs-lookup"><span data-stu-id="c00c3-146">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="c00c3-147">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="c00c3-147">RELATED LINKS</span></span>

[<span data-ttu-id="c00c3-148">Disable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="c00c3-148">Disable-LocalUser</span></span>](Disable-LocalUser.md)

[<span data-ttu-id="c00c3-149">Enable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="c00c3-149">Enable-LocalUser</span></span>](Enable-LocalUser.md)

[<span data-ttu-id="c00c3-150">Get-LocalUser</span><span class="sxs-lookup"><span data-stu-id="c00c3-150">Get-LocalUser</span></span>](Get-LocalUser.md)

[<span data-ttu-id="c00c3-151">New-LocalUser</span><span class="sxs-lookup"><span data-stu-id="c00c3-151">New-LocalUser</span></span>](New-LocalUser.md)

[<span data-ttu-id="c00c3-152">Rename-LocalUser</span><span class="sxs-lookup"><span data-stu-id="c00c3-152">Rename-LocalUser</span></span>](Rename-LocalUser.md)

[<span data-ttu-id="c00c3-153">Set-LocalUser</span><span class="sxs-lookup"><span data-stu-id="c00c3-153">Set-LocalUser</span></span>](Set-LocalUser.md)
