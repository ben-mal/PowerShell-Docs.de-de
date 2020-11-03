---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/rename-localuser?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Rename-LocalUser
ms.openlocfilehash: fc5740e52e08ad2146981799a4e1659cd420b321
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215631"
---
# <span data-ttu-id="65001-103">Rename-LocalUser</span><span class="sxs-lookup"><span data-stu-id="65001-103">Rename-LocalUser</span></span>

## <span data-ttu-id="65001-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="65001-104">SYNOPSIS</span></span>
<span data-ttu-id="65001-105">Benennt ein lokales Benutzerkonto um.</span><span class="sxs-lookup"><span data-stu-id="65001-105">Renames a local user account.</span></span>

## <span data-ttu-id="65001-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="65001-106">SYNTAX</span></span>

### <span data-ttu-id="65001-107">InputObject</span><span class="sxs-lookup"><span data-stu-id="65001-107">InputObject</span></span>

```
Rename-LocalUser [-InputObject] <LocalUser> [-NewName] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="65001-108">Standard</span><span class="sxs-lookup"><span data-stu-id="65001-108">Default</span></span>

```
Rename-LocalUser [-Name] <String> [-NewName] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="65001-109">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="65001-109">SecurityIdentifier</span></span>

```
Rename-LocalUser [-NewName] <String> [-SID] <SecurityIdentifier> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="65001-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="65001-110">DESCRIPTION</span></span>
<span data-ttu-id="65001-111">Das Cmdlet **Rename-LocalUser** benennt ein lokales Benutzerkonto um.</span><span class="sxs-lookup"><span data-stu-id="65001-111">The **Rename-LocalUser** cmdlet renames a local user account.</span></span>

> [!NOTE]
> <span data-ttu-id="65001-112">Das Microsoft. PowerShell. LocalAccounts-Modul ist in der 32-Bit-PowerShell auf einem 64-Bit-System nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="65001-112">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="65001-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="65001-113">EXAMPLES</span></span>

### <span data-ttu-id="65001-114">Beispiel 1: Umbenennen eines Benutzerkontos</span><span class="sxs-lookup"><span data-stu-id="65001-114">Example 1: Rename a user account</span></span>

```
PS C:\> Rename-LocalUser -Name "Admin02" -NewName "AdminContoso02"
```

<span data-ttu-id="65001-115">Mit diesem Befehl wird das Benutzerkonto mit dem Namen "Admin02" umbenannt.</span><span class="sxs-lookup"><span data-stu-id="65001-115">This command renames the user account named Admin02.</span></span>

## <span data-ttu-id="65001-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="65001-116">PARAMETERS</span></span>

### <span data-ttu-id="65001-117">-InputObject</span><span class="sxs-lookup"><span data-stu-id="65001-117">-InputObject</span></span>
<span data-ttu-id="65001-118">Gibt das Benutzerkonto an, das von diesem Cmdlet umbenannt wird.</span><span class="sxs-lookup"><span data-stu-id="65001-118">Specifies the user account that this cmdlet renames.</span></span>
<span data-ttu-id="65001-119">Verwenden Sie das Cmdlet "Get-LocalUser", um ein Benutzerkonto zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="65001-119">To obtain a user account, use the Get-LocalUser cmdlet.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.LocalUser
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="65001-120">-Name</span><span class="sxs-lookup"><span data-stu-id="65001-120">-Name</span></span>
<span data-ttu-id="65001-121">Gibt den Namen des Benutzerkontos an, das von diesem Cmdlet umbenannt wird.</span><span class="sxs-lookup"><span data-stu-id="65001-121">Specifies the name of the user account that this cmdlet renames.</span></span>

```yaml
Type: System.String
Parameter Sets: Default
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="65001-122">-Newname</span><span class="sxs-lookup"><span data-stu-id="65001-122">-NewName</span></span>
<span data-ttu-id="65001-123">Gibt einen neuen Namen für das Benutzerkonto an.</span><span class="sxs-lookup"><span data-stu-id="65001-123">Specifies a new name for the user account.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="65001-124">-SID</span><span class="sxs-lookup"><span data-stu-id="65001-124">-SID</span></span>
<span data-ttu-id="65001-125">Gibt die Sicherheits-ID (SID) von Benutzerkonten an, die von diesem Cmdlet umbenannt werden.</span><span class="sxs-lookup"><span data-stu-id="65001-125">Specifies the security ID (SID) of a user accounts that this cmdlet renames.</span></span>

