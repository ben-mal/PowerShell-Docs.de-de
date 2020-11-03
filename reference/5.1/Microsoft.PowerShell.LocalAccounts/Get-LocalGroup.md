---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/get-localgroup?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-LocalGroup
ms.openlocfilehash: 2cd77c2766840527825b0ccf68abaac3c2ea6c16
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211903"
---
# <span data-ttu-id="83847-103">Get-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="83847-103">Get-LocalGroup</span></span>

## <span data-ttu-id="83847-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="83847-104">SYNOPSIS</span></span>
<span data-ttu-id="83847-105">Ruft die lokalen Sicherheitsgruppen ab.</span><span class="sxs-lookup"><span data-stu-id="83847-105">Gets the local security groups.</span></span>

## <span data-ttu-id="83847-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="83847-106">SYNTAX</span></span>

### <span data-ttu-id="83847-107">Standard (Standard)</span><span class="sxs-lookup"><span data-stu-id="83847-107">Default (Default)</span></span>

```
Get-LocalGroup [[-Name] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="83847-108">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="83847-108">SecurityIdentifier</span></span>

```
Get-LocalGroup [[-SID] <SecurityIdentifier[]>] [<CommonParameters>]
```

## <span data-ttu-id="83847-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="83847-109">DESCRIPTION</span></span>
<span data-ttu-id="83847-110">Mit dem " **Get-localgroup"-** Cmdlet werden lokale Sicherheitsgruppen im Sicherheits Konto-Manager abgerufen.</span><span class="sxs-lookup"><span data-stu-id="83847-110">The **Get-LocalGroup** cmdlet gets local security groups in Security Account Manager.</span></span>
<span data-ttu-id="83847-111">Mit diesem Cmdlet werden die von Ihnen erstellten standardmäßigen integrierten Gruppen und lokalen Sicherheitsgruppen abgerufen.</span><span class="sxs-lookup"><span data-stu-id="83847-111">This cmdlet gets default built-in groups and local security groups that you create.</span></span>

> [!NOTE]
> <span data-ttu-id="83847-112">Das Microsoft. PowerShell. LocalAccounts-Modul ist in der 32-Bit-PowerShell auf einem 64-Bit-System nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="83847-112">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="83847-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="83847-113">EXAMPLES</span></span>

### <span data-ttu-id="83847-114">Beispiel 1: erhalten der Gruppe "Administratoren"</span><span class="sxs-lookup"><span data-stu-id="83847-114">Example 1: Get the Administrators group</span></span>

```
PS C:\> Get-LocalGroup -Name "Administrators"
Name           Description
----           -----------
Administrators Administrators have complete and unrestricted access to the computer/domain
```

<span data-ttu-id="83847-115">Mit diesem Befehl wird die lokale Gruppe "Administratoren" abgerufen.</span><span class="sxs-lookup"><span data-stu-id="83847-115">This command gets the local Administrators group.</span></span>
<span data-ttu-id="83847-116">Der Befehl zeigt die Eigenschaften der Gruppe in der-Konsole an.</span><span class="sxs-lookup"><span data-stu-id="83847-116">The command displays properties of the group in the console.</span></span>

## <span data-ttu-id="83847-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="83847-117">PARAMETERS</span></span>

### <span data-ttu-id="83847-118">-Name</span><span class="sxs-lookup"><span data-stu-id="83847-118">-Name</span></span>
<span data-ttu-id="83847-119">Gibt ein Array von Namen von Sicherheitsgruppen an, die von diesem Cmdlet abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="83847-119">Specifies an array of names of security groups that this cmdlet gets.</span></span>
<span data-ttu-id="83847-120">Sie können das Platzhalter Zeichen verwenden.</span><span class="sxs-lookup"><span data-stu-id="83847-120">You can use the wildcard character.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="83847-121">-SID</span><span class="sxs-lookup"><span data-stu-id="83847-121">-SID</span></span>
<span data-ttu-id="83847-122">Gibt ein Array von Sicherheits-IDs (SIDs) von Sicherheitsgruppen an, die von diesem Cmdlet abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="83847-122">Specifies an array of security IDs (SIDs) of security groups that this cmdlet gets.</span></span>

```yaml
Type: System.Security.Principal.SecurityIdentifier[]
Parameter Sets: SecurityIdentifier
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="83847-123">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="83847-123">CommonParameters</span></span>
<span data-ttu-id="83847-124">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="83847-124">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="83847-125">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="83847-125">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="83847-126">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="83847-126">INPUTS</span></span>

### <span data-ttu-id="83847-127">System. String, System. Security. Principal. SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="83847-127">System.String, System.Security.Principal.SecurityIdentifier</span></span>
<span data-ttu-id="83847-128">Sie können eine Zeichenfolge oder eine SID an dieses Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="83847-128">You can pipe a string or a SID to this cmdlet.</span></span>

## <span data-ttu-id="83847-129">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="83847-129">OUTPUTS</span></span>

### <span data-ttu-id="83847-130">System. Management. Automation. securityaccounzmanager. localgroup</span><span class="sxs-lookup"><span data-stu-id="83847-130">System.Management.Automation.SecurityAccountsManager.LocalGroup</span></span>
<span data-ttu-id="83847-131">Mit diesem Cmdlet wird eine lokale Gruppe zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="83847-131">This cmdlet returns a local group.</span></span>

## <span data-ttu-id="83847-132">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="83847-132">NOTES</span></span>

* <span data-ttu-id="83847-133">Die **principalsource** -Eigenschaft ist eine Eigenschaft für die Objekte " **LocalUser** ", " **localgroup** " und " **localprincipal** ", die die Quelle des Objekts beschreiben.</span><span class="sxs-lookup"><span data-stu-id="83847-133">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="83847-134">Folgende Quellen sind möglich:</span><span class="sxs-lookup"><span data-stu-id="83847-134">The possible sources are as follows:</span></span>

- <span data-ttu-id="83847-135">Lokal</span><span class="sxs-lookup"><span data-stu-id="83847-135">Local</span></span>
- <span data-ttu-id="83847-136">Active Directory</span><span class="sxs-lookup"><span data-stu-id="83847-136">Active Directory</span></span>
- <span data-ttu-id="83847-137">Azure Active Directory-Gruppe</span><span class="sxs-lookup"><span data-stu-id="83847-137">Azure Active Directory group</span></span>
- <span data-ttu-id="83847-138">Microsoft-Konto</span><span class="sxs-lookup"><span data-stu-id="83847-138">Microsoft Account</span></span>

<span data-ttu-id="83847-139">**Principalsource** wird nur von Windows 10, Windows Server 2016 und neueren Versionen des Windows-Betriebssystems unterstützt.</span><span class="sxs-lookup"><span data-stu-id="83847-139">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="83847-140">Bei früheren Versionen ist die-Eigenschaft leer.</span><span class="sxs-lookup"><span data-stu-id="83847-140">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="83847-141">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="83847-141">RELATED LINKS</span></span>

[<span data-ttu-id="83847-142">New-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="83847-142">New-LocalGroup</span></span>](New-LocalGroup.md)

[<span data-ttu-id="83847-143">Remove-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="83847-143">Remove-LocalGroup</span></span>](Remove-LocalGroup.md)

[<span data-ttu-id="83847-144">Rename-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="83847-144">Rename-LocalGroup</span></span>](Rename-LocalGroup.md)

[<span data-ttu-id="83847-145">Set-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="83847-145">Set-LocalGroup</span></span>](Set-LocalGroup.md)
