---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 05/01/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/rename-computer?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Rename-Computer
ms.openlocfilehash: 070a428530f4f3eecceb0ae3f520ad565097c1e0
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599205"
---
# <span data-ttu-id="cd896-102">Rename-Computer</span><span class="sxs-lookup"><span data-stu-id="cd896-102">Rename-Computer</span></span>

## <span data-ttu-id="cd896-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="cd896-103">SYNOPSIS</span></span>
<span data-ttu-id="cd896-104">Benennt einen Computer um.</span><span class="sxs-lookup"><span data-stu-id="cd896-104">Renames a computer.</span></span>

## <span data-ttu-id="cd896-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="cd896-105">SYNTAX</span></span>

```
Rename-Computer [-ComputerName <String>] [-PassThru] [-DomainCredential <PSCredential>]
 [-LocalCredential <PSCredential>] [-NewName] <String> [-Force] [-Restart] [-WsmanAuthentication <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="cd896-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="cd896-106">DESCRIPTION</span></span>

<span data-ttu-id="cd896-107">Das `Rename-Computer` Cmdlet benennt den lokalen Computer oder einen Remote Computer um.</span><span class="sxs-lookup"><span data-stu-id="cd896-107">The `Rename-Computer` cmdlet renames the local computer or a remote computer.</span></span>
<span data-ttu-id="cd896-108">Es benennt einen Computer in jedem Befehl um.</span><span class="sxs-lookup"><span data-stu-id="cd896-108">It renames one computer in each command.</span></span>

<span data-ttu-id="cd896-109">Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="cd896-109">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="cd896-110">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="cd896-110">EXAMPLES</span></span>

### <span data-ttu-id="cd896-111">Beispiel 1: Umbenennen des lokalen Computers</span><span class="sxs-lookup"><span data-stu-id="cd896-111">Example 1: Rename the local computer</span></span>

<span data-ttu-id="cd896-112">Mit diesem Befehl wird der lokale Computer in umbenannt `Server044` und dann neu gestartet, damit die Änderung wirksam wird.</span><span class="sxs-lookup"><span data-stu-id="cd896-112">This command renames the local computer to `Server044` and then restarts it to make the change effective.</span></span>

```powershell
Rename-Computer -NewName "Server044" -DomainCredential Domain01\Admin01 -Restart
```

### <span data-ttu-id="cd896-113">Beispiel 2: Umbenennen eines Remote Computers</span><span class="sxs-lookup"><span data-stu-id="cd896-113">Example 2: Rename a remote computer</span></span>

<span data-ttu-id="cd896-114">Mit diesem Befehl wird der `Srv01` Computer in umbenannt `Server001` .</span><span class="sxs-lookup"><span data-stu-id="cd896-114">This command renames the `Srv01` computer to `Server001`.</span></span> <span data-ttu-id="cd896-115">Der Computer wird nicht neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="cd896-115">The computer is not restarted.</span></span>

<span data-ttu-id="cd896-116">Mit dem **domaincredential** -Parameter werden die Anmelde Informationen eines Benutzers angegeben, der über die Berechtigung zum Umbenennen von Computern in der Domäne verfügt.</span><span class="sxs-lookup"><span data-stu-id="cd896-116">The **DomainCredential** parameter specifies the credentials of a user who has permission to rename computers in the domain.</span></span>

<span data-ttu-id="cd896-117">Der **Force** -Parameter unterdrückt die Bestätigungsaufforderung.</span><span class="sxs-lookup"><span data-stu-id="cd896-117">The **Force** parameter suppresses the confirmation prompt.</span></span>

```powershell
Rename-Computer -ComputerName "Srv01" -NewName "Server001" -DomainCredential Domain01\Admin01 -Force
```

## <span data-ttu-id="cd896-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="cd896-118">PARAMETERS</span></span>

### <span data-ttu-id="cd896-119">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="cd896-119">-ComputerName</span></span>

<span data-ttu-id="cd896-120">Benennt den angegebenen Remotecomputer um.</span><span class="sxs-lookup"><span data-stu-id="cd896-120">Renames the specified remote computer.</span></span>
<span data-ttu-id="cd896-121">Die Standardeinstellung ist der lokale Computer.</span><span class="sxs-lookup"><span data-stu-id="cd896-121">The default is the local computer.</span></span>

<span data-ttu-id="cd896-122">Geben Sie den NetBIOS-Namen, eine IP-Adresse oder den vollqualifizierten Domänennamen eines Remotecomputers ein.</span><span class="sxs-lookup"><span data-stu-id="cd896-122">Type the NetBIOS name, an IP address, or a fully qualified domain name of a remote computer.</span></span>
<span data-ttu-id="cd896-123">Um den lokalen Computer anzugeben, geben Sie den Computernamen, einen Punkt ( `.` ) oder ein `localhost` .</span><span class="sxs-lookup"><span data-stu-id="cd896-123">To specify the local computer, type the computer name, a dot (`.`), or `localhost`.</span></span>

<span data-ttu-id="cd896-124">Dieser Parameter beruht nicht auf PowerShell-Remoting.</span><span class="sxs-lookup"><span data-stu-id="cd896-124">This parameter does not rely on PowerShell remoting.</span></span>
<span data-ttu-id="cd896-125">Sie können den **Computername** -Parameter `Rename-Computer` auch dann verwenden, wenn der Computer nicht für das Ausführen von Remote Befehlen konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="cd896-125">You can use the **ComputerName** parameter of `Rename-Computer` even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Local Computer
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="cd896-126">-Domaincredential</span><span class="sxs-lookup"><span data-stu-id="cd896-126">-DomainCredential</span></span>

<span data-ttu-id="cd896-127">Gibt ein Benutzerkonto an, das über die Berechtigung zum Herstellen einer Verbindung mit der Domäne verfügt.</span><span class="sxs-lookup"><span data-stu-id="cd896-127">Specifies a user account that has permission to connect to the domain.</span></span>
<span data-ttu-id="cd896-128">Zum Umbenennen eines der Domäne hinzugefügten Computers sind explizite Anmeldeinformationen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="cd896-128">Explicit credentials are required to rename a computer that is joined to a domain.</span></span>

<span data-ttu-id="cd896-129">Geben Sie einen Benutzernamen ein, z. b. `User01` oder `Domain01\User01` , oder geben Sie ein **PSCredential** -Objekt ein, z. b. ein vom `Get-Credential` Cmdlet generiertes Objekt.</span><span class="sxs-lookup"><span data-stu-id="cd896-129">Type a user name, such as `User01` or `Domain01\User01`, or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="cd896-130">Wenn Sie einen Benutzernamen eingeben, werden Sie von diesem Cmdlet zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="cd896-130">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="cd896-131">Geben Sie ein Benutzerkonto, das über die Berechtigung zum Herstellen einer Verbindung mit dem durch den **ComputerName**-Parameter angegebenen Computer verfügt, mit dem **LocalCredential**-Parameter an.</span><span class="sxs-lookup"><span data-stu-id="cd896-131">To specify a user account that has permission to connect to the computer that is specified by the **ComputerName** parameter, use the **LocalCredential** parameter.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cd896-132">-Force</span><span class="sxs-lookup"><span data-stu-id="cd896-132">-Force</span></span>

<span data-ttu-id="cd896-133">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="cd896-133">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="cd896-134">-Localcredential</span><span class="sxs-lookup"><span data-stu-id="cd896-134">-LocalCredential</span></span>

<span data-ttu-id="cd896-135">Gibt ein Benutzerkonto an, das über die Berechtigung zum Herstellen einer Verbindung mit dem durch den **ComputerName**-Parameter angegebenen Computer verfügt.</span><span class="sxs-lookup"><span data-stu-id="cd896-135">Specifies a user account that has permission to connect to the computer specified by the **ComputerName** parameter.</span></span> <span data-ttu-id="cd896-136">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="cd896-136">The default is the current user.</span></span>

<span data-ttu-id="cd896-137">Geben Sie einen Benutzernamen ein, z. b. `User01` oder `Domain01\User01` , oder geben Sie ein **PSCredential** -Objekt ein, z. b. ein vom `Get-Credential` Cmdlet generiertes Objekt.</span><span class="sxs-lookup"><span data-stu-id="cd896-137">Type a user name, such as `User01` or `Domain01\User01`, or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="cd896-138">Wenn Sie einen Benutzernamen eingeben, werden Sie von diesem Cmdlet zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="cd896-138">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="cd896-139">Geben Sie ein Benutzerkonto, das über die Berechtigung zum Herstellen einer Verbindung mit der Domäne verfügt, mit dem **DomainCredential**-Parameter an.</span><span class="sxs-lookup"><span data-stu-id="cd896-139">To specify a user account that has permission to connect to the domain, use the **DomainCredential** parameter.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current User
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cd896-140">-Newname</span><span class="sxs-lookup"><span data-stu-id="cd896-140">-NewName</span></span>

<span data-ttu-id="cd896-141">Gibt einen neuen Namen für den Computer an.</span><span class="sxs-lookup"><span data-stu-id="cd896-141">Specifies a new name for the computer.</span></span>
<span data-ttu-id="cd896-142">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="cd896-142">This parameter is required.</span></span>

<span data-ttu-id="cd896-143">Standard Namen dürfen Buchstaben ( `a-z` ), ( `A-Z` ), Zahlen ( `0-9` ) und Bindestriche ( `-` ), jedoch keine Leerzeichen oder Punkte ( `.` ) enthalten.</span><span class="sxs-lookup"><span data-stu-id="cd896-143">Standard names may contain letters (`a-z`), (`A-Z`), numbers (`0-9`), and hyphens (`-`), but no spaces or periods (`.`).</span></span> <span data-ttu-id="cd896-144">Der Name darf nicht vollständig aus Ziffern bestehen und darf nicht länger als 63 Zeichen sein.</span><span class="sxs-lookup"><span data-stu-id="cd896-144">The name may not consist entirely of digits, and may not be longer than 63 characters</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="cd896-145">-PassThru</span><span class="sxs-lookup"><span data-stu-id="cd896-145">-PassThru</span></span>

<span data-ttu-id="cd896-146">Gibt die Ergebnisse des Befehls zurück.</span><span class="sxs-lookup"><span data-stu-id="cd896-146">Returns the results of the command.</span></span>
<span data-ttu-id="cd896-147">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="cd896-147">Otherwise, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="cd896-148">-Restart</span><span class="sxs-lookup"><span data-stu-id="cd896-148">-Restart</span></span>

<span data-ttu-id="cd896-149">Gibt an, dass mit diesem Cmdlet der umbenannte Computer neu gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="cd896-149">Indicates that this cmdlet restarts the computer that was renamed.</span></span>
<span data-ttu-id="cd896-150">Ein Neustart ist häufig erforderlich, damit die Änderung wirksam wird.</span><span class="sxs-lookup"><span data-stu-id="cd896-150">A restart is often required to make the change effective.</span></span>

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

### <span data-ttu-id="cd896-151">-Wsmanauthentication</span><span class="sxs-lookup"><span data-stu-id="cd896-151">-WsmanAuthentication</span></span>

<span data-ttu-id="cd896-152">Gibt den Mechanismus an, der verwendet wird, um die Benutzer Anmelde Informationen zu authentifizieren, wenn dieses Cmdlet das WSMAN-Protokoll verwendet.</span><span class="sxs-lookup"><span data-stu-id="cd896-152">Specifies the mechanism that is used to authenticate the user credentials when this cmdlet uses the WSMan protocol.</span></span> <span data-ttu-id="cd896-153">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="cd896-153">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="cd896-154">**Grundlegend**</span><span class="sxs-lookup"><span data-stu-id="cd896-154">**Basic**</span></span>
- <span data-ttu-id="cd896-155">**CredSSP**</span><span class="sxs-lookup"><span data-stu-id="cd896-155">**CredSSP**</span></span>
- <span data-ttu-id="cd896-156">**Standard**</span><span class="sxs-lookup"><span data-stu-id="cd896-156">**Default**</span></span>
- <span data-ttu-id="cd896-157">**Digest**</span><span class="sxs-lookup"><span data-stu-id="cd896-157">**Digest**</span></span>
- <span data-ttu-id="cd896-158">**Kerberos**</span><span class="sxs-lookup"><span data-stu-id="cd896-158">**Kerberos**</span></span>
- <span data-ttu-id="cd896-159">**Aushandeln**</span><span class="sxs-lookup"><span data-stu-id="cd896-159">**Negotiate**</span></span>

<span data-ttu-id="cd896-160">Der Standardwert lautet **Default**.</span><span class="sxs-lookup"><span data-stu-id="cd896-160">The default value is **Default**.</span></span>

<span data-ttu-id="cd896-161">Weitere Informationen zu den Werten dieses Parameters finden Sie unter [authenticationmechanism-Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span><span class="sxs-lookup"><span data-stu-id="cd896-161">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!WARNING]
> <span data-ttu-id="cd896-162">Die Authentifizierung des Anmelde Informations Diensts (Credential Security Service Provider, kredssp), in der die Benutzer Anmelde Informationen an einen Remote Computer übergeben werden, der authentifiziert werden soll, wurde für Befehle entworfen, die eine Authentifizierung auf mehreren Ressourcen erfordern</span><span class="sxs-lookup"><span data-stu-id="cd896-162">Credential Security Service Provider (CredSSP) authentication, in which the user credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span>
> <span data-ttu-id="cd896-163">Dieser Mechanismus erhöht das Sicherheitsrisiko des Remotevorgangs.</span><span class="sxs-lookup"><span data-stu-id="cd896-163">This mechanism increases the security risk of the remote operation.</span></span>
> <span data-ttu-id="cd896-164">Wenn der Remote Computer kompromittiert ist, können die an ihn weiter gegebenen Anmelde Informationen verwendet werden, um > die Netzwerksitzung zu steuern.</span><span class="sxs-lookup"><span data-stu-id="cd896-164">If the remote computer is compromised, the credentials that are passed to it can be used to control > the network session.</span></span>

<span data-ttu-id="cd896-165">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="cd896-165">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Default, Basic, Negotiate, CredSSP, Digest, Kerberos

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cd896-166">-Confirm</span><span class="sxs-lookup"><span data-stu-id="cd896-166">-Confirm</span></span>

<span data-ttu-id="cd896-167">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="cd896-167">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="cd896-168">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="cd896-168">-WhatIf</span></span>

<span data-ttu-id="cd896-169">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="cd896-169">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="cd896-170">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="cd896-170">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="cd896-171">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="cd896-171">CommonParameters</span></span>

<span data-ttu-id="cd896-172">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="cd896-172">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="cd896-173">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="cd896-173">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="cd896-174">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="cd896-174">INPUTS</span></span>

### <span data-ttu-id="cd896-175">Keine</span><span class="sxs-lookup"><span data-stu-id="cd896-175">None</span></span>

<span data-ttu-id="cd896-176">Dieses Cmdlet enthält keine Parameter, die eine Eingabe nach Wert annehmen.</span><span class="sxs-lookup"><span data-stu-id="cd896-176">This cmdlet does not have parameters that take input by value.</span></span> <span data-ttu-id="cd896-177">Sie können jedoch die Werte der Eigenschaften **ComputerName** und **NewName** von Objekten über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="cd896-177">However, you can pipe the values of the **ComputerName** and **NewName** properties of objects to this cmdlet.</span></span>

## <span data-ttu-id="cd896-178">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="cd896-178">OUTPUTS</span></span>

### <span data-ttu-id="cd896-179">Microsoft. PowerShell. Commands. computerchangeingefo</span><span class="sxs-lookup"><span data-stu-id="cd896-179">Microsoft.PowerShell.Commands.ComputerChangeInfo</span></span>

<span data-ttu-id="cd896-180">Dieses Cmdlet gibt ein **computerchangeinfo** -Objekt zurück, wenn Sie den **passthru** -Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="cd896-180">This cmdlet returns a **ComputerChangeInfo** object, if you specify the **PassThru** parameter.</span></span>
<span data-ttu-id="cd896-181">Andernfalls wird keine Ausgabe zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="cd896-181">Otherwise, it does not return any output.</span></span>

## <span data-ttu-id="cd896-182">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="cd896-182">NOTES</span></span>

<span data-ttu-id="cd896-183">Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="cd896-183">This cmdlet is only available on Windows platforms.</span></span>

## <span data-ttu-id="cd896-184">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="cd896-184">RELATED LINKS</span></span>

[<span data-ttu-id="cd896-185">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="cd896-185">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="cd896-186">Stop-Computer</span><span class="sxs-lookup"><span data-stu-id="cd896-186">Stop-Computer</span></span>](Stop-Computer.md)
