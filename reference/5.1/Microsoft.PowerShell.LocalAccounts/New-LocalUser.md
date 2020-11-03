---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/new-localuser?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-LocalUser
ms.openlocfilehash: d83f3ad12481df0849ff2fe3f61d553a9ffdcdde
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214671"
---
# <span data-ttu-id="4855c-103">New-LocalUser</span><span class="sxs-lookup"><span data-stu-id="4855c-103">New-LocalUser</span></span>

## <span data-ttu-id="4855c-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="4855c-104">SYNOPSIS</span></span>

<span data-ttu-id="4855c-105">Erstellt ein lokales Benutzerkonto.</span><span class="sxs-lookup"><span data-stu-id="4855c-105">Creates a local user account.</span></span>

## <span data-ttu-id="4855c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4855c-106">SYNTAX</span></span>

### <span data-ttu-id="4855c-107">Kennwort (Standard)</span><span class="sxs-lookup"><span data-stu-id="4855c-107">Password (Default)</span></span>

```
New-LocalUser [-AccountExpires <DateTime>] [-AccountNeverExpires] [-Description <String>] [-Disabled]
 [-FullName <String>] [-Name] <String> -Password <SecureString> [-PasswordNeverExpires]
 [-UserMayNotChangePassword] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="4855c-108">Nopassword</span><span class="sxs-lookup"><span data-stu-id="4855c-108">NoPassword</span></span>

```
New-LocalUser [-AccountExpires <DateTime>] [-AccountNeverExpires] [-Description <String>] [-Disabled]
 [-FullName <String>] [-Name] <String> [-NoPassword] [-UserMayNotChangePassword] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="4855c-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4855c-109">DESCRIPTION</span></span>

<span data-ttu-id="4855c-110">Mit dem- `New-LocalUser` Cmdlet wird ein lokales Benutzerkonto erstellt.</span><span class="sxs-lookup"><span data-stu-id="4855c-110">The `New-LocalUser` cmdlet creates a local user account.</span></span> <span data-ttu-id="4855c-111">Dieses Cmdlet erstellt ein lokales Benutzerkonto oder ein lokales Benutzerkonto, das mit einem Microsoft-Konto verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="4855c-111">This cmdlet creates a local user account or a local user account that is connected to a Microsoft account.</span></span>

> [!NOTE]
> <span data-ttu-id="4855c-112">Das Microsoft. PowerShell. LocalAccounts-Modul ist in der 32-Bit-PowerShell auf einem 64-Bit-System nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4855c-112">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="4855c-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="4855c-113">EXAMPLES</span></span>

### <span data-ttu-id="4855c-114">Beispiel 1: Erstellen eines Benutzerkontos</span><span class="sxs-lookup"><span data-stu-id="4855c-114">Example 1: Create a user account</span></span>

```
PS C:\> New-LocalUser -Name "User02" -Description "Description of this account." -NoPassword
Name    Enabled  Description
----    -------  -----------
User02  True     Description of this account.
```

<span data-ttu-id="4855c-115">Mit diesem Befehl wird ein lokales Benutzerkonto erstellt, und die Parameter " **AccountExpires** " oder " **Password** " werden nicht angegeben.</span><span class="sxs-lookup"><span data-stu-id="4855c-115">This command creates a local user account and does not specify the **AccountExpires** or **Password** parameters.</span></span> <span data-ttu-id="4855c-116">Daher läuft das Konto nicht ab oder hat standardmäßig ein Kennwort.</span><span class="sxs-lookup"><span data-stu-id="4855c-116">Therefore, the account doesn't expire or have a password by default.</span></span>

### <span data-ttu-id="4855c-117">Beispiel 2: Erstellen eines Benutzerkontos mit einem Kennwort</span><span class="sxs-lookup"><span data-stu-id="4855c-117">Example 2: Create a user account that has a password</span></span>

```
PS C:\> $Password = Read-Host -AsSecureString
PS C:\> New-LocalUser "User03" -Password $Password -FullName "Third User" -Description "Description of this account."
Name    Enabled  Description
----    -------  -----------
User03  True     Description of this account.
```

<span data-ttu-id="4855c-118">Der erste Befehl fordert Sie mithilfe des-Cmdlets zur Eingabe eines Kennworts auf `Read-Host` .</span><span class="sxs-lookup"><span data-stu-id="4855c-118">The first command prompts you for a password by using the `Read-Host` cmdlet.</span></span> <span data-ttu-id="4855c-119">Der Befehl speichert das Kennwort als sichere Zeichenfolge in der `$Password` Variablen.</span><span class="sxs-lookup"><span data-stu-id="4855c-119">The command stores the password as a secure string in the `$Password` variable.</span></span>