```yaml
Type: System.Security.Principal.SecurityIdentifier
Parameter Sets: SecurityIdentifier
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="65001-126">-Confirm</span><span class="sxs-lookup"><span data-stu-id="65001-126">-Confirm</span></span>
<span data-ttu-id="65001-127">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="65001-127">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="65001-128">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="65001-128">-WhatIf</span></span>
<span data-ttu-id="65001-129">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="65001-129">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="65001-130">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="65001-130">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="65001-131">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="65001-131">CommonParameters</span></span>
<span data-ttu-id="65001-132">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="65001-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="65001-133">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="65001-133">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="65001-134">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="65001-134">INPUTS</span></span>

### <span data-ttu-id="65001-135">System. Management. Automation. securityaccountmanager. LocalUser, System. String, System. Security. Principal. SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="65001-135">System.Management.Automation.SecurityAccountsManager.LocalUser, System.String, System.Security.Principal.SecurityIdentifier</span></span>
<span data-ttu-id="65001-136">Sie können einen lokalen Benutzer, eine Zeichenfolge oder eine SID an dieses Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="65001-136">You can pipe a local user, a string, or a SID to this cmdlet.</span></span>

## <span data-ttu-id="65001-137">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="65001-137">OUTPUTS</span></span>

### <span data-ttu-id="65001-138">Keine</span><span class="sxs-lookup"><span data-stu-id="65001-138">None</span></span>
<span data-ttu-id="65001-139">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="65001-139">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="65001-140">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="65001-140">NOTES</span></span>

* <span data-ttu-id="65001-141">Die **principalsource** -Eigenschaft ist eine Eigenschaft für die Objekte " **LocalUser** ", " **localgroup** " und " **localprincipal** ", die die Quelle des Objekts beschreiben.</span><span class="sxs-lookup"><span data-stu-id="65001-141">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="65001-142">Folgende Quellen sind möglich:</span><span class="sxs-lookup"><span data-stu-id="65001-142">The possible sources are as follows:</span></span>

- <span data-ttu-id="65001-143">Lokal</span><span class="sxs-lookup"><span data-stu-id="65001-143">Local</span></span>
- <span data-ttu-id="65001-144">Active Directory</span><span class="sxs-lookup"><span data-stu-id="65001-144">Active Directory</span></span>
- <span data-ttu-id="65001-145">Azure Active Directory-Gruppe</span><span class="sxs-lookup"><span data-stu-id="65001-145">Azure Active Directory group</span></span>
- <span data-ttu-id="65001-146">Microsoft-Konto</span><span class="sxs-lookup"><span data-stu-id="65001-146">Microsoft Account</span></span>

<span data-ttu-id="65001-147">**Principalsource** wird nur von Windows 10, Windows Server 2016 und neueren Versionen des Windows-Betriebssystems unterstützt.</span><span class="sxs-lookup"><span data-stu-id="65001-147">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="65001-148">Bei früheren Versionen ist die-Eigenschaft leer.</span><span class="sxs-lookup"><span data-stu-id="65001-148">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="65001-149">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="65001-149">RELATED LINKS</span></span>

[<span data-ttu-id="65001-150">Disable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="65001-150">Disable-LocalUser</span></span>](Disable-LocalUser.md)

[<span data-ttu-id="65001-151">Enable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="65001-151">Enable-LocalUser</span></span>](Enable-LocalUser.md)

[<span data-ttu-id="65001-152">Get-LocalUser</span><span class="sxs-lookup"><span data-stu-id="65001-152">Get-LocalUser</span></span>](Get-LocalUser.md)

[<span data-ttu-id="65001-153">New-LocalUser</span><span class="sxs-lookup"><span data-stu-id="65001-153">New-LocalUser</span></span>](New-LocalUser.md)

[<span data-ttu-id="65001-154">Remove-LocalUser</span><span class="sxs-lookup"><span data-stu-id="65001-154">Remove-LocalUser</span></span>](Remove-LocalUser.md)

[<span data-ttu-id="65001-155">Set-LocalUser</span><span class="sxs-lookup"><span data-stu-id="65001-155">Set-LocalUser</span></span>](Set-LocalUser.md)
