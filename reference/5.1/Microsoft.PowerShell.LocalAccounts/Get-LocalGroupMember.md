---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/get-localgroupmember?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-LocalGroupMember
ms.openlocfilehash: 200368c5d13bd027302ad824533e6c187906ed0f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211892"
---
# <span data-ttu-id="27a38-103">Get-LocalGroupMember</span><span class="sxs-lookup"><span data-stu-id="27a38-103">Get-LocalGroupMember</span></span>

## <span data-ttu-id="27a38-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="27a38-104">SYNOPSIS</span></span>
<span data-ttu-id="27a38-105">Ruft Mitglieder aus einer lokalen Gruppe ab.</span><span class="sxs-lookup"><span data-stu-id="27a38-105">Gets members from a local group.</span></span>

## <span data-ttu-id="27a38-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="27a38-106">SYNTAX</span></span>

### <span data-ttu-id="27a38-107">Standard (Standard)</span><span class="sxs-lookup"><span data-stu-id="27a38-107">Default (Default)</span></span>

```
Get-LocalGroupMember [[-Member] <String>] [-Name] <String> [<CommonParameters>]
```

### <span data-ttu-id="27a38-108">Group</span><span class="sxs-lookup"><span data-stu-id="27a38-108">Group</span></span>

```
Get-LocalGroupMember [-Group] <LocalGroup> [[-Member] <String>] [<CommonParameters>]
```

### <span data-ttu-id="27a38-109">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="27a38-109">SecurityIdentifier</span></span>

```
Get-LocalGroupMember [[-Member] <String>] [-SID] <SecurityIdentifier> [<CommonParameters>]
```

## <span data-ttu-id="27a38-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="27a38-110">DESCRIPTION</span></span>
<span data-ttu-id="27a38-111">Das **Get-localgroupmember** -Cmdlet ruft Mitglieder aus einer lokalen Gruppe ab.</span><span class="sxs-lookup"><span data-stu-id="27a38-111">The **Get-LocalGroupMember** cmdlet gets members from a local group.</span></span>

> [!NOTE]
> <span data-ttu-id="27a38-112">Das Microsoft. PowerShell. LocalAccounts-Modul ist in der 32-Bit-PowerShell auf einem 64-Bit-System nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="27a38-112">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="27a38-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="27a38-113">EXAMPLES</span></span>

### <span data-ttu-id="27a38-114">Beispiel 1: alle Mitglieder der Gruppe "Administratoren" erhalten</span><span class="sxs-lookup"><span data-stu-id="27a38-114">Example 1: Get all members of the Administrators group</span></span>

```
PS C:\> Get-LocalGroupMember -Group "Administrators"
ObjectClass Name                    PrincipalSource
----------- ----                    ---------------
User        CONTOSOPC\Administrator Local
User        CONTOSOPC\LocalAdmin    Local
```

<span data-ttu-id="27a38-115">Mit diesem Befehl werden alle Mitglieder der lokalen Gruppe "Administratoren" abgerufen.</span><span class="sxs-lookup"><span data-stu-id="27a38-115">This command gets all the members of the local Administrators group.</span></span>

## <span data-ttu-id="27a38-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="27a38-116">PARAMETERS</span></span>

### <span data-ttu-id="27a38-117">-Group</span><span class="sxs-lookup"><span data-stu-id="27a38-117">-Group</span></span>
<span data-ttu-id="27a38-118">Gibt die Sicherheitsgruppe an, von der dieses Cmdlet Mitglieder abruft.</span><span class="sxs-lookup"><span data-stu-id="27a38-118">Specifies the security group from which this cmdlet gets members.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.LocalGroup
Parameter Sets: Group
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="27a38-119">-Member</span><span class="sxs-lookup"><span data-stu-id="27a38-119">-Member</span></span>
<span data-ttu-id="27a38-120">Gibt einen Benutzer oder eine Gruppe an, der von diesem Cmdlet aus einer Sicherheitsgruppe abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="27a38-120">Specifies a user or group that this cmdlet gets from a security group.</span></span>
<span data-ttu-id="27a38-121">Sie können Benutzer oder Gruppen anhand des Namens oder der Sicherheits-ID (SID) angeben.</span><span class="sxs-lookup"><span data-stu-id="27a38-121">You can specify users or groups by name or security ID (SID).</span></span>
<span data-ttu-id="27a38-122">Geben Sie sid-Zeichen folgen in s-R-I-s-s an.</span><span class="sxs-lookup"><span data-stu-id="27a38-122">Specify SID strings in S-R-I-S-S .</span></span>
<span data-ttu-id="27a38-123">.</span><span class="sxs-lookup"><span data-stu-id="27a38-123">.</span></span> <span data-ttu-id="27a38-124">.</span><span class="sxs-lookup"><span data-stu-id="27a38-124">.</span></span>
<span data-ttu-id="27a38-125">akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="27a38-125">format.</span></span>
<span data-ttu-id="27a38-126">Sie können Platzhalter Zeichen verwenden.</span><span class="sxs-lookup"><span data-stu-id="27a38-126">You can use wildcard characters.</span></span>
<span data-ttu-id="27a38-127">Wenn Sie diesen Parameter nicht angeben, ruft das Cmdlet alle Mitglieder der Gruppe ab.</span><span class="sxs-lookup"><span data-stu-id="27a38-127">If you do not specify this parameter, the cmdlet gets all members of the group.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="27a38-128">-Name</span><span class="sxs-lookup"><span data-stu-id="27a38-128">-Name</span></span>
<span data-ttu-id="27a38-129">Gibt den Namen der Sicherheitsgruppe an, von der dieses Cmdlet Mitglieder abruft.</span><span class="sxs-lookup"><span data-stu-id="27a38-129">Specifies the name of the security group from which this cmdlet gets members.</span></span>

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