<span data-ttu-id="4855c-120">Mit dem zweiten Befehl wird ein lokales Benutzerkonto mit dem in gespeicherten Kennwort erstellt `$Password` .</span><span class="sxs-lookup"><span data-stu-id="4855c-120">The second command creates a local user account by using the password stored in `$Password`.</span></span> <span data-ttu-id="4855c-121">Der Befehl gibt einen Benutzernamen, einen vollständigen Namen und eine Beschreibung für das Benutzerkonto an.</span><span class="sxs-lookup"><span data-stu-id="4855c-121">The command specifies a user name, full name, and description for the user account.</span></span>

## <span data-ttu-id="4855c-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4855c-122">PARAMETERS</span></span>

### <span data-ttu-id="4855c-123">-AccountExpires</span><span class="sxs-lookup"><span data-stu-id="4855c-123">-AccountExpires</span></span>

<span data-ttu-id="4855c-124">Gibt an, wann das Benutzerkonto abläuft.</span><span class="sxs-lookup"><span data-stu-id="4855c-124">Specifies when the user account expires.</span></span> <span data-ttu-id="4855c-125">Verwenden Sie zum Abrufen eines **DateTime** -Objekts das- `Get-Date` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="4855c-125">To obtain a **DateTime** object, use the `Get-Date` cmdlet.</span></span>
<span data-ttu-id="4855c-126">Wenn Sie diesen Parameter nicht angeben, läuft das Konto nicht ab.</span><span class="sxs-lookup"><span data-stu-id="4855c-126">If you do not specify this parameter, the account does not expire.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4855c-127">-Accountneverabläuft</span><span class="sxs-lookup"><span data-stu-id="4855c-127">-AccountNeverExpires</span></span>

<span data-ttu-id="4855c-128">Gibt an, dass das Konto nicht abläuft.</span><span class="sxs-lookup"><span data-stu-id="4855c-128">Indicates that the account does not expire.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4855c-129">-Description</span><span class="sxs-lookup"><span data-stu-id="4855c-129">-Description</span></span>

<span data-ttu-id="4855c-130">Gibt einen Kommentar für das Benutzerkonto an.</span><span class="sxs-lookup"><span data-stu-id="4855c-130">Specifies a comment for the user account.</span></span>
<span data-ttu-id="4855c-131">Die maximale Länge beträgt 48 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="4855c-131">The maximum length is 48 characters.</span></span>

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

### <span data-ttu-id="4855c-132">-Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="4855c-132">-Disabled</span></span>

<span data-ttu-id="4855c-133">Gibt an, dass dieses Cmdlet das Benutzerkonto als deaktiviert erstellt.</span><span class="sxs-lookup"><span data-stu-id="4855c-133">Indicates that this cmdlet creates the user account as disabled.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4855c-134">-FullName</span><span class="sxs-lookup"><span data-stu-id="4855c-134">-FullName</span></span>

<span data-ttu-id="4855c-135">Gibt den vollständigen Namen des Benutzerkontos an.</span><span class="sxs-lookup"><span data-stu-id="4855c-135">Specifies the full name for the user account.</span></span> <span data-ttu-id="4855c-136">Der vollständige Name unterscheidet sich vom Benutzernamen des Benutzerkontos.</span><span class="sxs-lookup"><span data-stu-id="4855c-136">The full name differs from the user name of the user account.</span></span>

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

### <span data-ttu-id="4855c-137">-Name</span><span class="sxs-lookup"><span data-stu-id="4855c-137">-Name</span></span>

<span data-ttu-id="4855c-138">Gibt den Benutzernamen für das Benutzerkonto an.</span><span class="sxs-lookup"><span data-stu-id="4855c-138">Specifies the user name for the user account.</span></span>

<span data-ttu-id="4855c-139">Wenn Sie ein lokales Benutzerkonto für das lokale System erstellen, kann der Benutzername bis zu 20 Groß-oder Kleinbuchstaben enthalten.</span><span class="sxs-lookup"><span data-stu-id="4855c-139">If you create a local user account for the local system, the user name can contain up to 20 uppercase characters or lowercase characters.</span></span> <span data-ttu-id="4855c-140">Ein Benutzername darf nicht die folgenden Zeichen enthalten:</span><span class="sxs-lookup"><span data-stu-id="4855c-140">A user name cannot contain the following characters:</span></span>

<span data-ttu-id="4855c-141">`"`, `/`, `\`, `[`, `]`, `:`, `;`, `|`, `=`, `,`, `+`, `*`, `?`, `<`, `>`, `@`</span><span class="sxs-lookup"><span data-stu-id="4855c-141">`"`, `/`, `\`, `[`, `]`, `:`, `;`, `|`, `=`, `,`, `+`, `*`, `?`, `<`, `>`, `@`</span></span>

