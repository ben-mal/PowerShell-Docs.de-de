---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/set-localgroup?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-LocalGroup
ms.openlocfilehash: 471c3c7bc01bf26dfe9d8eec26e4414464cae02e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215628"
---
# <span data-ttu-id="740e4-103">Set-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="740e4-103">Set-LocalGroup</span></span>

## <span data-ttu-id="740e4-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="740e4-104">SYNOPSIS</span></span>
<span data-ttu-id="740e4-105">Ändert eine lokale Sicherheitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="740e4-105">Changes a local security group.</span></span>

## <span data-ttu-id="740e4-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="740e4-106">SYNTAX</span></span>

### <span data-ttu-id="740e4-107">InputObject</span><span class="sxs-lookup"><span data-stu-id="740e4-107">InputObject</span></span>

```
Set-LocalGroup -Description <String> [-InputObject] <LocalGroup> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="740e4-108">Standard</span><span class="sxs-lookup"><span data-stu-id="740e4-108">Default</span></span>

```
Set-LocalGroup -Description <String> [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="740e4-109">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="740e4-109">SecurityIdentifier</span></span>

```
Set-LocalGroup -Description <String> [-SID] <SecurityIdentifier> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="740e4-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="740e4-110">DESCRIPTION</span></span>
<span data-ttu-id="740e4-111">Das Cmdlet " **Set-localgroup** " ändert eine lokale Sicherheitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="740e4-111">The **Set-LocalGroup** cmdlet changes a local security group.</span></span>

## <span data-ttu-id="740e4-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="740e4-112">EXAMPLES</span></span>

### <span data-ttu-id="740e4-113">Beispiel 1: Ändern einer Gruppenbeschreibung</span><span class="sxs-lookup"><span data-stu-id="740e4-113">Example 1: Change a group description</span></span>

```
PS C:\> Set-LocalGroup -Name "SecurityGroup04" -Description "This is a sample description."
```

<span data-ttu-id="740e4-114">Mit diesem Befehl wird die Beschreibung einer lokalen Gruppe geändert.</span><span class="sxs-lookup"><span data-stu-id="740e4-114">This command changes the description of a local group.</span></span>

> [!NOTE]
> <span data-ttu-id="740e4-115">Das Microsoft. PowerShell. LocalAccounts-Modul ist in der 32-Bit-PowerShell auf einem 64-Bit-System nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="740e4-115">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="740e4-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="740e4-116">PARAMETERS</span></span>

### <span data-ttu-id="740e4-117">-Description</span><span class="sxs-lookup"><span data-stu-id="740e4-117">-Description</span></span>
<span data-ttu-id="740e4-118">Gibt einen Kommentar für die Gruppe an.</span><span class="sxs-lookup"><span data-stu-id="740e4-118">Specifies a comment for the group.</span></span>
<span data-ttu-id="740e4-119">Die maximale Länge beträgt 48 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="740e4-119">The maximum length is 48 characters.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="740e4-120">-InputObject</span><span class="sxs-lookup"><span data-stu-id="740e4-120">-InputObject</span></span>
<span data-ttu-id="740e4-121">Gibt die Sicherheitsgruppe an, die von diesem Cmdlet geändert wird.</span><span class="sxs-lookup"><span data-stu-id="740e4-121">Specifies the security group that this cmdlet changes.</span></span>
<span data-ttu-id="740e4-122">Verwenden Sie das Cmdlet "Get-LocalGroup", um eine Sicherheitsgruppe zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="740e4-122">To obtain a security group, use the Get-LocalGroup cmdlet.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.LocalGroup
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="740e4-123">-Name</span><span class="sxs-lookup"><span data-stu-id="740e4-123">-Name</span></span>
<span data-ttu-id="740e4-124">Gibt den Namen der Sicherheitsgruppe an, die von diesem Cmdlet geändert wird.</span><span class="sxs-lookup"><span data-stu-id="740e4-124">Specifies the name of the security group that this cmdlet changes.</span></span>

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

### <span data-ttu-id="740e4-125">-SID</span><span class="sxs-lookup"><span data-stu-id="740e4-125">-SID</span></span>
<span data-ttu-id="740e4-126">Gibt die Sicherheits-ID (SID) der Sicherheitsgruppe an, die von diesem Cmdlet geändert wird.</span><span class="sxs-lookup"><span data-stu-id="740e4-126">Specifies the security ID (SID) of the security group that this cmdlet changes.</span></span>

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

### <span data-ttu-id="740e4-127">-Confirm</span><span class="sxs-lookup"><span data-stu-id="740e4-127">-Confirm</span></span>
<span data-ttu-id="740e4-128">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="740e4-128">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="740e4-129">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="740e4-129">-WhatIf</span></span>
<span data-ttu-id="740e4-130">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="740e4-130">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="740e4-131">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="740e4-131">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="740e4-132">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="740e4-132">CommonParameters</span></span>
<span data-ttu-id="740e4-133">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="740e4-133">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="740e4-134">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="740e4-134">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="740e4-135">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="740e4-135">INPUTS</span></span>

### <span data-ttu-id="740e4-136">System. Management. Automation. securityaccountmanager. localgroup, System. String, System. Security. Principal. SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="740e4-136">System.Management.Automation.SecurityAccountsManager.LocalGroup, System.String, System.Security.Principal.SecurityIdentifier</span></span>
<span data-ttu-id="740e4-137">Sie können eine Sicherheitsgruppe, eine Zeichenfolge oder eine SID an dieses Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="740e4-137">You can pipe a security group, a string, or a SID to this cmdlet.</span></span>

## <span data-ttu-id="740e4-138">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="740e4-138">OUTPUTS</span></span>

### <span data-ttu-id="740e4-139">Keine</span><span class="sxs-lookup"><span data-stu-id="740e4-139">None</span></span>
<span data-ttu-id="740e4-140">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="740e4-140">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="740e4-141">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="740e4-141">NOTES</span></span>

* <span data-ttu-id="740e4-142">Die **principalsource** -Eigenschaft ist eine Eigenschaft für die Objekte " **LocalUser** ", " **localgroup** " und " **localprincipal** ", die die Quelle des Objekts beschreiben.</span><span class="sxs-lookup"><span data-stu-id="740e4-142">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="740e4-143">Folgende Quellen sind möglich:</span><span class="sxs-lookup"><span data-stu-id="740e4-143">The possible sources are as follows:</span></span>

- <span data-ttu-id="740e4-144">Lokal</span><span class="sxs-lookup"><span data-stu-id="740e4-144">Local</span></span>
- <span data-ttu-id="740e4-145">Active Directory</span><span class="sxs-lookup"><span data-stu-id="740e4-145">Active Directory</span></span>
- <span data-ttu-id="740e4-146">Azure Active Directory-Gruppe</span><span class="sxs-lookup"><span data-stu-id="740e4-146">Azure Active Directory group</span></span>
- <span data-ttu-id="740e4-147">Microsoft-Konto</span><span class="sxs-lookup"><span data-stu-id="740e4-147">Microsoft Account</span></span>

<span data-ttu-id="740e4-148">**Principalsource** wird nur von Windows 10, Windows Server 2016 und neueren Versionen des Windows-Betriebssystems unterstützt.</span><span class="sxs-lookup"><span data-stu-id="740e4-148">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="740e4-149">Bei früheren Versionen ist die-Eigenschaft leer.</span><span class="sxs-lookup"><span data-stu-id="740e4-149">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="740e4-150">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="740e4-150">RELATED LINKS</span></span>

[<span data-ttu-id="740e4-151">Get-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="740e4-151">Get-LocalGroup</span></span>](Get-LocalGroup.md)

[<span data-ttu-id="740e4-152">New-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="740e4-152">New-LocalGroup</span></span>](New-LocalGroup.md)

[<span data-ttu-id="740e4-153">Remove-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="740e4-153">Remove-LocalGroup</span></span>](Remove-LocalGroup.md)

[<span data-ttu-id="740e4-154">Rename-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="740e4-154">Rename-LocalGroup</span></span>](Rename-LocalGroup.md)