### <span data-ttu-id="27a38-130">-SID</span><span class="sxs-lookup"><span data-stu-id="27a38-130">-SID</span></span>
<span data-ttu-id="27a38-131">Gibt die Sicherheits-ID der Sicherheitsgruppe an, von der das Cmdlet Mitglieder abruft.</span><span class="sxs-lookup"><span data-stu-id="27a38-131">Specifies the security ID of the security group from which this cmdlet gets members.</span></span>

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

### <span data-ttu-id="27a38-132">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="27a38-132">CommonParameters</span></span>
<span data-ttu-id="27a38-133">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="27a38-133">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="27a38-134">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="27a38-134">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="27a38-135">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="27a38-135">INPUTS</span></span>

### <span data-ttu-id="27a38-136">System. Management. Automation. securityaccountmanager. localgroup, System. String, System. Security. Principal. SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="27a38-136">System.Management.Automation.SecurityAccountsManager.LocalGroup, System.String, System.Security.Principal.SecurityIdentifier</span></span>
<span data-ttu-id="27a38-137">Sie können eine lokale Gruppe, eine Zeichenfolge oder eine SID über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="27a38-137">You can pipe a local group, a string, or a SID to this cmdlet.</span></span>

## <span data-ttu-id="27a38-138">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="27a38-138">OUTPUTS</span></span>

### <span data-ttu-id="27a38-139">Microsoft. securityaccounpmanager. localprincipal</span><span class="sxs-lookup"><span data-stu-id="27a38-139">Microsoft.SecurityAccountsManager.LocalPrincipal</span></span>
<span data-ttu-id="27a38-140">Mit diesem Cmdlet werden lokale Prinzipale zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="27a38-140">This cmdlet returns local principals.</span></span>

## <span data-ttu-id="27a38-141">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="27a38-141">NOTES</span></span>

* <span data-ttu-id="27a38-142">Die **principalsource** -Eigenschaft ist eine Eigenschaft für die Objekte " **LocalUser** ", " **localgroup** " und " **localprincipal** ", die die Quelle des Objekts beschreiben.</span><span class="sxs-lookup"><span data-stu-id="27a38-142">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="27a38-143">Folgende Quellen sind möglich:</span><span class="sxs-lookup"><span data-stu-id="27a38-143">The possible sources are as follows:</span></span>

- <span data-ttu-id="27a38-144">Lokal</span><span class="sxs-lookup"><span data-stu-id="27a38-144">Local</span></span>
- <span data-ttu-id="27a38-145">Active Directory</span><span class="sxs-lookup"><span data-stu-id="27a38-145">Active Directory</span></span>
- <span data-ttu-id="27a38-146">Azure Active Directory-Gruppe</span><span class="sxs-lookup"><span data-stu-id="27a38-146">Azure Active Directory group</span></span>
- <span data-ttu-id="27a38-147">Microsoft-Konto</span><span class="sxs-lookup"><span data-stu-id="27a38-147">Microsoft Account</span></span>

<span data-ttu-id="27a38-148">**Principalsource** wird nur von Windows 10, Windows Server 2016 und neueren Versionen des Windows-Betriebssystems unterstützt.</span><span class="sxs-lookup"><span data-stu-id="27a38-148">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="27a38-149">Bei früheren Versionen ist die-Eigenschaft leer.</span><span class="sxs-lookup"><span data-stu-id="27a38-149">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="27a38-150">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="27a38-150">RELATED LINKS</span></span>

[<span data-ttu-id="27a38-151">Add-LocalGroupMember</span><span class="sxs-lookup"><span data-stu-id="27a38-151">Add-LocalGroupMember</span></span>](Add-LocalGroupMember.md)

[<span data-ttu-id="27a38-152">New-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="27a38-152">New-LocalGroup</span></span>](New-LocalGroup.md)

[<span data-ttu-id="27a38-153">Remove-LocalGroupMember</span><span class="sxs-lookup"><span data-stu-id="27a38-153">Remove-LocalGroupMember</span></span>](Remove-LocalGroupMember.md)
