---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/new-localgroup?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-LocalGroup
ms.openlocfilehash: de66ad724d3cfee2d296d3b431618768a9cd38da
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214687"
---
# <span data-ttu-id="d4ef9-103">New-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="d4ef9-103">New-LocalGroup</span></span>

## <span data-ttu-id="d4ef9-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="d4ef9-104">SYNOPSIS</span></span>
<span data-ttu-id="d4ef9-105">Erstellt eine lokale Sicherheitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="d4ef9-105">Creates a local security group.</span></span>

## <span data-ttu-id="d4ef9-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d4ef9-106">SYNTAX</span></span>

```
New-LocalGroup [-Description <String>] [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="d4ef9-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d4ef9-107">DESCRIPTION</span></span>
<span data-ttu-id="d4ef9-108">Mit dem Cmdlet " **New-localgroup** " wird eine lokale Sicherheitsgruppe im Sicherheits Konto-Manager erstellt.</span><span class="sxs-lookup"><span data-stu-id="d4ef9-108">The **New-LocalGroup** cmdlet creates a local security group in the Security Account Manager.</span></span>

> [!NOTE]
> <span data-ttu-id="d4ef9-109">Das Microsoft. PowerShell. LocalAccounts-Modul ist in der 32-Bit-PowerShell auf einem 64-Bit-System nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d4ef9-109">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="d4ef9-110">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="d4ef9-110">EXAMPLES</span></span>

### <span data-ttu-id="d4ef9-111">Beispiel 1: Erstellen einer Sicherheitsgruppe</span><span class="sxs-lookup"><span data-stu-id="d4ef9-111">Example 1: Create a security group</span></span>

```
PS C:\> New-LocalGroup -Name "SecurityGroup04"
```

<span data-ttu-id="d4ef9-112">Mit diesem Befehl wird eine Gruppe mit dem Namen SecurityGroup04 erstellt.</span><span class="sxs-lookup"><span data-stu-id="d4ef9-112">This command creates a group named SecurityGroup04.</span></span>

## <span data-ttu-id="d4ef9-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d4ef9-113">PARAMETERS</span></span>

### <span data-ttu-id="d4ef9-114">-Description</span><span class="sxs-lookup"><span data-stu-id="d4ef9-114">-Description</span></span>
<span data-ttu-id="d4ef9-115">Gibt einen Kommentar für die Gruppe an.</span><span class="sxs-lookup"><span data-stu-id="d4ef9-115">Specifies a comment for the group.</span></span>
<span data-ttu-id="d4ef9-116">Die maximale Länge beträgt 48 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="d4ef9-116">The maximum length is 48 characters.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d4ef9-117">-Name</span><span class="sxs-lookup"><span data-stu-id="d4ef9-117">-Name</span></span>
<span data-ttu-id="d4ef9-118">Gibt einen Namen für die Gruppe an.</span><span class="sxs-lookup"><span data-stu-id="d4ef9-118">Specifies a name for the group.</span></span>
<span data-ttu-id="d4ef9-119">Die maximale Länge beträgt 256 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="d4ef9-119">The maximum length is 256 characters.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="d4ef9-120">-Confirm</span><span class="sxs-lookup"><span data-stu-id="d4ef9-120">-Confirm</span></span>
<span data-ttu-id="d4ef9-121">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="d4ef9-121">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="d4ef9-122">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="d4ef9-122">-WhatIf</span></span>
<span data-ttu-id="d4ef9-123">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d4ef9-123">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="d4ef9-124">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d4ef9-124">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="d4ef9-125">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d4ef9-125">CommonParameters</span></span>
<span data-ttu-id="d4ef9-126">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d4ef9-126">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d4ef9-127">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d4ef9-127">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d4ef9-128">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="d4ef9-128">INPUTS</span></span>

### <span data-ttu-id="d4ef9-129">System.String</span><span class="sxs-lookup"><span data-stu-id="d4ef9-129">System.String</span></span>
<span data-ttu-id="d4ef9-130">Sie können eine Zeichenfolge über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="d4ef9-130">You can pipe a string to this cmdlet.</span></span>

## <span data-ttu-id="d4ef9-131">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="d4ef9-131">OUTPUTS</span></span>

### <span data-ttu-id="d4ef9-132">System. Management. Automation. securityaccounzmanager. localgroup</span><span class="sxs-lookup"><span data-stu-id="d4ef9-132">System.Management.Automation.SecurityAccountsManager.LocalGroup</span></span>
<span data-ttu-id="d4ef9-133">Mit diesem Cmdlet wird eine Sicherheitsgruppe zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d4ef9-133">This cmdlet returns a security group.</span></span>

## <span data-ttu-id="d4ef9-134">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="d4ef9-134">NOTES</span></span>

* <span data-ttu-id="d4ef9-135">Die **principalsource** -Eigenschaft ist eine Eigenschaft für die Objekte " **LocalUser** ", " **localgroup** " und " **localprincipal** ", die die Quelle des Objekts beschreiben.</span><span class="sxs-lookup"><span data-stu-id="d4ef9-135">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="d4ef9-136">Folgende Quellen sind möglich:</span><span class="sxs-lookup"><span data-stu-id="d4ef9-136">The possible sources are as follows:</span></span>

- <span data-ttu-id="d4ef9-137">Lokal</span><span class="sxs-lookup"><span data-stu-id="d4ef9-137">Local</span></span>
- <span data-ttu-id="d4ef9-138">Active Directory</span><span class="sxs-lookup"><span data-stu-id="d4ef9-138">Active Directory</span></span>
- <span data-ttu-id="d4ef9-139">Azure Active Directory-Gruppe</span><span class="sxs-lookup"><span data-stu-id="d4ef9-139">Azure Active Directory group</span></span>
- <span data-ttu-id="d4ef9-140">Microsoft-Konto</span><span class="sxs-lookup"><span data-stu-id="d4ef9-140">Microsoft Account</span></span>

<span data-ttu-id="d4ef9-141">**Principalsource** wird nur von Windows 10, Windows Server 2016 und neueren Versionen des Windows-Betriebssystems unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d4ef9-141">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="d4ef9-142">Bei früheren Versionen ist die-Eigenschaft leer.</span><span class="sxs-lookup"><span data-stu-id="d4ef9-142">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="d4ef9-143">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="d4ef9-143">RELATED LINKS</span></span>

[<span data-ttu-id="d4ef9-144">Get-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="d4ef9-144">Get-LocalGroup</span></span>](Get-LocalGroup.md)

[<span data-ttu-id="d4ef9-145">Remove-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="d4ef9-145">Remove-LocalGroup</span></span>](Remove-LocalGroup.md)

[<span data-ttu-id="d4ef9-146">Rename-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="d4ef9-146">Rename-LocalGroup</span></span>](Rename-LocalGroup.md)

[<span data-ttu-id="d4ef9-147">Set-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="d4ef9-147">Set-LocalGroup</span></span>](Set-LocalGroup.md)