<span data-ttu-id="4855c-142">Ein Benutzername darf nicht ausschließlich aus Punkten `.` oder Leerzeichen bestehen.</span><span class="sxs-lookup"><span data-stu-id="4855c-142">A user name cannot consist only of periods `.` or spaces.</span></span>

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

### <span data-ttu-id="4855c-143">-Nopassword</span><span class="sxs-lookup"><span data-stu-id="4855c-143">-NoPassword</span></span>

<span data-ttu-id="4855c-144">Gibt an, dass das Benutzerkonto nicht über ein Kennwort verfügt.</span><span class="sxs-lookup"><span data-stu-id="4855c-144">Indicates that the user account does not have a password.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NoPassword
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4855c-145">-Password</span><span class="sxs-lookup"><span data-stu-id="4855c-145">-Password</span></span>

<span data-ttu-id="4855c-146">Gibt ein Kennwort für das Benutzerkonto an.</span><span class="sxs-lookup"><span data-stu-id="4855c-146">Specifies a password for the user account.</span></span> <span data-ttu-id="4855c-147">Sie können `Read-Host -GetCredential` , oder verwenden, `Get-Credential` `ConvertTo-SecureString` um ein **SecureString** -Objekt für das Kennwort zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4855c-147">You can use `Read-Host -GetCredential`, `Get-Credential`, or `ConvertTo-SecureString` to create a **SecureString** object for the password.</span></span>

<span data-ttu-id="4855c-148">Wenn Sie die Parameter " **Password** " und " **nopassword** " weglassen, werden `New-LocalUser` Sie von aufgefordert, das Kennwort des neuen Benutzers einzugeben.</span><span class="sxs-lookup"><span data-stu-id="4855c-148">If you omit the **Password** and **NoPassword** parameters, `New-LocalUser` prompts you for the new user's password.</span></span>

