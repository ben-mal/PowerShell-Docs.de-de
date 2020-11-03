---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/enable-localuser?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-LocalUser
ms.openlocfilehash: 80d062578e7114b69e5cb5f3367b56da3871b9df
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211916"
---
# <span data-ttu-id="43646-103">Enable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="43646-103">Enable-LocalUser</span></span>

## <span data-ttu-id="43646-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="43646-104">SYNOPSIS</span></span>
<span data-ttu-id="43646-105">Aktiviert ein lokales Benutzerkonto.</span><span class="sxs-lookup"><span data-stu-id="43646-105">Enables a local user account.</span></span>

## <span data-ttu-id="43646-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="43646-106">SYNTAX</span></span>

### <span data-ttu-id="43646-107">InputObject</span><span class="sxs-lookup"><span data-stu-id="43646-107">InputObject</span></span>

```
Enable-LocalUser [-InputObject] <LocalUser[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="43646-108">Standard</span><span class="sxs-lookup"><span data-stu-id="43646-108">Default</span></span>

```
Enable-LocalUser [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="43646-109">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="43646-109">SecurityIdentifier</span></span>

```
Enable-LocalUser [-SID] <SecurityIdentifier[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="43646-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="43646-110">DESCRIPTION</span></span>
<span data-ttu-id="43646-111">Das **enable-LocalUser-** Cmdlet aktiviert lokale Benutzerkonten.</span><span class="sxs-lookup"><span data-stu-id="43646-111">The **Enable-LocalUser** cmdlet enables local user accounts.</span></span>
<span data-ttu-id="43646-112">Wenn ein Benutzerkonto deaktiviert ist, kann sich der Benutzer nicht anmelden.</span><span class="sxs-lookup"><span data-stu-id="43646-112">When a user account is disabled, the user cannot log on.</span></span>
<span data-ttu-id="43646-113">Wenn ein Benutzerkonto aktiviert ist, kann sich der Benutzer anmelden.</span><span class="sxs-lookup"><span data-stu-id="43646-113">When a user account is enabled, the user can log on.</span></span>

> [!NOTE]
> <span data-ttu-id="43646-114">Das Microsoft. PowerShell. LocalAccounts-Modul ist in der 32-Bit-PowerShell auf einem 64-Bit-System nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="43646-114">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="43646-115">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="43646-115">EXAMPLES</span></span>

### <span data-ttu-id="43646-116">Beispiel 1: Aktivieren eines Kontos durch Angeben eines Namens</span><span class="sxs-lookup"><span data-stu-id="43646-116">Example 1: Enable an account by specifying a name</span></span>

```
PS C:\> Enable-LocalUser -Name "Admin02"
```

<span data-ttu-id="43646-117">Mit diesem Befehl wird das Benutzerkonto mit dem Namen Admin02 aktiviert.</span><span class="sxs-lookup"><span data-stu-id="43646-117">This command enables the user account named Admin02.</span></span>

### <span data-ttu-id="43646-118">Beispiel 2: Aktivieren eines Kontos mithilfe der Pipeline</span><span class="sxs-lookup"><span data-stu-id="43646-118">Example 2: Enable an account by using the pipeline</span></span>

```
PS C:\> Get-LocalUser -Name "Administrator" | Enable-LocalUser
```

<span data-ttu-id="43646-119">Mit diesem Befehl wird das integrierte Administrator Konto mithilfe von **Get-LocalUser** abgerufen und dann mithilfe des Pipeline-Operators an das aktuelle Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="43646-119">This command gets the built-in Administrator account by using **Get-LocalUser** , and then passes it to the current cmdlet by using the pipeline operator.</span></span>
<span data-ttu-id="43646-120">Dieses Cmdlet aktiviert dieses Konto.</span><span class="sxs-lookup"><span data-stu-id="43646-120">That cmdlet enables that account.</span></span>

## <span data-ttu-id="43646-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="43646-121">PARAMETERS</span></span>

### <span data-ttu-id="43646-122">-InputObject</span><span class="sxs-lookup"><span data-stu-id="43646-122">-InputObject</span></span>
<span data-ttu-id="43646-123">Gibt ein Array von Benutzerkonten an, die von diesem Cmdlet aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="43646-123">Specifies an array of user accounts that this cmdlet enables.</span></span>
<span data-ttu-id="43646-124">Verwenden Sie das Cmdlet "Get-LocalUser", um ein Benutzerkonto zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="43646-124">To obtain a user account, use the Get-LocalUser cmdlet.</span></span>

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

### <span data-ttu-id="43646-125">-Name</span><span class="sxs-lookup"><span data-stu-id="43646-125">-Name</span></span>
<span data-ttu-id="43646-126">Gibt ein Array von Namen der Benutzerkonten an, die von diesem Cmdlet aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="43646-126">Specifies an array of names of the user accounts that this cmdlet enables.</span></span>

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

### <span data-ttu-id="43646-127">-SID</span><span class="sxs-lookup"><span data-stu-id="43646-127">-SID</span></span>
<span data-ttu-id="43646-128">Gibt ein Array von Benutzerkonten an, die von diesem Cmdlet aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="43646-128">Specifies an array of user accounts that this cmdlet enables.</span></span>

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

### <span data-ttu-id="43646-129">-Confirm</span><span class="sxs-lookup"><span data-stu-id="43646-129">-Confirm</span></span>
<span data-ttu-id="43646-130">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="43646-130">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="43646-131">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="43646-131">-WhatIf</span></span>
<span data-ttu-id="43646-132">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="43646-132">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="43646-133">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="43646-133">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="43646-134">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="43646-134">CommonParameters</span></span>
<span data-ttu-id="43646-135">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="43646-135">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="43646-136">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="43646-136">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="43646-137">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="43646-137">INPUTS</span></span>

### <span data-ttu-id="43646-138">System. Management. Automation. securityaccountmanager. LocalUser, System. String, System. Security. Principal. SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="43646-138">System.Management.Automation.SecurityAccountsManager.LocalUser, System.String, System.Security.Principal.SecurityIdentifier</span></span>
<span data-ttu-id="43646-139">Sie können einen lokalen Benutzer, eine Zeichenfolge oder eine SID an dieses Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="43646-139">You can pipe a local user, a string, or a SID to this cmdlet.</span></span>

## <span data-ttu-id="43646-140">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="43646-140">OUTPUTS</span></span>

### <span data-ttu-id="43646-141">Keine</span><span class="sxs-lookup"><span data-stu-id="43646-141">None</span></span>
<span data-ttu-id="43646-142">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="43646-142">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="43646-143">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="43646-143">NOTES</span></span>

* <span data-ttu-id="43646-144">Die **principalsource** -Eigenschaft ist eine Eigenschaft für die Objekte " **LocalUser** ", " **localgroup** " und " **localprincipal** ", die die Quelle des Objekts beschreiben.</span><span class="sxs-lookup"><span data-stu-id="43646-144">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="43646-145">Folgende Quellen sind möglich:</span><span class="sxs-lookup"><span data-stu-id="43646-145">The possible sources are as follows:</span></span>

- <span data-ttu-id="43646-146">Lokal</span><span class="sxs-lookup"><span data-stu-id="43646-146">Local</span></span>
- <span data-ttu-id="43646-147">Active Directory</span><span class="sxs-lookup"><span data-stu-id="43646-147">Active Directory</span></span>
- <span data-ttu-id="43646-148">Azure Active Directory-Gruppe</span><span class="sxs-lookup"><span data-stu-id="43646-148">Azure Active Directory group</span></span>
- <span data-ttu-id="43646-149">Microsoft-Konto</span><span class="sxs-lookup"><span data-stu-id="43646-149">Microsoft Account</span></span>

<span data-ttu-id="43646-150">**Principalsource** wird nur von Windows 10, Windows Server 2016 und neueren Versionen des Windows-Betriebssystems unterstützt.</span><span class="sxs-lookup"><span data-stu-id="43646-150">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="43646-151">Bei früheren Versionen ist die-Eigenschaft leer.</span><span class="sxs-lookup"><span data-stu-id="43646-151">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="43646-152">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="43646-152">RELATED LINKS</span></span>

[<span data-ttu-id="43646-153">Disable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="43646-153">Disable-LocalUser</span></span>](Disable-LocalUser.md)

[<span data-ttu-id="43646-154">Get-LocalUser</span><span class="sxs-lookup"><span data-stu-id="43646-154">Get-LocalUser</span></span>](Get-LocalUser.md)

[<span data-ttu-id="43646-155">New-LocalUser</span><span class="sxs-lookup"><span data-stu-id="43646-155">New-LocalUser</span></span>](New-LocalUser.md)

[<span data-ttu-id="43646-156">Remove-LocalUser</span><span class="sxs-lookup"><span data-stu-id="43646-156">Remove-LocalUser</span></span>](Remove-LocalUser.md)

[<span data-ttu-id="43646-157">Rename-LocalUser</span><span class="sxs-lookup"><span data-stu-id="43646-157">Rename-LocalUser</span></span>](Rename-LocalUser.md)

[<span data-ttu-id="43646-158">Set-LocalUser</span><span class="sxs-lookup"><span data-stu-id="43646-158">Set-LocalUser</span></span>](Set-LocalUser.md)
