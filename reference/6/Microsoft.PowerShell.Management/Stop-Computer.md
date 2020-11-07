---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/11/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/stop-computer?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Computer
ms.openlocfilehash: 8c6d70622f48183ed2f6bcd4526c305c70fe6eb2
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2020
ms.locfileid: "94345084"
---
# <span data-ttu-id="047f4-103">Stop-Computer</span><span class="sxs-lookup"><span data-stu-id="047f4-103">Stop-Computer</span></span>

## <span data-ttu-id="047f4-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="047f4-104">SYNOPSIS</span></span>
<span data-ttu-id="047f4-105">Beendet den lokalen Computer und Remotecomputer (fährt sie herunter).</span><span class="sxs-lookup"><span data-stu-id="047f4-105">Stops (shuts down) local and remote computers.</span></span>

## <span data-ttu-id="047f4-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="047f4-106">SYNTAX</span></span>

### <span data-ttu-id="047f4-107">Alle</span><span class="sxs-lookup"><span data-stu-id="047f4-107">All</span></span>

```
Stop-Computer [-WsmanAuthentication <String>] [[-ComputerName] <String[]>]
 [[-Credential] <PSCredential>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="047f4-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="047f4-108">DESCRIPTION</span></span>

<span data-ttu-id="047f4-109">Mit dem `Stop-Computer` -Cmdlet werden der lokale Computer und Remote Computer heruntergefahren.</span><span class="sxs-lookup"><span data-stu-id="047f4-109">The `Stop-Computer` cmdlet shuts down the local computer and remote computers.</span></span>

<span data-ttu-id="047f4-110">Mit den Parametern von können Sie `Stop-Computer` die Authentifizierungs Ebenen und Alternative Anmelde Informationen angeben und ein sofortiges Herunterfahren erzwingen.</span><span class="sxs-lookup"><span data-stu-id="047f4-110">You can use the parameters of `Stop-Computer` to specify the authentication levels and alternate credentials, and to force an immediate shut down.</span></span>

## <span data-ttu-id="047f4-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="047f4-111">EXAMPLES</span></span>

### <span data-ttu-id="047f4-112">Beispiel 1: Herunterfahren des lokalen Computers</span><span class="sxs-lookup"><span data-stu-id="047f4-112">Example 1: Shut down the local computer</span></span>

<span data-ttu-id="047f4-113">In diesem Beispiel wird der lokale Computer heruntergefahren.</span><span class="sxs-lookup"><span data-stu-id="047f4-113">This example shuts down the local computer.</span></span>

```powershell
Stop-Computer -ComputerName localhost
```

### <span data-ttu-id="047f4-114">Beispiel 2: Herunterfahren von zwei Remote Computern und dem lokalen Computer</span><span class="sxs-lookup"><span data-stu-id="047f4-114">Example 2: Shut down two remote computers and the local computer</span></span>

<span data-ttu-id="047f4-115">In diesem Beispiel werden zwei Remote Computer und der lokale Computer angehalten.</span><span class="sxs-lookup"><span data-stu-id="047f4-115">This example stops two remote computers and the local computer.</span></span>

```powershell
Stop-Computer -ComputerName "Server01", "Server02", "localhost"
```

<span data-ttu-id="047f4-116">`Stop-Computer` verwendet den **Computername** -Parameter, um zwei Remote Computer und den lokalen Computer anzugeben.</span><span class="sxs-lookup"><span data-stu-id="047f4-116">`Stop-Computer` uses the **ComputerName** parameter to specify two remote computers and the local computer.</span></span> <span data-ttu-id="047f4-117">Jeder Computer wird heruntergefahren.</span><span class="sxs-lookup"><span data-stu-id="047f4-117">Each computer is shut down.</span></span>

### <span data-ttu-id="047f4-118">Beispiel 3: Herunterfahren von Remote Computern als Hintergrund Auftrag</span><span class="sxs-lookup"><span data-stu-id="047f4-118">Example 3: Shut down remote computers as a background job</span></span>

<span data-ttu-id="047f4-119">In diesem Beispiel wird `Stop-Computer` als Hintergrund Auftrag auf zwei Remote Computern ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="047f4-119">In this example, `Stop-Computer` runs as a background job on two remote computers.</span></span>

<span data-ttu-id="047f4-120">Der Background-Operator `&` führt den `Stop-Computer` Befehl als Hintergrund Auftrag aus.</span><span class="sxs-lookup"><span data-stu-id="047f4-120">The background operator `&` runs the `Stop-Computer` command as a background job.</span></span> <span data-ttu-id="047f4-121">Weitere Informationen finden Sie unter [about_Operators](../microsoft.powershell.core/about/about_operators.md#background-operator-).</span><span class="sxs-lookup"><span data-stu-id="047f4-121">For more information, see [about_Operators](../microsoft.powershell.core/about/about_operators.md#background-operator-).</span></span>

```powershell
$j = Stop-Computer -ComputerName "Server01", "Server02" &
$results = $j | Receive-Job
$results
```

<span data-ttu-id="047f4-122">`Stop-Computer` verwendet den **Computername** -Parameter, um zwei Remote Computer anzugeben.</span><span class="sxs-lookup"><span data-stu-id="047f4-122">`Stop-Computer` uses the **ComputerName** parameter to specify two remote computers.</span></span> <span data-ttu-id="047f4-123">Der `&` Background-Operator führt den Befehl als Hintergrund Auftrag aus.</span><span class="sxs-lookup"><span data-stu-id="047f4-123">The `&` background operator runs the command as a background job.</span></span> <span data-ttu-id="047f4-124">Die Auftrags Objekte werden in der `$j` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="047f4-124">The job objects are stored in the `$j` variable.</span></span>

<span data-ttu-id="047f4-125">Die Auftrags Objekte in der `$j` Variablen werden an die Pipeline gesendet `Receive-Job` , die die Auftrags Ergebnisse abruft.</span><span class="sxs-lookup"><span data-stu-id="047f4-125">The job objects in the `$j` variable are sent down the pipeline to `Receive-Job`, which gets the job results.</span></span> <span data-ttu-id="047f4-126">Die-Objekte werden in der- `$results` Variable gespeichert.</span><span class="sxs-lookup"><span data-stu-id="047f4-126">The objects are stored in the `$results` variable.</span></span> <span data-ttu-id="047f4-127">Die `$results` Variable zeigt die Auftrags Informationen in der PowerShell-Konsole an.</span><span class="sxs-lookup"><span data-stu-id="047f4-127">The `$results` variable displays the job information in the PowerShell console.</span></span>

### <span data-ttu-id="047f4-128">Beispiel 4: Herunterfahren eines Remote Computers</span><span class="sxs-lookup"><span data-stu-id="047f4-128">Example 4: Shut down a remote computer</span></span>

<span data-ttu-id="047f4-129">In diesem Beispiel wird ein Remote Computer mithilfe der angegebenen Authentifizierung heruntergefahren.</span><span class="sxs-lookup"><span data-stu-id="047f4-129">This example shuts down a remote computer using specified authentication.</span></span>

```powershell
Stop-Computer -ComputerName "Server01" -WsmanAuthentication Kerberos
```

<span data-ttu-id="047f4-130">`Stop-Computer` verwendet den **Computername** -Parameter, um den Remote Computer anzugeben.</span><span class="sxs-lookup"><span data-stu-id="047f4-130">`Stop-Computer` uses the **ComputerName** parameter to specify the remote computer.</span></span> <span data-ttu-id="047f4-131">Der **wsmanauthentication** -Parameter gibt an, dass Kerberos verwendet werden soll, um eine Remote Verbindung herzustellen.</span><span class="sxs-lookup"><span data-stu-id="047f4-131">The **WsmanAuthentication** parameter specifies to use Kerberos to establish a remote connection.</span></span>

### <span data-ttu-id="047f4-132">Beispiel 5: Herunterfahren von Computern in einer Domäne</span><span class="sxs-lookup"><span data-stu-id="047f4-132">Example 5: Shut down computers in a domain</span></span>

<span data-ttu-id="047f4-133">In diesem Beispiel erzwingen die Befehle ein sofortiges Herunterfahren aller Computer in einer angegebenen Domäne.</span><span class="sxs-lookup"><span data-stu-id="047f4-133">In this example, the commands force an immediate shut down of all computers in a specified domain.</span></span>

```powershell
$s = Get-Content -Path ./Domain01.txt
$c = Get-Credential -Credential Domain01\Admin01
Stop-Computer -ComputerName $s -Force -Credential $c
```

<span data-ttu-id="047f4-134">`Get-Content` verwendet den **path** -Parameter, um eine Datei im aktuellen Verzeichnis mit der Liste der Domänen Computer zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="047f4-134">`Get-Content` uses the **Path** parameter to get a file in the current directory with the list of domain computers.</span></span> <span data-ttu-id="047f4-135">Die-Objekte werden in der- `$s` Variable gespeichert.</span><span class="sxs-lookup"><span data-stu-id="047f4-135">The objects are stored in the `$s` variable.</span></span>

<span data-ttu-id="047f4-136">`Get-Credential` verwendet den **Credential** -Parameter, um die Anmelde Informationen eines Domänen Administrators anzugeben.</span><span class="sxs-lookup"><span data-stu-id="047f4-136">`Get-Credential` uses the **Credential** parameter to specify the credentials of a domain administrator.</span></span> <span data-ttu-id="047f4-137">Die Anmelde Informationen werden in der `$c` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="047f4-137">The credentials are stored in the `$c` variable.</span></span>

<span data-ttu-id="047f4-138">`Stop-Computer` fährt die Computer herunter, die mit der Liste der Computer des Computer **Name** -Parameters in der Variablen angegeben werden `$s` .</span><span class="sxs-lookup"><span data-stu-id="047f4-138">`Stop-Computer` shuts down the computers specified with the **ComputerName** parameter's list of computers in the `$s` variable.</span></span> <span data-ttu-id="047f4-139">Der **Force** -Parameter erzwingt ein sofortiges Herunterfahren.</span><span class="sxs-lookup"><span data-stu-id="047f4-139">The **Force** parameter forces an immediate shutdown.</span></span> <span data-ttu-id="047f4-140">Mit dem **Credential** -Parameter werden die in der Variablen gespeicherten Anmelde Informationen übermittelt `$c` .</span><span class="sxs-lookup"><span data-stu-id="047f4-140">The **Credential** parameter submits the credentials saved in the `$c` variable.</span></span>

## <span data-ttu-id="047f4-141">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="047f4-141">PARAMETERS</span></span>

### <span data-ttu-id="047f4-142">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="047f4-142">-ComputerName</span></span>

<span data-ttu-id="047f4-143">Gibt die zu stoppenden Computer an.</span><span class="sxs-lookup"><span data-stu-id="047f4-143">Specifies the computers to stop.</span></span> <span data-ttu-id="047f4-144">Die Standardeinstellung ist der lokale Computer.</span><span class="sxs-lookup"><span data-stu-id="047f4-144">The default is the local computer.</span></span>

<span data-ttu-id="047f4-145">Geben Sie den NetBIOS-Namen, die IP-Adresse oder den vollqualifizierten Domänennamen eines Computers oder mehrerer Computer in einer durch Trennzeichen getrennten Liste ein.</span><span class="sxs-lookup"><span data-stu-id="047f4-145">Type the NETBIOS name, IP address, or fully qualified domain name of one or more computers in a comma-separated list.</span></span> <span data-ttu-id="047f4-146">Geben Sie den Computernamen oder localhost ein, um den lokalen Computer anzugeben.</span><span class="sxs-lookup"><span data-stu-id="047f4-146">To specify the local computer, type the computer name or localhost.</span></span>

<span data-ttu-id="047f4-147">Dieser Parameter beruht nicht auf PowerShell-Remoting.</span><span class="sxs-lookup"><span data-stu-id="047f4-147">This parameter doesn't rely on PowerShell remoting.</span></span> <span data-ttu-id="047f4-148">Sie können den **Computername** -Parameter auch dann verwenden, wenn der Computer nicht für das Ausführen von Remote Befehlen konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="047f4-148">You can use the **ComputerName** parameter even if your computer isn't configured to run remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN, __SERVER, Server, IPAddress

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="047f4-149">-Confirm</span><span class="sxs-lookup"><span data-stu-id="047f4-149">-Confirm</span></span>

<span data-ttu-id="047f4-150">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="047f4-150">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="047f4-151">-Credential</span><span class="sxs-lookup"><span data-stu-id="047f4-151">-Credential</span></span>

<span data-ttu-id="047f4-152">Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="047f4-152">Specifies a user account that has permission to do this action.</span></span> <span data-ttu-id="047f4-153">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="047f4-153">The default is the current user.</span></span>

<span data-ttu-id="047f4-154">Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01** , oder geben Sie ein **PSCredential** -Objekt ein, das vom `Get-Credential` Cmdlet generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="047f4-154">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="047f4-155">Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe des Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="047f4-155">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="047f4-156">Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.</span><span class="sxs-lookup"><span data-stu-id="047f4-156">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="047f4-157">Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="047f4-157">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="047f4-158">-Force</span><span class="sxs-lookup"><span data-stu-id="047f4-158">-Force</span></span>

<span data-ttu-id="047f4-159">Erzwingt ein sofortiges Herunterfahren des Computers.</span><span class="sxs-lookup"><span data-stu-id="047f4-159">Forces an immediate shut down of the computer.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="047f4-160">-Wsmanauthentication</span><span class="sxs-lookup"><span data-stu-id="047f4-160">-WsmanAuthentication</span></span>

<span data-ttu-id="047f4-161">Gibt den Mechanismus an, der verwendet wird, um die Benutzer Anmelde Informationen zu authentifizieren, wenn dieses Cmdlet das WSMAN-Protokoll verwendet.</span><span class="sxs-lookup"><span data-stu-id="047f4-161">Specifies the mechanism that is used to authenticate the user credentials when this cmdlet uses the WSMan protocol.</span></span> <span data-ttu-id="047f4-162">Der Standardwert lautet **Default**.</span><span class="sxs-lookup"><span data-stu-id="047f4-162">The default value is **Default**.</span></span>

<span data-ttu-id="047f4-163">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="047f4-163">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="047f4-164">Einfach</span><span class="sxs-lookup"><span data-stu-id="047f4-164">Basic</span></span>
- <span data-ttu-id="047f4-165">CredSSP</span><span class="sxs-lookup"><span data-stu-id="047f4-165">CredSSP</span></span>
- <span data-ttu-id="047f4-166">Standard</span><span class="sxs-lookup"><span data-stu-id="047f4-166">Default</span></span>
- <span data-ttu-id="047f4-167">Digest</span><span class="sxs-lookup"><span data-stu-id="047f4-167">Digest</span></span>
- <span data-ttu-id="047f4-168">Kerberos</span><span class="sxs-lookup"><span data-stu-id="047f4-168">Kerberos</span></span>
- <span data-ttu-id="047f4-169">Negotiate</span><span class="sxs-lookup"><span data-stu-id="047f4-169">Negotiate.</span></span>

<span data-ttu-id="047f4-170">Weitere Informationen zu den Werten dieses Parameters finden Sie unter [authenticationmechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span><span class="sxs-lookup"><span data-stu-id="047f4-170">For more information about the values of this parameter, see [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!CAUTION]
> <span data-ttu-id="047f4-171">Die Authentifizierung des Anmelde Informations Diensts (Credential Security Service Provider, kredssp), in der die Benutzer Anmelde Informationen an einen Remote Computer übergeben werden, der authentifiziert werden soll, wurde für Befehle entworfen, die eine Authentifizierung auf mehreren Ressourcen erfordern</span><span class="sxs-lookup"><span data-stu-id="047f4-171">Credential Security Service Provider (CredSSP) authentication, in which the user credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="047f4-172">Dieser Mechanismus erhöht das Sicherheitsrisiko des Remotevorgangs.</span><span class="sxs-lookup"><span data-stu-id="047f4-172">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="047f4-173">Wenn die Sicherheit des Remotecomputers gefährdet ist, können die an ihn übergebenen Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="047f4-173">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

<span data-ttu-id="047f4-174">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="047f4-174">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Default, Basic, Negotiate, CredSSP, Digest, Kerberos

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="047f4-175">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="047f4-175">-WhatIf</span></span>

<span data-ttu-id="047f4-176">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="047f4-176">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="047f4-177">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="047f4-177">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="047f4-178">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="047f4-178">CommonParameters</span></span>

<span data-ttu-id="047f4-179">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="047f4-179">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="047f4-180">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="047f4-180">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="047f4-181">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="047f4-181">INPUTS</span></span>

### <span data-ttu-id="047f4-182">Keine</span><span class="sxs-lookup"><span data-stu-id="047f4-182">None</span></span>

<span data-ttu-id="047f4-183">Eingaben können nicht an dieses Cmdlet übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="047f4-183">You can't pipe input to this cmdlet.</span></span>

## <span data-ttu-id="047f4-184">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="047f4-184">OUTPUTS</span></span>

### <span data-ttu-id="047f4-185">Keine</span><span class="sxs-lookup"><span data-stu-id="047f4-185">None</span></span>

## <span data-ttu-id="047f4-186">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="047f4-186">NOTES</span></span>

<span data-ttu-id="047f4-187">Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="047f4-187">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="047f4-188">Dieses Cmdlet funktioniert nur unter Windows und verwendet die **Win32Shutdown** -Methode der WMI-Klasse **Win32_OperatingSystem** .</span><span class="sxs-lookup"><span data-stu-id="047f4-188">This cmdlet only works on Windows and uses the **Win32Shutdown** method of the **Win32_OperatingSystem** WMI class.</span></span> <span data-ttu-id="047f4-189">Diese Methode erfordert, dass die **SeShutdownPrivilege** -Berechtigung für das Benutzerkonto aktiviert ist, mit dem der Computer neu gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="047f4-189">This method requires the **SeShutdownPrivilege** privilege be enabled for the user account used to restart the machine.</span></span>

## <span data-ttu-id="047f4-190">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="047f4-190">RELATED LINKS</span></span>

[<span data-ttu-id="047f4-191">Rename-Computer</span><span class="sxs-lookup"><span data-stu-id="047f4-191">Rename-Computer</span></span>](Rename-Computer.md)

[<span data-ttu-id="047f4-192">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="047f4-192">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="047f4-193">Test-Connection</span><span class="sxs-lookup"><span data-stu-id="047f4-193">Test-Connection</span></span>](Test-Connection.md)