```yaml
Type: System.Security.SecureString
Parameter Sets: Password
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4855c-149">-Passwordneverabläuft</span><span class="sxs-lookup"><span data-stu-id="4855c-149">-PasswordNeverExpires</span></span>

<span data-ttu-id="4855c-150">Gibt an, ob das Kennwort abläuft.</span><span class="sxs-lookup"><span data-stu-id="4855c-150">Indicates whether the password expires.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Password
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4855c-151">-Usermaynotchangepassword</span><span class="sxs-lookup"><span data-stu-id="4855c-151">-UserMayNotChangePassword</span></span>

<span data-ttu-id="4855c-152">Gibt an, dass der Benutzer das Kennwort für das Benutzerkonto nicht ändern kann.</span><span class="sxs-lookup"><span data-stu-id="4855c-152">Indicates that the user cannot change the password on the user account.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4855c-153">-Confirm</span><span class="sxs-lookup"><span data-stu-id="4855c-153">-Confirm</span></span>

<span data-ttu-id="4855c-154">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="4855c-154">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="4855c-155">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="4855c-155">-WhatIf</span></span>

<span data-ttu-id="4855c-156">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4855c-156">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="4855c-157">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4855c-157">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="4855c-158">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="4855c-158">CommonParameters</span></span>

<span data-ttu-id="4855c-159">Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="4855c-159">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="4855c-160">Weitere Informationen findest du unter [about_CommonParameters](/reference/6/Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="4855c-160">For more information, see [about_CommonParameters](/reference/6/Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="4855c-161">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="4855c-161">INPUTS</span></span>

### <span data-ttu-id="4855c-162">System. String, System. DateTime, System. Boolean, System. Security. SecureString</span><span class="sxs-lookup"><span data-stu-id="4855c-162">System.String, System.DateTime, System.Boolean, System.Security.SecureString</span></span>

<span data-ttu-id="4855c-163">Sie können eine Zeichenfolge, ein **DateTime** -Objekt, einen booleschen Wert oder eine sichere Zeichenfolge an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="4855c-163">You can pipe a string, a **DateTime** object, a boolean value, or a secure string to this cmdlet.</span></span>

## <span data-ttu-id="4855c-164">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="4855c-164">OUTPUTS</span></span>

### <span data-ttu-id="4855c-165">System. Management. Automation. securityaccounungmanager. LocalUser</span><span class="sxs-lookup"><span data-stu-id="4855c-165">System.Management.Automation.SecurityAccountsManager.LocalUser</span></span>

<span data-ttu-id="4855c-166">Dieses Cmdlet gibt ein **LocalUser** -Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="4855c-166">This cmdlet returns a **LocalUser** object.</span></span>
<span data-ttu-id="4855c-167">Dieses Objekt stellt Informationen zum Benutzerkonto bereit.</span><span class="sxs-lookup"><span data-stu-id="4855c-167">This object provides information about the user account.</span></span>

## <span data-ttu-id="4855c-168">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="4855c-168">NOTES</span></span>

- <span data-ttu-id="4855c-169">Ein Benutzername darf nicht mit einem anderen Benutzernamen oder Gruppennamen auf dem Computer identisch sein.</span><span class="sxs-lookup"><span data-stu-id="4855c-169">A user name cannot be identical to any other user name or group name on the computer.</span></span> <span data-ttu-id="4855c-170">Ein Benutzername darf nicht ausschließlich aus Punkten `.` oder Leerzeichen bestehen.</span><span class="sxs-lookup"><span data-stu-id="4855c-170">A user name cannot consist only of periods `.` or spaces.</span></span> <span data-ttu-id="4855c-171">Ein Benutzername kann bis zu 20 Groß-oder Kleinbuchstaben enthalten.</span><span class="sxs-lookup"><span data-stu-id="4855c-171">A user name can contain up to 20 uppercase characters or lowercase characters.</span></span> <span data-ttu-id="4855c-172">Ein Benutzername darf nicht die folgenden Zeichen enthalten:</span><span class="sxs-lookup"><span data-stu-id="4855c-172">A user name cannot contain the following characters:</span></span>

<span data-ttu-id="4855c-173">`"`, `/`, `\`, `[`, `]`, `:`, `;`, `|`, `=`, `,`, `+`, `*`, `?`, `<`, `>`, `@`</span><span class="sxs-lookup"><span data-stu-id="4855c-173">`"`, `/`, `\`, `[`, `]`, `:`, `;`, `|`, `=`, `,`, `+`, `*`, `?`, `<`, `>`, `@`</span></span>

- <span data-ttu-id="4855c-174">Ein Kennwort kann bis zu 127 Zeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="4855c-174">A password can contain up to 127 characters.</span></span>
- <span data-ttu-id="4855c-175">Die **principalsource** -Eigenschaft ist eine Eigenschaft für die Objekte " **LocalUser** ", " **localgroup** " und " **localprincipal** ", die die Quelle des Objekts beschreiben.</span><span class="sxs-lookup"><span data-stu-id="4855c-175">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="4855c-176">Folgende Quellen sind möglich:</span><span class="sxs-lookup"><span data-stu-id="4855c-176">The possible sources are as follows:</span></span>

  - <span data-ttu-id="4855c-177">Lokal</span><span class="sxs-lookup"><span data-stu-id="4855c-177">Local</span></span>
  - <span data-ttu-id="4855c-178">Active Directory</span><span class="sxs-lookup"><span data-stu-id="4855c-178">Active Directory</span></span>
  - <span data-ttu-id="4855c-179">Azure Active Directory-Gruppe</span><span class="sxs-lookup"><span data-stu-id="4855c-179">Azure Active Directory group</span></span>
  - <span data-ttu-id="4855c-180">Microsoft-Konto</span><span class="sxs-lookup"><span data-stu-id="4855c-180">Microsoft Account</span></span>

> [!NOTE]
> <span data-ttu-id="4855c-181">**Principalsource** wird nur von Windows 10, Windows Server 2016 und neueren Versionen des Windows-Betriebssystems unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4855c-181">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="4855c-182">Bei früheren Versionen ist die-Eigenschaft leer.</span><span class="sxs-lookup"><span data-stu-id="4855c-182">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="4855c-183">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="4855c-183">RELATED LINKS</span></span>

[<span data-ttu-id="4855c-184">Disable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="4855c-184">Disable-LocalUser</span></span>](Disable-LocalUser.md)

[<span data-ttu-id="4855c-185">Enable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="4855c-185">Enable-LocalUser</span></span>](Enable-LocalUser.md)

[<span data-ttu-id="4855c-186">Get-LocalUser</span><span class="sxs-lookup"><span data-stu-id="4855c-186">Get-LocalUser</span></span>](Get-LocalUser.md)

[<span data-ttu-id="4855c-187">Remove-LocalUser</span><span class="sxs-lookup"><span data-stu-id="4855c-187">Remove-LocalUser</span></span>](Remove-LocalUser.md)

[<span data-ttu-id="4855c-188">Rename-LocalUser</span><span class="sxs-lookup"><span data-stu-id="4855c-188">Rename-LocalUser</span></span>](Rename-LocalUser.md)

[<span data-ttu-id="4855c-189">Set-LocalUser</span><span class="sxs-lookup"><span data-stu-id="4855c-189">Set-LocalUser</span></span>](Set-LocalUser.md)
