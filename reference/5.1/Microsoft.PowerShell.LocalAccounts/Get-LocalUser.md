---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 02/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/get-localuser?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-LocalUser
ms.openlocfilehash: 2b1831a854c4c61d4c4631ae475a59d8240a926b
ms.sourcegitcommit: 4d6ed6f7d747a9bbb3fcfcf6c981c5aa8a973a08
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/31/2021
ms.locfileid: "106072275"
---
# <span data-ttu-id="4bae5-103">Get-LocalUser</span><span class="sxs-lookup"><span data-stu-id="4bae5-103">Get-LocalUser</span></span>

## <span data-ttu-id="4bae5-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="4bae5-104">SYNOPSIS</span></span>
<span data-ttu-id="4bae5-105">Ruft lokale Benutzerkonten ab.</span><span class="sxs-lookup"><span data-stu-id="4bae5-105">Gets local user accounts.</span></span>

## <span data-ttu-id="4bae5-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4bae5-106">SYNTAX</span></span>

### <span data-ttu-id="4bae5-107">Standard (Standard)</span><span class="sxs-lookup"><span data-stu-id="4bae5-107">Default (Default)</span></span>

```
Get-LocalUser [[-Name] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="4bae5-108">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="4bae5-108">SecurityIdentifier</span></span>

```
Get-LocalUser [[-SID] <SecurityIdentifier[]>] [<CommonParameters>]
```

## <span data-ttu-id="4bae5-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4bae5-109">DESCRIPTION</span></span>

<span data-ttu-id="4bae5-110">Mit dem- `Get-LocalUser` Cmdlet werden lokale Benutzerkonten abgerufen.</span><span class="sxs-lookup"><span data-stu-id="4bae5-110">The `Get-LocalUser` cmdlet gets local user accounts.</span></span> <span data-ttu-id="4bae5-111">Mit diesem Cmdlet werden standardmäßige integrierte Benutzerkonten, lokale Benutzerkonten, die Sie erstellt haben, und lokale Konten, die Sie mit Microsoft-Konten verbunden haben, abgerufen.</span><span class="sxs-lookup"><span data-stu-id="4bae5-111">This cmdlet gets default built-in user accounts, local user accounts that you created, and local accounts that you connected to Microsoft accounts.</span></span>

> [!NOTE]
> <span data-ttu-id="4bae5-112">Das Microsoft. PowerShell. LocalAccounts-Modul ist in der 32-Bit-PowerShell auf einem 64-Bit-System nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4bae5-112">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="4bae5-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="4bae5-113">EXAMPLES</span></span>

### <span data-ttu-id="4bae5-114">Beispiel 1: erhalten eines Kontos mithilfe des Namens</span><span class="sxs-lookup"><span data-stu-id="4bae5-114">Example 1: Get an account by using its name</span></span>

<span data-ttu-id="4bae5-115">In diesem Beispiel wird ein Benutzerkonto mit dem Namen AdminContoso02 abgerufen.</span><span class="sxs-lookup"><span data-stu-id="4bae5-115">This example gets a user account named AdminContoso02.</span></span>

```powershell
Get-LocalUser -Name "AdminContoso02"
```

```Output
Name             Enabled Description
----             ------- -----------
AdminContoso02   True    Description of this account.
```

### <span data-ttu-id="4bae5-116">Beispiel 2: Holen Sie sich ein Konto, das mit einem Microsoft-Konto verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="4bae5-116">Example 2: Get an account that is connected to a Microsoft account</span></span>

<span data-ttu-id="4bae5-117">In diesem Beispiel wird ein Benutzerkonto abgerufen, das mit einem Microsoft-Konto verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="4bae5-117">This example gets a user account that is connected to a Microsoft account.</span></span> <span data-ttu-id="4bae5-118">In diesem Beispiel wird ein Platzhalter Wert für den Benutzernamen eines Kontos unter Outlook.com verwendet.</span><span class="sxs-lookup"><span data-stu-id="4bae5-118">This example uses a placeholder value for the username of an account at Outlook.com.</span></span>

```powershell
Get-LocalUser -Name "MicrosoftAccount\username@Outlook.com"
```

```Output
Name                                    Enabled  Description
----                                    -------  -----------
MicrosoftAccount\username@outlook.com  True     Description of this account.
```

### <span data-ttu-id="4bae5-119">Beispiel 3: Konto mit der angegebenen sid</span><span class="sxs-lookup"><span data-stu-id="4bae5-119">Example 3: Get an account that has the specified SID</span></span>

<span data-ttu-id="4bae5-120">In diesem Beispiel wird ein lokales Benutzerkonto abgerufen, das über die angegebene SID verfügt.</span><span class="sxs-lookup"><span data-stu-id="4bae5-120">This example gets a local user account that has the specified SID.</span></span>

```powershell
Get-LocalUser -SID S-1-5-21-9526073513-1762370368-3942940353-500
```

```Output
Name          Enabled Description
----          ------- -----------
Administrator True    Built-in account for administering the computer/domain
```

## <span data-ttu-id="4bae5-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4bae5-121">PARAMETERS</span></span>

### <span data-ttu-id="4bae5-122">-Name</span><span class="sxs-lookup"><span data-stu-id="4bae5-122">-Name</span></span>

<span data-ttu-id="4bae5-123">Gibt ein Array von Namen von Benutzerkonten an, die von diesem Cmdlet abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="4bae5-123">Specifies an array of names of user accounts that this cmdlet gets.</span></span> <span data-ttu-id="4bae5-124">Sie können das Platzhalter Zeichen verwenden.</span><span class="sxs-lookup"><span data-stu-id="4bae5-124">You can use the wildcard character.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="4bae5-125">-SID</span><span class="sxs-lookup"><span data-stu-id="4bae5-125">-SID</span></span>

<span data-ttu-id="4bae5-126">Gibt ein Array von Sicherheits-IDs (SIDs) von Benutzerkonten an, die von diesem Cmdlet abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="4bae5-126">Specifies an array of security IDs (SIDs) of user accounts that this cmdlet gets.</span></span>

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

### <span data-ttu-id="4bae5-127">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="4bae5-127">CommonParameters</span></span>

<span data-ttu-id="4bae5-128">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4bae5-128">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4bae5-129">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4bae5-129">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4bae5-130">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="4bae5-130">INPUTS</span></span>

### <span data-ttu-id="4bae5-131">System. String, System. Security. Principal. SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="4bae5-131">System.String, System.Security.Principal.SecurityIdentifier</span></span>

<span data-ttu-id="4bae5-132">Sie können eine Zeichenfolge oder eine SID an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="4bae5-132">You can pipe a string or SID to this cmdlet.</span></span>

## <span data-ttu-id="4bae5-133">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="4bae5-133">OUTPUTS</span></span>

### <span data-ttu-id="4bae5-134">System. Management. Automation. securityaccounungmanager. LocalUser []</span><span class="sxs-lookup"><span data-stu-id="4bae5-134">System.Management.Automation.SecurityAccountsManager.LocalUser[]</span></span>

<span data-ttu-id="4bae5-135">Mit diesem Cmdlet werden lokale Benutzerkonten zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4bae5-135">This cmdlet returns local user accounts.</span></span>

## <span data-ttu-id="4bae5-136">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="4bae5-136">NOTES</span></span>

<span data-ttu-id="4bae5-137">Die **principalsource** -Eigenschaft für die Objekte **LocalUser**, **localgroup** und **localprincipal** beschreibt die Quelle des Objekts.</span><span class="sxs-lookup"><span data-stu-id="4bae5-137">The **PrincipalSource** property on **LocalUser**, **LocalGroup**, and **LocalPrincipal** objects describes the source of the object.</span></span> <span data-ttu-id="4bae5-138">Folgende Quellen sind möglich:</span><span class="sxs-lookup"><span data-stu-id="4bae5-138">The possible sources are as follows:</span></span>

- <span data-ttu-id="4bae5-139">Lokal</span><span class="sxs-lookup"><span data-stu-id="4bae5-139">Local</span></span>
- <span data-ttu-id="4bae5-140">Active Directory</span><span class="sxs-lookup"><span data-stu-id="4bae5-140">Active Directory</span></span>
- <span data-ttu-id="4bae5-141">Azure Active Directory-Gruppe</span><span class="sxs-lookup"><span data-stu-id="4bae5-141">Azure Active Directory group</span></span>
- <span data-ttu-id="4bae5-142">Microsoft-Konto</span><span class="sxs-lookup"><span data-stu-id="4bae5-142">Microsoft Account</span></span>

<span data-ttu-id="4bae5-143">**Principalsource** wird nur von Windows 10, Windows Server 2016 und neueren Versionen des Windows-Betriebssystems unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4bae5-143">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="4bae5-144">Bei früheren Versionen ist die-Eigenschaft leer.</span><span class="sxs-lookup"><span data-stu-id="4bae5-144">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="4bae5-145">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="4bae5-145">RELATED LINKS</span></span>

[<span data-ttu-id="4bae5-146">Disable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="4bae5-146">Disable-LocalUser</span></span>](Disable-LocalUser.md)

[<span data-ttu-id="4bae5-147">Enable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="4bae5-147">Enable-LocalUser</span></span>](Enable-LocalUser.md)

[<span data-ttu-id="4bae5-148">New-LocalUser</span><span class="sxs-lookup"><span data-stu-id="4bae5-148">New-LocalUser</span></span>](New-LocalUser.md)

[<span data-ttu-id="4bae5-149">Remove-LocalUser</span><span class="sxs-lookup"><span data-stu-id="4bae5-149">Remove-LocalUser</span></span>](Remove-LocalUser.md)

[<span data-ttu-id="4bae5-150">Rename-LocalUser</span><span class="sxs-lookup"><span data-stu-id="4bae5-150">Rename-LocalUser</span></span>](Rename-LocalUser.md)

[<span data-ttu-id="4bae5-151">Set-LocalUser</span><span class="sxs-lookup"><span data-stu-id="4bae5-151">Set-LocalUser</span></span>](Set-LocalUser.md)
