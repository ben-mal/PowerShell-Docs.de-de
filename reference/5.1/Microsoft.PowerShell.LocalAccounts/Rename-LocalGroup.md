---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/rename-localgroup?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Rename-LocalGroup
ms.openlocfilehash: 566d33bdeb52323cca41fa9757d36334b40f1654
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215623"
---
# <span data-ttu-id="f9410-103">Rename-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="f9410-103">Rename-LocalGroup</span></span>

## <span data-ttu-id="f9410-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="f9410-104">SYNOPSIS</span></span>
<span data-ttu-id="f9410-105">Benennt eine lokale Sicherheitsgruppe um.</span><span class="sxs-lookup"><span data-stu-id="f9410-105">Renames a local security group.</span></span>

## <span data-ttu-id="f9410-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f9410-106">SYNTAX</span></span>

### <span data-ttu-id="f9410-107">InputObject</span><span class="sxs-lookup"><span data-stu-id="f9410-107">InputObject</span></span>

```
Rename-LocalGroup [-InputObject] <LocalGroup> [-NewName] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="f9410-108">Standard</span><span class="sxs-lookup"><span data-stu-id="f9410-108">Default</span></span>

```
Rename-LocalGroup [-Name] <String> [-NewName] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="f9410-109">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="f9410-109">SecurityIdentifier</span></span>

