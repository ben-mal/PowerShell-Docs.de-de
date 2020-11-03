---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/disable-localuser?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-LocalUser
ms.openlocfilehash: a62242251da00688d3299c60e4cdae7aae6f581a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211924"
---
# <span data-ttu-id="3c02d-103">Disable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="3c02d-103">Disable-LocalUser</span></span>

## <span data-ttu-id="3c02d-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="3c02d-104">SYNOPSIS</span></span>
<span data-ttu-id="3c02d-105">Deaktiviert ein lokales Benutzerkonto.</span><span class="sxs-lookup"><span data-stu-id="3c02d-105">Disables a local user account.</span></span>

## <span data-ttu-id="3c02d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3c02d-106">SYNTAX</span></span>

### <span data-ttu-id="3c02d-107">InputObject</span><span class="sxs-lookup"><span data-stu-id="3c02d-107">InputObject</span></span>

```
Disable-LocalUser [-InputObject] <LocalUser[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="3c02d-108">Standard</span><span class="sxs-lookup"><span data-stu-id="3c02d-108">Default</span></span>

```
Disable-LocalUser [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="3c02d-109">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="3c02d-109">SecurityIdentifier</span></span>

```
Disable-LocalUser [-SID] <SecurityIdentifier[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="3c02d-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3c02d-110">DESCRIPTION</span></span>
<span data-ttu-id="3c02d-111">Das **Deaktivierte** Cmdlet "-LocalUser" deaktiviert lokale Benutzerkonten.</span><span class="sxs-lookup"><span data-stu-id="3c02d-111">The **Disable-LocalUser** cmdlet disables local user accounts.</span></span>
<span data-ttu-id="3c02d-112">Wenn ein Benutzerkonto deaktiviert ist, kann sich der Benutzer nicht anmelden.</span><span class="sxs-lookup"><span data-stu-id="3c02d-112">When a user account is disabled, the user cannot log on.</span></span>
<span data-ttu-id="3c02d-113">Wenn ein Benutzerkonto aktiviert ist, kann sich der Benutzer anmelden.</span><span class="sxs-lookup"><span data-stu-id="3c02d-113">When a user account is enabled, the user can log on.</span></span>

> [!NOTE]
> <span data-ttu-id="3c02d-114">Das Microsoft. PowerShell. LocalAccounts-Modul ist in der 32-Bit-PowerShell auf einem 64-Bit-System nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="3c02d-114">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="3c02d-115">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="3c02d-115">EXAMPLES</span></span>

### <span data-ttu-id="3c02d-116">Beispiel 1: Deaktivieren eines Kontos durch Angeben eines Namens</span><span class="sxs-lookup"><span data-stu-id="3c02d-116">Example 1: Disable an account by specifying a name</span></span>

```
PS C:\> Disable-LocalUser -Name "Admin02"
```

<span data-ttu-id="3c02d-117">Mit diesem Befehl wird das Benutzerkonto mit dem Namen Admin02 deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="3c02d-117">This command disables the user account named Admin02.</span></span>

### <span data-ttu-id="3c02d-118">Beispiel 2: Deaktivieren eines Kontos mithilfe der Pipeline</span><span class="sxs-lookup"><span data-stu-id="3c02d-118">Example 2: Disable an account by using the pipeline</span></span>

```
PS C:\> Get-LocalUser Guest | Disable-LocalUser
```

<span data-ttu-id="3c02d-119">Mit diesem Befehl wird das integrierte Gastkonto mithilfe von **Get-LocalUser** abgerufen und dann mithilfe des Pipeline-Operators an das aktuelle Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="3c02d-119">This command gets the built-in Guest account by using **Get-LocalUser** , and then passes it to the current cmdlet by using the pipeline operator.</span></span>
<span data-ttu-id="3c02d-120">Dieses Cmdlet deaktiviert dieses Konto.</span><span class="sxs-lookup"><span data-stu-id="3c02d-120">That cmdlet disables that account.</span></span>

## <span data-ttu-id="3c02d-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3c02d-121">PARAMETERS</span></span>

### <span data-ttu-id="3c02d-122">-InputObject</span><span class="sxs-lookup"><span data-stu-id="3c02d-122">-InputObject</span></span>
<span data-ttu-id="3c02d-123">Gibt ein Array von Benutzerkonten an, die von diesem Cmdlet deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="3c02d-123">Specifies an array of user accounts that this cmdlet disables.</span></span>
<span data-ttu-id="3c02d-124">Verwenden Sie das Cmdlet "Get-LocalUser", um ein Benutzerkonto zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="3c02d-124">To obtain a user account, use the Get-LocalUser cmdlet.</span></span>

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

### <span data-ttu-id="3c02d-125">-Name</span><span class="sxs-lookup"><span data-stu-id="3c02d-125">-Name</span></span>
<span data-ttu-id="3c02d-126">Gibt ein Array von Namen der Benutzerkonten an, die von diesem Cmdlet deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="3c02d-126">Specifies an array of names of the user accounts that this cmdlet disables.</span></span>

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

### <span data-ttu-id="3c02d-127">-SID</span><span class="sxs-lookup"><span data-stu-id="3c02d-127">-SID</span></span>
<span data-ttu-id="3c02d-128">Gibt ein Array von Benutzerkonten an, die von diesem Cmdlet deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="3c02d-128">Specifies an array of user accounts that this cmdlet disables.</span></span>

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

### <span data-ttu-id="3c02d-129">-Confirm</span><span class="sxs-lookup"><span data-stu-id="3c02d-129">-Confirm</span></span>
<span data-ttu-id="3c02d-130">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="3c02d-130">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="3c02d-131">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="3c02d-131">-WhatIf</span></span>
<span data-ttu-id="3c02d-132">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3c02d-132">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="3c02d-133">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="3c02d-133">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="3c02d-134">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="3c02d-134">CommonParameters</span></span>
<span data-ttu-id="3c02d-135">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3c02d-135">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3c02d-136">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="3c02d-136">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3c02d-137">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="3c02d-137">INPUTS</span></span>

### <span data-ttu-id="3c02d-138">System. Management. Automation. securityaccountmanager. LocalUser, System. String, System. Security. Principal. SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="3c02d-138">System.Management.Automation.SecurityAccountsManager.LocalUser, System.String, System.Security.Principal.SecurityIdentifier</span></span>
<span data-ttu-id="3c02d-139">Sie können einen lokalen Benutzer, eine Zeichenfolge oder eine SID an dieses Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="3c02d-139">You can pipe a local user, a string, or a SID to this cmdlet.</span></span>

## <span data-ttu-id="3c02d-140">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="3c02d-140">OUTPUTS</span></span>

### <span data-ttu-id="3c02d-141">Keine</span><span class="sxs-lookup"><span data-stu-id="3c02d-141">None</span></span>
<span data-ttu-id="3c02d-142">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="3c02d-142">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="3c02d-143">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="3c02d-143">NOTES</span></span>

* <span data-ttu-id="3c02d-144">Die **principalsource** -Eigenschaft ist eine Eigenschaft für die Objekte " **LocalUser** ", " **localgroup** " und " **localprincipal** ", die die Quelle des Objekts beschreiben.</span><span class="sxs-lookup"><span data-stu-id="3c02d-144">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="3c02d-145">Folgende Quellen sind möglich:</span><span class="sxs-lookup"><span data-stu-id="3c02d-145">The possible sources are as follows:</span></span>

- <span data-ttu-id="3c02d-146">Lokal</span><span class="sxs-lookup"><span data-stu-id="3c02d-146">Local</span></span>
- <span data-ttu-id="3c02d-147">Active Directory</span><span class="sxs-lookup"><span data-stu-id="3c02d-147">Active Directory</span></span>
- <span data-ttu-id="3c02d-148">Azure Active Directory-Gruppe</span><span class="sxs-lookup"><span data-stu-id="3c02d-148">Azure Active Directory group</span></span>
- <span data-ttu-id="3c02d-149">Microsoft-Konto</span><span class="sxs-lookup"><span data-stu-id="3c02d-149">Microsoft Account</span></span>

<span data-ttu-id="3c02d-150">**Principalsource** wird nur von Windows 10, Windows Server 2016 und neueren Versionen des Windows-Betriebssystems unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3c02d-150">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="3c02d-151">Bei früheren Versionen ist die-Eigenschaft leer.</span><span class="sxs-lookup"><span data-stu-id="3c02d-151">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="3c02d-152">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="3c02d-152">RELATED LINKS</span></span>

[<span data-ttu-id="3c02d-153">Enable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="3c02d-153">Enable-LocalUser</span></span>](Enable-LocalUser.md)

[<span data-ttu-id="3c02d-154">Get-LocalUser</span><span class="sxs-lookup"><span data-stu-id="3c02d-154">Get-LocalUser</span></span>](Get-LocalUser.md)

[<span data-ttu-id="3c02d-155">New-LocalUser</span><span class="sxs-lookup"><span data-stu-id="3c02d-155">New-LocalUser</span></span>](New-LocalUser.md)

[<span data-ttu-id="3c02d-156">Remove-LocalUser</span><span class="sxs-lookup"><span data-stu-id="3c02d-156">Remove-LocalUser</span></span>](Remove-LocalUser.md)

[<span data-ttu-id="3c02d-157">Rename-LocalUser</span><span class="sxs-lookup"><span data-stu-id="3c02d-157">Rename-LocalUser</span></span>](Rename-LocalUser.md)

[<span data-ttu-id="3c02d-158">Set-LocalUser</span><span class="sxs-lookup"><span data-stu-id="3c02d-158">Set-LocalUser</span></span>](Set-LocalUser.md)
