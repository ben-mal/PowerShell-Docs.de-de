---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/set-localuser?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-LocalUser
ms.openlocfilehash: a6352611b757dae828a2efef07f9ce65abaa5e2e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215615"
---
# <span data-ttu-id="ed388-103">Set-LocalUser</span><span class="sxs-lookup"><span data-stu-id="ed388-103">Set-LocalUser</span></span>

## <span data-ttu-id="ed388-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="ed388-104">SYNOPSIS</span></span>
<span data-ttu-id="ed388-105">Ändert ein lokales Benutzerkonto.</span><span class="sxs-lookup"><span data-stu-id="ed388-105">Modifies a local user account.</span></span>

## <span data-ttu-id="ed388-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ed388-106">SYNTAX</span></span>

### <span data-ttu-id="ed388-107">Name (Standard)</span><span class="sxs-lookup"><span data-stu-id="ed388-107">Name (Default)</span></span>

```
Set-LocalUser [-AccountExpires <DateTime>] [-AccountNeverExpires] [-Description <String>] [-FullName <String>]
 [-Name] <String> [-Password <SecureString>] [-PasswordNeverExpires <Boolean>]
 [-UserMayChangePassword <Boolean>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="ed388-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="ed388-108">InputObject</span></span>

```
Set-LocalUser [-AccountExpires <DateTime>] [-AccountNeverExpires] [-Description <String>] [-FullName <String>]
 [-InputObject] <LocalUser> [-Password <SecureString>] [-PasswordNeverExpires <Boolean>]
 [-UserMayChangePassword <Boolean>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="ed388-109">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="ed388-109">SecurityIdentifier</span></span>

```
Set-LocalUser [-AccountExpires <DateTime>] [-AccountNeverExpires] [-Description <String>] [-FullName <String>]
 [-Password <SecureString>] [-PasswordNeverExpires <Boolean>] [-SID] <SecurityIdentifier>
 [-UserMayChangePassword <Boolean>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="ed388-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ed388-110">DESCRIPTION</span></span>
<span data-ttu-id="ed388-111">Mit dem Cmdlet " **Set-LocalUser** " wird ein lokales Benutzerkonto geändert.</span><span class="sxs-lookup"><span data-stu-id="ed388-111">The **Set-LocalUser** cmdlet modifies a local user account.</span></span>
<span data-ttu-id="ed388-112">Dieses Cmdlet kann das Kennwort eines lokalen Benutzerkontos zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="ed388-112">This cmdlet can reset the password of a local user account.</span></span>

> [!NOTE]
> <span data-ttu-id="ed388-113">Das Microsoft. PowerShell. LocalAccounts-Modul ist in der 32-Bit-PowerShell auf einem 64-Bit-System nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ed388-113">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="ed388-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="ed388-114">EXAMPLES</span></span>

### <span data-ttu-id="ed388-115">Beispiel 1: Ändern einer Beschreibung eines Benutzerkontos</span><span class="sxs-lookup"><span data-stu-id="ed388-115">Example 1: Change a description of a user account</span></span>

```
PS C:\> Set-LocalUser -Name "Admin07" -Description "Description of this account."
```

<span data-ttu-id="ed388-116">Mit diesem Befehl wird die Beschreibung eines Benutzerkontos mit dem Namen Admin07 geändert.</span><span class="sxs-lookup"><span data-stu-id="ed388-116">This command changes the description of a user account named Admin07.</span></span>

### <span data-ttu-id="ed388-117">Beispiel 2: Ändern des Kennworts für ein Konto</span><span class="sxs-lookup"><span data-stu-id="ed388-117">Example 2: Change the password on an account</span></span>

```
PS C:\> $Password = Read-Host -AsSecureString
PS C:\> $UserAccount = Get-LocalUser -Name "User02"
PS C:\> $UserAccount | Set-LocalUser -Password $Password
```

<span data-ttu-id="ed388-118">Der erste Befehl fordert Sie mithilfe des Read-Host-Cmdlets zur Eingabe eines Kennworts auf.</span><span class="sxs-lookup"><span data-stu-id="ed388-118">The first command prompts you for a password by using the Read-Host cmdlet.</span></span>
<span data-ttu-id="ed388-119">Der Befehl speichert das Kennwort als sichere Zeichenfolge in der $Password Variable.</span><span class="sxs-lookup"><span data-stu-id="ed388-119">The command stores the password as a secure string in the $Password variable.</span></span>

<span data-ttu-id="ed388-120">Mit dem zweiten Befehl wird ein Benutzerkonto mit dem Namen User02 mithilfe von **Get-LocalUser** abgerufen.</span><span class="sxs-lookup"><span data-stu-id="ed388-120">The second command gets a user account named User02 by using **Get-LocalUser** .</span></span>
<span data-ttu-id="ed388-121">Der Befehl speichert das Konto in der $Useraccount Variable.</span><span class="sxs-lookup"><span data-stu-id="ed388-121">The command stores the account in the $UserAccount variable.</span></span>

<span data-ttu-id="ed388-122">Mit dem dritten Befehl wird das neue Kennwort für das in $Useraccount gespeicherte Benutzerkonto festgelegt.</span><span class="sxs-lookup"><span data-stu-id="ed388-122">The third command sets the new password on the user account stored in $UserAccount.</span></span>

## <span data-ttu-id="ed388-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ed388-123">PARAMETERS</span></span>

### <span data-ttu-id="ed388-124">-AccountExpires</span><span class="sxs-lookup"><span data-stu-id="ed388-124">-AccountExpires</span></span>
<span data-ttu-id="ed388-125">Gibt an, wann das Benutzerkonto abläuft.</span><span class="sxs-lookup"><span data-stu-id="ed388-125">Specifies when the user account expires.</span></span>
<span data-ttu-id="ed388-126">Zum Abrufen eines **DateTime** -Objekts verwenden Sie das Cmdlet "Get-Date".</span><span class="sxs-lookup"><span data-stu-id="ed388-126">To obtain a **DateTime** object, use the Get-Date cmdlet.</span></span>

<span data-ttu-id="ed388-127">Wenn Sie nicht möchten, dass das Konto abläuft, geben Sie den *accountneverexpire* -Parameter an.</span><span class="sxs-lookup"><span data-stu-id="ed388-127">If you do not want the account to expire, specify the *AccountNeverExpires* parameter.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ed388-128">-Accountneverabläuft</span><span class="sxs-lookup"><span data-stu-id="ed388-128">-AccountNeverExpires</span></span>
<span data-ttu-id="ed388-129">Gibt an, dass das Konto nicht abläuft.</span><span class="sxs-lookup"><span data-stu-id="ed388-129">Indicates that the account does not expire.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ed388-130">-Description</span><span class="sxs-lookup"><span data-stu-id="ed388-130">-Description</span></span>
<span data-ttu-id="ed388-131">Gibt einen Kommentar für das Benutzerkonto an.</span><span class="sxs-lookup"><span data-stu-id="ed388-131">Specifies a comment for the user account.</span></span>
<span data-ttu-id="ed388-132">Die maximale Länge beträgt 48 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="ed388-132">The maximum length is 48 characters.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ed388-133">-FullName</span><span class="sxs-lookup"><span data-stu-id="ed388-133">-FullName</span></span>
<span data-ttu-id="ed388-134">Gibt den vollständigen Namen des Benutzerkontos an.</span><span class="sxs-lookup"><span data-stu-id="ed388-134">Specifies the full name for the user account.</span></span>
<span data-ttu-id="ed388-135">Der vollständige Name unterscheidet sich vom Benutzernamen des Benutzerkontos.</span><span class="sxs-lookup"><span data-stu-id="ed388-135">The full name differs from the user name of the user account.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ed388-136">-InputObject</span><span class="sxs-lookup"><span data-stu-id="ed388-136">-InputObject</span></span>
<span data-ttu-id="ed388-137">Gibt das Benutzerkonto an, das von diesem Cmdlet geändert wird.</span><span class="sxs-lookup"><span data-stu-id="ed388-137">Specifies the user account that this cmdlet changes.</span></span>
<span data-ttu-id="ed388-138">Verwenden Sie das Cmdlet "Get-LocalUser", um ein Benutzerkonto zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="ed388-138">To obtain a user account, use the Get-LocalUser cmdlet.</span></span>

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

### <span data-ttu-id="ed388-139">-Name</span><span class="sxs-lookup"><span data-stu-id="ed388-139">-Name</span></span>
<span data-ttu-id="ed388-140">Gibt den Namen des Benutzerkontos an, das von diesem Cmdlet geändert wird.</span><span class="sxs-lookup"><span data-stu-id="ed388-140">Specifies the name of the user account that this cmdlet changes.</span></span>

```yaml
Type: System.String
Parameter Sets: Name
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="ed388-141">-Password</span><span class="sxs-lookup"><span data-stu-id="ed388-141">-Password</span></span>
<span data-ttu-id="ed388-142">Gibt ein Kennwort für das Benutzerkonto an.</span><span class="sxs-lookup"><span data-stu-id="ed388-142">Specifies a password for the user account.</span></span>
<span data-ttu-id="ed388-143">Wenn das Benutzerkonto mit einem Microsoft-Konto verbunden ist, legen Sie kein Kennwort fest.</span><span class="sxs-lookup"><span data-stu-id="ed388-143">If the user account is connected to a Microsoft account, do not set a password.</span></span>

<span data-ttu-id="ed388-144">Sie können `Read-Host -GetCredential` , Get-Credential oder ConvertTo-SecureString verwenden, um ein **SecureString** -Objekt für das Kennwort zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ed388-144">You can use `Read-Host -GetCredential`, Get-Credential, or ConvertTo-SecureString to create a **SecureString** object for the password.</span></span>

<span data-ttu-id="ed388-145">Wenn Sie die Parameter " *Password* " und " *nopassword* " weglassen, werden Sie von **Set-LocalUser** zur Eingabe des Benutzer Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="ed388-145">If you omit the *Password* and *NoPassword* parameters, **Set-LocalUser** prompts you for the user's password.</span></span>

```yaml
Type: System.Security.SecureString
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ed388-146">-Passwordneverabläuft</span><span class="sxs-lookup"><span data-stu-id="ed388-146">-PasswordNeverExpires</span></span>
<span data-ttu-id="ed388-147">Gibt an, ob das Kennwort abläuft.</span><span class="sxs-lookup"><span data-stu-id="ed388-147">Indicates whether the password expires.</span></span>

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ed388-148">-SID</span><span class="sxs-lookup"><span data-stu-id="ed388-148">-SID</span></span>
<span data-ttu-id="ed388-149">Gibt die Sicherheits-ID (SID) des Benutzerkontos an, das von diesem Cmdlet geändert wird.</span><span class="sxs-lookup"><span data-stu-id="ed388-149">Specifies the security ID (SID) of the user account that this cmdlet changes.</span></span>

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

### <span data-ttu-id="ed388-150">-Usermaychangepassword</span><span class="sxs-lookup"><span data-stu-id="ed388-150">-UserMayChangePassword</span></span>
<span data-ttu-id="ed388-151">Gibt an, dass der Benutzer das Kennwort für das Benutzerkonto ändern kann.</span><span class="sxs-lookup"><span data-stu-id="ed388-151">Indicates that the user can change the password on the user account.</span></span>

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ed388-152">-Confirm</span><span class="sxs-lookup"><span data-stu-id="ed388-152">-Confirm</span></span>
<span data-ttu-id="ed388-153">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="ed388-153">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="ed388-154">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="ed388-154">-WhatIf</span></span>
<span data-ttu-id="ed388-155">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ed388-155">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="ed388-156">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ed388-156">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="ed388-157">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ed388-157">CommonParameters</span></span>
<span data-ttu-id="ed388-158">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ed388-158">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ed388-159">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ed388-159">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ed388-160">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="ed388-160">INPUTS</span></span>

### <span data-ttu-id="ed388-161">System. Management. Automation. securityaccountmanager. LocalUser, System. String, System. Security. Principal. SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="ed388-161">System.Management.Automation.SecurityAccountsManager.LocalUser, System.String, System.Security.Principal.SecurityIdentifier</span></span>
<span data-ttu-id="ed388-162">Sie können einen lokalen Benutzer, eine Zeichenfolge oder eine SID an dieses Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="ed388-162">You can pipe a local user, a string, or a SID to this cmdlet.</span></span>

## <span data-ttu-id="ed388-163">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="ed388-163">OUTPUTS</span></span>

### <span data-ttu-id="ed388-164">Keine</span><span class="sxs-lookup"><span data-stu-id="ed388-164">None</span></span>
<span data-ttu-id="ed388-165">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="ed388-165">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="ed388-166">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="ed388-166">NOTES</span></span>

* <span data-ttu-id="ed388-167">Die **principalsource** -Eigenschaft ist eine Eigenschaft für die Objekte " **LocalUser** ", " **localgroup** " und " **localprincipal** ", die die Quelle des Objekts beschreiben.</span><span class="sxs-lookup"><span data-stu-id="ed388-167">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="ed388-168">Folgende Quellen sind möglich:</span><span class="sxs-lookup"><span data-stu-id="ed388-168">The possible sources are as follows:</span></span>

- <span data-ttu-id="ed388-169">Lokal</span><span class="sxs-lookup"><span data-stu-id="ed388-169">Local</span></span>
- <span data-ttu-id="ed388-170">Active Directory</span><span class="sxs-lookup"><span data-stu-id="ed388-170">Active Directory</span></span>
- <span data-ttu-id="ed388-171">Azure Active Directory-Gruppe</span><span class="sxs-lookup"><span data-stu-id="ed388-171">Azure Active Directory group</span></span>
- <span data-ttu-id="ed388-172">Microsoft-Konto</span><span class="sxs-lookup"><span data-stu-id="ed388-172">Microsoft Account</span></span>

<span data-ttu-id="ed388-173">**Principalsource** wird nur von Windows 10, Windows Server 2016 und neueren Versionen des Windows-Betriebssystems unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ed388-173">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="ed388-174">Bei früheren Versionen ist die-Eigenschaft leer.</span><span class="sxs-lookup"><span data-stu-id="ed388-174">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="ed388-175">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="ed388-175">RELATED LINKS</span></span>

[<span data-ttu-id="ed388-176">Disable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="ed388-176">Disable-LocalUser</span></span>](Disable-LocalUser.md)

[<span data-ttu-id="ed388-177">Enable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="ed388-177">Enable-LocalUser</span></span>](Enable-LocalUser.md)

[<span data-ttu-id="ed388-178">Get-LocalUser</span><span class="sxs-lookup"><span data-stu-id="ed388-178">Get-LocalUser</span></span>](Get-LocalUser.md)

[<span data-ttu-id="ed388-179">New-LocalUser</span><span class="sxs-lookup"><span data-stu-id="ed388-179">New-LocalUser</span></span>](New-LocalUser.md)

[<span data-ttu-id="ed388-180">Remove-LocalUser</span><span class="sxs-lookup"><span data-stu-id="ed388-180">Remove-LocalUser</span></span>](Remove-LocalUser.md)

[<span data-ttu-id="ed388-181">Rename-LocalUser</span><span class="sxs-lookup"><span data-stu-id="ed388-181">Rename-LocalUser</span></span>](Rename-LocalUser.md)