```
Rename-LocalGroup [-NewName] <String> [-SID] <SecurityIdentifier> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="f9410-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f9410-110">DESCRIPTION</span></span>
<span data-ttu-id="f9410-111">Das Cmdlet **Rename-localgroup** benennt eine lokale Sicherheitsgruppe um.</span><span class="sxs-lookup"><span data-stu-id="f9410-111">The **Rename-LocalGroup** cmdlet renames a local security group.</span></span>

> [!NOTE]
> <span data-ttu-id="f9410-112">Das Microsoft. PowerShell. LocalAccounts-Modul ist in der 32-Bit-PowerShell auf einem 64-Bit-System nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f9410-112">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="f9410-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="f9410-113">EXAMPLES</span></span>

### <span data-ttu-id="f9410-114">Beispiel 1: Ändern des Namens einer Gruppe</span><span class="sxs-lookup"><span data-stu-id="f9410-114">Example 1: Change the name of a group</span></span>

```
PS C:\> Rename-LocalGroup -Name "SecurityGroup" -NewName "SecurityGroup04"
```

<span data-ttu-id="f9410-115">Mit diesem Befehl wird eine Sicherheitsgruppe mit dem Namen "SecurityGroup" umbenannt.</span><span class="sxs-lookup"><span data-stu-id="f9410-115">This command renames a security group named SecurityGroup.</span></span>

## <span data-ttu-id="f9410-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f9410-116">PARAMETERS</span></span>

### <span data-ttu-id="f9410-117">-InputObject</span><span class="sxs-lookup"><span data-stu-id="f9410-117">-InputObject</span></span>
<span data-ttu-id="f9410-118">Gibt die Sicherheitsgruppe an, die dieses Cmdlet umbenennt.</span><span class="sxs-lookup"><span data-stu-id="f9410-118">Specifies the security group that this cmdlet renames.</span></span>
<span data-ttu-id="f9410-119">Verwenden Sie das Cmdlet "Get-LocalGroup", um eine Sicherheitsgruppe zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="f9410-119">To obtain a security group, use the Get-LocalGroup cmdlet.</span></span>

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

### <span data-ttu-id="f9410-120">-Name</span><span class="sxs-lookup"><span data-stu-id="f9410-120">-Name</span></span>
<span data-ttu-id="f9410-121">Gibt den Namen der Sicherheitsgruppe an, die dieses Cmdlet umbenennt.</span><span class="sxs-lookup"><span data-stu-id="f9410-121">Specifies the name of the security group that this cmdlet renames.</span></span>

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

### <span data-ttu-id="f9410-122">-Newname</span><span class="sxs-lookup"><span data-stu-id="f9410-122">-NewName</span></span>
<span data-ttu-id="f9410-123">Gibt einen neuen Namen für die Sicherheitsgruppe an.</span><span class="sxs-lookup"><span data-stu-id="f9410-123">Specifies a new name for the security group.</span></span>

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

### <span data-ttu-id="f9410-124">-SID</span><span class="sxs-lookup"><span data-stu-id="f9410-124">-SID</span></span>
<span data-ttu-id="f9410-125">Gibt die Sicherheits-ID (SID) einer Sicherheitsgruppe an, die dieses Cmdlet umbenennt.</span><span class="sxs-lookup"><span data-stu-id="f9410-125">Specifies the security ID (SID) of a security group that this cmdlet renames.</span></span>

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

### <span data-ttu-id="f9410-126">-Confirm</span><span class="sxs-lookup"><span data-stu-id="f9410-126">-Confirm</span></span>
<span data-ttu-id="f9410-127">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="f9410-127">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="f9410-128">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="f9410-128">-WhatIf</span></span>
<span data-ttu-id="f9410-129">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f9410-129">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="f9410-130">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f9410-130">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="f9410-131">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f9410-131">CommonParameters</span></span>
<span data-ttu-id="f9410-132">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f9410-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f9410-133">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f9410-133">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f9410-134">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="f9410-134">INPUTS</span></span>

### <span data-ttu-id="f9410-135">System. Management. Automation. securityaccountmanager. localgroup, System. String, System. Security. Principal. SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="f9410-135">System.Management.Automation.SecurityAccountsManager.LocalGroup, System.String, System.Security.Principal.SecurityIdentifier</span></span>
<span data-ttu-id="f9410-136">Sie können eine Sicherheitsgruppe, eine Zeichenfolge oder eine SID an dieses Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="f9410-136">You can pipe a security group, a string, or a SID to this cmdlet.</span></span>

## <span data-ttu-id="f9410-137">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="f9410-137">OUTPUTS</span></span>

### <span data-ttu-id="f9410-138">Keine</span><span class="sxs-lookup"><span data-stu-id="f9410-138">None</span></span>
<span data-ttu-id="f9410-139">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="f9410-139">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="f9410-140">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="f9410-140">NOTES</span></span>

* <span data-ttu-id="f9410-141">Die **principalsource** -Eigenschaft ist eine Eigenschaft für die Objekte " **LocalUser** ", " **localgroup** " und " **localprincipal** ", die die Quelle des Objekts beschreiben.</span><span class="sxs-lookup"><span data-stu-id="f9410-141">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="f9410-142">Folgende Quellen sind möglich:</span><span class="sxs-lookup"><span data-stu-id="f9410-142">The possible sources are as follows:</span></span>

- <span data-ttu-id="f9410-143">Lokal</span><span class="sxs-lookup"><span data-stu-id="f9410-143">Local</span></span>
- <span data-ttu-id="f9410-144">Active Directory</span><span class="sxs-lookup"><span data-stu-id="f9410-144">Active Directory</span></span>
- <span data-ttu-id="f9410-145">Azure Active Directory-Gruppe</span><span class="sxs-lookup"><span data-stu-id="f9410-145">Azure Active Directory group</span></span>
- <span data-ttu-id="f9410-146">Microsoft-Konto</span><span class="sxs-lookup"><span data-stu-id="f9410-146">Microsoft Account</span></span>

<span data-ttu-id="f9410-147">**Principalsource** wird nur von Windows 10, Windows Server 2016 und neueren Versionen des Windows-Betriebssystems unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f9410-147">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="f9410-148">Bei früheren Versionen ist die-Eigenschaft leer.</span><span class="sxs-lookup"><span data-stu-id="f9410-148">For earlier  versions, the property is blank.</span></span>

## <span data-ttu-id="f9410-149">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="f9410-149">RELATED LINKS</span></span>

[<span data-ttu-id="f9410-150">Get-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="f9410-150">Get-LocalGroup</span></span>](Get-LocalGroup.md)

[<span data-ttu-id="f9410-151">New-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="f9410-151">New-LocalGroup</span></span>](New-LocalGroup.md)

[<span data-ttu-id="f9410-152">Remove-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="f9410-152">Remove-LocalGroup</span></span>](Remove-LocalGroup.md)

[<span data-ttu-id="f9410-153">Set-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="f9410-153">Set-LocalGroup</span></span>](Set-LocalGroup.md)
